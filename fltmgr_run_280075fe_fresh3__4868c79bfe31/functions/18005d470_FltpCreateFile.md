# FltpCreateFile

- ea: `0x18005d470`
- end: `0x18005d845`
- name: `FltpCreateFile`
- size: `981`
- prototype: `__int64 __fastcall(_QWORD *FltObject, __int64, PHANDLE FileHandle, PVOID *, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, PLARGE_INTEGER AllocationSize, ULONG FileAttributes, ULONG ShareAccess, ULONG Disposition, ULONG CreateOptions, PVOID EaBuffer, ULONG EaLength, ULONG Options, __int16 *EcpContextSize)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18005d200`
- `0x18005d2b0`
- `0x18005d3c0`

## callees

- `0x180009f20`
- `0x18005d470`
- `0x18005d850`
- `0x18005dc10`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18005d79b`
- `ntoskrnl!ObfDereferenceObject` at `0x18005d809`
- `ntoskrnl!ObfDereferenceObject` at `0x18005d79b`
- `ntoskrnl!ObfDereferenceObject` at `0x18005d809`
- `ntoskrnl!ZwClose` at `0x18005d774`
- `ntoskrnl!ZwClose` at `0x18005d819`
- `ntoskrnl!ZwClose` at `0x18005d774`
- `ntoskrnl!ZwClose` at `0x18005d819`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005d61c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005d61c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005d834`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005d834`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005d7be`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005d7be`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005d6d6`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005d6d6`
- `ntoskrnl!IoFileObjectType` at `0x18005d5f3`
- `ntoskrnl!IoCreateFileEx` at `0x18005d5ca`
- `ntoskrnl!IoCreateFileEx` at `0x18005d5ca`

## pseudocode

```c
__int64 __fastcall FltpCreateFile(
        _QWORD *FltObject,
        __int64 a2,
        PHANDLE FileHandle,
        PVOID *a4,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        PLARGE_INTEGER AllocationSize,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG Disposition,
        ULONG CreateOptions,
        PVOID EaBuffer,
        ULONG EaLength,
        ULONG Options,
        __int16 *EcpContextSize)
{
  bool v18; // bl
  _BYTE *v20; // rdi
  unsigned int v21; // r15d
  unsigned int ECP; // esi
  int v23; // eax
  int v24; // eax
  struct _ECP_LIST *ExtraCreateParameter; // rcx
  unsigned __int16 v27; // dx
  void *v28; // rcx
  unsigned int v29; // eax
  PVOID Object; // [rsp+80h] [rbp-41h] BYREF
  PVOID EcpContext; // [rsp+88h] [rbp-39h] BYREF
  PVOID v32; // [rsp+90h] [rbp-31h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-29h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-9h]

  v34 = 1;
  v18 = 0;
  Object = 0;
  EcpContext = 0;
  v32 = 0;
  v20 = 0;
  v21 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  if ( EcpContextSize )
  {
    v27 = *EcpContextSize;
    if ( (unsigned __int16)*EcpContextSize < 0x20u || *((_QWORD *)EcpContextSize + 2) )
    {
      ECP = -1073741811;
      goto LABEL_10;
    }
    DriverContext.ExtraCreateParameter = (struct _ECP_LIST *)*((_QWORD *)EcpContextSize + 1);
    DriverContext.TxnParameters = (PTXN_PARAMETER_BLOCK)*((_QWORD *)EcpContextSize + 3);
    if ( v27 >= 0x28u )
      v34 = *((_QWORD *)EcpContextSize + 4);
  }
  ECP = TargetedIOCtrlGenerateECP(
          (int)&EcpContext,
          0,
          0,
          FltObject[7],
          FltObject,
          a2,
          0,
          &DriverContext.ExtraCreateParameter,
          (__int64)&v32);
  v23 = FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2854, 3223060491LL);
  v20 = EcpContext;
  if ( v23 >= 0 )
  {
    v18 = (*((_BYTE *)EcpContext + 6) & 8) != 0;
    if ( a2 )
      DriverContext.DeviceObjectHint = *(PVOID *)(*(_QWORD *)(a2 + 64) + 64LL);
    ECP = IoCreateFileEx(
            FileHandle,
            DesiredAccess,
            ObjectAttributes,
            IoStatusBlock,
            AllocationSize,
            FileAttributes,
            ShareAccess,
            Disposition,
            CreateOptions,
            EaBuffer,
            EaLength,
            CreateFileTypeNone,
            0,
            Options,
            &DriverContext);
    if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2915, 0) >= 0 )
    {
      v21 = ECP;
      ECP = ObReferenceObjectByHandle(*FileHandle, DesiredAccess, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2945, 0) < 0 )
      {
        v28 = *FileHandle;
        Object = 0;
        ZwClose(v28);
      }
      else if ( (*((_DWORD *)Object + 20) & 0x800) != 0 )
      {
        ECP = -1073741811;
        ObfDereferenceObject(Object);
        ZwClose(*FileHandle);
      }
      else if ( a4 )
      {
        *a4 = Object;
      }
      else
      {
        ObfDereferenceObject(Object);
      }
    }
  }
LABEL_10:
  if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3009, 0) < 0 )
  {
    *FileHandle = 0;
    if ( a4 )
      *a4 = 0;
  }
  if ( v20 )
  {
    v24 = FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3021, 0);
    ExtraCreateParameter = DriverContext.ExtraCreateParameter;
    EcpContext = 0;
    if ( v24 < 0 )
      v20 = 0;
    LODWORD(EcpContextSize) = 0;
    if ( DriverContext.ExtraCreateParameter )
    {
      if ( !v20 || (v20[6] & 1) == 0 )
      {
        v29 = FsRtlRemoveExtraCreateParameter(
                DriverContext.ExtraCreateParameter,
                &FLTMGR_TIOCTRL_ECP_GUID,
                &EcpContext,
                (ULONG *)&EcpContextSize);
        if ( (int)FltpDbgStatus(v29, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 654, 0) >= 0 )
        {
          *((_WORD *)EcpContext + 3) &= ~0x10u;
          FreeTargetedIoCtrl(EcpContext);
        }
        ExtraCreateParameter = DriverContext.ExtraCreateParameter;
      }
      if ( v18 )
      {
        FsRtlFreeExtraCreateParameterList(ExtraCreateParameter);
        ExtraCreateParameter = 0;
        DriverContext.ExtraCreateParameter = 0;
      }
    }
    if ( v32 )
      FsRtlInsertExtraCreateParameter(ExtraCreateParameter, v32);
  }
  if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3058, 0) < 0 )
    return ECP;
  return v21;
}

```

## disassembly

```asm
0x18005d470  push    rbp
0x18005d472  push    rbx
0x18005d473  push    rsi
0x18005d474  push    rdi
0x18005d475  push    r12
0x18005d477  push    r13
0x18005d479  push    r14
0x18005d47b  push    r15
0x18005d47d  lea     rbp, [rsp-7]
0x18005d482  sub     rsp, 0C8h
0x18005d489  xorps   xmm0, xmm0
0x18005d48c  mov     [rbp+3Fh+var_48], 1
0x18005d494  mov     r13, r9
0x18005d497  mov     r12, r8
0x18005d49a  xor     r8d, r8d; int
0x18005d49d  mov     r9, rcx
0x18005d4a0  mov     rcx, [rbp+3Fh+EcpContextSize]
0x18005d4a7  xor     bl, bl
0x18005d4a9  mov     [rbp+3Fh+Object], r8
0x18005d4ad  mov     eax, 28h ; '('
0x18005d4b2  mov     [rbp+3Fh+EcpContext], r8
0x18005d4b6  mov     r14, rdx
0x18005d4b9  mov     [rbp+3Fh+var_70], r8
0x18005d4bd  mov     edi, r8d
0x18005d4c0  mov     r15d, r8d
0x18005d4c3  movups  xmmword ptr [rbp+3Fh+var_68.Size], xmm0
0x18005d4c7  mov     [rbp+3Fh+var_68.Size], ax
0x18005d4cb  movups  xmmword ptr [rbp+3Fh+var_68.DeviceObjectHint], xmm0
0x18005d4cf  test    rcx, rcx
0x18005d4d2  jnz     loc_18005D72B
0x18005d4d8  lea     rax, [rbp+3Fh+var_70]
0x18005d4dc  xor     edx, edx; int
0x18005d4de  mov     qword ptr [rsp+100h+CreateOptions], rax; __int64
0x18005d4e3  lea     rcx, [rbp+3Fh+EcpContext]; int
0x18005d4e7  lea     rax, [rbp+3Fh+var_68.ExtraCreateParameter]
0x18005d4eb  mov     qword ptr [rsp+100h+Disposition], rax; EcpList
0x18005d4f0  mov     qword ptr [rsp+100h+ShareAccess], r8; PVOID
0x18005d4f5  mov     qword ptr [rsp+100h+FileAttributes], r14; __int64
0x18005d4fa  mov     [rsp+100h+AllocationSize], r9; FltObject
0x18005d4ff  mov     r9, [r9+38h]; int
0x18005d503  call    TargetedIOCtrlGenerateECP
0x18005d508  mov     r8d, 0B26h
0x18005d50e  mov     [rsp+100h+AllocationSize], rdi
0x18005d513  mov     r9d, 0C01C000Bh
0x18005d519  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d520  mov     ecx, eax
0x18005d522  mov     esi, eax
0x18005d524  call    FltpDbgStatus
0x18005d529  mov     rdi, [rbp+3Fh+EcpContext]
0x18005d52d  test    eax, eax
0x18005d52f  js      loc_18005D667
0x18005d535  movzx   ebx, byte ptr [rdi+6]
0x18005d539  shr     bl, 3
0x18005d53c  and     bl, 1
0x18005d53f  test    r14, r14
0x18005d542  jz      short loc_18005D550
0x18005d544  mov     rax, [r14+40h]
0x18005d548  mov     rcx, [rax+40h]
0x18005d54c  mov     [rbp+3Fh+var_68.DeviceObjectHint], rcx
0x18005d550  mov     r14d, [rbp+3Fh+DesiredAccess]
0x18005d554  lea     rax, [rbp+3Fh+var_68]
0x18005d558  mov     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x18005d55c  mov     edx, r14d; DesiredAccess
0x18005d55f  mov     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18005d563  mov     rcx, r12; FileHandle
0x18005d566  mov     [rsp+100h+DriverContext], rax; DriverContext
0x18005d56b  mov     eax, [rbp+3Fh+arg_70]
0x18005d571  mov     [rsp+100h+Options], eax; Options
0x18005d575  xor     eax, eax
0x18005d577  mov     [rsp+100h+InternalParameters], rax; InternalParameters
0x18005d57c  mov     [rsp+100h+CreateFileType], eax; CreateFileType
0x18005d580  mov     eax, [rbp+3Fh+arg_68]
0x18005d586  mov     [rsp+100h+EaLength], eax; EaLength
0x18005d58a  mov     rax, [rbp+3Fh+arg_60]
0x18005d591  mov     [rsp+100h+EaBuffer], rax; EaBuffer
0x18005d596  mov     eax, [rbp+3Fh+arg_58]
0x18005d59c  mov     [rsp+100h+CreateOptions], eax; CreateOptions
0x18005d5a0  mov     eax, [rbp+3Fh+arg_50]
0x18005d5a6  mov     [rsp+100h+Disposition], eax; Disposition
0x18005d5aa  mov     eax, [rbp+3Fh+arg_48]
0x18005d5b0  mov     [rsp+100h+ShareAccess], eax; ShareAccess
0x18005d5b4  mov     eax, [rbp+3Fh+arg_40]
0x18005d5ba  mov     [rsp+100h+FileAttributes], eax; FileAttributes
0x18005d5be  mov     rax, [rbp+3Fh+arg_38]
0x18005d5c5  mov     [rsp+100h+AllocationSize], rax; AllocationSize
0x18005d5ca  call    cs:__imp_IoCreateFileEx
0x18005d5d1  nop     dword ptr [rax+rax+00h]
0x18005d5d6  mov     r8d, 0B63h
0x18005d5dc  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d5e3  mov     ecx, eax
0x18005d5e5  xor     r9d, r9d
0x18005d5e8  mov     esi, eax
0x18005d5ea  call    FltpDbgStatus
0x18005d5ef  test    eax, eax
0x18005d5f1  js      short loc_18005D667
0x18005d5f3  mov     r8, cs:__imp_IoFileObjectType
0x18005d5fa  lea     rax, [rbp+3Fh+Object]
0x18005d5fe  mov     rcx, [r12]; Handle
0x18005d602  xor     r9d, r9d; AccessMode
0x18005d605  mov     qword ptr [rsp+100h+FileAttributes], 0; HandleInformation
0x18005d60e  mov     edx, r14d; DesiredAccess
0x18005d611  mov     r15d, esi
0x18005d614  mov     [rsp+100h+AllocationSize], rax; Object
0x18005d619  mov     r8, [r8]; ObjectType
0x18005d61c  call    cs:__imp_ObReferenceObjectByHandle
0x18005d623  nop     dword ptr [rax+rax+00h]
0x18005d628  mov     r8d, 0B81h
0x18005d62e  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d635  mov     ecx, eax
0x18005d637  xor     r9d, r9d
0x18005d63a  mov     esi, eax
0x18005d63c  call    FltpDbgStatus
0x18005d641  test    eax, eax
0x18005d643  js      loc_18005D769
0x18005d649  mov     rcx, [rbp+3Fh+Object]; Object
0x18005d64d  test    dword ptr [rcx+50h], 800h
0x18005d654  jnz     loc_18005D804
0x18005d65a  test    r13, r13
0x18005d65d  jz      loc_18005D79B
0x18005d663  mov     [r13+0], rcx
0x18005d667  xor     r14d, r14d
0x18005d66a  mov     r8d, 0BC1h
0x18005d670  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d677  xor     r9d, r9d
0x18005d67a  mov     ecx, esi
0x18005d67c  call    FltpDbgStatus
0x18005d681  test    eax, eax
0x18005d683  js      loc_18005D785
0x18005d689  test    rdi, rdi
0x18005d68c  jz      short loc_18005D6F6
0x18005d68e  xor     r9d, r9d
0x18005d691  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d698  mov     r8d, 0BCDh
0x18005d69e  mov     ecx, esi
0x18005d6a0  call    FltpDbgStatus
0x18005d6a5  mov     rcx, [rbp+3Fh+var_68.ExtraCreateParameter]; EcpList
0x18005d6a9  test    eax, eax
0x18005d6ab  mov     [rbp+3Fh+EcpContext], r14
0x18005d6af  cmovs   rdi, r14
0x18005d6b3  mov     dword ptr [rbp+3Fh+EcpContextSize], r14d
0x18005d6ba  test    rcx, rcx
0x18005d6bd  jz      short loc_18005D6E9
0x18005d6bf  test    rdi, rdi
0x18005d6c2  jz      loc_18005D7AC
0x18005d6c8  test    byte ptr [rdi+6], 1
0x18005d6cc  jz      loc_18005D7AC
0x18005d6d2  test    bl, bl
0x18005d6d4  jz      short loc_18005D6E9
0x18005d6d6  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x18005d6dd  nop     dword ptr [rax+rax+00h]
0x18005d6e2  mov     rcx, r14; EcpList
0x18005d6e5  mov     [rbp+3Fh+var_68.ExtraCreateParameter], rcx
0x18005d6e9  mov     rdx, [rbp+3Fh+var_70]; EcpContext
0x18005d6ed  test    rdx, rdx
0x18005d6f0  jnz     loc_18005D834
0x18005d6f6  mov     r8d, 0BF2h
0x18005d6fc  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005d703  xor     r9d, r9d
0x18005d706  mov     ecx, esi
0x18005d708  call    FltpDbgStatus
0x18005d70d  test    eax, eax
0x18005d70f  cmovs   r15d, esi
0x18005d713  mov     eax, r15d
0x18005d716  add     rsp, 0C8h
0x18005d71d  pop     r15
0x18005d71f  pop     r14
0x18005d721  pop     r13
0x18005d723  pop     r12
0x18005d725  pop     rdi
0x18005d726  pop     rsi
0x18005d727  pop     rbx
0x18005d728  pop     rbp
0x18005d729  retn
0x18005d72b  movzx   edx, word ptr [rcx]
0x18005d72e  cmp     dx, 20h ; ' '
0x18005d732  jb      loc_18005D82A
0x18005d738  cmp     [rcx+10h], rdi
0x18005d73c  jnz     loc_18005D82A
0x18005d742  mov     rax, [rcx+8]
0x18005d746  mov     [rbp+3Fh+var_68.ExtraCreateParameter], rax
0x18005d74a  mov     rax, [rcx+18h]
0x18005d74e  mov     [rbp+3Fh+var_68.TxnParameters], rax
0x18005d752  cmp     dx, 28h ; '('
0x18005d756  jb      loc_18005D4D8
0x18005d75c  mov     rax, [rcx+20h]
0x18005d760  mov     [rbp+3Fh+var_48], rax
0x18005d764  jmp     loc_18005D4D8
0x18005d769  mov     rcx, [r12]; Handle
0x18005d76d  xor     r14d, r14d
0x18005d770  mov     [rbp+3Fh+Object], r14
0x18005d774  call    cs:__imp_ZwClose
0x18005d77b  nop     dword ptr [rax+rax+00h]
0x18005d780  jmp     loc_18005D66A
0x18005d785  mov     [r12], r14
0x18005d789  test    r13, r13
0x18005d78c  jz      loc_18005D689
0x18005d792  mov     [r13+0], r14
0x18005d796  jmp     loc_18005D689
0x18005d79b  call    cs:__imp_ObfDereferenceObject
0x18005d7a2  nop     dword ptr [rax+rax+00h]
0x18005d7a7  jmp     loc_18005D667
0x18005d7ac  lea     r9, [rbp+3Fh+EcpContextSize]; EcpContextSize
0x18005d7b3  lea     r8, [rbp+3Fh+EcpContext]; EcpContext
0x18005d7b7  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18005d7be  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x18005d7c5  nop     dword ptr [rax+rax+00h]
0x18005d7ca  mov     r8d, 28Eh
0x18005d7d0  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005d7d7  mov     ecx, eax
0x18005d7d9  xor     r9d, r9d
0x18005d7dc  call    FltpDbgStatus
0x18005d7e1  test    eax, eax
0x18005d7e3  js      short loc_18005D7FB
0x18005d7e5  mov     rax, [rbp+3Fh+EcpContext]
0x18005d7e9  mov     ecx, 0FFEFh
0x18005d7ee  and     [rax+6], cx
0x18005d7f2  mov     rcx, [rbp+3Fh+EcpContext]; EcpContext
0x18005d7f6  call    FreeTargetedIoCtrl
0x18005d7fb  mov     rcx, [rbp+3Fh+var_68.ExtraCreateParameter]
0x18005d7ff  jmp     loc_18005D6D2
0x18005d804  mov     esi, 0C000000Dh
0x18005d809  call    cs:__imp_ObfDereferenceObject
0x18005d810  nop     dword ptr [rax+rax+00h]
0x18005d815  mov     rcx, [r12]; Handle
0x18005d819  call    cs:__imp_ZwClose
0x18005d820  nop     dword ptr [rax+rax+00h]
0x18005d825  jmp     loc_18005D667
0x18005d82a  mov     esi, 0C000000Dh
0x18005d82f  jmp     loc_18005D667
0x18005d834  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005d83b  nop     dword ptr [rax+rax+00h]
0x18005d840  jmp     loc_18005D6F6
```

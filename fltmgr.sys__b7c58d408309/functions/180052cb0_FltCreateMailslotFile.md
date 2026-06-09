# FltCreateMailslotFile

- ea: `0x180052cb0`
- end: `0x180052ff8`
- name: `FltCreateMailslotFile`
- size: `840`
- prototype: `__int64 __fastcall(_QWORD *FltObject, __int64, PHANDLE FileHandle, PVOID *, ACCESS_MASK DesiredAccess, OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, ULONG CreateOptions, unsigned int, unsigned int, _QWORD *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180052cb0`
- `0x18005d850`
- `0x18005df50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180052fc9`
- `ntoskrnl!ObfDereferenceObject` at `0x180052fe7`
- `ntoskrnl!ObfDereferenceObject` at `0x180052fc9`
- `ntoskrnl!ObfDereferenceObject` at `0x180052fe7`
- `ntoskrnl!ZwClose` at `0x180052ef0`
- `ntoskrnl!ZwClose` at `0x180052ef0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180052ebc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180052ebc`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x180052f6a`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x180052f6a`
- `ntoskrnl!IoFileObjectType` at `0x180052e98`
- `ntoskrnl!IoCreateFileEx` at `0x180052e6f`
- `ntoskrnl!IoCreateFileEx` at `0x180052e6f`

## pseudocode

```c
__int64 __fastcall FltCreateMailslotFile(
        _QWORD *FltObject,
        __int64 a2,
        PHANDLE FileHandle,
        PVOID *a4,
        ACCESS_MASK DesiredAccess,
        OBJECT_ATTRIBUTES *a6,
        struct _IO_STATUS_BLOCK *a7,
        ULONG CreateOptions,
        unsigned int a9,
        unsigned int a10,
        _QWORD *a11,
        unsigned __int16 *a12)
{
  __int64 v14; // r13
  __int64 v15; // rsi
  unsigned int v16; // r12d
  bool v17; // bl
  unsigned int ECP; // edi
  int v19; // eax
  int v20; // eax
  __int64 v21; // r8
  PVOID Object; // [rsp+80h] [rbp-71h] BYREF
  int v24[2]; // [rsp+88h] [rbp-69h] BYREF
  PVOID EcpContext; // [rsp+90h] [rbp-61h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-59h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-39h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-31h]
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-29h]
  __int128 InternalParameters; // [rsp+D0h] [rbp-21h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-11h]

  ObjectAttributes = a6;
  IoStatusBlock = a7;
  Object = 0;
  *(_QWORD *)v24 = 0;
  v14 = a2;
  EcpContext = 0;
  v15 = 0;
  v31 = 0;
  v16 = 0;
  v27 = 1;
  v17 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  InternalParameters = 0;
  if ( a12 )
  {
    LODWORD(a2) = *a12;
    if ( (unsigned __int16)a2 < 0x20u || *((_QWORD *)a12 + 2) )
    {
      ECP = -1073741811;
      goto LABEL_16;
    }
    DriverContext.ExtraCreateParameter = (struct _ECP_LIST *)*((_QWORD *)a12 + 1);
    DriverContext.TxnParameters = (PTXN_PARAMETER_BLOCK)*((_QWORD *)a12 + 3);
    if ( (unsigned __int16)a2 >= 0x28u )
      v27 = *((_QWORD *)a12 + 4);
  }
  if ( a11 )
  {
    *((_QWORD *)&InternalParameters + 1) = *a11;
    LOBYTE(v31) = 1;
  }
  *(_QWORD *)&InternalParameters = __PAIR64__(a10, a9);
  LOBYTE(a2) = 19;
  ECP = TargetedIOCtrlGenerateECP(
          (int)v24,
          a2,
          0,
          FltObject[7],
          FltObject,
          v14,
          0,
          &DriverContext.ExtraCreateParameter,
          (__int64)&EcpContext);
  v19 = FltpDbgStatus(ECP);
  v15 = *(_QWORD *)v24;
  if ( v19 >= 0 )
  {
    v17 = (*(_BYTE *)(*(_QWORD *)v24 + 6LL) & 8) != 0;
    if ( v14 )
      DriverContext.DeviceObjectHint = *(PVOID *)(*(_QWORD *)(v14 + 64) + 64LL);
    ECP = IoCreateFileEx(
            FileHandle,
            DesiredAccess,
            ObjectAttributes,
            IoStatusBlock,
            0,
            0,
            3u,
            2u,
            CreateOptions,
            0,
            0,
            CreateFileTypeMailslot,
            &InternalParameters,
            0,
            &DriverContext);
    if ( (int)FltpDbgStatus(ECP) >= 0 )
    {
      v16 = ECP;
      ECP = ObReferenceObjectByHandle(*FileHandle, DesiredAccess, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( (int)FltpDbgStatus(ECP) < 0 )
      {
        Object = 0;
LABEL_14:
        ZwClose(*FileHandle);
        goto LABEL_16;
      }
      if ( (*((_DWORD *)Object + 20) & 0x800) != 0 )
      {
        ECP = -1073741811;
        ObfDereferenceObject(Object);
        goto LABEL_14;
      }
      if ( a4 )
        *a4 = Object;
      else
        ObfDereferenceObject(Object);
    }
  }
LABEL_16:
  if ( (int)FltpDbgStatus(ECP) < 0 )
  {
    *FileHandle = 0;
    if ( a4 )
      *a4 = 0;
  }
  if ( v15 )
  {
    v20 = FltpDbgStatus(ECP);
    LOBYTE(v21) = v17;
    if ( v20 < 0 )
      v15 = 0;
    CleanupTargetedIo(v15, &DriverContext.ExtraCreateParameter, v21);
    if ( EcpContext )
      FsRtlInsertExtraCreateParameter(DriverContext.ExtraCreateParameter, EcpContext);
  }
  if ( (int)FltpDbgStatus(ECP) < 0 )
    return ECP;
  return v16;
}

```

## disassembly

```asm
0x180052cb0  push    rbp
0x180052cb2  push    rbx
0x180052cb3  push    rsi
0x180052cb4  push    rdi
0x180052cb5  push    r12
0x180052cb7  push    r13
0x180052cb9  push    r14
0x180052cbb  push    r15
0x180052cbd  lea     rbp, [rsp-7]
0x180052cc2  sub     rsp, 0F8h
0x180052cc9  mov     rax, cs:__security_cookie
0x180052cd0  xor     rax, rsp
0x180052cd3  mov     [rbp+3Fh+var_48], rax
0x180052cd7  mov     rax, [rbp+3Fh+arg_28]
0x180052cdb  xor     r10d, r10d
0x180052cde  xorps   xmm0, xmm0
0x180052ce1  mov     [rbp+3Fh+ObjectAttributes], rax
0x180052ce5  mov     rax, [rbp+3Fh+arg_30]
0x180052ce9  mov     r14, r9
0x180052cec  mov     [rbp+3Fh+IoStatusBlock], rax
0x180052cf0  mov     r9, rcx
0x180052cf3  mov     rcx, [rbp+3Fh+arg_58]
0x180052cfa  lea     r11d, [r10+28h]
0x180052cfe  xor     eax, eax
0x180052d00  mov     [rbp+3Fh+Object], r10
0x180052d04  mov     qword ptr [rbp+3Fh+var_A8], r10
0x180052d08  mov     r15, r8
0x180052d0b  mov     r8, [rbp+3Fh+arg_50]
0x180052d12  mov     r13, rdx
0x180052d15  mov     [rbp+3Fh+EcpContext], r10
0x180052d19  mov     esi, r10d
0x180052d1c  mov     [rbp+3Fh+var_50], rax
0x180052d20  mov     r12d, r10d
0x180052d23  mov     [rbp+3Fh+var_78], 1
0x180052d2b  mov     bl, r10b
0x180052d2e  movups  xmmword ptr [rbp+3Fh+var_98.Size], xmm0
0x180052d32  mov     [rbp+3Fh+var_98.Size], r11w
0x180052d37  movups  [rbp+3Fh+var_60], xmm0
0x180052d3b  movups  xmmword ptr [rbp+3Fh+var_98.DeviceObjectHint], xmm0
0x180052d3f  test    rcx, rcx
0x180052d42  jz      short loc_180052D79
0x180052d44  movzx   edx, word ptr [rcx]
0x180052d47  cmp     dx, 20h ; ' '
0x180052d4b  jb      loc_180052EFE
0x180052d51  cmp     [rcx+10h], r10
0x180052d55  jnz     loc_180052EFE
0x180052d5b  mov     rax, [rcx+8]
0x180052d5f  mov     [rbp+3Fh+var_98.ExtraCreateParameter], rax
0x180052d63  mov     rax, [rcx+18h]
0x180052d67  mov     [rbp+3Fh+var_98.TxnParameters], rax
0x180052d6b  cmp     dx, r11w
0x180052d6f  jb      short loc_180052D79
0x180052d71  mov     rax, [rcx+20h]
0x180052d75  mov     [rbp+3Fh+var_78], rax
0x180052d79  test    r8, r8
0x180052d7c  jz      short loc_180052D89
0x180052d7e  mov     rax, [r8]
0x180052d81  mov     qword ptr [rbp+3Fh+var_60+8], rax
0x180052d85  mov     byte ptr [rbp+3Fh+var_50], 1
0x180052d89  mov     eax, [rbp+3Fh+arg_40]
0x180052d8f  lea     rcx, [rbp+3Fh+var_A8]; int
0x180052d93  mov     dword ptr [rbp+3Fh+var_60], eax
0x180052d96  xor     r8d, r8d; int
0x180052d99  mov     eax, [rbp+3Fh+arg_48]
0x180052d9f  mov     dl, 13h; int
0x180052da1  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x180052da4  lea     rax, [rbp+3Fh+EcpContext]
0x180052da8  mov     qword ptr [rsp+130h+CreateOptions], rax; __int64
0x180052dad  lea     rax, [rbp+3Fh+var_98.ExtraCreateParameter]
0x180052db1  mov     qword ptr [rsp+130h+Disposition], rax; EcpList
0x180052db6  mov     qword ptr [rsp+130h+ShareAccess], r10; PVOID
0x180052dbb  mov     qword ptr [rsp+130h+FileAttributes], r13; __int64
0x180052dc0  mov     [rsp+130h+AllocationSize], r9; FltObject
0x180052dc5  mov     r9, [r9+38h]; int
0x180052dc9  call    TargetedIOCtrlGenerateECP
0x180052dce  mov     r8d, 0FE3h
0x180052dd4  mov     [rsp+130h+AllocationSize], rsi
0x180052dd9  mov     r9d, 0C01C000Bh
0x180052ddf  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052de6  mov     ecx, eax
0x180052de8  mov     edi, eax
0x180052dea  call    FltpDbgStatus
0x180052def  mov     rsi, qword ptr [rbp+3Fh+var_A8]
0x180052df3  test    eax, eax
0x180052df5  js      loc_180052F03
0x180052dfb  mov     bl, [rsi+6]
0x180052dfe  shr     bl, 3
0x180052e01  and     bl, 1
0x180052e04  test    r13, r13
0x180052e07  jz      short loc_180052E15
0x180052e09  mov     rax, [r13+40h]
0x180052e0d  mov     rcx, [rax+40h]
0x180052e11  mov     [rbp+3Fh+var_98.DeviceObjectHint], rcx
0x180052e15  mov     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180052e19  lea     rax, [rbp+3Fh+var_98]
0x180052e1d  mov     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180052e21  xor     r13d, r13d
0x180052e24  mov     edx, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x180052e27  mov     [rsp+130h+DriverContext], rax; DriverContext
0x180052e2c  lea     rax, [rbp+3Fh+var_60]
0x180052e30  mov     [rsp+130h+Options], r13d; Options
0x180052e35  mov     [rsp+130h+InternalParameters], rax; InternalParameters
0x180052e3a  lea     ecx, [r13+2]
0x180052e3e  mov     eax, [rbp+3Fh+arg_38]
0x180052e44  mov     [rsp+130h+CreateFileType], ecx; CreateFileType
0x180052e48  mov     [rsp+130h+EaLength], r13d; EaLength
0x180052e4d  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x180052e52  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x180052e56  mov     [rsp+130h+Disposition], ecx; Disposition
0x180052e5a  mov     rcx, r15; FileHandle
0x180052e5d  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x180052e65  mov     [rsp+130h+FileAttributes], r13d; FileAttributes
0x180052e6a  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x180052e6f  call    cs:__imp_IoCreateFileEx
0x180052e76  nop     dword ptr [rax+rax+00h]
0x180052e7b  mov     r8d, 1020h
0x180052e81  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052e88  mov     ecx, eax
0x180052e8a  xor     r9d, r9d
0x180052e8d  mov     edi, eax
0x180052e8f  call    FltpDbgStatus
0x180052e94  test    eax, eax
0x180052e96  js      short loc_180052F06
0x180052e98  mov     r8, cs:__imp_IoFileObjectType
0x180052e9f  lea     rax, [rbp+3Fh+Object]
0x180052ea3  mov     edx, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x180052ea6  xor     r9d, r9d; AccessMode
0x180052ea9  mov     rcx, [r15]; Handle
0x180052eac  mov     r12d, edi
0x180052eaf  mov     qword ptr [rsp+130h+FileAttributes], r13; HandleInformation
0x180052eb4  mov     r8, [r8]; ObjectType
0x180052eb7  mov     [rsp+130h+AllocationSize], rax; Object
0x180052ebc  call    cs:__imp_ObReferenceObjectByHandle
0x180052ec3  nop     dword ptr [rax+rax+00h]
0x180052ec8  mov     r8d, 103Eh
0x180052ece  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052ed5  mov     ecx, eax
0x180052ed7  xor     r9d, r9d
0x180052eda  mov     edi, eax
0x180052edc  call    FltpDbgStatus
0x180052ee1  test    eax, eax
0x180052ee3  jns     loc_180052FB7
0x180052ee9  mov     [rbp+3Fh+Object], r13
0x180052eed  mov     rcx, [r15]; Handle
0x180052ef0  call    cs:__imp_ZwClose
0x180052ef7  nop     dword ptr [rax+rax+00h]
0x180052efc  jmp     short loc_180052F06
0x180052efe  mov     edi, 0C000000Dh
0x180052f03  xor     r13d, r13d
0x180052f06  mov     r8d, 107Eh
0x180052f0c  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052f13  xor     r9d, r9d
0x180052f16  mov     ecx, edi
0x180052f18  call    FltpDbgStatus
0x180052f1d  test    eax, eax
0x180052f1f  jns     short loc_180052F2C
0x180052f21  mov     [r15], r13
0x180052f24  test    r14, r14
0x180052f27  jz      short loc_180052F2C
0x180052f29  mov     [r14], r13
0x180052f2c  test    rsi, rsi
0x180052f2f  jz      short loc_180052F76
0x180052f31  xor     r9d, r9d
0x180052f34  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052f3b  mov     r8d, 108Ah
0x180052f41  mov     ecx, edi
0x180052f43  call    FltpDbgStatus
0x180052f48  test    eax, eax
0x180052f4a  lea     rdx, [rbp+3Fh+var_98.ExtraCreateParameter]
0x180052f4e  mov     r8b, bl
0x180052f51  cmovs   rsi, r13
0x180052f55  mov     rcx, rsi
0x180052f58  call    CleanupTargetedIo
0x180052f5d  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x180052f61  test    rdx, rdx
0x180052f64  jz      short loc_180052F76
0x180052f66  mov     rcx, [rbp+3Fh+var_98.ExtraCreateParameter]; EcpList
0x180052f6a  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x180052f71  nop     dword ptr [rax+rax+00h]
0x180052f76  mov     r8d, 10AFh
0x180052f7c  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180052f83  xor     r9d, r9d
0x180052f86  mov     ecx, edi
0x180052f88  call    FltpDbgStatus
0x180052f8d  test    eax, eax
0x180052f8f  cmovs   r12d, edi
0x180052f93  mov     eax, r12d
0x180052f96  mov     rcx, [rbp+3Fh+var_48]
0x180052f9a  xor     rcx, rsp; StackCookie
0x180052f9d  call    __security_check_cookie
0x180052fa2  add     rsp, 0F8h
0x180052fa9  pop     r15
0x180052fab  pop     r14
0x180052fad  pop     r13
0x180052faf  pop     r12
0x180052fb1  pop     rdi
0x180052fb2  pop     rsi
0x180052fb3  pop     rbx
0x180052fb4  pop     rbp
0x180052fb5  retn
0x180052fb7  mov     rcx, [rbp+3Fh+Object]; Object
0x180052fbb  test    dword ptr [rcx+50h], 800h
0x180052fc2  jz      short loc_180052FDA
0x180052fc4  mov     edi, 0C000000Dh
0x180052fc9  call    cs:__imp_ObfDereferenceObject
0x180052fd0  nop     dword ptr [rax+rax+00h]
0x180052fd5  jmp     loc_180052EED
0x180052fda  test    r14, r14
0x180052fdd  jz      short loc_180052FE7
0x180052fdf  mov     [r14], rcx
0x180052fe2  jmp     loc_180052F06
0x180052fe7  call    cs:__imp_ObfDereferenceObject
0x180052fee  nop     dword ptr [rax+rax+00h]
0x180052ff3  jmp     loc_180052F06
```

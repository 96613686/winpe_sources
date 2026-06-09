# FltCreateNamedPipeFile

- ea: `0x180053000`
- end: `0x18005337b`
- name: `FltCreateNamedPipeFile`
- size: `891`
- prototype: `__int64 __fastcall(_QWORD *FltObject, __int64, PHANDLE FileHandle, PVOID *, ACCESS_MASK DesiredAccess, OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, ULONG ShareAccess, ULONG Disposition, ULONG CreateOptions, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, _QWORD *, __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180053000`
- `0x18005d850`
- `0x18005df50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18005334c`
- `ntoskrnl!ObfDereferenceObject` at `0x18005336a`
- `ntoskrnl!ObfDereferenceObject` at `0x18005334c`
- `ntoskrnl!ObfDereferenceObject` at `0x18005336a`
- `ntoskrnl!ZwClose` at `0x180053273`
- `ntoskrnl!ZwClose` at `0x180053273`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005323f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005323f`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1800532ed`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1800532ed`
- `ntoskrnl!IoFileObjectType` at `0x18005321b`
- `ntoskrnl!IoCreateFileEx` at `0x1800531f2`
- `ntoskrnl!IoCreateFileEx` at `0x1800531f2`

## pseudocode

```c
__int64 __fastcall FltCreateNamedPipeFile(
        _QWORD *FltObject,
        __int64 a2,
        PHANDLE FileHandle,
        PVOID *a4,
        ACCESS_MASK DesiredAccess,
        OBJECT_ATTRIBUTES *a6,
        struct _IO_STATUS_BLOCK *a7,
        ULONG ShareAccess,
        ULONG Disposition,
        ULONG CreateOptions,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15,
        unsigned int a16,
        _QWORD *a17,
        __int16 *a18)
{
  __int64 v21; // rsi
  unsigned int v22; // r12d
  bool v23; // bl
  unsigned __int16 v24; // dx
  unsigned int v25; // edi
  int v26; // eax
  int v27; // eax
  __int64 v28; // r8
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  int v31[2]; // [rsp+88h] [rbp-78h] BYREF
  PVOID EcpContext; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-48h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h]
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h]
  __int128 InternalParameters; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+F0h] [rbp-10h]

  ObjectAttributes = a6;
  IoStatusBlock = a7;
  Object = 0;
  *(_QWORD *)v31 = 0;
  EcpContext = 0;
  v21 = 0;
  v39 = 0;
  v22 = 0;
  v34 = 1;
  v23 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  InternalParameters = 0;
  v38 = 0;
  if ( a18 )
  {
    v24 = *a18;
    if ( (unsigned __int16)*a18 < 0x20u || *((_QWORD *)a18 + 2) )
    {
      v25 = -1073741811;
      goto LABEL_16;
    }
    DriverContext.ExtraCreateParameter = (struct _ECP_LIST *)*((_QWORD *)a18 + 1);
    DriverContext.TxnParameters = (PTXN_PARAMETER_BLOCK)*((_QWORD *)a18 + 3);
    if ( v24 >= 0x28u )
      v34 = *((_QWORD *)a18 + 4);
  }
  if ( a17 )
  {
    *((_QWORD *)&v38 + 1) = *a17;
    LOBYTE(v39) = 1;
  }
  *(_QWORD *)&InternalParameters = __PAIR64__(a12, a11);
  *((_QWORD *)&InternalParameters + 1) = __PAIR64__(a14, a13);
  *(_QWORD *)&v38 = __PAIR64__(a16, a15);
  v25 = TargetedIOCtrlGenerateECP(
          (PVOID *)v31,
          1,
          0,
          FltObject[7],
          FltObject,
          a2,
          0,
          &DriverContext.ExtraCreateParameter,
          &EcpContext);
  v26 = FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3707, 3223060491LL);
  v21 = *(_QWORD *)v31;
  if ( v26 >= 0 )
  {
    v23 = (*(_BYTE *)(*(_QWORD *)v31 + 6LL) & 8) != 0;
    if ( a2 )
      DriverContext.DeviceObjectHint = *(PVOID *)(*(_QWORD *)(a2 + 64) + 64LL);
    v25 = IoCreateFileEx(
            FileHandle,
            DesiredAccess,
            ObjectAttributes,
            IoStatusBlock,
            0,
            0,
            ShareAccess,
            Disposition,
            CreateOptions,
            0,
            0,
            CreateFileTypeNamedPipe,
            &InternalParameters,
            0,
            &DriverContext);
    if ( (int)FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3768, 0) >= 0 )
    {
      v22 = v25;
      v25 = ObReferenceObjectByHandle(*FileHandle, DesiredAccess, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( (int)FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3798, 0) < 0 )
      {
        Object = 0;
LABEL_14:
        ZwClose(*FileHandle);
        goto LABEL_16;
      }
      if ( (*((_DWORD *)Object + 20) & 0x800) != 0 )
      {
        v25 = -1073741811;
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
  if ( (int)FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3862, 0) < 0 )
  {
    *FileHandle = 0;
    if ( a4 )
      *a4 = 0;
  }
  if ( v21 )
  {
    v27 = FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3874, 0);
    LOBYTE(v28) = v23;
    if ( v27 < 0 )
      v21 = 0;
    CleanupTargetedIo(v21, &DriverContext.ExtraCreateParameter, v28);
    if ( EcpContext )
      FsRtlInsertExtraCreateParameter(DriverContext.ExtraCreateParameter, EcpContext);
  }
  if ( (int)FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3910, 0) < 0 )
    return v25;
  return v22;
}

```

## disassembly

```asm
0x180053000  push    rbp
0x180053002  push    rbx
0x180053003  push    rsi
0x180053004  push    rdi
0x180053005  push    r12
0x180053007  push    r13
0x180053009  push    r14
0x18005300b  push    r15
0x18005300d  lea     rbp, [rsp-8]
0x180053012  sub     rsp, 108h
0x180053019  mov     rax, cs:__security_cookie
0x180053020  xor     rax, rsp
0x180053023  mov     [rbp+40h+var_48], rax
0x180053027  mov     rax, [rbp+40h+arg_28]
0x18005302b  xor     r10d, r10d
0x18005302e  xorps   xmm0, xmm0
0x180053031  mov     [rbp+40h+ObjectAttributes], rax
0x180053035  mov     rax, [rbp+40h+arg_30]
0x18005303c  mov     r14, r9
0x18005303f  mov     [rbp+40h+IoStatusBlock], rax
0x180053043  mov     r9, rcx
0x180053046  mov     rcx, [rbp+40h+arg_88]
0x18005304d  lea     r11d, [r10+28h]
0x180053051  xor     eax, eax
0x180053053  mov     [rbp+40h+Object], r10
0x180053057  mov     qword ptr [rbp+40h+var_B8], r10
0x18005305b  mov     r15, r8
0x18005305e  mov     r8, [rbp+40h+arg_80]
0x180053065  mov     r13, rdx
0x180053068  mov     [rbp+40h+EcpContext], r10
0x18005306c  mov     esi, r10d
0x18005306f  mov     [rbp+40h+var_50], rax
0x180053073  mov     r12d, r10d
0x180053076  mov     [rbp+40h+var_88], 1
0x18005307e  mov     bl, r10b
0x180053081  movups  xmmword ptr [rbp+40h+var_A8.Size], xmm0
0x180053085  mov     [rbp+40h+var_A8.Size], r11w
0x18005308a  movups  [rbp+40h+var_70], xmm0
0x18005308e  movups  [rbp+40h+var_60], xmm0
0x180053092  movups  xmmword ptr [rbp+40h+var_A8.DeviceObjectHint], xmm0
0x180053096  test    rcx, rcx
0x180053099  jz      short loc_1800530D0
0x18005309b  movzx   edx, word ptr [rcx]
0x18005309e  cmp     dx, 20h ; ' '
0x1800530a2  jb      loc_180053281
0x1800530a8  cmp     [rcx+10h], r10
0x1800530ac  jnz     loc_180053281
0x1800530b2  mov     rax, [rcx+8]
0x1800530b6  mov     [rbp+40h+var_A8.ExtraCreateParameter], rax
0x1800530ba  mov     rax, [rcx+18h]
0x1800530be  mov     [rbp+40h+var_A8.TxnParameters], rax
0x1800530c2  cmp     dx, r11w
0x1800530c6  jb      short loc_1800530D0
0x1800530c8  mov     rax, [rcx+20h]
0x1800530cc  mov     [rbp+40h+var_88], rax
0x1800530d0  test    r8, r8
0x1800530d3  jz      short loc_1800530E0
0x1800530d5  mov     rax, [r8]
0x1800530d8  mov     qword ptr [rbp+40h+var_60+8], rax
0x1800530dc  mov     byte ptr [rbp+40h+var_50], 1
0x1800530e0  mov     eax, [rbp+40h+arg_50]
0x1800530e6  lea     rcx, [rbp+40h+var_B8]; int
0x1800530ea  mov     dword ptr [rbp+40h+var_70], eax
0x1800530ed  xor     r8d, r8d; int
0x1800530f0  mov     eax, [rbp+40h+arg_58]
0x1800530f6  mov     dl, 1; int
0x1800530f8  mov     dword ptr [rbp+40h+var_70+4], eax
0x1800530fb  mov     eax, [rbp+40h+arg_60]
0x180053101  mov     dword ptr [rbp+40h+var_70+8], eax
0x180053104  mov     eax, [rbp+40h+arg_68]
0x18005310a  mov     dword ptr [rbp+40h+var_70+0Ch], eax
0x18005310d  mov     eax, [rbp+40h+arg_70]
0x180053113  mov     dword ptr [rbp+40h+var_60], eax
0x180053116  mov     eax, [rbp+40h+arg_78]
0x18005311c  mov     dword ptr [rbp+40h+var_60+4], eax
0x18005311f  lea     rax, [rbp+40h+EcpContext]
0x180053123  mov     qword ptr [rsp+140h+CreateOptions], rax; __int64
0x180053128  lea     rax, [rbp+40h+var_A8.ExtraCreateParameter]
0x18005312c  mov     qword ptr [rsp+140h+Disposition], rax; EcpList
0x180053131  mov     qword ptr [rsp+140h+ShareAccess], r10; PVOID
0x180053136  mov     qword ptr [rsp+140h+FileAttributes], r13; __int64
0x18005313b  mov     [rsp+140h+AllocationSize], r9; FltObject
0x180053140  mov     r9, [r9+38h]; int
0x180053144  call    TargetedIOCtrlGenerateECP
0x180053149  mov     r8d, 0E7Bh
0x18005314f  mov     [rsp+140h+AllocationSize], rsi
0x180053154  mov     r9d, 0C01C000Bh
0x18005315a  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180053161  mov     ecx, eax
0x180053163  mov     edi, eax
0x180053165  call    FltpDbgStatus
0x18005316a  mov     rsi, qword ptr [rbp+40h+var_B8]
0x18005316e  test    eax, eax
0x180053170  js      loc_180053286
0x180053176  mov     bl, [rsi+6]
0x180053179  shr     bl, 3
0x18005317c  and     bl, 1
0x18005317f  test    r13, r13
0x180053182  jz      short loc_180053190
0x180053184  mov     rax, [r13+40h]
0x180053188  mov     rcx, [rax+40h]
0x18005318c  mov     [rbp+40h+var_A8.DeviceObjectHint], rcx
0x180053190  mov     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x180053194  lea     rax, [rbp+40h+var_A8]
0x180053198  mov     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18005319c  xor     r13d, r13d
0x18005319f  mov     edx, [rbp+40h+DesiredAccess]; DesiredAccess
0x1800531a2  mov     rcx, r15; FileHandle
0x1800531a5  mov     [rsp+140h+DriverContext], rax; DriverContext
0x1800531aa  lea     rax, [rbp+40h+var_70]
0x1800531ae  mov     [rsp+140h+Options], r13d; Options
0x1800531b3  mov     [rsp+140h+InternalParameters], rax; InternalParameters
0x1800531b8  mov     eax, [rbp+40h+arg_48]
0x1800531be  mov     [rsp+140h+CreateFileType], 1; CreateFileType
0x1800531c6  mov     [rsp+140h+EaLength], r13d; EaLength
0x1800531cb  mov     [rsp+140h+EaBuffer], r13; EaBuffer
0x1800531d0  mov     [rsp+140h+CreateOptions], eax; CreateOptions
0x1800531d4  mov     eax, [rbp+40h+arg_40]
0x1800531da  mov     [rsp+140h+Disposition], eax; Disposition
0x1800531de  mov     eax, [rbp+40h+arg_38]
0x1800531e4  mov     [rsp+140h+ShareAccess], eax; ShareAccess
0x1800531e8  mov     [rsp+140h+FileAttributes], r13d; FileAttributes
0x1800531ed  mov     [rsp+140h+AllocationSize], r13; AllocationSize
0x1800531f2  call    cs:__imp_IoCreateFileEx
0x1800531f9  nop     dword ptr [rax+rax+00h]
0x1800531fe  mov     r8d, 0EB8h
0x180053204  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005320b  mov     ecx, eax
0x18005320d  xor     r9d, r9d
0x180053210  mov     edi, eax
0x180053212  call    FltpDbgStatus
0x180053217  test    eax, eax
0x180053219  js      short loc_180053289
0x18005321b  mov     r8, cs:__imp_IoFileObjectType
0x180053222  lea     rax, [rbp+40h+Object]
0x180053226  mov     edx, [rbp+40h+DesiredAccess]; DesiredAccess
0x180053229  xor     r9d, r9d; AccessMode
0x18005322c  mov     rcx, [r15]; Handle
0x18005322f  mov     r12d, edi
0x180053232  mov     qword ptr [rsp+140h+FileAttributes], r13; HandleInformation
0x180053237  mov     r8, [r8]; ObjectType
0x18005323a  mov     [rsp+140h+AllocationSize], rax; Object
0x18005323f  call    cs:__imp_ObReferenceObjectByHandle
0x180053246  nop     dword ptr [rax+rax+00h]
0x18005324b  mov     r8d, 0ED6h
0x180053251  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180053258  mov     ecx, eax
0x18005325a  xor     r9d, r9d
0x18005325d  mov     edi, eax
0x18005325f  call    FltpDbgStatus
0x180053264  test    eax, eax
0x180053266  jns     loc_18005333A
0x18005326c  mov     [rbp+40h+Object], r13
0x180053270  mov     rcx, [r15]; Handle
0x180053273  call    cs:__imp_ZwClose
0x18005327a  nop     dword ptr [rax+rax+00h]
0x18005327f  jmp     short loc_180053289
0x180053281  mov     edi, 0C000000Dh
0x180053286  xor     r13d, r13d
0x180053289  mov     r8d, 0F16h
0x18005328f  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180053296  xor     r9d, r9d
0x180053299  mov     ecx, edi
0x18005329b  call    FltpDbgStatus
0x1800532a0  test    eax, eax
0x1800532a2  jns     short loc_1800532AF
0x1800532a4  mov     [r15], r13
0x1800532a7  test    r14, r14
0x1800532aa  jz      short loc_1800532AF
0x1800532ac  mov     [r14], r13
0x1800532af  test    rsi, rsi
0x1800532b2  jz      short loc_1800532F9
0x1800532b4  xor     r9d, r9d
0x1800532b7  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800532be  mov     r8d, 0F22h
0x1800532c4  mov     ecx, edi
0x1800532c6  call    FltpDbgStatus
0x1800532cb  test    eax, eax
0x1800532cd  lea     rdx, [rbp+40h+var_A8.ExtraCreateParameter]
0x1800532d1  mov     r8b, bl
0x1800532d4  cmovs   rsi, r13
0x1800532d8  mov     rcx, rsi
0x1800532db  call    CleanupTargetedIo
0x1800532e0  mov     rdx, [rbp+40h+EcpContext]; EcpContext
0x1800532e4  test    rdx, rdx
0x1800532e7  jz      short loc_1800532F9
0x1800532e9  mov     rcx, [rbp+40h+var_A8.ExtraCreateParameter]; EcpList
0x1800532ed  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1800532f4  nop     dword ptr [rax+rax+00h]
0x1800532f9  mov     r8d, 0F46h
0x1800532ff  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180053306  xor     r9d, r9d
0x180053309  mov     ecx, edi
0x18005330b  call    FltpDbgStatus
0x180053310  test    eax, eax
0x180053312  cmovs   r12d, edi
0x180053316  mov     eax, r12d
0x180053319  mov     rcx, [rbp+40h+var_48]
0x18005331d  xor     rcx, rsp; StackCookie
0x180053320  call    __security_check_cookie
0x180053325  add     rsp, 108h
0x18005332c  pop     r15
0x18005332e  pop     r14
0x180053330  pop     r13
0x180053332  pop     r12
0x180053334  pop     rdi
0x180053335  pop     rsi
0x180053336  pop     rbx
0x180053337  pop     rbp
0x180053338  retn
0x18005333a  mov     rcx, [rbp+40h+Object]; Object
0x18005333e  test    dword ptr [rcx+50h], 800h
0x180053345  jz      short loc_18005335D
0x180053347  mov     edi, 0C000000Dh
0x18005334c  call    cs:__imp_ObfDereferenceObject
0x180053353  nop     dword ptr [rax+rax+00h]
0x180053358  jmp     loc_180053270
0x18005335d  test    r14, r14
0x180053360  jz      short loc_18005336A
0x180053362  mov     [r14], rcx
0x180053365  jmp     loc_180053289
0x18005336a  call    cs:__imp_ObfDereferenceObject
0x180053371  nop     dword ptr [rax+rax+00h]
0x180053376  jmp     loc_180053289
```

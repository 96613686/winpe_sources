# NfsPathConf

- ea: `0x14000c8d8`
- end: `0x14000cdb0`
- name: `NfsPathConf`
- size: `1240`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1400293c4`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000c818`
- `0x14000c8d8`
- `0x14000d99c`
- `0x14000fa80`
- `0x14000fb40`
- `0x140011f84`
- `0x140013ac0`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400204c0`
- `0x140022220`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000ca45`
- `ntoskrnl!KeReleaseMutex` at `0x14000cbb1`
- `ntoskrnl!KeReleaseMutex` at `0x14000ca45`
- `ntoskrnl!KeReleaseMutex` at `0x14000cbb1`
- `rpcxdr!OncRpcDestroy` at `0x14000ccbe`
- `rpcxdr!OncRpcDestroy` at `0x14000ccd2`
- `rpcxdr!OncRpcDestroy` at `0x14000cce1`
- `rpcxdr!OncRpcDestroy` at `0x14000cd56`
- `rpcxdr!OncRpcDestroy` at `0x14000ccbe`
- `rpcxdr!OncRpcDestroy` at `0x14000ccd2`
- `rpcxdr!OncRpcDestroy` at `0x14000cce1`
- `rpcxdr!OncRpcDestroy` at `0x14000cd56`

## pseudocode

```c
__int64 __fastcall NfsPathConf(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v6; // r15
  int v7; // r13d
  __int64 v9; // r10
  _DWORD *v10; // rbx
  int v11; // r14d
  bool v12; // r12
  __int64 v14; // r14
  int v15; // ebx
  __int64 v16; // r8
  int v17; // edx
  __int64 v18; // r15
  __int64 v19; // r8
  unsigned int v20; // ebx
  char v21; // al
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h]
  __int64 v27; // [rsp+A8h] [rbp+58h]

  v27 = a4;
  v4 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 40);
  v7 = a2;
  v25 = 0;
  v9 = *(_QWORD *)(v4 + 32);
  v26 = *(_QWORD *)(a2 + 80);
  v10 = *(_DWORD **)(v9 + 32);
  v11 = v10[22];
  v12 = v11 == 3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 300, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  if ( !v6 || !v10 )
    return 3221225662LL;
  if ( v11 != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 301, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    return 3221225659LL;
  }
  if ( (unsigned __int8)HacIsEntryFake(a3) )
    return 3221225659LL;
  v14 = NfsRdrBuildCall((int)v10 + 116, v10[20], v10[21], v10[22], 20, 68, a1);
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 302, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = -1073741670;
    goto LABEL_60;
  }
  HacAcquireLock(a3);
  LOBYTE(v16) = v12;
  XdrEncodeNfsFileHandleUnsafe(v14, a3 + 216, v16);
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  if ( *(int *)(v14 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 303, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = *(_DWORD *)(v14 + 264);
    goto LABEL_59;
  }
  v18 = v26;
  v15 = NfsSendWaitReply(v26, v17, a1, v7, *(_QWORD *)(a1 + 40), (__int64)(v10 + 18), v14, (__int64)&v25, 0);
  if ( v15 < 0 || !v25 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 304, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_59;
  }
  v15 = OncRpcMapRpcStatusToNtStatus(v25);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_51;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 305, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_44;
  }
  v20 = XdrDecodeInt(v19);
  v21 = XdrDecodeBool(v25);
  v19 = v25;
  if ( *(int *)(v25 + 264) < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_50;
    v23 = 306;
LABEL_49:
    WPP_SF_(v22->AttachedDevice, v23, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v19 = v25;
LABEL_50:
    v15 = *(_DWORD *)(v19 + 264);
    goto LABEL_51;
  }
  if ( v21 )
  {
    HacAcquireLock(a3);
    LOBYTE(v24) = v12;
    XdrDecodeNfsFileAttributes(v25, a3 + 128, v24);
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    v19 = v25;
    if ( *(int *)(v25 + 264) >= 0 )
    {
      HacUpdateTimeStamp(a3);
      v19 = v25;
    }
  }
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 307, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = MapNFSStatusToNtStatus(v20);
    if ( v15 != -1073741816 )
      goto LABEL_51;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 308, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
    HacOrphanStaleEntry(v18, a3);
LABEL_44:
    v19 = v25;
LABEL_51:
    OncRpcDestroy(v19);
LABEL_59:
    OncRpcDestroy(v14);
LABEL_60:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 311, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    return (unsigned int)v15;
  }
  XdrDecodeNfs3PathConf(v19, v27);
  v19 = v25;
  if ( *(int *)(v25 + 264) < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_50;
    v23 = 309;
    goto LABEL_49;
  }
  OncRpcDestroy(v25);
  OncRpcDestroy(v14);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 310, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14000c8d8  mov     [rsp-38h+arg_10], rbx
0x14000c8dd  mov     [rsp-38h+arg_18], r9
0x14000c8e2  push    rbp
0x14000c8e3  push    rsi
0x14000c8e4  push    rdi
0x14000c8e5  push    r12
0x14000c8e7  push    r13
0x14000c8e9  push    r14
0x14000c8eb  push    r15
0x14000c8ed  mov     rbp, rsp
0x14000c8f0  sub     rsp, 50h
0x14000c8f4  mov     rax, [rcx+20h]
0x14000c8f8  mov     rsi, r8
0x14000c8fb  mov     r15, [rcx+28h]
0x14000c8ff  mov     r13, rdx
0x14000c902  mov     [rbp+arg_0], 0
0x14000c90a  mov     rdi, rcx
0x14000c90d  mov     r10, [rax+20h]
0x14000c911  mov     rax, [rdx+50h]
0x14000c915  mov     [rbp+arg_8], rax
0x14000c919  mov     rbx, [r10+20h]
0x14000c91d  mov     r14d, [rbx+58h]
0x14000c921  cmp     r14d, 3
0x14000c925  setz    r12b
0x14000c929  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c930  lea     rax, WPP_GLOBAL_Control
0x14000c937  cmp     rcx, rax
0x14000c93a  jz      short loc_14000C95F
0x14000c93c  mov     eax, [rcx+2Ch]
0x14000c93f  test    al, 40h
0x14000c941  jz      short loc_14000C958
0x14000c943  mov     rcx, [rcx+18h]
0x14000c947  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000c94e  mov     edx, 12Ch
0x14000c953  call    WPP_SF_
0x14000c958  lea     rax, WPP_GLOBAL_Control
0x14000c95f  test    r15, r15
0x14000c962  jz      loc_14000CD92
0x14000c968  test    rbx, rbx
0x14000c96b  jz      loc_14000CD92
0x14000c971  cmp     r14d, 3
0x14000c975  jz      short loc_14000C9A1
0x14000c977  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c97e  cmp     rcx, rax
0x14000c981  jz      short loc_14000C9AD
0x14000c983  mov     eax, [rcx+2Ch]
0x14000c986  test    al, 2
0x14000c988  jz      short loc_14000C9AD
0x14000c98a  mov     rcx, [rcx+18h]
0x14000c98e  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000c995  mov     edx, 12Dh
0x14000c99a  call    WPP_SF_
0x14000c99f  jmp     short loc_14000C9AD
0x14000c9a1  mov     rcx, rsi
0x14000c9a4  call    HacIsEntryFake
0x14000c9a9  test    al, al
0x14000c9ab  jz      short loc_14000C9B7
0x14000c9ad  mov     eax, 0C00000BBh
0x14000c9b2  jmp     loc_14000CD97
0x14000c9b7  mov     r9d, [rbx+58h]
0x14000c9bb  lea     rcx, [rbx+74h]
0x14000c9bf  mov     r8d, [rbx+54h]
0x14000c9c3  mov     edx, [rbx+50h]
0x14000c9c6  mov     [rsp+50h+var_20], rdi
0x14000c9cb  mov     dword ptr [rsp+50h+var_28], 44h ; 'D'
0x14000c9d3  mov     dword ptr [rsp+50h+var_30], 14h
0x14000c9db  call    NfsRdrBuildCall
0x14000c9e0  mov     r14, rax
0x14000c9e3  test    rax, rax
0x14000c9e6  jnz     short loc_14000CA25
0x14000c9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9ef  lea     r12, WPP_GLOBAL_Control
0x14000c9f6  mov     dil, 1
0x14000c9f9  cmp     rcx, r12
0x14000c9fc  jz      short loc_14000CA1B
0x14000c9fe  mov     eax, [rcx+2Ch]
0x14000ca01  test    dil, al
0x14000ca04  jz      short loc_14000CA1B
0x14000ca06  mov     rcx, [rcx+18h]
0x14000ca0a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000ca11  mov     edx, 12Eh
0x14000ca16  call    WPP_SF_
0x14000ca1b  mov     ebx, 0C000009Ah
0x14000ca20  jmp     loc_14000CD62
0x14000ca25  mov     rcx, rsi
0x14000ca28  call    HacAcquireLock
0x14000ca2d  lea     rdx, [rsi+0D8h]
0x14000ca34  mov     r8b, r12b
0x14000ca37  mov     rcx, r14
0x14000ca3a  call    XdrEncodeNfsFileHandleUnsafe
0x14000ca3f  mov     rcx, [rsi+28h]; Mutex
0x14000ca43  xor     edx, edx; Wait
0x14000ca45  call    cs:__imp_KeReleaseMutex
0x14000ca4c  nop     dword ptr [rax+rax+00h]
0x14000ca51  cmp     dword ptr [r14+108h], 0
0x14000ca59  jge     short loc_14000CA9A
0x14000ca5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca62  lea     r12, WPP_GLOBAL_Control
0x14000ca69  mov     dil, 1
0x14000ca6c  cmp     rcx, r12
0x14000ca6f  jz      short loc_14000CA8E
0x14000ca71  mov     eax, [rcx+2Ch]
0x14000ca74  test    dil, al
0x14000ca77  jz      short loc_14000CA8E
0x14000ca79  mov     rcx, [rcx+18h]
0x14000ca7d  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000ca84  mov     edx, 12Fh
0x14000ca89  call    WPP_SF_
0x14000ca8e  mov     ebx, [r14+108h]
0x14000ca95  jmp     loc_14000CD53
0x14000ca9a  mov     r15, [rbp+arg_8]
0x14000ca9e  lea     rcx, [rbp+arg_0]
0x14000caa2  mov     [rsp+50h+var_10], 0
0x14000caaa  lea     rax, [rbx+48h]
0x14000caae  mov     [rsp+50h+var_18], rcx
0x14000cab3  mov     r9, r13
0x14000cab6  mov     [rsp+50h+var_20], r14
0x14000cabb  mov     r8, rdi
0x14000cabe  mov     [rsp+50h+var_28], rax
0x14000cac3  mov     rcx, r15
0x14000cac6  mov     rax, [rdi+28h]
0x14000caca  mov     [rsp+50h+var_30], rax
0x14000cacf  call    NfsSendWaitReply
0x14000cad4  xor     r13d, r13d
0x14000cad7  mov     ebx, eax
0x14000cad9  mov     dil, 1
0x14000cadc  test    eax, eax
0x14000cade  js      loc_14000CD20
0x14000cae4  mov     r8, [rbp+arg_0]
0x14000cae8  test    r8, r8
0x14000caeb  jz      loc_14000CD20
0x14000caf1  mov     rcx, r8
0x14000caf4  call    OncRpcMapRpcStatusToNtStatus
0x14000caf9  mov     ebx, eax
0x14000cafb  test    eax, eax
0x14000cafd  jns     short loc_14000CB3F
0x14000caff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb06  lea     r12, WPP_GLOBAL_Control
0x14000cb0d  cmp     rcx, r12
0x14000cb10  jz      loc_14000CCBB
0x14000cb16  mov     eax, [rcx+2Ch]
0x14000cb19  test    dil, al
0x14000cb1c  jz      loc_14000CCBB
0x14000cb22  mov     rcx, [rcx+18h]
0x14000cb26  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cb2d  mov     edx, 131h
0x14000cb32  mov     r9d, ebx
0x14000cb35  call    WPP_SF_d
0x14000cb3a  jmp     loc_14000CC61
0x14000cb3f  mov     rcx, r8
0x14000cb42  call    XdrDecodeInt
0x14000cb47  mov     rcx, [rbp+arg_0]
0x14000cb4b  mov     ebx, eax
0x14000cb4d  call    XdrDecodeBool
0x14000cb52  mov     r8, [rbp+arg_0]
0x14000cb56  cmp     [r8+108h], r13d
0x14000cb5d  jge     short loc_14000CB8C
0x14000cb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb66  lea     r12, WPP_GLOBAL_Control
0x14000cb6d  cmp     rcx, r12
0x14000cb70  jz      loc_14000CCB4
0x14000cb76  mov     eax, [rcx+2Ch]
0x14000cb79  test    dil, al
0x14000cb7c  jz      loc_14000CCB4
0x14000cb82  mov     edx, 132h
0x14000cb87  jmp     loc_14000CCA0
0x14000cb8c  test    al, al
0x14000cb8e  jz      short loc_14000CBD6
0x14000cb90  mov     rcx, rsi
0x14000cb93  call    HacAcquireLock
0x14000cb98  mov     rcx, [rbp+arg_0]
0x14000cb9c  lea     rdx, [rsi+80h]
0x14000cba3  mov     r8b, r12b
0x14000cba6  call    XdrDecodeNfsFileAttributes
0x14000cbab  mov     rcx, [rsi+28h]; Mutex
0x14000cbaf  xor     edx, edx; Wait
0x14000cbb1  call    cs:__imp_KeReleaseMutex
0x14000cbb8  nop     dword ptr [rax+rax+00h]
0x14000cbbd  mov     r8, [rbp+arg_0]
0x14000cbc1  cmp     [r8+108h], r13d
0x14000cbc8  jl      short loc_14000CBD6
0x14000cbca  mov     rcx, rsi
0x14000cbcd  call    HacUpdateTimeStamp
0x14000cbd2  mov     r8, [rbp+arg_0]
0x14000cbd6  test    ebx, ebx
0x14000cbd8  jz      loc_14000CC67
0x14000cbde  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbe5  lea     r12, WPP_GLOBAL_Control
0x14000cbec  cmp     rcx, r12
0x14000cbef  jz      short loc_14000CC15
0x14000cbf1  mov     eax, [rcx+2Ch]
0x14000cbf4  test    dil, al
0x14000cbf7  jz      short loc_14000CC15
0x14000cbf9  mov     rcx, [rcx+18h]
0x14000cbfd  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cc04  mov     edx, 133h
0x14000cc09  mov     r9d, ebx
0x14000cc0c  call    WPP_SF_d
0x14000cc11  mov     r8, [rbp+arg_0]
0x14000cc15  mov     ecx, ebx
0x14000cc17  call    MapNFSStatusToNtStatus
0x14000cc1c  mov     ebx, eax
0x14000cc1e  cmp     eax, 0C0000008h
0x14000cc23  jnz     loc_14000CCBB
0x14000cc29  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc30  cmp     rcx, r12
0x14000cc33  jz      short loc_14000CC56
0x14000cc35  mov     eax, [rcx+2Ch]
0x14000cc38  test    dil, al
0x14000cc3b  jz      short loc_14000CC56
0x14000cc3d  mov     rcx, [rcx+18h]
0x14000cc41  lea     r9, [rsi+40h]
0x14000cc45  mov     edx, 134h
0x14000cc4a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cc51  call    WPP_SF_Z
0x14000cc56  mov     rdx, rsi
0x14000cc59  mov     rcx, r15
0x14000cc5c  call    HacOrphanStaleEntry
0x14000cc61  mov     r8, [rbp+arg_0]
0x14000cc65  jmp     short loc_14000CCBB
0x14000cc67  mov     rdx, [rbp+arg_18]
0x14000cc6b  mov     rcx, r8
0x14000cc6e  call    XdrDecodeNfs3PathConf
0x14000cc73  mov     r8, [rbp+arg_0]
0x14000cc77  cmp     [r8+108h], r13d
0x14000cc7e  jge     short loc_14000CCCF
0x14000cc80  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc87  lea     r12, WPP_GLOBAL_Control
0x14000cc8e  cmp     rcx, r12
0x14000cc91  jz      short loc_14000CCB4
0x14000cc93  mov     eax, [rcx+2Ch]
0x14000cc96  test    dil, al
0x14000cc99  jz      short loc_14000CCB4
0x14000cc9b  mov     edx, 135h
0x14000cca0  mov     rcx, [rcx+18h]
0x14000cca4  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000ccab  call    WPP_SF_
0x14000ccb0  mov     r8, [rbp+arg_0]
0x14000ccb4  mov     ebx, [r8+108h]
0x14000ccbb  mov     rcx, r8
0x14000ccbe  call    cs:__imp_OncRpcDestroy
0x14000ccc5  nop     dword ptr [rax+rax+00h]
0x14000ccca  jmp     loc_14000CD53
0x14000cccf  mov     rcx, r8
0x14000ccd2  call    cs:__imp_OncRpcDestroy
0x14000ccd9  nop     dword ptr [rax+rax+00h]
0x14000ccde  mov     rcx, r14
0x14000cce1  call    cs:__imp_OncRpcDestroy
0x14000cce8  nop     dword ptr [rax+rax+00h]
0x14000cced  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccf4  lea     r12, WPP_GLOBAL_Control
0x14000ccfb  cmp     rcx, r12
0x14000ccfe  jz      short loc_14000CD1C
0x14000cd00  mov     eax, [rcx+2Ch]
0x14000cd03  test    al, 40h
0x14000cd05  jz      short loc_14000CD1C
0x14000cd07  mov     rcx, [rcx+18h]
0x14000cd0b  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cd12  mov     edx, 136h
0x14000cd17  call    WPP_SF_
0x14000cd1c  xor     eax, eax
0x14000cd1e  jmp     short loc_14000CD97
0x14000cd20  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd27  lea     r12, WPP_GLOBAL_Control
0x14000cd2e  cmp     rcx, r12
0x14000cd31  jz      short loc_14000CD53
0x14000cd33  mov     eax, [rcx+2Ch]
0x14000cd36  test    dil, al
0x14000cd39  jz      short loc_14000CD53
0x14000cd3b  mov     rcx, [rcx+18h]
0x14000cd3f  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cd46  mov     edx, 130h
0x14000cd4b  mov     r9d, ebx
0x14000cd4e  call    WPP_SF_d
0x14000cd53  mov     rcx, r14
0x14000cd56  call    cs:__imp_OncRpcDestroy
0x14000cd5d  nop     dword ptr [rax+rax+00h]
0x14000cd62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd69  cmp     rcx, r12
0x14000cd6c  jz      short loc_14000CD8E
0x14000cd6e  mov     eax, [rcx+2Ch]
0x14000cd71  test    dil, al
0x14000cd74  jz      short loc_14000CD8E
0x14000cd76  mov     rcx, [rcx+18h]
0x14000cd7a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000cd81  mov     edx, 137h
0x14000cd86  mov     r9d, ebx
0x14000cd89  call    WPP_SF_d
0x14000cd8e  mov     eax, ebx
0x14000cd90  jmp     short loc_14000CD97
0x14000cd92  mov     eax, 0C00000BEh
0x14000cd97  mov     rbx, [rsp+50h+arg_10]
0x14000cd9f  add     rsp, 50h
0x14000cda3  pop     r15
0x14000cda5  pop     r14
0x14000cda7  pop     r13
0x14000cda9  pop     r12
0x14000cdab  pop     rdi
0x14000cdac  pop     rsi
0x14000cdad  pop     rbp
  ... truncated ...
```

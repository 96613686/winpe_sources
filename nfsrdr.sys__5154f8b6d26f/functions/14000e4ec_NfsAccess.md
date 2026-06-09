# NfsAccess

- ea: `0x14000e4ec`
- end: `0x14000e939`
- name: `NfsAccess`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1400374f8`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000e4ec`
- `0x14000fa80`
- `0x14000fb40`
- `0x140011960`
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

- `ntoskrnl!KeReleaseMutex` at `0x14000e610`
- `ntoskrnl!KeReleaseMutex` at `0x14000e746`
- `ntoskrnl!KeReleaseMutex` at `0x14000e610`
- `ntoskrnl!KeReleaseMutex` at `0x14000e746`
- `rpcxdr!OncRpcDestroy` at `0x14000e84d`
- `rpcxdr!OncRpcDestroy` at `0x14000e861`
- `rpcxdr!OncRpcDestroy` at `0x14000e871`
- `rpcxdr!OncRpcDestroy` at `0x14000e8e6`
- `rpcxdr!OncRpcDestroy` at `0x14000e84d`
- `rpcxdr!OncRpcDestroy` at `0x14000e861`
- `rpcxdr!OncRpcDestroy` at `0x14000e871`
- `rpcxdr!OncRpcDestroy` at `0x14000e8e6`

## pseudocode

```c
__int64 __fastcall NfsAccess(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // r13
  int v7; // r15d
  __int64 v9; // rbx
  bool v10; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r14
  int v15; // ebx
  __int64 v16; // r8
  int v17; // edx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // [rsp+A0h] [rbp+48h] BYREF

  v5 = *(_QWORD *)(a2 + 80);
  v7 = a2;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v10 = *(_DWORD *)(v9 + 88) == 3;
  if ( !v9 || !*(_QWORD *)(a1 + 40) )
    return 3221225662LL;
  if ( (unsigned __int8)HacIsEntryFake(a3) )
    return 3221225506LL;
  v14 = NfsRdrBuildCall(v9 + 116, *(_DWORD *)(v9 + 80), *(_DWORD *)(v9 + 84), *(_DWORD *)(v9 + 88), 4, 68, a1);
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = -1073741670;
    goto LABEL_52;
  }
  HacAcquireLock(a3, v12, v13);
  LOBYTE(v16) = v10;
  XdrEncodeNfsFileHandleUnsafe(v14, a3 + 216, v16);
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  XdrEncodeIntUnsafe(v14, 16);
  if ( *(int *)(v14 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = *(_DWORD *)(v14 + 264);
    goto LABEL_51;
  }
  v15 = NfsSendWaitReply(v5, v17, a1, v7, *(_QWORD *)(a1 + 40), v9 + 72, v14, (__int64)&v23, 0);
  if ( v15 < 0 || !v23 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_51;
  }
  v15 = OncRpcMapRpcStatusToNtStatus(v23);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_43:
    OncRpcDestroy(v23);
LABEL_51:
    OncRpcDestroy(v14);
LABEL_52:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    return (unsigned int)v15;
  }
  v18 = XdrDecodeInt(v23);
  if ( (unsigned __int8)XdrDecodeBool(v23) )
  {
    HacAcquireLock(a3, v19, v20);
    LOBYTE(v21) = v10;
    XdrDecodeNfsFileAttributes(v23, a3 + 128, v21);
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    if ( *(int *)(v23 + 264) >= 0 )
      HacUpdateTimeStamp(a3);
  }
  if ( !v18 )
  {
    v22 = XdrDecodeInt(v23);
    *a5 = v22;
  }
  if ( *(int *)(v23 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = *(_DWORD *)(v23 + 264);
    goto LABEL_43;
  }
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = MapNFSStatusToNtStatus(v18);
    if ( v15 == -1073741816 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 168, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
      HacOrphanStaleEntry(v5, a3);
    }
    goto LABEL_43;
  }
  OncRpcDestroy(v14);
  OncRpcDestroy(v23);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14000e4ec  push    rbp
0x14000e4ee  push    rbx
0x14000e4ef  push    rsi
0x14000e4f0  push    rdi
0x14000e4f1  push    r12
0x14000e4f3  push    r13
0x14000e4f5  push    r14
0x14000e4f7  push    r15
0x14000e4f9  mov     rbp, rsp
0x14000e4fc  sub     rsp, 58h
0x14000e500  mov     r13, [rdx+50h]
0x14000e504  mov     rsi, r8
0x14000e507  mov     r15, rdx
0x14000e50a  mov     [rbp+arg_0], 0
0x14000e512  mov     rdi, rcx
0x14000e515  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e51c  lea     rax, WPP_GLOBAL_Control
0x14000e523  cmp     rcx, rax
0x14000e526  jz      short loc_14000E544
0x14000e528  mov     eax, [rcx+2Ch]
0x14000e52b  test    al, 40h
0x14000e52d  jz      short loc_14000E544
0x14000e52f  mov     rcx, [rcx+18h]
0x14000e533  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e53a  mov     edx, 0A1h
0x14000e53f  call    WPP_SF_
0x14000e544  mov     rax, [rdi+20h]
0x14000e548  mov     rcx, [rax+20h]
0x14000e54c  mov     rbx, [rcx+20h]
0x14000e550  cmp     dword ptr [rbx+58h], 3
0x14000e554  setz    r12b
0x14000e558  test    rbx, rbx
0x14000e55b  jz      loc_14000E922
0x14000e561  cmp     qword ptr [rdi+28h], 0
0x14000e566  jz      loc_14000E922
0x14000e56c  mov     rcx, rsi
0x14000e56f  call    HacIsEntryFake
0x14000e574  test    al, al
0x14000e576  jz      short loc_14000E582
0x14000e578  mov     eax, 0C0000022h
0x14000e57d  jmp     loc_14000E927
0x14000e582  mov     r9d, [rbx+58h]
0x14000e586  lea     rcx, [rbx+74h]
0x14000e58a  mov     r8d, [rbx+54h]
0x14000e58e  mov     edx, [rbx+50h]
0x14000e591  mov     [rsp+58h+var_28], rdi
0x14000e596  mov     dword ptr [rsp+58h+var_30], 44h ; 'D'
0x14000e59e  mov     dword ptr [rsp+58h+var_38], 4
0x14000e5a6  call    NfsRdrBuildCall
0x14000e5ab  mov     r14, rax
0x14000e5ae  test    rax, rax
0x14000e5b1  jnz     short loc_14000E5F0
0x14000e5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5ba  lea     r15, WPP_GLOBAL_Control
0x14000e5c1  mov     dil, 1
0x14000e5c4  cmp     rcx, r15
0x14000e5c7  jz      short loc_14000E5E6
0x14000e5c9  mov     eax, [rcx+2Ch]
0x14000e5cc  test    dil, al
0x14000e5cf  jz      short loc_14000E5E6
0x14000e5d1  mov     rcx, [rcx+18h]
0x14000e5d5  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e5dc  mov     edx, 0A2h
0x14000e5e1  call    WPP_SF_
0x14000e5e6  mov     ebx, 0C000009Ah
0x14000e5eb  jmp     loc_14000E8F2
0x14000e5f0  mov     rcx, rsi
0x14000e5f3  call    HacAcquireLock
0x14000e5f8  lea     rdx, [rsi+0D8h]
0x14000e5ff  mov     r8b, r12b
0x14000e602  mov     rcx, r14
0x14000e605  call    XdrEncodeNfsFileHandleUnsafe
0x14000e60a  mov     rcx, [rsi+28h]; Mutex
0x14000e60e  xor     edx, edx; Wait
0x14000e610  call    cs:__imp_KeReleaseMutex
0x14000e617  nop     dword ptr [rax+rax+00h]
0x14000e61c  mov     edx, 10h
0x14000e621  mov     rcx, r14
0x14000e624  call    XdrEncodeIntUnsafe
0x14000e629  cmp     dword ptr [r14+108h], 0
0x14000e631  jge     short loc_14000E672
0x14000e633  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e63a  lea     r15, WPP_GLOBAL_Control
0x14000e641  mov     dil, 1
0x14000e644  cmp     rcx, r15
0x14000e647  jz      short loc_14000E666
0x14000e649  mov     eax, [rcx+2Ch]
0x14000e64c  test    dil, al
0x14000e64f  jz      short loc_14000E666
0x14000e651  mov     rcx, [rcx+18h]
0x14000e655  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e65c  mov     edx, 0A3h
0x14000e661  call    WPP_SF_
0x14000e666  mov     ebx, [r14+108h]
0x14000e66d  jmp     loc_14000E8E3
0x14000e672  mov     [rsp+58h+var_18], 0
0x14000e67a  lea     rcx, [rbp+arg_0]
0x14000e67e  mov     [rsp+58h+var_20], rcx
0x14000e683  lea     rax, [rbx+48h]
0x14000e687  mov     [rsp+58h+var_28], r14
0x14000e68c  mov     r9, r15
0x14000e68f  mov     [rsp+58h+var_30], rax
0x14000e694  mov     r8, rdi
0x14000e697  mov     rax, [rdi+28h]
0x14000e69b  mov     rcx, r13
0x14000e69e  mov     [rsp+58h+var_38], rax
0x14000e6a3  call    NfsSendWaitReply
0x14000e6a8  mov     ebx, eax
0x14000e6aa  mov     dil, 1
0x14000e6ad  test    eax, eax
0x14000e6af  js      loc_14000E8B0
0x14000e6b5  mov     rcx, [rbp+arg_0]
0x14000e6b9  test    rcx, rcx
0x14000e6bc  jz      loc_14000E8B0
0x14000e6c2  call    OncRpcMapRpcStatusToNtStatus
0x14000e6c7  mov     ebx, eax
0x14000e6c9  test    eax, eax
0x14000e6cb  jns     short loc_14000E70D
0x14000e6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6d4  lea     r15, WPP_GLOBAL_Control
0x14000e6db  cmp     rcx, r15
0x14000e6de  jz      loc_14000E849
0x14000e6e4  mov     eax, [rcx+2Ch]
0x14000e6e7  test    dil, al
0x14000e6ea  jz      loc_14000E849
0x14000e6f0  mov     rcx, [rcx+18h]
0x14000e6f4  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e6fb  mov     edx, 0A5h
0x14000e700  mov     r9d, ebx
0x14000e703  call    WPP_SF_d
0x14000e708  jmp     loc_14000E849
0x14000e70d  mov     rcx, [rbp+arg_0]
0x14000e711  call    XdrDecodeInt
0x14000e716  mov     rcx, [rbp+arg_0]
0x14000e71a  mov     ebx, eax
0x14000e71c  call    XdrDecodeBool
0x14000e721  test    al, al
0x14000e723  jz      short loc_14000E767
0x14000e725  mov     rcx, rsi
0x14000e728  call    HacAcquireLock
0x14000e72d  mov     rcx, [rbp+arg_0]
0x14000e731  lea     rdx, [rsi+80h]
0x14000e738  mov     r8b, r12b
0x14000e73b  call    XdrDecodeNfsFileAttributes
0x14000e740  mov     rcx, [rsi+28h]; Mutex
0x14000e744  xor     edx, edx; Wait
0x14000e746  call    cs:__imp_KeReleaseMutex
0x14000e74d  nop     dword ptr [rax+rax+00h]
0x14000e752  mov     rax, [rbp+arg_0]
0x14000e756  cmp     dword ptr [rax+108h], 0
0x14000e75d  jl      short loc_14000E767
0x14000e75f  mov     rcx, rsi
0x14000e762  call    HacUpdateTimeStamp
0x14000e767  test    ebx, ebx
0x14000e769  jnz     short loc_14000E77A
0x14000e76b  mov     rcx, [rbp+arg_0]
0x14000e76f  call    XdrDecodeInt
0x14000e774  mov     rcx, [rbp+arg_20]
0x14000e778  mov     [rcx], eax
0x14000e77a  mov     rax, [rbp+arg_0]
0x14000e77e  cmp     dword ptr [rax+108h], 0
0x14000e785  jge     short loc_14000E7C6
0x14000e787  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e78e  lea     r15, WPP_GLOBAL_Control
0x14000e795  cmp     rcx, r15
0x14000e798  jz      short loc_14000E7B7
0x14000e79a  mov     eax, [rcx+2Ch]
0x14000e79d  test    dil, al
0x14000e7a0  jz      short loc_14000E7B7
0x14000e7a2  mov     rcx, [rcx+18h]
0x14000e7a6  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e7ad  mov     edx, 0A6h
0x14000e7b2  call    WPP_SF_
0x14000e7b7  mov     rax, [rbp+arg_0]
0x14000e7bb  mov     ebx, [rax+108h]
0x14000e7c1  jmp     loc_14000E849
0x14000e7c6  test    ebx, ebx
0x14000e7c8  jz      loc_14000E85E
0x14000e7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7d5  lea     r15, WPP_GLOBAL_Control
0x14000e7dc  cmp     rcx, r15
0x14000e7df  jz      short loc_14000E801
0x14000e7e1  mov     eax, [rcx+2Ch]
0x14000e7e4  test    dil, al
0x14000e7e7  jz      short loc_14000E801
0x14000e7e9  mov     rcx, [rcx+18h]
0x14000e7ed  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e7f4  mov     edx, 0A7h
0x14000e7f9  mov     r9d, ebx
0x14000e7fc  call    WPP_SF_d
0x14000e801  mov     ecx, ebx
0x14000e803  call    MapNFSStatusToNtStatus
0x14000e808  mov     ebx, eax
0x14000e80a  cmp     eax, 0C0000008h
0x14000e80f  jnz     short loc_14000E849
0x14000e811  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e818  cmp     rcx, r15
0x14000e81b  jz      short loc_14000E83E
0x14000e81d  mov     eax, [rcx+2Ch]
0x14000e820  test    dil, al
0x14000e823  jz      short loc_14000E83E
0x14000e825  mov     rcx, [rcx+18h]
0x14000e829  lea     r9, [rsi+40h]
0x14000e82d  mov     edx, 0A8h
0x14000e832  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e839  call    WPP_SF_Z
0x14000e83e  mov     rdx, rsi
0x14000e841  mov     rcx, r13
0x14000e844  call    HacOrphanStaleEntry
0x14000e849  mov     rcx, [rbp+arg_0]
0x14000e84d  call    cs:__imp_OncRpcDestroy
0x14000e854  nop     dword ptr [rax+rax+00h]
0x14000e859  jmp     loc_14000E8E3
0x14000e85e  mov     rcx, r14
0x14000e861  call    cs:__imp_OncRpcDestroy
0x14000e868  nop     dword ptr [rax+rax+00h]
0x14000e86d  mov     rcx, [rbp+arg_0]
0x14000e871  call    cs:__imp_OncRpcDestroy
0x14000e878  nop     dword ptr [rax+rax+00h]
0x14000e87d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e884  lea     r15, WPP_GLOBAL_Control
0x14000e88b  cmp     rcx, r15
0x14000e88e  jz      short loc_14000E8AC
0x14000e890  mov     eax, [rcx+2Ch]
0x14000e893  test    al, 40h
0x14000e895  jz      short loc_14000E8AC
0x14000e897  mov     rcx, [rcx+18h]
0x14000e89b  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e8a2  mov     edx, 0A9h
0x14000e8a7  call    WPP_SF_
0x14000e8ac  xor     eax, eax
0x14000e8ae  jmp     short loc_14000E927
0x14000e8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8b7  lea     r15, WPP_GLOBAL_Control
0x14000e8be  cmp     rcx, r15
0x14000e8c1  jz      short loc_14000E8E3
0x14000e8c3  mov     eax, [rcx+2Ch]
0x14000e8c6  test    dil, al
0x14000e8c9  jz      short loc_14000E8E3
0x14000e8cb  mov     rcx, [rcx+18h]
0x14000e8cf  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e8d6  mov     edx, 0A4h
0x14000e8db  mov     r9d, ebx
0x14000e8de  call    WPP_SF_d
0x14000e8e3  mov     rcx, r14
0x14000e8e6  call    cs:__imp_OncRpcDestroy
0x14000e8ed  nop     dword ptr [rax+rax+00h]
0x14000e8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8f9  cmp     rcx, r15
0x14000e8fc  jz      short loc_14000E91E
0x14000e8fe  mov     eax, [rcx+2Ch]
0x14000e901  test    dil, al
0x14000e904  jz      short loc_14000E91E
0x14000e906  mov     rcx, [rcx+18h]
0x14000e90a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e911  mov     edx, 0AAh
0x14000e916  mov     r9d, ebx
0x14000e919  call    WPP_SF_d
0x14000e91e  mov     eax, ebx
0x14000e920  jmp     short loc_14000E927
0x14000e922  mov     eax, 0C00000BEh
0x14000e927  add     rsp, 58h
0x14000e92b  pop     r15
0x14000e92d  pop     r14
0x14000e92f  pop     r13
0x14000e931  pop     r12
0x14000e933  pop     rdi
0x14000e934  pop     rsi
0x14000e935  pop     rbx
0x14000e936  pop     rbp
0x14000e937  retn
```

# NfsReadlink

- ea: `0x1400132cc`
- end: `0x140013822`
- name: `NfsReadlink`
- size: `1366`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x14001a950`
- `0x140035384`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000fa80`
- `0x14000fb40`
- `0x140011f84`
- `0x1400132cc`
- `0x140013830`
- `0x140013ac0`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400204c0`
- `0x140022220`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001340d`
- `ntoskrnl!KeReleaseMutex` at `0x14001352d`
- `ntoskrnl!KeReleaseMutex` at `0x14001340d`
- `ntoskrnl!KeReleaseMutex` at `0x14001352d`
- `rpcxdr!OncRpcDestroy` at `0x1400136fa`
- `rpcxdr!OncRpcDestroy` at `0x140013709`
- `rpcxdr!OncRpcDestroy` at `0x140013784`
- `rpcxdr!OncRpcDestroy` at `0x1400137c8`
- `rpcxdr!OncRpcDestroy` at `0x1400136fa`
- `rpcxdr!OncRpcDestroy` at `0x140013709`
- `rpcxdr!OncRpcDestroy` at `0x140013784`
- `rpcxdr!OncRpcDestroy` at `0x1400137c8`

## pseudocode

```c
__int64 __fastcall NfsReadlink(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // r13d
  _DWORD *v7; // rbx
  int v8; // r15d
  __int64 v10; // r14
  int v11; // ebx
  __int64 v12; // r8
  int v13; // edx
  int v14; // r9d
  __int64 v15; // r13
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // ebx
  __int64 v19; // r8
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  int v22; // edx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // [rsp+50h] [rbp-20h]
  __int128 v26; // [rsp+58h] [rbp-18h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+48h]
  __int64 v29; // [rsp+C8h] [rbp+58h]

  v29 = a4;
  v28 = *(_QWORD *)(a2 + 80);
  v26 = 0;
  v5 = a2;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v7 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v8 = v7[22];
  if ( !v7 )
    return 3221225662LL;
  v25 = *(_QWORD *)(a1 + 40);
  if ( !v25 )
    return 3221225662LL;
  if ( (unsigned __int8)HacIsEntryFake(a3) )
    return 3221225506LL;
  v10 = NfsRdrBuildCall((int)v7 + 116, v7[20], v7[21], v7[22], 5, 68, a1);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 172, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v11 = -1073741670;
    goto LABEL_68;
  }
  HacAcquireLock(a3);
  LOBYTE(v12) = v8 == 3;
  XdrEncodeNfsFileHandleUnsafe(v10, a3 + 216, v12);
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  if ( *(int *)(v10 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v11 = *(_DWORD *)(v10 + 264);
    goto LABEL_67;
  }
  v14 = v5;
  v15 = v28;
  v11 = NfsSendWaitReply(v28, v13, a1, v14, *(_QWORD *)(a1 + 40), (__int64)(v7 + 18), v10, (__int64)&v27, 0);
  if ( v11 < 0 || !v27 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_67;
  }
  v11 = OncRpcMapRpcStatusToNtStatus(v27);
  if ( v11 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_63;
    v17 = 175;
    goto LABEL_54;
  }
  v18 = XdrDecodeInt(v27);
  if ( v8 == 3 )
  {
    if ( (unsigned __int8)XdrDecodeBool(v27) )
    {
      HacAcquireLock(a3);
      LOBYTE(v19) = 1;
      XdrDecodeNfsFileAttributes(v27, a3 + 128, v19);
      KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
      if ( *(int *)(v27 + 264) >= 0 )
        HacUpdateTimeStamp(a3);
    }
  }
  if ( *(int *)(v27 + 264) < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_48;
    v21 = 176;
LABEL_47:
    WPP_SF_(v20->AttachedDevice, v21, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_48:
    v11 = *(_DWORD *)(v27 + 264);
LABEL_63:
    OncRpcDestroy(v27);
LABEL_67:
    OncRpcDestroy(v10);
LABEL_68:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 183, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    return (unsigned int)v11;
  }
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 177, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v11 = MapNFSStatusToNtStatus(v18);
    if ( v11 == -1073741816 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 178, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
      HacOrphanStaleEntry(v15, a3);
    }
    goto LABEL_63;
  }
  v22 = XdrDecodeInt(v27);
  v24 = *(_QWORD *)(v27 + 72);
  if ( v24 )
    v24 = *(_QWORD *)(v24 + 64);
  *((_QWORD *)&v26 + 1) = v24;
  if ( *(int *)(v27 + 264) < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_48;
    v21 = 179;
    goto LABEL_47;
  }
  if ( (unsigned int)(v22 - 1) > 0x3FF )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 180, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v11 = -1073741629;
    goto LABEL_63;
  }
  LOWORD(v26) = v22;
  LOBYTE(v23) = 1;
  v11 = NfsConvertAnsiToUnicode(v15, v29, &v26, v23, *(_DWORD *)(v25 + 32));
  if ( v11 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_63;
    v17 = 181;
LABEL_54:
    WPP_SF_d(v16->AttachedDevice, v17, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_63;
  }
  OncRpcDestroy(v27);
  OncRpcDestroy(v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400132cc  mov     [rsp-38h+arg_10], rbx
0x1400132d1  mov     [rsp-38h+arg_18], r9
0x1400132d6  push    rbp
0x1400132d7  push    rsi
0x1400132d8  push    rdi
0x1400132d9  push    r12
0x1400132db  push    r13
0x1400132dd  push    r14
0x1400132df  push    r15
0x1400132e1  mov     rbp, rsp
0x1400132e4  sub     rsp, 70h
0x1400132e8  mov     rax, [rdx+50h]
0x1400132ec  xorps   xmm0, xmm0
0x1400132ef  mov     [rbp+arg_8], rax
0x1400132f3  mov     rsi, r8
0x1400132f6  movups  [rbp+var_18], xmm0
0x1400132fa  mov     r13, rdx
0x1400132fd  mov     [rbp+arg_0], 0
0x140013305  mov     rdi, rcx
0x140013308  mov     rcx, cs:WPP_GLOBAL_Control
0x14001330f  lea     rax, WPP_GLOBAL_Control
0x140013316  cmp     rcx, rax
0x140013319  jz      short loc_140013337
0x14001331b  mov     eax, [rcx+2Ch]
0x14001331e  test    al, 40h
0x140013320  jz      short loc_140013337
0x140013322  mov     rcx, [rcx+18h]
0x140013326  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14001332d  mov     edx, 0ABh
0x140013332  call    WPP_SF_
0x140013337  mov     rax, [rdi+20h]
0x14001333b  mov     rcx, [rax+20h]
0x14001333f  mov     rbx, [rcx+20h]
0x140013343  mov     r15d, [rbx+58h]
0x140013347  cmp     r15d, 3
0x14001334b  setz    r12b
0x14001334f  test    rbx, rbx
0x140013352  jz      loc_140013804
0x140013358  mov     rax, [rdi+28h]
0x14001335c  mov     [rbp+var_20], rax
0x140013360  test    rax, rax
0x140013363  jz      loc_140013804
0x140013369  mov     rcx, rsi
0x14001336c  call    HacIsEntryFake
0x140013371  test    al, al
0x140013373  jz      short loc_14001337F
0x140013375  mov     eax, 0C0000022h
0x14001337a  jmp     loc_140013809
0x14001337f  mov     r9d, [rbx+58h]
0x140013383  lea     rcx, [rbx+74h]
0x140013387  mov     r8d, [rbx+54h]
0x14001338b  mov     edx, [rbx+50h]
0x14001338e  mov     [rsp+70h+var_40], rdi
0x140013393  mov     dword ptr [rsp+70h+var_48], 44h ; 'D'
0x14001339b  mov     dword ptr [rsp+70h+var_50], 5
0x1400133a3  call    NfsRdrBuildCall
0x1400133a8  mov     r14, rax
0x1400133ab  test    rax, rax
0x1400133ae  jnz     short loc_1400133ED
0x1400133b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133b7  lea     r15, WPP_GLOBAL_Control
0x1400133be  mov     dil, 1
0x1400133c1  cmp     rcx, r15
0x1400133c4  jz      short loc_1400133E3
0x1400133c6  mov     eax, [rcx+2Ch]
0x1400133c9  test    dil, al
0x1400133cc  jz      short loc_1400133E3
0x1400133ce  mov     rcx, [rcx+18h]
0x1400133d2  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400133d9  mov     edx, 0ACh
0x1400133de  call    WPP_SF_
0x1400133e3  mov     ebx, 0C000009Ah
0x1400133e8  jmp     loc_1400137D4
0x1400133ed  mov     rcx, rsi
0x1400133f0  call    HacAcquireLock
0x1400133f5  lea     rdx, [rsi+0D8h]
0x1400133fc  mov     r8b, r12b
0x1400133ff  mov     rcx, r14
0x140013402  call    XdrEncodeNfsFileHandleUnsafe
0x140013407  mov     rcx, [rsi+28h]; Mutex
0x14001340b  xor     edx, edx; Wait
0x14001340d  call    cs:__imp_KeReleaseMutex
0x140013414  nop     dword ptr [rax+rax+00h]
0x140013419  cmp     dword ptr [r14+108h], 0
0x140013421  jge     short loc_140013462
0x140013423  mov     rcx, cs:WPP_GLOBAL_Control
0x14001342a  lea     r15, WPP_GLOBAL_Control
0x140013431  mov     dil, 1
0x140013434  cmp     rcx, r15
0x140013437  jz      short loc_140013456
0x140013439  mov     eax, [rcx+2Ch]
0x14001343c  test    dil, al
0x14001343f  jz      short loc_140013456
0x140013441  mov     rcx, [rcx+18h]
0x140013445  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14001344c  mov     edx, 0ADh
0x140013451  call    WPP_SF_
0x140013456  mov     ebx, [r14+108h]
0x14001345d  jmp     loc_1400137C5
0x140013462  mov     [rsp+70h+var_30], 0
0x14001346a  lea     rcx, [rbp+arg_0]
0x14001346e  mov     [rsp+70h+var_38], rcx
0x140013473  lea     rax, [rbx+48h]
0x140013477  mov     [rsp+70h+var_40], r14
0x14001347c  mov     r9, r13
0x14001347f  mov     r13, [rbp+arg_8]
0x140013483  mov     r8, rdi
0x140013486  mov     [rsp+70h+var_48], rax
0x14001348b  mov     rcx, r13
0x14001348e  mov     rax, [rdi+28h]
0x140013492  mov     [rsp+70h+var_50], rax
0x140013497  call    NfsSendWaitReply
0x14001349c  mov     ebx, eax
0x14001349e  mov     dil, 1
0x1400134a1  test    eax, eax
0x1400134a3  js      loc_140013792
0x1400134a9  mov     rcx, [rbp+arg_0]
0x1400134ad  test    rcx, rcx
0x1400134b0  jz      loc_140013792
0x1400134b6  call    OncRpcMapRpcStatusToNtStatus
0x1400134bb  mov     ebx, eax
0x1400134bd  test    eax, eax
0x1400134bf  jns     short loc_1400134EE
0x1400134c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134c8  lea     r15, WPP_GLOBAL_Control
0x1400134cf  cmp     rcx, r15
0x1400134d2  jz      loc_140013780
0x1400134d8  mov     eax, [rcx+2Ch]
0x1400134db  test    dil, al
0x1400134de  jz      loc_140013780
0x1400134e4  mov     edx, 0AFh
0x1400134e9  jmp     loc_1400136DE
0x1400134ee  mov     rcx, [rbp+arg_0]
0x1400134f2  call    XdrDecodeInt
0x1400134f7  mov     ebx, eax
0x1400134f9  cmp     r15d, 3
0x1400134fd  jnz     short loc_14001354E
0x1400134ff  mov     rcx, [rbp+arg_0]
0x140013503  call    XdrDecodeBool
0x140013508  test    al, al
0x14001350a  jz      short loc_14001354E
0x14001350c  mov     rcx, rsi
0x14001350f  call    HacAcquireLock
0x140013514  mov     rcx, [rbp+arg_0]
0x140013518  lea     rdx, [rsi+80h]
0x14001351f  mov     r8b, r12b
0x140013522  call    XdrDecodeNfsFileAttributes
0x140013527  mov     rcx, [rsi+28h]; Mutex
0x14001352b  xor     edx, edx; Wait
0x14001352d  call    cs:__imp_KeReleaseMutex
0x140013534  nop     dword ptr [rax+rax+00h]
0x140013539  mov     rax, [rbp+arg_0]
0x14001353d  cmp     dword ptr [rax+108h], 0
0x140013544  jl      short loc_14001354E
0x140013546  mov     rcx, rsi
0x140013549  call    HacUpdateTimeStamp
0x14001354e  mov     rax, [rbp+arg_0]
0x140013552  cmp     dword ptr [rax+108h], 0
0x140013559  jge     short loc_140013588
0x14001355b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013562  lea     r15, WPP_GLOBAL_Control
0x140013569  cmp     rcx, r15
0x14001356c  jz      loc_140013671
0x140013572  mov     eax, [rcx+2Ch]
0x140013575  test    dil, al
0x140013578  jz      loc_140013671
0x14001357e  mov     edx, 0B0h
0x140013583  jmp     loc_140013661
0x140013588  test    ebx, ebx
0x14001358a  jz      loc_140013614
0x140013590  mov     rcx, cs:WPP_GLOBAL_Control
0x140013597  lea     r15, WPP_GLOBAL_Control
0x14001359e  cmp     rcx, r15
0x1400135a1  jz      short loc_1400135C3
0x1400135a3  mov     eax, [rcx+2Ch]
0x1400135a6  test    dil, al
0x1400135a9  jz      short loc_1400135C3
0x1400135ab  mov     rcx, [rcx+18h]
0x1400135af  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400135b6  mov     edx, 0B1h
0x1400135bb  mov     r9d, ebx
0x1400135be  call    WPP_SF_d
0x1400135c3  mov     ecx, ebx
0x1400135c5  call    MapNFSStatusToNtStatus
0x1400135ca  mov     ebx, eax
0x1400135cc  cmp     eax, 0C0000008h
0x1400135d1  jnz     loc_140013780
0x1400135d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135de  cmp     rcx, r15
0x1400135e1  jz      short loc_140013604
0x1400135e3  mov     eax, [rcx+2Ch]
0x1400135e6  test    dil, al
0x1400135e9  jz      short loc_140013604
0x1400135eb  mov     rcx, [rcx+18h]
0x1400135ef  lea     r9, [rsi+40h]
0x1400135f3  mov     edx, 0B2h
0x1400135f8  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400135ff  call    WPP_SF_Z
0x140013604  mov     rdx, rsi
0x140013607  mov     rcx, r13
0x14001360a  call    HacOrphanStaleEntry
0x14001360f  jmp     loc_140013780
0x140013614  mov     rcx, [rbp+arg_0]
0x140013618  call    XdrDecodeInt
0x14001361d  mov     rcx, [rbp+arg_0]
0x140013621  mov     edx, eax
0x140013623  mov     rcx, [rcx+48h]
0x140013627  test    rcx, rcx
0x14001362a  jz      short loc_140013630
0x14001362c  mov     rcx, [rcx+40h]
0x140013630  mov     rax, [rbp+arg_0]
0x140013634  mov     qword ptr [rbp+var_18+8], rcx
0x140013638  cmp     dword ptr [rax+108h], 0
0x14001363f  jge     short loc_140013680
0x140013641  mov     rcx, cs:WPP_GLOBAL_Control
0x140013648  lea     r15, WPP_GLOBAL_Control
0x14001364f  cmp     rcx, r15
0x140013652  jz      short loc_140013671
0x140013654  mov     eax, [rcx+2Ch]
0x140013657  test    dil, al
0x14001365a  jz      short loc_140013671
0x14001365c  mov     edx, 0B3h
0x140013661  mov     rcx, [rcx+18h]
0x140013665  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14001366c  call    WPP_SF_
0x140013671  mov     rax, [rbp+arg_0]
0x140013675  mov     ebx, [rax+108h]
0x14001367b  jmp     loc_140013780
0x140013680  lea     eax, [rdx-1]
0x140013683  cmp     eax, 3FFh
0x140013688  ja      loc_14001374B
0x14001368e  mov     rax, [rbp+var_20]
0x140013692  lea     r8, [rbp+var_18]
0x140013696  mov     word ptr [rbp+var_18], dx
0x14001369a  mov     r9b, dil
0x14001369d  mov     rdx, [rbp+arg_18]
0x1400136a1  mov     rcx, r13
0x1400136a4  mov     eax, [rax+20h]
0x1400136a7  mov     dword ptr [rsp+70h+var_50], eax
0x1400136ab  call    NfsConvertAnsiToUnicode
0x1400136b0  mov     ebx, eax
0x1400136b2  test    eax, eax
0x1400136b4  jns     short loc_1400136F6
0x1400136b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400136bd  lea     r15, WPP_GLOBAL_Control
0x1400136c4  cmp     rcx, r15
0x1400136c7  jz      loc_140013780
0x1400136cd  mov     eax, [rcx+2Ch]
0x1400136d0  test    dil, al
0x1400136d3  jz      loc_140013780
0x1400136d9  mov     edx, 0B5h
0x1400136de  mov     rcx, [rcx+18h]
0x1400136e2  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400136e9  mov     r9d, ebx
0x1400136ec  call    WPP_SF_d
0x1400136f1  jmp     loc_140013780
0x1400136f6  mov     rcx, [rbp+arg_0]
0x1400136fa  call    cs:__imp_OncRpcDestroy
0x140013701  nop     dword ptr [rax+rax+00h]
0x140013706  mov     rcx, r14
0x140013709  call    cs:__imp_OncRpcDestroy
0x140013710  nop     dword ptr [rax+rax+00h]
0x140013715  mov     rcx, cs:WPP_GLOBAL_Control
0x14001371c  lea     r15, WPP_GLOBAL_Control
0x140013723  cmp     rcx, r15
0x140013726  jz      short loc_140013744
0x140013728  mov     eax, [rcx+2Ch]
0x14001372b  test    al, 40h
0x14001372d  jz      short loc_140013744
0x14001372f  mov     rcx, [rcx+18h]
0x140013733  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14001373a  mov     edx, 0B6h
0x14001373f  call    WPP_SF_
0x140013744  xor     eax, eax
0x140013746  jmp     loc_140013809
0x14001374b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013752  lea     r15, WPP_GLOBAL_Control
0x140013759  cmp     rcx, r15
0x14001375c  jz      short loc_14001377B
0x14001375e  mov     eax, [rcx+2Ch]
0x140013761  test    dil, al
0x140013764  jz      short loc_14001377B
0x140013766  mov     rcx, [rcx+18h]
0x14001376a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140013771  mov     edx, 0B4h
0x140013776  call    WPP_SF_
0x14001377b  mov     ebx, 0C00000C3h
0x140013780  mov     rcx, [rbp+arg_0]
0x140013784  call    cs:__imp_OncRpcDestroy
0x14001378b  nop     dword ptr [rax+rax+00h]
0x140013790  jmp     short loc_1400137C5
0x140013792  mov     rcx, cs:WPP_GLOBAL_Control
0x140013799  lea     r15, WPP_GLOBAL_Control
0x1400137a0  cmp     rcx, r15
0x1400137a3  jz      short loc_1400137C5
0x1400137a5  mov     eax, [rcx+2Ch]
0x1400137a8  test    dil, al
0x1400137ab  jz      short loc_1400137C5
0x1400137ad  mov     rcx, [rcx+18h]
0x1400137b1  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
  ... truncated ...
```

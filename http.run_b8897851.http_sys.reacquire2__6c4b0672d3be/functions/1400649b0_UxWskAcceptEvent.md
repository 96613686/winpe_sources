# UxWskAcceptEvent

- ea: `0x1400649b0`
- end: `0x140064ffb`
- name: `UxWskAcceptEvent`
- size: `1611`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x140051410`
- `0x14005d530`
- `0x14005d930`
- `0x140060adc`
- `0x140064800`
- `0x1400649b0`
- `0x140065010`
- `0x140065040`
- `0x140065080`
- `0x140065180`
- `0x140065240`
- `0x1401677e0`
- `0x140167840`
- `0x140167b40`
- `0x1401d834c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!EtwProviderEnabled` at `0x140064c92`
- `ntoskrnl!EtwProviderEnabled` at `0x140064c92`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a26`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a26`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064a5c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064c4c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064a5c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064c4c`
- `ntoskrnl!EtwActivityIdControl` at `0x140064cae`
- `ntoskrnl!EtwActivityIdControl` at `0x140064cae`
- `ntoskrnl!IoAllocateIrp` at `0x140064bea`
- `ntoskrnl!IoAllocateIrp` at `0x140064bea`
- `ntoskrnl!KeReadStateEvent` at `0x140064db2`
- `ntoskrnl!KeReadStateEvent` at `0x140064db2`
- `ntoskrnl!KfRaiseIrql` at `0x140064f5d`
- `ntoskrnl!KfRaiseIrql` at `0x140064f5d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064a48`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064ecd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064a48`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064ecd`
- `ntoskrnl!KeLowerIrql` at `0x140064fea`
- `ntoskrnl!KeLowerIrql` at `0x140064fea`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064af0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064c73`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064af0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064c73`
- `HAL!KeQueryPerformanceCounter` at `0x140064aab`
- `HAL!KeQueryPerformanceCounter` at `0x140064aab`

## pseudocode

```c
__int64 __fastcall UxWskAcceptEvent(
        __int64 a1,
        __int64 a2,
        ADDRESS_FAMILY *a3,
        ADDRESS_FAMILY *a4,
        __int64 a5,
        volatile signed __int32 **a6,
        _QWORD *a7)
{
  volatile signed __int32 *v7; // rbx
  unsigned int v10; // ebp
  __int64 v11; // rbx
  USHORT CurrentNodeNumber; // ax
  volatile signed __int32 *v13; // rax
  int v14; // eax
  int v15; // eax
  UCHAR v16; // al
  _WORD *v17; // r12
  UCHAR v18; // al
  const void *v19; // rdx
  _WORD *v20; // r15
  __int16 v21; // dx
  _QWORD *v22; // rcx
  int v23; // eax
  _QWORD *v24; // rcx
  int v25; // eax
  PIRP Irp; // rax
  int LockArray_high; // edi
  unsigned __int64 v28; // rdi
  _DWORD *v29; // rax
  int v30; // edx
  int v31; // ecx
  int v32; // edi
  int v33; // r8d
  int v34; // eax
  int v35; // eax
  __int64 v37; // rdi
  USHORT v38; // ax
  int v39; // eax
  int v40; // [rsp+20h] [rbp-78h]
  KIRQL v41; // [rsp+40h] [rbp-58h]
  __int64 v42; // [rsp+48h] [rbp-50h] BYREF
  __int64 v43; // [rsp+50h] [rbp-48h] BYREF
  char v44; // [rsp+A0h] [rbp+8h]

  v7 = 0;
  v44 = 0;
  v10 = -1073741616;
  v41 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( !a5 )
  {
    v32 = -1073741616;
    goto LABEL_38;
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v32 = -1073741436;
    goto LABEL_38;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 200) + 8354LL) && !KeReadStateEvent(UxHighNonPagedPoolEvent) )
  {
    v32 = -1073741258;
    goto LABEL_38;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    v41 = KfRaiseIrql(2u);
    v44 = 1;
  }
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8680LL);
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  v13 = (volatile signed __int32 *)ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11
                                                                                       + 8LL * CurrentNodeNumber
                                                                                       + 8));
  v7 = v13;
  if ( !v13 )
  {
    v32 = -1073741670;
    goto LABEL_38;
  }
  *((_DWORD *)v13 + 8) = 1129606229;
  v14 = _InterlockedIncrement(v13 + 9);
  if ( UxDebugCheckRefcount && v14 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 1u, v14);
  memset((void *)(v7 + 10), 0, 0x268u);
  *((LARGE_INTEGER *)v7 + 67) = KeQueryPerformanceCounter(0);
  *((_QWORD *)v7 + 54) = 0;
  *((_QWORD *)v7 + 56) = 0;
  *((_QWORD *)v7 + 58) = 0;
  UlPmAssociateTlConnection(v7);
  *(_OWORD *)(v7 + 10) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_DWORD *)v7 + 14) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)v7 + 15);
  *((_QWORD *)v7 + 29) = 0;
  *((_QWORD *)v7 + 17) = v7 + 32;
  *((_QWORD *)v7 + 16) = v7 + 32;
  *((_DWORD *)v7 + 132) = 2;
  *((_QWORD *)v7 + 26) = a1;
  v15 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, a1 + 8, 0xFu, v15);
  v16 = SOCKADDR_SIZE(*a3);
  if ( v16 > 0x1Cu )
  {
    v32 = -1073741595;
    goto LABEL_38;
  }
  v17 = v7 + 37;
  memmove((void *)(v7 + 37), a3, v16);
  v18 = SOCKADDR_SIZE(*a4);
  if ( v18 > 0x1Cu )
  {
    v32 = -1073741595;
    goto LABEL_38;
  }
  v20 = v7 + 44;
  memmove((void *)(v7 + 44), v19, v18);
  v21 = 23;
  if ( *v17 == 23 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v7 + 39)) )
  {
    v23 = *((_DWORD *)v7 + 42);
    *v17 = 2;
    *((_DWORD *)v7 + 38) = v23;
    *v22 = 0;
  }
  if ( v21 == *v20 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v7 + 46)) )
  {
    v25 = *((_DWORD *)v7 + 49);
    *v20 = 2;
    *((_DWORD *)v7 + 45) = v25;
    *v24 = 0;
  }
  Irp = IoAllocateIrp(1, 0);
  *((_QWORD *)v7 + 12) = Irp;
  if ( !Irp )
    goto LABEL_53;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  LODWORD(v42) = LockArray_high;
  if ( UxDebugDisableLookaside )
  {
    v29 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0390)(
                      (unsigned int)dword_1401A0378,
                      qword_1401A0380,
                      (unsigned int)dword_1401A0388,
                      0);
  }
  else
  {
    if ( UxCompactMode )
    {
      v37 = qword_1401A0370;
      v38 = KeGetCurrentNodeNumber();
      v29 = (_DWORD *)PplAllocateFromLookasideListProcessor(v37, v38);
    }
    else
    {
      v28 = qword_1401A0370 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v28 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0370, v28 + 64);
      v29 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v28 + 64));
    }
    LockArray_high = v42;
  }
  if ( !v29 )
  {
    *((_QWORD *)v7 + 13) = 0;
LABEL_53:
    v32 = -1073741670;
    goto LABEL_38;
  }
  *v29 = LockArray_high;
  *((_QWORD *)v7 + 13) = v29;
  *((_QWORD *)v7 + 9) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)v7 + 8);
  if ( EtwProviderEnabled(*(_QWORD *)(*(_QWORD *)(a1 + 200) + 1688LL), 0, 0) )
    EtwActivityIdControl(3u, (LPGUID)(v7 + 102));
  v32 = UlEtInitializeEdgeTraversalCheck(v7);
  if ( v32 >= 0 )
  {
    if ( SBYTE2(xmmword_1401A2CA0) < 0 )
      WPP_SF_qD_SOCKADDR__SOCKADDR_(
        v31,
        v30,
        v33,
        (_DWORD)v7,
        *(_DWORD *)(a1 + 12),
        (__int64)(v7 + 37),
        (__int64)(v7 + 44));
    v34 = _InterlockedIncrement(v7 + 9);
    if ( UxDebugCheckRefcount && v34 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 0x37u, v34);
    v40 = *(_DWORD *)(a1 + 12);
    v42 = 0;
    v43 = 0;
    v35 = UxSslAttachConnection((_DWORD)v7, (unsigned int)UxTlDispatch, (unsigned int)&v42, (unsigned int)&v43, v40);
    v32 = v35;
    if ( v35 >= 0 )
    {
      *((_QWORD *)v7 + 5) = v42;
      *((_QWORD *)v7 + 6) = v43;
      *((_DWORD *)v7 + 14) = 2;
      *a6 = v7;
      *a7 = &UxWskClientConnDispatch;
      *((_QWORD *)v7 + 10) = a5;
      if ( (int)UxTlIoReadyEvent(v7) >= 0 )
        goto LABEL_41;
      if ( SBYTE2(xmmword_1401A2C90) < 0 )
        WPP_SF_qD(535, 17, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids, v7, v32);
      goto LABEL_35;
    }
    if ( SBYTE2(xmmword_1401A2C90) < 0 )
      WPP_SF_qD(535, 16, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids, v7, v35);
    v39 = _InterlockedDecrement(v7 + 9);
    if ( UxDebugCheckRefcount && v39 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 0x37u, v39);
    if ( !v39 )
      UxTlDestroyConnection((char *)v7);
  }
LABEL_38:
  if ( _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 200) + 8424LL)) == 1 )
    UlEnablePeriodicScavenger(*(_QWORD *)(a1 + 200) + 8432LL);
  if ( v7 )
LABEL_35:
    UxTlCleanupConnection((PVOID)v7);
LABEL_41:
  if ( v44 )
    KeLowerIrql(v41);
  if ( v32 >= 0 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x1400649b0  mov     [rsp+arg_8], rbx
0x1400649b5  mov     [rsp+arg_18], r9
0x1400649ba  push    rbp
0x1400649bb  push    rsi
0x1400649bc  push    rdi
0x1400649bd  push    r12
0x1400649bf  push    r13
0x1400649c1  push    r14
0x1400649c3  push    r15
0x1400649c5  sub     rsp, 60h
0x1400649c9  mov     rax, [rsp+98h+arg_28]
0x1400649d1  xor     r12d, r12d
0x1400649d4  mov     ebx, r12d
0x1400649d7  mov     r15, r8
0x1400649da  mov     rsi, rcx
0x1400649dd  mov     [rsp+98h+arg_0], bl
0x1400649e4  mov     ebp, 0C00000D0h
0x1400649e9  mov     [rsp+98h+var_58], bl
0x1400649ed  mov     [rax], r12
0x1400649f0  mov     rax, [rsp+98h+arg_30]
0x1400649f8  mov     [rax], r12
0x1400649fb  cmp     [rsp+98h+arg_20], r12
0x140064a03  jz      loc_140064F3E
0x140064a09  cmp     [rcx+18h], rbx
0x140064a0d  jz      loc_140064F4B
0x140064a13  mov     rax, [rcx+0C8h]
0x140064a1a  cmp     [rax+20A2h], bl
0x140064a20  jnz     loc_140064DAB
0x140064a26  call    cs:__imp_KeGetCurrentIrql
0x140064a2d  nop     dword ptr [rax+rax+00h]
0x140064a32  cmp     al, 2
0x140064a34  jb      loc_140064F5B
0x140064a3a  mov     rax, [rsi+0C8h]
0x140064a41  mov     rbx, [rax+21E8h]
0x140064a48  call    cs:__imp_KeGetCurrentNodeNumber
0x140064a4f  nop     dword ptr [rax+rax+00h]
0x140064a54  movzx   ecx, ax
0x140064a57  mov     rcx, [rbx+rcx*8+8]; Lookaside
0x140064a5c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140064a63  nop     dword ptr [rax+rax+00h]
0x140064a68  mov     rbx, rax
0x140064a6b  mov     r13d, 1
0x140064a71  test    rax, rax
0x140064a74  jz      loc_140064F7A
0x140064a7a  mov     dword ptr [rax+20h], 43546C55h
0x140064a81  mov     eax, r13d
0x140064a84  lock xadd [rbx+24h], eax
0x140064a89  inc     eax
0x140064a8b  cmp     cs:UxDebugCheckRefcount, r12b
0x140064a92  jnz     loc_140064E31
0x140064a98  xor     edx, edx; Val
0x140064a9a  lea     rcx, [rbx+28h]; void *
0x140064a9e  mov     r8d, 268h; Size
0x140064aa4  call    memset
0x140064aa9  xor     ecx, ecx; PerformanceFrequency
0x140064aab  call    cs:__imp_KeQueryPerformanceCounter
0x140064ab2  nop     dword ptr [rax+rax+00h]
0x140064ab7  mov     [rbx+218h], rax
0x140064abe  mov     rcx, rbx
0x140064ac1  mov     [rbx+1B0h], r12
0x140064ac8  mov     [rbx+1C0h], r12
0x140064acf  mov     [rbx+1D0h], r12
0x140064ad6  call    UlPmAssociateTlConnection
0x140064adb  xorps   xmm0, xmm0
0x140064ade  lea     rcx, [rbx+78h]; SpinLock
0x140064ae2  movups  xmmword ptr [rbx+28h], xmm0
0x140064ae6  xor     eax, eax
0x140064ae8  mov     [rbx+38h], rax
0x140064aec  mov     [rbx+38h], r13d
0x140064af0  call    cs:__imp_KeInitializeSpinLock
0x140064af7  nop     dword ptr [rax+rax+00h]
0x140064afc  lea     rax, [rbx+80h]
0x140064b03  mov     [rbx+0E8h], r12
0x140064b0a  mov     [rax+8], rax
0x140064b0e  lea     rdx, [rsi+8]; BugCheckParameter2
0x140064b12  mov     [rax], rax
0x140064b15  mov     edi, 2
0x140064b1a  mov     [rbx+210h], edi
0x140064b20  mov     eax, r13d
0x140064b23  mov     [rbx+0D0h], rsi
0x140064b2a  lock xadd [rdx], eax
0x140064b2e  inc     eax
0x140064b30  cmp     cs:UxDebugCheckRefcount, r12b
0x140064b37  jnz     loc_140064E4F
0x140064b3d  movzx   ecx, word ptr [r15]; af
0x140064b41  call    SOCKADDR_SIZE
0x140064b46  cmp     al, 1Ch
0x140064b48  ja      loc_140064F84
0x140064b4e  lea     r12, [rbx+94h]
0x140064b55  movzx   r8d, al; Size
0x140064b59  mov     rcx, r12; void *
0x140064b5c  mov     rdx, r15; Src
0x140064b5f  call    memmove
0x140064b64  mov     rdx, [rsp+98h+arg_18]
0x140064b6c  movzx   ecx, word ptr [rdx]; af
0x140064b6f  call    SOCKADDR_SIZE
0x140064b74  cmp     al, 1Ch
0x140064b76  ja      loc_140064F8E
0x140064b7c  lea     r15, [rbx+0B0h]
0x140064b83  movzx   r8d, al; Size
0x140064b87  mov     rcx, r15; void *
0x140064b8a  call    memmove
0x140064b8f  mov     edx, 17h
0x140064b94  cmp     dx, [r12]
0x140064b99  jnz     short loc_140064BBE
0x140064b9b  lea     rcx, [r12+8]; a
0x140064ba0  call    IN6_IS_ADDR_V4MAPPED
0x140064ba5  test    al, al
0x140064ba7  jz      short loc_140064BBE
0x140064ba9  mov     eax, [rbx+0A8h]
0x140064baf  mov     [r12], di
0x140064bb4  mov     [r12+4], eax
0x140064bb9  xor     eax, eax
0x140064bbb  mov     [rcx], rax
0x140064bbe  cmp     dx, [r15]
0x140064bc2  jnz     short loc_140064BE4
0x140064bc4  lea     rcx, [r15+8]; a
0x140064bc8  call    IN6_IS_ADDR_V4MAPPED
0x140064bcd  test    al, al
0x140064bcf  jz      short loc_140064BE4
0x140064bd1  mov     eax, [rbx+0C4h]
0x140064bd7  mov     [r15], di
0x140064bdb  mov     [r15+4], eax
0x140064bdf  xor     eax, eax
0x140064be1  mov     [rcx], rax
0x140064be4  xor     edx, edx; ChargeQuota
0x140064be6  movzx   ecx, r13b; StackSize
0x140064bea  call    cs:__imp_IoAllocateIrp
0x140064bf1  nop     dword ptr [rax+rax+00h]
0x140064bf6  mov     [rbx+60h], rax
0x140064bfa  test    rax, rax
0x140064bfd  jz      loc_140064E91
0x140064c03  mov     edi, gs:1A4h
0x140064c0b  cmp     cs:UxDebugDisableLookaside, 0
0x140064c12  mov     dword ptr [rsp+98h+var_50], edi
0x140064c16  jnz     loc_140064E9E
0x140064c1c  cmp     cs:UxCompactMode, 0
0x140064c23  jnz     loc_140064EC6
0x140064c29  mov     rcx, cs:qword_1401A0370
0x140064c30  inc     edi
0x140064c32  shl     rdi, 7
0x140064c36  add     rdi, rcx
0x140064c39  movzx   eax, byte ptr [rdi+0B0h]
0x140064c40  test    al, al
0x140064c42  jz      loc_140064EE9
0x140064c48  lea     rcx, [rdi+40h]; Lookaside
0x140064c4c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140064c53  nop     dword ptr [rax+rax+00h]
0x140064c58  mov     edi, dword ptr [rsp+98h+var_50]
0x140064c5c  test    rax, rax
0x140064c5f  jz      loc_140064E8D
0x140064c65  mov     [rax], edi
0x140064c67  lea     rcx, [rbx+40h]; SpinLock
0x140064c6b  mov     [rbx+68h], rax
0x140064c6f  mov     [rbx+48h], r13
0x140064c73  call    cs:__imp_KeInitializeSpinLock
0x140064c7a  nop     dword ptr [rax+rax+00h]
0x140064c7f  mov     rcx, [rsi+0C8h]
0x140064c86  xor     r8d, r8d; Keyword
0x140064c89  xor     edx, edx; Level
0x140064c8b  mov     rcx, [rcx+698h]; RegHandle
0x140064c92  call    cs:__imp_EtwProviderEnabled
0x140064c99  nop     dword ptr [rax+rax+00h]
0x140064c9e  test    al, al
0x140064ca0  jz      short loc_140064CBA
0x140064ca2  lea     rdx, [rbx+198h]; ActivityId
0x140064ca9  mov     ecx, 3; ControlCode
0x140064cae  call    cs:__imp_EtwActivityIdControl
0x140064cb5  nop     dword ptr [rax+rax+00h]
0x140064cba  mov     rcx, rbx
0x140064cbd  call    UlEtInitializeEdgeTraversalCheck
0x140064cc2  mov     edi, eax
0x140064cc4  test    eax, eax
0x140064cc6  js      loc_140064E96
0x140064ccc  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x140064cd3  jl      loc_140064F98
0x140064cd9  mov     eax, r13d
0x140064cdc  lock xadd [rbx+24h], eax
0x140064ce1  inc     eax
0x140064ce3  cmp     cs:UxDebugCheckRefcount, 0
0x140064cea  jnz     loc_140064E6C
0x140064cf0  mov     eax, [rsi+0Ch]
0x140064cf3  lea     r9, [rsp+98h+var_48]
0x140064cf8  xor     r12d, r12d
0x140064cfb  mov     [rsp+98h+var_78], eax
0x140064cff  lea     r8, [rsp+98h+var_50]
0x140064d04  mov     [rsp+98h+var_50], r12
0x140064d09  lea     rdx, UxTlDispatch
0x140064d10  mov     [rsp+98h+var_48], r12
0x140064d15  mov     rcx, rbx
0x140064d18  call    UxSslAttachConnection
0x140064d1d  mov     edi, eax
0x140064d1f  test    eax, eax
0x140064d21  js      loc_140064FB6
0x140064d27  mov     rax, [rsp+98h+var_50]
0x140064d2c  lea     rcx, UxWskClientConnDispatch
0x140064d33  mov     [rbx+28h], rax
0x140064d37  mov     rax, [rsp+98h+var_48]
0x140064d3c  mov     [rbx+30h], rax
0x140064d40  mov     rax, [rsp+98h+arg_28]
0x140064d48  mov     dword ptr [rbx+38h], 2
0x140064d4f  mov     [rax], rbx
0x140064d52  mov     rax, [rsp+98h+arg_30]
0x140064d5a  mov     [rax], rcx
0x140064d5d  mov     rcx, rbx
0x140064d60  mov     rax, [rsp+98h+arg_20]
0x140064d68  mov     [rbx+50h], rax
0x140064d6c  call    UxTlIoReadyEvent
0x140064d71  test    eax, eax
0x140064d73  jns     loc_140064E02
0x140064d79  cmp     byte ptr cs:xmmword_1401A2C90+2, r12b
0x140064d80  jge     short loc_140064D9F
0x140064d82  mov     edx, 11h
0x140064d87  mov     [rsp+98h+var_78], edi
0x140064d8b  mov     ecx, 217h
0x140064d90  lea     r8, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids
0x140064d97  mov     r9, rbx
0x140064d9a  call    WPP_SF_qD
0x140064d9f  xor     edx, edx
0x140064da1  mov     rcx, rbx; Entry
0x140064da4  call    UxTlCleanupConnection
0x140064da9  jmp     short loc_140064E02
0x140064dab  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140064db2  call    cs:__imp_KeReadStateEvent
0x140064db9  nop     dword ptr [rax+rax+00h]
0x140064dbe  test    eax, eax
0x140064dc0  jnz     loc_140064A26
0x140064dc6  mov     edi, 0C0000236h
0x140064dcb  mov     r13d, 1
0x140064dd1  mov     rax, [rsi+0C8h]
0x140064dd8  lock xadd [rax+20E8h], r13d
0x140064de1  inc     r13d
0x140064de4  cmp     r13d, 1
0x140064de8  jnz     short loc_140064DFD
0x140064dea  mov     rcx, [rsi+0C8h]
0x140064df1  add     rcx, 20F0h
0x140064df8  call    UlEnablePeriodicScavenger
0x140064dfd  test    rbx, rbx
0x140064e00  jnz     short loc_140064D9F
0x140064e02  cmp     [rsp+98h+arg_0], 0
0x140064e0a  jnz     loc_140064FE5
0x140064e10  mov     rbx, [rsp+98h+arg_8]
0x140064e18  test    edi, edi
0x140064e1a  cmovns  ebp, r12d
0x140064e1e  mov     eax, ebp
0x140064e20  add     rsp, 60h
0x140064e24  pop     r15
0x140064e26  pop     r14
0x140064e28  pop     r13
0x140064e2a  pop     r12
0x140064e2c  pop     rdi
0x140064e2d  pop     rsi
0x140064e2e  pop     rbp
0x140064e2f  retn
0x140064e31  cmp     eax, 0FFFFFFFFh
0x140064e34  jg      loc_140064A98
0x140064e3a  movsxd  r9, eax; BugCheckParameter4
0x140064e3d  lea     rdx, [rbx+24h]; BugCheckParameter2
0x140064e41  mov     r8, r13; BugCheckParameter3
0x140064e44  mov     ecx, 3; BugCheckParameter1
0x140064e49  call    UlBugCheckEx
0x140064e4f  cmp     eax, 0FFFFFFFFh
0x140064e52  jg      loc_140064B3D
0x140064e58  movsxd  r9, eax; BugCheckParameter4
0x140064e5b  mov     ecx, 3; BugCheckParameter1
0x140064e60  mov     r8d, 0Fh; BugCheckParameter3
0x140064e66  call    UlBugCheckEx
0x140064e6c  cmp     eax, 0FFFFFFFFh
0x140064e6f  jg      loc_140064CF0
0x140064e75  movsxd  r9, eax; BugCheckParameter4
0x140064e78  lea     rdx, [rbx+24h]; BugCheckParameter2
0x140064e7c  mov     r8d, 37h ; '7'; BugCheckParameter3
0x140064e82  mov     ecx, 3; BugCheckParameter1
0x140064e87  call    UlBugCheckEx
0x140064e8d  mov     [rbx+68h], rax
0x140064e91  mov     edi, 0C000009Ah
0x140064e96  xor     r12d, r12d
0x140064e99  jmp     loc_140064DD1
0x140064e9e  mov     rax, cs:off_1401A0390
0x140064ea5  xor     r9d, r9d
0x140064ea8  mov     r8d, cs:dword_1401A0388
0x140064eaf  mov     rdx, cs:qword_1401A0380
0x140064eb6  mov     ecx, cs:dword_1401A0378
0x140064ebc  call    _guard_dispatch_icall
0x140064ec1  jmp     loc_140064C5C
0x140064ec6  mov     rdi, cs:qword_1401A0370
0x140064ecd  call    cs:__imp_KeGetCurrentNodeNumber
0x140064ed4  nop     dword ptr [rax+rax+00h]
0x140064ed9  movzx   edx, ax
0x140064edc  mov     rcx, rdi
0x140064edf  call    PplAllocateFromLookasideListProcessor
0x140064ee4  jmp     loc_140064C58
0x140064ee9  lea     rdx, [rdi+40h]
0x140064eed  call    PplpLazyInitializeLookasideList
0x140064ef2  jmp     loc_140064C48
0x140064ef7  mov     eax, 0FFFFFFFFh
0x140064efc  lock xadd [rbx+24h], eax
0x140064f01  dec     eax
0x140064f03  cmp     cs:UxDebugCheckRefcount, r12b
0x140064f0a  jnz     short loc_140064F21
  ... truncated ...
```

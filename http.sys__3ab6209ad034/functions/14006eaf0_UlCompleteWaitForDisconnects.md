# UlCompleteWaitForDisconnects

- ea: `0x14006eaf0`
- end: `0x14006f1ed`
- name: `UlCompleteWaitForDisconnects`
- size: `1789`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037ae0`
- `0x1400568c0`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x14006e4ec`
- `0x14006eaf0`
- `0x14006f200`
- `0x1400705d0`
- `0x14009620c`
- `0x1400a031c`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3974`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da550`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14006efa4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006efa4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006ede8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006ede8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006efc8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006efc8`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006f008`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006f008`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ebaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ec0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ebaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ec0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed3a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006eb5c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006ebe6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006eb5c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006ebe6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006eba3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ec03`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006eba3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ec03`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed2e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed2e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006eeb0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006eeb0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ec82`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ec9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ec82`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ec9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006eb4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ebd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec8e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006eb4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ebd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec8e`

## pseudocode

```c
void __fastcall UlCompleteWaitForDisconnects(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbp
  _DWORD *v5; // rbx
  _QWORD *i; // rsi
  volatile signed __int32 *v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ecx
  int v10; // eax
  __int64 v11; // rsi
  __int64 v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rdx
  volatile signed __int32 *v18; // rdx
  volatile signed __int32 *v19; // rdx
  int v20; // eax
  __int64 v21; // rsi
  int v22; // edi
  bool v23; // zf
  unsigned __int64 v24; // rdi
  int v25; // eax
  __int64 v26; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v28; // r9
  __int64 v29; // rbp
  __int64 v30; // rcx
  char v31; // si
  __int64 v32; // rax
  __int64 v33; // r14
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // [rsp+28h] [rbp-D0h]
  _BYTE v37[8]; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v38; // [rsp+48h] [rbp-B0h]
  _DWORD v39[24]; // [rsp+60h] [rbp-98h] BYREF

  v37[0] = a2;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v34 = *(_QWORD *)(a1 + 48);
    else
      v34 = 0;
    WPP_SF_qqD(1032, 215, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, v34, (unsigned __int8)a2);
  }
  v4 = a1 + 944;
  v5 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    ((void (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), _BYTE *, _QWORD))WPP_SF_qPqqq)(
      a1,
      a2,
      a3,
      v4,
      24,
      UlpCompleteWaitForDisconnects,
      v37,
      0);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v4, 0);
  for ( i = *(_QWORD **)(v4 + 8); i != (_QWORD *)(v4 + 8); i = (_QWORD *)*i )
  {
    v7 = (volatile signed __int32 *)i - 1;
    while ( 1 )
    {
      v8 = *v7;
      if ( !*v7 )
        break;
      v9 = v8 + 1;
      if ( UxDebugCheckRefcount && v9 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v7, 0x21u, v9);
      if ( v8 == _InterlockedCompareExchange(v7, v9, v8) )
      {
        ExReleasePushLockSharedEx(v4, 0);
        KeLeaveCriticalRegion();
        if ( v5 )
        {
          v35 = _InterlockedDecrement(v5 + 5);
          if ( UxDebugCheckRefcount && v35 <= -1 )
            UlBugCheckEx(3u, (ULONG_PTR)(v5 + 5), 0x21u, v35);
          if ( !v35 )
            UlpFreeCoupling(v5);
        }
        UlpCompleteWaitForDisconnects(i - 3, v37, 0);
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(v4, 0);
        v5 = i - 3;
        break;
      }
    }
  }
  ExReleasePushLockSharedEx(v4, 0);
  KeLeaveCriticalRegion();
  if ( !v5 )
    goto LABEL_35;
  v10 = _InterlockedDecrement(v5 + 5);
  if ( UxDebugCheckRefcount && v10 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v5 + 5), 0x21u, v10);
  if ( v10 )
    goto LABEL_35;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5, 0);
  v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v5 + 8) + 264LL) + 8LL * *(unsigned __int16 *)(*((_QWORD *)v5 + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)v5 + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v11, 0);
  v12 = *((_QWORD *)v5 + 3);
  v13 = v5 + 6;
  if ( *(_DWORD **)(v12 + 8) != v5 + 6 )
    goto LABEL_53;
  v14 = (_QWORD *)*((_QWORD *)v5 + 4);
  if ( (_QWORD *)*v14 != v13
    || (*v14 = v12,
        *(_QWORD *)(v12 + 8) = v14,
        *v13 = 0,
        *((_QWORD *)v5 + 4) = 0,
        v15 = v5 + 10,
        v16 = *((_QWORD *)v5 + 5),
        *(_DWORD **)(v16 + 8) != v5 + 10)
    || (v17 = (_QWORD *)*((_QWORD *)v5 + 6), (_QWORD *)*v17 != v15) )
  {
LABEL_53:
    __fastfail(3u);
  }
  *v17 = v16;
  *(_QWORD *)(v16 + 8) = v17;
  *v15 = 0;
  *((_QWORD *)v5 + 6) = 0;
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)v5 + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v18 = (volatile signed __int32 *)*((_QWORD *)v5 + 11);
  if ( v18 )
  {
    v25 = _InterlockedDecrement(v18);
    if ( UxDebugCheckRefcount && v25 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v18, 0xEu, v25);
    if ( !v25 )
      UlConsumerCleanupCompletion(*((_QWORD *)v5 + 11));
    *((_QWORD *)v5 + 11) = 0;
  }
  v19 = (volatile signed __int32 *)*((_QWORD *)v5 + 8);
  v20 = _InterlockedDecrement(v19);
  if ( UxDebugCheckRefcount && v20 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v19, 0xEu, v20);
  if ( !v20 )
    UlFreeRequestQueue(*((PVOID *)v5 + 8));
  v21 = *((_QWORD *)v5 + 7);
  *((_QWORD *)v5 + 8) = 0;
  v22 = _InterlockedDecrement((volatile signed __int32 *)(v21 + 40));
  if ( UxDebugCheckRefcount && v22 <= -1 )
    UlBugCheckEx(3u, v21 + 40, 0xEu, v22);
  if ( v22 )
    goto LABEL_27;
  v26 = v21 + 64;
  CurrentProcess = IoGetCurrentProcess();
  v29 = *(_QWORD *)(v21 + 1088);
  v30 = *(_QWORD *)(v21 + 64);
  if ( UxSystemProcess != CurrentProcess )
  {
    if ( v30 || *(_QWORD *)(v21 + 80) || *(_QWORD *)(v21 + 96) )
      UlBugCheckEx(1u, v21 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    goto LABEL_66;
  }
  if ( v30 || *(_QWORD *)(v21 + 80) || *(_QWORD *)(v21 + 96) )
    UlBugCheckEx(1u, v21 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
  if ( KeGetCurrentIrql() )
  {
LABEL_66:
    LODWORD(v36) = -1;
    LOBYTE(v28) = 1;
    UlThreadPoolEnqueueWorkItem(0, v21 + 64, UlFreeHttpConnection, v28, v29, v36);
    goto LABEL_27;
  }
  v31 = 0;
  v38 = 0;
  if ( v29 == -1 )
  {
    v33 = *((_QWORD *)&v38 + 1);
LABEL_62:
    UlFreeHttpConnection(v26);
    if ( !v31 )
      goto LABEL_27;
    goto LABEL_63;
  }
  v32 = PsAttachSiloToCurrentThread(v29);
  v33 = v32;
  v31 = 1;
  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) == 0 )
    goto LABEL_62;
  WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v32, v29);
  UlFreeHttpConnection(v26);
LABEL_63:
  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v33);
  PsDetachSiloFromCurrentThread(v33);
LABEL_27:
  v23 = UxDebugDisableLookaside == 0;
  *((_QWORD *)v5 + 7) = 0;
  v5[4] = 1969441909;
  if ( v23 )
  {
    if ( UxCompactMode )
    {
      PnlFreeToLookasideList(qword_1401A0910, v5);
    }
    else
    {
      v24 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*v5 + 1) << 7);
      if ( !*(_BYTE *)(v24 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v24 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v24 + 64), v5);
    }
  }
  else
  {
    memset(v39, 0, sizeof(v39));
    v39[10] = dword_1401A0928;
    ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v5, v39);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_35:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    {
      WPP_SF_(1032, 33, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 216, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14006eaf0  mov     [rsp+arg_18], rbx
0x14006eaf5  push    rbp
0x14006eaf6  push    rsi
0x14006eaf7  push    rdi
0x14006eaf8  push    r12
0x14006eafa  push    r14
0x14006eafc  sub     rsp, 0D0h
0x14006eb03  mov     rax, cs:__security_cookie
0x14006eb0a  xor     rax, rsp
0x14006eb0d  mov     [rsp+0F8h+var_38], rax
0x14006eb15  mov     rbp, rcx
0x14006eb18  mov     [rsp+0F8h+var_B8], dl
0x14006eb1c  xor     r12d, r12d
0x14006eb1f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006eb26  jnz     loc_14006F0FF
0x14006eb2c  add     rbp, 3B0h
0x14006eb33  mov     rbx, r12
0x14006eb36  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006eb3d  jnz     loc_14006F095
0x14006eb43  mov     [rsp+0F8h+arg_10], r15
0x14006eb4b  call    cs:__imp_KeEnterCriticalRegion
0x14006eb52  nop     dword ptr [rax+rax+00h]
0x14006eb57  xor     edx, edx
0x14006eb59  mov     rcx, rbp
0x14006eb5c  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006eb63  nop     dword ptr [rax+rax+00h]
0x14006eb68  mov     rsi, [rbp+8]
0x14006eb6c  lea     r14, [rbp+8]
0x14006eb70  mov     edi, 0FFFFFFFFh
0x14006eb75  cmp     rsi, r14
0x14006eb78  jz      loc_14006EBFE
0x14006eb7e  lea     rdx, [rsi-4]; BugCheckParameter2
0x14006eb82  mov     eax, [rdx]
0x14006eb84  test    eax, eax
0x14006eb86  jz      short loc_14006EBF6
0x14006eb88  cmp     cs:UxDebugCheckRefcount, r12b
0x14006eb8f  lea     ecx, [rax+1]
0x14006eb92  jnz     loc_14006EF88
0x14006eb98  lock cmpxchg [rdx], ecx
0x14006eb9c  jnz     short loc_14006EB82
0x14006eb9e  xor     edx, edx
0x14006eba0  mov     rcx, rbp
0x14006eba3  call    cs:__imp_ExReleasePushLockSharedEx
0x14006ebaa  nop     dword ptr [rax+rax+00h]
0x14006ebaf  call    cs:__imp_KeLeaveCriticalRegion
0x14006ebb6  nop     dword ptr [rax+rax+00h]
0x14006ebbb  test    rbx, rbx
0x14006ebbe  jnz     loc_14006F137
0x14006ebc4  xor     r8d, r8d
0x14006ebc7  lea     rdx, [rsp+0F8h+var_B8]
0x14006ebcc  lea     rcx, [rsi-18h]
0x14006ebd0  call    UlpCompleteWaitForDisconnects
0x14006ebd5  call    cs:__imp_KeEnterCriticalRegion
0x14006ebdc  nop     dword ptr [rax+rax+00h]
0x14006ebe1  xor     edx, edx
0x14006ebe3  mov     rcx, rbp
0x14006ebe6  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006ebed  nop     dword ptr [rax+rax+00h]
0x14006ebf2  lea     rbx, [rsi-18h]
0x14006ebf6  mov     rsi, [rsi]
0x14006ebf9  cmp     rsi, r14
0x14006ebfc  jnz     short loc_14006EB7E
0x14006ebfe  xor     edx, edx
0x14006ec00  mov     rcx, rbp
0x14006ec03  call    cs:__imp_ExReleasePushLockSharedEx
0x14006ec0a  nop     dword ptr [rax+rax+00h]
0x14006ec0f  call    cs:__imp_KeLeaveCriticalRegion
0x14006ec16  nop     dword ptr [rax+rax+00h]
0x14006ec1b  test    rbx, rbx
0x14006ec1e  jz      loc_14006EE43
0x14006ec24  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006ec28  mov     eax, edi
0x14006ec2a  lock xadd [rdx], eax
0x14006ec2e  dec     eax
0x14006ec30  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ec37  jnz     loc_14006EF03
0x14006ec3d  test    eax, eax
0x14006ec3f  jnz     loc_14006EE43
0x14006ec45  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ec4c  jnz     loc_14006F072
0x14006ec52  mov     rax, [rbx+38h]
0x14006ec56  movzx   edx, word ptr [rax+38h]
0x14006ec5a  mov     rax, [rbx+40h]
0x14006ec5e  mov     rcx, [rax+108h]
0x14006ec65  mov     rsi, [rcx+rdx*8]
0x14006ec69  call    cs:__imp_KeEnterCriticalRegion
0x14006ec70  nop     dword ptr [rax+rax+00h]
0x14006ec75  mov     rcx, [rbx+38h]
0x14006ec79  xor     edx, edx
0x14006ec7b  add     rcx, 3B0h
0x14006ec82  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006ec89  nop     dword ptr [rax+rax+00h]
0x14006ec8e  call    cs:__imp_KeEnterCriticalRegion
0x14006ec95  nop     dword ptr [rax+rax+00h]
0x14006ec9a  xor     edx, edx
0x14006ec9c  mov     rcx, rsi
0x14006ec9f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006eca6  nop     dword ptr [rax+rax+00h]
0x14006ecab  mov     rdx, [rbx+18h]
0x14006ecaf  lea     rax, [rbx+18h]
0x14006ecb3  cmp     [rdx+8], rax
0x14006ecb7  jnz     loc_14006EF58
0x14006ecbd  mov     rcx, [rax+8]
0x14006ecc1  cmp     [rcx], rax
0x14006ecc4  jnz     loc_14006EF58
0x14006ecca  mov     [rcx], rdx
0x14006eccd  mov     [rdx+8], rcx
0x14006ecd1  mov     [rax], r12
0x14006ecd4  mov     [rax+8], r12
0x14006ecd8  lea     rax, [rbx+28h]
0x14006ecdc  mov     r8, [rax]
0x14006ecdf  cmp     [r8+8], rax
0x14006ece3  jnz     loc_14006EF58
0x14006ece9  mov     rdx, [rax+8]
0x14006eced  cmp     [rdx], rax
0x14006ecf0  jnz     loc_14006EF58
0x14006ecf6  mov     [rdx], r8
0x14006ecf9  mov     rcx, rsi
0x14006ecfc  mov     [r8+8], rdx
0x14006ed00  xor     edx, edx
0x14006ed02  mov     [rax], r12
0x14006ed05  mov     [rax+8], r12
0x14006ed09  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006ed10  nop     dword ptr [rax+rax+00h]
0x14006ed15  call    cs:__imp_KeLeaveCriticalRegion
0x14006ed1c  nop     dword ptr [rax+rax+00h]
0x14006ed21  mov     rcx, [rbx+38h]
0x14006ed25  xor     edx, edx
0x14006ed27  add     rcx, 3B0h
0x14006ed2e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006ed35  nop     dword ptr [rax+rax+00h]
0x14006ed3a  call    cs:__imp_KeLeaveCriticalRegion
0x14006ed41  nop     dword ptr [rax+rax+00h]
0x14006ed46  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14006ed4a  test    rdx, rdx
0x14006ed4d  jnz     loc_14006EE86
0x14006ed53  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14006ed57  mov     eax, edi
0x14006ed59  lock xadd [rdx], eax
0x14006ed5d  dec     eax
0x14006ed5f  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ed66  jnz     loc_14006EF1F
0x14006ed6c  test    eax, eax
0x14006ed6e  jz      loc_14006F189
0x14006ed74  mov     rsi, [rbx+38h]
0x14006ed78  mov     [rbx+40h], r12
0x14006ed7c  lea     rdx, [rsi+28h]; BugCheckParameter2
0x14006ed80  lock xadd [rdx], edi
0x14006ed84  dec     edi
0x14006ed86  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ed8d  jnz     loc_14006EF3B
0x14006ed93  test    edi, edi
0x14006ed95  jz      loc_14006EEAC
0x14006ed9b  cmp     cs:UxDebugDisableLookaside, r12b
0x14006eda2  mov     [rbx+38h], r12
0x14006eda6  mov     dword ptr [rbx+10h], 75634C75h
0x14006edad  jnz     loc_14006F1B5
0x14006edb3  cmp     cs:UxCompactMode, r12b
0x14006edba  mov     rcx, cs:qword_1401A0910
0x14006edc1  jnz     loc_14006EF7B
0x14006edc7  mov     edi, [rbx]
0x14006edc9  inc     edi
0x14006edcb  shl     rdi, 7
0x14006edcf  add     rdi, rcx
0x14006edd2  movzx   eax, byte ptr [rdi+0B0h]
0x14006edd9  test    al, al
0x14006eddb  jz      loc_14006F0F1
0x14006ede1  mov     rdx, rbx; Entry
0x14006ede4  lea     rcx, [rdi+40h]; Lookaside
0x14006ede8  call    cs:__imp_ExFreeToLookasideListEx
0x14006edef  nop     dword ptr [rax+rax+00h]
0x14006edf4  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006edfb  jnz     short loc_14006EE2D
0x14006edfd  mov     r15, [rsp+0F8h+arg_10]
0x14006ee05  mov     rcx, [rsp+0F8h+var_38]
0x14006ee0d  xor     rcx, rsp; StackCookie
0x14006ee10  call    __security_check_cookie
0x14006ee15  mov     rbx, [rsp+0F8h+arg_18]
0x14006ee1d  add     rsp, 0D0h
0x14006ee24  pop     r14
0x14006ee26  pop     r12
0x14006ee28  pop     rdi
0x14006ee29  pop     rsi
0x14006ee2a  pop     rbp
0x14006ee2b  retn
0x14006ee2d  mov     edx, 18h
0x14006ee32  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee39  mov     ecx, 408h
0x14006ee3e  call    WPP_SF_
0x14006ee43  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ee4a  jz      short loc_14006EDFD
0x14006ee4c  mov     edx, 21h ; '!'
0x14006ee51  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee58  mov     ecx, 408h
0x14006ee5d  call    WPP_SF_
0x14006ee62  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ee69  jz      short loc_14006EDFD
0x14006ee6b  mov     edx, 0D8h
0x14006ee70  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee77  mov     ecx, 408h
0x14006ee7c  call    WPP_SF_
0x14006ee81  jmp     loc_14006EDFD
0x14006ee86  mov     eax, edi
0x14006ee88  lock xadd [rdx], eax
0x14006ee8c  dec     eax
0x14006ee8e  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ee95  jnz     loc_14006EF5F
0x14006ee9b  test    eax, eax
0x14006ee9d  jz      loc_14006F17B
0x14006eea3  mov     [rbx+58h], r12
0x14006eea7  jmp     loc_14006ED53
0x14006eeac  lea     rdi, [rsi+40h]
0x14006eeb0  call    cs:__imp_IoGetCurrentProcess
0x14006eeb7  nop     dword ptr [rax+rax+00h]
0x14006eebc  cmp     cs:UxSystemProcess, rax
0x14006eec3  mov     rbp, [rsi+440h]
0x14006eeca  mov     rcx, [rdi]
0x14006eecd  jnz     loc_14006F046
0x14006eed3  test    rcx, rcx
0x14006eed6  jnz     short loc_14006EEE8
0x14006eed8  cmp     [rdi+10h], r12
0x14006eedc  jnz     short loc_14006EEE8
0x14006eede  cmp     [rdi+20h], r12
0x14006eee2  jz      loc_14006EFA4
0x14006eee8  mov     r9d, 0E1h; BugCheckParameter4
0x14006eeee  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14006eef5  mov     rdx, rdi; BugCheckParameter2
0x14006eef8  mov     ecx, 1; BugCheckParameter1
0x14006eefd  call    UlBugCheckEx
0x14006ef03  cmp     eax, edi
0x14006ef05  jg      loc_14006EC3D
0x14006ef0b  movsxd  r9, eax; BugCheckParameter4
0x14006ef0e  mov     ecx, 3; BugCheckParameter1
0x14006ef13  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14006ef19  call    UlBugCheckEx
0x14006ef1f  cmp     eax, edi
0x14006ef21  jg      loc_14006ED6C
0x14006ef27  movsxd  r9, eax; BugCheckParameter4
0x14006ef2a  mov     ecx, 3; BugCheckParameter1
0x14006ef2f  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef35  call    UlBugCheckEx
0x14006ef3b  cmp     edi, 0FFFFFFFFh
0x14006ef3e  jg      loc_14006ED93
0x14006ef44  movsxd  r9, edi; BugCheckParameter4
0x14006ef47  mov     ecx, 3; BugCheckParameter1
0x14006ef4c  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef52  call    UlBugCheckEx
0x14006ef58  mov     ecx, 3
0x14006ef5d  int     29h; Win8: RtlFailFast(ecx)
0x14006ef5f  cmp     eax, edi
0x14006ef61  jg      loc_14006EE9B
0x14006ef67  movsxd  r9, eax; BugCheckParameter4
0x14006ef6a  mov     ecx, 3; BugCheckParameter1
0x14006ef6f  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef75  call    UlBugCheckEx
0x14006ef7b  mov     rdx, rbx
0x14006ef7e  call    PnlFreeToLookasideList
0x14006ef83  jmp     loc_14006EDF4
0x14006ef88  cmp     ecx, edi
0x14006ef8a  jg      loc_14006EB98
0x14006ef90  movsxd  r9, ecx; BugCheckParameter4
0x14006ef93  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14006ef99  mov     ecx, 3; BugCheckParameter1
0x14006ef9e  call    UlBugCheckEx
0x14006efa4  call    cs:__imp_KeGetCurrentIrql
0x14006efab  nop     dword ptr [rax+rax+00h]
0x14006efb0  test    al, al
0x14006efb2  jnz     short loc_14006F019
0x14006efb4  xor     sil, sil
0x14006efb7  xorps   xmm0, xmm0
0x14006efba  movups  [rsp+0F8h+var_B0], xmm0
0x14006efbf  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14006efc3  jz      short loc_14006F03F
0x14006efc5  mov     rcx, rbp
0x14006efc8  call    cs:__imp_PsAttachSiloToCurrentThread
0x14006efcf  nop     dword ptr [rax+rax+00h]
0x14006efd4  mov     r14, rax
0x14006efd7  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14006efde  mov     sil, 1
0x14006efe1  jnz     loc_14006F0C6
0x14006efe7  mov     rcx, rdi
0x14006efea  call    UlFreeHttpConnection
0x14006efef  test    sil, sil
0x14006eff2  jz      loc_14006ED9B
0x14006eff8  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14006efff  jnz     loc_14006F197
0x14006f005  mov     rcx, r14
0x14006f008  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14006f00f  nop     dword ptr [rax+rax+00h]
0x14006f014  jmp     loc_14006ED9B
0x14006f019  mov     dword ptr [rsp+0F8h+var_D0], 0FFFFFFFFh
0x14006f021  lea     r8, UlFreeHttpConnection
0x14006f028  mov     r9b, 1
0x14006f02b  mov     [rsp+0F8h+var_D8], rbp
0x14006f030  mov     rdx, rdi
0x14006f033  xor     ecx, ecx
0x14006f035  call    UlThreadPoolEnqueueWorkItem
0x14006f03a  jmp     loc_14006ED9B
0x14006f03f  mov     r14, qword ptr [rsp+0F8h+var_B0+8]
0x14006f044  jmp     short loc_14006EFE7
  ... truncated ...
```

# UlCompleteWaitForDisconnects

- ea: `0x14006eb10`
- end: `0x14006f20d`
- name: `UlCompleteWaitForDisconnects`
- size: `1789`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037b00`
- `0x1400568e0`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14006e50c`
- `0x14006eb10`
- `0x14006f220`
- `0x1400705f0`
- `0x14009622c`
- `0x1400a033c`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3974`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da550`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14006efc4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006efc4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006ee08`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006ee08`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006efe8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006efe8`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006f028`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006f028`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ebcf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ec2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed5a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ebcf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ec2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ed5a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006eb7c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006ec06`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006eb7c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006ec06`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ebc3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ec23`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ebc3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006ec23`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed4e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ed4e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006eed0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006eed0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006eca2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ecbf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006eca2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ecbf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006eb6b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ebf5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ecae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006eb6b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ebf5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ec89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006ecae`

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
  _BYTE v36[8]; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+48h] [rbp-B0h]
  _DWORD v38[24]; // [rsp+60h] [rbp-98h] BYREF

  v36[0] = a2;
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
      v36,
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
        UlpCompleteWaitForDisconnects(i - 3, v36, 0);
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
    LOBYTE(v28) = 1;
    UlThreadPoolEnqueueWorkItem(0, v21 + 64, UlFreeHttpConnection, v28, v29, -1);
    goto LABEL_27;
  }
  v31 = 0;
  v37 = 0;
  if ( v29 == -1 )
  {
    v33 = *((_QWORD *)&v37 + 1);
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
    memset(v38, 0, sizeof(v38));
    v38[10] = dword_1401A0928;
    ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v5, v38);
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
0x14006eb10  mov     [rsp+arg_18], rbx
0x14006eb15  push    rbp
0x14006eb16  push    rsi
0x14006eb17  push    rdi
0x14006eb18  push    r12
0x14006eb1a  push    r14
0x14006eb1c  sub     rsp, 0D0h
0x14006eb23  mov     rax, cs:__security_cookie
0x14006eb2a  xor     rax, rsp
0x14006eb2d  mov     [rsp+0F8h+var_38], rax
0x14006eb35  mov     rbp, rcx
0x14006eb38  mov     [rsp+0F8h+var_B8], dl
0x14006eb3c  xor     r12d, r12d
0x14006eb3f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006eb46  jnz     loc_14006F11F
0x14006eb4c  add     rbp, 3B0h
0x14006eb53  mov     rbx, r12
0x14006eb56  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006eb5d  jnz     loc_14006F0B5
0x14006eb63  mov     [rsp+0F8h+arg_10], r15
0x14006eb6b  call    cs:__imp_KeEnterCriticalRegion
0x14006eb72  nop     dword ptr [rax+rax+00h]
0x14006eb77  xor     edx, edx
0x14006eb79  mov     rcx, rbp
0x14006eb7c  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006eb83  nop     dword ptr [rax+rax+00h]
0x14006eb88  mov     rsi, [rbp+8]
0x14006eb8c  lea     r14, [rbp+8]
0x14006eb90  mov     edi, 0FFFFFFFFh
0x14006eb95  cmp     rsi, r14
0x14006eb98  jz      loc_14006EC1E
0x14006eb9e  lea     rdx, [rsi-4]; BugCheckParameter2
0x14006eba2  mov     eax, [rdx]
0x14006eba4  test    eax, eax
0x14006eba6  jz      short loc_14006EC16
0x14006eba8  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ebaf  lea     ecx, [rax+1]
0x14006ebb2  jnz     loc_14006EFA8
0x14006ebb8  lock cmpxchg [rdx], ecx
0x14006ebbc  jnz     short loc_14006EBA2
0x14006ebbe  xor     edx, edx
0x14006ebc0  mov     rcx, rbp
0x14006ebc3  call    cs:__imp_ExReleasePushLockSharedEx
0x14006ebca  nop     dword ptr [rax+rax+00h]
0x14006ebcf  call    cs:__imp_KeLeaveCriticalRegion
0x14006ebd6  nop     dword ptr [rax+rax+00h]
0x14006ebdb  test    rbx, rbx
0x14006ebde  jnz     loc_14006F157
0x14006ebe4  xor     r8d, r8d
0x14006ebe7  lea     rdx, [rsp+0F8h+var_B8]
0x14006ebec  lea     rcx, [rsi-18h]
0x14006ebf0  call    UlpCompleteWaitForDisconnects
0x14006ebf5  call    cs:__imp_KeEnterCriticalRegion
0x14006ebfc  nop     dword ptr [rax+rax+00h]
0x14006ec01  xor     edx, edx
0x14006ec03  mov     rcx, rbp
0x14006ec06  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006ec0d  nop     dword ptr [rax+rax+00h]
0x14006ec12  lea     rbx, [rsi-18h]
0x14006ec16  mov     rsi, [rsi]
0x14006ec19  cmp     rsi, r14
0x14006ec1c  jnz     short loc_14006EB9E
0x14006ec1e  xor     edx, edx
0x14006ec20  mov     rcx, rbp
0x14006ec23  call    cs:__imp_ExReleasePushLockSharedEx
0x14006ec2a  nop     dword ptr [rax+rax+00h]
0x14006ec2f  call    cs:__imp_KeLeaveCriticalRegion
0x14006ec36  nop     dword ptr [rax+rax+00h]
0x14006ec3b  test    rbx, rbx
0x14006ec3e  jz      loc_14006EE63
0x14006ec44  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006ec48  mov     eax, edi
0x14006ec4a  lock xadd [rdx], eax
0x14006ec4e  dec     eax
0x14006ec50  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ec57  jnz     loc_14006EF23
0x14006ec5d  test    eax, eax
0x14006ec5f  jnz     loc_14006EE63
0x14006ec65  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ec6c  jnz     loc_14006F092
0x14006ec72  mov     rax, [rbx+38h]
0x14006ec76  movzx   edx, word ptr [rax+38h]
0x14006ec7a  mov     rax, [rbx+40h]
0x14006ec7e  mov     rcx, [rax+108h]
0x14006ec85  mov     rsi, [rcx+rdx*8]
0x14006ec89  call    cs:__imp_KeEnterCriticalRegion
0x14006ec90  nop     dword ptr [rax+rax+00h]
0x14006ec95  mov     rcx, [rbx+38h]
0x14006ec99  xor     edx, edx
0x14006ec9b  add     rcx, 3B0h
0x14006eca2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006eca9  nop     dword ptr [rax+rax+00h]
0x14006ecae  call    cs:__imp_KeEnterCriticalRegion
0x14006ecb5  nop     dword ptr [rax+rax+00h]
0x14006ecba  xor     edx, edx
0x14006ecbc  mov     rcx, rsi
0x14006ecbf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006ecc6  nop     dword ptr [rax+rax+00h]
0x14006eccb  mov     rdx, [rbx+18h]
0x14006eccf  lea     rax, [rbx+18h]
0x14006ecd3  cmp     [rdx+8], rax
0x14006ecd7  jnz     loc_14006EF78
0x14006ecdd  mov     rcx, [rax+8]
0x14006ece1  cmp     [rcx], rax
0x14006ece4  jnz     loc_14006EF78
0x14006ecea  mov     [rcx], rdx
0x14006eced  mov     [rdx+8], rcx
0x14006ecf1  mov     [rax], r12
0x14006ecf4  mov     [rax+8], r12
0x14006ecf8  lea     rax, [rbx+28h]
0x14006ecfc  mov     r8, [rax]
0x14006ecff  cmp     [r8+8], rax
0x14006ed03  jnz     loc_14006EF78
0x14006ed09  mov     rdx, [rax+8]
0x14006ed0d  cmp     [rdx], rax
0x14006ed10  jnz     loc_14006EF78
0x14006ed16  mov     [rdx], r8
0x14006ed19  mov     rcx, rsi
0x14006ed1c  mov     [r8+8], rdx
0x14006ed20  xor     edx, edx
0x14006ed22  mov     [rax], r12
0x14006ed25  mov     [rax+8], r12
0x14006ed29  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006ed30  nop     dword ptr [rax+rax+00h]
0x14006ed35  call    cs:__imp_KeLeaveCriticalRegion
0x14006ed3c  nop     dword ptr [rax+rax+00h]
0x14006ed41  mov     rcx, [rbx+38h]
0x14006ed45  xor     edx, edx
0x14006ed47  add     rcx, 3B0h
0x14006ed4e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006ed55  nop     dword ptr [rax+rax+00h]
0x14006ed5a  call    cs:__imp_KeLeaveCriticalRegion
0x14006ed61  nop     dword ptr [rax+rax+00h]
0x14006ed66  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14006ed6a  test    rdx, rdx
0x14006ed6d  jnz     loc_14006EEA6
0x14006ed73  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14006ed77  mov     eax, edi
0x14006ed79  lock xadd [rdx], eax
0x14006ed7d  dec     eax
0x14006ed7f  cmp     cs:UxDebugCheckRefcount, r12b
0x14006ed86  jnz     loc_14006EF3F
0x14006ed8c  test    eax, eax
0x14006ed8e  jz      loc_14006F1A9
0x14006ed94  mov     rsi, [rbx+38h]
0x14006ed98  mov     [rbx+40h], r12
0x14006ed9c  lea     rdx, [rsi+28h]; BugCheckParameter2
0x14006eda0  lock xadd [rdx], edi
0x14006eda4  dec     edi
0x14006eda6  cmp     cs:UxDebugCheckRefcount, r12b
0x14006edad  jnz     loc_14006EF5B
0x14006edb3  test    edi, edi
0x14006edb5  jz      loc_14006EECC
0x14006edbb  cmp     cs:UxDebugDisableLookaside, r12b
0x14006edc2  mov     [rbx+38h], r12
0x14006edc6  mov     dword ptr [rbx+10h], 75634C75h
0x14006edcd  jnz     loc_14006F1D5
0x14006edd3  cmp     cs:UxCompactMode, r12b
0x14006edda  mov     rcx, cs:qword_1401A0910
0x14006ede1  jnz     loc_14006EF9B
0x14006ede7  mov     edi, [rbx]
0x14006ede9  inc     edi
0x14006edeb  shl     rdi, 7
0x14006edef  add     rdi, rcx
0x14006edf2  movzx   eax, byte ptr [rdi+0B0h]
0x14006edf9  test    al, al
0x14006edfb  jz      loc_14006F111
0x14006ee01  mov     rdx, rbx; Entry
0x14006ee04  lea     rcx, [rdi+40h]; Lookaside
0x14006ee08  call    cs:__imp_ExFreeToLookasideListEx
0x14006ee0f  nop     dword ptr [rax+rax+00h]
0x14006ee14  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ee1b  jnz     short loc_14006EE4D
0x14006ee1d  mov     r15, [rsp+0F8h+arg_10]
0x14006ee25  mov     rcx, [rsp+0F8h+var_38]
0x14006ee2d  xor     rcx, rsp; StackCookie
0x14006ee30  call    __security_check_cookie
0x14006ee35  mov     rbx, [rsp+0F8h+arg_18]
0x14006ee3d  add     rsp, 0D0h
0x14006ee44  pop     r14
0x14006ee46  pop     r12
0x14006ee48  pop     rdi
0x14006ee49  pop     rsi
0x14006ee4a  pop     rbp
0x14006ee4b  retn
0x14006ee4d  mov     edx, 18h
0x14006ee52  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee59  mov     ecx, 408h
0x14006ee5e  call    WPP_SF_
0x14006ee63  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ee6a  jz      short loc_14006EE1D
0x14006ee6c  mov     edx, 21h ; '!'
0x14006ee71  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee78  mov     ecx, 408h
0x14006ee7d  call    WPP_SF_
0x14006ee82  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ee89  jz      short loc_14006EE1D
0x14006ee8b  mov     edx, 0D8h
0x14006ee90  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14006ee97  mov     ecx, 408h
0x14006ee9c  call    WPP_SF_
0x14006eea1  jmp     loc_14006EE1D
0x14006eea6  mov     eax, edi
0x14006eea8  lock xadd [rdx], eax
0x14006eeac  dec     eax
0x14006eeae  cmp     cs:UxDebugCheckRefcount, r12b
0x14006eeb5  jnz     loc_14006EF7F
0x14006eebb  test    eax, eax
0x14006eebd  jz      loc_14006F19B
0x14006eec3  mov     [rbx+58h], r12
0x14006eec7  jmp     loc_14006ED73
0x14006eecc  lea     rdi, [rsi+40h]
0x14006eed0  call    cs:__imp_IoGetCurrentProcess
0x14006eed7  nop     dword ptr [rax+rax+00h]
0x14006eedc  cmp     cs:UxSystemProcess, rax
0x14006eee3  mov     rbp, [rsi+440h]
0x14006eeea  mov     rcx, [rdi]
0x14006eeed  jnz     loc_14006F066
0x14006eef3  test    rcx, rcx
0x14006eef6  jnz     short loc_14006EF08
0x14006eef8  cmp     [rdi+10h], r12
0x14006eefc  jnz     short loc_14006EF08
0x14006eefe  cmp     [rdi+20h], r12
0x14006ef02  jz      loc_14006EFC4
0x14006ef08  mov     r9d, 0E1h; BugCheckParameter4
0x14006ef0e  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14006ef15  mov     rdx, rdi; BugCheckParameter2
0x14006ef18  mov     ecx, 1; BugCheckParameter1
0x14006ef1d  call    UlBugCheckEx
0x14006ef23  cmp     eax, edi
0x14006ef25  jg      loc_14006EC5D
0x14006ef2b  movsxd  r9, eax; BugCheckParameter4
0x14006ef2e  mov     ecx, 3; BugCheckParameter1
0x14006ef33  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14006ef39  call    UlBugCheckEx
0x14006ef3f  cmp     eax, edi
0x14006ef41  jg      loc_14006ED8C
0x14006ef47  movsxd  r9, eax; BugCheckParameter4
0x14006ef4a  mov     ecx, 3; BugCheckParameter1
0x14006ef4f  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef55  call    UlBugCheckEx
0x14006ef5b  cmp     edi, 0FFFFFFFFh
0x14006ef5e  jg      loc_14006EDB3
0x14006ef64  movsxd  r9, edi; BugCheckParameter4
0x14006ef67  mov     ecx, 3; BugCheckParameter1
0x14006ef6c  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef72  call    UlBugCheckEx
0x14006ef78  mov     ecx, 3
0x14006ef7d  int     29h; Win8: RtlFailFast(ecx)
0x14006ef7f  cmp     eax, edi
0x14006ef81  jg      loc_14006EEBB
0x14006ef87  movsxd  r9, eax; BugCheckParameter4
0x14006ef8a  mov     ecx, 3; BugCheckParameter1
0x14006ef8f  mov     r8d, 0Eh; BugCheckParameter3
0x14006ef95  call    UlBugCheckEx
0x14006ef9b  mov     rdx, rbx
0x14006ef9e  call    PnlFreeToLookasideList
0x14006efa3  jmp     loc_14006EE14
0x14006efa8  cmp     ecx, edi
0x14006efaa  jg      loc_14006EBB8
0x14006efb0  movsxd  r9, ecx; BugCheckParameter4
0x14006efb3  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14006efb9  mov     ecx, 3; BugCheckParameter1
0x14006efbe  call    UlBugCheckEx
0x14006efc4  call    cs:__imp_KeGetCurrentIrql
0x14006efcb  nop     dword ptr [rax+rax+00h]
0x14006efd0  test    al, al
0x14006efd2  jnz     short loc_14006F039
0x14006efd4  xor     sil, sil
0x14006efd7  xorps   xmm0, xmm0
0x14006efda  movups  [rsp+0F8h+var_B0], xmm0
0x14006efdf  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14006efe3  jz      short loc_14006F05F
0x14006efe5  mov     rcx, rbp
0x14006efe8  call    cs:__imp_PsAttachSiloToCurrentThread
0x14006efef  nop     dword ptr [rax+rax+00h]
0x14006eff4  mov     r14, rax
0x14006eff7  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14006effe  mov     sil, 1
0x14006f001  jnz     loc_14006F0E6
0x14006f007  mov     rcx, rdi
0x14006f00a  call    UlFreeHttpConnection
0x14006f00f  test    sil, sil
0x14006f012  jz      loc_14006EDBB
0x14006f018  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14006f01f  jnz     loc_14006F1B7
0x14006f025  mov     rcx, r14
0x14006f028  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14006f02f  nop     dword ptr [rax+rax+00h]
0x14006f034  jmp     loc_14006EDBB
0x14006f039  mov     dword ptr [rsp+0F8h+var_D0], 0FFFFFFFFh
0x14006f041  lea     r8, UlFreeHttpConnection
0x14006f048  mov     r9b, 1
0x14006f04b  mov     [rsp+0F8h+var_D8], rbp
0x14006f050  mov     rdx, rdi
0x14006f053  xor     ecx, ecx
0x14006f055  call    UlThreadPoolEnqueueWorkItem
0x14006f05a  jmp     loc_14006EDBB
0x14006f05f  mov     r14, qword ptr [rsp+0F8h+var_B0+8]
0x14006f064  jmp     short loc_14006F007
  ... truncated ...
```

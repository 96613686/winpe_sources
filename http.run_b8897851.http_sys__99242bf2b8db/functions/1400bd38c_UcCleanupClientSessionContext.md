# UcCleanupClientSessionContext

- ea: `0x1400bd38c`
- end: `0x1400bd6ab`
- name: `UcCleanupClientSessionContext`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400629a0`

## callees

- `0x14000a350`
- `0x140035a70`
- `0x140062bf0`
- `0x1400bd38c`
- `0x1400bd6b4`
- `0x1400bd7b8`
- `0x1400bd9e4`
- `0x1400bdbe4`
- `0x1400bde14`
- `0x14015c698`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400bd647`
- `ntoskrnl!IofCompleteRequest` at `0x1400bd647`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd4cc`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd4cc`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd455`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd455`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd4d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd4f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd4d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd4f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd4ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd4ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bd439`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bd439`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd41e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd445`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd41e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd445`

## pseudocode

```c
__int64 __fastcall UcCleanupClientSessionContext(__int64 a1, __int64 a2)
{
  char v4; // r15
  ULONG_PTR v5; // rbx
  _QWORD *v6; // rdi
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  IRP *v15; // rcx
  _QWORD v17[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF

  v17[0] = v17;
  v17[1] = v17;
  v4 = 0;
  v18[0] = v18;
  v18[1] = v18;
  v19 = 0;
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_qq(1053, 34, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, a1, a2);
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v6 = *(_QWORD **)(v5 + 8);
  UxPodAttachThread(v6[9], &v19);
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 32LL) = 1699955544;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6[10] + 8712LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(v6[8]);
  *(_BYTE *)(v5 + 4) = 1;
  UcpFlushConnectionsFromSessionContext(v5, v17);
  UcpFlushCredentialsFromSessionContext(v5, v18);
  UcpRemoveSessionContextFromSessionList(v5, v6);
  if ( (_QWORD *)v6[3] == v6 + 3 )
  {
    v7 = v6 + 1;
    v8 = v6[1];
    if ( *(_QWORD **)(v8 + 8) != v6 + 1 || (v9 = (_QWORD *)v6[2], (_QWORD *)*v9 != v7) )
LABEL_17:
      __fastfail(3u);
    *v9 = v8;
    v4 = 1;
    *(_QWORD *)(v8 + 8) = v9;
    *v7 = 0;
    v6[2] = 0;
  }
  ExReleaseCacheAwarePushLockExclusive(v6[8]);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(v6[10] + 8712LL, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_q(1053, 44, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, v17);
  while ( 1 )
  {
    v10 = (_QWORD *)v17[0];
    if ( (_QWORD *)v17[0] == v17 )
      break;
    if ( *(_QWORD **)(v17[0] + 8LL) != v17 )
      goto LABEL_17;
    v11 = *(_QWORD *)v17[0];
    if ( *(_QWORD *)(*(_QWORD *)v17[0] + 8LL) != v17[0] )
      goto LABEL_17;
    v17[0] = *(_QWORD *)v17[0];
    *(_QWORD *)(v11 + 8) = v17;
    *v10 = 0;
    v10[1] = 0;
    UcCloseConnection(v10 - 12);
  }
  while ( 1 )
  {
    v12 = (_QWORD *)v18[0];
    if ( (_QWORD *)v18[0] == v18 )
      break;
    if ( *(_QWORD **)(v18[0] + 8LL) != v18 )
      goto LABEL_17;
    v13 = *(_QWORD *)v18[0];
    if ( *(_QWORD *)(*(_QWORD *)v18[0] + 8LL) != v18[0] )
      goto LABEL_17;
    v18[0] = *(_QWORD *)v18[0];
    *(_QWORD *)(v13 + 8) = v18;
    *v12 = 0;
    v12[1] = 0;
    UcCloseCredential(v12 - 9);
  }
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(v5 + 24) = a1;
  if ( v4 )
    UcpCleanupClientSession(v6);
  v14 = _InterlockedDecrement((volatile signed __int32 *)v5);
  if ( UxDebugCheckRefcount && v14 <= -1 )
    UlBugCheckEx(3u, v5, 1u, v14);
  if ( !v14 )
  {
    if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
      WPP_SF_q(1053, 36, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids, v5);
    v15 = *(IRP **)(v5 + 24);
    *(_QWORD *)(v5 + 24) = 0;
    v15->IoStatus.Status = 0;
    IofCompleteRequest(v15, 2);
    if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
      WPP_SF_(1053, 37, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids);
  }
  UxPodDetachThread(&v19);
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_(1053, 35, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x1400bd38c  push    rbp
0x1400bd38e  push    rbx
0x1400bd38f  push    rsi
0x1400bd390  push    rdi
0x1400bd391  push    r13
0x1400bd393  push    r14
0x1400bd395  push    r15
0x1400bd397  mov     rbp, rsp
0x1400bd39a  sub     rsp, 60h
0x1400bd39e  lea     rax, [rbp+var_30]
0x1400bd3a2  xorps   xmm0, xmm0
0x1400bd3a5  mov     [rbp+var_30], rax
0x1400bd3a9  mov     r14, rdx
0x1400bd3ac  lea     rax, [rbp+var_30]
0x1400bd3b0  mov     rsi, rcx
0x1400bd3b3  mov     [rbp+var_28], rax
0x1400bd3b7  xor     r15b, r15b
0x1400bd3ba  lea     rax, [rbp+var_20]
0x1400bd3be  mov     [rbp+var_20], rax
0x1400bd3c2  lea     rax, [rbp+var_20]
0x1400bd3c6  mov     [rbp+var_18], rax
0x1400bd3ca  movups  [rbp+var_10], xmm0
0x1400bd3ce  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd3d5  mov     r13d, 41Dh
0x1400bd3db  jz      short loc_1400BD3F9
0x1400bd3dd  mov     edx, 22h ; '"'
0x1400bd3e2  mov     [rsp+60h+var_40], r14
0x1400bd3e7  mov     ecx, r13d
0x1400bd3ea  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd3f1  mov     r9, rsi
0x1400bd3f4  call    WPP_SF_qq
0x1400bd3f9  mov     rax, [r14+30h]
0x1400bd3fd  lea     rdx, [rbp+var_10]
0x1400bd401  mov     rbx, [rax+18h]
0x1400bd405  mov     rdi, [rbx+8]
0x1400bd409  mov     rcx, [rdi+48h]
0x1400bd40d  call    UxPodAttachThread
0x1400bd412  mov     rax, [r14+30h]
0x1400bd416  mov     qword ptr [rax+20h], 65534358h
0x1400bd41e  call    cs:__imp_KeEnterCriticalRegion
0x1400bd425  nop     dword ptr [rax+rax+00h]
0x1400bd42a  mov     rcx, [rdi+50h]
0x1400bd42e  mov     r14d, 2208h
0x1400bd434  add     rcx, r14
0x1400bd437  xor     edx, edx
0x1400bd439  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400bd440  nop     dword ptr [rax+rax+00h]
0x1400bd445  call    cs:__imp_KeEnterCriticalRegion
0x1400bd44c  nop     dword ptr [rax+rax+00h]
0x1400bd451  mov     rcx, [rdi+40h]
0x1400bd455  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bd45c  nop     dword ptr [rax+rax+00h]
0x1400bd461  lea     rdx, [rbp+var_30]
0x1400bd465  mov     byte ptr [rbx+4], 1
0x1400bd469  mov     rcx, rbx
0x1400bd46c  call    UcpFlushConnectionsFromSessionContext
0x1400bd471  lea     rdx, [rbp+var_20]
0x1400bd475  mov     rcx, rbx
0x1400bd478  call    UcpFlushCredentialsFromSessionContext
0x1400bd47d  mov     rdx, rdi
0x1400bd480  mov     rcx, rbx
0x1400bd483  call    UcpRemoveSessionContextFromSessionList
0x1400bd488  lea     rax, [rdi+18h]
0x1400bd48c  cmp     [rax], rax
0x1400bd48f  jnz     short loc_1400BD4C8
0x1400bd491  lea     rax, [rdi+8]
0x1400bd495  mov     rcx, [rax]
0x1400bd498  cmp     [rcx+8], rax
0x1400bd49c  jnz     loc_1400BD5B9
0x1400bd4a2  mov     rdx, [rax+8]
0x1400bd4a6  cmp     [rdx], rax
0x1400bd4a9  jnz     loc_1400BD5B9
0x1400bd4af  mov     [rdx], rcx
0x1400bd4b2  mov     r15b, 1
0x1400bd4b5  mov     [rcx+8], rdx
0x1400bd4b9  mov     qword ptr [rax], 0
0x1400bd4c0  mov     qword ptr [rax+8], 0
0x1400bd4c8  mov     rcx, [rdi+40h]
0x1400bd4cc  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bd4d3  nop     dword ptr [rax+rax+00h]
0x1400bd4d8  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd4df  nop     dword ptr [rax+rax+00h]
0x1400bd4e4  mov     rcx, [rdi+50h]
0x1400bd4e8  xor     edx, edx
0x1400bd4ea  add     rcx, r14
0x1400bd4ed  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd4f4  nop     dword ptr [rax+rax+00h]
0x1400bd4f9  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd500  nop     dword ptr [rax+rax+00h]
0x1400bd505  mov     r14b, 20h ; ' '
0x1400bd508  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd50f  jz      short loc_1400BD529
0x1400bd511  mov     edx, 2Ch ; ','
0x1400bd516  lea     r9, [rbp+var_30]
0x1400bd51a  mov     ecx, r13d
0x1400bd51d  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd524  call    WPP_SF_q
0x1400bd529  mov     rcx, [rbp+var_30]
0x1400bd52d  lea     rax, [rbp+var_30]
0x1400bd531  cmp     rcx, rax
0x1400bd534  jz      short loc_1400BD571
0x1400bd536  lea     rax, [rbp+var_30]
0x1400bd53a  cmp     [rcx+8], rax
0x1400bd53e  jnz     short loc_1400BD5B9
0x1400bd540  mov     rax, [rcx]
0x1400bd543  cmp     [rax+8], rcx
0x1400bd547  jnz     short loc_1400BD5B9
0x1400bd549  mov     [rbp+var_30], rax
0x1400bd54d  lea     rdx, [rbp+var_30]
0x1400bd551  mov     [rax+8], rdx
0x1400bd555  xor     edx, edx
0x1400bd557  mov     qword ptr [rcx], 0
0x1400bd55e  mov     qword ptr [rcx+8], 0
0x1400bd566  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x1400bd56a  call    UcCloseConnection
0x1400bd56f  jmp     short loc_1400BD529
0x1400bd571  mov     rcx, [rbp+var_20]
0x1400bd575  lea     rax, [rbp+var_20]
0x1400bd579  cmp     rcx, rax
0x1400bd57c  jz      short loc_1400BD5C0
0x1400bd57e  lea     rax, [rbp+var_20]
0x1400bd582  cmp     [rcx+8], rax
0x1400bd586  jnz     short loc_1400BD5B9
0x1400bd588  mov     rax, [rcx]
0x1400bd58b  cmp     [rax+8], rcx
0x1400bd58f  jnz     short loc_1400BD5B9
0x1400bd591  mov     [rbp+var_20], rax
0x1400bd595  lea     rdx, [rbp+var_20]
0x1400bd599  mov     [rax+8], rdx
0x1400bd59d  xor     edx, edx
0x1400bd59f  mov     qword ptr [rcx], 0
0x1400bd5a6  mov     qword ptr [rcx+8], 0
0x1400bd5ae  add     rcx, 0FFFFFFFFFFFFFFB8h; P
0x1400bd5b2  call    UcCloseCredential
0x1400bd5b7  jmp     short loc_1400BD571
0x1400bd5b9  mov     ecx, 3
0x1400bd5be  int     29h; Win8: RtlFailFast(ecx)
0x1400bd5c0  mov     rax, [rsi+0B8h]
0x1400bd5c7  or      byte ptr [rax+3], 1
0x1400bd5cb  mov     dword ptr [rsi+30h], 103h
0x1400bd5d2  mov     [rbx+18h], rsi
0x1400bd5d6  test    r15b, r15b
0x1400bd5d9  jz      short loc_1400BD5E3
0x1400bd5db  mov     rcx, rdi; P
0x1400bd5de  call    UcpCleanupClientSession
0x1400bd5e3  or      eax, 0FFFFFFFFh
0x1400bd5e6  lock xadd [rbx], eax
0x1400bd5ea  dec     eax
0x1400bd5ec  cmp     cs:UxDebugCheckRefcount, 0
0x1400bd5f3  jz      short loc_1400BD610
0x1400bd5f5  cmp     eax, 0FFFFFFFFh
0x1400bd5f8  jg      short loc_1400BD610
0x1400bd5fa  mov     r8d, 1; BugCheckParameter3
0x1400bd600  movsxd  r9, eax; BugCheckParameter4
0x1400bd603  mov     rdx, rbx; BugCheckParameter2
0x1400bd606  lea     ecx, [r8+2]; BugCheckParameter1
0x1400bd60a  call    UlBugCheckEx
0x1400bd610  test    eax, eax
0x1400bd612  jnz     short loc_1400BD670
0x1400bd614  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd61b  jz      short loc_1400BD632
0x1400bd61d  lea     edx, [rax+24h]
0x1400bd620  mov     ecx, r13d
0x1400bd623  mov     r9, rbx
0x1400bd626  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd62d  call    WPP_SF_q
0x1400bd632  mov     rcx, [rbx+18h]; Irp
0x1400bd636  mov     dl, 2; PriorityBoost
0x1400bd638  mov     qword ptr [rbx+18h], 0
0x1400bd640  mov     dword ptr [rcx+30h], 0
0x1400bd647  call    cs:__imp_IofCompleteRequest
0x1400bd64e  nop     dword ptr [rax+rax+00h]
0x1400bd653  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd65a  jz      short loc_1400BD670
0x1400bd65c  mov     edx, 25h ; '%'
0x1400bd661  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd668  mov     ecx, r13d
0x1400bd66b  call    WPP_SF_
0x1400bd670  lea     rcx, [rbp+var_10]
0x1400bd674  call    UxPodDetachThread
0x1400bd679  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd680  jz      short loc_1400BD696
0x1400bd682  mov     edx, 23h ; '#'
0x1400bd687  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd68e  mov     ecx, r13d
0x1400bd691  call    WPP_SF_
0x1400bd696  mov     eax, 103h
0x1400bd69b  add     rsp, 60h
0x1400bd69f  pop     r15
0x1400bd6a1  pop     r14
0x1400bd6a3  pop     r13
0x1400bd6a5  pop     rdi
0x1400bd6a6  pop     rsi
0x1400bd6a7  pop     rbx
0x1400bd6a8  pop     rbp
0x1400bd6a9  retn
```

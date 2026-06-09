# UcCleanupClientSessionContext

- ea: `0x1400bd2ac`
- end: `0x1400bd5cb`
- name: `UcCleanupClientSessionContext`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140062980`

## callees

- `0x14000a350`
- `0x140035a50`
- `0x140062bd0`
- `0x1400bd2ac`
- `0x1400bd5d4`
- `0x1400bd6d8`
- `0x1400bd904`
- `0x1400bdb04`
- `0x1400bdd34`
- `0x14015c7a8`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400bd567`
- `ntoskrnl!IofCompleteRequest` at `0x1400bd567`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd3ec`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400bd3ec`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd375`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400bd375`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd3f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd419`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd3f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd419`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd40d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd40d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bd359`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bd359`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd33e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd365`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd33e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd365`

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
0x1400bd2ac  push    rbp
0x1400bd2ae  push    rbx
0x1400bd2af  push    rsi
0x1400bd2b0  push    rdi
0x1400bd2b1  push    r13
0x1400bd2b3  push    r14
0x1400bd2b5  push    r15
0x1400bd2b7  mov     rbp, rsp
0x1400bd2ba  sub     rsp, 60h
0x1400bd2be  lea     rax, [rbp+var_30]
0x1400bd2c2  xorps   xmm0, xmm0
0x1400bd2c5  mov     [rbp+var_30], rax
0x1400bd2c9  mov     r14, rdx
0x1400bd2cc  lea     rax, [rbp+var_30]
0x1400bd2d0  mov     rsi, rcx
0x1400bd2d3  mov     [rbp+var_28], rax
0x1400bd2d7  xor     r15b, r15b
0x1400bd2da  lea     rax, [rbp+var_20]
0x1400bd2de  mov     [rbp+var_20], rax
0x1400bd2e2  lea     rax, [rbp+var_20]
0x1400bd2e6  mov     [rbp+var_18], rax
0x1400bd2ea  movups  [rbp+var_10], xmm0
0x1400bd2ee  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400bd2f5  mov     r13d, 41Dh
0x1400bd2fb  jz      short loc_1400BD319
0x1400bd2fd  mov     edx, 22h ; '"'
0x1400bd302  mov     [rsp+60h+var_40], r14
0x1400bd307  mov     ecx, r13d
0x1400bd30a  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd311  mov     r9, rsi
0x1400bd314  call    WPP_SF_qq
0x1400bd319  mov     rax, [r14+30h]
0x1400bd31d  lea     rdx, [rbp+var_10]
0x1400bd321  mov     rbx, [rax+18h]
0x1400bd325  mov     rdi, [rbx+8]
0x1400bd329  mov     rcx, [rdi+48h]
0x1400bd32d  call    UxPodAttachThread
0x1400bd332  mov     rax, [r14+30h]
0x1400bd336  mov     qword ptr [rax+20h], 65534358h
0x1400bd33e  call    cs:__imp_KeEnterCriticalRegion
0x1400bd345  nop     dword ptr [rax+rax+00h]
0x1400bd34a  mov     rcx, [rdi+50h]
0x1400bd34e  mov     r14d, 2208h
0x1400bd354  add     rcx, r14
0x1400bd357  xor     edx, edx
0x1400bd359  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400bd360  nop     dword ptr [rax+rax+00h]
0x1400bd365  call    cs:__imp_KeEnterCriticalRegion
0x1400bd36c  nop     dword ptr [rax+rax+00h]
0x1400bd371  mov     rcx, [rdi+40h]
0x1400bd375  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400bd37c  nop     dword ptr [rax+rax+00h]
0x1400bd381  lea     rdx, [rbp+var_30]
0x1400bd385  mov     byte ptr [rbx+4], 1
0x1400bd389  mov     rcx, rbx
0x1400bd38c  call    UcpFlushConnectionsFromSessionContext
0x1400bd391  lea     rdx, [rbp+var_20]
0x1400bd395  mov     rcx, rbx
0x1400bd398  call    UcpFlushCredentialsFromSessionContext
0x1400bd39d  mov     rdx, rdi
0x1400bd3a0  mov     rcx, rbx
0x1400bd3a3  call    UcpRemoveSessionContextFromSessionList
0x1400bd3a8  lea     rax, [rdi+18h]
0x1400bd3ac  cmp     [rax], rax
0x1400bd3af  jnz     short loc_1400BD3E8
0x1400bd3b1  lea     rax, [rdi+8]
0x1400bd3b5  mov     rcx, [rax]
0x1400bd3b8  cmp     [rcx+8], rax
0x1400bd3bc  jnz     loc_1400BD4D9
0x1400bd3c2  mov     rdx, [rax+8]
0x1400bd3c6  cmp     [rdx], rax
0x1400bd3c9  jnz     loc_1400BD4D9
0x1400bd3cf  mov     [rdx], rcx
0x1400bd3d2  mov     r15b, 1
0x1400bd3d5  mov     [rcx+8], rdx
0x1400bd3d9  mov     qword ptr [rax], 0
0x1400bd3e0  mov     qword ptr [rax+8], 0
0x1400bd3e8  mov     rcx, [rdi+40h]
0x1400bd3ec  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400bd3f3  nop     dword ptr [rax+rax+00h]
0x1400bd3f8  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd3ff  nop     dword ptr [rax+rax+00h]
0x1400bd404  mov     rcx, [rdi+50h]
0x1400bd408  xor     edx, edx
0x1400bd40a  add     rcx, r14
0x1400bd40d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bd414  nop     dword ptr [rax+rax+00h]
0x1400bd419  call    cs:__imp_KeLeaveCriticalRegion
0x1400bd420  nop     dword ptr [rax+rax+00h]
0x1400bd425  mov     r14b, 20h ; ' '
0x1400bd428  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd42f  jz      short loc_1400BD449
0x1400bd431  mov     edx, 2Ch ; ','
0x1400bd436  lea     r9, [rbp+var_30]
0x1400bd43a  mov     ecx, r13d
0x1400bd43d  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd444  call    WPP_SF_q
0x1400bd449  mov     rcx, [rbp+var_30]
0x1400bd44d  lea     rax, [rbp+var_30]
0x1400bd451  cmp     rcx, rax
0x1400bd454  jz      short loc_1400BD491
0x1400bd456  lea     rax, [rbp+var_30]
0x1400bd45a  cmp     [rcx+8], rax
0x1400bd45e  jnz     short loc_1400BD4D9
0x1400bd460  mov     rax, [rcx]
0x1400bd463  cmp     [rax+8], rcx
0x1400bd467  jnz     short loc_1400BD4D9
0x1400bd469  mov     [rbp+var_30], rax
0x1400bd46d  lea     rdx, [rbp+var_30]
0x1400bd471  mov     [rax+8], rdx
0x1400bd475  xor     edx, edx
0x1400bd477  mov     qword ptr [rcx], 0
0x1400bd47e  mov     qword ptr [rcx+8], 0
0x1400bd486  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x1400bd48a  call    UcCloseConnection
0x1400bd48f  jmp     short loc_1400BD449
0x1400bd491  mov     rcx, [rbp+var_20]
0x1400bd495  lea     rax, [rbp+var_20]
0x1400bd499  cmp     rcx, rax
0x1400bd49c  jz      short loc_1400BD4E0
0x1400bd49e  lea     rax, [rbp+var_20]
0x1400bd4a2  cmp     [rcx+8], rax
0x1400bd4a6  jnz     short loc_1400BD4D9
0x1400bd4a8  mov     rax, [rcx]
0x1400bd4ab  cmp     [rax+8], rcx
0x1400bd4af  jnz     short loc_1400BD4D9
0x1400bd4b1  mov     [rbp+var_20], rax
0x1400bd4b5  lea     rdx, [rbp+var_20]
0x1400bd4b9  mov     [rax+8], rdx
0x1400bd4bd  xor     edx, edx
0x1400bd4bf  mov     qword ptr [rcx], 0
0x1400bd4c6  mov     qword ptr [rcx+8], 0
0x1400bd4ce  add     rcx, 0FFFFFFFFFFFFFFB8h; P
0x1400bd4d2  call    UcCloseCredential
0x1400bd4d7  jmp     short loc_1400BD491
0x1400bd4d9  mov     ecx, 3
0x1400bd4de  int     29h; Win8: RtlFailFast(ecx)
0x1400bd4e0  mov     rax, [rsi+0B8h]
0x1400bd4e7  or      byte ptr [rax+3], 1
0x1400bd4eb  mov     dword ptr [rsi+30h], 103h
0x1400bd4f2  mov     [rbx+18h], rsi
0x1400bd4f6  test    r15b, r15b
0x1400bd4f9  jz      short loc_1400BD503
0x1400bd4fb  mov     rcx, rdi; P
0x1400bd4fe  call    UcpCleanupClientSession
0x1400bd503  or      eax, 0FFFFFFFFh
0x1400bd506  lock xadd [rbx], eax
0x1400bd50a  dec     eax
0x1400bd50c  cmp     cs:UxDebugCheckRefcount, 0
0x1400bd513  jz      short loc_1400BD530
0x1400bd515  cmp     eax, 0FFFFFFFFh
0x1400bd518  jg      short loc_1400BD530
0x1400bd51a  mov     r8d, 1; BugCheckParameter3
0x1400bd520  movsxd  r9, eax; BugCheckParameter4
0x1400bd523  mov     rdx, rbx; BugCheckParameter2
0x1400bd526  lea     ecx, [r8+2]; BugCheckParameter1
0x1400bd52a  call    UlBugCheckEx
0x1400bd530  test    eax, eax
0x1400bd532  jnz     short loc_1400BD590
0x1400bd534  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd53b  jz      short loc_1400BD552
0x1400bd53d  lea     edx, [rax+24h]
0x1400bd540  mov     ecx, r13d
0x1400bd543  mov     r9, rbx
0x1400bd546  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd54d  call    WPP_SF_q
0x1400bd552  mov     rcx, [rbx+18h]; Irp
0x1400bd556  mov     dl, 2; PriorityBoost
0x1400bd558  mov     qword ptr [rbx+18h], 0
0x1400bd560  mov     dword ptr [rcx+30h], 0
0x1400bd567  call    cs:__imp_IofCompleteRequest
0x1400bd56e  nop     dword ptr [rax+rax+00h]
0x1400bd573  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd57a  jz      short loc_1400BD590
0x1400bd57c  mov     edx, 25h ; '%'
0x1400bd581  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd588  mov     ecx, r13d
0x1400bd58b  call    WPP_SF_
0x1400bd590  lea     rcx, [rbp+var_10]
0x1400bd594  call    UxPodDetachThread
0x1400bd599  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400bd5a0  jz      short loc_1400BD5B6
0x1400bd5a2  mov     edx, 23h ; '#'
0x1400bd5a7  lea     r8, WPP_1c9fc173e3a532fbfac1de99b88b286f_Traceguids
0x1400bd5ae  mov     ecx, r13d
0x1400bd5b1  call    WPP_SF_
0x1400bd5b6  mov     eax, 103h
0x1400bd5bb  add     rsp, 60h
0x1400bd5bf  pop     r15
0x1400bd5c1  pop     r14
0x1400bd5c3  pop     r13
0x1400bd5c5  pop     rdi
0x1400bd5c6  pop     rsi
0x1400bd5c7  pop     rbx
0x1400bd5c8  pop     rbp
0x1400bd5c9  retn
```

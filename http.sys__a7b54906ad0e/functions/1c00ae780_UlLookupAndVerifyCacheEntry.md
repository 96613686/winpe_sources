# UlLookupAndVerifyCacheEntry

- ea: `0x1c00ae780`
- end: `0x1c00aeb06`
- name: `UlLookupAndVerifyCacheEntry`
- size: `902`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1c00ae070`
- `0x1c0125d7c`

## callees

- `0x1c001194c`
- `0x1c002c560`
- `0x1c002e650`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c0090454`
- `0x1c0090c00`
- `0x1c00929d4`
- `0x1c0092ed8`
- `0x1c00936d8`
- `0x1c00ae780`
- `0x1c00d314c`
- `0x1c010623c`
- `0x1c01062dc`
- `0x1c0106a68`
- `0x1c010949c`
- `0x1c010b698`
- `0x1c0142738`
- `0x1c01431ec`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00e4570`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00e4570`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00e451d`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00e451d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ae90e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e457c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ae90e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e457c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00ae902`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00ae902`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00ae8d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00ae8d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ae8c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e4508`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ae8c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e4508`

## pseudocode

```c
__int64 __fastcall UlLookupAndVerifyCacheEntry(__int64 a1, __int64 *a2, _DWORD *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // r8d
  __int64 v10; // rcx
  __int64 v11; // rsi
  int v12; // r15d
  unsigned __int64 v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rsi
  int v16; // edx
  int RoutingToken; // ebx
  int v19; // edx
  __int64 BestContent; // rax
  __int64 v21; // r9
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r14
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // r15
  __int128 v30; // [rsp+30h] [rbp-50h] BYREF
  __int128 v31; // [rsp+40h] [rbp-40h]
  __int128 v32; // [rsp+50h] [rbp-30h]
  __int64 v33; // [rsp+60h] [rbp-20h]

  v30 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    if ( a1 )
      v25 = *(_QWORD *)(a1 + 64);
    else
      v25 = 0;
    WPP_SF_qqqI(132, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, a1, v25, a2, a3);
  }
  *a2 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
  if ( !*(_DWORD *)(v6 + 1160) && !*(_DWORD *)(v6 + 1164) )
    goto LABEL_4;
  RoutingToken = UlGenerateRoutingToken(a1, 2);
  if ( RoutingToken < 0 )
  {
    UlSetErrorCode(a1, 18, 0);
    *a3 = 5;
    goto LABEL_17;
  }
  LOBYTE(v26) = 1;
  UlInitSearchKeyFromRequest(a1, v26, &v30);
  v15 = UlCheckoutUriCacheEntry(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL), &v30, a1);
  if ( !v15 )
  {
LABEL_4:
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
      WPP_SF_qilq(113, WPP_ede9639403cc3db159114586db5b30dd_Traceguids, a1, *(_QWORD *)(a1 + 64), 0, &v30);
    v7 = *(_QWORD *)(a1 + 2016);
    v8 = *(_DWORD *)(a1 + 2052);
    v9 = *(_DWORD *)(a1 + 2048);
    *((_QWORD *)&v31 + 1) = *(_QWORD *)(a1 + 2032);
    HIDWORD(v30) = v8;
    v10 = (*((_QWORD *)&v31 + 1) - v7) >> 1;
    *(_QWORD *)&v31 = *(_QWORD *)(a1 + 2024);
    LOWORD(v10) = 2 * v10;
    LOWORD(v8) = *(_WORD *)(a1 + 2058);
    DWORD2(v30) = v9;
    WORD2(v32) = v8;
    LOWORD(v8) = *(_WORD *)(a1 + 2056);
    WORD1(v32) = v9 - v10;
    *(_QWORD *)&v30 = v7;
    LOWORD(v32) = v8;
    *((_QWORD *)&v32 + 1) = 0;
    LODWORD(v33) = 0;
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
      WPP_SF_(114, WPP_ede9639403cc3db159114586db5b30dd_Traceguids);
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
      WPP_SF_qqqi(v10, v7, v11, &v30, a1, *(_QWORD *)(a1 + 64));
    v12 = HIDWORD(v30);
    v13 = *(_QWORD *)(v11 + 1072) + ((unsigned __int64)(HIDWORD(v30) & (unsigned int)UlHashTableMask) << 6);
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(v13, 0);
    v14 = *(_QWORD *)(v13 + 8);
    if ( !v14 )
    {
LABEL_11:
      v15 = 0;
      if ( v14 )
      {
        BestContent = UlFindBestContent(v14, a1);
        v15 = BestContent;
        if ( BestContent )
          _InterlockedIncrement((volatile signed __int32 *)(BestContent + 4));
      }
      ExReleasePushLockSharedEx(v13, 0);
      KeLeaveCriticalRegion();
      if ( !v15 )
      {
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) == 0 )
          goto LABEL_14;
        WPP_SF_SS(22, WPP_ede9639403cc3db159114586db5b30dd_Traceguids, *((_QWORD *)&v32 + 1), v30);
        goto LABEL_67;
      }
      v21 = *(_QWORD *)(v15 + 8);
      if ( *(_DWORD *)(v15 + 124) == 2 && MEMORY[0xFFFFF78000000014] > *(_QWORD *)(v15 + 136) )
      {
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
        {
          v27 = 23;
LABEL_63:
          WPP_SF_q(v27, WPP_ede9639403cc3db159114586db5b30dd_Traceguids, v15);
        }
      }
      else
      {
        v22 = *(_QWORD *)(v15 + 208);
        if ( !v22 || !*(_DWORD *)(v22 + 224) )
        {
          ++*(_DWORD *)(v15 + 32);
          *(_DWORD *)(v15 + 120) = 0;
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) == 0 )
            goto LABEL_14;
          WPP_SF_qSd(25, v16, v15, *(_QWORD *)(v21 + 40), *(_DWORD *)(v15 + 4));
LABEL_67:
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
            WPP_SF_q(26, WPP_ede9639403cc3db159114586db5b30dd_Traceguids, v15);
LABEL_14:
          if ( !v15 )
          {
            *a3 = 2;
LABEL_16:
            RoutingToken = 0;
            goto LABEL_17;
          }
          goto LABEL_31;
        }
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
        {
          v27 = 24;
          goto LABEL_63;
        }
      }
      UlCheckinUriCacheEntry((PVOID)v15);
      v15 = 0;
      goto LABEL_67;
    }
    v19 = v33;
    while ( 1 )
    {
      if ( *(_DWORD *)(v14 + 52) == v12 )
      {
        if ( *((_QWORD *)&v32 + 1) && v19 )
        {
          if ( WORD1(v32) + v19 == *(_DWORD *)(v14 + 48) )
          {
            if ( (unsigned __int8)UlEqualUnicodeStringEx(
                                    DWORD2(v32),
                                    v19,
                                    DWORD2(v31),
                                    WORD1(v32),
                                    *(_QWORD *)(v14 + 40)) )
              goto LABEL_11;
            goto LABEL_50;
          }
        }
        else if ( DWORD2(v30) == *(_DWORD *)(v14 + 48) )
        {
          if ( (unsigned __int8)UlEqualUnicodeString(v30, *(_QWORD *)(v14 + 40)) )
            goto LABEL_11;
LABEL_50:
          v19 = v33;
        }
      }
      v14 = *(_QWORD *)(v14 + 8);
      if ( !v14 )
        goto LABEL_11;
    }
  }
LABEL_31:
  if ( !*(_DWORD *)(v15 + 512) )
    goto LABEL_69;
  v23 = *(_DWORD *)(v15 + 352);
  if ( v23 == 4 )
  {
    RoutingToken = -1073741772;
    v24 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
      WPP_SF_qq(162, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a1, *(_QWORD *)(a1 + 64));
    if ( *(int *)(v24 + 1324) > 0 || *(int *)(v24 + 1320) > 0 )
    {
      KeEnterCriticalRegion();
      v29 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v24 + 1360), 0);
      if ( *(int *)(*(_QWORD *)(v24 + 1312) + 28LL) <= 0
        || (RoutingToken = UlpTreeFindIpOnlyNode(a1, 3), RoutingToken == -1073741772) )
      {
        if ( *(int *)(*(_QWORD *)(v24 + 1312) + 16LL) > 0 )
          RoutingToken = UlpTreeFindIpOnlyNode(a1, 2);
      }
      ExReleaseCacheAwarePushLockSharedEx(v29, 0);
      KeLeaveCriticalRegion();
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
      WPP_SF_D(163, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
    if ( RoutingToken >= 0 )
      goto LABEL_69;
    if ( RoutingToken == -1073741772 )
      goto LABEL_41;
    UlCheckinUriCacheEntry((PVOID)v15);
    UlSetErrorCode(a1, 18, 0);
    *a3 = 5;
  }
  else
  {
    if ( v23 == 1 )
    {
      v28 = UlLookupHostPlusIPSite(a1);
      if ( v28 >= 0 )
        goto LABEL_69;
      if ( v28 != -1073741772 )
      {
        UlCheckinUriCacheEntry((PVOID)v15);
        UlSetErrorCode(a1, 18, 0);
        *a3 = 5;
        goto LABEL_16;
      }
      goto LABEL_41;
    }
    if ( v23 > 1 && (v23 <= 3 || v23 == 5) )
    {
LABEL_41:
      if ( (*(_DWORD *)(a1 + 2184) & 0x20) != 0 || (unsigned __int8)UlParseAcceptHeaderMatch(a1, v15) )
      {
        *a3 = 1;
        *a2 = v15;
        goto LABEL_16;
      }
LABEL_69:
      UlCheckinUriCacheEntry((PVOID)v15);
      *a3 = 2;
      goto LABEL_16;
    }
    UlCheckinUriCacheEntry((PVOID)v15);
    UlSetErrorCode(a1, 18, 0);
    *a3 = 5;
    RoutingToken = -1073741436;
  }
LABEL_17:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqD(133, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, *a2, a3, RoutingToken);
  return (unsigned int)RoutingToken;
}

```

## disassembly

```asm
0x1c00ae780  push    rbp
0x1c00ae782  push    r12
0x1c00ae784  push    r13
0x1c00ae786  mov     rbp, rsp
0x1c00ae789  sub     rsp, 80h
0x1c00ae790  xorps   xmm0, xmm0
0x1c00ae793  mov     [rsp+80h+arg_10], rdi
0x1c00ae79b  xor     eax, eax
0x1c00ae79d  mov     [rsp+80h+var_10], r15
0x1c00ae7a2  movups  [rbp+var_50], xmm0
0x1c00ae7a6  mov     [rbp+var_20], rax
0x1c00ae7aa  mov     r12, r8
0x1c00ae7ad  movups  [rbp+var_40], xmm0
0x1c00ae7b1  mov     r13, rdx
0x1c00ae7b4  mov     rdi, rcx
0x1c00ae7b7  movups  [rbp+var_30], xmm0
0x1c00ae7bb  xor     r15d, r15d
0x1c00ae7be  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00ae7c8  jnz     loc_1C00E42A8
0x1c00ae7ce  mov     [r13+0], r15
0x1c00ae7d2  mov     rax, [rdi+18h]
0x1c00ae7d6  mov     [rsp+80h+arg_0], rbx
0x1c00ae7de  mov     [rsp+80h+arg_8], rsi
0x1c00ae7e6  mov     [rsp+80h+var_8], r14
0x1c00ae7eb  mov     rcx, [rax+3C0h]
0x1c00ae7f2  cmp     [rcx+488h], r15d
0x1c00ae7f9  jnz     loc_1C00E42DA
0x1c00ae7ff  cmp     [rcx+48Ch], r15d
0x1c00ae806  jnz     loc_1C00E42DA
0x1c00ae80c  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00ae816  jnz     loc_1C00E433C
0x1c00ae81c  mov     rcx, [rdi+7F0h]
0x1c00ae823  mov     rdx, [rdi+7E0h]
0x1c00ae82a  mov     eax, [rdi+804h]
0x1c00ae830  mov     r8d, [rdi+800h]
0x1c00ae837  mov     qword ptr [rbp+var_40+8], rcx
0x1c00ae83b  sub     rcx, rdx
0x1c00ae83e  mov     dword ptr [rbp+var_50+0Ch], eax
0x1c00ae841  mov     rax, [rdi+7E8h]
0x1c00ae848  sar     rcx, 1
0x1c00ae84b  mov     qword ptr [rbp+var_40], rax
0x1c00ae84f  add     cx, cx
0x1c00ae852  movzx   eax, word ptr [rdi+80Ah]
0x1c00ae859  mov     dword ptr [rbp+var_50+8], r8d
0x1c00ae85d  sub     r8w, cx
0x1c00ae861  mov     word ptr [rbp+var_30+4], ax
0x1c00ae865  movzx   eax, word ptr [rdi+808h]
0x1c00ae86c  mov     word ptr [rbp+var_30+2], r8w
0x1c00ae871  mov     qword ptr [rbp+var_50], rdx
0x1c00ae875  mov     word ptr [rbp+var_30], ax
0x1c00ae879  mov     qword ptr [rbp+var_30+8], r15
0x1c00ae87d  mov     dword ptr [rbp+var_20], r15d
0x1c00ae881  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00ae88b  jnz     loc_1C00E4368
0x1c00ae891  mov     rax, [rdi+18h]
0x1c00ae895  mov     rsi, [rax+3C0h]
0x1c00ae89c  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00ae8a6  jnz     loc_1C00E437F
0x1c00ae8ac  mov     r15d, dword ptr [rbp+var_50+0Ch]
0x1c00ae8b0  mov     ebx, cs:UlHashTableMask
0x1c00ae8b6  and     rbx, r15
0x1c00ae8b9  shl     rbx, 6
0x1c00ae8bd  add     rbx, [rsi+430h]
0x1c00ae8c4  call    cs:__imp_KeEnterCriticalRegion
0x1c00ae8cb  nop     dword ptr [rax+rax+00h]
0x1c00ae8d0  xor     edx, edx
0x1c00ae8d2  mov     rcx, rbx
0x1c00ae8d5  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00ae8dc  nop     dword ptr [rax+rax+00h]
0x1c00ae8e1  mov     r14, [rbx+8]
0x1c00ae8e5  test    r14, r14
0x1c00ae8e8  jnz     loc_1C00AE989
0x1c00ae8ee  xor     r15d, r15d
0x1c00ae8f1  mov     esi, r15d
0x1c00ae8f4  test    r14, r14
0x1c00ae8f7  jnz     loc_1C00AE9A5
0x1c00ae8fd  xor     edx, edx
0x1c00ae8ff  mov     rcx, rbx
0x1c00ae902  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00ae909  nop     dword ptr [rax+rax+00h]
0x1c00ae90e  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ae915  nop     dword ptr [rax+rax+00h]
0x1c00ae91a  test    rsi, rsi
0x1c00ae91d  jnz     loc_1C00AE9C5
0x1c00ae923  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00ae92d  jnz     loc_1C00E439F
0x1c00ae933  test    rsi, rsi
0x1c00ae936  jnz     loc_1C00AEA08
0x1c00ae93c  mov     dword ptr [r12], 2
0x1c00ae944  mov     ebx, r15d
0x1c00ae947  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00ae951  mov     r15, [rsp+80h+var_10]
0x1c00ae956  mov     r14, [rsp+80h+var_8]
0x1c00ae95b  mov     rdi, [rsp+80h+arg_10]
0x1c00ae963  mov     rsi, [rsp+80h+arg_8]
0x1c00ae96b  jnz     loc_1C00E45E6
0x1c00ae971  mov     eax, ebx
0x1c00ae973  mov     rbx, [rsp+80h+arg_0]
0x1c00ae97b  add     rsp, 80h
0x1c00ae982  pop     r13
0x1c00ae984  pop     r12
0x1c00ae986  pop     rbp
0x1c00ae987  retn
0x1c00ae989  mov     edx, dword ptr [rbp+var_20]
0x1c00ae98c  cmp     [r14+34h], r15d
0x1c00ae990  jz      loc_1C00AEA9F
0x1c00ae996  mov     r14, [r14+8]
0x1c00ae99a  test    r14, r14
0x1c00ae99d  jz      loc_1C00AE8EE
0x1c00ae9a3  jmp     short loc_1C00AE98C
0x1c00ae9a5  mov     rdx, rdi
0x1c00ae9a8  mov     rcx, r14
0x1c00ae9ab  call    UlFindBestContent
0x1c00ae9b0  mov     rsi, rax
0x1c00ae9b3  test    rax, rax
0x1c00ae9b6  jz      loc_1C00AE8FD
0x1c00ae9bc  lock inc dword ptr [rax+4]
0x1c00ae9c0  jmp     loc_1C00AE8FD
0x1c00ae9c5  cmp     dword ptr [rsi+7Ch], 2
0x1c00ae9c9  mov     r9, [rsi+8]
0x1c00ae9cd  jz      loc_1C00E43BA
0x1c00ae9d3  mov     rax, [rsi+0D0h]
0x1c00ae9da  test    rax, rax
0x1c00ae9dd  jz      short loc_1C00AE9EC
0x1c00ae9df  cmp     [rax+0E0h], r15d
0x1c00ae9e6  jnz     loc_1C00E4408
0x1c00ae9ec  inc     dword ptr [rsi+20h]
0x1c00ae9ef  mov     [rsi+78h], r15d
0x1c00ae9f3  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00ae9fd  jz      loc_1C00AE933
0x1c00aea03  jmp     loc_1C00E4416
0x1c00aea08  cmp     dword ptr [rsi+200h], 0
0x1c00aea0f  jz      loc_1C00E4458
0x1c00aea15  mov     eax, [rsi+160h]
0x1c00aea1b  cmp     eax, 4
0x1c00aea1e  jnz     loc_1C00E446D
0x1c00aea24  mov     rax, [rdi+18h]
0x1c00aea28  mov     ebx, 0C0000034h
0x1c00aea2d  mov     r14, [rax+3C0h]
0x1c00aea34  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aea3a  test    al, 8
0x1c00aea3c  jnz     loc_1C00E44EA
0x1c00aea42  cmp     dword ptr [r14+52Ch], 0
0x1c00aea4a  jg      loc_1C00E4508
0x1c00aea50  cmp     dword ptr [r14+528h], 0
0x1c00aea58  jg      loc_1C00E4508
0x1c00aea5e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aea64  test    al, 8
0x1c00aea66  jnz     loc_1C00E4590
0x1c00aea6c  test    ebx, ebx
0x1c00aea6e  jns     loc_1C00E4458
0x1c00aea74  cmp     ebx, 0C0000034h
0x1c00aea7a  jnz     loc_1C00E45AA
0x1c00aea80  mov     eax, [rdi+888h]
0x1c00aea86  test    al, 20h
0x1c00aea88  jz      loc_1C00E45CE
0x1c00aea8e  mov     dword ptr [r12], 1
0x1c00aea96  mov     [r13+0], rsi
0x1c00aea9a  jmp     loc_1C00AE944
0x1c00aea9f  mov     rcx, qword ptr [rbp+var_30+8]
0x1c00aeaa3  test    rcx, rcx
0x1c00aeaa6  jnz     short loc_1C00AEACD
0x1c00aeaa8  mov     r8d, dword ptr [rbp+var_50+8]
0x1c00aeaac  cmp     r8d, [r14+30h]
0x1c00aeab0  jnz     loc_1C00AE996
0x1c00aeab6  mov     rdx, [r14+28h]
0x1c00aeaba  mov     rcx, qword ptr [rbp+var_50]
0x1c00aeabe  call    UlEqualUnicodeString
0x1c00aeac3  test    al, al
0x1c00aeac5  jnz     loc_1C00AE8EE
0x1c00aeacb  jmp     short loc_1C00AEAFE
0x1c00aeacd  test    edx, edx
0x1c00aeacf  jz      short loc_1C00AEAA8
0x1c00aead1  movzx   r9d, word ptr [rbp+var_30+2]
0x1c00aead6  lea     eax, [r9+rdx]
0x1c00aeada  cmp     eax, [r14+30h]
0x1c00aeade  jnz     loc_1C00AE996
0x1c00aeae4  mov     rax, [r14+28h]
0x1c00aeae8  mov     r8, qword ptr [rbp+var_40+8]
0x1c00aeaec  mov     [rsp+80h+var_60], rax
0x1c00aeaf1  call    UlEqualUnicodeStringEx
0x1c00aeaf6  test    al, al
0x1c00aeaf8  jnz     loc_1C00AE8EE
0x1c00aeafe  mov     edx, dword ptr [rbp+var_20]
0x1c00aeb01  jmp     loc_1C00AE996
0x1c00e42a8  test    rdi, rdi
0x1c00e42ab  jz      short loc_1C00E42B3
0x1c00e42ad  mov     r9, [rcx+40h]
0x1c00e42b1  jmp     short loc_1C00E42B6
0x1c00e42b3  mov     r9, r15
0x1c00e42b6  mov     ecx, 84h
0x1c00e42bb  mov     [rsp+80h+var_58], r12
0x1c00e42c0  mov     r8, rdi
0x1c00e42c3  mov     [rsp+80h+var_60], r13
0x1c00e42c8  lea     rdx, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids
0x1c00e42cf  call    WPP_SF_qqqI
0x1c00e42d4  nop
0x1c00e42d5  jmp     loc_1C00AE7CE
0x1c00e42da  mov     edx, 2
0x1c00e42df  mov     rcx, rdi
0x1c00e42e2  call    UlGenerateRoutingToken
0x1c00e42e7  mov     ebx, eax
0x1c00e42e9  mov     rcx, rdi
0x1c00e42ec  test    eax, eax
0x1c00e42ee  jns     short loc_1C00E4309
0x1c00e42f0  xor     r8d, r8d
0x1c00e42f3  lea     edx, [r8+12h]
0x1c00e42f7  call    UlSetErrorCode
0x1c00e42fc  mov     dword ptr [r12], 5
0x1c00e4304  jmp     loc_1C00AE947
0x1c00e4309  lea     r8, [rbp+var_50]
0x1c00e430d  mov     dl, 1
0x1c00e430f  call    UlInitSearchKeyFromRequest
0x1c00e4314  mov     rcx, [rdi+18h]
0x1c00e4318  lea     rdx, [rbp+var_50]
0x1c00e431c  mov     r8, rdi
0x1c00e431f  mov     rcx, [rcx+3C0h]
0x1c00e4326  call    UlCheckoutUriCacheEntry
0x1c00e432b  mov     rsi, rax
0x1c00e432e  test    rax, rax
0x1c00e4331  jnz     loc_1C00AEA08
0x1c00e4337  jmp     loc_1C00AE80C
0x1c00e433c  mov     r9, [rdi+40h]
0x1c00e4340  lea     rax, [rbp+var_50]
0x1c00e4344  mov     [rsp+80h+var_58], rax
0x1c00e4349  lea     rdx, WPP_ede9639403cc3db159114586db5b30dd_Traceguids
0x1c00e4350  mov     ecx, 71h ; 'q'
0x1c00e4355  mov     dword ptr [rsp+80h+var_60], r15d
0x1c00e435a  mov     r8, rdi
0x1c00e435d  call    WPP_SF_qilq
0x1c00e4362  nop
0x1c00e4363  jmp     loc_1C00AE81C
0x1c00e4368  mov     ecx, 72h ; 'r'
0x1c00e436d  lea     rdx, WPP_ede9639403cc3db159114586db5b30dd_Traceguids
0x1c00e4374  call    WPP_SF_
0x1c00e4379  nop
0x1c00e437a  jmp     loc_1C00AE891
0x1c00e437f  mov     rax, [rdi+40h]
0x1c00e4383  lea     r9, [rbp+var_50]
0x1c00e4387  mov     [rsp+80h+var_58], rax
0x1c00e438c  mov     r8, rsi
0x1c00e438f  mov     [rsp+80h+var_60], rdi
0x1c00e4394  call    WPP_SF_qqqi
0x1c00e4399  nop
0x1c00e439a  jmp     loc_1C00AE8AC
0x1c00e439f  mov     r9, qword ptr [rbp+var_50]
0x1c00e43a3  lea     rdx, WPP_ede9639403cc3db159114586db5b30dd_Traceguids
0x1c00e43aa  mov     r8, qword ptr [rbp+var_30+8]
0x1c00e43ae  mov     ecx, 16h
0x1c00e43b3  call    WPP_SF_SS
0x1c00e43b8  jmp     short loc_1C00E442E
0x1c00e43ba  mov     rax, 0FFFFF78000000014h
0x1c00e43c4  mov     rax, [rax]
0x1c00e43c7  cmp     rax, [rsi+88h]
0x1c00e43ce  jle     loc_1C00AE9D3
0x1c00e43d4  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00e43de  jz      short loc_1C00E43FB
0x1c00e43e0  mov     ecx, 17h
0x1c00e43e5  jmp     short loc_1C00E43EC
0x1c00e43e7  mov     ecx, 18h
0x1c00e43ec  mov     r8, rsi
0x1c00e43ef  lea     rdx, WPP_ede9639403cc3db159114586db5b30dd_Traceguids
0x1c00e43f6  call    WPP_SF_q
0x1c00e43fb  mov     rcx, rsi; P
0x1c00e43fe  call    UlCheckinUriCacheEntry
0x1c00e4403  mov     rsi, r15
0x1c00e4406  jmp     short loc_1C00E442E
0x1c00e4408  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00e4412  jz      short loc_1C00E43FB
0x1c00e4414  jmp     short loc_1C00E43E7
0x1c00e4416  mov     eax, [rsi+4]
0x1c00e4419  mov     ecx, 19h
0x1c00e441e  mov     r9, [r9+28h]
0x1c00e4422  mov     r8, rsi
0x1c00e4425  mov     dword ptr [rsp+80h+var_60], eax
0x1c00e4429  call    WPP_SF_qSd
0x1c00e442e  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00e4438  jz      loc_1C00AE933
0x1c00e443e  mov     ecx, 1Ah
0x1c00e4443  lea     rdx, WPP_ede9639403cc3db159114586db5b30dd_Traceguids
0x1c00e444a  mov     r8, rsi
0x1c00e444d  call    WPP_SF_q
0x1c00e4452  nop
0x1c00e4453  jmp     loc_1C00AE933
0x1c00e4458  mov     rcx, rsi; P
0x1c00e445b  call    UlCheckinUriCacheEntry
0x1c00e4460  mov     dword ptr [r12], 2
0x1c00e4468  jmp     loc_1C00AE944
0x1c00e446d  cmp     eax, 1
0x1c00e4470  jz      short loc_1C00E44AF
0x1c00e4472  jle     short loc_1C00E4486
0x1c00e4474  cmp     eax, 3
0x1c00e4477  jle     loc_1C00AEA80
0x1c00e447d  cmp     eax, 5
0x1c00e4480  jz      loc_1C00AEA80
0x1c00e4486  mov     rcx, rsi; P
0x1c00e4489  call    UlCheckinUriCacheEntry
0x1c00e448e  xor     r8d, r8d
0x1c00e4491  mov     rcx, rdi
0x1c00e4494  lea     edx, [r8+12h]
  ... truncated ...
```

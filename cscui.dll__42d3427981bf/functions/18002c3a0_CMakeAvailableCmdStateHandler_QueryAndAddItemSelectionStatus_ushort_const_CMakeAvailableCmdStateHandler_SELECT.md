# CMakeAvailableCmdStateHandler::_QueryAndAddItemSelectionStatus(ushort const *,CMakeAvailableCmdStateHandler::SELECTION_STATUS *)

- ea: `0x18002c3a0`
- end: `0x18002c692`
- name: `?_QueryAndAddItemSelectionStatus@CMakeAvailableCmdStateHandler@@AEAAJPEBGPEAUSELECTION_STATUS@1@@Z`
- size: `754`
- prototype: `__int64 __fastcall(CMakeAvailableCmdStateHandler *__hidden this, const unsigned __int16 *, struct CMakeAvailableCmdStateHandler::SELECTION_STATUS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c910`

## callees

- `0x18001101c`
- `0x180013d9c`
- `0x18001465c`
- `0x18002be10`
- `0x18002bec4`
- `0x18002c3a0`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18002c411`
- `SHLWAPI!PathIsUNCW` at `0x18002c411`
- `SHLWAPI!StrChrW` at `0x18002c473`
- `SHLWAPI!StrChrW` at `0x18002c473`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c4b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c4b8`

## pseudocode

```c
__int64 __fastcall CMakeAvailableCmdStateHandler::_QueryAndAddItemSelectionStatus(
        WCHAR *this,
        const unsigned __int16 *a2,
        struct CMakeAvailableCmdStateHandler::SELECTION_STATUS *a3)
{
  int IsItemParentPinned; // ebx
  const unsigned __int16 *v8; // rbx
  PWSTR v9; // rax
  __int64 v10; // r9
  int IsItemCacheable; // eax
  __int64 v12; // rcx
  int v13; // eax
  UstCommon::CImpersonator *v14; // rcx
  __int64 v15; // rdx
  int v16; // ecx
  __int128 v17; // [rsp+30h] [rbp-79h]
  _OWORD v18[2]; // [rsp+40h] [rbp-69h] BYREF
  void **v19; // [rsp+60h] [rbp-49h] BYREF
  __int64 v20; // [rsp+68h] [rbp-41h]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-39h]
  __int64 v22; // [rsp+78h] [rbp-31h]
  __int128 v23; // [rsp+80h] [rbp-29h]
  __int128 v24; // [rsp+90h] [rbp-19h]
  __int64 v25; // [rsp+A0h] [rbp-9h]
  __int64 v26; // [rsp+A8h] [rbp-1h]
  __int64 v27; // [rsp+B0h] [rbp+7h]
  int v28; // [rsp+128h] [rbp+7Fh] BYREF

  v28 = 0;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids, a2);
  }
  memset(v18, 0, 28);
  v17 = 0;
  if ( !PathIsUNCW(a2) )
    goto LABEL_5;
  v8 = a2 + 2;
  v9 = StrChrW(a2 + 2, 0x5Cu);
  if ( v9 )
  {
    v10 = v9 - v8;
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
  }
  if ( CompareStringW(0x400u, 1u, a2 + 2, v10, this + 60, -1) == 2 )
  {
LABEL_5:
    IsItemParentPinned = -2147024735;
  }
  else
  {
    IsItemCacheable = CMakeAvailableCmdStateHandler::_IsItemCacheable((CMakeAvailableCmdStateHandler *)this, a2, &v28);
    IsItemParentPinned = IsItemCacheable;
    if ( IsItemCacheable == 1 )
    {
      IsItemParentPinned = -2147467259;
      goto LABEL_6;
    }
    if ( IsItemCacheable < 0 )
      goto LABEL_6;
    if ( !v28 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) == 0 )
      {
        goto LABEL_50;
      }
      v15 = 24;
      goto LABEL_49;
    }
    v12 = *((_QWORD *)this + 4);
    v19 = &CQueryCscItemInfoTask::`vftable';
    v23 = 0;
    v24 = 0;
    v20 = 0;
    v21 = a2;
    v22 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v13 = CComTaskThread<CCscComTaskContext>::DoTask(v12, &v19);
    IsItemParentPinned = v13;
    if ( v13 == -2147024894 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) == 0 )
      {
        goto LABEL_50;
      }
      v15 = 23;
LABEL_49:
      WPP_SF_S(*((_QWORD *)v14 + 2), v15, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids, a2);
LABEL_50:
      IsItemParentPinned = 0;
      v16 = 1;
      goto LABEL_51;
    }
    if ( v13 >= 0 )
    {
      IsItemParentPinned = v20;
      if ( (int)v20 >= 0 )
      {
        if ( (_DWORD)v24 )
          DWORD2(v17) = 1;
        if ( *(_QWORD *)((char *)&v24 + 4) || HIDWORD(v24) )
          HIDWORD(v17) = 1;
        if ( (v26 & 0x1000) != 0 )
          ++DWORD1(v18[0]);
        if ( (_DWORD)v25 )
          ++DWORD2(v18[1]);
        if ( (_DWORD)v27 == 1 )
        {
          switch ( HIDWORD(v27) )
          {
            case 2:
              ++LODWORD(v18[1]);
              break;
            case 3:
              ++DWORD1(v18[1]);
              break;
            case 4:
              ++HIDWORD(v18[0]);
              break;
          }
        }
        ++LODWORD(v18[0]);
        IsItemParentPinned = CMakeAvailableCmdStateHandler::_IsItemParentPinned(
                               (CMakeAvailableCmdStateHandler *)this,
                               a2);
        if ( IsItemParentPinned )
        {
          if ( IsItemParentPinned < 0 )
            goto LABEL_6;
        }
        else
        {
          ++DWORD2(v18[0]);
        }
        v16 = 0;
LABEL_51:
        *(_DWORD *)a3 += v17;
        *((_DWORD *)a3 + 2) += DWORD2(v17);
        *((_DWORD *)a3 + 3) += HIDWORD(v17);
        *((_DWORD *)a3 + 4) += LODWORD(v18[0]);
        *((_DWORD *)a3 + 6) += DWORD2(v18[0]);
        *((_DWORD *)a3 + 7) += HIDWORD(v18[0]);
        *((_DWORD *)a3 + 8) += LODWORD(v18[1]);
        *((_DWORD *)a3 + 9) += DWORD1(v18[1]);
        *((_DWORD *)a3 + 5) += DWORD1(v18[0]);
        *((_DWORD *)a3 + 1) += v16;
        *((_DWORD *)a3 + 10) += DWORD2(v18[1]);
      }
    }
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids,
      (unsigned int)IsItemParentPinned);
  }
  return (unsigned int)IsItemParentPinned;
}

```

## disassembly

```asm
0x18002c3a0  push    rbp
0x18002c3a2  push    rbx
0x18002c3a3  push    rsi
0x18002c3a4  push    rdi
0x18002c3a5  push    r12
0x18002c3a7  push    r13
0x18002c3a9  push    r14
0x18002c3ab  push    r15
0x18002c3ad  lea     rbp, [rsp-1Fh]
0x18002c3b2  sub     rsp, 0C8h
0x18002c3b9  xor     r15d, r15d
0x18002c3bc  mov     rsi, r8
0x18002c3bf  mov     [rbp+57h+arg_18], r15d
0x18002c3c3  mov     rdi, rdx
0x18002c3c6  mov     r14, rcx
0x18002c3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3d0  lea     rax, WPP_GLOBAL_Control
0x18002c3d7  mov     r13d, 4000000h
0x18002c3dd  cmp     rcx, rax
0x18002c3e0  jz      short loc_18002C3FF
0x18002c3e2  test    [rcx+1Ch], r13d
0x18002c3e6  jz      short loc_18002C3FF
0x18002c3e8  mov     rcx, [rcx+10h]
0x18002c3ec  lea     edx, [r15+16h]
0x18002c3f0  mov     r9, rdi
0x18002c3f3  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002c3fa  call    WPP_SF_S
0x18002c3ff  xorps   xmm0, xmm0
0x18002c402  mov     rcx, rdi; pszPath
0x18002c405  movups  [rbp+57h+var_C0], xmm0
0x18002c409  movups  [rbp+57h+var_C0+0Ch], xmm0
0x18002c40d  movups  [rbp+57h+var_D0], xmm0
0x18002c411  call    cs:__imp_PathIsUNCW
0x18002c417  test    eax, eax
0x18002c419  jnz     short loc_18002C467
0x18002c41b  mov     ebx, 800700A1h
0x18002c420  lea     r14, WPP_GLOBAL_Control
0x18002c427  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c42e  cmp     rcx, r14
0x18002c431  jz      short loc_18002C451
0x18002c433  test    [rcx+1Ch], r13d
0x18002c437  jz      short loc_18002C451
0x18002c439  mov     rcx, [rcx+10h]
0x18002c43d  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002c444  mov     edx, 19h
0x18002c449  mov     r9d, ebx
0x18002c44c  call    WPP_SF_d
0x18002c451  mov     eax, ebx
0x18002c453  add     rsp, 0C8h
0x18002c45a  pop     r15
0x18002c45c  pop     r14
0x18002c45e  pop     r13
0x18002c460  pop     r12
0x18002c462  pop     rdi
0x18002c463  pop     rsi
0x18002c464  pop     rbx
0x18002c465  pop     rbp
0x18002c466  retn
0x18002c467  lea     rbx, [rdi+4]
0x18002c46b  mov     edx, 5Ch ; '\'; wMatch
0x18002c470  mov     rcx, rbx; pszStart
0x18002c473  call    cs:__imp_StrChrW
0x18002c479  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c47d  mov     r9, rax
0x18002c480  test    rax, rax
0x18002c483  jz      short loc_18002C48D
0x18002c485  sub     r9, rbx
0x18002c488  sar     r9, 1
0x18002c48b  jmp     short loc_18002C49A
0x18002c48d  mov     r9, rcx
0x18002c490  inc     r9; cchCount1
0x18002c493  cmp     [rbx+r9*2], r15w
0x18002c498  jnz     short loc_18002C490
0x18002c49a  mov     [rsp+100h+cchCount2], ecx; cchCount2
0x18002c49e  lea     rax, [r14+78h]
0x18002c4a2  mov     r12d, 1
0x18002c4a8  mov     [rsp+100h+lpString2], rax; lpString2
0x18002c4ad  mov     edx, r12d; dwCmpFlags
0x18002c4b0  mov     r8, rbx; lpString1
0x18002c4b3  mov     ecx, 400h; Locale
0x18002c4b8  call    cs:__imp_CompareStringW
0x18002c4be  cmp     eax, 2
0x18002c4c1  jz      loc_18002C41B
0x18002c4c7  lea     r8, [rbp+57h+arg_18]; int *
0x18002c4cb  mov     rdx, rdi; unsigned __int16 *
0x18002c4ce  mov     rcx, r14; this
0x18002c4d1  call    ?_IsItemCacheable@CMakeAvailableCmdStateHandler@@AEAAJPEBGPEAH@Z; CMakeAvailableCmdStateHandler::_IsItemCacheable(ushort const *,int *)
0x18002c4d6  mov     ebx, eax
0x18002c4d8  cmp     eax, r12d
0x18002c4db  jnz     short loc_18002C4E7
0x18002c4dd  mov     ebx, 80004005h
0x18002c4e2  jmp     loc_18002C420
0x18002c4e7  test    eax, eax
0x18002c4e9  js      loc_18002C420
0x18002c4ef  cmp     [rbp+57h+arg_18], r15d
0x18002c4f3  jz      loc_18002C615
0x18002c4f9  mov     rcx, [r14+20h]
0x18002c4fd  lea     rax, ??_7CQueryCscItemInfoTask@@6B@; const CQueryCscItemInfoTask::`vftable'
0x18002c504  xorps   xmm0, xmm0
0x18002c507  mov     [rbp+57h+var_A0], rax
0x18002c50b  xorps   xmm1, xmm1
0x18002c50e  movdqa  [rbp+57h+var_80], xmm0
0x18002c513  lea     rdx, [rbp+57h+var_A0]
0x18002c517  movdqa  [rbp+57h+var_70], xmm1
0x18002c51c  mov     [rbp+57h+var_98], r15
0x18002c520  mov     [rbp+57h+var_90], rdi
0x18002c524  mov     [rbp+57h+var_88], r15
0x18002c528  mov     [rbp+57h+var_60], r15
0x18002c52c  mov     [rbp+57h+var_58], r15
0x18002c530  mov     [rbp+57h+var_50], r15
0x18002c534  call    ?DoTask@?$CComTaskThread@VCCscComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscComTaskContext@@@@@Z; CComTaskThread<CCscComTaskContext>::DoTask(CComTask<CCscComTaskContext> *)
0x18002c539  mov     ebx, eax
0x18002c53b  cmp     eax, 80070002h
0x18002c540  jnz     short loc_18002C56D
0x18002c542  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c549  lea     r14, WPP_GLOBAL_Control
0x18002c550  cmp     rcx, r14
0x18002c553  jz      loc_18002C646
0x18002c559  test    [rcx+1Ch], r13d
0x18002c55d  jz      loc_18002C646
0x18002c563  mov     edx, 17h
0x18002c568  jmp     loc_18002C633
0x18002c56d  test    eax, eax
0x18002c56f  js      loc_18002C420
0x18002c575  mov     ebx, dword ptr [rbp+57h+var_98]
0x18002c578  test    ebx, ebx
0x18002c57a  js      loc_18002C420
0x18002c580  mov     eax, dword ptr [rbp+57h+var_58]
0x18002c583  and     eax, 1000h
0x18002c588  cmp     dword ptr [rbp+57h+var_70], r15d
0x18002c58c  jz      short loc_18002C592
0x18002c58e  add     dword ptr [rbp+57h+var_D0+8], r12d
0x18002c592  cmp     dword ptr [rbp+57h+var_70+4], r15d
0x18002c596  jnz     short loc_18002C5A4
0x18002c598  cmp     dword ptr [rbp+57h+var_70+8], r15d
0x18002c59c  jnz     short loc_18002C5A4
0x18002c59e  cmp     dword ptr [rbp+57h+var_70+0Ch], r15d
0x18002c5a2  jz      short loc_18002C5A8
0x18002c5a4  add     dword ptr [rbp+57h+var_D0+0Ch], r12d
0x18002c5a8  test    eax, eax
0x18002c5aa  jz      short loc_18002C5B0
0x18002c5ac  add     dword ptr [rbp+57h+var_C0+4], r12d
0x18002c5b0  cmp     dword ptr [rbp+57h+var_60], r15d
0x18002c5b4  jz      short loc_18002C5BA
0x18002c5b6  add     [rbp+57h+var_A8], r12d
0x18002c5ba  test    ebx, ebx
0x18002c5bc  js      short loc_18002C5E6
0x18002c5be  cmp     dword ptr [rbp+57h+var_50], r12d
0x18002c5c2  jnz     short loc_18002C5E6
0x18002c5c4  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x18002c5c7  sub     ecx, 2
0x18002c5ca  jz      short loc_18002C5E2
0x18002c5cc  sub     ecx, r12d
0x18002c5cf  jz      short loc_18002C5DC
0x18002c5d1  cmp     ecx, r12d
0x18002c5d4  jnz     short loc_18002C5E6
0x18002c5d6  add     dword ptr [rbp+57h+var_C0+0Ch], r12d
0x18002c5da  jmp     short loc_18002C5E6
0x18002c5dc  add     [rbp+57h+var_AC], r12d
0x18002c5e0  jmp     short loc_18002C5E6
0x18002c5e2  add     [rbp+57h+var_B0], r12d
0x18002c5e6  add     dword ptr [rbp+57h+var_C0], r12d
0x18002c5ea  mov     rdx, rdi; unsigned __int16 *
0x18002c5ed  mov     rcx, r14; this
0x18002c5f0  call    ?_IsItemParentPinned@CMakeAvailableCmdStateHandler@@AEAAJPEBG@Z; CMakeAvailableCmdStateHandler::_IsItemParentPinned(ushort const *)
0x18002c5f5  mov     ebx, eax
0x18002c5f7  test    eax, eax
0x18002c5f9  jnz     short loc_18002C60B
0x18002c5fb  add     dword ptr [rbp+57h+var_C0+8], r12d
0x18002c5ff  mov     ecx, dword ptr [rbp+57h+var_D0+4]
0x18002c602  lea     r14, WPP_GLOBAL_Control
0x18002c609  jmp     short loc_18002C64F
0x18002c60b  test    ebx, ebx
0x18002c60d  js      loc_18002C420
0x18002c613  jmp     short loc_18002C5FF
0x18002c615  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c61c  lea     r14, WPP_GLOBAL_Control
0x18002c623  cmp     rcx, r14
0x18002c626  jz      short loc_18002C646
0x18002c628  test    [rcx+1Ch], r13d
0x18002c62c  jz      short loc_18002C646
0x18002c62e  mov     edx, 18h
0x18002c633  mov     rcx, [rcx+10h]
0x18002c637  lea     r8, WPP_d6b627e249a03c7d4470f53aabba48a7_Traceguids
0x18002c63e  mov     r9, rdi
0x18002c641  call    WPP_SF_S
0x18002c646  mov     ecx, dword ptr [rbp+57h+var_D0+4]
0x18002c649  mov     ebx, r15d
0x18002c64c  add     ecx, r12d
0x18002c64f  mov     eax, dword ptr [rbp+57h+var_D0]
0x18002c652  add     [rsi], eax
0x18002c654  mov     eax, dword ptr [rbp+57h+var_D0+8]
0x18002c657  add     [rsi+8], eax
0x18002c65a  mov     eax, dword ptr [rbp+57h+var_D0+0Ch]
0x18002c65d  add     [rsi+0Ch], eax
0x18002c660  mov     eax, dword ptr [rbp+57h+var_C0]
0x18002c663  add     [rsi+10h], eax
0x18002c666  mov     eax, dword ptr [rbp+57h+var_C0+8]
0x18002c669  add     [rsi+18h], eax
0x18002c66c  mov     eax, dword ptr [rbp+57h+var_C0+0Ch]
0x18002c66f  add     [rsi+1Ch], eax
0x18002c672  mov     eax, [rbp+57h+var_B0]
0x18002c675  add     [rsi+20h], eax
0x18002c678  mov     eax, [rbp+57h+var_AC]
0x18002c67b  add     [rsi+24h], eax
0x18002c67e  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x18002c681  add     [rsi+14h], eax
0x18002c684  add     [rsi+4], ecx
0x18002c687  mov     eax, [rbp+57h+var_A8]
0x18002c68a  add     [rsi+28h], eax
0x18002c68d  jmp     loc_18002C427
```

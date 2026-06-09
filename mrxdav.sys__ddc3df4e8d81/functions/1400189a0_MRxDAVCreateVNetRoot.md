# MRxDAVCreateVNetRoot

- ea: `0x1400189a0`
- end: `0x1400191a6`
- name: `MRxDAVCreateVNetRoot`
- size: `2054`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001bc4`
- `0x140002ac4`
- `0x140002be4`
- `0x1400033dc`
- `0x140006880`
- `0x1400189a0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400189d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018a1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018a85`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018acd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018b31`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018b7c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018be0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018c46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018d9e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018e26`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018ebd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018f32`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001905a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400190bb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019100`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001916c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400189d7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018a1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018a85`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018acd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018b31`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018b7c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018be0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018c46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018d9e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018e26`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018ebd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018f32`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001905a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400190bb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019100`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001916c`
- `ntoskrnl!ExAllocatePool2` at `0x140018f81`
- `ntoskrnl!ExAllocatePool2` at `0x140018f81`
- `rdbss!RxNameCacheInitializeEx` at `0x140018fd5`
- `rdbss!RxNameCacheInitializeEx` at `0x140019000`
- `rdbss!RxNameCacheInitializeEx` at `0x140019029`
- `rdbss!RxNameCacheInitializeEx` at `0x140018fd5`
- `rdbss!RxNameCacheInitializeEx` at `0x140019000`
- `rdbss!RxNameCacheInitializeEx` at `0x140019029`

## string_xrefs

- `0x140018c7c`: `MRxDAVCreateVNetRoot`
- `0x140018dcd`: `MRxDAVCreateVNetRoot`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateVNetRoot(__int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // r15
  __int64 v8; // rsi
  __int64 v9; // r13
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // rbx
  HANDLE v15; // rax
  int v16; // edi
  __int64 v17; // rbx
  HANDLE v18; // rax
  int v19; // ebx
  __int64 v20; // rdi
  HANDLE v21; // rax
  __int64 v22; // rbx
  BOOL v23; // edi
  HANDLE v24; // rax
  int v25; // edx
  int v26; // edi
  int v27; // r8d
  __int64 v28; // rbx
  HANDLE v29; // rax
  int v30; // eax
  int v31; // edi
  __int64 v32; // rax
  unsigned __int16 v33; // si
  int v34; // edx
  __int64 v35; // rcx
  unsigned __int16 v36; // si
  int v37; // r8d
  __int64 v38; // rbx
  HANDLE v39; // rax
  __int64 v40; // rbx
  HANDLE v41; // rax
  __int64 v42; // rbx
  HANDLE v43; // rax
  int v44; // edi
  __int64 v45; // rbx
  HANDLE v46; // rax
  volatile signed __int32 *v47; // rsi
  __int64 Pool2; // rax
  __int64 v49; // rdi
  __int64 v50; // rbx
  HANDLE v51; // rax
  volatile signed __int32 v52; // ebx
  __int64 v53; // rdi
  HANDLE v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rbx
  HANDLE v58; // rax
  __int64 v59; // rbx
  HANDLE v60; // rax
  int v62; // [rsp+90h] [rbp+8h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 10, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qq(v5, 11, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v6, 0);
    }
  }
  v7 = *(_QWORD *)(a1 + 264);
  v8 = *(_QWORD *)(a1 + 32);
  v62 = v8;
  v9 = *(_QWORD *)(v7 + 32);
  v10 = *(_QWORD *)(v7 + 40);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v11 = *(_QWORD *)(v9 + 88);
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZ(v12, 12, (unsigned int)WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v13, v11);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      WPP_SF_qq(v14, 13, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v15, v7);
    }
  }
  v16 = *(_DWORD *)(v7 + 72);
  *(_DWORD *)(v10 + 80) = v16;
  *(_DWORD *)(v10 + 84) = *(_DWORD *)(v7 + 76);
  *(_DWORD *)(v10 + 76) = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      WPP_SF_qD(v17, 14, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v18, v16);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v19 = *(_DWORD *)(v10 + 84);
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v21 = PsGetCurrentThreadId();
      WPP_SF_qD(v20, 15, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v21, v19);
    }
  }
  if ( ((*(_BYTE *)(v9 + 77) - 1) & 0xFB) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v57 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v58 = PsGetCurrentThreadId();
      WPP_SF_q(v57, 16, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v58);
    }
    v31 = -1073741634;
    *(_DWORD *)(v10 + 100) = 1;
    *(_DWORD *)(a1 + 284) = -1073741634;
    goto LABEL_88;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v23 = ((*(_DWORD *)(v8 + 120) >> 12) & 1) == 0;
    v24 = PsGetCurrentThreadId();
    WPP_SF_qD(v22, 17, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v24, v23);
  }
  v26 = MRxDAVGetCompletePathName(v8, 0x744E5644u, (struct _UNICODE_STRING *)(v10 + 112));
  if ( v26 < 0 )
  {
    *(_DWORD *)(v10 + 100) = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v28 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v29 = PsGetCurrentThreadId();
      WPP_SF_qD(v28, 18, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v29, v26);
    }
    *(_DWORD *)(a1 + 280) = -1073741634;
    goto LABEL_89;
  }
  *(_QWORD *)(v8 + 216) = v7;
  *(_QWORD *)(v8 + 232) = a1;
  v30 = UMRxAsyncEngOuterWrapper(
          v8,
          v25,
          v27,
          4,
          (__int64)MRxDAVCreateVNetRootContinuation,
          (__int64)"MRxDAVCreateVNetRoot");
  v31 = v30;
  if ( v30 < 0 )
  {
    if ( v30 == -1073741790
      || v30 == -1073741718
      || v30 == -1073741715
      || v30 == -1073741424
      || v30 == -1073741117
      || v30 == -1073740918
      || v30 == -1073739515 )
    {
      goto LABEL_55;
    }
    v32 = *(_QWORD *)(v8 + 216);
    if ( v32 )
      v2 = *(_QWORD *)(v32 + 40);
    v33 = *(_WORD *)(v2 + 112);
    v34 = 0;
    if ( !v33 )
      goto LABEL_55;
    v35 = *(_QWORD *)(v2 + 120);
    v36 = (v33 >> 1) - 1;
    if ( !v36 )
      goto LABEL_55;
    v37 = 0xFFFF;
    while ( !*(_WORD *)(v35 + 2LL * v36) )
    {
      if ( !--v36 )
        goto LABEL_55;
    }
    while ( *(_WORD *)(v35 + 2LL * v36) == 92 )
    {
      if ( !--v36 )
        goto LABEL_55;
    }
    while ( *(_WORD *)(v35 + 2LL * v36) != 92 )
    {
      if ( !--v36 )
        goto LABEL_55;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v38 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v39 = PsGetCurrentThreadId();
      WPP_SF_qD(v38, 19, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v39, v31);
    }
    *(_WORD *)(v2 + 112) = 2 * v36;
    v31 = UMRxAsyncEngOuterWrapper(
            v62,
            v34,
            v37,
            4,
            (__int64)MRxDAVCreateVNetRootContinuation,
            (__int64)"MRxDAVCreateVNetRoot");
  }
  if ( v31 )
  {
LABEL_55:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v40 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v41 = PsGetCurrentThreadId();
      WPP_SF_qD(v40, 20, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v41, v31);
    }
    *(_DWORD *)(v10 + 100) = 1;
    if ( v31 != -1073741790
      && v31 != -1073741715
      && v31 != -1073741419
      && v31 != -1073741117
      && v31 != -1073740918
      && v31 != -1073739515 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v42 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v43 = PsGetCurrentThreadId();
        WPP_SF_qD(v42, 21, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v43, v31);
      }
      v31 = -1073741634;
    }
LABEL_88:
    *(_DWORD *)(a1 + 280) = v31;
    goto LABEL_89;
  }
  if ( *(_DWORD *)(v10 + 92) || *(_DWORD *)(v10 + 88) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v46 = PsGetCurrentThreadId();
      WPP_SF_q(v45, 22, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v46);
    }
    v44 = -1073741634;
  }
  else
  {
    *(_DWORD *)(v9 + 80) = 7;
    *(_BYTE *)(v9 + 77) = 0;
    v44 = 0;
  }
  *(_DWORD *)(a1 + 280) = v44;
  *(_DWORD *)(a1 + 284) = v44;
  v47 = *(volatile signed __int32 **)(v9 + 40);
  if ( v47 )
  {
    *(_QWORD *)(v7 + 48) = v47;
    _InterlockedIncrement(v47);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v52 = *v47;
      v53 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v54 = PsGetCurrentThreadId();
      WPP_SF_qqqqd(v53, v55, v56, v54, v47, v9, v7, v52);
    }
  }
  else
  {
    Pool2 = ExAllocatePool2(66, 568, 1951290948);
    *(_QWORD *)(v9 + 40) = Pool2;
    v49 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 2;
      *(_QWORD *)(Pool2 + 8) = v9;
      RxNameCacheInitializeEx(Pool2 + 16, 40, (unsigned int)NameCacheMaxEntries);
      RxNameCacheInitializeEx(v49 + 200, 24, (unsigned int)NameCacheMaxEntries);
      RxNameCacheInitializeEx(v49 + 384, 0, (unsigned int)NameCacheMaxEntries);
      *(_QWORD *)(v7 + 48) = v49;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v50 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v51 = PsGetCurrentThreadId();
        WPP_SF_qqqq(v50, 23, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v51, v49, v9, v7);
      }
    }
    else
    {
      *(_DWORD *)(a1 + 280) = -1073741670;
      *(_DWORD *)(a1 + 284) = -1073741670;
    }
  }
LABEL_89:
  (*(void (__fastcall **)(__int64))(a1 + 272))(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v59 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v60 = PsGetCurrentThreadId();
    WPP_SF_q(v59, 27, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v60);
  }
  return 259;
}

```

## disassembly

```asm
0x1400189a0  push    rbx
0x1400189a2  push    rbp
0x1400189a3  push    rsi
0x1400189a4  push    rdi
0x1400189a5  push    r12
0x1400189a7  push    r13
0x1400189a9  push    r14
0x1400189ab  push    r15
0x1400189ad  sub     rsp, 48h
0x1400189b1  mov     rbp, rcx
0x1400189b4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400189bb  lea     rcx, WPP_GLOBAL_Control
0x1400189c2  xor     r12d, r12d
0x1400189c5  cmp     rbx, rcx
0x1400189c8  jz      short loc_140018A49
0x1400189ca  test    dword ptr [rbx+2Ch], 4000h
0x1400189d1  jz      short loc_140018A01
0x1400189d3  mov     rbx, [rbx+18h]
0x1400189d7  call    cs:__imp_PsGetCurrentThreadId
0x1400189de  nop     dword ptr [rax+rax+00h]
0x1400189e3  lea     edx, [r12+0Ah]
0x1400189e8  mov     rcx, rbx
0x1400189eb  mov     r9, rax
0x1400189ee  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400189f5  call    WPP_SF_q
0x1400189fa  lea     rcx, WPP_GLOBAL_Control
0x140018a01  mov     rbx, cs:WPP_GLOBAL_Control
0x140018a08  cmp     rbx, rcx
0x140018a0b  jz      short loc_140018A49
0x140018a0d  test    dword ptr [rbx+2Ch], 2000h
0x140018a14  jz      short loc_140018A49
0x140018a16  mov     rbx, [rbx+18h]
0x140018a1a  call    cs:__imp_PsGetCurrentThreadId
0x140018a21  nop     dword ptr [rax+rax+00h]
0x140018a26  mov     edx, 0Bh
0x140018a2b  mov     [rsp+88h+var_68], r12
0x140018a30  mov     r9, rax
0x140018a33  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018a3a  mov     rcx, rbx
0x140018a3d  call    WPP_SF_qq
0x140018a42  lea     rcx, WPP_GLOBAL_Control
0x140018a49  mov     r15, [rbp+108h]
0x140018a50  mov     rsi, [rbp+20h]
0x140018a54  mov     [rsp+88h+arg_0], rsi
0x140018a5c  mov     r13, [r15+20h]
0x140018a60  mov     r14, [r15+28h]
0x140018a64  mov     rdi, cs:WPP_GLOBAL_Control
0x140018a6b  cmp     rdi, rcx
0x140018a6e  jz      loc_140018AFC
0x140018a74  test    dword ptr [rdi+2Ch], 4000h
0x140018a7b  jz      short loc_140018AB4
0x140018a7d  mov     rbx, [r13+58h]
0x140018a81  mov     rdi, [rdi+18h]
0x140018a85  call    cs:__imp_PsGetCurrentThreadId
0x140018a8c  nop     dword ptr [rax+rax+00h]
0x140018a91  mov     edx, 0Ch
0x140018a96  mov     [rsp+88h+var_68], rbx
0x140018a9b  mov     r9, rax
0x140018a9e  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018aa5  mov     rcx, rdi
0x140018aa8  call    WPP_SF_qZ
0x140018aad  lea     rcx, WPP_GLOBAL_Control
0x140018ab4  mov     rbx, cs:WPP_GLOBAL_Control
0x140018abb  cmp     rbx, rcx
0x140018abe  jz      short loc_140018AFC
0x140018ac0  test    dword ptr [rbx+2Ch], 4000h
0x140018ac7  jz      short loc_140018AFC
0x140018ac9  mov     rbx, [rbx+18h]
0x140018acd  call    cs:__imp_PsGetCurrentThreadId
0x140018ad4  nop     dword ptr [rax+rax+00h]
0x140018ad9  mov     edx, 0Dh
0x140018ade  mov     [rsp+88h+var_68], r15
0x140018ae3  mov     r9, rax
0x140018ae6  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018aed  mov     rcx, rbx
0x140018af0  call    WPP_SF_qq
0x140018af5  lea     rcx, WPP_GLOBAL_Control
0x140018afc  mov     edi, [r15+48h]
0x140018b00  mov     [r14+50h], edi
0x140018b04  mov     eax, [r15+4Ch]
0x140018b08  mov     [r14+54h], eax
0x140018b0c  mov     dword ptr [r14+4Ch], 1
0x140018b14  mov     rbx, cs:WPP_GLOBAL_Control
0x140018b1b  cmp     rbx, rcx
0x140018b1e  jz      loc_140018BAA
0x140018b24  test    dword ptr [rbx+2Ch], 4000h
0x140018b2b  jz      short loc_140018B5F
0x140018b2d  mov     rbx, [rbx+18h]
0x140018b31  call    cs:__imp_PsGetCurrentThreadId
0x140018b38  nop     dword ptr [rax+rax+00h]
0x140018b3d  mov     edx, 0Eh
0x140018b42  mov     dword ptr [rsp+88h+var_68], edi
0x140018b46  mov     r9, rax
0x140018b49  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018b50  mov     rcx, rbx
0x140018b53  call    WPP_SF_qD
0x140018b58  lea     rcx, WPP_GLOBAL_Control
0x140018b5f  mov     rdi, cs:WPP_GLOBAL_Control
0x140018b66  cmp     rdi, rcx
0x140018b69  jz      short loc_140018BAA
0x140018b6b  test    dword ptr [rdi+2Ch], 4000h
0x140018b72  jz      short loc_140018BAA
0x140018b74  mov     ebx, [r14+54h]
0x140018b78  mov     rdi, [rdi+18h]
0x140018b7c  call    cs:__imp_PsGetCurrentThreadId
0x140018b83  nop     dword ptr [rax+rax+00h]
0x140018b88  mov     edx, 0Fh
0x140018b8d  mov     dword ptr [rsp+88h+var_68], ebx
0x140018b91  mov     r9, rax
0x140018b94  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018b9b  mov     rcx, rdi
0x140018b9e  call    WPP_SF_qD
0x140018ba3  lea     rcx, WPP_GLOBAL_Control
0x140018baa  mov     al, [r13+4Dh]
0x140018bae  mov     edx, 1
0x140018bb3  sub     al, dl
0x140018bb5  test    al, 0FBh
0x140018bb7  jz      loc_1400190E7
0x140018bbd  mov     rbx, cs:WPP_GLOBAL_Control
0x140018bc4  cmp     rbx, rcx
0x140018bc7  jz      short loc_140018C07
0x140018bc9  test    dword ptr [rbx+2Ch], 4000h
0x140018bd0  jz      short loc_140018C07
0x140018bd2  mov     edi, [rsi+78h]
0x140018bd5  mov     rbx, [rbx+18h]
0x140018bd9  shr     edi, 0Ch
0x140018bdc  not     edi
0x140018bde  and     edi, edx
0x140018be0  call    cs:__imp_PsGetCurrentThreadId
0x140018be7  nop     dword ptr [rax+rax+00h]
0x140018bec  mov     edx, 11h
0x140018bf1  mov     dword ptr [rsp+88h+var_68], edi
0x140018bf5  mov     r9, rax
0x140018bf8  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018bff  mov     rcx, rbx
0x140018c02  call    WPP_SF_qD
0x140018c07  lea     r8, [r14+70h]
0x140018c0b  mov     edx, 744E5644h
0x140018c10  mov     rcx, rsi
0x140018c13  call    MRxDAVGetCompletePathName
0x140018c18  mov     edi, eax
0x140018c1a  test    eax, eax
0x140018c1c  jns     short loc_140018C7C
0x140018c1e  mov     dword ptr [r14+64h], 1
0x140018c26  mov     rbx, cs:WPP_GLOBAL_Control
0x140018c2d  lea     rax, WPP_GLOBAL_Control
0x140018c34  cmp     rbx, rax
0x140018c37  jz      short loc_140018C6D
0x140018c39  test    dword ptr [rbx+2Ch], 2000h
0x140018c40  jz      short loc_140018C6D
0x140018c42  mov     rbx, [rbx+18h]
0x140018c46  call    cs:__imp_PsGetCurrentThreadId
0x140018c4d  nop     dword ptr [rax+rax+00h]
0x140018c52  mov     edx, 12h
0x140018c57  mov     dword ptr [rsp+88h+var_68], edi
0x140018c5b  mov     r9, rax
0x140018c5e  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018c65  mov     rcx, rbx
0x140018c68  call    WPP_SF_qD
0x140018c6d  mov     dword ptr [rbp+118h], 0C00000BEh
0x140018c77  jmp     loc_14001913D
0x140018c7c  lea     rax, aMrxdavcreatevn; "MRxDAVCreateVNetRoot"
0x140018c83  mov     [rsi+0D8h], r15
0x140018c8a  mov     [rsp+88h+var_60], rax
0x140018c8f  mov     r9d, 4
0x140018c95  lea     rax, MRxDAVCreateVNetRootContinuation
0x140018c9c  mov     [rsi+0E8h], rbp
0x140018ca3  mov     rcx, rsi
0x140018ca6  mov     [rsp+88h+var_68], rax
0x140018cab  call    UMRxAsyncEngOuterWrapper
0x140018cb0  mov     edi, eax
0x140018cb2  test    eax, eax
0x140018cb4  jns     loc_140018DFE
0x140018cba  cmp     eax, 0C0000022h
0x140018cbf  jz      loc_140018E06
0x140018cc5  cmp     eax, 0C000006Ah
0x140018cca  jz      loc_140018E06
0x140018cd0  cmp     eax, 0C000006Dh
0x140018cd5  jz      loc_140018E06
0x140018cdb  cmp     eax, 0C0000190h
0x140018ce0  jz      loc_140018E06
0x140018ce6  cmp     eax, 0C00002C3h
0x140018ceb  jz      loc_140018E06
0x140018cf1  cmp     eax, 0C000038Ah
0x140018cf6  jz      loc_140018E06
0x140018cfc  cmp     eax, 0C0000905h
0x140018d01  jz      loc_140018E06
0x140018d07  mov     rax, [rsi+0D8h]
0x140018d0e  test    rax, rax
0x140018d11  jz      short loc_140018D17
0x140018d13  mov     r12, [rax+28h]
0x140018d17  movzx   esi, word ptr [r12+70h]
0x140018d1d  xor     edx, edx
0x140018d1f  test    si, si
0x140018d22  jz      loc_140018E06
0x140018d28  mov     rcx, [r12+78h]
0x140018d2d  shr     si, 1
0x140018d30  sub     si, 1
0x140018d34  jz      loc_140018E06
0x140018d3a  mov     r8d, 0FFFFh
0x140018d40  movzx   eax, si
0x140018d43  cmp     [rcx+rax*2], dx
0x140018d47  jnz     short loc_140018D54
0x140018d49  add     si, r8w
0x140018d4d  jnz     short loc_140018D40
0x140018d4f  jmp     loc_140018E06
0x140018d54  movzx   eax, si
0x140018d57  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x140018d5c  jnz     short loc_140018D69
0x140018d5e  add     si, r8w
0x140018d62  jnz     short loc_140018D54
0x140018d64  jmp     loc_140018E06
0x140018d69  movzx   eax, si
0x140018d6c  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x140018d71  jz      short loc_140018D7E
0x140018d73  add     si, r8w
0x140018d77  jnz     short loc_140018D69
0x140018d79  jmp     loc_140018E06
0x140018d7e  mov     rbx, cs:WPP_GLOBAL_Control
0x140018d85  lea     rax, WPP_GLOBAL_Control
0x140018d8c  cmp     rbx, rax
0x140018d8f  jz      short loc_140018DC5
0x140018d91  test    dword ptr [rbx+2Ch], 2000h
0x140018d98  jz      short loc_140018DC5
0x140018d9a  mov     rbx, [rbx+18h]
0x140018d9e  call    cs:__imp_PsGetCurrentThreadId
0x140018da5  nop     dword ptr [rax+rax+00h]
0x140018daa  mov     edx, 13h
0x140018daf  mov     dword ptr [rsp+88h+var_68], edi
0x140018db3  mov     r9, rax
0x140018db6  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018dbd  mov     rcx, rbx
0x140018dc0  call    WPP_SF_qD
0x140018dc5  mov     rcx, [rsp+88h+arg_0]
0x140018dcd  lea     rax, aMrxdavcreatevn; "MRxDAVCreateVNetRoot"
0x140018dd4  mov     [rsp+88h+var_60], rax
0x140018dd9  add     si, si
0x140018ddc  lea     rax, MRxDAVCreateVNetRootContinuation
0x140018de3  mov     [r12+70h], si
0x140018de9  mov     r9d, 4
0x140018def  mov     [rsp+88h+var_68], rax
0x140018df4  call    UMRxAsyncEngOuterWrapper
0x140018df9  mov     edi, eax
0x140018dfb  xor     r12d, r12d
0x140018dfe  test    edi, edi
0x140018e00  jz      loc_140018EEE
0x140018e06  mov     rbx, cs:WPP_GLOBAL_Control
0x140018e0d  lea     rax, WPP_GLOBAL_Control
0x140018e14  cmp     rbx, rax
0x140018e17  jz      short loc_140018E54
0x140018e19  test    dword ptr [rbx+2Ch], 2000h
0x140018e20  jz      short loc_140018E4D
0x140018e22  mov     rbx, [rbx+18h]
0x140018e26  call    cs:__imp_PsGetCurrentThreadId
0x140018e2d  nop     dword ptr [rax+rax+00h]
0x140018e32  mov     edx, 14h
0x140018e37  mov     dword ptr [rsp+88h+var_68], edi
0x140018e3b  mov     r9, rax
0x140018e3e  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018e45  mov     rcx, rbx
0x140018e48  call    WPP_SF_qD
0x140018e4d  lea     rax, WPP_GLOBAL_Control
0x140018e54  mov     dword ptr [r14+64h], 1
0x140018e5c  cmp     edi, 0C0000022h
0x140018e62  jz      loc_140019137
0x140018e68  cmp     edi, 0C000006Dh
0x140018e6e  jz      loc_140019137
0x140018e74  cmp     edi, 0C0000195h
0x140018e7a  jz      loc_140019137
0x140018e80  cmp     edi, 0C00002C3h
0x140018e86  jz      loc_140019137
0x140018e8c  cmp     edi, 0C000038Ah
0x140018e92  jz      loc_140019137
0x140018e98  cmp     edi, 0C0000905h
0x140018e9e  jz      loc_140019137
0x140018ea4  mov     rbx, cs:WPP_GLOBAL_Control
0x140018eab  cmp     rbx, rax
0x140018eae  jz      short loc_140018EE4
0x140018eb0  test    dword ptr [rbx+2Ch], 2000h
0x140018eb7  jz      short loc_140018EE4
0x140018eb9  mov     rbx, [rbx+18h]
0x140018ebd  call    cs:__imp_PsGetCurrentThreadId
0x140018ec4  nop     dword ptr [rax+rax+00h]
0x140018ec9  mov     edx, 15h
0x140018ece  mov     dword ptr [rsp+88h+var_68], edi
0x140018ed2  mov     r9, rax
0x140018ed5  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140018edc  mov     rcx, rbx
0x140018edf  call    WPP_SF_qD
0x140018ee4  mov     edi, 0C00000BEh
0x140018ee9  jmp     loc_140019137
0x140018eee  cmp     [r14+5Ch], r12d
0x140018ef2  jnz     short loc_140018F12
0x140018ef4  cmp     [r14+58h], r12d
0x140018ef8  jnz     short loc_140018F12
0x140018efa  mov     dword ptr [r13+50h], 7
0x140018f02  lea     r14, WPP_GLOBAL_Control
0x140018f09  mov     [r13+4Dh], r12b
0x140018f0d  mov     edi, r12d
0x140018f10  jmp     short loc_140018F5A
  ... truncated ...
```

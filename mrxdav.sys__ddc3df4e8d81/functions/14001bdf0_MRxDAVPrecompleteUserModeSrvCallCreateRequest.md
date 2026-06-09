# MRxDAVPrecompleteUserModeSrvCallCreateRequest

- ea: `0x14001bdf0`
- end: `0x14001c38e`
- name: `MRxDAVPrecompleteUserModeSrvCallCreateRequest`
- size: `1438`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400019bc`
- `0x140001b64`
- `0x140003464`
- `0x140006880`
- `0x14001bdf0`
- `0x14001c570`
- `0x140027658`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001be38`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001be7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bf27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bf8d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bfeb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c04e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c0b1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c114`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c177`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c1dd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c2cd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c34a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001be38`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001be7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bf27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bf8d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bfeb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c04e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c0b1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c114`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c177`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c1dd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c2cd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c34a`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001bedd`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001bedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bef2`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeSrvCallCreateRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // r15
  __int64 v13; // rbp
  __int64 v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  unsigned int v19; // eax
  int v20; // r14d
  __int64 v21; // rbx
  HANDLE v22; // rax
  int v23; // r14d
  __int64 v24; // rbx
  HANDLE v25; // rax
  int v26; // r14d
  __int64 v27; // rbx
  HANDLE v28; // rax
  int v29; // r14d
  __int64 v30; // rbx
  HANDLE v31; // rax
  int v32; // r14d
  __int64 v33; // rbx
  HANDLE v34; // rax
  int v35; // esi
  __int64 v36; // rbx
  HANDLE v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // esi
  unsigned __int16 v41; // di
  __int64 v42; // rcx
  unsigned __int16 v43; // di
  __int64 v44; // rbx
  HANDLE v45; // rax
  __int64 v47; // rbx
  HANDLE v48; // rax
  __int64 v49; // [rsp+60h] [rbp+8h] BYREF

  v49 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 36, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 37, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v11, a1, a2);
    }
  }
  v12 = 0;
  if ( a5 )
  {
    v13 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      WPP_SF_qqq(v15, 38, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v16, a1, a2);
    }
  }
  else
  {
    v13 = *(_QWORD *)(a2 + 216);
    v14 = *(_QWORD *)(v13 + 264);
    if ( v14 )
      v12 = *(_QWORD *)(v14 + 32);
    SeDeleteClientSecurity(*(_QWORD *)(a2 + 224));
    ExFreePoolWithTag(*(PVOID *)(a2 + 224), 0);
    *(_QWORD *)(a2 + 224) = 0;
    *(_BYTE *)(v12 + 4) = 0;
  }
  v17 = *(_QWORD *)(a3 + 632);
  if ( v17 )
  {
    if ( *(_DWORD *)(a1 + 128)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v18, 39, (unsigned int)WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v19, v17);
    }
    v20 = UMRxFreeSecondaryBuffer(a1);
    if ( v20
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v22 = PsGetCurrentThreadId();
      WPP_SF_qD(v21, 40, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v22, v20);
    }
  }
  if ( *(_QWORD *)(a3 + 672) )
  {
    v23 = UMRxFreeSecondaryBuffer(a1);
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v25 = PsGetCurrentThreadId();
        WPP_SF_qD(v24, 41, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v25, v23);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 7080) )
  {
    v26 = UMRxFreeSecondaryBuffer(a1);
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v28 = PsGetCurrentThreadId();
        WPP_SF_qD(v27, 42, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v28, v26);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 9168) )
  {
    v29 = UMRxFreeSecondaryBuffer(a1);
    if ( v29 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v31 = PsGetCurrentThreadId();
        WPP_SF_qD(v30, 43, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v31, v29);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 7104) )
  {
    v32 = UMRxFreeSecondaryBuffer(a1);
    if ( v32
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v34 = PsGetCurrentThreadId();
      WPP_SF_qD(v33, 44, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v34, v32);
    }
    *(_QWORD *)(a3 + 7104) = 0;
  }
  if ( !a5 )
  {
    v35 = *(_DWORD *)(a3 + 2312);
    *(_DWORD *)v12 = v35;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v36 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v37 = PsGetCurrentThreadId();
      WPP_SF_ql(v36, v38, v39, v37, v35);
    }
    *(_DWORD *)(v13 + 280) = *(_DWORD *)(a1 + 128);
  }
  UMRxFinalizeAsyncEngineContext(&v49);
  UMRxFinalizeAsyncEngineContext(&v49);
  if ( !a5 )
  {
    v40 = *(_DWORD *)(v13 + 280);
    if ( v40 >= 0
      || v40 == -1073741790
      || v40 == -1073741718
      || v40 == -1073741715
      || v40 == -1073741424
      || v40 == -1073741117
      || v40 == -1073740918
      || v40 == -1073739515
      || (v41 = *(_WORD *)(v12 + 24)) == 0
      || v41 != *(_WORD *)(v12 + 26)
      || (v42 = *(_QWORD *)(v12 + 32), (v43 = (v41 >> 1) - 1) == 0) )
    {
LABEL_63:
      (*(void (__fastcall **)(__int64))(v13 + 272))(v13);
    }
    else
    {
      while ( !*(_WORD *)(v42 + 2LL * v43) )
      {
        if ( !--v43 )
          goto LABEL_63;
      }
      while ( *(_WORD *)(v42 + 2LL * v43) == 92 )
      {
        if ( !--v43 )
          goto LABEL_63;
      }
      while ( *(_WORD *)(v42 + 2LL * v43) != 92 )
      {
        if ( !--v43 )
          goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v47 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v48 = PsGetCurrentThreadId();
        WPP_SF_qD(v47, 46, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v48, v40);
      }
      *(_WORD *)(v12 + 24) = 2 * v43;
      *(_DWORD *)(v13 + 280) = 0;
      MRxDAVSrvCallWrapper((PVOID)a2);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v44 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v45 = PsGetCurrentThreadId();
    WPP_SF_q(v44, 47, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v45);
  }
  return 0;
}

```

## disassembly

```asm
0x14001bdf0  mov     [rsp+arg_8], rbx
0x14001bdf5  mov     [rsp+arg_10], rbp
0x14001bdfa  mov     [rsp+arg_0], rcx
0x14001bdff  push    rsi
0x14001be00  push    rdi
0x14001be01  push    r13
0x14001be03  push    r14
0x14001be05  push    r15
0x14001be07  sub     rsp, 30h
0x14001be0b  mov     rsi, r8
0x14001be0e  mov     r13, rdx
0x14001be11  mov     rdi, rcx
0x14001be14  mov     rbx, cs:WPP_GLOBAL_Control
0x14001be1b  lea     rax, WPP_GLOBAL_Control
0x14001be22  cmp     rbx, rax
0x14001be25  jz      loc_14001BEAF
0x14001be2b  test    dword ptr [rbx+2Ch], 4000h
0x14001be32  jz      short loc_14001BE5B
0x14001be34  mov     rbx, [rbx+18h]
0x14001be38  call    cs:__imp_PsGetCurrentThreadId
0x14001be3f  nop     dword ptr [rax+rax+00h]
0x14001be44  mov     edx, 24h ; '$'
0x14001be49  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001be50  mov     r9, rax
0x14001be53  mov     rcx, rbx
0x14001be56  call    WPP_SF_q
0x14001be5b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001be62  lea     rax, WPP_GLOBAL_Control
0x14001be69  cmp     rbx, rax
0x14001be6c  jz      short loc_14001BEAF
0x14001be6e  test    dword ptr [rbx+2Ch], 2000h
0x14001be75  jz      short loc_14001BEA8
0x14001be77  mov     rbx, [rbx+18h]
0x14001be7b  call    cs:__imp_PsGetCurrentThreadId
0x14001be82  nop     dword ptr [rax+rax+00h]
0x14001be87  mov     edx, 25h ; '%'
0x14001be8c  mov     [rsp+58h+var_30], r13
0x14001be91  mov     r9, rax
0x14001be94  mov     [rsp+58h+var_38], rdi
0x14001be99  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bea0  mov     rcx, rbx
0x14001bea3  call    WPP_SF_qqq
0x14001bea8  lea     rax, WPP_GLOBAL_Control
0x14001beaf  xor     r14d, r14d
0x14001beb2  mov     r15d, r14d
0x14001beb5  cmp     [rsp+58h+arg_20], r14d
0x14001bebd  jnz     short loc_14001BF0B
0x14001bebf  mov     rbp, [r13+0D8h]
0x14001bec6  mov     rax, [rbp+108h]
0x14001becd  test    rax, rax
0x14001bed0  jz      short loc_14001BED6
0x14001bed2  mov     r15, [rax+20h]
0x14001bed6  mov     rcx, [r13+0E0h]
0x14001bedd  call    cs:__imp_SeDeleteClientSecurity
0x14001bee4  nop     dword ptr [rax+rax+00h]
0x14001bee9  mov     rcx, [r13+0E0h]; P
0x14001bef0  xor     edx, edx; Tag
0x14001bef2  call    cs:__imp_ExFreePoolWithTag
0x14001bef9  nop     dword ptr [rax+rax+00h]
0x14001befe  mov     [r13+0E0h], r14
0x14001bf05  mov     [r15+4], r14b
0x14001bf09  jmp     short loc_14001BF54
0x14001bf0b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bf12  mov     rbp, r14
0x14001bf15  cmp     rbx, rax
0x14001bf18  jz      short loc_14001BF5B
0x14001bf1a  test    dword ptr [rbx+2Ch], 2000h
0x14001bf21  jz      short loc_14001BF54
0x14001bf23  mov     rbx, [rbx+18h]
0x14001bf27  call    cs:__imp_PsGetCurrentThreadId
0x14001bf2e  nop     dword ptr [rax+rax+00h]
0x14001bf33  mov     edx, 26h ; '&'
0x14001bf38  mov     [rsp+58h+var_30], r13
0x14001bf3d  mov     r9, rax
0x14001bf40  mov     [rsp+58h+var_38], rdi
0x14001bf45  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bf4c  mov     rcx, rbx
0x14001bf4f  call    WPP_SF_qqq
0x14001bf54  lea     rax, WPP_GLOBAL_Control
0x14001bf5b  mov     r14, [rsi+278h]
0x14001bf62  test    r14, r14
0x14001bf65  jz      loc_14001C013
0x14001bf6b  cmp     dword ptr [rdi+80h], 0
0x14001bf72  jz      short loc_14001BFB5
0x14001bf74  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bf7b  cmp     rbx, rax
0x14001bf7e  jz      short loc_14001BFB5
0x14001bf80  test    dword ptr [rbx+2Ch], 2000h
0x14001bf87  jz      short loc_14001BFB5
0x14001bf89  mov     rbx, [rbx+18h]
0x14001bf8d  call    cs:__imp_PsGetCurrentThreadId
0x14001bf94  nop     dword ptr [rax+rax+00h]
0x14001bf99  mov     edx, 27h ; '''
0x14001bf9e  mov     [rsp+58h+var_38], r14
0x14001bfa3  mov     r9, rax
0x14001bfa6  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001bfad  mov     rcx, rbx
0x14001bfb0  call    WPP_SF_qS
0x14001bfb5  mov     rdx, [rsi+278h]
0x14001bfbc  mov     rcx, rdi
0x14001bfbf  call    UMRxFreeSecondaryBuffer
0x14001bfc4  mov     r14d, eax
0x14001bfc7  test    eax, eax
0x14001bfc9  jz      short loc_14001C013
0x14001bfcb  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bfd2  lea     rax, WPP_GLOBAL_Control
0x14001bfd9  cmp     rbx, rax
0x14001bfdc  jz      short loc_14001C013
0x14001bfde  test    dword ptr [rbx+2Ch], 2000h
0x14001bfe5  jz      short loc_14001C013
0x14001bfe7  mov     rbx, [rbx+18h]
0x14001bfeb  call    cs:__imp_PsGetCurrentThreadId
0x14001bff2  nop     dword ptr [rax+rax+00h]
0x14001bff7  mov     edx, 28h ; '('
0x14001bffc  mov     dword ptr [rsp+58h+var_38], r14d
0x14001c001  mov     r9, rax
0x14001c004  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c00b  mov     rcx, rbx
0x14001c00e  call    WPP_SF_qD
0x14001c013  mov     rdx, [rsi+2A0h]
0x14001c01a  test    rdx, rdx
0x14001c01d  jz      short loc_14001C076
0x14001c01f  mov     rcx, rdi
0x14001c022  call    UMRxFreeSecondaryBuffer
0x14001c027  mov     r14d, eax
0x14001c02a  test    eax, eax
0x14001c02c  jz      short loc_14001C076
0x14001c02e  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c035  lea     rax, WPP_GLOBAL_Control
0x14001c03c  cmp     rbx, rax
0x14001c03f  jz      short loc_14001C076
0x14001c041  test    dword ptr [rbx+2Ch], 2000h
0x14001c048  jz      short loc_14001C076
0x14001c04a  mov     rbx, [rbx+18h]
0x14001c04e  call    cs:__imp_PsGetCurrentThreadId
0x14001c055  nop     dword ptr [rax+rax+00h]
0x14001c05a  mov     edx, 29h ; ')'
0x14001c05f  mov     dword ptr [rsp+58h+var_38], r14d
0x14001c064  mov     r9, rax
0x14001c067  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c06e  mov     rcx, rbx
0x14001c071  call    WPP_SF_qD
0x14001c076  mov     rdx, [rsi+1BA8h]
0x14001c07d  test    rdx, rdx
0x14001c080  jz      short loc_14001C0D9
0x14001c082  mov     rcx, rdi
0x14001c085  call    UMRxFreeSecondaryBuffer
0x14001c08a  mov     r14d, eax
0x14001c08d  test    eax, eax
0x14001c08f  jz      short loc_14001C0D9
0x14001c091  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c098  lea     rax, WPP_GLOBAL_Control
0x14001c09f  cmp     rbx, rax
0x14001c0a2  jz      short loc_14001C0D9
0x14001c0a4  test    dword ptr [rbx+2Ch], 2000h
0x14001c0ab  jz      short loc_14001C0D9
0x14001c0ad  mov     rbx, [rbx+18h]
0x14001c0b1  call    cs:__imp_PsGetCurrentThreadId
0x14001c0b8  nop     dword ptr [rax+rax+00h]
0x14001c0bd  mov     edx, 2Ah ; '*'
0x14001c0c2  mov     dword ptr [rsp+58h+var_38], r14d
0x14001c0c7  mov     r9, rax
0x14001c0ca  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c0d1  mov     rcx, rbx
0x14001c0d4  call    WPP_SF_qD
0x14001c0d9  mov     rdx, [rsi+23D0h]
0x14001c0e0  test    rdx, rdx
0x14001c0e3  jz      short loc_14001C13C
0x14001c0e5  mov     rcx, rdi
0x14001c0e8  call    UMRxFreeSecondaryBuffer
0x14001c0ed  mov     r14d, eax
0x14001c0f0  test    eax, eax
0x14001c0f2  jz      short loc_14001C13C
0x14001c0f4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c0fb  lea     rax, WPP_GLOBAL_Control
0x14001c102  cmp     rbx, rax
0x14001c105  jz      short loc_14001C13C
0x14001c107  test    dword ptr [rbx+2Ch], 2000h
0x14001c10e  jz      short loc_14001C13C
0x14001c110  mov     rbx, [rbx+18h]
0x14001c114  call    cs:__imp_PsGetCurrentThreadId
0x14001c11b  nop     dword ptr [rax+rax+00h]
0x14001c120  mov     edx, 2Bh ; '+'
0x14001c125  mov     dword ptr [rsp+58h+var_38], r14d
0x14001c12a  mov     r9, rax
0x14001c12d  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c134  mov     rcx, rbx
0x14001c137  call    WPP_SF_qD
0x14001c13c  mov     rdx, [rsi+1BC0h]
0x14001c143  test    rdx, rdx
0x14001c146  jz      short loc_14001C1AA
0x14001c148  mov     rcx, rdi
0x14001c14b  call    UMRxFreeSecondaryBuffer
0x14001c150  mov     r14d, eax
0x14001c153  test    eax, eax
0x14001c155  jz      short loc_14001C19F
0x14001c157  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c15e  lea     rax, WPP_GLOBAL_Control
0x14001c165  cmp     rbx, rax
0x14001c168  jz      short loc_14001C19F
0x14001c16a  test    dword ptr [rbx+2Ch], 2000h
0x14001c171  jz      short loc_14001C19F
0x14001c173  mov     rbx, [rbx+18h]
0x14001c177  call    cs:__imp_PsGetCurrentThreadId
0x14001c17e  nop     dword ptr [rax+rax+00h]
0x14001c183  mov     edx, 2Ch ; ','
0x14001c188  mov     dword ptr [rsp+58h+var_38], r14d
0x14001c18d  mov     r9, rax
0x14001c190  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c197  mov     rcx, rbx
0x14001c19a  call    WPP_SF_qD
0x14001c19f  mov     qword ptr [rsi+1BC0h], 0
0x14001c1aa  cmp     [rsp+58h+arg_20], 0
0x14001c1b2  jnz     short loc_14001C206
0x14001c1b4  mov     esi, [rsi+908h]
0x14001c1ba  mov     [r15], esi
0x14001c1bd  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c1c4  lea     r14, WPP_GLOBAL_Control
0x14001c1cb  cmp     rbx, r14
0x14001c1ce  jz      short loc_14001C1F8
0x14001c1d0  test    dword ptr [rbx+2Ch], 4000h
0x14001c1d7  jz      short loc_14001C1F8
0x14001c1d9  mov     rbx, [rbx+18h]
0x14001c1dd  call    cs:__imp_PsGetCurrentThreadId
0x14001c1e4  nop     dword ptr [rax+rax+00h]
0x14001c1e9  mov     rcx, rbx
0x14001c1ec  mov     dword ptr [rsp+58h+var_38], esi
0x14001c1f0  mov     r9, rax
0x14001c1f3  call    WPP_SF_ql
0x14001c1f8  mov     eax, [rdi+80h]
0x14001c1fe  mov     [rbp+118h], eax
0x14001c204  jmp     short loc_14001C20D
0x14001c206  lea     r14, WPP_GLOBAL_Control
0x14001c20d  lea     rcx, [rsp+58h+arg_0]
0x14001c212  call    UMRxFinalizeAsyncEngineContext
0x14001c217  lea     rcx, [rsp+58h+arg_0]
0x14001c21c  call    UMRxFinalizeAsyncEngineContext
0x14001c221  xor     edx, edx
0x14001c223  cmp     [rsp+58h+arg_20], edx
0x14001c22a  jnz     loc_14001C2B4
0x14001c230  mov     esi, [rbp+118h]
0x14001c236  test    esi, esi
0x14001c238  jns     short loc_14001C2A5
0x14001c23a  cmp     esi, 0C0000022h
0x14001c240  jz      short loc_14001C2A5
0x14001c242  cmp     esi, 0C000006Ah
0x14001c248  jz      short loc_14001C2A5
0x14001c24a  cmp     esi, 0C000006Dh
0x14001c250  jz      short loc_14001C2A5
0x14001c252  cmp     esi, 0C0000190h
0x14001c258  jz      short loc_14001C2A5
0x14001c25a  cmp     esi, 0C00002C3h
0x14001c260  jz      short loc_14001C2A5
0x14001c262  cmp     esi, 0C000038Ah
0x14001c268  jz      short loc_14001C2A5
0x14001c26a  cmp     esi, 0C0000905h
0x14001c270  jz      short loc_14001C2A5
0x14001c272  movzx   edi, word ptr [r15+18h]
0x14001c277  test    di, di
0x14001c27a  jz      short loc_14001C2A5
0x14001c27c  cmp     di, [r15+1Ah]
0x14001c281  jnz     short loc_14001C2A5
0x14001c283  mov     rcx, [r15+20h]
0x14001c287  shr     di, 1
0x14001c28a  sub     di, 1
0x14001c28e  jz      short loc_14001C2A5
0x14001c290  mov     r8d, 0FFFFh
0x14001c296  movzx   eax, di
0x14001c299  cmp     [rcx+rax*2], dx
0x14001c29d  jnz     short loc_14001C30A
0x14001c29f  add     di, r8w
0x14001c2a3  jnz     short loc_14001C296
0x14001c2a5  mov     rax, [rbp+110h]
0x14001c2ac  mov     rcx, rbp
0x14001c2af  call    _guard_dispatch_icall
0x14001c2b4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c2bb  cmp     rbx, r14
0x14001c2be  jz      short loc_14001C2F0
0x14001c2c0  test    dword ptr [rbx+2Ch], 4000h
0x14001c2c7  jz      short loc_14001C2F0
0x14001c2c9  mov     rbx, [rbx+18h]
0x14001c2cd  call    cs:__imp_PsGetCurrentThreadId
0x14001c2d4  nop     dword ptr [rax+rax+00h]
0x14001c2d9  mov     edx, 2Fh ; '/'
0x14001c2de  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c2e5  mov     r9, rax
0x14001c2e8  mov     rcx, rbx
0x14001c2eb  call    WPP_SF_q
0x14001c2f0  mov     rbx, [rsp+58h+arg_8]
0x14001c2f5  xor     eax, eax
0x14001c2f7  mov     rbp, [rsp+58h+arg_10]
0x14001c2fc  add     rsp, 30h
0x14001c300  pop     r15
0x14001c302  pop     r14
0x14001c304  pop     r13
0x14001c306  pop     rdi
0x14001c307  pop     rsi
0x14001c308  retn
0x14001c30a  movzx   eax, di
0x14001c30d  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
  ... truncated ...
```

# MRxDAVFormatUserModeSrvCallCreateRequest

- ea: `0x14001b360`
- end: `0x14001bc1d`
- name: `MRxDAVFormatUserModeSrvCallCreateRequest`
- size: `2237`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x1400019bc`
- `0x140001b64`
- `0x140006900`
- `0x14000f0cc`
- `0x14001b360`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b3a2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b3ed`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b4b0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b510`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b595`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b5ee`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b672`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b70f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b8fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b9d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ba1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bac0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bb68`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bba5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bbe5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b3a2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b3ed`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b4b0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b510`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b595`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b5ee`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b672`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b70f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b8fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b9d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ba1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bac0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bb68`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bba5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001bbe5`
- `ntoskrnl!SeTokenIsRestricted` at `0x14001b45f`
- `ntoskrnl!SeTokenIsRestricted` at `0x14001b45f`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14001b47d`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14001b47d`
- `rdbss!RxFindEa` at `0x14001b849`
- `rdbss!RxFindEa` at `0x14001b891`
- `rdbss!RxFindEa` at `0x14001b943`
- `rdbss!RxFindEa` at `0x14001b972`
- `rdbss!RxFindEa` at `0x14001ba5a`
- `rdbss!RxFindEa` at `0x14001b849`
- `rdbss!RxFindEa` at `0x14001b891`
- `rdbss!RxFindEa` at `0x14001b943`
- `rdbss!RxFindEa` at `0x14001b972`
- `rdbss!RxFindEa` at `0x14001ba5a`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeSrvCallCreateRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  void *v13; // rbx
  NTSTATUS AuthenticationIdToken; // r14d
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rdx
  struct _SECURITY_CLIENT_CONTEXT *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  wchar_t *SecondaryBuffer; // rax
  __int64 v22; // rbx
  HANDLE v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rdi
  unsigned int v27; // eax
  __int64 v28; // rax
  PVOID v29; // rax
  unsigned int i; // ebx
  __int64 v31; // rdx
  _QWORD *v32; // rbx
  unsigned int v33; // r9d
  unsigned __int16 *v34; // rdx
  unsigned int v35; // ecx
  const void **v36; // rdx
  unsigned __int64 v37; // rax
  unsigned __int16 *v38; // rdx
  __int64 v39; // rdx
  __int64 Ea; // rax
  int v41; // ecx
  __int64 v42; // rax
  __int64 v43; // rbx
  unsigned int v44; // eax
  PVOID v45; // rax
  __int64 v46; // rax
  __int64 v47; // rbx
  unsigned int v48; // eax
  PVOID v49; // rax
  __int64 v50; // rbx
  HANDLE v51; // rax
  __int64 v52; // rax
  __int64 v53; // rbx
  unsigned int v54; // eax
  PVOID v55; // rax
  int v56; // eax
  __int64 v57; // rbx
  HANDLE v58; // rax
  __int64 v59; // rbx
  HANDLE v60; // rax
  __int64 v61; // rbx
  HANDLE v62; // rax
  __int64 v64; // [rsp+38h] [rbp-50h]
  __int64 v65; // [rsp+40h] [rbp-48h]
  size_t cbDesta; // [rsp+98h] [rbp+10h]
  int cbDestb; // [rsp+98h] [rbp+10h]
  __int64 v70; // [rsp+A0h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v6, 21, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v9 = PsGetCurrentThreadId();
    WPP_SF_qqq(v8, 22, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v9, a1, a2);
  }
  v10 = *(_QWORD *)(a2 + 216);
  v65 = v10;
  v11 = *(_QWORD *)(v10 + 264);
  v64 = v11;
  if ( v11 )
    v70 = *(_QWORD *)(v11 + 32);
  else
    v70 = 0;
  v12 = *(_QWORD *)(v10 + 40);
  v13 = *(void **)v12;
  if ( !*(_QWORD *)v12 )
    v13 = *(void **)(v12 + 16);
  if ( SeTokenIsRestricted(v13) )
  {
    AuthenticationIdToken = -1073741790;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v59 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v60 = PsGetCurrentThreadId();
      WPP_SF_qD(v59, 24, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v60, -1073741790);
    }
    goto LABEL_93;
  }
  AuthenticationIdToken = SeQueryAuthenticationIdToken(v13, (PLUID)(a3 + 640));
  if ( AuthenticationIdToken )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      v17 = 23;
LABEL_17:
      WPP_SF_qD(v15, v17, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v16, AuthenticationIdToken);
      goto LABEL_93;
    }
    goto LABEL_93;
  }
  v18 = *(struct _SECURITY_CLIENT_CONTEXT **)(a2 + 224);
  if ( !v18 )
  {
    AuthenticationIdToken = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v57 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v58 = PsGetCurrentThreadId();
      WPP_SF_q(v57, 26, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v58);
    }
    goto LABEL_93;
  }
  AuthenticationIdToken = UMRxImpersonateClient(v18);
  if ( AuthenticationIdToken >= 0 )
  {
    *(_DWORD *)(a3 + 48) = 4;
    *(_QWORD *)(a3 + 632) = 0;
    v19 = *(_QWORD *)(*(_QWORD *)(v64 + 64) + 8LL);
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v19 + 2 * v20 + 2) );
    cbDesta = (unsigned int)(2 * v20 + 2);
    SecondaryBuffer = (wchar_t *)UMRxAllocateSecondaryBuffer(a1, (unsigned int)cbDesta);
    if ( !SecondaryBuffer )
    {
      AuthenticationIdToken = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_93;
      v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v23 = PsGetCurrentThreadId();
      v24 = 27;
      goto LABEL_29;
    }
    *(_QWORD *)(a3 + 632) = SecondaryBuffer;
    StringCbCopyW(SecondaryBuffer, cbDesta, (STRSAFE_LPCWSTR)(v19 + 2));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v25 = *(_QWORD *)(a3 + 632);
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v27 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v26, 28, (unsigned int)WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v27, v25);
      v10 = v65;
    }
    v28 = *(unsigned __int16 *)(v70 + 24);
    if ( (_WORD)v28 )
    {
      v29 = UMRxAllocateSecondaryBuffer(a1, v28 + 2);
      *(_QWORD *)(a3 + 672) = v29;
      if ( !v29 )
      {
        AuthenticationIdToken = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_93;
        }
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = PsGetCurrentThreadId();
        v24 = 29;
        goto LABEL_29;
      }
      for ( i = 0; i < *(unsigned __int16 *)(v70 + 24) >> 1; ++i )
      {
        v31 = *(unsigned __int16 *)(*(_QWORD *)(v70 + 32) + 2LL * i);
        if ( (_WORD)v31 == 92 )
          v31 = 47;
        RtlWriteUShortToUser(*(_QWORD *)(a3 + 672) + 2LL * i, v31);
      }
      RtlWriteUShortToUser(*(_QWORD *)(a3 + 672) + 2LL * i, 0);
    }
    else
    {
      *(_QWORD *)(a3 + 672) = 0;
    }
    v32 = *(_QWORD **)(v10 + 112);
    if ( v32 )
    {
      v33 = 0;
      v34 = (unsigned __int16 *)v32[4];
      if ( v34 && *v34 && (*v34 & 0xFFFEu) < 0x400 )
      {
        memmove((void *)(a3 + 5536), *((const void **)v34 + 1), *v34);
        v35 = *(unsigned __int16 *)v32[4] >> 1;
        *(_WORD *)(a3 + 2LL * v35 + 5536) = 92;
        v33 = v35 + 1;
      }
      v36 = (const void **)v32[2];
      if ( v36 )
      {
        v37 = *(unsigned __int16 *)v36;
        if ( (_WORD)v37 )
        {
          if ( v33 + (v37 >> 1) < 0x201 )
            memmove((void *)(a3 + 2 * (v33 + 2768LL)), v36[1], *(unsigned __int16 *)v36);
        }
      }
      v38 = (unsigned __int16 *)v32[3];
      v32 = 0;
      if ( v38 && *v38 && (*v38 & 0xFFFEu) < 0x200 )
        memmove((void *)(a3 + 6562), *((const void **)v38 + 1), *v38);
    }
    v39 = *(unsigned int *)(v10 + 72);
    if ( (_DWORD)v39 )
    {
      Ea = RxFindEa(*(_QWORD *)(v10 + 64), v39, "Https:", 7);
      v41 = (int)v32;
      LOBYTE(v41) = Ea != 0;
      cbDestb = v41;
      *(_QWORD *)(a3 + 7088) = 0;
      *(_QWORD *)(a3 + 7080) = v32;
      *(_QWORD *)(a3 + 9168) = v32;
      v42 = RxFindEa(*(_QWORD *)(v10 + 64), *(unsigned int *)(v10 + 72), "Client-Cert", 11);
      v43 = v42;
      if ( v42 )
      {
        *(_DWORD *)(a3 + 7088) = *(unsigned __int16 *)(v42 + 6);
        v44 = *(unsigned __int16 *)(v42 + 6);
        if ( (_WORD)v44 )
        {
          v45 = UMRxAllocateSecondaryBuffer(a1, v44);
          if ( !v45 )
          {
            AuthenticationIdToken = -1073741670;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
            {
              goto LABEL_93;
            }
            v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v23 = PsGetCurrentThreadId();
            v24 = 31;
            goto LABEL_29;
          }
          *(_QWORD *)(a3 + 7080) = v45;
          memmove(v45, (const void *)(v43 + *(unsigned __int8 *)(v43 + 5) + 9LL), *(unsigned __int16 *)(v43 + 6));
        }
      }
      else if ( RxFindEa(*(_QWORD *)(v10 + 64), *(unsigned int *)(v10 + 72), "NoClient-Cert", 15) )
      {
        *(_DWORD *)(a3 + 7092) = 1;
      }
      v46 = RxFindEa(*(_QWORD *)(v10 + 64), *(unsigned int *)(v10 + 72), "Pin", 3);
      v47 = v46;
      if ( v46 )
      {
        v48 = *(unsigned __int16 *)(v46 + 6);
        if ( (_WORD)v48 )
        {
          v49 = UMRxAllocateSecondaryBuffer(a1, v48);
          if ( !v49 )
          {
            AuthenticationIdToken = -1073741670;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
            {
              goto LABEL_93;
            }
            v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v23 = PsGetCurrentThreadId();
            v24 = 32;
            goto LABEL_29;
          }
          *(_QWORD *)(a3 + 9168) = v49;
          memmove(v49, (const void *)(v47 + 9 + *(unsigned __int8 *)(v47 + 5)), *(unsigned __int16 *)(v47 + 6));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v50 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v51 = PsGetCurrentThreadId();
            WPP_SF_q(v50, 33, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v51);
          }
        }
      }
      *(_QWORD *)(a3 + 7104) = 0;
      *(_DWORD *)(a3 + 7112) = 0;
      v52 = RxFindEa(*(_QWORD *)(v10 + 64), *(unsigned int *)(v10 + 72), "Cookie:", 7);
      v53 = v52;
      if ( v52 )
      {
        *(_DWORD *)(a3 + 7112) = *(unsigned __int16 *)(v52 + 6);
        v54 = *(unsigned __int16 *)(v52 + 6);
        if ( (_WORD)v54 )
        {
          v55 = UMRxAllocateSecondaryBuffer(a1, v54);
          if ( !v55 )
          {
            AuthenticationIdToken = -1073741670;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
            {
              goto LABEL_93;
            }
            v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v23 = PsGetCurrentThreadId();
            v24 = 34;
LABEL_29:
            WPP_SF_qD(v22, v24, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v23, -1073741670);
            goto LABEL_93;
          }
          *(_QWORD *)(a3 + 7104) = v55;
          memmove(v55, (const void *)(v53 + *(unsigned __int8 *)(v53 + 5) + 9LL), *(unsigned __int16 *)(v53 + 6));
        }
      }
      v56 = cbDestb;
    }
    else
    {
      *(_QWORD *)(a3 + 7080) = v32;
      *(_QWORD *)(a3 + 7088) = 0;
      *(_QWORD *)(a3 + 7104) = v32;
      *(_DWORD *)(a3 + 7112) = (_DWORD)v32;
      *(_QWORD *)(a3 + 9168) = v32;
      v56 = (int)v32;
    }
    *(_DWORD *)(a3 + 7096) = v56;
    *(_QWORD *)(a3 + 648) = *(_QWORD *)(v70 + 8);
    *(_QWORD *)(a3 + 656) = *(_QWORD *)(v70 + 16);
    goto LABEL_93;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = PsGetCurrentThreadId();
    v17 = 25;
    goto LABEL_17;
  }
LABEL_93:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v61 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v62 = PsGetCurrentThreadId();
    WPP_SF_qD(v61, 35, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v62, AuthenticationIdToken);
  }
  return (unsigned int)AuthenticationIdToken;
}

```

## disassembly

```asm
0x14001b360  mov     [rsp+cbDest], rdx
0x14001b365  mov     [rsp+arg_0], rcx
0x14001b36a  push    rbx
0x14001b36b  push    rsi
0x14001b36c  push    rdi
0x14001b36d  push    r12
0x14001b36f  push    r13
0x14001b371  push    r14
0x14001b373  push    r15
0x14001b375  sub     rsp, 50h
0x14001b379  mov     rsi, r8
0x14001b37c  mov     rdi, rdx
0x14001b37f  mov     r14, rcx
0x14001b382  lea     r12, WPP_GLOBAL_Control
0x14001b389  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b390  cmp     rbx, r12
0x14001b393  jz      short loc_14001B3CA
0x14001b395  test    dword ptr [rbx+2Ch], 4000h
0x14001b39c  jz      short loc_14001B3CA
0x14001b39e  mov     rbx, [rbx+18h]
0x14001b3a2  call    cs:__imp_PsGetCurrentThreadId
0x14001b3a9  nop     dword ptr [rax+rax+00h]
0x14001b3ae  mov     r9, rax
0x14001b3b1  mov     edx, 15h
0x14001b3b6  lea     r15, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b3bd  mov     r8, r15
0x14001b3c0  mov     rcx, rbx
0x14001b3c3  call    WPP_SF_q
0x14001b3c8  jmp     short loc_14001B3D1
0x14001b3ca  lea     r15, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b3d1  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b3d8  mov     r13d, 2000h
0x14001b3de  cmp     rbx, r12
0x14001b3e1  jz      short loc_14001B416
0x14001b3e3  test    [rbx+2Ch], r13d
0x14001b3e7  jz      short loc_14001B416
0x14001b3e9  mov     rbx, [rbx+18h]
0x14001b3ed  call    cs:__imp_PsGetCurrentThreadId
0x14001b3f4  nop     dword ptr [rax+rax+00h]
0x14001b3f9  mov     r9, rax
0x14001b3fc  mov     edx, 16h
0x14001b401  mov     [rsp+88h+var_60], rdi
0x14001b406  mov     [rsp+88h+var_68], r14
0x14001b40b  mov     r8, r15
0x14001b40e  mov     rcx, rbx
0x14001b411  call    WPP_SF_qqq
0x14001b416  mov     rdi, [rdi+0D8h]
0x14001b41d  mov     [rsp+88h+var_48], rdi
0x14001b422  mov     rax, [rdi+108h]
0x14001b429  mov     [rsp+88h+var_50], rax
0x14001b42e  xor     r14d, r14d
0x14001b431  test    rax, rax
0x14001b434  jnz     short loc_14001B440
0x14001b436  mov     [rsp+88h+arg_10], r14
0x14001b43e  jmp     short loc_14001B44C
0x14001b440  mov     rax, [rax+20h]
0x14001b444  mov     [rsp+88h+arg_10], rax
0x14001b44c  mov     rax, [rdi+28h]
0x14001b450  mov     rbx, [rax]
0x14001b453  test    rbx, rbx
0x14001b456  jnz     short loc_14001B45C
0x14001b458  mov     rbx, [rax+10h]
0x14001b45c  mov     rcx, rbx; Token
0x14001b45f  call    cs:__imp_SeTokenIsRestricted
0x14001b466  nop     dword ptr [rax+rax+00h]
0x14001b46b  test    al, al
0x14001b46d  jnz     loc_14001BB89
0x14001b473  lea     rdx, [rsi+280h]; AuthenticationId
0x14001b47a  mov     rcx, rbx; Token
0x14001b47d  call    cs:__imp_SeQueryAuthenticationIdToken
0x14001b484  nop     dword ptr [rax+rax+00h]
0x14001b489  mov     r14d, eax
0x14001b48c  xor     ebx, ebx
0x14001b48e  test    eax, eax
0x14001b490  jz      short loc_14001B4CB
0x14001b492  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b499  cmp     rbx, r12
0x14001b49c  jz      loc_14001BBCC
0x14001b4a2  test    [rbx+2Ch], r13d
0x14001b4a6  jz      loc_14001BBCC
0x14001b4ac  mov     rbx, [rbx+18h]
0x14001b4b0  call    cs:__imp_PsGetCurrentThreadId
0x14001b4b7  nop     dword ptr [rax+rax+00h]
0x14001b4bc  mov     edx, 17h
0x14001b4c1  mov     dword ptr [rsp+88h+var_68], r14d
0x14001b4c6  jmp     loc_14001BBBE
0x14001b4cb  mov     rax, [rsp+88h+cbDest]
0x14001b4d3  mov     rcx, [rax+0E0h]; ClientContext
0x14001b4da  test    rcx, rcx
0x14001b4dd  jz      loc_14001BB4C
0x14001b4e3  mov     rdx, rsi
0x14001b4e6  call    UMRxImpersonateClient
0x14001b4eb  mov     r14d, eax
0x14001b4ee  test    eax, eax
0x14001b4f0  jns     short loc_14001B523
0x14001b4f2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b4f9  cmp     rbx, r12
0x14001b4fc  jz      loc_14001BBCC
0x14001b502  test    [rbx+2Ch], r13d
0x14001b506  jz      loc_14001BBCC
0x14001b50c  mov     rbx, [rbx+18h]
0x14001b510  call    cs:__imp_PsGetCurrentThreadId
0x14001b517  nop     dword ptr [rax+rax+00h]
0x14001b51c  mov     edx, 19h
0x14001b521  jmp     short loc_14001B4C1
0x14001b523  mov     dword ptr [rsi+30h], 4
0x14001b52a  mov     [rsi+278h], rbx
0x14001b531  mov     rax, [rsp+88h+var_50]
0x14001b536  mov     rax, [rax+40h]
0x14001b53a  mov     rbx, [rax+8]
0x14001b53e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b542  xor     ecx, ecx
0x14001b544  inc     rax
0x14001b547  cmp     [rbx+rax*2+2], cx
0x14001b54c  jnz     short loc_14001B544
0x14001b54e  lea     eax, ds:2[rax*2]
0x14001b555  mov     [rsp+88h+cbDest], rax
0x14001b55d  mov     edx, eax
0x14001b55f  mov     rcx, [rsp+88h+arg_0]
0x14001b567  call    UMRxAllocateSecondaryBuffer
0x14001b56c  test    rax, rax
0x14001b56f  jnz     short loc_14001B5B3
0x14001b571  mov     r14d, 0C000009Ah
0x14001b577  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b57e  cmp     rbx, r12
0x14001b581  jz      loc_14001BBCC
0x14001b587  test    [rbx+2Ch], r13d
0x14001b58b  jz      loc_14001BBCC
0x14001b591  mov     rbx, [rbx+18h]
0x14001b595  call    cs:__imp_PsGetCurrentThreadId
0x14001b59c  nop     dword ptr [rax+rax+00h]
0x14001b5a1  mov     edx, 1Bh
0x14001b5a6  mov     dword ptr [rsp+88h+var_68], 0C000009Ah
0x14001b5ae  jmp     loc_14001BBBE
0x14001b5b3  mov     [rsi+278h], rax
0x14001b5ba  lea     r8, [rbx+2]; pszSrc
0x14001b5be  mov     rdx, [rsp+88h+cbDest]; cbDest
0x14001b5c6  mov     rcx, rax; pszDest
0x14001b5c9  call    StringCbCopyW
0x14001b5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5d5  cmp     rcx, r12
0x14001b5d8  jz      short loc_14001B617
0x14001b5da  test    dword ptr [rcx+2Ch], 4000h
0x14001b5e1  jz      short loc_14001B617
0x14001b5e3  mov     rbx, [rsi+278h]
0x14001b5ea  mov     rdi, [rcx+18h]
0x14001b5ee  call    cs:__imp_PsGetCurrentThreadId
0x14001b5f5  nop     dword ptr [rax+rax+00h]
0x14001b5fa  mov     r9, rax
0x14001b5fd  mov     edx, 1Ch
0x14001b602  mov     [rsp+88h+var_68], rbx
0x14001b607  mov     r8, r15
0x14001b60a  mov     rcx, rdi
0x14001b60d  call    WPP_SF_qS
0x14001b612  mov     rdi, [rsp+88h+var_48]
0x14001b617  mov     rax, [rsp+88h+arg_10]
0x14001b61f  movzx   eax, word ptr [rax+18h]
0x14001b623  xor     r10d, r10d
0x14001b626  test    ax, ax
0x14001b629  jz      loc_14001B74A
0x14001b62f  lea     rdx, [rax+2]
0x14001b633  mov     rcx, [rsp+88h+arg_0]
0x14001b63b  call    UMRxAllocateSecondaryBuffer
0x14001b640  mov     [rsi+2A0h], rax
0x14001b647  xor     ecx, ecx
0x14001b649  test    rax, rax
0x14001b64c  jnz     short loc_14001B688
0x14001b64e  mov     r14d, 0C000009Ah
0x14001b654  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b65b  cmp     rbx, r12
0x14001b65e  jz      loc_14001BBCC
0x14001b664  test    [rbx+2Ch], r13d
0x14001b668  jz      loc_14001BBCC
0x14001b66e  mov     rbx, [rbx+18h]
0x14001b672  call    cs:__imp_PsGetCurrentThreadId
0x14001b679  nop     dword ptr [rax+rax+00h]
0x14001b67e  mov     edx, 1Dh
0x14001b683  jmp     loc_14001B5A6
0x14001b688  mov     ebx, ecx
0x14001b68a  mov     [rsp+88h+var_58], ecx
0x14001b68e  mov     r9d, 5Ch ; '\'
0x14001b694  mov     r8d, ebx
0x14001b697  mov     rdx, [rsp+88h+arg_10]
0x14001b69f  movzx   eax, word ptr [rdx+18h]
0x14001b6a3  shr     eax, 1
0x14001b6a5  cmp     ebx, eax
0x14001b6a7  jnb     short loc_14001B6D5
0x14001b6a9  mov     ecx, ebx
0x14001b6ab  mov     rax, [rdx+20h]
0x14001b6af  movzx   edx, word ptr [rax+rcx*2]
0x14001b6b3  cmp     dx, r9w
0x14001b6b7  jnz     short loc_14001B6BD
0x14001b6b9  lea     edx, [r9-2Dh]
0x14001b6bd  mov     rax, [rsi+2A0h]
0x14001b6c4  lea     rcx, [rax+r8*2]
0x14001b6c8  call    RtlWriteUShortToUser
0x14001b6cd  inc     ebx
0x14001b6cf  mov     [rsp+88h+var_58], ebx
0x14001b6d3  jmp     short loc_14001B68E
0x14001b6d5  xor     edx, edx
0x14001b6d7  mov     rax, [rsi+2A0h]
0x14001b6de  lea     rcx, [rax+r8*2]
0x14001b6e2  call    RtlWriteUShortToUser
0x14001b6e7  xor     r10d, r10d
0x14001b6ea  jmp     short loc_14001B751
0x14001b6ec  mov     r14d, eax
0x14001b6ef  lea     rax, WPP_GLOBAL_Control
0x14001b6f6  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b6fd  cmp     rbx, rax
0x14001b700  jz      short loc_14001B737
0x14001b702  test    dword ptr [rbx+2Ch], 2000h
0x14001b709  jz      short loc_14001B737
0x14001b70b  mov     rbx, [rbx+18h]
0x14001b70f  call    cs:__imp_PsGetCurrentThreadId
0x14001b716  nop     dword ptr [rax+rax+00h]
0x14001b71b  mov     r9, rax
0x14001b71e  mov     edx, 1Eh
0x14001b723  mov     dword ptr [rsp+88h+var_68], r14d
0x14001b728  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b72f  mov     rcx, rbx
0x14001b732  call    WPP_SF_qD
0x14001b737  lea     r12, WPP_GLOBAL_Control
0x14001b73e  lea     r15, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b745  jmp     loc_14001BBCC
0x14001b74a  mov     [rsi+2A0h], r10
0x14001b751  mov     rbx, [rdi+70h]
0x14001b755  test    rbx, rbx
0x14001b758  jz      loc_14001B82D
0x14001b75e  mov     r9d, r10d
0x14001b761  mov     rdx, [rbx+20h]
0x14001b765  test    rdx, rdx
0x14001b768  jz      short loc_14001B7B5
0x14001b76a  movzx   ecx, word ptr [rdx]
0x14001b76d  test    cx, cx
0x14001b770  jz      short loc_14001B7B5
0x14001b772  movzx   eax, cx
0x14001b775  mov     r8d, 0FFFEh
0x14001b77b  and     ax, r8w
0x14001b77f  mov     r8d, 400h
0x14001b785  cmp     ax, r8w
0x14001b789  jnb     short loc_14001B7B5
0x14001b78b  mov     r8d, ecx; Size
0x14001b78e  lea     rcx, [rsi+15A0h]; void *
0x14001b795  mov     rdx, [rdx+8]; Src
0x14001b799  call    memmove
0x14001b79e  mov     rax, [rbx+20h]
0x14001b7a2  movzx   ecx, word ptr [rax]
0x14001b7a5  shr     ecx, 1
0x14001b7a7  mov     word ptr [rsi+rcx*2+15A0h], 5Ch ; '\'
0x14001b7b1  lea     r9d, [rcx+1]
0x14001b7b5  mov     rdx, [rbx+10h]
0x14001b7b9  test    rdx, rdx
0x14001b7bc  jz      short loc_14001B7EE
0x14001b7be  movzx   eax, word ptr [rdx]
0x14001b7c1  test    ax, ax
0x14001b7c4  jz      short loc_14001B7EE
0x14001b7c6  mov     ecx, r9d
0x14001b7c9  mov     r8d, eax; Size
0x14001b7cc  shr     rax, 1
0x14001b7cf  add     rax, rcx
0x14001b7d2  cmp     rax, 201h
0x14001b7d8  jnb     short loc_14001B7EE
0x14001b7da  add     rcx, 0AD0h
0x14001b7e1  lea     rcx, [rsi+rcx*2]; void *
0x14001b7e5  mov     rdx, [rdx+8]; Src
0x14001b7e9  call    memmove
0x14001b7ee  mov     rdx, [rbx+18h]
0x14001b7f2  xor     ebx, ebx
0x14001b7f4  test    rdx, rdx
0x14001b7f7  jz      short loc_14001B82D
0x14001b7f9  movzx   ecx, word ptr [rdx]
0x14001b7fc  test    cx, cx
0x14001b7ff  jz      short loc_14001B82D
0x14001b801  movzx   eax, cx
0x14001b804  mov     r8d, 0FFFEh
0x14001b80a  and     ax, r8w
0x14001b80e  mov     r8d, 200h
0x14001b814  cmp     ax, r8w
0x14001b818  jnb     short loc_14001B82D
0x14001b81a  mov     r8d, ecx; Size
0x14001b81d  lea     rcx, [rsi+19A2h]; void *
0x14001b824  mov     rdx, [rdx+8]; Src
0x14001b828  call    memmove
0x14001b82d  mov     edx, [rdi+48h]
0x14001b830  test    edx, edx
0x14001b832  jz      loc_14001BAFB
0x14001b838  mov     r9d, 7
0x14001b83e  lea     r8, aHttps; "Https:"
0x14001b845  mov     rcx, [rdi+40h]
0x14001b849  call    cs:__imp_RxFindEa
0x14001b850  nop     dword ptr [rax+rax+00h]
0x14001b855  mov     ecx, ebx
0x14001b857  test    rax, rax
0x14001b85a  setnz   cl
0x14001b85d  mov     dword ptr [rsp+88h+cbDest], ecx
0x14001b864  mov     qword ptr [rsi+1BB0h], 0
0x14001b86f  mov     [rsi+1BA8h], rbx
0x14001b876  mov     [rsi+23D0h], rbx
0x14001b87d  mov     r9d, 0Bh
0x14001b883  lea     r8, aClientCert; "Client-Cert"
  ... truncated ...
```

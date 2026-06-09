# NlpAddResourceGroupsToSamInfo(_NETLOGON_VALIDATION_INFO_CLASS,_NETLOGON_VALIDATION_SAM_INFO4 * *,_SAMPR_PSID_ARRAY *)

- ea: `0x180053728`
- end: `0x180054029`
- name: `?NlpAddResourceGroupsToSamInfo@@YAJW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAMPR_PSID_ARRAY@@@Z`
- size: `2305`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180031a3c`
- `0x180053684`
- `0x1800548a0`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000f3e4`
- `0x180016a70`
- `0x180016aa4`
- `0x180041e90`
- `0x180053728`
- `0x18008a5c0`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053b0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053fd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053b0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053fd7`
- `ntdll!RtlLengthSid` at `0x18005378d`
- `ntdll!RtlLengthSid` at `0x1800537df`
- `ntdll!RtlLengthSid` at `0x18005381e`
- `ntdll!RtlLengthSid` at `0x180053c2d`
- `ntdll!RtlLengthSid` at `0x180053ca3`
- `ntdll!RtlLengthSid` at `0x180053d14`
- `ntdll!RtlLengthSid` at `0x180053d40`
- `ntdll!RtlLengthSid` at `0x18005378d`
- `ntdll!RtlLengthSid` at `0x1800537df`
- `ntdll!RtlLengthSid` at `0x18005381e`
- `ntdll!RtlLengthSid` at `0x180053c2d`
- `ntdll!RtlLengthSid` at `0x180053ca3`
- `ntdll!RtlLengthSid` at `0x180053d14`
- `ntdll!RtlLengthSid` at `0x180053d40`

## string_xrefs

- `0x180053cf1`: `onecore\ds\netapi\svcdlls\logonsrv\server\rgroups.cxx`
- `0x180053cf8`: `GroupIndex == ExtraSids`

## pseudocode

```c
__int64 __fastcall NlpAddResourceGroupsToSamInfo(int a1, unsigned __int8 *a2, __int64 a3)
{
  __int64 v3; // rsi
  int v4; // r15d
  unsigned __int8 *v6; // r13
  unsigned __int64 v7; // rax
  unsigned int v8; // edi
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  unsigned int i; // edi
  ULONG v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  __int64 v16; // r15
  ULONG v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // eax
  unsigned int v20; // ecx
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // eax
  unsigned int v26; // ecx
  int v27; // eax
  unsigned int v28; // ecx
  int v29; // eax
  unsigned int v30; // ecx
  int v31; // eax
  unsigned int v32; // ecx
  int v33; // eax
  unsigned int v34; // ecx
  int v35; // eax
  unsigned int v36; // ecx
  int v37; // eax
  unsigned int v38; // ecx
  struct _UNICODE_STRING *v39; // rax
  struct _UNICODE_STRING *v40; // r15
  __int64 v41; // rax
  _BYTE *v42; // rcx
  __int64 v43; // rax
  _BYTE *v44; // rcx
  __int64 result; // rax
  struct _UNICODE_STRING *v46; // rcx
  __int64 v47; // rdx
  struct _UNICODE_STRING v48; // xmm1
  char *v49; // r9
  __int64 v50; // rbx
  unsigned int v51; // r13d
  char *v52; // r14
  __int64 v53; // rdi
  size_t v54; // rbx
  unsigned int v55; // r12d
  unsigned int *v56; // rsi
  __int64 v57; // rcx
  size_t v58; // rbx
  ULONG v59; // eax
  __int64 v60; // rax
  _BYTE *v61; // rcx
  __int64 v62; // rax
  _BYTE *v63; // rcx
  unsigned int v64; // [rsp+20h] [rbp-18h]
  __int64 v65; // [rsp+28h] [rbp-10h]
  unsigned __int8 *v67; // [rsp+88h] [rbp+50h] BYREF
  unsigned int *v68; // [rsp+90h] [rbp+58h]
  size_t size; // [rsp+98h] [rbp+60h] BYREF

  v68 = (unsigned int *)a3;
  v67 = a2;
  v3 = *(_QWORD *)a2;
  v4 = a1;
  v65 = *(_QWORD *)a2;
  v6 = a2;
  v7 = 8LL * *(unsigned int *)(*(_QWORD *)a2 + 156LL);
  if ( v7 > 0xFFFFFFFF )
  {
    v9 = 447;
    goto LABEL_77;
  }
  v8 = v7 + 480;
  if ( (int)v7 + 480 < (unsigned int)v7 )
  {
    v9 = 453;
LABEL_77:
    NlPrintRoutine(0x100u, L"NlpAddResourceGroupsToSamInfo: Integer overflow in length calculation at line %d\n", v9);
    return 3221225621LL;
  }
  v10 = RtlLengthSid(*(PSID *)(v3 + 224)) + v8;
  if ( v10 < v8 )
  {
    v9 = 459;
    goto LABEL_77;
  }
  v11 = 0;
  LODWORD(size) = v10;
  v64 = 0;
  if ( v4 != 2 && (*(_BYTE *)(v3 + 168) & 0x20) != 0 )
  {
    v11 = *(_DWORD *)(v3 + 272);
    v64 = v11;
    if ( v11 )
    {
      for ( i = 0; i < v11; ++i )
      {
        v13 = RtlLengthSid(*(PSID *)(*(_QWORD *)(v3 + 280) + 16LL * i));
        v11 = *(_DWORD *)(v3 + 272);
        v10 += v13 + 16;
        v64 = v11;
      }
      LODWORD(size) = v10;
    }
  }
  v14 = v10;
  if ( a3 )
  {
    v15 = *(_DWORD *)a3;
    if ( *(_DWORD *)a3 )
    {
      v16 = 0;
      do
      {
        v17 = RtlLengthSid(*(PSID *)(*(_QWORD *)(a3 + 8) + 8 * v16));
        v16 = (unsigned int)(v16 + 1);
        v10 = v17 + v14 + 16;
        v15 = *(_DWORD *)a3;
        LODWORD(size) = v10;
        v14 = v10;
      }
      while ( (unsigned int)v16 < v15 );
      v4 = a1;
    }
    v11 += v15;
    v64 = v11;
  }
  if ( (int)NetpULongRoundUp(v10, 2u, (unsigned int *)&size) < 0
    || (v18 = *(unsigned __int16 *)(v3 + 80)
            + 16
            + *(unsigned __int16 *)(v3 + 96)
            + *(unsigned __int16 *)(v3 + 208)
            + *(unsigned __int16 *)(v3 + 48)
            + *(unsigned __int16 *)(v3 + 112)
            + *(unsigned __int16 *)(v3 + 64)
            + *(unsigned __int16 *)(v3 + 128)
            + size
            + *(unsigned __int16 *)(v3 + 192),
        v18 < (unsigned int)size) )
  {
    v9 = 501;
    goto LABEL_77;
  }
  LODWORD(size) = *(unsigned __int16 *)(v3 + 80)
                + 16
                + *(unsigned __int16 *)(v3 + 96)
                + *(unsigned __int16 *)(v3 + 208)
                + *(unsigned __int16 *)(v3 + 48)
                + *(unsigned __int16 *)(v3 + 112)
                + *(unsigned __int16 *)(v3 + 64)
                + *(unsigned __int16 *)(v3 + 128)
                + size
                + *(unsigned __int16 *)(v3 + 192);
  if ( v4 == 6 )
  {
    v19 = v18 + *(unsigned __int16 *)(v3 + 304);
    v20 = v19 + *(unsigned __int16 *)(v3 + 288) + 4;
    if ( v20 < v18 )
      goto LABEL_44;
    LODWORD(size) = v19 + *(unsigned __int16 *)(v3 + 288) + 4;
    if ( (int)NetpULongRoundUp(v20, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v21 = *(unsigned __int16 *)(v3 + 320);
    v22 = v21 + size + 2;
    if ( v22 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v21 + size + 2;
    if ( (int)NetpULongRoundUp(v22, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v23 = *(unsigned __int16 *)(v3 + 336);
    v24 = v23 + size + 2;
    if ( v24 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v23 + size + 2;
    if ( (int)NetpULongRoundUp(v24, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v25 = *(unsigned __int16 *)(v3 + 352);
    v26 = v25 + size + 2;
    if ( v26 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v25 + size + 2;
    if ( (int)NetpULongRoundUp(v26, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v27 = *(unsigned __int16 *)(v3 + 368);
    v28 = v27 + size + 2;
    if ( v28 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v27 + size + 2;
    if ( (int)NetpULongRoundUp(v28, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v29 = *(unsigned __int16 *)(v3 + 384);
    v30 = v29 + size + 2;
    if ( v30 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v29 + size + 2;
    if ( (int)NetpULongRoundUp(v30, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v31 = *(unsigned __int16 *)(v3 + 400);
    v32 = v31 + size + 2;
    if ( v32 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v31 + size + 2;
    if ( (int)NetpULongRoundUp(v32, 2u, (unsigned int *)&size) < 0 )
      goto LABEL_44;
    v33 = *(unsigned __int16 *)(v3 + 416);
    v34 = v33 + size + 2;
    if ( v34 < (unsigned int)size )
      goto LABEL_44;
    LODWORD(size) = v33 + size + 2;
    if ( (int)NetpULongRoundUp(v34, 2u, (unsigned int *)&size) < 0
      || (v35 = *(unsigned __int16 *)(v3 + 432), v36 = v35 + size + 2, v36 < (unsigned int)size)
      || (LODWORD(size) = v35 + size + 2, (int)NetpULongRoundUp(v36, 2u, (unsigned int *)&size) < 0)
      || (v37 = *(unsigned __int16 *)(v3 + 448), v38 = v37 + size + 2, v38 < (unsigned int)size)
      || (LODWORD(size) = v37 + size + 2, (int)NetpULongRoundUp(v38, 2u, (unsigned int *)&size) < 0)
      || (v18 = *(unsigned __int16 *)(v3 + 464) + size + 2, v18 < (unsigned int)size) )
    {
LABEL_44:
      v9 = 546;
      goto LABEL_77;
    }
    LODWORD(size) = *(unsigned __int16 *)(v3 + 464) + size + 2;
  }
  if ( (int)NetpULongRoundUp(v18, 2u, (unsigned int *)&size) < 0 )
  {
    v9 = 552;
    goto LABEL_77;
  }
  v39 = (struct _UNICODE_STRING *)MIDL_user_allocate((unsigned int)size);
  v40 = v39;
  if ( v39 )
  {
    v46 = (struct _UNICODE_STRING *)v3;
    v47 = 2;
    do
    {
      *v39 = *v46;
      v39[1] = v46[1];
      v39[2] = v46[2];
      v39[3] = v46[3];
      v39[4] = v46[4];
      v39[5] = v46[5];
      v39[6] = v46[6];
      v48 = v46[7];
      v46 += 8;
      v39[7] = v48;
      v39 += 8;
      --v47;
    }
    while ( v47 );
    *v39 = *v46;
    memset_0(&v40[17], 0, 0xD0u);
    memcpy_0(&v40[30], *(const void **)(v3 + 160), 8LL * *(unsigned int *)(v3 + 156));
    *(_QWORD *)&v40[10].Length = v40 + 30;
    v50 = (__int64)&v40[30] + 8 * *(unsigned int *)(v3 + 156);
    if ( v11 )
    {
      v51 = 0;
      v52 = (char *)(v50 + 16LL * v11);
      v40[17].Buffer = (PWSTR)v50;
      v50 = (__int64)v52;
      if ( a1 != 2 && (*(_BYTE *)(v3 + 168) & 0x20) != 0 && *(_DWORD *)(v3 + 272) )
      {
        do
        {
          v53 = 2LL * v51;
          *(_DWORD *)&v40[17].Buffer[4 * v53 + 4] = *(_DWORD *)(*(_QWORD *)(v3 + 280) + 16LL * v51 + 8);
          *(_QWORD *)&v40[17].Buffer[4 * v53] = v50;
          v54 = RtlLengthSid(*(PSID *)(*(_QWORD *)(v3 + 280) + 16LL * v51));
          memcpy_0(v52, *(const void **)(*(_QWORD *)(v3 + 280) + 16LL * v51), v54);
          v50 = (__int64)&v52[v54];
          ++v51;
          v52 = (char *)v50;
        }
        while ( v51 < *(_DWORD *)(v3 + 272) );
      }
      if ( v68 && *v68 )
      {
        v55 = 0;
        v56 = v68;
        do
        {
          v57 = 2LL * v51;
          *(_DWORD *)&v40[17].Buffer[4 * v57 + 4] = 536870919;
          *(_QWORD *)&v40[17].Buffer[4 * v57] = v50;
          v58 = RtlLengthSid(*(PSID *)(*((_QWORD *)v56 + 1) + 8LL * v55));
          memcpy_0(v52, *(const void **)(*((_QWORD *)v56 + 1) + 8LL * v55), v58);
          v50 = (__int64)&v52[v58];
          ++v51;
          ++v55;
          v52 = (char *)v50;
        }
        while ( v55 < *v56 );
        v3 = v65;
        v11 = v64;
      }
      *(_DWORD *)&v40[17].Length = v51;
      if ( v51 != v11 )
        NlAssertFailed(
          "GroupIndex == ExtraSids",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\rgroups.cxx",
          0x290u,
          v49);
      v6 = v67;
    }
    else
    {
      v52 = (char *)&v40[30] + 8 * *(unsigned int *)(v3 + 156);
    }
    v59 = RtlLengthSid(*(PSID *)(v3 + 224));
    memcpy_0(v52, *(const void **)(v3 + 224), v59);
    *(_QWORD *)&v40[14].Length = v50;
    v67 = (unsigned __int8 *)&v52[RtlLengthSid(*(PSID *)(v3 + 224))];
    NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
    NlpPutString(v40 + 3, (PCUNICODE_STRING)(v3 + 48), &v67);
    NlpPutString(v40 + 4, (PCUNICODE_STRING)(v3 + 64), &v67);
    NlpPutString(v40 + 5, (PCUNICODE_STRING)(v3 + 80), &v67);
    NlpPutString(v40 + 6, (PCUNICODE_STRING)(v3 + 96), &v67);
    NlpPutString(v40 + 7, (PCUNICODE_STRING)(v3 + 112), &v67);
    NlpPutString(v40 + 8, (PCUNICODE_STRING)(v3 + 128), &v67);
    NlpPutString(v40 + 12, (PCUNICODE_STRING)(v3 + 192), &v67);
    NlpPutString(v40 + 13, (PCUNICODE_STRING)(v3 + 208), &v67);
    if ( a1 == 6 )
    {
      NlpPutString(v40 + 18, (PCUNICODE_STRING)(v3 + 288), &v67);
      NlpPutString(v40 + 19, (PCUNICODE_STRING)(v3 + 304), &v67);
      NlpPutString(v40 + 20, (PCUNICODE_STRING)(v3 + 320), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 21, (PCUNICODE_STRING)(v3 + 336), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 22, (PCUNICODE_STRING)(v3 + 352), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 23, (PCUNICODE_STRING)(v3 + 368), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 24, (PCUNICODE_STRING)(v3 + 384), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 25, (PCUNICODE_STRING)(v3 + 400), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 26, (PCUNICODE_STRING)(v3 + 416), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 27, (PCUNICODE_STRING)(v3 + 432), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 28, (PCUNICODE_STRING)(v3 + 448), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2u, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 29, (PCUNICODE_STRING)(v3 + 464), &v67);
    }
    v60 = 16;
    v61 = (_BYTE *)(v3 + 172);
    do
    {
      *v61++ = 0;
      --v60;
    }
    while ( v60 );
    v62 = 40;
    v63 = (_BYTE *)(v3 + 232);
    do
    {
      *v63++ = 0;
      --v62;
    }
    while ( v62 );
    free((void *)v3);
    result = 0;
    *(_QWORD *)v6 = v40;
  }
  else
  {
    v41 = 16;
    v42 = (_BYTE *)(v3 + 172);
    do
    {
      *v42++ = 0;
      --v41;
    }
    while ( v41 );
    v43 = 40;
    v44 = (_BYTE *)(v3 + 232);
    do
    {
      *v44++ = 0;
      --v43;
    }
    while ( v43 );
    free((void *)v3);
    result = 3221225626LL;
    *(_QWORD *)v6 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180053728  mov     [rsp-40h+arg_10], r8
0x18005372d  mov     [rsp-40h+arg_8], rdx
0x180053732  mov     [rsp-40h+arg_0], ecx
0x180053736  push    rbp
0x180053737  push    rbx
0x180053738  push    rsi
0x180053739  push    rdi
0x18005373a  push    r12
0x18005373c  push    r13
0x18005373e  push    r14
0x180053740  push    r15
0x180053742  mov     rbp, rsp
0x180053745  sub     rsp, 38h
0x180053749  mov     rsi, [rdx]
0x18005374c  mov     r15d, ecx
0x18005374f  mov     ecx, 0FFFFFFFFh
0x180053754  mov     [rbp+var_10], rsi
0x180053758  mov     r14, r8
0x18005375b  mov     r13, rdx
0x18005375e  mov     eax, [rsi+9Ch]
0x180053764  shl     rax, 3
0x180053768  cmp     rax, rcx
0x18005376b  ja      loc_180053FFB
0x180053771  lea     edi, [rax+1E0h]
0x180053777  cmp     edi, eax
0x180053779  jnb     short loc_180053786
0x18005377b  mov     r8d, 1C5h
0x180053781  jmp     loc_180054001
0x180053786  mov     rcx, [rsi+0E0h]; Sid
0x18005378d  call    cs:__imp_RtlLengthSid
0x180053794  nop     dword ptr [rax+rax+00h]
0x180053799  lea     ebx, [rax+rdi]
0x18005379c  cmp     ebx, edi
0x18005379e  jb      loc_180053FF3
0x1800537a4  xor     r12d, r12d
0x1800537a7  mov     dword ptr [rbp+size], ebx
0x1800537aa  mov     [rbp+var_18], r12d
0x1800537ae  cmp     r15d, 2
0x1800537b2  jz      short loc_180053805
0x1800537b4  test    byte ptr [rsi+0A8h], 20h
0x1800537bb  jz      short loc_180053805
0x1800537bd  mov     r12d, [rsi+110h]
0x1800537c4  mov     [rbp+var_18], r12d
0x1800537c8  test    r12d, r12d
0x1800537cb  jz      short loc_180053805
0x1800537cd  xor     edi, edi
0x1800537cf  mov     rcx, [rsi+118h]
0x1800537d6  mov     eax, edi
0x1800537d8  add     rax, rax
0x1800537db  mov     rcx, [rcx+rax*8]; Sid
0x1800537df  call    cs:__imp_RtlLengthSid
0x1800537e6  nop     dword ptr [rax+rax+00h]
0x1800537eb  mov     r12d, [rsi+110h]
0x1800537f2  add     ebx, 10h
0x1800537f5  add     ebx, eax
0x1800537f7  mov     [rbp+var_18], r12d
0x1800537fb  inc     edi
0x1800537fd  cmp     edi, r12d
0x180053800  jb      short loc_1800537CF
0x180053802  mov     dword ptr [rbp+size], ebx
0x180053805  mov     edi, ebx
0x180053807  test    r14, r14
0x18005380a  jz      short loc_18005384A
0x18005380c  mov     eax, [r14]
0x18005380f  test    eax, eax
0x180053811  jz      short loc_180053843
0x180053813  xor     r15d, r15d
0x180053816  mov     rcx, [r14+8]
0x18005381a  mov     rcx, [rcx+r15*8]; Sid
0x18005381e  call    cs:__imp_RtlLengthSid
0x180053825  nop     dword ptr [rax+rax+00h]
0x18005382a  lea     ebx, [rdi+10h]
0x18005382d  inc     r15d
0x180053830  add     ebx, eax
0x180053832  mov     eax, [r14]
0x180053835  mov     dword ptr [rbp+size], ebx
0x180053838  mov     edi, ebx
0x18005383a  cmp     r15d, eax
0x18005383d  jb      short loc_180053816
0x18005383f  mov     r15d, [rbp+arg_0]
0x180053843  add     r12d, eax
0x180053846  mov     [rbp+var_18], r12d
0x18005384a  mov     r14d, 2
0x180053850  lea     r8, [rbp+size]; unsigned int *
0x180053854  mov     edx, r14d; unsigned int
0x180053857  mov     ecx, ebx; unsigned int
0x180053859  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005385e  xor     edi, edi
0x180053860  test    eax, eax
0x180053862  js      loc_180053FEB
0x180053868  movzx   eax, word ptr [rsi+40h]
0x18005386c  movzx   edx, word ptr [rsi+80h]
0x180053873  movzx   r9d, word ptr [rsi+0C0h]
0x18005387b  add     edx, eax
0x18005387d  add     r9d, dword ptr [rbp+size]
0x180053881  movzx   eax, word ptr [rsi+70h]
0x180053885  add     edx, eax
0x180053887  movzx   eax, word ptr [rsi+30h]
0x18005388b  add     edx, eax
0x18005388d  movzx   eax, word ptr [rsi+0D0h]
0x180053894  add     edx, eax
0x180053896  movzx   eax, word ptr [rsi+60h]
0x18005389a  add     edx, eax
0x18005389c  movzx   eax, word ptr [rsi+50h]
0x1800538a0  add     eax, 10h
0x1800538a3  add     r9d, edx
0x1800538a6  add     r9d, eax
0x1800538a9  cmp     r9d, dword ptr [rbp+size]
0x1800538ad  jb      loc_180053FEB
0x1800538b3  mov     dword ptr [rbp+size], r9d
0x1800538b7  cmp     r15d, 6
0x1800538bb  jnz     loc_180053A9F
0x1800538c1  movzx   eax, word ptr [rsi+130h]
0x1800538c8  movzx   ecx, word ptr [rsi+120h]
0x1800538cf  add     eax, r9d
0x1800538d2  add     ecx, 4
0x1800538d5  add     ecx, eax; unsigned int
0x1800538d7  cmp     ecx, r9d
0x1800538da  jb      loc_180053ABD
0x1800538e0  lea     r8, [rbp+size]; unsigned int *
0x1800538e4  mov     dword ptr [rbp+size], ecx
0x1800538e7  mov     edx, r14d; unsigned int
0x1800538ea  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800538ef  test    eax, eax
0x1800538f1  js      loc_180053ABD
0x1800538f7  mov     edx, dword ptr [rbp+size]
0x1800538fa  movzx   eax, word ptr [rsi+140h]
0x180053901  lea     ecx, [rdx+2]
0x180053904  add     ecx, eax; unsigned int
0x180053906  cmp     ecx, edx
0x180053908  jb      loc_180053ABD
0x18005390e  lea     r8, [rbp+size]; unsigned int *
0x180053912  mov     dword ptr [rbp+size], ecx
0x180053915  mov     edx, r14d; unsigned int
0x180053918  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005391d  test    eax, eax
0x18005391f  js      loc_180053ABD
0x180053925  mov     edx, dword ptr [rbp+size]
0x180053928  movzx   eax, word ptr [rsi+150h]
0x18005392f  lea     ecx, [rdx+2]
0x180053932  add     ecx, eax; unsigned int
0x180053934  cmp     ecx, edx
0x180053936  jb      loc_180053ABD
0x18005393c  lea     r8, [rbp+size]; unsigned int *
0x180053940  mov     dword ptr [rbp+size], ecx
0x180053943  mov     edx, r14d; unsigned int
0x180053946  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005394b  test    eax, eax
0x18005394d  js      loc_180053ABD
0x180053953  mov     edx, dword ptr [rbp+size]
0x180053956  movzx   eax, word ptr [rsi+160h]
0x18005395d  lea     ecx, [rdx+2]
0x180053960  add     ecx, eax; unsigned int
0x180053962  cmp     ecx, edx
0x180053964  jb      loc_180053ABD
0x18005396a  lea     r8, [rbp+size]; unsigned int *
0x18005396e  mov     dword ptr [rbp+size], ecx
0x180053971  mov     edx, r14d; unsigned int
0x180053974  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053979  test    eax, eax
0x18005397b  js      loc_180053ABD
0x180053981  mov     edx, dword ptr [rbp+size]
0x180053984  movzx   eax, word ptr [rsi+170h]
0x18005398b  lea     ecx, [rdx+2]
0x18005398e  add     ecx, eax; unsigned int
0x180053990  cmp     ecx, edx
0x180053992  jb      loc_180053ABD
0x180053998  lea     r8, [rbp+size]; unsigned int *
0x18005399c  mov     dword ptr [rbp+size], ecx
0x18005399f  mov     edx, r14d; unsigned int
0x1800539a2  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800539a7  test    eax, eax
0x1800539a9  js      loc_180053ABD
0x1800539af  mov     edx, dword ptr [rbp+size]
0x1800539b2  movzx   eax, word ptr [rsi+180h]
0x1800539b9  lea     ecx, [rdx+2]
0x1800539bc  add     ecx, eax; unsigned int
0x1800539be  cmp     ecx, edx
0x1800539c0  jb      loc_180053ABD
0x1800539c6  lea     r8, [rbp+size]; unsigned int *
0x1800539ca  mov     dword ptr [rbp+size], ecx
0x1800539cd  mov     edx, r14d; unsigned int
0x1800539d0  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800539d5  test    eax, eax
0x1800539d7  js      loc_180053ABD
0x1800539dd  mov     edx, dword ptr [rbp+size]
0x1800539e0  movzx   eax, word ptr [rsi+190h]
0x1800539e7  lea     ecx, [rdx+2]
0x1800539ea  add     ecx, eax; unsigned int
0x1800539ec  cmp     ecx, edx
0x1800539ee  jb      loc_180053ABD
0x1800539f4  lea     r8, [rbp+size]; unsigned int *
0x1800539f8  mov     dword ptr [rbp+size], ecx
0x1800539fb  mov     edx, r14d; unsigned int
0x1800539fe  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053a03  test    eax, eax
0x180053a05  js      loc_180053ABD
0x180053a0b  mov     edx, dword ptr [rbp+size]
0x180053a0e  movzx   eax, word ptr [rsi+1A0h]
0x180053a15  lea     ecx, [rdx+2]
0x180053a18  add     ecx, eax; unsigned int
0x180053a1a  cmp     ecx, edx
0x180053a1c  jb      loc_180053ABD
0x180053a22  lea     r8, [rbp+size]; unsigned int *
0x180053a26  mov     dword ptr [rbp+size], ecx
0x180053a29  mov     edx, r14d; unsigned int
0x180053a2c  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053a31  test    eax, eax
0x180053a33  js      loc_180053ABD
0x180053a39  mov     edx, dword ptr [rbp+size]
0x180053a3c  movzx   eax, word ptr [rsi+1B0h]
0x180053a43  lea     ecx, [rdx+2]
0x180053a46  add     ecx, eax; unsigned int
0x180053a48  cmp     ecx, edx
0x180053a4a  jb      short loc_180053ABD
0x180053a4c  lea     r8, [rbp+size]; unsigned int *
0x180053a50  mov     dword ptr [rbp+size], ecx
0x180053a53  mov     edx, r14d; unsigned int
0x180053a56  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053a5b  test    eax, eax
0x180053a5d  js      short loc_180053ABD
0x180053a5f  mov     edx, dword ptr [rbp+size]
0x180053a62  movzx   eax, word ptr [rsi+1C0h]
0x180053a69  lea     ecx, [rdx+2]
0x180053a6c  add     ecx, eax; unsigned int
0x180053a6e  cmp     ecx, edx
0x180053a70  jb      short loc_180053ABD
0x180053a72  lea     r8, [rbp+size]; unsigned int *
0x180053a76  mov     dword ptr [rbp+size], ecx
0x180053a79  mov     edx, r14d; unsigned int
0x180053a7c  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053a81  test    eax, eax
0x180053a83  js      short loc_180053ABD
0x180053a85  mov     ecx, dword ptr [rbp+size]
0x180053a88  movzx   eax, word ptr [rsi+1D0h]
0x180053a8f  lea     r9d, [rcx+2]
0x180053a93  add     r9d, eax
0x180053a96  cmp     r9d, ecx
0x180053a99  jb      short loc_180053ABD
0x180053a9b  mov     dword ptr [rbp+size], r9d
0x180053a9f  lea     r8, [rbp+size]; unsigned int *
0x180053aa3  mov     edx, r14d; unsigned int
0x180053aa6  mov     ecx, r9d; unsigned int
0x180053aa9  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180053aae  test    eax, eax
0x180053ab0  jns     short loc_180053AC8
0x180053ab2  mov     r8d, 228h
0x180053ab8  jmp     loc_180054001
0x180053abd  mov     r8d, 222h
0x180053ac3  jmp     loc_180054001
0x180053ac8  mov     ecx, dword ptr [rbp+size]; size
0x180053acb  call    MIDL_user_allocate
0x180053ad0  mov     r15, rax
0x180053ad3  test    rax, rax
0x180053ad6  jnz     short loc_180053B24
0x180053ad8  lea     eax, [r15+10h]
0x180053adc  lea     rcx, [rsi+0ACh]
0x180053ae3  mov     [rcx], dil
0x180053ae6  inc     rcx
0x180053ae9  sub     rax, 1
0x180053aed  jnz     short loc_180053AE3
0x180053aef  mov     eax, 28h ; '('
0x180053af4  lea     rcx, [rsi+0E8h]
0x180053afb  mov     [rcx], dil
0x180053afe  inc     rcx
0x180053b01  sub     rax, 1
0x180053b05  jnz     short loc_180053AFB
0x180053b07  mov     rcx, rsi; Block
0x180053b0a  call    cs:__imp_free
0x180053b11  nop     dword ptr [rax+rax+00h]
0x180053b16  mov     eax, 0C000009Ah
0x180053b1b  mov     [r13+0], rdi
0x180053b1f  jmp     loc_180054017
0x180053b24  mov     rcx, rsi
0x180053b27  mov     rdx, r14
0x180053b2a  mov     r8d, 80h
0x180053b30  movups  xmm0, xmmword ptr [rcx]
0x180053b33  movups  xmmword ptr [rax], xmm0
0x180053b36  movups  xmm1, xmmword ptr [rcx+10h]
0x180053b3a  movups  xmmword ptr [rax+10h], xmm1
0x180053b3e  movups  xmm0, xmmword ptr [rcx+20h]
0x180053b42  movups  xmmword ptr [rax+20h], xmm0
0x180053b46  movups  xmm1, xmmword ptr [rcx+30h]
0x180053b4a  movups  xmmword ptr [rax+30h], xmm1
0x180053b4e  movups  xmm0, xmmword ptr [rcx+40h]
0x180053b52  movups  xmmword ptr [rax+40h], xmm0
0x180053b56  movups  xmm1, xmmword ptr [rcx+50h]
0x180053b5a  movups  xmmword ptr [rax+50h], xmm1
0x180053b5e  movups  xmm0, xmmword ptr [rcx+60h]
0x180053b62  movups  xmmword ptr [rax+60h], xmm0
0x180053b66  movups  xmm1, xmmword ptr [rcx+70h]
0x180053b6a  add     rcx, r8
0x180053b6d  movups  xmmword ptr [rax+70h], xmm1
0x180053b71  add     rax, r8
0x180053b74  sub     rdx, 1; Val
0x180053b78  jnz     short loc_180053B30
0x180053b7a  movups  xmm0, xmmword ptr [rcx]
0x180053b7d  lea     rcx, [r15+110h]; void *
0x180053b84  mov     r8d, 0D0h; Size
0x180053b8a  movups  xmmword ptr [rax], xmm0
  ... truncated ...
```

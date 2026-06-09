# NlpAddResourceGroupsToSamInfo(_NETLOGON_VALIDATION_INFO_CLASS,_NETLOGON_VALIDATION_SAM_INFO4 * *,_SAMPR_PSID_ARRAY *)

- ea: `0x18004ffd8`
- end: `0x1800508a2`
- name: `?NlpAddResourceGroupsToSamInfo@@YAJW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAMPR_PSID_ARRAY@@@Z`
- size: `2250`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002fdb4`
- `0x18004ff38`
- `0x180051050`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000ed34`
- `0x18001606c`
- `0x1800160a0`
- `0x18003f564`
- `0x18004ffd8`
- `0x1800844d0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800503a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050857`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800503a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050857`
- `ntdll!RtlLengthSid` at `0x18005003d`
- `ntdll!RtlLengthSid` at `0x180050089`
- `ntdll!RtlLengthSid` at `0x1800500c2`
- `ntdll!RtlLengthSid` at `0x1800504c5`
- `ntdll!RtlLengthSid` at `0x180050535`
- `ntdll!RtlLengthSid` at `0x1800505a0`
- `ntdll!RtlLengthSid` at `0x1800505c6`
- `ntdll!RtlLengthSid` at `0x18005003d`
- `ntdll!RtlLengthSid` at `0x180050089`
- `ntdll!RtlLengthSid` at `0x1800500c2`
- `ntdll!RtlLengthSid` at `0x1800504c5`
- `ntdll!RtlLengthSid` at `0x180050535`
- `ntdll!RtlLengthSid` at `0x1800505a0`
- `ntdll!RtlLengthSid` at `0x1800505c6`

## string_xrefs

- `0x18005057d`: `onecore\ds\netapi\svcdlls\logonsrv\server\rgroups.cxx`
- `0x180050584`: `GroupIndex == ExtraSids`

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
          656,
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
    NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
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
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 21, (PCUNICODE_STRING)(v3 + 336), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 22, (PCUNICODE_STRING)(v3 + 352), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 23, (PCUNICODE_STRING)(v3 + 368), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 24, (PCUNICODE_STRING)(v3 + 384), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 25, (PCUNICODE_STRING)(v3 + 400), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 26, (PCUNICODE_STRING)(v3 + 416), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 27, (PCUNICODE_STRING)(v3 + 432), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
      NlpPutString(v40 + 28, (PCUNICODE_STRING)(v3 + 448), &v67);
      NetpULongPtrRoundUp((unsigned __int64)v67, 2, (unsigned __int64 *)&v67);
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
0x18004ffd8  mov     [rsp-40h+arg_10], r8
0x18004ffdd  mov     [rsp-40h+arg_8], rdx
0x18004ffe2  mov     [rsp-40h+arg_0], ecx
0x18004ffe6  push    rbp
0x18004ffe7  push    rbx
0x18004ffe8  push    rsi
0x18004ffe9  push    rdi
0x18004ffea  push    r12
0x18004ffec  push    r13
0x18004ffee  push    r14
0x18004fff0  push    r15
0x18004fff2  mov     rbp, rsp
0x18004fff5  sub     rsp, 38h
0x18004fff9  mov     rsi, [rdx]
0x18004fffc  mov     r15d, ecx
0x18004ffff  mov     ecx, 0FFFFFFFFh
0x180050004  mov     [rbp+var_10], rsi
0x180050008  mov     r14, r8
0x18005000b  mov     r13, rdx
0x18005000e  mov     eax, [rsi+9Ch]
0x180050014  shl     rax, 3
0x180050018  cmp     rax, rcx
0x18005001b  ja      loc_180050875
0x180050021  lea     edi, [rax+1E0h]
0x180050027  cmp     edi, eax
0x180050029  jnb     short loc_180050036
0x18005002b  mov     r8d, 1C5h
0x180050031  jmp     loc_18005087B
0x180050036  mov     rcx, [rsi+0E0h]; Sid
0x18005003d  call    cs:__imp_RtlLengthSid
0x180050043  lea     ebx, [rax+rdi]
0x180050046  cmp     ebx, edi
0x180050048  jb      loc_18005086D
0x18005004e  xor     r12d, r12d
0x180050051  mov     dword ptr [rbp+size], ebx
0x180050054  mov     [rbp+var_18], r12d
0x180050058  cmp     r15d, 2
0x18005005c  jz      short loc_1800500A9
0x18005005e  test    byte ptr [rsi+0A8h], 20h
0x180050065  jz      short loc_1800500A9
0x180050067  mov     r12d, [rsi+110h]
0x18005006e  mov     [rbp+var_18], r12d
0x180050072  test    r12d, r12d
0x180050075  jz      short loc_1800500A9
0x180050077  xor     edi, edi
0x180050079  mov     rcx, [rsi+118h]
0x180050080  mov     eax, edi
0x180050082  add     rax, rax
0x180050085  mov     rcx, [rcx+rax*8]; Sid
0x180050089  call    cs:__imp_RtlLengthSid
0x18005008f  mov     r12d, [rsi+110h]
0x180050096  add     ebx, 10h
0x180050099  add     ebx, eax
0x18005009b  mov     [rbp+var_18], r12d
0x18005009f  inc     edi
0x1800500a1  cmp     edi, r12d
0x1800500a4  jb      short loc_180050079
0x1800500a6  mov     dword ptr [rbp+size], ebx
0x1800500a9  mov     edi, ebx
0x1800500ab  test    r14, r14
0x1800500ae  jz      short loc_1800500E8
0x1800500b0  mov     eax, [r14]
0x1800500b3  test    eax, eax
0x1800500b5  jz      short loc_1800500E1
0x1800500b7  xor     r15d, r15d
0x1800500ba  mov     rcx, [r14+8]
0x1800500be  mov     rcx, [rcx+r15*8]; Sid
0x1800500c2  call    cs:__imp_RtlLengthSid
0x1800500c8  lea     ebx, [rdi+10h]
0x1800500cb  inc     r15d
0x1800500ce  add     ebx, eax
0x1800500d0  mov     eax, [r14]
0x1800500d3  mov     dword ptr [rbp+size], ebx
0x1800500d6  mov     edi, ebx
0x1800500d8  cmp     r15d, eax
0x1800500db  jb      short loc_1800500BA
0x1800500dd  mov     r15d, [rbp+arg_0]
0x1800500e1  add     r12d, eax
0x1800500e4  mov     [rbp+var_18], r12d
0x1800500e8  mov     r14d, 2
0x1800500ee  lea     r8, [rbp+size]; unsigned int *
0x1800500f2  mov     edx, r14d; unsigned int
0x1800500f5  mov     ecx, ebx; unsigned int
0x1800500f7  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800500fc  xor     edi, edi
0x1800500fe  test    eax, eax
0x180050100  js      loc_180050865
0x180050106  movzx   eax, word ptr [rsi+40h]
0x18005010a  movzx   edx, word ptr [rsi+80h]
0x180050111  movzx   r9d, word ptr [rsi+0C0h]
0x180050119  add     edx, eax
0x18005011b  add     r9d, dword ptr [rbp+size]
0x18005011f  movzx   eax, word ptr [rsi+70h]
0x180050123  add     edx, eax
0x180050125  movzx   eax, word ptr [rsi+30h]
0x180050129  add     edx, eax
0x18005012b  movzx   eax, word ptr [rsi+0D0h]
0x180050132  add     edx, eax
0x180050134  movzx   eax, word ptr [rsi+60h]
0x180050138  add     edx, eax
0x18005013a  movzx   eax, word ptr [rsi+50h]
0x18005013e  add     eax, 10h
0x180050141  add     r9d, edx
0x180050144  add     r9d, eax
0x180050147  cmp     r9d, dword ptr [rbp+size]
0x18005014b  jb      loc_180050865
0x180050151  mov     dword ptr [rbp+size], r9d
0x180050155  cmp     r15d, 6
0x180050159  jnz     loc_18005033D
0x18005015f  movzx   eax, word ptr [rsi+130h]
0x180050166  movzx   ecx, word ptr [rsi+120h]
0x18005016d  add     eax, r9d
0x180050170  add     ecx, 4
0x180050173  add     ecx, eax; unsigned int
0x180050175  cmp     ecx, r9d
0x180050178  jb      loc_18005035B
0x18005017e  lea     r8, [rbp+size]; unsigned int *
0x180050182  mov     dword ptr [rbp+size], ecx
0x180050185  mov     edx, r14d; unsigned int
0x180050188  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005018d  test    eax, eax
0x18005018f  js      loc_18005035B
0x180050195  mov     edx, dword ptr [rbp+size]
0x180050198  movzx   eax, word ptr [rsi+140h]
0x18005019f  lea     ecx, [rdx+2]
0x1800501a2  add     ecx, eax; unsigned int
0x1800501a4  cmp     ecx, edx
0x1800501a6  jb      loc_18005035B
0x1800501ac  lea     r8, [rbp+size]; unsigned int *
0x1800501b0  mov     dword ptr [rbp+size], ecx
0x1800501b3  mov     edx, r14d; unsigned int
0x1800501b6  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800501bb  test    eax, eax
0x1800501bd  js      loc_18005035B
0x1800501c3  mov     edx, dword ptr [rbp+size]
0x1800501c6  movzx   eax, word ptr [rsi+150h]
0x1800501cd  lea     ecx, [rdx+2]
0x1800501d0  add     ecx, eax; unsigned int
0x1800501d2  cmp     ecx, edx
0x1800501d4  jb      loc_18005035B
0x1800501da  lea     r8, [rbp+size]; unsigned int *
0x1800501de  mov     dword ptr [rbp+size], ecx
0x1800501e1  mov     edx, r14d; unsigned int
0x1800501e4  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800501e9  test    eax, eax
0x1800501eb  js      loc_18005035B
0x1800501f1  mov     edx, dword ptr [rbp+size]
0x1800501f4  movzx   eax, word ptr [rsi+160h]
0x1800501fb  lea     ecx, [rdx+2]
0x1800501fe  add     ecx, eax; unsigned int
0x180050200  cmp     ecx, edx
0x180050202  jb      loc_18005035B
0x180050208  lea     r8, [rbp+size]; unsigned int *
0x18005020c  mov     dword ptr [rbp+size], ecx
0x18005020f  mov     edx, r14d; unsigned int
0x180050212  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180050217  test    eax, eax
0x180050219  js      loc_18005035B
0x18005021f  mov     edx, dword ptr [rbp+size]
0x180050222  movzx   eax, word ptr [rsi+170h]
0x180050229  lea     ecx, [rdx+2]
0x18005022c  add     ecx, eax; unsigned int
0x18005022e  cmp     ecx, edx
0x180050230  jb      loc_18005035B
0x180050236  lea     r8, [rbp+size]; unsigned int *
0x18005023a  mov     dword ptr [rbp+size], ecx
0x18005023d  mov     edx, r14d; unsigned int
0x180050240  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180050245  test    eax, eax
0x180050247  js      loc_18005035B
0x18005024d  mov     edx, dword ptr [rbp+size]
0x180050250  movzx   eax, word ptr [rsi+180h]
0x180050257  lea     ecx, [rdx+2]
0x18005025a  add     ecx, eax; unsigned int
0x18005025c  cmp     ecx, edx
0x18005025e  jb      loc_18005035B
0x180050264  lea     r8, [rbp+size]; unsigned int *
0x180050268  mov     dword ptr [rbp+size], ecx
0x18005026b  mov     edx, r14d; unsigned int
0x18005026e  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180050273  test    eax, eax
0x180050275  js      loc_18005035B
0x18005027b  mov     edx, dword ptr [rbp+size]
0x18005027e  movzx   eax, word ptr [rsi+190h]
0x180050285  lea     ecx, [rdx+2]
0x180050288  add     ecx, eax; unsigned int
0x18005028a  cmp     ecx, edx
0x18005028c  jb      loc_18005035B
0x180050292  lea     r8, [rbp+size]; unsigned int *
0x180050296  mov     dword ptr [rbp+size], ecx
0x180050299  mov     edx, r14d; unsigned int
0x18005029c  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800502a1  test    eax, eax
0x1800502a3  js      loc_18005035B
0x1800502a9  mov     edx, dword ptr [rbp+size]
0x1800502ac  movzx   eax, word ptr [rsi+1A0h]
0x1800502b3  lea     ecx, [rdx+2]
0x1800502b6  add     ecx, eax; unsigned int
0x1800502b8  cmp     ecx, edx
0x1800502ba  jb      loc_18005035B
0x1800502c0  lea     r8, [rbp+size]; unsigned int *
0x1800502c4  mov     dword ptr [rbp+size], ecx
0x1800502c7  mov     edx, r14d; unsigned int
0x1800502ca  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800502cf  test    eax, eax
0x1800502d1  js      loc_18005035B
0x1800502d7  mov     edx, dword ptr [rbp+size]
0x1800502da  movzx   eax, word ptr [rsi+1B0h]
0x1800502e1  lea     ecx, [rdx+2]
0x1800502e4  add     ecx, eax; unsigned int
0x1800502e6  cmp     ecx, edx
0x1800502e8  jb      short loc_18005035B
0x1800502ea  lea     r8, [rbp+size]; unsigned int *
0x1800502ee  mov     dword ptr [rbp+size], ecx
0x1800502f1  mov     edx, r14d; unsigned int
0x1800502f4  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x1800502f9  test    eax, eax
0x1800502fb  js      short loc_18005035B
0x1800502fd  mov     edx, dword ptr [rbp+size]
0x180050300  movzx   eax, word ptr [rsi+1C0h]
0x180050307  lea     ecx, [rdx+2]
0x18005030a  add     ecx, eax; unsigned int
0x18005030c  cmp     ecx, edx
0x18005030e  jb      short loc_18005035B
0x180050310  lea     r8, [rbp+size]; unsigned int *
0x180050314  mov     dword ptr [rbp+size], ecx
0x180050317  mov     edx, r14d; unsigned int
0x18005031a  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005031f  test    eax, eax
0x180050321  js      short loc_18005035B
0x180050323  mov     ecx, dword ptr [rbp+size]
0x180050326  movzx   eax, word ptr [rsi+1D0h]
0x18005032d  lea     r9d, [rcx+2]
0x180050331  add     r9d, eax
0x180050334  cmp     r9d, ecx
0x180050337  jb      short loc_18005035B
0x180050339  mov     dword ptr [rbp+size], r9d
0x18005033d  lea     r8, [rbp+size]; unsigned int *
0x180050341  mov     edx, r14d; unsigned int
0x180050344  mov     ecx, r9d; unsigned int
0x180050347  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18005034c  test    eax, eax
0x18005034e  jns     short loc_180050366
0x180050350  mov     r8d, 228h
0x180050356  jmp     loc_18005087B
0x18005035b  mov     r8d, 222h
0x180050361  jmp     loc_18005087B
0x180050366  mov     ecx, dword ptr [rbp+size]; size
0x180050369  call    MIDL_user_allocate
0x18005036e  mov     r15, rax
0x180050371  test    rax, rax
0x180050374  jnz     short loc_1800503BC
0x180050376  lea     eax, [r15+10h]
0x18005037a  lea     rcx, [rsi+0ACh]
0x180050381  mov     [rcx], dil
0x180050384  inc     rcx
0x180050387  sub     rax, 1
0x18005038b  jnz     short loc_180050381
0x18005038d  mov     eax, 28h ; '('
0x180050392  lea     rcx, [rsi+0E8h]
0x180050399  mov     [rcx], dil
0x18005039c  inc     rcx
0x18005039f  sub     rax, 1
0x1800503a3  jnz     short loc_180050399
0x1800503a5  mov     rcx, rsi; Block
0x1800503a8  call    cs:__imp_free
0x1800503ae  mov     eax, 0C000009Ah
0x1800503b3  mov     [r13+0], rdi
0x1800503b7  jmp     loc_180050891
0x1800503bc  mov     rcx, rsi
0x1800503bf  mov     rdx, r14
0x1800503c2  mov     r8d, 80h
0x1800503c8  movups  xmm0, xmmword ptr [rcx]
0x1800503cb  movups  xmmword ptr [rax], xmm0
0x1800503ce  movups  xmm1, xmmword ptr [rcx+10h]
0x1800503d2  movups  xmmword ptr [rax+10h], xmm1
0x1800503d6  movups  xmm0, xmmword ptr [rcx+20h]
0x1800503da  movups  xmmword ptr [rax+20h], xmm0
0x1800503de  movups  xmm1, xmmword ptr [rcx+30h]
0x1800503e2  movups  xmmword ptr [rax+30h], xmm1
0x1800503e6  movups  xmm0, xmmword ptr [rcx+40h]
0x1800503ea  movups  xmmword ptr [rax+40h], xmm0
0x1800503ee  movups  xmm1, xmmword ptr [rcx+50h]
0x1800503f2  movups  xmmword ptr [rax+50h], xmm1
0x1800503f6  movups  xmm0, xmmword ptr [rcx+60h]
0x1800503fa  movups  xmmword ptr [rax+60h], xmm0
0x1800503fe  movups  xmm1, xmmword ptr [rcx+70h]
0x180050402  add     rcx, r8
0x180050405  movups  xmmword ptr [rax+70h], xmm1
0x180050409  add     rax, r8
0x18005040c  sub     rdx, 1; Val
0x180050410  jnz     short loc_1800503C8
0x180050412  movups  xmm0, xmmword ptr [rcx]
0x180050415  lea     rcx, [r15+110h]; void *
0x18005041c  mov     r8d, 0D0h; Size
0x180050422  movups  xmmword ptr [rax], xmm0
0x180050425  call    memset_0
0x18005042a  mov     r8d, [rsi+9Ch]
0x180050431  lea     rbx, [r15+1E0h]
0x180050438  mov     rdx, [rsi+0A0h]; Src
  ... truncated ...
```

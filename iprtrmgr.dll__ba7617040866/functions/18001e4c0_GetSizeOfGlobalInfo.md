# GetSizeOfGlobalInfo

- ea: `0x18001e4c0`
- end: `0x18001e945`
- name: `GetSizeOfGlobalInfo`
- size: `1157`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800241f4`
- `0x18003cac0`

## callees

- `0x180011790`
- `0x18001e4c0`
- `0x180057c8c`
- `0x180057cd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `iprtprio!GetPriorityInfo` at `0x18001e62b`
- `iprtprio!GetPriorityInfo` at `0x18001e62b`

## string_xrefs

- `0x18001e740`: `GetSizeOfGlobalInfo1: Error %d while adding computed size for global info =%d`
- `0x18001e71b`: `GetSizeOfGlobalInfo2: Error %d while adding computed size for global info =%d`
- `0x18001e8bf`: `GetSizeOfGlobalInfo3: Error %d while adding computed size for global info =%d`
- `0x18001e895`: `GetSizeOfGlobalInfo4: Error %d while adding computed size for global info =%d`
- `0x18001e873`: `GetSizeOfGlobalInfo5: Error %d while adding computed size for global info =%d`

## pseudocode

```c
__int64 __fastcall GetSizeOfGlobalInfo(struct _GUID *a1, int a2, unsigned int *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rcx
  __int64 *v6; // r15
  unsigned int v7; // r13d
  unsigned __int64 v10; // rcx
  BOOL v11; // r12d
  __int128 *v12; // r9
  unsigned int v14; // edi
  __int64 (__fastcall *v15)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int *); // rax
  unsigned int v16; // eax
  __int64 v17; // r9
  __int128 *v18; // r9
  __int64 v19; // r9
  unsigned int v20; // edi
  const wchar_t *v21; // rdx
  unsigned int v22; // esi
  int v23; // r15d
  __int64 *v24; // rdi
  int v25; // eax
  __int64 *v26; // r14
  bool v27; // zf
  int v28; // eax
  __int128 *v29; // r9
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh]
  unsigned int *v36; // [rsp+58h] [rbp-A8h]
  __int128 v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+70h] [rbp-90h] BYREF
  __int128 v39; // [rsp+74h] [rbp-8Ch]
  __int128 v40; // [rsp+84h] [rbp-7Ch]
  int v41; // [rsp+94h] [rbp-6Ch]
  int v42; // [rsp+A0h] [rbp-60h] BYREF
  char v43[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = 0;
  v36 = a3;
  v35 = a2;
  v30 = 0;
  v31 = 0;
  v5 = *(_QWORD *)&a1->Data1;
  v6 = &g_rgicInfoCbv4;
  if ( a2 != 1 )
    v6 = &g_rgicInfoCbv6;
  v34 = 0;
  v33 = 0;
  v7 = 5;
  v32 = 0;
  if ( a2 != 1 )
    v7 = 3;
  v10 = v5 - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v10 )
    v10 = *(_QWORD *)a1->Data4 - _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0];
  v42 = 0;
  v11 = v10 != 0;
  memset_0(v43, 0, sizeof(v43));
  v38 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v42) = 0;
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v42, L"Entered: %ws", L"GetSizeOfGlobalInfo");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12 = &v37;
      if ( a1 )
        LODWORD(v12) = (_DWORD)a1;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v42,
        (_DWORD)v12,
        0,
        (__int64)&v38);
    }
  }
  if ( !(unsigned int)IsMultiTenancyEnabled() && v11 || !a3 )
    return 87;
  v14 = 12;
  if ( a2 )
  {
    v30 = 0;
    GetPriorityInfo(0, &v30);
    v14 = v30 + 36;
  }
  while ( (unsigned int)v3 < v7 )
  {
    v15 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))v6[5 * v3 + 4];
    if ( v15 )
    {
      v31 = 0;
      v16 = v15(0, 0, 0, 0, &v31);
      if ( !v16 || v16 == 122 )
      {
        v19 = v31 + 24;
        if ( (unsigned int)v19 < v31 )
        {
          v20 = 534;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v19 = v31;
            v21 = L"GetSizeOfGlobalInfo1: Error %d while adding computed size for global info =%d";
            goto LABEL_62;
          }
          return v20;
        }
        v14 += v19;
        if ( v14 < (unsigned int)v19 )
        {
          v20 = 534;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v21 = L"GetSizeOfGlobalInfo2: Error %d while adding computed size for global info =%d";
            goto LABEL_62;
          }
          return v20;
        }
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v17 = v6[5 * v3];
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v42, L"GetSizeOfGlobalInfo: Error %d in GetGlobInfo for %hs\n", v16, v17);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v18 = &v37;
          if ( a1 )
            LODWORD(v18) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v42,
            (_DWORD)v18,
            0,
            (__int64)&v38);
        }
      }
    }
    v3 = (unsigned int)(v3 + 1);
  }
  v22 = v14 + 32;
  if ( v14 + 32 < v14 )
  {
    v20 = 534;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v19 = 0xFFFFFFFFLL;
      v21 = L"GetSizeOfGlobalInfo3: Error %d while adding computed size for global info =%d";
      goto LABEL_62;
    }
    return v20;
  }
  v23 = v35;
  if ( v35 == 1 )
  {
    v24 = (__int64 *)g_leProtoCbListV4;
    v25 = 33;
  }
  else
  {
    v24 = (__int64 *)g_leProtoCbListV6;
    v25 = 87;
  }
  v26 = (__int64 *)&g_leProtoCbListV4;
  if ( v25 != 33 )
    v26 = &g_leProtoCbListV6;
  while ( 1 )
  {
    if ( v24 == v26 )
    {
      v20 = 0;
      *v36 = v22;
      return v20;
    }
    if ( !*((_DWORD *)v24 + 4) )
    {
      if ( v11 )
      {
        if ( !(unsigned int)IsProtocolEnabledForRoutingDomain(a1, v23 != 0 ? 33 : 87, *((_DWORD *)v24 + 15)) )
          goto LABEL_54;
        v27 = v24[37] == 0;
      }
      else
      {
        v27 = v24[12] == 0;
      }
      if ( !v27 )
      {
        v30 = 0;
        v28 = v11
            ? ((__int64 (__fastcall *)(struct _GUID *, _QWORD, unsigned int *, int *, int *, int *))v24[37])(
                a1,
                0,
                &v30,
                &v34,
                &v33,
                &v32)
            : ((unsigned __int64 (__fastcall *)(_QWORD, unsigned int *, int *, int *, int *))v24[12])(
                0,
                &v30,
                &v34,
                &v33,
                &v32);
        if ( !v28 || v28 == 122 )
          break;
      }
    }
LABEL_54:
    v24 = (__int64 *)*v24;
  }
  v19 = v30 + 24;
  if ( (unsigned int)v19 >= v30 )
  {
    v22 += v19;
    if ( v22 < (unsigned int)v19 )
    {
      v20 = 534;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v20;
      v21 = L"GetSizeOfGlobalInfo5: Error %d while adding computed size for global info =%d";
      goto LABEL_62;
    }
    goto LABEL_54;
  }
  v20 = 534;
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
    return v20;
  v19 = v30;
  v21 = L"GetSizeOfGlobalInfo4: Error %d while adding computed size for global info =%d";
LABEL_62:
  LOWORD(v42) = 0;
  LOWORD(v38) = 0;
  FormatRRASErrorString(&v42, v21, 534, v19);
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v29 = &v37;
    if ( a1 )
      LODWORD(v29) = (_DWORD)a1;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrMgrParamTraceError,
      (unsigned int)&v42,
      (_DWORD)v29,
      0,
      (__int64)&v38);
  }
  return v20;
}

```

## disassembly

```asm
0x18001e4c0  mov     [rsp-8+arg_8], rbx
0x18001e4c5  push    rbp
0x18001e4c6  push    rsi
0x18001e4c7  push    rdi
0x18001e4c8  push    r12
0x18001e4ca  push    r13
0x18001e4cc  push    r14
0x18001e4ce  push    r15
0x18001e4d0  lea     rbp, [rsp-7B0h]
0x18001e4d8  sub     rsp, 8B0h
0x18001e4df  mov     rax, cs:__security_cookie
0x18001e4e6  xor     rax, rsp
0x18001e4e9  mov     [rbp+7E0h+var_40], rax
0x18001e4f0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001e4f7  xor     esi, esi
0x18001e4f9  mov     [rsp+8E0h+var_888], r8
0x18001e4fe  cmp     edx, 1
0x18001e501  mov     [rsp+8E0h+var_88C], edx
0x18001e505  lea     rax, g_rgicInfoCbv6
0x18001e50c  mov     [rsp+8E0h+var_8A0], esi
0x18001e510  mov     rbx, rcx
0x18001e513  mov     [rsp+8E0h+var_89C], esi
0x18001e517  mov     rcx, [rcx]
0x18001e51a  lea     r15, g_rgicInfoCbv4
0x18001e521  cmovnz  r15, rax
0x18001e525  mov     [rsp+8E0h+var_890], esi
0x18001e529  lea     eax, [rsi+3]
0x18001e52c  mov     [rsp+8E0h+var_894], esi
0x18001e530  lea     r13d, [rsi+5]
0x18001e534  mov     [rsp+8E0h+var_898], esi
0x18001e538  cmovnz  r13d, eax
0x18001e53c  mov     rdi, r8
0x18001e53f  movq    rax, xmm0
0x18001e544  mov     r14d, edx
0x18001e547  sub     rcx, rax
0x18001e54a  jnz     short loc_18001E55D
0x18001e54c  mov     rcx, [rbx+8]
0x18001e550  psrldq  xmm0, 8
0x18001e555  movq    rax, xmm0
0x18001e55a  sub     rcx, rax
0x18001e55d  test    rcx, rcx
0x18001e560  mov     [rbp+7E0h+var_840], esi
0x18001e563  mov     r12d, esi
0x18001e566  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18001e56a  setnz   r12b
0x18001e56e  mov     r8d, 7FCh; Size
0x18001e574  xor     edx, edx; Val
0x18001e576  call    memset_0
0x18001e57b  xorps   xmm0, xmm0
0x18001e57e  mov     [rsp+8E0h+var_870], esi
0x18001e582  xor     eax, eax
0x18001e584  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001e58b  movups  [rsp+8E0h+var_86C], xmm0
0x18001e590  mov     [rbp+7E0h+var_84C], eax
0x18001e593  movups  [rbp+7E0h+var_85C], xmm0
0x18001e597  movups  [rsp+8E0h+var_880], xmm0
0x18001e59c  jge     short loc_18001E5F9
0x18001e59e  lea     r8, aGetsizeofgloba_5; "GetSizeOfGlobalInfo"
0x18001e5a5  mov     word ptr [rbp+7E0h+var_840], si
0x18001e5a9  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001e5b0  mov     word ptr [rsp+8E0h+var_870], si
0x18001e5b5  lea     rcx, [rbp+7E0h+var_840]
0x18001e5b9  call    FormatRRASErrorString
0x18001e5be  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001e5c5  jge     short loc_18001E5F9
0x18001e5c7  test    rbx, rbx
0x18001e5ca  lea     rax, [rsp+8E0h+var_870]
0x18001e5cf  mov     [rsp+8E0h+var_8B8], rax
0x18001e5d4  lea     r9, [rsp+8E0h+var_880]
0x18001e5d9  cmovnz  r9, rbx
0x18001e5dd  mov     [rsp+8E0h+var_8C0], rsi
0x18001e5e2  lea     r8, [rbp+7E0h+var_840]
0x18001e5e6  lea     rdx, RasRtrmgrParamTraceInfo
0x18001e5ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e5f4  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e5f9  call    IsMultiTenancyEnabled
0x18001e5fe  test    eax, eax
0x18001e600  jnz     short loc_18001E607
0x18001e602  test    r12d, r12d
0x18001e605  jnz     short loc_18001E60C
0x18001e607  test    rdi, rdi
0x18001e60a  jnz     short loc_18001E616
0x18001e60c  mov     eax, 57h ; 'W'
0x18001e611  jmp     loc_18001E91B
0x18001e616  mov     edi, 0Ch
0x18001e61b  test    r14d, r14d
0x18001e61e  jz      short loc_18001E638
0x18001e620  lea     rdx, [rsp+8E0h+var_8A0]
0x18001e625  mov     [rsp+8E0h+var_8A0], esi
0x18001e629  xor     ecx, ecx
0x18001e62b  call    cs:__imp_GetPriorityInfo
0x18001e631  mov     edi, [rsp+8E0h+var_8A0]
0x18001e635  add     edi, 24h ; '$'
0x18001e638  cmp     esi, r13d
0x18001e63b  jnb     loc_18001E74C
0x18001e641  lea     r14, [rsi+rsi*4]
0x18001e645  mov     rax, [r15+r14*8+20h]
0x18001e64a  test    rax, rax
0x18001e64d  jz      loc_18001E6FE
0x18001e653  lea     rcx, [rsp+8E0h+var_89C]
0x18001e658  mov     [rsp+8E0h+var_89C], 0
0x18001e660  mov     [rsp+8E0h+var_8C0], rcx
0x18001e665  xor     r9d, r9d
0x18001e668  xor     ecx, ecx
0x18001e66a  xor     r8d, r8d
0x18001e66d  xor     edx, edx
0x18001e66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e674  test    eax, eax
0x18001e676  jz      short loc_18001E6E9
0x18001e678  cmp     eax, 7Ah ; 'z'
0x18001e67b  jz      short loc_18001E6E9
0x18001e67d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e684  jz      short loc_18001E6FE
0x18001e686  mov     r9, [r15+r14*8]
0x18001e68a  lea     rdx, aGetsizeofgloba; "GetSizeOfGlobalInfo: Error %d in GetGlo"...
0x18001e691  xor     ecx, ecx
0x18001e693  mov     r8d, eax
0x18001e696  mov     word ptr [rbp+7E0h+var_840], cx
0x18001e69a  mov     word ptr [rsp+8E0h+var_870], cx
0x18001e69f  lea     rcx, [rbp+7E0h+var_840]
0x18001e6a3  call    FormatRRASErrorString
0x18001e6a8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e6af  jz      short loc_18001E6FE
0x18001e6b1  test    rbx, rbx
0x18001e6b4  lea     rax, [rsp+8E0h+var_870]
0x18001e6b9  mov     [rsp+8E0h+var_8B8], rax
0x18001e6be  lea     r9, [rsp+8E0h+var_880]
0x18001e6c3  cmovnz  r9, rbx
0x18001e6c7  mov     [rsp+8E0h+var_8C0], 0
0x18001e6d0  lea     r8, [rbp+7E0h+var_840]
0x18001e6d4  lea     rdx, RasRtrMgrParamTraceError
0x18001e6db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e6e2  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e6e7  jmp     short loc_18001E6FE
0x18001e6e9  mov     ecx, [rsp+8E0h+var_89C]
0x18001e6ed  lea     r9d, [rcx+18h]
0x18001e6f1  cmp     r9d, ecx
0x18001e6f4  jb      short loc_18001E727
0x18001e6f6  add     edi, r9d
0x18001e6f9  cmp     edi, r9d
0x18001e6fc  jb      short loc_18001E705
0x18001e6fe  inc     esi
0x18001e700  jmp     loc_18001E638
0x18001e705  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e70c  mov     r8d, 216h
0x18001e712  mov     edi, r8d
0x18001e715  jz      loc_18001E919
0x18001e71b  lea     rdx, aGetsizeofgloba_0; "GetSizeOfGlobalInfo2: Error %d while ad"...
0x18001e722  jmp     loc_18001E8C6
0x18001e727  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e72e  mov     r8d, 216h
0x18001e734  mov     edi, r8d
0x18001e737  jz      loc_18001E919
0x18001e73d  mov     r9d, ecx
0x18001e740  lea     rdx, aGetsizeofgloba_2; "GetSizeOfGlobalInfo1: Error %d while ad"...
0x18001e747  jmp     loc_18001E8C6
0x18001e74c  lea     esi, [rdi+20h]
0x18001e74f  cmp     esi, edi
0x18001e751  jb      loc_18001E8A9
0x18001e757  mov     r15d, [rsp+8E0h+var_88C]
0x18001e75c  cmp     r15d, 1
0x18001e760  jnz     short loc_18001E76F
0x18001e762  mov     rdi, cs:g_leProtoCbListV4
0x18001e769  lea     eax, [r15+20h]
0x18001e76d  jmp     short loc_18001E77B
0x18001e76f  mov     rdi, cs:g_leProtoCbListV6
0x18001e776  mov     eax, 57h ; 'W'
0x18001e77b  cmp     eax, 21h ; '!'
0x18001e77e  lea     rcx, g_leProtoCbListV6
0x18001e785  lea     r14, g_leProtoCbListV4
0x18001e78c  cmovnz  r14, rcx
0x18001e790  cmp     rdi, r14
0x18001e793  jz      loc_18001E89E
0x18001e799  cmp     dword ptr [rdi+10h], 0
0x18001e79d  jnz     loc_18001E855
0x18001e7a3  test    r12d, r12d
0x18001e7a6  jz      short loc_18001E7D3
0x18001e7a8  mov     r8d, [rdi+3Ch]; unsigned int
0x18001e7ac  mov     eax, r15d
0x18001e7af  neg     eax
0x18001e7b1  mov     rcx, rbx; struct _GUID *
0x18001e7b4  sbb     edx, edx
0x18001e7b6  and     edx, 0FFFFFFCAh
0x18001e7b9  add     edx, 57h ; 'W'; unsigned int
0x18001e7bc  call    IsProtocolEnabledForRoutingDomain
0x18001e7c1  test    eax, eax
0x18001e7c3  jz      loc_18001E855
0x18001e7c9  cmp     qword ptr [rdi+128h], 0
0x18001e7d1  jmp     short loc_18001E7D8
0x18001e7d3  cmp     qword ptr [rdi+60h], 0
0x18001e7d8  jz      short loc_18001E855
0x18001e7da  mov     [rsp+8E0h+var_8A0], 0
0x18001e7e2  lea     rax, [rsp+8E0h+var_898]
0x18001e7e7  test    r12d, r12d
0x18001e7ea  jnz     short loc_18001E80D
0x18001e7ec  mov     [rsp+8E0h+var_8C0], rax
0x18001e7f1  lea     r9, [rsp+8E0h+var_894]
0x18001e7f6  mov     rax, [rdi+60h]
0x18001e7fa  lea     r8, [rsp+8E0h+var_890]
0x18001e7ff  lea     rdx, [rsp+8E0h+var_8A0]
0x18001e804  xor     ecx, ecx
0x18001e806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80b  jmp     short loc_18001E837
0x18001e80d  mov     [rsp+8E0h+var_8B8], rax
0x18001e812  lea     r9, [rsp+8E0h+var_890]
0x18001e817  lea     rax, [rsp+8E0h+var_894]
0x18001e81c  xor     edx, edx
0x18001e81e  mov     [rsp+8E0h+var_8C0], rax
0x18001e823  lea     r8, [rsp+8E0h+var_8A0]
0x18001e828  mov     rax, [rdi+128h]
0x18001e82f  mov     rcx, rbx
0x18001e832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e837  test    eax, eax
0x18001e839  jz      short loc_18001E840
0x18001e83b  cmp     eax, 7Ah ; 'z'
0x18001e83e  jnz     short loc_18001E855
0x18001e840  mov     ecx, [rsp+8E0h+var_8A0]
0x18001e844  lea     r9d, [rcx+18h]
0x18001e848  cmp     r9d, ecx
0x18001e84b  jb      short loc_18001E87C
0x18001e84d  add     esi, r9d
0x18001e850  cmp     esi, r9d
0x18001e853  jb      short loc_18001E85D
0x18001e855  mov     rdi, [rdi]
0x18001e858  jmp     loc_18001E790
0x18001e85d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e864  mov     r8d, 216h
0x18001e86a  mov     edi, r8d
0x18001e86d  jz      loc_18001E919
0x18001e873  lea     rdx, aGetsizeofgloba_4; "GetSizeOfGlobalInfo5: Error %d while ad"...
0x18001e87a  jmp     short loc_18001E8C6
0x18001e87c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e883  mov     r8d, 216h
0x18001e889  mov     edi, r8d
0x18001e88c  jz      loc_18001E919
0x18001e892  mov     r9d, ecx
0x18001e895  lea     rdx, aGetsizeofgloba_3; "GetSizeOfGlobalInfo4: Error %d while ad"...
0x18001e89c  jmp     short loc_18001E8C6
0x18001e89e  mov     rax, [rsp+8E0h+var_888]
0x18001e8a3  xor     edi, edi
0x18001e8a5  mov     [rax], esi
0x18001e8a7  jmp     short loc_18001E919
0x18001e8a9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e8b0  mov     r8d, 216h
0x18001e8b6  mov     edi, r8d
0x18001e8b9  jz      short loc_18001E919
0x18001e8bb  or      r9d, 0FFFFFFFFh
0x18001e8bf  lea     rdx, aGetsizeofgloba_1; "GetSizeOfGlobalInfo3: Error %d while ad"...
0x18001e8c6  xor     eax, eax
0x18001e8c8  lea     rcx, [rbp+7E0h+var_840]
0x18001e8cc  mov     word ptr [rbp+7E0h+var_840], ax
0x18001e8d0  mov     word ptr [rsp+8E0h+var_870], ax
0x18001e8d5  call    FormatRRASErrorString
0x18001e8da  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001e8e1  jz      short loc_18001E919
0x18001e8e3  test    rbx, rbx
0x18001e8e6  lea     rax, [rsp+8E0h+var_870]
0x18001e8eb  mov     [rsp+8E0h+var_8B8], rax
0x18001e8f0  lea     r9, [rsp+8E0h+var_880]
0x18001e8f5  cmovnz  r9, rbx
0x18001e8f9  mov     [rsp+8E0h+var_8C0], 0
0x18001e902  lea     r8, [rbp+7E0h+var_840]
0x18001e906  lea     rdx, RasRtrMgrParamTraceError
0x18001e90d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e914  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e919  mov     eax, edi
0x18001e91b  mov     rcx, [rbp+7E0h+var_40]
0x18001e922  xor     rcx, rsp; StackCookie
0x18001e925  call    __security_check_cookie
0x18001e92a  mov     rbx, [rsp+8E0h+arg_8]
0x18001e932  add     rsp, 8B0h
0x18001e939  pop     r15
0x18001e93b  pop     r14
0x18001e93d  pop     r13
0x18001e93f  pop     r12
0x18001e941  pop     rdi
0x18001e942  pop     rsi
0x18001e943  pop     rbp
0x18001e944  retn
```

# GetGlobalConfiguration

- ea: `0x18001d134`
- end: `0x18001d7db`
- name: `GetGlobalConfiguration`
- size: `1703`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800241f4`
- `0x18003cac0`

## callees

- `0x180011790`
- `0x18001d134`
- `0x180057c8c`
- `0x180057cd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `iprtprio!GetPriorityInfo` at `0x18001d428`
- `iprtprio!GetPriorityInfo` at `0x18001d428`

## string_xrefs

- `0x18001d225`: `GetGlobalConfiguration`
- `0x18001d329`: `GetGlobalConfiguration: TransportID %d and Total Routing protocols %d`
- `0x18001d673`: `GetGlobalConfiguration: Error %d getting global info from %ws`
- `0x18001d74e`: `GetGlobalConfiguration: Error %d while adding routing protocol global info size `

## pseudocode

```c
__int64 __fastcall GetGlobalConfiguration(_DWORD *a1, int a2, struct _GUID *a3, int a4)
{
  unsigned int v4; // edi
  _DWORD *v5; // rsi
  __int64 *v6; // rax
  int v7; // eax
  __int64 v8; // rcx
  unsigned __int64 v11; // rcx
  _BOOL8 v12; // rbx
  __int128 *v13; // r9
  __int64 *v15; // rbx
  int v16; // eax
  __int64 *v17; // r12
  __int64 v18; // r8
  __int128 *v19; // r9
  __int64 *v20; // r12
  unsigned int v21; // ecx
  unsigned int v22; // edi
  __int64 v23; // rbx
  void (__fastcall *v24)(_QWORD, unsigned int *, _QWORD, _QWORD, unsigned int *); // rax
  __int64 v25; // rax
  int v26; // r8d
  char *v27; // r12
  __int64 v28; // rax
  _DWORD *v29; // rbx
  unsigned int v30; // edx
  unsigned int v31; // r14d
  __int64 v32; // rdi
  __int64 *v33; // r15
  void (__fastcall *v34)(_DWORD *, int *, _DWORD *, _DWORD *, unsigned int *); // rax
  unsigned __int64 v35; // rbx
  unsigned int v36; // r12d
  __int64 *v37; // rdi
  int v38; // eax
  struct _GUID *v39; // r14
  bool v40; // zf
  __int64 *v41; // rax
  BOOL v42; // eax
  unsigned int v43; // eax
  __int128 *v44; // r9
  unsigned __int64 v45; // rax
  __int128 *v46; // r9
  int v47; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v48; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v50; // [rsp+50h] [rbp-B0h]
  unsigned int v51; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v52; // [rsp+5Ch] [rbp-A4h]
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v55; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+6Ch] [rbp-94h] BYREF
  _DWORD *v57; // [rsp+70h] [rbp-90h]
  __int64 *v58; // [rsp+78h] [rbp-88h]
  struct _GUID *v59; // [rsp+80h] [rbp-80h]
  __int128 v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+98h] [rbp-68h] BYREF
  __int128 v62; // [rsp+9Ch] [rbp-64h]
  __int128 v63; // [rsp+ACh] [rbp-54h]
  int v64; // [rsp+BCh] [rbp-44h]
  int v65; // [rsp+C0h] [rbp-40h] BYREF
  char v66[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v4 = 0;
  v57 = a1;
  v5 = a1;
  v59 = a3;
  LODWORD(v50) = a2;
  v48 = 0;
  v6 = &g_rgicInfoCbv4;
  v51 = 0;
  if ( a4 != 1 )
    v6 = &g_rgicInfoCbv6;
  v47 = 0;
  v58 = v6;
  v7 = 5;
  v49 = 0;
  if ( a4 != 1 )
    v7 = 3;
  v56 = 0;
  v8 = *(_QWORD *)&a3->Data1;
  v55 = v7;
  v53 = 0;
  v54 = 0;
  v11 = v8 - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v11 )
    v11 = *(_QWORD *)a3->Data4 - _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0];
  v65 = 0;
  v12 = v11 != 0;
  v52 = v11 != 0;
  memset_0(v66, 0, sizeof(v66));
  v61 = 0;
  v62 = 0;
  v64 = 0;
  v63 = 0;
  v60 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v65) = 0;
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v65, L"Entered: %ws", L"GetGlobalConfiguration");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v13 = &v60;
      if ( a3 )
        LODWORD(v13) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v65,
        (_DWORD)v13,
        0,
        (__int64)&v61);
    }
  }
  if ( !(unsigned int)IsMultiTenancyEnabled() && v12 )
    return 87;
  if ( a4 == 1 )
  {
    v15 = (__int64 *)g_leProtoCbListV4;
    v16 = 33;
  }
  else
  {
    v15 = (__int64 *)g_leProtoCbListV6;
    v16 = 87;
  }
  v17 = (__int64 *)&g_leProtoCbListV4;
  if ( v16 != 33 )
    v17 = &g_leProtoCbListV6;
  if ( v15 != v17 )
  {
    while ( 1 )
    {
      if ( !*((_DWORD *)v15 + 4) )
      {
        if ( v52 )
        {
          if ( !(unsigned int)IsProtocolEnabledForRoutingDomain(a3, a4 != 0 ? 33 : 87, *((_DWORD *)v15 + 15))
            || !v15[37] )
          {
            goto LABEL_28;
          }
LABEL_27:
          ++v4;
          goto LABEL_28;
        }
        if ( v15[12] )
          goto LABEL_27;
      }
LABEL_28:
      v15 = (__int64 *)*v15;
      if ( v15 == v17 )
      {
        v5 = v57;
        break;
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v65) = 0;
    LOWORD(v61) = 0;
    v18 = 33;
    if ( a4 != 1 )
      v18 = 87;
    FormatRRASErrorString(&v65, L"GetGlobalConfiguration: TransportID %d and Total Routing protocols %d", v18, v4);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v19 = &v60;
      if ( a3 )
        LODWORD(v19) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v65,
        (_DWORD)v19,
        0,
        (__int64)&v61);
    }
  }
  v20 = v58;
  v21 = v4 + (a4 != 0) + 1;
  v22 = v55;
  v51 = v21;
  v23 = 0;
  do
  {
    v24 = (void (__fastcall *)(_QWORD, unsigned int *, _QWORD, _QWORD, unsigned int *))v20[5 * v23 + 4];
    if ( v24 )
    {
      v49 = 0;
      v24(0, &v51, 0, 0, &v49);
    }
    v23 = (unsigned int)(v23 + 1);
  }
  while ( (unsigned int)v23 < v22 );
  v25 = v51;
  v26 = 0;
  v27 = (char *)v5 + (unsigned int)v50;
  v5[2] = v51;
  v28 = 4 * v25;
  *v5 = 1;
  v57 = v27;
  v47 = 0;
  v29 = (_DWORD *)(((unsigned __int64)&v5[v28 + 4] + 3) & 0xFFFFFFFFFFFFFFF8uLL);
  v30 = (_DWORD)v27 - (_DWORD)v29;
  if ( a4 )
  {
    v48 = (_DWORD)v27 - (_DWORD)v29;
    GetPriorityInfo(((unsigned __int64)&v5[v28 + 4] + 3) & 0xFFFFFFFFFFFFFFF8uLL, &v48);
    v5[4 * v47 + 4] = v48;
    v5[4 * v47 + 3] = -65513;
    v5[4 * v47 + 5] = 1;
    v5[4 * v47 + 6] = (_DWORD)v29 - (_DWORD)v5;
    v26 = ++v47;
    v29 = (_DWORD *)(((unsigned __int64)v29 + v48 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    v30 = (_DWORD)v27 - (_DWORD)v29;
  }
  v31 = v55;
  v32 = 0;
  v33 = v58;
  do
  {
    v34 = (void (__fastcall *)(_DWORD *, int *, _DWORD *, _DWORD *, unsigned int *))v33[5 * v32 + 4];
    if ( v34 )
    {
      v49 = v30;
      v34(&v5[4 * v26 + 3], &v47, v29, v5, &v49);
      v26 = v47;
      v29 = (_DWORD *)(((unsigned __int64)v29 + v49 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      v30 = (_DWORD)v27 - (_DWORD)v29;
    }
    v32 = (unsigned int)(v32 + 1);
  }
  while ( (unsigned int)v32 < v31 );
  v49 = 8;
  v5[4 * v26 + 4] = 8;
  v5[4 * v47 + 3] = a4 != 0 ? -65533 : -65521;
  v5[4 * v47 + 5] = 1;
  v5[4 * v47 + 6] = (_DWORD)v29 - (_DWORD)v5;
  v29[1] = g_dwLoggingLevel;
  *v29 = 0;
  ++v47;
  v35 = ((unsigned __int64)v29 + v49 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v36 = (_DWORD)v27 - v35;
  if ( a4 == 1 )
  {
    v37 = (__int64 *)g_leProtoCbListV4;
    v38 = 33;
  }
  else
  {
    v37 = (__int64 *)g_leProtoCbListV6;
    v38 = 87;
  }
  v39 = v59;
  v40 = v38 == 33;
  v41 = (__int64 *)&g_leProtoCbListV4;
  if ( !v40 )
    v41 = &g_leProtoCbListV6;
  v50 = v41;
  while ( 1 )
  {
    if ( v37 == v41 )
    {
      v5[1] = v35 - (_DWORD)v5;
      return 0;
    }
    if ( !*((_DWORD *)v37 + 4) )
      break;
LABEL_72:
    v37 = (__int64 *)*v37;
  }
  v42 = v52;
  if ( v52 )
  {
    if ( !(unsigned int)IsProtocolEnabledForRoutingDomain(v39, a4 != 0 ? 33 : 87, *((_DWORD *)v37 + 15)) || !v37[37] )
      goto LABEL_71;
    v42 = v52;
  }
  else if ( !v37[12] )
  {
LABEL_71:
    v41 = v50;
    goto LABEL_72;
  }
  v48 = v36;
  if ( v42 )
    v43 = ((__int64 (__fastcall *)(struct _GUID *, unsigned __int64, unsigned int *, int *, int *, int *))v37[37])(
            v39,
            v35,
            &v48,
            &v56,
            &v53,
            &v54);
  else
    v43 = ((__int64 (__fastcall *)(unsigned __int64, unsigned int *, int *, int *, int *))v37[12])(
            v35,
            &v48,
            &v56,
            &v53,
            &v54);
  if ( v43 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v65) = 0;
      LOWORD(v61) = 0;
      FormatRRASErrorString(&v65, L"GetGlobalConfiguration: Error %d getting global info from %ws", v43, v37[3]);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v44 = &v60;
        if ( v39 )
          LODWORD(v44) = (_DWORD)v39;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v65,
          (_DWORD)v44,
          0,
          (__int64)&v61);
      }
    }
    goto LABEL_71;
  }
  v5[4 * v47 + 4] = v53;
  v5[4 * v47 + 3] = *((_DWORD *)v37 + 15);
  v5[4 * v47 + 6] = v35 - (_DWORD)v5;
  v5[4 * v47++ + 5] = v54;
  v45 = v35 + v48;
  if ( v45 >= v35 )
  {
    v35 = (v45 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v36 = (_DWORD)v57 - v35;
    goto LABEL_71;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v65) = 0;
    LOWORD(v61) = 0;
    FormatRRASErrorString(
      &v65,
      L"GetGlobalConfiguration: Error %d while adding routing protocol global info size ",
      534);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v46 = &v60;
      if ( v39 )
        LODWORD(v46) = (_DWORD)v39;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v65,
        (_DWORD)v46,
        0,
        (__int64)&v61);
    }
  }
  return 534;
}

```

## disassembly

```asm
0x18001d134  mov     [rsp-8+arg_18], rbx
0x18001d139  push    rbp
0x18001d13a  push    rsi
0x18001d13b  push    rdi
0x18001d13c  push    r12
0x18001d13e  push    r13
0x18001d140  push    r14
0x18001d142  push    r15
0x18001d144  lea     rbp, [rsp-7D0h]
0x18001d14c  sub     rsp, 8D0h
0x18001d153  mov     rax, cs:__security_cookie
0x18001d15a  xor     rax, rsp
0x18001d15d  mov     [rbp+800h+var_40], rax
0x18001d164  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001d16b  xor     edi, edi
0x18001d16d  mov     [rsp+900h+var_890], rcx
0x18001d172  mov     rsi, rcx
0x18001d175  mov     [rbp+800h+var_880], r8
0x18001d179  cmp     r9d, 1
0x18001d17d  mov     dword ptr [rsp+900h+var_8B0], edx
0x18001d181  lea     rcx, g_rgicInfoCbv6
0x18001d188  mov     [rsp+900h+var_8BC], edi
0x18001d18c  lea     rax, g_rgicInfoCbv4
0x18001d193  mov     [rsp+900h+var_8A8], edi
0x18001d197  cmovnz  rax, rcx
0x18001d19b  mov     [rsp+900h+var_8C0], edi
0x18001d19f  mov     [rsp+900h+var_888], rax
0x18001d1a4  lea     ecx, [rdi+3]
0x18001d1a7  lea     eax, [rdi+5]
0x18001d1aa  mov     [rsp+900h+var_8B8], edi
0x18001d1ae  cmovnz  eax, ecx
0x18001d1b1  mov     [rsp+900h+var_894], edi
0x18001d1b5  mov     rcx, [r8]
0x18001d1b8  mov     r13d, r9d
0x18001d1bb  mov     [rsp+900h+var_898], eax
0x18001d1bf  mov     r14, r8
0x18001d1c2  movq    rax, xmm0
0x18001d1c7  mov     [rsp+900h+var_8A0], edi
0x18001d1cb  mov     [rsp+900h+var_89C], edi
0x18001d1cf  sub     rcx, rax
0x18001d1d2  jnz     short loc_18001D1E5
0x18001d1d4  mov     rcx, [r8+8]
0x18001d1d8  psrldq  xmm0, 8
0x18001d1dd  movq    rax, xmm0
0x18001d1e2  sub     rcx, rax
0x18001d1e5  test    rcx, rcx
0x18001d1e8  mov     [rbp+800h+var_840], edi
0x18001d1eb  mov     ebx, edi
0x18001d1ed  lea     rcx, [rbp+800h+var_83C]; void *
0x18001d1f1  setnz   bl
0x18001d1f4  mov     r8d, 7FCh; Size
0x18001d1fa  xor     edx, edx; Val
0x18001d1fc  mov     [rsp+900h+var_8A4], ebx
0x18001d200  call    memset_0
0x18001d205  xorps   xmm0, xmm0
0x18001d208  mov     [rbp+800h+var_868], edi
0x18001d20b  xor     eax, eax
0x18001d20d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001d214  movups  [rbp+800h+var_864], xmm0
0x18001d218  mov     [rbp+800h+var_844], eax
0x18001d21b  movups  [rbp+800h+var_854], xmm0
0x18001d21f  movups  [rbp+800h+var_878], xmm0
0x18001d223  jge     short loc_18001D27D
0x18001d225  lea     r8, aGetglobalconfi_2; "GetGlobalConfiguration"
0x18001d22c  mov     word ptr [rbp+800h+var_840], di
0x18001d230  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001d237  mov     word ptr [rbp+800h+var_868], di
0x18001d23b  lea     rcx, [rbp+800h+var_840]
0x18001d23f  call    FormatRRASErrorString
0x18001d244  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001d24b  jge     short loc_18001D27D
0x18001d24d  test    r14, r14
0x18001d250  lea     rax, [rbp+800h+var_868]
0x18001d254  mov     [rsp+900h+var_8D8], rax
0x18001d259  lea     r9, [rbp+800h+var_878]
0x18001d25d  cmovnz  r9, r14
0x18001d261  mov     [rsp+900h+var_8E0], rdi
0x18001d266  lea     r8, [rbp+800h+var_840]
0x18001d26a  lea     rdx, RasRtrmgrParamTraceInfo
0x18001d271  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001d278  call    McTemplateU0zjzz_EventWriteTransfer
0x18001d27d  call    IsMultiTenancyEnabled
0x18001d282  test    eax, eax
0x18001d284  jnz     short loc_18001D294
0x18001d286  test    ebx, ebx
0x18001d288  jz      short loc_18001D294
0x18001d28a  mov     eax, 57h ; 'W'
0x18001d28f  jmp     loc_18001D7B1
0x18001d294  mov     r15d, 57h ; 'W'
0x18001d29a  cmp     r13d, 1
0x18001d29e  jnz     short loc_18001D2AD
0x18001d2a0  mov     rbx, cs:g_leProtoCbListV4
0x18001d2a7  lea     eax, [r15-36h]
0x18001d2ab  jmp     short loc_18001D2B7
0x18001d2ad  mov     rbx, cs:g_leProtoCbListV6
0x18001d2b4  mov     eax, r15d
0x18001d2b7  cmp     eax, 21h ; '!'
0x18001d2ba  lea     rcx, g_leProtoCbListV6
0x18001d2c1  lea     r12, g_leProtoCbListV4
0x18001d2c8  cmovnz  r12, rcx
0x18001d2cc  cmp     rbx, r12
0x18001d2cf  jz      short loc_18001D31E
0x18001d2d1  mov     esi, [rsp+900h+var_8A4]
0x18001d2d5  cmp     dword ptr [rbx+10h], 0
0x18001d2d9  jnz     short loc_18001D311
0x18001d2db  test    esi, esi
0x18001d2dd  jz      short loc_18001D308
0x18001d2df  mov     r8d, [rbx+3Ch]; unsigned int
0x18001d2e3  mov     eax, r13d
0x18001d2e6  neg     eax
0x18001d2e8  mov     rcx, r14; struct _GUID *
0x18001d2eb  sbb     edx, edx
0x18001d2ed  and     edx, 0FFFFFFCAh
0x18001d2f0  add     edx, r15d; unsigned int
0x18001d2f3  call    IsProtocolEnabledForRoutingDomain
0x18001d2f8  test    eax, eax
0x18001d2fa  jz      short loc_18001D311
0x18001d2fc  cmp     qword ptr [rbx+128h], 0
0x18001d304  jnz     short loc_18001D30F
0x18001d306  jmp     short loc_18001D311
0x18001d308  cmp     qword ptr [rbx+60h], 0
0x18001d30d  jz      short loc_18001D311
0x18001d30f  inc     edi
0x18001d311  mov     rbx, [rbx]
0x18001d314  cmp     rbx, r12
0x18001d317  jnz     short loc_18001D2D5
0x18001d319  mov     rsi, [rsp+900h+var_890]
0x18001d31e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001d325  jge     short loc_18001D38D
0x18001d327  xor     eax, eax
0x18001d329  lea     rdx, aGetglobalconfi_1; "GetGlobalConfiguration: TransportID %d "...
0x18001d330  cmp     r13d, 1
0x18001d334  mov     word ptr [rbp+800h+var_840], ax
0x18001d338  mov     r9d, edi
0x18001d33b  mov     word ptr [rbp+800h+var_868], ax
0x18001d33f  lea     rcx, [rbp+800h+var_840]
0x18001d343  lea     r8d, [rax+21h]
0x18001d347  cmovnz  r8d, r15d
0x18001d34b  call    FormatRRASErrorString
0x18001d350  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001d357  jge     short loc_18001D38D
0x18001d359  test    r14, r14
0x18001d35c  lea     rax, [rbp+800h+var_868]
0x18001d360  mov     [rsp+900h+var_8D8], rax
0x18001d365  lea     r9, [rbp+800h+var_878]
0x18001d369  cmovnz  r9, r14
0x18001d36d  mov     [rsp+900h+var_8E0], 0
0x18001d376  lea     r8, [rbp+800h+var_840]
0x18001d37a  lea     rdx, RasRtrmgrParamTraceInfo
0x18001d381  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001d388  call    McTemplateU0zjzz_EventWriteTransfer
0x18001d38d  mov     r12, [rsp+900h+var_888]
0x18001d392  mov     eax, r13d
0x18001d395  neg     eax
0x18001d397  sbb     ecx, ecx
0x18001d399  neg     ecx
0x18001d39b  inc     ecx
0x18001d39d  add     ecx, edi
0x18001d39f  mov     edi, [rsp+900h+var_898]
0x18001d3a3  mov     [rsp+900h+var_8A8], ecx
0x18001d3a7  xor     ebx, ebx
0x18001d3a9  lea     rcx, [rbx+rbx*4]
0x18001d3ad  mov     rax, [r12+rcx*8+20h]
0x18001d3b2  test    rax, rax
0x18001d3b5  jz      short loc_18001D3DB
0x18001d3b7  lea     rcx, [rsp+900h+var_8B8]
0x18001d3bc  mov     [rsp+900h+var_8B8], 0
0x18001d3c4  mov     [rsp+900h+var_8E0], rcx
0x18001d3c9  lea     rdx, [rsp+900h+var_8A8]
0x18001d3ce  xor     ecx, ecx
0x18001d3d0  xor     r9d, r9d
0x18001d3d3  xor     r8d, r8d
0x18001d3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3db  inc     ebx
0x18001d3dd  cmp     ebx, edi
0x18001d3df  jb      short loc_18001D3A9
0x18001d3e1  mov     eax, [rsp+900h+var_8A8]
0x18001d3e5  xor     r8d, r8d
0x18001d3e8  mov     r12d, dword ptr [rsp+900h+var_8B0]
0x18001d3ed  add     r12, rsi
0x18001d3f0  mov     [rsi+8], eax
0x18001d3f3  shl     rax, 4
0x18001d3f7  mov     edx, r12d
0x18001d3fa  mov     dword ptr [rsi], 1
0x18001d400  mov     [rsp+900h+var_890], r12
0x18001d405  mov     [rsp+900h+var_8C0], r8d
0x18001d40a  lea     rbx, [rax+13h]
0x18001d40e  add     rbx, rsi
0x18001d411  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001d415  sub     edx, ebx
0x18001d417  test    r13d, r13d
0x18001d41a  jz      short loc_18001D48D
0x18001d41c  mov     [rsp+900h+var_8BC], edx
0x18001d420  mov     rcx, rbx
0x18001d423  lea     rdx, [rsp+900h+var_8BC]
0x18001d428  call    cs:__imp_GetPriorityInfo
0x18001d42e  mov     ecx, [rsp+900h+var_8C0]
0x18001d432  mov     edx, r12d
0x18001d435  mov     eax, [rsp+900h+var_8BC]
0x18001d439  inc     rcx
0x18001d43c  add     rcx, rcx
0x18001d43f  mov     [rsi+rcx*8], eax
0x18001d442  mov     ecx, ebx
0x18001d444  mov     eax, [rsp+900h+var_8C0]
0x18001d448  sub     ecx, esi
0x18001d44a  add     rax, rax
0x18001d44d  mov     dword ptr [rsi+rax*8+0Ch], 0FFFF0017h
0x18001d455  mov     eax, [rsp+900h+var_8C0]
0x18001d459  add     rax, rax
0x18001d45c  mov     dword ptr [rsi+rax*8+14h], 1
0x18001d464  mov     eax, [rsp+900h+var_8C0]
0x18001d468  add     rax, rax
0x18001d46b  mov     [rsi+rax*8+18h], ecx
0x18001d46f  mov     r8d, [rsp+900h+var_8C0]
0x18001d474  mov     eax, [rsp+900h+var_8BC]
0x18001d478  inc     r8d
0x18001d47b  add     rax, 7
0x18001d47f  mov     [rsp+900h+var_8C0], r8d
0x18001d484  add     rbx, rax
0x18001d487  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001d48b  sub     edx, ebx
0x18001d48d  mov     r14d, [rsp+900h+var_898]
0x18001d492  xor     edi, edi
0x18001d494  mov     r15, [rsp+900h+var_888]
0x18001d499  lea     rcx, [rdi+rdi*4]
0x18001d49d  mov     rax, [r15+rcx*8+20h]
0x18001d4a2  test    rax, rax
0x18001d4a5  jz      short loc_18001D4EC
0x18001d4a7  mov     ecx, r8d
0x18001d4aa  mov     r9, rsi
0x18001d4ad  shl     rcx, 4
0x18001d4b1  mov     r8, rbx
0x18001d4b4  mov     [rsp+900h+var_8B8], edx
0x18001d4b8  add     rcx, 0Ch
0x18001d4bc  lea     rdx, [rsp+900h+var_8B8]
0x18001d4c1  add     rcx, rsi
0x18001d4c4  mov     [rsp+900h+var_8E0], rdx
0x18001d4c9  lea     rdx, [rsp+900h+var_8C0]
0x18001d4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4d3  mov     eax, [rsp+900h+var_8B8]
0x18001d4d7  mov     edx, r12d
0x18001d4da  mov     r8d, [rsp+900h+var_8C0]
0x18001d4df  add     rax, 7
0x18001d4e3  add     rbx, rax
0x18001d4e6  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001d4ea  sub     edx, ebx
0x18001d4ec  inc     edi
0x18001d4ee  cmp     edi, r14d
0x18001d4f1  jb      short loc_18001D499
0x18001d4f3  mov     ecx, 8
0x18001d4f8  mov     eax, r8d
0x18001d4fb  inc     rax
0x18001d4fe  mov     [rsp+900h+var_8B8], ecx
0x18001d502  add     rax, rax
0x18001d505  mov     r15d, 57h ; 'W'
0x18001d50b  mov     [rsi+rax*8], ecx
0x18001d50e  mov     eax, r13d
0x18001d511  neg     eax
0x18001d513  mov     eax, [rsp+900h+var_8C0]
0x18001d517  sbb     ecx, ecx
0x18001d519  add     rax, rax
0x18001d51c  and     ecx, 0FFFFFFF4h
0x18001d51f  add     ecx, 0FFFF000Fh
0x18001d525  mov     [rsi+rax*8+0Ch], ecx
0x18001d529  mov     ecx, ebx
0x18001d52b  mov     eax, [rsp+900h+var_8C0]
0x18001d52f  sub     ecx, esi
0x18001d531  add     rax, rax
0x18001d534  mov     dword ptr [rsi+rax*8+14h], 1
0x18001d53c  mov     eax, [rsp+900h+var_8C0]
0x18001d540  add     rax, rax
0x18001d543  mov     [rsi+rax*8+18h], ecx
0x18001d547  mov     eax, cs:g_dwLoggingLevel
0x18001d54d  mov     [rbx+4], eax
0x18001d550  mov     dword ptr [rbx], 0
0x18001d556  mov     eax, [rsp+900h+var_8B8]
0x18001d55a  inc     [rsp+900h+var_8C0]
0x18001d55e  add     rax, 7
0x18001d562  add     rbx, rax
0x18001d565  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001d569  sub     r12d, ebx
0x18001d56c  cmp     r13d, 1
0x18001d570  jnz     short loc_18001D57F
0x18001d572  mov     rdi, cs:g_leProtoCbListV4
0x18001d579  lea     eax, [r15-36h]
0x18001d57d  jmp     short loc_18001D589
0x18001d57f  mov     rdi, cs:g_leProtoCbListV6
0x18001d586  mov     eax, r15d
0x18001d589  mov     r14, [rbp+800h+var_880]
0x18001d58d  lea     rcx, g_leProtoCbListV6
0x18001d594  cmp     eax, 21h ; '!'
0x18001d597  lea     rax, g_leProtoCbListV4
0x18001d59e  cmovnz  rax, rcx
0x18001d5a2  mov     [rsp+900h+var_8B0], rax
0x18001d5a7  cmp     rdi, rax
0x18001d5aa  jz      loc_18001D7AA
0x18001d5b0  cmp     dword ptr [rdi+10h], 0
0x18001d5b4  jnz     loc_18001D736
0x18001d5ba  mov     eax, [rsp+900h+var_8A4]
0x18001d5be  test    eax, eax
  ... truncated ...
```

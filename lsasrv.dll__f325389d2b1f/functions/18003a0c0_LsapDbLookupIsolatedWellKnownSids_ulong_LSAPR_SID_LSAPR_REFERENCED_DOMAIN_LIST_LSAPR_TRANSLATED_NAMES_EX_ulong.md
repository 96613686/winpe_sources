# LsapDbLookupIsolatedWellKnownSids(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *)

- ea: `0x18003a0c0`
- end: `0x18003a683`
- name: `?LsapDbLookupIsolatedWellKnownSids@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3@Z`
- size: `1475`
- prototype: `__int64 __fastcall(unsigned int, struct _LSAPR_SID **, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011cdc`

## callees

- `0x18003a0c0`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a1a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a591`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a64f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a672`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a1a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a591`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a64f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a672`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a27a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a2f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a3f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a45d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a4ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a27a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a2f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a3f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a45d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a4ab`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003a2cc`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003a325`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003a2cc`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003a325`
- `ntdll!RtlLengthRequiredSid` at `0x18003a2e3`
- `ntdll!RtlLengthRequiredSid` at `0x18003a2e3`
- `ntdll!RtlCopyUnicodeString` at `0x18003a29a`
- `ntdll!RtlCopyUnicodeString` at `0x18003a47e`
- `ntdll!RtlCopyUnicodeString` at `0x18003a29a`
- `ntdll!RtlCopyUnicodeString` at `0x18003a47e`
- `ntdll!RtlLengthSid` at `0x18003a496`
- `ntdll!RtlLengthSid` at `0x18003a496`
- `ntdll!RtlEqualSid` at `0x18003a157`
- `ntdll!RtlEqualSid` at `0x18003a556`
- `ntdll!RtlEqualSid` at `0x18003a5ae`
- `ntdll!RtlEqualSid` at `0x18003a157`
- `ntdll!RtlEqualSid` at `0x18003a556`
- `ntdll!RtlEqualSid` at `0x18003a5ae`

## pseudocode

```c
__int64 __fastcall LsapDbLookupIsolatedWellKnownSids(
        unsigned int a1,
        struct _LSAPR_SID **a2,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a3,
        struct _LSAPR_TRANSLATED_NAMES_EX *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v6; // r13d
  __int64 v7; // rbx
  unsigned int v8; // r14d
  struct _LSAPR_SID *v9; // r13
  __int64 v10; // r15
  int i; // ebx
  __int64 v12; // rdi
  void *v13; // rdx
  HLOCAL v14; // rax
  __int64 result; // rax
  __int64 v16; // rbx
  __int64 v17; // r9
  __int64 v18; // r15
  const UNICODE_STRING *v19; // rbx
  __int64 v20; // rsi
  HLOCAL v21; // rax
  int v22; // ecx
  PUCHAR v23; // rax
  ULONG v24; // ebx
  HLOCAL v25; // rax
  void *v26; // r15
  PUCHAR v27; // rax
  int v28; // ebx
  int v29; // r14d
  __int64 v30; // r15
  __int64 v31; // r15
  PSID v32; // rdi
  int v33; // ebx
  int v34; // esi
  __int64 v35; // r14
  unsigned int v36; // edi
  unsigned int v37; // ebx
  HLOCAL v38; // rax
  HLOCAL v39; // rsi
  void *v40; // r14
  __int64 v41; // rsi
  PSID v42; // rbx
  ULONG v43; // edi
  HLOCAL v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  void *v47; // rcx
  void *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // [rsp+28h] [rbp-49h]
  HLOCAL hMem; // [rsp+30h] [rbp-41h]
  int v52; // [rsp+3Ch] [rbp-35h]
  _BYTE DestinationString[24]; // [rsp+40h] [rbp-31h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-19h] BYREF
  PSID Sid; // [rsp+68h] [rbp-9h]
  __int64 v56; // [rsp+70h] [rbp-1h]
  struct _LSAPR_SID **v58; // [rsp+D0h] [rbp+5Fh]
  unsigned int v60; // [rsp+E0h] [rbp+6Fh]

  v58 = a2;
  v6 = a1;
  v7 = 0;
  v8 = 0;
  v50 = *((_QWORD *)a4 + 1);
  Sid = 0;
  hMem = 0;
  v60 = a1;
  v52 = 0;
  SourceString = 0;
  if ( !a1 )
    goto LABEL_18;
  while ( 1 )
  {
    v9 = a2[v7];
    v10 = (unsigned int)v7;
    for ( i = 0; ; ++i )
    {
      if ( i >= 80 )
        goto LABEL_15;
      v12 = 48LL * i;
      v13 = *(void **)((char *)WellKnownSids + v12);
      if ( v13 )
      {
        if ( RtlEqualSid(v9, v13) )
          break;
      }
    }
    if ( (unsigned int)(i - 16) > 1 )
      break;
LABEL_15:
    v6 = a1;
    v7 = (unsigned int)(v52 + 1);
    v52 = v7;
    if ( (unsigned int)v7 >= a1 )
      goto LABEL_16;
    a2 = v58;
  }
  v16 = 32;
  v17 = v50;
  if ( *(_DWORD *)((char *)WellKnownSids + v12 + 8) != 3 )
    v16 = 16;
  v18 = 32 * v10;
  v19 = (const UNICODE_STRING *)((char *)WellKnownSids + v12 + v16);
  v56 = v18;
  v20 = v18 + v50;
  *(UNICODE_STRING *)(v18 + v50 + 8) = *v19;
  if ( v19->Buffer )
  {
    if ( v19->MaximumLength )
    {
      v21 = LocalAlloc(0x40u, v19->MaximumLength);
      *(_QWORD *)(v20 + 16) = v21;
      if ( !v21 )
      {
        v8 = -1073741670;
        goto LABEL_72;
      }
      RtlCopyUnicodeString((PUNICODE_STRING)(v20 + 8), v19);
      v17 = v50;
    }
    else
    {
      *(_QWORD *)(v20 + 16) = 0;
    }
  }
  v22 = *(_DWORD *)((char *)WellKnownSids + v12 + 8);
  *(_DWORD *)(v18 + v17) = v22;
  if ( v22 == 3 )
  {
    Sid = v9;
    hMem = 0;
  }
  else
  {
    v23 = RtlSubAuthorityCountSid(v9);
    v8 = -1073741670;
    v24 = RtlLengthRequiredSid(*v23 - 1);
    v25 = LocalAlloc(0x40u, v24);
    hMem = v25;
    v26 = v25;
    if ( !v25 )
    {
      v6 = a1;
      goto LABEL_18;
    }
    memcpy_0(v25, v9, v24);
    v27 = RtlSubAuthorityCountSid(v26);
    v17 = v50;
    v9 = (struct _LSAPR_SID *)v26;
    --*v27;
    Sid = v26;
  }
  v28 = 0;
  v29 = *(_DWORD *)a3;
  v30 = *((_QWORD *)a3 + 1);
  *(_DWORD *)(v56 + v17 + 24) = -1;
  while ( v28 < v29 && v9 )
  {
    v47 = *(void **)(v30 + 24LL * v28 + 16);
    if ( v47 && RtlEqualSid(v47, v9) )
    {
      v49 = v56;
      *(_DWORD *)(v56 + v50 + 24) = v28;
      if ( *(_DWORD *)(v49 + v50) == 3 || *(_QWORD *)(v49 + v50 + 16) )
        --v60;
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      v8 = 0;
      goto LABEL_15;
    }
    ++v28;
  }
  v31 = v56;
  SourceString = *(UNICODE_STRING *)((char *)WellKnownSids + v12 + 32);
  if ( *(_DWORD *)(v56 + v50) != 3 && !*(_WORD *)(v20 + 8) )
  {
    *(_DWORD *)(v56 + v50) = 8;
    *(_WORD *)(v20 + 8) = 0;
    *(_WORD *)(v31 + v50 + 10) = 0;
    *(_QWORD *)(v31 + v50 + 16) = 0;
LABEL_50:
    v8 = 0;
LABEL_13:
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    goto LABEL_15;
  }
  --v60;
  v32 = Sid;
  v33 = 0;
  v34 = *(_DWORD *)a3;
  v35 = *((_QWORD *)a3 + 1);
  *(_DWORD *)(v56 + v50 + 24) = -1;
  memset(DestinationString, 0, sizeof(DestinationString));
  while ( v33 < v34 && v32 )
  {
    v48 = *(void **)(v35 + 24LL * v33 + 16);
    if ( v48 && RtlEqualSid(v48, v32) )
    {
      v8 = 0;
      *(_DWORD *)(v31 + v50 + 24) = v33;
      goto LABEL_13;
    }
    ++v33;
  }
  v36 = *((_DWORD *)a3 + 4);
  if ( *(_DWORD *)a3 < v36 || (v37 = v36 + 32, v36 >= v36 + 32) )
  {
LABEL_42:
    v41 = *(unsigned int *)a3;
    *(UNICODE_STRING *)DestinationString = SourceString;
    if ( SourceString.Buffer )
    {
      if ( SourceString.MaximumLength )
      {
        v14 = LocalAlloc(0x40u, SourceString.MaximumLength);
        *(_QWORD *)&DestinationString[8] = v14;
        if ( !v14 )
          goto LABEL_8;
        RtlCopyUnicodeString((PUNICODE_STRING)DestinationString, &SourceString);
      }
      else
      {
        *(_QWORD *)&DestinationString[8] = 0;
      }
    }
    v42 = Sid;
    if ( Sid )
    {
      v43 = RtlLengthSid(Sid);
      v44 = LocalAlloc(0x40u, v43);
      *(_QWORD *)&DestinationString[16] = v44;
      if ( !v44 )
        goto LABEL_7;
      memcpy_0(v44, v42, v43);
    }
    v45 = *((_QWORD *)a3 + 1);
    v46 = 3 * v41;
    *(_OWORD *)(v45 + 8 * v46) = *(_OWORD *)DestinationString;
    *(_QWORD *)(v45 + 8 * v46 + 16) = *(_QWORD *)&DestinationString[16];
    *(_DWORD *)(v31 + v50 + 24) = v41;
    ++*(_DWORD *)a3;
    goto LABEL_50;
  }
  v38 = LocalAlloc(0x40u, 24 * v37);
  v39 = v38;
  if ( v38 )
  {
    v40 = (void *)*((_QWORD *)a3 + 1);
    if ( v40 )
    {
      memcpy_0(v38, *((const void **)a3 + 1), 24 * v36);
      LocalFree(v40);
    }
    *((_QWORD *)a3 + 1) = v39;
    *((_DWORD *)a3 + 4) = v37;
    goto LABEL_42;
  }
LABEL_7:
  v14 = *(HLOCAL *)&DestinationString[8];
LABEL_8:
  v8 = -1073741670;
  if ( v14 )
    LocalFree(v14);
  if ( *(_QWORD *)&DestinationString[16] )
    LocalFree(*(HLOCAL *)&DestinationString[16]);
LABEL_72:
  v6 = a1;
LABEL_16:
  if ( hMem )
    LocalFree(hMem);
LABEL_18:
  result = v8;
  *a5 = v6 - v60;
  *a6 = v60;
  return result;
}

```

## disassembly

```asm
0x18003a0c0  mov     r11, rsp
0x18003a0c3  mov     [r11+18h], r8
0x18003a0c7  mov     [r11+10h], rdx
0x18003a0cb  mov     [rsp-8+arg_0], ecx
0x18003a0cf  push    rbp
0x18003a0d0  push    rbx
0x18003a0d1  push    r13
0x18003a0d3  push    r14
0x18003a0d5  lea     rbp, [r11-4Fh]
0x18003a0d9  sub     rsp, 98h
0x18003a0e0  mov     r13d, ecx
0x18003a0e3  xor     eax, eax
0x18003a0e5  mov     rcx, [r9+8]
0x18003a0e9  xor     ebx, ebx
0x18003a0eb  xor     r14d, r14d
0x18003a0ee  mov     [rbp+47h+var_90], rcx
0x18003a0f2  mov     [rbp+47h+Sid], rax
0x18003a0f6  xorps   xmm0, xmm0
0x18003a0f9  mov     [rbp+47h+hMem], rax
0x18003a0fd  mov     [rbp+47h+arg_18], r13d
0x18003a101  mov     [rbp+47h+var_7C], ebx
0x18003a104  movups  xmmword ptr [rbp+47h+SourceString.Length], xmm0
0x18003a108  test    r13d, r13d
0x18003a10b  jz      loc_18003A1F8
0x18003a111  mov     [r11-28h], rsi
0x18003a115  mov     esi, 10h
0x18003a11a  mov     [r11-30h], rdi
0x18003a11e  mov     [r11-40h], r15
0x18003a122  mov     [r11-38h], r12
0x18003a126  mov     r13, [rdx+rbx*8]
0x18003a12a  mov     r15d, ebx
0x18003a12d  xor     ebx, ebx
0x18003a12f  nop
0x18003a130  cmp     ebx, 50h ; 'P'
0x18003a133  jge     loc_18003A1BD
0x18003a139  movsxd  rax, ebx
0x18003a13c  lea     rdi, [rax+rax*2]
0x18003a140  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18003a147  shl     rdi, 4
0x18003a14b  mov     rdx, [rdi+rax]; Sid2
0x18003a14f  test    rdx, rdx
0x18003a152  jz      short loc_18003A16B
0x18003a154  mov     rcx, r13; Sid1
0x18003a157  call    cs:__imp_RtlEqualSid
0x18003a15e  nop     dword ptr [rax+rax+00h]
0x18003a163  test    al, al
0x18003a165  jnz     loc_18003A226
0x18003a16b  inc     ebx
0x18003a16d  jmp     short loc_18003A130
0x18003a16f  mov     rax, [rbp+47h+DestinationString.Buffer]
0x18003a173  mov     r14d, 0C000009Ah
0x18003a179  test    rax, rax
0x18003a17c  jnz     loc_18003A63B
0x18003a182  mov     rcx, [rbp+47h+var_68]; hMem
0x18003a186  test    rcx, rcx
0x18003a189  jnz     loc_18003A64F
0x18003a18f  test    r14d, r14d
0x18003a192  js      loc_18003A666
0x18003a198  mov     rax, [rbp+47h+hMem]
0x18003a19c  test    rax, rax
0x18003a19f  jz      short loc_18003A1B8
0x18003a1a1  mov     rcx, rax; hMem
0x18003a1a4  call    cs:__imp_LocalFree
0x18003a1ab  nop     dword ptr [rax+rax+00h]
0x18003a1b0  mov     [rbp+47h+hMem], 0
0x18003a1b8  mov     esi, 10h
0x18003a1bd  mov     ebx, [rbp+47h+var_7C]
0x18003a1c0  mov     r13d, [rbp+47h+arg_0]
0x18003a1c4  inc     ebx
0x18003a1c6  mov     [rbp+47h+var_7C], ebx
0x18003a1c9  cmp     ebx, r13d
0x18003a1cc  jb      short loc_18003A21D
0x18003a1ce  mov     rax, [rbp+47h+hMem]
0x18003a1d2  test    rax, rax
0x18003a1d5  jnz     loc_18003A66F
0x18003a1db  mov     r12, [rsp+0B0h+var_30]
0x18003a1e3  mov     rdi, [rsp+0B0h+var_28]
0x18003a1eb  mov     rsi, [rsp+90h]
0x18003a1f3  mov     r15, [rsp+0B0h+var_38]
0x18003a1f8  mov     rcx, [rbp+47h+arg_20]
0x18003a1fc  mov     eax, r14d
0x18003a1ff  mov     ebx, [rbp+47h+arg_18]
0x18003a202  sub     r13d, ebx
0x18003a205  mov     [rcx], r13d
0x18003a208  mov     rcx, [rbp+47h+arg_28]
0x18003a20c  mov     [rcx], ebx
0x18003a20e  add     rsp, 98h
0x18003a215  pop     r14
0x18003a217  pop     r13
0x18003a219  pop     rbx
0x18003a21a  pop     rbp
0x18003a21b  retn
0x18003a21d  mov     rdx, [rbp+47h+arg_8]
0x18003a221  jmp     loc_18003A126
0x18003a226  add     ebx, 0FFFFFFF0h
0x18003a229  cmp     ebx, 1
0x18003a22c  jbe     short loc_18003A1BD
0x18003a22e  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18003a235  mov     ebx, 20h ; ' '
0x18003a23a  mov     r9, [rbp+47h+var_90]
0x18003a23e  add     rcx, rdi
0x18003a241  cmp     dword ptr [rcx+8], 3
0x18003a245  cmovnz  rbx, rsi
0x18003a249  shl     r15, 5
0x18003a24d  add     rbx, rcx
0x18003a250  mov     [rbp+47h+var_48], r15
0x18003a254  lea     rsi, [r15+r9]
0x18003a258  movups  xmm0, xmmword ptr [rbx]
0x18003a25b  movups  xmmword ptr [rsi+8], xmm0
0x18003a25f  cmp     qword ptr [rbx+8], 0
0x18003a264  jz      short loc_18003A2AA
0x18003a266  movzx   eax, word ptr [rbx+2]
0x18003a26a  test    ax, ax
0x18003a26d  jz      loc_18003A5D3
0x18003a273  mov     edx, eax; uBytes
0x18003a275  mov     ecx, 40h ; '@'; uFlags
0x18003a27a  call    cs:__imp_LocalAlloc
0x18003a281  nop     dword ptr [rax+rax+00h]
0x18003a286  mov     [rsi+10h], rax
0x18003a28a  test    rax, rax
0x18003a28d  jz      loc_18003A660
0x18003a293  mov     rdx, rbx; SourceString
0x18003a296  lea     rcx, [rsi+8]; DestinationString
0x18003a29a  call    cs:__imp_RtlCopyUnicodeString
0x18003a2a1  nop     dword ptr [rax+rax+00h]
0x18003a2a6  mov     r9, [rbp+47h+var_90]
0x18003a2aa  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18003a2b1  xor     r12d, r12d
0x18003a2b4  mov     [rbp+47h+var_80], r12d
0x18003a2b8  mov     ecx, [rdi+rax+8]
0x18003a2bc  mov     [r15+r9], ecx
0x18003a2c0  cmp     ecx, 3
0x18003a2c3  jz      loc_18003A544
0x18003a2c9  mov     rcx, r13; Sid
0x18003a2cc  call    cs:__imp_RtlSubAuthorityCountSid
0x18003a2d3  nop     dword ptr [rax+rax+00h]
0x18003a2d8  mov     r14d, 0C000009Ah
0x18003a2de  movzx   ecx, byte ptr [rax]
0x18003a2e1  dec     ecx; SubAuthorityCount
0x18003a2e3  call    cs:__imp_RtlLengthRequiredSid
0x18003a2ea  nop     dword ptr [rax+rax+00h]
0x18003a2ef  mov     edx, eax; uBytes
0x18003a2f1  mov     ecx, 40h ; '@'; uFlags
0x18003a2f6  mov     ebx, eax
0x18003a2f8  call    cs:__imp_LocalAlloc
0x18003a2ff  nop     dword ptr [rax+rax+00h]
0x18003a304  mov     [rbp+47h+hMem], rax
0x18003a308  mov     r15, rax
0x18003a30b  test    rax, rax
0x18003a30e  jz      loc_18003A5ED
0x18003a314  mov     r8d, ebx; Size
0x18003a317  mov     rdx, r13; Src
0x18003a31a  mov     rcx, rax; void *
0x18003a31d  call    memcpy_0
0x18003a322  mov     rcx, r15; Sid
0x18003a325  call    cs:__imp_RtlSubAuthorityCountSid
0x18003a32c  nop     dword ptr [rax+rax+00h]
0x18003a331  mov     r9, [rbp+47h+var_90]
0x18003a335  mov     r13, r15
0x18003a338  dec     byte ptr [rax]
0x18003a33a  mov     [rbp+47h+Sid], r15
0x18003a33e  mov     r8, [rbp+47h+arg_10]
0x18003a342  xor     ebx, ebx
0x18003a344  mov     rax, [rbp+47h+var_48]
0x18003a348  mov     r14d, [r8]
0x18003a34b  mov     r15, [r8+8]
0x18003a34f  mov     dword ptr [rax+r9+18h], 0FFFFFFFFh
0x18003a358  cmp     ebx, r14d
0x18003a35b  jl      loc_18003A502
0x18003a361  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18003a368  mov     r15, [rbp+47h+var_48]
0x18003a36c  add     rcx, rdi
0x18003a36f  mov     r9, [rbp+47h+var_90]
0x18003a373  movzx   eax, word ptr [rcx+20h]
0x18003a377  mov     [rbp+47h+SourceString.Length], ax
0x18003a37b  movzx   eax, word ptr [rcx+22h]
0x18003a37f  mov     [rbp+47h+SourceString.MaximumLength], ax
0x18003a383  mov     eax, [rcx+24h]
0x18003a386  mov     dword ptr [rbp+47h+SourceString+4], eax
0x18003a389  mov     rax, [rcx+28h]
0x18003a38d  mov     [rbp+47h+SourceString.Buffer], rax
0x18003a391  cmp     dword ptr [r15+r9], 3
0x18003a396  jz      short loc_18003A3A3
0x18003a398  cmp     word ptr [rsi+8], 0
0x18003a39d  jz      loc_18003A5F6
0x18003a3a3  mov     r13, [rbp+47h+arg_10]
0x18003a3a7  xorps   xmm0, xmm0
0x18003a3aa  dec     [rbp+47h+arg_18]
0x18003a3ad  mov     rdi, [rbp+47h+Sid]
0x18003a3b1  xor     ebx, ebx
0x18003a3b3  mov     r12d, [rbp+47h+var_80]
0x18003a3b7  mov     esi, [r13+0]
0x18003a3bb  mov     r14, [r13+8]
0x18003a3bf  mov     dword ptr [r15+r9+18h], 0FFFFFFFFh
0x18003a3c8  mov     qword ptr [rbp+47h+DestinationString.Length], 0
0x18003a3d0  movdqu  xmmword ptr [rbp+47h+DestinationString.Buffer], xmm0
0x18003a3d5  cmp     ebx, esi
0x18003a3d7  jl      loc_18003A523
0x18003a3dd  mov     edi, [r13+10h]
0x18003a3e1  cmp     [r13+0], edi
0x18003a3e5  jb      short loc_18003A426
0x18003a3e7  lea     ebx, [rdi+20h]
0x18003a3ea  cmp     edi, ebx
0x18003a3ec  jnb     short loc_18003A426
0x18003a3ee  lea     edx, [rbx+rbx*2]
0x18003a3f1  mov     ecx, 40h ; '@'; uFlags
0x18003a3f6  shl     edx, 3; uBytes
0x18003a3f9  call    cs:__imp_LocalAlloc
0x18003a400  nop     dword ptr [rax+rax+00h]
0x18003a405  mov     rsi, rax
0x18003a408  test    rax, rax
0x18003a40b  jz      loc_18003A16F
0x18003a411  mov     r14, [r13+8]
0x18003a415  test    r14, r14
0x18003a418  jnz     loc_18003A614
0x18003a41e  mov     [r13+8], rsi
0x18003a422  mov     [r13+10h], ebx
0x18003a426  movzx   eax, [rbp+47h+SourceString.Length]
0x18003a42a  movzx   ecx, [rbp+47h+SourceString.MaximumLength]
0x18003a42e  mov     esi, [r13+0]
0x18003a432  mov     [rbp+47h+DestinationString.Length], ax
0x18003a436  mov     eax, dword ptr [rbp+47h+SourceString+4]
0x18003a439  mov     dword ptr [rbp+47h+DestinationString+4], eax
0x18003a43c  mov     rax, [rbp+47h+SourceString.Buffer]
0x18003a440  mov     [rbp+47h+DestinationString.MaximumLength], cx
0x18003a444  mov     [rbp+47h+DestinationString.Buffer], rax
0x18003a448  test    rax, rax
0x18003a44b  jz      short loc_18003A48A
0x18003a44d  test    cx, cx
0x18003a450  jz      loc_18003A5E0
0x18003a456  mov     edx, ecx; uBytes
0x18003a458  mov     ecx, 40h ; '@'; uFlags
0x18003a45d  call    cs:__imp_LocalAlloc
0x18003a464  nop     dword ptr [rax+rax+00h]
0x18003a469  mov     [rbp+47h+DestinationString.Buffer], rax
0x18003a46d  test    rax, rax
0x18003a470  jz      loc_18003A173
0x18003a476  lea     rdx, [rbp+47h+SourceString]; SourceString
0x18003a47a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18003a47e  call    cs:__imp_RtlCopyUnicodeString
0x18003a485  nop     dword ptr [rax+rax+00h]
0x18003a48a  mov     rbx, [rbp+47h+Sid]
0x18003a48e  test    rbx, rbx
0x18003a491  jz      short loc_18003A4D2
0x18003a493  mov     rcx, rbx; Sid
0x18003a496  call    cs:__imp_RtlLengthSid
0x18003a49d  nop     dword ptr [rax+rax+00h]
0x18003a4a2  mov     edx, eax; uBytes
0x18003a4a4  mov     ecx, 40h ; '@'; uFlags
0x18003a4a9  mov     edi, eax
0x18003a4ab  call    cs:__imp_LocalAlloc
0x18003a4b2  nop     dword ptr [rax+rax+00h]
0x18003a4b7  mov     [rbp+47h+var_68], rax
0x18003a4bb  test    rax, rax
0x18003a4be  jz      loc_18003A16F
0x18003a4c4  mov     r8d, edi; Size
0x18003a4c7  mov     rdx, rbx; Src
0x18003a4ca  mov     rcx, rax; void *
0x18003a4cd  call    memcpy_0
0x18003a4d2  mov     rax, [r13+8]
0x18003a4d6  lea     rcx, [rsi+rsi*2]
0x18003a4da  movups  xmm0, xmmword ptr [rbp+47h+DestinationString.Length]
0x18003a4de  movups  xmmword ptr [rax+rcx*8], xmm0
0x18003a4e2  movsd   xmm1, [rbp+47h+var_68]
0x18003a4e7  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18003a4ed  mov     rcx, [rbp+47h+var_90]
0x18003a4f1  mov     [r15+rcx+18h], esi
0x18003a4f6  inc     dword ptr [r13+0]
0x18003a4fa  mov     r14d, r12d
0x18003a4fd  jmp     loc_18003A198
0x18003a502  test    r13, r13
0x18003a505  jz      loc_18003A361
0x18003a50b  movsxd  rax, ebx
0x18003a50e  lea     rcx, [rax+rax*2]
0x18003a512  mov     rcx, [r15+rcx*8+10h]; Sid1
0x18003a517  test    rcx, rcx
0x18003a51a  jnz     short loc_18003A553
0x18003a51c  inc     ebx
0x18003a51e  jmp     loc_18003A358
0x18003a523  test    rdi, rdi
0x18003a526  jz      loc_18003A3DD
0x18003a52c  movsxd  rax, ebx
0x18003a52f  lea     rcx, [rax+rax*2]
0x18003a533  mov     rcx, [r14+rcx*8+10h]; Sid1
0x18003a538  test    rcx, rcx
0x18003a53b  jnz     short loc_18003A5AB
0x18003a53d  inc     ebx
0x18003a53f  jmp     loc_18003A3D5
0x18003a544  xor     eax, eax
0x18003a546  mov     [rbp+47h+Sid], r13
0x18003a54a  mov     [rbp+47h+hMem], rax
0x18003a54e  jmp     loc_18003A33E
0x18003a553  mov     rdx, r13; Sid2
0x18003a556  call    cs:__imp_RtlEqualSid
0x18003a55d  nop     dword ptr [rax+rax+00h]
0x18003a562  test    al, al
0x18003a564  jz      short loc_18003A51C
0x18003a566  mov     rax, [rbp+47h+var_48]
0x18003a56a  mov     r9, [rbp+47h+var_90]
0x18003a56e  mov     [rax+r9+18h], ebx
  ... truncated ...
```

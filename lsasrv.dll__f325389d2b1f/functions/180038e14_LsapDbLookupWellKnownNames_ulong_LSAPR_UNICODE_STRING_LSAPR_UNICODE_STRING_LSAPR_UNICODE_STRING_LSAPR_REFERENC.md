# LsapDbLookupWellKnownNames(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x180038e14`
- end: `0x180039156`
- name: `?LsapDbLookupWellKnownNames@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK3@Z`
- size: `834`
- prototype: `__int64 __fastcall(unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800388a0`

## callees

- `0x180038530`
- `0x180038e14`
- `0x180039400`
- `0x180039b10`
- `0x180039c10`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039136`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039000`
- `ntdll!RtlSubAuthorityCountSid` at `0x180038f9e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180039029`
- `ntdll!RtlSubAuthorityCountSid` at `0x180038f9e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180039029`
- `ntdll!RtlSubAuthoritySid` at `0x180038fdc`
- `ntdll!RtlSubAuthoritySid` at `0x180038fdc`
- `ntdll!RtlLengthRequiredSid` at `0x180038feb`
- `ntdll!RtlLengthRequiredSid` at `0x180038feb`
- `ntdll!RtlEqualUnicodeString` at `0x180038ec3`
- `ntdll!RtlEqualUnicodeString` at `0x180038ee7`
- `ntdll!RtlEqualUnicodeString` at `0x180038f0b`
- `ntdll!RtlEqualUnicodeString` at `0x180038f2d`
- `ntdll!RtlEqualUnicodeString` at `0x180038ec3`
- `ntdll!RtlEqualUnicodeString` at `0x180038ee7`
- `ntdll!RtlEqualUnicodeString` at `0x180038f0b`
- `ntdll!RtlEqualUnicodeString` at `0x180038f2d`

## pseudocode

```c
__int64 __fastcall LsapDbLookupWellKnownNames(
        unsigned int a1,
        struct _LSAPR_UNICODE_STRING *a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a5,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned int v8; // esi
  __int64 v10; // r14
  struct _LSAPR_UNICODE_STRING *v11; // rax
  __int64 v12; // r15
  int v13; // edi
  void *v14; // rbx
  unsigned int v15; // ebp
  __int64 v16; // r13
  __int64 v17; // r14
  const UNICODE_STRING *v18; // r15
  unsigned __int8 v19; // al
  __int64 v20; // r14
  void *v21; // rdi
  int v22; // edx
  int v23; // ecx
  int v24; // ebx
  SIZE_T v25; // rsi
  HLOCAL v26; // rax
  PUCHAR v27; // rax
  __int64 v28; // rsi
  int v29; // eax
  struct _LSAPR_TRANSLATED_SIDS_EX2 *v30; // rax
  __int64 v32; // [rsp+20h] [rbp-68h]
  __int128 v33; // [rsp+28h] [rbp-60h] BYREF
  void *v34; // [rsp+38h] [rbp-50h]
  int v35; // [rsp+90h] [rbp+8h] BYREF
  struct _LSAPR_UNICODE_STRING *v36; // [rsp+98h] [rbp+10h]
  struct _LSAPR_UNICODE_STRING *v37; // [rsp+A0h] [rbp+18h]
  struct _LSAPR_UNICODE_STRING *v38; // [rsp+A8h] [rbp+20h]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v8 = 0;
  v35 = 0;
  v10 = 0;
  v11 = a3;
  v12 = *((_QWORD *)a6 + 1);
  v13 = 0;
  v33 = 0;
  v34 = 0;
  v14 = 0;
  v15 = a1;
  v32 = v12;
  *a7 = 0;
  while ( 1 )
  {
    LODWORD(v36) = v10;
    if ( (unsigned int)v10 >= a1 || !v15 )
      break;
    v16 = 3 * v10;
    if ( *(_DWORD *)(v12 + 24 * v10) != 8 )
      goto LABEL_33;
    v17 = 16 * v10;
    v18 = (const UNICODE_STRING *)((char *)v11 + v17);
    if ( *(_WORD *)((char *)v11 + v17) )
    {
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v11 + v17), (PCUNICODE_STRING)WellKnownSids + 47, 1u)
        || RtlEqualUnicodeString(v18, (PCUNICODE_STRING)WellKnownSids + 107, 1u)
        || RtlEqualUnicodeString(v18, (PCUNICODE_STRING)WellKnownSids + 239, 1u) )
      {
        v8 = 1;
      }
    }
    else
    {
      v8 = 3;
    }
    if ( RtlEqualUnicodeString(v18, &NTAuthorityName, 1u) )
    {
      v8 = (v8 != 0) + 2;
    }
    else if ( !v8 )
    {
      v8 = 0;
      goto LABEL_31;
    }
    v19 = LsapDbLookupIndexWellKnownName(
            (PCUNICODE_STRING)((char *)v38 + v17),
            (enum _LSAP_WELL_KNOWN_SID_INDEX *)&v35,
            v8);
    v8 = 0;
    if ( v19 && (unsigned int)(v35 - 16) > 1 )
    {
      v20 = 6LL * v35;
      v21 = (void *)*((_QWORD *)WellKnownSids + 6 * v35);
      v12 = v32;
      v22 = *RtlSubAuthorityCountSid(v21);
      v23 = *((_DWORD *)WellKnownSids + 2 * v20 + 2);
      *(_DWORD *)(v32 + 8 * v16) = v23;
      if ( v23 == 3 )
      {
        v14 = 0;
        v34 = v21;
      }
      else
      {
        v24 = v22;
        if ( (_BYTE)v22 )
          RtlSubAuthoritySid(v21, v22 - 1);
        v25 = RtlLengthRequiredSid(v24 - 1);
        v26 = LocalAlloc(0x40u, v25);
        v14 = v26;
        if ( !v26 )
          return (unsigned int)-1073741670;
        memcpy_0(v26, v21, (unsigned int)v25);
        v27 = RtlSubAuthorityCountSid(v14);
        --*v27;
        v34 = v14;
      }
      v13 = LsapRpcCopySid(0, v32 + 8 + 8 * v16, v21);
      if ( v13 < 0 )
        goto LABEL_37;
      v28 = v32 + 8 * v16;
      if ( (unsigned __int8)LsapDbLookupListReferencedDomains(a5, v34, v28 + 16) )
      {
        --v15;
        v8 = 0;
        if ( v14 )
        {
          LocalFree(v14);
          v14 = 0;
        }
      }
      else
      {
        v33 = *(_OWORD *)((char *)WellKnownSids + 8 * v20 + 32);
        v29 = LsapDbLookupAddListReferencedDomains(a5, &v33, v28 + 16);
        v8 = 0;
        v13 = v29;
        if ( v29 < 0 )
          goto LABEL_37;
        if ( v14 )
        {
          LocalFree(v14);
          v14 = 0;
        }
        --v15;
      }
      goto LABEL_32;
    }
LABEL_31:
    v12 = v32;
LABEL_32:
    v11 = v37;
LABEL_33:
    v10 = (unsigned int)((_DWORD)v36 + 1);
  }
  if ( v13 >= 0 )
  {
    v30 = a6;
    *(_DWORD *)a6 = a1;
    *((_QWORD *)v30 + 1) = v12;
    *a7 = a1 - v15;
    *a8 = v15;
  }
LABEL_37:
  if ( v14 )
    LocalFree(v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180038e14  mov     r11, rsp
0x180038e17  mov     [r11+20h], r9
0x180038e1b  mov     [r11+18h], r8
0x180038e1f  mov     [r11+10h], rdx
0x180038e23  push    rbx
0x180038e24  push    rbp
0x180038e25  push    rsi
0x180038e26  push    rdi
0x180038e27  push    r12
0x180038e29  push    r13
0x180038e2b  push    r14
0x180038e2d  push    r15
0x180038e2f  sub     rsp, 48h
0x180038e33  mov     r15, [rsp+88h+arg_28]
0x180038e3b  xor     esi, esi
0x180038e3d  mov     r12d, ecx
0x180038e40  mov     [r11+8], esi
0x180038e44  xor     ecx, ecx
0x180038e46  mov     r14d, esi
0x180038e49  xorps   xmm0, xmm0
0x180038e4c  mov     rax, r8
0x180038e4f  mov     r15, [r15+8]
0x180038e53  mov     edi, esi
0x180038e55  movups  [rsp+88h+var_60], xmm0
0x180038e5a  mov     [r11-50h], rcx
0x180038e5e  mov     ebx, esi
0x180038e60  mov     rcx, [rsp+88h+arg_30]
0x180038e68  mov     ebp, r12d
0x180038e6b  mov     [rsp+88h+var_68], r15
0x180038e70  mov     [rcx], esi
0x180038e72  mov     dword ptr [rsp+88h+arg_8], r14d
0x180038e7a  cmp     r14d, r12d
0x180038e7d  jnb     loc_180039103
0x180038e83  test    ebp, ebp
0x180038e85  jz      loc_180039103
0x180038e8b  lea     r13, [r14+r14*2]
0x180038e8f  cmp     dword ptr [r15+r13*8], 8
0x180038e94  jnz     loc_1800390EC
0x180038e9a  shl     r14, 4
0x180038e9e  lea     r15, [r14+rax]
0x180038ea2  cmp     [r15], si
0x180038ea6  jnz     short loc_180038EAF
0x180038ea8  mov     esi, 3
0x180038ead  jmp     short loc_180038F20
0x180038eaf  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180038eb6  mov     r8b, 1; CaseInsensitive
0x180038eb9  add     rdx, 2F0h; String2
0x180038ec0  mov     rcx, r15; String1
0x180038ec3  call    cs:__imp_RtlEqualUnicodeString
0x180038eca  nop     dword ptr [rax+rax+00h]
0x180038ecf  test    al, al
0x180038ed1  jnz     short loc_180038F1B
0x180038ed3  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180038eda  mov     r8b, 1; CaseInsensitive
0x180038edd  add     rdx, 6B0h; String2
0x180038ee4  mov     rcx, r15; String1
0x180038ee7  call    cs:__imp_RtlEqualUnicodeString
0x180038eee  nop     dword ptr [rax+rax+00h]
0x180038ef3  test    al, al
0x180038ef5  jnz     short loc_180038F1B
0x180038ef7  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180038efe  mov     r8b, 1; CaseInsensitive
0x180038f01  add     rdx, 0EF0h; String2
0x180038f08  mov     rcx, r15; String1
0x180038f0b  call    cs:__imp_RtlEqualUnicodeString
0x180038f12  nop     dword ptr [rax+rax+00h]
0x180038f17  test    al, al
0x180038f19  jz      short loc_180038F20
0x180038f1b  mov     esi, 1
0x180038f20  mov     r8b, 1; CaseInsensitive
0x180038f23  lea     rdx, ?NTAuthorityName@@3U_UNICODE_STRING@@A; String2
0x180038f2a  mov     rcx, r15; String1
0x180038f2d  call    cs:__imp_RtlEqualUnicodeString
0x180038f34  nop     dword ptr [rax+rax+00h]
0x180038f39  test    al, al
0x180038f3b  jz      short loc_180038F48
0x180038f3d  neg     esi
0x180038f3f  sbb     esi, esi
0x180038f41  neg     esi
0x180038f43  add     esi, 2
0x180038f46  jmp     short loc_180038F50
0x180038f48  test    esi, esi
0x180038f4a  jz      loc_1800390DD
0x180038f50  mov     rcx, [rsp+88h+arg_18]
0x180038f58  lea     rdx, [rsp+88h+arg_0]; enum _LSAP_WELL_KNOWN_SID_INDEX *
0x180038f60  add     rcx, r14; String1
0x180038f63  mov     r8d, esi; unsigned int
0x180038f66  call    ?LsapDbLookupIndexWellKnownName@@YAEPEAU_LSAPR_UNICODE_STRING@@PEAW4_LSAP_WELL_KNOWN_SID_INDEX@@K@Z; LsapDbLookupIndexWellKnownName(_LSAPR_UNICODE_STRING *,_LSAP_WELL_KNOWN_SID_INDEX *,ulong)
0x180038f6b  xor     esi, esi
0x180038f6d  test    al, al
0x180038f6f  jz      loc_1800390DF
0x180038f75  movsxd  rcx, [rsp+88h+arg_0]
0x180038f7d  lea     eax, [rcx-10h]
0x180038f80  cmp     eax, 1
0x180038f83  jbe     loc_1800390DF
0x180038f89  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180038f90  lea     r14, [rcx+rcx*2]
0x180038f94  add     r14, r14
0x180038f97  mov     rdi, [rax+r14*8]
0x180038f9b  mov     rcx, rdi; Sid
0x180038f9e  call    cs:__imp_RtlSubAuthorityCountSid
0x180038fa5  nop     dword ptr [rax+rax+00h]
0x180038faa  mov     r15, [rsp+88h+var_68]
0x180038faf  movzx   edx, byte ptr [rax]
0x180038fb2  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180038fb9  mov     ecx, [rax+r14*8+8]
0x180038fbe  mov     [r15+r13*8], ecx
0x180038fc2  cmp     ecx, 3
0x180038fc5  jnz     short loc_180038FD0
0x180038fc7  mov     ebx, esi
0x180038fc9  mov     [rsp+88h+var_50], rdi
0x180038fce  jmp     short loc_18003903C
0x180038fd0  mov     ebx, edx
0x180038fd2  test    dl, dl
0x180038fd4  jz      short loc_180038FE8
0x180038fd6  lea     edx, [rbx-1]; SubAuthority
0x180038fd9  mov     rcx, rdi; Sid
0x180038fdc  call    cs:__imp_RtlSubAuthoritySid
0x180038fe3  nop     dword ptr [rax+rax+00h]
0x180038fe8  lea     ecx, [rbx-1]; SubAuthorityCount
0x180038feb  call    cs:__imp_RtlLengthRequiredSid
0x180038ff2  nop     dword ptr [rax+rax+00h]
0x180038ff7  mov     edx, eax; uBytes
0x180038ff9  mov     ecx, 40h ; '@'; uFlags
0x180038ffe  mov     esi, eax
0x180039000  call    cs:__imp_LocalAlloc
0x180039007  nop     dword ptr [rax+rax+00h]
0x18003900c  mov     rbx, rax
0x18003900f  test    rax, rax
0x180039012  jz      loc_1800390FC
0x180039018  mov     r8d, esi; Size
0x18003901b  mov     rdx, rdi; Src
0x18003901e  mov     rcx, rax; void *
0x180039021  call    memcpy_0
0x180039026  mov     rcx, rbx; Sid
0x180039029  call    cs:__imp_RtlSubAuthorityCountSid
0x180039030  nop     dword ptr [rax+rax+00h]
0x180039035  dec     byte ptr [rax]
0x180039037  mov     [rsp+88h+var_50], rbx
0x18003903c  lea     rdx, [r15+8]
0x180039040  mov     r8, rdi
0x180039043  lea     rdx, [rdx+r13*8]
0x180039047  xor     ecx, ecx
0x180039049  call    LsapRpcCopySid
0x18003904e  mov     edi, eax
0x180039050  test    eax, eax
0x180039052  js      loc_18003912E
0x180039058  mov     rdx, [rsp+88h+var_50]
0x18003905d  lea     rsi, [r15+r13*8]
0x180039061  mov     rcx, [rsp+88h+arg_20]
0x180039069  lea     r8, [rsi+10h]
0x18003906d  call    LsapDbLookupListReferencedDomains
0x180039072  test    al, al
0x180039074  jz      short loc_180039092
0x180039076  dec     ebp
0x180039078  xor     esi, esi
0x18003907a  test    rbx, rbx
0x18003907d  jz      short loc_1800390E4
0x18003907f  mov     rcx, rbx; hMem
0x180039082  call    cs:__imp_LocalFree
0x180039089  nop     dword ptr [rax+rax+00h]
0x18003908e  mov     ebx, esi
0x180039090  jmp     short loc_1800390E4
0x180039092  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180039099  lea     r8, [rsi+10h]
0x18003909d  mov     rcx, [rsp+88h+arg_20]
0x1800390a5  lea     rdx, [rsp+88h+var_60]
0x1800390aa  movups  xmm0, xmmword ptr [rax+r14*8+20h]
0x1800390b0  movdqu  [rsp+88h+var_60], xmm0
0x1800390b6  call    LsapDbLookupAddListReferencedDomains
0x1800390bb  xor     esi, esi
0x1800390bd  mov     edi, eax
0x1800390bf  test    eax, eax
0x1800390c1  js      short loc_18003912E
0x1800390c3  test    rbx, rbx
0x1800390c6  jz      short loc_1800390D9
0x1800390c8  mov     rcx, rbx; hMem
0x1800390cb  call    cs:__imp_LocalFree
0x1800390d2  nop     dword ptr [rax+rax+00h]
0x1800390d7  mov     ebx, esi
0x1800390d9  dec     ebp
0x1800390db  jmp     short loc_1800390E4
0x1800390dd  xor     esi, esi
0x1800390df  mov     r15, [rsp+88h+var_68]
0x1800390e4  mov     rax, [rsp+88h+arg_10]
0x1800390ec  mov     r14d, dword ptr [rsp+88h+arg_8]
0x1800390f4  inc     r14d
0x1800390f7  jmp     loc_180038E72
0x1800390fc  mov     edi, 0C000009Ah
0x180039101  jmp     short loc_180039142
0x180039103  test    edi, edi
0x180039105  js      short loc_18003912E
0x180039107  mov     rax, [rsp+88h+arg_28]
0x18003910f  mov     [rax], r12d
0x180039112  sub     r12d, ebp
0x180039115  mov     [rax+8], r15
0x180039119  mov     rax, [rsp+88h+arg_30]
0x180039121  mov     [rax], r12d
0x180039124  mov     rax, [rsp+88h+arg_38]
0x18003912c  mov     [rax], ebp
0x18003912e  test    rbx, rbx
0x180039131  jz      short loc_180039142
0x180039133  mov     rcx, rbx; hMem
0x180039136  call    cs:__imp_LocalFree
0x18003913d  nop     dword ptr [rax+rax+00h]
0x180039142  mov     eax, edi
0x180039144  add     rsp, 48h
0x180039148  pop     r15
0x18003914a  pop     r14
0x18003914c  pop     r13
0x18003914e  pop     r12
0x180039150  pop     rdi
0x180039151  pop     rsi
0x180039152  pop     rbp
0x180039153  pop     rbx
0x180039154  retn
```

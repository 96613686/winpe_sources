# LsapTranslateLogonSessionSids(ulong,ulong,_LSAPR_SID * *,_LSAPR_SID * *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAPR_REFERENCED_DOMAIN_LIST * *,ulong *,ulong *)

- ea: `0x1800143e0`
- end: `0x18001494d`
- name: `?LsapTranslateLogonSessionSids@@YAJKKPEAPEAU_LSAPR_SID@@0PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAK3@Z`
- size: `1389`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _LSAPR_SID **, struct _LSAPR_SID **, struct _LSAPR_TRANSLATED_NAMES_EX *, struct _LSAPR_REFERENCED_DOMAIN_LIST **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011cdc`

## callees

- `0x1800143e0`
- `0x180014954`
- `0x1800b86d0`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014916`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001492a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014916`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001492a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014680`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014725`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014798`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014680`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014725`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014798`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147f2`
- `ntdll!RtlSubAuthorityCountSid` at `0x180014486`
- `ntdll!RtlSubAuthorityCountSid` at `0x180014486`
- `ntdll!RtlSubAuthoritySid` at `0x180014507`
- `ntdll!RtlSubAuthoritySid` at `0x1800145a4`
- `ntdll!RtlSubAuthoritySid` at `0x1800145bc`
- `ntdll!RtlSubAuthoritySid` at `0x180014507`
- `ntdll!RtlSubAuthoritySid` at `0x1800145a4`
- `ntdll!RtlSubAuthoritySid` at `0x1800145bc`
- `ntdll!RtlCopyUnicodeString` at `0x1800146a1`
- `ntdll!RtlCopyUnicodeString` at `0x1800147bc`
- `ntdll!RtlCopyUnicodeString` at `0x1800146a1`
- `ntdll!RtlCopyUnicodeString` at `0x1800147bc`
- `ntdll!RtlLengthSid` at `0x1800147dc`
- `ntdll!RtlLengthSid` at `0x1800147dc`
- `ntdll!RtlEqualSid` at `0x180014874`
- `ntdll!RtlEqualSid` at `0x180014874`
- `ntdll!RtlInitUnicodeString` at `0x1800145fc`
- `ntdll!RtlInitUnicodeString` at `0x180014610`
- `ntdll!RtlInitUnicodeString` at `0x1800145fc`
- `ntdll!RtlInitUnicodeString` at `0x180014610`

## pseudocode

```c
__int64 __fastcall LsapTranslateLogonSessionSids(
        unsigned int a1,
        unsigned int a2,
        struct _LSAPR_SID **a3,
        struct _LSAPR_SID **a4,
        struct _LSAPR_TRANSLATED_NAMES_EX *a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST **a6,
        unsigned int *a7,
        unsigned int *a8)
{
  int v9; // r13d
  struct _LSAPR_TRANSLATED_NAMES_EX *v10; // rax
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r15
  struct _LSAPR_SID *v15; // rdi
  struct _LSAPR_TRANSLATED_NAMES_EX *v17; // rcx
  struct _LSAPR_SID *v18; // rcx
  ULONG v19; // edi
  struct _LSAPR_TRANSLATED_NAMES_EX *v20; // rcx
  __int64 v21; // rdi
  HLOCAL v22; // rax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v23; // rdi
  HLOCAL v24; // rdx
  void *v25; // r13
  unsigned int *v26; // rax
  int v27; // r12d
  int v28; // r15d
  unsigned int v29; // r12d
  unsigned int v30; // r15d
  HLOCAL v31; // r13
  void *v32; // rax
  unsigned int v33; // edx
  HLOCAL v34; // rax
  const void *v35; // r15
  SIZE_T v36; // r12
  HLOCAL v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  void *v40; // rcx
  __int64 v41; // [rsp+28h] [rbp-E0h]
  HLOCAL v42; // [rsp+38h] [rbp-D0h]
  HLOCAL v43; // [rsp+38h] [rbp-D0h]
  unsigned int v44; // [rsp+38h] [rbp-D0h]
  struct _LSAPR_SID **v45; // [rsp+40h] [rbp-C8h]
  _BYTE v46[24]; // [rsp+48h] [rbp-C0h] BYREF
  struct _LSAPR_TRANSLATED_NAMES_EX *v47; // [rsp+60h] [rbp-A8h]
  _BYTE v48[24]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v49; // [rsp+80h] [rbp-88h]
  unsigned int *v50; // [rsp+88h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-78h] BYREF
  UNICODE_STRING v52; // [rsp+A0h] [rbp-68h] BYREF
  struct _LSAPR_REFERENCED_DOMAIN_LIST **v53; // [rsp+B0h] [rbp-58h]
  struct _LSAPR_SID **v54; // [rsp+B8h] [rbp-50h]
  unsigned int *v55; // [rsp+C0h] [rbp-48h]
  unsigned int *v56; // [rsp+C8h] [rbp-40h]
  WCHAR SourceString[104]; // [rsp+D8h] [rbp-30h] BYREF

  v9 = 0;
  v10 = a5;
  v11 = 0;
  v56 = a7;
  v12 = 0;
  v53 = a6;
  v55 = a8;
  v54 = a4;
  v45 = a3;
  v49 = a1;
  v47 = a5;
  if ( a1 )
  {
    while ( 1 )
    {
      if ( (unsigned int)v12 >= a2 )
        goto LABEL_8;
      v13 = *((_QWORD *)v10 + 1);
      v14 = 32LL * (unsigned int)v11;
      if ( *(_DWORD *)(v14 + v13 + 24) == -1 && *(_DWORD *)(v14 + v13) == 8 )
        break;
LABEL_7:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= v49 )
        goto LABEL_8;
      v10 = v47;
    }
    v15 = a3[v11];
    if ( *RtlSubAuthorityCountSid(v15) != 3
      || *RtlSubAuthoritySid(v15, 0) != 5
      || *((_BYTE *)v15 + 2)
      || *((_BYTE *)v15 + 3)
      || *((_BYTE *)v15 + 4)
      || *((_BYTE *)v15 + 5)
      || *((_BYTE *)v15 + 6)
      || *((_BYTE *)v15 + 7) != 5 )
    {
      a3 = v45;
      v54[v12] = v45[v11];
      v55[v12] = v11;
      v12 = (unsigned int)(v12 + 1);
      goto LABEL_7;
    }
    v17 = v47;
    memset(v48, 0, sizeof(v48));
    *(_DWORD *)(v14 + *((_QWORD *)v47 + 1)) = 11;
    *(_DWORD *)(v14 + *((_QWORD *)v17 + 1) + 24) = 0;
    v18 = v45[v11];
    v52 = 0;
    DestinationString = 0;
    v19 = *RtlSubAuthoritySid(v18, 1u);
    LODWORD(v41) = *RtlSubAuthoritySid(v45[v11], 2u);
    v9 = RtlStringCchPrintfW(SourceString, 0x64u, L"LogonSessionId_%lu_%lu", v19, v41);
    if ( v9 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"NT AUTHORITY");
      RtlInitUnicodeString(&v52, SourceString);
      *(struct _UNICODE_STRING *)v48 = DestinationString;
      *(_QWORD *)&v48[16] = *((_QWORD *)WellKnownSids + 42);
      v20 = v47;
      v21 = v14 + *((_QWORD *)v47 + 1);
      *(UNICODE_STRING *)(v21 + 8) = v52;
      if ( v52.Buffer )
      {
        if ( v52.MaximumLength )
        {
          v22 = LocalAlloc(0x40u, v52.MaximumLength);
          *(_QWORD *)(v21 + 16) = v22;
          if ( !v22 )
          {
            v9 = -1073741670;
            goto LABEL_8;
          }
          RtlCopyUnicodeString((PUNICODE_STRING)(v21 + 8), &v52);
          v20 = v47;
        }
        else
        {
          *(_QWORD *)(v21 + 16) = 0;
        }
      }
      memset(v46, 0, sizeof(v46));
      v23 = *v53;
      if ( !*v53 )
      {
        v9 = -1073741811;
        goto LABEL_8;
      }
      v24 = (HLOCAL)*((_QWORD *)v23 + 1);
      v25 = *(void **)&v48[16];
      v26 = (unsigned int *)(v14 + *((_QWORD *)v20 + 1) + 24LL);
      v27 = *(_DWORD *)v23;
      v28 = 0;
      v50 = v26;
      v42 = v24;
      *v26 = -1;
      while ( v28 < v27 && v25 )
      {
        v40 = (void *)*((_QWORD *)v24 + 3 * v28 + 2);
        if ( v40 )
        {
          if ( RtlEqualSid(v40, v25) )
          {
            v9 = 0;
            a3 = v45;
            *v50 = v28;
            goto LABEL_7;
          }
          v24 = v42;
        }
        ++v28;
      }
      v29 = *((_DWORD *)v23 + 4);
      if ( *(_DWORD *)v23 >= v29 )
      {
        v30 = v29 + 32;
        if ( v29 < v29 + 32 )
        {
          v31 = LocalAlloc(0x40u, 24 * v30);
          if ( !v31 )
            goto LABEL_47;
          v32 = (void *)*((_QWORD *)v23 + 1);
          v43 = v32;
          if ( v32 )
          {
            memcpy_0(v31, v32, 24 * v29);
            LocalFree(v43);
          }
          *((_QWORD *)v23 + 1) = v31;
          *((_DWORD *)v23 + 4) = v30;
        }
      }
      v33 = *(_DWORD *)v23;
      *(_OWORD *)v46 = *(_OWORD *)v48;
      v44 = v33;
      if ( *(_QWORD *)&v48[8] )
      {
        if ( *(_WORD *)&v48[2] )
        {
          v34 = LocalAlloc(0x40u, *(unsigned __int16 *)&v48[2]);
          *(_QWORD *)&v46[8] = v34;
          if ( !v34 )
          {
LABEL_48:
            v9 = -1073741670;
            if ( v34 )
              LocalFree(v34);
            if ( *(_QWORD *)&v46[16] )
              LocalFree(*(HLOCAL *)&v46[16]);
            goto LABEL_8;
          }
          RtlCopyUnicodeString((PUNICODE_STRING)v46, (PCUNICODE_STRING)v48);
          v33 = v44;
        }
        else
        {
          *(_QWORD *)&v46[8] = 0;
        }
      }
      v35 = *(const void **)&v48[16];
      v9 = 0;
      if ( !*(_QWORD *)&v48[16] )
      {
LABEL_37:
        a3 = v45;
        v38 = 3LL * v33;
        v39 = *((_QWORD *)v23 + 1);
        *(_OWORD *)(v39 + 8 * v38) = *(_OWORD *)v46;
        *(_QWORD *)(v39 + 8 * v38 + 16) = *(_QWORD *)&v46[16];
        *v50 = v33;
        ++*(_DWORD *)v23;
        goto LABEL_7;
      }
      v36 = RtlLengthSid(*(PSID *)&v48[16]);
      v37 = LocalAlloc(0x40u, v36);
      *(_QWORD *)&v46[16] = v37;
      if ( v37 )
      {
        memcpy_0(v37, v35, (unsigned int)v36);
        v33 = v44;
        goto LABEL_37;
      }
LABEL_47:
      v34 = *(HLOCAL *)&v46[8];
      goto LABEL_48;
    }
  }
LABEL_8:
  *v56 = a2 - v12;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800143e0  mov     r11, rsp
0x1800143e3  push    rbp
0x1800143e4  push    rbx
0x1800143e5  push    rsi
0x1800143e6  push    r13
0x1800143e8  push    r14
0x1800143ea  lea     rbp, [r11-0E8h]
0x1800143f1  sub     rsp, 1C0h
0x1800143f8  mov     rax, cs:__security_cookie
0x1800143ff  xor     rax, rsp
0x180014402  mov     [rbp+0E0h+var_40], rax
0x180014409  mov     rsi, [rbp+0E0h+arg_30]
0x180014410  mov     ebx, edx
0x180014412  mov     rdx, [rbp+0E0h+arg_28]
0x180014419  xor     r13d, r13d
0x18001441c  mov     rax, [rbp+0E0h+arg_20]
0x180014423  xor     r14d, r14d
0x180014426  mov     [rbp+0E0h+var_120], rsi
0x18001442a  xor     esi, esi
0x18001442c  mov     [rbp+0E0h+var_138], rdx
0x180014430  mov     rdx, [rbp+0E0h+arg_38]
0x180014437  mov     [rbp+0E0h+var_128], rdx
0x18001443b  mov     [rbp+0E0h+var_130], r9
0x18001443f  mov     qword ptr [rsp+1E0h+var_1A8], r8
0x180014444  mov     [rsp+1E0h+var_168], ecx
0x180014448  mov     qword ptr [rsp+1E0h+var_188], rax
0x18001444d  test    ecx, ecx
0x18001444f  jz      loc_1800144D8
0x180014455  mov     [r11-30h], r12
0x180014459  mov     [r11-38h], r15
0x18001445d  mov     [r11+8], rdi
0x180014461  cmp     esi, ebx
0x180014463  jnb     short loc_1800144C0
0x180014465  mov     rax, [rax+8]
0x180014469  mov     r15d, r14d
0x18001446c  shl     r15, 5
0x180014470  cmp     dword ptr [r15+rax+18h], 0FFFFFFFFh
0x180014476  jnz     short loc_1800144B2
0x180014478  cmp     dword ptr [r15+rax], 8
0x18001447d  jnz     short loc_1800144B2
0x18001447f  mov     rdi, [r8+r14*8]
0x180014483  mov     rcx, rdi; Sid
0x180014486  call    cs:__imp_RtlSubAuthorityCountSid
0x18001448d  nop     dword ptr [rax+rax+00h]
0x180014492  cmp     byte ptr [rax], 3
0x180014495  jz      short loc_180014502
0x180014497  mov     rdx, [rbp+0E0h+var_130]
0x18001449b  mov     r8, qword ptr [rsp+1E0h+var_1A8]
0x1800144a0  mov     rax, [r8+r14*8]
0x1800144a4  mov     [rdx+rsi*8], rax
0x1800144a8  mov     rdx, [rbp+0E0h+var_128]
0x1800144ac  mov     [rdx+rsi*4], r14d
0x1800144b0  inc     esi
0x1800144b2  inc     r14d
0x1800144b5  cmp     r14d, [rsp+1E0h+var_168]
0x1800144ba  jb      loc_180014938
0x1800144c0  mov     rdi, [rsp+1E0h+arg_0]
0x1800144c8  mov     r12, [rsp+1B8h]
0x1800144d0  mov     r15, [rsp+1E0h+var_30]
0x1800144d8  mov     rax, [rbp+0E0h+var_120]
0x1800144dc  sub     ebx, esi
0x1800144de  mov     [rax], ebx
0x1800144e0  mov     eax, r13d
0x1800144e3  mov     rcx, [rbp+0E0h+var_40]
0x1800144ea  xor     rcx, rsp; StackCookie
0x1800144ed  call    __security_check_cookie
0x1800144f2  add     rsp, 1C0h
0x1800144f9  pop     r14
0x1800144fb  pop     r13
0x1800144fd  pop     rsi
0x1800144fe  pop     rbx
0x1800144ff  pop     rbp
0x180014500  retn
0x180014502  xor     edx, edx; SubAuthority
0x180014504  mov     rcx, rdi; Sid
0x180014507  call    cs:__imp_RtlSubAuthoritySid
0x18001450e  nop     dword ptr [rax+rax+00h]
0x180014513  cmp     dword ptr [rax], 5
0x180014516  jnz     loc_180014497
0x18001451c  cmp     byte ptr [rdi+2], 0
0x180014520  jnz     loc_180014497
0x180014526  cmp     byte ptr [rdi+3], 0
0x18001452a  jnz     loc_180014497
0x180014530  cmp     byte ptr [rdi+4], 0
0x180014534  jnz     loc_180014497
0x18001453a  cmp     byte ptr [rdi+5], 0
0x18001453e  jnz     loc_180014497
0x180014544  cmp     byte ptr [rdi+6], 0
0x180014548  jnz     loc_180014497
0x18001454e  cmp     byte ptr [rdi+7], 5
0x180014552  jnz     loc_180014497
0x180014558  mov     rcx, qword ptr [rsp+1E0h+var_188]
0x18001455d  xor     eax, eax
0x18001455f  mov     r13, qword ptr [rsp+1E0h+var_1A8]
0x180014564  xorps   xmm0, xmm0
0x180014567  mov     word ptr [rsp+1E0h+var_186+6], ax
0x18001456c  xorps   xmm1, xmm1
0x18001456f  movups  xmmword ptr [rsp+1E0h+var_186+8], xmm0
0x180014574  mov     [rsp+1E0h+Sid], rax
0x180014579  mov     edx, 1; SubAuthority
0x18001457e  mov     rax, [rcx+8]
0x180014582  mov     dword ptr [r15+rax], 0Bh
0x18001458a  mov     rax, [rcx+8]
0x18001458e  mov     dword ptr [r15+rax+18h], 0
0x180014597  mov     rcx, [r13+r14*8+0]; Sid
0x18001459c  movups  xmmword ptr [rbp+0E0h+var_148.Length], xmm0
0x1800145a0  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm1
0x1800145a4  call    cs:__imp_RtlSubAuthoritySid
0x1800145ab  nop     dword ptr [rax+rax+00h]
0x1800145b0  mov     rcx, [r13+r14*8+0]; Sid
0x1800145b5  mov     edx, 2; SubAuthority
0x1800145ba  mov     edi, [rax]
0x1800145bc  call    cs:__imp_RtlSubAuthoritySid
0x1800145c3  nop     dword ptr [rax+rax+00h]
0x1800145c8  mov     r9d, edi
0x1800145cb  lea     r8, aLogonsessionid; "LogonSessionId_%lu_%lu"
0x1800145d2  mov     edx, 64h ; 'd'; unsigned __int64
0x1800145d7  mov     ecx, [rax]
0x1800145d9  mov     [rsp+20h], ecx
0x1800145dd  lea     rcx, [rbp+0E0h+SourceString]; unsigned __int16 *
0x1800145e1  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800145e6  mov     r13d, eax
0x1800145e9  test    eax, eax
0x1800145eb  js      loc_1800144C0
0x1800145f1  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x1800145f8  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1800145fc  call    cs:__imp_RtlInitUnicodeString
0x180014603  nop     dword ptr [rax+rax+00h]
0x180014608  lea     rdx, [rbp+0E0h+SourceString]; SourceString
0x18001460c  lea     rcx, [rbp+0E0h+var_148]; DestinationString
0x180014610  call    cs:__imp_RtlInitUnicodeString
0x180014617  nop     dword ptr [rax+rax+00h]
0x18001461c  movzx   eax, [rbp+0E0h+DestinationString.Length]
0x180014620  movups  xmm0, xmmword ptr [rbp+0E0h+var_148.Length]
0x180014624  mov     word ptr [rsp+1E0h+var_186+6], ax
0x180014629  movzx   eax, [rbp+0E0h+DestinationString.MaximumLength]
0x18001462d  mov     word ptr [rsp+1E0h+var_186+8], ax
0x180014632  mov     eax, dword ptr [rbp+0E0h+DestinationString+4]
0x180014635  mov     dword ptr [rsp+1E0h+var_186+0Ah], eax
0x180014639  mov     rax, [rbp+0E0h+DestinationString.Buffer]
0x18001463d  mov     qword ptr [rsp+1E0h+var_186+0Eh], rax
0x180014642  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180014649  mov     rcx, [rax+150h]
0x180014650  mov     [rsp+1E0h+Sid], rcx
0x180014655  mov     rcx, qword ptr [rsp+1E0h+var_188]
0x18001465a  mov     rdi, [rcx+8]
0x18001465e  add     rdi, r15
0x180014661  movups  xmmword ptr [rdi+8], xmm0
0x180014665  cmp     [rbp+0E0h+var_148.Buffer], 0
0x18001466a  jz      short loc_1800146B2
0x18001466c  movzx   eax, [rbp+0E0h+var_148.MaximumLength]
0x180014670  test    ax, ax
0x180014673  jz      loc_1800148B1
0x180014679  mov     edx, eax; uBytes
0x18001467b  mov     ecx, 40h ; '@'; uFlags
0x180014680  call    cs:__imp_LocalAlloc
0x180014687  nop     dword ptr [rax+rax+00h]
0x18001468c  mov     [rdi+10h], rax
0x180014690  test    rax, rax
0x180014693  jz      loc_180014942
0x180014699  lea     rdx, [rbp+0E0h+var_148]; SourceString
0x18001469d  lea     rcx, [rdi+8]; DestinationString
0x1800146a1  call    cs:__imp_RtlCopyUnicodeString
0x1800146a8  nop     dword ptr [rax+rax+00h]
0x1800146ad  mov     rcx, qword ptr [rsp+1E0h+var_188]
0x1800146b2  mov     rax, [rbp+0E0h+var_138]
0x1800146b6  xorps   xmm0, xmm0
0x1800146b9  mov     qword ptr [rsp+1E0h+var_1A8+8], 0
0x1800146c2  movdqu  xmmword ptr [rsp+1E0h+var_1A8+10h], xmm0
0x1800146c8  mov     rdi, [rax]
0x1800146cb  test    rdi, rdi
0x1800146ce  jz      loc_180014898
0x1800146d4  mov     rax, [rcx+8]
0x1800146d8  mov     rdx, [rdi+8]
0x1800146dc  add     rax, 18h
0x1800146e0  mov     r13, [rsp+1E0h+Sid]
0x1800146e5  add     rax, r15
0x1800146e8  mov     r12d, [rdi]
0x1800146eb  xor     r15d, r15d
0x1800146ee  mov     [rbp+0E0h+var_160], rax
0x1800146f2  mov     [rsp+1E0h+var_1B0], rdx
0x1800146f7  mov     dword ptr [rax], 0FFFFFFFFh
0x1800146fd  cmp     r15d, r12d
0x180014700  jl      loc_18001484F
0x180014706  mov     r12d, [rdi+10h]
0x18001470a  cmp     [rdi], r12d
0x18001470d  jb      short loc_180014757
0x18001470f  lea     r15d, [r12+20h]
0x180014714  cmp     r12d, r15d
0x180014717  jnb     short loc_180014757
0x180014719  lea     edx, [r15+r15*2]
0x18001471d  mov     ecx, 40h ; '@'; uFlags
0x180014722  shl     edx, 3; uBytes
0x180014725  call    cs:__imp_LocalAlloc
0x18001472c  nop     dword ptr [rax+rax+00h]
0x180014731  mov     r13, rax
0x180014734  test    rax, rax
0x180014737  jz      loc_1800148CC
0x18001473d  mov     rax, [rdi+8]
0x180014741  mov     [rsp+1E0h+var_1B0], rax
0x180014746  test    rax, rax
0x180014749  jnz     loc_1800148FE
0x18001474f  mov     [rdi+8], r13
0x180014753  mov     [rdi+10h], r15d
0x180014757  movzx   eax, word ptr [rsp+1E0h+var_186+6]
0x18001475c  movzx   ecx, word ptr [rsp+1E0h+var_186+8]
0x180014761  mov     edx, [rdi]
0x180014763  mov     word ptr [rsp+1E0h+var_1A8+8], ax
0x180014768  mov     eax, dword ptr [rsp+1E0h+var_186+0Ah]
0x18001476c  mov     dword ptr [rsp+1E0h+var_1A8+0Ch], eax
0x180014770  mov     rax, qword ptr [rsp+1E0h+var_186+0Eh]
0x180014775  mov     dword ptr [rsp+1E0h+var_1B0], edx
0x180014779  mov     word ptr [rsp+1E0h+var_1A8+0Ah], cx
0x18001477e  mov     qword ptr [rsp+1E0h+var_1A8+10h], rax
0x180014783  test    rax, rax
0x180014786  jz      short loc_1800147CC
0x180014788  test    cx, cx
0x18001478b  jz      loc_1800148BE
0x180014791  mov     edx, ecx; uBytes
0x180014793  mov     ecx, 40h ; '@'; uFlags
0x180014798  call    cs:__imp_LocalAlloc
0x18001479f  nop     dword ptr [rax+rax+00h]
0x1800147a4  mov     qword ptr [rsp+1E0h+var_1A8+10h], rax
0x1800147a9  test    rax, rax
0x1800147ac  jz      loc_1800148D1
0x1800147b2  lea     rdx, [rsp+1E0h+var_186+6]; SourceString
0x1800147b7  lea     rcx, [rsp+1E0h+var_1A8+8]; DestinationString
0x1800147bc  call    cs:__imp_RtlCopyUnicodeString
0x1800147c3  nop     dword ptr [rax+rax+00h]
0x1800147c8  mov     edx, dword ptr [rsp+1E0h+var_1B0]
0x1800147cc  mov     r15, [rsp+1E0h+Sid]
0x1800147d1  xor     r13d, r13d
0x1800147d4  test    r15, r15
0x1800147d7  jz      short loc_18001481E
0x1800147d9  mov     rcx, r15; Sid
0x1800147dc  call    cs:__imp_RtlLengthSid
0x1800147e3  nop     dword ptr [rax+rax+00h]
0x1800147e8  mov     edx, eax; uBytes
0x1800147ea  mov     ecx, 40h ; '@'; uFlags
0x1800147ef  mov     r12d, eax
0x1800147f2  call    cs:__imp_LocalAlloc
0x1800147f9  nop     dword ptr [rax+rax+00h]
0x1800147fe  mov     [rsp+1E0h+hMem], rax
0x180014803  test    rax, rax
0x180014806  jz      loc_1800148CC
0x18001480c  mov     r8d, r12d; Size
0x18001480f  mov     rdx, r15; Src
0x180014812  mov     rcx, rax; void *
0x180014815  call    memcpy_0
0x18001481a  mov     edx, dword ptr [rsp+1E0h+var_1B0]
0x18001481e  movups  xmm0, xmmword ptr [rsp+1E0h+var_1A8+8]
0x180014823  mov     r8, qword ptr [rsp+1E0h+var_1A8]
0x180014828  mov     eax, edx
0x18001482a  lea     rcx, [rax+rax*2]
0x18001482e  mov     rax, [rdi+8]
0x180014832  movups  xmmword ptr [rax+rcx*8], xmm0
0x180014836  movsd   xmm1, [rsp+1E0h+hMem]
0x18001483c  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x180014842  mov     rax, [rbp+0E0h+var_160]
0x180014846  mov     [rax], edx
0x180014848  inc     dword ptr [rdi]
0x18001484a  jmp     loc_1800144B2
0x18001484f  test    r13, r13
0x180014852  jz      loc_180014706
0x180014858  movsxd  rax, r15d
0x18001485b  lea     rcx, [rax+rax*2]
0x18001485f  mov     rcx, [rdx+rcx*8+10h]; Sid1
0x180014864  test    rcx, rcx
0x180014867  jnz     short loc_180014871
0x180014869  inc     r15d
0x18001486c  jmp     loc_1800146FD
0x180014871  mov     rdx, r13; Sid2
0x180014874  call    cs:__imp_RtlEqualSid
0x18001487b  nop     dword ptr [rax+rax+00h]
0x180014880  test    al, al
0x180014882  jz      short loc_1800148F4
0x180014884  mov     rax, [rbp+0E0h+var_160]
0x180014888  xor     r13d, r13d
0x18001488b  mov     r8, qword ptr [rsp+1E0h+var_1A8]
0x180014890  mov     [rax], r15d
0x180014893  jmp     loc_1800144B2
0x180014898  mov     r13d, 0C000000Dh
0x18001489e  test    r13d, r13d
0x1800148a1  js      loc_1800144C0
0x1800148a7  mov     r8, qword ptr [rsp+1E0h+var_1A8]
0x1800148ac  jmp     loc_1800144B2
0x1800148b1  mov     qword ptr [rdi+10h], 0
0x1800148b9  jmp     loc_1800146B2
0x1800148be  mov     qword ptr [rsp+1E0h+var_1A8+10h], 0
0x1800148c7  jmp     loc_1800147CC
0x1800148cc  mov     rax, qword ptr [rsp+1E0h+var_1A8+10h]
0x1800148d1  mov     r13d, 0C000009Ah
0x1800148d7  test    rax, rax
0x1800148da  jnz     short loc_180014927
0x1800148dc  mov     rcx, [rsp+1E0h+hMem]; hMem
0x1800148e1  test    rcx, rcx
0x1800148e4  jz      short loc_18001489E
0x1800148e6  call    cs:__imp_LocalFree
0x1800148ed  nop     dword ptr [rax+rax+00h]
0x1800148f2  jmp     short loc_18001489E
  ... truncated ...
```

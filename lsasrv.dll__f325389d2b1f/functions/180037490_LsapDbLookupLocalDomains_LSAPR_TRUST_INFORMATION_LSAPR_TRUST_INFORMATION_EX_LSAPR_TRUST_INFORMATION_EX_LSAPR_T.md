# LsapDbLookupLocalDomains(_LSAPR_TRUST_INFORMATION *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_TRUST_INFORMATION *)

- ea: `0x180037490`
- end: `0x1800377b2`
- name: `?LsapDbLookupLocalDomains@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAU_LSAPR_TRUST_INFORMATION_EX@@10@Z`
- size: `802`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUST_INFORMATION *, struct _LSAPR_TRUST_INFORMATION_EX *, struct _LSAPR_TRUST_INFORMATION_EX *, struct _LSAPR_TRUST_INFORMATION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012da4`

## callees

- `0x180037490`
- `0x180037840`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003769a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003769a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800375d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037626`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800375d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037626`
- `ntdll!RtlEqualSid` at `0x1800374fd`
- `ntdll!RtlEqualSid` at `0x180037719`
- `ntdll!RtlEqualSid` at `0x1800374fd`
- `ntdll!RtlEqualSid` at `0x180037719`
- `ntdll!RtlEqualUnicodeString` at `0x180037736`
- `ntdll!RtlEqualUnicodeString` at `0x180037736`
- `DNSAPI!DnsNameCompare_W` at `0x180037668`
- `DNSAPI!DnsNameCompare_W` at `0x180037668`

## pseudocode

```c
__int64 __fastcall LsapDbLookupLocalDomains(
        struct _LSAPR_TRUST_INFORMATION *a1,
        struct _LSAPR_TRUST_INFORMATION_EX *a2,
        struct _LSAPR_TRUST_INFORMATION_EX *a3,
        struct _LSAPR_TRUST_INFORMATION *a4)
{
  int v7; // ebx
  struct _LSAP_WELL_KNOWN_SID_ENTRY *v8; // r9
  void *v9; // rsi
  __int64 v10; // rdi
  void *v11; // rdx
  __int64 result; // rax
  __int64 v13; // rax
  __int128 v14; // xmm0
  struct _LSAP_DB_DOMAIN_CACHE_TYPE *v15; // rax
  __int64 v16; // rdi
  unsigned __int16 *v17; // rbx
  __int128 *v18; // r13
  void *v19; // rcx
  __int128 v20; // xmm0
  unsigned __int64 v21; // rdx
  WCHAR *v22; // rax
  WCHAR *v23; // rsi
  char v24; // r15
  unsigned __int64 v25; // rdx
  int v26; // edi
  char v27; // bp
  WCHAR *v28; // rax
  WCHAR *v29; // r14
  struct _LSAPR_TRUST_INFORMATION *v30; // rax
  void *v31; // rdx
  __int128 v32; // xmm0
  struct _LSAP_DB_DOMAIN_CACHE_TYPE *v33; // [rsp+60h] [rbp+8h] BYREF
  struct _LSAPR_TRUST_INFORMATION *v34; // [rsp+78h] [rbp+20h]

  v34 = a4;
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  v7 = 0;
  *((_OWORD *)a2 + 2) = 0;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_OWORD *)a3 + 2) = 0;
  v8 = WellKnownSids;
  v9 = (void *)*((_QWORD *)WellKnownSids + 84);
  *((_QWORD *)a1 + 2) = v9;
  while ( 1 )
  {
    if ( v7 >= 80 )
      return 3221225816LL;
    v10 = 48LL * v7;
    v11 = *(void **)((char *)v8 + v10);
    if ( v11 )
      break;
LABEL_6:
    ++v7;
  }
  if ( !RtlEqualSid(v9, v11) )
  {
    v8 = WellKnownSids;
    goto LABEL_6;
  }
  v13 = 32;
  if ( *(_DWORD *)((char *)WellKnownSids + v10 + 8) != 3 )
    v13 = 16;
  v14 = *(_OWORD *)((char *)WellKnownSids + v10 + v13);
  v15 = LsapDbPolicyCache;
  v33 = LsapDbPolicyCache;
  *(_OWORD *)a1 = v14;
  if ( v15 )
  {
LABEL_12:
    v16 = *(_QWORD *)v15;
    v17 = (unsigned __int16 *)*((_QWORD *)v15 + 1);
    v18 = (__int128 *)*((_QWORD *)v15 + 2);
    *((_QWORD *)a2 + 4) = *(_QWORD *)(*(_QWORD *)v15 + 16LL);
    *((_OWORD *)a2 + 1) = *(_OWORD *)v16;
    v19 = (void *)*((_QWORD *)v17 + 8);
    if ( v19
      && (v31 = *(void **)(v16 + 16)) != 0
      && RtlEqualSid(v19, v31)
      && RtlEqualUnicodeString((PCUNICODE_STRING)v17, (PCUNICODE_STRING)v16, 1u) )
    {
      v20 = *((_OWORD *)v17 + 1);
      *((_BYTE *)a2 + 40) = 1;
    }
    else
    {
      v20 = *((_OWORD *)a2 + 1);
    }
    *(_OWORD *)a2 = v20;
    *((_QWORD *)a3 + 4) = *((_QWORD *)v17 + 8);
    *((_OWORD *)a3 + 1) = *(_OWORD *)v17;
    *(_OWORD *)a3 = *((_OWORD *)v17 + 1);
    v21 = v17[8];
    if ( v17[9] > (unsigned __int16)v21 )
    {
      v23 = (WCHAR *)*((_QWORD *)v17 + 3);
      if ( !v23[v21 >> 1] )
      {
        v24 = 0;
        goto LABEL_17;
      }
    }
    v22 = (WCHAR *)LocalAlloc(0x40u, v21 + 2);
    v23 = v22;
    if ( v22 )
    {
      v24 = 1;
      memcpy_0(v22, *((const void **)v17 + 3), v17[8]);
      v23[(unsigned __int64)v17[8] >> 1] = 0;
LABEL_17:
      v25 = *v17;
      v26 = 0;
      v27 = 0;
      if ( v17[1] <= (unsigned __int16)v25 || (v29 = (WCHAR *)*((_QWORD *)v17 + 1), v29[v25 >> 1]) )
      {
        v28 = (WCHAR *)LocalAlloc(0x40u, v25 + 2);
        v29 = v28;
        if ( v28 )
        {
          v27 = 1;
          memcpy_0(v28, *((const void **)v17 + 1), *v17);
          v29[(unsigned __int64)*v17 >> 1] = 0;
        }
        else
        {
          v26 = -1073741801;
        }
      }
      if ( v26 >= 0 && !DnsNameCompare_W(v23, v29) )
        *((_BYTE *)a3 + 40) = 1;
      if ( v24 )
        LocalFree(v23);
      if ( v27 )
        LocalFree(v29);
      if ( v26 < 0 )
      {
        return (unsigned int)v26;
      }
      else
      {
        v30 = v34;
        if ( !v18 )
        {
          *(_OWORD *)v34 = 0;
          *((_QWORD *)v30 + 2) = 0;
          return (unsigned int)v26;
        }
        v32 = *v18;
        *((_QWORD *)v34 + 2) = *((_QWORD *)v18 + 2);
        *(_OWORD *)v30 = v32;
        return (unsigned int)v26;
      }
    }
    else
    {
      return 3221225495LL;
    }
  }
  else
  {
    result = LsapDbLookupBuildDomainCache(&v33);
    if ( (int)result >= 0 )
    {
      v15 = v33;
      goto LABEL_12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037490  mov     [rsp+arg_18], r9
0x180037495  push    rbx
0x180037496  push    rbp
0x180037497  push    rsi
0x180037498  push    r12
0x18003749a  push    r14
0x18003749c  sub     rsp, 30h
0x1800374a0  xorps   xmm0, xmm0
0x1800374a3  mov     [rsp+58h+arg_8], rdi
0x1800374a8  movups  xmmword ptr [rdx], xmm0
0x1800374ab  mov     r12, r8
0x1800374ae  mov     rbp, rdx
0x1800374b1  movups  xmmword ptr [rdx+10h], xmm0
0x1800374b5  mov     r14, rcx
0x1800374b8  xor     ebx, ebx
0x1800374ba  movups  xmmword ptr [rdx+20h], xmm0
0x1800374be  xorps   xmm1, xmm1
0x1800374c1  movups  xmmword ptr [r8], xmm1
0x1800374c5  movups  xmmword ptr [r8+10h], xmm1
0x1800374ca  movups  xmmword ptr [r8+20h], xmm1
0x1800374cf  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800374d6  mov     rsi, [r9+2A0h]
0x1800374dd  mov     [rcx+10h], rsi
0x1800374e1  cmp     ebx, 50h ; 'P'
0x1800374e4  jge     short loc_180037518
0x1800374e6  movsxd  rax, ebx
0x1800374e9  lea     rdi, [rax+rax*2]
0x1800374ed  shl     rdi, 4
0x1800374f1  mov     rdx, [rdi+r9]; Sid2
0x1800374f5  test    rdx, rdx
0x1800374f8  jz      short loc_180037514
0x1800374fa  mov     rcx, rsi; Sid1
0x1800374fd  call    cs:__imp_RtlEqualSid
0x180037504  nop     dword ptr [rax+rax+00h]
0x180037509  test    al, al
0x18003750b  jnz     short loc_18003752F
0x18003750d  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180037514  inc     ebx
0x180037516  jmp     short loc_1800374E1
0x180037518  mov     eax, 0C0000158h
0x18003751d  mov     rdi, [rsp+58h+arg_8]
0x180037522  add     rsp, 30h
0x180037526  pop     r14
0x180037528  pop     r12
0x18003752a  pop     rsi
0x18003752b  pop     rbp
0x18003752c  pop     rbx
0x18003752d  retn
0x18003752f  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180037536  mov     eax, 20h ; ' '
0x18003753b  add     rcx, rdi
0x18003753e  mov     edx, 10h
0x180037543  cmp     dword ptr [rcx+8], 3
0x180037547  cmovnz  eax, edx
0x18003754a  movups  xmm0, xmmword ptr [rax+rcx]
0x18003754e  mov     rax, cs:?LsapDbPolicyCache@@3PEAU_LSAP_DB_DOMAIN_CACHE_TYPE@@EA; _LSAP_DB_DOMAIN_CACHE_TYPE * LsapDbPolicyCache
0x180037555  mov     [rsp+58h+arg_0], rax
0x18003755a  movups  xmmword ptr [r14], xmm0
0x18003755e  test    rax, rax
0x180037561  jz      loc_180037796
0x180037567  mov     rdi, [rax]
0x18003756a  mov     rbx, [rax+8]
0x18003756e  mov     [rsp+58h+var_30], r13
0x180037573  mov     r13, [rax+10h]
0x180037577  mov     rax, [rdi+10h]
0x18003757b  mov     [rbp+20h], rax
0x18003757f  movups  xmm0, xmmword ptr [rdi]
0x180037582  movups  xmmword ptr [rbp+10h], xmm0
0x180037586  mov     rcx, [rbx+40h]; Sid1
0x18003758a  test    rcx, rcx
0x18003758d  jnz     loc_18003770C
0x180037593  movups  xmm0, xmmword ptr [rbp+10h]
0x180037597  movups  xmmword ptr [rbp+0], xmm0
0x18003759b  mov     rax, [rbx+40h]
0x18003759f  mov     [r12+20h], rax
0x1800375a4  movups  xmm0, xmmword ptr [rbx]
0x1800375a7  mov     [rsp+58h+var_38], r15
0x1800375ac  movups  xmmword ptr [r12+10h], xmm0
0x1800375b2  movups  xmm0, xmmword ptr [rbx+10h]
0x1800375b6  movups  xmmword ptr [r12], xmm0
0x1800375bb  movzx   edx, word ptr [rbx+10h]
0x1800375bf  cmp     [rbx+12h], dx
0x1800375c3  ja      loc_1800376D5
0x1800375c9  add     rdx, 2; uBytes
0x1800375cd  mov     ecx, 40h ; '@'; uFlags
0x1800375d2  call    cs:__imp_LocalAlloc
0x1800375d9  nop     dword ptr [rax+rax+00h]
0x1800375de  mov     rsi, rax
0x1800375e1  test    rax, rax
0x1800375e4  jz      loc_180037778
0x1800375ea  movzx   r8d, word ptr [rbx+10h]; Size
0x1800375ef  mov     rcx, rax; void *
0x1800375f2  mov     rdx, [rbx+18h]; Src
0x1800375f6  mov     r15b, 1
0x1800375f9  call    memcpy_0
0x1800375fe  movzx   ecx, word ptr [rbx+10h]
0x180037602  shr     rcx, 1
0x180037605  xor     eax, eax
0x180037607  mov     [rsi+rcx*2], ax
0x18003760b  movzx   edx, word ptr [rbx]
0x18003760e  xor     edi, edi
0x180037610  xor     bpl, bpl
0x180037613  cmp     [rbx+2], dx
0x180037617  ja      loc_1800376F2
0x18003761d  add     rdx, 2; uBytes
0x180037621  mov     ecx, 40h ; '@'; uFlags
0x180037626  call    cs:__imp_LocalAlloc
0x18003762d  nop     dword ptr [rax+rax+00h]
0x180037632  mov     r14, rax
0x180037635  test    rax, rax
0x180037638  jz      loc_18003778C
0x18003763e  movzx   r8d, word ptr [rbx]; Size
0x180037642  mov     rcx, rax; void *
0x180037645  mov     rdx, [rbx+8]; Src
0x180037649  mov     bpl, 1
0x18003764c  call    memcpy_0
0x180037651  movzx   ecx, word ptr [rbx]
0x180037654  shr     rcx, 1
0x180037657  xor     eax, eax
0x180037659  mov     [r14+rcx*2], ax
0x18003765e  test    edi, edi
0x180037660  js      short loc_18003767E
0x180037662  mov     rdx, r14; pName2
0x180037665  mov     rcx, rsi; pName1
0x180037668  call    cs:__imp_DnsNameCompare_W
0x18003766f  nop     dword ptr [rax+rax+00h]
0x180037674  test    eax, eax
0x180037676  jnz     short loc_18003767E
0x180037678  mov     byte ptr [r12+28h], 1
0x18003767e  test    r15b, r15b
0x180037681  jz      short loc_180037692
0x180037683  mov     rcx, rsi; hMem
0x180037686  call    cs:__imp_LocalFree
0x18003768d  nop     dword ptr [rax+rax+00h]
0x180037692  test    bpl, bpl
0x180037695  jz      short loc_1800376A6
0x180037697  mov     rcx, r14; hMem
0x18003769a  call    cs:__imp_LocalFree
0x1800376a1  nop     dword ptr [rax+rax+00h]
0x1800376a6  test    edi, edi
0x1800376a8  js      short loc_1800376C4
0x1800376aa  mov     rax, [rsp+58h+arg_18]
0x1800376af  test    r13, r13
0x1800376b2  jnz     loc_180037757
0x1800376b8  xorps   xmm0, xmm0
0x1800376bb  xor     ecx, ecx
0x1800376bd  movups  xmmword ptr [rax], xmm0
0x1800376c0  mov     [rax+10h], rcx
0x1800376c4  mov     r15, [rsp+58h+var_38]
0x1800376c9  mov     eax, edi
0x1800376cb  mov     r13, [rsp+58h+var_30]
0x1800376d0  jmp     loc_18003751D
0x1800376d5  mov     rsi, [rbx+18h]
0x1800376d9  mov     rax, rdx
0x1800376dc  shr     rax, 1
0x1800376df  cmp     word ptr [rsi+rax*2], 0
0x1800376e4  jnz     loc_1800375C9
0x1800376ea  xor     r15b, r15b
0x1800376ed  jmp     loc_18003760B
0x1800376f2  mov     r14, [rbx+8]
0x1800376f6  mov     rax, rdx
0x1800376f9  shr     rax, 1
0x1800376fc  cmp     [r14+rax*2], di
0x180037701  jnz     loc_18003761D
0x180037707  jmp     loc_18003765E
0x18003770c  mov     rdx, [rdi+10h]; Sid2
0x180037710  test    rdx, rdx
0x180037713  jz      loc_180037593
0x180037719  call    cs:__imp_RtlEqualSid
0x180037720  nop     dword ptr [rax+rax+00h]
0x180037725  test    al, al
0x180037727  jz      loc_180037593
0x18003772d  mov     r8b, 1; CaseInsensitive
0x180037730  mov     rdx, rdi; String2
0x180037733  mov     rcx, rbx; String1
0x180037736  call    cs:__imp_RtlEqualUnicodeString
0x18003773d  nop     dword ptr [rax+rax+00h]
0x180037742  test    al, al
0x180037744  jz      loc_180037593
0x18003774a  movups  xmm0, xmmword ptr [rbx+10h]
0x18003774e  mov     byte ptr [rbp+28h], 1
0x180037752  jmp     loc_180037597
0x180037757  movups  xmm0, xmmword ptr [r13+0]
0x18003775c  mov     rcx, [r13+10h]
0x180037760  mov     [rax+10h], rcx
0x180037764  movups  xmmword ptr [rax], xmm0
0x180037767  mov     r15, [rsp+58h+var_38]
0x18003776c  mov     eax, edi
0x18003776e  mov     r13, [rsp+58h+var_30]
0x180037773  jmp     loc_18003751D
0x180037778  mov     eax, 0C0000017h
0x18003777d  mov     r15, [rsp+58h+var_38]
0x180037782  mov     r13, [rsp+58h+var_30]
0x180037787  jmp     loc_18003751D
0x18003778c  mov     edi, 0C0000017h
0x180037791  jmp     loc_18003765E
0x180037796  lea     rcx, [rsp+58h+arg_0]; struct _LSAP_DB_DOMAIN_CACHE_TYPE **
0x18003779b  call    ?LsapDbLookupBuildDomainCache@@YAJPEAPEAU_LSAP_DB_DOMAIN_CACHE_TYPE@@@Z; LsapDbLookupBuildDomainCache(_LSAP_DB_DOMAIN_CACHE_TYPE * *)
0x1800377a0  test    eax, eax
0x1800377a2  js      loc_18003751D
0x1800377a8  mov     rax, [rsp+58h+arg_0]
0x1800377ad  jmp     loc_180037567
```

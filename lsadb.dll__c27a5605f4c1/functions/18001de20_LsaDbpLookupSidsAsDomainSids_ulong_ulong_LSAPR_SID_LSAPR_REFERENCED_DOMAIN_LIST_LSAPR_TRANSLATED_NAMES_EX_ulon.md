# LsaDbpLookupSidsAsDomainSids(ulong,ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *)

- ea: `0x18001de20`
- end: `0x18001e131`
- name: `?LsaDbpLookupSidsAsDomainSids@@YAJKKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK@Z`
- size: `785`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _LSAPR_SID **, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001db90`

## callees

- `0x180001670`
- `0x18001a6d8`
- `0x18001a894`
- `0x18001de20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001def2`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001def2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001df08`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001df08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e102`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e102`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001e010`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001e010`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001e047`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001e047`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001e097`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001e0e4`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001e097`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001e0e4`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsAsDomainSids(
        int a1,
        unsigned int a2,
        struct _LSAPR_SID **a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4,
        struct _LSAPR_TRANSLATED_NAMES_EX *a5,
        unsigned int *a6)
{
  struct _LSAPR_TRANSLATED_NAMES_EX *v6; // rsi
  int v7; // ebx
  PSID Sid; // rdi
  PWSTR Buffer; // rcx
  __int64 v10; // r13
  __int64 v12; // rax
  __int64 v13; // r15
  bool v14; // zf
  struct _LSAPR_SID *v15; // rcx
  char v16; // al
  char *v17; // rsi
  int HasTransitiveTrust; // eax
  int HasDomainTrust; // eax
  int v20; // eax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v21; // r14
  __int64 v22; // rax
  unsigned __int8 v24[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh]
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbDomainSid; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h]
  struct _LSAPR_TRANSLATED_NAMES_EX *v30; // [rsp+50h] [rbp-B0h]
  struct _LSA_TRUST_INFORMATION hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v32; // [rsp+70h] [rbp-90h]
  unsigned int *v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+98h] [rbp-68h] BYREF
  LSA_UNICODE_STRING Name; // [rsp+A8h] [rbp-58h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  _BYTE pDomainSid[72]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a5;
  v7 = 0;
  v25 = a1;
  Sid = 0;
  Buffer = (PWSTR)a6;
  v10 = 0;
  v33 = a6;
  v32 = a4;
  v29 = a2;
  v30 = a5;
  v24[0] = 0;
  hMem.Name = 0;
  if ( !a2 )
    goto LABEL_38;
  while ( 1 )
  {
    cbDomainSid = 0;
    v26 = 0;
    Sid = 0;
    v39 = 0;
    v28 = 0;
    v12 = *((_QWORD *)v6 + 1);
    v13 = 32LL * (unsigned int)v10;
    v36 = 0;
    Name = 0;
    v14 = *(_DWORD *)(v12 + v13 + 24) == -1;
    v38 = 0;
    memset(&hMem, 0, sizeof(hMem));
    if ( v14 && *(_DWORD *)(v12 + 32LL * (unsigned int)v10) == 8 )
    {
      v15 = a3[v10];
      cbDomainSid = 68;
      if ( GetWindowsAccountDomainSid(v15, pDomainSid, &cbDomainSid) )
      {
        if ( EqualSid(pDomainSid, a3[v10]) )
          break;
      }
    }
LABEL_35:
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= v29 )
      goto LABEL_36;
  }
  v16 = v25;
  v17 = 0;
  if ( (v25 & 2) != 0 )
  {
    HasTransitiveTrust = LsaDbpDomainHasTransitiveTrust(0, a3[v10], &hMem);
    Sid = hMem.Sid;
    v7 = HasTransitiveTrust;
    if ( HasTransitiveTrust >= 0 )
    {
      v17 = (char *)&v36;
      Name = hMem.Name;
      *(_QWORD *)&v38 = hMem.Sid;
      goto LABEL_24;
    }
    if ( HasTransitiveTrust != -1073741601 )
      goto LABEL_36;
    v16 = v25;
    v7 = 0;
  }
  if ( (v16 & 1) != 0 )
  {
    HasDomainTrust = LsaDbpDomainHasDomainTrust(3u, 0, a3[v10], v24, &v28);
    v7 = HasDomainTrust;
    if ( HasDomainTrust < 0 )
    {
      if ( HasDomainTrust != -1073741601 )
        goto LABEL_36;
      v7 = 0;
    }
    else
    {
      v17 = (char *)v28 + 16;
    }
    if ( v17 )
      goto LABEL_24;
    v16 = v25;
  }
  if ( (v16 & 8) == 0 )
    goto LABEL_27;
  v20 = LsaDbpDomainHasDomainTrust(4u, 0, a3[v10], v24, &v28);
  v7 = v20;
  if ( v20 < 0 )
  {
    if ( v20 != -1073741601 )
      goto LABEL_36;
    v7 = 0;
  }
  else
  {
    v17 = (char *)v28 + 16;
  }
  if ( !v17 )
  {
LABEL_27:
    v6 = v30;
    goto LABEL_28;
  }
LABEL_24:
  v21 = v32;
  if ( !(unsigned __int8)LsapDbLookupListReferencedDomains(v32, a3[v10], &v26) )
  {
    v22 = *((_QWORD *)v17 + 4);
    v34 = *((_OWORD *)v17 + 1);
    v35 = v22;
    v7 = LsapDbLookupAddListReferencedDomains(v21, &v34, &v26);
    if ( v7 < 0 )
      goto LABEL_36;
  }
  v6 = v30;
  *(_DWORD *)(v13 + *((_QWORD *)v30 + 1)) = 3;
  Buffer = (PWSTR)*((_QWORD *)v6 + 1);
  *(_DWORD *)&Buffer[(unsigned __int64)v13 / 2 + 12] = v26;
  *(_OWORD *)(*((_QWORD *)v6 + 1) + v13 + 8) = 0;
  ++*v33;
LABEL_28:
  if ( v24[0] )
  {
    LsapDbExpReleaseLockTrustedDomainList(Buffer);
    v24[0] = 0;
  }
  Buffer = hMem.Name.Buffer;
  if ( hMem.Name.Buffer )
  {
    LocalFree(hMem.Name.Buffer);
    hMem.Name.Buffer = 0;
  }
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  if ( v7 >= 0 )
    goto LABEL_35;
LABEL_36:
  if ( v24[0] )
    LsapDbExpReleaseLockTrustedDomainList(Buffer);
LABEL_38:
  if ( hMem.Name.Buffer )
    LocalFree(hMem.Name.Buffer);
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001de20  mov     [rsp-8+arg_0], rbx
0x18001de25  push    rbp
0x18001de26  push    rsi
0x18001de27  push    rdi
0x18001de28  push    r12
0x18001de2a  push    r13
0x18001de2c  push    r14
0x18001de2e  push    r15
0x18001de30  lea     rbp, [rsp-20h]
0x18001de35  sub     rsp, 120h
0x18001de3c  mov     rax, cs:__security_cookie
0x18001de43  xor     rax, rsp
0x18001de46  mov     [rbp+50h+var_38], rax
0x18001de4a  mov     rsi, [rbp+50h+arg_20]
0x18001de51  xor     ebx, ebx
0x18001de53  mov     [rsp+150h+var_11C], ecx
0x18001de57  xor     edi, edi
0x18001de59  mov     rcx, [rbp+50h+arg_28]
0x18001de60  xor     r13d, r13d
0x18001de63  mov     [rsp+150h+var_D8], rcx
0x18001de68  xorps   xmm0, xmm0
0x18001de6b  mov     [rsp+150h+var_E0], r9
0x18001de70  mov     r12, r8
0x18001de73  mov     [rsp+150h+var_108], edx
0x18001de77  mov     [rsp+150h+var_100], rsi
0x18001de7c  mov     [rsp+150h+var_120], bl
0x18001de80  movups  xmmword ptr [rsp+150h+hMem], xmm0
0x18001de85  test    edx, edx
0x18001de87  jz      loc_18001E0EA
0x18001de8d  xor     eax, eax
0x18001de8f  mov     r15d, r13d
0x18001de92  xorps   xmm0, xmm0
0x18001de95  mov     [rsp+150h+cbDomainSid], eax
0x18001de99  mov     [rsp+150h+var_118], eax
0x18001de9d  xor     edi, edi
0x18001de9f  mov     [rbp+50h+var_88], rax
0x18001dea3  mov     [rsp+150h+var_110], rax
0x18001dea8  mov     rax, [rsi+8]
0x18001deac  shl     r15, 5
0x18001deb0  movups  [rbp+50h+var_B8], xmm0
0x18001deb4  mov     [rsp+150h+var_E8], rdi
0x18001deb9  movups  [rbp+50h+var_A8], xmm0
0x18001debd  cmp     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18001dec3  movups  [rbp+50h+var_98], xmm0
0x18001dec7  movups  xmmword ptr [rsp+150h+hMem], xmm0
0x18001decc  jnz     loc_18001E0CF
0x18001ded2  cmp     dword ptr [rax+r15], 8
0x18001ded7  jnz     loc_18001E0CF
0x18001dedd  mov     rcx, [r12+r13*8]; pSid
0x18001dee1  lea     r8, [rsp+150h+cbDomainSid]; cbDomainSid
0x18001dee6  lea     rdx, [rbp+50h+pDomainSid]; pDomainSid
0x18001deea  mov     [rsp+150h+cbDomainSid], 44h ; 'D'
0x18001def2  call    cs:__imp_GetWindowsAccountDomainSid
0x18001def8  test    eax, eax
0x18001defa  jz      loc_18001E0CF
0x18001df00  mov     rdx, [r12+r13*8]; pSid2
0x18001df04  lea     rcx, [rbp+50h+pDomainSid]; pSid1
0x18001df08  call    cs:__imp_EqualSid
0x18001df0e  test    eax, eax
0x18001df10  jz      loc_18001E0CF
0x18001df16  mov     eax, [rsp+150h+var_11C]
0x18001df1a  xor     esi, esi
0x18001df1c  test    al, 2
0x18001df1e  jz      short loc_18001DF6B
0x18001df20  mov     rdx, [r12+r13*8]; void *
0x18001df24  lea     r8, [rsp+150h+hMem]; struct _LSA_TRUST_INFORMATION *
0x18001df29  xor     ecx, ecx; struct _UNICODE_STRING *
0x18001df2b  call    ?LsaDbpDomainHasTransitiveTrust@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_TRUST_INFORMATION@@@Z; LsaDbpDomainHasTransitiveTrust(_UNICODE_STRING *,void *,_LSA_TRUST_INFORMATION *)
0x18001df30  mov     rdi, [rsp+150h+var_E8]
0x18001df35  mov     ebx, eax
0x18001df37  test    eax, eax
0x18001df39  js      short loc_18001DF5A
0x18001df3b  mov     rcx, [rsp+150h+hMem]
0x18001df40  lea     rsi, [rbp+50h+var_B8]
0x18001df44  mov     qword ptr [rbp+50h+var_A8], rcx
0x18001df48  mov     rcx, [rsp+150h+hMem+8]
0x18001df4d  mov     qword ptr [rbp+50h+var_A8+8], rcx
0x18001df51  mov     qword ptr [rbp+50h+var_98], rdi
0x18001df55  jmp     loc_18001DFFF
0x18001df5a  cmp     eax, 0C00000DFh
0x18001df5f  jnz     loc_18001E0DD
0x18001df65  mov     eax, [rsp+150h+var_11C]
0x18001df69  xor     ebx, ebx
0x18001df6b  test    al, 1
0x18001df6d  jz      short loc_18001DFB3
0x18001df6f  mov     r8, [r12+r13*8]; void *
0x18001df73  lea     rax, [rsp+150h+var_110]
0x18001df78  xor     edx, edx; struct _UNICODE_STRING *
0x18001df7a  mov     [rsp+150h+var_130], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001df7f  lea     r9, [rsp+150h+var_120]; unsigned __int8 *
0x18001df84  lea     ecx, [rdx+3]; unsigned int
0x18001df87  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001df8c  mov     ebx, eax
0x18001df8e  test    eax, eax
0x18001df90  js      short loc_18001DF9D
0x18001df92  mov     rsi, [rsp+150h+var_110]
0x18001df97  add     rsi, 10h
0x18001df9b  jmp     short loc_18001DFAA
0x18001df9d  cmp     eax, 0C00000DFh
0x18001dfa2  jnz     loc_18001E0DD
0x18001dfa8  xor     ebx, ebx
0x18001dfaa  test    rsi, rsi
0x18001dfad  jnz     short loc_18001DFFF
0x18001dfaf  mov     eax, [rsp+150h+var_11C]
0x18001dfb3  test    al, 8
0x18001dfb5  jz      loc_18001E08B
0x18001dfbb  mov     r8, [r12+r13*8]; void *
0x18001dfbf  lea     rax, [rsp+150h+var_110]
0x18001dfc4  xor     edx, edx; struct _UNICODE_STRING *
0x18001dfc6  mov     [rsp+150h+var_130], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001dfcb  lea     r9, [rsp+150h+var_120]; unsigned __int8 *
0x18001dfd0  lea     ecx, [rdx+4]; unsigned int
0x18001dfd3  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001dfd8  mov     ebx, eax
0x18001dfda  test    eax, eax
0x18001dfdc  js      short loc_18001DFE9
0x18001dfde  mov     rsi, [rsp+150h+var_110]
0x18001dfe3  add     rsi, 10h
0x18001dfe7  jmp     short loc_18001DFF6
0x18001dfe9  cmp     eax, 0C00000DFh
0x18001dfee  jnz     loc_18001E0DD
0x18001dff4  xor     ebx, ebx
0x18001dff6  test    rsi, rsi
0x18001dff9  jz      loc_18001E08B
0x18001dfff  mov     r14, [rsp+150h+var_E0]
0x18001e004  lea     r8, [rsp+150h+var_118]
0x18001e009  mov     rdx, [r12+r13*8]
0x18001e00d  mov     rcx, r14
0x18001e010  call    cs:__imp_LsapDbLookupListReferencedDomains
0x18001e016  test    al, al
0x18001e018  jnz     short loc_18001E057
0x18001e01a  movups  xmm0, xmmword ptr [rsi+10h]
0x18001e01e  mov     rax, [rsi+20h]
0x18001e022  lea     r8, [rsp+150h+var_118]
0x18001e027  mov     qword ptr [rbp+50h+var_D0], 0
0x18001e02f  lea     rdx, [rbp+50h+var_D0]
0x18001e033  mov     qword ptr [rbp+50h+var_D0+8], 0
0x18001e03b  mov     rcx, r14
0x18001e03e  movdqu  [rbp+50h+var_D0], xmm0
0x18001e043  mov     [rbp+50h+var_C0], rax
0x18001e047  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x18001e04d  mov     ebx, eax
0x18001e04f  test    eax, eax
0x18001e051  js      loc_18001E0DD
0x18001e057  mov     rsi, [rsp+150h+var_100]
0x18001e05c  xorps   xmm0, xmm0
0x18001e05f  mov     rax, [rsi+8]
0x18001e063  mov     dword ptr [r15+rax], 3
0x18001e06b  mov     rcx, [rsi+8]
0x18001e06f  mov     eax, [rsp+150h+var_118]
0x18001e073  mov     [rcx+r15+18h], eax
0x18001e078  mov     rax, [rsi+8]
0x18001e07c  movups  xmmword ptr [rax+r15+8], xmm0
0x18001e082  mov     rax, [rsp+150h+var_D8]
0x18001e087  inc     dword ptr [rax]
0x18001e089  jmp     short loc_18001E090
0x18001e08b  mov     rsi, [rsp+150h+var_100]
0x18001e090  cmp     [rsp+150h+var_120], 0
0x18001e095  jz      short loc_18001E0A2
0x18001e097  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001e09d  mov     [rsp+150h+var_120], 0
0x18001e0a2  mov     rcx, [rsp+150h+hMem+8]; hMem
0x18001e0a7  test    rcx, rcx
0x18001e0aa  jz      short loc_18001E0BB
0x18001e0ac  call    cs:__imp_LocalFree
0x18001e0b2  mov     [rsp+150h+hMem+8], 0
0x18001e0bb  test    rdi, rdi
0x18001e0be  jz      short loc_18001E0CB
0x18001e0c0  mov     rcx, rdi; hMem
0x18001e0c3  call    cs:__imp_LocalFree
0x18001e0c9  xor     edi, edi
0x18001e0cb  test    ebx, ebx
0x18001e0cd  js      short loc_18001E0DD
0x18001e0cf  inc     r13d
0x18001e0d2  cmp     r13d, [rsp+150h+var_108]
0x18001e0d7  jb      loc_18001DE8D
0x18001e0dd  cmp     [rsp+150h+var_120], 0
0x18001e0e2  jz      short loc_18001E0EA
0x18001e0e4  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001e0ea  mov     rcx, [rsp+150h+hMem+8]; hMem
0x18001e0ef  test    rcx, rcx
0x18001e0f2  jz      short loc_18001E0FA
0x18001e0f4  call    cs:__imp_LocalFree
0x18001e0fa  test    rdi, rdi
0x18001e0fd  jz      short loc_18001E108
0x18001e0ff  mov     rcx, rdi; hMem
0x18001e102  call    cs:__imp_LocalFree
0x18001e108  mov     eax, ebx
0x18001e10a  mov     rcx, [rbp+50h+var_38]
0x18001e10e  xor     rcx, rsp; StackCookie
0x18001e111  call    __security_check_cookie
0x18001e116  mov     rbx, [rsp+150h+arg_0]
0x18001e11e  add     rsp, 120h
0x18001e125  pop     r15
0x18001e127  pop     r14
0x18001e129  pop     r13
0x18001e12b  pop     r12
0x18001e12d  pop     rdi
0x18001e12e  pop     rsi
0x18001e12f  pop     rbp
0x18001e130  retn
```

# QueryUserAttributesOnce(ushort const *,ushort const *,ulong,ushort * *,_IAS_NTDS_RESULT *)

- ea: `0x18001d04c`
- end: `0x18001d67c`
- name: `?QueryUserAttributesOnce@@YAKPEBG0KPEAPEAGPEAU_IAS_NTDS_RESULT@@@Z`
- size: `1584`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 **@<r9>, struct _IAS_NTDS_RESULT *)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d9a4`

## callees

- `0x180001c88`
- `0x1800028e0`
- `0x18000a760`
- `0x18000d49c`
- `0x18000d59c`
- `0x18000e754`
- `0x18001cbc4`
- `0x18001cbec`
- `0x18001cbf8`
- `0x18001cc10`
- `0x18001cc34`
- `0x18001cd90`
- `0x18001d04c`
- `0x18001dddc`
- `0x18001f5d0`
- `0x18001f9b0`
- `0x180025264`
- `0x1800254a0`
- `0x18002b472`
- `0x18002b4a0`
- `0x18002b560`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x18001d291`
- `msvcrt!wcsncat_s` at `0x18001d394`
- `msvcrt!wcsncat_s` at `0x18001d291`
- `msvcrt!wcsncat_s` at `0x18001d394`
- `msvcrt!wcschr` at `0x18001d180`
- `msvcrt!wcschr` at `0x18001d180`
- `msvcrt!wcscat_s` at `0x18001d3b1`
- `msvcrt!wcscat_s` at `0x18001d3b1`
- `msvcrt!wcscpy_s` at `0x18001d274`
- `msvcrt!wcscpy_s` at `0x18001d274`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001d46c`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001d46c`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001d492`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001d492`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18001d485`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18001d485`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001d4c9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001d4c9`

## string_xrefs

- `0x18001d5b6`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18001d619`: `DS not installed for domain %S.`
- `0x18001d536`: `Could not open an LDAP connection to domain %S.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall QueryUserAttributesOnce(
        const unsigned __int16 *a1,
        wchar_t *a2,
        int a3,
        unsigned __int16 **a4,
        struct _IAS_NTDS_RESULT *a5)
{
  DWORD Domain; // edi
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  int v10; // r9d
  unsigned __int64 v11; // r13
  int v12; // r15d
  unsigned int i; // ebx
  wchar_t *v14; // rax
  int v15; // ecx
  size_t v16; // rsi
  void *p_lpCriticalSection; // rbx
  size_t v18; // rcx
  __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  _DWORD *v22; // rax
  rsize_t v23; // rsi
  __int64 v24; // rdx
  size_t v25; // r15
  void *p_MaxCount; // rsi
  size_t v27; // rcx
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  _DWORD *v32; // rax
  rsize_t v33; // r15
  const wchar_t *v34; // r8
  int v35; // r9d
  unsigned __int16 **v36; // rdx
  int v37; // r14d
  unsigned __int16 **v38; // r15
  __int64 v39; // rax
  unsigned __int16 **v40; // rdx
  LPCRITICAL_SECTION v41; // rdi
  unsigned int SingleEntry; // esi
  LDAPMessage *v43; // rbx
  __int64 v44; // rax
  LDAPMessage *entry; // rbx
  __int64 v46; // rax
  unsigned __int16 *dnW; // rbx
  struct _RTL_CRITICAL_SECTION *v48; // rax
  struct _IAS_NTDS_RESULT *v49; // rcx
  int v51; // r9d
  unsigned int v52; // eax
  __int64 v53; // rcx
  int v54; // r9d
  _BYTE v55[32]; // [rsp+0h] [rbp-30h] BYREF
  unsigned __int16 **v56; // [rsp+20h] [rbp-10h]
  struct ldapmsg **p_res; // [rsp+28h] [rbp-8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+0h] BYREF
  rsize_t MaxCount; // [rsp+38h] [rbp+8h] BYREF
  LDAPMessage *res; // [rsp+40h] [rbp+10h] BYREF
  void *v61; // [rsp+48h] [rbp+18h] BYREF
  int v62; // [rsp+50h] [rbp+20h]
  void *v63; // [rsp+58h] [rbp+28h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp+30h]
  rsize_t SizeInWords; // [rsp+68h] [rbp+38h]
  unsigned __int16 **v66; // [rsp+70h] [rbp+40h]
  struct _IAS_NTDS_RESULT *v67; // [rsp+78h] [rbp+48h]
  char Buffer[256]; // [rsp+80h] [rbp+50h] BYREF

  v66 = a4;
  v62 = a3;
  Source = a2;
  v67 = a5;
  ATL::CComPtr<IRequest>::CComPtr<IRequest>(&lpCriticalSection);
  MaxCount = 0;
  Domain = NTCache::getDomain(0, a1, (struct NTDomain **)&MaxCount);
  if ( Domain )
  {
    lpCriticalSection = 0;
LABEL_57:
    if ( Domain == 8200 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("DS not installed for domain %S.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
          v54,
          (__int64)a1);
      }
      Domain = 8200;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Could not open an LDAP connection to domain %S.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
          v51,
          (__int64)a1);
      }
      v52 = IASFormatSysErr(Domain, Buffer);
      if ( v52 >= 0x100 )
        _report_rangecheckfailure(v53);
      Buffer[v52] = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
        WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"NTDomain::getConnection", (__int64)Buffer);
      }
    }
    goto LABEL_73;
  }
  Domain = NTDomain::getConnection(
             (struct _RTL_CRITICAL_SECTION *)MaxCount,
             (struct LDAPConnection **)&lpCriticalSection);
  NTDomain::Release((NTDomain *)MaxCount);
  v8 = 0;
  if ( Domain )
    goto LABEL_57;
  Domain = 8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v9 = (_QWORD *)(ATL::CComPtrBase<LDAPConnection>::operator->(&lpCriticalSection, 0) + 64);
    WppDbgPrint("Sending LDAP search to %S.");
    if ( v9[3] >= 8u )
      v9 = (_QWORD *)*v9;
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
      v10,
      (__int64)v9);
    v8 = 0;
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = 0;
  for ( i = 0; i < v11; ++i )
  {
    v14 = wcschr(L"*()\\/", a2[i]);
    v15 = v12 + 1;
    v8 = 0;
    if ( !v14 )
      v15 = v12;
    v12 = v15;
  }
  LODWORD(MaxCount) = v11 + 2 * v12;
  SizeInWords = (unsigned int)(MaxCount + 20);
  v16 = 2 * SizeInWords;
  p_lpCriticalSection = 0;
  if ( !(2 * SizeInWords) )
    goto LABEL_23;
  if ( v16 > g_ulMaxStackAllocSize )
    goto LABEL_23;
  v18 = v16 + g_ulAdditionalProbeSize + 8;
  if ( v18 < v16 || !(unsigned int)VerifyStackAvailable(v18, 0) )
    goto LABEL_23;
  v19 = v16 + 23;
  if ( v16 + 23 <= v16 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
  v21 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
  p_lpCriticalSection = &lpCriticalSection;
  if ( v55 == (_BYTE *)-48LL || (LODWORD(lpCriticalSection) = 1801679955, (p_lpCriticalSection = &MaxCount) == 0) )
  {
LABEL_23:
    if ( v16 + 8 >= v16 )
    {
      v22 = (_DWORD *)((__int64 (__fastcall *)(size_t, __int64))g_pfnAllocate)(v16 + 8, v8);
      if ( !v22 )
        goto LABEL_73;
      *v22 = 1885431112;
      p_lpCriticalSection = v22 + 2;
    }
    if ( p_lpCriticalSection )
      goto LABEL_27;
LABEL_73:
    ATL::CComPtr<LDAPConnection>::~CComPtr<LDAPConnection>(&lpCriticalSection);
    return Domain;
  }
LABEL_27:
  v63 = p_lpCriticalSection;
  memset_0(p_lpCriticalSection, 0, v16);
  v23 = SizeInWords;
  wcscpy_s((wchar_t *)p_lpCriticalSection, SizeInWords, L"(sAMAccountName=");
  v24 = 0;
  if ( !v12 )
  {
    wcsncat_s((wchar_t *)p_lpCriticalSection, v23, Source, 0x100u);
    goto LABEL_45;
  }
  v25 = 2LL * (unsigned int)(MaxCount + 1);
  p_MaxCount = 0;
  if ( !v25 )
    goto LABEL_37;
  if ( v25 > g_ulMaxStackAllocSize )
    goto LABEL_37;
  v27 = v25 + g_ulAdditionalProbeSize + 8;
  if ( v27 < v25 || !(unsigned int)VerifyStackAvailable(v27, 0) )
    goto LABEL_37;
  v28 = v25 + 23;
  if ( v25 + 23 <= v25 + 8 )
    v28 = 0xFFFFFFFFFFFFFF0LL;
  v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
  v30 = alloca(v29);
  v31 = alloca(v29);
  p_MaxCount = &lpCriticalSection;
  if ( v55 == (_BYTE *)-48LL || (LODWORD(lpCriticalSection) = 1801679955, (p_MaxCount = &MaxCount) == 0) )
  {
LABEL_37:
    if ( v25 + 8 >= v25 )
    {
      v32 = (_DWORD *)((__int64 (__fastcall *)(size_t, __int64))g_pfnAllocate)(v25 + 8, v24);
      if ( !v32 )
      {
LABEL_41:
        SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v63);
        goto LABEL_73;
      }
      *v32 = 1885431112;
      p_MaxCount = v32 + 2;
    }
    if ( !p_MaxCount )
      goto LABEL_41;
  }
  v61 = p_MaxCount;
  memset_0(p_MaxCount, 0, v25);
  v33 = (unsigned int)MaxCount;
  Domain = EscapeSpecialCharacters(Source, v11, (unsigned __int16 *)p_MaxCount, MaxCount);
  if ( Domain )
  {
    SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v61);
    goto LABEL_41;
  }
  v34 = (const wchar_t *)p_MaxCount;
  v23 = SizeInWords;
  wcsncat_s((wchar_t *)p_lpCriticalSection, SizeInWords, v34, v33);
  SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v61);
LABEL_45:
  wcscat_s((wchar_t *)p_lpCriticalSection, v23, asc_1800361D8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Using encoded filter %S for search ");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
      v35,
      (__int64)p_lpCriticalSection);
  }
  res = 0;
  v36 = (unsigned __int16 **)&NO_ATTRS;
  v37 = v62;
  v38 = v66;
  if ( v62 )
    v36 = v66;
  v39 = ATL::CComPtrBase<LDAPConnection>::operator->(&lpCriticalSection, v36);
  p_res = &res;
  v56 = v40;
  v41 = lpCriticalSection;
  SingleEntry = GetSingleEntry(
                  lpCriticalSection,
                  *(unsigned __int16 **)(v39 + 112),
                  2u,
                  (unsigned __int16 *)p_lpCriticalSection,
                  v40,
                  &res);
  if ( !SingleEntry )
  {
    if ( v37 )
      goto LABEL_54;
    v43 = res;
    v44 = ATL::CComPtrBase<LDAPConnection>::operator*(&lpCriticalSection);
    entry = ldap_first_entry(*(LDAP **)(v44 + 88), v43);
    v46 = ATL::CComPtrBase<LDAPConnection>::operator*(&lpCriticalSection);
    dnW = ldap_get_dnW(*(LDAP **)(v46 + 88), entry);
    ldap_msgfree(res);
    v48 = (struct _RTL_CRITICAL_SECTION *)ATL::CComPtrBase<LDAPConnection>::operator LDAPConnection *(&lpCriticalSection);
    SingleEntry = GetSingleEntry(v48, dnW, 0, L"(objectclass=*)", v38, &res);
    ldap_memfreeW(dnW);
    if ( !SingleEntry )
    {
LABEL_54:
      _InterlockedIncrement((volatile signed __int32 *)&v41[2].OwningThread);
      v49 = v67;
      *(_QWORD *)v67 = v41;
      *((_QWORD *)v49 + 1) = res;
    }
  }
  SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v63);
  ATL::CComPtr<LDAPConnection>::~CComPtr<LDAPConnection>(&lpCriticalSection);
  return SingleEntry;
}

```

## disassembly

```asm
0x18001d04c  push    rbp
0x18001d04e  push    rsi
0x18001d04f  push    rdi
0x18001d050  push    r12
0x18001d052  push    r13
0x18001d054  push    r14
0x18001d056  push    r15
0x18001d058  sub     rsp, 190h
0x18001d05f  lea     rbp, [rsp+30h]
0x18001d064  mov     [rbp+190h+arg_10], rbx
0x18001d06b  mov     rax, cs:__security_cookie
0x18001d072  xor     rax, rbp
0x18001d075  mov     [rbp+190h+var_40], rax
0x18001d07c  mov     [rbp+190h+var_150], r9
0x18001d080  mov     [rbp+190h+var_170], r8d
0x18001d084  mov     rsi, rdx
0x18001d087  mov     [rbp+190h+Source], rdx
0x18001d08b  mov     rbx, rcx
0x18001d08e  mov     rax, [rbp+190h+arg_20]
0x18001d095  mov     [rbp+190h+var_148], rax
0x18001d099  lea     rcx, [rbp+190h+lpCriticalSection]; void *
0x18001d09d  call    ??0?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::CComPtr<IRequest>(void)
0x18001d0a2  nop
0x18001d0a3  xor     ecx, ecx; this
0x18001d0a5  mov     [rbp+190h+MaxCount], rcx
0x18001d0a9  lea     r8, [rbp+190h+MaxCount]; struct NTDomain **
0x18001d0ad  mov     rdx, rbx; unsigned __int16 *
0x18001d0b0  call    ?getDomain@NTCache@@QEAAKPEBGPEAPEAVNTDomain@@@Z; NTCache::getDomain(ushort const *,NTDomain * *)
0x18001d0b5  mov     edi, eax
0x18001d0b7  xor     edx, edx
0x18001d0b9  test    eax, eax
0x18001d0bb  jnz     loc_18001D500
0x18001d0c1  lea     rdx, [rbp+190h+lpCriticalSection]; struct LDAPConnection **
0x18001d0c5  mov     rcx, [rbp+190h+MaxCount]; this
0x18001d0c9  call    ?getConnection@NTDomain@@QEAAKPEAPEAVLDAPConnection@@@Z; NTDomain::getConnection(LDAPConnection * *)
0x18001d0ce  mov     edi, eax
0x18001d0d0  mov     rcx, [rbp+190h+MaxCount]; this
0x18001d0d4  call    ?Release@NTDomain@@QEAAXXZ; NTDomain::Release(void)
0x18001d0d9  xor     edx, edx
0x18001d0db  test    edi, edi
0x18001d0dd  jnz     loc_18001D504
0x18001d0e3  lea     r12, WPP_GLOBAL_Control
0x18001d0ea  lea     edi, [rdx+8]
0x18001d0ed  mov     r14b, 4
0x18001d0f0  mov     rax, cs:WPP_GLOBAL_Control
0x18001d0f7  cmp     rax, r12
0x18001d0fa  jz      short loc_18001D15B
0x18001d0fc  cmp     [rax+19h], r14b
0x18001d100  jb      short loc_18001D15B
0x18001d102  test    [rax+1Ch], r14b
0x18001d106  jz      short loc_18001D15B
0x18001d108  lea     rcx, [rbp+190h+lpCriticalSection]
0x18001d10c  call    ??C?$CComPtrBase@VLDAPConnection@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@VLDAPConnection@@@1@XZ; ATL::CComPtrBase<LDAPConnection>::operator->(void)
0x18001d111  lea     rbx, [rax+40h]
0x18001d115  cmp     [rbx+18h], rdi
0x18001d119  jb      short loc_18001D120
0x18001d11b  mov     rdx, [rbx]
0x18001d11e  jmp     short loc_18001D123
0x18001d120  mov     rdx, rbx
0x18001d123  lea     rcx, aSendingLdapSea; "Sending LDAP search to %S."
0x18001d12a  call    WppDbgPrint
0x18001d12f  cmp     [rbx+18h], rdi
0x18001d133  jb      short loc_18001D138
0x18001d135  mov     rbx, [rbx]
0x18001d138  mov     edx, 12h
0x18001d13d  mov     [rsp+1C0h+var_1A0], rbx
0x18001d142  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001d149  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d150  mov     rcx, [rcx+10h]
0x18001d154  call    WPP_SF_sS
0x18001d159  xor     edx, edx
0x18001d15b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001d15f  inc     r13
0x18001d162  cmp     [rsi+r13*2], dx
0x18001d167  jnz     short loc_18001D15F
0x18001d169  mov     r15d, edx
0x18001d16c  mov     ebx, edx
0x18001d16e  test    r13, r13
0x18001d171  jz      short loc_18001D19F
0x18001d173  mov     edx, ebx
0x18001d175  movzx   edx, word ptr [rsi+rdx*2]; Ch
0x18001d179  lea     rcx, Str; "*()\\/"
0x18001d180  call    cs:__imp_wcschr
0x18001d186  lea     ecx, [r15+1]
0x18001d18a  xor     edx, edx
0x18001d18c  test    rax, rax
0x18001d18f  cmovz   ecx, r15d
0x18001d193  mov     r15d, ecx
0x18001d196  inc     ebx
0x18001d198  mov     eax, ebx
0x18001d19a  cmp     rax, r13
0x18001d19d  jb      short loc_18001D173
0x18001d19f  lea     eax, ds:0[r15*2]
0x18001d1a7  add     eax, r13d
0x18001d1aa  mov     dword ptr [rbp+190h+MaxCount], eax
0x18001d1ad  add     eax, 14h
0x18001d1b0  mov     [rbp+190h+SizeInWords], rax
0x18001d1b4  lea     rsi, [rax+rax]
0x18001d1b8  mov     rbx, rdx
0x18001d1bb  test    rsi, rsi
0x18001d1be  jz      short loc_18001D21F
0x18001d1c0  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001d1c7  ja      short loc_18001D21F
0x18001d1c9  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001d1d0  add     rcx, rdi
0x18001d1d3  add     rcx, rsi
0x18001d1d6  cmp     rcx, rsi
0x18001d1d9  jb      short loc_18001D21F
0x18001d1db  call    VerifyStackAvailable
0x18001d1e0  test    eax, eax
0x18001d1e2  jz      short loc_18001D21F
0x18001d1e4  lea     rax, [rsi+8]
0x18001d1e8  lea     rcx, [rax+0Fh]
0x18001d1ec  cmp     rcx, rax
0x18001d1ef  ja      short loc_18001D1FB
0x18001d1f1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001d1fb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d1ff  mov     rax, rcx
0x18001d202  call    _alloca_probe
0x18001d207  sub     rsp, rcx
0x18001d20a  lea     rbx, [rsp+1C0h+lpCriticalSection]
0x18001d20f  test    rbx, rbx
0x18001d212  jz      short loc_18001D21F
0x18001d214  mov     dword ptr [rbx], 6B637453h
0x18001d21a  add     rbx, rdi
0x18001d21d  jnz     short loc_18001D252
0x18001d21f  lea     rcx, [rsi+8]
0x18001d223  cmp     rcx, rsi
0x18001d226  jb      short loc_18001D249
0x18001d228  mov     rax, cs:g_pfnAllocate
0x18001d22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d234  mov     rbx, rax
0x18001d237  test    rax, rax
0x18001d23a  jz      loc_18001D648
0x18001d240  mov     dword ptr [rax], 70616548h
0x18001d246  add     rbx, rdi
0x18001d249  test    rbx, rbx
0x18001d24c  jz      loc_18001D648
0x18001d252  mov     [rbp+190h+var_168], rbx
0x18001d256  mov     r8, rsi; Size
0x18001d259  xor     edx, edx; Val
0x18001d25b  mov     rcx, rbx; void *
0x18001d25e  call    memset_0
0x18001d263  lea     r8, aSamaccountname; "(sAMAccountName="
0x18001d26a  mov     rsi, [rbp+190h+SizeInWords]
0x18001d26e  mov     rdx, rsi; SizeInWords
0x18001d271  mov     rcx, rbx; Destination
0x18001d274  call    cs:__imp_wcscpy_s
0x18001d27a  xor     edx, edx
0x18001d27c  test    r15d, r15d
0x18001d27f  jnz     short loc_18001D29F
0x18001d281  mov     r9d, 100h; MaxCount
0x18001d287  mov     r8, [rbp+190h+Source]; Source
0x18001d28b  mov     rdx, rsi; SizeInWords
0x18001d28e  mov     rcx, rbx; Destination
0x18001d291  call    cs:__imp_wcsncat_s
0x18001d297  xor     r13d, r13d
0x18001d29a  jmp     loc_18001D3A4
0x18001d29f  mov     eax, dword ptr [rbp+190h+MaxCount]
0x18001d2a2  inc     eax
0x18001d2a4  lea     r15, [rax+rax]
0x18001d2a8  mov     rsi, rdx
0x18001d2ab  test    r15, r15
0x18001d2ae  jz      short loc_18001D310
0x18001d2b0  cmp     r15, cs:g_ulMaxStackAllocSize
0x18001d2b7  ja      short loc_18001D310
0x18001d2b9  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001d2c0  add     rcx, 8
0x18001d2c4  add     rcx, r15
0x18001d2c7  cmp     rcx, r15
0x18001d2ca  jb      short loc_18001D310
0x18001d2cc  call    VerifyStackAvailable
0x18001d2d1  test    eax, eax
0x18001d2d3  jz      short loc_18001D310
0x18001d2d5  lea     rax, [r15+8]
0x18001d2d9  lea     rcx, [rax+0Fh]
0x18001d2dd  cmp     rcx, rax
0x18001d2e0  ja      short loc_18001D2EC
0x18001d2e2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001d2ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d2f0  mov     rax, rcx
0x18001d2f3  call    _alloca_probe
0x18001d2f8  sub     rsp, rcx
0x18001d2fb  lea     rsi, [rsp+1C0h+lpCriticalSection]
0x18001d300  test    rsi, rsi
0x18001d303  jz      short loc_18001D310
0x18001d305  mov     dword ptr [rsi], 6B637453h
0x18001d30b  add     rsi, rdi
0x18001d30e  jnz     short loc_18001D349
0x18001d310  lea     rcx, [r15+8]
0x18001d314  cmp     rcx, r15
0x18001d317  jb      short loc_18001D336
0x18001d319  mov     rax, cs:g_pfnAllocate
0x18001d320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d325  mov     rsi, rax
0x18001d328  test    rax, rax
0x18001d32b  jz      short loc_18001D33B
0x18001d32d  mov     dword ptr [rax], 70616548h
0x18001d333  add     rsi, rdi
0x18001d336  test    rsi, rsi
0x18001d339  jnz     short loc_18001D349
0x18001d33b  lea     rcx, [rbp+190h+var_168]; this
0x18001d33f  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18001d344  jmp     loc_18001D648
0x18001d349  mov     [rbp+190h+var_178], rsi
0x18001d34d  mov     r8, r15; Size
0x18001d350  xor     edx, edx; Val
0x18001d352  mov     rcx, rsi; void *
0x18001d355  call    memset_0
0x18001d35a  mov     r15d, dword ptr [rbp+190h+MaxCount]
0x18001d35e  mov     r9d, r15d; unsigned int
0x18001d361  mov     r8, rsi; unsigned __int16 *
0x18001d364  mov     rdx, r13; unsigned __int64
0x18001d367  mov     rcx, [rbp+190h+Source]; unsigned __int16 *
0x18001d36b  call    ?EscapeSpecialCharacters@@YAKPEBG_KPEAGK@Z; EscapeSpecialCharacters(ushort const *,unsigned __int64,ushort *,ulong)
0x18001d370  mov     edi, eax
0x18001d372  xor     r13d, r13d
0x18001d375  test    eax, eax
0x18001d377  jz      short loc_18001D384
0x18001d379  lea     rcx, [rbp+190h+var_178]; this
0x18001d37d  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18001d382  jmp     short loc_18001D33B
0x18001d384  mov     r9, r15; MaxCount
0x18001d387  mov     r8, rsi; Source
0x18001d38a  mov     rsi, [rbp+190h+SizeInWords]
0x18001d38e  mov     rdx, rsi; SizeInWords
0x18001d391  mov     rcx, rbx; Destination
0x18001d394  call    cs:__imp_wcsncat_s
0x18001d39a  nop
0x18001d39b  lea     rcx, [rbp+190h+var_178]; this
0x18001d39f  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18001d3a4  lea     r8, asc_1800361D8; ")"
0x18001d3ab  mov     rdx, rsi; SizeInWords
0x18001d3ae  mov     rcx, rbx; Destination
0x18001d3b1  call    cs:__imp_wcscat_s
0x18001d3b7  mov     rax, cs:WPP_GLOBAL_Control
0x18001d3be  cmp     rax, r12
0x18001d3c1  jz      short loc_18001D3FF
0x18001d3c3  cmp     [rax+19h], r14b
0x18001d3c7  jb      short loc_18001D3FF
0x18001d3c9  test    [rax+1Ch], r14b
0x18001d3cd  jz      short loc_18001D3FF
0x18001d3cf  mov     rdx, rbx
0x18001d3d2  lea     rcx, aUsingEncodedFi; "Using encoded filter %S for search "
0x18001d3d9  call    WppDbgPrint
0x18001d3de  mov     edx, 16h
0x18001d3e3  mov     [rsp+1C0h+var_1A0], rbx
0x18001d3e8  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001d3ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3f6  mov     rcx, [rcx+10h]
0x18001d3fa  call    WPP_SF_sS
0x18001d3ff  mov     [rbp+190h+res], r13
0x18001d403  lea     rdx, ?NO_ATTRS@@3PAPEAGA; ushort * near * NO_ATTRS
0x18001d40a  mov     r14d, [rbp+190h+var_170]
0x18001d40e  test    r14d, r14d
0x18001d411  mov     r15, [rbp+190h+var_150]
0x18001d415  cmovnz  rdx, r15
0x18001d419  lea     rcx, [rbp+190h+lpCriticalSection]
0x18001d41d  call    ??C?$CComPtrBase@VLDAPConnection@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@VLDAPConnection@@@1@XZ; ATL::CComPtrBase<LDAPConnection>::operator->(void)
0x18001d422  lea     rcx, [rbp+190h+res]
0x18001d426  mov     [rsp+1C0h+var_198], rcx; struct ldapmsg **
0x18001d42b  mov     [rsp+1C0h+var_1A0], rdx; unsigned __int16 **
0x18001d430  mov     r9, rbx; unsigned __int16 *
0x18001d433  mov     r8d, 2; unsigned int
0x18001d439  mov     rdx, [rax+70h]; unsigned __int16 *
0x18001d43d  mov     rdi, [rbp+190h+lpCriticalSection]
0x18001d441  mov     rcx, rdi; lpCriticalSection
0x18001d444  call    ?GetSingleEntry@@YAKPEAVLDAPConnection@@PEAGK1PEAPEAGPEAPEAUldapmsg@@@Z; GetSingleEntry(LDAPConnection *,ushort *,ulong,ushort *,ushort * *,ldapmsg * *)
0x18001d449  mov     esi, eax
0x18001d44b  test    eax, eax
0x18001d44d  jnz     loc_18001D4E6
0x18001d453  test    r14d, r14d
0x18001d456  jnz     short loc_18001D4D3
0x18001d458  mov     rbx, [rbp+190h+res]
0x18001d45c  lea     rcx, [rbp+190h+lpCriticalSection]
0x18001d460  call    ??D?$CComPtrBase@VLDAPConnection@@@ATL@@QEBAAEAVLDAPConnection@@XZ; ATL::CComPtrBase<LDAPConnection>::operator*(void)
0x18001d465  mov     rdx, rbx; res
0x18001d468  mov     rcx, [rax+58h]; ld
0x18001d46c  call    cs:__imp_ldap_first_entry
0x18001d472  mov     rbx, rax
0x18001d475  lea     rcx, [rbp+190h+lpCriticalSection]
0x18001d479  call    ??D?$CComPtrBase@VLDAPConnection@@@ATL@@QEBAAEAVLDAPConnection@@XZ; ATL::CComPtrBase<LDAPConnection>::operator*(void)
0x18001d47e  mov     rdx, rbx; entry
0x18001d481  mov     rcx, [rax+58h]; ld
0x18001d485  call    cs:__imp_ldap_get_dnW
0x18001d48b  mov     rbx, rax
0x18001d48e  mov     rcx, [rbp+190h+res]; res
0x18001d492  call    cs:__imp_ldap_msgfree
0x18001d498  lea     rcx, [rbp+190h+lpCriticalSection]
0x18001d49c  call    ??B?$CComPtrBase@VLDAPConnection@@@ATL@@QEBAPEAVLDAPConnection@@XZ; ATL::CComPtrBase<LDAPConnection>::operator LDAPConnection *(void)
0x18001d4a1  mov     rcx, rax; lpCriticalSection
0x18001d4a4  lea     rax, [rbp+190h+res]
0x18001d4a8  mov     [rsp+1C0h+var_198], rax; struct ldapmsg **
0x18001d4ad  mov     [rsp+1C0h+var_1A0], r15; unsigned __int16 **
0x18001d4b2  lea     r9, filter; "(objectclass=*)"
0x18001d4b9  xor     r8d, r8d; unsigned int
0x18001d4bc  mov     rdx, rbx; unsigned __int16 *
0x18001d4bf  call    ?GetSingleEntry@@YAKPEAVLDAPConnection@@PEAGK1PEAPEAGPEAPEAUldapmsg@@@Z; GetSingleEntry(LDAPConnection *,ushort *,ulong,ushort *,ushort * *,ldapmsg * *)
0x18001d4c4  mov     esi, eax
0x18001d4c6  mov     rcx, rbx; Block
  ... truncated ...
```

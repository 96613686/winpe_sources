# TSLSLoadLocalGroupSecDes(void)

- ea: `0x1800385d8`
- end: `0x180038a98`
- name: `?TSLSLoadLocalGroupSecDes@@YAHXZ`
- size: `1216`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dab8`
- `0x180037a5c`

## callees

- `0x180002974`
- `0x180002be4`
- `0x180002c54`
- `0x18000d060`
- `0x18001ae3c`
- `0x180031db8`
- `0x180031f3c`
- `0x1800320d0`
- `0x1800385d8`
- `0x18006d850`
- `0x180078870`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180038a72`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180038a72`
- `ADVAPI32!AddAccessAllowedAce` at `0x180038a49`
- `ADVAPI32!AddAccessAllowedAce` at `0x180038a49`
- `ADVAPI32!InitializeAcl` at `0x180038913`
- `ADVAPI32!InitializeAcl` at `0x180038913`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800388ca`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800388ca`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800388ad`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800388ad`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180038888`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180038888`
- `ADVAPI32!GetLengthSid` at `0x180038850`
- `ADVAPI32!GetLengthSid` at `0x1800388dd`
- `ADVAPI32!GetLengthSid` at `0x180038850`
- `ADVAPI32!GetLengthSid` at `0x1800388dd`
- `ADVAPI32!LookupAccountNameW` at `0x1800387a0`
- `ADVAPI32!LookupAccountNameW` at `0x180038835`
- `ADVAPI32!LookupAccountNameW` at `0x1800387a0`
- `ADVAPI32!LookupAccountNameW` at `0x180038835`
- `NETAPI32!DsRoleFreeMemory` at `0x180038944`
- `NETAPI32!DsRoleFreeMemory` at `0x180038944`
- `KERNEL32!GetComputerNameW` at `0x180038731`
- `KERNEL32!GetComputerNameW` at `0x180038731`
- `KERNEL32!GetLastError` at `0x180038741`
- `KERNEL32!GetLastError` at `0x1800387b0`
- `KERNEL32!GetLastError` at `0x180038927`
- `KERNEL32!GetLastError` at `0x180038741`
- `KERNEL32!GetLastError` at `0x1800387b0`
- `KERNEL32!GetLastError` at `0x180038927`
- `KERNEL32!LocalAlloc` at `0x1800387cb`
- `KERNEL32!LocalAlloc` at `0x1800387f2`
- `KERNEL32!LocalAlloc` at `0x180038864`
- `KERNEL32!LocalAlloc` at `0x1800388f0`
- `KERNEL32!LocalAlloc` at `0x1800387cb`
- `KERNEL32!LocalAlloc` at `0x1800387f2`
- `KERNEL32!LocalAlloc` at `0x180038864`
- `KERNEL32!LocalAlloc` at `0x1800388f0`
- `KERNEL32!LocalFree` at `0x180038958`
- `KERNEL32!LocalFree` at `0x180038970`
- `KERNEL32!LocalFree` at `0x18003898b`
- `KERNEL32!LocalFree` at `0x1800389a6`
- `KERNEL32!LocalFree` at `0x180038958`
- `KERNEL32!LocalFree` at `0x180038970`
- `KERNEL32!LocalFree` at `0x18003898b`
- `KERNEL32!LocalFree` at `0x1800389a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 TSLSLoadLocalGroupSecDes(void)
{
  WCHAR *ReferencedDomainName; // rbx
  unsigned int v1; // edx
  unsigned __int16 *v2; // rcx
  DWORD LengthSid; // eax
  HLOCAL v4; // rax
  DWORD v5; // edi
  struct _ACL *v6; // rax
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD nSize[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v11; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-A8h] BYREF
  PVOID v13; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v14[3]; // [rsp+70h] [rbp-98h] BYREF
  WCHAR AccountName[520]; // [rsp+88h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+498h] [rbp+390h] BYREF

  ReferencedDomainName = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  nSize[0] = 0;
  nSize[1] = 260;
  v13 = 0;
  if ( dword_1800E9780 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800E9780);
    if ( dword_1800E9780 == -1 )
    {
      CCriticalSection::CCriticalSection((CCriticalSection *)qword_1800E9788, v1);
      atexit(TSLSLoadLocalGroupSecDes_::_2_::_dynamic_atexit_destructor_for__zFuncLock__);
      Init_thread_footer(&dword_1800E9780);
    }
  }
  v14[1] = qword_1800E9788;
  CCriticalSection::Lock((CCriticalSection *)qword_1800E9788);
  v11 = 0;
  v12 = 0;
  v2 = (unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
      L"TSLSLoadLocalGroupSecDes");
  if ( (int)ConvertSidToAccountName(v2, &v11, &v12) < 0 )
    goto LABEL_28;
  if ( g_pSid && g_Dacl && g_pSecDes )
  {
LABEL_40:
    CCriticalSection::UnLock((CCriticalSection *)qword_1800E9788);
    return 1;
  }
  if ( !(unsigned int)IsLSonDC(v14, &v13) )
  {
    if ( !GetComputerNameW(Buffer, &nSize[1]) )
      goto LABEL_23;
    StringCchPrintfW(AccountName, 0x204u, L"%s\\%s", v12, v11);
    ReferencedDomainName = 0;
    if ( !LookupAccountNameW(0, AccountName, 0, &cbSid, 0, &cchReferencedDomainName, (PSID_NAME_USE)nSize)
      && GetLastError() != 122 )
    {
      goto LABEL_24;
    }
    g_pSid = LocalAlloc(0, cbSid);
    if ( !g_pSid )
      goto LABEL_24;
    ReferencedDomainName = (WCHAR *)LocalAlloc(0, 2LL * (cchReferencedDomainName + 1));
    if ( !ReferencedDomainName )
      goto LABEL_24;
    if ( !LookupAccountNameW(
            0,
            AccountName,
            g_pSid,
            &cbSid,
            ReferencedDomainName,
            &cchReferencedDomainName,
            (PSID_NAME_USE)nSize) )
      goto LABEL_23;
    LengthSid = GetLengthSid(g_pSid);
    v4 = LocalAlloc(0, 3 * (LengthSid + 20));
    g_pSecDes = v4;
    if ( !v4 )
      goto LABEL_24;
    if ( !InitializeSecurityDescriptor(v4, 1u) )
    {
LABEL_23:
      GetLastError();
      goto LABEL_24;
    }
    SetSecurityDescriptorOwner(g_pSecDes, g_pSid, 0);
    SetSecurityDescriptorGroup(g_pSecDes, g_pSid, 0);
    v5 = GetLengthSid(g_pSid) + 16;
    v6 = (struct _ACL *)LocalAlloc(0, v5);
    g_Dacl = v6;
    if ( v6 )
    {
      if ( InitializeAcl(v6, v5, 2u)
        && AddAccessAllowedAce((PACL)g_Dacl, 2u, 0x20000u, g_pSid)
        && SetSecurityDescriptorDacl(g_pSecDes, 1, (PACL)g_Dacl, 0) )
      {
        goto LABEL_40;
      }
      goto LABEL_23;
    }
  }
LABEL_24:
  if ( v13 )
    DsRoleFreeMemory(v13);
  if ( ReferencedDomainName )
    LocalFree(ReferencedDomainName);
LABEL_28:
  if ( g_pSid )
    LocalFree(g_pSid);
  if ( g_Dacl )
    LocalFree(g_Dacl);
  if ( g_pSecDes )
    LocalFree(g_pSecDes);
  g_pSid = 0;
  g_Dacl = 0;
  g_pSecDes = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
      L"TSLSLoadLocalGroupSecDes");
  CCriticalSection::UnLock((CCriticalSection *)qword_1800E9788);
  return 0;
}

```

## disassembly

```asm
0x1800385d8  mov     rax, rsp
0x1800385db  mov     [rax+8], rbx
0x1800385df  mov     [rax+10h], rsi
0x1800385e3  mov     [rax+18h], rdi
0x1800385e7  mov     [rax+20h], r14
0x1800385eb  push    rbp
0x1800385ec  lea     rbp, [rax-5B8h]
0x1800385f3  sub     rsp, 6B0h
0x1800385fa  mov     rax, cs:__security_cookie
0x180038601  xor     rax, rsp
0x180038604  mov     [rbp+5B0h+var_10], rax
0x18003860b  xor     esi, esi
0x18003860d  mov     ebx, esi
0x18003860f  mov     [rsp+6B0h+cbSid], esi
0x180038613  mov     [rsp+6B0h+var_670], esi
0x180038617  mov     [rsp+6B0h+nSize], esi
0x18003861b  mov     [rsp+6B0h+nSize+4], 104h
0x180038623  mov     [rsp+6B0h+var_650], rsi
0x180038628  mov     ecx, cs:_tls_index
0x18003862e  mov     rax, gs:58h
0x180038637  mov     edx, 4
0x18003863c  mov     rax, [rax+rcx*8]
0x180038640  lea     r14, qword_1800E9788
0x180038647  mov     eax, [rdx+rax]
0x18003864a  cmp     cs:dword_1800E9780, eax
0x180038650  jle     short loc_180038688
0x180038652  lea     rcx, dword_1800E9780
0x180038659  call    _Init_thread_header
0x18003865e  cmp     cs:dword_1800E9780, 0FFFFFFFFh
0x180038665  jnz     short loc_180038688
0x180038667  mov     rcx, r14; this
0x18003866a  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x18003866f  lea     rcx, _TSLSLoadLocalGroupSecDes____2____dynamic_atexit_destructor_for__zFuncLock__; void (__cdecl *)()
0x180038676  call    atexit
0x18003867b  nop
0x18003867c  lea     rcx, dword_1800E9780
0x180038683  call    _Init_thread_footer
0x180038688  mov     [rsp+6B0h+var_640], r14
0x18003868d  mov     rcx, r14; this
0x180038690  call    ?Lock@CCriticalSection@@QEAAXXZ; CCriticalSection::Lock(void)
0x180038695  nop
0x180038696  mov     [rsp+6B0h+var_660], rsi
0x18003869b  mov     [rsp+6B0h+var_658], rsi
0x1800386a0  lea     rdi, WPP_GLOBAL_Control
0x1800386a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386ae  cmp     rcx, rdi
0x1800386b1  jz      short loc_1800386D8
0x1800386b3  test    dword ptr [rcx+1Ch], 1000h
0x1800386ba  jz      short loc_1800386D8
0x1800386bc  mov     edx, 27h ; '''
0x1800386c1  lea     r9, aTslsloadlocalg; "TSLSLoadLocalGroupSecDes"
0x1800386c8  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x1800386cf  mov     rcx, [rcx+10h]
0x1800386d3  call    WPP_SF_S
0x1800386d8  lea     r8, [rsp+6B0h+var_658]; unsigned __int16 **
0x1800386dd  lea     rdx, [rsp+6B0h+var_660]; unsigned __int16 **
0x1800386e2  call    ?ConvertSidToAccountName@@YAJPEAGPEAPEAG1@Z; ConvertSidToAccountName(ushort *,ushort * *,ushort * *)
0x1800386e7  test    eax, eax
0x1800386e9  js      loc_180038964
0x1800386ef  cmp     cs:?g_pSid@@3PEAXEA, rsi; void * g_pSid
0x1800386f6  jz      short loc_18003870E
0x1800386f8  cmp     cs:?g_Dacl@@3PEAU_ACL@@EA, rsi; _ACL * g_Dacl
0x1800386ff  jz      short loc_18003870E
0x180038701  cmp     cs:?g_pSecDes@@3PEAXEA, rsi; void * g_pSecDes
0x180038708  jnz     loc_180038A86
0x18003870e  lea     rdx, [rsp+6B0h+var_650]
0x180038713  lea     rcx, [rsp+6B0h+var_648]
0x180038718  call    IsLSonDC
0x18003871d  test    eax, eax
0x18003871f  jnz     loc_18003893A
0x180038725  lea     rdx, [rsp+6B0h+nSize+4]; nSize
0x18003872a  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x180038731  call    cs:__imp_GetComputerNameW
0x180038738  nop     dword ptr [rax+rax+00h]
0x18003873d  test    eax, eax
0x18003873f  jnz     short loc_180038752
0x180038741  call    cs:__imp_GetLastError
0x180038748  nop     dword ptr [rax+rax+00h]
0x18003874d  jmp     loc_18003893A
0x180038752  mov     rax, [rsp+6B0h+var_660]
0x180038757  mov     [rsp+6B0h+ReferencedDomainName], rax
0x18003875c  mov     r9, [rsp+6B0h+var_658]
0x180038761  lea     r8, aSS_0; "%s\\%s"
0x180038768  mov     edx, 204h; unsigned __int64
0x18003876d  lea     rcx, [rbp+5B0h+AccountName]; unsigned __int16 *
0x180038771  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038776  mov     rbx, rsi
0x180038779  lea     rax, [rsp+6B0h+nSize]
0x18003877e  mov     [rsp+6B0h+peUse], rax; peUse
0x180038783  lea     rax, [rsp+6B0h+var_670]
0x180038788  mov     [rsp+6B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003878d  mov     [rsp+6B0h+ReferencedDomainName], rsi; ReferencedDomainName
0x180038792  lea     r9, [rsp+6B0h+cbSid]; cbSid
0x180038797  xor     r8d, r8d; Sid
0x18003879a  lea     rdx, [rbp+5B0h+AccountName]; lpAccountName
0x18003879e  xor     ecx, ecx; lpSystemName
0x1800387a0  call    cs:__imp_LookupAccountNameW
0x1800387a7  nop     dword ptr [rax+rax+00h]
0x1800387ac  test    eax, eax
0x1800387ae  jnz     short loc_1800387C5
0x1800387b0  call    cs:__imp_GetLastError
0x1800387b7  nop     dword ptr [rax+rax+00h]
0x1800387bc  cmp     eax, 7Ah ; 'z'
0x1800387bf  jnz     loc_18003893A
0x1800387c5  mov     edx, [rsp+6B0h+cbSid]; uBytes
0x1800387c9  xor     ecx, ecx; uFlags
0x1800387cb  call    cs:__imp_LocalAlloc
0x1800387d2  nop     dword ptr [rax+rax+00h]
0x1800387d7  mov     cs:?g_pSid@@3PEAXEA, rax; void * g_pSid
0x1800387de  test    rax, rax
0x1800387e1  jz      loc_18003893A
0x1800387e7  mov     edx, [rsp+6B0h+var_670]
0x1800387eb  inc     edx
0x1800387ed  add     rdx, rdx; uBytes
0x1800387f0  xor     ecx, ecx; uFlags
0x1800387f2  call    cs:__imp_LocalAlloc
0x1800387f9  nop     dword ptr [rax+rax+00h]
0x1800387fe  mov     rbx, rax
0x180038801  test    rax, rax
0x180038804  jz      loc_18003893A
0x18003880a  lea     rax, [rsp+6B0h+nSize]
0x18003880f  mov     [rsp+6B0h+peUse], rax; peUse
0x180038814  lea     rax, [rsp+6B0h+var_670]
0x180038819  mov     [rsp+6B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003881e  mov     [rsp+6B0h+ReferencedDomainName], rbx; ReferencedDomainName
0x180038823  lea     r9, [rsp+6B0h+cbSid]; cbSid
0x180038828  mov     r8, cs:?g_pSid@@3PEAXEA; Sid
0x18003882f  lea     rdx, [rbp+5B0h+AccountName]; lpAccountName
0x180038833  xor     ecx, ecx; lpSystemName
0x180038835  call    cs:__imp_LookupAccountNameW
0x18003883c  nop     dword ptr [rax+rax+00h]
0x180038841  test    eax, eax
0x180038843  jz      loc_180038741
0x180038849  mov     rcx, cs:?g_pSid@@3PEAXEA; pSid
0x180038850  call    cs:__imp_GetLengthSid
0x180038857  nop     dword ptr [rax+rax+00h]
0x18003885c  add     eax, 14h
0x18003885f  lea     edx, [rax+rax*2]; uBytes
0x180038862  xor     ecx, ecx; uFlags
0x180038864  call    cs:__imp_LocalAlloc
0x18003886b  nop     dword ptr [rax+rax+00h]
0x180038870  mov     cs:?g_pSecDes@@3PEAXEA, rax; void * g_pSecDes
0x180038877  test    rax, rax
0x18003887a  jz      loc_18003893A
0x180038880  mov     edx, 1; dwRevision
0x180038885  mov     rcx, rax; pSecurityDescriptor
0x180038888  call    cs:__imp_InitializeSecurityDescriptor
0x18003888f  nop     dword ptr [rax+rax+00h]
0x180038894  test    eax, eax
0x180038896  jz      loc_180038741
0x18003889c  xor     r8d, r8d; bOwnerDefaulted
0x18003889f  mov     rdx, cs:?g_pSid@@3PEAXEA; pOwner
0x1800388a6  mov     rcx, cs:?g_pSecDes@@3PEAXEA; pSecurityDescriptor
0x1800388ad  call    cs:__imp_SetSecurityDescriptorOwner
0x1800388b4  nop     dword ptr [rax+rax+00h]
0x1800388b9  xor     r8d, r8d; bGroupDefaulted
0x1800388bc  mov     rdx, cs:?g_pSid@@3PEAXEA; pGroup
0x1800388c3  mov     rcx, cs:?g_pSecDes@@3PEAXEA; pSecurityDescriptor
0x1800388ca  call    cs:__imp_SetSecurityDescriptorGroup
0x1800388d1  nop     dword ptr [rax+rax+00h]
0x1800388d6  mov     rcx, cs:?g_pSid@@3PEAXEA; pSid
0x1800388dd  call    cs:__imp_GetLengthSid
0x1800388e4  nop     dword ptr [rax+rax+00h]
0x1800388e9  lea     edi, [rax+10h]
0x1800388ec  mov     edx, edi; uBytes
0x1800388ee  xor     ecx, ecx; uFlags
0x1800388f0  call    cs:__imp_LocalAlloc
0x1800388f7  nop     dword ptr [rax+rax+00h]
0x1800388fc  mov     cs:?g_Dacl@@3PEAU_ACL@@EA, rax; _ACL * g_Dacl
0x180038903  test    rax, rax
0x180038906  jz      short loc_180038933
0x180038908  mov     r8d, 2; dwAclRevision
0x18003890e  mov     edx, edi; nAclLength
0x180038910  mov     rcx, rax; pAcl
0x180038913  call    cs:__imp_InitializeAcl
0x18003891a  nop     dword ptr [rax+rax+00h]
0x18003891f  test    eax, eax
0x180038921  jnz     loc_180038A30
0x180038927  call    cs:__imp_GetLastError
0x18003892e  nop     dword ptr [rax+rax+00h]
0x180038933  lea     rdi, WPP_GLOBAL_Control
0x18003893a  mov     rcx, [rsp+6B0h+var_650]; Buffer
0x18003893f  test    rcx, rcx
0x180038942  jz      short loc_180038950
0x180038944  call    cs:__imp_DsRoleFreeMemory
0x18003894b  nop     dword ptr [rax+rax+00h]
0x180038950  test    rbx, rbx
0x180038953  jz      short loc_180038964
0x180038955  mov     rcx, rbx; hMem
0x180038958  call    cs:__imp_LocalFree
0x18003895f  nop     dword ptr [rax+rax+00h]
0x180038964  mov     rcx, cs:?g_pSid@@3PEAXEA; hMem
0x18003896b  test    rcx, rcx
0x18003896e  jz      short loc_18003897C
0x180038970  call    cs:__imp_LocalFree
0x180038977  nop     dword ptr [rax+rax+00h]
0x18003897c  mov     rax, cs:?g_Dacl@@3PEAU_ACL@@EA; _ACL * g_Dacl
0x180038983  test    rax, rax
0x180038986  jz      short loc_180038997
0x180038988  mov     rcx, rax; hMem
0x18003898b  call    cs:__imp_LocalFree
0x180038992  nop     dword ptr [rax+rax+00h]
0x180038997  mov     rax, cs:?g_pSecDes@@3PEAXEA; void * g_pSecDes
0x18003899e  test    rax, rax
0x1800389a1  jz      short loc_1800389B2
0x1800389a3  mov     rcx, rax; hMem
0x1800389a6  call    cs:__imp_LocalFree
0x1800389ad  nop     dword ptr [rax+rax+00h]
0x1800389b2  mov     cs:?g_pSid@@3PEAXEA, rsi; void * g_pSid
0x1800389b9  mov     cs:?g_Dacl@@3PEAU_ACL@@EA, rsi; _ACL * g_Dacl
0x1800389c0  mov     cs:?g_pSecDes@@3PEAXEA, rsi; void * g_pSecDes
0x1800389c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389ce  cmp     rcx, rdi
0x1800389d1  jz      short loc_1800389F9
0x1800389d3  test    dword ptr [rcx+1Ch], 1000h
0x1800389da  jz      short loc_1800389F9
0x1800389dc  mov     edx, 28h ; '('
0x1800389e1  lea     r9, aTslsloadlocalg; "TSLSLoadLocalGroupSecDes"
0x1800389e8  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x1800389ef  mov     rcx, [rcx+10h]
0x1800389f3  call    WPP_SF_S
0x1800389f8  nop
0x1800389f9  mov     rcx, r14; this
0x1800389fc  call    ?UnLock@CCriticalSection@@QEAAXXZ; CCriticalSection::UnLock(void)
0x180038a01  xor     eax, eax
0x180038a03  mov     rcx, [rbp+5B0h+var_10]
0x180038a0a  xor     rcx, rsp; StackCookie
0x180038a0d  call    __security_check_cookie
0x180038a12  lea     r11, [rsp+6B0h+var_s0]
0x180038a1a  mov     rbx, [r11+10h]
0x180038a1e  mov     rsi, [r11+18h]
0x180038a22  mov     rdi, [r11+20h]
0x180038a26  mov     r14, [r11+28h]
0x180038a2a  mov     rsp, r11
0x180038a2d  pop     rbp
0x180038a2e  retn
0x180038a30  mov     r9, cs:?g_pSid@@3PEAXEA; pSid
0x180038a37  mov     edx, 2; dwAceRevision
0x180038a3c  mov     r8d, 20000h; AccessMask
0x180038a42  mov     rcx, cs:?g_Dacl@@3PEAU_ACL@@EA; pAcl
0x180038a49  call    cs:__imp_AddAccessAllowedAce
0x180038a50  nop     dword ptr [rax+rax+00h]
0x180038a55  test    eax, eax
0x180038a57  jz      loc_180038927
0x180038a5d  xor     r9d, r9d; bDaclDefaulted
0x180038a60  mov     r8, cs:?g_Dacl@@3PEAU_ACL@@EA; pDacl
0x180038a67  lea     edx, [r9+1]; bDaclPresent
0x180038a6b  mov     rcx, cs:?g_pSecDes@@3PEAXEA; pSecurityDescriptor
0x180038a72  call    cs:__imp_SetSecurityDescriptorDacl
0x180038a79  nop     dword ptr [rax+rax+00h]
0x180038a7e  test    eax, eax
0x180038a80  jz      loc_180038927
0x180038a86  mov     rcx, r14; this
0x180038a89  call    ?UnLock@CCriticalSection@@QEAAXXZ; CCriticalSection::UnLock(void)
0x180038a8e  mov     eax, 1
0x180038a93  jmp     loc_180038A03
```

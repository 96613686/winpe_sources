# GetMappedSID(ushort const *,ushort const *,void * const)

- ea: `0x18000e208`
- end: `0x18000e643`
- name: `?GetMappedSID@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0QEAX@Z`
- size: `1083`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eb2c`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x180005274`
- `0x18000536c`
- `0x18000c728`
- `0x18000d078`
- `0x18000d444`
- `0x18000d798`
- `0x18000e208`
- `0x180017e00`
- `0x18001b3f8`
- `0x18001f960`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e2c7`
- `msvcrt!_wcsicmp` at `0x18000e2ee`
- `msvcrt!_wcsicmp` at `0x18000e3d0`
- `msvcrt!_wcsicmp` at `0x18000e2c7`
- `msvcrt!_wcsicmp` at `0x18000e2ee`
- `msvcrt!_wcsicmp` at `0x18000e3d0`
- `ADVAPI32!LookupAccountSidW` at `0x18000e35b`
- `ADVAPI32!LookupAccountSidW` at `0x18000e420`
- `ADVAPI32!LookupAccountSidW` at `0x18000e35b`
- `ADVAPI32!LookupAccountSidW` at `0x18000e420`
- `USER32!SetCursor` at `0x18000e5ff`
- `USER32!SetCursor` at `0x18000e5ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall GetMappedSID(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3, void *a4)
{
  int v8; // r12d
  int v9; // r14d
  int v10; // r15d
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rdx
  int v13; // r14d
  CIDsCache *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  struct IDirectorySearch *v17; // rdx
  const unsigned __int16 *v18; // rdx
  CIDsCache *v19; // rcx
  int v20; // r15d
  __int64 v21; // rax
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  CIDsCache *v25; // rcx
  struct IDirectorySearch *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rdx
  CIDsCache *v29; // rcx
  struct IDirectorySearch *v30; // r8
  __int64 v31; // rax
  __int64 v32; // rdx
  CSidCache *v33; // rcx
  const unsigned __int16 *v34; // r8
  HCURSOR hCursor; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  struct IDirectorySearch *v40; // [rsp+58h] [rbp-A8h] BYREF
  struct IDirectorySearch *v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v43; // [rsp+70h] [rbp-90h]
  wchar_t *String2[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v45; // [rsp+90h] [rbp-70h]
  _BYTE v46[40]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v49[544]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v43 = a1;
  v8 = 0;
  std::wstring::wstring(a1);
  v9 = 1;
  v42 = 1;
  CWaitCursor::CWaitCursor((CWaitCursor *)&hCursor);
  if ( !(unsigned int)CLruCache::Fetch((CLruCache *)&g_SidCache, a4, v49, 0x220u) )
  {
    std::wstring::assign(a1, v49);
    goto LABEL_57;
  }
  GetComputerNameAsString(String2);
  if ( a2 )
  {
    v10 = 0;
    v11 = (const wchar_t *)String2;
    if ( v45 >= 8 )
      v11 = String2[0];
    if ( !_wcsicmp(a2, v11) )
      v10 = 1;
  }
  else
  {
    v10 = 1;
  }
  if ( a3 )
  {
    v9 = 0;
    v12 = (const wchar_t *)String2;
    if ( v45 >= 8 )
      v12 = String2[0];
    if ( !_wcsicmp(a3, v12) )
      v9 = 1;
  }
  if ( !v10 )
  {
    if ( v9 || _wcsicmp(a2, a3) )
      goto LABEL_16;
LABEL_23:
    v13 = 0;
    goto LABEL_17;
  }
  if ( v9 )
    goto LABEL_23;
LABEL_16:
  v13 = 1;
LABEL_17:
  cchName = 260;
  cchReferencedDomainName = 260;
  peUse = 0;
  if ( LookupAccountSidW(a2, a4, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
    || v13 && LookupAccountSidW(a3, a4, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    if ( ReferencedDomainName[0] )
    {
      std::wstring::assign(a1, ReferencedDomainName);
      v15 = std::char_traits<unsigned short>::length(L"\\");
      std::wstring::append(a1, L"\\", v15);
    }
    v16 = std::char_traits<unsigned short>::length(Name);
    std::wstring::append(a1, Name, v16);
    LOBYTE(v17) = 1;
    goto LABEL_56;
  }
  v40 = 0;
  v41 = 0;
  if ( a2 )
  {
    v18 = a2;
  }
  else
  {
    v18 = (const unsigned __int16 *)String2;
    if ( v45 >= 8 )
      v18 = String2[0];
  }
  v20 = CIDsCache::Fetch(v14, v18, &v40);
  v17 = v40;
  if ( v40 )
  {
    v21 = DoLdapQueryForSid(v46, v40, a4);
    std::wstring::operator=(a1, v21);
    std::wstring::_Tidy(v46, 1, 0);
    if ( *((_QWORD *)a1 + 2) )
      goto LABEL_55;
  }
  if ( !v13 )
    goto LABEL_43;
  if ( a3 )
  {
    v22 = a3;
  }
  else
  {
    v22 = (const unsigned __int16 *)String2;
    if ( v45 >= 8 )
      v22 = String2[0];
  }
  v8 = CIDsCache::Fetch(v19, v22, &v41);
  v17 = v41;
  if ( !v41 )
  {
LABEL_43:
    if ( v20 )
    {
LABEL_49:
      if ( !v8 )
      {
        v30 = DeriveGcFromServer(a3);
        v41 = v30;
        if ( v30 )
        {
          if ( !a3 )
          {
            a3 = (unsigned __int16 *)String2;
            if ( v45 >= 8 )
              a3 = String2[0];
          }
          CIDsCache::Add(v29, a3, v30);
          v31 = DoLdapQueryForSid(v46, v41, a4);
          std::wstring::operator=(a1, v31);
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v46, v32, 0);
        }
      }
      goto LABEL_55;
    }
LABEL_44:
    v26 = DeriveGcFromServer(a2);
    v40 = v26;
    if ( v26 )
    {
      if ( !a2 )
      {
        a2 = (unsigned __int16 *)String2;
        if ( v45 >= 8 )
          a2 = String2[0];
      }
      CIDsCache::Add(v25, a2, v26);
      v27 = DoLdapQueryForSid(v46, v40, a4);
      std::wstring::operator=(a1, v27);
      LOBYTE(v28) = 1;
      std::wstring::_Tidy(v46, v28, 0);
      if ( *((_QWORD *)a1 + 2) )
        goto LABEL_40;
    }
    goto LABEL_49;
  }
  if ( v40 == v41 )
  {
LABEL_55:
    LOBYTE(v17) = 1;
    goto LABEL_56;
  }
  v23 = DoLdapQueryForSid(v46, v41, a4);
  std::wstring::operator=(a1, v23);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(v46, v24, 0);
  if ( !*((_QWORD *)a1 + 2) && !v20 )
    goto LABEL_44;
LABEL_40:
  LOBYTE(v17) = 1;
LABEL_56:
  std::wstring::_Tidy(String2, v17, 0);
LABEL_57:
  SetCursor(hCursor);
  if ( *((_QWORD *)a1 + 3) < 8u )
    v34 = a1;
  else
    v34 = *(const unsigned __int16 **)a1;
  CSidCache::Add(v33, a4, v34);
  return a1;
}

```

## disassembly

```asm
0x18000e208  push    rbp
0x18000e20a  push    rbx
0x18000e20b  push    rsi
0x18000e20c  push    rdi
0x18000e20d  push    r12
0x18000e20f  push    r13
0x18000e211  push    r14
0x18000e213  push    r15
0x18000e215  lea     rbp, [rsp-618h]
0x18000e21d  sub     rsp, 718h
0x18000e224  mov     rax, cs:__security_cookie
0x18000e22b  xor     rax, rsp
0x18000e22e  mov     [rbp+650h+var_50], rax
0x18000e235  mov     r13, r9
0x18000e238  mov     rdi, r8
0x18000e23b  mov     rsi, rdx
0x18000e23e  mov     rbx, rcx
0x18000e241  mov     [rsp+750h+var_6E0], rcx
0x18000e246  xor     r12d, r12d
0x18000e249  mov     [rsp+750h+var_6E8], r12d
0x18000e24e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000e253  lea     r14d, [r12+1]
0x18000e258  mov     [rsp+750h+var_6E8], r14d
0x18000e25d  lea     rcx, [rsp+750h+hCursor]; this
0x18000e262  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000e267  nop
0x18000e268  mov     r9d, 220h; unsigned int
0x18000e26e  lea     r8, [rbp+650h+var_270]; void *
0x18000e275  mov     rdx, r13; void *
0x18000e278  lea     rcx, ?g_SidCache@@3VCSidCache@@A; this
0x18000e27f  call    ?Fetch@CLruCache@@UEAAJPEAX0K@Z; CLruCache::Fetch(void *,void *,ulong)
0x18000e284  test    eax, eax
0x18000e286  jnz     short loc_18000E29C
0x18000e288  lea     rdx, [rbp+650h+var_270]
0x18000e28f  mov     rcx, rbx
0x18000e292  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e297  jmp     loc_18000E5FA
0x18000e29c  lea     rcx, [rsp+750h+String2]
0x18000e2a1  call    ?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetComputerNameAsString(void)
0x18000e2a6  nop
0x18000e2a7  test    rsi, rsi
0x18000e2aa  jnz     short loc_18000E2B1
0x18000e2ac  mov     r15d, r14d
0x18000e2af  jmp     short loc_18000E2D3
0x18000e2b1  mov     r15d, r12d
0x18000e2b4  lea     rdx, [rsp+750h+String2]
0x18000e2b9  cmp     [rbp+650h+var_6C0], 8
0x18000e2be  cmovnb  rdx, [rsp+750h+String2]; String2
0x18000e2c4  mov     rcx, rsi; String1
0x18000e2c7  call    cs:__imp__wcsicmp
0x18000e2cd  test    eax, eax
0x18000e2cf  cmovz   r15d, r14d
0x18000e2d3  test    rdi, rdi
0x18000e2d6  jz      short loc_18000E2FF
0x18000e2d8  mov     r14d, r12d
0x18000e2db  lea     rdx, [rsp+750h+String2]
0x18000e2e0  cmp     [rbp+650h+var_6C0], 8
0x18000e2e5  cmovnb  rdx, [rsp+750h+String2]; String2
0x18000e2eb  mov     rcx, rdi; String1
0x18000e2ee  call    cs:__imp__wcsicmp
0x18000e2f4  test    eax, eax
0x18000e2f6  mov     edx, 1
0x18000e2fb  cmovz   r14d, edx
0x18000e2ff  test    r15d, r15d
0x18000e302  jz      loc_18000E3C1
0x18000e308  test    r14d, r14d
0x18000e30b  jnz     loc_18000E3DE
0x18000e311  mov     r15d, 1
0x18000e317  mov     r14d, r15d
0x18000e31a  mov     eax, 104h
0x18000e31f  mov     [rsp+750h+cchName], eax
0x18000e323  mov     [rsp+750h+var_704], eax
0x18000e327  mov     [rsp+750h+var_708], r12d
0x18000e32c  lea     rax, [rsp+750h+var_708]
0x18000e331  mov     [rsp+750h+peUse], rax; peUse
0x18000e336  lea     rax, [rsp+750h+var_704]
0x18000e33b  mov     [rsp+750h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000e340  lea     rax, [rbp+650h+var_690]
0x18000e344  mov     [rsp+750h+ReferencedDomainName], rax; ReferencedDomainName
0x18000e349  lea     r9, [rsp+750h+cchName]; cchName
0x18000e34e  lea     r8, [rbp+650h+Name]; Name
0x18000e355  mov     rdx, r13; Sid
0x18000e358  mov     rcx, rsi; lpSystemName
0x18000e35b  call    cs:__imp_LookupAccountSidW
0x18000e361  test    eax, eax
0x18000e363  jz      loc_18000E3EC
0x18000e369  cmp     [rbp+650h+var_690], r12w
0x18000e36e  jz      short loc_18000E39A
0x18000e370  lea     rdx, [rbp+650h+var_690]
0x18000e374  mov     rcx, rbx
0x18000e377  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e37c  lea     rcx, SubBlock; "\\"
0x18000e383  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e388  mov     r8, rax
0x18000e38b  lea     rdx, SubBlock; "\\"
0x18000e392  mov     rcx, rbx
0x18000e395  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e39a  lea     rcx, [rbp+650h+Name]
0x18000e3a1  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000e3a6  mov     r8, rax
0x18000e3a9  lea     rdx, [rbp+650h+Name]
0x18000e3b0  mov     rcx, rbx
0x18000e3b3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000e3b8  nop
0x18000e3b9  mov     dl, r15b
0x18000e3bc  jmp     loc_18000E5EC
0x18000e3c1  test    r14d, r14d
0x18000e3c4  jnz     loc_18000E311
0x18000e3ca  mov     rdx, rdi; String2
0x18000e3cd  mov     rcx, rsi; String1
0x18000e3d0  call    cs:__imp__wcsicmp
0x18000e3d6  test    eax, eax
0x18000e3d8  jnz     loc_18000E311
0x18000e3de  mov     r14d, r12d
0x18000e3e1  mov     r15d, 1
0x18000e3e7  jmp     loc_18000E31A
0x18000e3ec  test    r14d, r14d
0x18000e3ef  jz      short loc_18000E42E
0x18000e3f1  lea     rax, [rsp+750h+var_708]
0x18000e3f6  mov     [rsp+750h+peUse], rax; peUse
0x18000e3fb  lea     rax, [rsp+750h+var_704]
0x18000e400  mov     [rsp+750h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000e405  lea     rax, [rbp+650h+var_690]
0x18000e409  mov     [rsp+750h+ReferencedDomainName], rax; ReferencedDomainName
0x18000e40e  lea     r9, [rsp+750h+cchName]; cchName
0x18000e413  lea     r8, [rbp+650h+Name]; Name
0x18000e41a  mov     rdx, r13; Sid
0x18000e41d  mov     rcx, rdi; lpSystemName
0x18000e420  call    cs:__imp_LookupAccountSidW
0x18000e426  test    eax, eax
0x18000e428  jnz     loc_18000E369
0x18000e42e  mov     [rsp+750h+var_6F8], r12
0x18000e433  mov     [rsp+750h+var_6F0], r12
0x18000e438  test    rsi, rsi
0x18000e43b  jz      short loc_18000E442
0x18000e43d  mov     rdx, rsi
0x18000e440  jmp     short loc_18000E452
0x18000e442  lea     rdx, [rsp+750h+String2]
0x18000e447  cmp     [rbp+650h+var_6C0], 8
0x18000e44c  cmovnb  rdx, [rsp+750h+String2]; unsigned __int16 *
0x18000e452  lea     r8, [rsp+750h+var_6F8]; struct IDirectorySearch **
0x18000e457  call    ?Fetch@CIDsCache@@QEAAHPEBGPEAPEAUIDirectorySearch@@@Z; CIDsCache::Fetch(ushort const *,IDirectorySearch * *)
0x18000e45c  mov     r15d, eax
0x18000e45f  mov     rdx, [rsp+750h+var_6F8]
0x18000e464  test    rdx, rdx
0x18000e467  jz      short loc_18000E49A
0x18000e469  mov     r8, r13
0x18000e46c  lea     rcx, [rbp+650h+var_6B8]
0x18000e470  call    ?DoLdapQueryForSid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIDirectorySearch@@PEAX@Z; DoLdapQueryForSid(IDirectorySearch *,void *)
0x18000e475  mov     rdx, rax
0x18000e478  mov     rcx, rbx
0x18000e47b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e480  xor     r8d, r8d
0x18000e483  lea     edx, [r8+1]
0x18000e487  lea     rcx, [rbp+650h+var_6B8]
0x18000e48b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e490  cmp     [rbx+10h], r12
0x18000e494  jnz     loc_18000E5EA
0x18000e49a  test    r14d, r14d
0x18000e49d  jz      short loc_18000E51B
0x18000e49f  test    rdi, rdi
0x18000e4a2  jz      short loc_18000E4A9
0x18000e4a4  mov     rdx, rdi
0x18000e4a7  jmp     short loc_18000E4B9
0x18000e4a9  lea     rdx, [rsp+750h+String2]
0x18000e4ae  cmp     [rbp+650h+var_6C0], 8
0x18000e4b3  cmovnb  rdx, [rsp+750h+String2]; unsigned __int16 *
0x18000e4b9  lea     r8, [rsp+750h+var_6F0]; struct IDirectorySearch **
0x18000e4be  call    ?Fetch@CIDsCache@@QEAAHPEBGPEAPEAUIDirectorySearch@@@Z; CIDsCache::Fetch(ushort const *,IDirectorySearch * *)
0x18000e4c3  mov     r12d, eax
0x18000e4c6  mov     rdx, [rsp+750h+var_6F0]
0x18000e4cb  test    rdx, rdx
0x18000e4ce  jz      short loc_18000E51B
0x18000e4d0  cmp     [rsp+750h+var_6F8], rdx
0x18000e4d5  jz      loc_18000E5EA
0x18000e4db  mov     r8, r13
0x18000e4de  lea     rcx, [rbp+650h+var_6B8]
0x18000e4e2  call    ?DoLdapQueryForSid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIDirectorySearch@@PEAX@Z; DoLdapQueryForSid(IDirectorySearch *,void *)
0x18000e4e7  mov     rdx, rax
0x18000e4ea  mov     rcx, rbx
0x18000e4ed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e4f2  xor     r8d, r8d
0x18000e4f5  lea     r14d, [r8+1]
0x18000e4f9  mov     dl, r14b
0x18000e4fc  lea     rcx, [rbp+650h+var_6B8]
0x18000e500  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e505  cmp     qword ptr [rbx+10h], 0
0x18000e50a  jz      short loc_18000E514
0x18000e50c  mov     dl, r14b
0x18000e50f  jmp     loc_18000E5EC
0x18000e514  test    r15d, r15d
0x18000e517  jz      short loc_18000E524
0x18000e519  jmp     short loc_18000E50C
0x18000e51b  test    r15d, r15d
0x18000e51e  jnz     short loc_18000E588
0x18000e520  lea     r14d, [r15+1]
0x18000e524  mov     rcx, rsi; unsigned __int16 *
0x18000e527  call    ?DeriveGcFromServer@@YAPEAUIDirectorySearch@@PEBG@Z; DeriveGcFromServer(ushort const *)
0x18000e52c  mov     r8, rax; struct IDirectorySearch *
0x18000e52f  mov     [rsp+750h+var_6F8], rax
0x18000e534  test    rax, rax
0x18000e537  jz      short loc_18000E588
0x18000e539  test    rsi, rsi
0x18000e53c  jnz     short loc_18000E54E
0x18000e53e  lea     rsi, [rsp+750h+String2]
0x18000e543  cmp     [rbp+650h+var_6C0], 8
0x18000e548  cmovnb  rsi, [rsp+750h+String2]
0x18000e54e  mov     rdx, rsi; unsigned __int16 *
0x18000e551  call    ?Add@CIDsCache@@QEAAJPEBGPEAUIDirectorySearch@@@Z; CIDsCache::Add(ushort const *,IDirectorySearch *)
0x18000e556  mov     r8, r13
0x18000e559  mov     rdx, [rsp+750h+var_6F8]
0x18000e55e  lea     rcx, [rbp+650h+var_6B8]
0x18000e562  call    ?DoLdapQueryForSid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIDirectorySearch@@PEAX@Z; DoLdapQueryForSid(IDirectorySearch *,void *)
0x18000e567  mov     rdx, rax
0x18000e56a  mov     rcx, rbx
0x18000e56d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e572  xor     r8d, r8d
0x18000e575  mov     dl, r14b
0x18000e578  lea     rcx, [rbp+650h+var_6B8]
0x18000e57c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e581  cmp     qword ptr [rbx+10h], 0
0x18000e586  jnz     short loc_18000E50C
0x18000e588  test    r12d, r12d
0x18000e58b  jnz     short loc_18000E5EA
0x18000e58d  mov     rcx, rdi; unsigned __int16 *
0x18000e590  call    ?DeriveGcFromServer@@YAPEAUIDirectorySearch@@PEBG@Z; DeriveGcFromServer(ushort const *)
0x18000e595  mov     r8, rax; struct IDirectorySearch *
0x18000e598  mov     [rsp+750h+var_6F0], rax
0x18000e59d  test    rax, rax
0x18000e5a0  jz      short loc_18000E5EA
0x18000e5a2  test    rdi, rdi
0x18000e5a5  jnz     short loc_18000E5B7
0x18000e5a7  lea     rdi, [rsp+750h+String2]
0x18000e5ac  cmp     [rbp+650h+var_6C0], 8
0x18000e5b1  cmovnb  rdi, [rsp+750h+String2]
0x18000e5b7  mov     rdx, rdi; unsigned __int16 *
0x18000e5ba  call    ?Add@CIDsCache@@QEAAJPEBGPEAUIDirectorySearch@@@Z; CIDsCache::Add(ushort const *,IDirectorySearch *)
0x18000e5bf  mov     r8, r13
0x18000e5c2  mov     rdx, [rsp+750h+var_6F0]
0x18000e5c7  lea     rcx, [rbp+650h+var_6B8]
0x18000e5cb  call    ?DoLdapQueryForSid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIDirectorySearch@@PEAX@Z; DoLdapQueryForSid(IDirectorySearch *,void *)
0x18000e5d0  mov     rdx, rax
0x18000e5d3  mov     rcx, rbx
0x18000e5d6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e5db  xor     r8d, r8d
0x18000e5de  mov     dl, 1
0x18000e5e0  lea     rcx, [rbp+650h+var_6B8]
0x18000e5e4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e5e9  nop
0x18000e5ea  mov     dl, 1
0x18000e5ec  xor     r8d, r8d
0x18000e5ef  lea     rcx, [rsp+750h+String2]
0x18000e5f4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e5f9  nop
0x18000e5fa  mov     rcx, [rsp+750h+hCursor]; hCursor
0x18000e5ff  call    cs:__imp_SetCursor
0x18000e605  cmp     qword ptr [rbx+18h], 8
0x18000e60a  jb      short loc_18000E611
0x18000e60c  mov     r8, [rbx]
0x18000e60f  jmp     short loc_18000E614
0x18000e611  mov     r8, rbx; unsigned __int16 *
0x18000e614  mov     rdx, r13; void *
0x18000e617  call    ?Add@CSidCache@@QEAAJPEAXPEBG@Z; CSidCache::Add(void *,ushort const *)
0x18000e61c  mov     rax, rbx
0x18000e61f  mov     rcx, [rbp+650h+var_50]
0x18000e626  xor     rcx, rsp; StackCookie
0x18000e629  call    __security_check_cookie
0x18000e62e  add     rsp, 718h
0x18000e635  pop     r15
0x18000e637  pop     r14
0x18000e639  pop     r13
0x18000e63b  pop     r12
0x18000e63d  pop     rdi
0x18000e63e  pop     rsi
0x18000e63f  pop     rbx
0x18000e640  pop     rbp
0x18000e641  retn
```

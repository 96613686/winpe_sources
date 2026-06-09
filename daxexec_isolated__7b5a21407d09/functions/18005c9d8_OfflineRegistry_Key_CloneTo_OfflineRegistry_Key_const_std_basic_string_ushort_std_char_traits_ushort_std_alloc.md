# OfflineRegistry::Key::CloneTo(OfflineRegistry::Key const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * const,bool)

- ea: `0x18005c9d8`
- end: `0x18005cf19`
- name: `?CloneTo@Key@OfflineRegistry@@QEBA?AV12@AEBV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX_N@Z`
- size: `1345`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005df70`

## callees

- `0x180004f70`
- `0x180005340`
- `0x1800059a8`
- `0x18000afe4`
- `0x1800125f4`
- `0x180014e74`
- `0x1800210fc`
- `0x180021118`
- `0x18002d4f0`
- `0x18005c9d8`
- `0x1800a1e98`
- `0x1800a28f0`
- `0x1800a3698`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cdc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cdc3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18005cd0d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18005cd0d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18005cce5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18005cce5`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18005cb93`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18005cb93`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005cdd9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005cdd9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005cc15`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005cc15`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ccb2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005ccb2`

## string_xrefs

- `0x18005ce28`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce40`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce5c`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce71`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce86`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce9b`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cead`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cec8`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cedd`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cef2`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cf07`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OfflineRegistry::Key::CloneTo(_QWORD *a1, __int64 a2, _QWORD *a3, __int64 *a4, __int64 a5, char a6)
{
  int v9; // r15d
  unsigned int v10; // eax
  void *v11; // rdi
  int v12; // eax
  unsigned __int64 v13; // rbx
  unsigned int v14; // eax
  void *v15; // rbx
  unsigned int v16; // esi
  unsigned int v17; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  const char *v19; // r9
  ULONG v20; // esi
  DWORD v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned __int64 v26; // rdx
  unsigned int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2a; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2b; // [rsp+20h] [rbp-E0h]
  unsigned __int8 DaclDefaulted[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 DaclPresent[4]; // [rsp+64h] [rbp-9Ch] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  void *v34; // [rsp+70h] [rbp-90h] BYREF
  PACL Dacl; // [rsp+78h] [rbp-88h] BYREF
  PACL NewAcl; // [rsp+80h] [rbp-80h] BYREF
  PSID pSid; // [rsp+88h] [rbp-78h] BYREF
  void *v38; // [rsp+90h] [rbp-70h]
  _QWORD *v39; // [rsp+98h] [rbp-68h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+D0h] [rbp-30h]
  int v42; // [rsp+D4h] [rbp-2Ch]
  int v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  _OWORD SecurityDescriptor[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v39 = a3;
  v50 = a2;
  v9 = 0;
  LODWORD(v34) = 1;
  Size = 0;
  v10 = ORQueryInfoKey(*a1, (unsigned int)DaclPresent, (unsigned int)&v34, 0, 0, 0, 0, 0, 0, (__int64)&Size, 0);
  if ( v10 && v10 != 234 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v10,
      nSubAuthority2);
  v11 = 0;
  v38 = 0;
  v12 = (int)v34;
  if ( (_DWORD)v34 )
  {
    LODWORD(v34) = (_DWORD)v34 + 1;
    v13 = saturated_mul((unsigned int)(v12 + 1), 2u);
    v11 = operator new[](v13);
    memset_0(v11, 0, v13);
    v9 = 2;
    HIDWORD(Size) = 2;
    v38 = v11;
    v14 = ORQueryInfoKey(*a1, (_DWORD)v11, (unsigned int)&v34, 0, 0, 0, 0, 0, 0, 0, 0);
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v14,
        nSubAuthority2);
  }
  v15 = 0;
  v34 = 0;
  Dacl = 0;
  if ( (_DWORD)Size )
  {
    v16 = Size;
    v15 = operator new[]((unsigned int)Size);
    memset_0(v15, 0, v16);
    v9 |= 4u;
    HIDWORD(Size) = v9;
    v34 = v15;
    v17 = ORGetKeySecurity(*a1, 0x10000, v15, &Size);
    if ( v17 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v17,
        nSubAuthority2);
    DaclPresent[0] = 0;
    DaclDefaulted[0] = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v15, DaclPresent, &Dacl, DaclDefaulted);
    if ( DaclSecurityDescriptor < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)(unsigned int)DaclSecurityDescriptor,
        nSubAuthority2);
    if ( !Dacl )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)0x8007054FLL,
        nSubAuthority2);
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  pSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      v19);
  v20 = 1;
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  if ( a6 )
  {
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)0x80070057LL,
        nSubAuthority2a);
    v20 = 2;
    v41 = 131078;
    v42 = 1;
    v43 = 2;
    v44 = 0;
    v45 = 0;
    v46 = 1;
    v47 = a5;
  }
  NewAcl = 0;
  v21 = SetEntriesInAclW(v20, &pListOfExplicitEntries, Dacl, &NewAcl);
  if ( v21 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v21,
      nSubAuthority2a);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v49 = 0;
  v22 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)(unsigned int)v22,
      nSubAuthority2a);
  v23 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, NewAcl, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)(unsigned int)v23,
      nSubAuthority2a);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = ORCloseKey;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 40) = 7;
  *(_WORD *)(a2 + 16) = 0;
  HIDWORD(Size) = v9 | 1;
  if ( *(_QWORD *)a2 )
    (*(void (**)(void))(a2 + 8))();
  *(_QWORD *)a2 = 0;
  if ( (unsigned __int64)a4[3] <= 7 )
    LODWORD(v24) = (_DWORD)a4;
  else
    v24 = *a4;
  v25 = ORCreateKey(*v39, v24, (int)v11, 0, SecurityDescriptor, a2, 0);
  if ( v25 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v25,
      nSubAuthority2b);
  std::wstring::operator=(a2 + 16, a4);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pSid )
    FreeSid(pSid);
  if ( v15 )
    operator delete(v15, v26);
  if ( v11 )
    operator delete(v11, v26);
  return a2;
}

```

## disassembly

```asm
0x18005c9d8  push    rbp
0x18005c9da  push    rbx
0x18005c9db  push    rsi
0x18005c9dc  push    rdi
0x18005c9dd  push    r12
0x18005c9df  push    r13
0x18005c9e1  push    r14
0x18005c9e3  push    r15
0x18005c9e5  lea     rbp, [rsp-48h]
0x18005c9ea  sub     rsp, 148h
0x18005c9f1  mov     rax, cs:__security_cookie
0x18005c9f8  xor     rax, rsp
0x18005c9fb  mov     [rbp+80h+var_48], rax
0x18005c9ff  mov     r12, r9
0x18005ca02  mov     [rbp+80h+var_E8], r8
0x18005ca06  mov     r14, rdx
0x18005ca09  mov     r13, rcx
0x18005ca0c  mov     [rbp+80h+var_58], rdx
0x18005ca10  xor     esi, esi
0x18005ca12  mov     r15d, esi
0x18005ca15  mov     dword ptr [rsp+180h+Size+4], esi
0x18005ca19  mov     dword ptr [rsp+180h+var_110], 1
0x18005ca21  mov     dword ptr [rsp+180h+Size], esi
0x18005ca25  mov     [rsp+180h+pSid], rsi
0x18005ca2a  lea     rax, [rsp+180h+Size]
0x18005ca2f  mov     qword ptr [rsp+180h+nSubAuthority7], rax
0x18005ca34  mov     qword ptr [rsp+180h+nSubAuthority6], rsi
0x18005ca39  mov     qword ptr [rsp+180h+nSubAuthority5], rsi
0x18005ca3e  mov     qword ptr [rsp+180h+nSubAuthority4], rsi
0x18005ca43  mov     qword ptr [rsp+180h+nSubAuthority3], rsi
0x18005ca48  mov     qword ptr [rsp+180h+nSubAuthority2], rsi; unsigned int
0x18005ca4d  xor     r9d, r9d
0x18005ca50  lea     r8, [rsp+180h+var_110]
0x18005ca55  lea     rdx, [rsp+180h+DaclPresent]
0x18005ca5a  mov     rcx, [rcx]
0x18005ca5d  call    ORQueryInfoKey
0x18005ca62  test    eax, eax
0x18005ca64  jz      short loc_18005CA71
0x18005ca66  cmp     eax, 0EAh
0x18005ca6b  jnz     loc_18005CE52
0x18005ca71  mov     rdi, rsi
0x18005ca74  mov     [rbp+80h+var_F0], rsi
0x18005ca78  mov     eax, dword ptr [rsp+180h+var_110]
0x18005ca7c  test    eax, eax
0x18005ca7e  jz      loc_18005CB0F
0x18005ca84  inc     eax
0x18005ca86  mov     dword ptr [rsp+180h+var_110], eax
0x18005ca8a  mov     ecx, eax
0x18005ca8c  mov     eax, 2
0x18005ca91  mul     rcx
0x18005ca94  mov     rbx, rax
0x18005ca97  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005ca9e  cmovb   rbx, rax
0x18005caa2  mov     rcx, rbx; unsigned __int64
0x18005caa5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005caaa  mov     rdi, rax
0x18005caad  mov     r8, rbx; Size
0x18005cab0  xor     edx, edx; Val
0x18005cab2  mov     rcx, rax; void *
0x18005cab5  call    memset_0
0x18005caba  mov     r15d, 2
0x18005cac0  mov     dword ptr [rsp+180h+Size+4], r15d
0x18005cac5  mov     [rbp+80h+var_F0], rdi
0x18005cac9  mov     [rsp+180h+pSid], rsi
0x18005cace  mov     qword ptr [rsp+180h+nSubAuthority7], rsi
0x18005cad3  mov     qword ptr [rsp+180h+nSubAuthority6], rsi
0x18005cad8  mov     qword ptr [rsp+180h+nSubAuthority5], rsi
0x18005cadd  mov     qword ptr [rsp+180h+nSubAuthority4], rsi
0x18005cae2  mov     qword ptr [rsp+180h+nSubAuthority3], rsi
0x18005cae7  mov     qword ptr [rsp+180h+nSubAuthority2], rsi; int
0x18005caec  xor     r9d, r9d
0x18005caef  lea     r8, [rsp+180h+var_110]
0x18005caf4  mov     rdx, rdi
0x18005caf7  mov     rcx, [r13+0]
0x18005cafb  call    ORQueryInfoKey
0x18005cb00  mov     rcx, [rbp+88h]; this
0x18005cb07  test    eax, eax
0x18005cb09  jnz     loc_18005CE6E
0x18005cb0f  mov     rbx, rsi
0x18005cb12  mov     [rsp+180h+var_110], rbx
0x18005cb17  mov     [rsp+180h+Dacl], rsi
0x18005cb1c  mov     eax, dword ptr [rsp+180h+Size]
0x18005cb20  test    eax, eax
0x18005cb22  jz      loc_18005CBC2
0x18005cb28  mov     esi, eax
0x18005cb2a  mov     ecx, eax; unsigned __int64
0x18005cb2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005cb31  mov     rbx, rax
0x18005cb34  mov     r8d, esi; Size
0x18005cb37  xor     edx, edx; Val
0x18005cb39  mov     rcx, rax; void *
0x18005cb3c  call    memset_0
0x18005cb41  or      r15d, 4
0x18005cb45  mov     dword ptr [rsp+180h+Size+4], r15d
0x18005cb4a  mov     [rsp+180h+var_110], rbx
0x18005cb4f  lea     r9, [rsp+180h+Size]
0x18005cb54  mov     r8, rbx
0x18005cb57  mov     edx, 10000h
0x18005cb5c  mov     rcx, [r13+0]
0x18005cb60  call    ORGetKeySecurity
0x18005cb65  mov     rcx, [rbp+88h]; this
0x18005cb6c  xor     r13d, r13d
0x18005cb6f  test    eax, eax
0x18005cb71  jnz     loc_18005CE83
0x18005cb77  mov     [rsp+180h+DaclPresent], r13b
0x18005cb7c  mov     [rsp+180h+DaclDefaulted], r13b
0x18005cb81  lea     r9, [rsp+180h+DaclDefaulted]; DaclDefaulted
0x18005cb86  lea     r8, [rsp+180h+Dacl]; Dacl
0x18005cb8b  lea     rdx, [rsp+180h+DaclPresent]; DaclPresent
0x18005cb90  mov     rcx, rbx; SecurityDescriptor
0x18005cb93  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18005cb9a  nop     dword ptr [rax+rax+00h]
0x18005cb9f  mov     rcx, [rbp+88h]; this
0x18005cba6  test    eax, eax
0x18005cba8  js      loc_18005CE98
0x18005cbae  mov     rcx, [rbp+88h]; this
0x18005cbb5  cmp     [rsp+180h+Dacl], r13
0x18005cbba  jz      loc_18005CE3A
0x18005cbc0  jmp     short loc_18005CBC5
0x18005cbc2  xor     r13d, r13d
0x18005cbc5  mov     dword ptr [rbp+80h+pIdentifierAuthority.Value], 0
0x18005cbcc  mov     word ptr [rbp+80h+pIdentifierAuthority.Value+4], 0F00h
0x18005cbd2  mov     [rbp+80h+var_F8], r13
0x18005cbd6  mov     rsi, [rbp+88h]
0x18005cbdd  lea     rax, [rbp+80h+var_F8]
0x18005cbe1  mov     [rsp+180h+pSid], rax; pSid
0x18005cbe6  mov     [rsp+180h+nSubAuthority7], r13d; nSubAuthority7
0x18005cbeb  mov     [rsp+180h+nSubAuthority6], r13d; nSubAuthority6
0x18005cbf0  mov     [rsp+180h+nSubAuthority5], r13d; nSubAuthority5
0x18005cbf5  mov     [rsp+180h+nSubAuthority4], r13d; nSubAuthority4
0x18005cbfa  mov     [rsp+180h+nSubAuthority3], r13d; nSubAuthority3
0x18005cbff  mov     [rsp+180h+nSubAuthority2], r13d; int
0x18005cc04  mov     r9d, 1; nSubAuthority1
0x18005cc0a  lea     r8d, [r9+1]; nSubAuthority0
0x18005cc0e  mov     dl, r8b; nSubAuthorityCount
0x18005cc11  lea     rcx, [rbp+80h+pIdentifierAuthority]; pIdentifierAuthority
0x18005cc15  call    cs:__imp_AllocateAndInitializeSid
0x18005cc1c  nop     dword ptr [rax+rax+00h]
0x18005cc21  test    eax, eax
0x18005cc23  jz      loc_18005CEAD
0x18005cc29  mov     esi, 1
0x18005cc2e  xor     edx, edx; Val
0x18005cc30  lea     r8d, [rsi+5Fh]; Size
0x18005cc34  lea     rcx, [rbp+80h+pListOfExplicitEntries]; void *
0x18005cc38  call    memset_0
0x18005cc3d  mov     [rbp+80h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x18005cc44  lea     edx, [rsi+1]
0x18005cc47  mov     qword ptr [rbp+80h+pListOfExplicitEntries.grfAccessMode], rdx
0x18005cc4b  mov     [rbp+80h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x18005cc4f  mov     [rbp+80h+pListOfExplicitEntries.Trustee.TrusteeType], edx
0x18005cc52  mov     rax, [rbp+80h+var_F8]
0x18005cc56  mov     [rbp+80h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18005cc5a  cmp     [rbp+80h+arg_28], r13b
0x18005cc61  jz      short loc_18005CC9F
0x18005cc63  mov     rcx, [rbp+88h]; this
0x18005cc6a  mov     rax, [rbp+80h+arg_20]
0x18005cc71  test    rax, rax
0x18005cc74  jz      loc_18005CEC2
0x18005cc7a  mov     esi, edx
0x18005cc7c  mov     [rbp+80h+var_B0], 20006h
0x18005cc83  lea     ecx, [rdx-1]
0x18005cc86  mov     [rbp+80h+var_AC], ecx
0x18005cc89  mov     [rbp+80h+var_A8], edx
0x18005cc8c  mov     [rbp+80h+var_A0], r13
0x18005cc90  mov     [rbp+80h+var_98], 0
0x18005cc98  mov     [rbp+80h+var_90], ecx
0x18005cc9b  mov     [rbp+80h+var_88], rax
0x18005cc9f  mov     [rbp+80h+NewAcl], r13
0x18005cca3  lea     r9, [rbp+80h+NewAcl]; NewAcl
0x18005cca7  mov     r8, [rsp+180h+Dacl]; OldAcl
0x18005ccac  lea     rdx, [rbp+80h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005ccb0  mov     ecx, esi; cCountOfExplicitEntries
0x18005ccb2  call    cs:__imp_SetEntriesInAclW
0x18005ccb9  nop     dword ptr [rax+rax+00h]
0x18005ccbe  mov     rcx, [rbp+88h]; this
0x18005ccc5  test    eax, eax
0x18005ccc7  jnz     loc_18005CEDA
0x18005cccd  xorps   xmm0, xmm0
0x18005ccd0  xor     eax, eax
0x18005ccd2  movups  [rbp+80h+SecurityDescriptor], xmm0
0x18005ccd6  movups  [rbp+80h+var_70], xmm0
0x18005ccda  mov     [rbp+80h+var_60], rax
0x18005ccde  lea     edx, [rax+1]; Revision
0x18005cce1  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x18005cce5  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005ccec  nop     dword ptr [rax+rax+00h]
0x18005ccf1  mov     rcx, [rbp+88h]; this
0x18005ccf8  test    eax, eax
0x18005ccfa  js      loc_18005CEEF
0x18005cd00  xor     r9d, r9d; DaclDefaulted
0x18005cd03  mov     r8, [rbp+80h+NewAcl]; Dacl
0x18005cd07  mov     dl, 1; DaclPresent
0x18005cd09  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x18005cd0d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18005cd14  nop     dword ptr [rax+rax+00h]
0x18005cd19  mov     rcx, [rbp+88h]; this
0x18005cd20  test    eax, eax
0x18005cd22  js      loc_18005CF04
0x18005cd28  mov     [r14], r13
0x18005cd2b  lea     rax, ORCloseKey
0x18005cd32  mov     [r14+8], rax
0x18005cd36  lea     rsi, [r14+10h]
0x18005cd3a  xorps   xmm0, xmm0
0x18005cd3d  movups  xmmword ptr [rsi], xmm0
0x18005cd40  mov     [rsi+10h], r13
0x18005cd44  mov     qword ptr [rsi+18h], 7
0x18005cd4c  mov     [rsi], r13w
0x18005cd50  or      r15d, 1
0x18005cd54  mov     dword ptr [rsp+180h+Size+4], r15d
0x18005cd59  mov     rcx, [r14]
0x18005cd5c  test    rcx, rcx
0x18005cd5f  jz      short loc_18005CD6A
0x18005cd61  mov     rax, [r14+8]
0x18005cd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd6a  mov     [r14], r13
0x18005cd6d  cmp     qword ptr [r12+18h], 7
0x18005cd73  jbe     short loc_18005CD7B
0x18005cd75  mov     rdx, [r12]
0x18005cd79  jmp     short loc_18005CD7E
0x18005cd7b  mov     rdx, r12; int
0x18005cd7e  mov     qword ptr [rsp+180h+nSubAuthority4], r13; __int64
0x18005cd83  mov     qword ptr [rsp+180h+nSubAuthority3], r14; __int64
0x18005cd88  lea     rax, [rbp+80h+SecurityDescriptor]
0x18005cd8c  mov     qword ptr [rsp+180h+nSubAuthority2], rax; unsigned int
0x18005cd91  xor     r9d, r9d; int
0x18005cd94  mov     r8, rdi; int
0x18005cd97  mov     rcx, [rbp+80h+var_E8]
0x18005cd9b  mov     rcx, [rcx]; int
0x18005cd9e  call    ORCreateKey
0x18005cda3  mov     rcx, [rbp+88h]; this
0x18005cdaa  test    eax, eax
0x18005cdac  jnz     short loc_18005CE25
0x18005cdae  mov     rdx, r12
0x18005cdb1  mov     rcx, rsi
0x18005cdb4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005cdb9  nop
0x18005cdba  mov     rcx, [rbp+80h+NewAcl]; hMem
0x18005cdbe  test    rcx, rcx
0x18005cdc1  jz      short loc_18005CDD0
0x18005cdc3  call    cs:__imp_LocalFree
0x18005cdca  nop     dword ptr [rax+rax+00h]
0x18005cdcf  nop
0x18005cdd0  mov     rcx, [rbp+80h+var_F8]; pSid
0x18005cdd4  test    rcx, rcx
0x18005cdd7  jz      short loc_18005CDE6
0x18005cdd9  call    cs:__imp_FreeSid
0x18005cde0  nop     dword ptr [rax+rax+00h]
0x18005cde5  nop
0x18005cde6  test    rbx, rbx
0x18005cde9  jz      short loc_18005CDF4
0x18005cdeb  mov     rcx, rbx; void *
0x18005cdee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cdf3  nop
0x18005cdf4  test    rdi, rdi
0x18005cdf7  jz      short loc_18005CE01
0x18005cdf9  mov     rcx, rdi; void *
0x18005cdfc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ce01  mov     rax, r14
0x18005ce04  mov     rcx, [rbp+80h+var_48]
0x18005ce08  xor     rcx, rsp; StackCookie
0x18005ce0b  call    __security_check_cookie
0x18005ce10  add     rsp, 148h
0x18005ce17  pop     r15
0x18005ce19  pop     r14
0x18005ce1b  pop     r13
0x18005ce1d  pop     r12
0x18005ce1f  pop     rdi
0x18005ce20  pop     rsi
0x18005ce21  pop     rbx
0x18005ce22  pop     rbp
0x18005ce23  retn
0x18005ce25  mov     r9d, eax; char *
0x18005ce28  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ce2f  mov     edx, 172h; void *
0x18005ce34  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005ce3a  mov     r9d, 8007054Fh; char *
0x18005ce40  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ce47  mov     edx, 145h; void *
0x18005ce4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ce52  mov     rcx, [rbp+88h]; this
0x18005ce59  mov     r9d, eax; char *
0x18005ce5c  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ce63  mov     edx, 130h; void *
0x18005ce68  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005ce6e  mov     r9d, eax; char *
0x18005ce71  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ce78  mov     edx, 138h; void *
0x18005ce7d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005ce83  mov     r9d, eax; char *
0x18005ce86  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ce8d  mov     edx, 140h; void *
0x18005ce92  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005ce98  mov     r9d, eax; char *
0x18005ce9b  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005cea2  mov     edx, 144h; void *
0x18005cea7  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18005cead  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005ceb4  mov     edx, 14Fh; void *
0x18005ceb9  mov     rcx, rsi; this
0x18005cebc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
  ... truncated ...
```

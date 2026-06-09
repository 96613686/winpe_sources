# OfflineRegistry::Key::CloneTo(OfflineRegistry::Key const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * const,bool)

- ea: `0x18005af8c`
- end: `0x18005b4c4`
- name: `?CloneTo@Key@OfflineRegistry@@QEBA?AV12@AEBV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX_N@Z`
- size: `1336`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005c6d4`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x180009484`
- `0x180010a84`
- `0x180013100`
- `0x18002031c`
- `0x180020338`
- `0x18002c9c8`
- `0x18005af8c`
- `0x1800a05f8`
- `0x1800a1084`
- `0x1800a1e5c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b36e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b36e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18005b2ba`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18005b2ba`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18005b292`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18005b292`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18005b150`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18005b150`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005b384`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005b384`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005b1c6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005b1c6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005b25f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005b25f`

## string_xrefs

- `0x18005b3d3`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b3ef`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b404`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b419`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b42e`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b446`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b458`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b473`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b488`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b49d`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005b4b2`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OfflineRegistry::Key::CloneTo(_QWORD *a1, __int64 a2, _QWORD *a3, __int64 *a4, __int64 a5, char a6)
{
  void *v9; // rbx
  int v10; // r15d
  unsigned int v11; // eax
  void *v12; // rdi
  int v13; // eax
  unsigned __int64 v14; // rbx
  unsigned int v15; // eax
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
  _QWORD *v40; // [rsp+A0h] [rbp-60h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp-50h] BYREF
  int v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E4h] [rbp-1Ch]
  int v44; // [rsp+E8h] [rbp-18h]
  __int64 v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  _OWORD SecurityDescriptor[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v40 = a3;
  v39 = a1;
  v51 = a2;
  v9 = 0;
  v10 = 0;
  LODWORD(v34) = 1;
  Size = 0;
  v11 = ORQueryInfoKey(*a1, (unsigned int)DaclPresent, (unsigned int)&v34, 0, 0, 0, 0, 0, 0, (__int64)&Size, 0);
  if ( v11 && v11 != 234 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v11,
      nSubAuthority2);
  v12 = 0;
  v38 = 0;
  v13 = (int)v34;
  if ( (_DWORD)v34 )
  {
    LODWORD(v34) = (_DWORD)v34 + 1;
    v14 = saturated_mul((unsigned int)(v13 + 1), 2u);
    v12 = operator new[](v14);
    memset_0(v12, 0, v14);
    v10 = 2;
    HIDWORD(Size) = 2;
    v38 = v12;
    v9 = 0;
    v15 = ORQueryInfoKey(*a1, (_DWORD)v12, (unsigned int)&v34, 0, 0, 0, 0, 0, 0, 0, 0);
    if ( v15 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v15,
        nSubAuthority2);
  }
  v34 = 0;
  Dacl = 0;
  if ( (_DWORD)Size )
  {
    v16 = Size;
    v9 = operator new[]((unsigned int)Size);
    memset_0(v9, 0, v16);
    v10 |= 4u;
    HIDWORD(Size) = v10;
    v34 = v9;
    v17 = ORGetKeySecurity(*v39, 0x10000, v9, &Size);
    if ( v17 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v17,
        nSubAuthority2);
    DaclPresent[0] = 0;
    DaclDefaulted[0] = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v9, DaclPresent, &Dacl, DaclDefaulted);
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
    v42 = 131078;
    v43 = 1;
    v44 = 2;
    v45 = 0;
    v46 = 0;
    v47 = 1;
    v48 = a5;
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
  v50 = 0;
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
  HIDWORD(Size) = v10 | 1;
  if ( *(_QWORD *)a2 )
    (*(void (**)(void))(a2 + 8))();
  *(_QWORD *)a2 = 0;
  LODWORD(v24) = (_DWORD)a4;
  if ( (unsigned __int64)a4[3] > 7 )
    v24 = *a4;
  v25 = ORCreateKey(*v40, v24, (int)v12, 0, SecurityDescriptor, a2, 0);
  if ( v25 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v25,
      nSubAuthority2b);
  std::wstring::operator=((void *)(a2 + 16));
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pSid )
    FreeSid(pSid);
  if ( v9 )
    operator delete(v9, v26);
  if ( v12 )
    operator delete(v12, v26);
  return a2;
}

```

## disassembly

```asm
0x18005af8c  push    rbp
0x18005af8e  push    rbx
0x18005af8f  push    rsi
0x18005af90  push    rdi
0x18005af91  push    r12
0x18005af93  push    r13
0x18005af95  push    r14
0x18005af97  push    r15
0x18005af99  lea     rbp, [rsp-58h]
0x18005af9e  sub     rsp, 158h
0x18005afa5  mov     rax, cs:__security_cookie
0x18005afac  xor     rax, rsp
0x18005afaf  mov     [rbp+90h+var_48], rax
0x18005afb3  mov     r12, r9
0x18005afb6  mov     [rbp+90h+var_F0], r8
0x18005afba  mov     r14, rdx
0x18005afbd  mov     rsi, rcx
0x18005afc0  mov     [rbp+90h+var_F8], rcx
0x18005afc4  mov     r13, [rbp+90h+arg_20]
0x18005afcb  mov     [rbp+90h+var_58], rdx
0x18005afcf  xor     ebx, ebx
0x18005afd1  mov     r15d, ebx
0x18005afd4  mov     dword ptr [rsp+190h+Size+4], ebx
0x18005afd8  mov     dword ptr [rsp+190h+var_120], 1
0x18005afe0  mov     dword ptr [rsp+190h+Size], ebx
0x18005afe4  mov     [rsp+190h+pSid], rbx
0x18005afe9  lea     rax, [rsp+190h+Size]
0x18005afee  mov     qword ptr [rsp+190h+nSubAuthority7], rax
0x18005aff3  mov     qword ptr [rsp+190h+nSubAuthority6], rbx
0x18005aff8  mov     qword ptr [rsp+190h+nSubAuthority5], rbx
0x18005affd  mov     qword ptr [rsp+190h+nSubAuthority4], rbx
0x18005b002  mov     qword ptr [rsp+190h+nSubAuthority3], rbx
0x18005b007  mov     qword ptr [rsp+190h+nSubAuthority2], rbx; unsigned int
0x18005b00c  xor     r9d, r9d
0x18005b00f  lea     r8, [rsp+190h+var_120]
0x18005b014  lea     rdx, [rsp+190h+DaclPresent]
0x18005b019  mov     rcx, [rcx]
0x18005b01c  call    ORQueryInfoKey
0x18005b021  test    eax, eax
0x18005b023  jz      short loc_18005B030
0x18005b025  cmp     eax, 0EAh
0x18005b02a  jnz     loc_18005B3E5
0x18005b030  mov     rdi, rbx
0x18005b033  mov     [rbp+90h+var_100], rbx
0x18005b037  mov     eax, dword ptr [rsp+190h+var_120]
0x18005b03b  test    eax, eax
0x18005b03d  jz      loc_18005B0CF
0x18005b043  inc     eax
0x18005b045  mov     dword ptr [rsp+190h+var_120], eax
0x18005b049  mov     ecx, eax
0x18005b04b  mov     eax, 2
0x18005b050  mul     rcx
0x18005b053  mov     rbx, rax
0x18005b056  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005b05d  cmovo   rbx, rax
0x18005b061  mov     rcx, rbx; unsigned __int64
0x18005b064  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005b069  mov     rdi, rax
0x18005b06c  mov     r8, rbx; Size
0x18005b06f  xor     edx, edx; Val
0x18005b071  mov     rcx, rax; void *
0x18005b074  call    memset_0
0x18005b079  mov     r15d, 2
0x18005b07f  mov     dword ptr [rsp+190h+Size+4], r15d
0x18005b084  mov     [rbp+90h+var_100], rdi
0x18005b088  xor     ebx, ebx
0x18005b08a  mov     [rsp+190h+pSid], rbx
0x18005b08f  mov     qword ptr [rsp+190h+nSubAuthority7], rbx
0x18005b094  mov     qword ptr [rsp+190h+nSubAuthority6], rbx
0x18005b099  mov     qword ptr [rsp+190h+nSubAuthority5], rbx
0x18005b09e  mov     qword ptr [rsp+190h+nSubAuthority4], rbx
0x18005b0a3  mov     qword ptr [rsp+190h+nSubAuthority3], rbx
0x18005b0a8  mov     qword ptr [rsp+190h+nSubAuthority2], rbx; int
0x18005b0ad  xor     r9d, r9d
0x18005b0b0  lea     r8, [rsp+190h+var_120]
0x18005b0b5  mov     rdx, rdi
0x18005b0b8  mov     rcx, [rsi]
0x18005b0bb  call    ORQueryInfoKey
0x18005b0c0  mov     rcx, [rbp+98h]; this
0x18005b0c7  test    eax, eax
0x18005b0c9  jnz     loc_18005B401
0x18005b0cf  mov     [rsp+190h+var_120], rbx
0x18005b0d4  xor     edx, edx
0x18005b0d6  mov     [rsp+190h+Dacl], rdx
0x18005b0db  mov     eax, dword ptr [rsp+190h+Size]
0x18005b0df  test    eax, eax
0x18005b0e1  jz      loc_18005B17F
0x18005b0e7  mov     esi, eax
0x18005b0e9  mov     ecx, eax; unsigned __int64
0x18005b0eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005b0f0  mov     rbx, rax
0x18005b0f3  mov     r8d, esi; Size
0x18005b0f6  xor     edx, edx; Val
0x18005b0f8  mov     rcx, rax; void *
0x18005b0fb  call    memset_0
0x18005b100  or      r15d, 4
0x18005b104  mov     dword ptr [rsp+190h+Size+4], r15d
0x18005b109  mov     [rsp+190h+var_120], rbx
0x18005b10e  lea     r9, [rsp+190h+Size]
0x18005b113  mov     r8, rbx
0x18005b116  mov     edx, 10000h
0x18005b11b  mov     rcx, [rbp+90h+var_F8]
0x18005b11f  mov     rcx, [rcx]
0x18005b122  call    ORGetKeySecurity
0x18005b127  mov     rcx, [rbp+98h]; this
0x18005b12e  test    eax, eax
0x18005b130  jnz     loc_18005B416
0x18005b136  mov     [rsp+190h+DaclPresent], al
0x18005b13a  mov     [rsp+190h+DaclDefaulted], al
0x18005b13e  lea     r9, [rsp+190h+DaclDefaulted]; DaclDefaulted
0x18005b143  lea     r8, [rsp+190h+Dacl]; Dacl
0x18005b148  lea     rdx, [rsp+190h+DaclPresent]; DaclPresent
0x18005b14d  mov     rcx, rbx; SecurityDescriptor
0x18005b150  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18005b157  nop     dword ptr [rax+rax+00h]
0x18005b15c  mov     rcx, [rbp+98h]; this
0x18005b163  xor     edx, edx
0x18005b165  test    eax, eax
0x18005b167  js      loc_18005B42B
0x18005b16d  mov     rcx, [rbp+98h]; this
0x18005b174  cmp     [rsp+190h+Dacl], rdx
0x18005b179  jz      loc_18005B440
0x18005b17f  and     dword ptr [rbp+90h+pIdentifierAuthority.Value], 0
0x18005b183  mov     word ptr [rbp+90h+pIdentifierAuthority.Value+4], 0F00h
0x18005b189  mov     [rbp+90h+var_108], rdx
0x18005b18d  mov     rsi, [rbp+98h]
0x18005b194  lea     rax, [rbp+90h+var_108]
0x18005b198  mov     [rsp+190h+pSid], rax; pSid
0x18005b19d  mov     [rsp+190h+nSubAuthority7], edx; nSubAuthority7
0x18005b1a1  mov     [rsp+190h+nSubAuthority6], edx; nSubAuthority6
0x18005b1a5  mov     [rsp+190h+nSubAuthority5], edx; nSubAuthority5
0x18005b1a9  mov     [rsp+190h+nSubAuthority4], edx; nSubAuthority4
0x18005b1ad  mov     [rsp+190h+nSubAuthority3], edx; nSubAuthority3
0x18005b1b1  mov     [rsp+190h+nSubAuthority2], edx; int
0x18005b1b5  mov     r9d, 1; nSubAuthority1
0x18005b1bb  lea     r8d, [r9+1]; nSubAuthority0
0x18005b1bf  mov     dl, r8b; nSubAuthorityCount
0x18005b1c2  lea     rcx, [rbp+90h+pIdentifierAuthority]; pIdentifierAuthority
0x18005b1c6  call    cs:__imp_AllocateAndInitializeSid
0x18005b1cd  nop     dword ptr [rax+rax+00h]
0x18005b1d2  test    eax, eax
0x18005b1d4  jz      loc_18005B458
0x18005b1da  mov     esi, 1
0x18005b1df  xor     edx, edx; Val
0x18005b1e1  lea     r8d, [rsi+5Fh]; Size
0x18005b1e5  lea     rcx, [rbp+90h+pListOfExplicitEntries]; void *
0x18005b1e9  call    memset_0
0x18005b1ee  mov     [rbp+90h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x18005b1f5  lea     r8d, [rsi+1]
0x18005b1f9  mov     qword ptr [rbp+90h+pListOfExplicitEntries.grfAccessMode], r8
0x18005b1fd  xor     edx, edx
0x18005b1ff  mov     [rbp+90h+pListOfExplicitEntries.Trustee.TrusteeForm], edx
0x18005b202  mov     [rbp+90h+pListOfExplicitEntries.Trustee.TrusteeType], r8d
0x18005b206  mov     rax, [rbp+90h+var_108]
0x18005b20a  mov     [rbp+90h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18005b20e  cmp     [rbp+90h+arg_28], dl
0x18005b214  jz      short loc_18005B249
0x18005b216  mov     rcx, [rbp+98h]; this
0x18005b21d  test    r13, r13
0x18005b220  jz      loc_18005B46D
0x18005b226  mov     esi, r8d
0x18005b229  mov     [rbp+90h+var_B0], 20006h
0x18005b230  lea     eax, [rdx+1]
0x18005b233  mov     [rbp+90h+var_AC], eax
0x18005b236  mov     [rbp+90h+var_A8], r8d
0x18005b23a  mov     [rbp+90h+var_A0], rdx
0x18005b23e  mov     [rbp+90h+var_98], rdx
0x18005b242  mov     [rbp+90h+var_90], eax
0x18005b245  mov     [rbp+90h+var_88], r13
0x18005b249  xor     r13d, r13d
0x18005b24c  mov     [rbp+90h+NewAcl], r13
0x18005b250  lea     r9, [rbp+90h+NewAcl]; NewAcl
0x18005b254  mov     r8, [rsp+190h+Dacl]; OldAcl
0x18005b259  lea     rdx, [rbp+90h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005b25d  mov     ecx, esi; cCountOfExplicitEntries
0x18005b25f  call    cs:__imp_SetEntriesInAclW
0x18005b266  nop     dword ptr [rax+rax+00h]
0x18005b26b  mov     rcx, [rbp+98h]; this
0x18005b272  test    eax, eax
0x18005b274  jnz     loc_18005B485
0x18005b27a  xorps   xmm0, xmm0
0x18005b27d  xor     eax, eax
0x18005b27f  movups  [rbp+90h+SecurityDescriptor], xmm0
0x18005b283  movups  [rbp+90h+var_70], xmm0
0x18005b287  mov     [rbp+90h+var_60], rax
0x18005b28b  lea     edx, [rax+1]; Revision
0x18005b28e  lea     rcx, [rbp+90h+SecurityDescriptor]; SecurityDescriptor
0x18005b292  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005b299  nop     dword ptr [rax+rax+00h]
0x18005b29e  mov     rcx, [rbp+98h]; this
0x18005b2a5  test    eax, eax
0x18005b2a7  js      loc_18005B49A
0x18005b2ad  xor     r9d, r9d; DaclDefaulted
0x18005b2b0  mov     r8, [rbp+90h+NewAcl]; Dacl
0x18005b2b4  mov     dl, 1; DaclPresent
0x18005b2b6  lea     rcx, [rbp+90h+SecurityDescriptor]; SecurityDescriptor
0x18005b2ba  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18005b2c1  nop     dword ptr [rax+rax+00h]
0x18005b2c6  mov     rcx, [rbp+98h]; this
0x18005b2cd  test    eax, eax
0x18005b2cf  js      loc_18005B4AF
0x18005b2d5  mov     [r14], r13
0x18005b2d8  lea     rax, ORCloseKey
0x18005b2df  mov     [r14+8], rax
0x18005b2e3  lea     rsi, [r14+10h]
0x18005b2e7  xorps   xmm0, xmm0
0x18005b2ea  movups  xmmword ptr [rsi], xmm0
0x18005b2ed  mov     [rsi+10h], r13
0x18005b2f1  mov     qword ptr [rsi+18h], 7
0x18005b2f9  mov     [rsi], r13w
0x18005b2fd  or      r15d, 1
0x18005b301  mov     dword ptr [rsp+190h+Size+4], r15d
0x18005b306  mov     rcx, [r14]
0x18005b309  test    rcx, rcx
0x18005b30c  jz      short loc_18005B317
0x18005b30e  mov     rax, [r14+8]
0x18005b312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b317  mov     [r14], r13
0x18005b31a  mov     rdx, r12
0x18005b31d  cmp     qword ptr [r12+18h], 7
0x18005b323  jbe     short loc_18005B329
0x18005b325  mov     rdx, [r12]; int
0x18005b329  mov     qword ptr [rsp+190h+nSubAuthority4], r13; __int64
0x18005b32e  mov     qword ptr [rsp+190h+nSubAuthority3], r14; __int64
0x18005b333  lea     rax, [rbp+90h+SecurityDescriptor]
0x18005b337  mov     qword ptr [rsp+190h+nSubAuthority2], rax; unsigned int
0x18005b33c  xor     r9d, r9d; int
0x18005b33f  mov     r8, rdi; int
0x18005b342  mov     rcx, [rbp+90h+var_F0]
0x18005b346  mov     rcx, [rcx]; int
0x18005b349  call    ORCreateKey
0x18005b34e  mov     rcx, [rbp+98h]; this
0x18005b355  test    eax, eax
0x18005b357  jnz     short loc_18005B3D0
0x18005b359  mov     rdx, r12
0x18005b35c  mov     rcx, rsi; void *
0x18005b35f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005b364  nop
0x18005b365  mov     rcx, [rbp+90h+NewAcl]; hMem
0x18005b369  test    rcx, rcx
0x18005b36c  jz      short loc_18005B37B
0x18005b36e  call    cs:__imp_LocalFree
0x18005b375  nop     dword ptr [rax+rax+00h]
0x18005b37a  nop
0x18005b37b  mov     rcx, [rbp+90h+var_108]; pSid
0x18005b37f  test    rcx, rcx
0x18005b382  jz      short loc_18005B391
0x18005b384  call    cs:__imp_FreeSid
0x18005b38b  nop     dword ptr [rax+rax+00h]
0x18005b390  nop
0x18005b391  test    rbx, rbx
0x18005b394  jz      short loc_18005B39F
0x18005b396  mov     rcx, rbx; void *
0x18005b399  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b39e  nop
0x18005b39f  test    rdi, rdi
0x18005b3a2  jz      short loc_18005B3AC
0x18005b3a4  mov     rcx, rdi; void *
0x18005b3a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b3ac  mov     rax, r14
0x18005b3af  mov     rcx, [rbp+90h+var_48]
0x18005b3b3  xor     rcx, rsp; StackCookie
0x18005b3b6  call    __security_check_cookie
0x18005b3bb  add     rsp, 158h
0x18005b3c2  pop     r15
0x18005b3c4  pop     r14
0x18005b3c6  pop     r13
0x18005b3c8  pop     r12
0x18005b3ca  pop     rdi
0x18005b3cb  pop     rsi
0x18005b3cc  pop     rbx
0x18005b3cd  pop     rbp
0x18005b3ce  retn
0x18005b3d0  mov     r9d, eax; char *
0x18005b3d3  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b3da  mov     edx, 172h; void *
0x18005b3df  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005b3e5  mov     rcx, [rbp+98h]; this
0x18005b3ec  mov     r9d, eax; char *
0x18005b3ef  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b3f6  mov     edx, 130h; void *
0x18005b3fb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005b401  mov     r9d, eax; char *
0x18005b404  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b40b  mov     edx, 138h; void *
0x18005b410  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005b416  mov     r9d, eax; char *
0x18005b419  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b420  mov     edx, 140h; void *
0x18005b425  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005b42b  mov     r9d, eax; char *
0x18005b42e  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b435  mov     edx, 144h; void *
0x18005b43a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18005b440  mov     r9d, 8007054Fh; char *
0x18005b446  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b44d  mov     edx, 145h; void *
0x18005b452  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b458  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005b45f  mov     edx, 14Fh; void *
  ... truncated ...
```

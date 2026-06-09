# SidToAccountName

- ea: `0x18012beec`
- end: `0x18012c106`
- name: `SidToAccountName`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012b74c`

## callees

- `0x180019588`
- `0x180019594`
- `0x1800ed44c`
- `0x1800edc3c`
- `0x1800edd28`
- `0x1800fa538`
- `0x18012beec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf7e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012bf6a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012c012`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012bf6a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012c012`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18012bf11`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18012bf11`

## string_xrefs

- `0x18012bf25`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SidToAccountName(const WCHAR *a1, unsigned __int16 **a2)
{
  unsigned int LastError; // ebx
  const char *v4; // r9
  void *ReferencedDomainName; // rax
  LPWSTR v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-38h] BYREF
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  PSID Sid[3]; // [rsp+58h] [rbp-28h] BYREF
  char v16; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+38h] BYREF

  LastError = 0;
  Sid[0] = 0;
  if ( !ConvertStringSidToSidW(a1, Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3B8,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                  v4);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
    return LastError;
  }
  peUse = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  if ( LookupAccountSidW(0, Sid[0], 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
    return 0;
  }
  Name = (LPWSTR)operator new[](saturated_mul(cchName, 2u));
  ReferencedDomainName = operator new[](saturated_mul(cchReferencedDomainName, 2u));
  Block = ReferencedDomainName;
  Sid[1] = &Name;
  Sid[2] = &Block;
  v16 = 1;
  v6 = Name;
  if ( !Name )
  {
LABEL_14:
    operator delete(v6);
    operator delete(Block);
    goto LABEL_15;
  }
  if ( !LookupAccountSidW(0, Sid[0], Name, &cchName, (LPWSTR)ReferencedDomainName, &cchReferencedDomainName, &peUse)
    || (unsigned int)(peUse - 1) > 1 )
  {
    v6 = Name;
    goto LABEL_14;
  }
  v7 = -1;
  do
    ++v7;
  while ( Name[v7] );
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)Block + v8) );
  v9 = v8 + v7 + 2;
  v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
  *a2 = v10;
  StringCchCopyW(v10, v9, (const unsigned __int16 *)Block);
  StringCchCatW(*a2, v9, L"\\");
  StringCchCatW(*a2, v9, Name);
  operator delete(Name);
  operator delete(Block);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
  return 1;
}

```

## disassembly

```asm
0x18012beec  mov     [rsp-18h+arg_0], rbx
0x18012bef1  mov     [rsp-18h+arg_8], rsi
0x18012bef6  push    rbp
0x18012bef7  push    rdi
0x18012bef8  push    r14
0x18012befa  mov     rbp, rsp
0x18012befd  sub     rsp, 80h
0x18012bf04  mov     rdi, rdx
0x18012bf07  xor     ebx, ebx
0x18012bf09  mov     [rbp+Sid], rbx
0x18012bf0d  lea     rdx, [rbp+Sid]; Sid
0x18012bf11  call    cs:__imp_ConvertStringSidToSidW
0x18012bf18  nop     dword ptr [rax+rax+00h]
0x18012bf1d  test    eax, eax
0x18012bf1f  jnz     short loc_18012BF3D
0x18012bf21  mov     rcx, [rbp+18h]; this
0x18012bf25  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012bf2c  mov     edx, 3B8h; void *
0x18012bf31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012bf36  mov     ebx, eax
0x18012bf38  jmp     loc_18012C0D5
0x18012bf3d  mov     [rbp+var_40], ebx
0x18012bf40  mov     [rbp+cchName], ebx
0x18012bf43  mov     [rbp+arg_10], ebx
0x18012bf46  lea     rax, [rbp+var_40]
0x18012bf4a  mov     [rsp+80h+peUse], rax; peUse
0x18012bf4f  lea     rax, [rbp+arg_10]
0x18012bf53  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18012bf58  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x18012bf5d  lea     r9, [rbp+cchName]; cchName
0x18012bf61  xor     r8d, r8d; Name
0x18012bf64  mov     rdx, [rbp+Sid]; Sid
0x18012bf68  xor     ecx, ecx; lpSystemName
0x18012bf6a  call    cs:__imp_LookupAccountSidW
0x18012bf71  nop     dword ptr [rax+rax+00h]
0x18012bf76  test    eax, eax
0x18012bf78  jnz     loc_18012C0E2
0x18012bf7e  call    cs:__imp_GetLastError
0x18012bf85  nop     dword ptr [rax+rax+00h]
0x18012bf8a  cmp     eax, 7Ah ; 'z'
0x18012bf8d  jnz     loc_18012C0E2
0x18012bf93  mov     ecx, [rbp+cchName]
0x18012bf96  lea     r14d, [rax-78h]
0x18012bf9a  mov     eax, r14d
0x18012bf9d  mul     rcx
0x18012bfa0  lea     rsi, [r14-3]
0x18012bfa4  cmovb   rax, rsi
0x18012bfa8  mov     rcx, rax; unsigned __int64
0x18012bfab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012bfb0  mov     [rbp+Name], rax
0x18012bfb4  mov     ecx, [rbp+arg_10]
0x18012bfb7  mov     eax, r14d
0x18012bfba  mul     rcx
0x18012bfbd  cmovb   rax, rsi
0x18012bfc1  mov     rcx, rax; unsigned __int64
0x18012bfc4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012bfc9  mov     [rbp+Block], rax
0x18012bfcd  lea     rcx, [rbp+Name]
0x18012bfd1  mov     [rbp+var_20], rcx
0x18012bfd5  lea     rcx, [rbp+Block]
0x18012bfd9  mov     [rbp+var_18], rcx
0x18012bfdd  mov     [rbp+var_10], 1
0x18012bfe1  mov     rcx, [rbp+Name]; Block
0x18012bfe5  test    rcx, rcx
0x18012bfe8  jz      loc_18012C0C6
0x18012bfee  lea     rdx, [rbp+var_40]
0x18012bff2  mov     [rsp+80h+peUse], rdx; peUse
0x18012bff7  lea     rdx, [rbp+arg_10]
0x18012bffb  mov     [rsp+80h+cchReferencedDomainName], rdx; cchReferencedDomainName
0x18012c000  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x18012c005  lea     r9, [rbp+cchName]; cchName
0x18012c009  mov     r8, rcx; Name
0x18012c00c  mov     rdx, [rbp+Sid]; Sid
0x18012c010  xor     ecx, ecx; lpSystemName
0x18012c012  call    cs:__imp_LookupAccountSidW
0x18012c019  nop     dword ptr [rax+rax+00h]
0x18012c01e  test    eax, eax
0x18012c020  jnz     short loc_18012C02B
0x18012c022  mov     rcx, [rbp+Name]
0x18012c026  jmp     loc_18012C0C6
0x18012c02b  mov     eax, [rbp+var_40]
0x18012c02e  dec     eax
0x18012c030  cmp     eax, 1
0x18012c033  ja      short loc_18012C022
0x18012c035  mov     rax, [rbp+Name]
0x18012c039  mov     rcx, rsi
0x18012c03c  inc     rcx
0x18012c03f  cmp     [rax+rcx*2], bx
0x18012c043  jnz     short loc_18012C03C
0x18012c045  mov     r8, [rbp+Block]
0x18012c049  mov     rdx, rsi
0x18012c04c  inc     rdx
0x18012c04f  cmp     [r8+rdx*2], bx
0x18012c054  jnz     short loc_18012C04C
0x18012c056  lea     rbx, [rcx+2]
0x18012c05a  add     rbx, rdx
0x18012c05d  mov     rax, r14
0x18012c060  mul     rbx
0x18012c063  cmovb   rax, rsi
0x18012c067  mov     rcx, rax; unsigned __int64
0x18012c06a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012c06f  mov     [rdi], rax
0x18012c072  mov     r8, [rbp+Block]; unsigned __int16 *
0x18012c076  mov     rdx, rbx; unsigned __int64
0x18012c079  mov     rcx, rax; unsigned __int16 *
0x18012c07c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012c081  lea     r8, psz; "\\"
0x18012c088  mov     rdx, rbx; unsigned __int64
0x18012c08b  mov     rcx, [rdi]; unsigned __int16 *
0x18012c08e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012c093  mov     r8, [rbp+Name]; unsigned __int16 *
0x18012c097  mov     rdx, rbx; unsigned __int64
0x18012c09a  mov     rcx, [rdi]; unsigned __int16 *
0x18012c09d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012c0a2  nop
0x18012c0a3  mov     rcx, [rbp+Name]; Block
0x18012c0a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012c0ac  mov     rcx, [rbp+Block]; Block
0x18012c0b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012c0b5  nop
0x18012c0b6  lea     rcx, [rbp+Sid]
0x18012c0ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012c0bf  mov     eax, 1
0x18012c0c4  jmp     short loc_18012C0ED
0x18012c0c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012c0cb  mov     rcx, [rbp+Block]; Block
0x18012c0cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012c0d4  nop
0x18012c0d5  lea     rcx, [rbp+Sid]
0x18012c0d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012c0de  mov     eax, ebx
0x18012c0e0  jmp     short loc_18012C0ED
0x18012c0e2  lea     rcx, [rbp+Sid]
0x18012c0e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012c0eb  xor     eax, eax
0x18012c0ed  lea     r11, [rsp+80h+var_s0]
0x18012c0f5  mov     rbx, [r11+20h]
0x18012c0f9  mov     rsi, [r11+28h]
0x18012c0fd  mov     rsp, r11
0x18012c100  pop     r14
0x18012c102  pop     rdi
0x18012c103  pop     rbp
0x18012c104  retn
```

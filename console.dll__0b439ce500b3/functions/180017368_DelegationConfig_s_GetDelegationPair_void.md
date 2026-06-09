# DelegationConfig::s_GetDelegationPair(void)

- ea: `0x180017368`
- end: `0x1800175de`
- name: `?s_GetDelegationPair@DelegationConfig@@SA?AUDelegationPair@1@XZ`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016c14`

## callees

- `0x1800015b0`
- `0x180003ad8`
- `0x180003ccc`
- `0x1800070a4`
- `0x180008714`
- `0x1800150f0`
- `0x18001548c`
- `0x180017368`
- `0x180018580`
- `0x1800186bc`
- `0x1800186e4`
- `0x180018d00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180017507`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180017507`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800173cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800173cf`

## string_xrefs

- `0x18001740d`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`
- `0x180017482`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_GetDelegationPair(__int64 a1)
{
  LSTATUS v2; // eax
  __int64 v3; // rdx
  __int128 v4; // xmm0
  int v5; // eax
  __int128 v6; // xmm1
  unsigned __int64 v8; // rsi
  const wchar_t *v9; // rdx
  unsigned int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  HRESULT v13; // eax
  GUID v14; // xmm0
  int v15; // [rsp+20h] [rbp-79h]
  int v16; // [rsp+20h] [rbp-79h]
  HKEY hKey; // [rsp+30h] [rbp-69h] BYREF
  HKEY v18; // [rsp+38h] [rbp-61h] BYREF
  HKEY v19; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-51h] BYREF
  GUID Buf1; // [rsp+50h] [rbp-49h] BYREF
  GUID v22; // [rsp+60h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  hKey = 0;
  v18 = 0;
  v19 = 0;
  v2 = RegistrySerialization::s_OpenConsoleKey(&v19, &v18);
  if ( v2 < 0 )
  {
    v3 = 238;
LABEL_5:
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      (const char *)(unsigned int)v2,
      v15);
LABEL_6:
    v4 = DelegationConfig::DefaultDelegationPair;
    v5 = 0;
    v6 = xmmword_18001D4A8;
    goto LABEL_7;
  }
  hKey = 0;
  v2 = RegistrySerialization::s_OpenKey(v18, L"%%Startup", &hKey);
  if ( v2 < 0 )
  {
    v3 = 239;
    goto LABEL_5;
  }
  v8 = 0;
  Buf1 = DelegationConfig::CLSID_Default;
  v22 = DelegationConfig::CLSID_Default;
  do
  {
    v9 = off_18001B4A0[v8];
    v20 = 0;
    v10 = RegistrySerialization::s_QueryValue(hKey, v9, 0x4Eu, 1u, (unsigned __int8 *const)sz, &v20);
    if ( v10 )
    {
      if ( v10 != -1073283070 )
        wil::details::in1diag3::Log_NtStatus(retaddr, v11, v12, (const char *)v10, v16);
    }
    else if ( v20 == 78 )
    {
      sz[38] = 0;
      v13 = IIDFromString(sz, &Buf1 + v8);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
          (const char *)(unsigned int)v13,
          v16);
    }
    ++v8;
  }
  while ( v8 < 2 );
  if ( !memcmp_0(&Buf1, &DelegationConfig::CLSID_Default, 0x10u)
    || !memcmp_0(&v22, &DelegationConfig::CLSID_Default, 0x10u) )
  {
    goto LABEL_6;
  }
  if ( memcmp_0(&Buf1, &DelegationConfig::CLSID_Conhost, 0x10u)
    && memcmp_0(&v22, &DelegationConfig::CLSID_Conhost, 0x10u) )
  {
    v14 = Buf1;
    *(GUID *)(a1 + 20) = v22;
    *(_DWORD *)a1 = 3;
    *(GUID *)(a1 + 4) = v14;
    goto LABEL_8;
  }
  v4 = DelegationConfig::ConhostDelegationPair;
  v5 = 2107404511;
  v6 = xmmword_18001D480;
LABEL_7:
  *(_OWORD *)a1 = v4;
  *(_OWORD *)(a1 + 16) = v6;
  *(_DWORD *)(a1 + 32) = v5;
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  return a1;
}

```

## disassembly

```asm
0x180017368  push    rbp
0x18001736a  push    rbx
0x18001736b  push    rsi
0x18001736c  push    rdi
0x18001736d  lea     rbp, [rsp-3Fh]
0x180017372  sub     rsp, 0D8h
0x180017379  mov     rax, cs:__security_cookie
0x180017380  xor     rax, rsp
0x180017383  mov     [rbp+57h+var_30], rax
0x180017387  mov     rbx, rcx
0x18001738a  mov     [rbp+57h+hKey], 0
0x180017392  lea     rcx, [rbp+57h+var_B0]; HKEY *
0x180017396  mov     [rbp+57h+var_B8], 0
0x18001739e  lea     rdx, [rbp+57h+var_B8]; HKEY *
0x1800173a2  mov     [rbp+57h+var_B0], 0
0x1800173aa  call    ?s_OpenConsoleKey@RegistrySerialization@@SAJPEAPEAUHKEY__@@0@Z; RegistrySerialization::s_OpenConsoleKey(HKEY__ * *,HKEY__ * *)
0x1800173af  test    eax, eax
0x1800173b1  jns     short loc_1800173BA
0x1800173b3  mov     edx, 0EEh
0x1800173b8  jmp     short loc_180017409
0x1800173ba  mov     rdi, [rbp+57h+hKey]
0x1800173be  test    rdi, rdi
0x1800173c1  jz      short loc_1800173E4
0x1800173c3  lea     rcx, [rbp+57h+var_A8]; this
0x1800173c7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800173cc  mov     rcx, rdi; hKey
0x1800173cf  call    cs:__imp_RegCloseKey
0x1800173d6  nop     dword ptr [rax+rax+00h]
0x1800173db  lea     rcx, [rbp+57h+var_A8]; this
0x1800173df  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800173e4  mov     rcx, [rbp+57h+var_B8]; HKEY
0x1800173e8  lea     r8, [rbp+57h+hKey]; HKEY *
0x1800173ec  lea     rdx, aStartup; "%%Startup"
0x1800173f3  mov     [rbp+57h+hKey], 0
0x1800173fb  call    ?s_OpenKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_OpenKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x180017400  test    eax, eax
0x180017402  jns     short loc_180017474
0x180017404  mov     edx, 0EFh; void *
0x180017409  mov     rcx, [rbp+5Fh]; this
0x18001740d  lea     rdi, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180017414  mov     r8, rdi; unsigned int
0x180017417  mov     r9d, eax; char *
0x18001741a  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001741f  movups  xmm0, cs:?DefaultDelegationPair@DelegationConfig@@2UDelegationPair@1@B; DelegationConfig::DelegationPair const DelegationConfig::DefaultDelegationPair
0x180017426  mov     eax, cs:dword_18001D4B8
0x18001742c  movups  xmm1, cs:xmmword_18001D4A8
0x180017433  movups  xmmword ptr [rbx], xmm0
0x180017436  movups  xmmword ptr [rbx+10h], xmm1
0x18001743a  mov     [rbx+20h], eax
0x18001743d  lea     rcx, [rbp+57h+hKey]
0x180017441  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017446  lea     rcx, [rbp+57h+var_B8]
0x18001744a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001744f  lea     rcx, [rbp+57h+var_B0]
0x180017453  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017458  mov     rax, rbx
0x18001745b  mov     rcx, [rbp+57h+var_30]
0x18001745f  xor     rcx, rsp; StackCookie
0x180017462  call    __security_check_cookie
0x180017467  add     rsp, 0D8h
0x18001746e  pop     rdi
0x18001746f  pop     rsi
0x180017470  pop     rbx
0x180017471  pop     rbp
0x180017472  retn
0x180017474  movups  xmm0, xmmword ptr cs:?CLSID_Default@DelegationConfig@@2U_GUID@@B.Data1; _GUID const DelegationConfig::CLSID_Default ...
0x18001747b  mov     rax, qword ptr cs:?CLSID_Default@DelegationConfig@@2U_GUID@@B.Data4; _GUID const DelegationConfig::CLSID_Default ...
0x180017482  lea     rdi, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180017489  mov     qword ptr [rbp+57h+var_90+8], rax
0x18001748d  xor     esi, esi
0x18001748f  movdqu  [rbp+57h+Buf1], xmm0
0x180017494  movsd   qword ptr [rbp+57h+var_90], xmm0
0x180017499  mov     rcx, [rbp+57h+hKey]; HKEY
0x18001749d  lea     rax, [rbp+57h+var_A8]
0x1800174a1  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x1800174a6  lea     rdx, off_18001B4A0; "DelegationConsole"
0x1800174ad  mov     rdx, [rdx+rsi*8]; wchar_t *
0x1800174b1  lea     rax, [rbp+57h+sz]
0x1800174b5  mov     r9d, 1; unsigned int
0x1800174bb  mov     [rbp+57h+var_A8], 0
0x1800174c2  mov     [rsp+0F0h+var_D0], rax; int
0x1800174c7  lea     r8d, [r9+4Dh]; unsigned int
0x1800174cb  call    ?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z; RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)
0x1800174d0  test    eax, eax
0x1800174d2  jz      short loc_1800174E9
0x1800174d4  cmp     eax, 0C0070002h
0x1800174d9  jz      short loc_18001752B
0x1800174db  mov     rcx, [rbp+5Fh]; this
0x1800174df  mov     r9d, eax; char *
0x1800174e2  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x1800174e7  jmp     short loc_18001752B
0x1800174e9  cmp     [rbp+57h+var_A8], 4Eh ; 'N'
0x1800174ed  jnz     short loc_18001752B
0x1800174ef  xor     eax, eax
0x1800174f1  lea     rdx, [rbp+57h+Buf1]
0x1800174f5  mov     [rbp+57h+var_34], ax
0x1800174f9  lea     rcx, [rbp+57h+sz]; lpsz
0x1800174fd  mov     rax, rsi
0x180017500  shl     rax, 4
0x180017504  add     rdx, rax; lpiid
0x180017507  call    cs:__imp_IIDFromString
0x18001750e  nop     dword ptr [rax+rax+00h]
0x180017513  test    eax, eax
0x180017515  jns     short loc_18001752B
0x180017517  mov     rcx, [rbp+5Fh]; this
0x18001751b  mov     r9d, eax; char *
0x18001751e  mov     r8, rdi; unsigned int
0x180017521  mov     edx, 111h; void *
0x180017526  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001752b  inc     rsi
0x18001752e  cmp     rsi, 2
0x180017532  jb      loc_180017499
0x180017538  mov     edi, 10h
0x18001753d  lea     rdx, ?CLSID_Default@DelegationConfig@@2U_GUID@@B; Buf2
0x180017544  mov     r8d, edi; Size
0x180017547  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18001754b  call    memcmp_0
0x180017550  test    eax, eax
0x180017552  jz      loc_18001741F
0x180017558  mov     r8d, edi; Size
0x18001755b  lea     rdx, ?CLSID_Default@DelegationConfig@@2U_GUID@@B; Buf2
0x180017562  lea     rcx, [rbp+57h+var_90]; Buf1
0x180017566  call    memcmp_0
0x18001756b  test    eax, eax
0x18001756d  jz      loc_18001741F
0x180017573  mov     r8d, edi; Size
0x180017576  lea     rdx, ?CLSID_Conhost@DelegationConfig@@2U_GUID@@B; Buf2
0x18001757d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180017581  call    memcmp_0
0x180017586  test    eax, eax
0x180017588  jz      short loc_1800175C5
0x18001758a  mov     r8d, edi; Size
0x18001758d  lea     rdx, ?CLSID_Conhost@DelegationConfig@@2U_GUID@@B; Buf2
0x180017594  lea     rcx, [rbp+57h+var_90]; Buf1
0x180017598  call    memcmp_0
0x18001759d  test    eax, eax
0x18001759f  jz      short loc_1800175C5
0x1800175a1  mov     rax, qword ptr [rbp+57h+var_90]
0x1800175a5  movups  xmm0, [rbp+57h+Buf1]
0x1800175a9  mov     [rbx+14h], rax
0x1800175ad  mov     rax, qword ptr [rbp+57h+var_90+8]
0x1800175b1  mov     [rbx+1Ch], rax
0x1800175b5  mov     dword ptr [rbx], 3
0x1800175bb  movdqu  xmmword ptr [rbx+4], xmm0
0x1800175c0  jmp     loc_18001743D
0x1800175c5  movups  xmm0, cs:?ConhostDelegationPair@DelegationConfig@@2UDelegationPair@1@B; DelegationConfig::DelegationPair const DelegationConfig::ConhostDelegationPair
0x1800175cc  mov     eax, cs:dword_18001D490
0x1800175d2  movups  xmm1, cs:xmmword_18001D480
0x1800175d9  jmp     loc_180017433
```

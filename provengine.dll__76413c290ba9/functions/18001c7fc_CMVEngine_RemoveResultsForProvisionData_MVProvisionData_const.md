# CMVEngine::RemoveResultsForProvisionData(_MVProvisionData const &)

- ea: `0x18001c7fc`
- end: `0x18001c9d7`
- name: `?RemoveResultsForProvisionData@CMVEngine@@AEAAXAEBU_MVProvisionData@@@Z`
- size: `475`
- prototype: `void __fastcall(CMVEngine *__hidden this, const struct _MVProvisionData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180018698`

## callees

- `0x18000af20`
- `0x18000b030`
- `0x18001c7fc`
- `0x180022088`
- `0x18002f9bc`
- `0x18003cc98`
- `0x18003d1b8`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c8a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c96b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c999`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c8a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c96b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c999`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c934`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c987`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c987`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c959`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c959`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c906`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMVEngine::RemoveResultsForProvisionData(CMVEngine *this, const struct _MVProvisionData *a2)
{
  char *v3; // rdx
  unsigned __int64 v4; // r8
  void **v5; // rax
  HKEY *v6; // rsi
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  const WCHAR *v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp-19h]
  void *v14[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v15; // [rsp+68h] [rbp-1h]
  unsigned __int64 v16; // [rsp+70h] [rbp+7h]
  void *v17[3]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v18; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v3 = (char *)*((_QWORD *)a2 + 6);
  v16 = 7;
  v15 = 0;
  LOWORD(v14[0]) = 0;
  if ( *(_WORD *)v3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&v3[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  std::wstring::assign(v14, v3, v4);
  v5 = (void **)std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 40, v14);
  v18 = 7;
  v17[2] = 0;
  LOWORD(v17[0]) = 0;
  std::wstring::assign(v17, v5, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v16 >= 8 )
    operator delete(v14[0]);
  v16 = 7;
  v15 = 0;
  LOWORD(v14[0]) = 0;
  v6 = (HKEY *)*std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 38, v17);
  if ( ProvResults::LazyOpenParentKey((ProvResults *)v6) )
  {
    ProvResults::GetChildKeyNameFromProvData(lpSubKey);
    hKey = 0;
    v7 = (const WCHAR *)lpSubKey;
    if ( v13 >= 8 )
      v7 = lpSubKey[0];
    v8 = RegOpenKeyExW(v6[9], v7, 0, 0x10009u, &hKey);
    if ( v8 != 2 )
    {
      if ( v8 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x241,
          (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          (const char *)v8,
          phkResult);
      v9 = (const WCHAR *)lpSubKey;
      if ( v13 >= 8 )
        v9 = lpSubKey[0];
      RegDeleteTreeW(v6[9], v9);
    }
    if ( v13 >= 8 )
      operator delete((void *)lpSubKey[0]);
    LOWORD(lpSubKey[0]) = 0;
    lpSubKey[2] = 0;
    v13 = 7;
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v18 >= 8 )
    operator delete(v17[0]);
}

```

## disassembly

```asm
0x18001c7fc  mov     [rsp-8+arg_10], rbx
0x18001c801  push    rbp
0x18001c802  push    rsi
0x18001c803  push    rdi
0x18001c804  push    r14
0x18001c806  push    r15
0x18001c808  lea     rbp, [rsp-37h]
0x18001c80d  sub     rsp, 0A0h
0x18001c814  mov     rax, cs:__security_cookie
0x18001c81b  xor     rax, rsp
0x18001c81e  mov     [rbp+57h+var_28], rax
0x18001c822  mov     rbx, rdx
0x18001c825  mov     rdi, rcx
0x18001c828  mov     rdx, [rdx+30h]; Src
0x18001c82c  mov     r15d, 7
0x18001c832  mov     [rbp+57h+var_50], r15
0x18001c836  xor     r14d, r14d
0x18001c839  mov     [rbp+57h+var_58], r14
0x18001c83d  mov     word ptr [rbp+57h+var_68], r14w
0x18001c842  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c846  cmp     [rdx], r14w
0x18001c84a  jnz     short loc_18001C851
0x18001c84c  mov     r8d, r14d
0x18001c84f  jmp     short loc_18001C85E
0x18001c851  mov     r8, rsi
0x18001c854  inc     r8
0x18001c857  cmp     [rdx+r8*2], r14w
0x18001c85c  jnz     short loc_18001C854
0x18001c85e  lea     rcx, [rbp+57h+var_68]; void *
0x18001c862  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001c867  nop
0x18001c868  lea     rcx, [rdi+140h]
0x18001c86f  lea     rdx, [rbp+57h+var_68]
0x18001c873  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x18001c878  mov     [rbp+57h+var_30], r15
0x18001c87c  mov     [rbp+57h+var_38], r14
0x18001c880  mov     word ptr [rbp+57h+var_48], r14w
0x18001c885  mov     r9, rsi
0x18001c888  xor     r8d, r8d
0x18001c88b  mov     rdx, rax
0x18001c88e  lea     rcx, [rbp+57h+var_48]; void *
0x18001c892  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c897  nop
0x18001c898  cmp     [rbp+57h+var_50], 8
0x18001c89d  jb      short loc_18001C8A9
0x18001c89f  mov     rcx, [rbp+57h+var_68]
0x18001c8a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c8a9  mov     [rbp+57h+var_50], r15
0x18001c8ad  mov     [rbp+57h+var_58], r14
0x18001c8b1  mov     word ptr [rbp+57h+var_68], r14w
0x18001c8b6  lea     rcx, [rdi+130h]
0x18001c8bd  lea     rdx, [rbp+57h+var_48]
0x18001c8c1  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x18001c8c6  mov     rsi, [rax]
0x18001c8c9  mov     rcx, rsi; this
0x18001c8cc  call    ?LazyOpenParentKey@ProvResults@@AEBA_NXZ; ProvResults::LazyOpenParentKey(void)
0x18001c8d1  test    al, al
0x18001c8d3  jz      loc_18001C98E
0x18001c8d9  mov     [rbp+57h+hKey], r14
0x18001c8dd  mov     rdx, rbx
0x18001c8e0  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18001c8e4  call    ?GetChildKeyNameFromProvData@ProvResults@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MVProvisionData@@@Z; ProvResults::GetChildKeyNameFromProvData(_MVProvisionData const &)
0x18001c8e9  nop
0x18001c8ea  mov     rdi, [rbp+57h+hKey]
0x18001c8ee  test    rdi, rdi
0x18001c8f1  jz      short loc_18001C90C
0x18001c8f3  call    cs:__imp_GetLastError
0x18001c8f9  mov     ebx, eax
0x18001c8fb  mov     rcx, rdi; hKey
0x18001c8fe  call    cs:__imp_RegCloseKey
0x18001c904  mov     ecx, ebx; dwErrCode
0x18001c906  call    cs:__imp_SetLastError
0x18001c90c  mov     [rbp+57h+hKey], r14
0x18001c910  lea     rdx, [rbp+57h+lpSubKey]
0x18001c914  cmp     [rbp+57h+var_70], 8
0x18001c919  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001c91e  lea     rax, [rbp+57h+hKey]
0x18001c922  mov     qword ptr [rsp+0C0h+phkResult], rax; unsigned int
0x18001c927  mov     r9d, 10009h; samDesired
0x18001c92d  xor     r8d, r8d; ulOptions
0x18001c930  mov     rcx, [rsi+48h]; hKey
0x18001c934  call    cs:__imp_RegOpenKeyExW
0x18001c93a  cmp     eax, 2
0x18001c93d  jz      short loc_18001C960
0x18001c93f  mov     rcx, [rbp+5Fh]; this
0x18001c943  test    eax, eax
0x18001c945  jnz     short loc_18001C9C2
0x18001c947  lea     rdx, [rbp+57h+lpSubKey]
0x18001c94b  cmp     [rbp+57h+var_70], 8
0x18001c950  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001c955  mov     rcx, [rsi+48h]; hKey
0x18001c959  call    cs:__imp_RegDeleteTreeW
0x18001c95f  nop
0x18001c960  cmp     [rbp+57h+var_70], 8
0x18001c965  jb      short loc_18001C971
0x18001c967  mov     rcx, [rbp+57h+lpSubKey]
0x18001c96b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c971  mov     word ptr [rbp+57h+lpSubKey], r14w
0x18001c976  mov     [rbp+57h+var_78], r14
0x18001c97a  mov     [rbp+57h+var_70], r15
0x18001c97e  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c982  test    rcx, rcx
0x18001c985  jz      short loc_18001C98E
0x18001c987  call    cs:__imp_RegCloseKey
0x18001c98d  nop
0x18001c98e  cmp     [rbp+57h+var_30], 8
0x18001c993  jb      short loc_18001C99F
0x18001c995  mov     rcx, [rbp+57h+var_48]
0x18001c999  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c99f  mov     rcx, [rbp+57h+var_28]
0x18001c9a3  xor     rcx, rsp; StackCookie
0x18001c9a6  call    __security_check_cookie
0x18001c9ab  mov     rbx, [rsp+0C0h+arg_10]
0x18001c9b3  add     rsp, 0A0h
0x18001c9ba  pop     r15
0x18001c9bc  pop     r14
0x18001c9be  pop     rdi
0x18001c9bf  pop     rsi
0x18001c9c0  pop     rbp
0x18001c9c1  retn
0x18001c9c2  mov     r9d, eax; char *
0x18001c9c5  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18001c9cc  mov     edx, 241h; void *
0x18001c9d1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```

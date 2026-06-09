# RegistrySerialization::s_OpenConsoleKey(HKEY__ * *,HKEY__ * *)

- ea: `0x180018580`
- end: `0x1800186b6`
- name: `?s_OpenConsoleKey@RegistrySerialization@@SAJPEAPEAUHKEY__@@0@Z`
- size: `310`
- prototype: `__int64 __fastcall(HKEY *, HKEY *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800114d4`
- `0x180011f44`
- `0x180017368`
- `0x1800175e4`

## callees

- `0x180003ad8`
- `0x180003ccc`
- `0x1800150f0`
- `0x18001851c`
- `0x180018580`
- `0x1800186bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001863f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001863f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800185b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800185b8`

## pseudocode

```c
__int64 __fastcall RegistrySerialization::s_OpenConsoleKey(HKEY *a1, HKEY *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  HKEY v6; // rbx
  HKEY v7; // rbx
  HKEY hKey; // [rsp+40h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+28h] BYREF
  char v11; // [rsp+50h] [rbp+30h] BYREF

  hKey = 0;
  *a1 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  *a2 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = 0;
  v4 = RegOpenCurrentUser(0x2001Fu, &phkResult);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0xC0070000;
  if ( v5 >= 0 )
  {
    v6 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
      RegCloseKey(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
    }
    hKey = 0;
    v5 = RegistrySerialization::s_OpenKey(phkResult, L"Console", &hKey);
    if ( v5 == -1073283070 )
    {
      v7 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        RegCloseKey(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      hKey = 0;
      v5 = RegistrySerialization::s_CreateKey(phkResult, L"Console", &hKey);
    }
    if ( v5 >= 0 )
    {
      *a1 = phkResult;
      *a2 = hKey;
      phkResult = 0;
      hKey = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018580  mov     [rsp-18h+arg_18], rbx
0x180018585  push    rbp
0x180018586  push    rsi
0x180018587  push    rdi
0x180018588  mov     rbp, rsp
0x18001858b  sub     rsp, 20h
0x18001858f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018593  mov     [rbp+hKey], 0
0x18001859b  mov     [rcx], rax
0x18001859e  mov     rdi, rdx
0x1800185a1  mov     [rdx], rax
0x1800185a4  mov     rsi, rcx
0x1800185a7  lea     rdx, [rbp+phkResult]; phkResult
0x1800185ab  mov     [rbp+phkResult], 0
0x1800185b3  mov     ecx, 2001Fh; samDesired
0x1800185b8  call    cs:__imp_RegOpenCurrentUser
0x1800185bf  nop     dword ptr [rax+rax+00h]
0x1800185c4  mov     ebx, eax
0x1800185c6  test    eax, eax
0x1800185c8  jle     short loc_1800185D3
0x1800185ca  movzx   ebx, ax
0x1800185cd  or      ebx, 0C0070000h
0x1800185d3  test    ebx, ebx
0x1800185d5  js      loc_180018694
0x1800185db  mov     rbx, [rbp+hKey]
0x1800185df  test    rbx, rbx
0x1800185e2  jz      short loc_180018605
0x1800185e4  lea     rcx, [rbp+arg_10]; this
0x1800185e8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800185ed  mov     rcx, rbx; hKey
0x1800185f0  call    cs:__imp_RegCloseKey
0x1800185f7  nop     dword ptr [rax+rax+00h]
0x1800185fc  lea     rcx, [rbp+arg_10]; this
0x180018600  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018605  mov     rcx, [rbp+phkResult]; HKEY
0x180018609  lea     r8, [rbp+hKey]; HKEY *
0x18001860d  lea     rdx, aConsole; "Console"
0x180018614  mov     [rbp+hKey], 0
0x18001861c  call    ?s_OpenKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_OpenKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x180018621  mov     ebx, eax
0x180018623  cmp     eax, 0C0070002h
0x180018628  jnz     short loc_180018672
0x18001862a  mov     rbx, [rbp+hKey]
0x18001862e  test    rbx, rbx
0x180018631  jz      short loc_180018654
0x180018633  lea     rcx, [rbp+arg_10]; this
0x180018637  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001863c  mov     rcx, rbx; hKey
0x18001863f  call    cs:__imp_RegCloseKey
0x180018646  nop     dword ptr [rax+rax+00h]
0x18001864b  lea     rcx, [rbp+arg_10]; this
0x18001864f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018654  mov     rcx, [rbp+phkResult]; HKEY
0x180018658  lea     r8, [rbp+hKey]; HKEY *
0x18001865c  lea     rdx, aConsole; "Console"
0x180018663  mov     [rbp+hKey], 0
0x18001866b  call    ?s_CreateKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z; RegistrySerialization::s_CreateKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)
0x180018670  mov     ebx, eax
0x180018672  test    ebx, ebx
0x180018674  js      short loc_180018694
0x180018676  mov     rax, [rbp+phkResult]
0x18001867a  mov     [rsi], rax
0x18001867d  mov     rax, [rbp+hKey]
0x180018681  mov     [rdi], rax
0x180018684  mov     [rbp+phkResult], 0
0x18001868c  mov     [rbp+hKey], 0
0x180018694  lea     rcx, [rbp+hKey]
0x180018698  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001869d  lea     rcx, [rbp+phkResult]
0x1800186a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800186a6  mov     eax, ebx
0x1800186a8  mov     rbx, [rsp+20h+arg_18]
0x1800186ad  add     rsp, 20h
0x1800186b1  pop     rdi
0x1800186b2  pop     rsi
0x1800186b3  pop     rbp
0x1800186b4  retn
```

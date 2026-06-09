# helium::GetChildCount(ushort const *)

- ea: `0x180012180`
- end: `0x1800122b9`
- name: `?GetChildCount@helium@@YAKPEBG@Z`
- size: `313`
- prototype: `unsigned int __fastcall(helium *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012c08`
- `0x180012d70`

## callees

- `0x1800118c0`
- `0x180012180`
- `0x180013100`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001224f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001224f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001226f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001226f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121cf`

## string_xrefs

- `0x180012292`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`
- `0x1800122a7`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`
- `0x1800121c1`: `Software\Microsoft\AppModel\Lookaside\Packages`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall helium::GetChildCount(helium *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  DWORD v5; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  HKEY *p_hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY v9; // [rsp+68h] [rbp-18h] BYREF
  char v10; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  DWORD cSubKeys; // [rsp+90h] [rbp+10h] BYREF
  int v13; // [rsp+94h] [rbp+14h]
  HKEY hKey; // [rsp+98h] [rbp+18h] BYREF

  v13 = HIDWORD(this);
  cSubKeys = 0;
  hKey = 0;
  p_hKey = &hKey;
  v9 = 0;
  v10 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\AppModel\\Lookaside\\Packages", 0, 0x20019u, &v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v2 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v2,
        phkResult);
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v4,
        phkResulta);
    v5 = cSubKeys;
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
}

```

## disassembly

```asm
0x180012180  mov     [rsp-8+arg_10], rbx
0x180012185  mov     qword ptr [rsp-8+cSubKeys], rcx
0x18001218a  push    rbp
0x18001218b  mov     rbp, rsp
0x18001218e  sub     rsp, 80h
0x180012195  and     [rbp+cSubKeys], 0
0x180012199  and     [rbp+hKey], 0
0x18001219e  lea     rax, [rbp+hKey]
0x1800121a2  mov     [rbp+var_20], rax
0x1800121a6  and     [rbp+var_18], 0
0x1800121ab  mov     [rbp+var_10], 1
0x1800121af  lea     rax, [rbp+var_18]
0x1800121b3  mov     [rsp+80h+phkResult], rax; unsigned int
0x1800121b8  mov     r9d, 20019h; samDesired
0x1800121be  xor     r8d, r8d; ulOptions
0x1800121c1  lea     rdx, SubKey; "Software\\Microsoft\\AppModel\\Lookasid"...
0x1800121c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800121cf  call    cs:__imp_RegOpenKeyExW
0x1800121d6  nop     dword ptr [rax+rax+00h]
0x1800121db  mov     ebx, eax
0x1800121dd  lea     rcx, [rbp+var_20]
0x1800121e1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800121e6  cmp     ebx, 2
0x1800121e9  jnz     short loc_180012204
0x1800121eb  mov     rcx, [rbp+hKey]; hKey
0x1800121ef  test    rcx, rcx
0x1800121f2  jz      short loc_180012200
0x1800121f4  call    cs:__imp_RegCloseKey
0x1800121fb  nop     dword ptr [rax+rax+00h]
0x180012200  xor     eax, eax
0x180012202  jmp     short loc_18001227D
0x180012204  mov     rcx, [rbp+8]; this
0x180012208  test    ebx, ebx
0x18001220a  jnz     loc_1800122A4
0x180012210  and     [rsp+80h+var_28], 0
0x180012216  and     [rsp+80h+var_30], 0
0x18001221c  and     [rsp+80h+var_38], 0
0x180012222  and     [rsp+80h+var_40], 0
0x180012228  and     [rsp+80h+var_48], 0
0x18001222e  and     [rsp+80h+var_50], 0
0x180012234  and     [rsp+80h+var_58], 0
0x18001223a  lea     rax, [rbp+cSubKeys]
0x18001223e  mov     [rsp+80h+phkResult], rax; unsigned int
0x180012243  xor     r9d, r9d; lpReserved
0x180012246  xor     r8d, r8d; lpcchClass
0x180012249  xor     edx, edx; lpClass
0x18001224b  mov     rcx, [rbp+hKey]; hKey
0x18001224f  call    cs:__imp_RegQueryInfoKeyW
0x180012256  nop     dword ptr [rax+rax+00h]
0x18001225b  mov     rcx, [rbp+8]; this
0x18001225f  test    eax, eax
0x180012261  jnz     short loc_18001228F
0x180012263  mov     ebx, [rbp+cSubKeys]
0x180012266  mov     rcx, [rbp+hKey]; hKey
0x18001226a  test    rcx, rcx
0x18001226d  jz      short loc_18001227B
0x18001226f  call    cs:__imp_RegCloseKey
0x180012276  nop     dword ptr [rax+rax+00h]
0x18001227b  mov     eax, ebx
0x18001227d  mov     rbx, [rsp+80h+arg_10]
0x180012285  add     rsp, 80h
0x18001228c  pop     rbp
0x18001228d  retn
0x18001228f  mov     r9d, eax; char *
0x180012292  lea     r8, aOnecoreBaseApp_57; "onecore\\base\\appmodel\\execmodel\\des"...
0x180012299  mov     edx, 0F0h; void *
0x18001229e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800122a4  mov     r9d, ebx; char *
0x1800122a7  lea     r8, aOnecoreBaseApp_57; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800122ae  mov     edx, 0EFh; void *
0x1800122b3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

# wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)

- ea: `0x180029380`
- end: `0x18002941b`
- name: `?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180027c44`
- `0x180063920`

## callees

- `0x180029380`
- `0x180029424`
- `0x180029474`
- `0x18003cf0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293d7`

## string_xrefs

- `0x1800293c9`: `SYSTEM\CurrentControlSet\Services\RasMan\Profiles\`
- `0x1800293f5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::reg::open_unique_key(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  HKEY *v6; // rbx
  REGSAM access_flags; // eax
  int v8; // eax
  bool v9; // sf
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a1);
  access_flags = wil::reg::reg_view_details::get_access_flags(a4);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Profiles\\",
         0,
         access_flags,
         v6);
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8 < 0;
  }
  if ( v9 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v8,
      phkResult);
  return a1;
}

```

## disassembly

```asm
0x180029380  mov     rax, rsp
0x180029383  mov     [rax+10h], rbx
0x180029387  mov     [rax+18h], rsi
0x18002938b  mov     [rax+8], rcx
0x18002938f  push    rdi
0x180029390  sub     rsp, 40h
0x180029394  mov     edi, r9d
0x180029397  mov     rsi, rcx
0x18002939a  mov     dword ptr [rax-18h], 0
0x1800293a1  mov     qword ptr [rcx], 0
0x1800293a8  mov     dword ptr [rax-18h], 1
0x1800293af  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800293b4  mov     rbx, rax
0x1800293b7  mov     ecx, edi
0x1800293b9  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x1800293be  mov     qword ptr [rsp+48h+phkResult], rbx; int
0x1800293c3  mov     r9d, eax; samDesired
0x1800293c6  xor     r8d, r8d; ulOptions
0x1800293c9  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800293d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800293d7  call    cs:__imp_RegOpenKeyExW
0x1800293dd  test    eax, eax
0x1800293df  jle     short loc_1800293EB
0x1800293e1  movzx   eax, ax
0x1800293e4  or      eax, 80070000h
0x1800293e9  test    eax, eax
0x1800293eb  jns     short loc_180029407
0x1800293ed  mov     rcx, [rsp+48h]; this
0x1800293f2  mov     r9d, eax; char *
0x1800293f5  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800293fc  mov     edx, 1CBEh; void *
0x180029401  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180029407  mov     rax, rsi
0x18002940a  mov     rbx, [rsp+48h+arg_8]
0x18002940f  mov     rsi, [rsp+48h+arg_10]
0x180029414  add     rsp, 40h
0x180029418  pop     rdi
0x180029419  retn
```

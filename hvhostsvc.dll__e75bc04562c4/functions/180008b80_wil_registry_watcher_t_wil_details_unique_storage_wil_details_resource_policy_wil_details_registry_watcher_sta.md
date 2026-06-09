# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180008b80`
- end: `0x180008c4f`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `207`
- prototype: `LSTATUS __fastcall(__int64, HKEY, const WCHAR *, char, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800084f4`

## callees

- `0x180007f58`
- `0x180008250`
- `0x180008b80`
- `0x180008c58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008bd4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008bd4`

## string_xrefs

- `0x180008c23`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180008c3d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LSTATUS __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        char a4,
        __int64 a5)
{
  int Key; // eax
  __int64 v8; // r8
  bool v9; // sf
  int common; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  HKEY v13[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v13[0] = 0;
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x10u, 0, v13, 0);
  v9 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v9 = Key < 0;
  }
  if ( v9 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Key,
      dwOptions);
  LOBYTE(v8) = a4;
  common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
             a1,
             v13,
             v8,
             a5);
  if ( common < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)common,
      dwOptions);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v13);
}

```

## disassembly

```asm
0x180008b80  mov     r11, rsp
0x180008b83  mov     [r11+8], rbx
0x180008b87  push    rdi
0x180008b88  sub     rsp, 60h
0x180008b8c  mov     bl, r9b
0x180008b8f  mov     rax, r8
0x180008b92  mov     r10, rdx
0x180008b95  mov     rdi, rcx
0x180008b98  mov     qword ptr [r11-18h], 0
0x180008ba0  mov     qword ptr [r11-28h], 0
0x180008ba8  lea     rcx, [r11-18h]
0x180008bac  mov     [r11-30h], rcx
0x180008bb0  mov     qword ptr [r11-38h], 0
0x180008bb8  mov     [rsp+68h+samDesired], 10h; samDesired
0x180008bc0  mov     [rsp+68h+dwOptions], 0; int
0x180008bc8  xor     r9d, r9d; lpClass
0x180008bcb  xor     r8d, r8d; Reserved
0x180008bce  mov     rdx, rax; lpSubKey
0x180008bd1  mov     rcx, r10; hKey
0x180008bd4  call    cs:__imp_RegCreateKeyExW
0x180008bda  test    eax, eax
0x180008bdc  jle     short loc_180008BE8
0x180008bde  movzx   eax, ax
0x180008be1  or      eax, 80070000h
0x180008be6  test    eax, eax
0x180008be8  js      short loc_180008C35
0x180008bea  mov     r9, [rsp+68h+arg_20]
0x180008bf2  mov     r8b, bl
0x180008bf5  lea     rdx, [rsp+68h+var_18]
0x180008bfa  mov     rcx, rdi
0x180008bfd  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180008c02  mov     rcx, [rsp+68h]; this
0x180008c07  test    eax, eax
0x180008c09  js      short loc_180008C20
0x180008c0b  lea     rcx, [rsp+68h+var_18]
0x180008c10  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180008c15  mov     rbx, [rsp+68h+arg_0]
0x180008c1a  add     rsp, 60h
0x180008c1e  pop     rdi
0x180008c1f  retn
0x180008c20  mov     r9d, eax; char *
0x180008c23  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008c2a  mov     edx, 1CBEh; void *
0x180008c2f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008c35  mov     rcx, [rsp+68h]; this
0x180008c3a  mov     r9d, eax; char *
0x180008c3d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008c44  mov     edx, 1CBEh; void *
0x180008c49  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

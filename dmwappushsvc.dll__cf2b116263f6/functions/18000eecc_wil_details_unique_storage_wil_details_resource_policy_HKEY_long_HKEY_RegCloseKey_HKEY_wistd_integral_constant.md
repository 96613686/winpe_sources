# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)

- ea: `0x18000eecc`
- end: `0x18000ef19`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z`
- size: `77`
- prototype: `void __fastcall(HKEY *, HKEY)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000df4c`
- `0x18000e2d0`
- `0x18000e354`
- `0x18000eccc`
- `0x18000f0ec`
- `0x18000faf0`
- `0x18000ffa0`
- `0x180010770`

## callees

- `0x1800074a0`
- `0x180007c98`
- `0x18000eecc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eef6`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        HKEY *a1,
        HKEY a2)
{
  HKEY v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    RegCloseKey(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000eecc  mov     [rsp+arg_8], rbx
0x18000eed1  mov     [rsp+arg_10], rsi
0x18000eed6  push    rdi
0x18000eed7  sub     rsp, 20h
0x18000eedb  mov     rdi, [rcx]
0x18000eede  mov     rsi, rdx
0x18000eee1  mov     rbx, rcx
0x18000eee4  test    rdi, rdi
0x18000eee7  jz      short loc_18000EF06
0x18000eee9  lea     rcx, [rsp+28h+arg_0]; this
0x18000eeee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000eef3  mov     rcx, rdi; hKey
0x18000eef6  call    cs:__imp_RegCloseKey
0x18000eefc  lea     rcx, [rsp+28h+arg_0]; this
0x18000ef01  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ef06  mov     [rbx], rsi
0x18000ef09  mov     rbx, [rsp+28h+arg_8]
0x18000ef0e  mov     rsi, [rsp+28h+arg_10]
0x18000ef13  add     rsp, 20h
0x18000ef17  pop     rdi
0x18000ef18  retn
```

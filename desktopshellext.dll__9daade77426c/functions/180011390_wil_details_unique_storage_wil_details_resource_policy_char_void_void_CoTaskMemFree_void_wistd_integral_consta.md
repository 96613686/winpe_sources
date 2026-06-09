# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x180011390`
- end: `0x1800113cc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fe58`

## callees

- `0x180011390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800113ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800113ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113b2`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180011390  push    rbx
0x180011392  push    rbp
0x180011393  push    rsi
0x180011394  push    rdi
0x180011395  sub     rsp, 28h
0x180011399  mov     rsi, [rcx]
0x18001139c  mov     rbp, rdx
0x18001139f  mov     rdi, rcx
0x1800113a2  test    rsi, rsi
0x1800113a5  jz      short loc_1800113C0
0x1800113a7  call    cs:__imp_GetLastError
0x1800113ad  mov     rcx, rsi; pv
0x1800113b0  mov     ebx, eax
0x1800113b2  call    cs:__imp_CoTaskMemFree
0x1800113b8  mov     ecx, ebx; dwErrCode
0x1800113ba  call    cs:__imp_SetLastError
0x1800113c0  mov     [rdi], rbp
0x1800113c3  add     rsp, 28h
0x1800113c7  pop     rdi
0x1800113c8  pop     rsi
0x1800113c9  pop     rbp
0x1800113ca  pop     rbx
0x1800113cb  retn
```

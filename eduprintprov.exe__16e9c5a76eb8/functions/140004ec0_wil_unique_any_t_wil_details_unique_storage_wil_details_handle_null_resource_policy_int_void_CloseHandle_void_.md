# wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)

- ea: `0x140004ec0`
- end: `0x140004edc`
- name: `??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013231`
- `0x1400132d6`
- `0x140013310`
- `0x140013893`

## callees

- `0x140004ec0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ed1`

## pseudocode

```c
int __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(
        void **a1)
{
  char *v1; // rcx
  int result; // eax

  v1 = (char *)*a1;
  result = (_DWORD)v1 - 1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x140004ec0  sub     rsp, 28h
0x140004ec4  mov     rcx, [rcx]; hObject
0x140004ec7  lea     rax, [rcx-1]
0x140004ecb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140004ecf  ja      short loc_140004ED7
0x140004ed1  call    cs:__imp_CloseHandle
0x140004ed7  add     rsp, 28h
0x140004edb  retn
```

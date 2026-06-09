# wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)

- ea: `0x180006460`
- end: `0x18000647c`
- name: `??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `28`
- prototype: `int __fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018758`
- `0x18001876a`
- `0x1800187c3`
- `0x180018889`
- `0x18001889b`
- `0x1800188e3`
- `0x180018b39`

## callees

- `0x180006460`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006471`

## pseudocode

```c
int __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(
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
0x180006460  sub     rsp, 28h
0x180006464  mov     rcx, [rcx]; hObject
0x180006467  lea     rax, [rcx-1]
0x18000646b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000646f  ja      short loc_180006477
0x180006471  call    cs:__imp_CloseHandle
0x180006477  add     rsp, 28h
0x18000647b  retn
```

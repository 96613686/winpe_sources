# wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)

- ea: `0x180007064`
- end: `0x180007080`
- name: `??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ`
- size: `28`
- prototype: `int __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006ebc`
- `0x180007000`
- `0x1800071d0`
- `0x1800082fc`
- `0x180008380`
- `0x1800084f4`

## callees

- `0x180007064`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007075`

## pseudocode

```c
int __fastcall wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(
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
0x180007064  sub     rsp, 28h
0x180007068  mov     rcx, [rcx]; hObject
0x18000706b  lea     rax, [rcx-1]
0x18000706f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007073  ja      short loc_18000707B
0x180007075  call    cs:__imp_CloseHandle
0x18000707b  add     rsp, 28h
0x18000707f  retn
```

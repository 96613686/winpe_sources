# wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>>(void)

- ea: `0x1800064a8`
- end: `0x1800064c4`
- name: `??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `28`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800185ee`
- `0x180018604`
- `0x1800186b6`
- `0x1800186c8`
- `0x180018722`
- `0x180018a71`
- `0x180018b03`
- `0x180018b27`

## callees

- `0x1800064a8`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x1800064b9`
- `WIMGAPI!WIMCloseHandle` at `0x1800064b9`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int WIMCloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int WIMCloseHandle(void *)>>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  result = v1 - 1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return WIMCloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x1800064a8  sub     rsp, 28h
0x1800064ac  mov     rcx, [rcx]
0x1800064af  lea     rax, [rcx-1]
0x1800064b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800064b7  ja      short loc_1800064BF
0x1800064b9  call    cs:__imp_WIMCloseHandle
0x1800064bf  add     rsp, 28h
0x1800064c3  retn
```

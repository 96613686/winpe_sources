# FciCallbacks::CallbackFciFileWrite(__int64,void *,uint,int *,void *)

- ea: `0x18000d520`
- end: `0x18000d54e`
- name: `?CallbackFciFileWrite@FciCallbacks@@SAI_JPEAXIPEAH1@Z`
- size: `46`
- prototype: `__int64 __fastcall(INT_PTR hf, void *memory, UINT cb, DWORD *err)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000c48c`
- `0x18000d520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d539`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciFileWrite(INT_PTR hf, void *memory, UINT cb, DWORD *err)
{
  unsigned int v5; // ebx

  v5 = Utils::WriteFile((void *const)hf, memory, cb);
  if ( v5 == -1 )
    *err = GetLastError();
  return v5;
}

```

## disassembly

```asm
0x18000d520  mov     [rsp+arg_0], rbx
0x18000d525  push    rdi
0x18000d526  sub     rsp, 20h
0x18000d52a  mov     rdi, r9
0x18000d52d  call    ?WriteFile@Utils@@SAIQEAXPEBXI@Z; Utils::WriteFile(void * const,void const *,uint)
0x18000d532  mov     ebx, eax
0x18000d534  cmp     eax, 0FFFFFFFFh
0x18000d537  jnz     short loc_18000D541
0x18000d539  call    cs:__imp_GetLastError
0x18000d53f  mov     [rdi], eax
0x18000d541  mov     eax, ebx
0x18000d543  mov     rbx, [rsp+28h+arg_0]
0x18000d548  add     rsp, 20h
0x18000d54c  pop     rdi
0x18000d54d  retn
```

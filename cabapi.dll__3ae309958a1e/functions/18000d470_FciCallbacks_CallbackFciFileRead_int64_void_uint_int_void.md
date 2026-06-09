# FciCallbacks::CallbackFciFileRead(__int64,void *,uint,int *,void *)

- ea: `0x18000d470`
- end: `0x18000d49e`
- name: `?CallbackFciFileRead@FciCallbacks@@SAI_JPEAXIPEAH1@Z`
- size: `46`
- prototype: `__int64 __fastcall(INT_PTR hf, void *memory, UINT cb, DWORD *err)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000bfdc`
- `0x18000d470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d489`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciFileRead(INT_PTR hf, void *memory, UINT cb, DWORD *err)
{
  unsigned int File; // ebx

  File = Utils::ReadFile((void *const)hf, memory, cb);
  if ( File == -1 )
    *err = GetLastError();
  return File;
}

```

## disassembly

```asm
0x18000d470  mov     [rsp+arg_0], rbx
0x18000d475  push    rdi
0x18000d476  sub     rsp, 20h
0x18000d47a  mov     rdi, r9
0x18000d47d  call    ?ReadFile@Utils@@SAIQEAXPEAXI@Z; Utils::ReadFile(void * const,void *,uint)
0x18000d482  mov     ebx, eax
0x18000d484  cmp     eax, 0FFFFFFFFh
0x18000d487  jnz     short loc_18000D491
0x18000d489  call    cs:__imp_GetLastError
0x18000d48f  mov     [rdi], eax
0x18000d491  mov     eax, ebx
0x18000d493  mov     rbx, [rsp+28h+arg_0]
0x18000d498  add     rsp, 20h
0x18000d49c  pop     rdi
0x18000d49d  retn
```

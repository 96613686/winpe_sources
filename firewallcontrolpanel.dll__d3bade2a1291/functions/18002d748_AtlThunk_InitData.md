# AtlThunk_InitData

- ea: `0x18002d748`
- end: `0x18002d7c1`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a53c`
- `0x18000a630`
- `0x18000b480`
- `0x180018290`
- `0x180018384`
- `0x180018478`
- `0x18001856c`
- `0x1800277c4`

## callees

- `0x18002d3dc`
- `0x18002d748`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d785`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d785`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18002d797`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18002d797`

## pseudocode

```c
void __stdcall AtlThunk_InitData(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)
{
  char *v3; // rbx
  HANDLE CurrentProcess; // rax
  void (__fastcall *ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64)(_QWORD, void *, size_t); // rax

  if ( Thunk )
  {
    v3 = (char *)*((_QWORD *)Thunk + 1);
    if ( v3 )
    {
      if ( *(_DWORD *)Thunk )
      {
        *(_WORD *)v3 = -18104;
        *(_QWORD *)(v3 + 2) = FirstParameter;
        *((_WORD *)v3 + 5) = -18360;
        *(_QWORD *)(v3 + 12) = Proc;
        *((_WORD *)v3 + 10) = -7937;
        CurrentProcess = GetCurrentProcess();
        FlushInstructionCache(CurrentProcess, v3, 0x16u);
      }
      else
      {
        ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 = (void (__fastcall *)(_QWORD, void *, size_t))GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__();
        if ( ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 )
          ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64(
            *((_QWORD *)Thunk + 1),
            Proc,
            FirstParameter);
      }
    }
  }
}

```

## disassembly

```asm
0x18002d748  test    rcx, rcx
0x18002d74b  jz      short locret_18002D7C0
0x18002d74d  push    rbx
0x18002d74e  push    rbp
0x18002d74f  push    rsi
0x18002d750  push    rdi
0x18002d751  sub     rsp, 28h
0x18002d755  mov     rbx, [rcx+8]
0x18002d759  mov     rsi, r8
0x18002d75c  mov     rbp, rdx
0x18002d75f  mov     rdi, rcx
0x18002d762  test    rbx, rbx
0x18002d765  jz      short loc_18002D7B8
0x18002d767  cmp     dword ptr [rcx], 0
0x18002d76a  jz      short loc_18002D79F
0x18002d76c  mov     word ptr [rbx], 0B948h
0x18002d771  mov     [rbx+2], r8
0x18002d775  mov     word ptr [rbx+0Ah], 0B848h
0x18002d77b  mov     [rbx+0Ch], rdx
0x18002d77f  mov     word ptr [rbx+14h], 0E0FFh
0x18002d785  call    cs:__imp_GetCurrentProcess
0x18002d78b  mov     r8d, 16h; dwSize
0x18002d791  mov     rdx, rbx; lpBaseAddress
0x18002d794  mov     rcx, rax; hProcess
0x18002d797  call    cs:__imp_FlushInstructionCache
0x18002d79d  jmp     short loc_18002D7B8
0x18002d79f  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x18002d7a4  test    rax, rax
0x18002d7a7  jz      short loc_18002D7B8
0x18002d7a9  mov     rcx, [rdi+8]
0x18002d7ad  mov     r8, rsi
0x18002d7b0  mov     rdx, rbp
0x18002d7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7b8  add     rsp, 28h
0x18002d7bc  pop     rdi
0x18002d7bd  pop     rsi
0x18002d7be  pop     rbp
0x18002d7bf  pop     rbx
0x18002d7c0  retn
```

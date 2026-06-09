# AtlThunk_InitData

- ea: `0x14000f5bc`
- end: `0x14000f635`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aac0`
- `0x14000b7c0`

## callees

- `0x14000f268`
- `0x14000f5bc`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f5f9`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x14000f60b`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x14000f60b`

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
0x14000f5bc  test    rcx, rcx
0x14000f5bf  jz      short locret_14000F634
0x14000f5c1  push    rbx
0x14000f5c2  push    rbp
0x14000f5c3  push    rsi
0x14000f5c4  push    rdi
0x14000f5c5  sub     rsp, 28h
0x14000f5c9  mov     rbx, [rcx+8]
0x14000f5cd  mov     rsi, r8
0x14000f5d0  mov     rbp, rdx
0x14000f5d3  mov     rdi, rcx
0x14000f5d6  test    rbx, rbx
0x14000f5d9  jz      short loc_14000F62C
0x14000f5db  cmp     dword ptr [rcx], 0
0x14000f5de  jz      short loc_14000F613
0x14000f5e0  mov     word ptr [rbx], 0B948h
0x14000f5e5  mov     [rbx+2], r8
0x14000f5e9  mov     word ptr [rbx+0Ah], 0B848h
0x14000f5ef  mov     [rbx+0Ch], rdx
0x14000f5f3  mov     word ptr [rbx+14h], 0E0FFh
0x14000f5f9  call    cs:__imp_GetCurrentProcess
0x14000f5ff  mov     r8d, 16h; dwSize
0x14000f605  mov     rdx, rbx; lpBaseAddress
0x14000f608  mov     rcx, rax; hProcess
0x14000f60b  call    cs:__imp_FlushInstructionCache
0x14000f611  jmp     short loc_14000F62C
0x14000f613  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x14000f618  test    rax, rax
0x14000f61b  jz      short loc_14000F62C
0x14000f61d  mov     rcx, [rdi+8]
0x14000f621  mov     r8, rsi
0x14000f624  mov     rdx, rbp
0x14000f627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f62c  add     rsp, 28h
0x14000f630  pop     rdi
0x14000f631  pop     rsi
0x14000f632  pop     rbp
0x14000f633  pop     rbx
0x14000f634  retn
```

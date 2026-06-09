# AtlThunk_InitData

- ea: `0x18004f778`
- end: `0x18004f7f1`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f1a0`
- `0x18002fb10`

## callees

- `0x18004f424`
- `0x18004f778`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f7b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004f7b5`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004f7c7`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x18004f7c7`

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
0x18004f778  test    rcx, rcx
0x18004f77b  jz      short locret_18004F7F0
0x18004f77d  push    rbx
0x18004f77e  push    rbp
0x18004f77f  push    rsi
0x18004f780  push    rdi
0x18004f781  sub     rsp, 28h
0x18004f785  mov     rbx, [rcx+8]
0x18004f789  mov     rsi, r8
0x18004f78c  mov     rbp, rdx
0x18004f78f  mov     rdi, rcx
0x18004f792  test    rbx, rbx
0x18004f795  jz      short loc_18004F7E8
0x18004f797  cmp     dword ptr [rcx], 0
0x18004f79a  jz      short loc_18004F7CF
0x18004f79c  mov     word ptr [rbx], 0B948h
0x18004f7a1  mov     [rbx+2], r8
0x18004f7a5  mov     word ptr [rbx+0Ah], 0B848h
0x18004f7ab  mov     [rbx+0Ch], rdx
0x18004f7af  mov     word ptr [rbx+14h], 0E0FFh
0x18004f7b5  call    cs:__imp_GetCurrentProcess
0x18004f7bb  mov     r8d, 16h; dwSize
0x18004f7c1  mov     rdx, rbx; lpBaseAddress
0x18004f7c4  mov     rcx, rax; hProcess
0x18004f7c7  call    cs:__imp_FlushInstructionCache
0x18004f7cd  jmp     short loc_18004F7E8
0x18004f7cf  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x18004f7d4  test    rax, rax
0x18004f7d7  jz      short loc_18004F7E8
0x18004f7d9  mov     rcx, [rdi+8]
0x18004f7dd  mov     r8, rsi
0x18004f7e0  mov     rdx, rbp
0x18004f7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7e8  add     rsp, 28h
0x18004f7ec  pop     rdi
0x18004f7ed  pop     rsi
0x18004f7ee  pop     rbp
0x18004f7ef  pop     rbx
0x18004f7f0  retn
```

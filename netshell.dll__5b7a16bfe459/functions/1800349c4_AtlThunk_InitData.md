# AtlThunk_InitData

- ea: `0x1800349c4`
- end: `0x180034a3d`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b030`
- `0x18002b4d0`
- `0x18002bfb8`
- `0x180059128`

## callees

- `0x180034658`
- `0x1800349c4`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034a01`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180034a13`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x180034a13`

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
0x1800349c4  test    rcx, rcx
0x1800349c7  jz      short locret_180034A3C
0x1800349c9  push    rbx
0x1800349ca  push    rbp
0x1800349cb  push    rsi
0x1800349cc  push    rdi
0x1800349cd  sub     rsp, 28h
0x1800349d1  mov     rbx, [rcx+8]
0x1800349d5  mov     rsi, r8
0x1800349d8  mov     rbp, rdx
0x1800349db  mov     rdi, rcx
0x1800349de  test    rbx, rbx
0x1800349e1  jz      short loc_180034A34
0x1800349e3  cmp     dword ptr [rcx], 0
0x1800349e6  jz      short loc_180034A1B
0x1800349e8  mov     word ptr [rbx], 0B948h
0x1800349ed  mov     [rbx+2], r8
0x1800349f1  mov     word ptr [rbx+0Ah], 0B848h
0x1800349f7  mov     [rbx+0Ch], rdx
0x1800349fb  mov     word ptr [rbx+14h], 0E0FFh
0x180034a01  call    cs:__imp_GetCurrentProcess
0x180034a07  mov     r8d, 16h; dwSize
0x180034a0d  mov     rdx, rbx; lpBaseAddress
0x180034a10  mov     rcx, rax; hProcess
0x180034a13  call    cs:__imp_FlushInstructionCache
0x180034a19  jmp     short loc_180034A34
0x180034a1b  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x180034a20  test    rax, rax
0x180034a23  jz      short loc_180034A34
0x180034a25  mov     rcx, [rdi+8]
0x180034a29  mov     r8, rsi
0x180034a2c  mov     rdx, rbp
0x180034a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a34  add     rsp, 28h
0x180034a38  pop     rdi
0x180034a39  pop     rsi
0x180034a3a  pop     rbp
0x180034a3b  pop     rbx
0x180034a3c  retn
```

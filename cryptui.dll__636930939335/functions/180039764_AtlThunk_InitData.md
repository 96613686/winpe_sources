# AtlThunk_InitData

- ea: `0x180039764`
- end: `0x1800397dd`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180013ce4`
- `0x1800152d0`
- `0x180023ce0`
- `0x180023dd0`
- `0x180023ec0`
- `0x1800257d0`

## callees

- `0x1800393f8`
- `0x180039764`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800397a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800397a1`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1800397b3`
- `api-ms-win-core-processthreads-l1-1-1!FlushInstructionCache` at `0x1800397b3`

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
0x180039764  test    rcx, rcx
0x180039767  jz      short locret_1800397DC
0x180039769  push    rbx
0x18003976a  push    rbp
0x18003976b  push    rsi
0x18003976c  push    rdi
0x18003976d  sub     rsp, 28h
0x180039771  mov     rbx, [rcx+8]
0x180039775  mov     rsi, r8
0x180039778  mov     rbp, rdx
0x18003977b  mov     rdi, rcx
0x18003977e  test    rbx, rbx
0x180039781  jz      short loc_1800397D4
0x180039783  cmp     dword ptr [rcx], 0
0x180039786  jz      short loc_1800397BB
0x180039788  mov     word ptr [rbx], 0B948h
0x18003978d  mov     [rbx+2], r8
0x180039791  mov     word ptr [rbx+0Ah], 0B848h
0x180039797  mov     [rbx+0Ch], rdx
0x18003979b  mov     word ptr [rbx+14h], 0E0FFh
0x1800397a1  call    cs:__imp_GetCurrentProcess
0x1800397a7  mov     r8d, 16h; dwSize
0x1800397ad  mov     rdx, rbx; lpBaseAddress
0x1800397b0  mov     rcx, rax; hProcess
0x1800397b3  call    cs:__imp_FlushInstructionCache
0x1800397b9  jmp     short loc_1800397D4
0x1800397bb  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x1800397c0  test    rax, rax
0x1800397c3  jz      short loc_1800397D4
0x1800397c5  mov     rcx, [rdi+8]
0x1800397c9  mov     r8, rsi
0x1800397cc  mov     rdx, rbp
0x1800397cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397d4  add     rsp, 28h
0x1800397d8  pop     rdi
0x1800397d9  pop     rsi
0x1800397da  pop     rbp
0x1800397db  pop     rbx
0x1800397dc  retn
```

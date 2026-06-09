# BinaryLogWriter_Core_Cleanup

- ea: `0x180029988`
- end: `0x1800299f3`
- name: `BinaryLogWriter_Core_Cleanup`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180026010`
- `0x1800260c0`
- `0x180029ab0`

## callees

- `0x18000af38`
- `0x180029988`
- `0x180029adc`
- `0x180043cd8`
- `0x180045010`

## import_xrefs

- `msvcrt!_close` at `0x180029998`
- `msvcrt!_close` at `0x180029998`
- `msvcrt!free` at `0x1800299ad`
- `msvcrt!free` at `0x1800299c5`
- `msvcrt!free` at `0x1800299ad`
- `msvcrt!free` at `0x1800299c5`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_Core_Cleanup(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rcx

  if ( *(_DWORD *)a1 != -1 )
  {
    _close(*(_DWORD *)a1);
    *(_DWORD *)a1 = -1;
    trace_BinLogWriter_ClosedLogFile(v3, v2, v4);
  }
  free(*(void **)(a1 + 48));
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
  {
    HashMap_Destroy(v5);
    free(*(void **)(a1 + 24));
  }
  v6 = *(_QWORD *)(a1 + 64);
  if ( v6 && *(_QWORD *)v6 )
    (*(void (**)(void))(*(_QWORD *)v6 + 16LL))();
  return DeleteClassesFromMOF(*(void **)(a1 + 72));
}

```

## disassembly

```asm
0x180029988  push    rbx
0x18002998a  sub     rsp, 20h
0x18002998e  cmp     dword ptr [rcx], 0FFFFFFFFh
0x180029991  mov     rbx, rcx
0x180029994  jz      short loc_1800299A9
0x180029996  mov     ecx, [rcx]; FileHandle
0x180029998  call    cs:__imp__close
0x18002999e  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800299a4  call    trace_BinLogWriter_ClosedLogFile
0x1800299a9  mov     rcx, [rbx+30h]; Block
0x1800299ad  call    cs:__imp_free
0x1800299b3  mov     rcx, [rbx+18h]
0x1800299b7  test    rcx, rcx
0x1800299ba  jz      short loc_1800299CB
0x1800299bc  call    HashMap_Destroy
0x1800299c1  mov     rcx, [rbx+18h]; Block
0x1800299c5  call    cs:__imp_free
0x1800299cb  mov     rcx, [rbx+40h]
0x1800299cf  test    rcx, rcx
0x1800299d2  jz      short loc_1800299E5
0x1800299d4  mov     rax, [rcx]
0x1800299d7  test    rax, rax
0x1800299da  jz      short loc_1800299E5
0x1800299dc  mov     rax, [rax+10h]
0x1800299e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299e5  mov     rcx, [rbx+48h]; Block
0x1800299e9  add     rsp, 20h
0x1800299ed  pop     rbx
0x1800299ee  jmp     DeleteClassesFromMOF
```

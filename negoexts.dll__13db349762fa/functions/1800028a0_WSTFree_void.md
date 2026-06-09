# WSTFree(void *)

- ea: `0x1800028a0`
- end: `0x1800028dc`
- name: `?WSTFree@@YAXPEAX@Z`
- size: `60`
- prototype: `void __fastcall(void *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011b4`
- `0x180001414`
- `0x180002694`
- `0x18000285c`
- `0x180003500`
- `0x1800070d0`
- `0x180008e60`
- `0x180009c98`
- `0x18000bf1c`
- `0x18000ea54`
- `0x180016f70`
- `0x180018c20`
- `0x180019eec`
- `0x18001a020`
- `0x18001a3b4`
- `0x18001b9b0`
- `0x18001bec0`

## callees

- `0x1800028a0`
- `0x180020010`

## pseudocode

```c
void __fastcall WSTFree(void *a1, __int64 a2)
{
  if ( a1 )
  {
    if ( *((_DWORD *)WSTGlobalBaseSSP + 52) == 1 )
      (*(void (__fastcall **)(void *, _QWORD, void *))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 392LL))(
        a1,
        *((_QWORD *)WSTGlobalBaseSSP + 30),
        a1);
    else
      (*(void (__fastcall **)(void *, __int64, void *))(*((_QWORD *)WSTGlobalBaseSSP + 31) + 8LL))(a1, a2, a1);
  }
}

```

## disassembly

```asm
0x1800028a0  mov     r8, rcx
0x1800028a3  test    rcx, rcx
0x1800028a6  jz      short locret_1800028CB
0x1800028a8  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x1800028af  cmp     dword ptr [rax+0D0h], 1
0x1800028b6  jnz     short loc_1800028CC
0x1800028b8  mov     rdx, [rax+0F0h]
0x1800028bf  mov     rax, [rdx+188h]
0x1800028c6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cb  retn
0x1800028cc  mov     rcx, [rax+0F8h]
0x1800028d3  mov     rax, [rcx+8]
0x1800028d7  mov     rcx, r8
0x1800028da  jmp     short loc_1800028C6
```

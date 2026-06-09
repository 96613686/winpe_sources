# basessp::BaseSSP::WSTFree(void *)

- ea: `0x180005960`
- end: `0x180005992`
- name: `?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012dc`
- `0x180004404`
- `0x180005bc0`
- `0x1800063e4`
- `0x18000676c`
- `0x18001d71c`
- `0x18001dc88`

## callees

- `0x180005960`
- `0x180020010`

## pseudocode

```c
void __fastcall basessp::BaseSSP::WSTFree(basessp::BaseSSP *this, void *a2)
{
  if ( a2 )
  {
    if ( *((_DWORD *)this + 52) == 1 )
      (*(void (__fastcall **)(void *))(*((_QWORD *)this + 30) + 392LL))(a2);
    else
      (*(void (__fastcall **)(void *))(*((_QWORD *)this + 31) + 8LL))(a2);
  }
}

```

## disassembly

```asm
0x180005960  test    rdx, rdx
0x180005963  jz      short locret_180005984
0x180005965  cmp     dword ptr [rcx+0D0h], 1
0x18000596c  jnz     short loc_180005985
0x18000596e  mov     rax, [rcx+0F0h]
0x180005975  mov     rax, [rax+188h]
0x18000597c  mov     rcx, rdx
0x18000597f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005984  retn
0x180005985  mov     rax, [rcx+0F8h]
0x18000598c  mov     rax, [rax+8]
0x180005990  jmp     short loc_18000597C
```

# MDIDestroyDecompression

- ea: `0x180009400`
- end: `0x180009446`
- name: `MDIDestroyDecompression`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088c0`

## callees

- `0x180009400`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MDIDestroyDecompression(__int64 a1)
{
  void (__fastcall *v2)(_QWORD); // rax

  if ( *(_DWORD *)a1 != 1128875085 )
    return 2;
  v2 = *(void (__fastcall **)(_QWORD))(a1 + 8);
  *(_DWORD *)a1 = 0;
  if ( v2 )
    v2(*(_QWORD *)(a1 + 24));
  (*(void (__fastcall **)(__int64))(a1 + 8))(a1);
  return 0;
}

```

## disassembly

```asm
0x180009400  push    rbx
0x180009402  sub     rsp, 20h
0x180009406  cmp     dword ptr [rcx], 4349444Dh
0x18000940c  mov     rbx, rcx
0x18000940f  jnz     short loc_18000943F
0x180009411  mov     rax, [rcx+8]
0x180009415  mov     dword ptr [rcx], 0
0x18000941b  test    rax, rax
0x18000941e  jnz     short loc_180009434
0x180009420  mov     rax, [rbx+8]
0x180009424  mov     rcx, rbx
0x180009427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000942c  xor     eax, eax
0x18000942e  add     rsp, 20h
0x180009432  pop     rbx
0x180009433  retn
0x180009434  mov     rcx, [rcx+18h]
0x180009438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943d  jmp     short loc_180009420
0x18000943f  mov     eax, 2
0x180009444  jmp     short loc_18000942E
```

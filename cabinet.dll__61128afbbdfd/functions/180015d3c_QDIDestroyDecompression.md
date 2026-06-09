# QDIDestroyDecompression

- ea: `0x180015d3c`
- end: `0x180015d7e`
- name: `QDIDestroyDecompression`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088c0`

## callees

- `0x180015d3c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall QDIDestroyDecompression(__int64 a1)
{
  void (__fastcall *v3)(__int64); // rax

  if ( *(_DWORD *)a1 != 1128875089 )
    return 2;
  (*(void (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 344));
  v3 = *(void (__fastcall **)(__int64))(a1 + 16);
  *(_DWORD *)a1 = 0;
  v3(a1);
  return 0;
}

```

## disassembly

```asm
0x180015d3c  push    rbx
0x180015d3e  sub     rsp, 20h
0x180015d42  cmp     dword ptr [rcx], 43494451h
0x180015d48  mov     rbx, rcx
0x180015d4b  jz      short loc_180015D54
0x180015d4d  mov     eax, 2
0x180015d52  jmp     short loc_180015D78
0x180015d54  mov     rcx, [rcx+158h]
0x180015d5b  mov     rax, [rbx+10h]
0x180015d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d64  mov     rax, [rbx+10h]
0x180015d68  mov     rcx, rbx
0x180015d6b  mov     dword ptr [rbx], 0
0x180015d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d76  xor     eax, eax
0x180015d78  add     rsp, 20h
0x180015d7c  pop     rbx
0x180015d7d  retn
```

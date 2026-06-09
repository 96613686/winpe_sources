# LCIDestroyCompression

- ea: `0x180016db8`
- end: `0x180016e00`
- name: `LCIDestroyCompression`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014088`

## callees

- `0x180016db8`
- `0x180017118`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall LCIDestroyCompression(__int64 a1)
{
  void (__fastcall *v3)(__int64); // rax

  if ( *(_DWORD *)a1 != 1128874828 )
    return 2;
  comp_free_compress_memory(*(_QWORD *)(a1 + 32));
  (*(void (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 32));
  v3 = *(void (__fastcall **)(__int64))(a1 + 16);
  *(_DWORD *)a1 = 0;
  v3(a1);
  return 0;
}

```

## disassembly

```asm
0x180016db8  push    rbx
0x180016dba  sub     rsp, 20h
0x180016dbe  cmp     dword ptr [rcx], 4349434Ch
0x180016dc4  mov     rbx, rcx
0x180016dc7  jz      short loc_180016DD0
0x180016dc9  mov     eax, 2
0x180016dce  jmp     short loc_180016DFA
0x180016dd0  mov     rcx, [rcx+20h]
0x180016dd4  call    comp_free_compress_memory
0x180016dd9  mov     rcx, [rbx+20h]
0x180016ddd  mov     rax, [rbx+10h]
0x180016de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016de6  mov     rax, [rbx+10h]
0x180016dea  mov     rcx, rbx
0x180016ded  mov     dword ptr [rbx], 0
0x180016df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df8  xor     eax, eax
0x180016dfa  add     rsp, 20h
0x180016dfe  pop     rbx
0x180016dff  retn
```

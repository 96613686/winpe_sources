# CTempBuffer<char,256>::~CTempBuffer<char,256>(void)

- ea: `0x140003b80`
- end: `0x140003b9a`
- name: `??1?$CTempBuffer@D$0BAA@@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400011e4`

## callees

- `0x140003b80`
- `0x140003c48`

## pseudocode

```c
void __fastcall CTempBuffer<char,256>::~CTempBuffer<char,256>(__int64 a1)
{
  if ( *(int *)(a1 + 8) > 256 )
    operator delete(*(void **)a1);
}

```

## disassembly

```asm
0x140003b80  sub     rsp, 28h
0x140003b84  cmp     dword ptr [rcx+8], 100h
0x140003b8b  jle     short loc_140003B95
0x140003b8d  mov     rcx, [rcx]; void *
0x140003b90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003b95  add     rsp, 28h
0x140003b99  retn
```

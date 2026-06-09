# CTempBuffer<char,512>::~CTempBuffer<char,512>(void)

- ea: `0x140003ba0`
- end: `0x140003bba`
- name: `??1?$CTempBuffer@D$0CAA@@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000580c`
- `0x1400078f0`

## callees

- `0x140003ba0`
- `0x140003c48`

## pseudocode

```c
void __fastcall CTempBuffer<char,512>::~CTempBuffer<char,512>(__int64 a1)
{
  if ( *(int *)(a1 + 8) > 512 )
    operator delete(*(void **)a1);
}

```

## disassembly

```asm
0x140003ba0  sub     rsp, 28h
0x140003ba4  cmp     dword ptr [rcx+8], 200h
0x140003bab  jle     short loc_140003BB5
0x140003bad  mov     rcx, [rcx]; void *
0x140003bb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003bb5  add     rsp, 28h
0x140003bb9  retn
```

# CTempBuffer<ushort,260>::~CTempBuffer<ushort,260>(void)

- ea: `0x140003bc0`
- end: `0x140003bda`
- name: `??1?$CTempBuffer@G$0BAE@@@QEAA@XZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400011e4`

## callees

- `0x140003bc0`
- `0x140003c48`

## pseudocode

```c
void __fastcall CTempBuffer<unsigned short,260>::~CTempBuffer<unsigned short,260>(__int64 a1)
{
  if ( *(int *)(a1 + 8) > 260 )
    operator delete(*(void **)a1);
}

```

## disassembly

```asm
0x140003bc0  sub     rsp, 28h
0x140003bc4  cmp     dword ptr [rcx+8], 104h
0x140003bcb  jle     short loc_140003BD5
0x140003bcd  mov     rcx, [rcx]; void *
0x140003bd0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003bd5  add     rsp, 28h
0x140003bd9  retn
```

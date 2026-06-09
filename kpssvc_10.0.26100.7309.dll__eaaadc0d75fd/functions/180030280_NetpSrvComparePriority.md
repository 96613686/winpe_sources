# NetpSrvComparePriority

- ea: `0x180030280`
- end: `0x1800302a1`
- name: `NetpSrvComparePriority`
- size: `33`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall NetpSrvComparePriority(const void *a1, const void *a2)
{
  return (*(_WORD *)(*(_QWORD *)a1 + 40LL) > *(_WORD *)(*(_QWORD *)a2 + 40LL))
       - (unsigned int)(*(_WORD *)(*(_QWORD *)a1 + 40LL) < *(_WORD *)(*(_QWORD *)a2 + 40LL));
}

```

## disassembly

```asm
0x180030280  mov     rax, [rcx]
0x180030283  movzx   ecx, word ptr [rax+28h]
0x180030287  mov     rax, [rdx]
0x18003028a  xor     edx, edx
0x18003028c  mov     r8d, edx
0x18003028f  cmp     cx, [rax+28h]
0x180030293  setnbe  r8b
0x180030297  setb    dl
0x18003029a  sub     r8d, edx
0x18003029d  mov     eax, r8d
0x1800302a0  retn
```

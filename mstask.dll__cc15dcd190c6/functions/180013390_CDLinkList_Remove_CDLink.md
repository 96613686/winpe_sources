# CDLinkList::Remove(CDLink *)

- ea: `0x180013390`
- end: `0x1800133ba`
- name: `?Remove@CDLinkList@@UEAAXPEAVCDLink@@@Z`
- size: `42`
- prototype: `void(CDLinkList *__hidden this, struct CDLink *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800133c0`

## callees

- `0x180013390`
- `0x180019914`

## pseudocode

```c
void __fastcall CDLinkList::Remove(CDLinkList *this, struct CDLink *a2)
{
  struct CDLink *v2; // rax
  struct CDLink *v3; // rax

  v2 = (struct CDLink *)*((_QWORD *)this + 1);
  if ( a2 == v2 )
    *((_QWORD *)this + 1) = *((_QWORD *)v2 + 1);
  v3 = (struct CDLink *)*((_QWORD *)this + 2);
  if ( a2 == v3 )
    *((_QWORD *)this + 2) = *((_QWORD *)v3 + 2);
  CDLink::UnLink(a2);
}

```

## disassembly

```asm
0x180013390  mov     rax, [rcx+8]
0x180013394  cmp     rdx, rax
0x180013397  jnz     short loc_1800133A1
0x180013399  mov     rax, [rax+8]
0x18001339d  mov     [rcx+8], rax
0x1800133a1  mov     rax, [rcx+10h]
0x1800133a5  cmp     rdx, rax
0x1800133a8  jnz     short loc_1800133B2
0x1800133aa  mov     rax, [rax+10h]
0x1800133ae  mov     [rcx+10h], rax
0x1800133b2  mov     rcx, rdx; this
0x1800133b5  jmp     ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
```

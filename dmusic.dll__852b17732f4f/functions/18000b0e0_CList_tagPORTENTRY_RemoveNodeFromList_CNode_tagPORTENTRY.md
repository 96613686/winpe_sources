# CList<tagPORTENTRY *>::RemoveNodeFromList(CNode<tagPORTENTRY *> *)

- ea: `0x18000b0e0`
- end: `0x18000b13d`
- name: `?RemoveNodeFromList@?$CList@PEAUtagPORTENTRY@@@@UEAAXPEAV?$CNode@PEAUtagPORTENTRY@@@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800012c4`
- `0x18000b0e0`

## pseudocode

```c
void __fastcall CList<tagPORTENTRY *>::RemoveNodeFromList(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdx
  _QWORD *v5; // rcx

  v4 = *a2;
  v5 = a2 + 1;
  if ( v4 )
    *(_QWORD *)(v4 + 8) = *v5;
  if ( *v5 )
    *(_QWORD *)*v5 = *a2;
  if ( a2 == *(__int64 **)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = *v5;
  if ( a2 == *(__int64 **)(a1 + 16) )
    *(_QWORD *)(a1 + 16) = *a2;
  operator delete(a2);
  --*(_DWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x18000b0e0  push    rbx
0x18000b0e2  sub     rsp, 20h
0x18000b0e6  mov     r8, rdx
0x18000b0e9  mov     rbx, rcx
0x18000b0ec  mov     rdx, [rdx]
0x18000b0ef  lea     rcx, [r8+8]
0x18000b0f3  test    rdx, rdx
0x18000b0f6  jz      short loc_18000B0FF
0x18000b0f8  mov     rax, [rcx]
0x18000b0fb  mov     [rdx+8], rax
0x18000b0ff  mov     rdx, [rcx]
0x18000b102  test    rdx, rdx
0x18000b105  jz      short loc_18000B10D
0x18000b107  mov     rax, [r8]
0x18000b10a  mov     [rdx], rax
0x18000b10d  cmp     r8, [rbx+8]
0x18000b111  jnz     short loc_18000B11A
0x18000b113  mov     rax, [rcx]
0x18000b116  mov     [rbx+8], rax
0x18000b11a  cmp     r8, [rbx+10h]
0x18000b11e  jnz     short loc_18000B127
0x18000b120  mov     rax, [r8]
0x18000b123  mov     [rbx+10h], rax
0x18000b127  mov     edx, 18h; unsigned __int64
0x18000b12c  mov     rcx, r8; void *
0x18000b12f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b134  dec     dword ptr [rbx+18h]
0x18000b137  add     rsp, 20h
0x18000b13b  pop     rbx
0x18000b13c  retn
```

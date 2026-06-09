# CDLink::UnLink(void)

- ea: `0x180019914`
- end: `0x180019948`
- name: `?UnLink@CDLink@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(CDLink *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009e30`
- `0x180013390`
- `0x180019678`

## callees

- `0x180019914`

## pseudocode

```c
void __fastcall CDLink::UnLink(CDLink *this)
{
  __int64 v1; // r8
  char *v2; // rdx

  v1 = *((_QWORD *)this + 1);
  v2 = (char *)this + 16;
  if ( v1 )
    *(_QWORD *)(v1 + 16) = *(_QWORD *)v2;
  if ( *(_QWORD *)v2 )
    *(_QWORD *)(*(_QWORD *)v2 + 8LL) = *((_QWORD *)this + 1);
  *(_QWORD *)v2 = 0;
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180019914  mov     r8, [rcx+8]
0x180019918  lea     rdx, [rcx+10h]
0x18001991c  test    r8, r8
0x18001991f  jz      short loc_180019928
0x180019921  mov     rax, [rdx]
0x180019924  mov     [r8+10h], rax
0x180019928  mov     r8, [rdx]
0x18001992b  test    r8, r8
0x18001992e  jz      short loc_180019938
0x180019930  mov     rax, [rcx+8]
0x180019934  mov     [r8+8], rax
0x180019938  mov     qword ptr [rdx], 0
0x18001993f  mov     qword ptr [rcx+8], 0
0x180019947  retn
```

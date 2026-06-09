# CDLink::UnLink(void)

- ea: `0x180004f68`
- end: `0x180004f9c`
- name: `?UnLink@CDLink@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(CDLink *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800018a0`
- `0x180002740`
- `0x1800046a8`
- `0x180005de0`
- `0x1800078a4`
- `0x180008698`
- `0x18001b910`
- `0x18001be20`
- `0x18001c48c`
- `0x180023500`
- `0x180023590`
- `0x180023620`
- `0x1800236b0`

## callees

- `0x180004f68`

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
0x180004f68  mov     r8, [rcx+8]
0x180004f6c  lea     rdx, [rcx+10h]
0x180004f70  test    r8, r8
0x180004f73  jz      short loc_180004F7C
0x180004f75  mov     rax, [rdx]
0x180004f78  mov     [r8+10h], rax
0x180004f7c  mov     r8, [rdx]
0x180004f7f  test    r8, r8
0x180004f82  jz      short loc_180004F8C
0x180004f84  mov     rax, [rcx+8]
0x180004f88  mov     [r8+8], rax
0x180004f8c  mov     qword ptr [rdx], 0
0x180004f93  mov     qword ptr [rcx+8], 0
0x180004f9b  retn
```

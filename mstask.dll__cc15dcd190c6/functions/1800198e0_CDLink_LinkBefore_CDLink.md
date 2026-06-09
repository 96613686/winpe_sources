# CDLink::LinkBefore(CDLink *)

- ea: `0x1800198e0`
- end: `0x18001990c`
- name: `?LinkBefore@CDLink@@QEAAXPEAV1@@Z`
- size: `44`
- prototype: `void __fastcall(CDLink *__hidden this, struct CDLink *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f40`

## callees

- `0x1800198e0`

## pseudocode

```c
void __fastcall CDLink::LinkBefore(CDLink *this, struct CDLink *a2)
{
  __int64 v2; // rax

  *((_QWORD *)this + 1) = a2;
  if ( a2 )
  {
    *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 2) = this;
    v2 = *((_QWORD *)this + 2);
    if ( v2 )
      *(_QWORD *)(v2 + 8) = this;
  }
  else
  {
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800198e0  mov     [rcx+8], rdx
0x1800198e4  test    rdx, rdx
0x1800198e7  jz      short loc_180019903
0x1800198e9  mov     rax, [rdx+10h]
0x1800198ed  mov     [rcx+10h], rax
0x1800198f1  mov     [rdx+10h], rcx
0x1800198f5  mov     rax, [rcx+10h]
0x1800198f9  test    rax, rax
0x1800198fc  jz      short locret_18001990B
0x1800198fe  mov     [rax+8], rcx
0x180019902  retn
0x180019903  mov     qword ptr [rcx+10h], 0
0x18001990b  retn
```

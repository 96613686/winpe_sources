# CDLink::LinkAfter(CDLink *)

- ea: `0x1800198ac`
- end: `0x1800198d8`
- name: `?LinkAfter@CDLink@@QEAAXPEAV1@@Z`
- size: `44`
- prototype: `void __fastcall(CDLink *__hidden this, struct CDLink *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f40`

## callees

- `0x1800198ac`

## pseudocode

```c
void __fastcall CDLink::LinkAfter(CDLink *this, struct CDLink *a2)
{
  __int64 v2; // rax

  *((_QWORD *)this + 2) = a2;
  if ( a2 )
  {
    *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
    *((_QWORD *)a2 + 1) = this;
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
      *(_QWORD *)(v2 + 16) = this;
  }
  else
  {
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1800198ac  mov     [rcx+10h], rdx
0x1800198b0  test    rdx, rdx
0x1800198b3  jz      short loc_1800198CF
0x1800198b5  mov     rax, [rdx+8]
0x1800198b9  mov     [rcx+8], rax
0x1800198bd  mov     [rdx+8], rcx
0x1800198c1  mov     rax, [rcx+8]
0x1800198c5  test    rax, rax
0x1800198c8  jz      short locret_1800198D7
0x1800198ca  mov     [rax+10h], rcx
0x1800198ce  retn
0x1800198cf  mov     qword ptr [rcx+8], 0
0x1800198d7  retn
```

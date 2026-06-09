# CMemFile::Write(void const *,uint)

- ea: `0x18000990c`
- end: `0x180009966`
- name: `?Write@CMemFile@@QEAAIPEBXI@Z`
- size: `90`
- prototype: `unsigned int __fastcall(CMemFile *__hidden this, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e50`
- `0x1800050d0`

## callees

- `0x18000990c`
- `0x180012a8c`

## import_xrefs

- `KERNEL32!_lwrite` at `0x180009955`
- `KERNEL32!_lwrite` at `0x180009955`

## pseudocode

```c
UINT __fastcall CMemFile::Write(CMemFile *this, const CHAR *a2, UINT a3)
{
  _QWORD *v3; // rax
  UINT v4; // edi
  unsigned int v7; // ecx

  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v4 = a3;
  if ( !v3 )
    return _lwrite(*(_DWORD *)this, a2, a3);
  if ( !*v3 )
    return -1;
  v7 = *((_DWORD *)this + 4) - *((_DWORD *)this + 5);
  if ( a3 > v7 )
    v4 = v7;
  memmove_0((void *)(*v3 + *((int *)this + 5)), a2, v4);
  *((_DWORD *)this + 5) += v4;
  return v4;
}

```

## disassembly

```asm
0x18000990c  mov     [rsp+arg_0], rbx
0x180009911  push    rdi
0x180009912  sub     rsp, 20h
0x180009916  mov     rax, [rcx+8]
0x18000991a  mov     edi, r8d
0x18000991d  mov     rbx, rcx
0x180009920  test    rax, rax
0x180009923  jz      short loc_180009953
0x180009925  mov     r9, [rax]
0x180009928  test    r9, r9
0x18000992b  jnz     short loc_180009932
0x18000992d  or      eax, 0FFFFFFFFh
0x180009930  jmp     short loc_18000995B
0x180009932  mov     ecx, [rcx+10h]
0x180009935  sub     ecx, [rbx+14h]
0x180009938  cmp     edi, ecx
0x18000993a  cmova   edi, ecx
0x18000993d  movsxd  rcx, dword ptr [rbx+14h]
0x180009941  add     rcx, r9; void *
0x180009944  mov     r8d, edi; Size
0x180009947  call    memmove_0
0x18000994c  add     [rbx+14h], edi
0x18000994f  mov     eax, edi
0x180009951  jmp     short loc_18000995B
0x180009953  mov     ecx, [rcx]; hFile
0x180009955  call    cs:__imp__lwrite
0x18000995b  mov     rbx, [rsp+28h+arg_0]
0x180009960  add     rsp, 20h
0x180009964  pop     rdi
0x180009965  retn
```

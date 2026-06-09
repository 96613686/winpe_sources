# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1800170f0`
- end: `0x180017149`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `89`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x1800170f0`
- `0x180019010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180017127`
- `KERNEL32!LocalFree` at `0x180017127`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800170f0  mov     [rsp+arg_0], rbx
0x1800170f5  push    rdi
0x1800170f6  sub     rsp, 20h
0x1800170fa  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180017101  mov     rbx, rcx
0x180017104  mov     [rcx], rax
0x180017107  mov     edi, edx
0x180017109  mov     rcx, [rcx+10h]
0x18001710d  test    rcx, rcx
0x180017110  jz      short loc_18001711E
0x180017112  mov     rax, [rcx]
0x180017115  mov     rax, [rax+10h]
0x180017119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001711e  mov     rcx, [rbx+18h]; hMem
0x180017122  test    rcx, rcx
0x180017125  jz      short loc_18001712D
0x180017127  call    cs:__imp_LocalFree
0x18001712d  test    dil, 1
0x180017131  jz      short loc_18001713B
0x180017133  mov     rcx, rbx; Block
0x180017136  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001713b  mov     rax, rbx
0x18001713e  mov     rbx, [rsp+28h+arg_0]
0x180017143  add     rsp, 20h
0x180017147  pop     rdi
0x180017148  retn
```

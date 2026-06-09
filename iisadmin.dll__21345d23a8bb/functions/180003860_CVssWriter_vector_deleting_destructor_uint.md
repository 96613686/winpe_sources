# CVssWriter::`vector deleting destructor'(uint)

- ea: `0x180003860`
- end: `0x1800038c2`
- name: `??_ECVssWriter@@UEAAPEAXI@Z`
- size: `98`
- prototype: `void *__fastcall(CVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003860`
- `0x180005010`

## pseudocode

```c
CVssWriter *__fastcall CVssWriter::`vector deleting destructor'(CVssWriter *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CVssWriter::`vftable';
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003860  mov     [rsp+arg_0], rbx
0x180003865  push    rdi
0x180003866  sub     rsp, 20h
0x18000386a  lea     rax, ??_7CVssWriter@@6B@; const CVssWriter::`vftable'
0x180003871  mov     rbx, rcx
0x180003874  mov     [rcx], rax
0x180003877  mov     edi, edx
0x180003879  mov     rcx, [rcx+8]
0x18000387d  test    rcx, rcx
0x180003880  jz      short loc_1800038A6
0x180003882  mov     rax, [rcx]
0x180003885  mov     rax, [rax+30h]
0x180003889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388e  mov     rcx, [rbx+8]
0x180003892  mov     rax, [rcx]
0x180003895  mov     rax, [rax+10h]
0x180003899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389e  mov     qword ptr [rbx+8], 0
0x1800038a6  test    dil, 1
0x1800038aa  jz      short loc_1800038B4
0x1800038ac  mov     rcx, rbx; Block
0x1800038af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038b4  mov     rax, rbx
0x1800038b7  mov     rbx, [rsp+28h+arg_0]
0x1800038bc  add     rsp, 20h
0x1800038c0  pop     rdi
0x1800038c1  retn
```

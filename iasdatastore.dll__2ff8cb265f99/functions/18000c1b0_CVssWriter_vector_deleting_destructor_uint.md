# CVssWriter::`vector deleting destructor'(uint)

- ea: `0x18000c1b0`
- end: `0x18000c213`
- name: `??_ECVssWriter@@UEAAPEAXI@Z`
- size: `99`
- prototype: `void *__fastcall(CVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c1b0`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x18000c1ff`
- `msvcrt!free` at `0x18000c1ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000c1b0  mov     [rsp+arg_0], rbx
0x18000c1b5  push    rdi
0x18000c1b6  sub     rsp, 20h
0x18000c1ba  mov     edi, edx
0x18000c1bc  mov     rbx, rcx
0x18000c1bf  lea     rax, ??_7CVssWriter@@6B@; const CVssWriter::`vftable'
0x18000c1c6  mov     [rcx], rax
0x18000c1c9  mov     rcx, [rcx+8]
0x18000c1cd  test    rcx, rcx
0x18000c1d0  jz      short loc_18000C1F6
0x18000c1d2  mov     rax, [rcx]
0x18000c1d5  mov     rax, [rax+30h]
0x18000c1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1de  mov     rcx, [rbx+8]
0x18000c1e2  mov     rax, [rcx]
0x18000c1e5  mov     rax, [rax+10h]
0x18000c1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ee  mov     qword ptr [rbx+8], 0
0x18000c1f6  test    dil, 1
0x18000c1fa  jz      short loc_18000C205
0x18000c1fc  mov     rcx, rbx; Block
0x18000c1ff  call    cs:__imp_free
0x18000c205  mov     rax, rbx
0x18000c208  mov     rbx, [rsp+28h+arg_0]
0x18000c20d  add     rsp, 20h
0x18000c211  pop     rdi
0x18000c212  retn
```

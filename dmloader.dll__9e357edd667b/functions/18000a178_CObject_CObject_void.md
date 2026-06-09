# CObject::~CObject(void)

- ea: `0x18000a178`
- end: `0x18000a1dc`
- name: `??1CObject@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CObject *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007fcc`
- `0x180008e90`
- `0x18000a310`
- `0x18000aa70`
- `0x18000b9b0`
- `0x18000c5d8`

## callees

- `0x1800019a0`
- `0x18000a10c`
- `0x18000a178`
- `0x180010010`

## pseudocode

```c
void __fastcall CObject::~CObject(CObject *this, unsigned __int64 a2)
{
  __int64 v3; // rcx
  void **v4; // rdi

  v3 = *((_QWORD *)this + 23);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 23) = 0;
  }
  v4 = (void **)*((_QWORD *)this + 25);
  if ( v4 )
  {
    operator delete(*v4);
    operator delete(v4);
  }
  CDescriptor::~CDescriptor((CObject *)((char *)this + 8), a2);
}

```

## disassembly

```asm
0x18000a178  mov     [rsp+arg_0], rbx
0x18000a17d  push    rdi
0x18000a17e  sub     rsp, 20h
0x18000a182  mov     rbx, rcx
0x18000a185  mov     rcx, [rcx+0B8h]
0x18000a18c  test    rcx, rcx
0x18000a18f  jz      short loc_18000A1A8
0x18000a191  mov     rax, [rcx]
0x18000a194  mov     rax, [rax+10h]
0x18000a198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a19d  mov     qword ptr [rbx+0B8h], 0
0x18000a1a8  mov     rdi, [rbx+0C8h]
0x18000a1af  test    rdi, rdi
0x18000a1b2  jz      short loc_18000A1C9
0x18000a1b4  mov     rcx, [rdi]; void *
0x18000a1b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a1bc  mov     edx, 10h; unsigned __int64
0x18000a1c1  mov     rcx, rdi; void *
0x18000a1c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a1c9  lea     rcx, [rbx+8]; this
0x18000a1cd  mov     rbx, [rsp+28h+arg_0]
0x18000a1d2  add     rsp, 20h
0x18000a1d6  pop     rdi
0x18000a1d7  jmp     ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
```

# CLightRecCache::~CLightRecCache(void)

- ea: `0x180014c24`
- end: `0x180014c5a`
- name: `??1CLightRecCache@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CLightRecCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b8a0`

## callees

- `0x1800034b4`
- `0x180014c24`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLightRecCache::~CLightRecCache(void **this)
{
  char *v1; // rcx
  char *v2; // rbx

  v1 = (char *)*this;
  if ( v1 )
  {
    v2 = v1 - 8;
    `eh vector destructor iterator'(v1, 0x1Cu, *((_QWORD *)v1 - 1), guard_check_icall_nop);
    operator delete[](v2);
  }
}

```

## disassembly

```asm
0x180014c24  push    rbx
0x180014c26  sub     rsp, 20h
0x180014c2a  mov     rcx, [rcx]; void *
0x180014c2d  test    rcx, rcx
0x180014c30  jz      short loc_180014C54
0x180014c32  lea     rbx, [rcx-8]
0x180014c36  lea     r9, _guard_check_icall_nop; void (*)(void *)
0x180014c3d  mov     r8, [rbx]; unsigned __int64
0x180014c40  mov     edx, 1Ch; unsigned __int64
0x180014c45  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180014c4a  mov     rcx, rbx
0x180014c4d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014c53  nop
0x180014c54  add     rsp, 20h
0x180014c58  pop     rbx
0x180014c59  retn
```

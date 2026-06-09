# ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)

- ea: `0x18000272c`
- end: `0x18000275b`
- name: `??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c9a0`
- `0x18000fae0`

## callees

- `0x18000178c`
- `0x180001d38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(
        ATL::CComTypeInfoHolder::stringdispid *this)
{
  char *v1; // rbx

  v1 = (char *)this - 8;
  `eh vector destructor iterator'(
    this,
    0x10u,
    *((_QWORD *)this - 1),
    (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::~stringdispid);
  operator delete(v1);
  return v1;
}

```

## disassembly

```asm
0x18000272c  push    rbx
0x18000272e  sub     rsp, 20h
0x180002732  lea     rbx, [rcx-8]
0x180002736  lea     r9, ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000273d  mov     r8, [rbx]; unsigned __int64
0x180002740  mov     edx, 10h; unsigned __int64
0x180002745  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000274a  mov     rcx, rbx; Block
0x18000274d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002752  mov     rax, rbx
0x180002755  add     rsp, 20h
0x180002759  pop     rbx
0x18000275a  retn
```

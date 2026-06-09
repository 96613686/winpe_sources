# ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)

- ea: `0x180002d84`
- end: `0x180002db6`
- name: `??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z`
- size: `50`
- prototype: `char *__fastcall(ATL::CComTypeInfoHolder::stringdispid *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de20`
- `0x18000f06c`

## callees

- `0x180001768`

## import_xrefs

- `msvcrt!free` at `0x180002da6`
- `msvcrt!free` at `0x180002da6`

## pseudocode

```c
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
  free(v1);
  return v1;
}

```

## disassembly

```asm
0x180002d84  push    rbx
0x180002d86  sub     rsp, 20h
0x180002d8a  lea     rbx, [rcx-8]
0x180002d8e  lea     r9, ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180002d95  mov     r8, [rbx]; unsigned __int64
0x180002d98  mov     edx, 10h; unsigned __int64
0x180002d9d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180002da2  nop
0x180002da3  mov     rcx, rbx; Block
0x180002da6  call    cs:__imp_free
0x180002dac  nop
0x180002dad  mov     rax, rbx
0x180002db0  add     rsp, 20h
0x180002db4  pop     rbx
0x180002db5  retn
```

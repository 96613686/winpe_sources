# _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180021aac`
- end: `0x180021acf`
- name: `??_G_SCRUB_DIRECTORY_ENTRY@@QEAAPEAXI@Z`
- size: `35`
- prototype: `_SCRUB_DIRECTORY_ENTRY *__fastcall(_SCRUB_DIRECTORY_ENTRY *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002138c`
- `0x180021480`
- `0x180024b24`
- `0x180027798`
- `0x180028360`
- `0x1800299f0`

## callees

- `0x180001bc4`
- `0x180003134`

## pseudocode

```c
_SCRUB_DIRECTORY_ENTRY *__fastcall _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'(_SCRUB_DIRECTORY_ENTRY *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 5);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180021aac  push    rbx
0x180021aae  sub     rsp, 20h
0x180021ab2  mov     rbx, rcx
0x180021ab5  add     rcx, 28h ; '('
0x180021ab9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021abe  mov     rcx, rbx; Block
0x180021ac1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021ac6  mov     rax, rbx
0x180021ac9  add     rsp, 20h
0x180021acd  pop     rbx
0x180021ace  retn
```

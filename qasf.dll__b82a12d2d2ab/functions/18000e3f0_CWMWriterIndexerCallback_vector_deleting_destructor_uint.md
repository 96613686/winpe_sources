# CWMWriterIndexerCallback::`vector deleting destructor'(uint)

- ea: `0x18000e3f0`
- end: `0x18000e418`
- name: `??_ECWMWriterIndexerCallback@@UEAAPEAXI@Z`
- size: `40`
- prototype: `void *__fastcall(CWMWriterIndexerCallback *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x18000e3f0`

## pseudocode

```c
CWMWriterIndexerCallback *__fastcall CWMWriterIndexerCallback::`vector deleting destructor'(
        CWMWriterIndexerCallback *this,
        char a2)
{
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e3f0  push    rbx
0x18000e3f2  sub     rsp, 20h
0x18000e3f6  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000e3fd  mov     rbx, rcx
0x18000e400  test    dl, 1
0x18000e403  jz      short loc_18000E40F
0x18000e405  mov     edx, 28h ; '('; unsigned __int64
0x18000e40a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e40f  mov     rax, rbx
0x18000e412  add     rsp, 20h
0x18000e416  pop     rbx
0x18000e417  retn
```

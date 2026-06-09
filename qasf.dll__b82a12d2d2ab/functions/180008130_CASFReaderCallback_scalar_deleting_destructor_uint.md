# CASFReaderCallback::`scalar deleting destructor'(uint)

- ea: `0x180008130`
- end: `0x180008158`
- name: `??_GCASFReaderCallback@@UEAAPEAXI@Z`
- size: `40`
- prototype: `void *__fastcall(CASFReaderCallback *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180008130`

## pseudocode

```c
CASFReaderCallback *__fastcall CASFReaderCallback::`scalar deleting destructor'(CASFReaderCallback *this, char a2)
{
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008130  push    rbx
0x180008132  sub     rsp, 20h
0x180008136  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000813d  mov     rbx, rcx
0x180008140  test    dl, 1
0x180008143  jz      short loc_18000814F
0x180008145  mov     edx, 30h ; '0'; unsigned __int64
0x18000814a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000814f  mov     rax, rbx
0x180008152  add     rsp, 20h
0x180008156  pop     rbx
0x180008157  retn
```

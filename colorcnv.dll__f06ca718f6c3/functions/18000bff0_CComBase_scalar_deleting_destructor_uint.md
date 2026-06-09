# CComBase::`scalar deleting destructor'(uint)

- ea: `0x18000bff0`
- end: `0x18000c022`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a6d0`
- `0x18000bff0`

## pseudocode

```c
CComBase *__fastcall CComBase::`scalar deleting destructor'(CComBase *this, char a2)
{
  *(_QWORD *)this = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000bff0  push    rbx
0x18000bff2  sub     rsp, 20h
0x18000bff6  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18000bffd  mov     rbx, rcx
0x18000c000  mov     [rcx], rax
0x18000c003  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000c00a  test    dl, 1
0x18000c00d  jz      short loc_18000C019
0x18000c00f  mov     edx, 18h; unsigned __int64
0x18000c014  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c019  mov     rax, rbx
0x18000c01c  add     rsp, 20h
0x18000c020  pop     rbx
0x18000c021  retn
```

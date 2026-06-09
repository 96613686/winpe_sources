# FTPHOST_CLASS::Release(void)

- ea: `0x1800039d0`
- end: `0x180003a10`
- name: `?Release@FTPHOST_CLASS@@UEAAKXZ`
- size: `64`
- prototype: `unsigned int __fastcall(FTPHOST_CLASS *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800033a8`
- `0x1800039d0`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::Release(FTPHOST_CLASS *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    FTPHOST_CLASS::~FTPHOST_CLASS(this);
    operator delete(this);
  }
  _InterlockedDecrement(&g_dwRefCount);
  return v2;
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_0], rbx
0x1800039d5  push    rdi
0x1800039d6  sub     rsp, 20h
0x1800039da  mov     rbx, rcx
0x1800039dd  or      edi, 0FFFFFFFFh
0x1800039e0  lock xadd [rcx+8], edi
0x1800039e5  sub     edi, 1
0x1800039e8  jnz     short loc_1800039FC
0x1800039ea  test    rcx, rcx
0x1800039ed  jz      short loc_1800039FC
0x1800039ef  call    ??1FTPHOST_CLASS@@AEAA@XZ; FTPHOST_CLASS::~FTPHOST_CLASS(void)
0x1800039f4  mov     rcx, rbx; Block
0x1800039f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800039fc  lock dec cs:?g_dwRefCount@@3JC; long volatile g_dwRefCount
0x180003a03  mov     eax, edi
0x180003a05  mov     rbx, [rsp+28h+arg_0]
0x180003a0a  add     rsp, 20h
0x180003a0e  pop     rdi
0x180003a0f  retn
```

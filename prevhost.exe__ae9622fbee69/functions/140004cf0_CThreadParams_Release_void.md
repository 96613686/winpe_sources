# CThreadParams::Release(void)

- ea: `0x140004cf0`
- end: `0x140004d2c`
- name: `?Release@CThreadParams@@UEAAKXZ`
- size: `60`
- prototype: `__int64 __fastcall(CThreadParams *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001728`
- `0x1400029c4`
- `0x140004cf0`

## pseudocode

```c
__int64 __fastcall CThreadParams::Release(CThreadParams *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CThreadParams::~CThreadParams(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x140004cf0  mov     [rsp+arg_0], rbx
0x140004cf5  push    rdi
0x140004cf6  sub     rsp, 20h
0x140004cfa  mov     rbx, rcx
0x140004cfd  or      edi, 0FFFFFFFFh
0x140004d00  lock xadd [rcx+8], edi
0x140004d05  sub     edi, 1
0x140004d08  jnz     short loc_140004D1F
0x140004d0a  test    rcx, rcx
0x140004d0d  jz      short loc_140004D1F
0x140004d0f  call    ??1CThreadParams@@AEAA@XZ; CThreadParams::~CThreadParams(void)
0x140004d14  lea     edx, [rdi+50h]
0x140004d17  mov     rcx, rbx; Block
0x140004d1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004d1f  mov     rbx, [rsp+28h+arg_0]
0x140004d24  mov     eax, edi
0x140004d26  add     rsp, 20h
0x140004d2a  pop     rdi
0x140004d2b  retn
```

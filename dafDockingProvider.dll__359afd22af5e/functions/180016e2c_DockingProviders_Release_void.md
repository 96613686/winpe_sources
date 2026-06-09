# DockingProviders::Release(void)

- ea: `0x180016e2c`
- end: `0x180016e65`
- name: `?Release@DockingProviders@@QEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(DockingProviders *this)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800086f0`
- `0x180008738`
- `0x18000c4cc`
- `0x18000cc5c`
- `0x18000ccdc`
- `0x18000d230`
- `0x18000d4f4`
- `0x18001134c`
- `0x180018420`
- `0x18001a8f0`

## callees

- `0x1800014d0`
- `0x180013dc8`
- `0x180016e2c`

## pseudocode

```c
__int64 __fastcall DockingProviders::Release(DockingProviders *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    DockingProviders::~DockingProviders(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180016e2c  mov     [rsp+arg_0], rbx
0x180016e31  push    rdi
0x180016e32  sub     rsp, 20h
0x180016e36  mov     rbx, rcx
0x180016e39  or      edi, 0FFFFFFFFh
0x180016e3c  lock xadd [rcx+8], edi
0x180016e41  sub     edi, 1
0x180016e44  jnz     short loc_180016E58
0x180016e46  test    rcx, rcx
0x180016e49  jz      short loc_180016E58
0x180016e4b  call    ??1DockingProviders@@AEAA@XZ; DockingProviders::~DockingProviders(void)
0x180016e50  mov     rcx, rbx; Block
0x180016e53  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016e58  mov     rbx, [rsp+28h+arg_0]
0x180016e5d  mov     eax, edi
0x180016e5f  add     rsp, 20h
0x180016e63  pop     rdi
0x180016e64  retn
```

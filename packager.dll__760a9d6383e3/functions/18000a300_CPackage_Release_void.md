# CPackage::Release(void)

- ea: `0x18000a300`
- end: `0x18000a339`
- name: `?Release@CPackage@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(CPackage *this)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a340`
- `0x18000a350`
- `0x18000a360`
- `0x18000a370`
- `0x18000a380`
- `0x18000a390`
- `0x18000a3a0`
- `0x18000a3b0`
- `0x18000a3c0`
- `0x18000a3d0`

## callees

- `0x18000710c`
- `0x18000a300`
- `0x18000a718`

## pseudocode

```c
__int64 __fastcall CPackage::Release(CPackage *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 22);
  if ( !v2 && this )
  {
    CPackage::~CPackage(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a300  mov     [rsp+arg_0], rbx
0x18000a305  push    rdi
0x18000a306  sub     rsp, 20h
0x18000a30a  mov     rbx, rcx
0x18000a30d  or      edi, 0FFFFFFFFh
0x18000a310  lock xadd [rcx+58h], edi
0x18000a315  sub     edi, 1
0x18000a318  jnz     short loc_18000A32C
0x18000a31a  test    rcx, rcx
0x18000a31d  jz      short loc_18000A32C
0x18000a31f  call    ??1CPackage@@QEAA@XZ; CPackage::~CPackage(void)
0x18000a324  mov     rcx, rbx; lpMem
0x18000a327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a32c  mov     rbx, [rsp+28h+arg_0]
0x18000a331  mov     eax, edi
0x18000a333  add     rsp, 20h
0x18000a337  pop     rdi
0x18000a338  retn
```

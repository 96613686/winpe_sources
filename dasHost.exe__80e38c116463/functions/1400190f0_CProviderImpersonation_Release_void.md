# CProviderImpersonation::Release(void)

- ea: `0x1400190f0`
- end: `0x14001912c`
- name: `?Release@CProviderImpersonation@@UEAAKXZ`
- size: `60`
- prototype: `__int64 __fastcall(CProviderImpersonation *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1400018d4`
- `0x140018f50`
- `0x1400190f0`

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::Release(CProviderImpersonation *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CProviderImpersonation::~CProviderImpersonation(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1400190f0  mov     [rsp+arg_0], rbx
0x1400190f5  push    rdi
0x1400190f6  sub     rsp, 20h
0x1400190fa  mov     rbx, rcx
0x1400190fd  or      edi, 0FFFFFFFFh
0x140019100  lock xadd [rcx+8], edi
0x140019105  sub     edi, 1
0x140019108  jnz     short loc_14001911F
0x14001910a  test    rcx, rcx
0x14001910d  jz      short loc_14001911F
0x14001910f  call    ??1CProviderImpersonation@@IEAA@XZ; CProviderImpersonation::~CProviderImpersonation(void)
0x140019114  lea     edx, [rdi+18h]; unsigned __int64
0x140019117  mov     rcx, rbx; void *
0x14001911a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001911f  mov     rbx, [rsp+28h+arg_0]
0x140019124  mov     eax, edi
0x140019126  add     rsp, 20h
0x14001912a  pop     rdi
0x14001912b  retn
```

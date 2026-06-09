# CContainer::Release(void)

- ea: `0x18000f640`
- end: `0x18000f67e`
- name: `?Release@CContainer@@UEAAKXZ`
- size: `62`
- prototype: `unsigned int __fastcall(CContainer *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ac0`
- `0x18000f690`
- `0x18000f6a0`
- `0x18000f6b0`

## callees

- `0x1800019a0`
- `0x18000dfd4`
- `0x18000f640`

## pseudocode

```c
__int64 __fastcall CContainer::Release(CContainer *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 12);
  if ( !v2 && this )
  {
    CContainer::~CContainer(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f640  mov     [rsp+arg_0], rbx
0x18000f645  push    rdi
0x18000f646  sub     rsp, 20h
0x18000f64a  mov     rbx, rcx
0x18000f64d  or      edi, 0FFFFFFFFh
0x18000f650  lock xadd [rcx+30h], edi
0x18000f655  sub     edi, 1
0x18000f658  jnz     short loc_18000F671
0x18000f65a  test    rcx, rcx
0x18000f65d  jz      short loc_18000F671
0x18000f65f  call    ??1CContainer@@QEAA@XZ; CContainer::~CContainer(void)
0x18000f664  mov     edx, 370h; unsigned __int64
0x18000f669  mov     rcx, rbx; void *
0x18000f66c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f671  mov     rbx, [rsp+28h+arg_0]
0x18000f676  mov     eax, edi
0x18000f678  add     rsp, 20h
0x18000f67c  pop     rdi
0x18000f67d  retn
```

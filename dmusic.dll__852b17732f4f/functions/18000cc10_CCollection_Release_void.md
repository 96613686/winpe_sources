# CCollection::Release(void)

- ea: `0x18000cc10`
- end: `0x18000cc51`
- name: `?Release@CCollection@@UEAAKXZ`
- size: `65`
- prototype: `unsigned int __fastcall(CCollection *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cc60`
- `0x18000cc70`
- `0x18000d140`
- `0x18000ec80`
- `0x180014438`

## callees

- `0x1800012c4`
- `0x18000b628`
- `0x18000cc10`

## pseudocode

```c
__int64 __fastcall CCollection::Release(CCollection *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 61);
  if ( !v2 && this )
  {
    CCollection::~CCollection(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000cc10  mov     [rsp+arg_0], rbx
0x18000cc15  push    rdi
0x18000cc16  sub     rsp, 20h
0x18000cc1a  mov     rbx, rcx
0x18000cc1d  or      edi, 0FFFFFFFFh
0x18000cc20  lock xadd [rcx+0F4h], edi
0x18000cc28  sub     edi, 1
0x18000cc2b  jnz     short loc_18000CC44
0x18000cc2d  test    rcx, rcx
0x18000cc30  jz      short loc_18000CC44
0x18000cc32  call    ??1CCollection@@QEAA@XZ; CCollection::~CCollection(void)
0x18000cc37  mov     edx, 130h; unsigned __int64
0x18000cc3c  mov     rcx, rbx; void *
0x18000cc3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cc44  mov     rbx, [rsp+28h+arg_0]
0x18000cc49  mov     eax, edi
0x18000cc4b  add     rsp, 20h
0x18000cc4f  pop     rdi
0x18000cc50  retn
```

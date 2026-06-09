# CAepStoreAccess::Release(void)

- ea: `0x1400197f0`
- end: `0x14001982c`
- name: `?Release@CAepStoreAccess@@UEAAKXZ`
- size: `60`
- prototype: `__int64 __fastcall(CAepStoreAccess *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1400018d4`
- `0x14001917c`
- `0x1400197f0`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::Release(CAepStoreAccess *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CAepStoreAccess::~CAepStoreAccess(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1400197f0  mov     [rsp+arg_0], rbx
0x1400197f5  push    rdi
0x1400197f6  sub     rsp, 20h
0x1400197fa  mov     rbx, rcx
0x1400197fd  or      edi, 0FFFFFFFFh
0x140019800  lock xadd [rcx+8], edi
0x140019805  sub     edi, 1
0x140019808  jnz     short loc_14001981F
0x14001980a  test    rcx, rcx
0x14001980d  jz      short loc_14001981F
0x14001980f  call    ??1CAepStoreAccess@@IEAA@XZ; CAepStoreAccess::~CAepStoreAccess(void)
0x140019814  lea     edx, [rdi+58h]; unsigned __int64
0x140019817  mov     rcx, rbx; void *
0x14001981a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001981f  mov     rbx, [rsp+28h+arg_0]
0x140019824  mov     eax, edi
0x140019826  add     rsp, 20h
0x14001982a  pop     rdi
0x14001982b  retn
```

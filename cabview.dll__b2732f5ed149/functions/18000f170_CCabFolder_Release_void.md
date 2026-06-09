# CCabFolder::Release(void)

- ea: `0x18000f170`
- end: `0x18000f1ac`
- name: `?Release@CCabFolder@@UEAAKXZ`
- size: `60`
- prototype: `unsigned int __fastcall(CCabFolder *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f1c0`
- `0x18000f1d0`
- `0x18000f1e0`
- `0x18000f1f0`

## callees

- `0x180002644`
- `0x18000d300`
- `0x18000f170`

## pseudocode

```c
__int64 __fastcall CCabFolder::Release(CCabFolder *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( !v2 && this )
  {
    CCabFolder::~CCabFolder(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f170  mov     [rsp+arg_0], rbx
0x18000f175  push    rdi
0x18000f176  sub     rsp, 20h
0x18000f17a  mov     rbx, rcx
0x18000f17d  or      edi, 0FFFFFFFFh
0x18000f180  lock xadd [rcx+28h], edi
0x18000f185  sub     edi, 1
0x18000f188  jnz     short loc_18000F19F
0x18000f18a  test    rcx, rcx
0x18000f18d  jz      short loc_18000F19F
0x18000f18f  call    ??1CCabFolder@@AEAA@XZ; CCabFolder::~CCabFolder(void)
0x18000f194  lea     edx, [rdi+50h]; unsigned __int64
0x18000f197  mov     rcx, rbx; void *
0x18000f19a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f19f  mov     rbx, [rsp+28h+arg_0]
0x18000f1a4  mov     eax, edi
0x18000f1a6  add     rsp, 20h
0x18000f1aa  pop     rdi
0x18000f1ab  retn
```

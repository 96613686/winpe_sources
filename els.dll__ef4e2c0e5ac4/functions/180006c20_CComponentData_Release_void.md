# CComponentData::Release(void)

- ea: `0x180006c20`
- end: `0x180006c5a`
- name: `?Release@CComponentData@@UEAAKXZ`
- size: `58`
- prototype: `unsigned int __fastcall(CComponentData *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006c60`
- `0x180006c70`
- `0x180006c80`
- `0x180006c90`
- `0x180006ca0`
- `0x180006cb0`

## callees

- `0x1800052a8`
- `0x180006c20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006c47`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006c47`

## pseudocode

```c
__int64 __fastcall CComponentData::Release(CComponentData *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 15);
  if ( !v2 && this )
  {
    CComponentData::~CComponentData(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180006c20  mov     [rsp+arg_0], rbx
0x180006c25  push    rdi
0x180006c26  sub     rsp, 20h
0x180006c2a  mov     rbx, rcx
0x180006c2d  or      edi, 0FFFFFFFFh
0x180006c30  lock xadd [rcx+3Ch], edi
0x180006c35  sub     edi, 1
0x180006c38  jnz     short loc_180006C4D
0x180006c3a  test    rcx, rcx
0x180006c3d  jz      short loc_180006C4D
0x180006c3f  call    ??1CComponentData@@QEAA@XZ; CComponentData::~CComponentData(void)
0x180006c44  mov     rcx, rbx
0x180006c47  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006c4d  mov     rbx, [rsp+28h+arg_0]
0x180006c52  mov     eax, edi
0x180006c54  add     rsp, 20h
0x180006c58  pop     rdi
0x180006c59  retn
```

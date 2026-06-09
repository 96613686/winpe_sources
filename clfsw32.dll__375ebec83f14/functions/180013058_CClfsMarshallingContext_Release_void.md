# CClfsMarshallingContext::Release(void)

- ea: `0x180013058`
- end: `0x180013099`
- name: `?Release@CClfsMarshallingContext@@QEAAKXZ`
- size: `65`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a7e0`
- `0x18000aaa0`
- `0x18000aec0`
- `0x18000d500`
- `0x18000d8c0`
- `0x1800101c8`

## callees

- `0x18000ddd8`
- `0x180013058`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001307f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001307f`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::Release(CClfsMarshallingContext *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 27);
  if ( !v2 && this )
  {
    CClfsMarshallingContext::~CClfsMarshallingContext(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180013058  mov     [rsp+arg_0], rbx
0x18001305d  push    rdi
0x18001305e  sub     rsp, 20h
0x180013062  mov     rbx, rcx
0x180013065  or      edi, 0FFFFFFFFh
0x180013068  lock xadd [rcx+6Ch], edi
0x18001306d  sub     edi, 1
0x180013070  jnz     short loc_18001308B
0x180013072  test    rcx, rcx
0x180013075  jz      short loc_18001308B
0x180013077  call    ??1CClfsMarshallingContext@@QEAA@XZ; CClfsMarshallingContext::~CClfsMarshallingContext(void)
0x18001307c  mov     rcx, rbx
0x18001307f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013086  nop     dword ptr [rax+rax+00h]
0x18001308b  mov     rbx, [rsp+28h+arg_0]
0x180013090  mov     eax, edi
0x180013092  add     rsp, 20h
0x180013096  pop     rdi
0x180013097  retn
```

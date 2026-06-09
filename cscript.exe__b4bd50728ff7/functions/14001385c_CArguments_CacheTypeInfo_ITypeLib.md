# CArguments::CacheTypeInfo(ITypeLib *)

- ea: `0x14001385c`
- end: `0x1400138a8`
- name: `?CacheTypeInfo@CArguments@@QEAAJPEAUITypeLib@@@Z`
- size: `76`
- prototype: `int(CArguments *__hidden this, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001bd0`

## callees

- `0x14000275c`
- `0x14001385c`

## pseudocode

```c
__int64 __fastcall CArguments::CacheTypeInfo(CArguments *this, struct ITypeLib *a2)
{
  __int64 result; // rax

  result = CDispatch::CacheTypeInfo((CDispatch *)(*((_QWORD *)this + 11) + 16LL), a2);
  if ( (int)result >= 0 )
  {
    result = CDispatch::CacheTypeInfo((CDispatch *)(*((_QWORD *)this + 12) + 16LL), a2);
    if ( (int)result >= 0 )
      return CDispatch::CacheTypeInfo((CArguments *)((char *)this + 24), a2);
  }
  return result;
}

```

## disassembly

```asm
0x14001385c  mov     [rsp+arg_0], rbx
0x140013861  push    rdi
0x140013862  sub     rsp, 20h
0x140013866  mov     rdi, rcx
0x140013869  mov     rbx, rdx
0x14001386c  mov     rcx, [rcx+58h]
0x140013870  add     rcx, 10h; this
0x140013874  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x140013879  test    eax, eax
0x14001387b  js      short loc_14001389D
0x14001387d  mov     rcx, [rdi+60h]
0x140013881  mov     rdx, rbx; struct ITypeLib *
0x140013884  add     rcx, 10h; this
0x140013888  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14001388d  test    eax, eax
0x14001388f  js      short loc_14001389D
0x140013891  lea     rcx, [rdi+18h]; this
0x140013895  mov     rdx, rbx; struct ITypeLib *
0x140013898  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14001389d  mov     rbx, [rsp+28h+arg_0]
0x1400138a2  add     rsp, 20h
0x1400138a6  pop     rdi
0x1400138a7  retn
```

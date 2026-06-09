# std::_Uninitialized_copy_n<winrt::hstring const *,std::allocator<winrt::hstring>>(winrt::hstring const *,unsigned __int64,winrt::hstring *,std::allocator<winrt::hstring> &)

- ea: `0x180025954`
- end: `0x1800259f7`
- name: `??$_Uninitialized_copy_n@PEBUhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@YAPEAUhstring@winrt@@PEBU12@_KPEAU12@AEAV?$allocator@Uhstring@winrt@@@0@@Z`
- size: `163`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(struct winrt::impl::shared_hstring_header **, __int64, struct winrt::impl::shared_hstring_header **, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800290e0`

## callees

- `0x180007eac`
- `0x180008274`
- `0x180025954`
- `0x180025e2c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall std::_Uninitialized_copy_n<winrt::hstring const *>(
        struct winrt::impl::shared_hstring_header **a1,
        __int64 a2,
        struct winrt::impl::shared_hstring_header **a3,
        __int64 a4)
{
  struct winrt::impl::shared_hstring_header **v4; // rsi
  __int64 v5; // rbp
  struct winrt::impl::shared_hstring_header *v7; // rdi
  unsigned int v8; // r15d
  const void *v9; // rbx
  struct winrt::impl::shared_hstring_header **v11; // [rsp+20h] [rbp-58h] BYREF
  struct winrt::impl::shared_hstring_header **v12; // [rsp+28h] [rbp-50h]
  __int64 i; // [rsp+30h] [rbp-48h]

  v4 = a3;
  v5 = a2;
  v11 = a3;
  v12 = a3;
  for ( i = a4; v5; --v5 )
  {
    v7 = *a1;
    if ( *a1 )
    {
      if ( (*(_BYTE *)v7 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v7 + 6);
        goto LABEL_8;
      }
      v8 = *((_DWORD *)v7 + 1);
      if ( v8 )
      {
        v9 = (const void *)*((_QWORD *)v7 + 2);
        v7 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v8, a2);
        memcpy_s((char *)v7 + 28, 2LL * v8, v9, 2LL * v8);
        goto LABEL_8;
      }
    }
    v7 = 0;
LABEL_8:
    *v4++ = v7;
    v12 = v4;
    ++a1;
  }
  v11 = v4;
  std::_Uninitialized_backout_al<std::allocator<winrt::hstring>>::~_Uninitialized_backout_al<std::allocator<winrt::hstring>>(&v11);
  return v4;
}

```

## disassembly

```asm
0x180025954  push    rbx
0x180025956  push    rbp
0x180025957  push    rsi
0x180025958  push    rdi
0x180025959  push    r14
0x18002595b  push    r15
0x18002595d  sub     rsp, 48h
0x180025961  mov     rsi, r8
0x180025964  mov     rbp, rdx
0x180025967  mov     r14, rcx
0x18002596a  mov     [rsp+78h+var_58], r8
0x18002596f  mov     [rsp+78h+var_50], r8
0x180025974  mov     [rsp+78h+var_48], r9
0x180025979  test    rdx, rdx
0x18002597c  jz      short loc_1800259D8
0x18002597e  mov     rdi, [r14]
0x180025981  test    rdi, rdi
0x180025984  jnz     short loc_18002598A
0x180025986  xor     edi, edi
0x180025988  jmp     short loc_1800259C2
0x18002598a  test    byte ptr [rdi], 1
0x18002598d  jnz     short loc_180025995
0x18002598f  lock inc dword ptr [rdi+18h]
0x180025993  jmp     short loc_1800259C2
0x180025995  mov     r15d, [rdi+4]
0x180025999  test    r15d, r15d
0x18002599c  jz      short loc_180025986
0x18002599e  mov     rbx, [rdi+10h]
0x1800259a2  mov     ecx, r15d; this
0x1800259a5  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800259aa  mov     rdi, rax
0x1800259ad  mov     edx, r15d
0x1800259b0  add     rdx, rdx; DestinationSize
0x1800259b3  lea     rcx, [rax+1Ch]; Destination
0x1800259b7  mov     r9, rdx; SourceSize
0x1800259ba  mov     r8, rbx; Source
0x1800259bd  call    memcpy_s
0x1800259c2  mov     [rsi], rdi
0x1800259c5  add     rsi, 8
0x1800259c9  mov     [rsp+78h+var_50], rsi
0x1800259ce  add     r14, 8
0x1800259d2  sub     rbp, 1
0x1800259d6  jnz     short loc_18002597E
0x1800259d8  mov     [rsp+78h+var_58], rsi
0x1800259dd  lea     rcx, [rsp+78h+var_58]
0x1800259e2  call    ??1?$_Uninitialized_backout_al@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<winrt::hstring>>::~_Uninitialized_backout_al<std::allocator<winrt::hstring>>(void)
0x1800259e7  mov     rax, rsi
0x1800259ea  add     rsp, 48h
0x1800259ee  pop     r15
0x1800259f0  pop     r14
0x1800259f2  pop     rdi
0x1800259f3  pop     rsi
0x1800259f4  pop     rbp
0x1800259f5  pop     rbx
0x1800259f6  retn
```

# winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32>::RemoveAt(uint)

- ea: `0x1800211e4`
- end: `0x18002126c`
- name: `?RemoveAt@?$vector_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@@winrt@@QEAAXI@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021110`

## callees

- `0x1800022da`
- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x1800211e4`

## pseudocode

```c
void *__fastcall winrt::vector_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32>::RemoveAt(
        volatile signed __int32 *a1,
        unsigned int a2)
{
  __int64 v2; // r8
  __int64 v3; // rbx
  void *result; // rax
  const struct winrt::impl::slim_source_location *v5; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-20h] BYREF

  v2 = (__int64)(a1 + 2);
  if ( !a1 )
    v2 = 48;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)(v2 + 8) - *(_QWORD *)v2) >> 4) )
  {
    v5 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v7);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v5);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement(a1);
  v3 = (__int64)(a1 + 4);
  if ( !a1 )
    v3 = 56;
  result = memmove_0(
             (void *)(*(_QWORD *)v2 + 16LL * a2),
             (const void *)(*(_QWORD *)v2 + 16LL * a2 + 16),
             *(_QWORD *)v3 - (*(_QWORD *)v2 + 16LL * a2 + 16));
  *(_QWORD *)v3 -= 16LL;
  return result;
}

```

## disassembly

```asm
0x1800211e4  push    rbx
0x1800211e6  sub     rsp, 50h
0x1800211ea  test    rcx, rcx
0x1800211ed  lea     r8, [rcx+8]
0x1800211f1  mov     eax, 30h ; '0'
0x1800211f6  mov     r9, rcx
0x1800211f9  cmovz   r8, rax
0x1800211fd  mov     ecx, edx
0x1800211ff  mov     rax, [r8+8]
0x180021203  sub     rax, [r8]
0x180021206  sar     rax, 4
0x18002120a  cmp     rcx, rax
0x18002120d  jnb     short loc_180021243
0x18002120f  lock inc dword ptr [r9]
0x180021213  shl     rcx, 4
0x180021217  lea     rbx, [r9+10h]
0x18002121b  add     rcx, [r8]; void *
0x18002121e  mov     eax, 38h ; '8'
0x180021223  test    r9, r9
0x180021226  cmovz   rbx, rax
0x18002122a  lea     rdx, [rcx+10h]; Src
0x18002122e  mov     r8, [rbx]
0x180021231  sub     r8, rdx; Size
0x180021234  call    memmove_0
0x180021239  add     qword ptr [rbx], 0FFFFFFFFFFFFFFF0h
0x18002123d  add     rsp, 50h
0x180021241  pop     rbx
0x180021242  retn
0x180021243  lea     rcx, [rsp+58h+var_20]
0x180021248  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002124d  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180021250  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180021255  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18002125a  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180021261  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180021266  call    _CxxThrowException_0
```

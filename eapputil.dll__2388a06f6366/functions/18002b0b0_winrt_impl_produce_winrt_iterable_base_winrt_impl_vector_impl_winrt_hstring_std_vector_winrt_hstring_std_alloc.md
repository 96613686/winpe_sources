# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::get_Current(void * *)

- ea: `0x18002b0b0`
- end: `0x18002b1c7`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `279`
- prototype: `__int64 __fastcall(__int64, struct winrt::impl::shared_hstring_header **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000395a`
- `0x180007eac`
- `0x18000817c`
- `0x180008274`
- `0x1800114d8`
- `0x18001151c`
- `0x18002b0b0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::get_Current(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rax
  struct winrt::impl::shared_hstring_header **v6; // rbx
  __int64 v7; // rax
  struct winrt::impl::shared_hstring_header *v8; // rbx
  unsigned int v9; // edi
  const void *v10; // r14
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  const struct winrt::impl::slim_source_location *v13; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v16[72]; // [rsp+50h] [rbp-48h] BYREF
  int v17; // [rsp+A0h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = a1 + 8;
  if ( !a1 )
    v3 = 24;
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v4 + 40LL) != *(_DWORD *)v3 )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v16);
      winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v12);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    v5 = a1 + 24;
    if ( !a1 )
      v5 = 40;
    v6 = *(struct winrt::impl::shared_hstring_header ***)v5;
    v7 = a1 + 32;
    if ( !a1 )
      v7 = 48;
    if ( v6 == *(struct winrt::impl::shared_hstring_header ***)v7 )
    {
      v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v16);
      winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)v15, v13);
      throw (winrt::hresult_out_of_bounds *)v15;
    }
    v8 = *v6;
    if ( v8 )
    {
      if ( (*(_BYTE *)v8 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
        goto LABEL_17;
      }
      v9 = *((_DWORD *)v8 + 1);
      if ( v9 )
      {
        v10 = (const void *)*((_QWORD *)v8 + 2);
        v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v9, (unsigned int)a2);
        memcpy_s((char *)v8 + 28, 2LL * v9, v10, 2LL * v9);
        goto LABEL_17;
      }
    }
    v8 = 0;
LABEL_17:
    *a2 = v8;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v17);
  }
  return result;
}

```

## disassembly

```asm
0x18002b0b0  push    rbx
0x18002b0b2  push    rsi
0x18002b0b3  push    rdi
0x18002b0b4  push    r14
0x18002b0b6  sub     rsp, 78h
0x18002b0ba  mov     rsi, rdx
0x18002b0bd  mov     r9, rcx
0x18002b0c0  mov     qword ptr [rdx], 0
0x18002b0c7  lea     r8, [rcx+8]
0x18002b0cb  mov     eax, 18h
0x18002b0d0  test    rcx, rcx
0x18002b0d3  cmovz   r8, rax
0x18002b0d7  lea     rax, [rcx+10h]
0x18002b0db  mov     ecx, 20h ; ' '
0x18002b0e0  cmovz   rax, rcx
0x18002b0e4  mov     rax, [rax]
0x18002b0e7  mov     ecx, [rax+28h]
0x18002b0ea  nop
0x18002b0eb  cmp     ecx, [r8]
0x18002b0ee  jnz     loc_18002B175
0x18002b0f4  lea     rax, [r9+18h]
0x18002b0f8  mov     ecx, 28h ; '('
0x18002b0fd  test    r9, r9
0x18002b100  cmovz   rax, rcx
0x18002b104  mov     rbx, [rax]
0x18002b107  lea     rax, [r9+20h]
0x18002b10b  mov     ecx, 30h ; '0'
0x18002b110  cmovz   rax, rcx
0x18002b114  cmp     rbx, [rax]
0x18002b117  jz      loc_18002B19D
0x18002b11d  mov     rbx, [rbx]
0x18002b120  test    rbx, rbx
0x18002b123  jnz     short loc_18002B129
0x18002b125  xor     ebx, ebx
0x18002b127  jmp     short loc_18002B15D
0x18002b129  test    byte ptr [rbx], 1
0x18002b12c  jnz     short loc_18002B134
0x18002b12e  lock inc dword ptr [rbx+18h]
0x18002b132  jmp     short loc_18002B15D
0x18002b134  mov     edi, [rbx+4]
0x18002b137  test    edi, edi
0x18002b139  jz      short loc_18002B125
0x18002b13b  mov     r14, [rbx+10h]
0x18002b13f  mov     ecx, edi; this
0x18002b141  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002b146  mov     rbx, rax
0x18002b149  mov     edx, edi
0x18002b14b  add     rdx, rdx; DestinationSize
0x18002b14e  lea     rcx, [rax+1Ch]; Destination
0x18002b152  mov     r9, rdx; SourceSize
0x18002b155  mov     r8, r14; Source
0x18002b158  call    memcpy_s
0x18002b15d  mov     [rsi], rbx
0x18002b160  xor     eax, eax
0x18002b162  jmp     short loc_18002B16B
0x18002b164  mov     eax, [rsp+98h+arg_0]
0x18002b16b  add     rsp, 78h
0x18002b16f  pop     r14
0x18002b171  pop     rdi
0x18002b172  pop     rsi
0x18002b173  pop     rbx
0x18002b174  retn
0x18002b175  lea     rcx, [rsp+98h+var_48]
0x18002b17a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002b17f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002b182  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18002b187  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x18002b18c  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18002b193  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002b198  call    _CxxThrowException_0
0x18002b19d  lea     rcx, [rsp+98h+var_48]
0x18002b1a2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002b1a7  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002b1aa  lea     rcx, [rsp+98h+var_60]; this
0x18002b1af  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18002b1b4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18002b1bb  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x18002b1c0  call    _CxxThrowException_0
```

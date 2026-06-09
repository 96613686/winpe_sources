# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::GetMany(uint,void * *,uint *)

- ea: `0x180011e80`
- end: `0x180011f97`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `279`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002b78`
- `0x18000395a`
- `0x18000817c`
- `0x1800083ec`
- `0x1800114d8`
- `0x180011e80`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int *a4)
{
  __int64 *v5; // rbx
  unsigned int v6; // edi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v20[80]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+10h]

  v5 = a3;
  v6 = a2;
  memset_0(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v20);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v16);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v17 = &v18;
      *((_DWORD *)v17 + 38) = *(_DWORD *)winrt::to_hresult(v17 + 19);
      return v21;
    }
  }
  v10 = a1 + 24;
  if ( !a1 )
    v10 = 40;
  v11 = *(__int64 **)v10;
  v12 = a1 + 32;
  if ( !a1 )
    v12 = 48;
  if ( v6 >= (unsigned int)((__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3) )
    v6 = (__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3;
  v13 = v6;
  if ( v6 )
  {
    while ( 1 )
    {
      if ( v5 != v11 )
      {
        if ( *v5 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v5);
        v14 = *v11;
        *v5 = *v11;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      }
      if ( !--v13 )
        break;
      ++v5;
      ++v11;
    }
  }
  *(_QWORD *)v10 += 8LL * v6;
  *a4 = v6;
  return 0;
}

```

## disassembly

```asm
0x180011e80  push    rbx
0x180011e82  push    rsi
0x180011e83  push    rdi
0x180011e84  push    r12
0x180011e86  push    r14
0x180011e88  push    r15
0x180011e8a  sub     rsp, 58h
0x180011e8e  mov     r12, r9
0x180011e91  mov     rbx, r8
0x180011e94  mov     edi, edx
0x180011e96  mov     r14, rcx
0x180011e99  mov     r8d, edi
0x180011e9c  shl     r8, 3; Size
0x180011ea0  xor     edx, edx; Val
0x180011ea2  mov     rcx, rbx; void *
0x180011ea5  call    memset_0
0x180011eaa  lea     r8, [r14+8]
0x180011eae  mov     eax, 18h
0x180011eb3  test    r14, r14
0x180011eb6  cmovz   r8, rax
0x180011eba  lea     rax, [r14+10h]
0x180011ebe  mov     ecx, 20h ; ' '
0x180011ec3  cmovz   rax, rcx
0x180011ec7  mov     rax, [rax]
0x180011eca  mov     ecx, [rax+28h]
0x180011ecd  nop
0x180011ece  cmp     ecx, [r8]
0x180011ed1  jnz     loc_180011F6D
0x180011ed7  lea     r15, [r14+18h]
0x180011edb  mov     eax, 28h ; '('
0x180011ee0  test    r14, r14
0x180011ee3  cmovz   r15, rax
0x180011ee7  mov     rsi, [r15]
0x180011eea  lea     rax, [r14+20h]
0x180011eee  mov     ecx, 30h ; '0'
0x180011ef3  cmovz   rax, rcx
0x180011ef7  mov     rcx, [rax]
0x180011efa  sub     rcx, rsi
0x180011efd  sar     rcx, 3
0x180011f01  cmp     edi, ecx
0x180011f03  cmovnb  edi, ecx
0x180011f06  mov     r14d, edi
0x180011f09  test    edi, edi
0x180011f0b  jz      short loc_180011F47
0x180011f0d  cmp     rbx, rsi
0x180011f10  jz      short loc_180011F37
0x180011f12  cmp     qword ptr [rbx], 0
0x180011f16  jz      short loc_180011F20
0x180011f18  mov     rcx, rbx
0x180011f1b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180011f20  mov     rcx, [rsi]
0x180011f23  mov     [rbx], rcx
0x180011f26  test    rcx, rcx
0x180011f29  jz      short loc_180011F37
0x180011f2b  mov     rax, [rcx]
0x180011f2e  mov     rax, [rax+8]
0x180011f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f37  add     r14d, 0FFFFFFFFh
0x180011f3b  jz      short loc_180011F47
0x180011f3d  add     rbx, 8
0x180011f41  add     rsi, 8
0x180011f45  jmp     short loc_180011F0D
0x180011f47  mov     eax, edi
0x180011f49  shl     rax, 3
0x180011f4d  add     [r15], rax
0x180011f50  mov     [r12], edi
0x180011f54  xor     eax, eax
0x180011f56  jmp     short loc_180011F5F
0x180011f58  mov     eax, [rsp+88h+arg_8]
0x180011f5f  add     rsp, 58h
0x180011f63  pop     r15
0x180011f65  pop     r14
0x180011f67  pop     r12
0x180011f69  pop     rdi
0x180011f6a  pop     rsi
0x180011f6b  pop     rbx
0x180011f6c  retn
0x180011f6d  lea     rcx, [rsp+88h+var_50]
0x180011f72  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180011f77  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180011f7a  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180011f7f  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180011f84  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180011f8b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180011f90  call    _CxxThrowException_0
```

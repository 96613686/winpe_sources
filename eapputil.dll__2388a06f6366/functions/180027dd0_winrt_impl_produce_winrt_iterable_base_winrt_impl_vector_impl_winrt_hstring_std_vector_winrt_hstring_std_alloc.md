# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(uint,void * *,uint *)

- ea: `0x180027dd0`
- end: `0x180027ec2`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, unsigned int, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002b78`
- `0x18000395a`
- `0x18000817c`
- `0x1800114d8`
- `0x180017fb8`
- `0x180027dd0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(
        __int64 a1,
        unsigned int a2,
        char *a3,
        unsigned int *a4)
{
  char *v5; // rdi
  unsigned int v6; // ebx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // esi
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v15; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  char v17[80]; // [rsp+38h] [rbp-50h] BYREF
  int v18; // [rsp+98h] [rbp+10h] BYREF

  v5 = a3;
  v6 = a2;
  memset_0(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
    {
      v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v17);
      winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v15);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    v10 = a1 + 24;
    if ( !a1 )
      v10 = 40;
    v11 = *(_QWORD *)v10;
    v12 = a1 + 32;
    if ( !a1 )
      v12 = 48;
    if ( v6 >= (unsigned int)((*(_QWORD *)v12 - v11) >> 3) )
      v6 = (*(_QWORD *)v12 - v11) >> 3;
    v13 = v6;
    if ( v6 )
    {
      while ( 1 )
      {
        winrt::hstring::operator=(v5, v11);
        if ( !--v13 )
          break;
        v5 += 8;
        v11 += 8;
      }
    }
    *(_QWORD *)v10 += 8LL * v6;
    *a4 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v18);
  }
  return result;
}

```

## disassembly

```asm
0x180027dd0  push    rbx
0x180027dd2  push    rsi
0x180027dd3  push    rdi
0x180027dd4  push    r12
0x180027dd6  push    r14
0x180027dd8  push    r15
0x180027dda  sub     rsp, 58h
0x180027dde  mov     r12, r9
0x180027de1  mov     rdi, r8
0x180027de4  mov     ebx, edx
0x180027de6  mov     rsi, rcx
0x180027de9  mov     r8d, ebx
0x180027dec  shl     r8, 3; Size
0x180027df0  xor     edx, edx; Val
0x180027df2  mov     rcx, rdi; void *
0x180027df5  call    memset_0
0x180027dfa  lea     r8, [rsi+8]
0x180027dfe  mov     eax, 18h
0x180027e03  test    rsi, rsi
0x180027e06  cmovz   r8, rax
0x180027e0a  lea     rax, [rsi+10h]
0x180027e0e  mov     ecx, 20h ; ' '
0x180027e13  cmovz   rax, rcx
0x180027e17  mov     rax, [rax]
0x180027e1a  mov     ecx, [rax+28h]
0x180027e1d  nop
0x180027e1e  cmp     ecx, [r8]
0x180027e21  jnz     short loc_180027E98
0x180027e23  lea     r15, [rsi+18h]
0x180027e27  mov     eax, 28h ; '('
0x180027e2c  test    rsi, rsi
0x180027e2f  cmovz   r15, rax
0x180027e33  mov     r14, [r15]
0x180027e36  lea     rax, [rsi+20h]
0x180027e3a  mov     ecx, 30h ; '0'
0x180027e3f  cmovz   rax, rcx
0x180027e43  mov     rcx, [rax]
0x180027e46  sub     rcx, r14
0x180027e49  sar     rcx, 3
0x180027e4d  cmp     ebx, ecx
0x180027e4f  cmovnb  ebx, ecx
0x180027e52  mov     esi, ebx
0x180027e54  test    ebx, ebx
0x180027e56  jz      short loc_180027E72
0x180027e58  mov     rdx, r14
0x180027e5b  mov     rcx, rdi
0x180027e5e  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x180027e63  add     esi, 0FFFFFFFFh
0x180027e66  jz      short loc_180027E72
0x180027e68  add     rdi, 8
0x180027e6c  add     r14, 8
0x180027e70  jmp     short loc_180027E58
0x180027e72  mov     eax, ebx
0x180027e74  shl     rax, 3
0x180027e78  add     [r15], rax
0x180027e7b  mov     [r12], ebx
0x180027e7f  xor     eax, eax
0x180027e81  jmp     short loc_180027E8A
0x180027e83  mov     eax, [rsp+88h+arg_8]
0x180027e8a  add     rsp, 58h
0x180027e8e  pop     r15
0x180027e90  pop     r14
0x180027e92  pop     r12
0x180027e94  pop     rdi
0x180027e95  pop     rsi
0x180027e96  pop     rbx
0x180027e97  retn
0x180027e98  lea     rcx, [rsp+88h+var_50]
0x180027e9d  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180027ea2  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180027ea5  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180027eaa  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180027eaf  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180027eb6  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180027ebb  call    _CxxThrowException_0
```

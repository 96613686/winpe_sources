# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(uint,void *)

- ea: `0x180029280`
- end: `0x1800293d6`
- name: `?SetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x180017fb8`
- `0x180029280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002939a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800293a5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002939a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800293a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r9
  volatile signed __int32 *v4; // r8
  volatile signed __int32 **v5; // rcx
  volatile signed __int32 *v6; // rax
  int v7; // ebx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  volatile signed __int32 *lpMem; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v13[48]; // [rsp+48h] [rbp-30h] BYREF
  int v14; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF

  v15 = a3;
  try
  {
    v3 = (a1 - 16) & -(__int64)(a1 != 0);
    v4 = (volatile signed __int32 *)(v3 + 40);
    if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38)
                                          - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3) )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v13);
      winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v10);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    _InterlockedIncrement(v4);
    v5 = (volatile signed __int32 **)(*(_QWORD *)((v3 & -(__int64)(v4 != 0)) + 0x30) + 8LL * a2);
    v6 = *v5;
    *v5 = 0;
    lpMem = v6;
    winrt::hstring::operator=(v5, &v15);
    if ( lpMem )
    {
      v7 = _InterlockedDecrement(lpMem + 6);
      if ( v7 )
      {
        if ( v7 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)lpMem);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x180029280  mov     [rsp+arg_0], rbx
0x180029285  mov     [rsp+arg_10], r8
0x18002928a  push    rsi
0x18002928b  push    rdi
0x18002928c  push    r14
0x18002928e  sub     rsp, 60h
0x180029292  lea     rax, [rcx-10h]
0x180029296  neg     rcx
0x180029299  sbb     r9, r9
0x18002929c  and     r9, rax
0x18002929f  lea     r8, [r9+28h]
0x1800292a3  mov     [rsp+78h+var_50], 0
0x1800292a8  mov     rax, r8
0x1800292ab  neg     rax
0x1800292ae  sbb     rcx, rcx
0x1800292b1  and     rcx, r9
0x1800292b4  mov     r14d, edx
0x1800292b7  mov     rax, [rcx+38h]
0x1800292bb  sub     rax, [rcx+30h]
0x1800292bf  sar     rax, 3
0x1800292c3  cmp     r14, rax
0x1800292c6  jnb     loc_1800293AC
0x1800292cc  lock inc dword ptr [r8]
0x1800292d0  neg     r8
0x1800292d3  sbb     rax, rax
0x1800292d6  and     rax, r9
0x1800292d9  mov     rsi, [rax+30h]
0x1800292dd  or      ebx, 0FFFFFFFFh
0x1800292e0  cmp     [rsp+78h+var_50], 0
0x1800292e5  jz      short loc_180029322
0x1800292e7  mov     rdi, [rsp+78h+lpMem]
0x1800292ec  test    rdi, rdi
0x1800292ef  jz      short loc_18002931D
0x1800292f1  mov     eax, ebx
0x1800292f3  lock xadd [rdi+18h], eax
0x1800292f8  sub     eax, 1
0x1800292fb  jnz     loc_180029392
0x180029301  nop
0x180029302  call    WINRT_IMPL_GetProcessHeap
0x180029307  mov     rcx, rax; hHeap
0x18002930a  mov     r8, rdi; lpMem
0x18002930d  xor     edx, edx; dwFlags
0x18002930f  call    WINRT_IMPL_HeapFree
0x180029314  mov     [rsp+78h+lpMem], 0
0x18002931d  mov     [rsp+78h+var_50], 0
0x180029322  lea     rcx, [rsi+r14*8]
0x180029326  mov     rax, [rcx]
0x180029329  mov     qword ptr [rcx], 0
0x180029330  mov     [rsp+78h+lpMem], rax
0x180029335  mov     [rsp+78h+var_50], 1
0x18002933a  lea     rdx, [rsp+78h+arg_10]
0x180029342  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x180029347  nop
0x180029348  cmp     [rsp+78h+var_50], 0
0x18002934d  jz      short loc_180029376
0x18002934f  mov     rdi, [rsp+78h+lpMem]
0x180029354  test    rdi, rdi
0x180029357  jz      short loc_180029376
0x180029359  lock xadd [rdi+18h], ebx
0x18002935e  sub     ebx, 1
0x180029361  jnz     short loc_1800293A1
0x180029363  nop
0x180029364  call    WINRT_IMPL_GetProcessHeap
0x180029369  mov     rcx, rax; hHeap
0x18002936c  mov     r8, rdi; lpMem
0x18002936f  xor     edx, edx; dwFlags
0x180029371  call    WINRT_IMPL_HeapFree
0x180029376  xor     eax, eax
0x180029378  jmp     short loc_180029381
0x18002937a  mov     eax, [rsp+78h+arg_8]
0x180029381  mov     rbx, [rsp+78h+arg_0]
0x180029389  add     rsp, 60h
0x18002938d  pop     r14
0x18002938f  pop     rdi
0x180029390  pop     rsi
0x180029391  retn
0x180029392  test    eax, eax
0x180029394  jns     loc_180029314
0x18002939a  call    cs:__imp_abort
0x1800293a1  test    ebx, ebx
0x1800293a3  jns     short loc_180029376
0x1800293a5  call    cs:__imp_abort
0x1800293ac  lea     rcx, [rsp+78h+var_30]
0x1800293b1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800293b6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800293b9  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800293be  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800293c3  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800293ca  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800293cf  call    _CxxThrowException_0
```

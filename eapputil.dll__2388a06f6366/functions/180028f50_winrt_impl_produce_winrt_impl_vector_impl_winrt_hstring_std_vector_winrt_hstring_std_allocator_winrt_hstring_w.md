# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(void)

- ea: `0x180028f50`
- end: `0x1800290d5`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x180028f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029084`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002908f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029084`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002908f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(
        __int64 a1)
{
  __int64 v1; // rsi
  volatile signed __int32 *v2; // r14
  char v3; // r15
  __int64 v4; // r13
  volatile signed __int32 *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r13
  volatile signed __int32 *v8; // rsi
  int v9; // eax
  HANDLE ProcessHeap; // rax
  int v11; // ebx
  HANDLE v12; // rax
  const struct winrt::impl::slim_source_location *v14; // rax
  __int64 v15; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-78h]
  char v17; // [rsp+28h] [rbp-70h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v19[80]; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+8h] BYREF

  v1 = (a1 - 16) & -(__int64)(a1 != 0);
  v2 = (volatile signed __int32 *)(v1 + 40);
  v17 = 0;
  if ( *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x30) == *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x38) )
  {
    v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v19);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v14);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v15 + 160) = *(_DWORD *)winrt::to_hresult(&v20);
      return v20;
    }
  }
  v3 = 1;
  _InterlockedAdd(v2, 1u);
  v4 = *(_QWORD *)((v1 & -(__int64)(v2 != 0)) + 0x38);
  v5 = *(volatile signed __int32 **)(v4 - 8);
  *(_QWORD *)(v4 - 8) = 0;
  lpMem = (LPVOID)v5;
  v17 = 1;
  v6 = v1 & -(__int64)(v2 != 0);
  v7 = *(_QWORD *)(v6 + 56);
  v8 = *(volatile signed __int32 **)(v7 - 8);
  if ( v8 )
  {
    v9 = _InterlockedDecrement(v8 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
    }
    *(_QWORD *)(v7 - 8) = 0;
    v3 = v17;
    v5 = (volatile signed __int32 *)lpMem;
  }
  *(_QWORD *)(v6 + 56) -= 8LL;
  if ( v3 && v5 )
  {
    v11 = _InterlockedDecrement(v5 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      v12 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028f50  push    rbx
0x180028f52  push    rsi
0x180028f53  push    rdi
0x180028f54  push    r13
0x180028f56  push    r14
0x180028f58  push    r15
0x180028f5a  sub     rsp, 68h
0x180028f5e  lea     rax, [rcx-10h]
0x180028f62  neg     rcx
0x180028f65  sbb     rsi, rsi
0x180028f68  and     rsi, rax
0x180028f6b  lea     r14, [rsi+28h]
0x180028f6f  mov     [rsp+98h+var_70], 0
0x180028f74  mov     rax, r14
0x180028f77  neg     rax
0x180028f7a  sbb     rcx, rcx
0x180028f7d  and     rcx, rsi
0x180028f80  mov     rax, [rcx+38h]
0x180028f84  cmp     [rcx+30h], rax
0x180028f88  jz      loc_1800290AB
0x180028f8e  mov     r15d, 1
0x180028f94  lock add [r14], r15d
0x180028f98  mov     rax, r14
0x180028f9b  neg     rax
0x180028f9e  sbb     rcx, rcx
0x180028fa1  and     rcx, rsi
0x180028fa4  mov     r13, [rcx+38h]
0x180028fa8  or      ebx, 0FFFFFFFFh
0x180028fab  cmp     [rsp+98h+var_70], 0
0x180028fb0  jz      short loc_180028FF3
0x180028fb2  mov     rdi, [rsp+98h+lpMem]
0x180028fb7  test    rdi, rdi
0x180028fba  jz      short loc_180028FEE
0x180028fbc  mov     eax, ebx
0x180028fbe  lock xadd [rdi+18h], eax
0x180028fc3  sub     eax, r15d
0x180028fc6  jnz     short loc_180028FDD
0x180028fc8  nop
0x180028fc9  call    WINRT_IMPL_GetProcessHeap
0x180028fce  mov     rcx, rax; hHeap
0x180028fd1  mov     r8, rdi; lpMem
0x180028fd4  xor     edx, edx; dwFlags
0x180028fd6  call    WINRT_IMPL_HeapFree
0x180028fdb  jmp     short loc_180028FE5
0x180028fdd  test    eax, eax
0x180028fdf  js      loc_180029084
0x180028fe5  mov     [rsp+98h+lpMem], 0
0x180028fee  mov     [rsp+98h+var_70], 0
0x180028ff3  mov     rdi, [r13-8]
0x180028ff7  mov     qword ptr [r13-8], 0
0x180028fff  mov     [rsp+98h+lpMem], rdi
0x180029004  mov     [rsp+98h+var_70], r15b
0x180029009  neg     r14
0x18002900c  sbb     r14, r14
0x18002900f  and     r14, rsi
0x180029012  mov     r13, [r14+38h]
0x180029016  mov     rsi, [r13-8]
0x18002901a  test    rsi, rsi
0x18002901d  jz      short loc_180029050
0x18002901f  mov     eax, ebx
0x180029021  lock xadd [rsi+18h], eax
0x180029026  sub     eax, r15d
0x180029029  jnz     short loc_180029080
0x18002902b  nop
0x18002902c  call    WINRT_IMPL_GetProcessHeap
0x180029031  mov     rcx, rax; hHeap
0x180029034  mov     r8, rsi; lpMem
0x180029037  xor     edx, edx; dwFlags
0x180029039  call    WINRT_IMPL_HeapFree
0x18002903e  mov     qword ptr [r13-8], 0
0x180029046  mov     r15b, [rsp+98h+var_70]
0x18002904b  mov     rdi, [rsp+98h+lpMem]
0x180029050  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180029055  test    r15b, r15b
0x180029058  jz      short loc_18002907C
0x18002905a  test    rdi, rdi
0x18002905d  jz      short loc_18002907C
0x18002905f  lock xadd [rdi+18h], ebx
0x180029064  sub     ebx, 1
0x180029067  jnz     short loc_18002908B
0x180029069  nop
0x18002906a  call    WINRT_IMPL_GetProcessHeap
0x18002906f  mov     rcx, rax; hHeap
0x180029072  mov     r8, rdi; lpMem
0x180029075  xor     edx, edx; dwFlags
0x180029077  call    WINRT_IMPL_HeapFree
0x18002907c  xor     eax, eax
0x18002907e  jmp     short loc_18002909D
0x180029080  test    eax, eax
0x180029082  jns     short loc_18002903E
0x180029084  call    cs:__imp_abort
0x18002908b  test    ebx, ebx
0x18002908d  jns     short loc_18002907C
0x18002908f  call    cs:__imp_abort
0x180029096  mov     eax, [rsp+98h+arg_0]
0x18002909d  add     rsp, 68h
0x1800290a1  pop     r15
0x1800290a3  pop     r14
0x1800290a5  pop     r13
0x1800290a7  pop     rdi
0x1800290a8  pop     rsi
0x1800290a9  pop     rbx
0x1800290aa  retn
0x1800290ab  lea     rcx, [rsp+98h+var_50]
0x1800290b0  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800290b5  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800290b8  lea     rcx, [rsp+98h+pExceptionObject]; this
0x1800290bd  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800290c2  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800290c9  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800290ce  call    _CxxThrowException_0
```

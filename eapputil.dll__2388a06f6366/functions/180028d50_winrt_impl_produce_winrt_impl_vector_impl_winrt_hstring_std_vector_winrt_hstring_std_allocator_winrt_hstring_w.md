# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(uint)

- ea: `0x180028d50`
- end: `0x180028f48`
- name: `?RemoveAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `504`
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
- `0x180028d50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f0c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f17`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f0c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r15
  volatile signed __int32 *v3; // r14
  __int64 v4; // r12
  void **v5; // rsi
  void *v6; // rax
  __int64 v7; // r14
  void **v8; // r13
  void **i; // rdi
  void *v10; // r12
  volatile signed __int32 *v11; // r15
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rsi
  volatile signed __int32 *v15; // rdi
  int v16; // eax
  HANDLE v17; // rax
  int v18; // ebx
  HANDLE v19; // rax
  const struct winrt::impl::slim_source_location *v21; // rax
  __int64 v22; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-68h]
  char v24; // [rsp+28h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  char v26[24]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v24 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v21 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v26);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v21);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v22 + 152) = *(_DWORD *)winrt::to_hresult(&v27);
      return v27;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (void **)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  lpMem = v6;
  v24 = 1;
  v7 = v2 & -(__int64)(v3 != 0);
  v8 = *(void ***)(v7 + 56);
  for ( i = v5 + 1; i != v8; ++i )
  {
    if ( v5 != i )
    {
      v10 = *i;
      *i = 0;
      v11 = (volatile signed __int32 *)*v5;
      if ( *v5 )
      {
        v12 = _InterlockedDecrement(v11 + 6);
        if ( v12 )
        {
          if ( v12 < 0 )
            goto LABEL_21;
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
        }
      }
      *v5 = v10;
    }
    ++v5;
  }
  v14 = *(_QWORD *)(v7 + 56);
  v15 = *(volatile signed __int32 **)(v14 - 8);
  if ( v15 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
LABEL_21:
        abort();
    }
    else
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v15);
    }
    *(_QWORD *)(v14 - 8) = 0;
  }
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v24 && lpMem )
  {
    v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, lpMem);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028d50  mov     [rsp+arg_0], rbx
0x180028d55  mov     [rsp+arg_10], rsi
0x180028d5a  push    rdi
0x180028d5b  push    r12
0x180028d5d  push    r13
0x180028d5f  push    r14
0x180028d61  push    r15
0x180028d63  sub     rsp, 60h
0x180028d67  lea     rax, [rcx-10h]
0x180028d6b  neg     rcx
0x180028d6e  sbb     r15, r15
0x180028d71  and     r15, rax
0x180028d74  lea     r14, [r15+28h]
0x180028d78  mov     [rsp+88h+var_60], 0
0x180028d7d  mov     rax, r14
0x180028d80  neg     rax
0x180028d83  sbb     rcx, rcx
0x180028d86  and     rcx, r15
0x180028d89  mov     r12d, edx
0x180028d8c  mov     rax, [rcx+38h]
0x180028d90  sub     rax, [rcx+30h]
0x180028d94  sar     rax, 3
0x180028d98  cmp     r12, rax
0x180028d9b  jnb     loc_180028F1E
0x180028da1  lock inc dword ptr [r14]
0x180028da5  mov     rax, r14
0x180028da8  neg     rax
0x180028dab  sbb     rcx, rcx
0x180028dae  and     rcx, r15
0x180028db1  mov     rsi, [rcx+30h]
0x180028db5  or      ebx, 0FFFFFFFFh
0x180028db8  cmp     [rsp+88h+var_60], 0
0x180028dbd  jz      short loc_180028E00
0x180028dbf  mov     rdi, [rsp+88h+lpMem]
0x180028dc4  test    rdi, rdi
0x180028dc7  jz      short loc_180028DFB
0x180028dc9  mov     eax, ebx
0x180028dcb  lock xadd [rdi+18h], eax
0x180028dd0  sub     eax, 1
0x180028dd3  jnz     short loc_180028DEA
0x180028dd5  nop
0x180028dd6  call    WINRT_IMPL_GetProcessHeap
0x180028ddb  mov     rcx, rax; hHeap
0x180028dde  mov     r8, rdi; lpMem
0x180028de1  xor     edx, edx; dwFlags
0x180028de3  call    WINRT_IMPL_HeapFree
0x180028de8  jmp     short loc_180028DF2
0x180028dea  test    eax, eax
0x180028dec  js      loc_180028F0C
0x180028df2  mov     [rsp+88h+lpMem], 0
0x180028dfb  mov     [rsp+88h+var_60], 0
0x180028e00  lea     rsi, [rsi+r12*8]
0x180028e04  mov     rax, [rsi]
0x180028e07  mov     qword ptr [rsi], 0
0x180028e0e  mov     [rsp+88h+lpMem], rax
0x180028e13  mov     [rsp+88h+var_60], 1
0x180028e18  neg     r14
0x180028e1b  sbb     r14, r14
0x180028e1e  and     r14, r15
0x180028e21  mov     r13, [r14+38h]
0x180028e25  lea     rdi, [rsi+8]
0x180028e29  jmp     short loc_180028E77
0x180028e2b  cmp     rsi, rdi
0x180028e2e  jz      short loc_180028E6F
0x180028e30  mov     r12, [rdi]
0x180028e33  mov     qword ptr [rdi], 0
0x180028e3a  mov     r15, [rsi]
0x180028e3d  test    r15, r15
0x180028e40  jz      short loc_180028E6C
0x180028e42  mov     eax, ebx
0x180028e44  lock xadd [r15+18h], eax
0x180028e4a  sub     eax, 1
0x180028e4d  jnz     short loc_180028E64
0x180028e4f  nop
0x180028e50  call    WINRT_IMPL_GetProcessHeap
0x180028e55  mov     rcx, rax; hHeap
0x180028e58  mov     r8, r15; lpMem
0x180028e5b  xor     edx, edx; dwFlags
0x180028e5d  call    WINRT_IMPL_HeapFree
0x180028e62  jmp     short loc_180028E6C
0x180028e64  test    eax, eax
0x180028e66  js      loc_180028F0C
0x180028e6c  mov     [rsi], r12
0x180028e6f  add     rsi, 8
0x180028e73  add     rdi, 8
0x180028e77  cmp     rdi, r13
0x180028e7a  jnz     short loc_180028E2B
0x180028e7c  mov     rsi, [r14+38h]
0x180028e80  mov     rdi, [rsi-8]
0x180028e84  test    rdi, rdi
0x180028e87  jz      short loc_180028EB0
0x180028e89  mov     eax, ebx
0x180028e8b  lock xadd [rdi+18h], eax
0x180028e90  sub     eax, 1
0x180028e93  jnz     short loc_180028F08
0x180028e95  nop
0x180028e96  call    WINRT_IMPL_GetProcessHeap
0x180028e9b  mov     rcx, rax; hHeap
0x180028e9e  mov     r8, rdi; lpMem
0x180028ea1  xor     edx, edx; dwFlags
0x180028ea3  call    WINRT_IMPL_HeapFree
0x180028ea8  mov     qword ptr [rsi-8], 0
0x180028eb0  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180028eb5  cmp     [rsp+88h+var_60], 0
0x180028eba  jz      short loc_180028EE3
0x180028ebc  mov     rdi, [rsp+88h+lpMem]
0x180028ec1  test    rdi, rdi
0x180028ec4  jz      short loc_180028EE3
0x180028ec6  lock xadd [rdi+18h], ebx
0x180028ecb  sub     ebx, 1
0x180028ece  jnz     short loc_180028F13
0x180028ed0  nop
0x180028ed1  call    WINRT_IMPL_GetProcessHeap
0x180028ed6  mov     rcx, rax; hHeap
0x180028ed9  mov     r8, rdi; lpMem
0x180028edc  xor     edx, edx; dwFlags
0x180028ede  call    WINRT_IMPL_HeapFree
0x180028ee3  xor     eax, eax
0x180028ee5  jmp     short loc_180028EEE
0x180028ee7  mov     eax, [rsp+88h+arg_8]
0x180028eee  lea     r11, [rsp+88h+var_28]
0x180028ef3  mov     rbx, [r11+30h]
0x180028ef7  mov     rsi, [r11+40h]
0x180028efb  mov     rsp, r11
0x180028efe  pop     r15
0x180028f00  pop     r14
0x180028f02  pop     r13
0x180028f04  pop     r12
0x180028f06  pop     rdi
0x180028f07  retn
0x180028f08  test    eax, eax
0x180028f0a  jns     short loc_180028EA8
0x180028f0c  call    cs:__imp_abort
0x180028f13  test    ebx, ebx
0x180028f15  jns     short loc_180028EE3
0x180028f17  call    cs:__imp_abort
0x180028f1e  lea     rcx, [rsp+88h+var_40]
0x180028f23  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180028f28  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180028f2b  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180028f30  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180028f35  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180028f3c  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180028f41  call    _CxxThrowException_0
```

# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x1800278f0`
- end: `0x180027972`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x1800278f0`
- `0x180027a08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002796a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002796a`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::GetAt(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v4; // rax
  __int64 v5; // rcx
  void *v6; // rbx
  int v7; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  try
  {
    v4 = (__int64 *)winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt();
    v5 = *v4;
    *v4 = 0;
    *a3 = v5;
    v6 = lpMem;
    if ( lpMem )
    {
      v7 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v7 )
      {
        if ( v7 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v6);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800278f0  push    rbx
0x1800278f2  sub     rsp, 20h
0x1800278f6  mov     rbx, r8
0x1800278f9  mov     rax, rcx
0x1800278fc  mov     qword ptr [r8], 0
0x180027903  add     rcx, 18h
0x180027907  mov     r8d, 28h ; '('
0x18002790d  test    rax, rax
0x180027910  cmovz   rcx, r8
0x180027914  mov     r8d, edx
0x180027917  lea     rdx, [rsp+28h+lpMem]
0x18002791c  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x180027921  mov     rcx, [rax]
0x180027924  mov     qword ptr [rax], 0
0x18002792b  mov     [rbx], rcx
0x18002792e  mov     rbx, [rsp+28h+lpMem]
0x180027933  test    rbx, rbx
0x180027936  jz      short loc_180027958
0x180027938  or      eax, 0FFFFFFFFh
0x18002793b  lock xadd [rbx+18h], eax
0x180027940  sub     eax, 1
0x180027943  jnz     short loc_180027966
0x180027945  nop
0x180027946  call    WINRT_IMPL_GetProcessHeap
0x18002794b  mov     rcx, rax; hHeap
0x18002794e  mov     r8, rbx; lpMem
0x180027951  xor     edx, edx; dwFlags
0x180027953  call    WINRT_IMPL_HeapFree
0x180027958  xor     eax, eax
0x18002795a  jmp     short loc_180027960
0x18002795c  mov     eax, dword ptr [rsp+28h+lpMem]
0x180027960  add     rsp, 20h
0x180027964  pop     rbx
0x180027965  retn
0x180027966  test    eax, eax
0x180027968  jns     short loc_180027958
0x18002796a  call    cs:__imp_abort
```

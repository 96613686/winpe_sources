# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x180027980`
- end: `0x180027a02`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x180027980`
- `0x180027a08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800279fa`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800279fa`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::GetAt(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // rcx
  void *v8; // rbx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 40;
  v6 = (__int64 *)winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(
                    v5,
                    &lpMem,
                    a2);
  v7 = *v6;
  *v6 = 0;
  *a3 = v7;
  v8 = lpMem;
  if ( lpMem )
  {
    v9 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027980  push    rbx
0x180027982  sub     rsp, 20h
0x180027986  mov     rbx, r8
0x180027989  mov     rax, rcx
0x18002798c  mov     qword ptr [r8], 0
0x180027993  add     rcx, 10h
0x180027997  mov     r8d, 28h ; '('
0x18002799d  test    rax, rax
0x1800279a0  cmovz   rcx, r8
0x1800279a4  mov     r8d, edx
0x1800279a7  lea     rdx, [rsp+28h+lpMem]
0x1800279ac  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x1800279b1  mov     rcx, [rax]
0x1800279b4  mov     qword ptr [rax], 0
0x1800279bb  mov     [rbx], rcx
0x1800279be  mov     rbx, [rsp+28h+lpMem]
0x1800279c3  test    rbx, rbx
0x1800279c6  jz      short loc_1800279E8
0x1800279c8  or      eax, 0FFFFFFFFh
0x1800279cb  lock xadd [rbx+18h], eax
0x1800279d0  sub     eax, 1
0x1800279d3  jnz     short loc_1800279F6
0x1800279d5  nop
0x1800279d6  call    WINRT_IMPL_GetProcessHeap
0x1800279db  mov     rcx, rax; hHeap
0x1800279de  mov     r8, rbx; lpMem
0x1800279e1  xor     edx, edx; dwFlags
0x1800279e3  call    WINRT_IMPL_HeapFree
0x1800279e8  xor     eax, eax
0x1800279ea  jmp     short loc_1800279F0
0x1800279ec  mov     eax, dword ptr [rsp+28h+lpMem]
0x1800279f0  add     rsp, 20h
0x1800279f4  pop     rbx
0x1800279f5  retn
0x1800279f6  test    eax, eax
0x1800279f8  jns     short loc_1800279E8
0x1800279fa  call    cs:__imp_abort
```

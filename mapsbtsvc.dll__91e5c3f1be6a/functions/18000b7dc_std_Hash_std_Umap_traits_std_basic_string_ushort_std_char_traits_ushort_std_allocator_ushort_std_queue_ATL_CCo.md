# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>,0>> &&)

- ea: `0x18000b7dc`
- end: `0x18000b878`
- name: `??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f49c`

## callees

- `0x18000b7dc`
- `0x180010e5c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  if ( a1 != a2 )
  {
    std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::clear();
    *(_DWORD *)a1 = *(_DWORD *)a2;
    v4 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = v4;
    v5 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = v5;
    v6 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(a2 + 24) = v6;
    v7 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 32) = v7;
    v8 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a2 + 40);
    *(_QWORD *)(a2 + 40) = v8;
    v9 = *(_QWORD *)(a1 + 48);
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(a2 + 48);
    *(_QWORD *)(a2 + 48) = v9;
    v10 = *(_QWORD *)(a1 + 56);
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a2 + 56);
    *(_QWORD *)(a2 + 56) = v10;
  }
  return a1;
}

```

## disassembly

```asm
0x18000b7dc  mov     [rsp+arg_0], rbx
0x18000b7e1  push    rdi
0x18000b7e2  sub     rsp, 20h
0x18000b7e6  mov     rdi, rdx
0x18000b7e9  mov     rbx, rcx
0x18000b7ec  cmp     rcx, rdx
0x18000b7ef  jz      short loc_18000B86A
0x18000b7f1  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::clear(void)
0x18000b7f6  mov     eax, [rdi]
0x18000b7f8  mov     [rbx], eax
0x18000b7fa  mov     rax, [rdi+8]
0x18000b7fe  mov     rcx, [rbx+8]
0x18000b802  mov     [rbx+8], rax
0x18000b806  mov     [rdi+8], rcx
0x18000b80a  mov     rax, [rdi+10h]
0x18000b80e  mov     rcx, [rbx+10h]
0x18000b812  mov     [rbx+10h], rax
0x18000b816  mov     [rdi+10h], rcx
0x18000b81a  mov     rax, [rdi+18h]
0x18000b81e  mov     rcx, [rbx+18h]
0x18000b822  mov     [rbx+18h], rax
0x18000b826  mov     [rdi+18h], rcx
0x18000b82a  mov     rax, [rdi+20h]
0x18000b82e  mov     rcx, [rbx+20h]
0x18000b832  mov     [rbx+20h], rax
0x18000b836  mov     [rdi+20h], rcx
0x18000b83a  mov     rax, [rdi+28h]
0x18000b83e  mov     rcx, [rbx+28h]
0x18000b842  mov     [rbx+28h], rax
0x18000b846  mov     [rdi+28h], rcx
0x18000b84a  mov     rax, [rdi+30h]
0x18000b84e  mov     rcx, [rbx+30h]
0x18000b852  mov     [rbx+30h], rax
0x18000b856  mov     [rdi+30h], rcx
0x18000b85a  mov     rax, [rdi+38h]
0x18000b85e  mov     rcx, [rbx+38h]
0x18000b862  mov     [rbx+38h], rax
0x18000b866  mov     [rdi+38h], rcx
0x18000b86a  mov     rax, rbx
0x18000b86d  mov     rbx, [rsp+28h+arg_0]
0x18000b872  add     rsp, 20h
0x18000b876  pop     rdi
0x18000b877  retn
```

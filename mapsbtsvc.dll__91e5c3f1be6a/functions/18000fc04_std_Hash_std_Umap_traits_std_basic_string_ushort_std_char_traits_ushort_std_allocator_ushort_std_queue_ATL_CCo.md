# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x18000fc04`
- end: `0x18000fc2a`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010bf4`

## callees

- `0x18000a0b8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  char *v1; // rdx
  __int64 result; // rax

  v1 = (char *)a1[2];
  a1[2] = *(_QWORD *)v1;
  std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(
    (__int64)a1,
    v1);
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x18000fc04  push    rbx
0x18000fc06  sub     rsp, 20h
0x18000fc0a  mov     rdx, [rcx+10h]
0x18000fc0e  mov     rbx, rcx
0x18000fc11  mov     rax, [rdx]
0x18000fc14  mov     [rcx+10h], rax
0x18000fc18  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *> *)
0x18000fc1d  mov     rax, [rbx]
0x18000fc20  dec     qword ptr [rax+8]
0x18000fc24  add     rsp, 20h
0x18000fc28  pop     rbx
0x18000fc29  retn
```

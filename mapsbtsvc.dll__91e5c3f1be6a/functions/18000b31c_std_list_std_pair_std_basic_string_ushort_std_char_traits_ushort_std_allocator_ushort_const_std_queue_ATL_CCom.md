# std::list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>>::~list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>>(void)

- ea: `0x18000b31c`
- end: `0x18000b33f`
- name: `??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014289`

## callees

- `0x180003c34`
- `0x18000a028`

## pseudocode

```c
void __fastcall std::list<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>::~list<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>(
        __int64 *a1)
{
  std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(
    (__int64)a1,
    *a1);
  std::_Deallocate<16>((void *)*a1, 0x58u);
}

```

## disassembly

```asm
0x18000b31c  push    rbx
0x18000b31e  sub     rsp, 20h
0x18000b322  mov     rdx, [rcx]
0x18000b325  mov     rbx, rcx
0x18000b328  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *> *)
0x18000b32d  mov     rcx, [rbx]
0x18000b330  mov     edx, 58h ; 'X'
0x18000b335  add     rsp, 20h
0x18000b339  pop     rbx
0x18000b33a  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```

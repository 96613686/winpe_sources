# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x18000fbd8`
- end: `0x18000fbfe`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010ac4`

## callees

- `0x18000a08c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 result; // rax

  a1[2] = *(_QWORD *)a1[2];
  std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>();
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x18000fbd8  push    rbx
0x18000fbda  sub     rsp, 20h
0x18000fbde  mov     rdx, [rcx+10h]
0x18000fbe2  mov     rbx, rcx
0x18000fbe5  mov     rax, [rdx]
0x18000fbe8  mov     [rcx+10h], rax
0x18000fbec  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> *)
0x18000fbf1  mov     rax, [rbx]
0x18000fbf4  dec     qword ptr [rax+8]
0x18000fbf8  add     rsp, 20h
0x18000fbfc  pop     rbx
0x18000fbfd  retn
```

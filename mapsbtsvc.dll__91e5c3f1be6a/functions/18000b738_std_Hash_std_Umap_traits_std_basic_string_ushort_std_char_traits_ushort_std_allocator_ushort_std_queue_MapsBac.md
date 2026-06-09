# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>> &&)

- ea: `0x18000b738`
- end: `0x18000b7d4`
- name: `??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c348`
- `0x18000f49c`

## callees

- `0x18000b738`
- `0x180010de4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::operator=(
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
    std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::clear();
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
0x18000b738  mov     [rsp+arg_0], rbx
0x18000b73d  push    rdi
0x18000b73e  sub     rsp, 20h
0x18000b742  mov     rdi, rdx
0x18000b745  mov     rbx, rcx
0x18000b748  cmp     rcx, rdx
0x18000b74b  jz      short loc_18000B7C6
0x18000b74d  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::clear(void)
0x18000b752  mov     eax, [rdi]
0x18000b754  mov     [rbx], eax
0x18000b756  mov     rax, [rdi+8]
0x18000b75a  mov     rcx, [rbx+8]
0x18000b75e  mov     [rbx+8], rax
0x18000b762  mov     [rdi+8], rcx
0x18000b766  mov     rax, [rdi+10h]
0x18000b76a  mov     rcx, [rbx+10h]
0x18000b76e  mov     [rbx+10h], rax
0x18000b772  mov     [rdi+10h], rcx
0x18000b776  mov     rax, [rdi+18h]
0x18000b77a  mov     rcx, [rbx+18h]
0x18000b77e  mov     [rbx+18h], rax
0x18000b782  mov     [rdi+18h], rcx
0x18000b786  mov     rax, [rdi+20h]
0x18000b78a  mov     rcx, [rbx+20h]
0x18000b78e  mov     [rbx+20h], rax
0x18000b792  mov     [rdi+20h], rcx
0x18000b796  mov     rax, [rdi+28h]
0x18000b79a  mov     rcx, [rbx+28h]
0x18000b79e  mov     [rbx+28h], rax
0x18000b7a2  mov     [rdi+28h], rcx
0x18000b7a6  mov     rax, [rdi+30h]
0x18000b7aa  mov     rcx, [rbx+30h]
0x18000b7ae  mov     [rbx+30h], rax
0x18000b7b2  mov     [rdi+30h], rcx
0x18000b7b6  mov     rax, [rdi+38h]
0x18000b7ba  mov     rcx, [rbx+38h]
0x18000b7be  mov     [rbx+38h], rax
0x18000b7c2  mov     [rdi+38h], rcx
0x18000b7c6  mov     rax, rbx
0x18000b7c9  mov     rbx, [rsp+28h+arg_0]
0x18000b7ce  add     rsp, 20h
0x18000b7d2  pop     rdi
0x18000b7d3  retn
```

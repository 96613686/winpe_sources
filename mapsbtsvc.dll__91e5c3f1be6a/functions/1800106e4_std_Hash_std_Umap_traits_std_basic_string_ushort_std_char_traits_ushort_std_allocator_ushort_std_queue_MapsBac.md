# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>,void *> * const,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>,void *> * const)

- ea: `0x1800106e4`
- end: `0x180010733`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `79`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a460`
- `0x18000a564`
- `0x18000a6d8`
- `0x18000a9b8`
- `0x18000aab8`

## callees

- `0x1800106e4`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r10
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r11

  v4 = *(_QWORD **)(a3 + 8);
  ++a1[2];
  *a4 = a3;
  a4[1] = v4;
  *v4 = a4;
  *(_QWORD *)(a3 + 8) = a4;
  v5 = a2 & a1[6];
  v6 = a1[3];
  v7 = 2 * v5;
  v8 = *(_QWORD *)(v6 + 8 * v7);
  if ( v8 == a1[1] )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
LABEL_6:
    *(_QWORD *)(v6 + 8 * v7 + 8) = a4;
    return a4;
  }
  if ( v8 == a3 )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
  }
  else if ( *(_QWORD **)(v6 + 8 * v7 + 8) == v4 )
  {
    goto LABEL_6;
  }
  return a4;
}

```

## disassembly

```asm
0x1800106e4  mov     r10, [r8+8]
0x1800106e8  inc     qword ptr [rcx+10h]
0x1800106ec  mov     [r9], r8
0x1800106ef  mov     [r9+8], r10
0x1800106f3  mov     [r10], r9
0x1800106f6  mov     [r8+8], r9
0x1800106fa  mov     rax, [rcx+30h]
0x1800106fe  and     rax, rdx
0x180010701  mov     rdx, [rcx+18h]
0x180010705  add     rax, rax
0x180010708  mov     r11, [rdx+rax*8]
0x18001070c  cmp     r11, [rcx+8]
0x180010710  jnz     short loc_180010718
0x180010712  mov     [rdx+rax*8], r9
0x180010716  jmp     short loc_18001072A
0x180010718  cmp     r11, r8
0x18001071b  jnz     short loc_180010723
0x18001071d  mov     [rdx+rax*8], r9
0x180010721  jmp     short loc_18001072F
0x180010723  cmp     [rdx+rax*8+8], r10
0x180010728  jnz     short loc_18001072F
0x18001072a  mov     [rdx+rax*8+8], r9
0x18001072f  mov     rax, r9
0x180010732  retn
```

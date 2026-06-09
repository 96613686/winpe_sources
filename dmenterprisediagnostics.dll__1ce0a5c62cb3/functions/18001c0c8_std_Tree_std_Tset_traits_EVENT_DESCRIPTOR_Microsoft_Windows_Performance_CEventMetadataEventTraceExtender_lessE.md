# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Lower_bound_duplicate<_EVENT_DESCRIPTOR>(std::_Tree_node<_EVENT_DESCRIPTOR,void *> * const,_EVENT_DESCRIPTOR const &)

- ea: `0x18001c0c8`
- end: `0x18001c0f0`
- name: `??$_Lower_bound_duplicate@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `40`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bb78`
- `0x18001d360`

## callees

- `0x18001c0c8`
- `0x18001cc88`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Lower_bound_duplicate<_EVENT_DESCRIPTOR>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  return !*(_BYTE *)(a2 + 25)
      && !(unsigned __int8)Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR::operator()(
                             a1,
                             a3);
}

```

## disassembly

```asm
0x18001c0c8  sub     rsp, 28h
0x18001c0cc  cmp     byte ptr [rdx+19h], 0
0x18001c0d0  mov     rax, r8
0x18001c0d3  jnz     short loc_18001C0E9
0x18001c0d5  lea     r8, [rdx+20h]
0x18001c0d9  mov     rdx, rax
0x18001c0dc  call    ??RlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEBA_NAEBU_EVENT_DESCRIPTOR@@0@Z; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR::operator()(_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x18001c0e1  test    al, al
0x18001c0e3  jnz     short loc_18001C0E9
0x18001c0e5  mov     al, 1
0x18001c0e7  jmp     short loc_18001C0EB
0x18001c0e9  xor     al, al
0x18001c0eb  add     rsp, 28h
0x18001c0ef  retn
```

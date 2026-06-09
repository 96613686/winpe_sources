# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(_EVENT_DESCRIPTOR const &)

- ea: `0x18001bf4c`
- end: `0x18001bfa7`
- name: `??$_Find_lower_bound@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `91`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bb78`
- `0x18001d360`

## callees

- `0x18001bf4c`
- `0x18001cc88`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(
        __int64 *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r10
  int v3; // r9d
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 *v6; // rcx
  int v7; // eax

  v2 = a2;
  *a2 = *(_QWORD *)(*a1 + 8);
  LOBYTE(v3) = 0;
  a2[1] = 0;
  v4 = *a1;
  v5 = *a2;
  a2[2] = v4;
  while ( *(_BYTE *)(v5 + 25) == (_BYTE)v3 )
  {
    *v2 = v5;
    if ( (unsigned __int8)Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR::operator()(
                            v5,
                            v5 + 32) )
    {
      v6 += 2;
      v7 = v3;
    }
    else
    {
      v2[2] = v6;
      v7 = 1;
    }
    *((_DWORD *)v2 + 2) = v7;
    v5 = *v6;
  }
  return v2;
}

```

## disassembly

```asm
0x18001bf4c  sub     rsp, 28h
0x18001bf50  mov     rax, [rcx]
0x18001bf53  mov     r10, rdx
0x18001bf56  mov     r9, [rax+8]
0x18001bf5a  mov     [rdx], r9
0x18001bf5d  xor     r9d, r9d
0x18001bf60  mov     [rdx+8], r9
0x18001bf64  mov     rax, [rcx]
0x18001bf67  mov     rcx, [rdx]
0x18001bf6a  mov     [rdx+10h], rax
0x18001bf6e  jmp     short loc_18001BF99
0x18001bf70  lea     rdx, [rcx+20h]
0x18001bf74  mov     [r10], rcx
0x18001bf77  call    ??RlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEBA_NAEBU_EVENT_DESCRIPTOR@@0@Z; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR::operator()(_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x18001bf7c  test    al, al
0x18001bf7e  jz      short loc_18001BF89
0x18001bf80  add     rcx, 10h
0x18001bf84  mov     eax, r9d
0x18001bf87  jmp     short loc_18001BF92
0x18001bf89  mov     [r10+10h], rcx
0x18001bf8d  mov     eax, 1
0x18001bf92  mov     [r10+8], eax
0x18001bf96  mov     rcx, [rcx]
0x18001bf99  cmp     [rcx+19h], r9b
0x18001bf9d  jz      short loc_18001BF70
0x18001bf9f  mov     rax, r10
0x18001bfa2  add     rsp, 28h
0x18001bfa6  retn
```

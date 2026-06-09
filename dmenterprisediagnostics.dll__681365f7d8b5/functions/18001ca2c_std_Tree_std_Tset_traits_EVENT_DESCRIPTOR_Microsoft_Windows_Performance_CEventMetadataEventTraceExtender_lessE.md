# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(_EVENT_DESCRIPTOR const &)

- ea: `0x18001ca2c`
- end: `0x18001ca88`
- name: `??$_Find_lower_bound@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c664`
- `0x18001de90`

## callees

- `0x18001ca2c`
- `0x18001d788`

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
0x18001ca2c  sub     rsp, 28h
0x18001ca30  mov     rax, [rcx]
0x18001ca33  mov     r10, rdx
0x18001ca36  mov     r9, [rax+8]
0x18001ca3a  mov     [rdx], r9
0x18001ca3d  xor     r9d, r9d
0x18001ca40  mov     [rdx+8], r9
0x18001ca44  mov     rax, [rcx]
0x18001ca47  mov     rcx, [rdx]
0x18001ca4a  mov     [rdx+10h], rax
0x18001ca4e  jmp     short loc_18001CA79
0x18001ca50  lea     rdx, [rcx+20h]
0x18001ca54  mov     [r10], rcx
0x18001ca57  call    ??RlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEBA_NAEBU_EVENT_DESCRIPTOR@@0@Z; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR::operator()(_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x18001ca5c  test    al, al
0x18001ca5e  jz      short loc_18001CA69
0x18001ca60  add     rcx, 10h
0x18001ca64  mov     eax, r9d
0x18001ca67  jmp     short loc_18001CA72
0x18001ca69  mov     [r10+10h], rcx
0x18001ca6d  mov     eax, 1
0x18001ca72  mov     [r10+8], eax
0x18001ca76  mov     rcx, [rcx]
0x18001ca79  cmp     [rcx+19h], r9b
0x18001ca7d  jz      short loc_18001CA50
0x18001ca7f  mov     rax, r10
0x18001ca82  add     rsp, 28h
0x18001ca86  retn
```

# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x180018014`
- end: `0x1800180a3`
- name: `?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011bfc`
- `0x180011e80`

## callees

- `0x18000181c`
- `0x180010a5c`
- `0x180011550`
- `0x180018014`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001803a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001803a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(
        _QWORD *a1,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-30h]

  if ( a1[1] == 0x199999999999999LL )
    std::_Xlength_error("list too long");
  v4 = *a1;
  v7 = a1;
  v5 = operator new(0xA0u);
  v8 = v5;
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
    (Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v5 + 2),
    a2);
  ++a1[1];
  v6 = *(_QWORD **)(v4 + 8);
  *v5 = v4;
  v5[1] = v6;
  v8 = 0;
  *(_QWORD *)(v4 + 8) = v5;
  *v6 = v5;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>((__int64)&v7);
}

```

## disassembly

```asm
0x180018014  push    rbx
0x180018016  push    rbp
0x180018017  push    rsi
0x180018018  push    rdi
0x180018019  sub     rsp, 38h
0x18001801d  mov     rbp, rdx
0x180018020  mov     rsi, rcx
0x180018023  mov     rax, 199999999999999h
0x18001802d  cmp     [rcx+8], rax
0x180018031  jnz     short loc_180018041
0x180018033  lea     rcx, aListTooLong; "list too long"
0x18001803a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018041  mov     rdi, [rcx]
0x180018044  mov     [rsp+58h+var_38], rsi
0x180018049  mov     [rsp+58h+var_30], 0
0x180018052  mov     ecx, 0A0h; Size
0x180018057  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001805c  mov     rbx, rax
0x18001805f  mov     [rsp+58h+var_30], rax
0x180018064  lea     rcx, [rax+10h]; this
0x180018068  mov     rdx, rbp; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x18001806b  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x180018070  nop
0x180018071  inc     qword ptr [rsi+8]
0x180018075  mov     rcx, [rdi+8]
0x180018079  mov     [rbx], rdi
0x18001807c  mov     [rbx+8], rcx
0x180018080  mov     [rsp+58h+var_30], 0
0x180018089  mov     [rdi+8], rbx
0x18001808d  mov     [rcx], rbx
0x180018090  lea     rcx, [rsp+58h+var_38]
0x180018095  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
0x18001809a  add     rsp, 38h
0x18001809e  pop     rdi
0x18001809f  pop     rsi
0x1800180a0  pop     rbp
0x1800180a1  pop     rbx
0x1800180a2  retn
```

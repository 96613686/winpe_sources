# std::list<PIXEventsThreadInfo,std::allocator<PIXEventsThreadInfo>>::_Emplace<>(std::_List_node<PIXEventsThreadInfo,void *> * const)

- ea: `0x180011934`
- end: `0x1800119c7`
- name: `??$_Emplace@$$V@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAAPEAU?$_List_node@UPIXEventsThreadInfo@@PEAX@1@QEAU21@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800119d0`

## callees

- `0x18000b828`
- `0x180011934`
- `0x180011a94`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001195b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001195b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall std::list<PIXEventsThreadInfo>::_Emplace<>(__int64 a1, __int64 a2)
{
  _OWORD *v3; // rbx
  _QWORD *v4; // rcx
  __int64 *v6; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+28h] [rbp-10h]

  if ( qword_18001E8A8 == 0x666666666666666LL )
    std::_Xlength_error("list too long");
  v6 = &qword_18001E8A0;
  v7 = 0;
  v3 = operator new(0x28u);
  v3[1] = 0;
  *((_QWORD *)v3 + 4) = 0;
  ++qword_18001E8A8;
  v4 = *(_QWORD **)(a2 + 8);
  *(_QWORD *)v3 = a2;
  *((_QWORD *)v3 + 1) = v4;
  v7 = 0;
  *(_QWORD *)(a2 + 8) = v3;
  *v4 = v3;
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>(&v6);
  return v3;
}

```

## disassembly

```asm
0x180011934  mov     [rsp+arg_0], rbx
0x180011939  push    rdi
0x18001193a  sub     rsp, 30h
0x18001193e  mov     rdi, rdx
0x180011941  mov     rax, 666666666666666h
0x18001194b  cmp     cs:qword_18001E8A8, rax
0x180011952  jnz     short loc_180011962
0x180011954  lea     rcx, aListTooLong; "list too long"
0x18001195b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011962  lea     rax, qword_18001E8A0
0x180011969  mov     [rsp+38h+var_18], rax
0x18001196e  mov     [rsp+38h+var_10], 0
0x180011977  mov     ecx, 28h ; '('; Size
0x18001197c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011981  mov     rbx, rax
0x180011984  xorps   xmm0, xmm0
0x180011987  xor     eax, eax
0x180011989  movups  xmmword ptr [rbx+10h], xmm0
0x18001198d  mov     [rbx+20h], rax
0x180011991  inc     cs:qword_18001E8A8
0x180011998  mov     rcx, [rdi+8]
0x18001199c  mov     [rbx], rdi
0x18001199f  mov     [rbx+8], rcx
0x1800119a3  mov     [rsp+38h+var_10], rax
0x1800119a8  mov     [rdi+8], rbx
0x1800119ac  mov     [rcx], rbx
0x1800119af  lea     rcx, [rsp+38h+var_18]
0x1800119b4  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UPIXEventsThreadInfo@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>(void)
0x1800119b9  mov     rax, rbx
0x1800119bc  mov     rbx, [rsp+38h+arg_0]
0x1800119c1  add     rsp, 30h
0x1800119c5  pop     rdi
0x1800119c6  retn
```

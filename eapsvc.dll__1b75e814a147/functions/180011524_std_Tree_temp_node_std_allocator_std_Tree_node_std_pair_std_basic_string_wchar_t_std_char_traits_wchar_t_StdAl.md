# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(void)

- ea: `0x180011524`
- end: `0x180011595`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001129c`

## callees

- `0x180002330`
- `0x18000ab70`
- `0x180011524`
- `0x180017010`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(_QWORD *)(v2 + 64);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    if ( *(_QWORD *)(v2 + 56) > 7u )
      operator delete(*(LPCVOID *)(v2 + 32));
    *(_QWORD *)(v2 + 48) = 0;
    *(_QWORD *)(v2 + 56) = 7;
    *(_WORD *)(v2 + 32) = 0;
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    operator delete(v4, 0x48u);
}

```

## disassembly

```asm
0x180011524  mov     [rsp+arg_0], rbx
0x180011529  push    rdi
0x18001152a  sub     rsp, 20h
0x18001152e  mov     rdi, rcx
0x180011531  mov     rbx, [rcx+8]
0x180011535  test    rbx, rbx
0x180011538  jz      short loc_180011576
0x18001153a  mov     rcx, [rbx+40h]
0x18001153e  test    rcx, rcx
0x180011541  jz      short loc_180011550
0x180011543  mov     rax, [rcx]
0x180011546  mov     rax, [rax+10h]
0x18001154a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154f  nop
0x180011550  cmp     qword ptr [rbx+38h], 7
0x180011555  jbe     short loc_180011560
0x180011557  mov     rcx, [rbx+20h]; lpMem
0x18001155b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011560  mov     qword ptr [rbx+30h], 0
0x180011568  mov     qword ptr [rbx+38h], 7
0x180011570  xor     eax, eax
0x180011572  mov     [rbx+20h], ax
0x180011576  mov     rcx, [rdi+8]; void *
0x18001157a  test    rcx, rcx
0x18001157d  jz      short loc_18001158A
0x18001157f  mov     edx, 48h ; 'H'; unsigned __int64
0x180011584  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011589  nop
0x18001158a  mov     rbx, [rsp+28h+arg_0]
0x18001158f  add     rsp, 20h
0x180011593  pop     rdi
0x180011594  retn
```

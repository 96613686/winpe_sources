# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>,void *>>>(void)

- ea: `0x18000eb84`
- end: `0x18000eba0`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800162f0`

## callees

- `0x180001bb4`
- `0x18000eb84`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000eb84  sub     rsp, 28h
0x18000eb88  mov     rcx, [rcx+8]; Block
0x18000eb8c  test    rcx, rcx
0x18000eb8f  jz      short loc_18000EB9B
0x18000eb91  mov     edx, 68h ; 'h'
0x18000eb96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eb9b  add     rsp, 28h
0x18000eb9f  retn
```

# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>>>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<AttestationResultType const,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>>>>,void *>>>(void)

- ea: `0x18000ebcc`
- end: `0x18000ebe8`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800163a4`

## callees

- `0x180001bb4`
- `0x18000ebcc`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,void *>>>(
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
0x18000ebcc  sub     rsp, 28h
0x18000ebd0  mov     rcx, [rcx+8]; Block
0x18000ebd4  test    rcx, rcx
0x18000ebd7  jz      short loc_18000EBE3
0x18000ebd9  mov     edx, 38h ; '8'
0x18000ebde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ebe3  add     rsp, 28h
0x18000ebe7  retn
```

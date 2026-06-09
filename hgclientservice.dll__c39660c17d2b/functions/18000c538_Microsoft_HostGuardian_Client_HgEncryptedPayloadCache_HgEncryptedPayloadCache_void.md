# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::~HgEncryptedPayloadCache(void)

- ea: `0x18000c538`
- end: `0x18000c56b`
- name: `??1HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@UEAA@XZ`
- size: `51`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015dc5`
- `0x180015eb6`

## callees

- `0x180004274`
- `0x18000bd7c`
- `0x18000c1d8`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::~HgEncryptedPayloadCache(
        Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *this)
{
  *(_QWORD *)this = &Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>((char **)this + 8);
  std::list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>((void **)this + 6);
  std::wstring::~wstring((char **)this + 1);
}

```

## disassembly

```asm
0x18000c538  push    rbx
0x18000c53a  sub     rsp, 20h
0x18000c53e  lea     rax, ??_7HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable'
0x18000c545  mov     rbx, rcx
0x18000c548  mov     [rcx], rax
0x18000c54b  add     rcx, 40h ; '@'
0x18000c54f  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>(void)
0x18000c554  lea     rcx, [rbx+30h]
0x18000c558  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>(void)
0x18000c55d  lea     rcx, [rbx+8]
0x18000c561  add     rsp, 20h
0x18000c565  pop     rbx
0x18000c566  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```

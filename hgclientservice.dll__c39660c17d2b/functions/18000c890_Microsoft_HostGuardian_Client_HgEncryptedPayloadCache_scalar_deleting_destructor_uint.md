# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`scalar deleting destructor'(uint)

- ea: `0x18000c890`
- end: `0x18000c8e4`
- name: `??_GHgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@UEAAPEAXI@Z`
- size: `84`
- prototype: `Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *__fastcall(Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *this, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180004274`
- `0x18000bd7c`
- `0x18000c1d8`
- `0x18000c890`

## pseudocode

```c
Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *__fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`scalar deleting destructor'(
        Microsoft::HostGuardian::Client::HgEncryptedPayloadCache *this,
        char a2)
{
  *(_QWORD *)this = &Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>((char **)this + 8);
  std::list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>((void **)this + 6);
  std::wstring::~wstring((char **)this + 1);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c890  mov     [rsp+arg_0], rbx
0x18000c895  push    rdi
0x18000c896  sub     rsp, 20h
0x18000c89a  lea     rax, ??_7HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable'
0x18000c8a1  mov     rdi, rcx
0x18000c8a4  mov     [rcx], rax
0x18000c8a7  mov     ebx, edx
0x18000c8a9  add     rcx, 40h ; '@'
0x18000c8ad  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>(void)
0x18000c8b2  lea     rcx, [rdi+30h]
0x18000c8b6  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>(void)
0x18000c8bb  lea     rcx, [rdi+8]
0x18000c8bf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c8c4  test    bl, 1
0x18000c8c7  jz      short loc_18000C8D6
0x18000c8c9  mov     edx, 70h ; 'p'
0x18000c8ce  mov     rcx, rdi; Block
0x18000c8d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c8d6  mov     rbx, [rsp+28h+arg_0]
0x18000c8db  mov     rax, rdi
0x18000c8de  add     rsp, 20h
0x18000c8e2  pop     rdi
0x18000c8e3  retn
```

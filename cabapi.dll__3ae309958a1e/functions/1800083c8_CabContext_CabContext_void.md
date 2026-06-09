# CabContext::~CabContext(void)

- ea: `0x1800083c8`
- end: `0x18000840c`
- name: `??1CabContext@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CabContext *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013fca`
- `0x180014024`
- `0x180014090`
- `0x180014144`
- `0x180014156`

## callees

- `0x180003648`
- `0x1800081d8`
- `0x180008248`

## pseudocode

```c
void __fastcall CabContext::~CabContext(CabContext *this)
{
  std::wstring::~wstring((char **)this + 16);
  std::wstring::~wstring((char **)this + 12);
  std::wstring::~wstring((char **)this + 8);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)this + 6);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((void **)this + 4);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((void **)this + 2);
}

```

## disassembly

```asm
0x1800083c8  push    rbx
0x1800083ca  sub     rsp, 20h
0x1800083ce  mov     rbx, rcx
0x1800083d1  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800083d5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800083da  lea     rcx, [rbx+60h]
0x1800083de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800083e3  lea     rcx, [rbx+40h]
0x1800083e7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800083ec  lea     rcx, [rbx+30h]
0x1800083f0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800083f5  lea     rcx, [rbx+20h]
0x1800083f9  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800083fe  lea     rcx, [rbx+10h]
0x180008402  add     rsp, 20h
0x180008406  pop     rbx
0x180008407  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
```

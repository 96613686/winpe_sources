# CNfsXmlParser::~CNfsXmlParser(void)

- ea: `0x18001cf20`
- end: `0x18001cfbf`
- name: `??1CNfsXmlParser@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CNfsXmlParser *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020b64`
- `0x1800369f4`

## callees

- `0x180009888`
- `0x18000e74c`
- `0x18001cdcc`
- `0x18001ce80`
- `0x18001cf20`
- `0x18001cfc8`
- `0x18001d014`
- `0x1800213d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001cf6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cf6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNfsXmlParser::~CNfsXmlParser(CNfsXmlParser *this)
{
  _QWORD *v2; // rbx
  CNfsXmlSharePermission **v3; // rax
  CNfsXmlSharePermission *v4; // rsi
  _QWORD v5[5]; // [rsp+20h] [rbp-28h] BYREF
  CNfsXmlSharePermission **v6; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD **)this;
  while ( 1 )
  {
    v2 = (_QWORD *)*v2;
    if ( v2 == *(_QWORD **)this )
      break;
    std::vector<CNfsXmlSharePermission *>::vector<CNfsXmlSharePermission *>(v5, v2 + 6);
    v3 = (CNfsXmlSharePermission **)v5[0];
    v6 = (CNfsXmlSharePermission **)v5[0];
    while ( v3 != (CNfsXmlSharePermission **)v5[1] )
    {
      v4 = *v3;
      if ( *v3 )
      {
        CNfsXmlSharePermission::~CNfsXmlSharePermission(*v3);
        operator delete(v4);
      }
      std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CNfsXmlSharePermission *>>>::operator++(&v6);
      v3 = v6;
    }
    std::vector<CNfsXmlSharePermission *>::_Tidy(v5);
  }
  std::list<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>::clear(this);
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::_Init(
    this,
    8);
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>(this);
}

```

## disassembly

```asm
0x18001cf20  mov     [rsp+arg_8], rbx
0x18001cf25  mov     [rsp+arg_10], rsi
0x18001cf2a  push    rdi
0x18001cf2b  sub     rsp, 40h
0x18001cf2f  mov     rdi, rcx
0x18001cf32  mov     rbx, [rcx]
0x18001cf35  mov     rbx, [rbx]
0x18001cf38  cmp     rbx, [rdi]
0x18001cf3b  jz      short loc_18001CF92
0x18001cf3d  lea     rdx, [rbx+30h]
0x18001cf41  lea     rcx, [rsp+48h+var_28]
0x18001cf46  call    ??0?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<CNfsXmlSharePermission *>::vector<CNfsXmlSharePermission *>(std::vector<CNfsXmlSharePermission *> const &)
0x18001cf4b  mov     rax, [rsp+48h+var_28]
0x18001cf50  mov     [rsp+48h+arg_0], rax
0x18001cf55  cmp     rax, [rsp+48h+var_20]
0x18001cf5a  jz      short loc_18001CF86
0x18001cf5c  mov     rsi, [rax]
0x18001cf5f  test    rsi, rsi
0x18001cf62  jz      short loc_18001CF75
0x18001cf64  mov     rcx, rsi; this
0x18001cf67  call    ??1CNfsXmlSharePermission@@QEAA@XZ; CNfsXmlSharePermission::~CNfsXmlSharePermission(void)
0x18001cf6c  mov     rcx, rsi
0x18001cf6f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cf75  lea     rcx, [rsp+48h+arg_0]
0x18001cf7a  call    ??E?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCNfsXmlSharePermission@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CNfsXmlSharePermission *>>>::operator++(void)
0x18001cf7f  mov     rax, [rsp+48h+arg_0]
0x18001cf84  jmp     short loc_18001CF55
0x18001cf86  lea     rcx, [rsp+48h+var_28]
0x18001cf8b  call    ?_Tidy@?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@IEAAXXZ; std::vector<CNfsXmlSharePermission *>::_Tidy(void)
0x18001cf90  jmp     short loc_18001CF35
0x18001cf92  mov     rcx, rdi
0x18001cf95  call    ?clear@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@@2@@std@@QEAAXXZ; std::list<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>::clear(void)
0x18001cf9a  mov     edx, 8
0x18001cf9f  mov     rcx, rdi
0x18001cfa2  call    ?_Init@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@@2@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::_Init(unsigned __int64)
0x18001cfa7  nop
0x18001cfa8  mov     rcx, rdi
0x18001cfab  mov     rbx, [rsp+48h+arg_8]
0x18001cfb0  mov     rsi, [rsp+48h+arg_10]
0x18001cfb5  add     rsp, 40h
0x18001cfb9  pop     rdi
0x18001cfba  jmp     ??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>(void)
```

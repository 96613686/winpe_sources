# CNDFHelperClassRegistry::~CNDFHelperClassRegistry(void)

- ea: `0x180005790`
- end: `0x180005866`
- name: `??1CNDFHelperClassRegistry@@QEAA@XZ`
- size: `214`
- prototype: `void __fastcall(CNDFHelperClassRegistry *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180005cf0`

## callees

- `0x1800055d0`
- `0x180005790`
- `0x18000a638`
- `0x18000a6c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800057d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005805`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005832`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005805`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005832`
- `KERNEL32!DeleteCriticalSection` at `0x1800057ae`
- `KERNEL32!DeleteCriticalSection` at `0x18000584d`
- `KERNEL32!DeleteCriticalSection` at `0x1800057ae`
- `KERNEL32!DeleteCriticalSection` at `0x18000584d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNDFHelperClassRegistry::~CNDFHelperClassRegistry(CNDFHelperClassRegistry *this)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CNDFHelperClassRegistry::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  TLinkedListDeallocator<CNDFHelperClass *>::~TLinkedListDeallocator<CNDFHelperClass *>((char *)this + 640);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear((char *)this + 616);
  operator delete(*((void **)this + 77));
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    (char *)this + 600,
    &v2,
    **((_QWORD **)this + 75),
    *((_QWORD *)this + 75));
  operator delete(*((void **)this + 75));
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    (char *)this + 584,
    &v2,
    **((_QWORD **)this + 73),
    *((_QWORD *)this + 73));
  operator delete(*((void **)this + 73));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180005790  mov     [rsp+arg_8], rbx
0x180005795  push    rdi
0x180005796  sub     rsp, 20h
0x18000579a  mov     rdi, rcx
0x18000579d  lea     rax, ??_7CNDFHelperClassRegistry@@6B@; const CNDFHelperClassRegistry::`vftable'
0x1800057a4  mov     [rcx], rax
0x1800057a7  add     rcx, 290h; lpCriticalSection
0x1800057ae  call    cs:__imp_DeleteCriticalSection
0x1800057b5  nop     dword ptr [rax+rax+00h]
0x1800057ba  lea     rcx, [rdi+280h]
0x1800057c1  call    ??1?$TLinkedListDeallocator@PEAVCNDFHelperClass@@@@QEAA@XZ; TLinkedListDeallocator<CNDFHelperClass *>::~TLinkedListDeallocator<CNDFHelperClass *>(void)
0x1800057c6  lea     rbx, [rdi+268h]
0x1800057cd  mov     rcx, rbx
0x1800057d0  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x1800057d5  mov     rcx, [rbx]
0x1800057d8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057df  nop     dword ptr [rax+rax+00h]
0x1800057e4  nop
0x1800057e5  lea     rbx, [rdi+258h]
0x1800057ec  mov     r8, [rbx]
0x1800057ef  mov     r9, r8
0x1800057f2  mov     r8, [r8]
0x1800057f5  lea     rdx, [rsp+28h+arg_0]
0x1800057fa  mov     rcx, rbx
0x1800057fd  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x180005802  mov     rcx, [rbx]
0x180005805  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000580c  nop     dword ptr [rax+rax+00h]
0x180005811  nop
0x180005812  lea     rbx, [rdi+248h]
0x180005819  mov     r8, [rbx]
0x18000581c  mov     r9, r8
0x18000581f  mov     r8, [r8]
0x180005822  lea     rdx, [rsp+28h+arg_0]
0x180005827  mov     rcx, rbx
0x18000582a  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x18000582f  mov     rcx, [rbx]
0x180005832  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005839  nop     dword ptr [rax+rax+00h]
0x18000583e  nop
0x18000583f  lea     rcx, [rdi+10h]; lpCriticalSection
0x180005843  cmp     byte ptr [rcx+28h], 0
0x180005847  jz      short loc_18000585A
0x180005849  mov     byte ptr [rcx+28h], 0
0x18000584d  call    cs:__imp_DeleteCriticalSection
0x180005854  nop     dword ptr [rax+rax+00h]
0x180005859  nop
0x18000585a  mov     rbx, [rsp+28h+arg_8]
0x18000585f  add     rsp, 20h
0x180005863  pop     rdi
0x180005864  retn
```

# CNDFHelperClassRegistry::InitializeData(void)

- ea: `0x180007a20`
- end: `0x180007c48`
- name: `?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180007260`
- `0x180007440`
- `0x180007520`
- `0x1800075c0`
- `0x180007750`

## callees

- `0x180007a20`
- `0x180009fcc`
- `0x18000a00c`
- `0x18000a638`
- `0x18000a6c0`
- `0x18000cb80`
- `0x180011a10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007b9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bb2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bd7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007c27`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007b9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bb2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bd7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007c27`
- `ADVAPI32!RegCloseKey` at `0x180007adc`
- `ADVAPI32!RegCloseKey` at `0x180007adc`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CNDFHelperClassRegistry::InitializeData(CNDFHelperClassRegistry *this)
{
  __int64 *v2; // rsi
  LSTATUS v3; // r14d
  void **v4; // rdx
  _QWORD *v5; // rcx
  __int64 v6; // rcx
  void **v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  void **v10; // rdx
  void *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  CNDFHelperClass *v14; // rdi
  void *v15; // rcx
  _QWORD *v17; // [rsp+30h] [rbp-59h] BYREF
  __int64 v18; // [rsp+38h] [rbp-51h]
  _QWORD *v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h]
  void *v21; // [rsp+50h] [rbp-39h] BYREF
  __int64 v22; // [rsp+58h] [rbp-31h]
  HKEY hKey[3]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v24[13]; // [rsp+78h] [rbp-11h] BYREF
  char v25; // [rsp+F0h] [rbp+67h] BYREF

  v20 = 0;
  v19 = (_QWORD *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode();
  v18 = 0;
  v17 = (_QWORD *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode();
  v22 = 0;
  v21 = (void *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
  v24[4] = 0;
  v24[6] = 0;
  v24[5] = -2147483646;
  v24[0] = &v19;
  v24[1] = &v17;
  v24[2] = &v21;
  v2 = (__int64 *)((char *)this + 640);
  v24[3] = (char *)this + 640;
  hKey[0] = HKEY_LOCAL_MACHINE;
  hKey[1] = 0;
  hKey[2] = 0;
  v3 = RegUtilIterateThroughKeys(
         hKey,
         (const unsigned __int16 *)this + 32,
         0,
         (int (*)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *))NDFRegistryInitKeyCallback,
         v24);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v3 < 0 )
  {
    v13 = *v2;
    while ( v13 )
    {
      v14 = *(CNDFHelperClass **)v13;
      if ( *(_QWORD *)v13 )
      {
        CNDFHelperClass::~CNDFHelperClass(*(CNDFHelperClass **)v13);
        operator delete(v14);
      }
      v15 = (void *)v13;
      v13 = *(_QWORD *)(v13 + 8);
      operator delete(v15);
    }
    *v2 = 0;
    v2[1] = 0;
  }
  else
  {
    v4 = (void **)((char *)this + 584);
    if ( (_QWORD **)((char *)this + 584) != &v19 )
    {
      v5 = *v4;
      *v4 = v19;
      v19 = v5;
      v6 = *((_QWORD *)this + 74);
      *((_QWORD *)this + 74) = v20;
      v20 = v6;
    }
    v7 = (void **)((char *)this + 600);
    if ( (_QWORD **)((char *)this + 600) != &v17 )
    {
      v8 = *v7;
      *v7 = v17;
      v17 = v8;
      v9 = *((_QWORD *)this + 76);
      *((_QWORD *)this + 76) = v18;
      v18 = v9;
    }
    v10 = (void **)((char *)this + 616);
    if ( (void **)((char *)this + 616) != &v21 )
    {
      v11 = *v10;
      *v10 = v21;
      v21 = v11;
      v12 = *((_QWORD *)this + 78);
      *((_QWORD *)this + 78) = v22;
      v22 = v12;
    }
    *((_DWORD *)this + 158) = 1;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(&v21);
  operator delete(v21);
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    &v17,
    &v25,
    *v17,
    v17);
  operator delete(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    &v19,
    &v25,
    *v19,
    v19);
  operator delete(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007a20  push    rbp
0x180007a22  push    rbx
0x180007a23  push    rsi
0x180007a24  push    rdi
0x180007a25  push    r14
0x180007a27  push    r15
0x180007a29  lea     rbp, [rsp-2Fh]
0x180007a2e  sub     rsp, 0B8h
0x180007a35  mov     rbx, rcx
0x180007a38  xor     r15d, r15d
0x180007a3b  mov     [rbp+57h+var_A0], r15
0x180007a3f  mov     [rbp+57h+var_98], r15
0x180007a43  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode(void)
0x180007a48  mov     [rbp+57h+var_A0], rax
0x180007a4c  mov     [rbp+57h+var_B0], r15
0x180007a50  mov     [rbp+57h+var_A8], r15
0x180007a54  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode(void)
0x180007a59  mov     [rbp+57h+var_B0], rax
0x180007a5d  mov     [rbp+57h+var_90], r15
0x180007a61  mov     [rbp+57h+var_88], r15
0x180007a65  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x180007a6a  mov     [rbp+57h+var_90], rax
0x180007a6e  mov     [rbp+57h+var_48], r15
0x180007a72  mov     [rbp+57h+var_38], r15
0x180007a76  mov     rcx, 0FFFFFFFF80000002h
0x180007a7d  mov     [rbp+57h+var_40], rcx
0x180007a81  lea     rax, [rbp+57h+var_A0]
0x180007a85  mov     [rbp+57h+var_68], rax
0x180007a89  lea     rax, [rbp+57h+var_B0]
0x180007a8d  mov     [rbp+57h+var_60], rax
0x180007a91  lea     rax, [rbp+57h+var_90]
0x180007a95  mov     [rbp+57h+var_58], rax
0x180007a99  lea     rsi, [rbx+280h]
0x180007aa0  mov     [rbp+57h+var_50], rsi
0x180007aa4  mov     [rbp+57h+hKey], rcx
0x180007aa8  mov     [rbp+57h+var_78], r15
0x180007aac  mov     [rbp+57h+var_70], r15
0x180007ab0  lea     rdx, [rbx+40h]; unsigned __int16 *
0x180007ab4  lea     rax, [rbp+57h+var_68]
0x180007ab8  mov     [rsp+0E0h+var_C0], rax; void *
0x180007abd  lea     r9, ?NDFRegistryInitKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z; int (*)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)
0x180007ac4  xor     r8d, r8d; unsigned __int16 *
0x180007ac7  lea     rcx, [rbp+57h+hKey]; struct ATL::CRegKey *
0x180007acb  call    ?RegUtilIterateThroughKeys@@YAJAEAVCRegKey@ATL@@PEBG1P6AJ011PEAX@Z2@Z; RegUtilIterateThroughKeys(ATL::CRegKey &,ushort const *,ushort const *,long (*)(ATL::CRegKey &,ushort const *,ushort const *,void *),void *)
0x180007ad0  mov     r14d, eax
0x180007ad3  mov     rcx, [rbp+57h+hKey]; hKey
0x180007ad7  test    rcx, rcx
0x180007ada  jz      short loc_180007AE8
0x180007adc  call    cs:__imp_RegCloseKey
0x180007ae3  nop     dword ptr [rax+rax+00h]
0x180007ae8  test    r14d, r14d
0x180007aeb  js      loc_180007B87
0x180007af1  lea     rdx, [rbx+248h]
0x180007af8  lea     rax, [rbp+57h+var_A0]
0x180007afc  cmp     rdx, rax
0x180007aff  jz      short loc_180007B1F
0x180007b01  mov     rcx, [rdx]
0x180007b04  mov     rax, [rbp+57h+var_A0]
0x180007b08  mov     [rdx], rax
0x180007b0b  mov     [rbp+57h+var_A0], rcx
0x180007b0f  mov     rcx, [rdx+8]
0x180007b13  mov     rax, [rbp+57h+var_98]
0x180007b17  mov     [rdx+8], rax
0x180007b1b  mov     [rbp+57h+var_98], rcx
0x180007b1f  lea     rdx, [rbx+258h]
0x180007b26  lea     rax, [rbp+57h+var_B0]
0x180007b2a  cmp     rdx, rax
0x180007b2d  jz      short loc_180007B4D
0x180007b2f  mov     rcx, [rdx]
0x180007b32  mov     rax, [rbp+57h+var_B0]
0x180007b36  mov     [rdx], rax
0x180007b39  mov     [rbp+57h+var_B0], rcx
0x180007b3d  mov     rcx, [rdx+8]
0x180007b41  mov     rax, [rbp+57h+var_A8]
0x180007b45  mov     [rdx+8], rax
0x180007b49  mov     [rbp+57h+var_A8], rcx
0x180007b4d  lea     rdx, [rbx+268h]
0x180007b54  lea     rax, [rbp+57h+var_90]
0x180007b58  cmp     rdx, rax
0x180007b5b  jz      short loc_180007B7B
0x180007b5d  mov     rcx, [rdx]
0x180007b60  mov     rax, [rbp+57h+var_90]
0x180007b64  mov     [rdx], rax
0x180007b67  mov     [rbp+57h+var_90], rcx
0x180007b6b  mov     rcx, [rdx+8]
0x180007b6f  mov     rax, [rbp+57h+var_88]
0x180007b73  mov     [rdx+8], rax
0x180007b77  mov     [rbp+57h+var_88], rcx
0x180007b7b  mov     dword ptr [rbx+278h], 1
0x180007b85  jmp     short loc_180007BCA
0x180007b87  mov     rbx, [rsi]
0x180007b8a  jmp     short loc_180007BBE
0x180007b8c  mov     rdi, [rbx]
0x180007b8f  test    rdi, rdi
0x180007b92  jz      short loc_180007BAB
0x180007b94  mov     rcx, rdi; this
0x180007b97  call    ??1CNDFHelperClass@@QEAA@XZ; CNDFHelperClass::~CNDFHelperClass(void)
0x180007b9c  mov     rcx, rdi
0x180007b9f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ba6  nop     dword ptr [rax+rax+00h]
0x180007bab  mov     rcx, rbx
0x180007bae  mov     rbx, [rbx+8]
0x180007bb2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007bb9  nop     dword ptr [rax+rax+00h]
0x180007bbe  test    rbx, rbx
0x180007bc1  jnz     short loc_180007B8C
0x180007bc3  mov     [rsi], r15
0x180007bc6  mov     [rsi+8], r15
0x180007bca  lea     rcx, [rbp+57h+var_90]
0x180007bce  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x180007bd3  mov     rcx, [rbp+57h+var_90]
0x180007bd7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007bde  nop     dword ptr [rax+rax+00h]
0x180007be3  nop
0x180007be4  mov     r8, [rbp+57h+var_B0]
0x180007be8  mov     r9, r8
0x180007beb  mov     r8, [r8]
0x180007bee  lea     rdx, [rbp+57h+arg_0]
0x180007bf2  lea     rcx, [rbp+57h+var_B0]
0x180007bf6  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x180007bfb  mov     rcx, [rbp+57h+var_B0]
0x180007bff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007c06  nop     dword ptr [rax+rax+00h]
0x180007c0b  nop
0x180007c0c  mov     r8, [rbp+57h+var_A0]
0x180007c10  mov     r9, r8
0x180007c13  mov     r8, [r8]
0x180007c16  lea     rdx, [rbp+57h+arg_0]
0x180007c1a  lea     rcx, [rbp+57h+var_A0]
0x180007c1e  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x180007c23  mov     rcx, [rbp+57h+var_A0]
0x180007c27  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007c2e  nop     dword ptr [rax+rax+00h]
0x180007c33  nop
0x180007c34  mov     eax, r14d
0x180007c37  add     rsp, 0B8h
0x180007c3e  pop     r15
0x180007c40  pop     r14
0x180007c42  pop     rdi
0x180007c43  pop     rsi
0x180007c44  pop     rbx
0x180007c45  pop     rbp
0x180007c46  retn
```

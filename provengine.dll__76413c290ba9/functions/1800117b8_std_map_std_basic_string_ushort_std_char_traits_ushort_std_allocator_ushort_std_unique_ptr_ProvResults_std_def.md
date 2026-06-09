# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>>::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800117b8`
- end: `0x180011917`
- name: `??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `351`
- prototype: `__int64 *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001a6fc`

## callees

- `0x18000af20`
- `0x18000c408`
- `0x18000dbac`
- `0x180011328`
- `0x1800117b8`
- `0x180022844`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800118df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800118f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800118df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800118f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall std::map<std::wstring,std::unique_ptr<ProvResults>>::operator[](_QWORD *a1, _QWORD *a2)
{
  __int64 *v4; // rbx
  _WORD *v5; // rcx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rax
  _WORD *v9; // rdx
  int v10; // eax
  __int64 v11; // rax
  ProvResults *v12; // rdi
  _QWORD *v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v15; // [rsp+38h] [rbp-38h] BYREF
  void *v16[3]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-18h]
  ProvResults *v18; // [rsp+60h] [rbp-10h]

  std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(
    a1,
    &v14,
    a2);
  v4 = v14;
  if ( v14 == (_QWORD *)*a1 )
    goto LABEL_18;
  if ( v14[7] < 8u )
    v5 = v14 + 4;
  else
    v5 = (_WORD *)v14[4];
  v6 = v14[6];
  v7 = a2[2];
  v8 = v7;
  if ( v7 >= v6 )
    v8 = v14[6];
  v9 = a2[3] < 8u ? a2 : (_WORD *)*a2;
  if ( v8 )
  {
    while ( *v9 == *v5 )
    {
      ++v9;
      ++v5;
      if ( !--v8 )
        goto LABEL_13;
    }
    v10 = *v9 < *v5 ? -1 : 1;
  }
  else
  {
LABEL_13:
    v10 = v7 >= v6 ? v7 != v6 : -1;
  }
  if ( v10 < 0 )
  {
LABEL_18:
    v14 = 0;
    v17 = 7;
    v16[2] = 0;
    LOWORD(v16[0]) = 0;
    std::wstring::assign(v16);
    v14 = 0;
    v18 = 0;
    v11 = std::_Tree_buy<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>::_Buynode<std::pair<std::wstring,std::unique_ptr<ProvResults>>>(
            (__int64)a1,
            (__int64)v16);
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_hint<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(
      a1,
      &v15,
      v4,
      v11 + 32,
      v11);
    v4 = v15;
    v12 = v18;
    if ( v18 )
    {
      ProvResults::~ProvResults(v18);
      operator delete(v12);
    }
    if ( v17 >= 8 )
      operator delete(v16[0]);
  }
  return v4 + 8;
}

```

## disassembly

```asm
0x1800117b8  mov     [rsp-18h+arg_10], rbx
0x1800117bd  push    rbp
0x1800117be  push    rsi
0x1800117bf  push    rdi
0x1800117c0  mov     rbp, rsp
0x1800117c3  sub     rsp, 70h
0x1800117c7  mov     rax, cs:__security_cookie
0x1800117ce  xor     rax, rsp
0x1800117d1  mov     [rbp+var_8], rax
0x1800117d5  mov     rdi, rdx
0x1800117d8  mov     rsi, rcx
0x1800117db  mov     r8, rdx
0x1800117de  lea     rdx, [rbp+var_40]
0x1800117e2  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(std::wstring const &)
0x1800117e7  mov     rbx, [rbp+var_40]
0x1800117eb  cmp     rbx, [rsi]
0x1800117ee  jz      short loc_180011862
0x1800117f0  cmp     qword ptr [rbx+38h], 8
0x1800117f5  jb      short loc_1800117FD
0x1800117f7  mov     rcx, [rbx+20h]
0x1800117fb  jmp     short loc_180011801
0x1800117fd  lea     rcx, [rbx+20h]
0x180011801  mov     r9, [rbx+30h]
0x180011805  mov     r8, [rdi+10h]
0x180011809  mov     rax, r8
0x18001180c  cmp     r8, r9
0x18001180f  cmovnb  rax, r9
0x180011813  cmp     qword ptr [rdi+18h], 8
0x180011818  jb      short loc_18001181F
0x18001181a  mov     rdx, [rdi]
0x18001181d  jmp     short loc_180011822
0x18001181f  mov     rdx, rdi
0x180011822  test    rax, rax
0x180011825  jz      short loc_18001183F
0x180011827  movzx   r10d, word ptr [rdx]
0x18001182b  cmp     r10w, [rcx]
0x18001182f  jnz     short loc_180011849
0x180011831  add     rdx, 2
0x180011835  add     rcx, 2
0x180011839  sub     rax, 1
0x18001183d  jnz     short loc_180011827
0x18001183f  cmp     r8, r9
0x180011842  jnb     short loc_180011852
0x180011844  or      eax, 0FFFFFFFFh
0x180011847  jmp     short loc_18001185A
0x180011849  sbb     eax, eax
0x18001184b  and     eax, 0FFFFFFFEh
0x18001184e  inc     eax
0x180011850  jmp     short loc_18001185A
0x180011852  xor     eax, eax
0x180011854  cmp     r8, r9
0x180011857  setnz   al
0x18001185a  test    eax, eax
0x18001185c  jns     loc_1800118F7
0x180011862  mov     [rbp+var_40], 0
0x18001186a  mov     [rbp+var_18], 7
0x180011872  mov     [rbp+var_20], 0
0x18001187a  xor     eax, eax
0x18001187c  mov     word ptr [rbp+var_30], ax
0x180011880  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011884  xor     r8d, r8d
0x180011887  mov     rdx, rdi
0x18001188a  lea     rcx, [rbp+var_30]; void *
0x18001188e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180011893  mov     [rbp+var_40], 0
0x18001189b  mov     [rbp+var_10], 0
0x1800118a3  lea     rdx, [rbp+var_30]
0x1800118a7  mov     rcx, rsi
0x1800118aa  call    ??$_Buynode@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>::_Buynode<std::pair<std::wstring,std::unique_ptr<ProvResults>>>(std::pair<std::wstring,std::unique_ptr<ProvResults>> &&)
0x1800118af  lea     r9, [rax+20h]
0x1800118b3  mov     [rsp+70h+var_50], rax
0x1800118b8  mov     r8, rbx
0x1800118bb  lea     rdx, [rbp+var_38]
0x1800118bf  mov     rcx, rsi
0x1800118c2  call    ??$_Insert_hint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_hint<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>>>,std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *)
0x1800118c7  mov     rbx, [rbp+var_38]
0x1800118cb  mov     rdi, [rbp+var_10]
0x1800118cf  test    rdi, rdi
0x1800118d2  jz      short loc_1800118E5
0x1800118d4  mov     rcx, rdi; this
0x1800118d7  call    ??1ProvResults@@QEAA@XZ; ProvResults::~ProvResults(void)
0x1800118dc  mov     rcx, rdi
0x1800118df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800118e5  cmp     [rbp+var_18], 8
0x1800118ea  jb      short loc_1800118F7
0x1800118ec  mov     rcx, [rbp+var_30]
0x1800118f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800118f6  nop
0x1800118f7  lea     rax, [rbx+40h]
0x1800118fb  mov     rcx, [rbp+var_8]
0x1800118ff  xor     rcx, rsp; StackCookie
0x180011902  call    __security_check_cookie
0x180011907  mov     rbx, [rsp+70h+arg_10]
0x18001190f  add     rsp, 70h
0x180011913  pop     rdi
0x180011914  pop     rsi
0x180011915  pop     rbp
0x180011916  retn
```

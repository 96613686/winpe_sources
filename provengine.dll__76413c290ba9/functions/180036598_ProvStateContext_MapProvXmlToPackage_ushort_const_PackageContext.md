# ProvStateContext::MapProvXmlToPackage(ushort const *,PackageContext *)

- ea: `0x180036598`
- end: `0x18003670d`
- name: `?MapProvXmlToPackage@ProvStateContext@@QEAAXPEBGPEAUPackageContext@@@Z`
- size: `373`
- prototype: `void __fastcall(ProvStateContext *__hidden this, const unsigned __int16 *, struct PackageContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001def0`

## callees

- `0x18000b030`
- `0x18000f56c`
- `0x180022844`
- `0x180034970`
- `0x180034c94`
- `0x180036598`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800366c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800366d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800366c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800366d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ProvStateContext::MapProvXmlToPackage(ProvStateContext *this, char *a2, struct PackageContext *a3)
{
  int v5; // edi
  unsigned __int64 v6; // r8
  _QWORD *v7; // rsi
  _QWORD *v8; // rbx
  _WORD *v9; // rcx
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // rax
  void **v12; // rdx
  __int64 v13; // rax
  _QWORD *v14; // [rsp+30h] [rbp-29h] BYREF
  void *v15[2]; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-11h]
  unsigned __int64 v17; // [rsp+50h] [rbp-9h]
  void *v18[5]; // [rsp+58h] [rbp-1h] BYREF

  v17 = 7;
  v16 = 0;
  LOWORD(v15[0]) = 0;
  v5 = -1;
  if ( *(_WORD *)a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a2[2 * v6] );
  }
  else
  {
    v6 = 0;
  }
  std::wstring::assign(v15, a2, v6);
  v7 = (_QWORD *)((char *)this + 48);
  std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(
    (char *)this + 48,
    &v14,
    v15);
  v8 = v14;
  if ( v14 == (_QWORD *)*v7 )
    goto LABEL_19;
  if ( v14[7] < 8u )
    v9 = v14 + 4;
  else
    v9 = (_WORD *)v14[4];
  v10 = v14[6];
  v11 = v16;
  if ( v16 >= v10 )
    v11 = v14[6];
  v12 = v15;
  if ( v17 >= 8 )
    v12 = (void **)v15[0];
  if ( v11 )
  {
    while ( *(_WORD *)v12 == *v9 )
    {
      v12 = (void **)((char *)v12 + 2);
      ++v9;
      if ( !--v11 )
        goto LABEL_16;
    }
    v5 = *(_WORD *)v12 < *v9 ? -1 : 1;
  }
  else
  {
LABEL_16:
    if ( v16 >= v10 )
      v5 = v16 != v10;
  }
  if ( v5 < 0 )
  {
LABEL_19:
    std::wstring::wstring(v18, v15);
    v18[4] = 0;
    v13 = std::_Tree_buy<std::pair<std::wstring const,PackageContext *>>::_Buynode<std::pair<std::wstring,PackageContext *>>(
            v7,
            v18);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Insert_hint<std::pair<std::wstring const,unsigned long> &,std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *> *>(
      (_DWORD)v7,
      (unsigned int)&v14,
      (_DWORD)v8,
      v13 + 32,
      v13);
    v8 = v14;
    if ( v18[3] >= (void *)8 )
      operator delete(v18[0]);
  }
  v8[8] = a3;
  if ( v17 >= 8 )
    operator delete(v15[0]);
}

```

## disassembly

```asm
0x180036598  mov     [rsp-8+arg_10], rbx
0x18003659d  push    rbp
0x18003659e  push    rsi
0x18003659f  push    rdi
0x1800365a0  push    r14
0x1800365a2  push    r15
0x1800365a4  lea     rbp, [rsp-37h]
0x1800365a9  sub     rsp, 90h
0x1800365b0  mov     rax, cs:__security_cookie
0x1800365b7  xor     rax, rsp
0x1800365ba  mov     [rbp+57h+var_30], rax
0x1800365be  mov     r14, r8
0x1800365c1  mov     rbx, rcx
0x1800365c4  mov     [rbp+57h+var_60], 7
0x1800365cc  xor     r15d, r15d
0x1800365cf  mov     [rbp+57h+var_68], r15
0x1800365d3  mov     word ptr [rbp+57h+var_78], r15w
0x1800365d8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800365dc  cmp     [rdx], r15w
0x1800365e0  jnz     short loc_1800365E7
0x1800365e2  mov     r8d, r15d
0x1800365e5  jmp     short loc_1800365F4
0x1800365e7  mov     r8, rdi
0x1800365ea  inc     r8
0x1800365ed  cmp     [rdx+r8*2], r15w
0x1800365f2  jnz     short loc_1800365EA
0x1800365f4  lea     rcx, [rbp+57h+var_78]; void *
0x1800365f8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800365fd  nop
0x1800365fe  lea     rsi, [rbx+30h]
0x180036602  lea     r8, [rbp+57h+var_78]
0x180036606  lea     rdx, [rbp+57h+var_80]
0x18003660a  mov     rcx, rsi
0x18003660d  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(std::wstring const &)
0x180036612  mov     rbx, [rbp+57h+var_80]
0x180036616  cmp     rbx, [rsi]
0x180036619  jz      short loc_18003667E
0x18003661b  cmp     qword ptr [rbx+38h], 8
0x180036620  jb      short loc_180036628
0x180036622  mov     rcx, [rbx+20h]
0x180036626  jmp     short loc_18003662C
0x180036628  lea     rcx, [rbx+20h]
0x18003662c  mov     r9, [rbx+30h]
0x180036630  mov     r8, [rbp+57h+var_68]
0x180036634  mov     rax, r8
0x180036637  cmp     r8, r9
0x18003663a  cmovnb  rax, r9
0x18003663e  lea     rdx, [rbp+57h+var_78]
0x180036642  cmp     [rbp+57h+var_60], 8
0x180036647  cmovnb  rdx, [rbp+57h+var_78]
0x18003664c  test    rax, rax
0x18003664f  jz      short loc_18003666D
0x180036651  movzx   r10d, word ptr [rdx]
0x180036655  cmp     r10w, [rcx]
0x180036659  jnz     loc_180036700
0x18003665f  add     rdx, 2
0x180036663  add     rcx, 2
0x180036667  sub     rax, 1
0x18003666b  jnz     short loc_180036651
0x18003666d  cmp     r8, r9
0x180036670  jb      short loc_18003667A
0x180036672  mov     eax, r15d
0x180036675  setnz   al
0x180036678  mov     edi, eax
0x18003667a  test    edi, edi
0x18003667c  jns     short loc_1800366C8
0x18003667e  lea     rdx, [rbp+57h+var_78]
0x180036682  lea     rcx, [rbp+57h+var_58]
0x180036686  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003668b  mov     [rbp+57h+var_38], r15
0x18003668f  lea     rdx, [rbp+57h+var_58]
0x180036693  mov     rcx, rsi
0x180036696  call    ??$_Buynode@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@PEAX@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,PackageContext *>>::_Buynode<std::pair<std::wstring,PackageContext *>>(std::pair<std::wstring,PackageContext *> &&)
0x18003669b  lea     r9, [rax+20h]
0x18003669f  mov     [rsp+0B0h+var_90], rax
0x1800366a4  mov     r8, rbx
0x1800366a7  lea     rdx, [rbp+57h+var_80]
0x1800366ab  mov     rcx, rsi
0x1800366ae  call    ??$_Insert_hint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Insert_hint<std::pair<std::wstring const,ulong> &,std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>>,std::pair<std::wstring const,ulong> &,std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *)
0x1800366b3  mov     rbx, [rbp+57h+var_80]
0x1800366b7  cmp     [rbp+57h+var_40], 8
0x1800366bc  jb      short loc_1800366C8
0x1800366be  mov     rcx, [rbp+57h+var_58]
0x1800366c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800366c8  mov     [rbx+40h], r14
0x1800366cc  cmp     [rbp+57h+var_60], 8
0x1800366d1  jb      short loc_1800366DD
0x1800366d3  mov     rcx, [rbp+57h+var_78]
0x1800366d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800366dd  mov     rcx, [rbp+57h+var_30]
0x1800366e1  xor     rcx, rsp; StackCookie
0x1800366e4  call    __security_check_cookie
0x1800366e9  mov     rbx, [rsp+0B0h+arg_10]
0x1800366f1  add     rsp, 90h
0x1800366f8  pop     r15
0x1800366fa  pop     r14
0x1800366fc  pop     rdi
0x1800366fd  pop     rsi
0x1800366fe  pop     rbp
0x1800366ff  retn
0x180036700  sbb     edi, edi
0x180036702  and     edi, 0FFFFFFFEh
0x180036705  inc     edi
0x180036707  jmp     loc_18003667A
```

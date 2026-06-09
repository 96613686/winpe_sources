# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>,0>>::_Insert_nohint<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>,void *> *>(bool,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>,void *> *)

- ea: `0x18000e5dc`
- end: `0x18000e831`
- name: `??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@@Z`
- size: `597`
- prototype: `__int64 __fastcall(__int64 ***, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000dbac`

## callees

- `0x18000cd0c`
- `0x18000e5dc`
- `0x180011328`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e805`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e805`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(
        __int64 ***a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 **v8; // r10
  __int64 *v9; // rax
  int v10; // edx
  unsigned __int64 v11; // r15
  _WORD *v12; // r9
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rcx
  _WORD *v15; // r8
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 *v18; // rbx
  __int64 *v19; // r9
  __int64 v20; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 *i; // rax
  _WORD *v24; // r10
  _QWORD *v25; // rax
  unsigned __int64 v26; // r11
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rcx
  __int64 v29; // rdi
  void *v30; // r14
  int v31; // [rsp+20h] [rbp-48h]
  __int64 v32; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    v8 = *a1;
    v9 = (*a1)[1];
    v10 = -1;
    if ( *((_BYTE *)v9 + 25) )
    {
      LOBYTE(v17) = 1;
      v19 = (__int64 *)*a1;
      v18 = (__int64 *)*a1;
    }
    else
    {
      v11 = *(_QWORD *)(a4 + 16);
      do
      {
        if ( (unsigned __int64)v9[7] < 8 )
          v12 = v9 + 4;
        else
          v12 = (_WORD *)v9[4];
        v13 = v9[6];
        v14 = v13;
        if ( v11 < v13 )
          v14 = v11;
        if ( *(_QWORD *)(a4 + 24) < 8u )
          v15 = (_WORD *)a4;
        else
          v15 = *(_WORD **)a4;
        if ( v14 )
        {
          while ( *v15 == *v12 )
          {
            ++v15;
            ++v12;
            if ( !--v14 )
              goto LABEL_15;
          }
          v16 = *v15 < *v12 ? -1 : 1;
        }
        else
        {
LABEL_15:
          if ( v11 >= v13 )
            v16 = v11 != v13;
          else
            v16 = -1;
        }
        v17 = v16 >> 31;
        v18 = v9;
        if ( (_BYTE)v17 )
          v9 = (__int64 *)*v9;
        else
          v9 = (__int64 *)v9[2];
      }
      while ( !*((_BYTE *)v9 + 25) );
      v19 = v18;
      if ( !(_BYTE)v17 )
      {
LABEL_41:
        if ( *(_QWORD *)(a4 + 24) < 8u )
          v24 = (_WORD *)a4;
        else
          v24 = *(_WORD **)a4;
        v25 = v18 + 4;
        v26 = *(_QWORD *)(a4 + 16);
        v27 = v18[6];
        v28 = v27;
        if ( v27 >= v26 )
          v28 = v26;
        if ( (unsigned __int64)v18[7] >= 8 )
          v25 = (_QWORD *)*v25;
        if ( v28 )
        {
          while ( *(_WORD *)v25 == *v24 )
          {
            v25 = (_QWORD *)((char *)v25 + 2);
            ++v24;
            if ( !--v28 )
              goto LABEL_51;
          }
          v10 = *(_WORD *)v25 < *v24 ? -1 : 1;
        }
        else
        {
LABEL_51:
          if ( v27 >= v26 )
            v10 = v27 != v26;
        }
        if ( v10 >= 0 )
        {
          v29 = a5;
          v30 = *(void **)(a5 + 64);
          if ( v30 )
          {
            ProvResults::~ProvResults(*(ProvResults **)(a5 + 64));
            operator delete(v30);
          }
          if ( *(_QWORD *)(v29 + 56) >= 8u )
            operator delete(*(void **)(v29 + 32));
          *(_QWORD *)(v29 + 56) = 7;
          *(_QWORD *)(v29 + 48) = 0;
          *(_WORD *)(v29 + 32) = 0;
          operator delete((void *)v29);
          *(_QWORD *)a2 = v18;
          *(_BYTE *)(a2 + 8) = 0;
          return a2;
        }
        else
        {
          *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(
                             a1,
                             &v32,
                             v17,
                             v19,
                             v31,
                             a5);
          *(_BYTE *)(a2 + 8) = 1;
          return a2;
        }
      }
    }
    if ( v19 == *v8 )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(
                         a1,
                         &v32,
                         1,
                         v19,
                         v31,
                         a5);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *((_BYTE *)v19 + 25) )
    {
      v18 = (__int64 *)v19[2];
    }
    else if ( *(_BYTE *)(*v19 + 25) )
    {
      for ( i = (__int64 *)v19[1]; !*((_BYTE *)i + 25) && v18 == (__int64 *)*i; i = (__int64 *)i[1] )
        v18 = i;
      if ( !*((_BYTE *)v18 + 25) )
        v18 = i;
    }
    else
    {
      v18 = (__int64 *)*v19;
      for ( j = *(_QWORD *)(*v19 + 16); !*(_BYTE *)(j + 25); j = v18[2] )
        v18 = (__int64 *)v18[2];
    }
    goto LABEL_41;
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Destroy_if_not_nil(
      v20,
      a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000e5dc  push    rbx
0x18000e5de  push    rsi
0x18000e5df  push    rdi
0x18000e5e0  push    r12
0x18000e5e2  push    r14
0x18000e5e4  push    r15
0x18000e5e6  sub     rsp, 38h
0x18000e5ea  mov     r11, r9
0x18000e5ed  mov     rsi, rdx
0x18000e5f0  mov     r12, rcx
0x18000e5f3  mov     r10, [rcx]
0x18000e5f6  mov     rax, [r10+8]
0x18000e5fa  or      edx, 0FFFFFFFFh
0x18000e5fd  cmp     byte ptr [rax+19h], 0
0x18000e601  jnz     loc_18000E6A3
0x18000e607  mov     r15, [r9+10h]
0x18000e60b  cmp     qword ptr [rax+38h], 8
0x18000e610  jb      short loc_18000E618
0x18000e612  mov     r9, [rax+20h]
0x18000e616  jmp     short loc_18000E61C
0x18000e618  lea     r9, [rax+20h]
0x18000e61c  mov     r14, [rax+30h]
0x18000e620  mov     rcx, r14
0x18000e623  cmp     r15, r14
0x18000e626  cmovb   rcx, r15
0x18000e62a  cmp     qword ptr [r11+18h], 8
0x18000e62f  jb      short loc_18000E636
0x18000e631  mov     r8, [r11]
0x18000e634  jmp     short loc_18000E639
0x18000e636  mov     r8, r11
0x18000e639  test    rcx, rcx
0x18000e63c  jz      short loc_18000E656
0x18000e63e  movzx   ebx, word ptr [r8]
0x18000e642  cmp     bx, [r9]
0x18000e646  jnz     short loc_18000E660
0x18000e648  add     r8, 2
0x18000e64c  add     r9, 2
0x18000e650  sub     rcx, 1
0x18000e654  jnz     short loc_18000E63E
0x18000e656  cmp     r15, r14
0x18000e659  jnb     short loc_18000E66C
0x18000e65b  mov     r8d, edx
0x18000e65e  jmp     short loc_18000E676
0x18000e660  sbb     r8d, r8d
0x18000e663  and     r8d, 0FFFFFFFEh
0x18000e667  inc     r8d
0x18000e66a  jmp     short loc_18000E676
0x18000e66c  xor     r8d, r8d
0x18000e66f  cmp     r15, r14
0x18000e672  setnz   r8b
0x18000e676  shr     r8d, 1Fh
0x18000e67a  mov     rbx, rax
0x18000e67d  test    r8b, r8b
0x18000e680  jz      short loc_18000E687
0x18000e682  mov     rax, [rax]
0x18000e685  jmp     short loc_18000E68B
0x18000e687  mov     rax, [rax+10h]
0x18000e68b  cmp     byte ptr [rax+19h], 0
0x18000e68f  jz      loc_18000E60B
0x18000e695  mov     r9, rbx
0x18000e698  test    r8b, r8b
0x18000e69b  jz      loc_18000E72F
0x18000e6a1  jmp     short loc_18000E6AC
0x18000e6a3  mov     r8b, 1
0x18000e6a6  mov     r9, r10
0x18000e6a9  mov     rbx, r10
0x18000e6ac  cmp     r9, [r10]
0x18000e6af  jnz     short loc_18000E6E0
0x18000e6b1  mov     rax, [rsp+68h+arg_20]
0x18000e6b9  mov     [rsp+68h+var_40], rax
0x18000e6be  mov     r8b, 1
0x18000e6c1  lea     rdx, [rsp+68h+arg_0]
0x18000e6c6  mov     rcx, r12
0x18000e6c9  call    ??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@1@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(bool,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *,std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *)
0x18000e6ce  mov     rax, [rax]
0x18000e6d1  mov     [rsi], rax
0x18000e6d4  mov     byte ptr [rsi+8], 1
0x18000e6d8  mov     rax, rsi
0x18000e6db  jmp     loc_18000E815
0x18000e6e0  cmp     byte ptr [r9+19h], 0
0x18000e6e5  jz      short loc_18000E6ED
0x18000e6e7  mov     rbx, [r9+10h]
0x18000e6eb  jmp     short loc_18000E72F
0x18000e6ed  mov     rax, [r9]
0x18000e6f0  cmp     byte ptr [rax+19h], 0
0x18000e6f4  jnz     short loc_18000E70F
0x18000e6f6  mov     rbx, rax
0x18000e6f9  mov     rax, [rax+10h]
0x18000e6fd  jmp     short loc_18000E707
0x18000e6ff  mov     rbx, [rbx+10h]
0x18000e703  mov     rax, [rbx+10h]
0x18000e707  cmp     byte ptr [rax+19h], 0
0x18000e70b  jz      short loc_18000E6FF
0x18000e70d  jmp     short loc_18000E72F
0x18000e70f  mov     rax, [r9+8]
0x18000e713  jmp     short loc_18000E721
0x18000e715  cmp     rbx, [rax]
0x18000e718  jnz     short loc_18000E727
0x18000e71a  mov     rbx, rax
0x18000e71d  mov     rax, [rax+8]
0x18000e721  cmp     byte ptr [rax+19h], 0
0x18000e725  jz      short loc_18000E715
0x18000e727  cmp     byte ptr [rbx+19h], 0
0x18000e72b  cmovz   rbx, rax
0x18000e72f  cmp     qword ptr [r11+18h], 8
0x18000e734  jb      short loc_18000E73B
0x18000e736  mov     r10, [r11]
0x18000e739  jmp     short loc_18000E73E
0x18000e73b  mov     r10, r11
0x18000e73e  lea     rax, [rbx+20h]
0x18000e742  mov     r11, [r11+10h]
0x18000e746  mov     rdi, [rax+10h]
0x18000e74a  mov     rcx, rdi
0x18000e74d  cmp     rdi, r11
0x18000e750  cmovnb  rcx, r11
0x18000e754  cmp     qword ptr [rax+18h], 8
0x18000e759  jb      short loc_18000E75E
0x18000e75b  mov     rax, [rax]
0x18000e75e  test    rcx, rcx
0x18000e761  jz      short loc_18000E77F
0x18000e763  movzx   r14d, word ptr [rax]
0x18000e767  cmp     r14w, [r10]
0x18000e76b  jnz     loc_18000E823
0x18000e771  add     rax, 2
0x18000e775  add     r10, 2
0x18000e779  sub     rcx, 1
0x18000e77d  jnz     short loc_18000E763
0x18000e77f  cmp     rdi, r11
0x18000e782  jb      short loc_18000E78C
0x18000e784  xor     edx, edx
0x18000e786  cmp     rdi, r11
0x18000e789  setnz   dl
0x18000e78c  test    edx, edx
0x18000e78e  jns     short loc_18000E7B9
0x18000e790  mov     rax, [rsp+68h+arg_20]
0x18000e798  mov     [rsp+68h+var_40], rax
0x18000e79d  lea     rdx, [rsp+68h+arg_0]
0x18000e7a2  mov     rcx, r12
0x18000e7a5  call    ??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@1@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(bool,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *,std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *)
0x18000e7aa  mov     rax, [rax]
0x18000e7ad  mov     [rsi], rax
0x18000e7b0  mov     byte ptr [rsi+8], 1
0x18000e7b4  mov     rax, rsi
0x18000e7b7  jmp     short loc_18000E815
0x18000e7b9  mov     rdi, [rsp+68h+arg_20]
0x18000e7c1  mov     r14, [rdi+40h]
0x18000e7c5  test    r14, r14
0x18000e7c8  jz      short loc_18000E7DB
0x18000e7ca  mov     rcx, r14; this
0x18000e7cd  call    ??1ProvResults@@QEAA@XZ; ProvResults::~ProvResults(void)
0x18000e7d2  mov     rcx, r14
0x18000e7d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e7db  cmp     qword ptr [rdi+38h], 8
0x18000e7e0  jb      short loc_18000E7EC
0x18000e7e2  mov     rcx, [rdi+20h]
0x18000e7e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e7ec  mov     qword ptr [rdi+38h], 7
0x18000e7f4  mov     qword ptr [rdi+30h], 0
0x18000e7fc  xor     eax, eax
0x18000e7fe  mov     [rdi+20h], ax
0x18000e802  mov     rcx, rdi
0x18000e805  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e80b  mov     [rsi], rbx
0x18000e80e  mov     byte ptr [rsi+8], 0
0x18000e812  mov     rax, rsi
0x18000e815  add     rsp, 38h
0x18000e819  pop     r15
0x18000e81b  pop     r14
0x18000e81d  pop     r12
0x18000e81f  pop     rdi
0x18000e820  pop     rsi
0x18000e821  pop     rbx
0x18000e822  retn
0x18000e823  sbb     edx, edx
0x18000e825  and     edx, 0FFFFFFFEh
0x18000e828  inc     edx
0x18000e82a  jmp     loc_18000E78C
```

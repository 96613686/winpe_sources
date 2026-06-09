# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>>,0>>::_Insert_nohint<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>,void *> *>(bool,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>,void *> *)

- ea: `0x180035378`
- end: `0x18003558e`
- name: `??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@@Z`
- size: `534`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180035fb0`

## callees

- `0x180010628`
- `0x180034a14`
- `0x180035378`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035565`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035565`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *a5)
{
  _QWORD *v8; // r10
  __int64 *v9; // rax
  int v10; // ecx
  unsigned __int64 v11; // r15
  _WORD *v12; // r9
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rdx
  _WORD *v15; // r8
  unsigned int v16; // r8d
  _QWORD *v17; // rbx
  _QWORD *v18; // r9
  __int64 v19; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 i; // rax
  _WORD *v23; // r10
  _QWORD *v24; // rax
  unsigned __int64 v25; // r11
  unsigned __int64 v26; // rdi
  unsigned __int64 v27; // rdx
  void *v28; // rdi
  int v29; // [rsp+20h] [rbp-48h]
  __int64 v30; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    v8 = (_QWORD *)*a1;
    v9 = *(__int64 **)(*a1 + 8LL);
    v10 = -1;
    if ( *((_BYTE *)v9 + 25) )
    {
      LOBYTE(a3) = 1;
      v18 = v8;
      v17 = v8;
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
        a3 = v16 >> 31;
        v17 = v9;
        if ( (_BYTE)a3 )
          v9 = (__int64 *)*v9;
        else
          v9 = (__int64 *)v9[2];
      }
      while ( !*((_BYTE *)v9 + 25) );
      v18 = v17;
      if ( !(_BYTE)a3 )
      {
LABEL_41:
        if ( *(_QWORD *)(a4 + 24) < 8u )
          v23 = (_WORD *)a4;
        else
          v23 = *(_WORD **)a4;
        v24 = v17 + 4;
        v25 = *(_QWORD *)(a4 + 16);
        v26 = v17[6];
        v27 = v26;
        if ( v26 >= v25 )
          v27 = v25;
        if ( v17[7] >= 8u )
          v24 = (_QWORD *)*v24;
        if ( v27 )
        {
          while ( *(_WORD *)v24 == *v23 )
          {
            v24 = (_QWORD *)((char *)v24 + 2);
            ++v23;
            if ( !--v27 )
              goto LABEL_51;
          }
          v10 = *(_WORD *)v24 < *v23 ? -1 : 1;
        }
        else
        {
LABEL_51:
          if ( v26 >= v25 )
            v10 = v26 != v25;
        }
        if ( v10 >= 0 )
        {
          v28 = a5;
          std::pair<std::wstring const,std::unique_ptr<PackageContext>>::~pair<std::wstring const,std::unique_ptr<PackageContext>>(
            a5 + 32,
            v27,
            a3,
            v18);
          operator delete(v28);
          *(_QWORD *)a2 = v17;
          *(_BYTE *)(a2 + 8) = 0;
        }
        else
        {
          *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(
                             a1,
                             &v30,
                             a3,
                             v18,
                             v29,
                             (__int64)a5);
          *(_BYTE *)(a2 + 8) = 1;
        }
        return a2;
      }
    }
    if ( v18 == (_QWORD *)*v8 )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(
                         a1,
                         &v30,
                         1,
                         v18,
                         v29,
                         (__int64)a5);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *((_BYTE *)v18 + 25) )
    {
      v17 = (_QWORD *)v18[2];
    }
    else if ( *(_BYTE *)(*v18 + 25LL) )
    {
      for ( i = v18[1]; !*(_BYTE *)(i + 25) && v17 == *(_QWORD **)i; i = *(_QWORD *)(i + 8) )
        v17 = (_QWORD *)i;
      if ( !*((_BYTE *)v17 + 25) )
        v17 = (_QWORD *)i;
    }
    else
    {
      v17 = (_QWORD *)*v18;
      for ( j = *(_QWORD *)(*v18 + 16LL); !*(_BYTE *)(j + 25); j = v17[2] )
        v17 = (_QWORD *)v17[2];
    }
    goto LABEL_41;
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Destroy_if_not_nil(
      v19,
      a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180035378  push    rbx
0x18003537a  push    rsi
0x18003537b  push    rdi
0x18003537c  push    r12
0x18003537e  push    r14
0x180035380  push    r15
0x180035382  sub     rsp, 38h
0x180035386  mov     r11, r9
0x180035389  mov     rsi, rdx
0x18003538c  mov     r12, rcx
0x18003538f  mov     r10, [rcx]
0x180035392  mov     rax, [r10+8]
0x180035396  or      ecx, 0FFFFFFFFh
0x180035399  cmp     byte ptr [rax+19h], 0
0x18003539d  jnz     loc_18003543F
0x1800353a3  mov     r15, [r9+10h]
0x1800353a7  cmp     qword ptr [rax+38h], 8
0x1800353ac  jb      short loc_1800353B4
0x1800353ae  mov     r9, [rax+20h]
0x1800353b2  jmp     short loc_1800353B8
0x1800353b4  lea     r9, [rax+20h]
0x1800353b8  mov     r14, [rax+30h]
0x1800353bc  mov     rdx, r14
0x1800353bf  cmp     r15, r14
0x1800353c2  cmovb   rdx, r15
0x1800353c6  cmp     qword ptr [r11+18h], 8
0x1800353cb  jb      short loc_1800353D2
0x1800353cd  mov     r8, [r11]
0x1800353d0  jmp     short loc_1800353D5
0x1800353d2  mov     r8, r11
0x1800353d5  test    rdx, rdx
0x1800353d8  jz      short loc_1800353F2
0x1800353da  movzx   ebx, word ptr [r8]
0x1800353de  cmp     bx, [r9]
0x1800353e2  jnz     short loc_1800353FC
0x1800353e4  add     r8, 2
0x1800353e8  add     r9, 2
0x1800353ec  sub     rdx, 1
0x1800353f0  jnz     short loc_1800353DA
0x1800353f2  cmp     r15, r14
0x1800353f5  jnb     short loc_180035408
0x1800353f7  mov     r8d, ecx
0x1800353fa  jmp     short loc_180035412
0x1800353fc  sbb     r8d, r8d
0x1800353ff  and     r8d, 0FFFFFFFEh
0x180035403  inc     r8d
0x180035406  jmp     short loc_180035412
0x180035408  xor     r8d, r8d
0x18003540b  cmp     r15, r14
0x18003540e  setnz   r8b
0x180035412  shr     r8d, 1Fh
0x180035416  mov     rbx, rax
0x180035419  test    r8b, r8b
0x18003541c  jz      short loc_180035423
0x18003541e  mov     rax, [rax]
0x180035421  jmp     short loc_180035427
0x180035423  mov     rax, [rax+10h]
0x180035427  cmp     byte ptr [rax+19h], 0
0x18003542b  jz      loc_1800353A7
0x180035431  mov     r9, rbx
0x180035434  test    r8b, r8b
0x180035437  jz      loc_1800354CB
0x18003543d  jmp     short loc_180035448
0x18003543f  mov     r8b, 1
0x180035442  mov     r9, r10
0x180035445  mov     rbx, r10
0x180035448  cmp     r9, [r10]
0x18003544b  jnz     short loc_18003547C
0x18003544d  mov     rax, [rsp+68h+arg_20]
0x180035455  mov     [rsp+68h+var_40], rax
0x18003545a  mov     r8b, 1
0x18003545d  lea     rdx, [rsp+68h+arg_0]
0x180035462  mov     rcx, r12
0x180035465  call    ??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@1@1@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(bool,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *,std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *)
0x18003546a  mov     rax, [rax]
0x18003546d  mov     [rsi], rax
0x180035470  mov     byte ptr [rsi+8], 1
0x180035474  mov     rax, rsi
0x180035477  jmp     loc_180035575
0x18003547c  cmp     byte ptr [r9+19h], 0
0x180035481  jz      short loc_180035489
0x180035483  mov     rbx, [r9+10h]
0x180035487  jmp     short loc_1800354CB
0x180035489  mov     rax, [r9]
0x18003548c  cmp     byte ptr [rax+19h], 0
0x180035490  jnz     short loc_1800354AB
0x180035492  mov     rbx, rax
0x180035495  mov     rax, [rax+10h]
0x180035499  jmp     short loc_1800354A3
0x18003549b  mov     rbx, [rbx+10h]
0x18003549f  mov     rax, [rbx+10h]
0x1800354a3  cmp     byte ptr [rax+19h], 0
0x1800354a7  jz      short loc_18003549B
0x1800354a9  jmp     short loc_1800354CB
0x1800354ab  mov     rax, [r9+8]
0x1800354af  jmp     short loc_1800354BD
0x1800354b1  cmp     rbx, [rax]
0x1800354b4  jnz     short loc_1800354C3
0x1800354b6  mov     rbx, rax
0x1800354b9  mov     rax, [rax+8]
0x1800354bd  cmp     byte ptr [rax+19h], 0
0x1800354c1  jz      short loc_1800354B1
0x1800354c3  cmp     byte ptr [rbx+19h], 0
0x1800354c7  cmovz   rbx, rax
0x1800354cb  cmp     qword ptr [r11+18h], 8
0x1800354d0  jb      short loc_1800354D7
0x1800354d2  mov     r10, [r11]
0x1800354d5  jmp     short loc_1800354DA
0x1800354d7  mov     r10, r11
0x1800354da  lea     rax, [rbx+20h]
0x1800354de  mov     r11, [r11+10h]
0x1800354e2  mov     rdi, [rax+10h]
0x1800354e6  mov     rdx, rdi
0x1800354e9  cmp     rdi, r11
0x1800354ec  cmovnb  rdx, r11
0x1800354f0  cmp     qword ptr [rax+18h], 8
0x1800354f5  jb      short loc_1800354FA
0x1800354f7  mov     rax, [rax]
0x1800354fa  test    rdx, rdx
0x1800354fd  jz      short loc_180035517
0x1800354ff  movzx   r14d, word ptr [rax]
0x180035503  cmp     r14w, [r10]
0x180035507  jnz     short loc_180035583
0x180035509  add     rax, 2
0x18003550d  add     r10, 2
0x180035511  sub     rdx, 1
0x180035515  jnz     short loc_1800354FF
0x180035517  cmp     rdi, r11
0x18003551a  jb      short loc_180035524
0x18003551c  xor     ecx, ecx
0x18003551e  cmp     rdi, r11
0x180035521  setnz   cl
0x180035524  test    ecx, ecx
0x180035526  jns     short loc_180035551
0x180035528  mov     rax, [rsp+68h+arg_20]
0x180035530  mov     [rsp+68h+var_40], rax
0x180035535  lea     rdx, [rsp+68h+arg_0]
0x18003553a  mov     rcx, r12
0x18003553d  call    ??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@1@1@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(bool,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *,std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *)
0x180035542  mov     rax, [rax]
0x180035545  mov     [rsi], rax
0x180035548  mov     byte ptr [rsi+8], 1
0x18003554c  mov     rax, rsi
0x18003554f  jmp     short loc_180035575
0x180035551  mov     rdi, [rsp+68h+arg_20]
0x180035559  lea     rcx, [rdi+20h]
0x18003555d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<PackageContext>>::~pair<std::wstring const,std::unique_ptr<PackageContext>>(void)
0x180035562  mov     rcx, rdi
0x180035565  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003556b  mov     [rsi], rbx
0x18003556e  mov     byte ptr [rsi+8], 0
0x180035572  mov     rax, rsi
0x180035575  add     rsp, 38h
0x180035579  pop     r15
0x18003557b  pop     r14
0x18003557d  pop     r12
0x18003557f  pop     rdi
0x180035580  pop     rsi
0x180035581  pop     rbx
0x180035582  retn
0x180035583  sbb     ecx, ecx
0x180035585  and     ecx, 0FFFFFFFEh
0x180035588  inc     ecx
0x18003558a  jmp     short loc_180035524
```

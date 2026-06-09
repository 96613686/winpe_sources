# NfsMapVolPathToMntPointWithSharePrefix

- ea: `0x180019010`
- end: `0x180019247`
- name: `NfsMapVolPathToMntPointWithSharePrefix`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path`

## callers

- `0x180019c74`
- `0x180019edc`

## callees

- `0x1800096cc`
- `0x18000eae4`
- `0x18000ec88`
- `0x18000efc8`
- `0x180016248`
- `0x180018110`
- `0x1800181b8`
- `0x180018284`
- `0x180018334`
- `0x180018380`
- `0x1800184c4`
- `0x180018764`
- `0x180018e10`
- `0x180019010`
- `0x18001e358`
- `0x18001e418`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180019127`
- `msvcrt!_wcsnicmp` at `0x180019127`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NfsMapVolPathToMntPointWithSharePrefix(__int64 a1)
{
  unsigned int NfsShareList; // r14d
  __int64 v2; // rsi
  __int64 v3; // rax
  __int64 v4; // r14
  __int64 v5; // rbx
  struct _LIST_ENTRY *Flink; // r15
  struct _LIST_ENTRY *v7; // r13
  unsigned __int64 v8; // r12
  __int64 *v9; // rdi
  __int64 v10; // rbx
  size_t v11; // r8
  const wchar_t *v12; // rdx
  __int64 v13; // rdx
  wchar_t **v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 i; // rax
  char v18; // al
  _WORD *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v23; // [rsp+28h] [rbp-91h] BYREF
  struct _LIST_ENTRY v24; // [rsp+30h] [rbp-89h] BYREF
  __int64 v25; // [rsp+40h] [rbp-79h]
  _QWORD v26[2]; // [rsp+48h] [rbp-71h] BYREF
  wchar_t *String2[2]; // [rsp+58h] [rbp-61h] BYREF
  size_t v28; // [rsp+68h] [rbp-51h]
  unsigned __int64 v29; // [rsp+70h] [rbp-49h]
  _WORD v30[8]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v31; // [rsp+88h] [rbp-31h]
  __int64 v32; // [rsp+90h] [rbp-29h]
  _BYTE v33[32]; // [rsp+98h] [rbp-21h] BYREF
  __int64 *v34; // [rsp+B8h] [rbp-1h] BYREF

  v25 = a1;
  v24 = 0;
  __0__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__std__QEAA_XZ(v26);
  NfsShareList = GetNfsShareList(&v24);
  if ( !NfsShareList )
  {
    NfsShareList = NfsGetVolumesToMountPointsMap((__int64)v26);
    if ( !NfsShareList )
    {
      v2 = v26[0];
      v3 = *(_QWORD *)v26[0];
      v23 = *(_QWORD *)v26[0];
      v4 = v25;
      while ( v3 != v2 )
      {
        v5 = v3 + 32;
        std::wstring::wstring(v33, v3 + 32);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(
          &v34,
          v5 + 32);
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        Flink = v24.Flink;
        if ( v24.Flink == &v24 )
          goto LABEL_28;
        do
        {
          v7 = Flink;
          Flink = Flink->Flink;
          v8 = -1;
          do
            ++v8;
          while ( *((_WORD *)&v7[1].Flink + v8) );
          v9 = v34;
          v10 = *v34;
          while ( (__int64 *)v10 != v9 )
          {
            std::wstring::wstring(String2, v10 + 32);
            v11 = v28;
            if ( v8 < v28 )
              v11 = v8;
            v12 = (const wchar_t *)String2;
            if ( v29 >= 8 )
              v12 = String2[0];
            if ( !_wcsnicmp((const wchar_t *)&v7[1], v12, v11) )
            {
              v14 = String2;
              if ( v29 >= 8 )
                v14 = (wchar_t **)String2[0];
              v15 = std::char_traits<unsigned short>::length(v14);
              std::wstring::assign(v30, v16, v15);
            }
            LOBYTE(v13) = 1;
            std::wstring::_Tidy(String2, v13, 0);
            if ( !*(_BYTE *)(v10 + 25) )
            {
              if ( *(_BYTE *)(*(_QWORD *)(v10 + 16) + 25LL) )
              {
                for ( i = *(_QWORD *)(v10 + 8); !*(_BYTE *)(i + 25) && v10 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
                  v10 = i;
                v10 = i;
              }
              else
              {
                v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
              }
            }
          }
        }
        while ( Flink != &v24 );
        v18 = 0;
        if ( !v31 )
LABEL_28:
          v18 = 1;
        v19 = v30;
        if ( v18 )
          v19 = v33;
        v20 = std::map<std::wstring,std::wstring>::operator[](v4, v33);
        std::wstring::operator=(v20, v19);
        LOBYTE(v21) = 1;
        std::wstring::_Tidy(v30, v21, 0);
        std::pair<std::wstring const,std::set<std::wstring>>::~pair<std::wstring const,std::set<std::wstring>>(v33);
        std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::set<std::wstring>>>>>::operator++(&v23);
        v3 = v23;
      }
      NfsShareList = 0;
    }
    FreeNfsExportList(&v24);
  }
  __1___Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__0A__std___std__QEAA_XZ(v26);
  return NfsShareList;
}

```

## disassembly

```asm
0x180019010  push    rbp
0x180019012  push    rbx
0x180019013  push    rsi
0x180019014  push    rdi
0x180019015  push    r12
0x180019017  push    r13
0x180019019  push    r14
0x18001901b  push    r15
0x18001901d  lea     rbp, [rsp-1Fh]
0x180019022  sub     rsp, 0D8h
0x180019029  mov     rax, cs:__security_cookie
0x180019030  xor     rax, rsp
0x180019033  mov     [rbp+57h+var_48], rax
0x180019037  mov     [rbp+57h+var_D0], rcx
0x18001903b  xorps   xmm0, xmm0
0x18001903e  movups  xmmword ptr [rsp+110h+var_E0.Flink], xmm0
0x180019043  lea     rcx, [rbp+57h+var_C8]
0x180019047  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ
0x18001904c  nop
0x18001904d  lea     rcx, [rsp+110h+var_E0]; struct _LIST_ENTRY *
0x180019052  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x180019057  mov     r14d, eax
0x18001905a  test    eax, eax
0x18001905c  jnz     loc_18001921B
0x180019062  lea     rcx, [rbp+57h+var_C8]
0x180019066  call    NfsGetVolumesToMountPointsMap
0x18001906b  mov     r14d, eax
0x18001906e  mov     [rsp+110h+var_F0], eax
0x180019072  test    eax, eax
0x180019074  jnz     loc_180019210
0x18001907a  mov     rsi, [rbp+57h+var_C8]
0x18001907e  mov     rax, [rsi]
0x180019081  mov     [rsp+110h+var_E8], rax
0x180019086  mov     r14, [rbp+57h+var_D0]
0x18001908a  cmp     rax, rsi
0x18001908d  jz      loc_18001920B
0x180019093  lea     rbx, [rax+20h]
0x180019097  mov     rdx, rbx
0x18001909a  lea     rcx, [rbp+57h+var_78]
0x18001909e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800190a3  nop
0x1800190a4  lea     rdx, [rbx+20h]
0x1800190a8  lea     rcx, [rbp+57h+var_58]
0x1800190ac  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>> const &,std::allocator<std::wstring> const &)
0x1800190b1  nop
0x1800190b2  mov     [rbp+57h+var_80], 7
0x1800190ba  xor     edx, edx
0x1800190bc  mov     [rbp+57h+var_88], rdx
0x1800190c0  mov     [rbp+57h+var_98], dx
0x1800190c4  mov     r15, [rsp+110h+var_E0.Flink]
0x1800190c9  lea     rax, [rsp+110h+var_E0]
0x1800190ce  cmp     r15, rax
0x1800190d1  jz      loc_1800191B7
0x1800190d7  lea     r13, [r15]
0x1800190da  mov     r15, [r15]
0x1800190dd  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800190e1  inc     r12
0x1800190e4  cmp     [r13+r12*2+10h], dx
0x1800190ea  jnz     short loc_1800190E1
0x1800190ec  mov     rdi, [rbp+57h+var_58]
0x1800190f0  mov     rbx, [rdi]
0x1800190f3  cmp     rbx, rdi
0x1800190f6  jz      loc_1800191A1
0x1800190fc  lea     rdx, [rbx+20h]
0x180019100  lea     rcx, [rbp+57h+String2]
0x180019104  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019109  nop
0x18001910a  mov     r8, [rbp+57h+var_A8]
0x18001910e  cmp     r12, r8
0x180019111  cmovb   r8, r12; MaxCount
0x180019115  lea     rdx, [rbp+57h+String2]
0x180019119  cmp     [rbp+57h+var_A0], 8
0x18001911e  cmovnb  rdx, [rbp+57h+String2]; String2
0x180019123  lea     rcx, [r13+10h]; String1
0x180019127  call    cs:__imp__wcsnicmp
0x18001912d  test    eax, eax
0x18001912f  jnz     short loc_180019154
0x180019131  lea     rcx, [rbp+57h+String2]
0x180019135  cmp     [rbp+57h+var_A0], 8
0x18001913a  cmovnb  rcx, [rbp+57h+String2]
0x18001913f  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180019144  mov     r8, rax
0x180019147  mov     rdx, rcx
0x18001914a  lea     rcx, [rbp+57h+var_98]
0x18001914e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180019153  nop
0x180019154  xor     r8d, r8d
0x180019157  mov     dl, 1
0x180019159  lea     rcx, [rbp+57h+String2]
0x18001915d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180019162  xor     edx, edx
0x180019164  cmp     [rbx+19h], dl
0x180019167  jnz     short loc_1800190F3
0x180019169  mov     rcx, [rbx+10h]
0x18001916d  cmp     [rcx+19h], dl
0x180019170  jnz     short loc_180019181
0x180019172  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180019177  mov     rbx, rax
0x18001917a  xor     edx, edx
0x18001917c  jmp     loc_1800190F3
0x180019181  mov     rax, [rbx+8]
0x180019185  jmp     short loc_180019194
0x180019187  cmp     rbx, [rax+10h]
0x18001918b  jnz     short loc_180019199
0x18001918d  mov     rbx, rax
0x180019190  mov     rax, [rax+8]
0x180019194  cmp     [rax+19h], dl
0x180019197  jz      short loc_180019187
0x180019199  mov     rbx, rax
0x18001919c  jmp     loc_1800190F3
0x1800191a1  lea     rax, [rsp+110h+var_E0]
0x1800191a6  cmp     r15, rax
0x1800191a9  jnz     loc_1800190D7
0x1800191af  cmp     [rbp+57h+var_88], rdx
0x1800191b3  mov     al, dl
0x1800191b5  jnz     short loc_1800191B9
0x1800191b7  mov     al, 1
0x1800191b9  lea     rbx, [rbp+57h+var_98]
0x1800191bd  lea     rcx, [rbp+57h+var_78]
0x1800191c1  test    al, al
0x1800191c3  cmovnz  rbx, rcx
0x1800191c7  lea     rdx, [rbp+57h+var_78]
0x1800191cb  mov     rcx, r14
0x1800191ce  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x1800191d3  mov     rcx, rax
0x1800191d6  mov     rdx, rbx
0x1800191d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800191de  nop
0x1800191df  xor     r8d, r8d
0x1800191e2  mov     dl, 1
0x1800191e4  lea     rcx, [rbp+57h+var_98]
0x1800191e8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800191ed  nop
0x1800191ee  lea     rcx, [rbp+57h+var_78]
0x1800191f2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::set<std::wstring>>::~pair<std::wstring const,std::set<std::wstring>>(void)
0x1800191f7  lea     rcx, [rsp+110h+var_E8]
0x1800191fc  call    ??E?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::set<std::wstring>>>>>::operator++(void)
0x180019201  mov     rax, [rsp+110h+var_E8]
0x180019206  jmp     loc_18001908A
0x18001920b  mov     r14d, [rsp+110h+var_F0]
0x180019210  lea     rcx, [rsp+110h+var_E0]; struct _LIST_ENTRY *
0x180019215  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001921a  nop
0x18001921b  lea     rcx, [rbp+57h+var_C8]
0x18001921f  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x180019224  mov     eax, r14d
0x180019227  mov     rcx, [rbp+57h+var_48]
0x18001922b  xor     rcx, rsp; StackCookie
0x18001922e  call    __security_check_cookie
0x180019233  add     rsp, 0D8h
0x18001923a  pop     r15
0x18001923c  pop     r14
0x18001923e  pop     r13
0x180019240  pop     r12
0x180019242  pop     rdi
0x180019243  pop     rsi
0x180019244  pop     rbx
0x180019245  pop     rbp
0x180019246  retn
```

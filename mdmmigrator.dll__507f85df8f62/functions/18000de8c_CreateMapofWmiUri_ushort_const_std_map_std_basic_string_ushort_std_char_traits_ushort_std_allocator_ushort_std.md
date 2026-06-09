# CreateMapofWmiUri(ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18000de8c`
- end: `0x18000e27d`
- name: `?CreateMapofWmiUri@@YAJPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(wchar_t *Str, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010864`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x180003320`
- `0x1800034ac`
- `0x18000763c`
- `0x180007720`
- `0x180007b38`
- `0x180007bec`
- `0x180007f40`
- `0x18000820c`
- `0x1800094dc`
- `0x180009734`
- `0x180009764`
- `0x180009850`
- `0x18000d4f0`
- `0x18000d6b8`
- `0x18000d8c0`
- `0x18000de8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000df24`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000df24`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000e230`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000e230`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000e23a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000e23a`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18000e1ca`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18000e1ca`

## pseudocode

```c
__int64 __fastcall CreateMapofWmiUri(wchar_t *Str, _QWORD *a2)
{
  _QWORD *v4; // rsi
  char *v5; // r15
  char **v6; // rdi
  wchar_t *v7; // rax
  _WORD *v8; // rdx
  unsigned __int64 v9; // r8
  __int128 *v10; // rsi
  char *v11; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // r8
  __int128 *v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rdi
  __int128 *v18; // rax
  _QWORD *v19; // rax
  __int128 v20; // xmm6
  __int64 v21; // rdx
  const wchar_t *v22; // rdx
  size_t v23; // rbx
  size_t v24; // rdi
  const wchar_t *v25; // rcx
  size_t v26; // r8
  int v27; // eax
  __int64 v28; // rdi
  _QWORD *v29; // rsi
  __int64 v30; // rax
  __int64 v32; // [rsp+30h] [rbp-D8h]
  _QWORD v33[3]; // [rsp+38h] [rbp-D0h] BYREF
  char v34[8]; // [rsp+50h] [rbp-B8h] BYREF
  char v35[120]; // [rsp+58h] [rbp-B0h] BYREF
  char v36[104]; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v37; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 v38; // [rsp+148h] [rbp+40h]
  unsigned __int64 v39; // [rsp+150h] [rbp+48h]
  __int128 v40; // [rsp+158h] [rbp+50h] BYREF
  __int64 v41; // [rsp+168h] [rbp+60h]
  __int64 v42; // [rsp+170h] [rbp+68h]
  __int128 v43; // [rsp+178h] [rbp+70h] BYREF
  __int64 v44; // [rsp+188h] [rbp+80h]
  __int64 v45; // [rsp+190h] [rbp+88h]
  wchar_t *S1[2]; // [rsp+198h] [rbp+90h] BYREF
  size_t v47; // [rsp+1A8h] [rbp+A0h]
  unsigned __int64 v48; // [rsp+1B0h] [rbp+A8h]

  v4 = (_QWORD *)*a2;
  v5 = *(char **)(*a2 + 8LL);
  while ( !v5[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      (__int64)a2,
      (__int64)a2,
      *((__int64 **)v5 + 2));
    v6 = (char **)v5;
    v5 = *(char **)v5;
    std::wstring::~wstring(v6 + 8);
    std::wstring::~wstring(v6 + 4);
    operator delete(v6, (const struct std::nothrow_t *)0x60);
  }
  v4[1] = v4;
  *v4 = v4;
  v4[2] = v4;
  a2[1] = 0;
  v7 = wcschr(Str, 0x2Eu);
  if ( v7 )
  {
    v8 = v7 + 1;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    std::wstring::_Construct<1,unsigned short const *>(&v43, v8, v9);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
      v33,
      &v43);
    std::wstring::~wstring((char **)&v43);
    v37 = 0;
    v38 = 0;
    v39 = 7;
    LOWORD(v37) = 0;
    *(_OWORD *)S1 = 0;
    v47 = 0;
    v48 = 7;
    LOWORD(S1[0]) = 0;
    v43 = 0;
    v44 = 0;
    v45 = 7;
    LOWORD(v43) = 0;
    while ( 1 )
    {
      do
      {
        v30 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v33, &v37);
        if ( !(unsigned __int8)std::ios_base::operator bool(v30 + *(int *)(*(_QWORD *)v30 + 4LL)) )
        {
          std::wstring::~wstring((char **)&v43);
          std::wstring::~wstring((char **)S1);
          std::wstring::~wstring((char **)&v37);
          *(_QWORD *)((char *)v33 + *(int *)(v33[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
          *(_DWORD *)((char *)&v32 + *(int *)(v33[0] + 4LL) + 4) = *(_DWORD *)(v33[0] + 4LL) - 152;
          std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v34);
          std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v35);
          std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v36);
          return 0;
        }
        v10 = &v37;
        if ( v39 > 7 )
          v10 = (__int128 *)v37;
        if ( !v38
          || (v11 = (char *)v10 + 2 * v38, trivial_2 = _std_find_trivial_2(v10, v11, 61), (char *)trivial_2 == v11) )
        {
          v13 = -1;
        }
        else
        {
          v13 = (trivial_2 - (__int64)v10) >> 1;
        }
      }
      while ( v13 == -1 );
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v14 = v38;
      if ( v38 >= v13 )
        v14 = v13;
      v15 = &v37;
      if ( v39 > 7 )
        v15 = (__int128 *)v37;
      std::wstring::_Construct<1,unsigned short const *>(&v40, v15, v14);
      std::wstring::operator=((char **)S1, (__int64)&v40);
      std::wstring::~wstring((char **)&v40);
      v17 = v13 + 1;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      if ( v38 < v17 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v16);
      v18 = &v37;
      if ( v39 > 7 )
        v18 = (__int128 *)v37;
      std::wstring::_Construct<1,unsigned short const *>(&v40, (char *)v18 + 2 * v17, v38 - v17);
      std::wstring::operator=((char **)&v43, (__int64)&v40);
      std::wstring::~wstring((char **)&v40);
      v19 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
              (__int64)a2,
              &v40,
              (__int64)S1);
      v20 = *(_OWORD *)v19;
      v21 = v19[2];
      if ( *(_BYTE *)(v21 + 25) )
      {
LABEL_33:
        if ( a2[1] == 0x2AAAAAAAAAAAAAALL )
          std::_Throw_tree_length_error();
        v28 = *a2;
        v29 = operator new(0x60u);
        *(_QWORD *)&v40 = v29 + 4;
        std::wstring::wstring((__int64)(v29 + 4), (__int64)S1);
        std::wstring::wstring((__int64)(v29 + 8), (__int64)&v43);
        *v29 = v28;
        v29[1] = v28;
        v29[2] = v28;
        *((_WORD *)v29 + 12) = 0;
        HIDWORD(v32) = 0;
        v40 = v20;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(a2, &v40, v29);
      }
      else
      {
        v22 = (const wchar_t *)(v21 + 32);
        v23 = *((_QWORD *)v22 + 2);
        if ( *((_QWORD *)v22 + 3) > 7u )
          v22 = *(const wchar_t **)v22;
        v24 = v47;
        v25 = (const wchar_t *)S1;
        if ( v48 > 7 )
          v25 = S1[0];
        v26 = v47;
        if ( v23 < v47 )
          v26 = v23;
        v27 = wmemcmp(v25, v22, v26);
        if ( v27 )
        {
          if ( v27 < 0 )
            goto LABEL_33;
        }
        else if ( v24 < v23 )
        {
          goto LABEL_33;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000de8c  mov     rax, rsp
0x18000de8f  mov     [rax+18h], rbx
0x18000de93  push    rbp
0x18000de94  push    rsi
0x18000de95  push    rdi
0x18000de96  push    r12
0x18000de98  push    r13
0x18000de9a  push    r14
0x18000de9c  push    r15
0x18000de9e  lea     rbp, [rax-108h]
0x18000dea5  sub     rsp, 1D0h
0x18000deac  movaps  xmmword ptr [rax-48h], xmm6
0x18000deb0  mov     rax, cs:__security_cookie
0x18000deb7  xor     rax, rsp
0x18000deba  mov     [rbp+100h+var_50], rax
0x18000dec1  mov     r14, rdx
0x18000dec4  mov     r12, rcx
0x18000dec7  xor     r13d, r13d
0x18000deca  mov     rsi, [rdx]
0x18000decd  mov     r15, [rsi+8]
0x18000ded1  jmp     short loc_18000DF07
0x18000ded3  mov     r8, [r15+10h]
0x18000ded7  mov     rdx, r14
0x18000deda  mov     rcx, r14
0x18000dedd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18000dee2  mov     rdi, r15
0x18000dee5  mov     r15, [r15]
0x18000dee8  lea     rcx, [rdi+40h]; void *
0x18000deec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000def1  lea     rcx, [rdi+20h]; void *
0x18000def5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000defa  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x18000deff  mov     rcx, rdi; void *
0x18000df02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df07  cmp     [r15+19h], r13b
0x18000df0b  jz      short loc_18000DED3
0x18000df0d  mov     [rsi+8], rsi
0x18000df11  mov     [rsi], rsi
0x18000df14  mov     [rsi+10h], rsi
0x18000df18  mov     [r14+8], r13
0x18000df1c  mov     edx, 2Eh ; '.'; Ch
0x18000df21  mov     rcx, r12; Str
0x18000df24  call    cs:__imp_wcschr
0x18000df2a  test    rax, rax
0x18000df2d  jz      loc_18000E240
0x18000df33  lea     rdx, [rax+2]
0x18000df37  xorps   xmm0, xmm0
0x18000df3a  movups  [rbp+100h+var_90], xmm0
0x18000df3e  mov     [rbp+100h+var_80], r13
0x18000df45  mov     [rbp+100h+var_78], r13
0x18000df4c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000df50  mov     r8, r15
0x18000df53  inc     r8
0x18000df56  cmp     [rdx+r8*2], r13w
0x18000df5b  jnz     short loc_18000DF53
0x18000df5d  lea     rcx, [rbp+100h+var_90]
0x18000df61  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000df66  nop
0x18000df67  lea     rdx, [rbp+100h+var_90]
0x18000df6b  lea     rcx, [rsp+200h+var_1D0]
0x18000df70  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring const &,int)
0x18000df75  nop
0x18000df76  lea     rcx, [rbp+100h+var_90]; void *
0x18000df7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df7f  xorps   xmm0, xmm0
0x18000df82  movups  [rbp+100h+var_D0], xmm0
0x18000df86  mov     [rbp+100h+var_C0], r13
0x18000df8a  mov     r12d, 7
0x18000df90  mov     [rbp+100h+var_B8], r12
0x18000df94  mov     word ptr [rbp+100h+var_D0], r13w
0x18000df99  movups  xmmword ptr [rbp+100h+S1], xmm0
0x18000dfa0  mov     [rbp+100h+var_60], r13
0x18000dfa7  mov     [rbp+100h+var_58], r12
0x18000dfae  mov     word ptr [rbp+100h+S1], r13w
0x18000dfb6  movups  [rbp+100h+var_90], xmm0
0x18000dfba  mov     [rbp+100h+var_80], r13
0x18000dfc1  mov     [rbp+100h+var_78], r12
0x18000dfc8  mov     word ptr [rbp+100h+var_90], r13w
0x18000dfcd  jmp     loc_18000E1B2
0x18000dfd2  mov     rax, [rbp+100h+var_C0]
0x18000dfd6  lea     rsi, [rbp+100h+var_D0]
0x18000dfda  cmp     [rbp+100h+var_B8], r12
0x18000dfde  cmova   rsi, qword ptr [rbp+100h+var_D0]
0x18000dfe3  test    rax, rax
0x18000dfe6  jz      short loc_18000E00D
0x18000dfe8  lea     rbx, [rsi+rax*2]
0x18000dfec  mov     r8d, 3Dh ; '='
0x18000dff2  mov     rdx, rbx
0x18000dff5  mov     rcx, rsi
0x18000dff8  call    __std_find_trivial_2
0x18000dffd  mov     rdi, rax
0x18000e000  cmp     rax, rbx
0x18000e003  jz      short loc_18000E00D
0x18000e005  sub     rdi, rsi
0x18000e008  sar     rdi, 1
0x18000e00b  jmp     short loc_18000E010
0x18000e00d  mov     rdi, r15
0x18000e010  cmp     rdi, r15
0x18000e013  jz      loc_18000E1B2
0x18000e019  xorps   xmm0, xmm0
0x18000e01c  movups  [rbp+100h+var_B0], xmm0
0x18000e020  mov     [rbp+100h+var_A0], r13
0x18000e024  mov     [rbp+100h+var_98], r13
0x18000e028  mov     r8, [rbp+100h+var_C0]
0x18000e02c  cmp     r8, rdi
0x18000e02f  cmovnb  r8, rdi
0x18000e033  lea     rdx, [rbp+100h+var_D0]
0x18000e037  cmp     [rbp+100h+var_B8], r12
0x18000e03b  cmova   rdx, qword ptr [rbp+100h+var_D0]
0x18000e040  lea     rcx, [rbp+100h+var_B0]
0x18000e044  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e049  lea     rdx, [rbp+100h+var_B0]
0x18000e04d  lea     rcx, [rbp+100h+S1]
0x18000e054  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e059  lea     rcx, [rbp+100h+var_B0]; void *
0x18000e05d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e062  inc     rdi
0x18000e065  xorps   xmm0, xmm0
0x18000e068  movups  [rbp+100h+var_B0], xmm0
0x18000e06c  mov     [rbp+100h+var_A0], r13
0x18000e070  mov     [rbp+100h+var_98], r13
0x18000e074  mov     rax, [rbp+100h+var_C0]
0x18000e078  cmp     rax, rdi
0x18000e07b  jb      loc_18000E277
0x18000e081  mov     r8, rax
0x18000e084  sub     r8, rdi
0x18000e087  cmp     r8, rax
0x18000e08a  cmovnb  r8, rax
0x18000e08e  lea     rax, [rbp+100h+var_D0]
0x18000e092  cmp     [rbp+100h+var_B8], r12
0x18000e096  cmova   rax, qword ptr [rbp+100h+var_D0]
0x18000e09b  lea     rdx, [rax+rdi*2]
0x18000e09f  lea     rcx, [rbp+100h+var_B0]
0x18000e0a3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e0a8  lea     rdx, [rbp+100h+var_B0]
0x18000e0ac  lea     rcx, [rbp+100h+var_90]
0x18000e0b0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e0b5  lea     rcx, [rbp+100h+var_B0]; void *
0x18000e0b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e0be  lea     r8, [rbp+100h+S1]
0x18000e0c5  lea     rdx, [rbp+100h+var_B0]
0x18000e0c9  mov     rcx, r14
0x18000e0cc  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000e0d1  movups  xmm6, xmmword ptr [rax]
0x18000e0d4  mov     rdx, [rax+10h]
0x18000e0d8  cmp     [rdx+19h], r13b
0x18000e0dc  jnz     short loc_18000E130
0x18000e0de  add     rdx, 20h ; ' '
0x18000e0e2  mov     rbx, [rdx+10h]
0x18000e0e6  cmp     [rdx+18h], r12
0x18000e0ea  jbe     short loc_18000E0EF
0x18000e0ec  mov     rdx, [rdx]; S2
0x18000e0ef  mov     rdi, [rbp+100h+var_60]
0x18000e0f6  lea     rcx, [rbp+100h+S1]
0x18000e0fd  cmp     [rbp+100h+var_58], r12
0x18000e104  cmova   rcx, [rbp+100h+S1]; S1
0x18000e10c  mov     r8, rdi
0x18000e10f  cmp     rbx, rdi
0x18000e112  cmovb   r8, rbx; N
0x18000e116  call    wmemcmp
0x18000e11b  test    eax, eax
0x18000e11d  jz      short loc_18000E127
0x18000e11f  jns     loc_18000E1B2
0x18000e125  jmp     short loc_18000E130
0x18000e127  cmp     rdi, rbx
0x18000e12a  jnb     loc_18000E1B2
0x18000e130  mov     rax, 2AAAAAAAAAAAAAAh
0x18000e13a  cmp     [r14+8], rax
0x18000e13e  jz      loc_18000E271
0x18000e144  mov     rdi, [r14]
0x18000e147  mov     [rsp+200h+var_1E0], r14
0x18000e14c  mov     [rsp+200h+var_1D8], r13
0x18000e151  mov     ecx, 60h ; '`'; Size
0x18000e156  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e15b  mov     rsi, rax
0x18000e15e  mov     [rsp+200h+var_1D8], rax
0x18000e163  lea     rbx, [rax+20h]
0x18000e167  mov     qword ptr [rbp+100h+var_B0], rbx
0x18000e16b  lea     rdx, [rbp+100h+S1]
0x18000e172  mov     rcx, rbx
0x18000e175  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e17a  nop
0x18000e17b  lea     rcx, [rbx+20h]
0x18000e17f  lea     rdx, [rbp+100h+var_90]
0x18000e183  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e188  nop
0x18000e189  mov     [rsi], rdi
0x18000e18c  mov     [rsi+8], rdi
0x18000e190  mov     [rsi+10h], rdi
0x18000e194  mov     [rsi+18h], r13w
0x18000e199  mov     [rsp+200h+var_1D8], r13
0x18000e19e  movdqu  [rbp+100h+var_B0], xmm6
0x18000e1a3  mov     r8, rsi
0x18000e1a6  lea     rdx, [rbp+100h+var_B0]
0x18000e1aa  mov     rcx, r14
0x18000e1ad  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000e1b2  lea     rdx, [rbp+100h+var_D0]
0x18000e1b6  lea     rcx, [rsp+200h+var_1D0]
0x18000e1bb  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x18000e1c0  mov     rcx, [rax]
0x18000e1c3  movsxd  rcx, dword ptr [rcx+4]
0x18000e1c7  add     rcx, rax
0x18000e1ca  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x18000e1d0  test    al, al
0x18000e1d2  jnz     loc_18000DFD2
0x18000e1d8  lea     rcx, [rbp+100h+var_90]; void *
0x18000e1dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e1e1  nop
0x18000e1e2  lea     rcx, [rbp+100h+S1]; void *
0x18000e1e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e1ee  nop
0x18000e1ef  lea     rcx, [rbp+100h+var_D0]; void *
0x18000e1f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e1f8  nop
0x18000e1f9  mov     rax, [rsp+200h+var_1D0]
0x18000e1fe  movsxd  rcx, dword ptr [rax+4]
0x18000e202  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x18000e209  mov     [rsp+rcx+200h+var_1D0], rax
0x18000e20e  mov     rax, [rsp+200h+var_1D0]
0x18000e213  movsxd  rcx, dword ptr [rax+4]
0x18000e217  lea     edx, [rcx-98h]
0x18000e21d  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x18000e221  lea     rcx, [rsp+200h+var_1B8]
0x18000e226  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18000e22b  lea     rcx, [rsp+200h+var_1B0]
0x18000e230  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x18000e236  lea     rcx, [rbp+100h+var_138]
0x18000e23a  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18000e240  xor     eax, eax
0x18000e242  mov     rcx, [rbp+100h+var_50]
0x18000e249  xor     rcx, rsp; StackCookie
0x18000e24c  call    __security_check_cookie
0x18000e251  lea     r11, [rsp+200h+var_30]
0x18000e259  mov     rbx, [r11+50h]
0x18000e25d  movaps  xmm6, xmmword ptr [r11-10h]
0x18000e262  mov     rsp, r11
0x18000e265  pop     r15
0x18000e267  pop     r14
0x18000e269  pop     r13
0x18000e26b  pop     r12
0x18000e26d  pop     rdi
0x18000e26e  pop     rsi
0x18000e26f  pop     rbp
0x18000e270  retn
0x18000e271  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18000e277  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```

# Container::Manager::Tools::CommandLineParser::Initialize(uint,ushort const * * const,ushort)

- ea: `0x140020e00`
- end: `0x14002127f`
- name: `?Initialize@CommandLineParser@Tools@Manager@Container@@QEAAJIQEAPEBGG@Z`
- size: `1151`
- prototype: `__int64 __fastcall(Container::Manager::Tools::CommandLineParser *this, unsigned int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400094c8`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140009010`
- `0x14000a7a4`
- `0x14000c7a8`
- `0x14000cd84`
- `0x1400209a4`
- `0x140020e00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020fdd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002101e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140020fdd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002101e`

## pseudocode

```c
__int64 __fastcall Container::Manager::Tools::CommandLineParser::Initialize(
        Container::Manager::Tools::CommandLineParser *this,
        unsigned int a2,
        const unsigned __int16 **const a3)
{
  Container::Manager::Tools::CommandLineParser *v5; // rbx
  const unsigned __int16 *v6; // rdx
  unsigned __int64 v7; // r8
  void *v8; // rcx
  int v9; // r14d
  const unsigned __int16 *v10; // rdx
  unsigned __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rdx
  int *v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rax
  char v17; // al
  const unsigned __int16 *v18; // rdx
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rsi
  __int64 v21; // r14
  int *v22; // rbx
  int *v23; // r15
  __int64 v24; // r12
  __int64 v26; // rdx
  int v27[2]; // [rsp+20h] [rbp-99h] BYREF
  int *v28; // [rsp+28h] [rbp-91h]
  int *v29; // [rsp+30h] [rbp-89h]
  __int64 v30; // [rsp+38h] [rbp-81h]
  void *v31; // [rsp+40h] [rbp-79h] BYREF
  char *v32; // [rsp+48h] [rbp-71h]
  _WORD v33[8]; // [rsp+50h] [rbp-69h] BYREF
  void *v34[2]; // [rsp+60h] [rbp-59h] BYREF
  _WORD v35[8]; // [rsp+70h] [rbp-49h] BYREF
  void *v36[2]; // [rsp+80h] [rbp-39h] BYREF
  _WORD v37[8]; // [rsp+90h] [rbp-29h] BYREF
  void *v38[2]; // [rsp+A0h] [rbp-19h] BYREF
  _WORD v39[8]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+7h] BYREF
  char v41; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v5 = this;
  if ( a2 < 2 )
    return 0;
  v34[0] = v35;
  v34[1] = v35;
  v35[0] = 0;
  v6 = a3[1];
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
  }
  else
  {
    v7 = 0;
  }
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v34,
          v6,
          v7) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
      (const char *)0x8007000ELL,
      v27[0]);
    v8 = v34[0];
    if ( v34[0] != v35 )
      goto LABEL_73;
    return 2147942414LL;
  }
  v36[0] = v37;
  v36[1] = v37;
  v37[0] = 0;
  *(_QWORD *)v27 = v27;
  v28 = v27;
  v29 = v27;
  v30 = 0;
  v9 = 2;
  if ( a2 <= 2 )
  {
LABEL_48:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (__int64)v5,
      (__int64)v34);
    v20 = (unsigned __int64)v5 + 32;
    v21 = *(_QWORD *)v27;
    v22 = v28;
    v23 = v29;
    v24 = v30;
    *(_QWORD *)v27 = v27;
    v28 = v27;
    v29 = v27;
    v30 = 0;
    utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear((_QWORD *)v20);
    if ( v23 != v27 )
    {
      *(_QWORD *)(v21 & 0xFFFFFFFFFFFFFFFEuLL) = v20 | 1;
      *(_QWORD *)v20 = v21;
      *(_QWORD *)(v20 + 8) = v22;
      *(_QWORD *)(v20 + 16) = v23;
      *(_QWORD *)(v20 + 24) = v24;
    }
    utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(v27);
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  while ( 1 )
  {
    v31 = v33;
    v32 = (char *)v33;
    v33[0] = 0;
    v10 = a3[v9];
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
    }
    else
    {
      v11 = 0;
    }
    if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (__int64)&v31,
            v10,
            v11) )
      break;
    if ( *(_WORD *)v31 == 45 )
    {
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (__int64)v36,
              v31,
              (v32 - (_BYTE *)v31) >> 1) )
      {
        v26 = 81;
        goto LABEL_68;
      }
      v38[0] = v39;
      v38[1] = v39;
      v39[0] = 0;
      utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::emplace<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
        (unsigned __int64)v27,
        (__int64)&v40,
        &v31,
        v38);
      if ( v38[0] != v39 )
        operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( !v40 )
      {
        v26 = 84;
        goto LABEL_68;
      }
      if ( !v41 )
      {
        v13 = 87;
LABEL_60:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
          (const char *)0x80070057LL,
          v27[0]);
        if ( v31 != v33 )
          operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(v27);
        if ( v36[0] != v37 )
          operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v34[0] != v35 )
          operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
        return 2147942487LL;
      }
      goto LABEL_44;
    }
    if ( v9 == 2 )
    {
      v13 = 92;
      goto LABEL_60;
    }
    v14 = v27;
    if ( v29 != v27 )
    {
      v15 = *(_QWORD *)v27;
      do
      {
        if ( (int)_o__wcsicmp(*(_QWORD *)(v15 + 24), v36[0]) < 0 )
        {
          v16 = 16;
        }
        else
        {
          v14 = (int *)v15;
          v16 = 8;
        }
        v15 = *(_QWORD *)(v16 + v15);
      }
      while ( (void **)v15 != &utl::_TreeSentinel );
      if ( v14 != v27 )
      {
        if ( (int)_o__wcsicmp(v36[0], *((_QWORD *)v14 + 3)) >= 0 )
        {
          v17 = 0;
          goto LABEL_36;
        }
        v14 = v27;
      }
    }
    v17 = 1;
LABEL_36:
    if ( v17 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x62,
        (int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
        v12);
    if ( *((_QWORD *)v14 + 7) != *((_QWORD *)v14 + 8) )
    {
      v13 = 104;
      goto LABEL_60;
    }
    v18 = a3[v9];
    if ( v18 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
    }
    else
    {
      v19 = 0;
    }
    if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (__int64)(v14 + 14),
            v18,
            v19) )
    {
      v26 = 107;
      goto LABEL_68;
    }
LABEL_44:
    if ( v31 != v33 )
      operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
    if ( ++v9 >= a2 )
    {
      v5 = this;
      goto LABEL_48;
    }
  }
  v26 = 74;
LABEL_68:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\tools\\helpers\\helpers.cpp",
    (const char *)0x8007000ELL,
    v27[0]);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(v27);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  v8 = v34[0];
  if ( v34[0] != v35 )
LABEL_73:
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140020e00  mov     [rsp-8+arg_0], rcx
0x140020e05  push    rbp
0x140020e06  push    rbx
0x140020e07  push    rsi
0x140020e08  push    rdi
0x140020e09  push    r12
0x140020e0b  push    r13
0x140020e0d  push    r14
0x140020e0f  push    r15
0x140020e11  lea     rbp, [rsp-1Fh]
0x140020e16  sub     rsp, 0D8h
0x140020e1d  mov     r13, r8
0x140020e20  mov     r12d, edx
0x140020e23  mov     rbx, rcx
0x140020e26  cmp     edx, 2
0x140020e29  jb      loc_140021158
0x140020e2f  lea     rax, [rbp+57h+var_A0]
0x140020e33  mov     [rbp+57h+var_B0], rax
0x140020e37  lea     rax, [rbp+57h+var_A0]
0x140020e3b  mov     [rbp+57h+var_A8], rax
0x140020e3f  xor     esi, esi
0x140020e41  mov     [rbp+57h+var_A0], si
0x140020e45  mov     rdx, [r8+8]
0x140020e49  test    rdx, rdx
0x140020e4c  jz      short loc_140020E5E
0x140020e4e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140020e52  inc     r8
0x140020e55  cmp     [rdx+r8*2], si
0x140020e5a  jnz     short loc_140020E52
0x140020e5c  jmp     short loc_140020E61
0x140020e5e  mov     r8, rsi
0x140020e61  lea     rcx, [rbp+57h+var_B0]
0x140020e65  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140020e6a  test    al, al
0x140020e6c  jnz     short loc_140020EA6
0x140020e6e  mov     rcx, [rbp+5Fh]; this
0x140020e72  mov     r9d, 8007000Eh; char *
0x140020e78  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140020e7f  mov     edx, 41h ; 'A'; void *
0x140020e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020e89  lea     rax, [rbp+57h+var_A0]
0x140020e8d  mov     rcx, [rbp+57h+var_B0]
0x140020e91  cmp     rcx, rax
0x140020e94  jz      loc_140021263
0x140020e9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140020ea1  jmp     loc_14002125E
0x140020ea6  lea     rax, [rbp+57h+var_80]
0x140020eaa  mov     [rbp+57h+var_90], rax
0x140020eae  lea     rax, [rbp+57h+var_80]
0x140020eb2  mov     [rbp+57h+var_88], rax
0x140020eb6  mov     [rbp+57h+var_80], si
0x140020eba  lea     rax, [rsp+110h+var_F0]
0x140020ebf  mov     qword ptr [rsp+110h+var_F0], rax; int
0x140020ec4  lea     rax, [rsp+110h+var_F0]
0x140020ec9  mov     [rsp+110h+var_E8], rax
0x140020ece  mov     [rsp+110h+var_E0], rax
0x140020ed3  mov     [rsp+110h+var_D8], rsi
0x140020ed8  mov     r14d, 2
0x140020ede  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140020ee5  cmp     r12d, r14d
0x140020ee8  jbe     loc_1400210AC
0x140020eee  lea     rax, [rbp+57h+var_C0]
0x140020ef2  mov     [rbp+57h+var_D0], rax
0x140020ef6  lea     rax, [rbp+57h+var_C0]
0x140020efa  mov     [rbp+57h+var_C8], rax
0x140020efe  mov     [rbp+57h+var_C0], si
0x140020f02  mov     r15d, r14d
0x140020f05  mov     rdx, [r13+r15*8+0]
0x140020f0a  test    rdx, rdx
0x140020f0d  jz      short loc_140020F1F
0x140020f0f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140020f13  inc     r8
0x140020f16  cmp     [rdx+r8*2], si
0x140020f1b  jnz     short loc_140020F13
0x140020f1d  jmp     short loc_140020F22
0x140020f1f  mov     r8, rsi
0x140020f22  lea     rcx, [rbp+57h+var_D0]
0x140020f26  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140020f2b  test    al, al
0x140020f2d  jz      loc_1400211FF
0x140020f33  mov     rdx, [rbp+57h+var_D0]
0x140020f37  cmp     word ptr [rdx], 2Dh ; '-'
0x140020f3b  jnz     short loc_140020FB5
0x140020f3d  mov     r8, [rbp+57h+var_C8]
0x140020f41  sub     r8, rdx
0x140020f44  sar     r8, 1
0x140020f47  lea     rcx, [rbp+57h+var_90]
0x140020f4b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140020f50  test    al, al
0x140020f52  jz      loc_140021179
0x140020f58  lea     rax, [rbp+57h+var_60]
0x140020f5c  mov     [rbp+57h+var_70], rax
0x140020f60  lea     rax, [rbp+57h+var_60]
0x140020f64  mov     [rbp+57h+var_68], rax
0x140020f68  mov     [rbp+57h+var_60], si
0x140020f6c  lea     r9, [rbp+57h+var_70]
0x140020f70  lea     r8, [rbp+57h+var_D0]
0x140020f74  lea     rdx, [rbp+57h+var_50]
0x140020f78  lea     rcx, [rsp+110h+var_F0]
0x140020f7d  call    ??$emplace@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@$0A@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@0@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::emplace<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x140020f82  lea     rax, [rbp+57h+var_60]
0x140020f86  mov     rcx, [rbp+57h+var_70]; void *
0x140020f8a  cmp     rcx, rax
0x140020f8d  jz      short loc_140020F97
0x140020f8f  mov     rdx, rdi; struct std::nothrow_t *
0x140020f92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020f97  cmp     [rbp+57h+var_50], rsi
0x140020f9b  jz      loc_14002116F
0x140020fa1  cmp     [rbp+57h+var_48], sil
0x140020fa5  jnz     loc_140021087
0x140020fab  mov     edx, 57h ; 'W'
0x140020fb0  jmp     loc_140021196
0x140020fb5  cmp     r14d, 2
0x140020fb9  jz      loc_140021191
0x140020fbf  lea     rax, [rsp+110h+var_F0]
0x140020fc4  lea     rbx, [rsp+110h+var_F0]
0x140020fc9  cmp     [rsp+110h+var_E0], rax
0x140020fce  jz      short loc_14002103E
0x140020fd0  mov     rsi, qword ptr [rsp+110h+var_F0]
0x140020fd5  mov     rdx, [rbp+57h+var_90]
0x140020fd9  mov     rcx, [rsi+18h]
0x140020fdd  call    cs:__imp__o__wcsicmp
0x140020fe4  nop     dword ptr [rax+rax+00h]
0x140020fe9  test    eax, eax
0x140020feb  js      short loc_140020FF7
0x140020fed  mov     rbx, rsi
0x140020ff0  mov     eax, 8
0x140020ff5  jmp     short loc_140020FFC
0x140020ff7  mov     eax, 10h
0x140020ffc  mov     rsi, [rax+rsi]
0x140021000  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140021007  cmp     rsi, rax
0x14002100a  jnz     short loc_140020FD5
0x14002100c  lea     rax, [rsp+110h+var_F0]
0x140021011  cmp     rbx, rax
0x140021014  jz      short loc_14002103C
0x140021016  mov     rdx, [rbx+18h]
0x14002101a  mov     rcx, [rbp+57h+var_90]
0x14002101e  call    cs:__imp__o__wcsicmp
0x140021025  nop     dword ptr [rax+rax+00h]
0x14002102a  xor     esi, esi
0x14002102c  test    eax, eax
0x14002102e  jns     short loc_140021037
0x140021030  lea     rbx, [rsp+110h+var_F0]
0x140021035  jmp     short loc_14002103E
0x140021037  mov     al, sil
0x14002103a  jmp     short loc_140021040
0x14002103c  xor     esi, esi
0x14002103e  mov     al, 1
0x140021040  mov     rcx, [rbp+5Fh]; this
0x140021044  test    al, al
0x140021046  jnz     loc_14002126D
0x14002104c  lea     rcx, [rbx+38h]
0x140021050  mov     rax, [rbx+40h]
0x140021054  cmp     [rcx], rax
0x140021057  jnz     loc_14002118A
0x14002105d  mov     rdx, [r13+r15*8+0]
0x140021062  test    rdx, rdx
0x140021065  jz      short loc_140021077
0x140021067  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002106b  inc     r8
0x14002106e  cmp     [rdx+r8*2], si
0x140021073  jnz     short loc_14002106B
0x140021075  jmp     short loc_14002107A
0x140021077  mov     r8, rsi
0x14002107a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14002107f  test    al, al
0x140021081  jz      loc_140021183
0x140021087  lea     rax, [rbp+57h+var_C0]
0x14002108b  mov     rcx, [rbp+57h+var_D0]; void *
0x14002108f  cmp     rcx, rax
0x140021092  jz      short loc_14002109C
0x140021094  mov     rdx, rdi; struct std::nothrow_t *
0x140021097  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002109c  inc     r14d
0x14002109f  cmp     r14d, r12d
0x1400210a2  jb      loc_140020EEE
0x1400210a8  mov     rbx, [rbp+57h+arg_0]
0x1400210ac  lea     rdx, [rbp+57h+var_B0]
0x1400210b0  mov     rcx, rbx
0x1400210b3  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1400210b8  lea     rsi, [rbx+20h]
0x1400210bc  mov     r14, qword ptr [rsp+110h+var_F0]
0x1400210c1  mov     rbx, [rsp+110h+var_E8]
0x1400210c6  mov     r15, [rsp+110h+var_E0]
0x1400210cb  mov     r12, [rsp+110h+var_D8]
0x1400210d0  lea     rax, [rsp+110h+var_F0]
0x1400210d5  mov     qword ptr [rsp+110h+var_F0], rax
0x1400210da  lea     rax, [rsp+110h+var_F0]
0x1400210df  mov     [rsp+110h+var_E8], rax
0x1400210e4  mov     [rsp+110h+var_E0], rax
0x1400210e9  mov     [rsp+110h+var_D8], 0
0x1400210f2  mov     rcx, rsi
0x1400210f5  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x1400210fa  lea     rax, [rsp+110h+var_F0]
0x1400210ff  cmp     r15, rax
0x140021102  jz      short loc_140021124
0x140021104  mov     rcx, rsi
0x140021107  or      rcx, 1
0x14002110b  mov     rax, r14
0x14002110e  and     rax, 0FFFFFFFFFFFFFFFEh
0x140021112  mov     [rax], rcx
0x140021115  mov     [rsi], r14
0x140021118  mov     [rsi+8], rbx
0x14002111c  mov     [rsi+10h], r15
0x140021120  mov     [rsi+18h], r12
0x140021124  lea     rcx, [rsp+110h+var_F0]
0x140021129  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x14002112e  lea     rax, [rbp+57h+var_80]
0x140021132  mov     rcx, [rbp+57h+var_90]; void *
0x140021136  cmp     rcx, rax
0x140021139  jz      short loc_140021143
0x14002113b  mov     rdx, rdi; struct std::nothrow_t *
0x14002113e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140021143  lea     rax, [rbp+57h+var_A0]
0x140021147  mov     rcx, [rbp+57h+var_B0]; void *
0x14002114b  cmp     rcx, rax
0x14002114e  jz      short loc_140021158
0x140021150  mov     rdx, rdi; struct std::nothrow_t *
0x140021153  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140021158  xor     eax, eax
0x14002115a  add     rsp, 0D8h
0x140021161  pop     r15
0x140021163  pop     r14
0x140021165  pop     r13
0x140021167  pop     r12
0x140021169  pop     rdi
0x14002116a  pop     rsi
0x14002116b  pop     rbx
0x14002116c  pop     rbp
0x14002116d  retn
0x14002116f  mov     edx, 54h ; 'T'
0x140021174  jmp     loc_140021204
0x140021179  mov     edx, 51h ; 'Q'
0x14002117e  jmp     loc_140021204
0x140021183  mov     edx, 6Bh ; 'k'
0x140021188  jmp     short loc_140021204
0x14002118a  mov     edx, 68h ; 'h'
0x14002118f  jmp     short loc_140021196
0x140021191  mov     edx, 5Ch ; '\'; void *
0x140021196  mov     r9d, 80070057h; char *
0x14002119c  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x1400211a3  mov     rcx, [rbp+5Fh]; this
0x1400211a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400211ac  lea     rax, [rbp+57h+var_C0]
0x1400211b0  mov     rcx, [rbp+57h+var_D0]; void *
0x1400211b4  cmp     rcx, rax
0x1400211b7  jz      short loc_1400211C1
0x1400211b9  mov     rdx, rdi; struct std::nothrow_t *
0x1400211bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400211c1  lea     rcx, [rsp+110h+var_F0]
0x1400211c6  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x1400211cb  lea     rax, [rbp+57h+var_80]
0x1400211cf  mov     rcx, [rbp+57h+var_90]; void *
0x1400211d3  cmp     rcx, rax
0x1400211d6  jz      short loc_1400211E0
0x1400211d8  mov     rdx, rdi; struct std::nothrow_t *
0x1400211db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400211e0  lea     rax, [rbp+57h+var_A0]
0x1400211e4  mov     rcx, [rbp+57h+var_B0]; void *
0x1400211e8  cmp     rcx, rax
0x1400211eb  jz      short loc_1400211F5
0x1400211ed  mov     rdx, rdi; struct std::nothrow_t *
0x1400211f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400211f5  mov     eax, 80070057h
0x1400211fa  jmp     loc_14002115A
0x1400211ff  mov     edx, 4Ah ; 'J'; void *
0x140021204  mov     r9d, 8007000Eh; char *
0x14002120a  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140021211  mov     rcx, [rbp+5Fh]; this
0x140021215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002121a  lea     rax, [rbp+57h+var_C0]
0x14002121e  mov     rcx, [rbp+57h+var_D0]; void *
0x140021222  cmp     rcx, rax
0x140021225  jz      short loc_14002122F
0x140021227  mov     rdx, rdi; struct std::nothrow_t *
0x14002122a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002122f  lea     rcx, [rsp+110h+var_F0]
0x140021234  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x140021239  lea     rax, [rbp+57h+var_80]
0x14002123d  mov     rcx, [rbp+57h+var_90]; void *
0x140021241  cmp     rcx, rax
0x140021244  jz      short loc_14002124E
0x140021246  mov     rdx, rdi; struct std::nothrow_t *
0x140021249  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002124e  lea     rax, [rbp+57h+var_A0]
0x140021252  mov     rcx, [rbp+57h+var_B0]; void *
0x140021256  cmp     rcx, rax
0x140021259  jz      short loc_140021263
0x14002125b  mov     rdx, rdi; struct std::nothrow_t *
0x14002125e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140021263  mov     eax, 8007000Eh
0x140021268  jmp     loc_14002115A
0x14002126d  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\too"...
0x140021274  mov     edx, 62h ; 'b'; void *
0x140021279  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

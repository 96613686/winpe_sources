# SetInterfaceDnsSuffixSearchList

- ea: `0x1800ab02c`
- end: `0x1800ab767`
- name: `SetInterfaceDnsSuffixSearchList`
- size: `1851`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180050374`

## callees

- `0x180003c5c`
- `0x180003cac`
- `0x180003ea8`
- `0x180003f20`
- `0x180003f40`
- `0x1800040b4`
- `0x1800040c4`
- `0x1800047c4`
- `0x180005e34`
- `0x1800a70bc`
- `0x1800a7ab8`
- `0x1800a7b40`
- `0x1800a7e5c`
- `0x1800a93e8`
- `0x1800a9b3c`
- `0x1800aa0e0`
- `0x1800ab02c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800ab16c`
- `msvcrt!wcstok_s` at `0x1800ab16c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ab23b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ab23b`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800ab5e9`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800ab64a`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800ab5e9`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800ab64a`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800ab0ef`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800ab0ef`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800ab707`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800ab707`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall SetInterfaceDnsSuffixSearchList(void ***a1, unsigned int a2, GUID *a3)
{
  unsigned int v4; // edi
  void ***v5; // r15
  unsigned int v6; // ebx
  unsigned int InterfaceDnsSettings; // eax
  wchar_t *SearchList; // rcx
  wchar_t *v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rbx
  const WCHAR *v14; // r15
  __int64 i; // rdi
  __int64 v16; // r9
  const WCHAR *v17; // rcx
  __int64 v18; // r8
  _QWORD *v19; // rdi
  struct std::locale::_Locimp *v20; // r14
  __int64 v21; // rcx
  __int64 *v22; // r9
  __int64 *v23; // rdx
  char v24; // cl
  __int64 v25; // rax
  __int64 v26; // r8
  WCHAR *v27; // rax
  GUID *v28; // rdi
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v32; // [rsp+30h] [rbp-258h] BYREF
  int v33; // [rsp+34h] [rbp-254h]
  void ***v34; // [rsp+38h] [rbp-250h]
  GUID v35; // [rsp+40h] [rbp-248h] BYREF
  GUID Interface; // [rsp+50h] [rbp-238h] BYREF
  _BYTE v37[8]; // [rsp+60h] [rbp-228h] BYREF
  __int128 v38; // [rsp+68h] [rbp-220h]
  __int64 v39; // [rsp+78h] [rbp-210h]
  _QWORD v40[2]; // [rsp+80h] [rbp-208h]
  __int64 *v41; // [rsp+90h] [rbp-1F8h] BYREF
  void **v42; // [rsp+98h] [rbp-1F0h] BYREF
  _BYTE v43[8]; // [rsp+A0h] [rbp-1E8h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-1E0h] BYREF
  _QWORD v45[3]; // [rsp+B0h] [rbp-1D8h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-1C0h] BYREF
  __int64 v47; // [rsp+D0h] [rbp-1B8h] BYREF
  __int64 *v48; // [rsp+D8h] [rbp-1B0h]
  __int64 *v49; // [rsp+E0h] [rbp-1A8h]
  _QWORD v50[5]; // [rsp+E8h] [rbp-1A0h] BYREF
  int v51; // [rsp+110h] [rbp-178h]
  _QWORD v52[13]; // [rsp+118h] [rbp-170h] BYREF
  DNS_INTERFACE_SETTINGS v53; // [rsp+180h] [rbp-108h] BYREF
  DNS_INTERFACE_SETTINGS Settings; // [rsp+1C0h] [rbp-C8h] BYREF
  _BYTE v55[8]; // [rsp+200h] [rbp-88h] BYREF
  void *v56; // [rsp+208h] [rbp-80h] BYREF
  __int64 v57; // [rsp+218h] [rbp-70h]
  unsigned __int64 v58; // [rsp+220h] [rbp-68h]
  _BYTE v59[8]; // [rsp+228h] [rbp-60h] BYREF
  void *Block; // [rsp+230h] [rbp-58h]
  __int64 v61; // [rsp+240h] [rbp-48h]
  unsigned __int64 v62; // [rsp+248h] [rbp-40h]

  *(_QWORD *)&v35.Data1 = a3;
  v4 = a2;
  v32 = a2;
  v5 = a1;
  v34 = a1;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, a2);
  }
  memset_0(&Settings, 0, sizeof(Settings));
  if ( v4 )
  {
    Settings.Version = 1;
    Settings.Flags = 4;
    Interface = *a3;
    InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
    v6 = InterfaceDnsSettings;
    if ( InterfaceDnsSettings )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 21, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, InterfaceDnsSettings);
      }
    }
    else
    {
      try
      {
        v38 = 0;
        v39 = 0;
        *(_QWORD *)&Interface.Data1 = 0;
        SearchList = Settings.SearchList;
        if ( Settings.SearchList )
        {
          while ( 1 )
          {
            v9 = wcstok_s(SearchList, L",", (wchar_t **)&Interface);
            if ( !v9 )
              break;
            v62 = 7;
            v61 = 0;
            LOWORD(Block) = 0;
            v10 = -1;
            do
              ++v10;
            while ( v9[v10] );
            std::wstring::assign(v59);
            std::vector<std::wstring>::push_back(v37, v59);
            if ( v62 >= 8 )
              operator delete(Block);
            SearchList = 0;
          }
        }
        v11 = 0;
        v12 = *((_QWORD *)&v38 + 1);
        v13 = v38;
        while ( v11 < v4 )
        {
          v14 = (const WCHAR *)&v5[65 * v11];
          for ( i = v13; i != v12; i += 40 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v14[v16] );
            v17 = (const WCHAR *)(i + 8);
            if ( *(_QWORD *)(i + 32) >= 8u )
              v17 = *(const WCHAR **)v17;
            if ( CompareStringOrdinal(v17, *(_DWORD *)(i + 24), v14, v16, 1) == 2 )
            {
              if ( i != v12 )
                goto LABEL_35;
              break;
            }
          }
          v62 = 7;
          v61 = 0;
          LOWORD(Block) = 0;
          v18 = -1;
          do
            ++v18;
          while ( v14[v18] );
          std::wstring::assign(v59);
          std::vector<std::wstring>::push_back(v37, v59);
          if ( v62 >= 8 )
            operator delete(Block);
          LOWORD(Block) = 0;
          v12 = *((_QWORD *)&v38 + 1);
          v13 = v38;
LABEL_35:
          ++v11;
          v4 = v32;
          v5 = v34;
        }
        v40[0] = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_istream<unsigned short>'};
        v41 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
        v33 |= 1u;
        v40[1] = 0;
        v52[0] = &std::basic_ostream<unsigned short>::`vftable';
        std::basic_ios<unsigned short>::init((std::ios_base *)v52);
        *(_QWORD *)((char *)v40 + *(int *)(v40[0] + 4LL)) = &std::basic_iostream<unsigned short>::`vftable';
        *(_QWORD *)((char *)v40 + *(int *)(v40[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
        v34 = &v42;
        v42 = &std::basic_streambuf<unsigned short>::`vftable';
        std::_Mutex::_Mutex((std::_Mutex *)v43);
        v19 = operator new(8u);
        if ( v19 )
        {
          *v19 = std::locale::_Init();
          v20 = std::locale::_Getgloballocale();
          std::_Lockit::_Lockit((std::_Lockit *)&v32, 0);
          v21 = *((_QWORD *)v20 + 1);
          if ( v21 != -1 )
            *((_QWORD *)v20 + 1) = v21 + 1;
          std::_Lockit::~_Lockit((std::_Lockit *)&v32);
        }
        else
        {
          v19 = 0;
        }
        v50[3] = v19;
        v45[1] = &v44;
        v45[2] = v45;
        v22 = &v46;
        v48 = &v46;
        v23 = &v47;
        v49 = &v47;
        v50[1] = v50;
        v50[2] = (char *)v50 + 4;
        v45[0] = 0;
        v47 = 0;
        v50[0] = 0;
        v44 = 0;
        v46 = 0;
        v42 = &std::basic_stringbuf<unsigned short>::`vftable';
        v50[4] = 0;
        v24 = 0;
        v51 = 0;
        if ( v13 && v12 != v13 )
        {
          std::operator<<<unsigned short>(&v41, v13, 0);
          while ( 1 )
          {
            v13 += 40;
            if ( v13 == v12 )
              break;
            v25 = std::basic_ostream<unsigned short>::operator<<(&v41);
            std::operator<<<unsigned short>(v25, v13, v26);
          }
          v24 = v51;
          v23 = v49;
          v22 = v48;
        }
        if ( (v24 & 2) == 0 && *v23 || (v24 & 4) == 0 && *v22 )
        {
          v58 = 7;
          v57 = 0;
          LOWORD(v56) = 0;
          std::wstring::assign(v55);
        }
        else
        {
          v58 = 7;
          v57 = 0;
          LOWORD(v56) = 0;
        }
        memset_0(&v53, 0, sizeof(v53));
        v53.Version = 1;
        v53.Flags = 4;
        v27 = (WCHAR *)&v56;
        if ( v58 >= 8 )
          v27 = (WCHAR *)v56;
        v53.SearchList = v27;
        v28 = *(GUID **)&v35.Data1;
        v35 = *(GUID *)*(_QWORD *)&v35.Data1;
        v29 = SetInterfaceDnsSettings(&v35, &v53);
        v6 = v29;
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v29);
          }
        }
        else
        {
          v53.Flags |= 1uLL;
          v35 = *v28;
          v30 = SetInterfaceDnsSettings(&v35, &v53);
          v6 = v30;
          if ( v30
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 23, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v30);
          }
        }
        if ( v58 >= 8 )
          operator delete(v56);
        v58 = 7;
        v57 = 0;
        LOWORD(v56) = 0;
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v52);
        v52[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v52);
        std::vector<std::wstring>::~vector<std::wstring>(v37);
      }
      catch ( ... )
      {
        v32 = 14;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 24, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, 14);
        }
        v6 = v32;
      }
    }
  }
  else
  {
    v6 = 87;
  }
  FreeInterfaceDnsSettings(&Settings);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 25, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800ab02c  mov     [rsp+arg_18], rbx
0x1800ab031  push    rsi
0x1800ab032  push    rdi
0x1800ab033  push    r13
0x1800ab035  push    r14
0x1800ab037  push    r15
0x1800ab039  sub     rsp, 260h
0x1800ab040  mov     rax, cs:__security_cookie
0x1800ab047  xor     rax, rsp
0x1800ab04a  mov     [rsp+288h+var_38], rax
0x1800ab052  mov     rbx, r8
0x1800ab055  mov     qword ptr [rsp+288h+var_248.Data1], rbx
0x1800ab05a  mov     edi, edx
0x1800ab05c  mov     [rsp+288h+var_258], edx
0x1800ab060  mov     r15, rcx
0x1800ab063  mov     [rsp+288h+var_250], rcx
0x1800ab068  xor     esi, esi
0x1800ab06a  mov     [rsp+288h+var_254], esi
0x1800ab06e  lea     r13, WPP_GLOBAL_Control
0x1800ab075  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab07c  cmp     rcx, r13
0x1800ab07f  jz      short loc_1800AB0A3
0x1800ab081  test    byte ptr [rcx+1Ch], 1
0x1800ab085  jz      short loc_1800AB0A3
0x1800ab087  cmp     byte ptr [rcx+19h], 6
0x1800ab08b  jb      short loc_1800AB0A3
0x1800ab08d  lea     edx, [rsi+14h]
0x1800ab090  mov     r9d, edi
0x1800ab093  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800ab09a  mov     rcx, [rcx+10h]
0x1800ab09e  call    WPP_SF_d
0x1800ab0a3  xor     edx, edx; Val
0x1800ab0a5  lea     r8d, [rdx+40h]; Size
0x1800ab0a9  lea     rcx, [rsp+288h+Settings]; void *
0x1800ab0b1  call    memset_0
0x1800ab0b6  test    edi, edi
0x1800ab0b8  jnz     short loc_1800AB0C2
0x1800ab0ba  lea     ebx, [rdi+57h]
0x1800ab0bd  jmp     loc_1800AB6FF
0x1800ab0c2  mov     [rsp+288h+Settings.Version], 1
0x1800ab0cd  mov     [rsp+288h+Settings.Flags], 4
0x1800ab0d9  movaps  xmm0, xmmword ptr [rbx]
0x1800ab0dc  movdqa  xmmword ptr [rsp+288h+Interface.Data1], xmm0
0x1800ab0e2  lea     rdx, [rsp+288h+Settings]; Settings
0x1800ab0ea  lea     rcx, [rsp+288h+Interface]; Interface
0x1800ab0ef  call    cs:__imp_GetInterfaceDnsSettings
0x1800ab0f5  mov     ebx, eax
0x1800ab0f7  test    eax, eax
0x1800ab0f9  jz      short loc_1800AB13C
0x1800ab0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab102  cmp     rcx, r13
0x1800ab105  jz      loc_1800AB6FF
0x1800ab10b  test    byte ptr [rcx+1Ch], 1
0x1800ab10f  jz      loc_1800AB6FF
0x1800ab115  cmp     byte ptr [rcx+19h], 2
0x1800ab119  jb      loc_1800AB6FF
0x1800ab11f  mov     edx, 15h
0x1800ab124  mov     r9d, eax
0x1800ab127  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800ab12e  mov     rcx, [rcx+10h]
0x1800ab132  call    WPP_SF_d
0x1800ab137  jmp     loc_1800AB6FF
0x1800ab13c  xorps   xmm0, xmm0
0x1800ab13f  movdqu  [rsp+288h+var_220], xmm0
0x1800ab145  mov     [rsp+288h+var_210], rsi
0x1800ab14a  mov     qword ptr [rsp+288h+Interface.Data1], rsi
0x1800ab14f  mov     rcx, [rsp+288h+Settings.SearchList]; String
0x1800ab157  test    rcx, rcx
0x1800ab15a  jz      loc_1800AB1E5
0x1800ab160  lea     r8, [rsp+288h+Interface]; Context
0x1800ab165  lea     rdx, Delimiter; ","
0x1800ab16c  call    cs:__imp_wcstok_s
0x1800ab172  test    rax, rax
0x1800ab175  jz      short loc_1800AB1E5
0x1800ab177  mov     [rsp+288h+var_40], 7
0x1800ab183  mov     [rsp+288h+var_48], rsi
0x1800ab18b  mov     word ptr [rsp+288h+Block], si
0x1800ab193  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ab197  inc     r8
0x1800ab19a  cmp     [rax+r8*2], si
0x1800ab19f  jnz     short loc_1800AB197
0x1800ab1a1  mov     rdx, rax
0x1800ab1a4  lea     rcx, [rsp+288h+var_60]
0x1800ab1ac  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800ab1b1  nop
0x1800ab1b2  lea     rdx, [rsp+288h+var_60]
0x1800ab1ba  lea     rcx, [rsp+288h+var_228]
0x1800ab1bf  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800ab1c4  nop
0x1800ab1c5  cmp     [rsp+288h+var_40], 8
0x1800ab1ce  jb      short loc_1800AB1DE
0x1800ab1d0  mov     rcx, [rsp+288h+Block]; Block
0x1800ab1d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab1dd  nop
0x1800ab1de  xor     ecx, ecx
0x1800ab1e0  jmp     loc_1800AB160
0x1800ab1e5  mov     r14, rsi
0x1800ab1e8  mov     rsi, qword ptr [rsp+288h+var_220+8]
0x1800ab1ed  mov     rbx, qword ptr [rsp+288h+var_220]
0x1800ab1f2  mov     eax, edi
0x1800ab1f4  cmp     r14, rax
0x1800ab1f7  jnb     loc_1800AB2DC
0x1800ab1fd  imul    rax, r14, 208h
0x1800ab204  add     r15, rax
0x1800ab207  mov     rdi, rbx
0x1800ab20a  cmp     rdi, rsi
0x1800ab20d  jz      short loc_1800AB251
0x1800ab20f  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800ab213  xor     eax, eax
0x1800ab215  inc     r9; cchCount2
0x1800ab218  cmp     [r15+r9*2], ax
0x1800ab21d  jnz     short loc_1800AB215
0x1800ab21f  lea     rcx, [rdi+8]
0x1800ab223  cmp     qword ptr [rdi+20h], 8
0x1800ab228  jb      short loc_1800AB22D
0x1800ab22a  mov     rcx, [rcx]; lpString1
0x1800ab22d  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800ab235  mov     r8, r15; lpString2
0x1800ab238  mov     edx, [rdi+18h]; cchCount1
0x1800ab23b  call    cs:__imp_CompareStringOrdinal
0x1800ab241  cmp     eax, 2
0x1800ab244  jz      short loc_1800AB24C
0x1800ab246  add     rdi, 28h ; '('
0x1800ab24a  jmp     short loc_1800AB20A
0x1800ab24c  cmp     rdi, rsi
0x1800ab24f  jnz     short loc_1800AB2CB
0x1800ab251  mov     [rsp+288h+var_40], 7
0x1800ab25d  xor     ebx, ebx
0x1800ab25f  mov     [rsp+288h+var_48], rbx
0x1800ab267  mov     word ptr [rsp+288h+Block], bx
0x1800ab26f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ab273  inc     r8
0x1800ab276  cmp     [r15+r8*2], bx
0x1800ab27b  jnz     short loc_1800AB273
0x1800ab27d  mov     rdx, r15
0x1800ab280  lea     rcx, [rsp+288h+var_60]
0x1800ab288  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800ab28d  nop
0x1800ab28e  lea     rdx, [rsp+288h+var_60]
0x1800ab296  lea     rcx, [rsp+288h+var_228]
0x1800ab29b  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800ab2a0  nop
0x1800ab2a1  cmp     [rsp+288h+var_40], 8
0x1800ab2aa  jb      short loc_1800AB2B9
0x1800ab2ac  mov     rcx, [rsp+288h+Block]; Block
0x1800ab2b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab2b9  mov     word ptr [rsp+288h+Block], bx
0x1800ab2c1  mov     rsi, qword ptr [rsp+288h+var_220+8]
0x1800ab2c6  mov     rbx, qword ptr [rsp+288h+var_220]
0x1800ab2cb  inc     r14
0x1800ab2ce  mov     edi, [rsp+288h+var_258]
0x1800ab2d2  mov     r15, [rsp+288h+var_250]
0x1800ab2d7  jmp     loc_1800AB1F2
0x1800ab2dc  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x1800ab2e3  mov     [rsp+288h+var_208], rax
0x1800ab2eb  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x1800ab2f2  mov     [rsp+288h+var_1F8], rax
0x1800ab2fa  or      [rsp+288h+var_254], 1
0x1800ab2ff  xor     r15d, r15d
0x1800ab302  mov     [rsp+288h+var_200], r15
0x1800ab30a  lea     rax, ??_7?$basic_ostream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ostream<ushort>::`vftable'
0x1800ab311  mov     [rsp+288h+var_170], rax
0x1800ab319  lea     rdx, [rsp+288h+var_1F0]
0x1800ab321  lea     rcx, [rsp+288h+var_170]; this
0x1800ab329  call    ?init@?$basic_ios@GU?$char_traits@G@std@@@std@@IEAAXPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@_N@Z; std::basic_ios<ushort>::init(std::basic_streambuf<ushort> *,bool)
0x1800ab32e  mov     rax, [rsp+288h+var_208]
0x1800ab336  movsxd  rcx, dword ptr [rax+4]
0x1800ab33a  lea     rax, ??_7?$basic_iostream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_iostream<ushort>::`vftable'
0x1800ab341  mov     [rsp+rcx+288h+var_208], rax
0x1800ab349  mov     rax, [rsp+288h+var_208]
0x1800ab351  movsxd  rcx, dword ptr [rax+4]
0x1800ab355  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x1800ab35c  mov     [rsp+rcx+288h+var_208], rax
0x1800ab364  lea     rax, [rsp+288h+var_1F0]
0x1800ab36c  mov     [rsp+288h+var_250], rax
0x1800ab371  lea     rax, ??_7?$basic_streambuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_streambuf<ushort>::`vftable'
0x1800ab378  mov     [rsp+288h+var_1F0], rax
0x1800ab380  lea     rcx, [rsp+288h+var_1E8]; this
0x1800ab388  call    ??0_Mutex@std@@QEAA@XZ; std::_Mutex::_Mutex(void)
0x1800ab38d  nop
0x1800ab38e  lea     ecx, [r15+8]; Size
0x1800ab392  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ab397  mov     rdi, rax
0x1800ab39a  test    rax, rax
0x1800ab39d  jz      short loc_1800AB3D9
0x1800ab39f  call    ?_Init@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Init(void)
0x1800ab3a4  mov     [rdi], rax
0x1800ab3a7  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x1800ab3ac  mov     r14, rax
0x1800ab3af  xor     edx, edx; int
0x1800ab3b1  lea     rcx, [rsp+288h+var_258]; this
0x1800ab3b6  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x1800ab3bb  mov     rcx, [r14+8]
0x1800ab3bf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab3c3  jnb     short loc_1800AB3CC
0x1800ab3c5  inc     rcx
0x1800ab3c8  mov     [r14+8], rcx
0x1800ab3cc  lea     rcx, [rsp+288h+var_258]; this
0x1800ab3d1  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x1800ab3d6  nop
0x1800ab3d7  jmp     short loc_1800AB3DC
0x1800ab3d9  mov     rdi, r15
0x1800ab3dc  mov     [rsp+288h+var_188], rdi
0x1800ab3e4  lea     r11, [rsp+288h+var_1E0]
0x1800ab3ec  mov     [rsp+288h+var_1D0], r11
0x1800ab3f4  lea     r10, [rsp+288h+var_1D8]
0x1800ab3fc  mov     [rsp+288h+var_1C8], r10
0x1800ab404  lea     r9, [rsp+288h+var_1C0]
0x1800ab40c  mov     [rsp+288h+var_1B0], r9
0x1800ab414  lea     rdx, [rsp+288h+var_1B8]
0x1800ab41c  mov     [rsp+288h+var_1A8], rdx
0x1800ab424  lea     rdi, [rsp+288h+var_1A0]
0x1800ab42c  mov     [rsp+288h+var_198], rdi
0x1800ab434  lea     rax, [rsp+288h+var_1A0+4]
0x1800ab43c  mov     [rsp+288h+var_190], rax
0x1800ab444  mov     [rsp+288h+var_1D8], r15
0x1800ab44c  mov     [rsp+288h+var_1B8], r15
0x1800ab454  mov     [rsp+288h+var_1A0], r15
0x1800ab45c  mov     [rsp+288h+var_1E0], r15
0x1800ab464  mov     [rsp+288h+var_1C0], r15
0x1800ab46c  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x1800ab473  mov     [rsp+288h+var_1F0], rax
0x1800ab47b  mov     r8, r15
0x1800ab47e  mov     [rsp+288h+var_180], r15
0x1800ab486  mov     ecx, r15d
0x1800ab489  mov     [rsp+288h+var_178], ecx
0x1800ab490  test    rbx, rbx
0x1800ab493  jz      short loc_1800AB504
0x1800ab495  cmp     rsi, rbx
0x1800ab498  jz      short loc_1800AB504
0x1800ab49a  mov     rdx, rbx
0x1800ab49d  lea     rcx, [rsp+288h+var_1F8]
0x1800ab4a5  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800ab4aa  add     rbx, 28h ; '('
0x1800ab4ae  cmp     rbx, rsi
0x1800ab4b1  jz      short loc_1800AB4CD
0x1800ab4b3  lea     rcx, [rsp+288h+var_1F8]
0x1800ab4bb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800ab4c0  mov     rdx, rbx
0x1800ab4c3  mov     rcx, rax
0x1800ab4c6  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800ab4cb  jmp     short loc_1800AB4AA
0x1800ab4cd  mov     ecx, [rsp+288h+var_178]
0x1800ab4d4  mov     r8, [rsp+288h+var_180]
0x1800ab4dc  mov     rdi, [rsp+288h+var_198]
0x1800ab4e4  mov     rdx, [rsp+288h+var_1A8]
0x1800ab4ec  mov     r9, [rsp+288h+var_1B0]
0x1800ab4f4  mov     r10, [rsp+288h+var_1C8]
0x1800ab4fc  mov     r11, [rsp+288h+var_1D0]
0x1800ab504  test    cl, 2
0x1800ab507  jnz     short loc_1800AB54A
0x1800ab509  cmp     [rdx], r15
0x1800ab50c  jz      short loc_1800AB54A
0x1800ab50e  cmp     r8, [rdx]
0x1800ab511  cmovb   r8, [rdx]
0x1800ab515  mov     rdx, [r10]
0x1800ab518  sub     r8, rdx
0x1800ab51b  sar     r8, 1
0x1800ab51e  mov     [rsp+288h+var_68], 7
0x1800ab52a  mov     [rsp+288h+var_70], r15
0x1800ab532  mov     word ptr [rsp+288h+var_80], r15w
0x1800ab53b  lea     rcx, [rsp+288h+var_88]
0x1800ab543  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800ab548  jmp     short loc_1800AB582
0x1800ab54a  test    cl, 4
0x1800ab54d  jnz     short loc_1800AB565
0x1800ab54f  cmp     [r9], r15
0x1800ab552  jz      short loc_1800AB565
0x1800ab554  mov     rdx, [r11]
0x1800ab557  movsxd  r8, dword ptr [rdi]
0x1800ab55a  add     r8, r8
0x1800ab55d  sub     r8, rdx
0x1800ab560  add     r8, [r9]
0x1800ab563  jmp     short loc_1800AB51B
0x1800ab565  mov     [rsp+288h+var_68], 7
0x1800ab571  mov     [rsp+288h+var_70], r15
0x1800ab579  mov     word ptr [rsp+288h+var_80], r15w
0x1800ab582  xor     edx, edx; Val
0x1800ab584  lea     r8d, [rdx+40h]; Size
0x1800ab588  lea     rcx, [rsp+288h+var_108]; void *
0x1800ab590  call    memset_0
0x1800ab595  mov     [rsp+288h+var_108.Version], 1
0x1800ab5a0  mov     [rsp+288h+var_108.Flags], 4
0x1800ab5ac  lea     rax, [rsp+288h+var_80]
0x1800ab5b4  cmp     [rsp+288h+var_68], 8
0x1800ab5bd  cmovnb  rax, [rsp+288h+var_80]
0x1800ab5c6  mov     [rsp+288h+var_108.SearchList], rax
0x1800ab5ce  mov     rdi, qword ptr [rsp+288h+var_248.Data1]
0x1800ab5d3  movaps  xmm0, xmmword ptr [rdi]
0x1800ab5d6  movdqa  xmmword ptr [rsp+288h+var_248.Data1], xmm0
0x1800ab5dc  lea     rdx, [rsp+288h+var_108]; Settings
0x1800ab5e4  lea     rcx, [rsp+288h+var_248]; Interface
0x1800ab5e9  call    cs:__imp_SetInterfaceDnsSettings
0x1800ab5ef  mov     ebx, eax
0x1800ab5f1  test    eax, eax
0x1800ab5f3  jz      short loc_1800AB62B
0x1800ab5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab5fc  cmp     rcx, r13
0x1800ab5ff  jz      loc_1800AB687
0x1800ab605  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```

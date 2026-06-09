# SetInterfaceDnsSuffixSearchList

- ea: `0x1800b107c`
- end: `0x1800b17e0`
- name: `SetInterfaceDnsSuffixSearchList`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180052950`

## callees

- `0x1800039ac`
- `0x1800039fc`
- `0x180003bf8`
- `0x180003c70`
- `0x180003c90`
- `0x180003e04`
- `0x180003e14`
- `0x180004514`
- `0x180005bfc`
- `0x1800ad08c`
- `0x1800adadc`
- `0x1800adb64`
- `0x1800ade8c`
- `0x1800af408`
- `0x1800afb5c`
- `0x1800b00b4`
- `0x1800b107c`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800b11c2`
- `msvcrt!wcstok_s` at `0x1800b11c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b1297`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b1297`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800b164b`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800b16b6`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800b164b`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x1800b16b6`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800b113f`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800b113f`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800b1779`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800b1779`

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
0x1800b107c  mov     [rsp+arg_18], rbx
0x1800b1081  push    rsi
0x1800b1082  push    rdi
0x1800b1083  push    r13
0x1800b1085  push    r14
0x1800b1087  push    r15
0x1800b1089  sub     rsp, 260h
0x1800b1090  mov     rax, cs:__security_cookie
0x1800b1097  xor     rax, rsp
0x1800b109a  mov     [rsp+288h+var_38], rax
0x1800b10a2  mov     rbx, r8
0x1800b10a5  mov     qword ptr [rsp+288h+var_248.Data1], rbx
0x1800b10aa  mov     edi, edx
0x1800b10ac  mov     [rsp+288h+var_258], edx
0x1800b10b0  mov     r15, rcx
0x1800b10b3  mov     [rsp+288h+var_250], rcx
0x1800b10b8  xor     esi, esi
0x1800b10ba  mov     [rsp+288h+var_254], esi
0x1800b10be  lea     r13, WPP_GLOBAL_Control
0x1800b10c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b10cc  cmp     rcx, r13
0x1800b10cf  jz      short loc_1800B10F3
0x1800b10d1  test    byte ptr [rcx+1Ch], 1
0x1800b10d5  jz      short loc_1800B10F3
0x1800b10d7  cmp     byte ptr [rcx+19h], 6
0x1800b10db  jb      short loc_1800B10F3
0x1800b10dd  lea     edx, [rsi+14h]
0x1800b10e0  mov     r9d, edi
0x1800b10e3  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b10ea  mov     rcx, [rcx+10h]
0x1800b10ee  call    WPP_SF_d
0x1800b10f3  xor     edx, edx; Val
0x1800b10f5  lea     r8d, [rdx+40h]; Size
0x1800b10f9  lea     rcx, [rsp+288h+Settings]; void *
0x1800b1101  call    memset_0
0x1800b1106  test    edi, edi
0x1800b1108  jnz     short loc_1800B1112
0x1800b110a  lea     ebx, [rdi+57h]
0x1800b110d  jmp     loc_1800B1771
0x1800b1112  mov     [rsp+288h+Settings.Version], 1
0x1800b111d  mov     [rsp+288h+Settings.Flags], 4
0x1800b1129  movaps  xmm0, xmmword ptr [rbx]
0x1800b112c  movdqa  xmmword ptr [rsp+288h+Interface.Data1], xmm0
0x1800b1132  lea     rdx, [rsp+288h+Settings]; Settings
0x1800b113a  lea     rcx, [rsp+288h+Interface]; Interface
0x1800b113f  call    cs:__imp_GetInterfaceDnsSettings
0x1800b1146  nop     dword ptr [rax+rax+00h]
0x1800b114b  mov     ebx, eax
0x1800b114d  test    eax, eax
0x1800b114f  jz      short loc_1800B1192
0x1800b1151  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1158  cmp     rcx, r13
0x1800b115b  jz      loc_1800B1771
0x1800b1161  test    byte ptr [rcx+1Ch], 1
0x1800b1165  jz      loc_1800B1771
0x1800b116b  cmp     byte ptr [rcx+19h], 2
0x1800b116f  jb      loc_1800B1771
0x1800b1175  mov     edx, 15h
0x1800b117a  mov     r9d, eax
0x1800b117d  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b1184  mov     rcx, [rcx+10h]
0x1800b1188  call    WPP_SF_d
0x1800b118d  jmp     loc_1800B1771
0x1800b1192  xorps   xmm0, xmm0
0x1800b1195  movdqu  [rsp+288h+var_220], xmm0
0x1800b119b  mov     [rsp+288h+var_210], rsi
0x1800b11a0  mov     qword ptr [rsp+288h+Interface.Data1], rsi
0x1800b11a5  mov     rcx, [rsp+288h+Settings.SearchList]; String
0x1800b11ad  test    rcx, rcx
0x1800b11b0  jz      loc_1800B1241
0x1800b11b6  lea     r8, [rsp+288h+Interface]; Context
0x1800b11bb  lea     rdx, Delimiter; ","
0x1800b11c2  call    cs:__imp_wcstok_s
0x1800b11c9  nop     dword ptr [rax+rax+00h]
0x1800b11ce  test    rax, rax
0x1800b11d1  jz      short loc_1800B1241
0x1800b11d3  mov     [rsp+288h+var_40], 7
0x1800b11df  mov     [rsp+288h+var_48], rsi
0x1800b11e7  mov     word ptr [rsp+288h+Block], si
0x1800b11ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b11f3  inc     r8
0x1800b11f6  cmp     [rax+r8*2], si
0x1800b11fb  jnz     short loc_1800B11F3
0x1800b11fd  mov     rdx, rax
0x1800b1200  lea     rcx, [rsp+288h+var_60]
0x1800b1208  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800b120d  nop
0x1800b120e  lea     rdx, [rsp+288h+var_60]
0x1800b1216  lea     rcx, [rsp+288h+var_228]
0x1800b121b  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800b1220  nop
0x1800b1221  cmp     [rsp+288h+var_40], 8
0x1800b122a  jb      short loc_1800B123A
0x1800b122c  mov     rcx, [rsp+288h+Block]; Block
0x1800b1234  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b1239  nop
0x1800b123a  xor     ecx, ecx
0x1800b123c  jmp     loc_1800B11B6
0x1800b1241  mov     r14, rsi
0x1800b1244  mov     rsi, qword ptr [rsp+288h+var_220+8]
0x1800b1249  mov     rbx, qword ptr [rsp+288h+var_220]
0x1800b124e  mov     eax, edi
0x1800b1250  cmp     r14, rax
0x1800b1253  jnb     loc_1800B133E
0x1800b1259  imul    rax, r14, 208h
0x1800b1260  add     r15, rax
0x1800b1263  mov     rdi, rbx
0x1800b1266  cmp     rdi, rsi
0x1800b1269  jz      short loc_1800B12B3
0x1800b126b  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b126f  xor     eax, eax
0x1800b1271  inc     r9; cchCount2
0x1800b1274  cmp     [r15+r9*2], ax
0x1800b1279  jnz     short loc_1800B1271
0x1800b127b  lea     rcx, [rdi+8]
0x1800b127f  cmp     qword ptr [rdi+20h], 8
0x1800b1284  jb      short loc_1800B1289
0x1800b1286  mov     rcx, [rcx]; lpString1
0x1800b1289  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800b1291  mov     r8, r15; lpString2
0x1800b1294  mov     edx, [rdi+18h]; cchCount1
0x1800b1297  call    cs:__imp_CompareStringOrdinal
0x1800b129e  nop     dword ptr [rax+rax+00h]
0x1800b12a3  cmp     eax, 2
0x1800b12a6  jz      short loc_1800B12AE
0x1800b12a8  add     rdi, 28h ; '('
0x1800b12ac  jmp     short loc_1800B1266
0x1800b12ae  cmp     rdi, rsi
0x1800b12b1  jnz     short loc_1800B132D
0x1800b12b3  mov     [rsp+288h+var_40], 7
0x1800b12bf  xor     ebx, ebx
0x1800b12c1  mov     [rsp+288h+var_48], rbx
0x1800b12c9  mov     word ptr [rsp+288h+Block], bx
0x1800b12d1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b12d5  inc     r8
0x1800b12d8  cmp     [r15+r8*2], bx
0x1800b12dd  jnz     short loc_1800B12D5
0x1800b12df  mov     rdx, r15
0x1800b12e2  lea     rcx, [rsp+288h+var_60]
0x1800b12ea  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800b12ef  nop
0x1800b12f0  lea     rdx, [rsp+288h+var_60]
0x1800b12f8  lea     rcx, [rsp+288h+var_228]
0x1800b12fd  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800b1302  nop
0x1800b1303  cmp     [rsp+288h+var_40], 8
0x1800b130c  jb      short loc_1800B131B
0x1800b130e  mov     rcx, [rsp+288h+Block]; Block
0x1800b1316  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b131b  mov     word ptr [rsp+288h+Block], bx
0x1800b1323  mov     rsi, qword ptr [rsp+288h+var_220+8]
0x1800b1328  mov     rbx, qword ptr [rsp+288h+var_220]
0x1800b132d  inc     r14
0x1800b1330  mov     edi, [rsp+288h+var_258]
0x1800b1334  mov     r15, [rsp+288h+var_250]
0x1800b1339  jmp     loc_1800B124E
0x1800b133e  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x1800b1345  mov     [rsp+288h+var_208], rax
0x1800b134d  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x1800b1354  mov     [rsp+288h+var_1F8], rax
0x1800b135c  or      [rsp+288h+var_254], 1
0x1800b1361  xor     r15d, r15d
0x1800b1364  mov     [rsp+288h+var_200], r15
0x1800b136c  lea     rax, ??_7?$basic_ostream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ostream<ushort>::`vftable'
0x1800b1373  mov     [rsp+288h+var_170], rax
0x1800b137b  lea     rdx, [rsp+288h+var_1F0]
0x1800b1383  lea     rcx, [rsp+288h+var_170]; this
0x1800b138b  call    ?init@?$basic_ios@GU?$char_traits@G@std@@@std@@IEAAXPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@_N@Z; std::basic_ios<ushort>::init(std::basic_streambuf<ushort> *,bool)
0x1800b1390  mov     rax, [rsp+288h+var_208]
0x1800b1398  movsxd  rcx, dword ptr [rax+4]
0x1800b139c  lea     rax, ??_7?$basic_iostream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_iostream<ushort>::`vftable'
0x1800b13a3  mov     [rsp+rcx+288h+var_208], rax
0x1800b13ab  mov     rax, [rsp+288h+var_208]
0x1800b13b3  movsxd  rcx, dword ptr [rax+4]
0x1800b13b7  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x1800b13be  mov     [rsp+rcx+288h+var_208], rax
0x1800b13c6  lea     rax, [rsp+288h+var_1F0]
0x1800b13ce  mov     [rsp+288h+var_250], rax
0x1800b13d3  lea     rax, ??_7?$basic_streambuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_streambuf<ushort>::`vftable'
0x1800b13da  mov     [rsp+288h+var_1F0], rax
0x1800b13e2  lea     rcx, [rsp+288h+var_1E8]; this
0x1800b13ea  call    ??0_Mutex@std@@QEAA@XZ; std::_Mutex::_Mutex(void)
0x1800b13ef  nop
0x1800b13f0  lea     ecx, [r15+8]; Size
0x1800b13f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b13f9  mov     rdi, rax
0x1800b13fc  test    rax, rax
0x1800b13ff  jz      short loc_1800B143B
0x1800b1401  call    ?_Init@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Init(void)
0x1800b1406  mov     [rdi], rax
0x1800b1409  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x1800b140e  mov     r14, rax
0x1800b1411  xor     edx, edx; int
0x1800b1413  lea     rcx, [rsp+288h+var_258]; this
0x1800b1418  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x1800b141d  mov     rcx, [r14+8]
0x1800b1421  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b1425  jnb     short loc_1800B142E
0x1800b1427  inc     rcx
0x1800b142a  mov     [r14+8], rcx
0x1800b142e  lea     rcx, [rsp+288h+var_258]; this
0x1800b1433  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x1800b1438  nop
0x1800b1439  jmp     short loc_1800B143E
0x1800b143b  mov     rdi, r15
0x1800b143e  mov     [rsp+288h+var_188], rdi
0x1800b1446  lea     r11, [rsp+288h+var_1E0]
0x1800b144e  mov     [rsp+288h+var_1D0], r11
0x1800b1456  lea     r10, [rsp+288h+var_1D8]
0x1800b145e  mov     [rsp+288h+var_1C8], r10
0x1800b1466  lea     r9, [rsp+288h+var_1C0]
0x1800b146e  mov     [rsp+288h+var_1B0], r9
0x1800b1476  lea     rdx, [rsp+288h+var_1B8]
0x1800b147e  mov     [rsp+288h+var_1A8], rdx
0x1800b1486  lea     rdi, [rsp+288h+var_1A0]
0x1800b148e  mov     [rsp+288h+var_198], rdi
0x1800b1496  lea     rax, [rsp+288h+var_1A0+4]
0x1800b149e  mov     [rsp+288h+var_190], rax
0x1800b14a6  mov     [rsp+288h+var_1D8], r15
0x1800b14ae  mov     [rsp+288h+var_1B8], r15
0x1800b14b6  mov     [rsp+288h+var_1A0], r15
0x1800b14be  mov     [rsp+288h+var_1E0], r15
0x1800b14c6  mov     [rsp+288h+var_1C0], r15
0x1800b14ce  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x1800b14d5  mov     [rsp+288h+var_1F0], rax
0x1800b14dd  mov     r8, r15
0x1800b14e0  mov     [rsp+288h+var_180], r15
0x1800b14e8  mov     ecx, r15d
0x1800b14eb  mov     [rsp+288h+var_178], ecx
0x1800b14f2  test    rbx, rbx
0x1800b14f5  jz      short loc_1800B1566
0x1800b14f7  cmp     rsi, rbx
0x1800b14fa  jz      short loc_1800B1566
0x1800b14fc  mov     rdx, rbx
0x1800b14ff  lea     rcx, [rsp+288h+var_1F8]
0x1800b1507  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800b150c  add     rbx, 28h ; '('
0x1800b1510  cmp     rbx, rsi
0x1800b1513  jz      short loc_1800B152F
0x1800b1515  lea     rcx, [rsp+288h+var_1F8]
0x1800b151d  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800b1522  mov     rdx, rbx
0x1800b1525  mov     rcx, rax
0x1800b1528  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800b152d  jmp     short loc_1800B150C
0x1800b152f  mov     ecx, [rsp+288h+var_178]
0x1800b1536  mov     r8, [rsp+288h+var_180]
0x1800b153e  mov     rdi, [rsp+288h+var_198]
0x1800b1546  mov     rdx, [rsp+288h+var_1A8]
0x1800b154e  mov     r9, [rsp+288h+var_1B0]
0x1800b1556  mov     r10, [rsp+288h+var_1C8]
0x1800b155e  mov     r11, [rsp+288h+var_1D0]
0x1800b1566  test    cl, 2
0x1800b1569  jnz     short loc_1800B15AC
0x1800b156b  cmp     [rdx], r15
0x1800b156e  jz      short loc_1800B15AC
0x1800b1570  cmp     r8, [rdx]
0x1800b1573  cmovb   r8, [rdx]
0x1800b1577  mov     rdx, [r10]
0x1800b157a  sub     r8, rdx
0x1800b157d  sar     r8, 1
0x1800b1580  mov     [rsp+288h+var_68], 7
0x1800b158c  mov     [rsp+288h+var_70], r15
0x1800b1594  mov     word ptr [rsp+288h+var_80], r15w
0x1800b159d  lea     rcx, [rsp+288h+var_88]
0x1800b15a5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800b15aa  jmp     short loc_1800B15E4
0x1800b15ac  test    cl, 4
0x1800b15af  jnz     short loc_1800B15C7
0x1800b15b1  cmp     [r9], r15
0x1800b15b4  jz      short loc_1800B15C7
0x1800b15b6  mov     rdx, [r11]
0x1800b15b9  movsxd  r8, dword ptr [rdi]
0x1800b15bc  add     r8, r8
0x1800b15bf  sub     r8, rdx
0x1800b15c2  add     r8, [r9]
0x1800b15c5  jmp     short loc_1800B157D
0x1800b15c7  mov     [rsp+288h+var_68], 7
0x1800b15d3  mov     [rsp+288h+var_70], r15
0x1800b15db  mov     word ptr [rsp+288h+var_80], r15w
0x1800b15e4  xor     edx, edx; Val
0x1800b15e6  lea     r8d, [rdx+40h]; Size
0x1800b15ea  lea     rcx, [rsp+288h+var_108]; void *
0x1800b15f2  call    memset_0
0x1800b15f7  mov     [rsp+288h+var_108.Version], 1
0x1800b1602  mov     [rsp+288h+var_108.Flags], 4
0x1800b160e  lea     rax, [rsp+288h+var_80]
0x1800b1616  cmp     [rsp+288h+var_68], 8
0x1800b161f  cmovnb  rax, [rsp+288h+var_80]
0x1800b1628  mov     [rsp+288h+var_108.SearchList], rax
0x1800b1630  mov     rdi, qword ptr [rsp+288h+var_248.Data1]
0x1800b1635  movaps  xmm0, xmmword ptr [rdi]
0x1800b1638  movdqa  xmmword ptr [rsp+288h+var_248.Data1], xmm0
0x1800b163e  lea     rdx, [rsp+288h+var_108]; Settings
0x1800b1646  lea     rcx, [rsp+288h+var_248]; Interface
0x1800b164b  call    cs:__imp_SetInterfaceDnsSettings
0x1800b1652  nop     dword ptr [rax+rax+00h]
0x1800b1657  mov     ebx, eax
0x1800b1659  test    eax, eax
0x1800b165b  jz      short loc_1800B1697
  ... truncated ...
```

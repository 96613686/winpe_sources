# ProcessorInfo::GetProcessorRegistry(void)

- ea: `0x18006fef0`
- end: `0x180070364`
- name: `?GetProcessorRegistry@ProcessorInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1140`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008dc0`
- `0x18000929c`
- `0x180009f14`
- `0x180014f2c`
- `0x180016748`
- `0x1800167b4`
- `0x180019970`
- `0x180034188`
- `0x180067fec`
- `0x180068d9c`
- `0x180068f88`
- `0x180069658`
- `0x180069b90`
- `0x180069d94`
- `0x180069e28`
- `0x180069ea0`
- `0x18006a118`
- `0x18006fef0`
- `0x18007036c`
- `0x1800704a4`
- `0x180071a34`
- `0x180071c34`
- `0x180071cd8`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180070334`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180070334`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180070327`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180070327`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800700c1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800700c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ffaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800702ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ffaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800702ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180070018`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180070018`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18006ff79`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18006ff79`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
unsigned __int64 *__fastcall ProcessorInfo::GetProcessorRegistry(__int64 a1, unsigned __int64 *a2)
{
  __int64 **v3; // rax
  DWORD i; // ebx
  unsigned __int64 v5; // r8
  _QWORD *v6; // rax
  int v7; // eax
  __int64 *v8; // rbx
  __int64 *v9; // rdi
  __int64 ProcessorRegistryTruncated; // rax
  __int64 v11; // rax
  _QWORD *v12; // rbx
  _QWORD *v13; // rdi
  __int64 v14; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v19[2]; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+80h] [rbp-80h] BYREF
  void *v21[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h] BYREF
  __int64 **v27; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v28; // [rsp+D0h] [rbp-30h]
  char *v29; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+10Ch] [rbp+Ch]
  __int64 v34; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v35[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v36[120]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v37[104]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v38[256]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v39[2]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR Name[256]; // [rsp+320h] [rbp+220h] BYREF

  v19[0] = a2;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v34);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v34, "{\"processors\":[");
  memset_0(Name, 0, 0x1FEu);
  cchName = 0;
  cSubKeys = 0;
  phkResult = 0;
  if ( RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Hardware\\Description\\System\\CentralProcessor\\", &phkResult) )
  {
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v34, "]}");
    std::basic_stringbuf<unsigned short>::str(v35, a2);
    if ( phkResult )
      RegCloseKey(phkResult);
    *(_QWORD *)&v35[*(int *)(v34 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
    *(int *)((char *)&v33 + *(int *)(v34 + 4)) = *(_DWORD *)(v34 + 4) - 136;
  }
  else
  {
    RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( cSubKeys )
    {
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v3 = (__int64 **)operator new(0x108u);
      *v3 = (__int64 *)v3;
      v3[1] = (__int64 *)v3;
      v27 = v3;
      v29 = 0;
      v30 = 0;
      v31 = 7;
      v32 = 8;
      v26 = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(
        &v29,
        16,
        v3);
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 255;
        if ( !RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0) )
        {
          memset(v39, 0, sizeof(v39));
          v5 = -1;
          do
            ++v5;
          while ( Name[v5] );
          std::wstring::_Construct<1,unsigned short const *>((char **)v39, Name, v5);
          ProcessorInfo::GetProcessorRegistryTuple_N(v38, v39);
          std::wstring::~wstring((char **)v39);
          std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(
            (__int64)&v26,
            (__int64)v19,
            (__int64)v38);
          ProcessorRegistryTuple::~ProcessorRegistryTuple((ProcessorRegistryTuple *)v38);
        }
      }
      v20 = 0;
      v21[0] = 0;
      v21[1] = 0;
      v6 = operator new(0x108u);
      *v6 = v6;
      v6[1] = v6;
      v21[0] = v6;
      v22 = 0;
      v23 = 0;
      v24 = 7;
      v25 = 8;
      v20 = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(
        &v22,
        16,
        v6);
      v7 = 4;
      if ( v28 <= 4 )
      {
        v19[0] = (unsigned __int64 *)&v20;
        v20 = v26;
        std::list<ProcessorRegistryTuple_2>::_Assign_cast<ProcessorRegistryTuple_2 &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>(
          (void ****)v21,
          *v27,
          (__int64 *)v27);
        v11 = std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Desired_grow_bucket_count(&v20);
        std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::_Forced_rehash(
          &v20,
          v11);
        v19[0] = 0;
        std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Clear_guard::~_Clear_guard(v19);
      }
      else
      {
        v8 = *v27;
        v9 = *v27;
        do
        {
          v9 = (__int64 *)*v9;
          --v7;
        }
        while ( v7 > 0 );
        while ( v8 != v9 )
        {
          std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(
            (__int64)&v20,
            (__int64)v19,
            (__int64)(v8 + 2));
          v8 = (__int64 *)*v8;
        }
        ProcessorRegistryTruncated = CProcessorInfo::GetProcessorRegistryTruncated(v38);
        std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::emplace<ProcessorRegistryTuple>(
          (__int64)&v20,
          (__int64)v19,
          ProcessorRegistryTruncated);
        ProcessorRegistryTuple::~ProcessorRegistryTuple((ProcessorRegistryTuple *)v38);
      }
      v12 = *(_QWORD **)v21[0];
      operator<<(&v34, *(_QWORD *)v21[0] + 16LL);
      v13 = v21[0];
      while ( 1 )
      {
        v12 = (_QWORD *)*v12;
        if ( v12 == v13 )
          break;
        v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v34, ",");
        operator<<(v14, v12 + 2);
      }
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(&v22);
      std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>(v21);
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(&v29);
      std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>((void **)&v27);
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v34, "]}");
    std::basic_stringbuf<unsigned short>::str(v35, a2);
    if ( phkResult )
      RegCloseKey(phkResult);
    *(_QWORD *)&v35[*(int *)(v34 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
    *(int *)((char *)&v33 + *(int *)(v34 + 4)) = *(_DWORD *)(v34 + 4) - 136;
  }
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v35);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v36);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v37);
  return a2;
}

```

## disassembly

```asm
0x18006fef0  mov     [rsp-8+arg_0], rbx
0x18006fef5  mov     [rsp-8+arg_10], rsi
0x18006fefa  push    rbp
0x18006fefb  push    rdi
0x18006fefc  push    r14
0x18006fefe  lea     rbp, [rsp-430h]
0x18006ff06  sub     rsp, 530h
0x18006ff0d  mov     rax, cs:__security_cookie
0x18006ff14  xor     rax, rsp
0x18006ff17  mov     [rbp+440h+var_20], rax
0x18006ff1e  mov     rsi, rdx
0x18006ff21  mov     [rsp+540h+var_4D0], rdx
0x18006ff26  xor     r14d, r14d
0x18006ff29  lea     rcx, [rbp+440h+var_430]
0x18006ff2d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18006ff32  nop
0x18006ff33  lea     rdx, aProcessors; "{\"processors\":["
0x18006ff3a  lea     rcx, [rbp+440h+var_430]
0x18006ff3e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18006ff43  xor     edx, edx; Val
0x18006ff45  mov     r8d, 1FEh; Size
0x18006ff4b  lea     rcx, [rbp+440h+Name]; void *
0x18006ff52  call    memset_0
0x18006ff57  mov     [rsp+540h+cchName], r14d
0x18006ff5c  mov     [rsp+540h+cSubKeys], r14d
0x18006ff61  mov     [rsp+540h+phkResult], r14
0x18006ff66  lea     r8, [rsp+540h+phkResult]; phkResult
0x18006ff6b  lea     rdx, aHardwareDescri_0; "Hardware\\Description\\System\\CentralP"...
0x18006ff72  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006ff79  call    cs:__imp_RegOpenKeyW
0x18006ff7f  test    eax, eax
0x18006ff81  jz      short loc_18006FFDE
0x18006ff83  lea     rdx, asc_1801BD500; "]}"
0x18006ff8a  lea     rcx, [rbp+440h+var_430]
0x18006ff8e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18006ff93  mov     rdx, rsi
0x18006ff96  lea     rcx, [rbp+440h+var_428]
0x18006ff9a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18006ff9f  nop
0x18006ffa0  mov     rcx, [rsp+540h+phkResult]; hKey
0x18006ffa5  test    rcx, rcx
0x18006ffa8  jz      short loc_18006FFB1
0x18006ffaa  call    cs:__imp_RegCloseKey
0x18006ffb0  nop
0x18006ffb1  mov     rax, [rbp+440h+var_430]
0x18006ffb5  movsxd  rcx, dword ptr [rax+4]
0x18006ffb9  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x18006ffc0  mov     [rbp+rcx+440h+var_430], rax
0x18006ffc5  mov     rcx, [rbp+440h+var_430]
0x18006ffc9  movsxd  rdx, dword ptr [rcx+4]
0x18006ffcd  lea     r8d, [rdx-88h]
0x18006ffd4  mov     [rbp+rdx+440h+var_434], r8d
0x18006ffd9  jmp     loc_18007031A
0x18006ffde  mov     [rsp+540h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18006ffe3  mov     [rsp+540h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18006ffe8  mov     [rsp+540h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18006ffed  mov     [rsp+540h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18006fff2  mov     [rsp+540h+lpcValues], r14; lpcValues
0x18006fff7  mov     [rsp+540h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18006fffc  mov     [rsp+540h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180070001  lea     rax, [rsp+540h+cSubKeys]
0x180070006  mov     [rsp+540h+lpcSubKeys], rax; lpcSubKeys
0x18007000b  xor     r9d, r9d; lpReserved
0x18007000e  xor     r8d, r8d; lpcchClass
0x180070011  xor     edx, edx; lpClass
0x180070013  mov     rcx, [rsp+540h+phkResult]; hKey
0x180070018  call    cs:__imp_RegQueryInfoKeyW
0x18007001e  cmp     [rsp+540h+cSubKeys], r14d
0x180070023  jz      loc_1800702C6
0x180070029  mov     [rbp+440h+var_480], 0
0x180070030  mov     [rbp+440h+var_478], r14
0x180070034  mov     [rbp+440h+var_470], r14
0x180070038  mov     edi, 108h
0x18007003d  mov     ecx, edi; Size
0x18007003f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070044  mov     [rax], rax
0x180070047  mov     [rax+8], rax
0x18007004b  mov     [rbp+440h+var_478], rax
0x18007004f  mov     [rbp+440h+var_468], r14
0x180070053  xorps   xmm0, xmm0
0x180070056  movdqa  [rbp+440h+var_460], xmm0
0x18007005b  mov     [rbp+440h+var_450], 7
0x180070063  mov     [rbp+440h+var_448], 8
0x18007006b  mov     [rbp+440h+var_480], 3F800000h
0x180070072  mov     r8, rax
0x180070075  mov     edx, 10h
0x18007007a  lea     rcx, [rbp+440h+var_468]
0x18007007e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>)
0x180070083  nop
0x180070084  mov     ebx, r14d
0x180070087  cmp     [rsp+540h+cSubKeys], r14d
0x18007008c  jbe     loc_18007015B
0x180070092  mov     [rsp+540h+cchName], 0FFh
0x18007009a  mov     [rsp+540h+lpcValues], r14; lpftLastWriteTime
0x18007009f  mov     [rsp+540h+lpcbMaxClassLen], r14; lpcchClass
0x1800700a4  mov     [rsp+540h+lpcbMaxSubKeyLen], r14; lpClass
0x1800700a9  mov     [rsp+540h+lpcSubKeys], r14; lpReserved
0x1800700ae  lea     r9, [rsp+540h+cchName]; lpcchName
0x1800700b3  lea     r8, [rbp+440h+Name]; lpName
0x1800700ba  mov     edx, ebx; dwIndex
0x1800700bc  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800700c1  call    cs:__imp_RegEnumKeyExW
0x1800700c7  test    eax, eax
0x1800700c9  jnz     loc_18007014F
0x1800700cf  xorps   xmm0, xmm0
0x1800700d2  movups  [rbp+440h+var_240], xmm0
0x1800700d9  xorps   xmm1, xmm1
0x1800700dc  movdqu  [rbp+440h+var_230], xmm1
0x1800700e4  lea     rax, [rbp+440h+Name]
0x1800700eb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800700ef  inc     r8
0x1800700f2  cmp     [rax+r8*2], r14w
0x1800700f7  jnz     short loc_1800700EF
0x1800700f9  lea     rdx, [rbp+440h+Name]
0x180070100  lea     rcx, [rbp+440h+var_240]
0x180070107  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007010c  nop
0x18007010d  lea     rdx, [rbp+440h+var_240]
0x180070114  lea     rcx, [rbp+440h+var_340]
0x18007011b  call    ?GetProcessorRegistryTuple_N@ProcessorInfo@@CA?AUProcessorRegistryTuple_2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProcessorInfo::GetProcessorRegistryTuple_N(std::wstring const &)
0x180070120  nop
0x180070121  lea     rcx, [rbp+440h+var_240]
0x180070128  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007012d  lea     r8, [rbp+440h+var_340]
0x180070134  lea     rdx, [rsp+540h+var_4D0]
0x180070139  lea     rcx, [rbp+440h+var_480]
0x18007013d  call    ??$emplace@AEBUProcessorRegistryTuple_2@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@@std@@_N@1@AEBUProcessorRegistryTuple_2@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(ProcessorRegistryTuple_2 const &)
0x180070142  nop
0x180070143  lea     rcx, [rbp+440h+var_340]; this
0x18007014a  call    ??1ProcessorRegistryTuple@@QEAA@XZ; ProcessorRegistryTuple::~ProcessorRegistryTuple(void)
0x18007014f  inc     ebx
0x180070151  cmp     ebx, [rsp+540h+cSubKeys]
0x180070155  jb      loc_180070092
0x18007015b  mov     [rbp+440h+var_4C0], 0
0x180070162  mov     [rbp+440h+var_4B8], r14
0x180070166  mov     [rbp+440h+var_4B0], r14
0x18007016a  mov     rcx, rdi; Size
0x18007016d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070172  mov     [rax], rax
0x180070175  mov     [rax+8], rax
0x180070179  mov     [rbp+440h+var_4B8], rax
0x18007017d  mov     [rbp+440h+var_4A8], r14
0x180070181  xorps   xmm0, xmm0
0x180070184  movdqa  [rbp+440h+var_4A0], xmm0
0x180070189  mov     [rbp+440h+var_490], 7
0x180070191  mov     [rbp+440h+var_488], 8
0x180070199  mov     [rbp+440h+var_4C0], 3F800000h
0x1800701a0  mov     r8, rax
0x1800701a3  mov     edx, 10h
0x1800701a8  lea     rcx, [rbp+440h+var_4A8]
0x1800701ac  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>)
0x1800701b1  nop
0x1800701b2  mov     eax, 4
0x1800701b7  cmp     [rbp+440h+var_470], rax
0x1800701bb  jbe     short loc_180070219
0x1800701bd  mov     rbx, [rbp+440h+var_478]
0x1800701c1  mov     rbx, [rbx]
0x1800701c4  mov     rdi, rbx
0x1800701c7  mov     rdi, [rdi]
0x1800701ca  dec     eax
0x1800701cc  test    eax, eax
0x1800701ce  jg      short loc_1800701C7
0x1800701d0  cmp     rbx, rdi
0x1800701d3  jz      short loc_1800701EC
0x1800701d5  lea     r8, [rbx+10h]
0x1800701d9  lea     rdx, [rsp+540h+var_4D0]
0x1800701de  lea     rcx, [rbp+440h+var_4C0]
0x1800701e2  call    ??$emplace@AEBUProcessorRegistryTuple_2@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@@std@@_N@1@AEBUProcessorRegistryTuple_2@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(ProcessorRegistryTuple_2 const &)
0x1800701e7  mov     rbx, [rbx]
0x1800701ea  jmp     short loc_1800701D0
0x1800701ec  lea     rcx, [rbp+440h+var_340]
0x1800701f3  call    ?GetProcessorRegistryTruncated@CProcessorInfo@@CA?AUProcessorRegistryTuple@@XZ; CProcessorInfo::GetProcessorRegistryTruncated(void)
0x1800701f8  nop
0x1800701f9  mov     r8, rax
0x1800701fc  lea     rdx, [rsp+540h+var_4D0]
0x180070201  lea     rcx, [rbp+440h+var_4C0]
0x180070205  call    ??$emplace@UProcessorRegistryTuple@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple@@V?$_Uhash_compare@UProcessorRegistryTuple@@U?$hash@UProcessorRegistryTuple@@@std@@U?$equal_to@UProcessorRegistryTuple@@@3@@std@@V?$allocator@UProcessorRegistryTuple@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@@std@@_N@1@$$QEAUProcessorRegistryTuple@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::emplace<ProcessorRegistryTuple>(ProcessorRegistryTuple &&)
0x18007020a  nop
0x18007020b  lea     rcx, [rbp+440h+var_340]; this
0x180070212  call    ??1ProcessorRegistryTuple@@QEAA@XZ; ProcessorRegistryTuple::~ProcessorRegistryTuple(void)
0x180070217  jmp     short loc_180070263
0x180070219  lea     rax, [rbp+440h+var_4C0]
0x18007021d  mov     [rsp+540h+var_4D0], rax
0x180070222  mov     eax, [rbp+440h+var_480]
0x180070225  mov     [rbp+440h+var_4C0], eax
0x180070228  mov     rdx, [rbp+440h+var_478]
0x18007022c  mov     r8, rdx
0x18007022f  mov     rdx, [rdx]
0x180070232  lea     rcx, [rbp+440h+var_4B8]
0x180070236  call    ??$_Assign_cast@AEAUProcessorRegistryTuple_2@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@?$list@UProcessorRegistryTuple_2@@V?$allocator@UProcessorRegistryTuple_2@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<ProcessorRegistryTuple_2>::_Assign_cast<ProcessorRegistryTuple_2 &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>)
0x18007023b  mov     rdx, [rbp+440h+var_4B0]
0x18007023f  lea     rcx, [rbp+440h+var_4C0]
0x180070243  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180070248  mov     rdx, rax
0x18007024b  lea     rcx, [rbp+440h+var_4C0]
0x18007024f  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple@@V?$_Uhash_compare@UProcessorRegistryTuple@@U?$hash@UProcessorRegistryTuple@@@std@@U?$equal_to@UProcessorRegistryTuple@@@3@@std@@V?$allocator@UProcessorRegistryTuple@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::_Forced_rehash(unsigned __int64)
0x180070254  mov     [rsp+540h+var_4D0], r14
0x180070259  lea     rcx, [rsp+540h+var_4D0]
0x18007025e  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Clear_guard::~_Clear_guard(void)
0x180070263  mov     rax, [rbp+440h+var_4B8]
0x180070267  mov     rbx, [rax]
0x18007026a  lea     rdx, [rbx+10h]
0x18007026e  lea     rcx, [rbp+440h+var_430]
0x180070272  call    ??6@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV01@AEBUProcessorRegistryTuple_2@@@Z; operator<<(std::basic_ostream<ushort> &,ProcessorRegistryTuple_2 const &)
0x180070277  mov     rdi, [rbp+440h+var_4B8]
0x18007027b  mov     rbx, [rbx]
0x18007027e  cmp     rbx, rdi
0x180070281  jz      short loc_1800702A1
0x180070283  lea     rdx, asc_1801BCDD4; ","
0x18007028a  lea     rcx, [rbp+440h+var_430]
0x18007028e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180070293  lea     rdx, [rbx+10h]
0x180070297  mov     rcx, rax
0x18007029a  call    ??6@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV01@AEBUProcessorRegistryTuple_2@@@Z; operator<<(std::basic_ostream<ushort> &,ProcessorRegistryTuple_2 const &)
0x18007029f  jmp     short loc_18007027B
0x1800702a1  lea     rcx, [rbp+440h+var_4A8]
0x1800702a5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(void)
0x1800702aa  lea     rcx, [rbp+440h+var_4B8]
0x1800702ae  call    ??1?$list@UProcessorRegistryTuple@@V?$allocator@UProcessorRegistryTuple@@@std@@@std@@QEAA@XZ; std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>(void)
0x1800702b3  nop
0x1800702b4  lea     rcx, [rbp+440h+var_468]
0x1800702b8  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(void)
0x1800702bd  lea     rcx, [rbp+440h+var_478]
0x1800702c1  call    ??1?$list@UProcessorRegistryTuple@@V?$allocator@UProcessorRegistryTuple@@@std@@@std@@QEAA@XZ; std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>(void)
0x1800702c6  lea     rdx, asc_1801BD500; "]}"
0x1800702cd  lea     rcx, [rbp+440h+var_430]
0x1800702d1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800702d6  mov     rdx, rsi
0x1800702d9  lea     rcx, [rbp+440h+var_428]
0x1800702dd  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800702e2  nop
0x1800702e3  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800702e8  test    rcx, rcx
0x1800702eb  jz      short loc_1800702F4
0x1800702ed  call    cs:__imp_RegCloseKey
0x1800702f3  nop
0x1800702f4  mov     rax, [rbp+440h+var_430]
0x1800702f8  movsxd  rcx, dword ptr [rax+4]
0x1800702fc  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x180070303  mov     [rbp+rcx+440h+var_430], rax
0x180070308  mov     rax, [rbp+440h+var_430]
0x18007030c  movsxd  rcx, dword ptr [rax+4]
0x180070310  lea     edx, [rcx-88h]
0x180070316  mov     [rbp+rcx+440h+var_434], edx
0x18007031a  lea     rcx, [rbp+440h+var_428]
0x18007031e  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180070323  lea     rcx, [rbp+440h+var_420]
0x180070327  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x18007032d  lea     rcx, [rbp+440h+var_3A8]
0x180070334  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18007033a  mov     rax, rsi
0x18007033d  mov     rcx, [rbp+440h+var_20]
0x180070344  xor     rcx, rsp; StackCookie
0x180070347  call    __security_check_cookie
0x18007034c  lea     r11, [rsp+540h+var_10]
0x180070354  mov     rbx, [r11+20h]
0x180070358  mov     rsi, [r11+30h]
0x18007035c  mov     rsp, r11
0x18007035f  pop     r14
0x180070361  pop     rdi
0x180070362  pop     rbp
0x180070363  retn
```

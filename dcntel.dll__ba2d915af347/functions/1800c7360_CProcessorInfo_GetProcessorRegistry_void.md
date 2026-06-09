# CProcessorInfo::GetProcessorRegistry(void)

- ea: `0x1800c7360`
- end: `0x1800c77d4`
- name: `?GetProcessorRegistry@CProcessorInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
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
- `0x18007036c`
- `0x180071a34`
- `0x180071c34`
- `0x180071cd8`
- `0x1800c7360`
- `0x1800c77dc`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800c77a4`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800c77a4`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800c7797`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800c7797`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c7531`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c7531`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c741a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c775d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c741a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c775d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c7488`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c7488`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800c73e9`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800c73e9`

## pseudocode

```c
unsigned __int64 *__fastcall CProcessorInfo::GetProcessorRegistry(__int64 a1, unsigned __int64 *a2)
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
          CProcessorInfo::GetProcessorRegistryTuple_N(v38, v39);
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
0x1800c7360  mov     [rsp-8+arg_0], rbx
0x1800c7365  mov     [rsp-8+arg_10], rsi
0x1800c736a  push    rbp
0x1800c736b  push    rdi
0x1800c736c  push    r14
0x1800c736e  lea     rbp, [rsp-430h]
0x1800c7376  sub     rsp, 530h
0x1800c737d  mov     rax, cs:__security_cookie
0x1800c7384  xor     rax, rsp
0x1800c7387  mov     [rbp+440h+var_20], rax
0x1800c738e  mov     rsi, rdx
0x1800c7391  mov     [rsp+540h+var_4D0], rdx
0x1800c7396  xor     r14d, r14d
0x1800c7399  lea     rcx, [rbp+440h+var_430]
0x1800c739d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800c73a2  nop
0x1800c73a3  lea     rdx, aProcessors; "{\"processors\":["
0x1800c73aa  lea     rcx, [rbp+440h+var_430]
0x1800c73ae  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800c73b3  xor     edx, edx; Val
0x1800c73b5  mov     r8d, 1FEh; Size
0x1800c73bb  lea     rcx, [rbp+440h+Name]; void *
0x1800c73c2  call    memset_0
0x1800c73c7  mov     [rsp+540h+cchName], r14d
0x1800c73cc  mov     [rsp+540h+cSubKeys], r14d
0x1800c73d1  mov     [rsp+540h+phkResult], r14
0x1800c73d6  lea     r8, [rsp+540h+phkResult]; phkResult
0x1800c73db  lea     rdx, aHardwareDescri_0; "Hardware\\Description\\System\\CentralP"...
0x1800c73e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c73e9  call    cs:__imp_RegOpenKeyW
0x1800c73ef  test    eax, eax
0x1800c73f1  jz      short loc_1800C744E
0x1800c73f3  lea     rdx, asc_1801BD500; "]}"
0x1800c73fa  lea     rcx, [rbp+440h+var_430]
0x1800c73fe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800c7403  mov     rdx, rsi
0x1800c7406  lea     rcx, [rbp+440h+var_428]
0x1800c740a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800c740f  nop
0x1800c7410  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800c7415  test    rcx, rcx
0x1800c7418  jz      short loc_1800C7421
0x1800c741a  call    cs:__imp_RegCloseKey
0x1800c7420  nop
0x1800c7421  mov     rax, [rbp+440h+var_430]
0x1800c7425  movsxd  rcx, dword ptr [rax+4]
0x1800c7429  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x1800c7430  mov     [rbp+rcx+440h+var_430], rax
0x1800c7435  mov     rcx, [rbp+440h+var_430]
0x1800c7439  movsxd  rdx, dword ptr [rcx+4]
0x1800c743d  lea     r8d, [rdx-88h]
0x1800c7444  mov     [rbp+rdx+440h+var_434], r8d
0x1800c7449  jmp     loc_1800C778A
0x1800c744e  mov     [rsp+540h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800c7453  mov     [rsp+540h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800c7458  mov     [rsp+540h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800c745d  mov     [rsp+540h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800c7462  mov     [rsp+540h+lpcValues], r14; lpcValues
0x1800c7467  mov     [rsp+540h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800c746c  mov     [rsp+540h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800c7471  lea     rax, [rsp+540h+cSubKeys]
0x1800c7476  mov     [rsp+540h+lpcSubKeys], rax; lpcSubKeys
0x1800c747b  xor     r9d, r9d; lpReserved
0x1800c747e  xor     r8d, r8d; lpcchClass
0x1800c7481  xor     edx, edx; lpClass
0x1800c7483  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800c7488  call    cs:__imp_RegQueryInfoKeyW
0x1800c748e  cmp     [rsp+540h+cSubKeys], r14d
0x1800c7493  jz      loc_1800C7736
0x1800c7499  mov     [rbp+440h+var_480], 0
0x1800c74a0  mov     [rbp+440h+var_478], r14
0x1800c74a4  mov     [rbp+440h+var_470], r14
0x1800c74a8  mov     edi, 108h
0x1800c74ad  mov     ecx, edi; Size
0x1800c74af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c74b4  mov     [rax], rax
0x1800c74b7  mov     [rax+8], rax
0x1800c74bb  mov     [rbp+440h+var_478], rax
0x1800c74bf  mov     [rbp+440h+var_468], r14
0x1800c74c3  xorps   xmm0, xmm0
0x1800c74c6  movdqa  [rbp+440h+var_460], xmm0
0x1800c74cb  mov     [rbp+440h+var_450], 7
0x1800c74d3  mov     [rbp+440h+var_448], 8
0x1800c74db  mov     [rbp+440h+var_480], 3F800000h
0x1800c74e2  mov     r8, rax
0x1800c74e5  mov     edx, 10h
0x1800c74ea  lea     rcx, [rbp+440h+var_468]
0x1800c74ee  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>)
0x1800c74f3  nop
0x1800c74f4  mov     ebx, r14d
0x1800c74f7  cmp     [rsp+540h+cSubKeys], r14d
0x1800c74fc  jbe     loc_1800C75CB
0x1800c7502  mov     [rsp+540h+cchName], 0FFh
0x1800c750a  mov     [rsp+540h+lpcValues], r14; lpftLastWriteTime
0x1800c750f  mov     [rsp+540h+lpcbMaxClassLen], r14; lpcchClass
0x1800c7514  mov     [rsp+540h+lpcbMaxSubKeyLen], r14; lpClass
0x1800c7519  mov     [rsp+540h+lpcSubKeys], r14; lpReserved
0x1800c751e  lea     r9, [rsp+540h+cchName]; lpcchName
0x1800c7523  lea     r8, [rbp+440h+Name]; lpName
0x1800c752a  mov     edx, ebx; dwIndex
0x1800c752c  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800c7531  call    cs:__imp_RegEnumKeyExW
0x1800c7537  test    eax, eax
0x1800c7539  jnz     loc_1800C75BF
0x1800c753f  xorps   xmm0, xmm0
0x1800c7542  movups  [rbp+440h+var_240], xmm0
0x1800c7549  xorps   xmm1, xmm1
0x1800c754c  movdqu  [rbp+440h+var_230], xmm1
0x1800c7554  lea     rax, [rbp+440h+Name]
0x1800c755b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c755f  inc     r8
0x1800c7562  cmp     [rax+r8*2], r14w
0x1800c7567  jnz     short loc_1800C755F
0x1800c7569  lea     rdx, [rbp+440h+Name]
0x1800c7570  lea     rcx, [rbp+440h+var_240]
0x1800c7577  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c757c  nop
0x1800c757d  lea     rdx, [rbp+440h+var_240]
0x1800c7584  lea     rcx, [rbp+440h+var_340]
0x1800c758b  call    ?GetProcessorRegistryTuple_N@CProcessorInfo@@CA?AUProcessorRegistryTuple@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CProcessorInfo::GetProcessorRegistryTuple_N(std::wstring const &)
0x1800c7590  nop
0x1800c7591  lea     rcx, [rbp+440h+var_240]
0x1800c7598  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c759d  lea     r8, [rbp+440h+var_340]
0x1800c75a4  lea     rdx, [rsp+540h+var_4D0]
0x1800c75a9  lea     rcx, [rbp+440h+var_480]
0x1800c75ad  call    ??$emplace@AEBUProcessorRegistryTuple_2@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@@std@@_N@1@AEBUProcessorRegistryTuple_2@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(ProcessorRegistryTuple_2 const &)
0x1800c75b2  nop
0x1800c75b3  lea     rcx, [rbp+440h+var_340]; this
0x1800c75ba  call    ??1ProcessorRegistryTuple@@QEAA@XZ; ProcessorRegistryTuple::~ProcessorRegistryTuple(void)
0x1800c75bf  inc     ebx
0x1800c75c1  cmp     ebx, [rsp+540h+cSubKeys]
0x1800c75c5  jb      loc_1800C7502
0x1800c75cb  mov     [rbp+440h+var_4C0], 0
0x1800c75d2  mov     [rbp+440h+var_4B8], r14
0x1800c75d6  mov     [rbp+440h+var_4B0], r14
0x1800c75da  mov     rcx, rdi; Size
0x1800c75dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c75e2  mov     [rax], rax
0x1800c75e5  mov     [rax+8], rax
0x1800c75e9  mov     [rbp+440h+var_4B8], rax
0x1800c75ed  mov     [rbp+440h+var_4A8], r14
0x1800c75f1  xorps   xmm0, xmm0
0x1800c75f4  movdqa  [rbp+440h+var_4A0], xmm0
0x1800c75f9  mov     [rbp+440h+var_490], 7
0x1800c7601  mov     [rbp+440h+var_488], 8
0x1800c7609  mov     [rbp+440h+var_4C0], 3F800000h
0x1800c7610  mov     r8, rax
0x1800c7613  mov     edx, 10h
0x1800c7618  lea     rcx, [rbp+440h+var_4A8]
0x1800c761c  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple>>,std::_Iterator_base0>)
0x1800c7621  nop
0x1800c7622  mov     eax, 4
0x1800c7627  cmp     [rbp+440h+var_470], rax
0x1800c762b  jbe     short loc_1800C7689
0x1800c762d  mov     rbx, [rbp+440h+var_478]
0x1800c7631  mov     rbx, [rbx]
0x1800c7634  mov     rdi, rbx
0x1800c7637  mov     rdi, [rdi]
0x1800c763a  dec     eax
0x1800c763c  test    eax, eax
0x1800c763e  jg      short loc_1800C7637
0x1800c7640  cmp     rbx, rdi
0x1800c7643  jz      short loc_1800C765C
0x1800c7645  lea     r8, [rbx+10h]
0x1800c7649  lea     rdx, [rsp+540h+var_4D0]
0x1800c764e  lea     rcx, [rbp+440h+var_4C0]
0x1800c7652  call    ??$emplace@AEBUProcessorRegistryTuple_2@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@@std@@_N@1@AEBUProcessorRegistryTuple_2@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::emplace<ProcessorRegistryTuple_2 const &>(ProcessorRegistryTuple_2 const &)
0x1800c7657  mov     rbx, [rbx]
0x1800c765a  jmp     short loc_1800C7640
0x1800c765c  lea     rcx, [rbp+440h+var_340]
0x1800c7663  call    ?GetProcessorRegistryTruncated@CProcessorInfo@@CA?AUProcessorRegistryTuple@@XZ; CProcessorInfo::GetProcessorRegistryTruncated(void)
0x1800c7668  nop
0x1800c7669  mov     r8, rax
0x1800c766c  lea     rdx, [rsp+540h+var_4D0]
0x1800c7671  lea     rcx, [rbp+440h+var_4C0]
0x1800c7675  call    ??$emplace@UProcessorRegistryTuple@@@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple@@V?$_Uhash_compare@UProcessorRegistryTuple@@U?$hash@UProcessorRegistryTuple@@@std@@U?$equal_to@UProcessorRegistryTuple@@@3@@std@@V?$allocator@UProcessorRegistryTuple@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple@@@std@@@std@@@std@@_N@1@$$QEAUProcessorRegistryTuple@@@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::emplace<ProcessorRegistryTuple>(ProcessorRegistryTuple &&)
0x1800c767a  nop
0x1800c767b  lea     rcx, [rbp+440h+var_340]; this
0x1800c7682  call    ??1ProcessorRegistryTuple@@QEAA@XZ; ProcessorRegistryTuple::~ProcessorRegistryTuple(void)
0x1800c7687  jmp     short loc_1800C76D3
0x1800c7689  lea     rax, [rbp+440h+var_4C0]
0x1800c768d  mov     [rsp+540h+var_4D0], rax
0x1800c7692  mov     eax, [rbp+440h+var_480]
0x1800c7695  mov     [rbp+440h+var_4C0], eax
0x1800c7698  mov     rdx, [rbp+440h+var_478]
0x1800c769c  mov     r8, rdx
0x1800c769f  mov     rdx, [rdx]
0x1800c76a2  lea     rcx, [rbp+440h+var_4B8]
0x1800c76a6  call    ??$_Assign_cast@AEAUProcessorRegistryTuple_2@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@?$list@UProcessorRegistryTuple_2@@V?$allocator@UProcessorRegistryTuple_2@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<ProcessorRegistryTuple_2>::_Assign_cast<ProcessorRegistryTuple_2 &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>)
0x1800c76ab  mov     rdx, [rbp+440h+var_4B0]
0x1800c76af  lea     rcx, [rbp+440h+var_4C0]
0x1800c76b3  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800c76b8  mov     rdx, rax
0x1800c76bb  lea     rcx, [rbp+440h+var_4C0]
0x1800c76bf  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple@@V?$_Uhash_compare@UProcessorRegistryTuple@@U?$hash@UProcessorRegistryTuple@@@std@@U?$equal_to@UProcessorRegistryTuple@@@3@@std@@V?$allocator@UProcessorRegistryTuple@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple,std::_Uhash_compare<ProcessorRegistryTuple,std::hash<ProcessorRegistryTuple>,std::equal_to<ProcessorRegistryTuple>>,std::allocator<ProcessorRegistryTuple>,0>>::_Forced_rehash(unsigned __int64)
0x1800c76c4  mov     [rsp+540h+var_4D0], r14
0x1800c76c9  lea     rcx, [rsp+540h+var_4D0]
0x1800c76ce  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@UProcessorRegistryTuple_2@@V?$_Uhash_compare@UProcessorRegistryTuple_2@@U?$hash@UProcessorRegistryTuple_2@@@std@@U?$equal_to@UProcessorRegistryTuple_2@@@3@@std@@V?$allocator@UProcessorRegistryTuple_2@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ProcessorRegistryTuple_2,std::_Uhash_compare<ProcessorRegistryTuple_2,std::hash<ProcessorRegistryTuple_2>,std::equal_to<ProcessorRegistryTuple_2>>,std::allocator<ProcessorRegistryTuple_2>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800c76d3  mov     rax, [rbp+440h+var_4B8]
0x1800c76d7  mov     rbx, [rax]
0x1800c76da  lea     rdx, [rbx+10h]
0x1800c76de  lea     rcx, [rbp+440h+var_430]
0x1800c76e2  call    ??6@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV01@AEBUProcessorRegistryTuple_2@@@Z; operator<<(std::basic_ostream<ushort> &,ProcessorRegistryTuple_2 const &)
0x1800c76e7  mov     rdi, [rbp+440h+var_4B8]
0x1800c76eb  mov     rbx, [rbx]
0x1800c76ee  cmp     rbx, rdi
0x1800c76f1  jz      short loc_1800C7711
0x1800c76f3  lea     rdx, asc_1801BCDD4; ","
0x1800c76fa  lea     rcx, [rbp+440h+var_430]
0x1800c76fe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800c7703  lea     rdx, [rbx+10h]
0x1800c7707  mov     rcx, rax
0x1800c770a  call    ??6@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV01@AEBUProcessorRegistryTuple_2@@@Z; operator<<(std::basic_ostream<ushort> &,ProcessorRegistryTuple_2 const &)
0x1800c770f  jmp     short loc_1800C76EB
0x1800c7711  lea     rcx, [rbp+440h+var_4A8]
0x1800c7715  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(void)
0x1800c771a  lea     rcx, [rbp+440h+var_4B8]
0x1800c771e  call    ??1?$list@UProcessorRegistryTuple@@V?$allocator@UProcessorRegistryTuple@@@std@@@std@@QEAA@XZ; std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>(void)
0x1800c7723  nop
0x1800c7724  lea     rcx, [rbp+440h+var_468]
0x1800c7728  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UProcessorRegistryTuple_2@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProcessorRegistryTuple_2>>,std::_Iterator_base0>>>(void)
0x1800c772d  lea     rcx, [rbp+440h+var_478]
0x1800c7731  call    ??1?$list@UProcessorRegistryTuple@@V?$allocator@UProcessorRegistryTuple@@@std@@@std@@QEAA@XZ; std::list<ProcessorRegistryTuple>::~list<ProcessorRegistryTuple>(void)
0x1800c7736  lea     rdx, asc_1801BD500; "]}"
0x1800c773d  lea     rcx, [rbp+440h+var_430]
0x1800c7741  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1800c7746  mov     rdx, rsi
0x1800c7749  lea     rcx, [rbp+440h+var_428]
0x1800c774d  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800c7752  nop
0x1800c7753  mov     rcx, [rsp+540h+phkResult]; hKey
0x1800c7758  test    rcx, rcx
0x1800c775b  jz      short loc_1800C7764
0x1800c775d  call    cs:__imp_RegCloseKey
0x1800c7763  nop
0x1800c7764  mov     rax, [rbp+440h+var_430]
0x1800c7768  movsxd  rcx, dword ptr [rax+4]
0x1800c776c  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x1800c7773  mov     [rbp+rcx+440h+var_430], rax
0x1800c7778  mov     rax, [rbp+440h+var_430]
0x1800c777c  movsxd  rcx, dword ptr [rax+4]
0x1800c7780  lea     edx, [rcx-88h]
0x1800c7786  mov     [rbp+rcx+440h+var_434], edx
0x1800c778a  lea     rcx, [rbp+440h+var_428]
0x1800c778e  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800c7793  lea     rcx, [rbp+440h+var_420]
0x1800c7797  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x1800c779d  lea     rcx, [rbp+440h+var_3A8]
0x1800c77a4  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800c77aa  mov     rax, rsi
0x1800c77ad  mov     rcx, [rbp+440h+var_20]
0x1800c77b4  xor     rcx, rsp; StackCookie
0x1800c77b7  call    __security_check_cookie
0x1800c77bc  lea     r11, [rsp+540h+var_10]
0x1800c77c4  mov     rbx, [r11+20h]
0x1800c77c8  mov     rsi, [r11+30h]
0x1800c77cc  mov     rsp, r11
0x1800c77cf  pop     r14
0x1800c77d1  pop     rdi
0x1800c77d2  pop     rbp
0x1800c77d3  retn
```

# NetworkEnumerator::RuntimeClassInitialize(ulong,tagNP_ENUM_NETWORK,std::vector<_GUID,std::allocator<_GUID>> const *,uint)

- ea: `0x180085310`
- end: `0x1800856c1`
- name: `?RuntimeClassInitialize@NetworkEnumerator@@QEAAJKW4tagNP_ENUM_NETWORK@@PEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@I@Z`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bcae4`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x1800116f8`
- `0x1800120a0`
- `0x1800131c4`
- `0x180013748`
- `0x180015608`
- `0x18002061c`
- `0x18003b250`
- `0x18004068c`
- `0x1800467cc`
- `0x1800490d4`
- `0x180085310`
- `0x1800a716c`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800d7d1c`
- `0x1800d7e7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800855d3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800855d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800854db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800854db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180085570`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180085570`

## string_xrefs

- `0x1800853ad`: `onecore\net\netprofiles\service\src\host\lib\enumprofilei.cpp`
- `0x180085427`: `onecore\net\netprofiles\service\src\host\lib\enumprofilei.cpp`
- `0x1800854f0`: `onecore\net\netprofiles\service\src\host\lib\enumprofilei.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall NetworkEnumerator::RuntimeClassInitialize(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int128 *a4,
        unsigned int a5)
{
  unsigned __int64 v7; // r15
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 i; // rbx
  __int64 v12; // rdi
  const WCHAR *v13; // rdx
  unsigned int v14; // eax
  DWORD j; // ebx
  _QWORD *k; // rcx
  __int64 v17; // rax
  int phkResult; // [rsp+20h] [rbp-F8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-F8h]
  DWORD cchName; // [rsp+40h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-B8h]
  __int128 v25; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+78h] [rbp-A0h]
  GUID iid; // [rsp+80h] [rbp-98h] BYREF
  WCHAR Name[40]; // [rsp+90h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v7 = a2;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 > 7 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_d(v9[2], 11, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids, (unsigned int)a3);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\enumprofilei.cpp",
      (const char *)0x80070057LL,
      phkResult);
  }
  v23 = 0;
  v24 = 0;
  std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(&v23);
  if ( a4 )
  {
    if ( &v23 != a4 )
      std::vector<_GUID>::_Assign_counted_range<_GUID *>(
        &v23,
        *(_QWORD *)a4,
        (__int64)(*((_QWORD *)a4 + 1) - *(_QWORD *)a4) >> 4);
  }
  else
  {
    if ( (a3 & 1) != 0 )
    {
      v10 = (unsigned int)a3 >> 2;
      LOBYTE(v10) = (a3 & 4) == 0;
      NetworkPropertyMaps::FindAllConnectedNetworks(&v25, v10, a5);
      v12 = *((_QWORD *)&v25 + 1);
      for ( i = v25; i != v12; i += 696 )
        std::vector<_GUID>::emplace_back<_GUID const &>(&v23, i + 32);
      std::vector<ACTIVE_NETWORK>::_Tidy(&v25);
    }
    if ( (a3 & 2) != 0 )
    {
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v13 = (const WCHAR *)&qword_1801C7140;
      if ( (unsigned __int64)qword_1801C7158 > 7 )
        v13 = qword_1801C7140;
      v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x20019u, &hKey);
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\enumprofilei.cpp",
          (const char *)v14,
          phkResulta);
      v25 = 0;
      v26 = 0;
      std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(&v25);
      for ( j = 0; ; ++j )
      {
        memset_0(Name, 0, 0x4Eu);
        cchName = 39;
        if ( RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0) )
          break;
        iid = 0;
        if ( IIDFromString(Name, &iid) >= 0 )
        {
          for ( k = (_QWORD *)v23; k != *((_QWORD **)&v23 + 1); k += 2 )
          {
            v17 = *k - *(_QWORD *)&iid.Data1;
            if ( *k == *(_QWORD *)&iid.Data1 )
              v17 = k[1] - *(_QWORD *)iid.Data4;
            if ( !v17 )
              goto LABEL_35;
          }
          std::vector<_GUID>::emplace_back<_GUID &>(&v25, &iid);
        }
LABEL_35:
        ;
      }
      std::vector<_GUID>::insert<std::move_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>,0>(
        (unsigned int)&v23,
        (unsigned int)&cchName,
        DWORD2(v23),
        v25,
        *((__int64 *)&v25 + 1));
      std::vector<_GUID>::~vector<_GUID>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  if ( v7 > (__int64)(*((_QWORD *)&v23 + 1) - v23) >> 4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\enumprofilei.cpp",
      (const char *)0x8000FFFFLL,
      phkResult);
  *(_DWORD *)(a1 + 60) = a5;
  std::vector<_GUID>::operator=(a1 + 24, &v23);
  *(_DWORD *)(a1 + 16) = v7;
  *(_DWORD *)(a1 + 64) = 1;
  *(_DWORD *)(a1 + 56) = a3;
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 24) + 16 * v7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids, 0);
  std::vector<_GUID>::~vector<_GUID>(&v23);
  return 0;
}

```

## disassembly

```asm
0x180085310  mov     [rsp+arg_8], rbx
0x180085315  push    rsi
0x180085316  push    rdi
0x180085317  push    r13
0x180085319  push    r14
0x18008531b  push    r15
0x18008531d  sub     rsp, 0F0h
0x180085324  mov     rax, cs:__security_cookie
0x18008532b  xor     rax, rsp
0x18008532e  mov     [rsp+118h+var_38], rax
0x180085336  mov     rbx, r9
0x180085339  mov     esi, r8d
0x18008533c  mov     r15d, edx
0x18008533f  mov     r14, rcx
0x180085342  lea     r13, WPP_GLOBAL_Control
0x180085349  mov     rcx, cs:WPP_GLOBAL_Control
0x180085350  cmp     rcx, r13
0x180085353  jz      short loc_180085377
0x180085355  test    byte ptr [rcx+1Ch], 8
0x180085359  jz      short loc_180085377
0x18008535b  mov     edx, 0Ah
0x180085360  lea     r8, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids
0x180085367  mov     rcx, [rcx+10h]
0x18008536b  call    WPP_SF_
0x180085370  mov     rcx, cs:WPP_GLOBAL_Control
0x180085377  cmp     esi, 7
0x18008537a  jle     short loc_1800853BE
0x18008537c  cmp     rcx, r13
0x18008537f  jz      short loc_18008539F
0x180085381  test    byte ptr [rcx+1Ch], 2
0x180085385  jz      short loc_18008539F
0x180085387  mov     edx, 0Bh
0x18008538c  mov     r9d, esi
0x18008538f  lea     r8, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids
0x180085396  mov     rcx, [rcx+10h]
0x18008539a  call    WPP_SF_d
0x18008539f  mov     rcx, [rsp+118h]; this
0x1800853a7  mov     r9d, 80070057h; char *
0x1800853ad  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x1800853b4  mov     edx, 1Bh; void *
0x1800853b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800853be  xorps   xmm0, xmm0
0x1800853c1  xor     eax, eax
0x1800853c3  movups  [rsp+118h+var_C8], xmm0
0x1800853c8  mov     [rsp+118h+var_B8], rax
0x1800853cd  lea     rcx, [rsp+118h+var_C8]
0x1800853d2  call    ??0?$vector@U?$pair@U_GUID@@UStructDifference@2@@std@@V?$allocator@U?$pair@U_GUID@@UStructDifference@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(void)
0x1800853d7  nop
0x1800853d8  test    rbx, rbx
0x1800853db  jz      short loc_180085438
0x1800853dd  lea     rax, [rsp+118h+var_C8]
0x1800853e2  cmp     rax, rbx
0x1800853e5  jz      short loc_1800853FF
0x1800853e7  mov     r8, [rbx+8]
0x1800853eb  sub     r8, [rbx]
0x1800853ee  sar     r8, 4
0x1800853f2  mov     rdx, [rbx]
0x1800853f5  lea     rcx, [rsp+118h+var_C8]
0x1800853fa  call    ??$_Assign_counted_range@PEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXPEAU_GUID@@_K@Z; std::vector<_GUID>::_Assign_counted_range<_GUID *>(_GUID *,unsigned __int64)
0x1800853ff  mov     rdi, r15
0x180085402  mov     rcx, [rsp+118h]; this
0x18008540a  mov     rax, qword ptr [rsp+118h+var_C8+8]
0x18008540f  sub     rax, qword ptr [rsp+118h+var_C8]
0x180085414  sar     rax, 4
0x180085418  cmp     r15, rax
0x18008541b  jbe     loc_180085626
0x180085421  mov     r9d, 8000FFFFh; char *
0x180085427  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x18008542e  mov     edx, 54h ; 'T'; void *
0x180085433  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085438  test    sil, 1
0x18008543c  jz      short loc_18008548B
0x18008543e  mov     edx, esi
0x180085440  shr     edx, 2
0x180085443  not     dl
0x180085445  and     dl, 1
0x180085448  mov     r8d, [rsp+118h+arg_20]
0x180085450  lea     rcx, [rsp+118h+var_B0]
0x180085455  call    ?FindAllConnectedNetworks@NetworkPropertyMaps@@SA?AV?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@_NI@Z; NetworkPropertyMaps::FindAllConnectedNetworks(bool,uint)
0x18008545a  nop
0x18008545b  mov     rbx, qword ptr [rsp+118h+var_B0]
0x180085460  mov     rdi, qword ptr [rsp+118h+var_B0+8]
0x180085465  cmp     rbx, rdi
0x180085468  jz      short loc_180085481
0x18008546a  lea     rdx, [rbx+20h]
0x18008546e  lea     rcx, [rsp+118h+var_C8]
0x180085473  call    ??$emplace_back@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAU_GUID@@AEBU2@@Z; std::vector<_GUID>::emplace_back<_GUID const &>(_GUID const &)
0x180085478  add     rbx, 2B8h
0x18008547f  jmp     short loc_180085465
0x180085481  lea     rcx, [rsp+118h+var_B0]
0x180085486  call    ?_Tidy@?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@AEAAXXZ; std::vector<ACTIVE_NETWORK>::_Tidy(void)
0x18008548b  test    sil, 2
0x18008548f  jz      loc_1800853FF
0x180085495  mov     [rsp+118h+hKey], 0
0x18008549e  xor     edx, edx
0x1800854a0  lea     rcx, [rsp+118h+hKey]
0x1800854a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800854aa  lea     rdx, qword_1801C7140
0x1800854b1  cmp     cs:qword_1801C7158, 7
0x1800854b9  cmova   rdx, cs:qword_1801C7140; lpSubKey
0x1800854c1  lea     rax, [rsp+118h+hKey]
0x1800854c6  mov     [rsp+118h+phkResult], rax; unsigned int
0x1800854cb  mov     r9d, 20019h; samDesired
0x1800854d1  xor     r8d, r8d; ulOptions
0x1800854d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800854db  call    cs:__imp_RegOpenKeyExW
0x1800854e1  mov     rcx, [rsp+118h]; this
0x1800854e9  test    eax, eax
0x1800854eb  jz      short loc_180085501
0x1800854ed  mov     r9d, eax; char *
0x1800854f0  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x1800854f7  mov     edx, 31h ; '1'; void *
0x1800854fc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180085501  xorps   xmm0, xmm0
0x180085504  xor     eax, eax
0x180085506  movups  [rsp+118h+var_B0], xmm0
0x18008550b  mov     [rsp+118h+var_A0], rax
0x180085510  lea     rcx, [rsp+118h+var_B0]
0x180085515  call    ??0?$vector@U?$pair@U_GUID@@UStructDifference@2@@std@@V?$allocator@U?$pair@U_GUID@@UStructDifference@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(void)
0x18008551a  nop
0x18008551b  xor     ebx, ebx
0x18008551d  xor     edx, edx; Val
0x18008551f  lea     r8d, [rdx+4Eh]; Size
0x180085523  lea     rcx, [rsp+118h+Name]; void *
0x18008552b  call    memset_0
0x180085530  mov     [rsp+118h+cchName], 27h ; '''
0x180085538  mov     [rsp+118h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180085541  mov     [rsp+118h+lpcchClass], 0; lpcchClass
0x18008554a  mov     [rsp+118h+lpClass], 0; lpClass
0x180085553  mov     [rsp+118h+phkResult], 0; lpReserved
0x18008555c  lea     r9, [rsp+118h+cchName]; lpcchName
0x180085561  lea     r8, [rsp+118h+Name]; lpName
0x180085569  mov     edx, ebx; dwIndex
0x18008556b  mov     rcx, [rsp+118h+hKey]; hKey
0x180085570  call    cs:__imp_RegEnumKeyExW
0x180085576  test    eax, eax
0x180085578  jz      short loc_1800855B8
0x18008557a  mov     rax, qword ptr [rsp+118h+var_B0+8]
0x18008557f  mov     [rsp+118h+phkResult], rax
0x180085584  mov     r9, qword ptr [rsp+118h+var_B0]
0x180085589  mov     r8, qword ptr [rsp+118h+var_C8+8]
0x18008558e  lea     rdx, [rsp+118h+cchName]
0x180085593  lea     rcx, [rsp+118h+var_C8]
0x180085598  call    ??$insert@V?$move_iterator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@std@@@std@@$0A@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@1@V?$move_iterator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@std@@@1@1@Z; std::vector<_GUID>::insert<std::move_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,std::move_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>,std::move_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>>)
0x18008559d  nop
0x18008559e  lea     rcx, [rsp+118h+var_B0]
0x1800855a3  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x1800855a8  nop
0x1800855a9  lea     rcx, [rsp+118h+hKey]
0x1800855ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800855b3  jmp     loc_1800853FF
0x1800855b8  xorps   xmm0, xmm0
0x1800855bb  movups  xmmword ptr [rsp+118h+iid.Data1], xmm0
0x1800855c3  lea     rdx, [rsp+118h+iid]; lpiid
0x1800855cb  lea     rcx, [rsp+118h+Name]; lpsz
0x1800855d3  call    cs:__imp_IIDFromString
0x1800855d9  test    eax, eax
0x1800855db  js      short loc_18008561F
0x1800855dd  mov     rcx, qword ptr [rsp+118h+var_C8]
0x1800855e2  cmp     rcx, qword ptr [rsp+118h+var_C8+8]
0x1800855e7  jz      short loc_18008560D
0x1800855e9  mov     rax, [rcx]
0x1800855ec  sub     rax, qword ptr [rsp+118h+iid.Data1]
0x1800855f4  jnz     short loc_180085602
0x1800855f6  mov     rax, [rcx+8]
0x1800855fa  sub     rax, qword ptr [rsp+118h+iid.Data4]
0x180085602  test    rax, rax
0x180085605  jz      short loc_18008561F
0x180085607  add     rcx, 10h
0x18008560b  jmp     short loc_1800855E2
0x18008560d  lea     rdx, [rsp+118h+iid]
0x180085615  lea     rcx, [rsp+118h+var_B0]
0x18008561a  call    ??$emplace_back@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAU_GUID@@AEAU2@@Z; std::vector<_GUID>::emplace_back<_GUID &>(_GUID &)
0x18008561f  inc     ebx
0x180085621  jmp     loc_18008551D
0x180085626  mov     eax, [rsp+118h+arg_20]
0x18008562d  mov     [r14+3Ch], eax
0x180085631  lea     rdx, [rsp+118h+var_C8]
0x180085636  lea     rcx, [r14+18h]
0x18008563a  call    ??4?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<_GUID>::operator=(std::vector<_GUID> &&)
0x18008563f  mov     [r14+10h], r15d
0x180085643  mov     dword ptr [r14+40h], 1
0x18008564b  mov     [r14+38h], esi
0x18008564f  shl     rdi, 4
0x180085653  add     rdi, [r14+18h]
0x180085657  mov     [r14+30h], rdi
0x18008565b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085662  cmp     rcx, r13
0x180085665  jz      short loc_180085686
0x180085667  test    byte ptr [rcx+1Ch], 8
0x18008566b  jz      short loc_180085686
0x18008566d  mov     edx, 0Ch
0x180085672  xor     r9d, r9d
0x180085675  lea     r8, WPP_1b3e06c3891833d3962ce812d67b731a_Traceguids
0x18008567c  mov     rcx, [rcx+10h]
0x180085680  call    WPP_SF_d
0x180085685  nop
0x180085686  lea     rcx, [rsp+118h+var_C8]
0x18008568b  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180085690  xor     eax, eax
0x180085692  jmp     short loc_180085698
0x180085694  mov     eax, [rsp+118h+cchName]
0x180085698  mov     rcx, [rsp+118h+var_38]
0x1800856a0  xor     rcx, rsp; StackCookie
0x1800856a3  call    __security_check_cookie
0x1800856a8  mov     rbx, [rsp+118h+arg_8]
0x1800856b0  add     rsp, 0F0h
0x1800856b7  pop     r15
0x1800856b9  pop     r14
0x1800856bb  pop     r13
0x1800856bd  pop     rdi
0x1800856be  pop     rsi
0x1800856bf  retn
```

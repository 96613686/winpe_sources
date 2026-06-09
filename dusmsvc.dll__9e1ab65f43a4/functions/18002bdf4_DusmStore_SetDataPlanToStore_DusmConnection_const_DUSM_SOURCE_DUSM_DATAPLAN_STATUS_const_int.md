# DusmStore::SetDataPlanToStore(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS const &,int)

- ea: `0x18002bdf4`
- end: `0x18002c16c`
- name: `?SetDataPlanToStore@DusmStore@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_DATAPLAN_STATUS@@H@Z`
- size: `888`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const void *, DWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18002b9f0`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x1800132f4`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180025a58`
- `0x180025da0`
- `0x180026fa0`
- `0x1800275a8`
- `0x180029344`
- `0x18002bdf4`
- `0x18002da30`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be37`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002bf88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c0d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c116`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002bf88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c0d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c116`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c054`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c054`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c08f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c0b9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c08f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c0b9`

## string_xrefs

- `0x18002c14b`: `DusmStore::SetDataPlanToStore::RegCreateKeyExW`
- `0x18002c0e6`: `DusmStore::SetDataPlanToStore::RegSetKeyValueW::flags`
- `0x18002c123`: `DusmStore::SetDataPlanToStore::RegSetKeyValueW::dataPlan`

## pseudocode

```c
__int64 __fastcall DusmStore::SetDataPlanToStore(__int64 a1, __int64 a2, unsigned int a3, const void *a4, DWORD a5)
{
  LPCRITICAL_SECTION v8; // rdi
  LPCRITICAL_SECTION v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  __int64 v14; // rax
  int *v15; // rcx
  const WCHAR *v16; // rax
  __int64 PlanGuid; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // edi
  unsigned int v24; // edi
  const WCHAR *v25; // rax
  const WCHAR *v26; // rax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  const char *samDesiredb; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[32]; // [rsp+B8h] [rbp-48h] BYREF
  BOOL Data; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v38[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v39; // [rsp+108h] [rbp+8h] BYREF
  __int64 v40; // [rsp+118h] [rbp+18h]
  __int64 v41; // [rsp+120h] [rbp+20h]
  _BYTE v42[80]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v8 = DusmStore::s_pInstance;
  v9 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v30 = v9;
  hKey = 0;
  v39 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(v39) = 0;
  v10 = std::wstring::wstring(v34, qword_180068EC8);
  v11 = std::operator+<wchar_t>(v33, v10, L"\\");
  std::operator+<wchar_t>(v38, v11, a2 + 144);
  std::wstring::_Tidy_deallocate(v33);
  std::wstring::_Tidy_deallocate(v34);
  memset_0(v42, 0, 0x44u);
  v12 = DusmStore::QueryDataPlanFromStore(v8, a2, a3, v42, &v39);
  if ( a5 )
  {
    if ( !v12 )
      goto LABEL_3;
  }
  else if ( !v12 )
  {
    goto LABEL_9;
  }
  if ( v40 )
  {
    v14 = std::operator+<wchar_t>((int)v31);
    std::wstring::append(v38, v14);
    v15 = v31;
    goto LABEL_10;
  }
  if ( a5 )
  {
LABEL_8:
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, v16);
    goto LABEL_3;
  }
LABEL_9:
  PlanGuid = CreatePlanGuid(v35);
  v20 = std::wstring::_Insert<wchar_t>(PlanGuid, v18, v19, 1);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  *(_OWORD *)v31 = *(_OWORD *)v20;
  v32 = *(_OWORD *)(v20 + 16);
  *(_WORD *)v20 = 0;
  *(_QWORD *)(v20 + 16) = 0;
  *(_QWORD *)(v20 + 24) = 7;
  std::wstring::append(v38, v31);
  std::wstring::_Tidy_deallocate(v31);
  v15 = (int *)v35;
LABEL_10:
  std::wstring::_Tidy_deallocate(v15);
  if ( a5 )
    goto LABEL_8;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38);
  v22 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v22 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v22,
      (unsigned int)"DusmStore::SetDataPlanToStore::RegCreateKeyExW",
      samDesired);
  Data = a3 == 3;
  v23 = RegSetKeyValueW(hKey, 0, L"DataPlanFlags", 4u, &Data, 4u);
  if ( v23 )
  {
    v25 = (const WCHAR *)std::wstring::c_str(v38);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, v25);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3AD,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v23,
      (unsigned int)"DusmStore::SetDataPlanToStore::RegSetKeyValueW::flags",
      samDesireda);
  }
  v24 = RegSetKeyValueW(hKey, 0, L"DataPlan", 3u, a4, 0x44u);
  if ( v24 )
  {
    v26 = (const WCHAR *)std::wstring::c_str(v38);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, v26);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3B6,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v24,
      (unsigned int)"DusmStore::SetDataPlanToStore::RegSetKeyValueW::dataPlan",
      samDesiredb);
  }
LABEL_3:
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(&v39);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
}

```

## disassembly

```asm
0x18002bdf4  mov     [rsp-8+arg_0], rbx
0x18002bdf9  push    rbp
0x18002bdfa  push    rsi
0x18002bdfb  push    rdi
0x18002bdfc  push    r14
0x18002bdfe  push    r15
0x18002be00  lea     rbp, [rsp-90h]
0x18002be08  sub     rsp, 190h
0x18002be0f  mov     rax, cs:__security_cookie
0x18002be16  xor     rax, rsp
0x18002be19  mov     [rbp+0B0h+var_30], rax
0x18002be20  mov     r15, r9
0x18002be23  mov     r14d, r8d
0x18002be26  mov     rsi, rdx
0x18002be29  mov     rdi, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002be30  lea     rbx, [rdi+28h]
0x18002be34  mov     rcx, rbx; lpCriticalSection
0x18002be37  call    cs:__imp_EnterCriticalSection
0x18002be3d  mov     [rsp+1B0h+var_160], rbx
0x18002be42  mov     [rbp+0B0h+hKey], 0
0x18002be4a  xorps   xmm0, xmm0
0x18002be4d  movups  [rbp+0B0h+var_A8], xmm0
0x18002be51  mov     [rbp+0B0h+var_98], 0
0x18002be59  mov     [rbp+0B0h+var_90], 7
0x18002be61  xor     eax, eax
0x18002be63  mov     word ptr [rbp+0B0h+var_A8], ax
0x18002be67  mov     rdx, cs:qword_180068EC8
0x18002be6e  lea     rcx, [rbp+0B0h+var_118]
0x18002be72  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002be77  nop
0x18002be78  lea     r8, asc_18004F678; "\\"
0x18002be7f  mov     rdx, rax
0x18002be82  lea     rcx, [rsp+1B0h+var_138]
0x18002be87  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002be8c  nop
0x18002be8d  lea     r8, [rsi+90h]
0x18002be94  mov     rdx, rax
0x18002be97  lea     rcx, [rbp+0B0h+var_C8]
0x18002be9b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002bea0  nop
0x18002bea1  lea     rcx, [rsp+1B0h+var_138]
0x18002bea6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002beab  nop
0x18002beac  lea     rcx, [rbp+0B0h+var_118]
0x18002beb0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002beb5  xor     edx, edx; Val
0x18002beb7  lea     r8d, [rdx+44h]; Size
0x18002bebb  lea     rcx, [rbp+0B0h+var_80]; void *
0x18002bebf  call    memset_0
0x18002bec4  lea     rax, [rbp+0B0h+var_A8]
0x18002bec8  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18002becd  lea     r9, [rbp+0B0h+var_80]
0x18002bed1  mov     r8d, r14d
0x18002bed4  mov     rdx, rsi
0x18002bed7  mov     rcx, rdi
0x18002beda  call    ?QueryDataPlanFromStore@DusmStore@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; DusmStore::QueryDataPlanFromStore(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &,std::wstring &)
0x18002bedf  mov     edi, 1
0x18002bee4  mov     ebx, [rbp+0B0h+arg_20]
0x18002beea  test    ebx, ebx
0x18002beec  jz      short loc_18002BF40
0x18002beee  test    eax, eax
0x18002bef0  jnz     short loc_18002BF44
0x18002bef2  lea     rcx, [rbp+0B0h+var_C8]
0x18002bef6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002befb  nop
0x18002befc  lea     rcx, [rbp+0B0h+var_A8]
0x18002bf00  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bf05  nop
0x18002bf06  lea     rcx, [rbp+0B0h+hKey]
0x18002bf0a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002bf0f  nop
0x18002bf10  lea     rcx, [rsp+1B0h+var_160]
0x18002bf15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002bf1a  mov     rcx, [rbp+0B0h+var_30]
0x18002bf21  xor     rcx, rsp; StackCookie
0x18002bf24  call    __security_check_cookie
0x18002bf29  mov     rbx, [rsp+1B0h+arg_0]
0x18002bf31  add     rsp, 190h
0x18002bf38  pop     r15
0x18002bf3a  pop     r14
0x18002bf3c  pop     rdi
0x18002bf3d  pop     rsi
0x18002bf3e  pop     rbp
0x18002bf3f  retn
0x18002bf40  test    eax, eax
0x18002bf42  jz      short loc_18002BF93
0x18002bf44  cmp     [rbp+0B0h+var_98], 0
0x18002bf49  jz      short loc_18002BF71
0x18002bf4b  lea     r8, [rbp+0B0h+var_A8]
0x18002bf4f  lea     rcx, [rsp+1B0h+var_158]; int
0x18002bf54  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_WAEBV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring const &)
0x18002bf59  nop
0x18002bf5a  mov     rdx, rax
0x18002bf5d  lea     rcx, [rbp+0B0h+var_C8]
0x18002bf61  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002bf66  nop
0x18002bf67  lea     rcx, [rsp+1B0h+var_158]
0x18002bf6c  jmp     loc_18002BFF9
0x18002bf71  test    ebx, ebx
0x18002bf73  jz      short loc_18002BF93
0x18002bf75  lea     rcx, [rbp+0B0h+var_C8]
0x18002bf79  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bf7e  mov     rdx, rax; lpSubKey
0x18002bf81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bf88  call    cs:__imp_RegDeleteTreeW
0x18002bf8e  jmp     loc_18002BEF2
0x18002bf93  lea     rcx, [rbp+0B0h+var_F8]
0x18002bf97  call    CreatePlanGuid
0x18002bf9c  nop
0x18002bf9d  mov     r9, rdi
0x18002bfa0  mov     rcx, rax
0x18002bfa3  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x18002bfa8  xorps   xmm0, xmm0
0x18002bfab  movups  xmmword ptr [rsp+1B0h+var_158], xmm0
0x18002bfb0  xorps   xmm1, xmm1
0x18002bfb3  movdqu  [rsp+1B0h+var_148], xmm1
0x18002bfb9  movups  xmm0, xmmword ptr [rax]
0x18002bfbc  movups  xmmword ptr [rsp+1B0h+var_158], xmm0
0x18002bfc1  movups  xmm1, xmmword ptr [rax+10h]
0x18002bfc5  movups  [rsp+1B0h+var_148], xmm1
0x18002bfca  xor     ecx, ecx
0x18002bfcc  mov     [rax], cx
0x18002bfcf  mov     [rax+10h], rcx
0x18002bfd3  mov     qword ptr [rax+18h], 7
0x18002bfdb  lea     rdx, [rsp+1B0h+var_158]
0x18002bfe0  lea     rcx, [rbp+0B0h+var_C8]
0x18002bfe4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002bfe9  nop
0x18002bfea  lea     rcx, [rsp+1B0h+var_158]
0x18002bfef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bff4  nop
0x18002bff5  lea     rcx, [rbp+0B0h+var_F8]
0x18002bff9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bffe  test    ebx, ebx
0x18002c000  jnz     loc_18002BF75
0x18002c006  xor     edx, edx
0x18002c008  lea     rcx, [rbp+0B0h+hKey]
0x18002c00c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c011  lea     rcx, [rbp+0B0h+var_C8]
0x18002c015  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c01a  mov     rdx, rax; lpSubKey
0x18002c01d  mov     [rsp+1B0h+lpdwDisposition], 0; lpdwDisposition
0x18002c026  lea     rax, [rbp+0B0h+hKey]
0x18002c02a  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18002c02f  mov     [rsp+1B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002c038  mov     dword ptr [rsp+1B0h+samDesired], 20006h; char *
0x18002c040  mov     [rsp+1B0h+dwOptions], ebx; dwOptions
0x18002c044  xor     r9d, r9d; lpClass
0x18002c047  xor     r8d, r8d; Reserved
0x18002c04a  mov     rbx, 0FFFFFFFF80000002h
0x18002c051  mov     rcx, rbx; hKey
0x18002c054  call    cs:__imp_RegCreateKeyExW
0x18002c05a  test    eax, eax
0x18002c05c  jnz     loc_18002C144
0x18002c062  mov     [rbp+0B0h+Data], eax
0x18002c065  cmp     r14d, 3
0x18002c069  jnz     short loc_18002C06E
0x18002c06b  mov     [rbp+0B0h+Data], edi
0x18002c06e  mov     r9d, 4; dwType
0x18002c074  mov     dword ptr [rsp+1B0h+samDesired], r9d; char *
0x18002c079  lea     rax, [rbp+0B0h+Data]
0x18002c07d  mov     qword ptr [rsp+1B0h+dwOptions], rax; lpData
0x18002c082  lea     r8, aDataplanflags; "DataPlanFlags"
0x18002c089  xor     edx, edx; lpSubKey
0x18002c08b  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18002c08f  call    cs:__imp_RegSetKeyValueW
0x18002c095  mov     edi, eax
0x18002c097  test    eax, eax
0x18002c099  jnz     short loc_18002C0CA
0x18002c09b  mov     dword ptr [rsp+1B0h+samDesired], 44h ; 'D'; char *
0x18002c0a3  mov     qword ptr [rsp+1B0h+dwOptions], r15; lpData
0x18002c0a8  lea     r9d, [rax+3]; dwType
0x18002c0ac  lea     r8, aDataplan; "DataPlan"
0x18002c0b3  xor     edx, edx; lpSubKey
0x18002c0b5  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18002c0b9  call    cs:__imp_RegSetKeyValueW
0x18002c0bf  mov     edi, eax
0x18002c0c1  test    eax, eax
0x18002c0c3  jnz     short loc_18002C107
0x18002c0c5  jmp     loc_18002BEF2
0x18002c0ca  lea     rcx, [rbp+0B0h+var_C8]
0x18002c0ce  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002c0d3  mov     rdx, rax; lpSubKey
0x18002c0d6  mov     rcx, rbx; hKey
0x18002c0d9  call    cs:__imp_RegDeleteTreeW
0x18002c0df  mov     rcx, [rbp+0B8h]; this
0x18002c0e6  lea     rax, aDusmstoreSetda_2; "DusmStore::SetDataPlanToStore::RegSetKe"...
0x18002c0ed  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002c0f2  mov     r9d, edi; char *
0x18002c0f5  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c0fc  mov     edx, 3ADh; void *
0x18002c101  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c107  lea     rcx, [rbp+0B0h+var_C8]
0x18002c10b  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002c110  mov     rdx, rax; lpSubKey
0x18002c113  mov     rcx, rbx; hKey
0x18002c116  call    cs:__imp_RegDeleteTreeW
0x18002c11c  mov     rcx, [rbp+0B8h]; this
0x18002c123  lea     rax, aDusmstoreSetda_0; "DusmStore::SetDataPlanToStore::RegSetKe"...
0x18002c12a  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002c12f  mov     r9d, edi; char *
0x18002c132  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c139  mov     edx, 3B6h; void *
0x18002c13e  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c144  mov     rcx, [rbp+0B8h]; this
0x18002c14b  lea     rdx, aDusmstoreSetda_9; "DusmStore::SetDataPlanToStore::RegCreat"...
0x18002c152  mov     qword ptr [rsp+1B0h+dwOptions], rdx; unsigned int
0x18002c157  mov     r9d, eax; char *
0x18002c15a  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c161  mov     edx, 39Dh; void *
0x18002c166  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```

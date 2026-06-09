# PFXCertificate::Delete(void)

- ea: `0x1800fe538`
- end: `0x1800fe7ef`
- name: `?Delete@PFXCertificate@@QEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(PFXCertificate *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18006c570`
- `0x18006c760`

## callees

- `0x180003504`
- `0x180008de0`
- `0x18000d4d4`
- `0x18000f36c`
- `0x180015888`
- `0x180023664`
- `0x18002412c`
- `0x180025ac0`
- `0x18002aed0`
- `0x1800681a4`
- `0x1800d07b4`
- `0x1800d0938`
- `0x1800fe1dc`
- `0x1800fe538`
- `0x1800feda0`
- `0x1800ffde0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fe573`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fe75f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fe573`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800fe75f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800fe6aa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800fe6aa`

## string_xrefs

- `0x1800fe5b7`: `Deleted PfxCertificate from Certificate Store`
- `0x1800fe713`: `Deleted PfxCertificate from Registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall PFXCertificate::Delete(PFXCertificate *this)
{
  CCertificate *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rdx
  _QWORD *Location; // rax
  int v7; // esi
  __int64 FriendlyNameRegistryPath; // rax
  unsigned int v10; // edi
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // edi
  unsigned int v14; // [rsp+20h] [rbp-C8h]
  char v15; // [rsp+30h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-B0h] BYREF
  struct _SYSTEMTIME v17; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-98h] BYREF
  char v19; // [rsp+60h] [rbp-88h]
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-78h]
  struct _SYSTEMTIME v21; // [rsp+80h] [rbp-68h] BYREF
  char v22; // [rsp+90h] [rbp-58h]
  struct _SYSTEMTIME v23; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  *(_QWORD *)&SystemTime.wYear = this;
  v15 = 0;
  v23 = 0;
  GetSystemTime(&v23);
  v18[0] = &v15;
  v18[1] = &v23;
  v19 = 1;
  v2 = (CCertificate *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    CCertificate::Delete(v2);
    if ( (unsigned int)dword_180155A70 > 5 )
    {
      *(_QWORD *)&v17.wYear = "Deleted PfxCertificate from Certificate Store";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_180155A70,
        (unsigned int)&unk_18013BD40,
        v3,
        v4,
        (__int64)&v17);
    }
    v5 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    if ( v5 )
      std::default_delete<PFXCertificate>::operator()();
  }
  hKey = 0;
  *(_QWORD *)&v21.wYear = &hKey;
  *(_QWORD *)&v21.wHour = 0;
  v22 = 1;
  Location = (_QWORD *)CCertificateStore::GetLocation(*((_QWORD *)this + 1), &v17);
  v7 = PFXCertificate::OpenRegkeyCurrentUserOrLocalMachine(Location, 0xF003Fu, (HKEY *)&v21.wHour);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v21);
  if ( v7 >= 0 )
  {
    FriendlyNameRegistryPath = PFXCertificate::GetFriendlyNameRegistryPath(this, &v21);
    if ( *(_QWORD *)(FriendlyNameRegistryPath + 24) > 7u )
      FriendlyNameRegistryPath = *(_QWORD *)FriendlyNameRegistryPath;
    v10 = RegDeleteKeyW(hKey, (LPCWSTR)FriendlyNameRegistryPath);
    std::wstring::_Tidy_deallocate(&v21);
    if ( v10 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2F3,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\pfxcertificate.cpp",
              (const char *)v10,
              v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v19 = 0;
      lambda_cfab9f70d7a8e493a5e53381049fea42_::operator()(v18);
      return v13;
    }
    else
    {
      if ( (unsigned int)dword_180155A70 > 5 )
      {
        *(_QWORD *)&v17.wYear = "Deleted PfxCertificate from Registry";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_180155A70,
          (unsigned int)byte_18013BD95,
          v11,
          v12,
          (__int64)&v17);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v15 = 1;
      v19 = 0;
      lambda_cfab9f70d7a8e493a5e53381049fea42_::operator()(v18);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\pfxcertificate.cpp",
      (const char *)(unsigned int)v7,
      v14);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v19 = 0;
    lambda_cfab9f70d7a8e493a5e53381049fea42_::operator()(v18);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1800fe538  mov     r11, rsp
0x1800fe53b  push    rbx
0x1800fe53c  push    rsi
0x1800fe53d  push    rdi
0x1800fe53e  push    r14
0x1800fe540  sub     rsp, 0C8h
0x1800fe547  mov     rax, cs:__security_cookie
0x1800fe54e  xor     rax, rsp
0x1800fe551  mov     [rsp+0E8h+var_38], rax
0x1800fe559  mov     rdi, rcx
0x1800fe55c  mov     qword ptr [rsp+0E8h+SystemTime.wYear], rcx
0x1800fe561  xor     ebx, ebx
0x1800fe563  mov     [rsp+0E8h+var_B8], bl
0x1800fe567  xorps   xmm0, xmm0
0x1800fe56a  movups  xmmword ptr [r11-48h], xmm0
0x1800fe56f  lea     rcx, [r11-48h]; lpSystemTime
0x1800fe573  call    cs:__imp_GetSystemTime
0x1800fe57a  nop     dword ptr [rax+rax+00h]
0x1800fe57f  lea     rax, [rsp+0E8h+var_B8]
0x1800fe584  mov     [rsp+0E8h+var_98], rax
0x1800fe589  lea     rax, [rsp+0E8h+var_48]
0x1800fe591  mov     [rsp+0E8h+var_90], rax
0x1800fe596  mov     r14b, 1
0x1800fe599  mov     [rsp+0E8h+var_88], r14b
0x1800fe59e  mov     rcx, [rdi+18h]; this
0x1800fe5a2  test    rcx, rcx
0x1800fe5a5  jz      short loc_1800FE5F2
0x1800fe5a7  call    ?Delete@CCertificate@@QEAAXXZ; CCertificate::Delete(void)
0x1800fe5ac  mov     eax, cs:dword_180155A70
0x1800fe5b2  cmp     eax, 5
0x1800fe5b5  jbe     short loc_1800FE5E0
0x1800fe5b7  lea     rax, aDeletedPfxcert; "Deleted PfxCertificate from Certificate"...
0x1800fe5be  mov     qword ptr [rsp+0E8h+var_A8.wYear], rax
0x1800fe5c3  lea     rax, [rsp+0E8h+var_A8]
0x1800fe5c8  mov     qword ptr [rsp+0E8h+var_C8], rax; unsigned int
0x1800fe5cd  lea     rdx, unk_18013BD40
0x1800fe5d4  lea     rcx, dword_180155A70
0x1800fe5db  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800fe5e0  mov     rdx, [rdi+18h]
0x1800fe5e4  mov     [rdi+18h], rbx
0x1800fe5e8  test    rdx, rdx
0x1800fe5eb  jz      short loc_1800FE5F2
0x1800fe5ed  call    ??R?$default_delete@VPFXCertificate@@@std@@QEBAXPEAVPFXCertificate@@@Z; std::default_delete<PFXCertificate>::operator()(PFXCertificate *)
0x1800fe5f2  mov     [rsp+0E8h+hKey], rbx
0x1800fe5f7  lea     rax, [rsp+0E8h+hKey]
0x1800fe5fc  mov     qword ptr [rsp+0E8h+var_68.wYear], rax
0x1800fe604  mov     qword ptr [rsp+0E8h+var_68.wHour], rbx
0x1800fe60c  mov     [rsp+0E8h+var_58], 1
0x1800fe614  lea     rdx, [rsp+0E8h+var_A8]
0x1800fe619  mov     rcx, [rdi+8]
0x1800fe61d  call    ?GetLocation@CCertificateStore@@QEAA?AV?$shared_ptr@VCCertificateLocation@@@std@@XZ; CCertificateStore::GetLocation(void)
0x1800fe622  lea     r8, [rsp+0E8h+var_68.wHour]
0x1800fe62a  mov     edx, 0F003Fh
0x1800fe62f  mov     rcx, rax
0x1800fe632  call    ?OpenRegkeyCurrentUserOrLocalMachine@PFXCertificate@@KAJV?$shared_ptr@VCCertificateLocation@@@std@@KPEAPEAUHKEY__@@@Z; PFXCertificate::OpenRegkeyCurrentUserOrLocalMachine(std::shared_ptr<CCertificateLocation>,ulong,HKEY__ * *)
0x1800fe637  mov     esi, eax
0x1800fe639  lea     rcx, [rsp+0E8h+var_68]
0x1800fe641  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800fe646  test    esi, esi
0x1800fe648  jns     short loc_1800FE688
0x1800fe64a  mov     rcx, [rsp+0E8h]; this
0x1800fe652  mov     r9d, esi; char *
0x1800fe655  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800fe65c  mov     edx, 2F0h; void *
0x1800fe661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe666  nop
0x1800fe667  lea     rcx, [rsp+0E8h+hKey]
0x1800fe66c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fe671  nop
0x1800fe672  mov     [rsp+0E8h+var_88], bl
0x1800fe676  lea     rcx, [rsp+0E8h+var_98]
0x1800fe67b  call    _lambda_cfab9f70d7a8e493a5e53381049fea42___operator__
0x1800fe680  nop
0x1800fe681  mov     eax, esi
0x1800fe683  jmp     loc_1800FE7D1
0x1800fe688  lea     rdx, [rsp+0E8h+var_68]
0x1800fe690  mov     rcx, rdi
0x1800fe693  call    ?GetFriendlyNameRegistryPath@PFXCertificate@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; PFXCertificate::GetFriendlyNameRegistryPath(void)
0x1800fe698  cmp     qword ptr [rax+18h], 7
0x1800fe69d  jbe     short loc_1800FE6A2
0x1800fe69f  mov     rax, [rax]
0x1800fe6a2  mov     rdx, rax; lpSubKey
0x1800fe6a5  mov     rcx, [rsp+0E8h+hKey]; hKey
0x1800fe6aa  call    cs:__imp_RegDeleteKeyW
0x1800fe6b1  nop     dword ptr [rax+rax+00h]
0x1800fe6b6  mov     edi, eax
0x1800fe6b8  lea     rcx, [rsp+0E8h+var_68]
0x1800fe6c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800fe6c5  test    edi, edi
0x1800fe6c7  jz      short loc_1800FE708
0x1800fe6c9  mov     rcx, [rsp+0E8h]; this
0x1800fe6d1  mov     r9d, edi; char *
0x1800fe6d4  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800fe6db  mov     edx, 2F3h; void *
0x1800fe6e0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fe6e5  mov     edi, eax
0x1800fe6e7  lea     rcx, [rsp+0E8h+hKey]
0x1800fe6ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fe6f1  nop
0x1800fe6f2  mov     [rsp+0E8h+var_88], bl
0x1800fe6f6  lea     rcx, [rsp+0E8h+var_98]
0x1800fe6fb  call    _lambda_cfab9f70d7a8e493a5e53381049fea42___operator__
0x1800fe700  nop
0x1800fe701  mov     eax, edi
0x1800fe703  jmp     loc_1800FE7D1
0x1800fe708  mov     eax, cs:dword_180155A70
0x1800fe70e  cmp     eax, 5
0x1800fe711  jbe     short loc_1800FE73D
0x1800fe713  lea     rax, aDeletedPfxcert_0; "Deleted PfxCertificate from Registry"
0x1800fe71a  mov     qword ptr [rsp+0E8h+var_A8.wYear], rax
0x1800fe71f  lea     rax, [rsp+0E8h+var_A8]
0x1800fe724  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1800fe729  lea     rdx, byte_18013BD95
0x1800fe730  lea     rcx, dword_180155A70
0x1800fe737  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800fe73c  nop
0x1800fe73d  lea     rcx, [rsp+0E8h+hKey]
0x1800fe742  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fe747  nop
0x1800fe748  jmp     short loc_1800FE7B6
0x1800fe74a  xor     ebx, ebx
0x1800fe74c  cmp     [rsp+0E8h+var_88], bl
0x1800fe750  jz      short loc_1800FE7A9
0x1800fe752  xorps   xmm0, xmm0
0x1800fe755  movups  xmmword ptr [rsp+0E8h+SystemTime.wYear], xmm0
0x1800fe75a  lea     rcx, [rsp+0E8h+SystemTime]; lpSystemTime
0x1800fe75f  call    cs:__imp_GetSystemTime
0x1800fe766  nop     dword ptr [rax+rax+00h]
0x1800fe76b  call    ?GetLogger@CCertStoreLogger@@SAPEAV1@XZ; CCertStoreLogger::GetLogger(void)
0x1800fe770  movaps  xmm0, xmmword ptr [rsp+0E8h+SystemTime.wYear]
0x1800fe775  movdqa  xmmword ptr [rsp+0E8h+var_A8.wYear], xmm0
0x1800fe77b  mov     rcx, [rsp+0E8h+var_90]
0x1800fe780  movups  xmm1, xmmword ptr [rcx]
0x1800fe783  movdqu  xmmword ptr [rsp+0E8h+var_68.wYear], xmm1
0x1800fe78c  lea     r9, [rsp+0E8h+var_A8]; struct _SYSTEMTIME
0x1800fe791  lea     r8, [rsp+0E8h+var_68]; struct _SYSTEMTIME
0x1800fe799  mov     rdx, [rsp+0E8h+var_98]
0x1800fe79e  mov     dl, [rdx]; bool
0x1800fe7a0  mov     rcx, rax; this
0x1800fe7a3  call    ?LogDeletePfxCertificateStatus@CCertStoreLogger@@QEAAX_NU_SYSTEMTIME@@1@Z; CCertStoreLogger::LogDeletePfxCertificateStatus(bool,_SYSTEMTIME,_SYSTEMTIME)
0x1800fe7a8  nop
0x1800fe7a9  mov     eax, dword ptr [rsp+0E8h+hKey]
0x1800fe7ad  jmp     short loc_1800FE7D1
0x1800fe7af  xor     ebx, ebx
0x1800fe7b1  mov     r14b, [rsp+0E8h+var_88]
0x1800fe7b6  mov     [rsp+0E8h+var_B8], 1
0x1800fe7bb  test    r14b, r14b
0x1800fe7be  jz      short loc_1800FE7CF
0x1800fe7c0  mov     [rsp+0E8h+var_88], bl
0x1800fe7c4  lea     rcx, [rsp+0E8h+var_98]
0x1800fe7c9  call    _lambda_cfab9f70d7a8e493a5e53381049fea42___operator__
0x1800fe7ce  nop
0x1800fe7cf  xor     eax, eax
0x1800fe7d1  mov     rcx, [rsp+0E8h+var_38]
0x1800fe7d9  xor     rcx, rsp; StackCookie
0x1800fe7dc  call    __security_check_cookie
0x1800fe7e1  add     rsp, 0C8h
0x1800fe7e8  pop     r14
0x1800fe7ea  pop     rdi
0x1800fe7eb  pop     rsi
0x1800fe7ec  pop     rbx
0x1800fe7ed  retn
```

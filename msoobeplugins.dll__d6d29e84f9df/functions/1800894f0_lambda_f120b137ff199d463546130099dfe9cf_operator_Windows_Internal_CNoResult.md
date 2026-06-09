# _lambda_f120b137ff199d463546130099dfe9cf_::operator()(Windows::Internal::CNoResult &)

- ea: `0x1800894f0`
- end: `0x1800896bb`
- name: `??R_lambda_f120b137ff199d463546130099dfe9cf_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008a930`

## callees

- `0x180008544`
- `0x18001ad08`
- `0x18001ea00`
- `0x1800230b0`
- `0x1800235c8`
- `0x180053e5c`
- `0x18005cf54`
- `0x18007fb9c`
- `0x1800894f0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180089663`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180089663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089647`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800895d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180089606`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800895d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180089606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800895aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800895aa`

## string_xrefs

- `0x18008955f`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x1800895bb`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x1800895ea`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089629`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089690`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x1800895fb`: `MachineLanguageConfiguration`
- `0x18008959c`: `Control Panel\Desktop\MuiCached`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_f120b137ff199d463546130099dfe9cf_::operator()(unsigned __int16 *a1, __int64 a2)
{
  void *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  int v9; // eax
  const WCHAR *StringRawBuffer; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  int v14; // eax
  int phkResult; // [rsp+20h] [rbp-10h]
  int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  __int64 LCData; // [rsp+58h] [rbp+28h] BYREF
  void *v21; // [rsp+60h] [rbp+30h] BYREF

  LCData = a2;
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
    &v21,
    a1 + 4);
  v3 = v21;
  if ( v21 )
  {
LABEL_5:
    v4 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, *a1);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 418;
      goto LABEL_7;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop\\MuiCached", 0, 2u, &hKey);
    if ( v7 >= 0 )
    {
      v8 = RegDeleteValueW(hKey, L"MachinePreferredUILanguages");
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
      RegDeleteValueW(hKey, L"MachineLanguageConfiguration");
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)(unsigned int)v7,
        phkResulta);
    }
    v9 = (*((__int64 (__fastcall **)(__int64, _QWORD))a1 + 4))(59, *((_QWORD *)a1 + 2));
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)(unsigned int)v9,
        phkResulta);
    LODWORD(LCData) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a1 + 2), 0);
    if ( GetLocaleInfoEx(StringRawBuffer, 0x2000005Bu, (LPWSTR)&LCData, 2) > 0 )
    {
      v14 = (*((__int64 (__fastcall **)(_QWORD))a1 + 5))((unsigned int)LCData);
      v13 = retaddr;
      if ( v14 )
      {
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v5 = 0;
        goto LABEL_21;
      }
      v12 = 442;
    }
    else
    {
      v12 = 440;
      v13 = retaddr;
    }
    wil::details::in1diag3::_Log_GetLastError(
      v13,
      (void *)v12,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
      v11);
    goto LABEL_20;
  }
  v21 = 0;
  v4 = CloudExperienceHostCreateElevatedObject(
         &GUID_9a31d292_655f_48f7_b5ad_553358bcd0c9,
         &GUID_dfd8d554_f9ba_4a87_b3d9_4f7acd3a3f3a,
         &v21);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v3 = v21;
    goto LABEL_5;
  }
  v6 = 416;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
    (const char *)(unsigned int)v4,
    phkResult);
LABEL_21:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v21);
  return v5;
}

```

## disassembly

```asm
0x1800894f0  mov     [rsp-18h+LCData], rdx
0x1800894f5  push    rbp
0x1800894f6  push    rbx
0x1800894f7  push    rdi
0x1800894f8  mov     rbp, rsp
0x1800894fb  sub     rsp, 30h
0x1800894ff  mov     rdi, rcx
0x180089502  lea     rdx, [rcx+8]
0x180089506  lea     rcx, [rbp+arg_10]
0x18008950a  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x18008950f  nop
0x180089510  mov     rcx, [rbp+arg_10]
0x180089514  test    rcx, rcx
0x180089517  jnz     short loc_180089545
0x180089519  mov     [rbp+arg_10], rcx
0x18008951d  lea     r8, [rbp+arg_10]; void **
0x180089521  lea     rdx, _GUID_dfd8d554_f9ba_4a87_b3d9_4f7acd3a3f3a; struct _GUID *
0x180089528  lea     rcx, _GUID_9a31d292_655f_48f7_b5ad_553358bcd0c9; struct _GUID *
0x18008952f  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x180089534  mov     ebx, eax
0x180089536  test    eax, eax
0x180089538  jns     short loc_180089541
0x18008953a  mov     edx, 1A0h
0x18008953f  jmp     short loc_18008955F
0x180089541  mov     rcx, [rbp+arg_10]
0x180089545  mov     rax, [rcx]
0x180089548  movzx   edx, word ptr [rdi]
0x18008954b  mov     rax, [rax+30h]
0x18008954f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089554  mov     ebx, eax
0x180089556  test    eax, eax
0x180089558  jns     short loc_180089577
0x18008955a  mov     edx, 1A2h; void *
0x18008955f  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089566  mov     r9d, eax; char *
0x180089569  mov     rcx, [rbp+18h]; this
0x18008956d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089572  jmp     loc_1800896A8
0x180089577  mov     [rbp+hKey], 0
0x18008957f  xor     edx, edx
0x180089581  lea     rcx, [rbp+hKey]
0x180089585  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008958a  lea     rax, [rbp+hKey]
0x18008958e  mov     qword ptr [rsp+30h+phkResult], rax; int
0x180089593  mov     r9d, 2; samDesired
0x180089599  xor     r8d, r8d; ulOptions
0x18008959c  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x1800895a3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800895aa  call    cs:__imp_RegOpenKeyExW
0x1800895b0  mov     rcx, [rbp+18h]; this
0x1800895b4  test    eax, eax
0x1800895b6  jns     short loc_1800895CE
0x1800895b8  mov     r9d, eax; char *
0x1800895bb  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800895c2  mov     edx, 1A6h; void *
0x1800895c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800895cc  jmp     short loc_18008960C
0x1800895ce  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x1800895d5  mov     rcx, [rbp+hKey]; hKey
0x1800895d9  call    cs:__imp_RegDeleteValueW
0x1800895df  mov     rcx, [rbp+18h]; this
0x1800895e3  test    eax, eax
0x1800895e5  jns     short loc_1800895FB
0x1800895e7  mov     r9d, eax; char *
0x1800895ea  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800895f1  mov     edx, 1A8h; void *
0x1800895f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800895fb  lea     rdx, aMachinelanguag; "MachineLanguageConfiguration"
0x180089602  mov     rcx, [rbp+hKey]; hKey
0x180089606  call    cs:__imp_RegDeleteValueW
0x18008960c  mov     ecx, 3Bh ; ';'
0x180089611  mov     rdx, [rdi+10h]
0x180089615  mov     rax, [rdi+20h]
0x180089619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008961e  mov     rcx, [rbp+18h]; this
0x180089622  test    eax, eax
0x180089624  jns     short loc_18008963A
0x180089626  mov     r9d, eax; char *
0x180089629  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089630  mov     edx, 1B1h; void *
0x180089635  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008963a  mov     dword ptr [rbp+LCData], 0
0x180089641  xor     edx, edx; length
0x180089643  mov     rcx, [rdi+10h]; string
0x180089647  call    cs:__imp_WindowsGetStringRawBuffer
0x18008964d  mov     rbx, [rbp+18h]
0x180089651  mov     r9d, 2; cchData
0x180089657  lea     r8, [rbp+LCData]; lpLCData
0x18008965b  mov     edx, 2000005Bh; LCType
0x180089660  mov     rcx, rax; lpLocaleName
0x180089663  call    cs:__imp_GetLocaleInfoEx
0x180089669  test    eax, eax
0x18008966b  jg      short loc_180089677
0x18008966d  mov     edx, 1B8h
0x180089672  mov     rcx, rbx
0x180089675  jmp     short loc_180089690
0x180089677  mov     ecx, dword ptr [rbp+LCData]
0x18008967a  mov     rax, [rdi+28h]
0x18008967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089683  mov     rcx, [rbp+18h]; this
0x180089687  test    eax, eax
0x180089689  jnz     short loc_18008969D
0x18008968b  mov     edx, 1BAh; void *
0x180089690  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089697  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008969c  nop
0x18008969d  lea     rcx, [rbp+hKey]
0x1800896a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800896a6  xor     ebx, ebx
0x1800896a8  lea     rcx, [rbp+arg_10]
0x1800896ac  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800896b1  mov     eax, ebx
0x1800896b3  add     rsp, 30h
0x1800896b7  pop     rdi
0x1800896b8  pop     rbx
0x1800896b9  pop     rbp
0x1800896ba  retn
```

# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetLinkedEnrollmentId(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18012ad58`
- end: `0x18012af4f`
- name: `?GetLinkedEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012e790`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ef8c4`
- `0x180105294`
- `0x18011273c`
- `0x18012a388`
- `0x18012ad58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ae1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ae85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ae1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ae85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012addc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ae4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012addc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ae4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012aeea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012aeea`

## string_xrefs

- `0x18012aede`: `LinkedEnrollment`
- `0x18012aed7`: `LinkedEnrollmentId`
- `0x18012aea4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetLinkedEnrollmentId(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v5; // rax
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  hKey = 0;
  hkey = 0;
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v14);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
  }
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath();
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  if ( ValueW )
  {
    v7 = 163;
  }
  else
  {
    if ( hkey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      RegCloseKey(hkey);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
    }
    hkey = 0;
    ValueW = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hkey);
    if ( !ValueW )
    {
      ValueW = RegGetValueW(hkey, L"LinkedEnrollment", L"LinkedEnrollmentId", 2u, 0, pvData, &pcbData);
      if ( ValueW != 2 )
      {
        if ( ValueW )
        {
          v7 = 171;
          goto LABEL_9;
        }
        std::wstring::assign(a3, pvData);
      }
      v8 = 0;
      goto LABEL_15;
    }
    v7 = 164;
  }
LABEL_9:
  v8 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v7,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
         (const char *)ValueW,
         phkResult);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18012ad58  mov     [rsp-8+arg_0], rbx
0x18012ad5d  push    rbp
0x18012ad5e  push    rsi
0x18012ad5f  push    rdi
0x18012ad60  lea     rbp, [rsp-180h]
0x18012ad68  sub     rsp, 280h
0x18012ad6f  mov     rax, cs:__security_cookie
0x18012ad76  xor     rax, rsp
0x18012ad79  mov     [rbp+190h+var_20], rax
0x18012ad80  mov     rdi, r8
0x18012ad83  mov     rsi, rdx
0x18012ad86  mov     [rsp+290h+hKey], 0
0x18012ad8f  mov     [rsp+290h+hkey], 0
0x18012ad98  mov     ebx, 208h
0x18012ad9d  mov     r8d, ebx; Size
0x18012ada0  xor     edx, edx; Val
0x18012ada2  lea     rcx, [rsp+290h+var_230]; void *
0x18012ada7  call    memset_0
0x18012adac  mov     [rsp+290h+var_240], ebx
0x18012adb0  mov     qword ptr [rdi+10h], 0
0x18012adb8  mov     rcx, rdi
0x18012adbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012adc0  xor     ecx, ecx
0x18012adc2  mov     [rax], cx
0x18012adc5  mov     rbx, [rsp+290h+hKey]
0x18012adca  test    rbx, rbx
0x18012adcd  jz      short loc_18012ADF2
0x18012adcf  lea     rcx, [rsp+290h+var_238]; this
0x18012add4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012add9  mov     rcx, rbx; hKey
0x18012addc  call    cs:__imp_RegCloseKey
0x18012ade3  nop     dword ptr [rax+rax+00h]
0x18012ade8  lea     rcx, [rsp+290h+var_238]; this
0x18012aded  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012adf2  mov     [rsp+290h+hKey], 0
0x18012adfb  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18012ae00  lea     rcx, [rsp+290h+hKey]
0x18012ae05  mov     [rsp+290h+phkResult], rcx; phkResult
0x18012ae0a  mov     r9d, 20019h; samDesired
0x18012ae10  xor     r8d, r8d; ulOptions
0x18012ae13  mov     rdx, rax; lpSubKey
0x18012ae16  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012ae1d  call    cs:__imp_RegOpenKeyExW
0x18012ae24  nop     dword ptr [rax+rax+00h]
0x18012ae29  test    eax, eax
0x18012ae2b  jz      short loc_18012AE34
0x18012ae2d  mov     edx, 0A3h
0x18012ae32  jmp     short loc_18012AE9A
0x18012ae34  mov     rbx, [rsp+290h+hkey]
0x18012ae39  test    rbx, rbx
0x18012ae3c  jz      short loc_18012AE61
0x18012ae3e  lea     rcx, [rsp+290h+var_238]; this
0x18012ae43  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012ae48  mov     rcx, rbx; hKey
0x18012ae4b  call    cs:__imp_RegCloseKey
0x18012ae52  nop     dword ptr [rax+rax+00h]
0x18012ae57  lea     rcx, [rsp+290h+var_238]; this
0x18012ae5c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012ae61  mov     [rsp+290h+hkey], 0
0x18012ae6a  lea     rax, [rsp+290h+hkey]
0x18012ae6f  mov     [rsp+290h+phkResult], rax; unsigned int
0x18012ae74  mov     r9d, 20019h; samDesired
0x18012ae7a  xor     r8d, r8d; ulOptions
0x18012ae7d  mov     rdx, rsi; lpSubKey
0x18012ae80  mov     rcx, [rsp+290h+hKey]; hKey
0x18012ae85  call    cs:__imp_RegOpenKeyExW
0x18012ae8c  nop     dword ptr [rax+rax+00h]
0x18012ae91  test    eax, eax
0x18012ae93  jz      short loc_18012AEB4
0x18012ae95  mov     edx, 0A4h; void *
0x18012ae9a  mov     rcx, [rbp+198h]; this
0x18012aea1  mov     r9d, eax; char *
0x18012aea4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012aeab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18012aeb0  mov     ebx, eax
0x18012aeb2  jmp     short loc_18012AF15
0x18012aeb4  lea     rax, [rsp+290h+var_240]
0x18012aeb9  mov     [rsp+290h+pcbData], rax; pcbData
0x18012aebe  lea     rax, [rsp+290h+var_230]
0x18012aec3  mov     [rsp+290h+pvData], rax; pvData
0x18012aec8  mov     [rsp+290h+phkResult], 0; pdwType
0x18012aed1  mov     r9d, 2; dwFlags
0x18012aed7  lea     r8, aLinkedenrollme_1; "LinkedEnrollmentId"
0x18012aede  lea     rdx, aLinkedenrollme; "LinkedEnrollment"
0x18012aee5  mov     rcx, [rsp+290h+hkey]; hkey
0x18012aeea  call    cs:__imp_RegGetValueW
0x18012aef1  nop     dword ptr [rax+rax+00h]
0x18012aef6  cmp     eax, 2
0x18012aef9  jz      short loc_18012AF13
0x18012aefb  test    eax, eax
0x18012aefd  jz      short loc_18012AF06
0x18012aeff  mov     edx, 0ABh
0x18012af04  jmp     short loc_18012AE9A
0x18012af06  lea     rdx, [rsp+290h+var_230]
0x18012af0b  mov     rcx, rdi
0x18012af0e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012af13  xor     ebx, ebx
0x18012af15  lea     rcx, [rsp+290h+hkey]
0x18012af1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012af1f  nop
0x18012af20  lea     rcx, [rsp+290h+hKey]
0x18012af25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012af2a  mov     eax, ebx
0x18012af2c  mov     rcx, [rbp+190h+var_20]
0x18012af33  xor     rcx, rsp; StackCookie
0x18012af36  call    __security_check_cookie
0x18012af3b  mov     rbx, [rsp+290h+arg_0]
0x18012af43  add     rsp, 280h
0x18012af4a  pop     rdi
0x18012af4b  pop     rsi
0x18012af4c  pop     rbp
0x18012af4d  retn
```

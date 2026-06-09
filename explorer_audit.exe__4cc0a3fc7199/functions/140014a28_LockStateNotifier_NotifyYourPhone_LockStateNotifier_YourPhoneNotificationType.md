# LockStateNotifier::NotifyYourPhone(LockStateNotifier::YourPhoneNotificationType)

- ea: `0x140014a28`
- end: `0x140014ebb`
- name: `?NotifyYourPhone@LockStateNotifier@@YAJW4YourPhoneNotificationType@1@@Z`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001d860`

## callees

- `0x140014a28`
- `0x1400158a4`
- `0x14002f838`
- `0x1400954e0`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014bbf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014e3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014e73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014bbf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014e3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014e73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014abd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140014abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140014c19`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140014d29`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140014d29`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140014b64`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140014c38`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140014b64`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140014c38`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x140014b07`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x140014b07`

## string_xrefs

- `0x140014a53`: `UserPresenceAppServiceSignalsCapable`
- `0x140014b3e`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LockStateNotifier::NotifyYourPhone(int a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  LSTATUS ValueW; // eax
  bool v5; // sf
  LONG PackagesByPackageFamily; // eax
  const WCHAR *v7; // rdi
  int ActivationFactory; // eax
  int v10; // eax
  HRESULT StringReference; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  bool v15; // sf
  int v16; // eax
  bool v17; // sf
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, HSTRING, DWORD *); // r14
  unsigned __int64 v20; // rbx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD bufferLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 count[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v2 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Mobility\\%ws",
         L"UserPresenceAppServiceSignalsCapable");
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v2,
      pdwType);
    return v3;
  }
  count[0] = 0;
  bufferLength[0] = 4;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, SubKey, L"OptedIn", 0x20000010u, 0, count, bufferLength);
  v5 = ValueW < 0;
  if ( ValueW > 0 )
    v5 = 1;
  if ( v5 || !count[0] )
    return 0;
  bufferLength[0] = 0;
  count[0] = 0;
  PackagesByPackageFamily = GetPackagesByPackageFamily(L"Microsoft.YourPhone_8wekyb3d8bbwe", count, 0, bufferLength, 0);
  if ( PackagesByPackageFamily != 122 )
  {
    v15 = PackagesByPackageFamily < 0;
    if ( PackagesByPackageFamily > 0 )
      v15 = 1;
    if ( !v15 )
    {
      bufferLength[0] = 0;
      v16 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"OptedIn", 4u, bufferLength, 4u);
      v17 = v16 < 0;
      if ( v16 > 0 )
      {
        v16 = (unsigned __int16)v16 | 0x80070000;
        v17 = v16 < 0;
      }
      if ( v17 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\MobilityExperienceSettings.h",
          (const char *)(unsigned int)v16,
          pdwTypeb);
      return 0;
    }
  }
  v7 = L"ms-phone-api://event/locked";
  if ( a1 )
    v7 = L"ms-phone-api://event/unlocked";
  *(_QWORD *)count = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, count);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)ActivationFactory,
      pdwTypea);
    if ( *(_QWORD *)count )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)count + 16LL))(*(_QWORD *)count);
    return v3;
  }
  *(_QWORD *)bufferLength = 0;
  v18 = *(_QWORD *)count;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING, DWORD *))(**(_QWORD **)count + 48LL);
  *(_QWORD *)bufferLength = 0;
  v20 = -1;
  do
    ++v20;
  while ( v7[v20] );
  if ( v20 > 0xFFFFFFFF )
  {
    LODWORD(v20) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v7, v20, &hstringHeader, &string);
  v10 = v19(v18, string, bufferLength);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v10,
      pdwTypea);
LABEL_52:
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(bufferLength);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(count);
    return v3;
  }
  v26 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.System.Launcher",
                      0x17u,
                      (HSTRING_HEADER *)&string,
                      (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v12 = RoGetActivationFactory(
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
          &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451,
          &v26);
  v3 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v12,
      pdwTypea);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v26);
    goto LABEL_52;
  }
  v27 = 0;
  v13 = *v26;
  v27 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v13 + 64))(v26, *(_QWORD *)bufferLength, &v27);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v14,
      pdwTypea);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v26 )
      (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    if ( *(_QWORD *)bufferLength )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bufferLength + 16LL))(*(_QWORD *)bufferLength);
    if ( *(_QWORD *)count )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)count + 16LL))(*(_QWORD *)count);
    return v3;
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v26 )
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  if ( *(_QWORD *)bufferLength )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bufferLength + 16LL))(*(_QWORD *)bufferLength);
  if ( *(_QWORD *)count )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)count + 16LL))(*(_QWORD *)count);
  return 0;
}

```

## disassembly

```asm
0x140014a28  push    rbp
0x140014a2a  push    rbx
0x140014a2b  push    rsi
0x140014a2c  push    rdi
0x140014a2d  push    r14
0x140014a2f  push    r15
0x140014a31  lea     rbp, [rsp-1A8h]
0x140014a39  sub     rsp, 2A8h
0x140014a40  mov     rax, cs:__security_cookie
0x140014a47  xor     rax, rsp
0x140014a4a  mov     [rbp+1D0h+var_40], rax
0x140014a51  mov     esi, ecx
0x140014a53  lea     r9, aUserpresenceap; "UserPresenceAppServiceSignalsCapable"
0x140014a5a  lea     r8, ?c_regKeyMobilityResource@MobilityExperienceSettings@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140014a61  mov     edx, 104h; unsigned __int64
0x140014a66  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x140014a6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014a6f  mov     ebx, eax
0x140014a71  xor     r15d, r15d
0x140014a74  test    eax, eax
0x140014a76  js      loc_140014D5C
0x140014a7c  mov     [rsp+2D0h+count], r15d
0x140014a81  lea     edi, [r15+4]
0x140014a85  mov     [rsp+2D0h+bufferLength], edi
0x140014a89  lea     rax, [rsp+2D0h+bufferLength]
0x140014a8e  mov     [rsp+2D0h+pcbData], rax; pcbData
0x140014a93  lea     rax, [rsp+2D0h+count]
0x140014a98  mov     [rsp+2D0h+pvData], rax; pvData
0x140014a9d  mov     [rsp+2D0h+pdwType], r15; pdwType
0x140014aa2  mov     r9d, 20000010h; dwFlags
0x140014aa8  lea     r8, ?c_regValueOptedIn@MobilityExperienceSettings@CreativeFramework@@3QBGB; "OptedIn"
0x140014aaf  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x140014ab3  mov     r14, 0FFFFFFFF80000001h
0x140014aba  mov     rcx, r14; hkey
0x140014abd  call    cs:__imp_RegGetValueW
0x140014ac3  mov     ebx, 80070000h
0x140014ac8  test    eax, eax
0x140014aca  jle     short loc_140014AD3
0x140014acc  movzx   eax, ax
0x140014acf  or      eax, ebx
0x140014ad1  test    eax, eax
0x140014ad3  js      loc_140014CD3
0x140014ad9  cmp     [rsp+2D0h+count], r15d
0x140014ade  jz      loc_140014CD3
0x140014ae4  mov     [rsp+2D0h+bufferLength], r15d
0x140014ae9  mov     [rsp+2D0h+count], r15d
0x140014aee  mov     [rsp+2D0h+pdwType], r15; int
0x140014af3  lea     r9, [rsp+2D0h+bufferLength]; bufferLength
0x140014af8  xor     r8d, r8d; packageFullNames
0x140014afb  lea     rdx, [rsp+2D0h+count]; count
0x140014b00  lea     rcx, ?c_yourPhonePackageFamilyName@MobilityExperienceSettings@CreativeFramework@@3QBGB; "Microsoft.YourPhone_8wekyb3d8bbwe"
0x140014b07  call    cs:__imp_GetPackagesByPackageFamily
0x140014b0d  cmp     eax, 7Ah ; 'z'
0x140014b10  jnz     loc_140014CF4
0x140014b16  lea     rax, sourceString; "ms-phone-api://event/unlocked"
0x140014b1d  lea     rdi, aMsPhoneApiEven; "ms-phone-api://event/locked"
0x140014b24  test    esi, esi
0x140014b26  cmovnz  rdi, rax
0x140014b2a  mov     qword ptr [rsp+2D0h+count], r15
0x140014b2f  lea     r9, [rsp+2D0h+string]; string
0x140014b34  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x140014b39  mov     edx, 16h; length
0x140014b3e  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x140014b45  call    cs:__imp_WindowsCreateStringReference
0x140014b4b  test    eax, eax
0x140014b4d  js      loc_140014E30
0x140014b53  lea     r8, [rsp+2D0h+count]
0x140014b58  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x140014b5f  mov     rcx, [rsp+2D0h+string]
0x140014b64  call    cs:__imp_RoGetActivationFactory
0x140014b6a  mov     ebx, eax
0x140014b6c  test    eax, eax
0x140014b6e  jns     loc_140014D7C
0x140014b74  mov     rcx, [rbp+1D8h]; this
0x140014b7b  mov     r9d, eax; char *
0x140014b7e  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x140014b85  mov     edx, 30h ; '0'; void *
0x140014b8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014b8f  nop
0x140014b90  mov     rcx, qword ptr [rsp+2D0h+count]
0x140014b95  test    rcx, rcx
0x140014b98  jz      short loc_140014BA7
0x140014b9a  mov     rax, [rcx]
0x140014b9d  mov     rax, [rax+10h]
0x140014ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ba6  nop
0x140014ba7  mov     eax, ebx
0x140014ba9  jmp     loc_140014CD5
0x140014bae  mov     ebx, eax
0x140014bb0  xor     r9d, r9d; lpArguments
0x140014bb3  xor     r8d, r8d; nNumberOfArguments
0x140014bb6  lea     edx, [r9+1]; dwExceptionFlags
0x140014bba  mov     ecx, 0C000000Dh; dwExceptionCode
0x140014bbf  call    cs:__imp_RaiseException
0x140014bc5  lea     r9, [rsp+2D0h+string]; string
0x140014bca  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x140014bcf  mov     edx, ebx; length
0x140014bd1  mov     rcx, rdi; sourceString
0x140014bd4  call    cs:__imp_WindowsCreateStringReference
0x140014bda  lea     r8, [rsp+2D0h+bufferLength]
0x140014bdf  mov     rdx, [rsp+2D0h+string]
0x140014be4  mov     rcx, rsi
0x140014be7  mov     rax, r14
0x140014bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014bef  mov     ebx, eax
0x140014bf1  test    eax, eax
0x140014bf3  js      loc_140014E4A
0x140014bf9  mov     [rsp+2D0h+var_280], r15
0x140014bfe  mov     qword ptr [rsp+2D0h+hstringHeader.Reserved+10h], r15
0x140014c03  lea     r9, [rsp+2D0h+hstringHeader.Reserved+10h]; string
0x140014c08  lea     r8, [rsp+2D0h+string]; hstringHeader
0x140014c0d  mov     edx, 17h; length
0x140014c12  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x140014c19  call    cs:__imp_WindowsCreateStringReference
0x140014c1f  test    eax, eax
0x140014c21  js      loc_140014E67
0x140014c27  lea     r8, [rsp+2D0h+var_280]
0x140014c2c  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x140014c33  mov     rcx, qword ptr [rsp+2D0h+hstringHeader.Reserved+10h]
0x140014c38  call    cs:__imp_RoGetActivationFactory
0x140014c3e  mov     ebx, eax
0x140014c40  test    eax, eax
0x140014c42  js      loc_140014E7A
0x140014c48  mov     [rsp+2D0h+var_278], r15
0x140014c4d  mov     rcx, [rsp+2D0h+var_280]
0x140014c52  mov     rax, [rcx]
0x140014c55  mov     [rsp+2D0h+var_278], r15
0x140014c5a  lea     r8, [rsp+2D0h+var_278]
0x140014c5f  mov     rdx, qword ptr [rsp+2D0h+bufferLength]
0x140014c64  mov     rax, [rax+40h]
0x140014c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c6d  mov     ebx, eax
0x140014c6f  test    eax, eax
0x140014c71  js      loc_140014DB3
0x140014c77  mov     rcx, [rsp+2D0h+var_278]
0x140014c7c  test    rcx, rcx
0x140014c7f  jz      short loc_140014C8E
0x140014c81  mov     rax, [rcx]
0x140014c84  mov     rax, [rax+10h]
0x140014c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c8d  nop
0x140014c8e  mov     rcx, [rsp+2D0h+var_280]
0x140014c93  test    rcx, rcx
0x140014c96  jz      short loc_140014CA5
0x140014c98  mov     rax, [rcx]
0x140014c9b  mov     rax, [rax+10h]
0x140014c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ca4  nop
0x140014ca5  mov     rcx, qword ptr [rsp+2D0h+bufferLength]
0x140014caa  test    rcx, rcx
0x140014cad  jz      short loc_140014CBC
0x140014caf  mov     rax, [rcx]
0x140014cb2  mov     rax, [rax+10h]
0x140014cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014cbb  nop
0x140014cbc  mov     rcx, qword ptr [rsp+2D0h+count]
0x140014cc1  test    rcx, rcx
0x140014cc4  jz      short loc_140014CD3
0x140014cc6  mov     rax, [rcx]
0x140014cc9  mov     rax, [rax+10h]
0x140014ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014cd2  nop
0x140014cd3  xor     eax, eax
0x140014cd5  mov     rcx, [rbp+1D0h+var_40]
0x140014cdc  xor     rcx, rsp; StackCookie
0x140014cdf  call    __security_check_cookie
0x140014ce4  add     rsp, 2A8h
0x140014ceb  pop     r15
0x140014ced  pop     r14
0x140014cef  pop     rdi
0x140014cf0  pop     rsi
0x140014cf1  pop     rbx
0x140014cf2  pop     rbp
0x140014cf3  retn
0x140014cf4  test    eax, eax
0x140014cf6  jle     short loc_140014CFF
0x140014cf8  movzx   eax, ax
0x140014cfb  or      eax, ebx
0x140014cfd  test    eax, eax
0x140014cff  js      loc_140014B16
0x140014d05  mov     [rsp+2D0h+bufferLength], r15d
0x140014d0a  mov     dword ptr [rsp+2D0h+pvData], edi; cbData
0x140014d0e  lea     rax, [rsp+2D0h+bufferLength]
0x140014d13  mov     [rsp+2D0h+pdwType], rax; int
0x140014d18  mov     r9d, edi; dwType
0x140014d1b  lea     r8, ?c_regValueOptedIn@MobilityExperienceSettings@CreativeFramework@@3QBGB; "OptedIn"
0x140014d22  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x140014d26  mov     rcx, r14; hKey
0x140014d29  call    cs:__imp_RegSetKeyValueW
0x140014d2f  test    eax, eax
0x140014d31  jle     short loc_140014D3A
0x140014d33  movzx   eax, ax
0x140014d36  or      eax, ebx
0x140014d38  test    eax, eax
0x140014d3a  jns     short loc_140014CD3
0x140014d3c  mov     rcx, [rbp+1D8h]; this
0x140014d43  mov     r9d, eax; char *
0x140014d46  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Mobil"...
0x140014d4d  mov     edx, 2Eh ; '.'; void *
0x140014d52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d57  jmp     loc_140014CD3
0x140014d5c  mov     rcx, [rbp+1D8h]; this
0x140014d63  mov     r9d, ebx; char *
0x140014d66  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x140014d6d  mov     edx, 1Dh; void *
0x140014d72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d77  jmp     loc_140014BA7
0x140014d7c  mov     qword ptr [rsp+2D0h+bufferLength], r15
0x140014d81  mov     rsi, qword ptr [rsp+2D0h+count]
0x140014d86  mov     rax, [rsi]
0x140014d89  mov     r14, [rax+30h]
0x140014d8d  mov     qword ptr [rsp+2D0h+bufferLength], r15
0x140014d92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140014d96  inc     rbx
0x140014d99  cmp     [rdi+rbx*2], r15w
0x140014d9e  jnz     short loc_140014D96
0x140014da0  mov     eax, 0FFFFFFFFh
0x140014da5  cmp     rbx, rax
0x140014da8  jbe     loc_140014BC5
0x140014dae  jmp     loc_140014BAE
0x140014db3  mov     rcx, [rbp+1D8h]; this
0x140014dba  mov     r9d, ebx; char *
0x140014dbd  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x140014dc4  mov     edx, 38h ; '8'; void *
0x140014dc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014dce  nop
0x140014dcf  mov     rcx, [rsp+2D0h+var_278]
0x140014dd4  test    rcx, rcx
0x140014dd7  jz      short loc_140014DE6
0x140014dd9  mov     rax, [rcx]
0x140014ddc  mov     rax, [rax+10h]
0x140014de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014de5  nop
0x140014de6  mov     rcx, [rsp+2D0h+var_280]
0x140014deb  test    rcx, rcx
0x140014dee  jz      short loc_140014DFD
0x140014df0  mov     rax, [rcx]
0x140014df3  mov     rax, [rax+10h]
0x140014df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014dfc  nop
0x140014dfd  mov     rcx, qword ptr [rsp+2D0h+bufferLength]
0x140014e02  test    rcx, rcx
0x140014e05  jz      short loc_140014E14
0x140014e07  mov     rax, [rcx]
0x140014e0a  mov     rax, [rax+10h]
0x140014e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e13  nop
0x140014e14  mov     rcx, qword ptr [rsp+2D0h+count]
0x140014e19  test    rcx, rcx
0x140014e1c  jz      short loc_140014E2B
0x140014e1e  mov     rax, [rcx]
0x140014e21  mov     rax, [rax+10h]
0x140014e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e2a  nop
0x140014e2b  jmp     loc_140014BA7
0x140014e30  xor     r9d, r9d; lpArguments
0x140014e33  xor     r8d, r8d; nNumberOfArguments
0x140014e36  lea     edx, [r9+1]; dwExceptionFlags
0x140014e3a  mov     ecx, 0C000000Dh; dwExceptionCode
0x140014e3f  call    cs:__imp_RaiseException
0x140014e45  jmp     loc_140014B53
0x140014e4a  mov     rcx, [rbp+1D8h]; this
0x140014e51  mov     r9d, eax; char *
0x140014e54  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x140014e5b  mov     edx, 32h ; '2'; void *
0x140014e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014e65  jmp     short loc_140014EA1
0x140014e67  xor     r9d, r9d; lpArguments
0x140014e6a  xor     r8d, r8d; nNumberOfArguments
0x140014e6d  lea     edx, [r9+1]; dwExceptionFlags
0x140014e71  mov     ecx, eax; dwExceptionCode
0x140014e73  call    cs:__imp_RaiseException
0x140014e79  int     3; Trap to Debugger
0x140014e7a  mov     rcx, [rbp+1D8h]; this
0x140014e81  mov     r9d, eax; char *
0x140014e84  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x140014e8b  mov     edx, 36h ; '6'; void *
0x140014e90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014e95  nop
0x140014e96  lea     rcx, [rsp+2D0h+var_280]
0x140014e9b  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x140014ea0  nop
0x140014ea1  lea     rcx, [rsp+2D0h+bufferLength]
0x140014ea6  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x140014eab  nop
0x140014eac  lea     rcx, [rsp+2D0h+count]
0x140014eb1  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x140014eb6  jmp     loc_140014BA7
```

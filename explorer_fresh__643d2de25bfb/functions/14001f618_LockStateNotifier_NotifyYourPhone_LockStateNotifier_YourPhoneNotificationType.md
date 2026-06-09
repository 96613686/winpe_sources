# LockStateNotifier::NotifyYourPhone(LockStateNotifier::YourPhoneNotificationType)

- ea: `0x14001f618`
- end: `0x14001fadd`
- name: `?NotifyYourPhone@LockStateNotifier@@YAJW4YourPhoneNotificationType@1@@Z`
- size: `1221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140019eb0`

## callees

- `0x140005aa8`
- `0x14001f618`
- `0x140020580`
- `0x14009ac68`
- `0x1400baca0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001f7c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001fa66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001f7c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001fa66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001f6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001f6ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f82d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f82d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001f94a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001f94a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f766`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f852`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f766`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001f852`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x14001f6fd`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x14001f6fd`

## string_xrefs

- `0x14001f643`: `UserPresenceAppServiceSignalsCapable`
- `0x14001f73a`: `Windows.Foundation.Uri`

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
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  bool v17; // sf
  int v18; // eax
  bool v19; // sf
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, HSTRING, DWORD *); // r14
  unsigned __int64 v22; // rbx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD bufferLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 count[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
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
    v17 = PackagesByPackageFamily < 0;
    if ( PackagesByPackageFamily > 0 )
      v17 = 1;
    if ( !v17 )
    {
      bufferLength[0] = 0;
      v18 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"OptedIn", 4u, bufferLength, 4u);
      v19 = v18 < 0;
      if ( v18 > 0 )
      {
        v18 = (unsigned __int16)v18 | 0x80070000;
        v19 = v18 < 0;
      }
      if ( v19 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\MobilityExperienceSettings.h",
          (const char *)(unsigned int)v18,
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
  v20 = *(_QWORD *)count;
  v21 = *(__int64 (__fastcall **)(__int64, HSTRING, DWORD *))(**(_QWORD **)count + 48LL);
  *(_QWORD *)bufferLength = 0;
  v22 = -1;
  do
    ++v22;
  while ( v7[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
    LODWORD(v22) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v7, v22, &hstringHeader, &string);
  v10 = v21(v20, string, bufferLength);
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
  v28 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.System.Launcher",
                      0x17u,
                      (HSTRING_HEADER *)&string,
                      (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v12, v13);
    __debugbreak();
  }
  v14 = RoGetActivationFactory(
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
          &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451,
          &v28);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v14,
      pdwTypea);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v28);
    goto LABEL_52;
  }
  v29 = 0;
  v15 = *v28;
  v29 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 64))(v28, *(_QWORD *)bufferLength, &v29);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"pcshell\\shell\\explorer\\lockstatenotifier.cpp",
      (const char *)(unsigned int)v16,
      pdwTypea);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    if ( *(_QWORD *)bufferLength )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bufferLength + 16LL))(*(_QWORD *)bufferLength);
    if ( *(_QWORD *)count )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)count + 16LL))(*(_QWORD *)count);
    return v3;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v28 )
    (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
  if ( *(_QWORD *)bufferLength )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bufferLength + 16LL))(*(_QWORD *)bufferLength);
  if ( *(_QWORD *)count )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)count + 16LL))(*(_QWORD *)count);
  return 0;
}

```

## disassembly

```asm
0x14001f618  push    rbp
0x14001f61a  push    rbx
0x14001f61b  push    rsi
0x14001f61c  push    rdi
0x14001f61d  push    r14
0x14001f61f  push    r15
0x14001f621  lea     rbp, [rsp-1A8h]
0x14001f629  sub     rsp, 2A8h
0x14001f630  mov     rax, cs:__security_cookie
0x14001f637  xor     rax, rsp
0x14001f63a  mov     [rbp+1D0h+var_40], rax
0x14001f641  mov     esi, ecx
0x14001f643  lea     r9, aUserpresenceap; "UserPresenceAppServiceSignalsCapable"
0x14001f64a  lea     r8, ?c_regKeyMobilityResource@MobilityExperienceSettings@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001f651  mov     edx, 104h; unsigned __int64
0x14001f656  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x14001f65a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001f65f  mov     ebx, eax
0x14001f661  xor     r15d, r15d
0x14001f664  test    eax, eax
0x14001f666  js      loc_14001F983
0x14001f66c  mov     [rsp+2D0h+count], r15d
0x14001f671  lea     edi, [r15+4]
0x14001f675  mov     [rsp+2D0h+bufferLength], edi
0x14001f679  lea     rax, [rsp+2D0h+bufferLength]
0x14001f67e  mov     [rsp+2D0h+pcbData], rax; pcbData
0x14001f683  lea     rax, [rsp+2D0h+count]
0x14001f688  mov     [rsp+2D0h+pvData], rax; pvData
0x14001f68d  mov     [rsp+2D0h+pdwType], r15; pdwType
0x14001f692  mov     r9d, 20000010h; dwFlags
0x14001f698  lea     r8, ?c_regValueOptedIn@MobilityExperienceSettings@CreativeFramework@@3QBGB; "OptedIn"
0x14001f69f  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x14001f6a3  mov     r14, 0FFFFFFFF80000001h
0x14001f6aa  mov     rcx, r14; hkey
0x14001f6ad  call    cs:__imp_RegGetValueW
0x14001f6b4  nop     dword ptr [rax+rax+00h]
0x14001f6b9  mov     ebx, 80070000h
0x14001f6be  test    eax, eax
0x14001f6c0  jle     short loc_14001F6C9
0x14001f6c2  movzx   eax, ax
0x14001f6c5  or      eax, ebx
0x14001f6c7  test    eax, eax
0x14001f6c9  js      loc_14001F8F3
0x14001f6cf  cmp     [rsp+2D0h+count], r15d
0x14001f6d4  jz      loc_14001F8F3
0x14001f6da  mov     [rsp+2D0h+bufferLength], r15d
0x14001f6df  mov     [rsp+2D0h+count], r15d
0x14001f6e4  mov     [rsp+2D0h+pdwType], r15; int
0x14001f6e9  lea     r9, [rsp+2D0h+bufferLength]; bufferLength
0x14001f6ee  xor     r8d, r8d; packageFullNames
0x14001f6f1  lea     rdx, [rsp+2D0h+count]; count
0x14001f6f6  lea     rcx, ?c_yourPhonePackageFamilyName@MobilityExperienceSettings@CreativeFramework@@3QBGB; "Microsoft.YourPhone_8wekyb3d8bbwe"
0x14001f6fd  call    cs:__imp_GetPackagesByPackageFamily
0x14001f704  nop     dword ptr [rax+rax+00h]
0x14001f709  cmp     eax, 7Ah ; 'z'
0x14001f70c  jnz     loc_14001F915
0x14001f712  lea     rax, aMsPhoneApiEven_0; "ms-phone-api://event/unlocked"
0x14001f719  lea     rdi, aMsPhoneApiEven; "ms-phone-api://event/locked"
0x14001f720  test    esi, esi
0x14001f722  cmovnz  rdi, rax
0x14001f726  mov     qword ptr [rsp+2D0h+count], r15
0x14001f72b  lea     r9, [rsp+2D0h+string]; string
0x14001f730  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x14001f735  mov     edx, 16h; length
0x14001f73a  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x14001f741  call    cs:__imp_WindowsCreateStringReference
0x14001f748  nop     dword ptr [rax+rax+00h]
0x14001f74d  test    eax, eax
0x14001f74f  js      loc_14001FA57
0x14001f755  lea     r8, [rsp+2D0h+count]
0x14001f75a  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x14001f761  mov     rcx, [rsp+2D0h+string]
0x14001f766  call    cs:__imp_RoGetActivationFactory
0x14001f76d  nop     dword ptr [rax+rax+00h]
0x14001f772  mov     ebx, eax
0x14001f774  test    eax, eax
0x14001f776  jns     loc_14001F9A3
0x14001f77c  mov     rcx, [rbp+1D8h]; this
0x14001f783  mov     r9d, eax; char *
0x14001f786  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x14001f78d  mov     edx, 30h ; '0'; void *
0x14001f792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f797  nop
0x14001f798  mov     rcx, qword ptr [rsp+2D0h+count]
0x14001f79d  test    rcx, rcx
0x14001f7a0  jz      short loc_14001F7AF
0x14001f7a2  mov     rax, [rcx]
0x14001f7a5  mov     rax, [rax+10h]
0x14001f7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f7ae  nop
0x14001f7af  mov     eax, ebx
0x14001f7b1  jmp     loc_14001F8F5
0x14001f7b6  mov     ebx, eax
0x14001f7b8  xor     r9d, r9d; lpArguments
0x14001f7bb  xor     r8d, r8d; nNumberOfArguments
0x14001f7be  lea     edx, [r9+1]; dwExceptionFlags
0x14001f7c2  mov     ecx, 0C000000Dh; dwExceptionCode
0x14001f7c7  call    cs:__imp_RaiseException
0x14001f7ce  nop     dword ptr [rax+rax+00h]
0x14001f7d3  lea     r9, [rsp+2D0h+string]; string
0x14001f7d8  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x14001f7dd  mov     edx, ebx; length
0x14001f7df  mov     rcx, rdi; sourceString
0x14001f7e2  call    cs:__imp_WindowsCreateStringReference
0x14001f7e9  nop     dword ptr [rax+rax+00h]
0x14001f7ee  lea     r8, [rsp+2D0h+bufferLength]
0x14001f7f3  mov     rdx, [rsp+2D0h+string]
0x14001f7f8  mov     rcx, rsi
0x14001f7fb  mov     rax, r14
0x14001f7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f803  mov     ebx, eax
0x14001f805  test    eax, eax
0x14001f807  js      loc_14001FA77
0x14001f80d  mov     [rsp+2D0h+var_280], r15
0x14001f812  mov     qword ptr [rsp+2D0h+hstringHeader.Reserved+10h], r15
0x14001f817  lea     r9, [rsp+2D0h+hstringHeader.Reserved+10h]; string
0x14001f81c  lea     r8, [rsp+2D0h+string]; hstringHeader
0x14001f821  mov     edx, 17h; length
0x14001f826  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x14001f82d  call    cs:__imp_WindowsCreateStringReference
0x14001f834  nop     dword ptr [rax+rax+00h]
0x14001f839  test    eax, eax
0x14001f83b  js      loc_14001FA94
0x14001f841  lea     r8, [rsp+2D0h+var_280]
0x14001f846  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x14001f84d  mov     rcx, qword ptr [rsp+2D0h+hstringHeader.Reserved+10h]
0x14001f852  call    cs:__imp_RoGetActivationFactory
0x14001f859  nop     dword ptr [rax+rax+00h]
0x14001f85e  mov     ebx, eax
0x14001f860  test    eax, eax
0x14001f862  js      loc_14001FA9C
0x14001f868  mov     [rsp+2D0h+var_278], r15
0x14001f86d  mov     rcx, [rsp+2D0h+var_280]
0x14001f872  mov     rax, [rcx]
0x14001f875  mov     [rsp+2D0h+var_278], r15
0x14001f87a  lea     r8, [rsp+2D0h+var_278]
0x14001f87f  mov     rdx, qword ptr [rsp+2D0h+bufferLength]
0x14001f884  mov     rax, [rax+40h]
0x14001f888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f88d  mov     ebx, eax
0x14001f88f  test    eax, eax
0x14001f891  js      loc_14001F9DA
0x14001f897  mov     rcx, [rsp+2D0h+var_278]
0x14001f89c  test    rcx, rcx
0x14001f89f  jz      short loc_14001F8AE
0x14001f8a1  mov     rax, [rcx]
0x14001f8a4  mov     rax, [rax+10h]
0x14001f8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8ad  nop
0x14001f8ae  mov     rcx, [rsp+2D0h+var_280]
0x14001f8b3  test    rcx, rcx
0x14001f8b6  jz      short loc_14001F8C5
0x14001f8b8  mov     rax, [rcx]
0x14001f8bb  mov     rax, [rax+10h]
0x14001f8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8c4  nop
0x14001f8c5  mov     rcx, qword ptr [rsp+2D0h+bufferLength]
0x14001f8ca  test    rcx, rcx
0x14001f8cd  jz      short loc_14001F8DC
0x14001f8cf  mov     rax, [rcx]
0x14001f8d2  mov     rax, [rax+10h]
0x14001f8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8db  nop
0x14001f8dc  mov     rcx, qword ptr [rsp+2D0h+count]
0x14001f8e1  test    rcx, rcx
0x14001f8e4  jz      short loc_14001F8F3
0x14001f8e6  mov     rax, [rcx]
0x14001f8e9  mov     rax, [rax+10h]
0x14001f8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8f2  nop
0x14001f8f3  xor     eax, eax
0x14001f8f5  mov     rcx, [rbp+1D0h+var_40]
0x14001f8fc  xor     rcx, rsp; StackCookie
0x14001f8ff  call    __security_check_cookie
0x14001f904  add     rsp, 2A8h
0x14001f90b  pop     r15
0x14001f90d  pop     r14
0x14001f90f  pop     rdi
0x14001f910  pop     rsi
0x14001f911  pop     rbx
0x14001f912  pop     rbp
0x14001f913  retn
0x14001f915  test    eax, eax
0x14001f917  jle     short loc_14001F920
0x14001f919  movzx   eax, ax
0x14001f91c  or      eax, ebx
0x14001f91e  test    eax, eax
0x14001f920  js      loc_14001F712
0x14001f926  mov     [rsp+2D0h+bufferLength], r15d
0x14001f92b  mov     dword ptr [rsp+2D0h+pvData], edi; cbData
0x14001f92f  lea     rax, [rsp+2D0h+bufferLength]
0x14001f934  mov     [rsp+2D0h+pdwType], rax; int
0x14001f939  mov     r9d, edi; dwType
0x14001f93c  lea     r8, ?c_regValueOptedIn@MobilityExperienceSettings@CreativeFramework@@3QBGB; "OptedIn"
0x14001f943  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x14001f947  mov     rcx, r14; hKey
0x14001f94a  call    cs:__imp_RegSetKeyValueW
0x14001f951  nop     dword ptr [rax+rax+00h]
0x14001f956  test    eax, eax
0x14001f958  jle     short loc_14001F961
0x14001f95a  movzx   eax, ax
0x14001f95d  or      eax, ebx
0x14001f95f  test    eax, eax
0x14001f961  jns     short loc_14001F8F3
0x14001f963  mov     rcx, [rbp+1D8h]; this
0x14001f96a  mov     r9d, eax; char *
0x14001f96d  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Mobil"...
0x14001f974  mov     edx, 2Eh ; '.'; void *
0x14001f979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f97e  jmp     loc_14001F8F3
0x14001f983  mov     rcx, [rbp+1D8h]; this
0x14001f98a  mov     r9d, ebx; char *
0x14001f98d  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x14001f994  mov     edx, 1Dh; void *
0x14001f999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f99e  jmp     loc_14001F7AF
0x14001f9a3  mov     qword ptr [rsp+2D0h+bufferLength], r15
0x14001f9a8  mov     rsi, qword ptr [rsp+2D0h+count]
0x14001f9ad  mov     rax, [rsi]
0x14001f9b0  mov     r14, [rax+30h]
0x14001f9b4  mov     qword ptr [rsp+2D0h+bufferLength], r15
0x14001f9b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001f9bd  inc     rbx
0x14001f9c0  cmp     [rdi+rbx*2], r15w
0x14001f9c5  jnz     short loc_14001F9BD
0x14001f9c7  mov     eax, 0FFFFFFFFh
0x14001f9cc  cmp     rbx, rax
0x14001f9cf  jbe     loc_14001F7D3
0x14001f9d5  jmp     loc_14001F7B6
0x14001f9da  mov     rcx, [rbp+1D8h]; this
0x14001f9e1  mov     r9d, ebx; char *
0x14001f9e4  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x14001f9eb  mov     edx, 38h ; '8'; void *
0x14001f9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f9f5  nop
0x14001f9f6  mov     rcx, [rsp+2D0h+var_278]
0x14001f9fb  test    rcx, rcx
0x14001f9fe  jz      short loc_14001FA0D
0x14001fa00  mov     rax, [rcx]
0x14001fa03  mov     rax, [rax+10h]
0x14001fa07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fa0c  nop
0x14001fa0d  mov     rcx, [rsp+2D0h+var_280]
0x14001fa12  test    rcx, rcx
0x14001fa15  jz      short loc_14001FA24
0x14001fa17  mov     rax, [rcx]
0x14001fa1a  mov     rax, [rax+10h]
0x14001fa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fa23  nop
0x14001fa24  mov     rcx, qword ptr [rsp+2D0h+bufferLength]
0x14001fa29  test    rcx, rcx
0x14001fa2c  jz      short loc_14001FA3B
0x14001fa2e  mov     rax, [rcx]
0x14001fa31  mov     rax, [rax+10h]
0x14001fa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fa3a  nop
0x14001fa3b  mov     rcx, qword ptr [rsp+2D0h+count]
0x14001fa40  test    rcx, rcx
0x14001fa43  jz      short loc_14001FA52
0x14001fa45  mov     rax, [rcx]
0x14001fa48  mov     rax, [rax+10h]
0x14001fa4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fa51  nop
0x14001fa52  jmp     loc_14001F7AF
0x14001fa57  xor     r9d, r9d; lpArguments
0x14001fa5a  xor     r8d, r8d; nNumberOfArguments
0x14001fa5d  lea     edx, [r9+1]; dwExceptionFlags
0x14001fa61  mov     ecx, 0C000000Dh; dwExceptionCode
0x14001fa66  call    cs:__imp_RaiseException
0x14001fa6d  nop     dword ptr [rax+rax+00h]
0x14001fa72  jmp     loc_14001F755
0x14001fa77  mov     rcx, [rbp+1D8h]; this
0x14001fa7e  mov     r9d, eax; char *
0x14001fa81  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x14001fa88  mov     edx, 32h ; '2'; void *
0x14001fa8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001fa92  jmp     short loc_14001FAC3
0x14001fa94  mov     ecx, eax; this
0x14001fa96  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001fa9b  int     3; Trap to Debugger
0x14001fa9c  mov     rcx, [rbp+1D8h]; this
0x14001faa3  mov     r9d, eax; char *
0x14001faa6  lea     r8, aPcshellShellEx_4; "pcshell\\shell\\explorer\\lockstatenoti"...
0x14001faad  mov     edx, 36h ; '6'; void *
0x14001fab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001fab7  nop
0x14001fab8  lea     rcx, [rsp+2D0h+var_280]
0x14001fabd  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001fac2  nop
0x14001fac3  lea     rcx, [rsp+2D0h+bufferLength]
0x14001fac8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001facd  nop
0x14001face  lea     rcx, [rsp+2D0h+count]
0x14001fad3  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001fad8  jmp     loc_14001F7AF
```

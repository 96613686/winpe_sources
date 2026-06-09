# CTray::_HandleOfficeHotKey(void)

- ea: `0x14012fa04`
- end: `0x14012fbca`
- name: `?_HandleOfficeHotKey@CTray@@IEAAXXZ`
- size: `454`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14012f214`

## callees

- `0x140005810`
- `0x14000fbdc`
- `0x14002825c`
- `0x1400283bc`
- `0x1400bd560`
- `0x14010e160`
- `0x14011e410`
- `0x140120194`
- `0x14012c7e4`
- `0x14012fa04`
- `0x1401308f4`
- `0x140130984`
- `0x140138f34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14012faf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14012faf9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14012fa86`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14012fa86`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14012fa47`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14012fa47`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14012fb0f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x14012fb0f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14012fa6e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14012fa6e`

## string_xrefs

- `0x14012fb7a`: `https://go.microsoft.com/fwlink/?linkid=2044481`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CTray::_HandleOfficeHotKey(CTray *this)
{
  unsigned int v2; // edi
  HWND ForegroundWindow; // rax
  CallerIdentity *v4; // rsi
  char v5; // r14
  char *v6; // rbx
  unsigned __int16 **v7; // r8
  unsigned __int16 **v8; // r8
  CTray *v9; // rcx
  struct HWND__ v10[2]; // [rsp+28h] [rbp-D8h] BYREF
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  char *v12; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[336]; // [rsp+40h] [rbp-C0h] BYREF

  TrayTelemetry::OfficeHotkeyHandled::Start<char>((TrayTelemetry::OfficeHotkeyHandled *)v13);
  v2 = 0;
  ForegroundWindow = GetForegroundWindow();
  v4 = (CallerIdentity *)ForegroundWindow;
  if ( !ForegroundWindow )
    goto LABEL_19;
  v5 = 0;
  dwProcessId = 0;
  GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
  v6 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
  v12 = v6;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)&v10[0].unused = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v10,
      0);
    if ( (int)CallerIdentity::GetImmersiveAppIdFromWindow(v4, v10, v7) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v10,
        0);
      CallerIdentity::GetProcessAppIdWithAppResolverFallback(v6, v10, v8);
    }
    if ( *(_QWORD *)&v10[0].unused
      && !(unsigned int)_o__wcsnicmp(L"Microsoft.MicrosoftOfficeHub", *(_QWORD *)&v10[0].unused, 28) )
    {
      ShowWindow((HWND)v4, 6);
      v5 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v10);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  if ( !v5 )
  {
LABEL_19:
    if ( CTray::_LaunchByProtocol(this, L"ms-officeapp", L"Officekey") )
    {
      v2 = 4;
    }
    else if ( CTray::_LaunchByAppId(
                v9,
                L"Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe!Microsoft.MicrosoftOfficeHub",
                L"Officekey") )
    {
      v2 = 2;
    }
    else if ( CTray::_OpenAppOrUrlCore(this, L"https://go.microsoft.com/fwlink/?linkid=2044481", 0) )
    {
      v2 = 5;
    }
  }
  TrayTelemetry::OfficeHotkeyHandled::Stop(v13, v2);
  TrayTelemetry::OfficeHotkeyHandled::~OfficeHotkeyHandled((TrayTelemetry::OfficeHotkeyHandled *)v13);
}

```

## disassembly

```asm
0x14012fa04  push    rbp
0x14012fa06  push    rbx
0x14012fa07  push    rsi
0x14012fa08  push    rdi
0x14012fa09  push    r14
0x14012fa0b  push    r15
0x14012fa0d  lea     rbp, [rsp-0A8h]
0x14012fa15  sub     rsp, 1A8h
0x14012fa1c  mov     rax, cs:__security_cookie
0x14012fa23  xor     rax, rsp
0x14012fa26  mov     [rbp+0D0h+var_40], rax
0x14012fa2d  mov     r15, rcx
0x14012fa30  mov     [rsp+1D0h+var_1B0], 0
0x14012fa35  lea     rdx, [rsp+1D0h+var_1B0]
0x14012fa3a  lea     rcx, [rsp+1D0h+var_190]; this
0x14012fa3f  call    ??$Start@D@OfficeHotkeyHandled@TrayTelemetry@@SA?AV01@$$QEAD@Z; TrayTelemetry::OfficeHotkeyHandled::Start<char>(char &&)
0x14012fa44  nop
0x14012fa45  xor     edi, edi
0x14012fa47  call    cs:__imp_GetForegroundWindow
0x14012fa4e  nop     dword ptr [rax+rax+00h]
0x14012fa53  mov     rsi, rax
0x14012fa56  test    rax, rax
0x14012fa59  jz      loc_14012FB38
0x14012fa5f  xor     r14b, r14b
0x14012fa62  mov     [rsp+1D0h+dwProcessId], edi
0x14012fa66  lea     rdx, [rsp+1D0h+dwProcessId]; lpdwProcessId
0x14012fa6b  mov     rcx, rax; hWnd
0x14012fa6e  call    cs:__imp_GetWindowThreadProcessId
0x14012fa75  nop     dword ptr [rax+rax+00h]
0x14012fa7a  mov     r8d, [rsp+1D0h+dwProcessId]; dwProcessId
0x14012fa7f  xor     edx, edx; bInheritHandle
0x14012fa81  mov     ecx, 1000h; dwDesiredAccess
0x14012fa86  call    cs:__imp_OpenProcess
0x14012fa8d  nop     dword ptr [rax+rax+00h]
0x14012fa92  mov     rbx, rax
0x14012fa95  mov     [rsp+1D0h+var_198], rax
0x14012fa9a  dec     rax
0x14012fa9d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14012faa1  ja      loc_14012FB29
0x14012faa7  mov     qword ptr [rsp+1D0h+var_1A8.unused], rdi
0x14012faac  xor     edx, edx
0x14012faae  lea     rcx, [rsp+1D0h+var_1A8]
0x14012fab3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14012fab8  lea     rdx, [rsp+1D0h+var_1A8]; HWND
0x14012fabd  mov     rcx, rsi; this
0x14012fac0  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x14012fac5  test    eax, eax
0x14012fac7  jns     short loc_14012FAE2
0x14012fac9  xor     edx, edx
0x14012facb  lea     rcx, [rsp+1D0h+var_1A8]
0x14012fad0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14012fad5  lea     rdx, [rsp+1D0h+var_1A8]; void *
0x14012fada  mov     rcx, rbx; Process
0x14012fadd  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x14012fae2  mov     rdx, qword ptr [rsp+1D0h+var_1A8.unused]
0x14012fae7  test    rdx, rdx
0x14012faea  jz      short loc_14012FB1E
0x14012faec  mov     r8d, 1Ch
0x14012faf2  lea     rcx, aMicrosoftMicro_5; "Microsoft.MicrosoftOfficeHub"
0x14012faf9  call    cs:__imp__o__wcsnicmp
0x14012fb00  nop     dword ptr [rax+rax+00h]
0x14012fb05  test    eax, eax
0x14012fb07  jnz     short loc_14012FB1E
0x14012fb09  lea     edx, [rax+6]; nCmdShow
0x14012fb0c  mov     rcx, rsi; hWnd
0x14012fb0f  call    cs:__imp_ShowWindow
0x14012fb16  nop     dword ptr [rax+rax+00h]
0x14012fb1b  mov     r14b, 1
0x14012fb1e  lea     rcx, [rsp+1D0h+var_1A8]
0x14012fb23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14012fb28  nop
0x14012fb29  lea     rcx, [rsp+1D0h+var_198]
0x14012fb2e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14012fb33  test    r14b, r14b
0x14012fb36  jnz     short loc_14012FB93
0x14012fb38  lea     r8, aOfficekey; "Officekey"
0x14012fb3f  lea     rdx, aMsOfficeapp; "ms-officeapp"
0x14012fb46  mov     rcx, r15; this
0x14012fb49  call    ?_LaunchByProtocol@CTray@@IEAA_NPEBG0@Z; CTray::_LaunchByProtocol(ushort const *,ushort const *)
0x14012fb4e  test    al, al
0x14012fb50  jz      short loc_14012FB59
0x14012fb52  mov     edi, 4
0x14012fb57  jmp     short loc_14012FB93
0x14012fb59  lea     r8, aOfficekey; "Officekey"
0x14012fb60  lea     rdx, aMicrosoftMicro_0; "Microsoft.MicrosoftOfficeHub_8wekyb3d8b"...
0x14012fb67  call    ?_LaunchByAppId@CTray@@IEAA_NPEBG0@Z; CTray::_LaunchByAppId(ushort const *,ushort const *)
0x14012fb6c  test    al, al
0x14012fb6e  jz      short loc_14012FB77
0x14012fb70  mov     edi, 2
0x14012fb75  jmp     short loc_14012FB93
0x14012fb77  xor     r8d, r8d; unsigned __int16 *
0x14012fb7a  lea     rdx, aHttpsGoMicroso_6; "https://go.microsoft.com/fwlink/?linkid"...
0x14012fb81  mov     rcx, r15; this
0x14012fb84  call    ?_OpenAppOrUrlCore@CTray@@IEAA_NPEBG0@Z; CTray::_OpenAppOrUrlCore(ushort const *,ushort const *)
0x14012fb89  mov     ecx, 5
0x14012fb8e  test    al, al
0x14012fb90  cmovnz  edi, ecx
0x14012fb93  mov     edx, edi
0x14012fb95  lea     rcx, [rsp+1D0h+var_190]
0x14012fb9a  call    ?Stop@OfficeHotkeyHandled@TrayTelemetry@@QEAAXW4OfficeLaunchType@2@@Z; TrayTelemetry::OfficeHotkeyHandled::Stop(TrayTelemetry::OfficeLaunchType)
0x14012fb9f  nop
0x14012fba0  lea     rcx, [rsp+1D0h+var_190]; this
0x14012fba5  call    ??1OfficeHotkeyHandled@TrayTelemetry@@QEAA@XZ; TrayTelemetry::OfficeHotkeyHandled::~OfficeHotkeyHandled(void)
0x14012fbaa  mov     rcx, [rbp+0D0h+var_40]
0x14012fbb1  xor     rcx, rsp; StackCookie
0x14012fbb4  call    __security_check_cookie
0x14012fbb9  add     rsp, 1A8h
0x14012fbc0  pop     r15
0x14012fbc2  pop     r14
0x14012fbc4  pop     rdi
0x14012fbc5  pop     rsi
0x14012fbc6  pop     rbx
0x14012fbc7  pop     rbp
0x14012fbc8  retn
```

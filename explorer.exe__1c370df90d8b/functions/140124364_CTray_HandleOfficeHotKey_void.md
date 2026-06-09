# CTray::_HandleOfficeHotKey(void)

- ea: `0x140124364`
- end: `0x140124507`
- name: `?_HandleOfficeHotKey@CTray@@IEAAXXZ`
- size: `419`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140123bbc`

## callees

- `0x140034af0`
- `0x14003588c`
- `0x1400363c4`
- `0x140065b60`
- `0x1400b73f4`
- `0x1401040e0`
- `0x140113b44`
- `0x1401158a8`
- `0x140121244`
- `0x140124364`
- `0x140125168`
- `0x1401251f8`
- `0x14012d330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140124443`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140124443`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401243da`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401243da`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1401243a7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1401243a7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x140124453`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!ShowWindow` at `0x140124453`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1401243c8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1401243c8`

## string_xrefs

- `0x1401244b8`: `https://go.microsoft.com/fwlink/?linkid=2044481`

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
0x140124364  push    rbp
0x140124366  push    rbx
0x140124367  push    rsi
0x140124368  push    rdi
0x140124369  push    r14
0x14012436b  push    r15
0x14012436d  lea     rbp, [rsp-0A8h]
0x140124375  sub     rsp, 1A8h
0x14012437c  mov     rax, cs:__security_cookie
0x140124383  xor     rax, rsp
0x140124386  mov     [rbp+0D0h+var_40], rax
0x14012438d  mov     r15, rcx
0x140124390  mov     [rsp+1D0h+var_1B0], 0
0x140124395  lea     rdx, [rsp+1D0h+var_1B0]
0x14012439a  lea     rcx, [rsp+1D0h+var_190]; this
0x14012439f  call    ??$Start@D@OfficeHotkeyHandled@TrayTelemetry@@SA?AV01@$$QEAD@Z; TrayTelemetry::OfficeHotkeyHandled::Start<char>(char &&)
0x1401243a4  nop
0x1401243a5  xor     edi, edi
0x1401243a7  call    cs:__imp_GetForegroundWindow
0x1401243ad  mov     rsi, rax
0x1401243b0  test    rax, rax
0x1401243b3  jz      loc_140124476
0x1401243b9  xor     r14b, r14b
0x1401243bc  mov     [rsp+1D0h+dwProcessId], edi
0x1401243c0  lea     rdx, [rsp+1D0h+dwProcessId]; lpdwProcessId
0x1401243c5  mov     rcx, rax; hWnd
0x1401243c8  call    cs:__imp_GetWindowThreadProcessId
0x1401243ce  mov     r8d, [rsp+1D0h+dwProcessId]; dwProcessId
0x1401243d3  xor     edx, edx; bInheritHandle
0x1401243d5  mov     ecx, 1000h; dwDesiredAccess
0x1401243da  call    cs:__imp_OpenProcess
0x1401243e0  mov     rbx, rax
0x1401243e3  mov     [rsp+1D0h+var_198], rax
0x1401243e8  dec     rax
0x1401243eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401243ef  ja      short loc_140124467
0x1401243f1  mov     qword ptr [rsp+1D0h+var_1A8.unused], rdi
0x1401243f6  xor     edx, edx
0x1401243f8  lea     rcx, [rsp+1D0h+var_1A8]
0x1401243fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140124402  lea     rdx, [rsp+1D0h+var_1A8]; HWND
0x140124407  mov     rcx, rsi; this
0x14012440a  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x14012440f  test    eax, eax
0x140124411  jns     short loc_14012442C
0x140124413  xor     edx, edx
0x140124415  lea     rcx, [rsp+1D0h+var_1A8]
0x14012441a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14012441f  lea     rdx, [rsp+1D0h+var_1A8]; void *
0x140124424  mov     rcx, rbx; Process
0x140124427  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x14012442c  mov     rdx, qword ptr [rsp+1D0h+var_1A8.unused]
0x140124431  test    rdx, rdx
0x140124434  jz      short loc_14012445C
0x140124436  mov     r8d, 1Ch
0x14012443c  lea     rcx, aMicrosoftMicro_5; "Microsoft.MicrosoftOfficeHub"
0x140124443  call    cs:__imp__o__wcsnicmp
0x140124449  test    eax, eax
0x14012444b  jnz     short loc_14012445C
0x14012444d  lea     edx, [rax+6]; nCmdShow
0x140124450  mov     rcx, rsi; hWnd
0x140124453  call    cs:__imp_ShowWindow
0x140124459  mov     r14b, 1
0x14012445c  lea     rcx, [rsp+1D0h+var_1A8]
0x140124461  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140124466  nop
0x140124467  lea     rcx, [rsp+1D0h+var_198]
0x14012446c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140124471  test    r14b, r14b
0x140124474  jnz     short loc_1401244D1
0x140124476  lea     r8, aOfficekey; "Officekey"
0x14012447d  lea     rdx, aMsOfficeapp; "ms-officeapp"
0x140124484  mov     rcx, r15; this
0x140124487  call    ?_LaunchByProtocol@CTray@@IEAA_NPEBG0@Z; CTray::_LaunchByProtocol(ushort const *,ushort const *)
0x14012448c  test    al, al
0x14012448e  jz      short loc_140124497
0x140124490  mov     edi, 4
0x140124495  jmp     short loc_1401244D1
0x140124497  lea     r8, aOfficekey; "Officekey"
0x14012449e  lea     rdx, aMicrosoftMicro_0; "Microsoft.MicrosoftOfficeHub_8wekyb3d8b"...
0x1401244a5  call    ?_LaunchByAppId@CTray@@IEAA_NPEBG0@Z; CTray::_LaunchByAppId(ushort const *,ushort const *)
0x1401244aa  test    al, al
0x1401244ac  jz      short loc_1401244B5
0x1401244ae  mov     edi, 2
0x1401244b3  jmp     short loc_1401244D1
0x1401244b5  xor     r8d, r8d; unsigned __int16 *
0x1401244b8  lea     rdx, aHttpsGoMicroso_6; "https://go.microsoft.com/fwlink/?linkid"...
0x1401244bf  mov     rcx, r15; this
0x1401244c2  call    ?_OpenAppOrUrlCore@CTray@@IEAA_NPEBG0@Z; CTray::_OpenAppOrUrlCore(ushort const *,ushort const *)
0x1401244c7  mov     ecx, 5
0x1401244cc  test    al, al
0x1401244ce  cmovnz  edi, ecx
0x1401244d1  mov     edx, edi
0x1401244d3  lea     rcx, [rsp+1D0h+var_190]
0x1401244d8  call    ?Stop@OfficeHotkeyHandled@TrayTelemetry@@QEAAXW4OfficeLaunchType@2@@Z; TrayTelemetry::OfficeHotkeyHandled::Stop(TrayTelemetry::OfficeLaunchType)
0x1401244dd  nop
0x1401244de  lea     rcx, [rsp+1D0h+var_190]; this
0x1401244e3  call    ??1OfficeHotkeyHandled@TrayTelemetry@@QEAA@XZ; TrayTelemetry::OfficeHotkeyHandled::~OfficeHotkeyHandled(void)
0x1401244e8  mov     rcx, [rbp+0D0h+var_40]
0x1401244ef  xor     rcx, rsp; StackCookie
0x1401244f2  call    __security_check_cookie
0x1401244f7  add     rsp, 1A8h
0x1401244fe  pop     r15
0x140124500  pop     r14
0x140124502  pop     rdi
0x140124503  pop     rsi
0x140124504  pop     rbx
0x140124505  pop     rbp
0x140124506  retn
```

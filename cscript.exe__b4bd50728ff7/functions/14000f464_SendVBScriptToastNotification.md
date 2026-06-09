# SendVBScriptToastNotification

- ea: `0x14000f464`
- end: `0x14000f7cf`
- name: `SendVBScriptToastNotification`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001950`

## callees

- `0x14000c2ec`
- `0x14000ec30`
- `0x14000ec9c`
- `0x14000ee40`
- `0x14000f08c`
- `0x14000f274`
- `0x14000f378`
- `0x14000f464`
- `0x14000f7d8`
- `0x1400161d0`
- `0x140016200`
- `0x140017010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000f50e`
- `msvcrt!_wcsicmp` at `0x14000f50e`
- `msvcrt!wcsrchr` at `0x14000f4dc`
- `msvcrt!wcsrchr` at `0x14000f4dc`
- `KERNEL32!GetLastError` at `0x14000f4b8`
- `KERNEL32!GetLastError` at `0x14000f4b8`
- `KERNEL32!GetModuleFileNameW` at `0x14000f4ae`
- `KERNEL32!GetModuleFileNameW` at `0x14000f4ae`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000f651`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000f651`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000f581`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000f72d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000f581`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000f72d`

## string_xrefs

- `0x14000f5f2`: `<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbscript-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VBScript Usage Detected</text><text>VBScript will be removed and may not be supported in future versions of Windows. Go to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual><actions><action content='Learn More' activationType='protocol' arguments='https://techcomm`
- `0x14000f632`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
signed int SendVBScriptToastNotification()
{
  signed int result; // eax
  wchar_t *v1; // rax
  unsigned __int16 *v2; // rbx
  int v3; // eax
  const unsigned __int16 *v4; // r8
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD); // rbx
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR sourceString[2048]; // [rsp+290h] [rbp+190h] BYREF

  if ( !IsInteractiveUserSession() )
    return 1;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v1 = wcsrchr(Filename, 0x5Cu);
  v2 = v1 ? v1 + 1 : Filename;
  if ( !(unsigned __int8)ShouldShowToastThrottled(v2) )
    return 1;
  v3 = _wcsicmp(v2, L"cscript.exe");
  v4 = L"Microsoft.WindowsScriptHost.CScript";
  if ( v3 )
    v4 = L"Microsoft.WindowsScriptHost.WScript";
  v22 = v4;
  EnsureStartMenuShortcut((__int64)v2, (__int64)Filename, v4);
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v16);
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Notifications.ToastNotificationManager",
    0x32u,
    0x31u);
  ActivationFactory = RoGetActivationFactory(v24, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v16);
  if ( ActivationFactory >= 0 )
  {
    v6 = v16;
    v17 = 0;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v17);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v22);
    ActivationFactory = v7(v6, *(_QWORD *)(v8 + 24), &v17);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = StringCchPrintfW(
                            sourceString,
                            0x800u,
                            L"<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-it"
                             "pro-blog/vbscript-deprecation-timelines-and-next-steps/4148301'><visual><binding template='"
                             "ToastGeneric'><text>VBScript Usage Detected</text><text>VBScript will be removed and may no"
                             "t be supported in future versions of Windows. Go to Event Viewer > VBScriptDeprecationEvent"
                             " for more details.</text></binding></visual><actions><action content='Learn More' activatio"
                             "nType='protocol' arguments='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbs"
                             "cript-deprecation-timelines-and-next-steps/4148301' /><action content='Dismiss' activationT"
                             "ype='system' arguments='dismiss' /></actions></toast>");
      if ( ActivationFactory >= 0 )
      {
        v18 = 0;
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v18);
        v24 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Xml.Dom.XmlDocument",
          0x21u,
          0x20u);
        ActivationFactory = RoActivateInstance(v24, &v18);
        if ( ActivationFactory >= 0 )
        {
          v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
          v19 = 0;
          v10 = **v18;
          Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v19);
          ActivationFactory = v10(v9, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v19);
          if ( ActivationFactory >= 0 )
          {
            v11 = v19;
            v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 48LL);
            v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
            ActivationFactory = v12(v11, *(_QWORD *)(v13 + 24));
            if ( ActivationFactory >= 0 )
            {
              v20 = 0;
              Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v20);
              v24 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.UI.Notifications.ToastNotification",
                0x2Bu,
                0x2Au);
              ActivationFactory = RoGetActivationFactory(v24, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v20);
              if ( ActivationFactory >= 0 )
              {
                v14 = v20;
                v21 = 0;
                v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL);
                Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
                ActivationFactory = v15(v14, v18, &v21);
                if ( ActivationFactory >= 0 )
                  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 48LL))(v17, v21);
                Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
              }
              Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v20);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v19);
        }
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v18);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v17);
  }
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v16);
  return ActivationFactory;
}

```

## disassembly

```asm
0x14000f464  mov     [rsp-8+arg_0], rbx
0x14000f469  mov     [rsp-8+arg_8], rdi
0x14000f46e  push    rbp
0x14000f46f  lea     rbp, [rsp-11A0h]
0x14000f477  mov     eax, 12A0h
0x14000f47c  call    _alloca_probe
0x14000f481  sub     rsp, rax
0x14000f484  mov     rax, cs:__security_cookie
0x14000f48b  xor     rax, rsp
0x14000f48e  mov     [rbp+11A0h+var_10], rax
0x14000f495  call    IsInteractiveUserSession
0x14000f49a  test    al, al
0x14000f49c  jz      loc_14000F7A6
0x14000f4a2  mov     r8d, 104h; nSize
0x14000f4a8  lea     rdx, [rbp+11A0h+Filename]; lpFilename
0x14000f4ac  xor     ecx, ecx; hModule
0x14000f4ae  call    cs:__imp_GetModuleFileNameW
0x14000f4b4  test    eax, eax
0x14000f4b6  jnz     short loc_14000F4D3
0x14000f4b8  call    cs:__imp_GetLastError
0x14000f4be  test    eax, eax
0x14000f4c0  jle     loc_14000F7AB
0x14000f4c6  movzx   eax, ax
0x14000f4c9  or      eax, 80070000h
0x14000f4ce  jmp     loc_14000F7AB
0x14000f4d3  mov     edx, 5Ch ; '\'; Ch
0x14000f4d8  lea     rcx, [rbp+11A0h+Filename]; Str
0x14000f4dc  call    cs:__imp_wcsrchr
0x14000f4e2  mov     rbx, rax
0x14000f4e5  test    rax, rax
0x14000f4e8  jz      short loc_14000F4F0
0x14000f4ea  add     rbx, 2
0x14000f4ee  jmp     short loc_14000F4F4
0x14000f4f0  lea     rbx, [rbp+11A0h+Filename]
0x14000f4f4  mov     rcx, rbx; unsigned __int16 *
0x14000f4f7  call    ShouldShowToastThrottled
0x14000f4fc  test    al, al
0x14000f4fe  jz      loc_14000F7A6
0x14000f504  lea     rdx, aCscriptExe_0; "cscript.exe"
0x14000f50b  mov     rcx, rbx; String1
0x14000f50e  call    cs:__imp__wcsicmp
0x14000f514  test    eax, eax
0x14000f516  lea     rcx, aMicrosoftWindo; "Microsoft.WindowsScriptHost.WScript"
0x14000f51d  lea     r8, aMicrosoftWindo_0; "Microsoft.WindowsScriptHost.CScript"
0x14000f524  cmovnz  r8, rcx
0x14000f528  lea     rdx, [rbp+11A0h+Filename]
0x14000f52c  mov     rcx, rbx
0x14000f52f  mov     [rsp+12A0h+var_1250], r8
0x14000f534  call    EnsureStartMenuShortcut
0x14000f539  lea     rcx, [rsp+12A0h+var_1280]
0x14000f53e  mov     [rsp+12A0h+var_1280], 0
0x14000f547  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f54c  mov     r9d, 31h ; '1'; unsigned int
0x14000f552  mov     [rsp+12A0h+var_1230], 0
0x14000f55b  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x14000f562  lea     rcx, [rsp+12A0h+hstringHeader]; hstringHeader
0x14000f567  lea     r8d, [r9+1]; unsigned int
0x14000f56b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000f570  mov     rcx, [rsp+12A0h+var_1230]
0x14000f575  lea     r8, [rsp+12A0h+var_1280]
0x14000f57a  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x14000f581  call    cs:__imp_RoGetActivationFactory
0x14000f587  mov     ebx, eax
0x14000f589  test    eax, eax
0x14000f58b  jns     short loc_14000F59E
0x14000f58d  lea     rcx, [rsp+12A0h+var_1280]
0x14000f592  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f597  mov     eax, ebx
0x14000f599  jmp     loc_14000F7AB
0x14000f59e  mov     rdi, [rsp+12A0h+var_1280]
0x14000f5a3  lea     rcx, [rsp+12A0h+var_1278]
0x14000f5a8  mov     [rsp+12A0h+var_1278], 0
0x14000f5b1  mov     rax, [rdi]
0x14000f5b4  mov     rbx, [rax+38h]
0x14000f5b8  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f5bd  lea     rdx, [rsp+12A0h+var_1250]
0x14000f5c2  lea     rcx, [rsp+12A0h+hstringHeader]
0x14000f5c7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000f5cc  lea     r8, [rsp+12A0h+var_1278]
0x14000f5d1  mov     rcx, rdi
0x14000f5d4  mov     rdx, [rax+18h]
0x14000f5d8  mov     rax, rbx
0x14000f5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5e0  mov     ebx, eax
0x14000f5e2  test    eax, eax
0x14000f5e4  jns     short loc_14000F5F2
0x14000f5e6  lea     rcx, [rsp+12A0h+var_1278]
0x14000f5eb  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f5f0  jmp     short loc_14000F58D
0x14000f5f2  lea     r8, aToastActivatio; "<toast activationType='protocol' launch"...
0x14000f5f9  mov     edx, 800h; unsigned __int64
0x14000f5fe  lea     rcx, [rbp+11A0h+sourceString]; unsigned __int16 *
0x14000f605  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f60a  mov     ebx, eax
0x14000f60c  test    eax, eax
0x14000f60e  js      short loc_14000F5E6
0x14000f610  lea     rcx, [rsp+12A0h+var_1270]
0x14000f615  mov     [rsp+12A0h+var_1270], 0
0x14000f61e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f623  mov     r9d, 20h ; ' '; unsigned int
0x14000f629  mov     [rsp+12A0h+var_1230], 0
0x14000f632  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x14000f639  lea     rcx, [rsp+12A0h+hstringHeader]; hstringHeader
0x14000f63e  lea     r8d, [r9+1]; unsigned int
0x14000f642  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000f647  mov     rcx, [rsp+12A0h+var_1230]
0x14000f64c  lea     rdx, [rsp+12A0h+var_1270]
0x14000f651  call    cs:__imp_RoActivateInstance
0x14000f657  mov     ebx, eax
0x14000f659  test    eax, eax
0x14000f65b  jns     short loc_14000F66C
0x14000f65d  lea     rcx, [rsp+12A0h+var_1270]
0x14000f662  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f667  jmp     loc_14000F5E6
0x14000f66c  mov     rbx, [rsp+12A0h+var_1270]
0x14000f671  lea     rcx, [rsp+12A0h+var_1268]
0x14000f676  mov     [rsp+12A0h+var_1268], 0
0x14000f67f  mov     rax, [rbx]
0x14000f682  mov     rdi, [rax]
0x14000f685  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f68a  lea     r8, [rsp+12A0h+var_1268]
0x14000f68f  mov     rcx, rbx
0x14000f692  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x14000f699  mov     rax, rdi
0x14000f69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6a1  mov     ebx, eax
0x14000f6a3  test    eax, eax
0x14000f6a5  jns     short loc_14000F6B3
0x14000f6a7  lea     rcx, [rsp+12A0h+var_1268]
0x14000f6ac  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f6b1  jmp     short loc_14000F65D
0x14000f6b3  mov     rdi, [rsp+12A0h+var_1268]
0x14000f6b8  lea     rdx, [rbp+11A0h+sourceString]; sourceString
0x14000f6bf  lea     rcx, [rsp+12A0h+hstringHeader]; hstringHeader
0x14000f6c4  mov     rax, [rdi]
0x14000f6c7  mov     rbx, [rax+30h]
0x14000f6cb  call    ??$?0$0IAA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IAA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2048])
0x14000f6d0  mov     rcx, rdi
0x14000f6d3  mov     rdx, [rax+18h]
0x14000f6d7  mov     rax, rbx
0x14000f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6df  mov     ebx, eax
0x14000f6e1  test    eax, eax
0x14000f6e3  js      short loc_14000F6A7
0x14000f6e5  lea     rcx, [rsp+12A0h+var_1260]
0x14000f6ea  mov     [rsp+12A0h+var_1260], 0
0x14000f6f3  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f6f8  mov     r9d, 2Ah ; '*'; unsigned int
0x14000f6fe  mov     [rsp+12A0h+var_1230], 0
0x14000f707  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotification@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x14000f70e  lea     rcx, [rsp+12A0h+hstringHeader]; hstringHeader
0x14000f713  lea     r8d, [r9+1]; unsigned int
0x14000f717  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000f71c  mov     rcx, [rsp+12A0h+var_1230]
0x14000f721  lea     r8, [rsp+12A0h+var_1260]
0x14000f726  lea     rdx, _GUID_04124b20_82c6_4229_b109_fd9ed4662b53
0x14000f72d  call    cs:__imp_RoGetActivationFactory
0x14000f733  mov     ebx, eax
0x14000f735  test    eax, eax
0x14000f737  jns     short loc_14000F748
0x14000f739  lea     rcx, [rsp+12A0h+var_1260]
0x14000f73e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f743  jmp     loc_14000F6A7
0x14000f748  mov     rdi, [rsp+12A0h+var_1260]
0x14000f74d  lea     rcx, [rsp+12A0h+var_1258]
0x14000f752  mov     [rsp+12A0h+var_1258], 0
0x14000f75b  mov     rax, [rdi]
0x14000f75e  mov     rbx, [rax+30h]
0x14000f762  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f767  mov     rdx, [rsp+12A0h+var_1270]
0x14000f76c  lea     r8, [rsp+12A0h+var_1258]
0x14000f771  mov     rcx, rdi
0x14000f774  mov     rax, rbx
0x14000f777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f77c  mov     ebx, eax
0x14000f77e  test    eax, eax
0x14000f780  js      short loc_14000F79A
0x14000f782  mov     rcx, [rsp+12A0h+var_1278]
0x14000f787  mov     rdx, [rsp+12A0h+var_1258]
0x14000f78c  mov     rax, [rcx]
0x14000f78f  mov     rax, [rax+30h]
0x14000f793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f798  mov     ebx, eax
0x14000f79a  lea     rcx, [rsp+12A0h+var_1258]
0x14000f79f  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f7a4  jmp     short loc_14000F739
0x14000f7a6  mov     eax, 1
0x14000f7ab  mov     rcx, [rbp+11A0h+var_10]
0x14000f7b2  xor     rcx, rsp; StackCookie
0x14000f7b5  call    __security_check_cookie
0x14000f7ba  lea     r11, [rsp+12A0h+var_s0]
0x14000f7c2  mov     rbx, [r11+10h]
0x14000f7c6  mov     rdi, [r11+18h]
0x14000f7ca  mov     rsp, r11
0x14000f7cd  pop     rbp
0x14000f7ce  retn
```

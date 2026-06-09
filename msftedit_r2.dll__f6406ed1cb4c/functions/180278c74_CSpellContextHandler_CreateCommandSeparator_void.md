# CSpellContextHandler::CreateCommandSeparator(void)

- ea: `0x180278c74`
- end: `0x180278d2d`
- name: `?CreateCommandSeparator@CSpellContextHandler@@AEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18027942c`
- `0x180279718`

## callees

- `0x18006ad18`
- `0x18013ce80`
- `0x1802781cc`
- `0x180278c74`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278ccd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278cae`

## string_xrefs

- `0x180278c9a`: `Windows.UI.Popups.UICommandSeparator`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreateCommandSeparator(CSpellContextHandler *this)
{
  int v2; // ebx
  __int64 v4; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v5; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v6; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Popups.UICommandSeparator", 0x24u, &v6, &v5) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(v5, &v4);
  if ( v2 >= 0 )
    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 104LL))(*((_QWORD *)this + 18), v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180278c74  mov     r11, rsp
0x180278c77  mov     [r11+10h], rbx
0x180278c7b  push    rdi
0x180278c7c  sub     rsp, 50h
0x180278c80  mov     rax, cs:__security_cookie
0x180278c87  xor     rax, rsp
0x180278c8a  mov     [rsp+58h+var_10], rax
0x180278c8f  mov     rdi, rcx
0x180278c92  mov     qword ptr [r11-38h], 0
0x180278c9a  lea     rcx, ?RuntimeClass_Windows_UI_Popups_UICommandSeparator@@3QBGB; "Windows.UI.Popups.UICommandSeparator"
0x180278ca1  mov     edx, 24h ; '$'; length
0x180278ca6  lea     r9, [r11-30h]; string
0x180278caa  lea     r8, [r11-28h]; hstringHeader
0x180278cae  call    cs:__imp_WindowsCreateStringReference
0x180278cb5  nop     dword ptr [rax+rax+00h]
0x180278cba  test    eax, eax
0x180278cbc  jns     short loc_180278CD9
0x180278cbe  xor     r9d, r9d; lpArguments
0x180278cc1  xor     r8d, r8d; nNumberOfArguments
0x180278cc4  mov     ecx, 0C000000Dh; dwExceptionCode
0x180278cc9  lea     edx, [r9+1]; dwExceptionFlags
0x180278ccd  call    cs:__imp_RaiseException
0x180278cd4  nop     dword ptr [rax+rax+00h]
0x180278cd9  mov     rcx, [rsp+58h+var_30]
0x180278cde  lea     rdx, [rsp+58h+var_38]
0x180278ce3  call    ??$ActivateInstance@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>)
0x180278ce8  mov     ebx, eax
0x180278cea  test    eax, eax
0x180278cec  js      short loc_180278D08
0x180278cee  mov     rcx, [rdi+90h]
0x180278cf5  mov     rdx, [rsp+58h+var_38]
0x180278cfa  mov     rax, [rcx]
0x180278cfd  mov     rax, [rax+68h]
0x180278d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278d06  mov     ebx, eax
0x180278d08  lea     rcx, [rsp+58h+var_38]
0x180278d0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180278d12  mov     eax, ebx
0x180278d14  mov     rcx, [rsp+58h+var_10]
0x180278d19  xor     rcx, rsp; StackCookie
0x180278d1c  call    __security_check_cookie
0x180278d21  mov     rbx, [rsp+58h+arg_8]
0x180278d26  add     rsp, 50h
0x180278d2a  pop     rdi
0x180278d2b  retn
```

# InitHiddenCharacter(void)

- ea: `0x180100570`
- end: `0x18010064d`
- name: `?InitHiddenCharacter@@YAXXZ`
- size: `221`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d0c40`

## callees

- `0x18006ad18`
- `0x180100570`
- `0x18013ce80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180100640`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180100640`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801005d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801005d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801005ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801005ab`

## string_xrefs

- `0x1801005a4`: `Windows.UI.Text.Core.CoreTextServicesConstants`

## pseudocode

```c
void InitHiddenCharacter(void)
{
  HRESULT v0; // eax
  HSTRING v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v4; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v5; // [rsp+40h] [rbp-18h] BYREF

  v3 = 0;
  v5 = 0;
  v0 = WindowsCreateStringReference(L"Windows.UI.Text.Core.CoreTextServicesConstants", 0x2Eu, &v4, &v5);
  if ( v0 < 0 )
  {
    RaiseException(v0, 1u, 0, 0);
    __debugbreak();
    JUMPOUT(0x18010064DLL);
  }
  v1 = v5;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v3);
  if ( (int)RoGetActivationFactory(v1, &GUID_91859a46_eccf_47a4_8ae7_098a9c6fbb15, &v3) >= 0 )
    (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v3 + 48LL))(v3, &wchTSF30Hidden);
  v2 = v3;
  if ( v3 )
  {
    v3 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x180100570  mov     r11, rsp
0x180100573  push    rbx
0x180100574  sub     rsp, 50h
0x180100578  mov     rax, cs:__security_cookie
0x18010057f  xor     rax, rsp
0x180100582  mov     [rsp+58h+var_10], rax
0x180100587  lea     r9, [r11-18h]; string
0x18010058b  mov     qword ptr [r11-38h], 0
0x180100593  lea     r8, [r11-30h]; hstringHeader
0x180100597  mov     qword ptr [r11-18h], 0
0x18010059f  mov     edx, 2Eh ; '.'; length
0x1801005a4  lea     rcx, ?RuntimeClass_Windows_UI_Text_Core_CoreTextServicesConstants@@3QBGB; "Windows.UI.Text.Core.CoreTextServicesCo"...
0x1801005ab  call    cs:__imp_WindowsCreateStringReference
0x1801005b2  nop     dword ptr [rax+rax+00h]
0x1801005b7  test    eax, eax
0x1801005b9  js      short loc_180100634
0x1801005bb  mov     rbx, [rsp+58h+var_18]
0x1801005c0  lea     rcx, [rsp+58h+var_38]
0x1801005c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801005ca  lea     r8, [rsp+58h+var_38]
0x1801005cf  mov     rcx, rbx
0x1801005d2  lea     rdx, _GUID_91859a46_eccf_47a4_8ae7_098a9c6fbb15
0x1801005d9  call    cs:__imp_RoGetActivationFactory
0x1801005e0  nop     dword ptr [rax+rax+00h]
0x1801005e5  test    eax, eax
0x1801005e7  js      short loc_180100601
0x1801005e9  mov     rcx, [rsp+58h+var_38]
0x1801005ee  lea     rdx, ?wchTSF30Hidden@@3GA; ushort wchTSF30Hidden
0x1801005f5  mov     rax, [rcx]
0x1801005f8  mov     rax, [rax+30h]
0x1801005fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100601  mov     rcx, [rsp+58h+var_38]
0x180100606  test    rcx, rcx
0x180100609  jz      short loc_180100620
0x18010060b  mov     [rsp+58h+var_38], 0
0x180100614  mov     rax, [rcx]
0x180100617  mov     rax, [rax+10h]
0x18010061b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100620  mov     rcx, [rsp+58h+var_10]
0x180100625  xor     rcx, rsp; StackCookie
0x180100628  call    __security_check_cookie
0x18010062d  add     rsp, 50h
0x180100631  pop     rbx
0x180100632  retn
0x180100634  xor     r9d, r9d; lpArguments
0x180100637  xor     r8d, r8d; nNumberOfArguments
0x18010063a  mov     ecx, eax; dwExceptionCode
0x18010063c  lea     edx, [r9+1]; dwExceptionFlags
0x180100640  call    cs:__imp_RaiseException
0x180100647  nop     dword ptr [rax+rax+00h]
0x18010064c  int     3; Trap to Debugger
```

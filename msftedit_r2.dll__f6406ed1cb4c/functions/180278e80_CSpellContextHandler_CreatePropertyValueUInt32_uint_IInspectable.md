# CSpellContextHandler::CreatePropertyValueUInt32(uint,IInspectable * *)

- ea: `0x180278e80`
- end: `0x180278f49`
- name: `?CreatePropertyValueUInt32@CSpellContextHandler@@AEAAJIPEAPEAUIInspectable@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, unsigned int, struct IInspectable **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180278a28`

## callees

- `0x18006ad18`
- `0x18013ce80`
- `0x1801f9834`
- `0x180278e80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278ee6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278ee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278ec7`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreatePropertyValueUInt32(
        CSpellContextHandler *this,
        unsigned int a2,
        struct IInspectable **a3)
{
  int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v9; // [rsp+30h] [rbp-28h] BYREF

  *a3 = 0;
  v7 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v9, &v8) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
         v8,
         &v7);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IInspectable **))(*(_QWORD *)v7 + 88LL))(v7, a2, a3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180278e80  mov     r11, rsp
0x180278e83  mov     [r11+8], rbx
0x180278e87  mov     [r11+20h], rsi
0x180278e8b  push    rdi
0x180278e8c  sub     rsp, 50h
0x180278e90  mov     rax, cs:__security_cookie
0x180278e97  xor     rax, rsp
0x180278e9a  mov     [rsp+58h+var_10], rax
0x180278e9f  mov     rdi, r8
0x180278ea2  mov     qword ptr [r8], 0
0x180278ea9  mov     esi, edx
0x180278eab  mov     qword ptr [r11-38h], 0
0x180278eb3  lea     r8, [r11-28h]; hstringHeader
0x180278eb7  mov     edx, 20h ; ' '; length
0x180278ebc  lea     r9, [r11-30h]; string
0x180278ec0  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180278ec7  call    cs:__imp_WindowsCreateStringReference
0x180278ece  nop     dword ptr [rax+rax+00h]
0x180278ed3  test    eax, eax
0x180278ed5  jns     short loc_180278EF2
0x180278ed7  xor     r9d, r9d; lpArguments
0x180278eda  xor     r8d, r8d; nNumberOfArguments
0x180278edd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180278ee2  lea     edx, [r9+1]; dwExceptionFlags
0x180278ee6  call    cs:__imp_RaiseException
0x180278eed  nop     dword ptr [rax+rax+00h]
0x180278ef2  mov     rcx, [rsp+58h+var_30]
0x180278ef7  lea     rdx, [rsp+58h+var_38]
0x180278efc  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180278f01  mov     ebx, eax
0x180278f03  test    eax, eax
0x180278f05  js      short loc_180278F1F
0x180278f07  mov     rcx, [rsp+58h+var_38]
0x180278f0c  mov     r8, rdi
0x180278f0f  mov     edx, esi
0x180278f11  mov     rax, [rcx]
0x180278f14  mov     rax, [rax+58h]
0x180278f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278f1d  mov     ebx, eax
0x180278f1f  lea     rcx, [rsp+58h+var_38]
0x180278f24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180278f29  mov     eax, ebx
0x180278f2b  mov     rcx, [rsp+58h+var_10]
0x180278f30  xor     rcx, rsp; StackCookie
0x180278f33  call    __security_check_cookie
0x180278f38  mov     rbx, [rsp+58h+arg_0]
0x180278f3d  mov     rsi, [rsp+58h+arg_18]
0x180278f42  add     rsp, 50h
0x180278f46  pop     rdi
0x180278f47  retn
```

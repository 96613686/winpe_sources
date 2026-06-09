# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1400602b0`
- end: `0x1400602e9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `57`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006059c`

## callees

- `0x1400602b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400602dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400602dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400602c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400602c7`

## string_xrefs

- `0x1400602bb`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        const unsigned __int16 *a2)
{
  HRESULT StringReference; // eax

  StringReference = WindowsCreateStringReference(
                      L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
                      0x37u,
                      hstringHeader,
                      (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1400602b0  sub     rsp, 28h
0x1400602b4  lea     r9, [rcx+18h]; string
0x1400602b8  mov     r8, rcx; hstringHeader
0x1400602bb  lea     rcx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x1400602c2  mov     edx, 37h ; '7'; length
0x1400602c7  call    cs:__imp_WindowsCreateStringReference
0x1400602cd  test    eax, eax
0x1400602cf  jns     short loc_1400602E4
0x1400602d1  xor     r9d, r9d; lpArguments
0x1400602d4  xor     r8d, r8d; nNumberOfArguments
0x1400602d7  mov     ecx, eax; dwExceptionCode
0x1400602d9  lea     edx, [r9+1]; dwExceptionFlags
0x1400602dd  call    cs:__imp_RaiseException
0x1400602e3  int     3; Trap to Debugger
0x1400602e4  add     rsp, 28h
0x1400602e8  retn
```

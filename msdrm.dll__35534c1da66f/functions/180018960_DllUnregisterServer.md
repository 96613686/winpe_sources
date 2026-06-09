# DllUnregisterServer

- ea: `0x180018960`
- end: `0x1800189f9`
- name: `DllUnregisterServer`
- size: `153`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018981`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189c8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018981`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189c8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800189e2`

## string_xrefs

- `0x180018971`: `CLSID\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}\InProcServer32`
- `0x1800189bb`: `CLSID\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}\InProcServer32`
- `0x1800189d5`: `CLSID\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}`
- `0x1800189a1`: `CLSID\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax

  result = RegDeleteKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}\\InProcServer32", 0, 0);
  if ( (result & 0xFFFFFFFD) == 0 )
  {
    result = RegDeleteKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}", 0, 0);
    if ( (result & 0xFFFFFFFD) == 0 )
    {
      result = RegDeleteKeyExW(
                 HKEY_CLASSES_ROOT,
                 L"CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}\\InProcServer32",
                 0,
                 0);
      if ( (result & 0xFFFFFFFD) == 0 )
      {
        result = RegDeleteKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}", 0, 0);
        if ( (result & 0xFFFFFFFD) == 0 )
          return 0;
      }
    }
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180018960  mov     [rsp+arg_0], rbx
0x180018965  push    rdi
0x180018966  sub     rsp, 20h
0x18001896a  mov     rbx, 0FFFFFFFF80000000h
0x180018971  lea     rdx, SubKey; "CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36"...
0x180018978  mov     rcx, rbx; hKey
0x18001897b  xor     r9d, r9d; Reserved
0x18001897e  xor     r8d, r8d; samDesired
0x180018981  call    cs:__imp_RegDeleteKeyExW
0x180018987  mov     edi, 0FFFFFFFDh
0x18001898c  test    edi, eax
0x18001898e  jz      short loc_18001899E
0x180018990  test    eax, eax
0x180018992  jle     short loc_1800189EE
0x180018994  movzx   eax, ax
0x180018997  or      eax, 80070000h
0x18001899c  jmp     short loc_1800189EE
0x18001899e  xor     r9d, r9d; Reserved
0x1800189a1  lea     rdx, aClsidCf2cf4283_0; "CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36"...
0x1800189a8  xor     r8d, r8d; samDesired
0x1800189ab  mov     rcx, rbx; hKey
0x1800189ae  call    cs:__imp_RegDeleteKeyExW
0x1800189b4  test    edi, eax
0x1800189b6  jnz     short loc_180018990
0x1800189b8  xor     r9d, r9d; Reserved
0x1800189bb  lea     rdx, aClsidBf5cb1487; "CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70C"...
0x1800189c2  xor     r8d, r8d; samDesired
0x1800189c5  mov     rcx, rbx; hKey
0x1800189c8  call    cs:__imp_RegDeleteKeyExW
0x1800189ce  test    edi, eax
0x1800189d0  jnz     short loc_180018990
0x1800189d2  xor     r9d, r9d; Reserved
0x1800189d5  lea     rdx, aClsidBf5cb1487_0; "CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70C"...
0x1800189dc  xor     r8d, r8d; samDesired
0x1800189df  mov     rcx, rbx; hKey
0x1800189e2  call    cs:__imp_RegDeleteKeyExW
0x1800189e8  test    edi, eax
0x1800189ea  jnz     short loc_180018990
0x1800189ec  xor     eax, eax
0x1800189ee  mov     rbx, [rsp+28h+arg_0]
0x1800189f3  add     rsp, 20h
0x1800189f7  pop     rdi
0x1800189f8  retn
```

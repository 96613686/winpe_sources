# OSGetLanguageStatics

- ea: `0x18000e7f8`
- end: `0x18000e876`
- name: `OSGetLanguageStatics`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e740`

## callees

- `0x18000e7f8`
- `0x18000e87c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e836`

## pseudocode

```c
__int64 __fastcall OSGetLanguageStatics(__int64 a1)
{
  unsigned int v2; // ebx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v2 = WindowsCreateString(L"Windows.Globalization.Language", 0x1Eu, &string);
  if ( !v2 )
    v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(
           string,
           a1);
  WindowsDeleteString(string);
  return v2;
}

```

## disassembly

```asm
0x18000e7f8  mov     [rsp+arg_0], rbx
0x18000e7fd  push    rdi
0x18000e7fe  sub     rsp, 20h
0x18000e802  mov     rdi, rcx
0x18000e805  mov     [rsp+28h+string], 0
0x18000e80e  xor     ecx, ecx; string
0x18000e810  call    cs:__imp_WindowsDeleteString
0x18000e817  nop     dword ptr [rax+rax+00h]
0x18000e81c  lea     r8, [rsp+28h+string]; string
0x18000e821  mov     [rsp+28h+string], 0
0x18000e82a  mov     edx, 1Eh; length
0x18000e82f  lea     rcx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x18000e836  call    cs:__imp_WindowsCreateString
0x18000e83d  nop     dword ptr [rax+rax+00h]
0x18000e842  mov     ebx, eax
0x18000e844  test    eax, eax
0x18000e846  jnz     short loc_18000E857
0x18000e848  mov     rcx, [rsp+28h+string]
0x18000e84d  mov     rdx, rdi
0x18000e850  call    ??$GetActivationFactory@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>)
0x18000e855  mov     ebx, eax
0x18000e857  mov     rcx, [rsp+28h+string]; string
0x18000e85c  call    cs:__imp_WindowsDeleteString
0x18000e863  nop     dword ptr [rax+rax+00h]
0x18000e868  mov     eax, ebx
0x18000e86a  mov     rbx, [rsp+28h+arg_0]
0x18000e86f  add     rsp, 20h
0x18000e873  pop     rdi
0x18000e874  retn
```

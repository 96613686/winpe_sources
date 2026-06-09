# OSGetTextServicesManagerStatics

- ea: `0x1800d0ba0`
- end: `0x1800d0c37`
- name: `OSGetTextServicesManagerStatics`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d0a40`

## callees

- `0x18006ad18`
- `0x1800d0ba0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d0c0a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d0c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d0bde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d0bde`

## string_xrefs

- `0x1800d0bd7`: `Windows.UI.Text.Core.CoreTextServicesManager`

## pseudocode

```c
__int64 __fastcall OSGetTextServicesManagerStatics(__int64 a1)
{
  unsigned int ActivationFactory; // ebx
  HSTRING v3; // rbx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.UI.Text.Core.CoreTextServicesManager", 0x2Cu, &string);
  if ( !ActivationFactory )
  {
    v3 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    ActivationFactory = RoGetActivationFactory(v3, &GUID_1520a388_e2cf_4d65_aeb9_b32d86fe39b9, a1);
  }
  WindowsDeleteString(string);
  return ActivationFactory;
}

```

## disassembly

```asm
0x1800d0ba0  mov     [rsp+arg_0], rbx
0x1800d0ba5  push    rdi
0x1800d0ba6  sub     rsp, 20h
0x1800d0baa  mov     rdi, rcx
0x1800d0bad  mov     [rsp+28h+string], 0
0x1800d0bb6  xor     ecx, ecx; string
0x1800d0bb8  call    cs:__imp_WindowsDeleteString
0x1800d0bbf  nop     dword ptr [rax+rax+00h]
0x1800d0bc4  lea     r8, [rsp+28h+string]; string
0x1800d0bc9  mov     [rsp+28h+string], 0
0x1800d0bd2  mov     edx, 2Ch ; ','; length
0x1800d0bd7  lea     rcx, ?RuntimeClass_Windows_UI_Text_Core_CoreTextServicesManager@@3QBGB; "Windows.UI.Text.Core.CoreTextServicesMa"...
0x1800d0bde  call    cs:__imp_WindowsCreateString
0x1800d0be5  nop     dword ptr [rax+rax+00h]
0x1800d0bea  mov     ebx, eax
0x1800d0bec  test    eax, eax
0x1800d0bee  jnz     short loc_1800D0C18
0x1800d0bf0  mov     rbx, [rsp+28h+string]
0x1800d0bf5  mov     rcx, rdi
0x1800d0bf8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d0bfd  mov     r8, rdi
0x1800d0c00  lea     rdx, _GUID_1520a388_e2cf_4d65_aeb9_b32d86fe39b9
0x1800d0c07  mov     rcx, rbx
0x1800d0c0a  call    cs:__imp_RoGetActivationFactory
0x1800d0c11  nop     dword ptr [rax+rax+00h]
0x1800d0c16  mov     ebx, eax
0x1800d0c18  mov     rcx, [rsp+28h+string]; string
0x1800d0c1d  call    cs:__imp_WindowsDeleteString
0x1800d0c24  nop     dword ptr [rax+rax+00h]
0x1800d0c29  mov     eax, ebx
0x1800d0c2b  mov     rbx, [rsp+28h+arg_0]
0x1800d0c30  add     rsp, 20h
0x1800d0c34  pop     rdi
0x1800d0c35  retn
```

# OSGetClipboardStatics

- ea: `0x1801f9cc8`
- end: `0x1801f9d42`
- name: `OSGetClipboardStatics`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801f9b5c`

## callees

- `0x18006ad18`
- `0x18006af48`
- `0x1801f9cc8`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f9d15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f9d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9d28`

## pseudocode

```c
__int64 __fastcall OSGetClipboardStatics(__int64 a1)
{
  unsigned int ActivationFactory; // ebx
  HSTRING v3; // rbx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  ActivationFactory = Microsoft::WRL::Wrappers::HString::Set(
                        &string,
                        L"Windows.ApplicationModel.DataTransfer.Clipboard",
                        0x2Fu);
  if ( !ActivationFactory )
  {
    v3 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    ActivationFactory = RoGetActivationFactory(v3, &GUID_c627e291_34e2_4963_8eed_93cbb0ea3d70, a1);
  }
  WindowsDeleteString(string);
  return ActivationFactory;
}

```

## disassembly

```asm
0x1801f9cc8  mov     [rsp+arg_0], rbx
0x1801f9ccd  push    rdi
0x1801f9cce  sub     rsp, 20h
0x1801f9cd2  mov     rdi, rcx
0x1801f9cd5  mov     [rsp+28h+string], 0
0x1801f9cde  lea     rcx, [rsp+28h+string]; this
0x1801f9ce3  mov     r8d, 2Fh ; '/'; unsigned int
0x1801f9ce9  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_Clipboard@@3QBGB; "Windows.ApplicationModel.DataTransfer.C"...
0x1801f9cf0  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801f9cf5  mov     ebx, eax
0x1801f9cf7  test    eax, eax
0x1801f9cf9  jnz     short loc_1801F9D23
0x1801f9cfb  mov     rbx, [rsp+28h+string]
0x1801f9d00  mov     rcx, rdi
0x1801f9d03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f9d08  mov     r8, rdi
0x1801f9d0b  lea     rdx, _GUID_c627e291_34e2_4963_8eed_93cbb0ea3d70
0x1801f9d12  mov     rcx, rbx
0x1801f9d15  call    cs:__imp_RoGetActivationFactory
0x1801f9d1c  nop     dword ptr [rax+rax+00h]
0x1801f9d21  mov     ebx, eax
0x1801f9d23  mov     rcx, [rsp+28h+string]; string
0x1801f9d28  call    cs:__imp_WindowsDeleteString
0x1801f9d2f  nop     dword ptr [rax+rax+00h]
0x1801f9d34  mov     eax, ebx
0x1801f9d36  mov     rbx, [rsp+28h+arg_0]
0x1801f9d3b  add     rsp, 20h
0x1801f9d3f  pop     rdi
0x1801f9d40  retn
```

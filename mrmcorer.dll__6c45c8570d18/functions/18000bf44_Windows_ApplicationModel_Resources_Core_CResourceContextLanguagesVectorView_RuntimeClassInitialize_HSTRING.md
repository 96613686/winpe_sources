# Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView::RuntimeClassInitialize(HSTRING__ *)

- ea: `0x18000bf44`
- end: `0x18000bfb9`
- name: `?RuntimeClassInitialize@CResourceContextLanguagesVectorView@Core@Resources@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `117`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be7c`

## callees

- `0x18000bf44`
- `0x18000c010`
- `0x18000c8a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bfaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bfaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000bf6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000bf6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView::RuntimeClassInitialize(
        struct Microsoft::Resources::Runtime::CContext::CLanguagesVectorView **this,
        HSTRING a2)
{
  HRESULT v3; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v5; // edi
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF
  HSTRING newString; // [rsp+40h] [rbp+18h] BYREF

  string = 0;
  newString = 0;
  v3 = WindowsDuplicateString(a2, &newString);
  Windows::Internal::String::FreeAndAssignOnSuccess(v3, newString, &string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = Microsoft::Resources::Runtime::CContext::CLanguagesVectorView::New(StringRawBuffer, this + 9);
  if ( string )
    WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18000bf44  push    rdi
0x18000bf46  sub     rsp, 20h
0x18000bf4a  mov     rax, rdx
0x18000bf4d  mov     rdi, rcx
0x18000bf50  mov     [rsp+28h+string], 0
0x18000bf59  mov     [rsp+28h+newString], 0
0x18000bf62  lea     rdx, [rsp+28h+newString]; newString
0x18000bf67  mov     rcx, rax; string
0x18000bf6a  call    cs:__imp_WindowsDuplicateString
0x18000bf70  lea     r8, [rsp+28h+string]; HSTRING *
0x18000bf75  mov     rdx, [rsp+28h+newString]; HSTRING
0x18000bf7a  mov     ecx, eax; int
0x18000bf7c  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18000bf81  nop
0x18000bf82  xor     edx, edx; length
0x18000bf84  mov     rcx, [rsp+28h+string]; string
0x18000bf89  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bf8f  lea     rdx, [rdi+48h]; struct Microsoft::Resources::Runtime::CContext::CLanguagesVectorView **
0x18000bf93  mov     rcx, rax; unsigned __int16 *
0x18000bf96  call    ?New@CLanguagesVectorView@CContext@Runtime@Resources@Microsoft@@SAJPEBGPEAPEAV12345@@Z; Microsoft::Resources::Runtime::CContext::CLanguagesVectorView::New(ushort const *,Microsoft::Resources::Runtime::CContext::CLanguagesVectorView * *)
0x18000bf9b  mov     edi, eax
0x18000bf9d  cmp     [rsp+28h+string], 0
0x18000bfa3  jz      short loc_18000BFB1
0x18000bfa5  mov     rcx, [rsp+28h+string]; string
0x18000bfaa  call    cs:__imp_WindowsDeleteString
0x18000bfb0  nop
0x18000bfb1  mov     eax, edi
0x18000bfb3  add     rsp, 20h
0x18000bfb7  pop     rdi
0x18000bfb8  retn
```

# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180012a24`
- end: `0x180012a9f`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `40`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011874`
- `0x180011cc8`
- `0x1800127ec`
- `0x180014190`
- `0x180015c1c`
- `0x18001c010`
- `0x18001c1b4`
- `0x1800224b4`
- `0x1800275dc`
- `0x180027778`
- `0x18003c7ec`
- `0x18004c758`
- `0x18004c810`
- `0x18004c8c8`
- `0x18004c980`
- `0x18004ca38`
- `0x18004caf0`
- `0x18004cba8`
- `0x18004cc60`
- `0x18004cd18`
- `0x18004cdd0`
- `0x18004ce88`
- `0x18004cf40`
- `0x18004cff8`
- `0x18004d0b0`
- `0x18004d168`
- `0x18004d220`
- `0x18004d2d8`
- `0x18004d390`
- `0x18004d448`
- `0x18004d500`
- `0x180054770`
- `0x180054828`
- `0x180056a28`
- `0x180056e2c`
- `0x180060b18`
- `0x180063928`
- `0x18006ca08`
- `0x18006eb40`
- `0x180071028`

## callees

- `0x180012a24`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012a5e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012a74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012a98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012a74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012a98`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  HSTRING *v2; // r9
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdx
  HRESULT StringReference; // eax

  v2 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v4 = *a2;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  if ( v5 > 0xFFFFFFFF || (int)v5 + 1 < (unsigned int)v5 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180012A9ELL);
  }
  StringReference = WindowsCreateStringReference(v4, v5, a1, v2);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x180012a24  mov     [rsp+arg_0], rbx
0x180012a29  push    rdi
0x180012a2a  sub     rsp, 20h
0x180012a2e  lea     r9, [rcx+18h]; string
0x180012a32  xor     edi, edi
0x180012a34  mov     [r9], rdi
0x180012a37  mov     rbx, rcx
0x180012a3a  mov     rcx, [rdx]; sourceString
0x180012a3d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012a41  inc     rdx; length
0x180012a44  cmp     [rcx+rdx*2], di
0x180012a48  jnz     short loc_180012A41
0x180012a4a  mov     eax, 0FFFFFFFFh
0x180012a4f  cmp     rdx, rax
0x180012a52  ja      short loc_180012A89
0x180012a54  lea     eax, [rdx+1]
0x180012a57  cmp     eax, edx
0x180012a59  jb      short loc_180012A89
0x180012a5b  mov     r8, rbx; hstringHeader
0x180012a5e  call    cs:__imp_WindowsCreateStringReference
0x180012a64  test    eax, eax
0x180012a66  jns     short loc_180012A7B
0x180012a68  xor     r9d, r9d; lpArguments
0x180012a6b  xor     r8d, r8d; nNumberOfArguments
0x180012a6e  mov     ecx, eax; dwExceptionCode
0x180012a70  lea     edx, [r9+1]; dwExceptionFlags
0x180012a74  call    cs:__imp_RaiseException
0x180012a7a  int     3; Trap to Debugger
0x180012a7b  mov     rax, rbx
0x180012a7e  mov     rbx, [rsp+28h+arg_0]
0x180012a83  add     rsp, 20h
0x180012a87  pop     rdi
0x180012a88  retn
0x180012a89  xor     r9d, r9d; lpArguments
0x180012a8c  xor     r8d, r8d; nNumberOfArguments
0x180012a8f  mov     ecx, 80070216h; dwExceptionCode
0x180012a94  lea     edx, [r9+1]; dwExceptionFlags
0x180012a98  call    cs:__imp_RaiseException
```

# GetBooleanAttribute(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,uchar *)

- ea: `0x180057c44`
- end: `0x180057dab`
- name: `?GetBooleanAttribute@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAE@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct IInspectable *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180057ab4`

## callees

- `0x180025dd4`
- `0x18005251c`
- `0x180057c44`
- `0x180057db4`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057cd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180057ce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180057d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180057ce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180057d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180057cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057d87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetBooleanAttribute(struct IInspectable *a1, unsigned __int16 *a2, bool *a3)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  bool v9; // bl
  HRESULT v10; // eax
  HRESULT v11; // edi
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  INT32 result; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string1; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a3 = 0;
  WindowsDeleteString(0);
  string1 = 0;
  if ( (int)LookupStringInPropertySet(a1, a2, &string1) >= 0 )
  {
    result = 0;
    string = 0;
    v6 = WindowsCreateStringReference(L"true", 4u, &hstringHeader, &string);
    if ( v6 < 0 )
    {
      RaiseException(v6, 1u, 0, 0);
      __debugbreak();
    }
    v7 = WindowsCompareStringOrdinal(string1, string, &result);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v7,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_9:
      WindowsDeleteString(string1);
      return v8;
    }
    v9 = 1;
    if ( result )
    {
      string = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"1", 2u, 1u);
      v10 = WindowsCompareStringOrdinal(string1, string, &result);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v10,
          (int)hstringHeader.Reserved.Reserved1);
        v8 = v11;
        goto LABEL_9;
      }
      v9 = result == 0;
    }
    *a3 = v9;
  }
  WindowsDeleteString(string1);
  return 0;
}

```

## disassembly

```asm
0x180057c44  mov     [rsp-18h+arg_18], rbx
0x180057c49  push    rbp
0x180057c4a  push    rsi
0x180057c4b  push    rdi
0x180057c4c  mov     rbp, rsp
0x180057c4f  sub     rsp, 60h
0x180057c53  mov     rax, cs:__security_cookie
0x180057c5a  xor     rax, rsp
0x180057c5d  mov     [rbp+var_10], rax
0x180057c61  mov     rsi, r8
0x180057c64  mov     rdi, rdx
0x180057c67  mov     rbx, rcx
0x180057c6a  mov     byte ptr [r8], 0
0x180057c6e  mov     [rbp+string1], 0
0x180057c76  xor     ecx, ecx; string
0x180057c78  call    cs:__imp_WindowsDeleteString
0x180057c7e  mov     [rbp+string1], 0
0x180057c86  lea     r8, [rbp+string1]; HSTRING *
0x180057c8a  mov     rdx, rdi; unsigned __int16 *
0x180057c8d  mov     rcx, rbx; struct IInspectable *
0x180057c90  call    ?LookupStringInPropertySet@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x180057c95  test    eax, eax
0x180057c97  js      loc_180057D83
0x180057c9d  mov     [rbp+result], 0
0x180057ca4  mov     [rbp+string], 0
0x180057cac  lea     r9, [rbp+string]; string
0x180057cb0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180057cb4  mov     edx, 4; length
0x180057cb9  lea     rcx, sourceString; "true"
0x180057cc0  call    cs:__imp_WindowsCreateStringReference
0x180057cc6  test    eax, eax
0x180057cc8  jns     short loc_180057CDD
0x180057cca  xor     r9d, r9d; lpArguments
0x180057ccd  xor     r8d, r8d; nNumberOfArguments
0x180057cd0  lea     edx, [r9+1]; dwExceptionFlags
0x180057cd4  mov     ecx, eax; dwExceptionCode
0x180057cd6  call    cs:__imp_RaiseException
0x180057cdc  int     3; Trap to Debugger
0x180057cdd  lea     r8, [rbp+result]; result
0x180057ce1  mov     rdx, [rbp+string]; string2
0x180057ce5  mov     rcx, [rbp+string1]; string1
0x180057ce9  call    cs:__imp_WindowsCompareStringOrdinal
0x180057cef  mov     ebx, eax
0x180057cf1  test    eax, eax
0x180057cf3  jns     short loc_180057D0F
0x180057cf5  mov     rcx, [rbp+18h]; this
0x180057cf9  mov     r9d, eax; char *
0x180057cfc  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180057d03  mov     edx, 114h; void *
0x180057d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d0d  jmp     short loc_180057D6B
0x180057d0f  mov     ebx, 1
0x180057d14  cmp     [rbp+result], 0
0x180057d18  jz      short loc_180057D81
0x180057d1a  mov     [rbp+string], 0
0x180057d22  mov     r9d, ebx; unsigned int
0x180057d25  lea     r8d, [rbx+1]; unsigned int
0x180057d29  lea     rdx, a1; "1"
0x180057d30  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180057d34  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180057d39  lea     r8, [rbp+result]; result
0x180057d3d  mov     rdx, [rbp+string]; string2
0x180057d41  mov     rcx, [rbp+string1]; string1
0x180057d45  call    cs:__imp_WindowsCompareStringOrdinal
0x180057d4b  mov     edi, eax
0x180057d4d  test    eax, eax
0x180057d4f  jns     short loc_180057D79
0x180057d51  mov     rcx, [rbp+18h]; this
0x180057d55  mov     r9d, eax; char *
0x180057d58  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180057d5f  mov     edx, 117h; void *
0x180057d64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d69  mov     ebx, edi
0x180057d6b  mov     rcx, [rbp+string1]; string
0x180057d6f  call    cs:__imp_WindowsDeleteString
0x180057d75  mov     eax, ebx
0x180057d77  jmp     short loc_180057D8F
0x180057d79  cmp     [rbp+result], 0
0x180057d7d  jz      short loc_180057D81
0x180057d7f  xor     bl, bl
0x180057d81  mov     [rsi], bl
0x180057d83  mov     rcx, [rbp+string1]; string
0x180057d87  call    cs:__imp_WindowsDeleteString
0x180057d8d  xor     eax, eax
0x180057d8f  mov     rcx, [rbp+var_10]
0x180057d93  xor     rcx, rsp; StackCookie
0x180057d96  call    __security_check_cookie
0x180057d9b  mov     rbx, [rsp+60h+arg_18]
0x180057da3  add     rsp, 60h
0x180057da7  pop     rdi
0x180057da8  pop     rsi
0x180057da9  pop     rbp
0x180057daa  retn
```

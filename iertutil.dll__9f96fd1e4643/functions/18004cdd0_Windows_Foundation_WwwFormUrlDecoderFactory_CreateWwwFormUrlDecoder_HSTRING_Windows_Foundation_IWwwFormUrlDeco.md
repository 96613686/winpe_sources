# Windows::Foundation::WwwFormUrlDecoderFactory::CreateWwwFormUrlDecoder(HSTRING__ *,Windows::Foundation::IWwwFormUrlDecoderRuntimeClass * *)

- ea: `0x18004cdd0`
- end: `0x18004ceb4`
- name: `?CreateWwwFormUrlDecoder@WwwFormUrlDecoderFactory@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIWwwFormUrlDecoderRuntimeClass@23@@Z`
- size: `228`
- prototype: `int(Windows::Foundation::WwwFormUrlDecoderFactory *__hidden this, HSTRING, struct Windows::Foundation::IWwwFormUrlDecoderRuntimeClass **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180026610`
- `0x180045dcc`
- `0x180045e10`
- `0x18004cdd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ce47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004ce47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ce01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ce01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce97`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::WwwFormUrlDecoderFactory::CreateWwwFormUrlDecoder(
        Windows::Foundation::WwwFormUrlDecoderFactory *this,
        HSTRING a2,
        struct Windows::Foundation::IWwwFormUrlDecoderRuntimeClass **a3)
{
  HSTRING v4; // rbp
  HSTRING v5; // rbx
  int Instance; // esi
  HRESULT v7; // eax
  int v8; // eax
  HSTRING v10; // [rsp+20h] [rbp-28h] BYREF
  HSTRING string1; // [rsp+58h] [rbp+10h] BYREF
  HSTRING newString; // [rsp+68h] [rbp+20h] BYREF

  v4 = a2;
  if ( a2 && a3 )
  {
    v5 = 0;
    v10 = 0;
    if ( *WindowsGetStringRawBuffer(a2, 0) == 63 )
      goto LABEL_10;
    string1 = 0;
    Instance = Windows::Internal::String::Initialize(&string1, L"?", 1u);
    if ( Instance >= 0 )
    {
      WindowsDeleteString(0);
      newString = 0;
      v7 = WindowsConcatString(string1, v4, &newString);
      v8 = Windows::Internal::String::FreeAndAssignOnSuccess(v7, newString, &v10);
      v5 = v10;
      Instance = v8;
      if ( v8 >= 0 )
        v4 = v10;
    }
    if ( string1 )
      WindowsDeleteString(string1);
    if ( Instance >= 0 )
LABEL_10:
      Instance = Windows::Foundation::WwwFormUrlDecoder::CreateInstance(v4, a3);
    if ( v5 )
      WindowsDeleteString(v5);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004cdd0  mov     [rsp+arg_0], rbx
0x18004cdd5  push    rbp
0x18004cdd6  push    rsi
0x18004cdd7  push    r14
0x18004cdd9  sub     rsp, 30h
0x18004cddd  mov     r14, r8
0x18004cde0  mov     rbp, rdx
0x18004cde3  test    rdx, rdx
0x18004cde6  jz      loc_18004CE9F
0x18004cdec  test    r8, r8
0x18004cdef  jz      loc_18004CE9F
0x18004cdf5  xor     ebx, ebx
0x18004cdf7  xor     edx, edx; length
0x18004cdf9  mov     rcx, rbp; string
0x18004cdfc  mov     [rsp+48h+var_28], rbx
0x18004ce01  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ce07  cmp     word ptr [rax], 3Fh ; '?'
0x18004ce0b  jz      short loc_18004CE82
0x18004ce0d  lea     r8d, [rbx+1]; length
0x18004ce11  mov     [rsp+48h+string1], rbx
0x18004ce16  lea     rdx, asc_1801FB6E0; "?"
0x18004ce1d  lea     rcx, [rsp+48h+string1]; this
0x18004ce22  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18004ce27  mov     esi, eax
0x18004ce29  test    eax, eax
0x18004ce2b  js      short loc_18004CE6B
0x18004ce2d  xor     ecx, ecx; string
0x18004ce2f  call    cs:__imp_WindowsDeleteString
0x18004ce35  mov     rcx, [rsp+48h+string1]; string1
0x18004ce3a  lea     r8, [rsp+48h+newString]; newString
0x18004ce3f  mov     rdx, rbp; string2
0x18004ce42  mov     [rsp+48h+newString], rbx
0x18004ce47  call    cs:__imp_WindowsConcatString
0x18004ce4d  mov     rdx, [rsp+48h+newString]; HSTRING
0x18004ce52  lea     r8, [rsp+48h+var_28]; HSTRING *
0x18004ce57  mov     ecx, eax; int
0x18004ce59  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18004ce5e  mov     rbx, [rsp+48h+var_28]
0x18004ce63  test    eax, eax
0x18004ce65  mov     esi, eax
0x18004ce67  cmovns  rbp, rbx
0x18004ce6b  cmp     [rsp+48h+string1], 0
0x18004ce71  jz      short loc_18004CE7E
0x18004ce73  mov     rcx, [rsp+48h+string1]; string
0x18004ce78  call    cs:__imp_WindowsDeleteString
0x18004ce7e  test    esi, esi
0x18004ce80  js      short loc_18004CE8F
0x18004ce82  mov     rdx, r14; struct Windows::Foundation::IWwwFormUrlDecoderRuntimeClass **
0x18004ce85  mov     rcx, rbp; HSTRING
0x18004ce88  call    ?CreateInstance@WwwFormUrlDecoder@Foundation@Windows@@SAJPEAUHSTRING__@@PEAPEAUIWwwFormUrlDecoderRuntimeClass@23@@Z; Windows::Foundation::WwwFormUrlDecoder::CreateInstance(HSTRING__ *,Windows::Foundation::IWwwFormUrlDecoderRuntimeClass * *)
0x18004ce8d  mov     esi, eax
0x18004ce8f  test    rbx, rbx
0x18004ce92  jz      short loc_18004CEA4
0x18004ce94  mov     rcx, rbx; string
0x18004ce97  call    cs:__imp_WindowsDeleteString
0x18004ce9d  jmp     short loc_18004CEA4
0x18004ce9f  mov     esi, 80004003h
0x18004cea4  mov     rbx, [rsp+48h+arg_0]
0x18004cea9  mov     eax, esi
0x18004ceab  add     rsp, 30h
0x18004ceaf  pop     r14
0x18004ceb1  pop     rsi
0x18004ceb2  pop     rbp
0x18004ceb3  retn
```

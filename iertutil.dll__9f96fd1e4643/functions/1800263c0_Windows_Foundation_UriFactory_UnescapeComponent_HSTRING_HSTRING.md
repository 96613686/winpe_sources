# Windows::Foundation::UriFactory::UnescapeComponent(HSTRING__ *,HSTRING__ * *)

- ea: `0x1800263c0`
- end: `0x18002653c`
- name: `?UnescapeComponent@UriFactory@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `380`
- prototype: `__int64 __fastcall(Windows::Foundation::UriFactory *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800263c0`
- `0x180026544`
- `0x180083c10`
- `0x180083cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026500`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026500`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800264ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026523`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800264ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026523`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026531`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18002640a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18002640a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026493`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002651b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002651b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::UriFactory::UnescapeComponent(
        Windows::Foundation::UriFactory *this,
        HSTRING a2,
        HSTRING *a3)
{
  HRESULT HasEmbeddedNull; // edi
  UINT32 v6; // eax
  unsigned __int16 *v7; // rsi
  unsigned __int16 *StringRawBuffer; // rax
  HSTRING v9; // rbx
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  BOOL hasEmbedNull; // [rsp+20h] [rbp-1088h] BYREF
  UINT32 length; // [rsp+24h] [rbp-1084h] BYREF
  HSTRING string; // [rsp+28h] [rbp-1080h] BYREF
  WCHAR sourceString[2088]; // [rsp+30h] [rbp-1078h] BYREF

  *a3 = 0;
  hasEmbedNull = 0;
  HasEmbeddedNull = WindowsStringHasEmbeddedNull(a2, &hasEmbedNull);
  if ( HasEmbeddedNull >= 0 )
  {
    if ( hasEmbedNull )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v6 = WindowsGetStringLen(a2) + 1;
      length = v6;
      if ( v6 > 0x824 )
      {
        v11 = 2LL * v6;
        if ( !is_mul_ok(v6, 2u) )
          v11 = -1;
        ProcessHeap = GetProcessHeap();
        v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v11);
        if ( !v7 )
        {
          HasEmbeddedNull = -2147024882;
          RoOriginateError(2147942414LL, 0);
          return (unsigned int)HasEmbeddedNull;
        }
      }
      else
      {
        v7 = sourceString;
      }
      StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a2, 0);
      HasEmbeddedNull = IE_UrlUnescapeW(StringRawBuffer, v7, &length, 0x40000u);
      if ( HasEmbeddedNull >= 0 )
      {
        string = 0;
        HasEmbeddedNull = WindowsCreateString(v7, length, &string);
        if ( HasEmbeddedNull >= 0 )
        {
          v9 = string;
          WindowsDeleteString(0);
          *a3 = v9;
        }
      }
      if ( v7 != sourceString )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v7);
      }
    }
  }
  return (unsigned int)HasEmbeddedNull;
}

```

## disassembly

```asm
0x1800263c0  mov     [rsp+arg_0], rbx
0x1800263c5  mov     [rsp+arg_18], rbp
0x1800263ca  push    rsi
0x1800263cb  push    rdi
0x1800263cc  push    r14
0x1800263ce  mov     eax, 1090h
0x1800263d3  call    _alloca_probe
0x1800263d8  sub     rsp, rax
0x1800263db  mov     rax, cs:__security_cookie
0x1800263e2  xor     rax, rsp
0x1800263e5  mov     [rsp+10A8h+var_28], rax
0x1800263ed  mov     rbp, rdx
0x1800263f0  mov     qword ptr [r8], 0
0x1800263f7  mov     rcx, rbp; string
0x1800263fa  mov     [rsp+10A8h+hasEmbedNull], 0
0x180026402  lea     rdx, [rsp+10A8h+hasEmbedNull]; hasEmbedNull
0x180026407  mov     r14, r8
0x18002640a  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180026410  mov     edi, eax
0x180026412  test    eax, eax
0x180026414  js      loc_1800264A6
0x18002641a  cmp     [rsp+10A8h+hasEmbedNull], 0
0x18002641f  jnz     loc_1800264D0
0x180026425  mov     rcx, rbp; string
0x180026428  call    cs:__imp_WindowsGetStringLen
0x18002642e  inc     eax
0x180026430  mov     [rsp+10A8h+length], eax
0x180026434  cmp     eax, 824h
0x180026439  ja      loc_1800264D7
0x18002643f  lea     rsi, [rsp+10A8h+sourceString]
0x180026444  xor     edx, edx; length
0x180026446  mov     rcx, rbp; string
0x180026449  call    cs:__imp_WindowsGetStringRawBuffer
0x18002644f  mov     r9d, 40000h; unsigned int
0x180026455  lea     r8, [rsp+10A8h+length]; unsigned int *
0x18002645a  mov     rcx, rax; unsigned __int16 *
0x18002645d  mov     rdx, rsi; unsigned __int16 *
0x180026460  call    ?IE_UrlUnescapeW@@YAJPEAG0PEAKK@Z; IE_UrlUnescapeW(ushort *,ushort *,ulong *,ulong)
0x180026465  mov     edi, eax
0x180026467  test    eax, eax
0x180026469  js      short loc_18002649C
0x18002646b  mov     edx, [rsp+10A8h+length]; length
0x18002646f  lea     r8, [rsp+10A8h+string]; string
0x180026474  mov     rcx, rsi; sourceString
0x180026477  mov     [rsp+10A8h+string], 0
0x180026480  call    cs:__imp_WindowsCreateString
0x180026486  mov     edi, eax
0x180026488  test    eax, eax
0x18002648a  js      short loc_18002649C
0x18002648c  mov     rbx, [rsp+10A8h+string]
0x180026491  xor     ecx, ecx; string
0x180026493  call    cs:__imp_WindowsDeleteString
0x180026499  mov     [r14], rbx
0x18002649c  lea     rax, [rsp+10A8h+sourceString]
0x1800264a1  cmp     rsi, rax
0x1800264a4  jnz     short loc_180026523
0x1800264a6  mov     eax, edi
0x1800264a8  mov     rcx, [rsp+10A8h+var_28]
0x1800264b0  xor     rcx, rsp; StackCookie
0x1800264b3  call    __security_check_cookie
0x1800264b8  lea     r11, [rsp+10A8h+var_18]
0x1800264c0  mov     rbx, [r11+20h]
0x1800264c4  mov     rbp, [r11+38h]
0x1800264c8  mov     rsp, r11
0x1800264cb  pop     r14
0x1800264cd  pop     rdi
0x1800264ce  pop     rsi
0x1800264cf  retn
0x1800264d0  mov     edi, 80070057h
0x1800264d5  jmp     short loc_1800264A6
0x1800264d7  mov     ecx, eax
0x1800264d9  mov     eax, 2
0x1800264de  mul     rcx
0x1800264e1  mov     rbx, rax
0x1800264e4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800264eb  cmovb   rbx, rax
0x1800264ef  call    cs:__imp_GetProcessHeap
0x1800264f5  mov     r8, rbx; dwBytes
0x1800264f8  mov     edx, 8; dwFlags
0x1800264fd  mov     rcx, rax; hHeap
0x180026500  call    cs:__imp_HeapAlloc
0x180026506  mov     rsi, rax
0x180026509  test    rax, rax
0x18002650c  jnz     loc_180026444
0x180026512  mov     edi, 8007000Eh
0x180026517  xor     edx, edx
0x180026519  mov     ecx, edi
0x18002651b  call    cs:__imp_RoOriginateError
0x180026521  jmp     short loc_1800264A6
0x180026523  call    cs:__imp_GetProcessHeap
0x180026529  mov     r8, rsi; lpMem
0x18002652c  xor     edx, edx; dwFlags
0x18002652e  mov     rcx, rax; hHeap
0x180026531  call    cs:__imp_HeapFree
0x180026537  jmp     loc_1800264A6
```

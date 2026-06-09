# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1401c9708`
- end: `0x1401c97dc`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1401c9f80`

## callees

- `0x1401c9708`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1401c9751`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1401c9751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c976b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c97b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c97c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c976b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c97b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c97c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1401c9781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1401c9781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1401c979a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1401c979a`

## pseudocode

```c
__int64 __fastcall SplitActionAndServiceId(HSTRING string, HSTRING *a2, HSTRING *a3)
{
  unsigned int v5; // edi
  const wchar_t *StringRawBuffer; // rax
  size_t v7; // r14
  HRESULT v8; // eax
  HSTRING stringa; // [rsp+48h] [rbp+28h] BYREF
  HSTRING *length; // [rsp+50h] [rbp+30h] BYREF

  length = a3;
  if ( a2 )
    *a2 = 0;
  v5 = 0;
  stringa = 0;
  LODWORD(length) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v7 = wcscspn(StringRawBuffer, L"+");
  if ( a2 )
  {
    if ( v7 >= (unsigned int)length )
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsDuplicateString(string, &stringa);
    }
    else
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsSubstringWithSpecifiedLength(string, 0, v7, &stringa);
    }
    v5 = v8;
    if ( v8 >= 0 )
    {
      *a2 = stringa;
      stringa = 0;
    }
  }
  WindowsDeleteString(0);
  WindowsDeleteString(stringa);
  return v5;
}

```

## disassembly

```asm
0x1401c9708  mov     [rsp-18h+arg_0], rbx
0x1401c970d  mov     [rsp-18h+arg_18], rsi
0x1401c9712  mov     [rsp-18h+length], r8
0x1401c9717  push    rbp
0x1401c9718  push    rdi
0x1401c9719  push    r14
0x1401c971b  mov     rbp, rsp
0x1401c971e  sub     rsp, 20h
0x1401c9722  mov     rbx, rdx
0x1401c9725  mov     rsi, rcx
0x1401c9728  test    rdx, rdx
0x1401c972b  jz      short loc_1401C9734
0x1401c972d  mov     qword ptr [rdx], 0
0x1401c9734  xor     edi, edi
0x1401c9736  lea     rdx, [rbp+length]; length
0x1401c973a  mov     [rbp+string], rdi
0x1401c973e  mov     dword ptr [rbp+length], edi
0x1401c9741  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c9747  mov     rcx, rax; String
0x1401c974a  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1401c9751  call    cs:__imp_wcscspn
0x1401c9757  mov     r14, rax
0x1401c975a  test    rbx, rbx
0x1401c975d  jz      short loc_1401C97B5
0x1401c975f  mov     eax, dword ptr [rbp+length]
0x1401c9762  mov     rcx, [rbp+string]; string
0x1401c9766  cmp     r14, rax
0x1401c9769  jnb     short loc_1401C9789
0x1401c976b  call    cs:__imp_WindowsDeleteString
0x1401c9771  mov     r8d, r14d; length
0x1401c9774  mov     [rbp+string], rdi
0x1401c9778  lea     r9, [rbp+string]; newString
0x1401c977c  xor     edx, edx; startIndex
0x1401c977e  mov     rcx, rsi; string
0x1401c9781  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1401c9787  jmp     short loc_1401C97A0
0x1401c9789  call    cs:__imp_WindowsDeleteString
0x1401c978f  lea     rdx, [rbp+string]; newString
0x1401c9793  mov     [rbp+string], rdi
0x1401c9797  mov     rcx, rsi; string
0x1401c979a  call    cs:__imp_WindowsDuplicateString
0x1401c97a0  mov     edi, eax
0x1401c97a2  test    eax, eax
0x1401c97a4  js      short loc_1401C97B5
0x1401c97a6  mov     rax, [rbp+string]
0x1401c97aa  mov     [rbx], rax
0x1401c97ad  mov     [rbp+string], 0
0x1401c97b5  xor     ecx, ecx; string
0x1401c97b7  call    cs:__imp_WindowsDeleteString
0x1401c97bd  mov     rcx, [rbp+string]; string
0x1401c97c1  call    cs:__imp_WindowsDeleteString
0x1401c97c7  mov     rbx, [rsp+20h+arg_0]
0x1401c97cc  mov     eax, edi
0x1401c97ce  mov     rsi, [rsp+20h+arg_18]
0x1401c97d3  add     rsp, 20h
0x1401c97d7  pop     r14
0x1401c97d9  pop     rdi
0x1401c97da  pop     rbp
0x1401c97db  retn
```

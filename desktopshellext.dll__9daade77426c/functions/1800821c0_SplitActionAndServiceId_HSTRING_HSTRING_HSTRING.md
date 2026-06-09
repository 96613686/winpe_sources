# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800821c0`
- end: `0x180082294`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180082a10`

## callees

- `0x1800821c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180082209`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180082209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008226f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008226f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180082252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180082252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180082239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180082239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800821f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800821f9`

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
  v7 = wcscspn(StringRawBuffer, &c_szActionServiceDelimiter);
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
0x1800821c0  mov     [rsp-18h+arg_0], rbx
0x1800821c5  mov     [rsp-18h+arg_18], rsi
0x1800821ca  mov     [rsp-18h+length], r8
0x1800821cf  push    rbp
0x1800821d0  push    rdi
0x1800821d1  push    r14
0x1800821d3  mov     rbp, rsp
0x1800821d6  sub     rsp, 20h
0x1800821da  mov     rbx, rdx
0x1800821dd  mov     rsi, rcx
0x1800821e0  test    rdx, rdx
0x1800821e3  jz      short loc_1800821EC
0x1800821e5  mov     qword ptr [rdx], 0
0x1800821ec  xor     edi, edi
0x1800821ee  lea     rdx, [rbp+length]; length
0x1800821f2  mov     [rbp+string], rdi
0x1800821f6  mov     dword ptr [rbp+length], edi
0x1800821f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800821ff  mov     rcx, rax; String
0x180082202  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x180082209  call    cs:__imp_wcscspn
0x18008220f  mov     r14, rax
0x180082212  test    rbx, rbx
0x180082215  jz      short loc_18008226D
0x180082217  mov     eax, dword ptr [rbp+length]
0x18008221a  mov     rcx, [rbp+string]; string
0x18008221e  cmp     r14, rax
0x180082221  jnb     short loc_180082241
0x180082223  call    cs:__imp_WindowsDeleteString
0x180082229  mov     r8d, r14d; length
0x18008222c  mov     [rbp+string], rdi
0x180082230  lea     r9, [rbp+string]; newString
0x180082234  xor     edx, edx; startIndex
0x180082236  mov     rcx, rsi; string
0x180082239  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18008223f  jmp     short loc_180082258
0x180082241  call    cs:__imp_WindowsDeleteString
0x180082247  lea     rdx, [rbp+string]; newString
0x18008224b  mov     [rbp+string], rdi
0x18008224f  mov     rcx, rsi; string
0x180082252  call    cs:__imp_WindowsDuplicateString
0x180082258  mov     edi, eax
0x18008225a  test    eax, eax
0x18008225c  js      short loc_18008226D
0x18008225e  mov     rax, [rbp+string]
0x180082262  mov     [rbx], rax
0x180082265  mov     [rbp+string], 0
0x18008226d  xor     ecx, ecx; string
0x18008226f  call    cs:__imp_WindowsDeleteString
0x180082275  mov     rcx, [rbp+string]; string
0x180082279  call    cs:__imp_WindowsDeleteString
0x18008227f  mov     rbx, [rsp+20h+arg_0]
0x180082284  mov     eax, edi
0x180082286  mov     rsi, [rsp+20h+arg_18]
0x18008228b  add     rsp, 20h
0x18008228f  pop     r14
0x180082291  pop     rdi
0x180082292  pop     rbp
0x180082293  retn
```

# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1401c8464`
- end: `0x1401c8569`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `261`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1401c8d20`

## callees

- `0x1401c8464`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1401c84b3`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1401c84b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c849d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c849d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c84d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c84fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c84d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c84fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1401c84ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1401c84ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1401c8514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1401c8514`

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
0x1401c8464  mov     [rsp-18h+arg_0], rbx
0x1401c8469  mov     [rsp-18h+arg_18], rsi
0x1401c846e  mov     [rsp-18h+length], r8
0x1401c8473  push    rbp
0x1401c8474  push    rdi
0x1401c8475  push    r14
0x1401c8477  mov     rbp, rsp
0x1401c847a  sub     rsp, 20h
0x1401c847e  mov     rbx, rdx
0x1401c8481  mov     rsi, rcx
0x1401c8484  test    rdx, rdx
0x1401c8487  jz      short loc_1401C8490
0x1401c8489  mov     qword ptr [rdx], 0
0x1401c8490  xor     edi, edi
0x1401c8492  lea     rdx, [rbp+length]; length
0x1401c8496  mov     [rbp+string], rdi
0x1401c849a  mov     dword ptr [rbp+length], edi
0x1401c849d  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c84a4  nop     dword ptr [rax+rax+00h]
0x1401c84a9  mov     rcx, rax; String
0x1401c84ac  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1401c84b3  call    cs:__imp_wcscspn
0x1401c84ba  nop     dword ptr [rax+rax+00h]
0x1401c84bf  mov     r14, rax
0x1401c84c2  test    rbx, rbx
0x1401c84c5  jz      short loc_1401C8535
0x1401c84c7  mov     eax, dword ptr [rbp+length]
0x1401c84ca  mov     rcx, [rbp+string]; string
0x1401c84ce  cmp     r14, rax
0x1401c84d1  jnb     short loc_1401C84FD
0x1401c84d3  call    cs:__imp_WindowsDeleteString
0x1401c84da  nop     dword ptr [rax+rax+00h]
0x1401c84df  mov     r8d, r14d; length
0x1401c84e2  mov     [rbp+string], rdi
0x1401c84e6  lea     r9, [rbp+string]; newString
0x1401c84ea  xor     edx, edx; startIndex
0x1401c84ec  mov     rcx, rsi; string
0x1401c84ef  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1401c84f6  nop     dword ptr [rax+rax+00h]
0x1401c84fb  jmp     short loc_1401C8520
0x1401c84fd  call    cs:__imp_WindowsDeleteString
0x1401c8504  nop     dword ptr [rax+rax+00h]
0x1401c8509  lea     rdx, [rbp+string]; newString
0x1401c850d  mov     [rbp+string], rdi
0x1401c8511  mov     rcx, rsi; string
0x1401c8514  call    cs:__imp_WindowsDuplicateString
0x1401c851b  nop     dword ptr [rax+rax+00h]
0x1401c8520  mov     edi, eax
0x1401c8522  test    eax, eax
0x1401c8524  js      short loc_1401C8535
0x1401c8526  mov     rax, [rbp+string]
0x1401c852a  mov     [rbx], rax
0x1401c852d  mov     [rbp+string], 0
0x1401c8535  xor     ecx, ecx; string
0x1401c8537  call    cs:__imp_WindowsDeleteString
0x1401c853e  nop     dword ptr [rax+rax+00h]
0x1401c8543  mov     rcx, [rbp+string]; string
0x1401c8547  call    cs:__imp_WindowsDeleteString
0x1401c854e  nop     dword ptr [rax+rax+00h]
0x1401c8553  mov     rbx, [rsp+20h+arg_0]
0x1401c8558  mov     eax, edi
0x1401c855a  mov     rsi, [rsp+20h+arg_18]
0x1401c855f  add     rsp, 20h
0x1401c8563  pop     r14
0x1401c8565  pop     rdi
0x1401c8566  pop     rbp
0x1401c8567  retn
```

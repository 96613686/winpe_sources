# Reader::OnCallbackFailure(long)

- ea: `0x1005dc52`
- end: `0x1005dcc1`
- name: `?OnCallbackFailure@Reader@@CGXJ@Z`
- size: `111`
- prototype: `void __userpurge(HRESULT hr@<ecx>)`
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x1003c2a0`
- `0x1003c452`
- `0x1003c57a`
- `0x1003d9d4`
- `0x100425b0`
- `0x1004d7fd`
- `0x10058e82`
- `0x100596b2`
- `0x1005cd0c`
- `0x1006a179`
- `0x1016511b`
- `0x1016577c`
- `0x10165c26`
- `0x10166192`
- `0x1016667c`
- `0x1016689e`
- `0x101679e8`
- `0x10167d2e`
- `0x10167ead`
- `0x101683fb`

## callees

- `0x1005dc52`
- `0x100679cb`
- `0x100679ff`
- `0x1006b470`
- `0x100703d9`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005dc73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005dc73`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1005dc9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1005dc9b`

## string_xrefs

- `0x1005dc7b`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

## pseudocode

```c
void __thiscall Reader::OnCallbackFailure(HRESULT hr)
{
  DWORD CurrentThreadId; // eax
  wchar_t awchBuffer[128]; // [esp+4h] [ebp-104h] BYREF

  if ( IsNewParserCallbackFailureTracingEnabled() )
  {
    CurrentThreadId = GetCurrentThreadId();
    StringCchPrintfW(
      awchBuffer,
      0x80u,
      L"SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\r\n",
      hr,
      CurrentThreadId);
    OutputDebugStringW(awchBuffer);
  }
  if ( IsNewParserCallbackFailureDebugBreakEnabled() )
    MEMORY[0] = 0;
}

```

## disassembly

```asm
0x1005dc52  mov     edi, edi
0x1005dc54  push    ebp
0x1005dc55  mov     ebp, esp
0x1005dc57  sub     esp, 104h
0x1005dc5d  mov     eax, ___security_cookie
0x1005dc62  xor     eax, ebp
0x1005dc64  mov     [ebp+var_4], eax
0x1005dc67  push    esi
0x1005dc68  mov     esi, hr
0x1005dc6a  call    ?IsNewParserCallbackFailureTracingEnabled@@YG_NXZ; IsNewParserCallbackFailureTracingEnabled(void)
0x1005dc6f  test    al, al
0x1005dc71  jz      short loc_1005DCA1
0x1005dc73  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1005dc79  push    eax
0x1005dc7a  push    esi
0x1005dc7b  push    offset aSaxCallbackFai; "SAX callback failed with HRESULT = 0x%0"...
0x1005dc80  lea     eax, [ebp+awchBuffer]
0x1005dc86  push    80h; cchDest
0x1005dc8b  push    eax; pszDest
0x1005dc8c  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1005dc91  add     esp, 14h
0x1005dc94  lea     eax, [ebp+awchBuffer]
0x1005dc9a  push    eax; lpOutputString
0x1005dc9b  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1005dca1  call    ?IsNewParserCallbackFailureDebugBreakEnabled@@YG_NXZ; IsNewParserCallbackFailureDebugBreakEnabled(void)
0x1005dca6  pop     esi
0x1005dca7  test    al, al
0x1005dca9  jz      short loc_1005DCB5
0x1005dcab  mov     large dword ptr ds:0, 0
0x1005dcb5  mov     hr, [ebp+var_4]
0x1005dcb8  xor     hr, ebp; cookie
0x1005dcba  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005dcbf  leave
0x1005dcc0  retn
```

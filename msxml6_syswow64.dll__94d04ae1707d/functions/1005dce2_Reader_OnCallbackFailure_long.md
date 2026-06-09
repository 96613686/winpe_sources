# Reader::OnCallbackFailure(long)

- ea: `0x1005dce2`
- end: `0x1005dd51`
- name: `?OnCallbackFailure@Reader@@CGXJ@Z`
- size: `111`
- prototype: `void __userpurge(HRESULT hr@<ecx>)`
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x1003c330`
- `0x1003c4e2`
- `0x1003c60a`
- `0x1003da64`
- `0x10042640`
- `0x1004d88d`
- `0x10058f12`
- `0x10059742`
- `0x1005cd9c`
- `0x1006a219`
- `0x1016501e`
- `0x1016567f`
- `0x10165b29`
- `0x10166095`
- `0x1016657f`
- `0x101667a1`
- `0x101678eb`
- `0x10167c31`
- `0x10167db0`
- `0x101682fe`

## callees

- `0x1005dce2`
- `0x10067a6b`
- `0x10067a9f`
- `0x1006b510`
- `0x10070469`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005dd03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005dd03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1005dd2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1005dd2b`

## string_xrefs

- `0x1005dd0b`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

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
0x1005dce2  mov     edi, edi
0x1005dce4  push    ebp
0x1005dce5  mov     ebp, esp
0x1005dce7  sub     esp, 104h
0x1005dced  mov     eax, ___security_cookie
0x1005dcf2  xor     eax, ebp
0x1005dcf4  mov     [ebp+var_4], eax
0x1005dcf7  push    esi
0x1005dcf8  mov     esi, hr
0x1005dcfa  call    ?IsNewParserCallbackFailureTracingEnabled@@YG_NXZ; IsNewParserCallbackFailureTracingEnabled(void)
0x1005dcff  test    al, al
0x1005dd01  jz      short loc_1005DD31
0x1005dd03  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1005dd09  push    eax
0x1005dd0a  push    esi
0x1005dd0b  push    offset aSaxCallbackFai; "SAX callback failed with HRESULT = 0x%0"...
0x1005dd10  lea     eax, [ebp+awchBuffer]
0x1005dd16  push    80h; cchDest
0x1005dd1b  push    eax; pszDest
0x1005dd1c  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1005dd21  add     esp, 14h
0x1005dd24  lea     eax, [ebp+awchBuffer]
0x1005dd2a  push    eax; lpOutputString
0x1005dd2b  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1005dd31  call    ?IsNewParserCallbackFailureDebugBreakEnabled@@YG_NXZ; IsNewParserCallbackFailureDebugBreakEnabled(void)
0x1005dd36  pop     esi
0x1005dd37  test    al, al
0x1005dd39  jz      short loc_1005DD45
0x1005dd3b  mov     large dword ptr ds:0, 0
0x1005dd45  mov     hr, [ebp+var_4]
0x1005dd48  xor     hr, ebp; cookie
0x1005dd4a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005dd4f  leave
0x1005dd50  retn
```

# Reader::OnCallbackFailure(long)

- ea: `0x1800bc810`
- end: `0x1800bc8e4`
- name: `?OnCallbackFailure@Reader@@CAXJ@Z`
- size: `212`
- prototype: `void __fastcall(HRESULT hr)`
- caller_count: `20`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014550`
- `0x180026578`
- `0x18002676c`
- `0x1800271b4`
- `0x180027bc0`
- `0x180028a74`
- `0x180028c90`
- `0x1800a62f4`
- `0x1800af04c`
- `0x1800bc690`
- `0x1800be570`
- `0x1800c521c`
- `0x1801705a8`
- `0x180170d98`
- `0x180171308`
- `0x18017176c`
- `0x180171a00`
- `0x180172524`
- `0x180172844`
- `0x1801729ec`

## callees

- `0x18007797c`
- `0x1800bc810`
- `0x1800cac00`
- `0x1800cada0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bc860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bc860`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800bc888`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800bc888`

## string_xrefs

- `0x1800bc869`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

## pseudocode

```c
void __fastcall Reader::OnCallbackFailure(unsigned int hr)
{
  bool v1; // al
  DWORD CurrentThreadId; // [rsp+20h] [rbp-128h]
  wchar_t awchBuffer[128]; // [rsp+30h] [rbp-118h] BYREF

  v1 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
  if ( !NewParserCallbackFailureTrackingRegistry::s_fInitialized )
  {
    NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
    NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
    Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
    v1 = 1;
    NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
  }
  if ( NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled )
  {
    CurrentThreadId = GetCurrentThreadId();
    StringCchPrintfW(
      awchBuffer,
      0x80u,
      L"SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\r\n",
      hr,
      CurrentThreadId);
    OutputDebugStringW(awchBuffer);
    v1 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
  }
  if ( !v1 )
  {
    NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
    NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
    Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
    NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
  }
  if ( NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled )
    MEMORY[0] = 0;
}

```

## disassembly

```asm
0x1800bc810  push    rbx
0x1800bc812  sub     rsp, 140h
0x1800bc819  mov     rax, cs:__security_cookie
0x1800bc820  xor     rax, rsp
0x1800bc823  mov     [rsp+148h+var_18], rax
0x1800bc82b  mov     al, cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bc831  mov     ebx, hr
0x1800bc833  test    al, al
0x1800bc835  jnz     short loc_1800BC857
0x1800bc837  lea     rcx, ?s_rgSettings@NewParserCallbackFailureTrackingRegistry@@0QBUReadSettings@Registry@@B; pSettings
0x1800bc83e  mov     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bc844  mov     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bc84a  call    ?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z; Registry::readMultipleSettings(Registry::ReadSettings const *)
0x1800bc84f  mov     al, 1
0x1800bc851  mov     cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bc857  cmp     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, 0; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bc85e  jz      short loc_1800BC894
0x1800bc860  call    cs:__imp_GetCurrentThreadId
0x1800bc866  mov     r9d, ebx
0x1800bc869  lea     r8, aSaxCallbackFai; "SAX callback failed with HRESULT = 0x%0"...
0x1800bc870  lea     rcx, [rsp+148h+awchBuffer]; pszDest
0x1800bc875  mov     [rsp+148h+var_128], eax
0x1800bc879  mov     edx, 80h; cchDest
0x1800bc87e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc883  lea     rcx, [rsp+148h+awchBuffer]; lpOutputString
0x1800bc888  call    cs:__imp_OutputDebugStringW
0x1800bc88e  mov     al, cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bc894  test    al, al
0x1800bc896  jnz     short loc_1800BC8B7
0x1800bc898  lea     rcx, ?s_rgSettings@NewParserCallbackFailureTrackingRegistry@@0QBUReadSettings@Registry@@B; pSettings
0x1800bc89f  mov     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bc8a5  mov     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bc8ab  call    ?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z; Registry::readMultipleSettings(Registry::ReadSettings const *)
0x1800bc8b0  mov     cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA, 1; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bc8b7  cmp     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, 0; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bc8be  jz      short loc_1800BC8CB
0x1800bc8c0  mov     dword ptr ds:0, 0
0x1800bc8cb  mov     rcx, [rsp+148h+var_18]
0x1800bc8d3  xor     rcx, rsp; StackCookie
0x1800bc8d6  call    __security_check_cookie
0x1800bc8db  add     rsp, 140h
0x1800bc8e2  pop     rbx
0x1800bc8e3  retn
```

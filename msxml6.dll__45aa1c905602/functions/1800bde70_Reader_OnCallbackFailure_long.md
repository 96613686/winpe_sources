# Reader::OnCallbackFailure(long)

- ea: `0x1800bde70`
- end: `0x1800bdf51`
- name: `?OnCallbackFailure@Reader@@CAXJ@Z`
- size: `225`
- prototype: `void __fastcall(HRESULT hr)`
- caller_count: `20`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020de0`
- `0x18003b36c`
- `0x18003b560`
- `0x18003bbc4`
- `0x18003c424`
- `0x180044b1c`
- `0x180044e64`
- `0x1800a763c`
- `0x1800b0650`
- `0x1800bdcf0`
- `0x1800bfa94`
- `0x1800c6abc`
- `0x18017417c`
- `0x180174974`
- `0x180174ee4`
- `0x180175348`
- `0x1801755dc`
- `0x180176100`
- `0x180176420`
- `0x1801765c8`

## callees

- `0x180076cdc`
- `0x1800bde70`
- `0x1800cc51c`
- `0x1800cc6c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdec0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdec0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800bdeee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800bdeee`

## string_xrefs

- `0x1800bdecf`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

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
0x1800bde70  push    rbx
0x1800bde72  sub     rsp, 140h
0x1800bde79  mov     rax, cs:__security_cookie
0x1800bde80  xor     rax, rsp
0x1800bde83  mov     [rsp+148h+var_18], rax
0x1800bde8b  mov     al, cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bde91  mov     ebx, hr
0x1800bde93  test    al, al
0x1800bde95  jnz     short loc_1800BDEB7
0x1800bde97  lea     rcx, ?s_rgSettings@NewParserCallbackFailureTrackingRegistry@@0QBUReadSettings@Registry@@B; pSettings
0x1800bde9e  mov     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bdea4  mov     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bdeaa  call    ?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z; Registry::readMultipleSettings(Registry::ReadSettings const *)
0x1800bdeaf  mov     al, 1
0x1800bdeb1  mov     cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bdeb7  cmp     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, 0; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bdebe  jz      short loc_1800BDF00
0x1800bdec0  call    cs:__imp_GetCurrentThreadId
0x1800bdec7  nop     dword ptr [rax+rax+00h]
0x1800bdecc  mov     r9d, ebx
0x1800bdecf  lea     r8, aSaxCallbackFai; "SAX callback failed with HRESULT = 0x%0"...
0x1800bded6  lea     rcx, [rsp+148h+awchBuffer]; pszDest
0x1800bdedb  mov     [rsp+148h+var_128], eax
0x1800bdedf  mov     edx, 80h; cchDest
0x1800bdee4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bdee9  lea     rcx, [rsp+148h+awchBuffer]; lpOutputString
0x1800bdeee  call    cs:__imp_OutputDebugStringW
0x1800bdef5  nop     dword ptr [rax+rax+00h]
0x1800bdefa  mov     al, cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bdf00  test    al, al
0x1800bdf02  jnz     short loc_1800BDF23
0x1800bdf04  lea     rcx, ?s_rgSettings@NewParserCallbackFailureTrackingRegistry@@0QBUReadSettings@Registry@@B; pSettings
0x1800bdf0b  mov     cs:?s_fTracingEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled
0x1800bdf11  mov     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, al; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bdf17  call    ?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z; Registry::readMultipleSettings(Registry::ReadSettings const *)
0x1800bdf1c  mov     cs:?s_fInitialized@NewParserCallbackFailureTrackingRegistry@@2_NA, 1; bool NewParserCallbackFailureTrackingRegistry::s_fInitialized
0x1800bdf23  cmp     cs:?s_fDebugBreakEnabled@NewParserCallbackFailureTrackingRegistry@@2_NA, 0; bool NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled
0x1800bdf2a  jz      short loc_1800BDF37
0x1800bdf2c  mov     dword ptr ds:0, 0
0x1800bdf37  mov     rcx, [rsp+148h+var_18]
0x1800bdf3f  xor     rcx, rsp; StackCookie
0x1800bdf42  call    __security_check_cookie
0x1800bdf47  add     rsp, 140h
0x1800bdf4e  pop     rbx
0x1800bdf4f  retn
```

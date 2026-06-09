# WinHttpSession::Initialize(void)

- ea: `0x180035fc8`
- end: `0x1800360e1`
- name: `?Initialize@WinHttpSession@@QEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(WinHttpSession *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d2d8`
- `0x180064b9c`
- `0x180066f68`
- `0x180079b64`
- `0x180083dc8`
- `0x180088bac`
- `0x1800b447c`
- `0x1800b60a4`
- `0x1800b885c`
- `0x1800ba1ac`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180035fc8`
- `0x180091308`
- `0x180098078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003603c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003603c`
- `WINHTTP!WinHttpOpen` at `0x18003602d`
- `WINHTTP!WinHttpOpen` at `0x18003602d`

## string_xrefs

- `0x180036084`: `%s: WinHttpOpen failed with error code: 0x%08x`
- `0x180036067`: `Logger::WriteWinhttpInitializationFailureEvent`
- `0x180036060`: `EventWriteWinhttpInitializationFailureEvent`
- `0x1800360b9`: `%s: Winhttp initialized. User agent: %s. Access type: %lu. Proxy name: %s. Proxy bypass address list: %s. Flags: %lu.`
- `0x180035ff2`: `ReadBoolOption`

## pseudocode

```c
__int64 __fastcall WinHttpSession::Initialize(WinHttpSession *this)
{
  int v2; // eax
  BOOL v3; // eax
  DWORD v4; // edi
  HINTERNET v5; // rax
  int v6; // edx
  int v7; // ecx
  DWORD LastError; // ebx
  int v9; // r8d
  unsigned int v10; // eax
  int dwFlags; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+30h] [rbp-18h]
  bool v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 1;
  v2 = ReadBoolOption(L"SkipProxyDetection", &v14);
  if ( v2 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"IsSkipProxyDetectionEnabled",
      L"ReadBoolOption",
      (unsigned int)v2);
  v3 = v14;
  *((_DWORD *)this + 4) = v14;
  v4 = v3 ? 4 : 0;
  v5 = WinHttpOpen(0, v4, 0, 0, 0x10000000u);
  *((_QWORD *)this + 1) = v5;
  if ( v5 )
  {
    v13 = 0x10000000;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Winhttp initialized. User agent: %s. Access type: %lu. Proxy name: %s. Proxy bypass address list: %s. Flags: %lu.",
      L"WinHttpSession::Initialize",
      0,
      v4,
      0,
      0,
      v13);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v10 = McTemplateU0zqzzqq_EventWriteTransfer(v7, v6, v9, v4, dwFlags);
      if ( v10 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpInitializationFailureEvent",
          L"EventWriteWinhttpInitializationFailureEvent",
          v10);
    }
    Logger::TraceError(L"%s: WinHttpOpen failed with error code: 0x%08x", L"WinHttpSession::Initialize", LastError);
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
}

```

## disassembly

```asm
0x180035fc8  mov     [rsp+arg_8], rbx
0x180035fcd  push    rdi
0x180035fce  sub     rsp, 40h
0x180035fd2  mov     rbx, rcx
0x180035fd5  mov     [rsp+48h+arg_0], 1
0x180035fda  lea     rcx, aSkipproxydetec; "SkipProxyDetection"
0x180035fe1  lea     rdx, [rsp+48h+arg_0]; bool *
0x180035fe6  call    ?ReadBoolOption@@YAJPEBGPEA_N@Z; ReadBoolOption(ushort const *,bool *)
0x180035feb  test    eax, eax
0x180035fed  jns     short loc_18003600C
0x180035fef  mov     r9d, eax
0x180035ff2  lea     r8, aReadbooloption; "ReadBoolOption"
0x180035ff9  lea     rdx, aIsskipproxydet; "IsSkipProxyDetectionEnabled"
0x180036000  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180036007  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003600c  movzx   eax, [rsp+48h+arg_0]
0x180036011  mov     [rbx+10h], eax
0x180036014  neg     eax
0x180036016  mov     [rsp+48h+dwFlags], 10000000h; dwFlags
0x18003601e  sbb     edi, edi
0x180036020  xor     r9d, r9d; pszProxyBypassW
0x180036023  and     edi, 4
0x180036026  xor     r8d, r8d; pszProxyW
0x180036029  mov     edx, edi; dwAccessType
0x18003602b  xor     ecx, ecx; pszAgentW
0x18003602d  call    cs:__imp_WinHttpOpen
0x180036033  mov     [rbx+8], rax
0x180036037  test    rax, rax
0x18003603a  jnz     short loc_1800360A1
0x18003603c  call    cs:__imp_GetLastError
0x180036042  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180036049  mov     ebx, eax
0x18003604b  jz      short loc_18003607A
0x18003604d  mov     r9d, edi
0x180036050  mov     [rsp+48h+var_10], eax
0x180036054  call    McTemplateU0zqzzqq_EventWriteTransfer
0x180036059  test    eax, eax
0x18003605b  jz      short loc_18003607A
0x18003605d  mov     r9d, eax
0x180036060  lea     r8, aEventwritewinh_8; "EventWriteWinhttpInitializationFailureE"...
0x180036067  lea     rdx, aLoggerWritewin_8; "Logger::WriteWinhttpInitializationFailu"...
0x18003606e  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180036075  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003607a  mov     r8d, ebx
0x18003607d  lea     rdx, aWinhttpsession; "WinHttpSession::Initialize"
0x180036084  lea     rcx, aSWinhttpopenFa; "%s: WinHttpOpen failed with error code:"...
0x18003608b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180036090  test    ebx, ebx
0x180036092  jle     short loc_18003609D
0x180036094  movzx   ebx, bx
0x180036097  or      ebx, 80070000h
0x18003609d  mov     eax, ebx
0x18003609f  jmp     short loc_1800360D6
0x1800360a1  mov     [rsp+48h+var_18], 10000000h
0x1800360a9  lea     rdx, aWinhttpsession; "WinHttpSession::Initialize"
0x1800360b0  mov     [rsp+48h+var_20], 0
0x1800360b9  lea     rcx, aSWinhttpInitia; "%s: Winhttp initialized. User agent: %s"...
0x1800360c0  mov     r9d, edi
0x1800360c3  mov     qword ptr [rsp+48h+dwFlags], 0
0x1800360cc  xor     r8d, r8d
0x1800360cf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800360d4  xor     eax, eax
0x1800360d6  mov     rbx, [rsp+48h+arg_8]
0x1800360db  add     rsp, 40h
0x1800360df  pop     rdi
0x1800360e0  retn
```

# W3_CGI_HANDLER::Initialize(void)

- ea: `0x180004344`
- end: `0x1800045f6`
- name: `?Initialize@W3_CGI_HANDLER@@SAJXZ`
- size: `690`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002450`

## callees

- `0x180001008`
- `0x180004344`
- `0x1800062a0`
- `0x180006e46`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004392`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000439e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000439e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004509`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004489`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004489`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004407`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800045be`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800045e5`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800045be`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800045e5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800044fb`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800044fb`
- `iisutil!PuDbgPrint` at `0x180004380`
- `iisutil!PuDbgPrint` at `0x180004552`
- `iisutil!PuDbgPrint` at `0x180004380`
- `iisutil!PuDbgPrint` at `0x180004552`

## string_xrefs

- `0x180004379`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x18000454b`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x1800043cb`: `System\CurrentControlSet\Services\w3svc\Parameters`

## pseudocode

```c
signed int W3_CGI_HANDLER::Initialize(void)
{
  signed int result; // eax
  WCHAR *EnvironmentStringsW; // rdi
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rcx
  void *v6; // rax
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      87,
      "W3_CGI_HANDLER::Initialize",
      "W3_CGI_HANDLER::Initialize() called\n");
  if ( InitializeCriticalSectionAndSpinCount(&W3_CGI_HANDLER::sm_CgiListLock, 0xAu) )
  {
    hKey = 0;
    qword_18000D678 = (__int64)&W3_CGI_HANDLER::sm_CgiListHead;
    W3_CGI_HANDLER::sm_CgiListHead.Flink = &W3_CGI_HANDLER::sm_CgiListHead;
    qword_18000D6B0 = (__int64)&W3_CGI_HANDLER::sm_QueuedCgisListHead;
    W3_CGI_HANDLER::sm_QueuedCgisListHead.Flink = &W3_CGI_HANDLER::sm_QueuedCgisListHead;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\w3svc\\Parameters",
            0,
            0x20019u,
            &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"ForwardServerEnvironmentBlock", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock = Data != 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"MaxConcurrentCgisExecuting", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        W3_CGI_HANDLER::sm_dwMaxCgisExecuting = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"DoNotKillCgiOnRequestEnd", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        W3_CGI_HANDLER::sm_fTerminateProcessOnRequestEnd = Data == 0;
      RegCloseKey(hKey);
    }
    if ( W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock )
    {
      EnvironmentStringsW = GetEnvironmentStringsW();
      if ( !EnvironmentStringsW )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
            158,
            "W3_CGI_HANDLER::Initialize",
            "GetEnvironmentStrings failed\n");
        goto LABEL_32;
      }
      W3_CGI_HANDLER::sm_cchEnvLength = 0;
      v4 = -1;
      do
        ++v4;
      while ( EnvironmentStringsW[v4] );
      LODWORD(v5) = 0;
      if ( (_DWORD)v4 )
      {
        do
        {
          v5 = (unsigned int)(v4 + 1 + v5);
          v4 = -1;
          do
            ++v4;
          while ( EnvironmentStringsW[v5 + v4] );
        }
        while ( (_DWORD)v4 );
        W3_CGI_HANDLER::sm_cchEnvLength = v5;
      }
      v6 = operator new(saturated_mul((unsigned int)v5, 2u));
      W3_CGI_HANDLER::sm_pEnvString = v6;
      if ( !v6 )
      {
        v3 = -2147024888;
        FreeEnvironmentStringsW(EnvironmentStringsW);
LABEL_32:
        W3_CGI_HANDLER::Terminate();
        return v3;
      }
      memcpy_0(v6, EnvironmentStringsW, 2LL * W3_CGI_HANDLER::sm_cchEnvLength);
      FreeEnvironmentStringsW(EnvironmentStringsW);
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004344  push    rbp
0x180004346  push    rbx
0x180004347  push    rsi
0x180004348  push    rdi
0x180004349  mov     rbp, rsp
0x18000434c  sub     rsp, 38h
0x180004350  test    cs:g_dwDebugFlags, 3
0x180004357  jz      short loc_180004386
0x180004359  mov     rcx, cs:g_pDebug
0x180004360  lea     rax, aW3CgiHandlerIn_0; "W3_CGI_HANDLER::Initialize() called\n"
0x180004367  lea     r9, aW3CgiHandlerIn; "W3_CGI_HANDLER::Initialize"
0x18000436e  mov     [rsp+38h+phkResult], rax
0x180004373  mov     r8d, 57h ; 'W'
0x180004379  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004380  call    cs:__imp_PuDbgPrint
0x180004386  mov     edx, 0Ah; dwSpinCount
0x18000438b  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004392  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004398  xor     esi, esi
0x18000439a  test    eax, eax
0x18000439c  jnz     short loc_1800043B9
0x18000439e  call    cs:__imp_GetLastError
0x1800043a4  test    eax, eax
0x1800043a6  jle     loc_1800045ED
0x1800043ac  movzx   eax, ax
0x1800043af  or      eax, 80070000h
0x1800043b4  jmp     loc_1800045ED
0x1800043b9  lea     rax, ?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x1800043c0  mov     [rbp+hKey], rsi
0x1800043c4  mov     cs:qword_18000D678, rax
0x1800043cb  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x1800043d2  mov     cs:?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x1800043d9  mov     r9d, 20019h; samDesired
0x1800043df  lea     rax, ?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x1800043e6  xor     r8d, r8d; ulOptions
0x1800043e9  mov     cs:qword_18000D6B0, rax
0x1800043f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800043f7  mov     cs:?sm_QueuedCgisListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY W3_CGI_HANDLER::sm_QueuedCgisListHead
0x1800043fe  lea     rax, [rbp+hKey]
0x180004402  mov     [rsp+38h+phkResult], rax; phkResult
0x180004407  call    cs:__imp_RegOpenKeyExW
0x18000440d  test    eax, eax
0x18000440f  jnz     loc_1800044EF
0x180004415  mov     rcx, [rbp+hKey]; hKey
0x180004419  lea     ebx, [rax+4]
0x18000441c  lea     rax, [rbp+cbData]
0x180004420  mov     [rbp+Type], esi
0x180004423  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180004428  lea     r9, [rbp+Type]; lpType
0x18000442c  lea     rax, [rbp+Data]
0x180004430  mov     [rbp+Data], esi
0x180004433  xor     r8d, r8d; lpReserved
0x180004436  mov     [rsp+38h+phkResult], rax; lpData
0x18000443b  lea     rdx, ValueName; "ForwardServerEnvironmentBlock"
0x180004442  mov     [rbp+cbData], ebx
0x180004445  call    cs:__imp_RegQueryValueExW
0x18000444b  test    eax, eax
0x18000444d  jnz     short loc_180004462
0x18000444f  cmp     [rbp+Type], ebx
0x180004452  jnz     short loc_180004462
0x180004454  cmp     [rbp+Data], esi
0x180004457  mov     eax, esi
0x180004459  setnz   al
0x18000445c  mov     cs:?sm_fForwardServerEnvironmentBlock@W3_CGI_HANDLER@@0HA, eax; int W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock
0x180004462  mov     rcx, [rbp+hKey]; hKey
0x180004466  lea     rax, [rbp+cbData]
0x18000446a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000446f  lea     r9, [rbp+Type]; lpType
0x180004473  lea     rax, [rbp+Data]
0x180004477  mov     [rbp+cbData], ebx
0x18000447a  xor     r8d, r8d; lpReserved
0x18000447d  mov     [rsp+38h+phkResult], rax; lpData
0x180004482  lea     rdx, aMaxconcurrentc; "MaxConcurrentCgisExecuting"
0x180004489  call    cs:__imp_RegQueryValueExW
0x18000448f  test    eax, eax
0x180004491  jnz     short loc_1800044A1
0x180004493  cmp     [rbp+Type], ebx
0x180004496  jnz     short loc_1800044A1
0x180004498  mov     eax, [rbp+Data]
0x18000449b  mov     cs:?sm_dwMaxCgisExecuting@W3_CGI_HANDLER@@0KA, eax; ulong W3_CGI_HANDLER::sm_dwMaxCgisExecuting
0x1800044a1  mov     rcx, [rbp+hKey]; hKey
0x1800044a5  lea     rax, [rbp+cbData]
0x1800044a9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800044ae  lea     r9, [rbp+Type]; lpType
0x1800044b2  lea     rax, [rbp+Data]
0x1800044b6  mov     [rbp+cbData], ebx
0x1800044b9  xor     r8d, r8d; lpReserved
0x1800044bc  mov     [rsp+38h+phkResult], rax; lpData
0x1800044c1  lea     rdx, aDonotkillcgion; "DoNotKillCgiOnRequestEnd"
0x1800044c8  call    cs:__imp_RegQueryValueExW
0x1800044ce  test    eax, eax
0x1800044d0  jnz     short loc_1800044E5
0x1800044d2  cmp     [rbp+Type], ebx
0x1800044d5  jnz     short loc_1800044E5
0x1800044d7  cmp     [rbp+Data], esi
0x1800044da  mov     eax, esi
0x1800044dc  setz    al
0x1800044df  mov     cs:?sm_fTerminateProcessOnRequestEnd@W3_CGI_HANDLER@@0HA, eax; int W3_CGI_HANDLER::sm_fTerminateProcessOnRequestEnd
0x1800044e5  mov     rcx, [rbp+hKey]; hKey
0x1800044e9  call    cs:__imp_RegCloseKey
0x1800044ef  cmp     cs:?sm_fForwardServerEnvironmentBlock@W3_CGI_HANDLER@@0HA, esi; int W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock
0x1800044f5  jz      loc_1800045EB
0x1800044fb  call    cs:__imp_GetEnvironmentStringsW
0x180004501  mov     rdi, rax
0x180004504  test    rax, rax
0x180004507  jnz     short loc_18000455A
0x180004509  call    cs:__imp_GetLastError
0x18000450f  mov     ebx, eax
0x180004511  test    eax, eax
0x180004513  jle     short loc_18000451E
0x180004515  movzx   ebx, ax
0x180004518  or      ebx, 80070000h
0x18000451e  test    cs:g_dwDebugFlags, 3
0x180004525  jz      loc_1800045C4
0x18000452b  mov     rcx, cs:g_pDebug
0x180004532  lea     rax, aGetenvironment; "GetEnvironmentStrings failed\n"
0x180004539  lea     r9, aW3CgiHandlerIn; "W3_CGI_HANDLER::Initialize"
0x180004540  mov     [rsp+38h+phkResult], rax
0x180004545  mov     r8d, 9Eh
0x18000454b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004552  call    cs:__imp_PuDbgPrint
0x180004558  jmp     short loc_1800045C4
0x18000455a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000455e  mov     cs:?sm_cchEnvLength@W3_CGI_HANDLER@@0KA, esi; ulong W3_CGI_HANDLER::sm_cchEnvLength
0x180004564  mov     rax, r8
0x180004567  inc     rax
0x18000456a  cmp     [rdi+rax*2], si
0x18000456e  jnz     short loc_180004567
0x180004570  mov     ecx, esi
0x180004572  test    eax, eax
0x180004574  jz      short loc_180004594
0x180004576  inc     eax
0x180004578  add     ecx, eax
0x18000457a  mov     rax, r8
0x18000457d  lea     rdx, [rdi+rcx*2]
0x180004581  inc     rax
0x180004584  cmp     [rdx+rax*2], si
0x180004588  jnz     short loc_180004581
0x18000458a  test    eax, eax
0x18000458c  jnz     short loc_180004576
0x18000458e  mov     cs:?sm_cchEnvLength@W3_CGI_HANDLER@@0KA, ecx; ulong W3_CGI_HANDLER::sm_cchEnvLength
0x180004594  mov     edx, ecx
0x180004596  mov     eax, 2
0x18000459b  mul     rdx
0x18000459e  cmovb   rax, r8
0x1800045a2  mov     rcx, rax; Size
0x1800045a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045aa  mov     cs:?sm_pEnvString@W3_CGI_HANDLER@@0PEAGEA, rax; ushort * W3_CGI_HANDLER::sm_pEnvString
0x1800045b1  test    rax, rax
0x1800045b4  jnz     short loc_1800045CD
0x1800045b6  mov     rcx, rdi; penv
0x1800045b9  mov     ebx, 80070008h
0x1800045be  call    cs:__imp_FreeEnvironmentStringsW
0x1800045c4  call    ?Terminate@W3_CGI_HANDLER@@SAXXZ; W3_CGI_HANDLER::Terminate(void)
0x1800045c9  mov     eax, ebx
0x1800045cb  jmp     short loc_1800045ED
0x1800045cd  mov     r8d, cs:?sm_cchEnvLength@W3_CGI_HANDLER@@0KA; ulong W3_CGI_HANDLER::sm_cchEnvLength
0x1800045d4  mov     rdx, rdi; Src
0x1800045d7  add     r8, r8; Size
0x1800045da  mov     rcx, rax; void *
0x1800045dd  call    memcpy_0
0x1800045e2  mov     rcx, rdi; penv
0x1800045e5  call    cs:__imp_FreeEnvironmentStringsW
0x1800045eb  xor     eax, eax
0x1800045ed  add     rsp, 38h
0x1800045f1  pop     rdi
0x1800045f2  pop     rsi
0x1800045f3  pop     rbx
0x1800045f4  pop     rbp
0x1800045f5  retn
```

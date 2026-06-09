# CGPServiceConfiguration::ReadServiceConfiguration(void)

- ea: `0x1800371c4`
- end: `0x1800373c6`
- name: `?ReadServiceConfiguration@CGPServiceConfiguration@@KAKXZ`
- size: `514`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180036340`
- `0x180067a78`

## callees

- `0x18001d6e8`
- `0x1800371c4`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003730c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003731f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003730c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003731f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037347`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003728b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003728b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037238`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003726f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800372ad`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003726f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800372ad`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003720c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003720c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800371e9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800371e9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037221`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003725a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037221`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003725a`

## string_xrefs

- `0x1800371dd`: `ServicesActive`
- `0x18003737b`: `GP Service config is unknown due to error 0x%x`
- `0x1800373b0`: `GP Service config is unknown due to error 0x%x`

## pseudocode

```c
__int64 CGPServiceConfiguration::ReadServiceConfiguration(void)
{
  DWORD LastError; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rdi
  struct _QUERY_SERVICE_CONFIGW *v4; // rsi
  struct _QUERY_SERVICE_CONFIGW *v6; // rax
  unsigned int v7; // ecx
  DWORD v8; // eax
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF

  LastError = 0;
  if ( CGPServiceConfiguration::m_CurrentConfiguration )
    return LastError;
  v1 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"gpsvc", 0x80000000);
    if ( !v3 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 87;
    }
    CloseServiceHandle(v2);
  }
  else
  {
    v3 = 0;
    LastError = GetLastError();
    if ( !LastError )
    {
      LastError = 87;
      pcbBytesNeeded = 0;
      goto LABEL_6;
    }
  }
  pcbBytesNeeded = 0;
  if ( !LastError )
  {
    if ( QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded) || (v8 = GetLastError(), (LastError = v8) == 0) )
    {
      LastError = 87;
    }
    else if ( v8 == 122 )
    {
      v6 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
      v4 = v6;
      if ( v6 )
      {
        if ( QueryServiceConfigW(v3, v6, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          if ( v4->dwServiceType == 32 )
          {
            CGPServiceConfiguration::m_CurrentConfiguration = 1;
            v7 = 4168;
          }
          else
          {
            CGPServiceConfiguration::m_CurrentConfiguration = 2;
            v7 = 4169;
          }
          CGPOperationalTraceEvent::ReportOperationalEvent(v7, 0);
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 87;
        }
      }
      else
      {
        LastError = 14;
      }
      goto LABEL_7;
    }
  }
LABEL_6:
  v4 = 0;
LABEL_7:
  LocalFree(v4);
  if ( v3 )
    CloseServiceHandle(v3);
  if ( LastError && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"GP Service config is unknown due to error 0x%x", LastError);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"GP Service config is unknown due to error 0x%x", LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800371c4  push    rbx
0x1800371c6  push    rsi
0x1800371c7  push    rdi
0x1800371c8  push    r14
0x1800371ca  sub     rsp, 28h
0x1800371ce  xor     ebx, ebx
0x1800371d0  cmp     cs:?m_CurrentConfiguration@CGPServiceConfiguration@@0W4ServiceConfiguration@1@A, ebx; CGPServiceConfiguration::ServiceConfiguration CGPServiceConfiguration::m_CurrentConfiguration
0x1800371d6  jnz     short loc_18003724B
0x1800371d8  mov     edi, 80000000h
0x1800371dd  lea     rdx, DatabaseName; "ServicesActive"
0x1800371e4  mov     r8d, edi; dwDesiredAccess
0x1800371e7  xor     ecx, ecx; lpMachineName
0x1800371e9  call    cs:__imp_OpenSCManagerW
0x1800371ef  lea     r14d, [rbx+57h]
0x1800371f3  mov     rsi, rax
0x1800371f6  test    rax, rax
0x1800371f9  jz      loc_1800372EE
0x1800371ff  mov     r8d, edi; dwDesiredAccess
0x180037202  lea     rdx, aGpsvc; "gpsvc"
0x180037209  mov     rcx, rax; hSCManager
0x18003720c  call    cs:__imp_OpenServiceW
0x180037212  mov     rdi, rax
0x180037215  test    rax, rax
0x180037218  jz      loc_18003730C
0x18003721e  mov     rcx, rsi; hSCObject
0x180037221  call    cs:__imp_CloseServiceHandle
0x180037227  mov     [rsp+48h+pcbBytesNeeded], 0
0x18003722f  test    ebx, ebx
0x180037231  jz      short loc_180037262
0x180037233  xor     esi, esi
0x180037235  mov     rcx, rsi; hMem
0x180037238  call    cs:__imp_LocalFree
0x18003723e  test    rdi, rdi
0x180037241  jnz     short loc_180037257
0x180037243  test    ebx, ebx
0x180037245  jnz     loc_18003735F
0x18003724b  mov     eax, ebx
0x18003724d  add     rsp, 28h
0x180037251  pop     r14
0x180037253  pop     rdi
0x180037254  pop     rsi
0x180037255  pop     rbx
0x180037256  retn
0x180037257  mov     rcx, rdi; hSCObject
0x18003725a  call    cs:__imp_CloseServiceHandle
0x180037260  jmp     short loc_180037243
0x180037262  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x180037267  xor     r8d, r8d; cbBufSize
0x18003726a  xor     edx, edx; lpServiceConfig
0x18003726c  mov     rcx, rdi; hService
0x18003726f  call    cs:__imp_QueryServiceConfigW
0x180037275  test    eax, eax
0x180037277  jz      loc_18003731F
0x18003727d  mov     ebx, r14d
0x180037280  jmp     short loc_180037233
0x180037282  mov     edx, [rsp+48h+pcbBytesNeeded]; uBytes
0x180037286  mov     ecx, 40h ; '@'; uFlags
0x18003728b  call    cs:__imp_LocalAlloc
0x180037291  mov     rsi, rax
0x180037294  test    rax, rax
0x180037297  jz      loc_18003733D
0x18003729d  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x1800372a2  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x1800372a7  mov     rdx, rax; lpServiceConfig
0x1800372aa  mov     rcx, rdi; hService
0x1800372ad  call    cs:__imp_QueryServiceConfigW
0x1800372b3  test    eax, eax
0x1800372b5  jz      loc_180037347
0x1800372bb  xor     edx, edx; unsigned int
0x1800372bd  cmp     dword ptr [rsi], 20h ; ' '
0x1800372c0  jz      short loc_1800372DD
0x1800372c2  mov     cs:?m_CurrentConfiguration@CGPServiceConfiguration@@0W4ServiceConfiguration@1@A, 2; CGPServiceConfiguration::ServiceConfiguration CGPServiceConfiguration::m_CurrentConfiguration
0x1800372cc  mov     ecx, 1049h; unsigned int
0x1800372d1  call    ?ReportOperationalEvent@CGPOperationalTraceEvent@@SAKKK@Z; CGPOperationalTraceEvent::ReportOperationalEvent(ulong,ulong)
0x1800372d6  xor     ebx, ebx
0x1800372d8  jmp     loc_180037235
0x1800372dd  mov     cs:?m_CurrentConfiguration@CGPServiceConfiguration@@0W4ServiceConfiguration@1@A, 1; CGPServiceConfiguration::ServiceConfiguration CGPServiceConfiguration::m_CurrentConfiguration
0x1800372e7  mov     ecx, 1048h
0x1800372ec  jmp     short loc_1800372D1
0x1800372ee  xor     edi, edi
0x1800372f0  call    cs:__imp_GetLastError
0x1800372f6  mov     ebx, eax
0x1800372f8  test    eax, eax
0x1800372fa  jnz     loc_180037227
0x180037300  mov     ebx, r14d
0x180037303  mov     [rsp+48h+pcbBytesNeeded], edi
0x180037307  jmp     loc_180037233
0x18003730c  call    cs:__imp_GetLastError
0x180037312  test    eax, eax
0x180037314  mov     ebx, eax
0x180037316  cmovz   ebx, r14d
0x18003731a  jmp     loc_18003721E
0x18003731f  call    cs:__imp_GetLastError
0x180037325  mov     ebx, eax
0x180037327  test    eax, eax
0x180037329  jz      loc_18003727D
0x18003732f  cmp     eax, 7Ah ; 'z'
0x180037332  jnz     loc_180037233
0x180037338  jmp     loc_180037282
0x18003733d  mov     ebx, 0Eh
0x180037342  jmp     loc_180037235
0x180037347  call    cs:__imp_GetLastError
0x18003734d  mov     ebx, eax
0x18003734f  test    eax, eax
0x180037351  jnz     loc_180037235
0x180037357  mov     ebx, r14d
0x18003735a  jmp     loc_180037235
0x18003735f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180037366  jz      loc_18003724B
0x18003736c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180037373  test    rax, rax
0x180037376  jz      short loc_180037391
0x180037378  mov     r8d, ebx
0x18003737b  lea     rdx, aGpServiceConfi; "GP Service config is unknown due to err"...
0x180037382  mov     ecx, 4
0x180037387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003738c  jmp     loc_18003724B
0x180037391  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180037399  jz      loc_18003724B
0x18003739f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800373a7  jz      loc_18003724B
0x1800373ad  mov     r8d, ebx
0x1800373b0  lea     rdx, aGpServiceConfi; "GP Service config is unknown due to err"...
0x1800373b7  mov     ecx, 4; unsigned int
0x1800373bc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800373c1  jmp     loc_18003724B
```

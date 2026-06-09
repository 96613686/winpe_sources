# CGPService::CreateGPSessions(ulong)

- ea: `0x180034c34`
- end: `0x1800350dc`
- name: `?CreateGPSessions@CGPService@@AEAAKK@Z`
- size: `1192`
- prototype: `__int64 __fastcall(CGPService *this, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035570`

## callees

- `0x180014080`
- `0x180014158`
- `0x180022bd4`
- `0x1800336a0`
- `0x180034c34`
- `0x18004d634`
- `0x180075578`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034e02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034eaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034e02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034eaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034cb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034cb3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034cfd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034cfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034d0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034d0e`
- `ntdll!EtwEventWrite` at `0x180034ddf`
- `ntdll!EtwEventWrite` at `0x180034ddf`
- `ntdll!EtwEventActivityIdControl` at `0x180034ed5`
- `ntdll!EtwEventActivityIdControl` at `0x180034ed5`

## string_xrefs

- `0x180034f6c`: `Detected that the service has been restarted after machine startup`
- `0x180034f9a`: `Detected that the service has been restarted after machine startup`

## pseudocode

```c
__int64 __fastcall CGPService::CreateGPSessions(CGPService *this, char a2)
{
  unsigned int v3; // r15d
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  int v5; // edx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  unsigned int EventDataDescriptorStorage; // eax
  _QWORD *v9; // rsi
  unsigned int v10; // r14d
  __int64 v11; // rax
  unsigned __int64 v12; // r12
  __int64 v13; // r8
  unsigned int v15; // eax
  HKEY v16; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-10h] BYREF
  __int64 v19; // [rsp+68h] [rbp-8h]
  DWORD dwDisposition; // [rsp+B0h] [rbp+40h] BYREF
  int v21; // [rsp+C0h] [rbp+50h] BYREF
  int v22; // [rsp+C8h] [rbp+58h] BYREF

  hKey = 0;
  v16 = 0;
  dwDisposition = 0;
  if ( *((_DWORD *)this + 32) )
  {
    if ( g_idleTimer )
      *((_DWORD *)this + 11) = 1;
    if ( (a2 & 1) != 0 )
      CGPService::CreateGPSessionsAtServiceRestart(this);
    else
      CGPService::CreateGPSessionsAtMachineStartup(this);
    XKey::Free((XKey *)&v16);
    XKey::Free((XKey *)&hKey);
    return 0;
  }
  else
  {
    if ( MakeRegKeySecure(0, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy", 0, 0, 0) )
    {
      v3 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy",
             0,
             0x20019u,
             &hKey);
      if ( !v3 )
      {
        v3 = RegCreateKeyExW(hKey, L"GPStartup", 0, 0, 1u, 4u, 0, &v16, &dwDisposition);
        if ( !v3 )
        {
          CGPService::s_ServiceStartTime = GetTickCount();
          if ( dwDisposition == 2 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Detected that the service has been restarted after machine startup");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Detected that the service has been restarted after machine startup");
              }
            }
            hMem = 0;
            v19 = 0;
            v22 = 0;
            v21 = 1;
            if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
            {
              v5 = HIDWORD(v19);
              v6 = 2LL * HIDWORD(v19);
              v7 = hMem;
              *((_QWORD *)hMem + v6) = &v21;
              v7[v6 + 1] = 4;
              HIDWORD(v19) = v5 + 1;
            }
            EventDataDescriptorStorage = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem);
            v9 = hMem;
            v10 = HIDWORD(v19);
            if ( !EventDataDescriptorStorage )
            {
              v11 = 2LL * HIDWORD(v19);
              *((_QWORD *)hMem + v11) = &v22;
              v9[v11 + 1] = 4;
              HIDWORD(v19) = ++v10;
            }
            v12 = CGPServiceEventReporting::s_pEventProviderHandle;
            v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
            if ( *(_BYTE *)(v13 + 8) == 1 )
            {
              v15 = EtwEventActivityIdControl(2, v13 + 16);
              if ( v15 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      2u,
                      L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                      v15);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      2u,
                      L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
                      v15);
                  }
                }
              }
            }
            if ( (unsigned int)EtwEventWrite(v12, gpEvent_GPSVC_START, v10, v9) )
              GetLastError();
            if ( g_idleTimer )
            {
              *((_DWORD *)this + 11) = 1;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"Manually set to trigger start due to restart and idle timer");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"Manually set to trigger start due to restart and idle timer");
                }
              }
            }
            if ( v9 )
              LocalFree(v9);
            CGPService::s_bMachineStartup = 0;
            CGPService::CreateGPSessionsAtServiceRestart(this);
          }
          else
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Detected that this is machine Startup");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Detected that this is machine Startup");
              }
            }
            hMem = 0;
            v19 = 0;
            CGPOperationalEvent::ReportEventW((CGPOperationalEvent *)&hMem, v4, 0, 1);
            *((_DWORD *)this + 31) = 1;
            if ( hMem )
              LocalFree(hMem);
            CGPService::s_bMachineStartup = 1;
            CGPService::CreateGPSessionsAtMachineStartup(this);
          }
        }
      }
    }
    else
    {
      v3 = 5;
    }
    if ( (unsigned __int64)v16 - 1 <= 0xFFFFFFFFFFFFFFFDuLL
      && (unsigned __int64)(v16 + 0x20000000) > 6
      && v16 != HKEY_PERFORMANCE_TEXT
      && v16 != HKEY_PERFORMANCE_NLSTEXT )
    {
      RegCloseKey(v16);
    }
    v16 = 0;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL
      && (unsigned __int64)(hKey + 0x20000000) > 6
      && hKey != HKEY_PERFORMANCE_TEXT
      && hKey != HKEY_PERFORMANCE_NLSTEXT )
    {
      RegCloseKey(hKey);
    }
    return v3;
  }
}

```

## disassembly

```asm
0x180034c34  mov     [rsp-38h+arg_8], rbx
0x180034c39  push    rbp
0x180034c3a  push    rsi
0x180034c3b  push    rdi
0x180034c3c  push    r12
0x180034c3e  push    r13
0x180034c40  push    r14
0x180034c42  push    r15
0x180034c44  mov     rbp, rsp
0x180034c47  sub     rsp, 70h
0x180034c4b  mov     rdi, rcx
0x180034c4e  xor     r13d, r13d
0x180034c51  mov     [rbp+hKey], r13
0x180034c55  mov     [rbp+var_20], r13
0x180034c59  mov     [rbp+dwDisposition], r13d
0x180034c5d  cmp     [rcx+80h], r13d
0x180034c64  jnz     loc_180034F19
0x180034c6a  mov     [rsp+70h+samDesired], r13d; int
0x180034c6f  mov     dword ptr [rsp+70h+phkResult], r13d; int
0x180034c74  xor     r9d, r9d; int
0x180034c77  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034c7e  mov     rbx, 0FFFFFFFF80000002h
0x180034c85  mov     rdx, rbx; HKEY
0x180034c88  xor     ecx, ecx; void *
0x180034c8a  call    ?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z; MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)
0x180034c8f  test    eax, eax
0x180034c91  jz      loc_180034F55
0x180034c97  lea     rax, [rbp+hKey]
0x180034c9b  mov     [rsp+70h+phkResult], rax; phkResult
0x180034ca0  mov     r9d, 20019h; samDesired
0x180034ca6  xor     r8d, r8d; ulOptions
0x180034ca9  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034cb0  mov     rcx, rbx; hKey
0x180034cb3  call    cs:__imp_RegOpenKeyExW
0x180034cb9  mov     r15d, eax
0x180034cbc  test    eax, eax
0x180034cbe  jnz     loc_180034E18
0x180034cc4  lea     rax, [rbp+dwDisposition]
0x180034cc8  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180034ccd  lea     rax, [rbp+var_20]
0x180034cd1  mov     [rsp+70h+var_38], rax; phkResult
0x180034cd6  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180034cdb  lea     r12d, [r13+4]
0x180034cdf  mov     [rsp+70h+samDesired], r12d; samDesired
0x180034ce4  lea     ebx, [r13+1]
0x180034ce8  mov     dword ptr [rsp+70h+phkResult], ebx; dwOptions
0x180034cec  xor     r9d, r9d; lpClass
0x180034cef  xor     r8d, r8d; Reserved
0x180034cf2  lea     rdx, aGpstartup; "GPStartup"
0x180034cf9  mov     rcx, [rbp+hKey]; hKey
0x180034cfd  call    cs:__imp_RegCreateKeyExW
0x180034d03  mov     r15d, eax
0x180034d06  test    eax, eax
0x180034d08  jnz     loc_180034E18
0x180034d0e  call    cs:__imp_GetTickCount
0x180034d14  mov     cs:?s_ServiceStartTime@CGPService@@0KA, eax; ulong CGPService::s_ServiceStartTime
0x180034d1a  cmp     [rbp+dwDisposition], 2
0x180034d1e  jnz     loc_180034E7F
0x180034d24  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180034d2b  jnz     loc_180034F60
0x180034d31  mov     [rbp+hMem], r13
0x180034d35  mov     [rbp+var_8], r13
0x180034d39  mov     [rbp+arg_18], r13d
0x180034d3d  mov     [rbp+arg_10], ebx
0x180034d40  lea     rcx, [rbp+hMem]; this
0x180034d44  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180034d49  test    eax, eax
0x180034d4b  jnz     short loc_180034D6F
0x180034d4d  mov     edx, dword ptr [rbp+var_8+4]
0x180034d50  mov     ecx, edx
0x180034d52  add     rcx, rcx
0x180034d55  mov     rax, [rbp+hMem]
0x180034d59  lea     r8, [rbp+arg_10]
0x180034d5d  mov     [rax+rcx*8], r8
0x180034d61  mov     qword ptr [rax+rcx*8+8], 4
0x180034d6a  add     edx, ebx
0x180034d6c  mov     dword ptr [rbp+var_8+4], edx
0x180034d6f  lea     rcx, [rbp+hMem]; this
0x180034d73  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180034d78  mov     rsi, [rbp+hMem]
0x180034d7c  test    eax, eax
0x180034d7e  jnz     loc_180034FAE
0x180034d84  mov     r14d, dword ptr [rbp+var_8+4]
0x180034d88  mov     eax, r14d
0x180034d8b  add     rax, rax
0x180034d8e  lea     rcx, [rbp+arg_18]
0x180034d92  mov     [rsi+rax*8], rcx
0x180034d96  mov     qword ptr [rsi+rax*8+8], 4
0x180034d9f  add     r14d, ebx
0x180034da2  mov     dword ptr [rbp+var_8+4], r14d
0x180034da6  mov     r12, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x180034dad  mov     ecx, cs:_tls_index
0x180034db3  mov     rax, gs:58h
0x180034dbc  mov     r8, [rax+rcx*8]
0x180034dc0  mov     eax, 8
0x180034dc5  cmp     [rax+r8], bl
0x180034dc9  jz      loc_180034EC8
0x180034dcf  mov     r9, rsi
0x180034dd2  mov     r8d, r14d
0x180034dd5  lea     rdx, gpEvent_GPSVC_START
0x180034ddc  mov     rcx, r12
0x180034ddf  call    cs:__imp_EtwEventWrite
0x180034de5  test    eax, eax
0x180034de7  jnz     loc_180034FE7
0x180034ded  cmp     cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA, r13; _TP_TIMER * g_idleTimer
0x180034df4  jnz     loc_180034FF2
0x180034dfa  test    rsi, rsi
0x180034dfd  jz      short loc_180034E08
0x180034dff  mov     rcx, rsi; hMem
0x180034e02  call    cs:__imp_LocalFree
0x180034e08  mov     cs:?s_bMachineStartup@CGPService@@0HA, r13d; int CGPService::s_bMachineStartup
0x180034e0f  mov     rcx, rdi; this
0x180034e12  call    ?CreateGPSessionsAtServiceRestart@CGPService@@AEAAKXZ; CGPService::CreateGPSessionsAtServiceRestart(void)
0x180034e17  nop
0x180034e18  mov     rcx, [rbp+var_20]; hKey
0x180034e1c  lea     rax, [rcx-1]
0x180034e20  mov     esi, 80000000h
0x180034e25  mov     rdi, 0FFFFFFFF80000050h
0x180034e2c  lea     rbx, [rdi+10h]
0x180034e30  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034e34  ja      short loc_180034E44
0x180034e36  lea     rax, [rcx+rsi]
0x180034e3a  cmp     rax, 6
0x180034e3e  ja      loc_1800350A2
0x180034e44  mov     [rbp+var_20], r13
0x180034e48  mov     rcx, [rbp+hKey]; hKey
0x180034e4c  lea     rax, [rcx-1]
0x180034e50  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034e54  ja      short loc_180034E64
0x180034e56  lea     rax, [rcx+rsi]
0x180034e5a  cmp     rax, 6
0x180034e5e  ja      loc_1800350BF
0x180034e64  mov     eax, r15d
0x180034e67  mov     rbx, [rsp+70h+arg_8]
0x180034e6f  add     rsp, 70h
0x180034e73  pop     r15
0x180034e75  pop     r14
0x180034e77  pop     r13
0x180034e79  pop     r12
0x180034e7b  pop     rdi
0x180034e7c  pop     rsi
0x180034e7d  pop     rbp
0x180034e7e  retn
0x180034e7f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180034e86  jnz     loc_180035054
0x180034e8c  mov     [rbp+hMem], r13
0x180034e90  mov     [rbp+var_8], r13
0x180034e94  mov     r9d, ebx; int
0x180034e97  xor     r8d, r8d; int
0x180034e9a  lea     rcx, [rbp+hMem]; this
0x180034e9e  call    ?ReportEventW@CGPOperationalEvent@@QEAAKPEBU_EVENT_DESCRIPTOR@@HH@Z; CGPOperationalEvent::ReportEventW(_EVENT_DESCRIPTOR const *,int,int)
0x180034ea3  mov     [rdi+7Ch], ebx
0x180034ea6  mov     rcx, [rbp+hMem]; hMem
0x180034eaa  test    rcx, rcx
0x180034ead  jz      short loc_180034EB5
0x180034eaf  call    cs:__imp_LocalFree
0x180034eb5  mov     cs:?s_bMachineStartup@CGPService@@0HA, ebx; int CGPService::s_bMachineStartup
0x180034ebb  mov     rcx, rdi; this
0x180034ebe  call    ?CreateGPSessionsAtMachineStartup@CGPService@@AEAAKXZ; CGPService::CreateGPSessionsAtMachineStartup(void)
0x180034ec3  jmp     loc_180034E18
0x180034ec8  mov     edx, 10h
0x180034ecd  add     rdx, r8
0x180034ed0  mov     ecx, 2
0x180034ed5  call    cs:__imp_EtwEventActivityIdControl
0x180034edb  mov     r8d, eax
0x180034ede  test    eax, eax
0x180034ee0  jz      loc_180034DCF
0x180034ee6  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180034eed  jz      loc_180034DCF
0x180034ef3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180034efa  test    rax, rax
0x180034efd  jz      loc_180034FB7
0x180034f03  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180034f0a  mov     ecx, 2
0x180034f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f14  jmp     loc_180034DCF
0x180034f19  mov     ebx, 1
0x180034f1e  cmp     cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA, r13; _TP_TIMER * g_idleTimer
0x180034f25  jz      short loc_180034F2A
0x180034f27  mov     [rcx+2Ch], ebx
0x180034f2a  test    bl, dl
0x180034f2c  jz      short loc_180034F35
0x180034f2e  call    ?CreateGPSessionsAtServiceRestart@CGPService@@AEAAKXZ; CGPService::CreateGPSessionsAtServiceRestart(void)
0x180034f33  jmp     short loc_180034F3B
0x180034f35  call    ?CreateGPSessionsAtMachineStartup@CGPService@@AEAAKXZ; CGPService::CreateGPSessionsAtMachineStartup(void)
0x180034f3a  nop
0x180034f3b  lea     rcx, [rbp+var_20]; this
0x180034f3f  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180034f44  nop
0x180034f45  lea     rcx, [rbp+hKey]; this
0x180034f49  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180034f4e  xor     eax, eax
0x180034f50  jmp     loc_180034E67
0x180034f55  mov     r15d, 5
0x180034f5b  jmp     loc_180034E18
0x180034f60  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180034f67  test    rax, rax
0x180034f6a  jz      short loc_180034F80
0x180034f6c  lea     rdx, aDetectedThatTh_1; "Detected that the service has been rest"...
0x180034f73  mov     ecx, r12d
0x180034f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f7b  jmp     loc_180034D31
0x180034f80  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180034f87  jz      loc_180034D31
0x180034f8d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180034f94  jz      loc_180034D31
0x180034f9a  lea     rdx, aDetectedThatTh_1; "Detected that the service has been rest"...
0x180034fa1  mov     ecx, r12d; unsigned int
0x180034fa4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180034fa9  jmp     loc_180034D31
0x180034fae  mov     r14d, dword ptr [rbp+var_8+4]
0x180034fb2  jmp     loc_180034DA6
0x180034fb7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180034fbe  jz      loc_180034DCF
0x180034fc4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180034fcb  jz      loc_180034DCF
0x180034fd1  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180034fd8  mov     ecx, 2; unsigned int
0x180034fdd  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180034fe2  jmp     loc_180034DCF
0x180034fe7  call    cs:__imp_GetLastError
0x180034fed  jmp     loc_180034DED
0x180034ff2  mov     [rdi+2Ch], ebx
0x180034ff5  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180034ffc  jz      loc_180034DFA
0x180035002  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180035009  test    rax, rax
0x18003500c  jz      short loc_180035024
0x18003500e  lea     rdx, aManuallySetToT; "Manually set to trigger start due to re"...
0x180035015  mov     ecx, 4
0x18003501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501f  jmp     loc_180034DFA
0x180035024  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003502b  jz      loc_180034DFA
0x180035031  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035038  jz      loc_180034DFA
0x18003503e  lea     rdx, aManuallySetToT; "Manually set to trigger start due to re"...
0x180035045  mov     ecx, 4; unsigned int
0x18003504a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003504f  jmp     loc_180034DFA
0x180035054  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003505b  test    rax, rax
0x18003505e  jz      short loc_180035074
0x180035060  lea     rdx, aDetectedThatTh; "Detected that this is machine Startup"
0x180035067  mov     ecx, r12d
0x18003506a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003506f  jmp     loc_180034E8C
0x180035074  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003507b  jz      loc_180034E8C
0x180035081  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035088  jz      loc_180034E8C
0x18003508e  lea     rdx, aDetectedThatTh; "Detected that this is machine Startup"
0x180035095  mov     ecx, r12d; unsigned int
0x180035098  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003509d  jmp     loc_180034E8C
0x1800350a2  cmp     rcx, rdi
0x1800350a5  jz      loc_180034E44
0x1800350ab  cmp     rcx, rbx
0x1800350ae  jz      loc_180034E44
0x1800350b4  call    cs:__imp_RegCloseKey
0x1800350ba  jmp     loc_180034E44
0x1800350bf  cmp     rcx, rdi
0x1800350c2  jz      loc_180034E64
0x1800350c8  cmp     rcx, rbx
0x1800350cb  jz      loc_180034E64
0x1800350d1  call    cs:__imp_RegCloseKey
0x1800350d7  jmp     loc_180034E64
```

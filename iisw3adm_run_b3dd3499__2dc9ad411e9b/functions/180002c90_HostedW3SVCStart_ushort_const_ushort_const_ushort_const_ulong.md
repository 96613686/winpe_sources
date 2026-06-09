# HostedW3SVCStart(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180002c90`
- end: `0x180003157`
- name: `?HostedW3SVCStart@@YAJPEBG00K@Z`
- size: `1223`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001234`
- `0x180002c90`
- `0x180003160`
- `0x180003a84`
- `0x180053bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002df7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002df7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003085`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180002ff0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000307b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180002ff0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000307b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002da2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002eff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002da2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002eff`
- `iisutil!PuDbgPrintError` at `0x180002ecc`
- `iisutil!PuDbgPrintError` at `0x180003131`
- `iisutil!PuDbgPrintError` at `0x180002ecc`
- `iisutil!PuDbgPrintError` at `0x180003131`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d29`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d3f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d29`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d3f`

## string_xrefs

- `0x180002ec1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\main.cxx`
- `0x18000312a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\main.cxx`
- `0x180002dd9`: `CreateThread() failed\n`
- `0x180002f32`: `CreateThread() failed\n`
- `0x180003102`: `Allocating WEB_ADMIN_SERVICE for hosted W3SVC failed\n`
- `0x18000301f`: `Main thread for hosted W3SVC failed\n`
- `0x1800030aa`: `Main thread for hosted W3SVC failed\n`
- `0x180002e53`: `Allocating HTTP_SERVICE for hosted W3SVC failed\n`

## pseudocode

```c
__int64 __fastcall HostedW3SVCStart(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  WEB_ADMIN_SERVICE *v8; // rax
  WEB_ADMIN_SERVICE *v9; // rax
  WEB_ADMIN_SERVICE *v10; // rbx
  int v11; // edi
  signed int v12; // ebx
  HANDLE Thread; // rax
  signed int LastError; // eax
  DWORD v15; // eax
  int v16; // eax
  signed int v17; // eax
  __int64 v18; // r8
  bool v19; // sf
  HANDLE v20; // rax
  signed int v21; // eax
  HANDLE v22; // rcx
  int v23; // eax
  bool v24; // cc
  DWORD v25; // eax
  signed int v26; // eax
  bool v27; // cc
  signed int v28; // eax
  signed int v29; // eax
  int v30; // ecx
  DWORD ExitCode[6]; // [rsp+30h] [rbp-18h] BYREF

  ExitCode[0] = 0;
  ExitCode[1] = 0;
  if ( g_pWebAdminService || g_pHttpService )
    return 2147943456LL;
  v8 = (WEB_ADMIN_SERVICE *)operator new(0x740u);
  if ( !v8 )
  {
    g_pWebAdminService = 0;
LABEL_78:
    v12 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1065,
        "HostedW3SVCStart",
        -2147024888,
        "Allocating WEB_ADMIN_SERVICE for hosted W3SVC failed\n");
    goto LABEL_80;
  }
  v9 = WEB_ADMIN_SERVICE::WEB_ADMIN_SERVICE(v8, 1);
  g_pWebAdminService = v9;
  v10 = v9;
  if ( !v9 )
    goto LABEL_78;
  v11 = STRU::Copy((WEB_ADMIN_SERVICE *)((char *)v9 + 1656), a1);
  if ( v11 < 0
    || (v11 = STRU::Copy((WEB_ADMIN_SERVICE *)((char *)v10 + 1712), a2), v11 < 0)
    || (v11 = STRU::Copy((WEB_ADMIN_SERVICE *)((char *)v10 + 1768), a3), v11 < 0) )
  {
    v12 = v11;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1088,
        "HostedW3SVCStart",
        v11,
        "Initializing of hosted W3SVC failed\n");
    goto LABEL_80;
  }
  *((_DWORD *)v10 + 456) = a4;
  Thread = CreateThread(0, 0x8000u, HostedWASThreadProc, 0, 0, &ExitCode[1]);
  g_hHostedWASMainThread = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    ExitCode[0] = LastError;
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1113,
        "HostedW3SVCStart",
        v12,
        "CreateThread() failed\n",
        *(_QWORD *)ExitCode);
    goto LABEL_29;
  }
  v12 = v11;
  v15 = WaitForSingleObject(Thread, 0xC8u);
  if ( v15 == -1 )
  {
LABEL_24:
    v17 = GetLastError();
    ExitCode[0] = v17;
    v12 = v17;
    if ( v17 > 0 )
      v12 = (unsigned __int16)v17 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v18 = 1139;
LABEL_28:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        v18,
        "HostedW3SVCStart",
        v12,
        "WaitForSingleObject() failed\n",
        *(_QWORD *)ExitCode);
    }
LABEL_29:
    v19 = v12 < 0;
    goto LABEL_30;
  }
  while ( v15 != 258 )
  {
    if ( !v15 )
    {
      if ( !GetExitCodeThread(g_hHostedWASMainThread, ExitCode) )
      {
        v29 = GetLastError();
        ExitCode[0] = v29;
        v12 = v29;
        if ( v29 > 0 )
          v12 = (unsigned __int16)v29 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
            1184,
            "HostedW3SVCStart",
            v12,
            "Main thread for hosted W3SVC failed\n",
            *(_QWORD *)ExitCode);
        goto LABEL_29;
      }
      v12 = ExitCode[0];
      v19 = (ExitCode[0] & 0x80000000) != 0;
      v27 = (signed int)ExitCode[0] <= 0;
      if ( !ExitCode[0] )
      {
        v30 = *((_DWORD *)g_pWebAdminService + 285);
        if ( v30 >= 0 )
          v30 = -2147467259;
        v12 = v30;
        goto LABEL_80;
      }
LABEL_72:
      if ( !v27 )
      {
        v12 = (unsigned __int16)v12;
LABEL_65:
        v12 |= 0x80070000;
        goto LABEL_29;
      }
LABEL_30:
      if ( v19 )
        goto LABEL_80;
      return (unsigned int)v12;
    }
LABEL_23:
    v15 = WaitForSingleObject(g_hHostedWASMainThread, 0xC8u);
    if ( v15 == -1 )
      goto LABEL_24;
  }
  if ( *((_DWORD *)g_pWebAdminService + 283) != 4 )
    goto LABEL_23;
  v16 = *((_DWORD *)g_pWebAdminService + 391);
  if ( v16 )
  {
    v12 = *((_DWORD *)g_pWebAdminService + 391);
    if ( v16 <= 0 )
      goto LABEL_29;
    v12 = (unsigned __int16)v16;
    goto LABEL_65;
  }
  HTTP_SERVICE::CreateHttpService(1);
  if ( !g_pHttpService )
  {
    v12 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1227,
        "HostedW3SVCStart",
        -2147024888,
        "Allocating HTTP_SERVICE for hosted W3SVC failed\n");
    goto LABEL_80;
  }
  v20 = CreateThread(0, 0x8000u, HostedW3SVCThreadProc, 0, 0, &ExitCode[1]);
  g_hHostedW3SVCMainThread = v20;
  if ( !v20 )
  {
    v21 = GetLastError();
    ExitCode[0] = v21;
    v12 = v21;
    if ( v21 > 0 )
      v12 = (unsigned __int16)v21 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1259,
        "HostedW3SVCStart",
        v12,
        "CreateThread() failed\n",
        *(_QWORD *)ExitCode);
    goto LABEL_29;
  }
  v22 = v20;
  while ( 2 )
  {
    v25 = WaitForSingleObject(v22, 0xC8u);
    if ( v25 == -1 )
    {
      v26 = GetLastError();
      ExitCode[0] = v26;
      v12 = v26;
      if ( v26 > 0 )
        v12 = (unsigned __int16)v26 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v18 = 1285;
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    if ( v25 == 258 )
    {
      if ( *((_DWORD *)g_pHttpService + 3) == 4 )
      {
        v23 = *((_DWORD *)g_pWebAdminService + 392);
        v24 = v23 <= 0;
        if ( !v23 )
        {
          if ( !*((_DWORD *)g_pWebAdminService + 391) )
            return (unsigned int)v12;
          v24 = 1;
        }
        if ( v24 )
          v12 = *((_DWORD *)g_pWebAdminService + 392);
        else
          v12 = (unsigned __int16)v23 | 0x80070000;
        v19 = v12 < 0;
        if ( !v12 )
        {
          v12 = *((_DWORD *)g_pWebAdminService + 391);
          v19 = v12 < 0;
          v27 = v12 <= 0;
          goto LABEL_72;
        }
        goto LABEL_30;
      }
      goto LABEL_46;
    }
    if ( v25 )
    {
LABEL_46:
      v22 = g_hHostedW3SVCMainThread;
      continue;
    }
    break;
  }
  if ( !GetExitCodeThread(g_hHostedW3SVCMainThread, ExitCode) )
  {
    v28 = GetLastError();
    ExitCode[0] = v28;
    v12 = v28;
    if ( v28 > 0 )
      v12 = (unsigned __int16)v28 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
        1345,
        "HostedW3SVCStart",
        v12,
        "Main thread for hosted W3SVC failed\n",
        *(_QWORD *)ExitCode);
    goto LABEL_29;
  }
  v12 = ExitCode[0];
  v19 = (ExitCode[0] & 0x80000000) != 0;
  v27 = (signed int)ExitCode[0] <= 0;
  if ( ExitCode[0] )
    goto LABEL_72;
  v12 = *((_DWORD *)g_pHttpService + 5);
  if ( v12 >= 0 )
  {
    v12 = -2147467259;
    goto LABEL_29;
  }
LABEL_80:
  HostedW3SVCStop(1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180002c90  push    rbp
0x180002c92  push    rbx
0x180002c93  push    rsi
0x180002c94  push    rdi
0x180002c95  push    r14
0x180002c97  push    r15
0x180002c99  mov     rbp, rsp
0x180002c9c  sub     rsp, 48h
0x180002ca0  cmp     cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA, 0; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180002ca8  mov     r15d, r9d
0x180002cab  mov     r14, r8
0x180002cae  mov     [rbp+ExitCode], 0
0x180002cb5  mov     rsi, rdx
0x180002cb8  mov     [rbp+ThreadId], 0
0x180002cbf  mov     rdi, rcx
0x180002cc2  jnz     loc_180003145
0x180002cc8  cmp     cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA, 0; HTTP_SERVICE * g_pHttpService
0x180002cd0  jnz     loc_180003145
0x180002cd6  mov     ecx, 740h; Size
0x180002cdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ce0  test    rax, rax
0x180002ce3  jz      loc_1800030E9
0x180002ce9  mov     edx, 1; int
0x180002cee  mov     rcx, rax; this
0x180002cf1  call    ??0WEB_ADMIN_SERVICE@@QEAA@H@Z; WEB_ADMIN_SERVICE::WEB_ADMIN_SERVICE(int)
0x180002cf6  mov     cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA, rax; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180002cfd  mov     rbx, rax
0x180002d00  test    rax, rax
0x180002d03  jz      loc_1800030F4
0x180002d09  lea     rcx, [rax+678h]
0x180002d10  mov     rdx, rdi
0x180002d13  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002d19  mov     edi, eax
0x180002d1b  test    eax, eax
0x180002d1d  js      short loc_180002D4B
0x180002d1f  lea     rcx, [rbx+6B0h]
0x180002d26  mov     rdx, rsi
0x180002d29  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002d2f  mov     edi, eax
0x180002d31  test    eax, eax
0x180002d33  js      short loc_180002D4B
0x180002d35  lea     rcx, [rbx+6E8h]
0x180002d3c  mov     rdx, r14
0x180002d3f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002d45  mov     edi, eax
0x180002d47  test    eax, eax
0x180002d49  jns     short loc_180002D75
0x180002d4b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002d52  mov     ebx, edi
0x180002d54  jz      loc_180003137
0x180002d5a  lea     rax, aInitializingOf; "Initializing of hosted W3SVC failed\n"
0x180002d61  mov     r8d, 440h
0x180002d67  mov     [rsp+48h+lpThreadId], rax
0x180002d6c  mov     [rsp+48h+dwCreationFlags], edi
0x180002d70  jmp     loc_18000311C
0x180002d75  mov     [rbx+720h], r15d
0x180002d7c  lea     rax, [rbp+ThreadId]
0x180002d80  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180002d85  lea     r8, ?HostedWASThreadProc@@YAKPEAX@Z; lpStartAddress
0x180002d8c  mov     r15d, 8000h
0x180002d92  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180002d9a  mov     edx, r15d; dwStackSize
0x180002d9d  xor     r9d, r9d; lpParameter
0x180002da0  xor     ecx, ecx; lpThreadAttributes
0x180002da2  call    cs:__imp_CreateThread
0x180002da8  mov     cs:?g_hHostedWASMainThread@@3PEAXEA, rax; void * g_hHostedWASMainThread
0x180002daf  test    rax, rax
0x180002db2  jnz     short loc_180002DEB
0x180002db4  call    cs:__imp_GetLastError
0x180002dba  mov     [rbp+ExitCode], eax
0x180002dbd  mov     ebx, eax
0x180002dbf  test    eax, eax
0x180002dc1  jle     short loc_180002DCC
0x180002dc3  movzx   ebx, ax
0x180002dc6  or      ebx, 80070000h
0x180002dcc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002dd3  jz      loc_180002ED2
0x180002dd9  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x180002de0  mov     r8d, 459h
0x180002de6  jmp     loc_180002EAE
0x180002deb  mov     ebx, edi
0x180002ded  mov     rcx, rax; hHandle
0x180002df0  mov     edi, 0C8h
0x180002df5  mov     edx, edi; dwMilliseconds
0x180002df7  call    cs:__imp_WaitForSingleObject
0x180002dfd  or      esi, 0FFFFFFFFh
0x180002e00  cmp     eax, esi
0x180002e02  jz      short loc_180002E80
0x180002e04  lea     r14d, [rdi+3Ah]
0x180002e08  cmp     eax, r14d
0x180002e0b  jnz     short loc_180002E65
0x180002e0d  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180002e14  cmp     dword ptr [rcx+46Ch], 4
0x180002e1b  jnz     short loc_180002E6D
0x180002e1d  mov     eax, [rcx+61Ch]
0x180002e23  test    eax, eax
0x180002e25  jnz     loc_180003058
0x180002e2b  lea     ecx, [rax+1]; int
0x180002e2e  call    ?CreateHttpService@HTTP_SERVICE@@SAXH@Z; HTTP_SERVICE::CreateHttpService(int)
0x180002e33  cmp     cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA, 0; HTTP_SERVICE * g_pHttpService
0x180002e3b  jnz     loc_180002EDF
0x180002e41  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002e48  mov     ebx, 80070008h
0x180002e4d  jz      loc_180003137
0x180002e53  lea     rax, aAllocatingHttp; "Allocating HTTP_SERVICE for hosted W3SV"...
0x180002e5a  mov     r8d, 4CBh
0x180002e60  jmp     loc_18000310F
0x180002e65  test    eax, eax
0x180002e67  jz      loc_180003070
0x180002e6d  mov     rcx, cs:?g_hHostedWASMainThread@@3PEAXEA; hHandle
0x180002e74  mov     edx, edi; dwMilliseconds
0x180002e76  call    cs:__imp_WaitForSingleObject
0x180002e7c  cmp     eax, esi
0x180002e7e  jnz     short loc_180002E08
0x180002e80  call    cs:__imp_GetLastError
0x180002e86  mov     [rbp+ExitCode], eax
0x180002e89  mov     ebx, eax
0x180002e8b  test    eax, eax
0x180002e8d  jle     short loc_180002E98
0x180002e8f  movzx   ebx, ax
0x180002e92  or      ebx, 80070000h
0x180002e98  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002e9f  jz      short loc_180002ED2
0x180002ea1  mov     r8d, 473h
0x180002ea7  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x180002eae  mov     rcx, cs:g_pDebug
0x180002eb5  lea     r9, aHostedw3svcsta_0; "HostedW3SVCStart"
0x180002ebc  mov     [rsp+48h+lpThreadId], rax
0x180002ec1  lea     rdx, aServercommonIn_39; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002ec8  mov     [rsp+48h+dwCreationFlags], ebx
0x180002ecc  call    cs:__imp_PuDbgPrintError
0x180002ed2  test    ebx, ebx
0x180002ed4  jns     loc_180003141
0x180002eda  jmp     loc_180003137
0x180002edf  lea     rax, [rbp+ThreadId]
0x180002ee3  xor     r9d, r9d; lpParameter
0x180002ee6  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180002eeb  lea     r8, ?HostedW3SVCThreadProc@@YAKPEAX@Z; lpStartAddress
0x180002ef2  mov     rdx, r15; dwStackSize
0x180002ef5  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180002efd  xor     ecx, ecx; lpThreadAttributes
0x180002eff  call    cs:__imp_CreateThread
0x180002f05  mov     cs:?g_hHostedW3SVCMainThread@@3PEAXEA, rax; void * g_hHostedW3SVCMainThread
0x180002f0c  test    rax, rax
0x180002f0f  jnz     short loc_180002F44
0x180002f11  call    cs:__imp_GetLastError
0x180002f17  mov     [rbp+ExitCode], eax
0x180002f1a  mov     ebx, eax
0x180002f1c  test    eax, eax
0x180002f1e  jle     short loc_180002F29
0x180002f20  movzx   ebx, ax
0x180002f23  or      ebx, 80070000h
0x180002f29  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002f30  jz      short loc_180002ED2
0x180002f32  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x180002f39  mov     r8d, 4EBh
0x180002f3f  jmp     loc_180002EAE
0x180002f44  mov     rcx, rax
0x180002f47  jmp     short loc_180002F8B
0x180002f49  cmp     eax, r14d
0x180002f4c  jnz     short loc_180002F80
0x180002f4e  mov     rax, cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA; HTTP_SERVICE * g_pHttpService
0x180002f55  cmp     dword ptr [rax+0Ch], 4
0x180002f59  jnz     short loc_180002F84
0x180002f5b  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180002f62  mov     eax, [rcx+620h]
0x180002f68  test    eax, eax
0x180002f6a  jnz     short loc_180002F7A
0x180002f6c  cmp     [rcx+61Ch], eax
0x180002f72  jz      loc_180003141
0x180002f78  test    eax, eax
0x180002f7a  jg      short loc_180002FC7
0x180002f7c  mov     ebx, eax
0x180002f7e  jmp     short loc_180002FD0
0x180002f80  test    eax, eax
0x180002f82  jz      short loc_180002FE5
0x180002f84  mov     rcx, cs:?g_hHostedW3SVCMainThread@@3PEAXEA; hHandle
0x180002f8b  mov     edx, edi; dwMilliseconds
0x180002f8d  call    cs:__imp_WaitForSingleObject
0x180002f93  cmp     eax, esi
0x180002f95  jnz     short loc_180002F49
0x180002f97  call    cs:__imp_GetLastError
0x180002f9d  mov     [rbp+ExitCode], eax
0x180002fa0  mov     ebx, eax
0x180002fa2  test    eax, eax
0x180002fa4  jle     short loc_180002FAF
0x180002fa6  movzx   ebx, ax
0x180002fa9  or      ebx, 80070000h
0x180002faf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002fb6  jz      loc_180002ED2
0x180002fbc  mov     r8d, 505h
0x180002fc2  jmp     loc_180002EA7
0x180002fc7  movzx   ebx, ax
0x180002fca  or      ebx, 80070000h
0x180002fd0  test    ebx, ebx
0x180002fd2  jnz     loc_180002ED4
0x180002fd8  mov     ebx, [rcx+61Ch]
0x180002fde  test    ebx, ebx
0x180002fe0  jmp     loc_1800030C3
0x180002fe5  mov     rcx, cs:?g_hHostedW3SVCMainThread@@3PEAXEA; hThread
0x180002fec  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180002ff0  call    cs:__imp_GetExitCodeThread
0x180002ff6  test    eax, eax
0x180002ff8  jnz     short loc_180003031
0x180002ffa  call    cs:__imp_GetLastError
0x180003000  mov     [rbp+ExitCode], eax
0x180003003  mov     ebx, eax
0x180003005  test    eax, eax
0x180003007  jle     short loc_180003012
0x180003009  movzx   ebx, ax
0x18000300c  or      ebx, 80070000h
0x180003012  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003019  jz      loc_180002ED2
0x18000301f  lea     rax, aMainThreadForH; "Main thread for hosted W3SVC failed\n"
0x180003026  mov     r8d, 541h
0x18000302c  jmp     loc_180002EAE
0x180003031  mov     ebx, [rbp+ExitCode]
0x180003034  test    ebx, ebx
0x180003036  jnz     loc_1800030C3
0x18000303c  mov     rax, cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA; HTTP_SERVICE * g_pHttpService
0x180003043  mov     ebx, [rax+14h]
0x180003046  test    ebx, ebx
0x180003048  js      loc_180003137
0x18000304e  mov     ebx, 80004005h
0x180003053  jmp     loc_180002ED2
0x180003058  mov     ebx, eax
0x18000305a  test    eax, eax
0x18000305c  jle     loc_180002ED2
0x180003062  movzx   ebx, ax
0x180003065  or      ebx, 80070000h
0x18000306b  jmp     loc_180002ED2
0x180003070  mov     rcx, cs:?g_hHostedWASMainThread@@3PEAXEA; hThread
0x180003077  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18000307b  call    cs:__imp_GetExitCodeThread
0x180003081  test    eax, eax
0x180003083  jnz     short loc_1800030BC
0x180003085  call    cs:__imp_GetLastError
0x18000308b  mov     [rbp+ExitCode], eax
0x18000308e  mov     ebx, eax
0x180003090  test    eax, eax
0x180003092  jle     short loc_18000309D
0x180003094  movzx   ebx, ax
0x180003097  or      ebx, 80070000h
0x18000309d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800030a4  jz      loc_180002ED2
0x1800030aa  lea     rax, aMainThreadForH; "Main thread for hosted W3SVC failed\n"
0x1800030b1  mov     r8d, 4A0h
0x1800030b7  jmp     loc_180002EAE
0x1800030bc  mov     ebx, [rbp+ExitCode]
0x1800030bf  test    ebx, ebx
0x1800030c1  jz      short loc_1800030CE
0x1800030c3  jle     loc_180002ED4
0x1800030c9  movzx   ebx, bx
0x1800030cc  jmp     short loc_180003065
0x1800030ce  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800030d5  mov     ebx, 80004005h
0x1800030da  mov     ecx, [rax+474h]
0x1800030e0  test    ecx, ecx
0x1800030e2  cmovns  ecx, ebx
0x1800030e5  mov     ebx, ecx
0x1800030e7  jmp     short loc_180003137
0x1800030e9  mov     cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA, 0; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800030f4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800030fb  mov     ebx, 80070008h
0x180003100  jz      short loc_180003137
0x180003102  lea     rax, aAllocatingWebA; "Allocating WEB_ADMIN_SERVICE for hosted"...
0x180003109  mov     r8d, 429h
0x18000310f  mov     [rsp+48h+lpThreadId], rax
0x180003114  mov     [rsp+48h+dwCreationFlags], 80070008h
0x18000311c  mov     rcx, cs:g_pDebug
0x180003123  lea     r9, aHostedw3svcsta_0; "HostedW3SVCStart"
0x18000312a  lea     rdx, aServercommonIn_39; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003131  call    cs:__imp_PuDbgPrintError
0x180003137  mov     ecx, 1; int
0x18000313c  call    ?HostedW3SVCStop@@YAJH@Z; HostedW3SVCStop(int)
0x180003141  mov     eax, ebx
0x180003143  jmp     short loc_18000314A
0x180003145  mov     eax, 80070420h
0x18000314a  add     rsp, 48h
0x18000314e  pop     r15
0x180003150  pop     r14
0x180003152  pop     rdi
0x180003153  pop     rsi
0x180003154  pop     rbx
0x180003155  pop     rbp
0x180003156  retn
```

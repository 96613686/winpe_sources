# WORKER_PROCESS::StartInprocHostableWebCore(void)

- ea: `0x180026da4`
- end: `0x180027002`
- name: `?StartInprocHostableWebCore@WORKER_PROCESS@@AEAAJXZ`
- size: `606`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023c8c`

## callees

- `0x180001234`
- `0x180001274`
- `0x180026da4`
- `0x180042180`
- `0x180042250`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f42`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026f2b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026f2b`
- `iisutil!PuDbgPrintError` at `0x180026f8b`
- `iisutil!PuDbgPrintError` at `0x180026fee`
- `iisutil!PuDbgPrintError` at `0x180026f8b`
- `iisutil!PuDbgPrintError` at `0x180026fee`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180026ebf`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180026ebf`

## string_xrefs

- `0x180026f67`: `CreateThread() failed\n`
- `0x180026f84`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180026fe7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180026fc6`: `Only one attempt to start hostable webcore is allowed\n`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::StartInprocHostableWebCore(WORKER_PROCESS *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  WEB_ADMIN_SERVICE *v10; // rcx
  signed int DefaultNativeConfigurationSystem; // edi
  HANDLE Thread; // rax
  signed int LastError; // eax
  struct INativeConfigurationSystem *v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  if ( WORKER_PROCESS::sm_InprocHostableWebcoreStartAttempts || *((_QWORD *)this + 11) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        3585,
        "WORKER_PROCESS::StartInprocHostableWebCore",
        -2147024809,
        "Only one attempt to start hostable webcore is allowed\n");
    return 2147942487LL;
  }
  else
  {
    v2 = operator new(0x70u);
    v3 = v2;
    if ( v2 )
    {
      *v2 = 0;
      v2[1] = 0;
      *((_DWORD *)v2 + 4) = 0;
      v2[3] = 0;
      v2[4] = 0;
      v2[5] = 0;
      v2[6] = 0;
      *((_DWORD *)v2 + 14) = 0;
      v2[8] = 0;
      v2[9] = 0;
      v2[10] = 0;
      v2[11] = 0;
      *((_DWORD *)v2 + 24) = 1;
      v2[13] = 0;
      *v2 = *(_QWORD *)(*((_QWORD *)this + 5) + 72LL);
      v2[3] = *(_QWORD *)(*((_QWORD *)this + 7) + 56LL);
      v4 = *((_QWORD *)this + 8);
      if ( *(_DWORD *)(v4 + 456) )
        v5 = *(_QWORD *)(v4 + 440);
      else
        v5 = 0;
      v3[5] = v5;
      v6 = *((_QWORD *)this + 8);
      if ( *(_DWORD *)(v6 + 512) )
        v7 = *(_QWORD *)(v6 + 496);
      else
        v7 = 0;
      v3[13] = v7;
      v8 = *((_QWORD *)this + 8);
      if ( *(_DWORD *)(v8 + 568) )
        v9 = *(_QWORD *)(v8 + 552);
      else
        v9 = 0;
      ++WORKER_PROCESS::sm_InprocHostableWebcoreStartAttempts;
      v3[6] = v9;
      *((_DWORD *)v3 + 14) = *(_DWORD *)(*((_QWORD *)this + 8) + 576LL);
      v10 = g_pWebAdminService;
      v3[8] = *((_QWORD *)g_pWebAdminService + 211);
      v3[9] = *((_QWORD *)v10 + 218);
      *((_DWORD *)v3 + 22) = 1;
      DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v15);
      if ( DefaultNativeConfigurationSystem >= 0 )
      {
        DefaultNativeConfigurationSystem = CONFIG_CS_PATH_MAPPER::SetConfigPathMapper(v15, 1);
        if ( DefaultNativeConfigurationSystem >= 0 )
        {
          DefaultNativeConfigurationSystem = CONFIG_CS_PATH_MAPPER::SetConfigFileMappings(
                                               v15,
                                               *((const unsigned __int16 **)g_pWebAdminService + 211),
                                               *((const unsigned __int16 **)g_pWebAdminService + 218));
          if ( DefaultNativeConfigurationSystem >= 0 )
          {
            Thread = CreateThread(0, 0x8000u, (LPTHREAD_START_ROUTINE)HostableWebCoreThreadProc, v3, 0, 0);
            *((_QWORD *)this + 11) = Thread;
            if ( Thread )
            {
              DefaultNativeConfigurationSystem = 0;
            }
            else
            {
              operator delete(v3);
              LastError = GetLastError();
              DefaultNativeConfigurationSystem = LastError;
              if ( LastError > 0 )
                DefaultNativeConfigurationSystem = (unsigned __int16)LastError | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
                  3662,
                  "WORKER_PROCESS::StartInprocHostableWebCore",
                  DefaultNativeConfigurationSystem,
                  "CreateThread() failed\n");
            }
          }
        }
      }
      if ( v15 )
        (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v15 + 16LL))(v15);
      return (unsigned int)DefaultNativeConfigurationSystem;
    }
    else
    {
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180026da4  push    rbx
0x180026da6  push    rbp
0x180026da7  push    rsi
0x180026da8  push    rdi
0x180026da9  sub     rsp, 38h
0x180026dad  xor     ebp, ebp
0x180026daf  mov     rsi, rcx
0x180026db2  cmp     cs:?sm_InprocHostableWebcoreStartAttempts@WORKER_PROCESS@@0KA, ebp; ulong WORKER_PROCESS::sm_InprocHostableWebcoreStartAttempts
0x180026db8  mov     [rsp+58h+arg_8], rbp
0x180026dbd  jnz     loc_180026FB6
0x180026dc3  cmp     [rcx+58h], rbp
0x180026dc7  jnz     loc_180026FB6
0x180026dcd  lea     ecx, [rbp+70h]; Size
0x180026dd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026dd5  mov     rbx, rax
0x180026dd8  test    rax, rax
0x180026ddb  jz      loc_180026FAF
0x180026de1  mov     [rax], rbp
0x180026de4  mov     [rax+8], rbp
0x180026de8  mov     [rax+10h], ebp
0x180026deb  mov     [rax+18h], rbp
0x180026def  mov     [rax+20h], rbp
0x180026df3  mov     [rax+28h], rbp
0x180026df7  mov     [rax+30h], rbp
0x180026dfb  mov     [rax+38h], ebp
0x180026dfe  mov     [rax+40h], rbp
0x180026e02  mov     [rax+48h], rbp
0x180026e06  mov     [rax+50h], rbp
0x180026e0a  mov     [rax+58h], rbp
0x180026e0e  mov     dword ptr [rax+60h], 1
0x180026e15  mov     [rax+68h], rbp
0x180026e19  mov     rax, [rsi+28h]
0x180026e1d  mov     rcx, [rax+48h]
0x180026e21  mov     [rbx], rcx
0x180026e24  mov     rax, [rsi+38h]
0x180026e28  mov     rcx, [rax+38h]
0x180026e2c  mov     [rbx+18h], rcx
0x180026e30  mov     rax, [rsi+40h]
0x180026e34  cmp     [rax+1C8h], ebp
0x180026e3a  jnz     short loc_180026E40
0x180026e3c  mov     eax, ebp
0x180026e3e  jmp     short loc_180026E47
0x180026e40  mov     rax, [rax+1B8h]
0x180026e47  mov     [rbx+28h], rax
0x180026e4b  mov     rax, [rsi+40h]
0x180026e4f  cmp     [rax+200h], ebp
0x180026e55  jnz     short loc_180026E5C
0x180026e57  mov     rax, rbp
0x180026e5a  jmp     short loc_180026E63
0x180026e5c  mov     rax, [rax+1F0h]
0x180026e63  mov     [rbx+68h], rax
0x180026e67  mov     rax, [rsi+40h]
0x180026e6b  cmp     [rax+238h], ebp
0x180026e71  jnz     short loc_180026E78
0x180026e73  mov     rax, rbp
0x180026e76  jmp     short loc_180026E7F
0x180026e78  mov     rax, [rax+228h]
0x180026e7f  inc     cs:?sm_InprocHostableWebcoreStartAttempts@WORKER_PROCESS@@0KA; ulong WORKER_PROCESS::sm_InprocHostableWebcoreStartAttempts
0x180026e85  mov     [rbx+30h], rax
0x180026e89  mov     rax, [rsi+40h]
0x180026e8d  mov     ecx, [rax+240h]
0x180026e93  mov     [rbx+38h], ecx
0x180026e96  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180026e9d  mov     rax, [rcx+698h]
0x180026ea4  mov     [rbx+40h], rax
0x180026ea8  mov     rax, [rcx+6D0h]
0x180026eaf  lea     rcx, [rsp+58h+arg_8]
0x180026eb4  mov     [rbx+48h], rax
0x180026eb8  mov     dword ptr [rbx+58h], 1
0x180026ebf  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180026ec5  mov     edi, eax
0x180026ec7  test    eax, eax
0x180026ec9  js      loc_180026F95
0x180026ecf  mov     rcx, [rsp+58h+arg_8]; struct INativeConfigurationSystem *
0x180026ed4  mov     edx, 1; int
0x180026ed9  call    ?SetConfigPathMapper@CONFIG_CS_PATH_MAPPER@@SAJPEAVINativeConfigurationSystem@@H@Z; CONFIG_CS_PATH_MAPPER::SetConfigPathMapper(INativeConfigurationSystem *,int)
0x180026ede  mov     edi, eax
0x180026ee0  test    eax, eax
0x180026ee2  js      loc_180026F95
0x180026ee8  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180026eef  mov     rcx, [rsp+58h+arg_8]; struct INativeConfigurationSystem *
0x180026ef4  mov     r8, [rdx+6D0h]; unsigned __int16 *
0x180026efb  mov     rdx, [rdx+698h]; unsigned __int16 *
0x180026f02  call    ?SetConfigFileMappings@CONFIG_CS_PATH_MAPPER@@SAJPEAVINativeConfigurationSystem@@PEBG1@Z; CONFIG_CS_PATH_MAPPER::SetConfigFileMappings(INativeConfigurationSystem *,ushort const *,ushort const *)
0x180026f07  mov     edi, eax
0x180026f09  test    eax, eax
0x180026f0b  js      loc_180026F95
0x180026f11  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x180026f16  lea     r8, ?HostableWebCoreThreadProc@@YAKPEAX@Z; lpStartAddress
0x180026f1d  mov     r9, rbx; lpParameter
0x180026f20  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x180026f24  mov     edx, 8000h; dwStackSize
0x180026f29  xor     ecx, ecx; lpThreadAttributes
0x180026f2b  call    cs:__imp_CreateThread
0x180026f31  mov     [rsi+58h], rax
0x180026f35  test    rax, rax
0x180026f38  jnz     short loc_180026F93
0x180026f3a  mov     rcx, rbx; Block
0x180026f3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026f42  call    cs:__imp_GetLastError
0x180026f48  mov     edi, eax
0x180026f4a  test    eax, eax
0x180026f4c  jle     short loc_180026F57
0x180026f4e  movzx   edi, ax
0x180026f51  or      edi, 80070000h
0x180026f57  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026f5e  jz      short loc_180026F95
0x180026f60  mov     rcx, cs:g_pDebug
0x180026f67  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x180026f6e  mov     [rsp+58h+lpThreadId], rax
0x180026f73  lea     r9, aWorkerProcessS_4; "WORKER_PROCESS::StartInprocHostableWebC"...
0x180026f7a  mov     r8d, 0E4Eh
0x180026f80  mov     [rsp+58h+dwCreationFlags], edi
0x180026f84  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026f8b  call    cs:__imp_PuDbgPrintError
0x180026f91  jmp     short loc_180026F95
0x180026f93  mov     edi, ebp
0x180026f95  mov     rcx, [rsp+58h+arg_8]
0x180026f9a  test    rcx, rcx
0x180026f9d  jz      short loc_180026FAB
0x180026f9f  mov     rax, [rcx]
0x180026fa2  mov     rax, [rax+10h]
0x180026fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fab  mov     eax, edi
0x180026fad  jmp     short loc_180026FF9
0x180026faf  mov     eax, 8007000Eh
0x180026fb4  jmp     short loc_180026FF9
0x180026fb6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026fbd  jz      short loc_180026FF4
0x180026fbf  mov     rcx, cs:g_pDebug
0x180026fc6  lea     rax, aOnlyOneAttempt; "Only one attempt to start hostable webc"...
0x180026fcd  mov     [rsp+58h+lpThreadId], rax
0x180026fd2  lea     r9, aWorkerProcessS_4; "WORKER_PROCESS::StartInprocHostableWebC"...
0x180026fd9  mov     r8d, 0E01h
0x180026fdf  mov     [rsp+58h+dwCreationFlags], 80070057h
0x180026fe7  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026fee  call    cs:__imp_PuDbgPrintError
0x180026ff4  mov     eax, 80070057h
0x180026ff9  add     rsp, 38h
0x180026ffd  pop     rdi
0x180026ffe  pop     rsi
0x180026fff  pop     rbp
0x180027000  pop     rbx
0x180027001  retn
```

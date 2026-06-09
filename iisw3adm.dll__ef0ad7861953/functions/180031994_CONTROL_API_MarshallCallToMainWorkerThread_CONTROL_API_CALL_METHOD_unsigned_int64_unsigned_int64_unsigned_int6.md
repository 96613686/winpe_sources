# CONTROL_API::MarshallCallToMainWorkerThread(CONTROL_API_CALL_METHOD,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180031994`
- end: `0x180031b7a`
- name: `?MarshallCallToMainWorkerThread@CONTROL_API@@AEAAJW4CONTROL_API_CALL_METHOD@@_K11111@Z`
- size: `486`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800312e0`
- `0x180031390`
- `0x180031430`
- `0x180031500`
- `0x1800315f0`
- `0x1800316b0`
- `0x180031780`
- `0x180031810`
- `0x1800318f0`
- `0x180031b80`
- `0x180031d10`
- `0x180031dd0`
- `0x180031e90`
- `0x180031f30`

## callees

- `0x180001234`
- `0x1800073fc`
- `0x180031994`
- `0x1800321f8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031b12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031b12`
- `iisutil!PuDbgPrint` at `0x180031ae6`
- `iisutil!PuDbgPrint` at `0x180031ae6`
- `iisutil!PuDbgPrintError` at `0x180031a9b`
- `iisutil!PuDbgPrintError` at `0x180031b69`
- `iisutil!PuDbgPrintError` at `0x180031a9b`
- `iisutil!PuDbgPrintError` at `0x180031b69`

## string_xrefs

- `0x180031a94`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\control_api.cxx`
- `0x180031adf`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\control_api.cxx`
- `0x180031b62`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\control_api.cxx`
- `0x180031a83`: `CONTROL_API::MarshallCallToMainWorkerThread`
- `0x180031acd`: `CONTROL_API::MarshallCallToMainWorkerThread`
- `0x180031b4d`: `CONTROL_API::MarshallCallToMainWorkerThread`
- `0x180031ac1`: `About to create/queue work item for processing control api call, CONTROL_API_CALL (ptr: %p)\n`

## pseudocode

```c
__int64 __fastcall CONTROL_API::MarshallCallToMainWorkerThread(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  int v13; // edi

  v11 = operator new(0x58u);
  v12 = v11;
  if ( v11 )
  {
    v11[3] = 1;
    *(_QWORD *)v11 = &CONTROL_API_CALL::`vftable';
    *((_QWORD *)v11 + 2) = 0;
    v11[6] = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 0;
    *((_QWORD *)v11 + 7) = 0;
    *((_QWORD *)v11 + 8) = 0;
    *((_QWORD *)v11 + 9) = 0;
    v11[20] = 0;
    v11[2] = 1279345475;
    v13 = CONTROL_API_CALL::Initialize(v11, a2, a3, a4, a5, a6, a7, a8);
    if ( v13 >= 0 )
    {
      if ( (g_dwDebugFlags & 0x110000) != 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\control_api.cxx",
          1251,
          "CONTROL_API::MarshallCallToMainWorkerThread",
          "About to create/queue work item for processing control api call, CONTROL_API_CALL (ptr: %p)\n",
          v12);
      v13 = WORK_QUEUE::GetAndQueueWorkItem(
              (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16),
              (struct WORK_DISPATCH *)v12,
              1u);
      if ( v13 >= 0 )
      {
        WaitForSingleObject(*((HANDLE *)v12 + 2), 0xFFFFFFFF);
        v13 = v12[20];
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\control_api.cxx",
        1235,
        "CONTROL_API::MarshallCallToMainWorkerThread",
        v13,
        "Initializing control api call failed\n");
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 8LL))(v12);
  }
  else
  {
    v13 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\control_api.cxx",
        1212,
        "CONTROL_API::MarshallCallToMainWorkerThread",
        -2147024888,
        "Allocating CONTROL_API_CALL failed\n");
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180031994  push    rbx
0x180031996  push    rbp
0x180031997  push    rsi
0x180031998  push    rdi
0x180031999  sub     rsp, 48h
0x18003199d  mov     ecx, 58h ; 'X'; Size
0x1800319a2  mov     rdi, r9
0x1800319a5  mov     rsi, r8
0x1800319a8  mov     ebp, edx
0x1800319aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800319af  mov     rbx, rax
0x1800319b2  test    rax, rax
0x1800319b5  jz      loc_180031B2C
0x1800319bb  lea     rax, ??_7CONTROL_API_CALL@@6B@; const CONTROL_API_CALL::`vftable'
0x1800319c2  mov     dword ptr [rbx+0Ch], 1
0x1800319c9  mov     [rbx], rax
0x1800319cc  mov     r9, rdi
0x1800319cf  mov     rax, [rsp+68h+arg_38]
0x1800319d7  mov     r8, rsi
0x1800319da  mov     [rsp+68h+var_30], rax
0x1800319df  mov     edx, ebp
0x1800319e1  mov     rax, [rsp+68h+arg_30]
0x1800319e9  mov     rcx, rbx
0x1800319ec  mov     [rsp+68h+var_38], rax
0x1800319f1  mov     rax, [rsp+68h+arg_28]
0x1800319f9  mov     [rsp+68h+var_40], rax
0x1800319fe  mov     rax, [rsp+68h+arg_20]
0x180031a06  mov     [rsp+68h+var_48], rax
0x180031a0b  mov     qword ptr [rbx+10h], 0
0x180031a13  mov     dword ptr [rbx+18h], 0
0x180031a1a  mov     qword ptr [rbx+20h], 0
0x180031a22  mov     qword ptr [rbx+28h], 0
0x180031a2a  mov     qword ptr [rbx+30h], 0
0x180031a32  mov     qword ptr [rbx+38h], 0
0x180031a3a  mov     qword ptr [rbx+40h], 0
0x180031a42  mov     qword ptr [rbx+48h], 0
0x180031a4a  mov     dword ptr [rbx+50h], 0
0x180031a51  mov     dword ptr [rbx+8], 4C414343h
0x180031a58  call    ?Initialize@CONTROL_API_CALL@@QEAAJW4CONTROL_API_CALL_METHOD@@_K11111@Z; CONTROL_API_CALL::Initialize(CONTROL_API_CALL_METHOD,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x180031a5d  mov     edi, eax
0x180031a5f  test    eax, eax
0x180031a61  jns     short loc_180031AA3
0x180031a63  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180031a6a  jz      loc_180031B1B
0x180031a70  mov     rcx, cs:g_pDebug
0x180031a77  lea     rax, aInitializingCo_0; "Initializing control api call failed\n"
0x180031a7e  mov     [rsp+68h+var_40], rax
0x180031a83  lea     r9, aControlApiMars; "CONTROL_API::MarshallCallToMainWorkerTh"...
0x180031a8a  mov     r8d, 4D3h
0x180031a90  mov     dword ptr [rsp+68h+var_48], edi
0x180031a94  lea     rdx, aServercommonIn_35; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180031a9b  call    cs:__imp_PuDbgPrintError
0x180031aa1  jmp     short loc_180031B1B
0x180031aa3  mov     eax, cs:g_dwDebugFlags
0x180031aa9  test    eax, 110000h
0x180031aae  setnz   cl
0x180031ab1  test    al, 3
0x180031ab3  setnz   al
0x180031ab6  test    al, cl
0x180031ab8  jz      short loc_180031AEC
0x180031aba  mov     rcx, cs:g_pDebug
0x180031ac1  lea     rax, aAboutToCreateQ_2; "About to create/queue work item for pro"...
0x180031ac8  mov     [rsp+68h+var_40], rbx
0x180031acd  lea     r9, aControlApiMars; "CONTROL_API::MarshallCallToMainWorkerTh"...
0x180031ad4  mov     r8d, 4E3h
0x180031ada  mov     [rsp+68h+var_48], rax
0x180031adf  lea     rdx, aServercommonIn_35; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180031ae6  call    cs:__imp_PuDbgPrint
0x180031aec  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180031af3  mov     r8d, 1; unsigned __int64
0x180031af9  add     rcx, 10h; this
0x180031afd  mov     rdx, rbx; struct WORK_DISPATCH *
0x180031b00  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x180031b05  mov     edi, eax
0x180031b07  test    eax, eax
0x180031b09  js      short loc_180031B1B
0x180031b0b  mov     rcx, [rbx+10h]; hHandle
0x180031b0f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031b12  call    cs:__imp_WaitForSingleObject
0x180031b18  mov     edi, [rbx+50h]
0x180031b1b  mov     rax, [rbx]
0x180031b1e  mov     rcx, rbx
0x180031b21  mov     rax, [rax+8]
0x180031b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b2a  jmp     short loc_180031B6F
0x180031b2c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180031b33  mov     edi, 80070008h
0x180031b38  jz      short loc_180031B6F
0x180031b3a  mov     rcx, cs:g_pDebug
0x180031b41  lea     rax, aAllocatingCont_1; "Allocating CONTROL_API_CALL failed\n"
0x180031b48  mov     [rsp+68h+var_40], rax
0x180031b4d  lea     r9, aControlApiMars; "CONTROL_API::MarshallCallToMainWorkerTh"...
0x180031b54  mov     r8d, 4BCh
0x180031b5a  mov     dword ptr [rsp+68h+var_48], 80070008h
0x180031b62  lea     rdx, aServercommonIn_35; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180031b69  call    cs:__imp_PuDbgPrintError
0x180031b6f  mov     eax, edi
0x180031b71  add     rsp, 48h
0x180031b75  pop     rdi
0x180031b76  pop     rsi
0x180031b77  pop     rbp
0x180031b78  pop     rbx
0x180031b79  retn
```

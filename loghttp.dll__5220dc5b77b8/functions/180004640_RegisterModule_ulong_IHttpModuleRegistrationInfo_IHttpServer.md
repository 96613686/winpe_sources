# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180004640`
- end: `0x1800047f1`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800025b0`
- `0x1800038f8`
- `0x180004640`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004675`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004675`
- `iisutil!PuCreateDebugPrintsObject` at `0x18000465c`
- `iisutil!PuCreateDebugPrintsObject` at `0x18000465c`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800046a1`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800046a1`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180004731`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180004731`

## string_xrefs

- `0x18000466e`: `Unable to Create Debug Print Object \n`
- `0x18000469a`: `System\CurrentControlSet\Services\W3SVC\Parameters\loghttp`

## pseudocode

```c
signed int __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  __int64 v6; // rax
  signed int result; // eax
  EVENT_LOG *v8; // rbx
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  int v11; // ebx
  _QWORD *v12; // rax
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  DebugPrintsObject = PuCreateDebugPrintsObject("loghttp", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return -2147467259;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return -2147467259;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\loghttp", 0);
  s_pHttpLogModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = *(_QWORD *)a3;
  s_pGlobalInfo = a3;
  v13 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(v6 + 160))(a3, &v13);
  if ( result < 0 )
    return result;
  v8 = (EVENT_LOG *)operator new(4u);
  if ( !v8 )
  {
    g_pEventLog = 0;
    return -2147024888;
  }
  v9 = (**(__int64 (__fastcall ***)(struct IHttpServer *))s_pGlobalInfo)(s_pGlobalInfo);
  v10 = L"HostableWebCore";
  if ( !v9 )
    v10 = L"W3SVC-WP";
  g_pEventLog = EVENT_LOG::EVENT_LOG(v8, v10);
  if ( !g_pEventLog )
    return -2147024888;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v13 + 40LL))(v13, 0, &g_fDoCentralBinaryLogging);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v13 = 0;
  if ( v11 < 0 )
    return v11;
  v12 = operator new(0x10u);
  if ( !v12 )
    return -2147024888;
  *v12 = &CIISModuleFactory::`vftable';
  v12[1] = &CIISHttpModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
             a2,
             v12,
             0x20000000,
             0);
  if ( result >= 0 )
    return HTTP_LOG_HANDLER::Initialize();
  return result;
}

```

## disassembly

```asm
0x180004640  mov     [rsp+arg_0], rbx
0x180004645  push    rdi
0x180004646  sub     rsp, 30h
0x18000464a  mov     rdi, rdx
0x18000464d  lea     rcx, aLoghttp; "loghttp"
0x180004654  mov     edx, 1
0x180004659  mov     rbx, r8
0x18000465c  call    cs:__imp_PuCreateDebugPrintsObject
0x180004662  mov     cs:g_pDebug, rax
0x180004669  test    rax, rax
0x18000466c  jnz     short loc_18000468B
0x18000466e  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180004675  call    cs:__imp_OutputDebugStringA
0x18000467b  mov     rax, cs:g_pDebug
0x180004682  test    rax, rax
0x180004685  jz      loc_1800047E1
0x18000468b  cmp     dword ptr [rax+280h], 0
0x180004692  jz      loc_1800047E1
0x180004698  xor     edx, edx
0x18000469a  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x1800046a1  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800046a7  mov     cs:g_dwDebugFlags, eax
0x1800046ad  mov     rcx, rdi
0x1800046b0  mov     rax, [rdi]
0x1800046b3  mov     rax, [rax+8]
0x1800046b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046bc  mov     cs:?s_pHttpLogModuleContext@@3PEAXEA, rax; void * s_pHttpLogModuleContext
0x1800046c3  lea     rdx, [rsp+38h+arg_18]
0x1800046c8  mov     rax, [rbx]
0x1800046cb  mov     rcx, rbx
0x1800046ce  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x1800046d5  mov     [rsp+38h+arg_18], 0
0x1800046de  mov     rax, [rax+0A0h]
0x1800046e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ea  test    eax, eax
0x1800046ec  js      loc_1800047E6
0x1800046f2  mov     ecx, 4; Size
0x1800046f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046fc  mov     rbx, rax
0x1800046ff  test    rax, rax
0x180004702  jz      loc_1800047CF
0x180004708  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000470f  mov     rdx, [rcx]
0x180004712  mov     rax, [rdx]
0x180004715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000471a  test    eax, eax
0x18000471c  lea     rcx, aW3svcWp; "W3SVC-WP"
0x180004723  lea     rdx, aHostablewebcor; "HostableWebCore"
0x18000472a  cmovz   rdx, rcx
0x18000472e  mov     rcx, rbx
0x180004731  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180004737  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, rax; EVENT_LOG * g_pEventLog
0x18000473e  test    rax, rax
0x180004741  jz      loc_1800047DA
0x180004747  mov     rcx, [rsp+38h+arg_18]
0x18000474c  lea     r8, ?g_fDoCentralBinaryLogging@@3HA; int g_fDoCentralBinaryLogging
0x180004753  xor     edx, edx
0x180004755  mov     rax, [rcx]
0x180004758  mov     rax, [rax+28h]
0x18000475c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004761  mov     rcx, [rsp+38h+arg_18]
0x180004766  mov     ebx, eax
0x180004768  mov     rdx, [rcx]
0x18000476b  mov     rax, [rdx+8]
0x18000476f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004774  mov     [rsp+38h+arg_18], 0
0x18000477d  test    ebx, ebx
0x18000477f  jns     short loc_180004785
0x180004781  mov     eax, ebx
0x180004783  jmp     short loc_1800047E6
0x180004785  mov     ecx, 10h; Size
0x18000478a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000478f  mov     rdx, rax
0x180004792  test    rax, rax
0x180004795  jz      short loc_1800047DA
0x180004797  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x18000479e  xor     r9d, r9d
0x1800047a1  mov     [rdx], rax
0x1800047a4  mov     r8d, 20000000h
0x1800047aa  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800047b1  mov     [rdx+8], rax
0x1800047b5  mov     rcx, [rdi]
0x1800047b8  mov     rax, [rcx+10h]
0x1800047bc  mov     rcx, rdi
0x1800047bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c4  test    eax, eax
0x1800047c6  js      short loc_1800047E6
0x1800047c8  call    ?Initialize@HTTP_LOG_HANDLER@@SAJXZ; HTTP_LOG_HANDLER::Initialize(void)
0x1800047cd  jmp     short loc_1800047E6
0x1800047cf  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x1800047da  mov     eax, 80070008h
0x1800047df  jmp     short loc_1800047E6
0x1800047e1  mov     eax, 80004005h
0x1800047e6  mov     rbx, [rsp+38h+arg_0]
0x1800047eb  add     rsp, 30h
0x1800047ef  pop     rdi
0x1800047f0  retn
```

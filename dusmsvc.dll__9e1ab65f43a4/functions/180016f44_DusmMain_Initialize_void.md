# DusmMain::Initialize(void)

- ea: `0x180016f44`
- end: `0x180017017`
- name: `?Initialize@DusmMain@@SAXXZ`
- size: `211`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800172f0`

## callees

- `0x1800021e4`
- `0x18000809c`
- `0x180013444`
- `0x180016a14`
- `0x180016f44`
- `0x180017020`
- `0x18001707c`
- `0x1800171a8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180016fce`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180016fce`

## string_xrefs

- `0x180016fe8`: `DusmMain::RegisterServiceControlHandler::RegisterServiceCtrlHandlerExW`

## pseudocode

```c
void DusmMain::Initialize(void)
{
  _DWORD *v0; // rcx
  char *v1; // rbx
  SERVICE_STATUS_HANDLE v2; // rax
  __int64 LastErrorIfNull; // rax
  DusmMain *v4; // rcx
  DusmMain *v5; // rcx
  void *retaddr; // [rsp+38h] [rbp+0h]

  v0 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v0 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v0,
      byte_180055E65);
  DusmSvc::Initialize();
  v1 = (char *)operator new(0x38u);
  *(_OWORD *)v1 = 0;
  *((_OWORD *)v1 + 1) = 0;
  *((_OWORD *)v1 + 2) = 0;
  *(_QWORD *)v1 = 0;
  *(_QWORD *)(v1 + 12) = 0;
  *(_QWORD *)(v1 + 20) = 0;
  *(_QWORD *)(v1 + 28) = 0;
  *((_QWORD *)v1 + 5) = 0;
  *((_QWORD *)v1 + 6) = 0;
  *((_DWORD *)v1 + 3) = 1;
  *((_DWORD *)v1 + 4) = 1;
  *((_DWORD *)v1 + 2) = 32;
  DusmMain::s_pInstance = (DusmMain *)v1;
  v2 = RegisterServiceCtrlHandlerExW(L"DusmSvc", DusmMain::ServiceControlHandler, 0);
  LastErrorIfNull = wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
                      retaddr,
                      71,
                      "onecoreuap\\net\\dusm\\svc\\svcmain.cpp",
                      v2,
                      "DusmMain::RegisterServiceControlHandler::RegisterServiceCtrlHandlerExW");
  v4 = DusmMain::s_pInstance;
  *(_QWORD *)v1 = LastErrorIfNull;
  DusmMain::NotifyCurrentState(v4, 4u);
  DusmMain::RegisterStopCallback(v5);
}

```

## disassembly

```asm
0x180016f44  push    rbx
0x180016f46  sub     rsp, 30h
0x180016f4a  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180016f4f  mov     rcx, [rax+8]
0x180016f53  mov     eax, [rcx]
0x180016f55  cmp     eax, 5
0x180016f58  jbe     short loc_180016F66
0x180016f5a  lea     rdx, byte_180055E65
0x180016f61  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180016f66  call    ?Initialize@DusmSvc@@SAXXZ; DusmSvc::Initialize(void)
0x180016f6b  mov     ecx, 38h ; '8'; Size
0x180016f70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016f75  mov     rbx, rax
0x180016f78  mov     [rsp+38h+arg_0], rax
0x180016f7d  xor     eax, eax
0x180016f7f  lea     rdx, ?ServiceControlHandler@DusmMain@@CAKKKPEAX0@Z; lpHandlerProc
0x180016f86  xorps   xmm0, xmm0
0x180016f89  lea     rcx, ServiceName; "DusmSvc"
0x180016f90  xor     r8d, r8d; lpContext
0x180016f93  movups  xmmword ptr [rbx], xmm0
0x180016f96  movups  xmmword ptr [rbx+10h], xmm0
0x180016f9a  movups  xmmword ptr [rbx+20h], xmm0
0x180016f9e  mov     [rbx], rax
0x180016fa1  mov     [rbx+0Ch], rax
0x180016fa5  mov     [rbx+14h], rax
0x180016fa9  mov     [rbx+1Ch], rax
0x180016fad  mov     [rbx+28h], rax
0x180016fb1  mov     [rbx+30h], rax
0x180016fb5  mov     eax, 1
0x180016fba  mov     [rbx+0Ch], eax
0x180016fbd  mov     [rbx+10h], eax
0x180016fc0  mov     dword ptr [rbx+8], 20h ; ' '
0x180016fc7  mov     cs:?s_pInstance@DusmMain@@0PEAV1@EA, rbx; DusmMain * DusmMain::s_pInstance
0x180016fce  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180016fd4  mov     rcx, [rsp+38h]
0x180016fd9  lea     r8, aOnecoreuapNetD_8; "onecoreuap\\net\\dusm\\svc\\svcmain.cpp"
0x180016fe0  mov     r9, rax
0x180016fe3  mov     edx, 47h ; 'G'
0x180016fe8  lea     rax, aDusmmainRegist; "DusmMain::RegisterServiceControlHandler"...
0x180016fef  mov     [rsp+38h+var_18], rax
0x180016ff4  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180016ff9  mov     rcx, cs:?s_pInstance@DusmMain@@0PEAV1@EA; this
0x180017000  mov     edx, 4; unsigned int
0x180017005  mov     [rbx], rax
0x180017008  call    ?NotifyCurrentState@DusmMain@@AEAAXK@Z; DusmMain::NotifyCurrentState(ulong)
0x18001700d  add     rsp, 30h
0x180017011  pop     rbx
0x180017012  jmp     ?RegisterStopCallback@DusmMain@@AEAAXXZ; DusmMain::RegisterStopCallback(void)
```

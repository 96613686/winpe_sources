# CGlobalMit::Run(void)

- ea: `0x18012d860`
- end: `0x18012db82`
- name: `?Run@CGlobalMit@@MEAAKXZ`
- size: `802`
- prototype: `unsigned int __fastcall(CGlobalMit *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180050270`
- `0x1800d3010`
- `0x18012d860`
- `0x18012db88`
- `0x18012ef08`
- `0x180158fc4`
- `0x180228880`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18012d9dc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18012d9dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012d876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012d876`
- `win32u!NtMITDeactivateInputProcessing` at `0x18012da44`
- `win32u!NtMITDeactivateInputProcessing` at `0x18012da44`
- `win32u!NtMITActivateInputProcessing` at `0x18012d97a`
- `win32u!NtMITActivateInputProcessing` at `0x18012d97a`
- `CoreMessaging!CoreUICreateEx` at `0x18012d8c7`
- `CoreMessaging!CoreUICreateEx` at `0x18012d8c7`
- `ext-ms-win-mininput-systeminputhost-l1-2-0!CreateSystemInputHost` at `0x18012d943`
- `ext-ms-win-mininput-systeminputhost-l1-2-0!CreateSystemInputHost` at `0x18012d943`
- `ext-ms-win-ntuser-mit-l1-1-0!MITGetCursorUpdateHandle` at `0x18012d953`
- `ext-ms-win-ntuser-mit-l1-1-0!MITGetCursorUpdateHandle` at `0x18012d953`

## pseudocode

```c
__int64 __fastcall CGlobalMit::Run(CGlobalMit *this)
{
  _QWORD *v2; // rax
  unsigned int v3; // edi
  int v4; // r9d
  int SystemInputHost; // eax
  __int64 updated; // rax
  __int64 v7; // rbx
  void (*i)(void); // rax
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  int v10; // eax
  void *v11; // rcx
  __int64 result; // rax
  unsigned int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  GetCurrentThreadId();
  v2 = operator new(8u);
  if ( v2 )
    *v2 = &CInputProxy::`vftable';
  else
    v2 = 0;
  *((_QWORD *)this + 5) = v2;
  if ( !v2 )
  {
    v3 = -2147024882;
    v13 = 131;
LABEL_6:
    v4 = v3;
LABEL_29:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_18032AAC0, 2u, v4, v13, 0);
    goto LABEL_30;
  }
  SystemInputHost = CoreUICreateEx(1, &CMit::s_pMessageSession);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 137;
    goto LABEL_28;
  }
  SystemInputHost = (*(__int64 (__fastcall **)(struct IMessageSession *, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), CGlobalMit *))(*(_QWORD *)CMit::s_pMessageSession + 272LL))(
                      CMit::s_pMessageSession,
                      *((_QWORD *)this + 3),
                      CGlobalMit::OnResetEvent,
                      this);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 139;
    goto LABEL_28;
  }
  SystemInputHost = (*(__int64 (__fastcall **)(struct IMessageSession *, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), CGlobalMit *))(*(_QWORD *)CMit::s_pMessageSession + 272LL))(
                      CMit::s_pMessageSession,
                      *((_QWORD *)this + 17),
                      CGlobalMit::OnResetEvent,
                      this);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 140;
    goto LABEL_28;
  }
  SystemInputHost = CreateSystemInputHost(*((_QWORD *)this + 5), 0, &CMit::s_pSystemInputHost);
  v3 = SystemInputHost;
  if ( SystemInputHost < 0 )
  {
    v13 = 145;
LABEL_28:
    v4 = SystemInputHost;
    goto LABEL_29;
  }
  updated = MITGetCursorUpdateHandle();
  if ( updated != -1 )
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 144,
      updated);
  if ( !(unsigned int)NtMITActivateInputProcessing(CGlobalMit::s_HitTestRequest, &v15) )
  {
    v3 = -2147467259;
    v13 = 158;
    goto LABEL_6;
  }
  v7 = v15;
  v3 = 0;
  v14 = 0;
  (*(void (__fastcall **)(struct IMessageSession *, __int64 *))(*(_QWORD *)CMit::s_pMessageSession + 40LL))(
    CMit::s_pMessageSession,
    &v14);
  (*(void (__fastcall **)(__int64, __int64, __int64 (__fastcall *)(void *, void *, void *), _QWORD))(*(_QWORD *)v14 + 64LL))(
    v14,
    v7,
    CGlobalMit::CompletionHandler,
    0);
  for ( i = *(void (**)(void))(*(_QWORD *)v14 + 16LL); ; i = *(void (**)(void))(*(_QWORD *)CMit::s_pMessageSession
                                                                              + 232LL) )
  {
    i();
    if ( *((_BYTE *)this + 32) )
      break;
    ResetEvent(*((HANDLE *)this + 3));
    if ( *((_BYTE *)this + 32) )
      break;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
    if ( *(_BYTE *)(*((_QWORD *)this + 1) + 808LL) )
    {
      v10 = CMmcssTask::Apply(v9, 1);
      if ( v10 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0xF4u, 0);
    }
    else
    {
      CMmcssTask::Revert((CMmcssTask *)v9);
    }
  }
  NtMITDeactivateInputProcessing();
LABEL_30:
  if ( CMit::s_pSystemInputHost )
  {
    (*(void (__fastcall **)(struct ISystemInputHost *))(*(_QWORD *)CMit::s_pSystemInputHost + 16LL))(CMit::s_pSystemInputHost);
    CMit::s_pSystemInputHost = 0;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    operator delete(v11, 8u);
    *((_QWORD *)this + 5) = 0;
  }
  if ( CMit::s_pMessageCallSendHost )
  {
    (*(void (__fastcall **)(struct IMessageCallSendHost *))(*(_QWORD *)CMit::s_pMessageCallSendHost + 16LL))(CMit::s_pMessageCallSendHost);
    CMit::s_pMessageCallSendHost = 0;
  }
  if ( CMit::s_pMessageSession )
  {
    (*(void (__fastcall **)(struct IMessageSession *, _QWORD))(*(_QWORD *)CMit::s_pMessageSession + 280LL))(
      CMit::s_pMessageSession,
      *((_QWORD *)this + 17));
    (*(void (__fastcall **)(struct IMessageSession *, _QWORD))(*(_QWORD *)CMit::s_pMessageSession + 280LL))(
      CMit::s_pMessageSession,
      *((_QWORD *)this + 3));
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)CMit::s_pMessageSession + 16LL))(CMit::s_pMessageSession);
    CMit::s_pMessageSession = 0;
  }
  result = (unsigned __int16)v3;
  if ( (v3 & 0x1FFF0000) != 0x70000 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x18012d860  mov     [rsp+arg_10], rbx
0x18012d865  push    rbp
0x18012d866  push    rsi
0x18012d867  push    rdi
0x18012d868  sub     rsp, 30h
0x18012d86c  xor     ebp, ebp
0x18012d86e  mov     rsi, rcx
0x18012d871  mov     [rsp+48h+arg_8], rbp
0x18012d876  call    cs:__imp_GetCurrentThreadId
0x18012d87c  lea     ecx, [rbp+8]; dwBytes
0x18012d87f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012d884  test    rax, rax
0x18012d887  jz      short loc_18012D895
0x18012d889  lea     rcx, ??_7CInputProxy@@6B@; const CInputProxy::`vftable'
0x18012d890  mov     [rax], rcx
0x18012d893  jmp     short loc_18012D898
0x18012d895  mov     rax, rbp
0x18012d898  mov     [rsi+28h], rax
0x18012d89c  test    rax, rax
0x18012d89f  jnz     short loc_18012D8BB
0x18012d8a1  mov     [rsp+48h+var_20], rbp
0x18012d8a6  mov     edi, 8007000Eh
0x18012d8ab  mov     [rsp+48h+var_28], 83h
0x18012d8b3  mov     r9d, edi
0x18012d8b6  jmp     loc_18012DAA0
0x18012d8bb  lea     rdx, ?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012d8c2  mov     ecx, 1
0x18012d8c7  call    cs:__imp_CoreUICreateEx
0x18012d8cd  mov     edi, eax
0x18012d8cf  test    eax, eax
0x18012d8d1  js      loc_18012DA90
0x18012d8d7  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012d8de  lea     r8, ?OnResetEvent@CGlobalMit@@CAJPEAXK0@Z; CGlobalMit::OnResetEvent(void *,ulong,void *)
0x18012d8e5  mov     rdx, [rsi+18h]
0x18012d8e9  mov     r9, rsi
0x18012d8ec  mov     rax, [rcx]
0x18012d8ef  mov     rax, [rax+110h]
0x18012d8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012d8fb  mov     edi, eax
0x18012d8fd  test    eax, eax
0x18012d8ff  js      loc_18012DA81
0x18012d905  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012d90c  lea     r8, ?OnResetEvent@CGlobalMit@@CAJPEAXK0@Z; CGlobalMit::OnResetEvent(void *,ulong,void *)
0x18012d913  mov     rdx, [rsi+88h]
0x18012d91a  mov     r9, rsi
0x18012d91d  mov     rax, [rcx]
0x18012d920  mov     rax, [rax+110h]
0x18012d927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012d92c  mov     edi, eax
0x18012d92e  test    eax, eax
0x18012d930  js      loc_18012DA72
0x18012d936  mov     rcx, [rsi+28h]
0x18012d93a  lea     r8, ?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA; ISystemInputHost * CMit::s_pSystemInputHost
0x18012d941  xor     edx, edx
0x18012d943  call    cs:__imp_CreateSystemInputHost
0x18012d949  mov     edi, eax
0x18012d94b  test    eax, eax
0x18012d94d  js      loc_18012DA63
0x18012d953  call    cs:__imp_MITGetCursorUpdateHandle
0x18012d959  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012d95d  jz      short loc_18012D96E
0x18012d95f  lea     rcx, [rsi+90h]
0x18012d966  mov     rdx, rax
0x18012d969  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18012d96e  lea     rdx, [rsp+48h+arg_8]
0x18012d973  lea     rcx, ?s_HitTestRequest@CGlobalMit@@SAHPEAU_InputHitTestRequest@@PEAU_InputHitTestResult@@@Z; CGlobalMit::s_HitTestRequest(_InputHitTestRequest *,_InputHitTestResult *)
0x18012d97a  call    cs:__imp_NtMITActivateInputProcessing
0x18012d980  test    eax, eax
0x18012d982  jz      loc_18012DA4C
0x18012d988  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012d98f  lea     rdx, [rsp+48h+arg_0]
0x18012d994  mov     rbx, [rsp+48h+arg_8]
0x18012d999  mov     edi, ebp
0x18012d99b  mov     [rsp+48h+arg_0], rbp
0x18012d9a0  mov     rax, [rcx]
0x18012d9a3  mov     rax, [rax+28h]
0x18012d9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012d9ac  mov     rcx, [rsp+48h+arg_0]
0x18012d9b1  lea     r8, ?CompletionHandler@CGlobalMit@@CAJPEAX00@Z; CGlobalMit::CompletionHandler(void *,void *,void *)
0x18012d9b8  xor     r9d, r9d
0x18012d9bb  mov     rdx, rbx
0x18012d9be  mov     rax, [rcx]
0x18012d9c1  mov     rax, [rax+40h]
0x18012d9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012d9ca  mov     rcx, [rsp+48h+arg_0]
0x18012d9cf  mov     rax, [rcx]
0x18012d9d2  mov     rax, [rax+10h]
0x18012d9d6  jmp     short loc_18012DA39
0x18012d9d8  mov     rcx, [rsi+18h]; hEvent
0x18012d9dc  call    cs:__imp_ResetEvent
0x18012d9e2  cmp     [rsi+20h], bpl
0x18012d9e6  jnz     short loc_18012DA44
0x18012d9e8  mov     rax, [rsi+8]
0x18012d9ec  lea     rcx, [rsi+30h]; this
0x18012d9f0  cmp     [rax+328h], bpl
0x18012d9f7  jz      short loc_18012DA23
0x18012d9f9  mov     dl, 1; bool
0x18012d9fb  call    ?Apply@CMmcssTask@@QEAAJ_N@Z; CMmcssTask::Apply(bool)
0x18012da00  test    eax, eax
0x18012da02  jns     short loc_18012DA28
0x18012da04  xor     edx, edx; int *
0x18012da06  mov     [rsp+48h+var_20], rbp; void *
0x18012da0b  mov     r9d, eax; int
0x18012da0e  mov     [rsp+48h+var_28], 0F4h; unsigned int
0x18012da16  xor     r8d, r8d; unsigned int
0x18012da19  lea     ecx, [rdx+14h]; unsigned int
0x18012da1c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18012da21  jmp     short loc_18012DA28
0x18012da23  call    ?Revert@CMmcssTask@@QEAAXXZ; CMmcssTask::Revert(void)
0x18012da28  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012da2f  mov     rax, [rcx]
0x18012da32  mov     rax, [rax+0E8h]
0x18012da39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012da3e  cmp     [rsi+20h], bpl
0x18012da42  jz      short loc_18012D9D8
0x18012da44  call    cs:__imp_NtMITDeactivateInputProcessing
0x18012da4a  jmp     short loc_18012DAB6
0x18012da4c  mov     [rsp+48h+var_20], rbp
0x18012da51  mov     edi, 80004005h
0x18012da56  mov     [rsp+48h+var_28], 9Eh
0x18012da5e  jmp     loc_18012D8B3
0x18012da63  mov     [rsp+48h+var_20], rbp
0x18012da68  mov     [rsp+48h+var_28], 91h
0x18012da70  jmp     short loc_18012DA9D
0x18012da72  mov     [rsp+48h+var_20], rbp
0x18012da77  mov     [rsp+48h+var_28], 8Ch
0x18012da7f  jmp     short loc_18012DA9D
0x18012da81  mov     [rsp+48h+var_20], rbp
0x18012da86  mov     [rsp+48h+var_28], 8Bh
0x18012da8e  jmp     short loc_18012DA9D
0x18012da90  mov     [rsp+48h+var_20], rbp; void *
0x18012da95  mov     [rsp+48h+var_28], 89h; unsigned int
0x18012da9d  mov     r9d, eax; int
0x18012daa0  mov     r8d, 2; unsigned int
0x18012daa6  lea     rdx, dword_18032AAC0; int *
0x18012daad  lea     ecx, [r8+12h]; unsigned int
0x18012dab1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18012dab6  mov     rcx, cs:?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA; ISystemInputHost * CMit::s_pSystemInputHost
0x18012dabd  test    rcx, rcx
0x18012dac0  jz      short loc_18012DAD5
0x18012dac2  mov     rax, [rcx]
0x18012dac5  mov     rax, [rax+10h]
0x18012dac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dace  mov     cs:?s_pSystemInputHost@CMit@@1PEAUISystemInputHost@@EA, rbp; ISystemInputHost * CMit::s_pSystemInputHost
0x18012dad5  mov     rcx, [rsi+28h]; void *
0x18012dad9  test    rcx, rcx
0x18012dadc  jz      short loc_18012DAEC
0x18012dade  mov     edx, 8; unsigned __int64
0x18012dae3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18012dae8  mov     [rsi+28h], rbp
0x18012daec  mov     rcx, cs:?s_pMessageCallSendHost@CMit@@1PEAUIMessageCallSendHost@@EA; IMessageCallSendHost * CMit::s_pMessageCallSendHost
0x18012daf3  test    rcx, rcx
0x18012daf6  jz      short loc_18012DB0B
0x18012daf8  mov     rax, [rcx]
0x18012dafb  mov     rax, [rax+10h]
0x18012daff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db04  mov     cs:?s_pMessageCallSendHost@CMit@@1PEAUIMessageCallSendHost@@EA, rbp; IMessageCallSendHost * CMit::s_pMessageCallSendHost
0x18012db0b  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012db12  test    rcx, rcx
0x18012db15  jz      short loc_18012DB61
0x18012db17  mov     rax, [rcx]
0x18012db1a  mov     rdx, [rsi+88h]
0x18012db21  mov     rax, [rax+118h]
0x18012db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db2d  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012db34  mov     rdx, [rsi+18h]
0x18012db38  mov     rax, [rcx]
0x18012db3b  mov     rax, [rax+118h]
0x18012db42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db47  mov     rcx, cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA; IMessageSession * CMit::s_pMessageSession
0x18012db4e  mov     rax, [rcx]
0x18012db51  mov     rax, [rax+10h]
0x18012db55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db5a  mov     cs:?s_pMessageSession@CMit@@1PEAUIMessageSession@@EA, rbp; IMessageSession * CMit::s_pMessageSession
0x18012db61  mov     rbx, [rsp+48h+arg_10]
0x18012db66  mov     ecx, edi
0x18012db68  and     ecx, 1FFF0000h
0x18012db6e  movzx   eax, di
0x18012db71  cmp     ecx, 70000h
0x18012db77  cmovnz  eax, edi
0x18012db7a  add     rsp, 30h
0x18012db7e  pop     rdi
0x18012db7f  pop     rsi
0x18012db80  pop     rbp
0x18012db81  retn
```

# Mso::Telemetry::EventController::~EventController(void)

- ea: `0x1800104a8`
- end: `0x180010583`
- name: `??1EventController@Telemetry@Mso@@UEAA@XZ`
- size: `219`
- prototype: `void __fastcall(Mso::Telemetry::EventController *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001039c`
- `0x18005c040`
- `0x1800638f0`

## callees

- `0x1800104a8`
- `0x180010fa4`
- `0x180010fe8`
- `0x18001131c`
- `0x1800114c0`
- `0x18003d560`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180010518`
- `KERNEL32!InitOnceComplete` at `0x180010518`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800104f6`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800104f6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180010576`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180010576`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Mso::Telemetry::EventController::~EventController(union _RTL_RUN_ONCE *this)
{
  union _RTL_RUN_ONCE *v2; // rdi
  BOOL fPending; // [rsp+40h] [rbp+8h] BYREF

  this->Ptr = &Mso::Telemetry::EventController::`vftable'{for `Mso::Telemetry::IEventController'};
  this[1].Ptr = &Mso::Telemetry::EventController::`vftable'{for `Mso::Telemetry::ITelemetryInitListener'};
  v2 = this + 82;
  this[82].Ptr = &Mso::Telemetry::TelemetryInitLock::`vftable';
  fPending = 0;
  if ( !__std_init_once_begin_initialize(this + 87, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    Mso::Telemetry::TelemetryInitLock::DecreaseLockCount((Mso::Telemetry::TelemetryInitLock *)v2);
    if ( !InitOnceComplete(v2 + 5, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  std::vector<Mso::Telemetry::Details::CopiedTelemetryEventParams>::~vector<Mso::Telemetry::Details::CopiedTelemetryEventParams>(&this[78]);
  std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(&this[75]);
  std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(&this[68]);
  std::vector<Mso::Functor<void (void)>>::~vector<Mso::Functor<void (void)>>(&this[30]);
  std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(&this[16]);
  std::vector<Mso::Functor<void (void)>>::~vector<Mso::Functor<void (void)>>(&this[3]);
}

```

## disassembly

```asm
0x1800104a8  mov     [rsp+arg_8], rbx
0x1800104ad  mov     [rsp+arg_10], rsi
0x1800104b2  push    rdi
0x1800104b3  sub     rsp, 30h
0x1800104b7  mov     rbx, rcx
0x1800104ba  lea     rax, ??_7EventController@Telemetry@Mso@@6BIEventController@12@@; const Mso::Telemetry::EventController::`vftable'{for `Mso::Telemetry::IEventController'}
0x1800104c1  mov     [rcx], rax
0x1800104c4  lea     rax, ??_7EventController@Telemetry@Mso@@6BITelemetryInitListener@12@@; const Mso::Telemetry::EventController::`vftable'{for `Mso::Telemetry::ITelemetryInitListener'}
0x1800104cb  mov     [rcx+8], rax
0x1800104cf  lea     rdi, [rcx+290h]
0x1800104d6  lea     rax, ??_7TelemetryInitLock@Telemetry@Mso@@6B@; const Mso::Telemetry::TelemetryInitLock::`vftable'
0x1800104dd  mov     [rdi], rax
0x1800104e0  mov     [rsp+38h+fPending], 0
0x1800104e8  xor     r9d, r9d; lpContext
0x1800104eb  lea     r8, [rsp+38h+fPending]; fPending
0x1800104f0  xor     edx, edx; dwFlags
0x1800104f2  lea     rcx, [rdi+28h]; lpInitOnce
0x1800104f6  call    cs:__imp___std_init_once_begin_initialize
0x1800104fc  test    eax, eax
0x1800104fe  jz      short loc_180010576
0x180010500  cmp     [rsp+38h+fPending], 0
0x180010505  jz      short loc_180010522
0x180010507  mov     rcx, rdi; this
0x18001050a  call    ?DecreaseLockCount@TelemetryInitLock@Telemetry@Mso@@IEAAXXZ; Mso::Telemetry::TelemetryInitLock::DecreaseLockCount(void)
0x18001050f  xor     r8d, r8d; lpContext
0x180010512  xor     edx, edx; dwFlags
0x180010514  lea     rcx, [rdi+28h]; lpInitOnce
0x180010518  call    cs:__imp_InitOnceComplete
0x18001051e  test    eax, eax
0x180010520  jz      short loc_18001057D
0x180010522  lea     rcx, [rbx+270h]
0x180010529  call    ??1?$vector@UCopiedTelemetryEventParams@Details@Telemetry@Mso@@V?$allocator@UCopiedTelemetryEventParams@Details@Telemetry@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::Telemetry::Details::CopiedTelemetryEventParams>::~vector<Mso::Telemetry::Details::CopiedTelemetryEventParams>(void)
0x18001052e  lea     rcx, [rbx+258h]
0x180010535  call    ??1?$vector@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@V?$allocator@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(void)
0x18001053a  lea     rcx, [rbx+220h]
0x180010541  call    ??1?$vector@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@V?$allocator@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(void)
0x180010546  lea     rcx, [rbx+0F0h]
0x18001054d  call    ??1?$vector@V?$Functor@$$A6AXXZ@Mso@@V?$allocator@V?$Functor@$$A6AXXZ@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::Functor<void (void)>>::~vector<Mso::Functor<void (void)>>(void)
0x180010552  lea     rcx, [rbx+80h]
0x180010559  call    ??1?$vector@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@V?$allocator@V?$unique_ptr@UIEventSource@Extensibility@Telemetry@Mso@@U?$default_delete@UIEventSource@Extensibility@Telemetry@Mso@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>::~vector<std::unique_ptr<Mso::Telemetry::Extensibility::IEventSource>>(void)
0x18001055e  lea     rcx, [rbx+18h]
0x180010562  mov     rbx, [rsp+38h+arg_8]
0x180010567  mov     rsi, [rsp+38h+arg_10]
0x18001056c  add     rsp, 30h
0x180010570  pop     rdi
0x180010571  jmp     ??1?$vector@V?$Functor@$$A6AXXZ@Mso@@V?$allocator@V?$Functor@$$A6AXXZ@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::Functor<void (void)>>::~vector<Mso::Functor<void (void)>>(void)
0x180010576  call    cs:__imp_abort
0x18001057d  call    __std_init_once_link_alternate_names_and_abort
```

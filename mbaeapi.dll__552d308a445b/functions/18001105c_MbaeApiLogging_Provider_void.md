# MbaeApiLogging::Provider(void)

- ea: `0x18001105c`
- end: `0x180011145`
- name: `?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `223`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010a30`
- `0x1800176a0`
- `0x180017d70`
- `0x180018030`
- `0x180018110`
- `0x180018210`
- `0x180018300`
- `0x180018430`
- `0x180018510`
- `0x1800185f0`
- `0x180018740`
- `0x1800188a0`
- `0x180018990`
- `0x180018a80`
- `0x180018b70`
- `0x180018c60`
- `0x180018d60`
- `0x180018e70`
- `0x180018f60`
- `0x180019050`
- `0x180019140`
- `0x180019230`
- `0x180019320`
- `0x180019410`
- `0x180019500`
- `0x180019640`
- `0x180019730`
- `0x180019820`
- `0x180019910`
- `0x180019a00`
- `0x180019af0`
- `0x180019bf0`
- `0x180019ce0`
- `0x180019dd0`
- `0x180019f60`
- `0x18001a060`
- `0x18001a160`
- `0x18001a260`
- `0x18001a360`
- `0x18001a450`
- `0x18001a580`
- `0x18001a710`
- `0x18001a880`
- `0x18001a970`
- `0x18001aa60`
- `0x18001ab50`
- `0x18001ac40`
- `0x18001ae80`
- `0x18001b080`
- `0x18001b2c0`

## callees

- `0x1800015b4`
- `0x180002890`
- `0x18001105c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011130`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011130`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011084`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011084`

## pseudocode

```c
const struct _tlgProvider_t *MbaeApiLogging::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`MbaeApiLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180088758 = 0;
    v2 = &qword_180088750;
    qword_180088750 = (__int64)&MbaeApiLogging::`vftable';
    byte_180088760 = 0;
    dword_180088764 = 0;
    CallbackContext = &`MbaeApiLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MbaeApiLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    qword_180088758 = (__int64)CallbackContext;
    byte_180088760 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180088764 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180088750 + 8))(&qword_180088750);
    InitOnceComplete(&`MbaeApiLogging::Instance'::`2'::wrapper, 0, &qword_180088750);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18001105c  mov     rax, rsp
0x18001105f  push    rbx
0x180011060  sub     rsp, 20h
0x180011064  lea     r9, [rax+10h]; lpContext
0x180011068  mov     qword ptr [rax+10h], 0
0x180011070  lea     r8, [rax+8]; fPending
0x180011074  mov     dword ptr [rax+8], 0
0x18001107b  xor     edx, edx; dwFlags
0x18001107d  lea     rcx, ?wrapper@?1??Instance@MbaeApiLogging@@KAPEAV2@XZ@4V?$static_lazy@VMbaeApiLogging@@@details@wil@@A; lpInitOnce
0x180011084  call    cs:__imp_InitOnceBeginInitialize
0x18001108a  test    eax, eax
0x18001108c  jz      loc_180011136
0x180011092  cmp     [rsp+28h+arg_0], 0
0x180011097  jz      loc_180011136
0x18001109d  lea     rbx, qword_180088750
0x1800110a4  mov     cs:qword_180088758, 0
0x1800110af  lea     rax, ??_7MbaeApiLogging@@6B@; const MbaeApiLogging::`vftable'
0x1800110b6  mov     [rsp+28h+arg_8], rbx
0x1800110bb  mov     cs:qword_180088750, rax
0x1800110c2  mov     cs:byte_180088760, 0
0x1800110c9  mov     cs:dword_180088764, 0
0x1800110d3  lea     rax, ?__hInner@?1???0StaticHandle@MbaeApiLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MbaeApiLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800110da  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MbaeApiLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x1800110e1  mov     cs:CallbackContext, rax
0x1800110e8  call    atexit
0x1800110ed  mov     rcx, cs:CallbackContext; CallbackContext
0x1800110f4  mov     cs:qword_180088758, rcx
0x1800110fb  mov     cs:byte_180088760, 1
0x180011102  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180011107  mov     rax, cs:qword_180088750
0x18001110e  mov     rcx, rbx
0x180011111  mov     cs:dword_180088764, 1
0x18001111b  mov     rax, [rax+8]
0x18001111f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011124  mov     r8, rbx; lpContext
0x180011127  lea     rcx, ?wrapper@?1??Instance@MbaeApiLogging@@KAPEAV2@XZ@4V?$static_lazy@VMbaeApiLogging@@@details@wil@@A; lpInitOnce
0x18001112e  xor     edx, edx; dwFlags
0x180011130  call    cs:__imp_InitOnceComplete
0x180011136  mov     rax, [rsp+28h+arg_8]
0x18001113b  mov     rax, [rax+8]
0x18001113f  add     rsp, 20h
0x180011143  pop     rbx
0x180011144  retn
```

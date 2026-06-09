# NdfTelemetryProviderSingleton::NdfTelemetryProviderSingleton(_tlgProvider_t const *)

- ea: `0x1800178ac`
- end: `0x18001797a`
- name: `??0NdfTelemetryProviderSingleton@@QEAA@PEBU_tlgProvider_t@@@Z`
- size: `206`
- prototype: `NdfTelemetryProviderSingleton *__fastcall(NdfTelemetryProviderSingleton *__hidden this, const struct _tlgProvider_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001760`

## callees

- `0x1800012dc`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x180017928`
- `KERNEL32!InitializeSRWLock` at `0x180017935`
- `KERNEL32!InitializeSRWLock` at `0x180017942`
- `KERNEL32!InitializeSRWLock` at `0x18001794f`
- `KERNEL32!InitializeSRWLock` at `0x180017928`
- `KERNEL32!InitializeSRWLock` at `0x180017935`
- `KERNEL32!InitializeSRWLock` at `0x180017942`
- `KERNEL32!InitializeSRWLock` at `0x18001794f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017968`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180017968`

## pseudocode

```c
NdfTelemetryProviderSingleton *__fastcall NdfTelemetryProviderSingleton::NdfTelemetryProviderSingleton(
        NdfTelemetryProviderSingleton *this,
        const struct _tlgProvider_t *a2)
{
  qword_180041D40 = 0;
  qword_180041D48 = 7;
  qword_180041D68 = 7;
  LOWORD(qword_180041D30) = 0;
  qword_180041D60 = 0;
  LOWORD(qword_180041D50) = 0;
  xmmword_180041D70 = 0;
  xmmword_180041D80 = 0;
  xmmword_180041D90 = 0;
  dword_180041DA0 = 0;
  word_180041DA4 = 0;
  qword_180041DA8 = 0;
  CallbackContext = &qword_180041048;
  InitializeSRWLock(&g_NdfTelemetryProviderSingleton);
  InitializeSRWLock(&stru_180041D08);
  InitializeSRWLock(&stru_180041D10);
  InitializeSRWLock(&stru_180041D18);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
  CoCreateGuid(&pguid);
  return (NdfTelemetryProviderSingleton *)&g_NdfTelemetryProviderSingleton;
}

```

## disassembly

```asm
0x1800178ac  sub     rsp, 28h
0x1800178b0  xor     edx, edx
0x1800178b2  lea     rax, qword_180041048
0x1800178b9  mov     ecx, 7
0x1800178be  mov     cs:qword_180041D40, rdx
0x1800178c5  xorps   xmm0, xmm0
0x1800178c8  mov     cs:qword_180041D48, rcx
0x1800178cf  mov     cs:qword_180041D68, rcx
0x1800178d6  xorps   xmm1, xmm1
0x1800178d9  lea     rcx, ?g_NdfTelemetryProviderSingleton@@3VNdfTelemetryProviderSingleton@@A; SRWLock
0x1800178e0  mov     word ptr cs:qword_180041D30, dx
0x1800178e7  mov     cs:qword_180041D60, rdx
0x1800178ee  mov     word ptr cs:qword_180041D50, dx
0x1800178f5  movdqa  cs:xmmword_180041D70, xmm0
0x1800178fd  movdqa  cs:xmmword_180041D80, xmm1
0x180017905  movdqa  cs:xmmword_180041D90, xmm0
0x18001790d  mov     cs:dword_180041DA0, edx
0x180017913  mov     cs:word_180041DA4, dx
0x18001791a  mov     cs:qword_180041DA8, rdx
0x180017921  mov     cs:CallbackContext, rax
0x180017928  call    cs:__imp_InitializeSRWLock
0x18001792e  lea     rcx, stru_180041D08; SRWLock
0x180017935  call    cs:__imp_InitializeSRWLock
0x18001793b  lea     rcx, stru_180041D10; SRWLock
0x180017942  call    cs:__imp_InitializeSRWLock
0x180017948  lea     rcx, stru_180041D18; SRWLock
0x18001794f  call    cs:__imp_InitializeSRWLock
0x180017955  mov     rcx, cs:CallbackContext; CallbackContext
0x18001795c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180017961  lea     rcx, pguid; pguid
0x180017968  call    cs:__imp_CoCreateGuid
0x18001796e  lea     rax, ?g_NdfTelemetryProviderSingleton@@3VNdfTelemetryProviderSingleton@@A; NdfTelemetryProviderSingleton g_NdfTelemetryProviderSingleton
0x180017975  add     rsp, 28h
0x180017979  retn
```

# PopUserShutdownScenarioInitialize

- ea: `0x140c73a7c`
- end: `0x140c73ada`
- name: `PopUserShutdownScenarioInitialize`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140c70a9c`

## callees

- `0x140786748`
- `0x140c73958`
- `0x140c73a7c`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c73a8c`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c73a8c`

## pseudocode

```c
__int64 PopUserShutdownScenarioInitialize()
{
  if ( (int)PdcTaskClientRegister(120, &PopUserShutdownTaskClient) < 0 )
    PopUserShutdownTaskClient = 0;
  PopInitializeTimer(
    (unsigned int)&PopUserShutdownCalloutDelayTimer,
    (unsigned int)PopUserShutdownCalloutDelayTimerCallback,
    0,
    (unsigned int)PopUserShutdownCalloutDelayTimerWorker,
    0);
  PopUserShutdownInitializeSleepstudyDiagnostics();
  return 0;
}

```

## disassembly

```asm
0x140c73a7c  sub     rsp, 38h
0x140c73a80  lea     rdx, PopUserShutdownTaskClient
0x140c73a87  mov     ecx, 78h ; 'x'
0x140c73a8c  call    cs:__imp_PdcTaskClientRegister
0x140c73a93  nop     dword ptr [rax+rax+00h]
0x140c73a98  test    eax, eax
0x140c73a9a  jns     short loc_140C73AA7
0x140c73a9c  mov     cs:PopUserShutdownTaskClient, 0
0x140c73aa7  lea     r9, PopUserShutdownCalloutDelayTimerWorker
0x140c73aae  mov     [rsp+38h+var_18], 0
0x140c73ab7  xor     r8d, r8d
0x140c73aba  lea     rdx, PopUserShutdownCalloutDelayTimerCallback
0x140c73ac1  lea     rcx, PopUserShutdownCalloutDelayTimer
0x140c73ac8  call    PopInitializeTimer
0x140c73acd  call    PopUserShutdownInitializeSleepstudyDiagnostics
0x140c73ad2  xor     eax, eax
0x140c73ad4  add     rsp, 38h
0x140c73ad8  retn
```

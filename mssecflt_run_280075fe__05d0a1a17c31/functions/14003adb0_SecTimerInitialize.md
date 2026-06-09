# SecTimerInitialize

- ea: `0x14003adb0`
- end: `0x14003ae48`
- name: `SecTimerInitialize`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a1d4`

## callees

- `0x14003adb0`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x14003ae2b`
- `ntoskrnl!PsCreateSystemThread` at `0x14003ae2b`
- `ntoskrnl!KeInitializeEvent` at `0x14003adec`
- `ntoskrnl!KeInitializeEvent` at `0x14003adec`

## pseudocode

```c
char SecTimerInitialize()
{
  NTSTATUS SystemThread; // eax

  LOBYTE(SystemThread) = SecStatData;
  if ( !SecStatData )
  {
    qword_14001B488 = MEMORY[0xFFFFF78000000320];
    qword_14001B490 = MEMORY[0xFFFFF78000000320];
    KeInitializeEvent(&stru_14001B470, NotificationEvent, 0);
    SystemThread = PsCreateSystemThread(
                     &Handle,
                     0x1FFFFFu,
                     0,
                     0,
                     0,
                     (PKSTART_ROUTINE)SecTimerThreadRoutine,
                     &SecStatData);
    if ( !SystemThread )
      SecStatData = 1;
  }
  return SystemThread;
}

```

## disassembly

```asm
0x14003adb0  sub     rsp, 48h
0x14003adb4  mov     al, cs:SecStatData
0x14003adba  test    al, al
0x14003adbc  jnz     loc_14003AE42
0x14003adc2  mov     rcx, 0FFFFF78000000320h
0x14003adcc  xor     r8d, r8d; State
0x14003adcf  xor     edx, edx; Type
0x14003add1  mov     rax, [rcx]
0x14003add4  mov     cs:qword_14001B488, rax
0x14003addb  mov     rax, [rcx]
0x14003adde  lea     rcx, stru_14001B470; Event
0x14003ade5  mov     cs:qword_14001B490, rax
0x14003adec  call    cs:__imp_KeInitializeEvent
0x14003adf3  nop     dword ptr [rax+rax+00h]
0x14003adf8  lea     rax, SecStatData
0x14003adff  xor     r9d, r9d; ProcessHandle
0x14003ae02  mov     [rsp+48h+StartContext], rax; StartContext
0x14003ae07  lea     rcx, Handle; ThreadHandle
0x14003ae0e  lea     rax, SecTimerThreadRoutine
0x14003ae15  xor     r8d, r8d; ObjectAttributes
0x14003ae18  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x14003ae1d  mov     edx, 1FFFFFh; DesiredAccess
0x14003ae22  mov     [rsp+48h+ClientId], 0; ClientId
0x14003ae2b  call    cs:__imp_PsCreateSystemThread
0x14003ae32  nop     dword ptr [rax+rax+00h]
0x14003ae37  test    eax, eax
0x14003ae39  jnz     short loc_14003AE42
0x14003ae3b  mov     cs:SecStatData, 1
0x14003ae42  add     rsp, 48h
0x14003ae46  retn
```

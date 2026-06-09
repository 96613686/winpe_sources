# GenIdWorkitemRoutine

- ea: `0x1800a2040`
- end: `0x1800a2116`
- name: `GenIdWorkitemRoutine`
- size: `214`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x18002dea0`
- `0x1800564c0`
- `0x180056780`
- `0x1800a2040`
- `0x1800a211c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800a20ff`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800a20ff`

## string_xrefs

- `0x1800a2094`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x1800a20da`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`

## pseudocode

```c
void __fastcall GenIdWorkitemRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  __int64 Status; // rcx
  NTSTATUS v3; // eax
  ENTROPY_SOURCE_HANDLE phEntropySource; // [rsp+40h] [rbp+18h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp+20h] BYREF

  Interval.QuadPart = 0;
  Status = (unsigned int)g_pIrp->IoStatus.Status;
  if ( (int)Status < 0 )
  {
    DebugTraceError(
      Status,
      "g_pIrp->IoStatus.Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\staterewind.c",
      324);
    Interval.QuadPart = -3000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  else
  {
    if ( !g_currentGenIdLength )
      g_currentGenIdLength = 16;
    phEntropySource = 0;
    v3 = EntropyRegisterSource(&phEntropySource, ENTROPY_SOURCE_TYPE_HIGH_PUSH, L"Microsoft Windows VM-GenId");
    if ( v3 >= 0 )
    {
      EntropyProvideData(phEntropySource, &g_currentGenId, 0x10u, 0x1F400u);
      EntropyUnregisterSource(phEntropySource);
    }
    else
    {
      DebugTraceError(
        (unsigned int)v3,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\staterewind.c",
        357);
    }
  }
  SendGenIdIoctl();
}

```

## disassembly

```asm
0x1800a2040  sub     rsp, 28h
0x1800a2044  mov     rax, cs:g_pIrp
0x1800a204b  mov     qword ptr [rsp+28h+Interval], 0
0x1800a2054  mov     ecx, [rax+30h]
0x1800a2057  test    ecx, ecx
0x1800a2059  js      short loc_1800A20D4
0x1800a205b  cmp     cs:g_currentGenIdLength, 0
0x1800a2062  jnz     short loc_1800A206B
0x1800a2064  mov     cs:g_currentGenIdLength, 10h
0x1800a206b  lea     r8, aMicrosoftWindo_1; "Microsoft Windows VM-GenId"
0x1800a2072  mov     [rsp+28h+phEntropySource], 0
0x1800a207b  mov     edx, 1; entropySourceType
0x1800a2080  lea     rcx, [rsp+28h+phEntropySource]; phEntropySource
0x1800a2085  call    EntropyRegisterSource
0x1800a208a  test    eax, eax
0x1800a208c  jns     short loc_1800A20AB
0x1800a208e  mov     r9d, 165h
0x1800a2094  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a209b  lea     rdx, aStatus_0; "status"
0x1800a20a2  mov     ecx, eax
0x1800a20a4  call    DebugTraceError
0x1800a20a9  jmp     short loc_1800A210B
0x1800a20ab  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a20b0  lea     rdx, g_currentGenId; pbData
0x1800a20b7  mov     r9d, 1F400h; entropyEstimateInMilliBits
0x1800a20bd  mov     r8d, 10h; cbData
0x1800a20c3  call    EntropyProvideData
0x1800a20c8  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a20cd  call    EntropyUnregisterSource
0x1800a20d2  jmp     short loc_1800A210B
0x1800a20d4  mov     r9d, 144h
0x1800a20da  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a20e1  lea     rdx, aGPirpIostatusS; "g_pIrp->IoStatus.Status"
0x1800a20e8  call    DebugTraceError
0x1800a20ed  lea     r8, [rsp+28h+Interval]; Interval
0x1800a20f2  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFD23940h
0x1800a20fb  xor     edx, edx; Alertable
0x1800a20fd  xor     ecx, ecx; WaitMode
0x1800a20ff  call    cs:__imp_KeDelayExecutionThread
0x1800a2106  nop     dword ptr [rax+rax+00h]
0x1800a210b  call    SendGenIdIoctl
0x1800a2110  add     rsp, 28h
0x1800a2114  retn
```

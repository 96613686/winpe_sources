# GenIdWorkitemRoutine

- ea: `0x1800a8de0`
- end: `0x1800a8eb6`
- name: `GenIdWorkitemRoutine`
- size: `214`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x180037fd0`
- `0x180060690`
- `0x180060950`
- `0x1800a8de0`
- `0x1800a8ebc`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800a8e9f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800a8e9f`

## string_xrefs

- `0x1800a8e34`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x1800a8e7a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`

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
0x1800a8de0  sub     rsp, 28h
0x1800a8de4  mov     rax, cs:g_pIrp
0x1800a8deb  mov     qword ptr [rsp+28h+Interval], 0
0x1800a8df4  mov     ecx, [rax+30h]
0x1800a8df7  test    ecx, ecx
0x1800a8df9  js      short loc_1800A8E74
0x1800a8dfb  cmp     cs:g_currentGenIdLength, 0
0x1800a8e02  jnz     short loc_1800A8E0B
0x1800a8e04  mov     cs:g_currentGenIdLength, 10h
0x1800a8e0b  lea     r8, aMicrosoftWindo_1; "Microsoft Windows VM-GenId"
0x1800a8e12  mov     [rsp+28h+phEntropySource], 0
0x1800a8e1b  mov     edx, 1; entropySourceType
0x1800a8e20  lea     rcx, [rsp+28h+phEntropySource]; phEntropySource
0x1800a8e25  call    EntropyRegisterSource
0x1800a8e2a  test    eax, eax
0x1800a8e2c  jns     short loc_1800A8E4B
0x1800a8e2e  mov     r9d, 165h
0x1800a8e34  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8e3b  lea     rdx, aStatus_0; "status"
0x1800a8e42  mov     ecx, eax
0x1800a8e44  call    DebugTraceError
0x1800a8e49  jmp     short loc_1800A8EAB
0x1800a8e4b  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a8e50  lea     rdx, g_currentGenId; pbData
0x1800a8e57  mov     r9d, 1F400h; entropyEstimateInMilliBits
0x1800a8e5d  mov     r8d, 10h; cbData
0x1800a8e63  call    EntropyProvideData
0x1800a8e68  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a8e6d  call    EntropyUnregisterSource
0x1800a8e72  jmp     short loc_1800A8EAB
0x1800a8e74  mov     r9d, 144h
0x1800a8e7a  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8e81  lea     rdx, aGPirpIostatusS; "g_pIrp->IoStatus.Status"
0x1800a8e88  call    DebugTraceError
0x1800a8e8d  lea     r8, [rsp+28h+Interval]; Interval
0x1800a8e92  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFD23940h
0x1800a8e9b  xor     edx, edx; Alertable
0x1800a8e9d  xor     ecx, ecx; WaitMode
0x1800a8e9f  call    cs:__imp_KeDelayExecutionThread
0x1800a8ea6  nop     dword ptr [rax+rax+00h]
0x1800a8eab  call    SendGenIdIoctl
0x1800a8eb0  add     rsp, 28h
0x1800a8eb4  retn
```

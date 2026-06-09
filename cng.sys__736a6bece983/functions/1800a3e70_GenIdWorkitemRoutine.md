# GenIdWorkitemRoutine

- ea: `0x1800a3e70`
- end: `0x1800a3f46`
- name: `GenIdWorkitemRoutine`
- size: `214`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x18002e9a0`
- `0x180056db0`
- `0x180057070`
- `0x1800a3e70`
- `0x1800a3f4c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800a3f2f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800a3f2f`

## string_xrefs

- `0x1800a3ec4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x1800a3f0a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`

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
0x1800a3e70  sub     rsp, 28h
0x1800a3e74  mov     rax, cs:g_pIrp
0x1800a3e7b  mov     qword ptr [rsp+28h+Interval], 0
0x1800a3e84  mov     ecx, [rax+30h]
0x1800a3e87  test    ecx, ecx
0x1800a3e89  js      short loc_1800A3F04
0x1800a3e8b  cmp     cs:g_currentGenIdLength, 0
0x1800a3e92  jnz     short loc_1800A3E9B
0x1800a3e94  mov     cs:g_currentGenIdLength, 10h
0x1800a3e9b  lea     r8, aMicrosoftWindo_1; "Microsoft Windows VM-GenId"
0x1800a3ea2  mov     [rsp+28h+phEntropySource], 0
0x1800a3eab  mov     edx, 1; entropySourceType
0x1800a3eb0  lea     rcx, [rsp+28h+phEntropySource]; phEntropySource
0x1800a3eb5  call    EntropyRegisterSource
0x1800a3eba  test    eax, eax
0x1800a3ebc  jns     short loc_1800A3EDB
0x1800a3ebe  mov     r9d, 165h
0x1800a3ec4  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3ecb  lea     rdx, aStatus_0; "status"
0x1800a3ed2  mov     ecx, eax
0x1800a3ed4  call    DebugTraceError
0x1800a3ed9  jmp     short loc_1800A3F3B
0x1800a3edb  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a3ee0  lea     rdx, g_currentGenId; pbData
0x1800a3ee7  mov     r9d, 1F400h; entropyEstimateInMilliBits
0x1800a3eed  mov     r8d, 10h; cbData
0x1800a3ef3  call    EntropyProvideData
0x1800a3ef8  mov     rcx, [rsp+28h+phEntropySource]; hEntropySource
0x1800a3efd  call    EntropyUnregisterSource
0x1800a3f02  jmp     short loc_1800A3F3B
0x1800a3f04  mov     r9d, 144h
0x1800a3f0a  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3f11  lea     rdx, aGPirpIostatusS; "g_pIrp->IoStatus.Status"
0x1800a3f18  call    DebugTraceError
0x1800a3f1d  lea     r8, [rsp+28h+Interval]; Interval
0x1800a3f22  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFD23940h
0x1800a3f2b  xor     edx, edx; Alertable
0x1800a3f2d  xor     ecx, ecx; WaitMode
0x1800a3f2f  call    cs:__imp_KeDelayExecutionThread
0x1800a3f36  nop     dword ptr [rax+rax+00h]
0x1800a3f3b  call    SendGenIdIoctl
0x1800a3f40  add     rsp, 28h
0x1800a3f44  retn
```

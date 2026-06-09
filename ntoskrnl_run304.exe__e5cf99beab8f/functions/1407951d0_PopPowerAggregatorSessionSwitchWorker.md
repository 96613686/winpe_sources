# PopPowerAggregatorSessionSwitchWorker

- ea: `0x1407951d0`
- end: `0x140795291`
- name: `PopPowerAggregatorSessionSwitchWorker`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14025ffd0`
- `0x1402f44c0`
- `0x14044fd64`
- `0x1407951d0`
- `0x140a10fac`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140795231`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14079524c`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140795231`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14079524c`

## pseudocode

```c
__int64 PopPowerAggregatorSessionSwitchWorker()
{
  char v0; // bl
  char v1; // di
  __int64 result; // rax
  __int64 v3; // rdx
  _QWORD v4[3]; // [rsp+20h] [rbp-18h] BYREF

  PopAcquireRwLockExclusive(&PopPowerAggregatorLock);
  if ( byte_140EF76F9 )
  {
    v0 = 0;
    unk_140EF76F8 = 0;
    v1 = 1;
    PopPowerAggregatorScheduleWorker(&PopPowerAggregatorContext);
  }
  else
  {
    v1 = 0;
    byte_140EF76F9 = 1;
    v0 = 1;
  }
  result = PopReleaseRwLock((struct _KTHREAD *)&PopPowerAggregatorLock);
  if ( v1 )
    return PdcTaskClientRequest(PopSleepStudyTaskClientActivator, 0);
  if ( v0 )
  {
    LOBYTE(v3) = 1;
    PdcTaskClientRequest(PopSleepStudyTaskClientActivator, v3);
    v4[0] = 0;
    v4[1] = -1;
    return KeSetTimer2(&unk_140EF7720, -50000000, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x1407951d0  mov     [rsp+arg_0], rbx
0x1407951d5  push    rdi
0x1407951d6  sub     rsp, 30h
0x1407951da  lea     rcx, PopPowerAggregatorLock
0x1407951e1  call    PopAcquireRwLockExclusive
0x1407951e6  cmp     cs:byte_140EF76F9, 0
0x1407951ed  jz      short loc_14079520B
0x1407951ef  xor     bl, bl
0x1407951f1  mov     word ptr cs:unk_140EF76F8, 0
0x1407951fa  lea     rcx, PopPowerAggregatorContext
0x140795201  mov     dil, 1
0x140795204  call    PopPowerAggregatorScheduleWorker
0x140795209  jmp     short loc_140795217
0x14079520b  xor     dil, dil
0x14079520e  mov     cs:byte_140EF76F9, 1
0x140795215  mov     bl, 1
0x140795217  lea     rcx, PopPowerAggregatorLock
0x14079521e  call    PopReleaseRwLock
0x140795223  test    dil, dil
0x140795226  jz      short loc_14079523F
0x140795228  mov     rcx, cs:PopSleepStudyTaskClientActivator
0x14079522f  xor     edx, edx
0x140795231  call    cs:__imp_PdcTaskClientRequest
0x140795238  nop     dword ptr [rax+rax+00h]
0x14079523d  jmp     short loc_140795285
0x14079523f  test    bl, bl
0x140795241  jz      short loc_140795285
0x140795243  mov     rcx, cs:PopSleepStudyTaskClientActivator
0x14079524a  mov     dl, 1
0x14079524c  call    cs:__imp_PdcTaskClientRequest
0x140795253  nop     dword ptr [rax+rax+00h]
0x140795258  lea     r9, [rsp+38h+var_18]
0x14079525d  mov     [rsp+38h+var_18], 0
0x140795266  xor     r8d, r8d
0x140795269  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFFh
0x140795272  mov     rdx, 0FFFFFFFFFD050F80h
0x140795279  lea     rcx, unk_140EF7720
0x140795280  call    KeSetTimer2
0x140795285  mov     rbx, [rsp+38h+arg_0]
0x14079528a  add     rsp, 30h
0x14079528e  pop     rdi
0x14079528f  retn
```

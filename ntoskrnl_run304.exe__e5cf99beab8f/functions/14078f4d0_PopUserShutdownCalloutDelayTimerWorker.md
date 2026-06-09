# PopUserShutdownCalloutDelayTimerWorker

- ea: `0x14078f4d0`
- end: `0x14078f510`
- name: `PopUserShutdownCalloutDelayTimerWorker`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140433300`
- `0x14078f4d0`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f4dd`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f4dd`

## pseudocode

```c
__int64 PopUserShutdownCalloutDelayTimerWorker()
{
  signed __int32 v0; // eax
  bool v1; // cc
  __int64 result; // rax

  do
  {
    PdcTaskClientRequest(PopUserShutdownTaskClient, 0);
    if ( PopUserShutdownPoBlockerHandle )
      SleepstudyHelperBlockerActiveDereference(PopUserShutdownPoBlockerHandle);
    v0 = _InterlockedExchangeAdd(&dword_140EFB328, 0xFFFFFFFF);
    v1 = v0 <= 1;
    result = (unsigned int)(v0 - 1);
  }
  while ( !v1 );
  return result;
}

```

## disassembly

```asm
0x14078f4d0  sub     rsp, 28h
0x14078f4d4  mov     rcx, cs:PopUserShutdownTaskClient
0x14078f4db  xor     edx, edx
0x14078f4dd  call    cs:__imp_PdcTaskClientRequest
0x14078f4e4  nop     dword ptr [rax+rax+00h]
0x14078f4e9  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x14078f4f0  test    rcx, rcx
0x14078f4f3  jz      short loc_14078F4FA
0x14078f4f5  call    SleepstudyHelperBlockerActiveDereference
0x14078f4fa  or      eax, 0FFFFFFFFh
0x14078f4fd  lock xadd cs:dword_140EFB328, eax
0x14078f505  sub     eax, 1
0x14078f508  jg      short loc_14078F4D4
0x14078f50a  add     rsp, 28h
0x14078f50e  retn
```

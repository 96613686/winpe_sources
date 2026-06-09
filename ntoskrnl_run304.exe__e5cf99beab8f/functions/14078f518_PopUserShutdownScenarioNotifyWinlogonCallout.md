# PopUserShutdownScenarioNotifyWinlogonCallout

- ea: `0x14078f518`
- end: `0x14078f59a`
- name: `PopUserShutdownScenarioNotifyWinlogonCallout`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140795d40`

## callees

- `0x1402f44c0`
- `0x140433300`
- `0x1404333a0`
- `0x14078f518`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f52a`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f577`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f52a`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f577`

## pseudocode

```c
void __fastcall PopUserShutdownScenarioNotifyWinlogonCallout(__int64 a1, __int64 a2)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( PopUserShutdownTaskClient )
  {
    LOBYTE(a2) = 1;
    PdcTaskClientRequest(PopUserShutdownTaskClient, a2);
    if ( PopUserShutdownPoBlockerHandle )
      SleepstudyHelperBlockerActiveReference(PopUserShutdownPoBlockerHandle);
    v2 = 0;
    if ( (unsigned __int8)KeSetTimer2(&PopUserShutdownCalloutDelayTimer, -900000000, 0, &v2) )
    {
      PdcTaskClientRequest(PopUserShutdownTaskClient, 0);
      if ( PopUserShutdownPoBlockerHandle )
        SleepstudyHelperBlockerActiveDereference(PopUserShutdownPoBlockerHandle);
    }
  }
}

```

## disassembly

```asm
0x14078f518  sub     rsp, 38h
0x14078f51c  mov     rcx, cs:PopUserShutdownTaskClient
0x14078f523  test    rcx, rcx
0x14078f526  jz      short loc_14078F594
0x14078f528  mov     dl, 1
0x14078f52a  call    cs:__imp_PdcTaskClientRequest
0x14078f531  nop     dword ptr [rax+rax+00h]
0x14078f536  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x14078f53d  test    rcx, rcx
0x14078f540  jz      short loc_14078F547
0x14078f542  call    SleepstudyHelperBlockerActiveReference
0x14078f547  xorps   xmm0, xmm0
0x14078f54a  lea     r9, [rsp+38h+var_18]
0x14078f54f  xor     r8d, r8d
0x14078f552  lea     rcx, PopUserShutdownCalloutDelayTimer
0x14078f559  mov     rdx, 0FFFFFFFFCA5B1700h
0x14078f560  movups  [rsp+38h+var_18], xmm0
0x14078f565  call    KeSetTimer2
0x14078f56a  test    al, al
0x14078f56c  jz      short loc_14078F594
0x14078f56e  mov     rcx, cs:PopUserShutdownTaskClient
0x14078f575  xor     edx, edx
0x14078f577  call    cs:__imp_PdcTaskClientRequest
0x14078f57e  nop     dword ptr [rax+rax+00h]
0x14078f583  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x14078f58a  test    rcx, rcx
0x14078f58d  jz      short loc_14078F594
0x14078f58f  call    SleepstudyHelperBlockerActiveDereference
0x14078f594  add     rsp, 38h
0x14078f598  retn
```

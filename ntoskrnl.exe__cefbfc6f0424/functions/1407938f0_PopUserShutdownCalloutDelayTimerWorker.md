# PopUserShutdownCalloutDelayTimerWorker

- ea: `0x1407938f0`
- end: `0x140793930`
- name: `PopUserShutdownCalloutDelayTimerWorker`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140446890`
- `0x1407938f0`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407938fd`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x1407938fd`

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
    v0 = _InterlockedExchangeAdd(&dword_140EFB068, 0xFFFFFFFF);
    v1 = v0 <= 1;
    result = (unsigned int)(v0 - 1);
  }
  while ( !v1 );
  return result;
}

```

## disassembly

```asm
0x1407938f0  sub     rsp, 28h
0x1407938f4  mov     rcx, cs:PopUserShutdownTaskClient
0x1407938fb  xor     edx, edx
0x1407938fd  call    cs:__imp_PdcTaskClientRequest
0x140793904  nop     dword ptr [rax+rax+00h]
0x140793909  mov     rcx, cs:PopUserShutdownPoBlockerHandle; SpinLock
0x140793910  test    rcx, rcx
0x140793913  jz      short loc_14079391A
0x140793915  call    SleepstudyHelperBlockerActiveDereference
0x14079391a  or      eax, 0FFFFFFFFh
0x14079391d  lock xadd cs:dword_140EFB068, eax
0x140793925  sub     eax, 1
0x140793928  jg      short loc_1407938F4
0x14079392a  add     rsp, 28h
0x14079392e  retn
```

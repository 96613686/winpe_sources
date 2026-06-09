# FwPersistentThreadStartRoutine

- ea: `0x1800205c0`
- end: `0x1800205f3`
- name: `FwPersistentThreadStartRoutine`
- size: `51`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800205c0`
- `0x18002f43c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800205dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800205dc`

## pseudocode

```c
__int64 __fastcall FwPersistentThreadStartRoutine(__int64 (__fastcall **Parameter)(_QWORD))
{
  int v2; // eax
  __int64 (__fastcall *v3)(_QWORD); // rcx

  v2 = Parameter[1](Parameter[2]);
  v3 = *Parameter;
  *((_DWORD *)Parameter + 6) = v2;
  if ( !SetEvent(v3) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x1800205c0  push    rbx
0x1800205c2  sub     rsp, 20h
0x1800205c6  mov     rbx, rcx
0x1800205c9  mov     rcx, [rcx+10h]
0x1800205cd  mov     rax, [rbx+8]
0x1800205d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205d6  mov     rcx, [rbx]; hEvent
0x1800205d9  mov     [rbx+18h], eax
0x1800205dc  call    cs:__imp_SetEvent
0x1800205e2  test    eax, eax
0x1800205e4  jnz     short loc_1800205EB
0x1800205e6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x1800205eb  xor     eax, eax
0x1800205ed  add     rsp, 20h
0x1800205f1  pop     rbx
0x1800205f2  retn
```

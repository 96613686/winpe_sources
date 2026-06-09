# ExecutionContext_SaveThread

- ea: `0x1800098f0`
- end: `0x180009923`
- name: `ExecutionContext_SaveThread`
- size: `51`
- prototype: `__int64 __fastcall(LPGUID ActivityId)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800098f0`
- `0x180009c44`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000990b`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000990b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009905`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009905`

## pseudocode

```c
void __fastcall ExecutionContext_SaveThread(LPGUID ActivityId)
{
  if ( ActivityId )
  {
    EventActivityIdControl(1u, ActivityId);
    *(_DWORD *)ActivityId[1].Data4 = GetThreadLocale();
    *(_QWORD *)&ActivityId[1].Data1 = GetTLSContext();
  }
}

```

## disassembly

```asm
0x1800098f0  test    rcx, rcx
0x1800098f3  jz      short locret_180009922
0x1800098f5  push    rbx
0x1800098f6  sub     rsp, 20h
0x1800098fa  mov     rbx, rcx
0x1800098fd  mov     rdx, rcx; ActivityId
0x180009900  mov     ecx, 1; ControlCode
0x180009905  call    cs:__imp_EventActivityIdControl
0x18000990b  call    cs:__imp_GetThreadLocale
0x180009911  mov     [rbx+18h], eax
0x180009914  call    GetTLSContext
0x180009919  mov     [rbx+10h], rax
0x18000991d  add     rsp, 20h
0x180009921  pop     rbx
0x180009922  retn
```

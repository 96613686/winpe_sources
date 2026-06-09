# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180016d68`
- end: `0x180016dba`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: `unsigned int __fastcall(_MCGEN_TRACE_CONTEXT *Descriptor, const _EVENT_DESCRIPTOR *EventDataCount, const _GUID *EventData, unsigned int Context, _EVENT_DATA_DESCRIPTOR *Descriptor)`
- caller_count: `24`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014f9c`
- `0x180016dc0`
- `0x180016e28`
- `0x180016e90`
- `0x180016f04`
- `0x18001a700`
- `0x18001a80c`
- `0x180020a6c`
- `0x1800231b8`
- `0x180023a70`
- `0x180023ac8`
- `0x180023c74`
- `0x180023d40`
- `0x180028a78`
- `0x180028b00`
- `0x18002d228`
- `0x180031c40`
- `0x180034270`
- `0x180034540`
- `0x180036454`
- `0x1800364b0`
- `0x180038d38`
- `0x180039a14`
- `0x180062d70`

## callees

- `0x180016d68`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180016daf`
- `ntdll!EtwEventWriteTransfer` at `0x180016daf`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(
        _MCGEN_TRACE_CONTEXT *Descriptor,
        const _EVENT_DESCRIPTOR *EventDataCount,
        const _GUID *EventData,
        unsigned int Context,
        _EVENT_DATA_DESCRIPTOR *Descriptor_0)
{
  unsigned __int16 *Logger; // rcx
  unsigned int v6; // r8d

  Logger = (unsigned __int16 *)PROVCORE_EVENTPROVIDER_GUID_Context.Logger;
  if ( PROVCORE_EVENTPROVIDER_GUID_Context.Logger )
  {
    Descriptor_0->Ptr = PROVCORE_EVENTPROVIDER_GUID_Context.Logger;
    v6 = 2;
    LODWORD(Logger) = *Logger;
  }
  else
  {
    Descriptor_0->Ptr = 0;
    v6 = 0;
  }
  Descriptor_0->Size = (unsigned int)Logger;
  Descriptor_0->Reserved = v6;
  return EtwEventWriteTransfer(
           PROVCORE_EVENTPROVIDER_GUID_Context.RegistrationHandle,
           EventDataCount,
           0,
           0,
           Context,
           Descriptor_0);
}

```

## disassembly

```asm
0x180016d68  sub     rsp, 38h
0x180016d6c  mov     rcx, cs:PROVCORE_EVENTPROVIDER_GUID_Context.Logger
0x180016d73  mov     rax, [rsp+38h+Descriptor_0]
0x180016d78  test    rcx, rcx
0x180016d7b  jnz     short loc_180016D85
0x180016d7d  mov     [rax], rcx
0x180016d80  xor     r8d, r8d
0x180016d83  jmp     short loc_180016D91
0x180016d85  mov     [rax], rcx
0x180016d88  mov     r8d, 2
0x180016d8e  movzx   ecx, word ptr [rcx]
0x180016d91  mov     [rax+8], ecx
0x180016d94  mov     [rax+0Ch], r8d
0x180016d98  xor     r8d, r8d
0x180016d9b  mov     rcx, cs:PROVCORE_EVENTPROVIDER_GUID_Context.RegistrationHandle
0x180016da2  mov     [rsp+38h+var_10], rax
0x180016da7  mov     [rsp+38h+var_18], EventDataCount
0x180016dac  xor     EventDataCount, EventDataCount
0x180016daf  call    cs:__imp_EtwEventWriteTransfer
0x180016db5  add     rsp, 38h
0x180016db9  retn
```

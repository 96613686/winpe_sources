# CIISGlobalModule::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x180002fa0`
- end: `0x180002fc2`
- name: `?OnGlobalConfigurationChange@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002238`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalConfigurationChange(__int64 a1, __int64 a2)
{
  const unsigned __int16 *v2; // rax

  v2 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  ETW_TRACE_HANDLER::DeleteTraceUrlList(v2);
  return 0;
}

```

## disassembly

```asm
0x180002fa0  sub     rsp, 28h
0x180002fa4  mov     rax, [rdx]
0x180002fa7  mov     rcx, rdx
0x180002faa  mov     rax, [rax+8]
0x180002fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb3  mov     rcx, rax; unsigned __int16 *
0x180002fb6  call    ?DeleteTraceUrlList@ETW_TRACE_HANDLER@@SAJPEBG@Z; ETW_TRACE_HANDLER::DeleteTraceUrlList(ushort const *)
0x180002fbb  xor     eax, eax
0x180002fbd  add     rsp, 28h
0x180002fc1  retn
```

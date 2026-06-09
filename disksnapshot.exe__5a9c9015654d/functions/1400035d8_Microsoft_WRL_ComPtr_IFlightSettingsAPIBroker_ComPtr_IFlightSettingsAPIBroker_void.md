# Microsoft::WRL::ComPtr<IFlightSettingsAPIBroker>::~ComPtr<IFlightSettingsAPIBroker>(void)

- ea: `0x1400035d8`
- end: `0x140003600`
- name: `??1?$ComPtr@UIFlightSettingsAPIBroker@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c677`

## callees

- `0x1400035d8`
- `0x14000d010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IFlightSettingsAPIBroker>::~ComPtr<IFlightSettingsAPIBroker>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1400035d8  sub     rsp, 28h
0x1400035dc  mov     rax, rcx
0x1400035df  mov     rcx, [rcx]
0x1400035e2  test    rcx, rcx
0x1400035e5  jz      short loc_1400035FB
0x1400035e7  mov     qword ptr [rax], 0
0x1400035ee  mov     rax, [rcx]
0x1400035f1  mov     rax, [rax+10h]
0x1400035f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035fa  nop
0x1400035fb  add     rsp, 28h
0x1400035ff  retn
```

# Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>(void)

- ea: `0x18000d840`
- end: `0x18000d868`
- name: `??1?$ComPtr@UIConfigManager2MutableURI@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f7db`
- `0x18001f7ff`
- `0x18001f999`
- `0x18001f9e1`
- `0x18001fa17`

## callees

- `0x18000d840`
- `0x180020010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>(_QWORD *a1)
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
0x18000d840  sub     rsp, 28h
0x18000d844  mov     rax, rcx
0x18000d847  mov     rcx, [rcx]
0x18000d84a  test    rcx, rcx
0x18000d84d  jz      short loc_18000D863
0x18000d84f  mov     qword ptr [rax], 0
0x18000d856  mov     rax, [rcx]
0x18000d859  mov     rax, [rax+10h]
0x18000d85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d862  nop
0x18000d863  add     rsp, 28h
0x18000d867  retn
```

# Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>(void)

- ea: `0x1800103c0`
- end: `0x1800103e8`
- name: `??1?$ComPtr@UIXmlWriter@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018907`
- `0x180018919`
- `0x18001892b`
- `0x18001893d`
- `0x18001894f`
- `0x180018961`
- `0x1800189bb`
- `0x1800189cd`
- `0x1800189df`

## callees

- `0x1800103c0`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>(_QWORD *a1)
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
0x1800103c0  sub     rsp, 28h
0x1800103c4  mov     rax, rcx
0x1800103c7  mov     rcx, [rcx]
0x1800103ca  test    rcx, rcx
0x1800103cd  jz      short loc_1800103E3
0x1800103cf  mov     qword ptr [rax], 0
0x1800103d6  mov     rax, [rcx]
0x1800103d9  mov     rax, [rax+10h]
0x1800103dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e2  nop
0x1800103e3  add     rsp, 28h
0x1800103e7  retn
```

# Microsoft::WRL::ComPtr<IConfigSession2>::~ComPtr<IConfigSession2>(void)

- ea: `0x180006990`
- end: `0x1800069b8`
- name: `??1?$ComPtr@UIConfigSession2@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d053`

## callees

- `0x180006990`
- `0x18000e010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IConfigSession2>::~ComPtr<IConfigSession2>(_QWORD *a1)
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
0x180006990  sub     rsp, 28h
0x180006994  mov     rax, rcx
0x180006997  mov     rcx, [rcx]
0x18000699a  test    rcx, rcx
0x18000699d  jz      short loc_1800069B3
0x18000699f  mov     qword ptr [rax], 0
0x1800069a6  mov     rax, [rcx]
0x1800069a9  mov     rax, [rax+10h]
0x1800069ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b2  nop
0x1800069b3  add     rsp, 28h
0x1800069b7  retn
```

# Microsoft::WRL::ComPtr<IConfigSession2>::~ComPtr<IConfigSession2>(void)

- ea: `0x180006cb0`
- end: `0x180006cd9`
- name: `??1?$ComPtr@UIConfigSession2@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d719`

## callees

- `0x180006cb0`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006cb0  sub     rsp, 28h
0x180006cb4  mov     rax, rcx
0x180006cb7  mov     rcx, [rcx]
0x180006cba  test    rcx, rcx
0x180006cbd  jz      short loc_180006CD3
0x180006cbf  mov     qword ptr [rax], 0
0x180006cc6  mov     rax, [rcx]
0x180006cc9  mov     rax, [rax+10h]
0x180006ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd2  nop
0x180006cd3  add     rsp, 28h
0x180006cd7  retn
```

# Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(void)

- ea: `0x1800074b0`
- end: `0x1800074d8`
- name: `??1?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac1c`
- `0x180013989`
- `0x18001399b`
- `0x1800139ad`
- `0x1800139bf`
- `0x1800139d1`
- `0x1800139e3`
- `0x1800139f5`
- `0x180013a07`
- `0x180013a19`
- `0x180013a2b`
- `0x180013a3d`
- `0x180013a4f`
- `0x180013a61`
- `0x180013a73`
- `0x180013a85`
- `0x180013ba5`
- `0x180013bb7`
- `0x180013bc9`
- `0x180013c47`
- `0x180013c59`

## callees

- `0x1800074b0`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(_QWORD *a1)
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
0x1800074b0  sub     rsp, 28h
0x1800074b4  mov     rax, rcx
0x1800074b7  mov     rcx, [rcx]
0x1800074ba  test    rcx, rcx
0x1800074bd  jz      short loc_1800074D3
0x1800074bf  mov     qword ptr [rax], 0
0x1800074c6  mov     rax, [rcx]
0x1800074c9  mov     rax, [rax+10h]
0x1800074cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d2  nop
0x1800074d3  add     rsp, 28h
0x1800074d7  retn
```

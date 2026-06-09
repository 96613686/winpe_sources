# Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)

- ea: `0x180002b68`
- end: `0x180002b90`
- name: `??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a427`
- `0x18000a4f3`
- `0x18000a505`
- `0x18000a517`

## callees

- `0x180002b68`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(_QWORD *a1)
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
0x180002b68  sub     rsp, 28h
0x180002b6c  mov     rax, rcx
0x180002b6f  mov     rcx, [rcx]
0x180002b72  test    rcx, rcx
0x180002b75  jz      short loc_180002B8B
0x180002b77  mov     qword ptr [rax], 0
0x180002b7e  mov     rax, [rcx]
0x180002b81  mov     rax, [rax+10h]
0x180002b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8a  nop
0x180002b8b  add     rsp, 28h
0x180002b8f  retn
```

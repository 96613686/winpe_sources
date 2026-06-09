# Microsoft::WRL::ComPtr<IMessageSession>::~ComPtr<IMessageSession>(void)

- ea: `0x140002ad8`
- end: `0x140002b00`
- name: `??1?$ComPtr@UIMessageSession@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005e1e`
- `0x140005e30`

## callees

- `0x140002ad8`
- `0x140006010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IMessageSession>::~ComPtr<IMessageSession>(_QWORD *a1)
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
0x140002ad8  sub     rsp, 28h
0x140002adc  mov     rax, rcx
0x140002adf  mov     rcx, [rcx]
0x140002ae2  test    rcx, rcx
0x140002ae5  jz      short loc_140002AFB
0x140002ae7  mov     qword ptr [rax], 0
0x140002aee  mov     rax, [rcx]
0x140002af1  mov     rax, [rax+10h]
0x140002af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002afa  nop
0x140002afb  add     rsp, 28h
0x140002aff  retn
```

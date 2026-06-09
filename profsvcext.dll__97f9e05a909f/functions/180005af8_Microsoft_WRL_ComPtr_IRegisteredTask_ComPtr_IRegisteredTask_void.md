# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x180005af8`
- end: `0x180005b20`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `12`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e760`
- `0x18001e7a0`
- `0x18001e7e0`
- `0x18001e83a`
- `0x18001efc6`
- `0x18001efea`
- `0x18001f00e`
- `0x18001f020`
- `0x18001f032`
- `0x18001f044`
- `0x18001f068`
- `0x18001f08c`

## callees

- `0x180005af8`
- `0x180020010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(_QWORD *a1)
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
0x180005af8  sub     rsp, 28h
0x180005afc  mov     rax, rcx
0x180005aff  mov     rcx, [rcx]
0x180005b02  test    rcx, rcx
0x180005b05  jz      short loc_180005B1B
0x180005b07  mov     qword ptr [rax], 0
0x180005b0e  mov     rax, [rcx]
0x180005b11  mov     rax, [rax+10h]
0x180005b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1a  nop
0x180005b1b  add     rsp, 28h
0x180005b1f  retn
```

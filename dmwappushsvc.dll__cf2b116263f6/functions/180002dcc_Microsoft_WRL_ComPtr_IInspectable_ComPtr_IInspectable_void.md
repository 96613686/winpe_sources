# Microsoft::WRL::ComPtr<IInspectable>::~ComPtr<IInspectable>(void)

- ea: `0x180002dcc`
- end: `0x180002df4`
- name: `??1?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011a1c`

## callees

- `0x180002dcc`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IInspectable>::~ComPtr<IInspectable>(_QWORD *a1)
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
0x180002dcc  sub     rsp, 28h
0x180002dd0  mov     rax, rcx
0x180002dd3  mov     rcx, [rcx]
0x180002dd6  test    rcx, rcx
0x180002dd9  jz      short loc_180002DEF
0x180002ddb  mov     qword ptr [rax], 0
0x180002de2  mov     rax, [rcx]
0x180002de5  mov     rax, [rax+10h]
0x180002de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dee  nop
0x180002def  add     rsp, 28h
0x180002df3  retn
```

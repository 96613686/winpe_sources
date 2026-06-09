# Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(void)

- ea: `0x1400039cc`
- end: `0x1400039f4`
- name: `??1?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007cc4`
- `0x140007cd6`

## callees

- `0x1400039cc`
- `0x140008010`

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
0x1400039cc  sub     rsp, 28h
0x1400039d0  mov     rax, rcx
0x1400039d3  mov     rcx, [rcx]
0x1400039d6  test    rcx, rcx
0x1400039d9  jz      short loc_1400039EF
0x1400039db  mov     qword ptr [rax], 0
0x1400039e2  mov     rax, [rcx]
0x1400039e5  mov     rax, [rax+10h]
0x1400039e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039ee  nop
0x1400039ef  add     rsp, 28h
0x1400039f3  retn
```

# Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(void)

- ea: `0x18000b3ec`
- end: `0x18000b414`
- name: `??1?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd91`
- `0x18000ddb5`
- `0x18000ddc7`

## callees

- `0x18000b3ec`
- `0x18000e010`

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
0x18000b3ec  sub     rsp, 28h
0x18000b3f0  mov     rax, rcx
0x18000b3f3  mov     rcx, [rcx]
0x18000b3f6  test    rcx, rcx
0x18000b3f9  jz      short loc_18000B40F
0x18000b3fb  mov     qword ptr [rax], 0
0x18000b402  mov     rax, [rcx]
0x18000b405  mov     rax, [rax+10h]
0x18000b409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b40e  nop
0x18000b40f  add     rsp, 28h
0x18000b413  retn
```

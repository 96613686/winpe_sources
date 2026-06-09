# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)

- ea: `0x14000fbbc`
- end: `0x14000fbe4`
- name: `??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e220`
- `0x14001e365`
- `0x14001e377`
- `0x14001e428`
- `0x14001e43a`
- `0x14001e44c`
- `0x14001e45e`
- `0x14001e7f8`

## callees

- `0x14000fbbc`
- `0x14001f010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(
        _QWORD *a1)
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
0x14000fbbc  sub     rsp, 28h
0x14000fbc0  mov     rax, rcx
0x14000fbc3  mov     rcx, [rcx]
0x14000fbc6  test    rcx, rcx
0x14000fbc9  jz      short loc_14000FBDF
0x14000fbcb  mov     qword ptr [rax], 0
0x14000fbd2  mov     rax, [rcx]
0x14000fbd5  mov     rax, [rax+10h]
0x14000fbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbde  nop
0x14000fbdf  add     rsp, 28h
0x14000fbe3  retn
```

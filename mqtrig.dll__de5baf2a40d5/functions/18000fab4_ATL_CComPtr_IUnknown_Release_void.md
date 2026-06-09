# ATL::CComPtr<IUnknown>::Release(void)

- ea: `0x18000fab4`
- end: `0x18000fadb`
- name: `?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d910`
- `0x18000d950`
- `0x18000d990`
- `0x18000d9d4`
- `0x18000da1c`
- `0x18000da64`
- `0x18000dab0`
- `0x18000dafc`

## callees

- `0x18000fab4`
- `0x180022010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtr<IUnknown>::Release(_QWORD *a1)
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
0x18000fab4  sub     rsp, 28h
0x18000fab8  mov     rax, rcx
0x18000fabb  mov     rcx, [rcx]
0x18000fabe  test    rcx, rcx
0x18000fac1  jz      short loc_18000FAD6
0x18000fac3  mov     qword ptr [rax], 0
0x18000faca  mov     rax, [rcx]
0x18000facd  mov     rax, [rax+10h]
0x18000fad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad6  add     rsp, 28h
0x18000fada  retn
```

# _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)

- ea: `0x1400046bc`
- end: `0x1400046da`
- name: `?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400076a8`
- `0x140007e04`
- `0x140007ea8`
- `0x140008f50`
- `0x14000a6dc`
- `0x14000bdc0`
- `0x14000cca0`
- `0x14000d110`
- `0x14000e768`

## callees

- `0x1400046bc`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1400046bc  sub     rsp, 28h
0x1400046c0  mov     rcx, [rcx]
0x1400046c3  test    rcx, rcx
0x1400046c6  jz      short loc_1400046D5
0x1400046c8  mov     rax, [rcx]
0x1400046cb  mov     rax, [rax+8]
0x1400046cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046d4  nop
0x1400046d5  add     rsp, 28h
0x1400046d9  retn
```

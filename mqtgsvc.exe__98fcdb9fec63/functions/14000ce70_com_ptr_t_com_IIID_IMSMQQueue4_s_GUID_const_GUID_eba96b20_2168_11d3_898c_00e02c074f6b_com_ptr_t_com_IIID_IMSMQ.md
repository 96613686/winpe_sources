# _com_ptr_t<_com_IIID<IMSMQQueue4,&__s_GUID const _GUID_eba96b20_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueue4,&__s_GUID const _GUID_eba96b20_2168_11d3_898c_00e02c074f6b>>(void)

- ea: `0x14000ce70`
- end: `0x14000ce8e`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIMSMQQueue4@@$1?_GUID_eba96b20_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e36a`

## callees

- `0x14000ce70`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQQueue4,&__s_GUID const _GUID_eba96b20_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueue4,&__s_GUID const _GUID_eba96b20_2168_11d3_898c_00e02c074f6b>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x14000ce70  sub     rsp, 28h
0x14000ce74  mov     rcx, [rcx]
0x14000ce77  test    rcx, rcx
0x14000ce7a  jz      short loc_14000CE89
0x14000ce7c  mov     rax, [rcx]
0x14000ce7f  mov     rax, [rax+10h]
0x14000ce83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce88  nop
0x14000ce89  add     rsp, 28h
0x14000ce8d  retn
```

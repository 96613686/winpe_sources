# _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::~_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>(void)

- ea: `0x1800055d8`
- end: `0x1800055f6`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001eca7`
- `0x18001ee2c`
- `0x18001ee50`
- `0x18001f112`
- `0x18001f508`
- `0x18001f53e`
- `0x18001f5ce`
- `0x18001f737`

## callees

- `0x1800055d8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::~_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>(
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
0x1800055d8  sub     rsp, 28h
0x1800055dc  mov     rcx, [rcx]
0x1800055df  test    rcx, rcx
0x1800055e2  jz      short loc_1800055F1
0x1800055e4  mov     rax, [rcx]
0x1800055e7  mov     rax, [rax+10h]
0x1800055eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f0  nop
0x1800055f1  add     rsp, 28h
0x1800055f5  retn
```

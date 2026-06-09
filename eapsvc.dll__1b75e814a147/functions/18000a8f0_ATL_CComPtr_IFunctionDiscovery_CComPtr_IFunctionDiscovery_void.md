# ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>(void)

- ea: `0x18000a8f0`
- end: `0x18000a90e`
- name: `??1?$CComPtr@UIFunctionDiscovery@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001533e`
- `0x18001589a`
- `0x180015daf`
- `0x180015e51`
- `0x180015e75`
- `0x180015eab`

## callees

- `0x18000a8f0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>(__int64 *a1)
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
0x18000a8f0  sub     rsp, 28h
0x18000a8f4  mov     rcx, [rcx]
0x18000a8f7  test    rcx, rcx
0x18000a8fa  jz      short loc_18000A909
0x18000a8fc  mov     rax, [rcx]
0x18000a8ff  mov     rax, [rax+10h]
0x18000a903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a908  nop
0x18000a909  add     rsp, 28h
0x18000a90d  retn
```

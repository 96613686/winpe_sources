# _UpdateAdapters_::_1_::dtor$0

- ea: `0x140011a2e`
- end: `0x140011a3a`
- name: `_UpdateAdapters_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000672c`

## pseudocode

```c
void __fastcall UpdateAdapters_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::~DXGIAdapterCacheHealthActivity((DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *)(a2 + 400));
}

```

## disassembly

```asm
0x140011a2e  lea     rcx, [rdx+190h]; this
0x140011a35  jmp     ??1DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@QEAA@XZ; DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::~DXGIAdapterCacheHealthActivity(void)
```

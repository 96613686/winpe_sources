# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180041324`
- end: `0x18004133b`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_2`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041468`
- `0x18005c160`
- `0x18005c3fc`
- `0x18005d474`

## callees

- `0x180041324`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041330`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180041324  sub     rsp, 28h
0x180041328  mov     rcx, [rcx]; pv
0x18004132b  test    rcx, rcx
0x18004132e  jz      short loc_180041336
0x180041330  call    cs:CoTaskMemFree
0x180041336  add     rsp, 28h
0x18004133a  retn
```

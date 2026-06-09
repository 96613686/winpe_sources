# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18017ec0c`
- end: `0x18017ec23`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18017ec9c`
- `0x180185b7c`
- `0x1801860d4`
- `0x180186fbc`

## callees

- `0x18017ec0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017ec18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017ec18`

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
0x18017ec0c  sub     rsp, 28h
0x18017ec10  mov     rcx, [rcx]; pv
0x18017ec13  test    rcx, rcx
0x18017ec16  jz      short loc_18017EC1E
0x18017ec18  call    cs:CoTaskMemFree
0x18017ec1e  add     rsp, 28h
0x18017ec22  retn
```

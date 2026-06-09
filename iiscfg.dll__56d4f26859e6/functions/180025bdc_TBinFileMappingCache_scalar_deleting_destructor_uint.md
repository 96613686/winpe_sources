# TBinFileMappingCache::`scalar deleting destructor'(uint)

- ea: `0x180025bdc`
- end: `0x180025bfc`
- name: `??_GTBinFileMappingCache@@AEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(TBinFileMappingCache *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180026500`
- `0x180028fb0`

## callees

- `0x180025bb4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180025bed`
- `ole32!CoTaskMemFree` at `0x180025bed`

## pseudocode

```c
TBinFileMappingCache *__fastcall TBinFileMappingCache::`scalar deleting destructor'(TBinFileMappingCache *this)
{
  TBinFileMappingCache::~TBinFileMappingCache(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180025bdc  push    rbx
0x180025bde  sub     rsp, 20h
0x180025be2  mov     rbx, rcx
0x180025be5  call    ??1TBinFileMappingCache@@AEAA@XZ; TBinFileMappingCache::~TBinFileMappingCache(void)
0x180025bea  mov     rcx, rbx; pv
0x180025bed  call    cs:__imp_CoTaskMemFree
0x180025bf3  mov     rax, rbx
0x180025bf6  add     rsp, 20h
0x180025bfa  pop     rbx
0x180025bfb  retn
```

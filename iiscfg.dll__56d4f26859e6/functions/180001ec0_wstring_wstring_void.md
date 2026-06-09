# wstring::~wstring(void)

- ea: `0x180001ec0`
- end: `0x180001ed7`
- name: `??1wstring@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wstring *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180001ec0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001ecc`
- `ole32!CoTaskMemFree` at `0x180001ecc`

## pseudocode

```c
void __fastcall wstring::~wstring(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180001ec0  sub     rsp, 28h
0x180001ec4  mov     rcx, [rcx]; pv
0x180001ec7  test    rcx, rcx
0x180001eca  jz      short loc_180001ED2
0x180001ecc  call    cs:__imp_CoTaskMemFree
0x180001ed2  add     rsp, 28h
0x180001ed6  retn
```

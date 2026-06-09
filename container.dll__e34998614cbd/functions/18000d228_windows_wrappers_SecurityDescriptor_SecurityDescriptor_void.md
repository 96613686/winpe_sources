# windows_wrappers::SecurityDescriptor::~SecurityDescriptor(void)

- ea: `0x18000d228`
- end: `0x18000d23f`
- name: `??1SecurityDescriptor@windows_wrappers@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(windows_wrappers::SecurityDescriptor *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032427`
- `0x18003246f`
- `0x180032cfc`
- `0x180032ec1`
- `0x180032fbd`
- `0x1800330a6`
- `0x1800332fa`
- `0x1800335d5`

## callees

- `0x180002ee4`
- `0x18000d228`

## pseudocode

```c
void __fastcall windows_wrappers::SecurityDescriptor::~SecurityDescriptor(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000d228  sub     rsp, 28h
0x18000d22c  mov     rcx, [rcx]; void *
0x18000d22f  test    rcx, rcx
0x18000d232  jz      short loc_18000D239
0x18000d234  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d239  add     rsp, 28h
0x18000d23d  retn
```

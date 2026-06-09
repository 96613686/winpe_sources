# _dynamic_atexit_destructor_for__s_configuration__

- ea: `0x180016970`
- end: `0x18001699a`
- name: `_dynamic_atexit_destructor_for__s_configuration__`
- size: `42`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180016970`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_configuration__()
{
  void *v0; // rcx

  v0 = s_configuration;
  s_configuration = 0;
  if ( v0 )
    operator delete(v0);
}

```

## disassembly

```asm
0x180016970  sub     rsp, 28h
0x180016974  mov     rcx, cs:?s_configuration@@3V?$unique_ptr@UIHgConfiguration@Client@HostGuardian@Microsoft@@U?$default_delete@UIHgConfiguration@Client@HostGuardian@Microsoft@@@wistd@@@wistd@@A; Block
0x18001697b  mov     cs:?s_configuration@@3V?$unique_ptr@UIHgConfiguration@Client@HostGuardian@Microsoft@@U?$default_delete@UIHgConfiguration@Client@HostGuardian@Microsoft@@@wistd@@@wistd@@A, 0; wistd::unique_ptr<Microsoft::HostGuardian::Client::IHgConfiguration,wistd::default_delete<Microsoft::HostGuardian::Client::IHgConfiguration>> s_configuration
0x180016986  test    rcx, rcx
0x180016989  jz      short loc_180016995
0x18001698b  mov     edx, 8
0x180016990  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016995  add     rsp, 28h
0x180016999  retn
```

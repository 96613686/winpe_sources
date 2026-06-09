# std::unique_ptr<uchar,Microsoft::HostGuardian::Client::Utilities::MIDL_user_free_deleter>::~unique_ptr<uchar,Microsoft::HostGuardian::Client::Utilities::MIDL_user_free_deleter>(void)

- ea: `0x18000c3e4`
- end: `0x18000c3fb`
- name: `??1?$unique_ptr@EUMIDL_user_free_deleter@Utilities@Client@HostGuardian@Microsoft@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016218`
- `0x18001622a`
- `0x18001623c`

## callees

- `0x18000c3e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3f0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char,Microsoft::HostGuardian::Client::Utilities::MIDL_user_free_deleter>::~unique_ptr<unsigned char,Microsoft::HostGuardian::Client::Utilities::MIDL_user_free_deleter>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    free(v1);
}

```

## disassembly

```asm
0x18000c3e4  sub     rsp, 28h
0x18000c3e8  mov     rcx, [rcx]; Block
0x18000c3eb  test    rcx, rcx
0x18000c3ee  jz      short loc_18000C3F6
0x18000c3f0  call    cs:__imp_free
0x18000c3f6  add     rsp, 28h
0x18000c3fa  retn
```

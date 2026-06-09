# _dynamic_atexit_destructor_for__RTSecurityContextBase::s_cryptoProviderCS__

- ea: `0x180025660`
- end: `0x180025677`
- name: `_dynamic_atexit_destructor_for__RTSecurityContextBase::s_cryptoProviderCS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002566b`
- `KERNEL32!DeleteCriticalSection` at `0x18002566b`

## pseudocode

```c
void dynamic_atexit_destructor_for__RTSecurityContextBase::s_cryptoProviderCS__()
{
  DeleteCriticalSection(&RTSecurityContextBase::s_cryptoProviderCS);
}

```

## disassembly

```asm
0x180025660  sub     rsp, 28h
0x180025664  lea     rcx, ?s_cryptoProviderCS@RTSecurityContextBase@@0VCCriticalSection@@A; lpCriticalSection
0x18002566b  call    cs:__imp_DeleteCriticalSection
0x180025671  nop
0x180025672  add     rsp, 28h
0x180025676  retn
```

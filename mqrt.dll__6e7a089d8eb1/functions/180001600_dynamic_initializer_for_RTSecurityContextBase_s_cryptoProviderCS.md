# _dynamic_initializer_for__RTSecurityContextBase::s_cryptoProviderCS__

- ea: `0x180001600`
- end: `0x180001620`
- name: `_dynamic_initializer_for__RTSecurityContextBase::s_cryptoProviderCS__`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f70`
- `0x18001305c`

## pseudocode

```c
int dynamic_initializer_for__RTSecurityContextBase::s_cryptoProviderCS__()
{
  CCriticalSection::CCriticalSection((CCriticalSection *)&RTSecurityContextBase::s_cryptoProviderCS);
  return atexit(dynamic_atexit_destructor_for__RTSecurityContextBase::s_cryptoProviderCS__);
}

```

## disassembly

```asm
0x180001600  sub     rsp, 28h
0x180001604  lea     rcx, ?s_cryptoProviderCS@RTSecurityContextBase@@0VCCriticalSection@@A; this
0x18000160b  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x180001610  lea     rcx, _dynamic_atexit_destructor_for__RTSecurityContextBase__s_cryptoProviderCS__
0x180001617  add     rsp, 28h
0x18000161b  jmp     atexit
```

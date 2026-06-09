# XMLScrSite::QueryContinue(void)

- ea: `0x140011830`
- end: `0x140011845`
- name: `?QueryContinue@XMLScrSite@@UEAAJXZ`
- size: `21`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall XMLScrSite::QueryContinue(XMLScrSite *this)
{
  return _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)this + 3) + 40LL), 0, 0) < 0;
}

```

## disassembly

```asm
0x140011830  mov     rdx, [rcx+18h]
0x140011834  xor     ecx, ecx
0x140011836  xor     eax, eax
0x140011838  lock cmpxchg [rdx+28h], ecx
0x14001183d  test    eax, eax
0x14001183f  sets    cl
0x140011842  mov     eax, ecx
0x140011844  retn
```

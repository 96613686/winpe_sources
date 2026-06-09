# CIISWebService::NonDelegatingAddRef(void)

- ea: `0x180006010`
- end: `0x180006018`
- name: `?NonDelegatingAddRef@CIISWebService@@UEAAKXZ`
- size: `8`
- prototype: `unsigned int __fastcall(CIISWebService *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CIISWebService::NonDelegatingAddRef(CIISWebService *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x180006010  lock inc dword ptr [rcx+8]
0x180006014  mov     eax, [rcx+8]
0x180006017  retn
```

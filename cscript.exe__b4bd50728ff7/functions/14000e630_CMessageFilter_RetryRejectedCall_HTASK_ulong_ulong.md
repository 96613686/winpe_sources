# CMessageFilter::RetryRejectedCall(HTASK__ *,ulong,ulong)

- ea: `0x14000e630`
- end: `0x14000e641`
- name: `?RetryRejectedCall@CMessageFilter@@UEAAKPEAUHTASK__@@KK@Z`
- size: `17`
- prototype: `unsigned int __fastcall(CMessageFilter *__hidden this, HTASK, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CMessageFilter::RetryRejectedCall(CMessageFilter *this, HTASK a2, unsigned int a3)
{
  return a3 < 0x2710 ? 500 : -1;
}

```

## disassembly

```asm
0x14000e630  cmp     r8d, 2710h
0x14000e637  sbb     eax, eax
0x14000e639  and     eax, 1F5h
0x14000e63e  dec     eax
0x14000e640  retn
```

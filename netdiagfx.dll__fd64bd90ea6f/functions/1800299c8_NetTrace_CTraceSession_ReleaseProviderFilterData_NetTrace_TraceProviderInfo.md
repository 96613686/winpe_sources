# NetTrace::CTraceSession::ReleaseProviderFilterData(NetTrace::TraceProviderInfo &)

- ea: `0x1800299c8`
- end: `0x1800299e7`
- name: `?ReleaseProviderFilterData@CTraceSession@NetTrace@@AEAAXAEAUTraceProviderInfo@2@@Z`
- size: `31`
- prototype: `void __fastcall(NetTrace::CTraceSession *__hidden this, struct NetTrace::TraceProviderInfo *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028940`
- `0x18002a0bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800299d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800299d5`

## pseudocode

```c
void __fastcall NetTrace::CTraceSession::ReleaseProviderFilterData(NetTrace::CTraceSession *this, LPVOID *a2)
{
  CoTaskMemFree(a2[4]);
  a2[4] = 0;
}

```

## disassembly

```asm
0x1800299c8  push    rbx
0x1800299ca  sub     rsp, 20h
0x1800299ce  mov     rcx, [rdx+20h]; pv
0x1800299d2  mov     rbx, rdx
0x1800299d5  call    cs:__imp_CoTaskMemFree
0x1800299db  xor     eax, eax
0x1800299dd  mov     [rbx+20h], rax
0x1800299e1  add     rsp, 20h
0x1800299e5  pop     rbx
0x1800299e6  retn
```

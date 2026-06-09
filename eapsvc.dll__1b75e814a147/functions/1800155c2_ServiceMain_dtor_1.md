# ServiceMain$dtor$1

- ea: `0x1800155c2`
- end: `0x1800155ce`
- name: `ServiceMain$dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000aa48`

## pseudocode

```c
void __fastcall ServiceMain_dtor_1(__int64 a1, __int64 a2)
{
  EapHost::EapSvcMgr::~EapSvcMgr((EapHost::EapSvcMgr *)(a2 + 80));
}

```

## disassembly

```asm
0x1800155c2  lea     rcx, [rdx+50h]; this
0x1800155c9  jmp     ??1EapSvcMgr@EapHost@@UEAA@XZ; EapHost::EapSvcMgr::~EapSvcMgr(void)
```

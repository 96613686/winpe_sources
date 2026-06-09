# CTVOAgent::~CTVOAgent(void)

- ea: `0x18001dd5c`
- end: `0x18001dd8e`
- name: `??1CTVOAgent@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180016770`
- `0x18001ddb8`

## callees

- `0x1800195f8`
- `0x18001dd94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dd75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dd75`

## pseudocode

```c
void __fastcall CTVOAgent::~CTVOAgent(LPCRITICAL_SECTION lpCriticalSection)
{
  CTVOCache::RemoveAllCacheEntries((CTVOCache *)&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
  CTVOCache::~CTVOCache((CTVOCache *)&lpCriticalSection[1]);
}

```

## disassembly

```asm
0x18001dd5c  mov     [rsp+arg_0], rbx
0x18001dd61  push    rdi
0x18001dd62  sub     rsp, 20h
0x18001dd66  mov     rbx, rcx
0x18001dd69  add     rcx, 28h ; '('; this
0x18001dd6d  call    ?RemoveAllCacheEntries@CTVOCache@@QEAAXXZ; CTVOCache::RemoveAllCacheEntries(void)
0x18001dd72  mov     rcx, rbx; lpCriticalSection
0x18001dd75  call    cs:__imp_DeleteCriticalSection
0x18001dd7b  lea     rcx, [rbx+28h]; this
0x18001dd7f  mov     rbx, [rsp+28h+arg_0]
0x18001dd84  add     rsp, 20h
0x18001dd88  pop     rdi
0x18001dd89  jmp     ??1CTVOCache@@QEAA@XZ; CTVOCache::~CTVOCache(void)
```

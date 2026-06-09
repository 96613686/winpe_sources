# CConnectivityWatcher::~CConnectivityWatcher(void)

- ea: `0x1800066f8`
- end: `0x180006716`
- name: `??1CConnectivityWatcher@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(CConnectivityWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000637c`

## callees

- `0x1800105e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000670f`

## pseudocode

```c
void __fastcall CConnectivityWatcher::~CConnectivityWatcher(CConnectivityWatcher *this)
{
  CConnectivityWatcher::UnregisterForConnectivityNotification(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800066f8  push    rbx
0x1800066fa  sub     rsp, 20h
0x1800066fe  mov     rbx, rcx
0x180006701  call    ?UnregisterForConnectivityNotification@CConnectivityWatcher@@QEAAJXZ; CConnectivityWatcher::UnregisterForConnectivityNotification(void)
0x180006706  lea     rcx, [rbx+10h]
0x18000670a  add     rsp, 20h
0x18000670e  pop     rbx
0x18000670f  jmp     cs:__imp_DeleteCriticalSection
```

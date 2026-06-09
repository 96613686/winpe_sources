# PushRouter::~PushRouter(void)

- ea: `0x180013c24`
- end: `0x180013c56`
- name: `??1PushRouter@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(PushRouter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e990`
- `0x180010930`
- `0x180013f64`

## callees

- `0x180013a7c`
- `0x180013b84`
- `0x180014040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c39`

## pseudocode

```c
void __fastcall PushRouter::~PushRouter(PushRouter *this)
{
  PushRouter::Deinitialize(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  PersistList::~PersistList((struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
  CTList<PushClient>::~CTList<PushClient>((__int64)this + 24);
}

```

## disassembly

```asm
0x180013c24  push    rbx
0x180013c26  sub     rsp, 20h
0x180013c2a  mov     rbx, rcx
0x180013c2d  call    ?Deinitialize@PushRouter@@AEAAJXZ; PushRouter::Deinitialize(void)
0x180013c32  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180013c39  call    cs:__imp_DeleteCriticalSection
0x180013c3f  lea     rcx, [rbx+60h]; this
0x180013c43  call    ??1PersistList@@UEAA@XZ; PersistList::~PersistList(void)
0x180013c48  lea     rcx, [rbx+18h]
0x180013c4c  add     rsp, 20h
0x180013c50  pop     rbx
0x180013c51  jmp     ??1?$CTList@VPushClient@@@@UEAA@XZ; CTList<PushClient>::~CTList<PushClient>(void)
```

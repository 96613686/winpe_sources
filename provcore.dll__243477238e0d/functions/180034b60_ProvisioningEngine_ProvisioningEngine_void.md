# ProvisioningEngine::~ProvisioningEngine(void)

- ea: `0x180034b60`
- end: `0x180034b8a`
- name: `??1ProvisioningEngine@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(ProvisioningEngine *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034a1c`
- `0x180034a60`

## callees

- `0x180017af8`
- `0x180034ae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b6d`

## pseudocode

```c
void __fastcall ProvisioningEngine::~ProvisioningEngine(ProvisioningEngine *this)
{
  DeleteCriticalSection(&this->m_msgTimeWindowLock.m_cs);
  std::unique_ptr<std::deque<unsigned __int64>>::~unique_ptr<std::deque<unsigned __int64>>(&this->m_msgTimeWindow);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(&this->m_critsec);
}

```

## disassembly

```asm
0x180034b60  push    rbx
0x180034b62  sub     rsp, 20h
0x180034b66  mov     rbx, this
0x180034b69  add     this, 50h ; 'P'; lpCriticalSection
0x180034b6d  call    cs:__imp_DeleteCriticalSection
0x180034b73  lea     this, [rbx+48h]; this
0x180034b77  call    ??1?$unique_ptr@V?$deque@_KV?$allocator@_K@std@@@std@@U?$default_delete@V?$deque@_KV?$allocator@_K@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::deque<unsigned __int64>>::~unique_ptr<std::deque<unsigned __int64>>(void)
0x180034b7c  lea     this, [rbx+18h]
0x180034b80  add     rsp, 20h
0x180034b84  pop     rbx
0x180034b85  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```

# CalibrationTask::~CalibrationTask(void)

- ea: `0x180020e74`
- end: `0x180020ea4`
- name: `??1CalibrationTask@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b478`

## callees

- `0x180020e74`
- `0x180020eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020e86`

## pseudocode

```c
void __fastcall CalibrationTask::~CalibrationTask(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  DeleteCriticalSection(this + 2);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)&this->OwningThread);
}

```

## disassembly

```asm
0x180020e74  push    rbx
0x180020e76  sub     rsp, 20h
0x180020e7a  mov     rbx, rcx
0x180020e7d  mov     rcx, [rcx+40h]; hObject
0x180020e81  test    rcx, rcx
0x180020e84  jz      short loc_180020E8C
0x180020e86  call    cs:__imp_CloseHandle
0x180020e8c  lea     rcx, [rbx+50h]; lpCriticalSection
0x180020e90  call    cs:__imp_DeleteCriticalSection
0x180020e96  lea     rcx, [rbx+10h]; this
0x180020e9a  add     rsp, 20h
0x180020e9e  pop     rbx
0x180020e9f  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```

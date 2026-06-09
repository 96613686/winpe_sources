# CCancelRpc::~CCancelRpc(void)

- ea: `0x180015730`
- end: `0x180015777`
- name: `??1CCancelRpc@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030bf0`

## callees

- `0x18000417c`
- `0x1800041cc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001576a`
- `KERNEL32!DeleteCriticalSection` at `0x18001576a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCancelRpc::~CCancelRpc(LPCRITICAL_SECTION lpCriticalSection)
{
  CHandle::~CHandle((CHandle *)&lpCriticalSection[2].SpinCount);
  CHandle::~CHandle((CHandle *)&lpCriticalSection[2].LockSemaphore);
  CHandle::~CHandle((CHandle *)&lpCriticalSection[2].OwningThread);
  CHandle::~CHandle((CHandle *)&lpCriticalSection[2].LockCount);
  CMap<void *,void *,__int64,__int64>::~CMap<void *,void *,__int64,__int64>(&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180015730  push    rbx
0x180015732  sub     rsp, 20h
0x180015736  mov     rbx, rcx
0x180015739  add     rcx, 70h ; 'p'; this
0x18001573d  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180015742  lea     rcx, [rbx+68h]; this
0x180015746  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001574b  lea     rcx, [rbx+60h]; this
0x18001574f  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180015754  lea     rcx, [rbx+58h]; this
0x180015758  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001575d  lea     rcx, [rbx+28h]
0x180015761  call    ??1?$CMap@PEAXPEAX_J_J@@UEAA@XZ; CMap<void *,void *,__int64,__int64>::~CMap<void *,void *,__int64,__int64>(void)
0x180015766  nop
0x180015767  mov     rcx, rbx; lpCriticalSection
0x18001576a  call    cs:__imp_DeleteCriticalSection
0x180015770  nop
0x180015771  add     rsp, 20h
0x180015775  pop     rbx
0x180015776  retn
```

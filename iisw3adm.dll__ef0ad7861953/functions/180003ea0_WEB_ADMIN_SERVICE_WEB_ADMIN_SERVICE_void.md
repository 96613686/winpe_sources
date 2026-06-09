# WEB_ADMIN_SERVICE::~WEB_ADMIN_SERVICE(void)

- ea: `0x180003ea0`
- end: `0x180003fde`
- name: `??1WEB_ADMIN_SERVICE@@UEAA@XZ`
- size: `318`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180004050`

## callees

- `0x180001274`
- `0x180003ea0`
- `0x1800070b0`
- `0x18000a158`
- `0x18000e784`
- `0x18002cfa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ef5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ef5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f53`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f53`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003f81`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003f81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f0c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f19`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f8e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f0c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f19`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003f8e`
- `iisutil!??1CSecurityDispenser@@QEAA@XZ` at `0x180003f41`
- `iisutil!??1CSecurityDispenser@@QEAA@XZ` at `0x180003f41`

## pseudocode

```c
void __fastcall WEB_ADMIN_SERVICE::~WEB_ADMIN_SERVICE(struct _RTL_CRITICAL_SECTION *this)
{
  APP_POOL_ISOLATION *SpinCount; // rdi
  HMODULE LockSemaphore; // rcx

  SpinCount = (APP_POOL_ISOLATION *)this[45].SpinCount;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WEB_ADMIN_SERVICE::`vftable';
  if ( SpinCount )
  {
    APP_POOL_ISOLATION::~APP_POOL_ISOLATION(SpinCount);
    operator delete(SpinCount);
    this[45].SpinCount = 0;
  }
  this->LockCount = 1483956599;
  if ( HIDWORD(this[26].SpinCount) )
  {
    DeleteCriticalSection(this + 27);
    HIDWORD(this[26].SpinCount) = 0;
  }
  STRU::~STRU((STRU *)&this[44].LockCount);
  STRU::~STRU((STRU *)&this[42].SpinCount);
  STRU::~STRU((STRU *)&this[41].OwningThread);
  this[39].OwningThread = &WMS_ERROR_LOGGER::`vftable';
  CSecurityDispenser::~CSecurityDispenser((CSecurityDispenser *)&this[35].OwningThread);
  LockSemaphore = (HMODULE)this[34].LockSemaphore;
  if ( LockSemaphore )
  {
    FreeLibrary(LockSemaphore);
    this[34].LockSemaphore = 0;
    *(_QWORD *)&this[34].LockCount = 0;
    this[34].OwningThread = 0;
  }
  CLKRHashTable::~CLKRHashTable((CLKRHashTable *)&this[31]);
  STRU::~STRU((STRU *)&this[29].LockSemaphore);
  LODWORD(this[26].SpinCount) = 1668246648;
  *(_QWORD *)&this[17].LockCount = &CONFIG_AND_CONTROL_MANAGER::`vftable';
  LODWORD(this[17].OwningThread) = 1483563875;
  CONFIG_MANAGER::~CONFIG_MANAGER((CONFIG_MANAGER *)&this[17].LockSemaphore);
  UL_AND_WORKER_MANAGER::~UL_AND_WORKER_MANAGER((UL_AND_WORKER_MANAGER *)&this[2].SpinCount);
  WORK_QUEUE::~WORK_QUEUE((WORK_QUEUE *)&this->OwningThread);
}

```

## disassembly

```asm
0x180003ea0  mov     [rsp+arg_0], rbx
0x180003ea5  push    rdi
0x180003ea6  sub     rsp, 20h
0x180003eaa  mov     rdi, [rcx+728h]
0x180003eb1  lea     rax, ??_7WEB_ADMIN_SERVICE@@6B@; const WEB_ADMIN_SERVICE::`vftable'
0x180003eb8  mov     [rcx], rax
0x180003ebb  mov     rbx, rcx
0x180003ebe  test    rdi, rdi
0x180003ec1  jz      short loc_180003EDE
0x180003ec3  mov     rcx, rdi; this
0x180003ec6  call    ??1APP_POOL_ISOLATION@@QEAA@XZ; APP_POOL_ISOLATION::~APP_POOL_ISOLATION(void)
0x180003ecb  mov     rcx, rdi; Block
0x180003ece  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ed3  mov     qword ptr [rbx+728h], 0
0x180003ede  mov     dword ptr [rbx+8], 58736177h
0x180003ee5  cmp     dword ptr [rbx+434h], 0
0x180003eec  jz      short loc_180003F05
0x180003eee  lea     rcx, [rbx+438h]; lpCriticalSection
0x180003ef5  call    cs:__imp_DeleteCriticalSection
0x180003efb  mov     dword ptr [rbx+434h], 0
0x180003f05  lea     rcx, [rbx+6E8h]
0x180003f0c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003f12  lea     rcx, [rbx+6B0h]
0x180003f19  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003f1f  lea     rcx, [rbx+678h]
0x180003f26  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003f2c  lea     rax, ??_7WMS_ERROR_LOGGER@@6B@; const WMS_ERROR_LOGGER::`vftable'
0x180003f33  lea     rcx, [rbx+588h]
0x180003f3a  mov     [rbx+628h], rax
0x180003f41  call    cs:__imp_??1CSecurityDispenser@@QEAA@XZ; CSecurityDispenser::~CSecurityDispenser(void)
0x180003f47  mov     rcx, [rbx+568h]; hLibModule
0x180003f4e  test    rcx, rcx
0x180003f51  jz      short loc_180003F7A
0x180003f53  call    cs:__imp_FreeLibrary
0x180003f59  mov     qword ptr [rbx+568h], 0
0x180003f64  mov     qword ptr [rbx+558h], 0
0x180003f6f  mov     qword ptr [rbx+560h], 0
0x180003f7a  lea     rcx, [rbx+4D8h]
0x180003f81  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180003f87  lea     rcx, [rbx+4A0h]
0x180003f8e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003f94  lea     rax, ??_7CONFIG_AND_CONTROL_MANAGER@@6B@; const CONFIG_AND_CONTROL_MANAGER::`vftable'
0x180003f9b  mov     dword ptr [rbx+430h], 636F6C78h
0x180003fa5  lea     rcx, [rbx+2C0h]; this
0x180003fac  mov     [rbx+2B0h], rax
0x180003fb3  mov     dword ptr [rbx+2B8h], 586D6363h
0x180003fbd  call    ??1CONFIG_MANAGER@@UEAA@XZ; CONFIG_MANAGER::~CONFIG_MANAGER(void)
0x180003fc2  lea     rcx, [rbx+70h]; this
0x180003fc6  call    ??1UL_AND_WORKER_MANAGER@@UEAA@XZ; UL_AND_WORKER_MANAGER::~UL_AND_WORKER_MANAGER(void)
0x180003fcb  lea     rcx, [rbx+10h]; this
0x180003fcf  mov     rbx, [rsp+28h+arg_0]
0x180003fd4  add     rsp, 20h
0x180003fd8  pop     rdi
0x180003fd9  jmp     ??1WORK_QUEUE@@UEAA@XZ; WORK_QUEUE::~WORK_QUEUE(void)
```

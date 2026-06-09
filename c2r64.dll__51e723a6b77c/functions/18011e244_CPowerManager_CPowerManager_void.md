# CPowerManager::~CPowerManager(void)

- ea: `0x18011e244`
- end: `0x18011e367`
- name: `??1CPowerManager@@UEAA@XZ`
- size: `291`
- prototype: `void __fastcall(CPowerManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18011e450`

## callees

- `0x1800264b4`
- `0x18011e130`
- `0x18011e190`
- `0x18011e244`
- `0x18011e68c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18011e29c`
- `KERNEL32!DeleteCriticalSection` at `0x18011e2b7`
- `KERNEL32!DeleteCriticalSection` at `0x18011e352`
- `KERNEL32!DeleteCriticalSection` at `0x18011e29c`
- `KERNEL32!DeleteCriticalSection` at `0x18011e2b7`
- `KERNEL32!DeleteCriticalSection` at `0x18011e352`
- `KERNEL32!CloseHandle` at `0x18011e2ed`
- `KERNEL32!CloseHandle` at `0x18011e30b`
- `KERNEL32!CloseHandle` at `0x18011e329`
- `KERNEL32!CloseHandle` at `0x18011e347`
- `KERNEL32!CloseHandle` at `0x18011e2ed`
- `KERNEL32!CloseHandle` at `0x18011e30b`
- `KERNEL32!CloseHandle` at `0x18011e329`
- `KERNEL32!CloseHandle` at `0x18011e347`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPowerManager::~CPowerManager(CPowerManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CPowerManager::`vftable'{for `ITpPowerManagerInternal'};
  *((_QWORD *)this + 1) = &CPowerManager::`vftable'{for `ITpPowerManagerDebug'};
  if ( *((_QWORD *)this + 21) )
    MsoShipAssertTagProc(4014411);
  if ( !*((_BYTE *)this + 403) )
    MsoShipAssertTagProc(4014412);
  std::vector<CPowerManager::DiscardableCacheRegistrationRecord>::~vector<CPowerManager::DiscardableCacheRegistrationRecord>((char *)this + 672);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  std::vector<CPowerManager::InputInfoRegistrationRecord>::~vector<CPowerManager::InputInfoRegistrationRecord>((char *)this + 600);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
  Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear((char *)this + 528);
  Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear((char *)this + 520);
  v2 = (void *)*((_QWORD *)this + 63);
  if ( v2 )
  {
    *((_QWORD *)this + 63) = 0;
    CloseHandle(v2);
  }
  v3 = (void *)*((_QWORD *)this + 62);
  if ( v3 )
  {
    *((_QWORD *)this + 62) = 0;
    CloseHandle(v3);
  }
  v4 = (void *)*((_QWORD *)this + 23);
  if ( v4 )
  {
    *((_QWORD *)this + 23) = 0;
    CloseHandle(v4);
  }
  v5 = (void *)*((_QWORD *)this + 22);
  if ( v5 )
  {
    *((_QWORD *)this + 22) = 0;
    CloseHandle(v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  std::vector<CPowerManager::InputInfoRegistrationRecord>::~vector<CPowerManager::InputInfoRegistrationRecord>((char *)this + 24);
}

```

## disassembly

```asm
0x18011e244  push    rbx
0x18011e246  sub     rsp, 20h
0x18011e24a  mov     rbx, rcx
0x18011e24d  lea     rax, ??_7CPowerManager@@6BITpPowerManagerInternal@@@; const CPowerManager::`vftable'{for `ITpPowerManagerInternal'}
0x18011e254  mov     [rcx], rax
0x18011e257  lea     rax, ??_7CPowerManager@@6BITpPowerManagerDebug@@@; const CPowerManager::`vftable'{for `ITpPowerManagerDebug'}
0x18011e25e  mov     [rcx+8], rax
0x18011e262  cmp     qword ptr [rcx+0A8h], 0
0x18011e26a  jz      short loc_18011E276
0x18011e26c  mov     ecx, 3D414Bh
0x18011e271  call    MsoShipAssertTagProc
0x18011e276  cmp     byte ptr [rbx+193h], 0
0x18011e27d  jnz     short loc_18011E289
0x18011e27f  mov     ecx, 3D414Ch
0x18011e284  call    MsoShipAssertTagProc
0x18011e289  lea     rcx, [rbx+2A0h]
0x18011e290  call    ??1?$vector@VDiscardableCacheRegistrationRecord@CPowerManager@@V?$allocator@VDiscardableCacheRegistrationRecord@CPowerManager@@@std@@@std@@QEAA@XZ; std::vector<CPowerManager::DiscardableCacheRegistrationRecord>::~vector<CPowerManager::DiscardableCacheRegistrationRecord>(void)
0x18011e295  lea     rcx, [rbx+278h]; lpCriticalSection
0x18011e29c  call    cs:__imp_DeleteCriticalSection
0x18011e2a2  lea     rcx, [rbx+258h]
0x18011e2a9  call    ??1?$vector@VInputInfoRegistrationRecord@CPowerManager@@V?$allocator@VInputInfoRegistrationRecord@CPowerManager@@@std@@@std@@QEAA@XZ; std::vector<CPowerManager::InputInfoRegistrationRecord>::~vector<CPowerManager::InputInfoRegistrationRecord>(void)
0x18011e2ae  xchg    ax, ax
0x18011e2b0  lea     rcx, [rbx+230h]; lpCriticalSection
0x18011e2b7  call    cs:__imp_DeleteCriticalSection
0x18011e2bd  nop
0x18011e2be  lea     rcx, [rbx+210h]
0x18011e2c5  call    ?Clear@?$TCntPtr@VMsoIdleTaskNoRefCount@@@Mso@@QEAAXXZ; Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear(void)
0x18011e2ca  lea     rcx, [rbx+208h]
0x18011e2d1  call    ?Clear@?$TCntPtr@VMsoIdleTaskNoRefCount@@@Mso@@QEAAXXZ; Mso::TCntPtr<MsoIdleTaskNoRefCount>::Clear(void)
0x18011e2d6  mov     rcx, [rbx+1F8h]; hObject
0x18011e2dd  test    rcx, rcx
0x18011e2e0  jz      short loc_18011E2F4
0x18011e2e2  mov     qword ptr [rbx+1F8h], 0
0x18011e2ed  call    cs:__imp_CloseHandle
0x18011e2f3  nop
0x18011e2f4  mov     rcx, [rbx+1F0h]; hObject
0x18011e2fb  test    rcx, rcx
0x18011e2fe  jz      short loc_18011E312
0x18011e300  mov     qword ptr [rbx+1F0h], 0
0x18011e30b  call    cs:__imp_CloseHandle
0x18011e311  nop
0x18011e312  mov     rcx, [rbx+0B8h]; hObject
0x18011e319  test    rcx, rcx
0x18011e31c  jz      short loc_18011E330
0x18011e31e  mov     qword ptr [rbx+0B8h], 0
0x18011e329  call    cs:__imp_CloseHandle
0x18011e32f  nop
0x18011e330  mov     rcx, [rbx+0B0h]; hObject
0x18011e337  test    rcx, rcx
0x18011e33a  jz      short loc_18011E34E
0x18011e33c  mov     qword ptr [rbx+0B0h], 0
0x18011e347  call    cs:__imp_CloseHandle
0x18011e34d  nop
0x18011e34e  lea     rcx, [rbx+38h]; lpCriticalSection
0x18011e352  call    cs:__imp_DeleteCriticalSection
0x18011e358  nop
0x18011e359  lea     rcx, [rbx+18h]
0x18011e35d  add     rsp, 20h
0x18011e361  pop     rbx
0x18011e362  jmp     ??1?$vector@VInputInfoRegistrationRecord@CPowerManager@@V?$allocator@VInputInfoRegistrationRecord@CPowerManager@@@std@@@std@@QEAA@XZ; std::vector<CPowerManager::InputInfoRegistrationRecord>::~vector<CPowerManager::InputInfoRegistrationRecord>(void)
```

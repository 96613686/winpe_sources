# CEnumOfflineFilesData::~CEnumOfflineFilesData(void)

- ea: `0x180022560`
- end: `0x18002273d`
- name: `??1CEnumOfflineFilesData@@EEAA@XZ`
- size: `477`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800224e0`

## callees

- `0x18001990c`
- `0x180022560`
- `0x180022750`
- `0x180022844`
- `0x18004fef4`
- `0x180089010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180022715`
- `ntdll!RtlFreeUnicodeString` at `0x180022715`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022681`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022681`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022592`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022592`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022691`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002269b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002269b`

## pseudocode

```c
void __fastcall CEnumOfflineFilesData::~CEnumOfflineFilesData(struct _RTL_CRITICAL_SECTION *this, unsigned int a2)
{
  bool v2; // zf
  CFindContext *SpinCount; // rcx
  WCHAR *OwningThread; // rax
  _WORD *LockSemaphore; // rcx
  __int64 v7; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  v2 = LODWORD(this[23].DebugInfo) == 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CEnumOfflineFilesData::`vftable'{for `CMonitoredObject'};
  this->OwningThread = &CEnumOfflineFilesData::`vftable'{for `IEnumOfflineFilesData'};
  if ( !v2 )
  {
    DeleteCriticalSection(this + 22);
    LODWORD(this[23].DebugInfo) = 0;
  }
  SpinCount = (CFindContext *)this->SpinCount;
  if ( SpinCount )
    CFindContext::`scalar deleting destructor'(SpinCount, a2);
  if ( this != (struct _RTL_CRITICAL_SECTION *)-928LL )
  {
    CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(&this[23].LockCount);
    CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(&this[23].OwningThread);
    CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(&this[23].LockSemaphore);
    CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(&this[23].SpinCount);
  }
  CItemFilter::_DestroyFilterControlBlocks((CItemFilter *)&this[15].OwningThread);
  if ( this != (struct _RTL_CRITICAL_SECTION *)-560LL )
  {
    if ( this != (struct _RTL_CRITICAL_SECTION *)-576LL )
    {
      OwningThread = (WCHAR *)this[14].OwningThread;
      if ( OwningThread )
      {
        if ( OwningThread != this[14].LockSemaphore )
        {
          *(_QWORD *)&UnicodeString.Length = 0;
          UnicodeString.Buffer = OwningThread;
          RtlFreeUnicodeString(&UnicodeString);
        }
        this[14].OwningThread = this[14].LockSemaphore;
        this[14].SpinCount = (ULONG_PTR)this[15].DebugInfo;
      }
    }
    LockSemaphore = this[14].LockSemaphore;
    *(_QWORD *)&this[14].LockCount = LockSemaphore;
    if ( LockSemaphore )
      *LockSemaphore = 0;
    LOWORD(this[14].DebugInfo) = 0;
    WORD1(this[14].DebugInfo) = this[15].DebugInfo;
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMonitoredObject::`vftable';
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_35f7768de0a037dc6f6ad00626564c6d_Traceguids, this);
  if ( this->RecursionCount )
  {
    v7 = g_invsemTasksInProgress;
    if ( g_invsemTasksInProgress )
    {
      _InterlockedIncrement((volatile signed __int32 *)(g_invsemTasksInProgress + 8LL));
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 32));
      v2 = (*(_DWORD *)(v7 + 24))-- == 1;
      if ( v2 )
        SetEvent(*(HANDLE *)(v7 + 16));
      LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 32));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
    }
  }
}

```

## disassembly

```asm
0x180022560  mov     [rsp+arg_8], rbx
0x180022565  push    rdi
0x180022566  sub     rsp, 30h
0x18002256a  cmp     dword ptr [rcx+398h], 0
0x180022571  lea     rax, ??_7CEnumOfflineFilesData@@6BCMonitoredObject@@@; const CEnumOfflineFilesData::`vftable'{for `CMonitoredObject'}
0x180022578  mov     [rcx], rax
0x18002257b  mov     rbx, rcx
0x18002257e  lea     rax, ??_7CEnumOfflineFilesData@@6BIEnumOfflineFilesData@@@; const CEnumOfflineFilesData::`vftable'{for `IEnumOfflineFilesData'}
0x180022585  mov     [rcx+10h], rax
0x180022589  jz      short loc_1800225A2
0x18002258b  add     rcx, 370h; lpCriticalSection
0x180022592  call    cs:__imp_DeleteCriticalSection
0x180022598  mov     dword ptr [rbx+398h], 0
0x1800225a2  mov     rcx, [rbx+20h]; this
0x1800225a6  test    rcx, rcx
0x1800225a9  jnz     loc_1800226E3
0x1800225af  lea     rdi, [rbx+3A0h]
0x1800225b6  test    rdi, rdi
0x1800225b9  jnz     loc_1800226BB
0x1800225bf  lea     rcx, [rbx+268h]; this
0x1800225c6  call    ?_DestroyFilterControlBlocks@CItemFilter@@AEAAXXZ; CItemFilter::_DestroyFilterControlBlocks(void)
0x1800225cb  lea     rdi, [rbx+230h]
0x1800225d2  test    rdi, rdi
0x1800225d5  jz      short loc_180022640
0x1800225d7  lea     rax, [rdi+10h]
0x1800225db  test    rax, rax
0x1800225de  jz      short loc_180022615
0x1800225e0  mov     rax, [rbx+240h]
0x1800225e7  test    rax, rax
0x1800225ea  jz      short loc_180022615
0x1800225ec  cmp     rax, [rbx+248h]
0x1800225f3  jnz     loc_180022702
0x1800225f9  mov     rax, [rbx+248h]
0x180022600  mov     [rbx+240h], rax
0x180022607  mov     rax, [rbx+258h]
0x18002260e  mov     [rbx+250h], rax
0x180022615  mov     rcx, [rbx+248h]
0x18002261c  mov     [rbx+238h], rcx
0x180022623  test    rcx, rcx
0x180022626  jz      short loc_18002262D
0x180022628  xor     eax, eax
0x18002262a  mov     [rcx], ax
0x18002262d  xor     eax, eax
0x18002262f  mov     [rdi], ax
0x180022632  movzx   eax, word ptr [rbx+258h]
0x180022639  mov     [rbx+232h], ax
0x180022640  lea     rax, ??_7CMonitoredObject@@6B@; const CMonitoredObject::`vftable'
0x180022647  mov     [rbx], rax
0x18002264a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022651  lea     rax, WPP_GLOBAL_Control
0x180022658  cmp     rcx, rax
0x18002265b  jz      short loc_180022667
0x18002265d  test    byte ptr [rcx+1Ch], 8
0x180022661  jnz     loc_180022720
0x180022667  cmp     dword ptr [rbx+0Ch], 0
0x18002266b  jz      short loc_1800226B0
0x18002266d  mov     rbx, cs:?g_invsemTasksInProgress@@3VCInvSemaphore@@A; CInvSemaphore g_invsemTasksInProgress
0x180022674  test    rbx, rbx
0x180022677  jz      short loc_1800226B0
0x180022679  lock inc dword ptr [rbx+8]
0x18002267d  lea     rcx, [rbx+20h]; lpCriticalSection
0x180022681  call    cs:__imp_EnterCriticalSection
0x180022687  sub     dword ptr [rbx+18h], 1
0x18002268b  jnz     short loc_180022697
0x18002268d  mov     rcx, [rbx+10h]; hEvent
0x180022691  call    cs:__imp_SetEvent
0x180022697  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002269b  call    cs:__imp_LeaveCriticalSection
0x1800226a1  mov     eax, 0FFFFFFFFh
0x1800226a6  lock xadd [rbx+8], eax
0x1800226ab  cmp     eax, 1
0x1800226ae  jz      short loc_1800226ED
0x1800226b0  mov     rbx, [rsp+38h+arg_8]
0x1800226b5  add     rsp, 30h
0x1800226b9  pop     rdi
0x1800226ba  retn
0x1800226bb  mov     rcx, rdi
0x1800226be  call    ??$CscCom_SafeReleaseAndNullPtr@UIEnumOfflineFilesData@@@@YAXAEAPEAUIEnumOfflineFilesData@@@Z; CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(IEnumOfflineFilesData * &)
0x1800226c3  lea     rcx, [rdi+8]
0x1800226c7  call    ??$CscCom_SafeReleaseAndNullPtr@UIEnumOfflineFilesData@@@@YAXAEAPEAUIEnumOfflineFilesData@@@Z; CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(IEnumOfflineFilesData * &)
0x1800226cc  lea     rcx, [rdi+10h]
0x1800226d0  call    ??$CscCom_SafeReleaseAndNullPtr@UIEnumOfflineFilesData@@@@YAXAEAPEAUIEnumOfflineFilesData@@@Z; CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(IEnumOfflineFilesData * &)
0x1800226d5  lea     rcx, [rdi+18h]
0x1800226d9  call    ??$CscCom_SafeReleaseAndNullPtr@UIEnumOfflineFilesData@@@@YAXAEAPEAUIEnumOfflineFilesData@@@Z; CscCom_SafeReleaseAndNullPtr<IEnumOfflineFilesData>(IEnumOfflineFilesData * &)
0x1800226de  jmp     loc_1800225BF
0x1800226e3  call    ??_GCFindContext@@QEAAPEAXI@Z; CFindContext::`scalar deleting destructor'(uint)
0x1800226e8  jmp     loc_1800225AF
0x1800226ed  mov     rax, [rbx]
0x1800226f0  mov     edx, 1
0x1800226f5  mov     rcx, rbx
0x1800226f8  mov     rax, [rax]
0x1800226fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022700  jmp     short loc_1800226B0
0x180022702  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180022707  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x180022710  mov     [rsp+38h+UnicodeString.Buffer], rax
0x180022715  call    cs:__imp_RtlFreeUnicodeString
0x18002271b  jmp     loc_1800225F9
0x180022720  mov     rcx, [rcx+10h]
0x180022724  lea     r8, WPP_35f7768de0a037dc6f6ad00626564c6d_Traceguids
0x18002272b  mov     edx, 10h
0x180022730  mov     r9, rbx
0x180022733  call    WPP_SF_q
0x180022738  jmp     loc_180022667
```

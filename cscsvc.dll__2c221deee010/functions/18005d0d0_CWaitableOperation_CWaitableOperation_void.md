# CWaitableOperation::~CWaitableOperation(void)

- ea: `0x18005d0d0`
- end: `0x18005d165`
- name: `??1CWaitableOperation@@UEAA@XZ`
- size: `149`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d020`
- `0x18005d270`

## callees

- `0x18004af1c`
- `0x18005d0d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d10b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d10b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d0fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d0fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005d0ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005d0ec`

## pseudocode

```c
void __fastcall CWaitableOperation::~CWaitableOperation(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_WAIT *OwningThread; // rcx
  HANDLE LockSemaphore; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWaitableOperation::`vftable';
  OwningThread = (struct _TP_WAIT *)this->OwningThread;
  if ( OwningThread )
    CloseThreadpoolWait(OwningThread);
  if ( LODWORD(this[2].DebugInfo) )
    DeleteCriticalSection(this + 1);
  LockSemaphore = this->LockSemaphore;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  _InterlockedDecrement(&g_cChgMonWaitableOpObjects);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
      (unsigned int)g_cChgMonWaitableOpObjects,
      this);
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CRefCounted::`vftable';
}

```

## disassembly

```asm
0x18005d0d0  push    rbx
0x18005d0d2  sub     rsp, 30h
0x18005d0d6  lea     rax, ??_7CWaitableOperation@@6B@; const CWaitableOperation::`vftable'
0x18005d0dd  mov     rbx, rcx
0x18005d0e0  mov     [rcx], rax
0x18005d0e3  mov     rcx, [rcx+10h]; pwa
0x18005d0e7  test    rcx, rcx
0x18005d0ea  jz      short loc_18005D0F2
0x18005d0ec  call    cs:__imp_CloseThreadpoolWait
0x18005d0f2  cmp     dword ptr [rbx+50h], 0
0x18005d0f6  jz      short loc_18005D102
0x18005d0f8  lea     rcx, [rbx+28h]; lpCriticalSection
0x18005d0fc  call    cs:__imp_DeleteCriticalSection
0x18005d102  mov     rcx, [rbx+18h]; hObject
0x18005d106  test    rcx, rcx
0x18005d109  jz      short loc_18005D111
0x18005d10b  call    cs:__imp_CloseHandle
0x18005d111  lock dec cs:?g_cChgMonWaitableOpObjects@@3JA; long g_cChgMonWaitableOpObjects
0x18005d118  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d11f  lea     rax, WPP_GLOBAL_Control
0x18005d126  cmp     rcx, rax
0x18005d129  jz      short loc_18005D155
0x18005d12b  test    dword ptr [rcx+1Ch], 10000h
0x18005d132  jz      short loc_18005D155
0x18005d134  mov     r9d, cs:?g_cChgMonWaitableOpObjects@@3JA; long g_cChgMonWaitableOpObjects
0x18005d13b  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005d142  mov     rcx, [rcx+10h]
0x18005d146  mov     edx, 0Bh
0x18005d14b  mov     [rsp+38h+var_18], rbx
0x18005d150  call    WPP_SF_dq
0x18005d155  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x18005d15c  mov     [rbx], rax
0x18005d15f  add     rsp, 30h
0x18005d163  pop     rbx
0x18005d164  retn
```

# CDXGIFactory::TryCreateWatchdogThread(void)

- ea: `0x180062a20`
- end: `0x180062b01`
- name: `?TryCreateWatchdogThread@CDXGIFactory@@QEAAXXZ`
- size: `225`
- prototype: `void __fastcall(CDXGIFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800217ec`

## callees

- `0x18001c7a4`
- `0x18001d480`
- `0x18002dbe8`
- `0x180058ef4`
- `0x180062a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a78`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180062a97`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180062a97`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180062ac4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180062ac4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062ad9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDXGIFactory::TryCreateWatchdogThread(CDXGIFactory *this)
{
  HANDLE EventA; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-28h] BYREF
  char v3; // [rsp+38h] [rbp-20h]
  _BYTE v4[24]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = (unsigned __int64)this;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    &lpCriticalSection,
    &CriticalSection);
  v5 = 0;
  if ( !(unsigned int)CompatValueImpl("DisableFullscreenWatchdog", &v5, 0) || !v5 )
  {
    CLockedDLLWatchdogThread::CLockedDLLWatchdogThread((CLockedDLLWatchdogThread *)v4);
    LeaveCriticalSection(lpCriticalSection);
    v3 = 0;
    if ( !hHandle )
    {
      EventA = CreateEventA(0, 0, 0, 0);
      if ( EventA )
      {
        hHandle = CreateThread(0, 0, FullscreenWatchdogThreadWorker, 0, 0, 0);
        if ( !hHandle )
          CloseHandle(EventA);
        hObject = EventA;
      }
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v4);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&lpCriticalSection);
}

```

## disassembly

```asm
0x180062a20  mov     [rsp+arg_0], rcx
0x180062a25  push    rbx
0x180062a26  sub     rsp, 50h
0x180062a2a  lea     rdx, CriticalSection
0x180062a31  lea     rcx, [rsp+58h+lpCriticalSection]
0x180062a36  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180062a3b  nop
0x180062a3c  mov     [rsp+58h+arg_0], 0
0x180062a45  xor     r8d, r8d; bool
0x180062a48  lea     rdx, [rsp+58h+arg_0]; unsigned __int64 *
0x180062a4d  lea     rcx, aDisablefullscr; "DisableFullscreenWatchdog"
0x180062a54  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x180062a59  test    eax, eax
0x180062a5b  jz      short loc_180062A69
0x180062a5d  cmp     [rsp+58h+arg_0], 0
0x180062a63  jnz     loc_180062AF1
0x180062a69  lea     rcx, [rsp+58h+var_18]; this
0x180062a6e  call    ??0CLockedDLLWatchdogThread@@QEAA@XZ; CLockedDLLWatchdogThread::CLockedDLLWatchdogThread(void)
0x180062a73  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180062a78  call    cs:__imp_LeaveCriticalSection
0x180062a7e  mov     [rsp+58h+var_20], 0
0x180062a83  cmp     cs:hHandle, 0
0x180062a8b  jnz     short loc_180062AE6
0x180062a8d  xor     r9d, r9d; lpName
0x180062a90  xor     r8d, r8d; bInitialState
0x180062a93  xor     edx, edx; bManualReset
0x180062a95  xor     ecx, ecx; lpEventAttributes
0x180062a97  call    cs:__imp_CreateEventA
0x180062a9d  mov     rbx, rax
0x180062aa0  test    rax, rax
0x180062aa3  jz      short loc_180062AE6
0x180062aa5  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180062aae  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180062ab6  xor     r9d, r9d; lpParameter
0x180062ab9  lea     r8, FullscreenWatchdogThreadWorker; lpStartAddress
0x180062ac0  xor     edx, edx; dwStackSize
0x180062ac2  xor     ecx, ecx; lpThreadAttributes
0x180062ac4  call    cs:__imp_CreateThread
0x180062aca  mov     cs:hHandle, rax
0x180062ad1  test    rax, rax
0x180062ad4  jnz     short loc_180062ADF
0x180062ad6  mov     rcx, rbx; hObject
0x180062ad9  call    cs:__imp_CloseHandle
0x180062adf  mov     cs:hObject, rbx
0x180062ae6  lea     rcx, [rsp+58h+var_18]
0x180062aeb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180062af0  nop
0x180062af1  lea     rcx, [rsp+58h+lpCriticalSection]
0x180062af6  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180062afb  add     rsp, 50h
0x180062aff  pop     rbx
0x180062b00  retn
```

# CDataStore::FinalRelease(void)

- ea: `0x180046a10`
- end: `0x180046ae3`
- name: `?FinalRelease@CDataStore@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CDataStore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046990`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180046a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ac2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ac2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046aac`

## pseudocode

```c
__int64 __fastcall CDataStore::FinalRelease(struct _RTL_CRITICAL_SECTION *this)
{
  _QWORD *LockSemaphore; // rcx
  _QWORD *p_Type; // rcx
  _QWORD *OwningThread; // rcx
  _QWORD *SpinCount; // rcx
  unsigned int v6; // ebx
  _DWORD v8[18]; // [rsp+20h] [rbp-48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v8, "CDataStore::FinalRelease", 124, 1);
  EnterCriticalSection(this + 1);
  while ( 1 )
  {
    LockSemaphore = this[19].LockSemaphore;
    if ( !LockSemaphore )
      break;
    this[19].LockSemaphore = (HANDLE)LockSemaphore[11];
    CoTaskMemFree(LockSemaphore);
  }
  while ( 1 )
  {
    p_Type = &this[20].DebugInfo->Type;
    if ( !p_Type )
      break;
    this[20].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)p_Type[11];
    CoTaskMemFree(p_Type);
  }
  while ( 1 )
  {
    OwningThread = this[20].OwningThread;
    if ( !OwningThread )
      break;
    this[20].OwningThread = (HANDLE)OwningThread[11];
    CoTaskMemFree(OwningThread);
  }
  while ( 1 )
  {
    SpinCount = (_QWORD *)this[20].SpinCount;
    if ( !SpinCount )
      break;
    this[20].SpinCount = SpinCount[11];
    CoTaskMemFree(SpinCount);
  }
  LeaveCriticalSection(this + 1);
  v6 = v8[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v8);
  return v6;
}

```

## disassembly

```asm
0x180046a10  mov     [rsp+arg_0], rbx
0x180046a15  push    rdi
0x180046a16  sub     rsp, 60h
0x180046a1a  mov     r9d, 1; unsigned __int16
0x180046a20  lea     rdx, aCdatastoreFina; "CDataStore::FinalRelease"
0x180046a27  mov     rbx, rcx
0x180046a2a  lea     rcx, [rsp+68h+var_48]; this
0x180046a2f  lea     r8d, [r9+7Bh]; unsigned __int16
0x180046a33  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180046a38  lea     rcx, [rbx+28h]; lpCriticalSection
0x180046a3c  call    cs:__imp_EnterCriticalSection
0x180046a42  jmp     short loc_180046A55
0x180046a44  mov     rax, [rcx+58h]
0x180046a48  mov     [rbx+310h], rax
0x180046a4f  call    cs:__imp_CoTaskMemFree
0x180046a55  mov     rcx, [rbx+310h]; pv
0x180046a5c  test    rcx, rcx
0x180046a5f  jnz     short loc_180046A44
0x180046a61  jmp     short loc_180046A74
0x180046a63  mov     rax, [rcx+58h]
0x180046a67  mov     [rbx+320h], rax
0x180046a6e  call    cs:__imp_CoTaskMemFree
0x180046a74  mov     rcx, [rbx+320h]; pv
0x180046a7b  test    rcx, rcx
0x180046a7e  jnz     short loc_180046A63
0x180046a80  jmp     short loc_180046A93
0x180046a82  mov     rax, [rcx+58h]
0x180046a86  mov     [rbx+330h], rax
0x180046a8d  call    cs:__imp_CoTaskMemFree
0x180046a93  mov     rcx, [rbx+330h]; pv
0x180046a9a  test    rcx, rcx
0x180046a9d  jnz     short loc_180046A82
0x180046a9f  jmp     short loc_180046AB2
0x180046aa1  mov     rax, [rcx+58h]
0x180046aa5  mov     [rbx+340h], rax
0x180046aac  call    cs:__imp_CoTaskMemFree
0x180046ab2  mov     rcx, [rbx+340h]; pv
0x180046ab9  test    rcx, rcx
0x180046abc  jnz     short loc_180046AA1
0x180046abe  lea     rcx, [rbx+28h]; lpCriticalSection
0x180046ac2  call    cs:__imp_LeaveCriticalSection
0x180046ac8  mov     ebx, [rsp+68h+var_48]
0x180046acc  lea     rcx, [rsp+68h+var_48]; this
0x180046ad1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180046ad6  mov     eax, ebx
0x180046ad8  mov     rbx, [rsp+68h+arg_0]
0x180046add  add     rsp, 60h
0x180046ae1  pop     rdi
0x180046ae2  retn
```

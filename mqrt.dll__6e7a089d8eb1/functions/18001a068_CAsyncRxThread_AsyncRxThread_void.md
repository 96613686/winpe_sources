# CAsyncRxThread::AsyncRxThread(void)

- ea: `0x18001a068`
- end: `0x18001a137`
- name: `?AsyncRxThread@CAsyncRxThread@@AEAAXXZ`
- size: `207`
- prototype: `void __fastcall __noreturn(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a140`

## callees

- `0x180013bbc`
- `0x18001a068`
- `0x18001a63c`
- `0x18001a6e8`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x18001a0aa`
- `KERNEL32!WaitForMultipleObjects` at `0x18001a0aa`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001a10f`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001a10f`
- `KERNEL32!CloseHandle` at `0x18001a0df`
- `KERNEL32!CloseHandle` at `0x18001a0df`
- `KERNEL32!LeaveCriticalSection` at `0x18001a0ce`
- `KERNEL32!LeaveCriticalSection` at `0x18001a103`
- `KERNEL32!LeaveCriticalSection` at `0x18001a0ce`
- `KERNEL32!LeaveCriticalSection` at `0x18001a103`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn CAsyncRxThread::AsyncRxThread(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v1; // rbx
  DWORD SpinCount; // ecx
  DWORD v3; // r9d
  DWORD v4; // eax
  HMODULE OwningThread; // rsi

  v1 = lpCriticalSection;
  while ( 1 )
  {
    try
    {
      do
      {
        while ( 1 )
        {
          if ( LOBYTE(v1[27].LockSemaphore) )
            CAsyncRxThread::RemoveCanceledEntries(v1);
          SpinCount = v1[1].SpinCount;
          v3 = 40000;
          if ( SpinCount != 1 )
            v3 = 36000000;
          v4 = WaitForMultipleObjects(SpinCount, (const HANDLE *)&v1[14].SpinCount, 0, v3);
          if ( v4 != 258 )
            break;
          CCriticalSection::Lock((CCriticalSection *)v1);
          if ( LODWORD(v1[1].SpinCount) <= 1 )
          {
            OwningThread = (HMODULE)v1[1].OwningThread;
            CloseHandle(v1[1].LockSemaphore);
            v1[1].LockSemaphore = 0;
            v1[1].OwningThread = 0;
            LOBYTE(v1[1].DebugInfo) = 0;
            LOBYTE(v1[27].LockSemaphore) = 0;
            LeaveCriticalSection(v1);
            FreeLibraryAndExitThread(OwningThread, 0);
          }
          LeaveCriticalSection(v1);
        }
      }
      while ( !v4 );
      CAsyncRxThread::InvokeCallback(v1, v4);
    }
    catch ( std::bad_alloc )
    {
      v1 = lpCriticalSection;
      continue;
    }
  }
}

```

## disassembly

```asm
0x18001a068  mov     [rsp+arg_10], rbx
0x18001a06d  mov     [rsp+arg_0], rcx
0x18001a072  push    rsi
0x18001a073  sub     rsp, 20h
0x18001a077  mov     rbx, rcx
0x18001a07a  cmp     byte ptr [rbx+450h], 0
0x18001a081  jz      short loc_18001A08B
0x18001a083  mov     rcx, rbx; lpCriticalSection
0x18001a086  call    ?RemoveCanceledEntries@CAsyncRxThread@@AEAAXXZ; CAsyncRxThread::RemoveCanceledEntries(void)
0x18001a08b  mov     ecx, [rbx+48h]; nCount
0x18001a08e  mov     eax, 2255100h
0x18001a093  mov     r9d, 9C40h
0x18001a099  cmp     ecx, 1
0x18001a09c  cmovnz  r9d, eax; dwMilliseconds
0x18001a0a0  lea     rdx, [rbx+250h]; lpHandles
0x18001a0a7  xor     r8d, r8d; bWaitAll
0x18001a0aa  call    cs:__imp_WaitForMultipleObjects
0x18001a0b0  cmp     eax, 102h
0x18001a0b5  jnz     short loc_18001A115
0x18001a0b7  mov     [rsp+28h+arg_8], rbx
0x18001a0bc  mov     rcx, rbx; this
0x18001a0bf  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a0c4  nop
0x18001a0c5  cmp     dword ptr [rbx+48h], 1
0x18001a0c9  jbe     short loc_18001A0D7
0x18001a0cb  mov     rcx, rbx; lpCriticalSection
0x18001a0ce  call    cs:__imp_LeaveCriticalSection
0x18001a0d4  nop
0x18001a0d5  jmp     short loc_18001A07A
0x18001a0d7  mov     rsi, [rbx+38h]
0x18001a0db  mov     rcx, [rbx+40h]; hObject
0x18001a0df  call    cs:__imp_CloseHandle
0x18001a0e5  mov     qword ptr [rbx+40h], 0
0x18001a0ed  mov     qword ptr [rbx+38h], 0
0x18001a0f5  mov     byte ptr [rbx+28h], 0
0x18001a0f9  mov     byte ptr [rbx+450h], 0
0x18001a100  mov     rcx, rbx; lpCriticalSection
0x18001a103  call    cs:__imp_LeaveCriticalSection
0x18001a109  nop
0x18001a10a  xor     edx, edx; dwExitCode
0x18001a10c  mov     rcx, rsi; hLibModule
0x18001a10f  call    cs:__imp_FreeLibraryAndExitThread
0x18001a115  test    eax, eax
0x18001a117  jz      loc_18001A07A
0x18001a11d  mov     edx, eax; unsigned int
0x18001a11f  mov     rcx, rbx; lpCriticalSection
0x18001a122  call    ?InvokeCallback@CAsyncRxThread@@AEAAXK@Z; CAsyncRxThread::InvokeCallback(ulong)
0x18001a127  nop
0x18001a128  jmp     loc_18001A07A
0x18001a12d  mov     rbx, [rsp+28h+arg_0]
0x18001a132  jmp     loc_18001A07A
```

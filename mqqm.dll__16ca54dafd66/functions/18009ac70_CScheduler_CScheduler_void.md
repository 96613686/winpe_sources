# CScheduler::CScheduler(void)

- ea: `0x18009ac70`
- end: `0x18009adeb`
- name: `??0CScheduler@@QEAA@XZ`
- size: `379`
- prototype: `CScheduler *__fastcall(CScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009bb58`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18000f634`
- `0x18009ac70`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009ad0c`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009adb4`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009ad0c`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009adb4`
- `KERNEL32!GetLastError` at `0x18009acd4`
- `KERNEL32!GetLastError` at `0x18009ad7c`
- `KERNEL32!GetLastError` at `0x18009acd4`
- `KERNEL32!GetLastError` at `0x18009ad7c`
- `KERNEL32!CloseHandle` at `0x18009addb`
- `KERNEL32!CloseHandle` at `0x18009addb`
- `KERNEL32!CreateEventW` at `0x18009acac`
- `KERNEL32!CreateEventW` at `0x18009acac`
- `KERNEL32!CreateThread` at `0x18009ad58`
- `KERNEL32!CreateThread` at `0x18009ad58`
- `KERNEL32!GetTickCount` at `0x18009ac96`
- `KERNEL32!GetTickCount` at `0x18009ac96`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CScheduler *__fastcall CScheduler::CScheduler(CScheduler *this, unsigned int a2)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  HANDLE v5; // rax
  DWORD v6; // eax
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD ThreadId; // [rsp+68h] [rbp+10h] BYREF

  CCriticalSection::CCriticalSection(this, a2);
  *((_QWORD *)this + 6) = (char *)this + 48;
  *((_QWORD *)this + 7) = (char *)this + 48;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 9) = GetTickCount();
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a8efc244ab6367b306b422e185e2b5f_Traceguids, LastError);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  ThreadId = 0;
  v5 = CreateThread(0, 0, CScheduler::SchedulerThread, this, 0, &ThreadId);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5a8efc244ab6367b306b422e185e2b5f_Traceguids, v6);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  CloseHandle(v5);
  return this;
}

```

## disassembly

```asm
0x18009ac70  mov     [rsp+arg_0], rcx
0x18009ac75  push    rbx
0x18009ac76  sub     rsp, 50h
0x18009ac7a  mov     rbx, rcx
0x18009ac7d  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x18009ac82  nop
0x18009ac83  lea     rax, [rbx+30h]
0x18009ac87  mov     [rax], rax
0x18009ac8a  mov     [rax+8], rax
0x18009ac8e  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18009ac96  call    cs:__imp_GetTickCount
0x18009ac9c  mov     eax, eax
0x18009ac9e  mov     [rbx+48h], rax
0x18009aca2  xor     r9d, r9d; lpName
0x18009aca5  xor     r8d, r8d; bInitialState
0x18009aca8  xor     edx, edx; bManualReset
0x18009acaa  xor     ecx, ecx; lpEventAttributes
0x18009acac  call    cs:__imp_CreateEventW
0x18009acb2  mov     [rbx+28h], rax
0x18009acb6  test    rax, rax
0x18009acb9  jnz     short loc_18009AD30
0x18009acbb  lea     rax, WPP_GLOBAL_Control
0x18009acc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009acc9  cmp     rcx, rax
0x18009accc  jz      short loc_18009ACFA
0x18009acce  test    byte ptr [rcx+1Ch], 1
0x18009acd2  jz      short loc_18009ACFA
0x18009acd4  call    cs:__imp_GetLastError
0x18009acda  mov     edx, 0Ah
0x18009acdf  mov     r9d, eax
0x18009ace2  lea     r8, WPP_5a8efc244ab6367b306b422e185e2b5f_Traceguids
0x18009ace9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009acf0  mov     rcx, [rcx+10h]
0x18009acf4  call    WPP_SF_d
0x18009acf9  nop
0x18009acfa  mov     r8d, 1
0x18009ad00  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009ad07  lea     rcx, [rsp+58h+pExceptionObject]
0x18009ad0c  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009ad12  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009ad19  mov     [rsp+58h+pExceptionObject], rax
0x18009ad1e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009ad25  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18009ad2a  call    _CxxThrowException_0
0x18009ad30  mov     [rsp+58h+ThreadId], 0
0x18009ad38  lea     rax, [rsp+58h+ThreadId]
0x18009ad3d  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18009ad42  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18009ad4a  mov     r9, rbx; lpParameter
0x18009ad4d  lea     r8, ?SchedulerThread@CScheduler@@CAKPEAX@Z; lpStartAddress
0x18009ad54  xor     edx, edx; dwStackSize
0x18009ad56  xor     ecx, ecx; lpThreadAttributes
0x18009ad58  call    cs:__imp_CreateThread
0x18009ad5e  test    rax, rax
0x18009ad61  jnz     short loc_18009ADD8
0x18009ad63  lea     rax, WPP_GLOBAL_Control
0x18009ad6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ad71  cmp     rcx, rax
0x18009ad74  jz      short loc_18009ADA2
0x18009ad76  test    byte ptr [rcx+1Ch], 1
0x18009ad7a  jz      short loc_18009ADA2
0x18009ad7c  call    cs:__imp_GetLastError
0x18009ad82  mov     edx, 0Bh
0x18009ad87  mov     r9d, eax
0x18009ad8a  lea     r8, WPP_5a8efc244ab6367b306b422e185e2b5f_Traceguids
0x18009ad91  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ad98  mov     rcx, [rcx+10h]
0x18009ad9c  call    WPP_SF_d
0x18009ada1  nop
0x18009ada2  mov     r8d, 1
0x18009ada8  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009adaf  lea     rcx, [rsp+58h+pExceptionObject]
0x18009adb4  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009adba  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009adc1  mov     [rsp+58h+pExceptionObject], rax
0x18009adc6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009adcd  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18009add2  call    _CxxThrowException_0
0x18009add8  mov     rcx, rax; hObject
0x18009addb  call    cs:__imp_CloseHandle
0x18009ade1  nop
0x18009ade2  mov     rax, rbx
0x18009ade5  add     rsp, 50h
0x18009ade9  pop     rbx
0x18009adea  retn
```

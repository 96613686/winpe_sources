# CReadWriteLock::GetReadWaiterSemaphore(void)

- ea: `0x180017a60`
- end: `0x180017b1e`
- name: `?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ`
- size: `190`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017be8`
- `0x180017e14`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x180017a60`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180017ae0`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180017ae0`
- `KERNEL32!CloseHandle` at `0x180017b0e`
- `KERNEL32!CloseHandle` at `0x180017b0e`
- `KERNEL32!CreateSemaphoreW` at `0x180017a81`
- `KERNEL32!CreateSemaphoreW` at `0x180017a81`
- `KERNEL32!GetLastError` at `0x180017aa8`
- `KERNEL32!GetLastError` at `0x180017aa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CReadWriteLock::GetReadWaiterSemaphore(CReadWriteLock *this)
{
  HANDLE SemaphoreW; // rax
  DWORD LastError; // eax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    if ( !SemaphoreW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
      }
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)SemaphoreW, 0) )
      CloseHandle(SemaphoreW);
  }
  return (void *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180017a60  push    rbx
0x180017a62  sub     rsp, 40h
0x180017a66  mov     rbx, rcx
0x180017a69  cmp     qword ptr [rcx+8], 0
0x180017a6e  jnz     loc_180017B14
0x180017a74  xor     r9d, r9d; lpName
0x180017a77  xor     edx, edx; lInitialCount
0x180017a79  xor     ecx, ecx; lpSemaphoreAttributes
0x180017a7b  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180017a81  call    cs:__imp_CreateSemaphoreW
0x180017a87  mov     rcx, rax; hObject
0x180017a8a  test    rax, rax
0x180017a8d  jnz     short loc_180017B04
0x180017a8f  lea     rcx, WPP_GLOBAL_Control
0x180017a96  mov     rax, cs:WPP_GLOBAL_Control
0x180017a9d  cmp     rax, rcx
0x180017aa0  jz      short loc_180017ACE
0x180017aa2  test    byte ptr [rax+1Ch], 1
0x180017aa6  jz      short loc_180017ACE
0x180017aa8  call    cs:__imp_GetLastError
0x180017aae  mov     edx, 0Eh
0x180017ab3  mov     r9d, eax
0x180017ab6  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ac4  mov     rcx, [rcx+10h]
0x180017ac8  call    WPP_SF_d
0x180017acd  nop
0x180017ace  mov     r8d, 1
0x180017ad4  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180017adb  lea     rcx, [rsp+48h+pExceptionObject]
0x180017ae0  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180017ae6  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180017aed  mov     [rsp+48h+pExceptionObject], rax
0x180017af2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180017af9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180017afe  call    _CxxThrowException_0
0x180017b04  xor     eax, eax
0x180017b06  lock cmpxchg [rbx+8], rcx
0x180017b0c  jz      short loc_180017B14
0x180017b0e  call    cs:__imp_CloseHandle
0x180017b14  mov     rax, [rbx+8]
0x180017b18  add     rsp, 40h
0x180017b1c  pop     rbx
0x180017b1d  retn
```

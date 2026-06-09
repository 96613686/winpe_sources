# CReadWriteLock::GetReadWaiterSemaphore(void)

- ea: `0x18009b394`
- end: `0x18009b452`
- name: `?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ`
- size: `190`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009b51c`
- `0x18009b748`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18009b394`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b414`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b414`
- `KERNEL32!CreateSemaphoreW` at `0x18009b3b5`
- `KERNEL32!CreateSemaphoreW` at `0x18009b3b5`
- `KERNEL32!GetLastError` at `0x18009b3dc`
- `KERNEL32!GetLastError` at `0x18009b3dc`
- `KERNEL32!CloseHandle` at `0x18009b442`
- `KERNEL32!CloseHandle` at `0x18009b442`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
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
0x18009b394  push    rbx
0x18009b396  sub     rsp, 40h
0x18009b39a  mov     rbx, rcx
0x18009b39d  cmp     qword ptr [rcx+8], 0
0x18009b3a2  jnz     loc_18009B448
0x18009b3a8  xor     r9d, r9d; lpName
0x18009b3ab  xor     edx, edx; lInitialCount
0x18009b3ad  xor     ecx, ecx; lpSemaphoreAttributes
0x18009b3af  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18009b3b5  call    cs:__imp_CreateSemaphoreW
0x18009b3bb  mov     rcx, rax; hObject
0x18009b3be  test    rax, rax
0x18009b3c1  jnz     short loc_18009B438
0x18009b3c3  lea     rcx, WPP_GLOBAL_Control
0x18009b3ca  mov     rax, cs:WPP_GLOBAL_Control
0x18009b3d1  cmp     rax, rcx
0x18009b3d4  jz      short loc_18009B402
0x18009b3d6  test    byte ptr [rax+1Ch], 1
0x18009b3da  jz      short loc_18009B402
0x18009b3dc  call    cs:__imp_GetLastError
0x18009b3e2  mov     edx, 0Eh
0x18009b3e7  mov     r9d, eax
0x18009b3ea  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x18009b3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b3f8  mov     rcx, [rcx+10h]
0x18009b3fc  call    WPP_SF_d
0x18009b401  nop
0x18009b402  mov     r8d, 1
0x18009b408  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009b40f  lea     rcx, [rsp+48h+pExceptionObject]
0x18009b414  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009b41a  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009b421  mov     [rsp+48h+pExceptionObject], rax
0x18009b426  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009b42d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18009b432  call    _CxxThrowException_0
0x18009b438  xor     eax, eax
0x18009b43a  lock cmpxchg [rbx+8], rcx
0x18009b440  jz      short loc_18009B448
0x18009b442  call    cs:__imp_CloseHandle
0x18009b448  mov     rax, [rbx+8]
0x18009b44c  add     rsp, 40h
0x18009b450  pop     rbx
0x18009b451  retn
```

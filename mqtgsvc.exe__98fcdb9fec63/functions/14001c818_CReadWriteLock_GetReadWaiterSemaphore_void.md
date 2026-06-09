# CReadWriteLock::GetReadWaiterSemaphore(void)

- ea: `0x14001c818`
- end: `0x14001c8d6`
- name: `?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ`
- size: `190`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c9a0`
- `0x14001cbcc`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x14001c818`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001c8c6`
- `KERNEL32!CloseHandle` at `0x14001c8c6`
- `KERNEL32!CreateSemaphoreW` at `0x14001c839`
- `KERNEL32!CreateSemaphoreW` at `0x14001c839`
- `KERNEL32!GetLastError` at `0x14001c860`
- `KERNEL32!GetLastError` at `0x14001c860`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14001c898`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14001c898`

## pseudocode

```c
void *__fastcall CReadWriteLock::GetReadWaiterSemaphore(CReadWriteLock *this)
{
  HANDLE SemaphoreW; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    if ( !SemaphoreW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids);
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
0x14001c818  push    rbx
0x14001c81a  sub     rsp, 40h
0x14001c81e  mov     rbx, rcx
0x14001c821  cmp     qword ptr [rcx+8], 0
0x14001c826  jnz     loc_14001C8CC
0x14001c82c  xor     r9d, r9d; lpName
0x14001c82f  xor     edx, edx; lInitialCount
0x14001c831  xor     ecx, ecx; lpSemaphoreAttributes
0x14001c833  mov     r8d, 7FFFFFFFh; lMaximumCount
0x14001c839  call    cs:__imp_CreateSemaphoreW
0x14001c83f  mov     rcx, rax; hObject
0x14001c842  test    rax, rax
0x14001c845  jnz     short loc_14001C8BC
0x14001c847  lea     rcx, WPP_GLOBAL_Control
0x14001c84e  mov     rax, cs:WPP_GLOBAL_Control
0x14001c855  cmp     rax, rcx
0x14001c858  jz      short loc_14001C886
0x14001c85a  test    byte ptr [rax+1Ch], 1
0x14001c85e  jz      short loc_14001C886
0x14001c860  call    cs:__imp_GetLastError
0x14001c866  mov     edx, 0Eh
0x14001c86b  mov     r9d, eax
0x14001c86e  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001c875  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c87c  mov     rcx, [rcx+10h]
0x14001c880  call    WPP_SF_d
0x14001c885  nop
0x14001c886  mov     r8d, 1
0x14001c88c  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14001c893  lea     rcx, [rsp+48h+pExceptionObject]
0x14001c898  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14001c89e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14001c8a5  mov     [rsp+48h+pExceptionObject], rax
0x14001c8aa  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14001c8b1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001c8b6  call    _CxxThrowException_0
0x14001c8bc  xor     eax, eax
0x14001c8be  lock cmpxchg [rbx+8], rcx
0x14001c8c4  jz      short loc_14001C8CC
0x14001c8c6  call    cs:__imp_CloseHandle
0x14001c8cc  mov     rax, [rbx+8]
0x14001c8d0  add     rsp, 40h
0x14001c8d4  pop     rbx
0x14001c8d5  retn
```

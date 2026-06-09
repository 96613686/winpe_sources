# CReadWriteLock::GetWriteWaiterEvent(void)

- ea: `0x18009b458`
- end: `0x18009b513`
- name: `?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ`
- size: `187`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009b5ec`
- `0x18009b6ac`
- `0x18009b748`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18009b458`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b4d5`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b4d5`
- `KERNEL32!GetLastError` at `0x18009b49d`
- `KERNEL32!GetLastError` at `0x18009b49d`
- `KERNEL32!CloseHandle` at `0x18009b503`
- `KERNEL32!CloseHandle` at `0x18009b503`
- `KERNEL32!CreateEventW` at `0x18009b476`
- `KERNEL32!CreateEventW` at `0x18009b476`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CReadWriteLock::GetWriteWaiterEvent(CReadWriteLock *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
      }
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)EventW, 0) )
      CloseHandle(EventW);
  }
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x18009b458  push    rbx
0x18009b45a  sub     rsp, 40h
0x18009b45e  mov     rbx, rcx
0x18009b461  cmp     qword ptr [rcx+10h], 0
0x18009b466  jnz     loc_18009B509
0x18009b46c  xor     r9d, r9d; lpName
0x18009b46f  xor     r8d, r8d; bInitialState
0x18009b472  xor     edx, edx; bManualReset
0x18009b474  xor     ecx, ecx; lpEventAttributes
0x18009b476  call    cs:__imp_CreateEventW
0x18009b47c  mov     rcx, rax; hObject
0x18009b47f  test    rax, rax
0x18009b482  jnz     short loc_18009B4F9
0x18009b484  lea     rcx, WPP_GLOBAL_Control
0x18009b48b  mov     rax, cs:WPP_GLOBAL_Control
0x18009b492  cmp     rax, rcx
0x18009b495  jz      short loc_18009B4C3
0x18009b497  test    byte ptr [rax+1Ch], 1
0x18009b49b  jz      short loc_18009B4C3
0x18009b49d  call    cs:__imp_GetLastError
0x18009b4a3  mov     edx, 0Fh
0x18009b4a8  mov     r9d, eax
0x18009b4ab  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x18009b4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b4b9  mov     rcx, [rcx+10h]
0x18009b4bd  call    WPP_SF_d
0x18009b4c2  nop
0x18009b4c3  mov     r8d, 1
0x18009b4c9  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009b4d0  lea     rcx, [rsp+48h+pExceptionObject]
0x18009b4d5  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009b4db  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009b4e2  mov     [rsp+48h+pExceptionObject], rax
0x18009b4e7  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009b4ee  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18009b4f3  call    _CxxThrowException_0
0x18009b4f9  xor     eax, eax
0x18009b4fb  lock cmpxchg [rbx+10h], rcx
0x18009b501  jz      short loc_18009B509
0x18009b503  call    cs:__imp_CloseHandle
0x18009b509  mov     rax, [rbx+10h]
0x18009b50d  add     rsp, 40h
0x18009b511  pop     rbx
0x18009b512  retn
```

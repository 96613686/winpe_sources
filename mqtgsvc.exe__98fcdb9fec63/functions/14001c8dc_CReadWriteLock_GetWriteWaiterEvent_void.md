# CReadWriteLock::GetWriteWaiterEvent(void)

- ea: `0x14001c8dc`
- end: `0x14001c997`
- name: `?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ`
- size: `187`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001ca70`
- `0x14001cb30`
- `0x14001cbcc`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x14001c8dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001c987`
- `KERNEL32!CloseHandle` at `0x14001c987`
- `KERNEL32!GetLastError` at `0x14001c921`
- `KERNEL32!GetLastError` at `0x14001c921`
- `KERNEL32!CreateEventW` at `0x14001c8fa`
- `KERNEL32!CreateEventW` at `0x14001c8fa`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14001c959`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14001c959`

## pseudocode

```c
void *__fastcall CReadWriteLock::GetWriteWaiterEvent(CReadWriteLock *this)
{
  HANDLE EventW; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids);
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
0x14001c8dc  push    rbx
0x14001c8de  sub     rsp, 40h
0x14001c8e2  mov     rbx, rcx
0x14001c8e5  cmp     qword ptr [rcx+10h], 0
0x14001c8ea  jnz     loc_14001C98D
0x14001c8f0  xor     r9d, r9d; lpName
0x14001c8f3  xor     r8d, r8d; bInitialState
0x14001c8f6  xor     edx, edx; bManualReset
0x14001c8f8  xor     ecx, ecx; lpEventAttributes
0x14001c8fa  call    cs:__imp_CreateEventW
0x14001c900  mov     rcx, rax; hObject
0x14001c903  test    rax, rax
0x14001c906  jnz     short loc_14001C97D
0x14001c908  lea     rcx, WPP_GLOBAL_Control
0x14001c90f  mov     rax, cs:WPP_GLOBAL_Control
0x14001c916  cmp     rax, rcx
0x14001c919  jz      short loc_14001C947
0x14001c91b  test    byte ptr [rax+1Ch], 1
0x14001c91f  jz      short loc_14001C947
0x14001c921  call    cs:__imp_GetLastError
0x14001c927  mov     edx, 0Fh
0x14001c92c  mov     r9d, eax
0x14001c92f  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001c936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c93d  mov     rcx, [rcx+10h]
0x14001c941  call    WPP_SF_d
0x14001c946  nop
0x14001c947  mov     r8d, 1
0x14001c94d  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14001c954  lea     rcx, [rsp+48h+pExceptionObject]
0x14001c959  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14001c95f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14001c966  mov     [rsp+48h+pExceptionObject], rax
0x14001c96b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14001c972  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001c977  call    _CxxThrowException_0
0x14001c97d  xor     eax, eax
0x14001c97f  lock cmpxchg [rbx+10h], rcx
0x14001c985  jz      short loc_14001C98D
0x14001c987  call    cs:__imp_CloseHandle
0x14001c98d  mov     rax, [rbx+10h]
0x14001c991  add     rsp, 40h
0x14001c995  pop     rbx
0x14001c996  retn
```

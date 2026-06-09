# CReadWriteLock::GetWriteWaiterEvent(void)

- ea: `0x180017b24`
- end: `0x180017bdf`
- name: `?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ`
- size: `187`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017cb8`
- `0x180017d78`
- `0x180017e14`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x180017b24`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180017ba1`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180017ba1`
- `KERNEL32!CloseHandle` at `0x180017bcf`
- `KERNEL32!CloseHandle` at `0x180017bcf`
- `KERNEL32!CreateEventW` at `0x180017b42`
- `KERNEL32!CreateEventW` at `0x180017b42`
- `KERNEL32!GetLastError` at `0x180017b69`
- `KERNEL32!GetLastError` at `0x180017b69`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
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
0x180017b24  push    rbx
0x180017b26  sub     rsp, 40h
0x180017b2a  mov     rbx, rcx
0x180017b2d  cmp     qword ptr [rcx+10h], 0
0x180017b32  jnz     loc_180017BD5
0x180017b38  xor     r9d, r9d; lpName
0x180017b3b  xor     r8d, r8d; bInitialState
0x180017b3e  xor     edx, edx; bManualReset
0x180017b40  xor     ecx, ecx; lpEventAttributes
0x180017b42  call    cs:__imp_CreateEventW
0x180017b48  mov     rcx, rax; hObject
0x180017b4b  test    rax, rax
0x180017b4e  jnz     short loc_180017BC5
0x180017b50  lea     rcx, WPP_GLOBAL_Control
0x180017b57  mov     rax, cs:WPP_GLOBAL_Control
0x180017b5e  cmp     rax, rcx
0x180017b61  jz      short loc_180017B8F
0x180017b63  test    byte ptr [rax+1Ch], 1
0x180017b67  jz      short loc_180017B8F
0x180017b69  call    cs:__imp_GetLastError
0x180017b6f  mov     edx, 0Fh
0x180017b74  mov     r9d, eax
0x180017b77  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b85  mov     rcx, [rcx+10h]
0x180017b89  call    WPP_SF_d
0x180017b8e  nop
0x180017b8f  mov     r8d, 1
0x180017b95  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180017b9c  lea     rcx, [rsp+48h+pExceptionObject]
0x180017ba1  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180017ba7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180017bae  mov     [rsp+48h+pExceptionObject], rax
0x180017bb3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180017bba  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180017bbf  call    _CxxThrowException_0
0x180017bc5  xor     eax, eax
0x180017bc7  lock cmpxchg [rbx+10h], rcx
0x180017bcd  jz      short loc_180017BD5
0x180017bcf  call    cs:__imp_CloseHandle
0x180017bd5  mov     rax, [rbx+10h]
0x180017bd9  add     rsp, 40h
0x180017bdd  pop     rbx
0x180017bde  retn
```

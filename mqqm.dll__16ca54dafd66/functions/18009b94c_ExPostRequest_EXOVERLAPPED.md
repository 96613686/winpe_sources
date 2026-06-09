# ExPostRequest(EXOVERLAPPED *)

- ea: `0x18009b94c`
- end: `0x18009b9f2`
- name: `?ExPostRequest@@YAXPEAVEXOVERLAPPED@@@Z`
- size: `166`
- prototype: `void __fastcall(LPOVERLAPPED lpOverlapped)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025cf8`
- `0x18007c318`
- `0x18009b1bc`
- `0x1800a1304`
- `0x1800bef8c`
- `0x1800c0798`
- `0x1800c4ed0`
- `0x1800c4ef0`
- `0x1800c4f60`
- `0x1800cd9fc`

## callees

- `0x180004d91`
- `0x18009b94c`
- `0x18009baf4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b9c8`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009b9c8`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18009b964`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18009b964`
- `KERNEL32!GetLastError` at `0x18009b987`
- `KERNEL32!GetLastError` at `0x18009b987`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ExPostRequest(LPOVERLAPPED lpOverlapped)
{
  DWORD LastError; // eax
  __int64 v3; // r8
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF

  if ( !PostQueuedCompletionStatus(CompletionPort, 0, 0, lpOverlapped) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v3, lpOverlapped, CompletionPort, LastError);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18009b94c  push    rbx
0x18009b94e  sub     rsp, 50h
0x18009b952  mov     rbx, rcx
0x18009b955  mov     r9, rcx; lpOverlapped
0x18009b958  xor     r8d, r8d; dwCompletionKey
0x18009b95b  xor     edx, edx; dwNumberOfBytesTransferred
0x18009b95d  mov     rcx, cs:CompletionPort; CompletionPort
0x18009b964  call    cs:__imp_PostQueuedCompletionStatus
0x18009b96a  test    eax, eax
0x18009b96c  jnz     short loc_18009B9EC
0x18009b96e  lea     rcx, WPP_GLOBAL_Control
0x18009b975  mov     rax, cs:WPP_GLOBAL_Control
0x18009b97c  cmp     rax, rcx
0x18009b97f  jz      short loc_18009B9B6
0x18009b981  test    byte ptr [rax+1Ch], 1
0x18009b985  jz      short loc_18009B9B6
0x18009b987  call    cs:__imp_GetLastError
0x18009b98d  mov     edx, 0Ch
0x18009b992  mov     [rsp+58h+var_30], eax
0x18009b996  mov     rax, cs:CompletionPort
0x18009b99d  mov     [rsp+58h+var_38], rax
0x18009b9a2  mov     r9, rbx
0x18009b9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b9ac  mov     rcx, [rcx+10h]
0x18009b9b0  call    WPP_SF_qqd
0x18009b9b5  nop
0x18009b9b6  mov     r8d, 1
0x18009b9bc  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009b9c3  lea     rcx, [rsp+58h+pExceptionObject]
0x18009b9c8  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009b9ce  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009b9d5  mov     [rsp+58h+pExceptionObject], rax
0x18009b9da  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009b9e1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18009b9e6  call    _CxxThrowException_0
0x18009b9ec  add     rsp, 50h
0x18009b9f0  pop     rbx
0x18009b9f1  retn
```

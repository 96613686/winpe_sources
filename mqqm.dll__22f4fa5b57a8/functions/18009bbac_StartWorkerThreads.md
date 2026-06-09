# StartWorkerThreads

- ea: `0x18009bbac`
- end: `0x18009bcd6`
- name: `StartWorkerThreads`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009bb58`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18009bbac`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009bca7`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18009bca7`
- `KERNEL32!GetLastError` at `0x18009bc6f`
- `KERNEL32!GetLastError` at `0x18009bc6f`
- `KERNEL32!CloseHandle` at `0x18009bc29`
- `KERNEL32!CloseHandle` at `0x18009bc29`
- `KERNEL32!CreateThread` at `0x18009bc19`
- `KERNEL32!CreateThread` at `0x18009bc19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StartWorkerThreads(unsigned int a1)
{
  unsigned int v1; // ebx
  HANDLE v2; // rax
  DWORD LastError; // eax
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  v1 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids, a1);
  while ( v1 )
  {
    ThreadId = 0;
    v2 = CreateThread(0, 0, ExpWorkingThread, 0, 0, &ThreadId);
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids, LastError);
      }
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    --v1;
    CloseHandle(v2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids, ThreadId);
  }
}

```

## disassembly

```asm
0x18009bbac  mov     [rsp+arg_8], rbx
0x18009bbb1  push    rdi
0x18009bbb2  sub     rsp, 50h
0x18009bbb6  mov     ebx, ecx
0x18009bbb8  lea     rdi, WPP_GLOBAL_Control
0x18009bbbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bbc6  cmp     rcx, rdi
0x18009bbc9  jz      short loc_18009BBE9
0x18009bbcb  test    byte ptr [rcx+1Ch], 4
0x18009bbcf  jz      short loc_18009BBE9
0x18009bbd1  mov     edx, 0Ah
0x18009bbd6  mov     r9d, ebx
0x18009bbd9  lea     r8, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids
0x18009bbe0  mov     rcx, [rcx+10h]
0x18009bbe4  call    WPP_SF_d
0x18009bbe9  test    ebx, ebx
0x18009bbeb  jz      loc_18009BCCB
0x18009bbf1  mov     [rsp+58h+ThreadId], 0
0x18009bbf9  lea     rax, [rsp+58h+ThreadId]
0x18009bbfe  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18009bc03  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18009bc0b  xor     r9d, r9d; lpParameter
0x18009bc0e  lea     r8, ?ExpWorkingThread@@YAKPEAX@Z; lpStartAddress
0x18009bc15  xor     edx, edx; dwStackSize
0x18009bc17  xor     ecx, ecx; lpThreadAttributes
0x18009bc19  call    cs:__imp_CreateThread
0x18009bc1f  test    rax, rax
0x18009bc22  jz      short loc_18009BC5D
0x18009bc24  dec     ebx
0x18009bc26  mov     rcx, rax; hObject
0x18009bc29  call    cs:__imp_CloseHandle
0x18009bc2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc36  cmp     rcx, rdi
0x18009bc39  jz      short loc_18009BBE9
0x18009bc3b  test    byte ptr [rcx+1Ch], 4
0x18009bc3f  jz      short loc_18009BBE9
0x18009bc41  mov     edx, 0Ch
0x18009bc46  mov     r9d, [rsp+58h+ThreadId]
0x18009bc4b  lea     r8, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids
0x18009bc52  mov     rcx, [rcx+10h]
0x18009bc56  call    WPP_SF_d
0x18009bc5b  jmp     short loc_18009BBE9
0x18009bc5d  mov     rax, cs:WPP_GLOBAL_Control
0x18009bc64  cmp     rax, rdi
0x18009bc67  jz      short loc_18009BC95
0x18009bc69  test    byte ptr [rax+1Ch], 1
0x18009bc6d  jz      short loc_18009BC95
0x18009bc6f  call    cs:__imp_GetLastError
0x18009bc75  mov     edx, 0Bh
0x18009bc7a  mov     r9d, eax
0x18009bc7d  lea     r8, WPP_65aff9a660c23318cc16e8357723afa1_Traceguids
0x18009bc84  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc8b  mov     rcx, [rcx+10h]
0x18009bc8f  call    WPP_SF_d
0x18009bc94  nop
0x18009bc95  mov     r8d, 1
0x18009bc9b  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18009bca2  lea     rcx, [rsp+58h+pExceptionObject]
0x18009bca7  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18009bcad  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18009bcb4  mov     [rsp+58h+pExceptionObject], rax
0x18009bcb9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18009bcc0  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18009bcc5  call    _CxxThrowException_0
0x18009bccb  mov     rbx, [rsp+58h+arg_8]
0x18009bcd0  add     rsp, 50h
0x18009bcd4  pop     rdi
0x18009bcd5  retn
```

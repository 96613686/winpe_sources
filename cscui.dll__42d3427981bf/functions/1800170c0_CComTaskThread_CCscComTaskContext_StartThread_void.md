# CComTaskThread<CCscComTaskContext>::_StartThread(void)

- ea: `0x1800170c0`
- end: `0x180017191`
- name: `?_StartThread@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016e74`

## callees

- `0x180006050`
- `0x180008788`
- `0x180014f94`
- `0x1800170c0`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18001713d`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18001713d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001715c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001715c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017170`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017170`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscComTaskContext>::_StartThread(char *Block)
{
  int ManualResetEvent; // ebx
  HANDLE *v3; // r14

  ManualResetEvent = 0;
  if ( !*((_QWORD *)Block + 9) )
  {
    ManualResetEvent = ((__int64 (*)(void))CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent)();
    if ( ManualResetEvent < 0 )
      goto LABEL_15;
  }
  if ( !*((_QWORD *)Block + 10) )
  {
    ManualResetEvent = ((__int64 (*)(void))CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent)();
    if ( ManualResetEvent < 0 )
      goto LABEL_15;
  }
  if ( !*((_QWORD *)Block + 8) )
    ManualResetEvent = CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(Block, Block + 64);
  if ( ManualResetEvent < 0 )
    goto LABEL_15;
  _InterlockedIncrement((volatile signed __int32 *)Block);
  v3 = (HANDLE *)(Block + 88);
  if ( !SHCreateThreadWithHandle((WCHAR)CComTaskThread<CCscComTaskContext>::_ThreadProc) )
  {
    CComTaskThread<CCscComTaskContext>::Release(Block);
LABEL_11:
    ManualResetEvent = -2147467259;
LABEL_15:
    CComTaskThread<CCscUiComTaskContext>::_CloseEvents(Block);
    return (unsigned int)ManualResetEvent;
  }
  if ( WaitForSingleObject(*((HANDLE *)Block + 8), 0xFFFFFFFF) )
    goto LABEL_11;
  ManualResetEvent = *((_DWORD *)Block + 26);
  if ( ManualResetEvent < 0 )
  {
    CloseHandle(*v3);
    *v3 = 0;
    goto LABEL_15;
  }
  return (unsigned int)ManualResetEvent;
}

```

## disassembly

```asm
0x1800170c0  push    rbx
0x1800170c2  push    rsi
0x1800170c3  push    rdi
0x1800170c4  push    r14
0x1800170c6  sub     rsp, 38h
0x1800170ca  xor     ebx, ebx
0x1800170cc  lea     rdx, [rcx+48h]
0x1800170d0  mov     rdi, rcx
0x1800170d3  cmp     [rdx], rbx
0x1800170d6  jnz     short loc_1800170E3
0x1800170d8  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x1800170dd  mov     ebx, eax
0x1800170df  test    eax, eax
0x1800170e1  js      short loc_180017110
0x1800170e3  lea     rdx, [rdi+50h]
0x1800170e7  cmp     qword ptr [rdx], 0
0x1800170eb  jnz     short loc_1800170F8
0x1800170ed  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x1800170f2  mov     ebx, eax
0x1800170f4  test    eax, eax
0x1800170f6  js      short loc_180017110
0x1800170f8  lea     rsi, [rdi+40h]
0x1800170fc  cmp     qword ptr [rsi], 0
0x180017100  jnz     short loc_18001710C
0x180017102  mov     rdx, rsi
0x180017105  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x18001710a  mov     ebx, eax
0x18001710c  test    ebx, ebx
0x18001710e  jns     short loc_180017120
0x180017110  mov     rcx, rdi
0x180017113  call    ?_CloseEvents@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAXXZ; CComTaskThread<CCscUiComTaskContext>::_CloseEvents(void)
0x180017118  test    ebx, ebx
0x18001711a  js      short loc_180017185
0x18001711c  lea     rsi, [rdi+40h]
0x180017120  lock inc dword ptr [rdi]
0x180017123  xor     r9d, r9d
0x180017126  lea     r14, [rdi+58h]
0x18001712a  mov     rdx, rdi
0x18001712d  mov     [rsp+58h+var_38], r14
0x180017132  lea     rcx, ?_ThreadProc@?$CComTaskThread@VCCscComTaskContext@@@@CAKPEAX@Z; ch
0x180017139  lea     r8d, [r9+10h]
0x18001713d  call    cs:__imp_SHCreateThreadWithHandle
0x180017143  test    eax, eax
0x180017145  jnz     short loc_180017156
0x180017147  mov     rcx, rdi; Block
0x18001714a  call    ?Release@?$CComTaskThread@VCCscComTaskContext@@@@QEAAKXZ; CComTaskThread<CCscComTaskContext>::Release(void)
0x18001714f  mov     ebx, 80004005h
0x180017154  jmp     short loc_18001717D
0x180017156  mov     rcx, [rsi]; hHandle
0x180017159  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001715c  call    cs:__imp_WaitForSingleObject
0x180017162  test    eax, eax
0x180017164  jnz     short loc_18001714F
0x180017166  mov     ebx, [rdi+68h]
0x180017169  test    ebx, ebx
0x18001716b  jns     short loc_180017185
0x18001716d  mov     rcx, [r14]; hObject
0x180017170  call    cs:__imp_CloseHandle
0x180017176  mov     qword ptr [r14], 0
0x18001717d  mov     rcx, rdi
0x180017180  call    ?_CloseEvents@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAXXZ; CComTaskThread<CCscUiComTaskContext>::_CloseEvents(void)
0x180017185  mov     eax, ebx
0x180017187  add     rsp, 38h
0x18001718b  pop     r14
0x18001718d  pop     rdi
0x18001718e  pop     rsi
0x18001718f  pop     rbx
0x180017190  retn
```

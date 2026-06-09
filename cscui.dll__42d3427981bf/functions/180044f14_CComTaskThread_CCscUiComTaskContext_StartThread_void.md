# CComTaskThread<CCscUiComTaskContext>::_StartThread(void)

- ea: `0x180044f14`
- end: `0x180044fe5`
- name: `?_StartThread@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044ee8`

## callees

- `0x180008788`
- `0x180014f94`
- `0x180044588`
- `0x180044f14`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180044f91`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180044f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044fb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044fb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044fc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044fc4`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscUiComTaskContext>::_StartThread(char *Block)
{
  int ManualResetEvent; // ebx
  HANDLE *v3; // r14

  ManualResetEvent = 0;
  if ( !*((_QWORD *)Block + 9) )
  {
    ManualResetEvent = CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(Block, Block + 72);
    if ( ManualResetEvent < 0 )
      goto LABEL_15;
  }
  if ( !*((_QWORD *)Block + 10) )
  {
    ManualResetEvent = CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(Block, Block + 80);
    if ( ManualResetEvent < 0 )
      goto LABEL_15;
  }
  if ( !*((_QWORD *)Block + 8) )
    ManualResetEvent = CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(Block, Block + 64);
  if ( ManualResetEvent < 0 )
    goto LABEL_15;
  _InterlockedIncrement((volatile signed __int32 *)Block);
  v3 = (HANDLE *)(Block + 88);
  if ( !SHCreateThreadWithHandle((WCHAR)CComTaskThread<CCscUiComTaskContext>::_ThreadProc) )
  {
    CComTaskThread<CCscUiComTaskContext>::Release(Block);
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
0x180044f14  push    rbx
0x180044f16  push    rsi
0x180044f17  push    rdi
0x180044f18  push    r14
0x180044f1a  sub     rsp, 38h
0x180044f1e  xor     ebx, ebx
0x180044f20  lea     rdx, [rcx+48h]
0x180044f24  mov     rdi, rcx
0x180044f27  cmp     [rdx], rbx
0x180044f2a  jnz     short loc_180044F37
0x180044f2c  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x180044f31  mov     ebx, eax
0x180044f33  test    eax, eax
0x180044f35  js      short loc_180044F64
0x180044f37  lea     rdx, [rdi+50h]
0x180044f3b  cmp     qword ptr [rdx], 0
0x180044f3f  jnz     short loc_180044F4C
0x180044f41  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x180044f46  mov     ebx, eax
0x180044f48  test    eax, eax
0x180044f4a  js      short loc_180044F64
0x180044f4c  lea     rsi, [rdi+40h]
0x180044f50  cmp     qword ptr [rsi], 0
0x180044f54  jnz     short loc_180044F60
0x180044f56  mov     rdx, rsi
0x180044f59  call    ?_CreateManualResetEvent@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJPEAPEAX@Z; CComTaskThread<CCscComTaskContext>::_CreateManualResetEvent(void * *)
0x180044f5e  mov     ebx, eax
0x180044f60  test    ebx, ebx
0x180044f62  jns     short loc_180044F74
0x180044f64  mov     rcx, rdi
0x180044f67  call    ?_CloseEvents@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAXXZ; CComTaskThread<CCscUiComTaskContext>::_CloseEvents(void)
0x180044f6c  test    ebx, ebx
0x180044f6e  js      short loc_180044FD9
0x180044f70  lea     rsi, [rdi+40h]
0x180044f74  lock inc dword ptr [rdi]
0x180044f77  xor     r9d, r9d
0x180044f7a  lea     r14, [rdi+58h]
0x180044f7e  mov     rdx, rdi
0x180044f81  mov     [rsp+58h+var_38], r14
0x180044f86  lea     rcx, ?_ThreadProc@?$CComTaskThread@VCCscUiComTaskContext@@@@CAKPEAX@Z; ch
0x180044f8d  lea     r8d, [r9+10h]
0x180044f91  call    cs:__imp_SHCreateThreadWithHandle
0x180044f97  test    eax, eax
0x180044f99  jnz     short loc_180044FAA
0x180044f9b  mov     rcx, rdi; Block
0x180044f9e  call    ?Release@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAKXZ; CComTaskThread<CCscUiComTaskContext>::Release(void)
0x180044fa3  mov     ebx, 80004005h
0x180044fa8  jmp     short loc_180044FD1
0x180044faa  mov     rcx, [rsi]; hHandle
0x180044fad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180044fb0  call    cs:__imp_WaitForSingleObject
0x180044fb6  test    eax, eax
0x180044fb8  jnz     short loc_180044FA3
0x180044fba  mov     ebx, [rdi+68h]
0x180044fbd  test    ebx, ebx
0x180044fbf  jns     short loc_180044FD9
0x180044fc1  mov     rcx, [r14]; hObject
0x180044fc4  call    cs:__imp_CloseHandle
0x180044fca  mov     qword ptr [r14], 0
0x180044fd1  mov     rcx, rdi
0x180044fd4  call    ?_CloseEvents@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAXXZ; CComTaskThread<CCscUiComTaskContext>::_CloseEvents(void)
0x180044fd9  mov     eax, ebx
0x180044fdb  add     rsp, 38h
0x180044fdf  pop     r14
0x180044fe1  pop     rdi
0x180044fe2  pop     rsi
0x180044fe3  pop     rbx
0x180044fe4  retn
```

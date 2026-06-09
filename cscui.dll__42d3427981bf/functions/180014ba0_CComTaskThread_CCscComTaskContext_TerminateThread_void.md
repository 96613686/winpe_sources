# CComTaskThread<CCscComTaskContext>::TerminateThread(void)

- ea: `0x180014ba0`
- end: `0x180014c37`
- name: `?TerminateThread@?$CComTaskThread@VCCscComTaskContext@@@@QEAAJXZ`
- size: `151`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007414`
- `0x180007b7c`
- `0x180017734`
- `0x180026b38`
- `0x180029718`
- `0x1800298c0`
- `0x18002c260`
- `0x180032d50`
- `0x180034b74`
- `0x18003694c`
- `0x18004666c`

## callees

- `0x180014ba0`
- `0x180014fd0`
- `0x180016e74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014bbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014bbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014bed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c02`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscComTaskContext>::TerminateThread(__int64 a1)
{
  int v2; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 96) = GetCurrentThreadId();
  if ( (int)CComTaskThread<CCscComTaskContext>::_ReadyToAcceptCommands(a1, 0) < 0 )
  {
    v2 = 0;
  }
  else
  {
    v2 = CComTaskThread<CCscComTaskContext>::_DoCommand(a1, 1);
    if ( v2 >= 0 )
    {
      if ( WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF) )
      {
        v2 = -2147467259;
      }
      else
      {
        CloseHandle(*(HANDLE *)(a1 + 88));
        *(_QWORD *)(a1 + 88) = 0;
      }
    }
  }
  *(_DWORD *)(a1 + 96) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014ba0  mov     [rsp+arg_0], rbx
0x180014ba5  mov     [rsp+arg_8], rsi
0x180014baa  push    rdi
0x180014bab  sub     rsp, 20h
0x180014baf  mov     rbx, rcx
0x180014bb2  add     rcx, 8; lpCriticalSection
0x180014bb6  call    cs:__imp_EnterCriticalSection
0x180014bbc  call    cs:__imp_GetCurrentThreadId
0x180014bc2  xor     edx, edx
0x180014bc4  mov     rcx, rbx
0x180014bc7  mov     [rbx+60h], eax
0x180014bca  call    ?_ReadyToAcceptCommands@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJH@Z; CComTaskThread<CCscComTaskContext>::_ReadyToAcceptCommands(int)
0x180014bcf  test    eax, eax
0x180014bd1  js      short loc_180014C12
0x180014bd3  mov     edx, 1
0x180014bd8  mov     rcx, rbx
0x180014bdb  call    ?_DoCommand@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJW4COMMANDS@1@@Z; CComTaskThread<CCscComTaskContext>::_DoCommand(CComTaskThread<CCscComTaskContext>::COMMANDS)
0x180014be0  mov     edi, eax
0x180014be2  test    eax, eax
0x180014be4  js      short loc_180014C14
0x180014be6  mov     rcx, [rbx+58h]; hHandle
0x180014bea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014bed  call    cs:__imp_WaitForSingleObject
0x180014bf3  test    eax, eax
0x180014bf5  jz      short loc_180014BFE
0x180014bf7  mov     edi, 80004005h
0x180014bfc  jmp     short loc_180014C14
0x180014bfe  mov     rcx, [rbx+58h]; hObject
0x180014c02  call    cs:__imp_CloseHandle
0x180014c08  mov     qword ptr [rbx+58h], 0
0x180014c10  jmp     short loc_180014C14
0x180014c12  xor     edi, edi
0x180014c14  lea     rcx, [rbx+8]; lpCriticalSection
0x180014c18  mov     dword ptr [rbx+60h], 0
0x180014c1f  call    cs:__imp_LeaveCriticalSection
0x180014c25  mov     rbx, [rsp+28h+arg_0]
0x180014c2a  mov     eax, edi
0x180014c2c  mov     rsi, [rsp+28h+arg_8]
0x180014c31  add     rsp, 20h
0x180014c35  pop     rdi
0x180014c36  retn
```

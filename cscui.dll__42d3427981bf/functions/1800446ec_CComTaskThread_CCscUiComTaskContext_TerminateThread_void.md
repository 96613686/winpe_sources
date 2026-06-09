# CComTaskThread<CCscUiComTaskContext>::TerminateThread(void)

- ea: `0x1800446ec`
- end: `0x180044783`
- name: `?TerminateThread@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJXZ`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043be0`
- `0x180043c24`
- `0x180043ef4`
- `0x1800440f4`

## callees

- `0x180014fd0`
- `0x1800446ec`
- `0x180044ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044708`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044739`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044739`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004476b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004476b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004474e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004474e`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscUiComTaskContext>::TerminateThread(__int64 a1)
{
  int v2; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 96) = GetCurrentThreadId();
  if ( (int)CComTaskThread<CCscUiComTaskContext>::_ReadyToAcceptCommands(a1, 0) < 0 )
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
0x1800446ec  mov     [rsp+arg_0], rbx
0x1800446f1  mov     [rsp+arg_8], rsi
0x1800446f6  push    rdi
0x1800446f7  sub     rsp, 20h
0x1800446fb  mov     rbx, rcx
0x1800446fe  add     rcx, 8; lpCriticalSection
0x180044702  call    cs:__imp_EnterCriticalSection
0x180044708  call    cs:__imp_GetCurrentThreadId
0x18004470e  xor     edx, edx
0x180044710  mov     rcx, rbx
0x180044713  mov     [rbx+60h], eax
0x180044716  call    ?_ReadyToAcceptCommands@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAJH@Z; CComTaskThread<CCscUiComTaskContext>::_ReadyToAcceptCommands(int)
0x18004471b  test    eax, eax
0x18004471d  js      short loc_18004475E
0x18004471f  mov     edx, 1
0x180044724  mov     rcx, rbx
0x180044727  call    ?_DoCommand@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJW4COMMANDS@1@@Z; CComTaskThread<CCscComTaskContext>::_DoCommand(CComTaskThread<CCscComTaskContext>::COMMANDS)
0x18004472c  mov     edi, eax
0x18004472e  test    eax, eax
0x180044730  js      short loc_180044760
0x180044732  mov     rcx, [rbx+58h]; hHandle
0x180044736  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180044739  call    cs:__imp_WaitForSingleObject
0x18004473f  test    eax, eax
0x180044741  jz      short loc_18004474A
0x180044743  mov     edi, 80004005h
0x180044748  jmp     short loc_180044760
0x18004474a  mov     rcx, [rbx+58h]; hObject
0x18004474e  call    cs:__imp_CloseHandle
0x180044754  mov     qword ptr [rbx+58h], 0
0x18004475c  jmp     short loc_180044760
0x18004475e  xor     edi, edi
0x180044760  lea     rcx, [rbx+8]; lpCriticalSection
0x180044764  mov     dword ptr [rbx+60h], 0
0x18004476b  call    cs:__imp_LeaveCriticalSection
0x180044771  mov     rbx, [rsp+28h+arg_0]
0x180044776  mov     eax, edi
0x180044778  mov     rsi, [rsp+28h+arg_8]
0x18004477d  add     rsp, 20h
0x180044781  pop     rdi
0x180044782  retn
```

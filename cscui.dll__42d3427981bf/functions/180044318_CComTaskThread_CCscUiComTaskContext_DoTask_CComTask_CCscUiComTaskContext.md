# CComTaskThread<CCscUiComTaskContext>::DoTask(CComTask<CCscUiComTaskContext> *)

- ea: `0x180044318`
- end: `0x18004438e`
- name: `?DoTask@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscUiComTaskContext@@@@@Z`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043ef4`
- `0x1800440f4`
- `0x18004501c`

## callees

- `0x180014fd0`
- `0x180044318`
- `0x180044ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044331`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044331`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscUiComTaskContext>::DoTask(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 result; // rax

  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 100);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 96) = GetCurrentThreadId();
  v4 = CComTaskThread<CCscUiComTaskContext>::_ReadyToAcceptCommands(a1, 1);
  if ( v4 >= 0 )
  {
    *(_QWORD *)(a1 + 48) = a2;
    v4 = CComTaskThread<CCscComTaskContext>::_DoCommand(a1, 0);
    *(_QWORD *)(a1 + 48) = 0;
  }
  *(_DWORD *)(a1 + 96) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  result = (unsigned int)v4;
  *(_DWORD *)(a2 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180044318  push    rbx
0x18004431a  push    rbp
0x18004431b  push    rsi
0x18004431c  push    rdi
0x18004431d  sub     rsp, 28h
0x180044321  mov     eax, [rcx+64h]
0x180044324  mov     rbx, rcx
0x180044327  add     rcx, 8; lpCriticalSection
0x18004432b  mov     [rdx+0Ch], eax
0x18004432e  mov     rdi, rdx
0x180044331  call    cs:__imp_EnterCriticalSection
0x180044337  call    cs:__imp_GetCurrentThreadId
0x18004433d  mov     edx, 1
0x180044342  mov     rcx, rbx
0x180044345  mov     [rbx+60h], eax
0x180044348  call    ?_ReadyToAcceptCommands@?$CComTaskThread@VCCscUiComTaskContext@@@@AEAAJH@Z; CComTaskThread<CCscUiComTaskContext>::_ReadyToAcceptCommands(int)
0x18004434d  mov     esi, eax
0x18004434f  test    eax, eax
0x180044351  js      short loc_18004436B
0x180044353  xor     edx, edx
0x180044355  mov     [rbx+30h], rdi
0x180044359  mov     rcx, rbx
0x18004435c  call    ?_DoCommand@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJW4COMMANDS@1@@Z; CComTaskThread<CCscComTaskContext>::_DoCommand(CComTaskThread<CCscComTaskContext>::COMMANDS)
0x180044361  mov     esi, eax
0x180044363  mov     qword ptr [rbx+30h], 0
0x18004436b  lea     rcx, [rbx+8]; lpCriticalSection
0x18004436f  mov     dword ptr [rbx+60h], 0
0x180044376  call    cs:__imp_LeaveCriticalSection
0x18004437c  mov     eax, esi
0x18004437e  mov     dword ptr [rdi+0Ch], 0
0x180044385  add     rsp, 28h
0x180044389  pop     rdi
0x18004438a  pop     rsi
0x18004438b  pop     rbp
0x18004438c  pop     rbx
0x18004438d  retn
```

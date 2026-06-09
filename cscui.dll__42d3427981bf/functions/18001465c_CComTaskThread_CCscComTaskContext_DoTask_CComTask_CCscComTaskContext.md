# CComTaskThread<CCscComTaskContext>::DoTask(CComTask<CCscComTaskContext> *)

- ea: `0x18001465c`
- end: `0x1800146d2`
- name: `?DoTask@?$CComTaskThread@VCCscComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscComTaskContext@@@@@Z`
- size: `118`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016390`
- `0x180016444`
- `0x180016958`
- `0x18001a7dc`
- `0x180029718`
- `0x1800298c0`
- `0x18002be10`
- `0x18002bec4`
- `0x18002c260`
- `0x18002c3a0`
- `0x180032d50`
- `0x180034b74`
- `0x18003694c`

## callees

- `0x18001465c`
- `0x180014fd0`
- `0x180016e74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001467b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001467b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800146ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800146ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014675`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014675`

## pseudocode

```c
__int64 __fastcall CComTaskThread<CCscComTaskContext>::DoTask(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 result; // rax

  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 100);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 96) = GetCurrentThreadId();
  v4 = CComTaskThread<CCscComTaskContext>::_ReadyToAcceptCommands(a1, 1);
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
0x18001465c  push    rbx
0x18001465e  push    rbp
0x18001465f  push    rsi
0x180014660  push    rdi
0x180014661  sub     rsp, 28h
0x180014665  mov     eax, [rcx+64h]
0x180014668  mov     rbx, rcx
0x18001466b  add     rcx, 8; lpCriticalSection
0x18001466f  mov     [rdx+0Ch], eax
0x180014672  mov     rdi, rdx
0x180014675  call    cs:__imp_EnterCriticalSection
0x18001467b  call    cs:__imp_GetCurrentThreadId
0x180014681  mov     edx, 1
0x180014686  mov     rcx, rbx
0x180014689  mov     [rbx+60h], eax
0x18001468c  call    ?_ReadyToAcceptCommands@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJH@Z; CComTaskThread<CCscComTaskContext>::_ReadyToAcceptCommands(int)
0x180014691  mov     esi, eax
0x180014693  test    eax, eax
0x180014695  js      short loc_1800146AF
0x180014697  xor     edx, edx
0x180014699  mov     [rbx+30h], rdi
0x18001469d  mov     rcx, rbx
0x1800146a0  call    ?_DoCommand@?$CComTaskThread@VCCscComTaskContext@@@@AEAAJW4COMMANDS@1@@Z; CComTaskThread<CCscComTaskContext>::_DoCommand(CComTaskThread<CCscComTaskContext>::COMMANDS)
0x1800146a5  mov     esi, eax
0x1800146a7  mov     qword ptr [rbx+30h], 0
0x1800146af  lea     rcx, [rbx+8]; lpCriticalSection
0x1800146b3  mov     dword ptr [rbx+60h], 0
0x1800146ba  call    cs:__imp_LeaveCriticalSection
0x1800146c0  mov     eax, esi
0x1800146c2  mov     dword ptr [rdi+0Ch], 0
0x1800146c9  add     rsp, 28h
0x1800146cd  pop     rdi
0x1800146ce  pop     rsi
0x1800146cf  pop     rbp
0x1800146d0  pop     rbx
0x1800146d1  retn
```

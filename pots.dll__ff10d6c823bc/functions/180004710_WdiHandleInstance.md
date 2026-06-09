# WdiHandleInstance

- ea: `0x180004710`
- end: `0x180004848`
- name: `WdiHandleInstance`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x1800028c0`
- `0x180002974`
- `0x1800032c0`
- `0x180004710`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180004814`
- `ntdll!EtwEventUnregister` at `0x180004814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000479d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000482d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000479d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000482d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000475e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000478f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000481f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000475e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000478f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000481f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000476c`
- `wdi!WdiGetEvent` at `0x180004740`
- `wdi!WdiGetEvent` at `0x180004785`
- `wdi!WdiGetEvent` at `0x180004740`
- `wdi!WdiGetEvent` at `0x180004785`

## pseudocode

```c
__int64 __fastcall WdiHandleInstance(__int64 a1, int a2)
{
  struct _EVENT_RECORD *v2; // rbx
  unsigned int v3; // ebp
  unsigned int v5; // ebx
  HANDLE v6; // rax
  struct _EVENT_RECORD *v7; // rax
  HANDLE ProcessHeap; // rax
  __int64 v9; // rcx
  HANDLE v10; // rax
  SIZE_T dwBytes; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  if ( a2 == 2 )
  {
    LODWORD(dwBytes) = 0;
    if ( (int)WdiGetEvent(a1, 0, &dwBytes) >= 0 )
    {
      if ( (_DWORD)dwBytes
        && (v5 = dwBytes, v6 = GetProcessHeap(), v7 = (struct _EVENT_RECORD *)HeapAlloc(v6, 0, v5), (v2 = v7) != 0) )
      {
        if ( (int)WdiGetEvent(a1, v7, &dwBytes) >= 0 )
        {
          TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation(&dword_1800091A8);
          switch ( v2->EventHeader.EventDescriptor.Id )
          {
            case 0x29u:
              PoWdiLogDirtySleepTelemetry(a1, v2);
              break;
            case 2u:
              v3 = PoWdiLogTelemetryData(a1, v2);
              break;
            case 0x8Eu:
              PoWdiLogAbnormalResetTelemetry(a1, v2);
              break;
          }
        }
        else
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v2);
          v2 = 0;
        }
      }
      else
      {
        v2 = 0;
      }
    }
  }
  v9 = qword_1800091C8;
  dword_1800091A8 = 0;
  qword_1800091C8 = 0;
  EtwEventUnregister(v9);
  if ( v2 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x180004710  mov     rax, rsp
0x180004713  mov     [rax+8], rbx
0x180004717  mov     [rax+18h], rbp
0x18000471b  push    rsi
0x18000471c  push    rdi
0x18000471d  push    r15
0x18000471f  sub     rsp, 20h
0x180004723  xor     ebx, ebx
0x180004725  xor     ebp, ebp
0x180004727  mov     rdi, rcx
0x18000472a  lea     r15d, [rbx+2]
0x18000472e  cmp     edx, r15d
0x180004731  jnz     loc_1800047F8
0x180004737  lea     r8, [rax+10h]
0x18000473b  mov     [rax+10h], ebx
0x18000473e  xor     edx, edx
0x180004740  call    cs:__imp_WdiGetEvent
0x180004746  test    eax, eax
0x180004748  js      loc_1800047F8
0x18000474e  mov     eax, dword ptr [rsp+38h+dwBytes]
0x180004752  xor     esi, esi
0x180004754  test    eax, eax
0x180004756  jz      loc_1800047F5
0x18000475c  mov     ebx, eax
0x18000475e  call    cs:__imp_GetProcessHeap
0x180004764  mov     r8d, ebx; dwBytes
0x180004767  xor     edx, edx; dwFlags
0x180004769  mov     rcx, rax; hHeap
0x18000476c  call    cs:__imp_HeapAlloc
0x180004772  mov     rbx, rax
0x180004775  test    rax, rax
0x180004778  jz      short loc_1800047F5
0x18000477a  lea     r8, [rsp+38h+dwBytes]
0x18000477f  mov     rdx, rax
0x180004782  mov     rcx, rdi
0x180004785  call    cs:__imp_WdiGetEvent
0x18000478b  test    eax, eax
0x18000478d  jns     short loc_1800047A7
0x18000478f  call    cs:__imp_GetProcessHeap
0x180004795  mov     r8, rbx; lpMem
0x180004798  xor     edx, edx; dwFlags
0x18000479a  mov     rcx, rax; hHeap
0x18000479d  call    cs:__imp_HeapFree
0x1800047a3  xor     ebx, ebx
0x1800047a5  jmp     short loc_1800047F8
0x1800047a7  lea     rcx, dword_1800091A8
0x1800047ae  call    TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation
0x1800047b3  cmp     word ptr [rbx+28h], 29h ; ')'
0x1800047b8  jnz     short loc_1800047C7
0x1800047ba  mov     rdx, rbx
0x1800047bd  mov     rcx, rdi
0x1800047c0  call    PoWdiLogDirtySleepTelemetry
0x1800047c5  jmp     short loc_1800047F8
0x1800047c7  cmp     [rbx+28h], r15w
0x1800047cc  jnz     short loc_1800047DD
0x1800047ce  mov     rdx, rbx
0x1800047d1  mov     rcx, rdi
0x1800047d4  call    PoWdiLogTelemetryData
0x1800047d9  mov     ebp, eax
0x1800047db  jmp     short loc_1800047F8
0x1800047dd  mov     eax, 8Eh
0x1800047e2  cmp     [rbx+28h], ax
0x1800047e6  jnz     short loc_1800047F8
0x1800047e8  mov     rdx, rbx
0x1800047eb  mov     rcx, rdi
0x1800047ee  call    PoWdiLogAbnormalResetTelemetry
0x1800047f3  jmp     short loc_1800047F8
0x1800047f5  mov     rbx, rsi
0x1800047f8  mov     rcx, cs:qword_1800091C8
0x1800047ff  mov     cs:dword_1800091A8, 0
0x180004809  mov     cs:qword_1800091C8, 0
0x180004814  call    cs:__imp_EtwEventUnregister
0x18000481a  test    rbx, rbx
0x18000481d  jz      short loc_180004833
0x18000481f  call    cs:__imp_GetProcessHeap
0x180004825  mov     r8, rbx; lpMem
0x180004828  xor     edx, edx; dwFlags
0x18000482a  mov     rcx, rax; hHeap
0x18000482d  call    cs:__imp_HeapFree
0x180004833  mov     rbx, [rsp+38h+arg_0]
0x180004838  mov     eax, ebp
0x18000483a  mov     rbp, [rsp+38h+arg_10]
0x18000483f  add     rsp, 20h
0x180004843  pop     r15
0x180004845  pop     rdi
0x180004846  pop     rsi
0x180004847  retn
```

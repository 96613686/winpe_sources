# CfpDrainProtectedHandle

- ea: `0x180004804`
- end: `0x1800048b3`
- name: `CfpDrainProtectedHandle`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003d00`
- `0x180003d50`
- `0x1800049e0`

## callees

- `0x180004804`
- `0x18001cc74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000488c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000488c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004843`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000485e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000485e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004880`

## pseudocode

```c
signed __int32 __fastcall CfpDrainProtectedHandle(__int64 a1)
{
  unsigned __int64 i; // rbx
  signed __int64 v3; // rax
  unsigned __int64 v4; // rcx
  __int64 v5; // rtt
  void *v6; // rcx
  signed __int32 result; // eax
  void *v8; // rcx
  HANDLE ProcessHeap; // rax

  if ( (a1 & 1) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  for ( i = a1 & 0xFFFFFFFFFFFFFFFEuLL; ; WaitForSingleObject(*(HANDLE *)(i + 8), 0xFFFFFFFF) )
  {
    do
    {
      v3 = *(_QWORD *)(i + 16);
      v4 = v3 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (v3 & 1) == 0 )
        break;
      v5 = *(_QWORD *)(i + 16);
      if ( v5 == _InterlockedCompareExchange64((volatile signed __int64 *)(i + 16), v4, v3) )
        break;
    }
    while ( v4 );
    if ( !v4 )
      break;
  }
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)i, -1);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(i + 24), 0xFFFFFFFF);
  if ( result == 1 )
  {
    v8 = *(void **)(i + 8);
    if ( v8 )
      CloseHandle(v8);
    ProcessHeap = GetProcessHeap();
    return HeapFree(ProcessHeap, 0, (LPVOID)i);
  }
  return result;
}

```

## disassembly

```asm
0x180004804  push    rbx
0x180004806  sub     rsp, 20h
0x18000480a  mov     rbx, rcx
0x18000480d  test    cl, 1
0x180004810  jz      short loc_180004817
0x180004812  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004817  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18000481b  mov     rax, [rbx+10h]
0x18000481f  mov     rcx, rax
0x180004822  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004826  test    al, 1
0x180004828  jz      short loc_180004837
0x18000482a  lock cmpxchg [rbx+10h], rcx
0x180004830  jz      short loc_180004837
0x180004832  test    rcx, rcx
0x180004835  jnz     short loc_18000481B
0x180004837  test    rcx, rcx
0x18000483a  jz      short loc_180004851
0x18000483c  mov     rcx, [rbx+8]; hHandle
0x180004840  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004843  call    cs:__imp_WaitForSingleObject
0x18000484a  nop     dword ptr [rax+rax+00h]
0x18000484f  jmp     short loc_18000481B
0x180004851  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004855  xchg    rcx, [rbx]; hObject
0x180004858  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000485c  jz      short loc_18000486A
0x18000485e  call    cs:__imp_CloseHandle
0x180004865  nop     dword ptr [rax+rax+00h]
0x18000486a  or      eax, 0FFFFFFFFh
0x18000486d  lock xadd [rbx+18h], eax
0x180004872  cmp     eax, 1
0x180004875  jnz     short loc_1800048AC
0x180004877  mov     rcx, [rbx+8]; hObject
0x18000487b  test    rcx, rcx
0x18000487e  jz      short loc_18000488C
0x180004880  call    cs:__imp_CloseHandle
0x180004887  nop     dword ptr [rax+rax+00h]
0x18000488c  call    cs:__imp_GetProcessHeap
0x180004893  nop     dword ptr [rax+rax+00h]
0x180004898  mov     r8, rbx; lpMem
0x18000489b  xor     edx, edx; dwFlags
0x18000489d  mov     rcx, rax; hHeap
0x1800048a0  call    cs:__imp_HeapFree
0x1800048a7  nop     dword ptr [rax+rax+00h]
0x1800048ac  add     rsp, 20h
0x1800048b0  pop     rbx
0x1800048b1  retn
```

# RecordThreadTraceEvent(ThreadTraceEvent::Enum,ulong,int,PCChainManager *)

- ea: `0x180109a40`
- end: `0x180109aed`
- name: `?RecordThreadTraceEvent@@YAXW4Enum@ThreadTraceEvent@@KHPEAVPCChainManager@@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801095d0`

## callees

- `0x180109a40`
- `0x180109af4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109ade`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109ade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109aca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109aa5`

## pseudocode

```c
int __fastcall RecordThreadTraceEvent(int a1, int a2, int a3, __int64 a4)
{
  LPVOID v8; // rax
  volatile int v9; // ecx
  __int64 v10; // rdx
  char *v11; // rbx
  HANDLE ProcessHeap; // rax

  if ( _InterlockedCompareExchange(&dword_1805DBFBC, 1, 0) )
  {
    v8 = pvAddress;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x1800u);
    pvAddress = v8;
  }
  if ( v8 )
  {
    EnsureThreadTraceRegisteredWithWER();
    do
    {
      v9 = g_nCurrentThreadTraceIndex;
      v10 = (unsigned __int8)(g_nCurrentThreadTraceIndex + 1);
    }
    while ( v9 != _InterlockedCompareExchange(&g_nCurrentThreadTraceIndex, v10, g_nCurrentThreadTraceIndex) );
    v11 = (char *)pvAddress + 24 * v10;
    LODWORD(v8) = GetCurrentThreadId();
    *(_DWORD *)v11 = (_DWORD)v8;
    *((_DWORD *)v11 + 1) = a1;
    *((_DWORD *)v11 + 2) = a2;
    *((_DWORD *)v11 + 3) = a3;
    *((_QWORD *)v11 + 2) = a4;
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180109a40  push    rbp
0x180109a42  push    rsi
0x180109a43  push    rdi
0x180109a44  push    r14
0x180109a46  sub     rsp, 38h
0x180109a4a  mov     r14d, ecx
0x180109a4d  mov     rdi, r9
0x180109a50  mov     ecx, 1
0x180109a55  mov     esi, r8d
0x180109a58  mov     ebp, edx
0x180109a5a  xor     eax, eax
0x180109a5c  lock cmpxchg cs:dword_1805DBFBC, ecx
0x180109a64  jz      short loc_180109ACA
0x180109a66  mov     rax, cs:pvAddress
0x180109a6d  test    rax, rax
0x180109a70  jz      short loc_180109AC0
0x180109a72  mov     [rsp+58h+arg_0], rbx
0x180109a77  call    ?EnsureThreadTraceRegisteredWithWER@@YAXXZ; EnsureThreadTraceRegisteredWithWER(void)
0x180109a7c  mov     ecx, cs:?g_nCurrentThreadTraceIndex@@3JC; long volatile g_nCurrentThreadTraceIndex
0x180109a82  lea     eax, [rcx+1]
0x180109a85  movzx   edx, al
0x180109a88  mov     eax, ecx
0x180109a8a  lock cmpxchg cs:?g_nCurrentThreadTraceIndex@@3JC, edx; long volatile g_nCurrentThreadTraceIndex
0x180109a92  cmp     ecx, eax
0x180109a94  jnz     short loc_180109A7C
0x180109a96  mov     rax, cs:pvAddress
0x180109a9d  lea     rcx, [rdx+rdx*2]
0x180109aa1  lea     rbx, [rax+rcx*8]
0x180109aa5  call    cs:__imp_GetCurrentThreadId
0x180109aab  mov     [rbx], eax
0x180109aad  mov     [rbx+4], r14d
0x180109ab1  mov     [rbx+8], ebp
0x180109ab4  mov     [rbx+0Ch], esi
0x180109ab7  mov     [rbx+10h], rdi
0x180109abb  mov     rbx, [rsp+58h+arg_0]
0x180109ac0  add     rsp, 38h
0x180109ac4  pop     r14
0x180109ac6  pop     rdi
0x180109ac7  pop     rsi
0x180109ac8  pop     rbp
0x180109ac9  retn
0x180109aca  call    cs:__imp_GetProcessHeap
0x180109ad0  mov     edx, 8; dwFlags
0x180109ad5  mov     r8d, 1800h; dwBytes
0x180109adb  mov     rcx, rax; hHeap
0x180109ade  call    cs:__imp_HeapAlloc
0x180109ae4  mov     cs:pvAddress, rax
0x180109aeb  jmp     short loc_180109A6D
```

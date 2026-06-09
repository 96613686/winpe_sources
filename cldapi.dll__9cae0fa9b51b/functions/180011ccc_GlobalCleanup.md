# GlobalCleanup

- ea: `0x180011ccc`
- end: `0x180011ef2`
- name: `GlobalCleanup`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000261c`

## callees

- `0x180011ccc`
- `0x18001b45c`
- `0x18001b518`
- `0x18001b5bc`
- `0x18001c920`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011d55`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011d55`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011db5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011db5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011df7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011df7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011e29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011e29`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011d08`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011eab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011eab`

## pseudocode

```c
void GlobalCleanup()
{
  HANDLE ProcessHeap; // rax
  HANDLE v1; // rax

  while ( byte_18002A915 )
  {
    if ( _InterlockedIncrement(&dword_18002A910) == 1 )
    {
      if ( !byte_18002A915 )
      {
        _InterlockedAdd(&dword_18002A910, 0xFFFFFFFF);
        return;
      }
      if ( byte_18002A914 )
      {
        if ( byte_18002A930 )
        {
          TlgUnregisterAggregateProvider();
          byte_18002A930 = 0;
        }
        if ( byte_18002A938 )
        {
          RtlAcquireSRWLockExclusive(&qword_18002A940);
          if ( lpMem )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, lpMem);
            lpMem = 0;
            dword_18002A948 = 0;
          }
          qword_18002A960 = 0;
          dword_18002A958 = 0;
          byte_18002A938 = 0;
          RtlReleaseSRWLockExclusive(&qword_18002A940);
        }
        if ( byte_18002A9B0 )
          TlmiUninitializeRunawayHydrationDetection();
        if ( byte_18002AA58 )
          TlmiUninitializeHydrationPerformanceTracking();
        if ( byte_18002A968 )
          TlmiUninitializeFirstRunExpStatus();
        if ( String2.Buffer )
        {
          v1 = GetProcessHeap();
          HeapFree(v1, 0, String2.Buffer);
          String2.Buffer = 0;
        }
        DeleteCriticalSection(&_G);
        dword_18002ABE8 = 0;
        if ( hPort != (HANDLE)-1LL )
        {
          CloseHandle(hPort);
          hPort = (HANDLE)-1LL;
        }
        if ( *(&hPort + 1) != (HANDLE)-1LL )
        {
          CloseHandle(*(&hPort + 1));
          *(&hPort + 1) = (HANDLE)-1LL;
        }
        if ( CompletionPort )
        {
          CloseHandle(CompletionPort);
          CompletionPort = 0;
        }
        if ( qword_18002AD00 != (HANDLE)-1LL )
        {
          CloseHandle(qword_18002AD00);
          qword_18002AD00 = (HANDLE)-1LL;
        }
        byte_18002A914 = 0;
      }
      byte_18002A915 = 0;
      _InterlockedAdd(&dword_18002A910, 0xFFFFFFFF);
    }
    else
    {
      _InterlockedAdd(&dword_18002A910, 0xFFFFFFFF);
      Sleep(0xAu);
    }
  }
}

```

## disassembly

```asm
0x180011ccc  mov     [rsp+arg_0], rbx
0x180011cd1  push    rdi
0x180011cd2  sub     rsp, 20h
0x180011cd6  xor     ebx, ebx
0x180011cd8  cmp     cs:byte_18002A915, bl
0x180011cde  jz      loc_180011EE6
0x180011ce4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011ce8  mov     eax, 1
0x180011ced  lock xadd cs:dword_18002A910, eax
0x180011cf5  inc     eax
0x180011cf7  cmp     eax, 1
0x180011cfa  jz      short loc_180011D19
0x180011cfc  lock add cs:dword_18002A910, edi
0x180011d03  mov     ecx, 0Ah; dwMilliseconds
0x180011d08  call    cs:__imp_Sleep
0x180011d0f  nop     dword ptr [rax+rax+00h]
0x180011d14  jmp     loc_180011ED1
0x180011d19  cmp     cs:byte_18002A915, bl
0x180011d1f  jz      loc_180011EDF
0x180011d25  cmp     cs:byte_18002A914, bl
0x180011d2b  jz      loc_180011EC4
0x180011d31  cmp     cs:byte_18002A930, bl
0x180011d37  jz      short loc_180011D44
0x180011d39  call    TlgUnregisterAggregateProvider
0x180011d3e  mov     cs:byte_18002A930, bl
0x180011d44  mov     al, cs:byte_18002A938
0x180011d4a  test    al, al
0x180011d4c  jz      short loc_180011DC1
0x180011d4e  lea     rcx, qword_18002A940
0x180011d55  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011d5c  nop     dword ptr [rax+rax+00h]
0x180011d61  cmp     cs:lpMem, rbx
0x180011d68  jz      short loc_180011D9B
0x180011d6a  call    cs:__imp_GetProcessHeap
0x180011d71  nop     dword ptr [rax+rax+00h]
0x180011d76  mov     r8, cs:lpMem; lpMem
0x180011d7d  xor     edx, edx; dwFlags
0x180011d7f  mov     rcx, rax; hHeap
0x180011d82  call    cs:__imp_HeapFree
0x180011d89  nop     dword ptr [rax+rax+00h]
0x180011d8e  mov     cs:lpMem, rbx
0x180011d95  mov     cs:dword_18002A948, ebx
0x180011d9b  mov     cs:qword_18002A960, rbx
0x180011da2  lea     rcx, qword_18002A940
0x180011da9  mov     cs:dword_18002A958, ebx
0x180011daf  mov     cs:byte_18002A938, bl
0x180011db5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011dbc  nop     dword ptr [rax+rax+00h]
0x180011dc1  mov     al, cs:byte_18002A9B0
0x180011dc7  test    al, al
0x180011dc9  jz      short loc_180011DD0
0x180011dcb  call    TlmiUninitializeRunawayHydrationDetection
0x180011dd0  mov     al, cs:byte_18002AA58
0x180011dd6  test    al, al
0x180011dd8  jz      short loc_180011DDF
0x180011dda  call    TlmiUninitializeHydrationPerformanceTracking
0x180011ddf  mov     al, cs:byte_18002A968
0x180011de5  test    al, al
0x180011de7  jz      short loc_180011DEE
0x180011de9  call    TlmiUninitializeFirstRunExpStatus
0x180011dee  cmp     cs:String2.Buffer, rbx
0x180011df5  jz      short loc_180011E22
0x180011df7  call    cs:__imp_GetProcessHeap
0x180011dfe  nop     dword ptr [rax+rax+00h]
0x180011e03  mov     r8, cs:String2.Buffer; lpMem
0x180011e0a  xor     edx, edx; dwFlags
0x180011e0c  mov     rcx, rax; hHeap
0x180011e0f  call    cs:__imp_HeapFree
0x180011e16  nop     dword ptr [rax+rax+00h]
0x180011e1b  mov     cs:String2.Buffer, rbx
0x180011e22  lea     rcx, __G; lpCriticalSection
0x180011e29  call    cs:__imp_DeleteCriticalSection
0x180011e30  nop     dword ptr [rax+rax+00h]
0x180011e35  mov     rcx, qword ptr cs:hPort; hObject
0x180011e3c  mov     cs:dword_18002ABE8, ebx
0x180011e42  cmp     rcx, rdi
0x180011e45  jz      short loc_180011E5A
0x180011e47  call    cs:__imp_CloseHandle
0x180011e4e  nop     dword ptr [rax+rax+00h]
0x180011e53  mov     qword ptr cs:hPort, rdi
0x180011e5a  mov     rcx, qword ptr cs:hPort+8; hObject
0x180011e61  cmp     rcx, rdi
0x180011e64  jz      short loc_180011E79
0x180011e66  call    cs:__imp_CloseHandle
0x180011e6d  nop     dword ptr [rax+rax+00h]
0x180011e72  mov     qword ptr cs:hPort+8, rdi
0x180011e79  mov     rcx, cs:CompletionPort; hObject
0x180011e80  test    rcx, rcx
0x180011e83  jz      short loc_180011E98
0x180011e85  call    cs:__imp_CloseHandle
0x180011e8c  nop     dword ptr [rax+rax+00h]
0x180011e91  mov     cs:CompletionPort, rbx
0x180011e98  mov     rax, cs:qword_18002AD00
0x180011e9f  cmp     rax, rdi
0x180011ea2  jz      short loc_180011EBE
0x180011ea4  mov     rcx, cs:qword_18002AD00; hObject
0x180011eab  call    cs:__imp_CloseHandle
0x180011eb2  nop     dword ptr [rax+rax+00h]
0x180011eb7  mov     cs:qword_18002AD00, rdi
0x180011ebe  mov     cs:byte_18002A914, bl
0x180011ec4  mov     cs:byte_18002A915, bl
0x180011eca  lock add cs:dword_18002A910, edi
0x180011ed1  cmp     cs:byte_18002A915, bl
0x180011ed7  jnz     loc_180011CE8
0x180011edd  jmp     short loc_180011EE6
0x180011edf  lock add cs:dword_18002A910, edi
0x180011ee6  mov     rbx, [rsp+28h+arg_0]
0x180011eeb  add     rsp, 20h
0x180011eef  pop     rdi
0x180011ef0  retn
```

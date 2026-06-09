# Query_AllocateQueryBlob

- ea: `0x180003668`
- end: `0x18000373d`
- name: `Query_AllocateQueryBlob`
- size: `213`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180001df0`
- `0x180003240`
- `0x18003f058`
- `0x18005b5ec`

## callees

- `0x180003668`

## import_xrefs

- `DNSAPI!AddRefQueryBlobEx` at `0x180003717`
- `DNSAPI!AddRefQueryBlobEx` at `0x180003717`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003692`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003692`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800036a7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800036a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036c7`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800036b4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800036c1`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800036b4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800036c1`

## pseudocode

```c
char *__fastcall Query_AllocateQueryBlob(unsigned int a1)
{
  HANDLE ProcessHeap; // rax
  char *v3; // rax
  char *v4; // rbx

  ProcessHeap = g_hProcessHeap;
  if ( !g_hProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  v3 = (char *)HeapAlloc(ProcessHeap, 8u, 0xDC8u);
  v4 = v3;
  if ( v3 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 184));
    GetSystemTimePreciseAsFileTime(v4 + 3436);
    GetSystemTimePreciseAsFileTime(v4 + 3444);
    *((_DWORD *)v4 + 86) = GetCurrentProcessId();
    *((_QWORD *)v4 + 16) = v4 + 120;
    *((_QWORD *)v4 + 15) = v4 + 120;
    *((_QWORD *)v4 + 18) = v4 + 136;
    *((_QWORD *)v4 + 17) = v4 + 136;
    *((_QWORD *)v4 + 20) = v4 + 152;
    *((_QWORD *)v4 + 19) = v4 + 152;
    *((_DWORD *)v4 + 858) = 0;
    AddRefQueryBlobEx(v4, "Query_AllocateQueryBlob", 101, a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180003668  mov     [rsp+arg_0], rbx
0x18000366d  push    rdi
0x18000366e  sub     rsp, 20h
0x180003672  mov     rax, cs:g_hProcessHeap
0x180003679  mov     edi, ecx
0x18000367b  test    rax, rax
0x18000367e  jz      loc_18000372B
0x180003684  mov     edx, 8; dwFlags
0x180003689  mov     r8d, 0DC8h; dwBytes
0x18000368f  mov     rcx, rax; hHeap
0x180003692  call    cs:__imp_HeapAlloc
0x180003698  mov     rbx, rax
0x18000369b  test    rax, rax
0x18000369e  jz      short loc_18000371D
0x1800036a0  lea     rcx, [rax+0B8h]; lpCriticalSection
0x1800036a7  call    cs:__imp_InitializeCriticalSection
0x1800036ad  lea     rcx, [rbx+0D6Ch]
0x1800036b4  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800036ba  lea     rcx, [rbx+0D74h]
0x1800036c1  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800036c7  call    cs:__imp_GetCurrentProcessId
0x1800036cd  mov     [rbx+158h], eax
0x1800036d3  lea     rcx, [rbx+78h]
0x1800036d7  mov     [rcx+8], rcx
0x1800036db  mov     r9d, edi
0x1800036de  mov     [rcx], rcx
0x1800036e1  lea     rax, [rbx+88h]
0x1800036e8  mov     [rax+8], rax
0x1800036ec  lea     rdx, aQueryAllocateq; "Query_AllocateQueryBlob"
0x1800036f3  mov     [rax], rax
0x1800036f6  mov     r8d, 65h ; 'e'
0x1800036fc  lea     rax, [rbx+98h]
0x180003703  mov     rcx, rbx
0x180003706  mov     [rax+8], rax
0x18000370a  mov     [rax], rax
0x18000370d  mov     dword ptr [rbx+0D68h], 0
0x180003717  call    cs:__imp_AddRefQueryBlobEx
0x18000371d  mov     rax, rbx
0x180003720  mov     rbx, [rsp+28h+arg_0]
0x180003725  add     rsp, 20h
0x180003729  pop     rdi
0x18000372a  retn
0x18000372b  call    cs:__imp_GetProcessHeap
0x180003731  mov     cs:g_hProcessHeap, rax
0x180003738  jmp     loc_180003684
```

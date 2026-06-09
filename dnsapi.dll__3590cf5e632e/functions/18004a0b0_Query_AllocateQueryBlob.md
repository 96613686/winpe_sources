# Query_AllocateQueryBlob

- ea: `0x18004a0b0`
- end: `0x18004a205`
- name: `Query_AllocateQueryBlob`
- size: `341`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048f18`
- `0x1800498e4`
- `0x180049e58`
- `0x180078720`
- `0x180084da0`
- `0x180092f48`

## callees

- `0x18004a0b0`
- `0x180083954`
- `0x180084c4c`
- `0x1800de6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a0fa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a0fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a12c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a12c`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004a10d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004a120`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004a10d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004a120`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a0db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a0db`

## pseudocode

```c
__int64 __fastcall Query_AllocateQueryBlob(int a1)
{
  HANDLE ProcessHeap; // rax
  __int64 v2; // rdi
  char *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentProcessId; // eax
  int v6; // r8d
  bool v7; // zf
  signed __int32 v8; // ecx
  __int64 v10; // rcx
  LPCSTR retaddr; // [rsp+48h] [rbp+0h]

  ProcessHeap = g_hProcessHeap;
  v2 = a1;
  if ( !g_hProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  v3 = (char *)HeapAlloc(ProcessHeap, 8u, 0xDC8u);
  v4 = (__int64)v3;
  if ( v3 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 184));
    GetSystemTimePreciseAsFileTime(v4 + 3436);
    GetSystemTimePreciseAsFileTime(v4 + 3444);
    CurrentProcessId = GetCurrentProcessId();
    v7 = g_fVelocitySuppressInternalExports == 0;
    *(_DWORD *)(v4 + 344) = CurrentProcessId;
    *(_QWORD *)(v4 + 128) = v4 + 120;
    *(_QWORD *)(v4 + 120) = v4 + 120;
    *(_QWORD *)(v4 + 144) = v4 + 136;
    *(_QWORD *)(v4 + 136) = v4 + 136;
    *(_QWORD *)(v4 + 160) = v4 + 152;
    *(_QWORD *)(v4 + 152) = v4 + 152;
    *(_DWORD *)(v4 + 3432) = 0;
    if ( v7 || g_DnsIsCache || (unsigned int)Dns_IsCallerDns(retaddr) )
    {
      v8 = _InterlockedIncrement((volatile signed __int32 *)v4);
      _InterlockedAdd16((volatile signed __int16 *)(v4 + 2 * v2 + 4), 1u);
      if ( (BYTE3(xmmword_1801119E0) & 4) != 0 )
        WPP_SF_lsdqd(v8, 14, v6, v2, (__int64)"Query_AllocateQueryBlob", 101, v4, v8);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004a0b0  mov     [rsp+arg_0], rbx
0x18004a0b5  push    rdi
0x18004a0b6  sub     rsp, 40h
0x18004a0ba  mov     rax, cs:g_hProcessHeap
0x18004a0c1  movsxd  rdi, ecx
0x18004a0c4  test    rax, rax
0x18004a0c7  jz      loc_18004A1A3
0x18004a0cd  mov     edx, 8; dwFlags
0x18004a0d2  mov     r8d, 0DC8h; dwBytes
0x18004a0d8  mov     rcx, rax; hHeap
0x18004a0db  call    cs:__imp_HeapAlloc
0x18004a0e2  nop     dword ptr [rax+rax+00h]
0x18004a0e7  mov     rbx, rax
0x18004a0ea  test    rax, rax
0x18004a0ed  jz      loc_18004A194
0x18004a0f3  lea     rcx, [rax+0B8h]; lpCriticalSection
0x18004a0fa  call    cs:__imp_InitializeCriticalSection
0x18004a101  nop     dword ptr [rax+rax+00h]
0x18004a106  lea     rcx, [rbx+0D6Ch]
0x18004a10d  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18004a114  nop     dword ptr [rax+rax+00h]
0x18004a119  lea     rcx, [rbx+0D74h]
0x18004a120  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18004a127  nop     dword ptr [rax+rax+00h]
0x18004a12c  call    cs:__imp_GetCurrentProcessId
0x18004a133  nop     dword ptr [rax+rax+00h]
0x18004a138  cmp     cs:g_fVelocitySuppressInternalExports, 0
0x18004a13f  lea     rcx, [rbx+78h]
0x18004a143  mov     [rbx+158h], eax
0x18004a149  lea     rax, [rbx+88h]
0x18004a150  mov     [rcx+8], rcx
0x18004a154  mov     [rcx], rcx
0x18004a157  mov     [rax+8], rax
0x18004a15b  mov     [rax], rax
0x18004a15e  lea     rax, [rbx+98h]
0x18004a165  mov     [rax+8], rax
0x18004a169  mov     [rax], rax
0x18004a16c  mov     dword ptr [rbx+0D68h], 0
0x18004a176  jnz     short loc_18004A1BB
0x18004a178  mov     edx, 1
0x18004a17d  mov     ecx, edx
0x18004a17f  lock xadd [rbx], ecx
0x18004a183  add     ecx, edx
0x18004a185  lock add [rbx+rdi*2+4], dx
0x18004a18b  test    byte ptr cs:xmmword_1801119E0+3, 4
0x18004a192  jnz     short loc_18004A1D9
0x18004a194  mov     rax, rbx
0x18004a197  mov     rbx, [rsp+48h+arg_0]
0x18004a19c  add     rsp, 40h
0x18004a1a0  pop     rdi
0x18004a1a1  retn
0x18004a1a3  call    cs:__imp_GetProcessHeap
0x18004a1aa  nop     dword ptr [rax+rax+00h]
0x18004a1af  mov     cs:g_hProcessHeap, rax
0x18004a1b6  jmp     loc_18004A0CD
0x18004a1bb  cmp     cs:g_DnsIsCache, 0
0x18004a1c2  jnz     short loc_18004A178
0x18004a1c4  mov     rcx, [rsp+48h]; lpModuleName
0x18004a1c9  call    Dns_IsCallerDns
0x18004a1ce  test    eax, eax
0x18004a1d0  jnz     short loc_18004A178
0x18004a1d2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a1d7  jmp     short loc_18004A194
0x18004a1d9  mov     [rsp+48h+var_10], ecx
0x18004a1dd  lea     rax, aQueryAllocateq; "Query_AllocateQueryBlob"
0x18004a1e4  mov     [rsp+48h+var_18], rbx
0x18004a1e9  mov     edx, 0Eh
0x18004a1ee  mov     [rsp+48h+var_20], 65h ; 'e'
0x18004a1f6  mov     r9d, edi
0x18004a1f9  mov     [rsp+48h+var_28], rax
0x18004a1fe  call    WPP_SF_lsdqd
0x18004a203  jmp     short loc_18004A194
```

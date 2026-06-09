# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800102c0`
- end: `0x180010456`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `406`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000feb0`
- `0x180010130`
- `0x18001020c`
- `0x1800289d8`

## callees

- `0x1800102c0`
- `0x18002e7a6`
- `0x18002e850`
- `0x18002f7db`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010410`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010427`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010410`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010427`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800103c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800103c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010347`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010347`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001044b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001044b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010312`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001043d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010312`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001043d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010323`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800103a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800103da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800103a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800103da`

## string_xrefs

- `0x180010340`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v4; // rdx
  DWORD LastError; // r15d
  SIZE_T v6; // r14
  HANDLE ProcessHeap; // rsi
  char *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v11; // rbp
  size_t v12; // rsi
  void *v13; // rbp
  HANDLE v15; // rax

  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this < v4 )
    return 1;
  if ( a2 < 2 * v4 )
    a2 = 2 * v4;
  if ( v4 >= a2 )
    return 1;
  LastError = GetLastError();
  v6 = (a2 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 0, v6);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
      ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
      : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v8);
  }
  if ( v8 )
  {
    v11 = *(_QWORD *)this;
    v12 = *((_QWORD *)this + 1) - *(_QWORD *)this;
    if ( v12 )
    {
      if ( !v11 || v6 < v12 )
      {
        memset_0(v8, 0, v6);
        if ( v11 )
        {
          if ( v6 >= v12 )
            goto LABEL_13;
          *(_DWORD *)_o__errno() = 34;
        }
        else
        {
          *(_DWORD *)_o__errno() = 22;
        }
        invalid_parameter_noinfo();
        goto LABEL_13;
      }
      memcpy_0(v8, *(const void **)this, v12);
    }
LABEL_13:
    v13 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v8;
    if ( v13 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v13);
    }
    *(_QWORD *)this = v8;
    *((_QWORD *)this + 1) = &v8[v12];
    *((_QWORD *)this + 2) = &v8[v6];
    SetLastError(LastError);
    return 1;
  }
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800102c0  push    rbx
0x1800102c2  push    rbp
0x1800102c3  push    rsi
0x1800102c4  push    rdi
0x1800102c5  push    r14
0x1800102c7  push    r15
0x1800102c9  sub     rsp, 28h
0x1800102cd  mov     rdi, rdx
0x1800102d0  mov     rbx, rcx
0x1800102d3  mov     rdx, [rcx+10h]
0x1800102d7  sub     rdx, [rcx]
0x1800102da  mov     rax, [rcx+8]
0x1800102de  sub     rax, [rcx]
0x1800102e1  add     rax, rdi
0x1800102e4  cmp     rax, rdx
0x1800102e7  jb      loc_1800103AF
0x1800102ed  lea     rax, [rdx+rdx]
0x1800102f1  cmp     rdi, rax
0x1800102f4  cmovb   rdi, rax
0x1800102f8  cmp     rdx, rdi
0x1800102fb  jnb     loc_1800103AF
0x180010301  call    cs:__imp_GetLastError
0x180010307  mov     r15d, eax
0x18001030a  and     rdi, 0FFFFFFFFFFFFFFC0h
0x18001030e  lea     r14, [rdi+40h]
0x180010312  call    cs:__imp_GetProcessHeap
0x180010318  mov     rsi, rax
0x18001031b  mov     r8, r14; dwBytes
0x18001031e  xor     edx, edx; dwFlags
0x180010320  mov     rcx, rax; hHeap
0x180010323  call    cs:__imp_HeapAlloc
0x180010329  mov     rdi, rax
0x18001032c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010333  test    rax, rax
0x180010336  jnz     short loc_180010365
0x180010338  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001033e  jnz     short loc_180010371
0x180010340  lea     rcx, ModuleName; "ntdll.dll"
0x180010347  call    cs:__imp_GetModuleHandleW
0x18001034d  test    rax, rax
0x180010350  jnz     short loc_1800103BE
0x180010352  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010359  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010360  test    rax, rax
0x180010363  jz      short loc_180010371
0x180010365  mov     rdx, rdi
0x180010368  mov     rcx, rsi
0x18001036b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010370  nop
0x180010371  test    rdi, rdi
0x180010374  jz      short loc_1800103D7
0x180010376  mov     rbp, [rbx]
0x180010379  mov     rsi, [rbx+8]
0x18001037d  sub     rsi, rbp
0x180010380  jnz     short loc_1800103E4
0x180010382  mov     rbp, [rbx+18h]
0x180010386  mov     [rbx+18h], rdi
0x18001038a  test    rbp, rbp
0x18001038d  jnz     loc_18001043D
0x180010393  mov     [rbx], rdi
0x180010396  lea     rax, [rsi+rdi]
0x18001039a  mov     [rbx+8], rax
0x18001039e  lea     rax, [r14+rdi]
0x1800103a2  mov     [rbx+10h], rax
0x1800103a6  mov     ecx, r15d; dwErrCode
0x1800103a9  call    cs:__imp_SetLastError
0x1800103af  mov     al, 1
0x1800103b1  add     rsp, 28h
0x1800103b5  pop     r15
0x1800103b7  pop     r14
0x1800103b9  pop     rdi
0x1800103ba  pop     rsi
0x1800103bb  pop     rbp
0x1800103bc  pop     rbx
0x1800103bd  retn
0x1800103be  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800103c5  mov     rcx, rax; hModule
0x1800103c8  call    cs:__imp_GetProcAddress
0x1800103ce  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800103d5  jmp     short loc_180010359
0x1800103d7  mov     ecx, r15d; dwErrCode
0x1800103da  call    cs:__imp_SetLastError
0x1800103e0  xor     al, al
0x1800103e2  jmp     short loc_1800103B1
0x1800103e4  test    rbp, rbp
0x1800103e7  jz      short loc_1800103FE
0x1800103e9  cmp     r14, rsi
0x1800103ec  jb      short loc_1800103FE
0x1800103ee  mov     r8, rsi; Size
0x1800103f1  mov     rdx, rbp; Src
0x1800103f4  mov     rcx, rdi; void *
0x1800103f7  call    memcpy_0
0x1800103fc  jmp     short loc_180010382
0x1800103fe  mov     r8, r14; Size
0x180010401  xor     edx, edx; Val
0x180010403  mov     rcx, rdi; void *
0x180010406  call    memset_0
0x18001040b  test    rbp, rbp
0x18001040e  jnz     short loc_18001041E
0x180010410  call    cs:__imp__o__errno
0x180010416  mov     dword ptr [rax], 16h
0x18001041c  jmp     short loc_180010433
0x18001041e  cmp     r14, rsi
0x180010421  jnb     loc_180010382
0x180010427  call    cs:__imp__o__errno
0x18001042d  mov     dword ptr [rax], 22h ; '"'
0x180010433  call    _invalid_parameter_noinfo
0x180010438  jmp     loc_180010382
0x18001043d  call    cs:__imp_GetProcessHeap
0x180010443  mov     rcx, rax; hHeap
0x180010446  mov     r8, rbp; lpMem
0x180010449  xor     edx, edx; dwFlags
0x18001044b  call    cs:__imp_HeapFree
0x180010451  jmp     loc_180010393
```

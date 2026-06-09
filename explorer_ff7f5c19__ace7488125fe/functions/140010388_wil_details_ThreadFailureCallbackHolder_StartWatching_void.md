# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x140010388`
- end: `0x14001051a`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `402`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `11`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f910`
- `0x1400102b4`
- `0x140010364`
- `0x14008ba00`
- `0x1400951e4`
- `0x1400b0950`
- `0x1400f9944`
- `0x14012c3c4`
- `0x14012c538`
- `0x14019d490`
- `0x1401b3fcc`

## callees

- `0x140010388`
- `0x140078ba8`
- `0x14010ed90`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400104fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400104fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010476`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010476`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001044c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001044c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010434`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400103b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001040b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400103b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001040b`

## string_xrefs

- `0x14001046f`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  unsigned __int64 CurrentThreadId; // r15
  unsigned __int64 v4; // rbp
  __int64 i; // rcx
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // r14
  char *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = (CurrentThreadId >> 2) % 0xA;
    for ( i = *(_QWORD *)(v2 + 8 * v4); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v6 = (_QWORD *)(i + 16);
        goto LABEL_8;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
      *(_DWORD *)v8 = CurrentThreadId;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      v6 = v8 + 16;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v11 = *(_QWORD *)(v2 + 8 * v4);
        *((_QWORD *)v8 + 1) = v11;
      }
      while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v4), (signed __int64)v8, v11) );
    }
    else
    {
      v6 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = *v6;
      *v6 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x140010388  push    rbx
0x14001038a  push    rbp
0x14001038b  push    rsi
0x14001038c  push    rdi
0x14001038d  push    r14
0x14001038f  push    r15
0x140010391  sub     rsp, 0C8h
0x140010398  mov     rbx, rcx
0x14001039b  cmp     dword ptr [rcx+18h], 0
0x14001039f  jnz     loc_1400104D4
0x1400103a5  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400103ac  test    rsi, rsi
0x1400103af  jz      short loc_14001042B
0x1400103b1  call    cs:__imp_GetCurrentThreadId
0x1400103b8  nop     dword ptr [rax+rax+00h]
0x1400103bd  mov     r15d, eax
0x1400103c0  mov     ebp, eax
0x1400103c2  shr     rbp, 2
0x1400103c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400103d0  mul     rbp
0x1400103d3  shr     rdx, 3
0x1400103d7  lea     rcx, [rdx+rdx*4]
0x1400103db  add     rcx, rcx
0x1400103de  sub     rbp, rcx
0x1400103e1  mov     rcx, [rsi+rbp*8]
0x1400103e5  test    rcx, rcx
0x1400103e8  jz      short loc_140010434
0x1400103ea  cmp     [rcx], r15d
0x1400103ed  jz      short loc_1400103F5
0x1400103ef  mov     rcx, [rcx+8]
0x1400103f3  jmp     short loc_1400103E5
0x1400103f5  add     rcx, 10h
0x1400103f9  mov     [rbx], rcx
0x1400103fc  test    rcx, rcx
0x1400103ff  jz      short loc_14001041A
0x140010401  mov     rax, [rcx]
0x140010404  mov     [rbx+10h], rax
0x140010408  mov     [rcx], rbx
0x14001040b  call    cs:__imp_GetCurrentThreadId
0x140010412  nop     dword ptr [rax+rax+00h]
0x140010417  mov     [rbx+18h], eax
0x14001041a  add     rsp, 0C8h
0x140010421  pop     r15
0x140010423  pop     r14
0x140010425  pop     rdi
0x140010426  pop     rsi
0x140010427  pop     rbp
0x140010428  pop     rbx
0x140010429  retn
0x14001042b  mov     qword ptr [rcx], 0
0x140010432  jmp     short loc_14001041A
0x140010434  call    cs:__imp_GetProcessHeap
0x14001043b  nop     dword ptr [rax+rax+00h]
0x140010440  mov     r14, rax
0x140010443  xor     edx, edx; dwFlags
0x140010445  lea     r8d, [rdx+18h]; dwBytes
0x140010449  mov     rcx, rax; hHeap
0x14001044c  call    cs:__imp_HeapAlloc
0x140010453  nop     dword ptr [rax+rax+00h]
0x140010458  mov     rdi, rax
0x14001045b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140010462  test    rax, rax
0x140010465  jnz     short loc_14001049A
0x140010467  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14001046d  jnz     short loc_1400104A6
0x14001046f  lea     rcx, ModuleName; "ntdll.dll"
0x140010476  call    cs:__imp_GetModuleHandleW
0x14001047d  nop     dword ptr [rax+rax+00h]
0x140010482  test    rax, rax
0x140010485  jnz     short loc_1400104F1
0x140010487  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14001048e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140010495  test    rax, rax
0x140010498  jz      short loc_1400104A6
0x14001049a  mov     rdx, rdi
0x14001049d  mov     rcx, r14
0x1400104a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104a5  nop
0x1400104a6  test    rdi, rdi
0x1400104a9  jz      short loc_140010513
0x1400104ab  mov     [rdi], r15d
0x1400104ae  xor     eax, eax
0x1400104b0  mov     [rdi+4], eax
0x1400104b3  mov     [rdi+8], rax
0x1400104b7  lea     rcx, [rdi+10h]
0x1400104bb  mov     [rcx], rax
0x1400104be  mov     rax, [rsi+rbp*8]
0x1400104c2  mov     [rdi+8], rax
0x1400104c6  lock cmpxchg [rsi+rbp*8], rdi
0x1400104cc  jz      loc_1400103F9
0x1400104d2  jmp     short loc_1400104BE
0x1400104d4  xor     edx, edx; Val
0x1400104d6  mov     r8d, 98h; Size
0x1400104dc  lea     rcx, [rsp+0F8h+var_D8]; void *
0x1400104e1  call    memset_0
0x1400104e6  lea     rcx, [rsp+0F8h+var_D8]; this
0x1400104eb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400104f1  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400104f8  mov     rcx, rax; hModule
0x1400104fb  call    cs:__imp_GetProcAddress
0x140010502  nop     dword ptr [rax+rax+00h]
0x140010507  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14001050e  jmp     loc_14001048E
0x140010513  xor     ecx, ecx
0x140010515  jmp     loc_1400103F9
```

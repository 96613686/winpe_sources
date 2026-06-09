# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180013a80`
- end: `0x180013bf1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009690`
- `0x180012fec`
- `0x180013bf8`
- `0x180030b10`
- `0x1800336c8`
- `0x180033954`
- `0x180045674`
- `0x18004d8f8`

## callees

- `0x180013a80`
- `0x1800235cc`
- `0x18003b310`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ba6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ba6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013b91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013b91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013afe`

## string_xrefs

- `0x180013b8a`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rdi
  unsigned __int64 CurrentThreadId; // rsi
  unsigned __int64 v4; // r15
  __int64 i; // rcx
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // r14
  FARPROC ProcAddress; // rax
  const struct wil::FailureInfo *v10; // rdx
  HMODULE ModuleHandleW; // rax
  signed __int64 v12; // rax
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v10);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
    for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v6 = (_QWORD *)(i + 16);
        goto LABEL_7;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
    ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
    if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
      || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
      && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
        ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
        : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                    `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
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
        v12 = *(_QWORD *)(v4 + v2);
        *((_QWORD *)v8 + 1) = v12;
      }
      while ( v12 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v8, v12) );
    }
    else
    {
      v6 = 0;
    }
LABEL_7:
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
0x180013a80  push    rbx
0x180013a82  push    rbp
0x180013a83  push    rsi
0x180013a84  push    rdi
0x180013a85  push    r14
0x180013a87  push    r15
0x180013a89  sub     rsp, 0C8h
0x180013a90  mov     rbx, rcx
0x180013a93  cmp     dword ptr [rcx+18h], 0
0x180013a97  jnz     loc_180013B64
0x180013a9d  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180013aa4  test    rdi, rdi
0x180013aa7  jz      short loc_180013B1D
0x180013aa9  call    cs:__imp_GetCurrentThreadId
0x180013aaf  mov     esi, eax
0x180013ab1  mov     r8d, eax
0x180013ab4  shr     r8, 2
0x180013ab8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013ac2  mul     r8
0x180013ac5  shr     rdx, 3
0x180013ac9  lea     rcx, [rdx+rdx*4]
0x180013acd  add     rcx, rcx
0x180013ad0  sub     r8, rcx
0x180013ad3  lea     r15, ds:0[r8*8]
0x180013adb  mov     rcx, [r15+rdi]
0x180013adf  test    rcx, rcx
0x180013ae2  jz      short loc_180013B24
0x180013ae4  cmp     [rcx], esi
0x180013ae6  jnz     short loc_180013B17
0x180013ae8  add     rcx, 10h
0x180013aec  mov     [rbx], rcx
0x180013aef  test    rcx, rcx
0x180013af2  jz      short loc_180013B07
0x180013af4  mov     rax, [rcx]
0x180013af7  mov     [rbx+10h], rax
0x180013afb  mov     [rcx], rbx
0x180013afe  call    cs:__imp_GetCurrentThreadId
0x180013b04  mov     [rbx+18h], eax
0x180013b07  add     rsp, 0C8h
0x180013b0e  pop     r15
0x180013b10  pop     r14
0x180013b12  pop     rdi
0x180013b13  pop     rsi
0x180013b14  pop     rbp
0x180013b15  pop     rbx
0x180013b16  retn
0x180013b17  mov     rcx, [rcx+8]
0x180013b1b  jmp     short loc_180013ADF
0x180013b1d  xor     eax, eax
0x180013b1f  mov     [rcx], rax
0x180013b22  jmp     short loc_180013B07
0x180013b24  call    cs:__imp_GetProcessHeap
0x180013b2a  mov     rbp, rax
0x180013b2d  xor     edx, edx; dwFlags
0x180013b2f  mov     r8d, 18h; dwBytes
0x180013b35  mov     rcx, rax; hHeap
0x180013b38  call    cs:__imp_HeapAlloc
0x180013b3e  mov     r14, rax
0x180013b41  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013b48  test    rax, rax
0x180013b4b  jz      short loc_180013B81
0x180013b4d  mov     rdx, r14
0x180013b50  mov     rcx, rbp
0x180013b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b58  nop
0x180013b59  xor     eax, eax
0x180013b5b  test    r14, r14
0x180013b5e  jnz     short loc_180013BCA
0x180013b60  mov     ecx, eax
0x180013b62  jmp     short loc_180013AEC
0x180013b64  xor     edx, edx; Val
0x180013b66  mov     r8d, 98h; Size
0x180013b6c  lea     rcx, [rsp+0F8h+var_D8]; void *
0x180013b71  call    memset_0
0x180013b76  lea     rcx, [rsp+0F8h+var_D8]; this
0x180013b7b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180013b81  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013b88  jnz     short loc_180013B59
0x180013b8a  lea     rcx, LibFileName; "ntdll.dll"
0x180013b91  call    cs:__imp_GetModuleHandleW
0x180013b97  test    rax, rax
0x180013b9a  jz      short loc_180013BB5
0x180013b9c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180013ba3  mov     rcx, rax; hModule
0x180013ba6  call    cs:__imp_GetProcAddress
0x180013bac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180013bb3  jmp     short loc_180013BBC
0x180013bb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013bbc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013bc3  test    rax, rax
0x180013bc6  jz      short loc_180013B59
0x180013bc8  jmp     short loc_180013B4D
0x180013bca  mov     [r14], esi
0x180013bcd  mov     [r14+4], eax
0x180013bd1  mov     [r14+8], rax
0x180013bd5  lea     rcx, [r14+10h]
0x180013bd9  mov     [rcx], rax
0x180013bdc  mov     rax, [r15+rdi]
0x180013be0  mov     [r14+8], rax
0x180013be4  lock cmpxchg [r15+rdi], r14
0x180013bea  jnz     short loc_180013BDC
0x180013bec  jmp     loc_180013AEC
```

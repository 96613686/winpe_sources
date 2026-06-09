# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x140007f34`
- end: `0x140008092`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `350`
- prototype: `__int64 __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, bool)`
- caller_count: `27`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006ae0`
- `0x140006b98`
- `0x140007ed4`
- `0x140008098`
- `0x140012e9c`
- `0x1400186f4`
- `0x14001ab58`
- `0x14008c5f8`
- `0x140091868`
- `0x1400932a0`
- `0x140097420`
- `0x1400a1128`
- `0x1400a6f80`
- `0x1400a7de0`
- `0x1400f17bc`
- `0x1401124b8`
- `0x1401151cc`
- `0x140115288`
- `0x14014b390`
- `0x14014b448`
- `0x14016fb1c`
- `0x1401b1130`
- `0x1401b11f8`
- `0x1401b5508`
- `0x1401b639c`
- `0x1401c7320`
- `0x1401cf848`

## callees

- `0x140007f34`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000807c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000807c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000801a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000801a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007fe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007fe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ff6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ff6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007fcb`

## string_xrefs

- `0x140008013`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wil::details::ThreadFailureCallbackHolder *__fastcall wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this,
        struct wil::details::IFailureCallback *a2,
        struct wil::CallContextInfo *a3,
        char a4)
{
  __int64 v5; // rsi
  unsigned __int64 CurrentThreadId; // r15
  unsigned __int64 v7; // rbp
  __int64 i; // rcx
  _QWORD *v9; // rcx
  HANDLE ProcessHeap; // r14
  char *v12; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v15; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_BYTE *)this + 40) = 0;
  if ( a4 )
  {
    v5 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = (CurrentThreadId >> 2) % 0xA;
      for ( i = *(_QWORD *)(v5 + 8 * v7); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        {
          v9 = (_QWORD *)(i + 16);
          goto LABEL_8;
        }
      }
      ProcessHeap = GetProcessHeap();
      v12 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
        ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v12);
      }
      if ( v12 )
      {
        *(_DWORD *)v12 = CurrentThreadId;
        *((_DWORD *)v12 + 1) = 0;
        *((_QWORD *)v12 + 1) = 0;
        v9 = v12 + 16;
        *((_QWORD *)v12 + 2) = 0;
        do
        {
          v15 = *(_QWORD *)(v5 + 8 * v7);
          *((_QWORD *)v12 + 1) = v15;
        }
        while ( v15 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + 8 * v7), (signed __int64)v12, v15) );
      }
      else
      {
        v9 = 0;
      }
LABEL_8:
      *(_QWORD *)this = v9;
      if ( v9 )
      {
        *((_QWORD *)this + 2) = *v9;
        *v9 = this;
        *((_DWORD *)this + 6) = GetCurrentThreadId();
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x140007f34  push    rbx
0x140007f36  push    rbp
0x140007f37  push    rsi
0x140007f38  push    rdi
0x140007f39  push    r14
0x140007f3b  push    r15
0x140007f3d  sub     rsp, 28h
0x140007f41  mov     rbx, rcx
0x140007f44  mov     qword ptr [rcx], 0
0x140007f4b  mov     [rcx+8], rdx
0x140007f4f  mov     qword ptr [rcx+10h], 0
0x140007f57  mov     dword ptr [rcx+18h], 0
0x140007f5e  mov     [rcx+20h], r8
0x140007f62  mov     byte ptr [rcx+28h], 0
0x140007f66  test    r9b, r9b
0x140007f69  jz      short loc_140007FD4
0x140007f6b  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140007f72  test    rsi, rsi
0x140007f75  jz      short loc_140007FD4
0x140007f77  call    cs:__imp_GetCurrentThreadId
0x140007f7d  mov     r15d, eax
0x140007f80  mov     ebp, eax
0x140007f82  shr     rbp, 2
0x140007f86  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140007f90  mul     rbp
0x140007f93  shr     rdx, 3
0x140007f97  lea     rcx, [rdx+rdx*4]
0x140007f9b  add     rcx, rcx
0x140007f9e  sub     rbp, rcx
0x140007fa1  mov     rcx, [rsi+rbp*8]
0x140007fa5  test    rcx, rcx
0x140007fa8  jz      short loc_140007FE4
0x140007faa  cmp     [rcx], r15d
0x140007fad  jz      short loc_140007FB5
0x140007faf  mov     rcx, [rcx+8]
0x140007fb3  jmp     short loc_140007FA5
0x140007fb5  add     rcx, 10h
0x140007fb9  mov     [rbx], rcx
0x140007fbc  test    rcx, rcx
0x140007fbf  jz      short loc_140007FD4
0x140007fc1  mov     rax, [rcx]
0x140007fc4  mov     [rbx+10h], rax
0x140007fc8  mov     [rcx], rbx
0x140007fcb  call    cs:__imp_GetCurrentThreadId
0x140007fd1  mov     [rbx+18h], eax
0x140007fd4  mov     rax, rbx
0x140007fd7  add     rsp, 28h
0x140007fdb  pop     r15
0x140007fdd  pop     r14
0x140007fdf  pop     rdi
0x140007fe0  pop     rsi
0x140007fe1  pop     rbp
0x140007fe2  pop     rbx
0x140007fe3  retn
0x140007fe4  call    cs:__imp_GetProcessHeap
0x140007fea  mov     r14, rax
0x140007fed  xor     edx, edx; dwFlags
0x140007fef  lea     r8d, [rdx+18h]; dwBytes
0x140007ff3  mov     rcx, rax; hHeap
0x140007ff6  call    cs:__imp_HeapAlloc
0x140007ffc  mov     rdi, rax
0x140007fff  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008006  test    rax, rax
0x140008009  jnz     short loc_140008038
0x14000800b  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008011  jnz     short loc_140008044
0x140008013  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000801a  call    cs:__imp_GetModuleHandleW
0x140008020  test    rax, rax
0x140008023  jnz     short loc_140008072
0x140008025  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000802c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008033  test    rax, rax
0x140008036  jz      short loc_140008044
0x140008038  mov     rdx, rdi
0x14000803b  mov     rcx, r14
0x14000803e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008043  nop
0x140008044  test    rdi, rdi
0x140008047  jz      short loc_14000808B
0x140008049  mov     [rdi], r15d
0x14000804c  xor     eax, eax
0x14000804e  mov     [rdi+4], eax
0x140008051  mov     [rdi+8], rax
0x140008055  lea     rcx, [rdi+10h]
0x140008059  mov     [rcx], rax
0x14000805c  mov     rax, [rsi+rbp*8]
0x140008060  mov     [rdi+8], rax
0x140008064  lock cmpxchg [rsi+rbp*8], rdi
0x14000806a  jz      loc_140007FB9
0x140008070  jmp     short loc_14000805C
0x140008072  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140008079  mov     rcx, rax; hModule
0x14000807c  call    cs:__imp_GetProcAddress
0x140008082  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140008089  jmp     short loc_14000802C
0x14000808b  xor     ecx, ecx
0x14000808d  jmp     loc_140007FB9
```

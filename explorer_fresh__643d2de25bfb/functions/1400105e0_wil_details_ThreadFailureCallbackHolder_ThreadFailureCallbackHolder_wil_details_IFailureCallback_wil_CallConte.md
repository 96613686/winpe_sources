# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x1400105e0`
- end: `0x140010763`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `387`
- prototype: `__int64 __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, bool)`
- caller_count: `27`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008200`
- `0x140010520`
- `0x14001057c`
- `0x14001144c`
- `0x1400180c4`
- `0x140045588`
- `0x140090b64`
- `0x140091cbc`
- `0x1400989c4`
- `0x14009c9dc`
- `0x1400a3a3c`
- `0x1400a6e84`
- `0x1400ad060`
- `0x1400ada84`
- `0x1400f9a70`
- `0x14010c128`
- `0x14011b3e0`
- `0x14011fac0`
- `0x14011fb80`
- `0x140155a90`
- `0x140155b48`
- `0x1401ad77c`
- `0x1401ade48`
- `0x1401b37fc`
- `0x1401b46ac`
- `0x1401c5f34`
- `0x1401ce798`

## callees

- `0x1400105e0`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010747`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010747`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400106df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400106df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001069d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001069d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001067d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001067d`

## string_xrefs

- `0x1400106d8`: `ntdll.dll`

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
0x1400105e0  push    rbx
0x1400105e2  push    rbp
0x1400105e3  push    rsi
0x1400105e4  push    rdi
0x1400105e5  push    r14
0x1400105e7  push    r15
0x1400105e9  sub     rsp, 28h
0x1400105ed  mov     rbx, rcx
0x1400105f0  mov     qword ptr [rcx], 0
0x1400105f7  mov     [rcx+8], rdx
0x1400105fb  mov     qword ptr [rcx+10h], 0
0x140010603  mov     dword ptr [rcx+18h], 0
0x14001060a  mov     [rcx+20h], r8
0x14001060e  mov     byte ptr [rcx+28h], 0
0x140010612  test    r9b, r9b
0x140010615  jz      short loc_14001068C
0x140010617  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14001061e  test    rsi, rsi
0x140010621  jz      short loc_14001068C
0x140010623  call    cs:__imp_GetCurrentThreadId
0x14001062a  nop     dword ptr [rax+rax+00h]
0x14001062f  mov     r15d, eax
0x140010632  mov     ebp, eax
0x140010634  shr     rbp, 2
0x140010638  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140010642  mul     rbp
0x140010645  shr     rdx, 3
0x140010649  lea     rcx, [rdx+rdx*4]
0x14001064d  add     rcx, rcx
0x140010650  sub     rbp, rcx
0x140010653  mov     rcx, [rsi+rbp*8]
0x140010657  test    rcx, rcx
0x14001065a  jz      short loc_14001069D
0x14001065c  cmp     [rcx], r15d
0x14001065f  jz      short loc_140010667
0x140010661  mov     rcx, [rcx+8]
0x140010665  jmp     short loc_140010657
0x140010667  add     rcx, 10h
0x14001066b  mov     [rbx], rcx
0x14001066e  test    rcx, rcx
0x140010671  jz      short loc_14001068C
0x140010673  mov     rax, [rcx]
0x140010676  mov     [rbx+10h], rax
0x14001067a  mov     [rcx], rbx
0x14001067d  call    cs:__imp_GetCurrentThreadId
0x140010684  nop     dword ptr [rax+rax+00h]
0x140010689  mov     [rbx+18h], eax
0x14001068c  mov     rax, rbx
0x14001068f  add     rsp, 28h
0x140010693  pop     r15
0x140010695  pop     r14
0x140010697  pop     rdi
0x140010698  pop     rsi
0x140010699  pop     rbp
0x14001069a  pop     rbx
0x14001069b  retn
0x14001069d  call    cs:__imp_GetProcessHeap
0x1400106a4  nop     dword ptr [rax+rax+00h]
0x1400106a9  mov     r14, rax
0x1400106ac  xor     edx, edx; dwFlags
0x1400106ae  lea     r8d, [rdx+18h]; dwBytes
0x1400106b2  mov     rcx, rax; hHeap
0x1400106b5  call    cs:__imp_HeapAlloc
0x1400106bc  nop     dword ptr [rax+rax+00h]
0x1400106c1  mov     rdi, rax
0x1400106c4  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400106cb  test    rax, rax
0x1400106ce  jnz     short loc_140010703
0x1400106d0  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400106d6  jnz     short loc_14001070F
0x1400106d8  lea     rcx, ModuleName; "ntdll.dll"
0x1400106df  call    cs:__imp_GetModuleHandleW
0x1400106e6  nop     dword ptr [rax+rax+00h]
0x1400106eb  test    rax, rax
0x1400106ee  jnz     short loc_14001073D
0x1400106f0  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400106f7  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400106fe  test    rax, rax
0x140010701  jz      short loc_14001070F
0x140010703  mov     rdx, rdi
0x140010706  mov     rcx, r14
0x140010709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001070e  nop
0x14001070f  test    rdi, rdi
0x140010712  jz      short loc_14001075C
0x140010714  mov     [rdi], r15d
0x140010717  xor     eax, eax
0x140010719  mov     [rdi+4], eax
0x14001071c  mov     [rdi+8], rax
0x140010720  lea     rcx, [rdi+10h]
0x140010724  mov     [rcx], rax
0x140010727  mov     rax, [rsi+rbp*8]
0x14001072b  mov     [rdi+8], rax
0x14001072f  lock cmpxchg [rsi+rbp*8], rdi
0x140010735  jz      loc_14001066B
0x14001073b  jmp     short loc_140010727
0x14001073d  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140010744  mov     rcx, rax; hModule
0x140010747  call    cs:__imp_GetProcAddress
0x14001074e  nop     dword ptr [rax+rax+00h]
0x140010753  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14001075a  jmp     short loc_1400106F7
0x14001075c  xor     ecx, ecx
0x14001075e  jmp     loc_14001066B
```

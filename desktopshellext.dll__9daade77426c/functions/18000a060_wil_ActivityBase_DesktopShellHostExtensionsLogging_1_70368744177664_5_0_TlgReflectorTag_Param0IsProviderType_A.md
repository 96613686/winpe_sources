# wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000a060`
- end: `0x18000a1be`
- name: `??1?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001a918`

## callees

- `0x18000a060`
- `0x18000a1c4`
- `0x18000cad8`
- `0x180035118`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a192`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a184`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0e2`

## string_xrefs

- `0x18000a124`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  __int64 **v2; // rdi
  volatile signed __int32 *v3; // rcx
  volatile signed __int32 *v4; // rax
  __int64 v5; // rax
  void *v6; // rcx
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  void *v9; // rdi
  HANDLE v10; // rax
  const struct _tlgProvider_t *v11; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (__int64 **)(a1 + 288);
  if ( *(_DWORD *)(a1 + 312) )
  {
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *((_DWORD *)v2 + 6) = 0;
    while ( 1 )
    {
      v5 = **v2;
      if ( !v5 )
        break;
      if ( (__int64 **)v5 == v2 )
      {
        **v2 = (__int64)v2[2];
        break;
      }
      *v2 = (__int64 *)(v5 + 16);
    }
    *v2 = 0;
  }
  v3 = *(volatile signed __int32 **)(a1 + 280);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
    {
      v6 = *(void **)(a1 + 280);
      if ( v6 )
        wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(v6);
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  v4 = *(volatile signed __int32 **)(a1 + 240);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
    {
      v7 = *(void **)(a1 + 240);
      ProcessHeap = GetProcessHeap();
      LODWORD(v4) = HeapFree(ProcessHeap, 0, v7);
    }
    *(_QWORD *)(a1 + 240) = 0;
    *(_QWORD *)(a1 + 248) = 0;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    v9 = *(void **)(a1 + 64);
    v10 = GetProcessHeap();
    LODWORD(v4) = HeapFree(v10, 0, v9);
    *(_BYTE *)(a1 + 72) = 0;
  }
  *(_QWORD *)(a1 + 64) = 0;
  if ( *(_DWORD *)(a1 + 8) == 1 )
  {
    *(_DWORD *)(a1 + 8) = 2;
    v11 = DesktopShellHostExtensionsLogging::Provider();
    LODWORD(v4) = _tlgWriteActivityAutoStop<70368744177664,5>(v11, a1 + 16);
  }
  *(_DWORD *)(a1 + 8) = 3;
  return (int)v4;
}

```

## disassembly

```asm
0x18000a060  mov     [rsp+arg_0], rbx
0x18000a065  mov     [rsp+arg_8], rsi
0x18000a06a  push    rdi
0x18000a06b  sub     rsp, 20h
0x18000a06f  mov     rbx, rcx
0x18000a072  lea     rdi, [rcx+120h]
0x18000a079  xor     esi, esi
0x18000a07b  cmp     [rdi+18h], esi
0x18000a07e  jnz     short loc_18000A0E2
0x18000a080  mov     rcx, [rbx+118h]
0x18000a087  mov     edi, 0FFFFFFFFh
0x18000a08c  test    rcx, rcx
0x18000a08f  jz      short loc_18000A0A3
0x18000a091  mov     eax, edi
0x18000a093  lock xadd [rcx], eax
0x18000a097  cmp     eax, 1
0x18000a09a  jz      short loc_18000A100
0x18000a09c  mov     [rbx+118h], rsi
0x18000a0a3  mov     rax, [rbx+0F0h]
0x18000a0aa  test    rax, rax
0x18000a0ad  jnz     loc_18000A149
0x18000a0b3  cmp     byte ptr [rbx+48h], 0
0x18000a0b7  jnz     loc_18000A180
0x18000a0bd  mov     [rbx+40h], rsi
0x18000a0c1  cmp     dword ptr [rbx+8], 1
0x18000a0c5  jz      loc_18000A1A1
0x18000a0cb  mov     dword ptr [rbx+8], 3
0x18000a0d2  mov     rbx, [rsp+28h+arg_0]
0x18000a0d7  mov     rsi, [rsp+28h+arg_8]
0x18000a0dc  add     rsp, 20h
0x18000a0e0  pop     rdi
0x18000a0e1  retn
0x18000a0e2  call    cs:__imp_GetCurrentThreadId
0x18000a0e8  cmp     [rdi+18h], eax
0x18000a0eb  jnz     short loc_18000A113
0x18000a0ed  mov     [rdi+18h], esi
0x18000a0f0  mov     rcx, [rdi]
0x18000a0f3  mov     rax, [rcx]
0x18000a0f6  test    rax, rax
0x18000a0f9  jnz     short loc_18000A132
0x18000a0fb  mov     [rdi], rsi
0x18000a0fe  jmp     short loc_18000A080
0x18000a100  mov     rcx, [rbx+118h]; void *
0x18000a107  test    rcx, rcx
0x18000a10a  jz      short loc_18000A09C
0x18000a10c  call    ??_GRefAndObject@?$shared_object@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAPEAXI@Z; wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(uint)
0x18000a111  jmp     short loc_18000A09C
0x18000a113  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000a11a  test    rax, rax
0x18000a11d  jz      short loc_18000A0ED
0x18000a11f  mov     rdx, [rsp+28h]
0x18000a124  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000a12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a130  jmp     short loc_18000A0ED
0x18000a132  cmp     rax, rdi
0x18000a135  jz      short loc_18000A140
0x18000a137  add     rax, 10h
0x18000a13b  mov     [rdi], rax
0x18000a13e  jmp     short loc_18000A0F0
0x18000a140  mov     rax, [rdi+10h]
0x18000a144  mov     [rcx], rax
0x18000a147  jmp     short loc_18000A0FB
0x18000a149  lock xadd [rax], edi
0x18000a14d  cmp     edi, 1
0x18000a150  jnz     short loc_18000A16D
0x18000a152  mov     rdi, [rbx+0F0h]
0x18000a159  call    cs:__imp_GetProcessHeap
0x18000a15f  mov     r8, rdi; lpMem
0x18000a162  xor     edx, edx; dwFlags
0x18000a164  mov     rcx, rax; hHeap
0x18000a167  call    cs:__imp_HeapFree
0x18000a16d  mov     [rbx+0F0h], rsi
0x18000a174  mov     [rbx+0F8h], rsi
0x18000a17b  jmp     loc_18000A0B3
0x18000a180  mov     rdi, [rbx+40h]
0x18000a184  call    cs:__imp_GetProcessHeap
0x18000a18a  mov     r8, rdi; lpMem
0x18000a18d  xor     edx, edx; dwFlags
0x18000a18f  mov     rcx, rax; hHeap
0x18000a192  call    cs:__imp_HeapFree
0x18000a198  mov     byte ptr [rbx+48h], 0
0x18000a19c  jmp     loc_18000A0BD
0x18000a1a1  mov     dword ptr [rbx+8], 2
0x18000a1a8  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x18000a1ad  lea     rdx, [rbx+10h]
0x18000a1b1  mov     rcx, rax
0x18000a1b4  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18000a1b9  jmp     loc_18000A0CB
```

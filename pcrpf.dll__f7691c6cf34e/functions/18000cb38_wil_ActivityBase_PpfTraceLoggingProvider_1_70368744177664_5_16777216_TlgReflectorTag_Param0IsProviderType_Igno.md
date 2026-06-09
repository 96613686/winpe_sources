# wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000cb38`
- end: `0x18000cbb3`
- name: `?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(__int64)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e260`
- `0x18000e3a0`
- `0x180018aa0`
- `0x180018d3c`
- `0x180019090`
- `0x180019330`
- `0x1800195cc`
- `0x180019a60`
- `0x180019cfc`
- `0x18001a0b0`
- `0x18001a34c`
- `0x18001a6a0`
- `0x18001a93c`
- `0x180050f10`
- `0x1800511b0`
- `0x18005144c`
- `0x180053ae0`

## callees

- `0x18000cb38`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb4e`

## string_xrefs

- `0x18000cb70`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v1 + 24) = 0;
    v2 = *(__int64 **)v1;
    while ( 1 )
    {
      v3 = *v2;
      if ( !*v2 )
        break;
      if ( v3 == v1 )
      {
        *v2 = *(_QWORD *)(v1 + 16);
        break;
      }
      v2 = (__int64 *)(v3 + 16);
      *(_QWORD *)v1 = v3 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000cb38  push    rbx
0x18000cb3a  sub     rsp, 20h
0x18000cb3e  cmp     dword ptr [rcx+138h], 0
0x18000cb45  jz      short loc_18000CBAC
0x18000cb47  lea     rbx, [rcx+120h]
0x18000cb4e  call    cs:__imp_GetCurrentThreadId
0x18000cb55  nop     dword ptr [rax+rax+00h]
0x18000cb5a  cmp     [rbx+18h], eax
0x18000cb5d  jz      short loc_18000CB7C
0x18000cb5f  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000cb66  test    rax, rax
0x18000cb69  jz      short loc_18000CB7C
0x18000cb6b  mov     rdx, [rsp+28h]
0x18000cb70  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000cb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7c  mov     dword ptr [rbx+18h], 0
0x18000cb83  mov     rcx, [rbx]
0x18000cb86  jmp     short loc_18000CB94
0x18000cb88  cmp     rax, rbx
0x18000cb8b  jz      short loc_18000CB9E
0x18000cb8d  lea     rcx, [rax+10h]
0x18000cb91  mov     [rbx], rcx
0x18000cb94  mov     rax, [rcx]
0x18000cb97  test    rax, rax
0x18000cb9a  jnz     short loc_18000CB88
0x18000cb9c  jmp     short loc_18000CBA5
0x18000cb9e  mov     rax, [rbx+10h]
0x18000cba2  mov     [rcx], rax
0x18000cba5  mov     qword ptr [rbx], 0
0x18000cbac  add     rsp, 20h
0x18000cbb0  pop     rbx
0x18000cbb1  retn
```

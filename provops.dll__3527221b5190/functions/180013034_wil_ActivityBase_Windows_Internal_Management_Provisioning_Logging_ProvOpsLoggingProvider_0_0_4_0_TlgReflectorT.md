# wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180013034`
- end: `0x1800130a8`
- name: `?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180018e80`
- `0x180018fcc`
- `0x180019118`
- `0x180019238`
- `0x180019360`
- `0x1800195e0`
- `0x180019860`
- `0x180019ae0`
- `0x180019d70`
- `0x18001a000`
- `0x18001a290`
- `0x18001a510`
- `0x18001a7a0`
- `0x18001aa20`
- `0x18001aca0`

## callees

- `0x180013034`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001304a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001304a`

## string_xrefs

- `0x180013066`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x180013034  push    rbx
0x180013036  sub     rsp, 20h
0x18001303a  cmp     dword ptr [rcx+138h], 0
0x180013041  jz      short loc_1800130A2
0x180013043  lea     rbx, [rcx+120h]
0x18001304a  call    cs:__imp_GetCurrentThreadId
0x180013050  cmp     [rbx+18h], eax
0x180013053  jz      short loc_180013072
0x180013055  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001305c  test    rax, rax
0x18001305f  jz      short loc_180013072
0x180013061  mov     rdx, [rsp+28h]
0x180013066  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001306d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013072  mov     dword ptr [rbx+18h], 0
0x180013079  mov     rcx, [rbx]
0x18001307c  jmp     short loc_18001308A
0x18001307e  cmp     rax, rbx
0x180013081  jz      short loc_180013094
0x180013083  lea     rcx, [rax+10h]
0x180013087  mov     [rbx], rcx
0x18001308a  mov     rax, [rcx]
0x18001308d  test    rax, rax
0x180013090  jnz     short loc_18001307E
0x180013092  jmp     short loc_18001309B
0x180013094  mov     rax, [rbx+10h]
0x180013098  mov     [rcx], rax
0x18001309b  mov     qword ptr [rbx], 0
0x1800130a2  add     rsp, 20h
0x1800130a6  pop     rbx
0x1800130a7  retn
```

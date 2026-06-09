# wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000a290`
- end: `0x18000a304`
- name: `?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d78c`
- `0x18000d8d8`
- `0x18000da00`
- `0x18000dc80`
- `0x18000df00`
- `0x18000e180`
- `0x18000e400`
- `0x18000e680`
- `0x18000e900`
- `0x18000eb90`
- `0x18000ee10`
- `0x18000f090`

## callees

- `0x18000a290`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2a6`

## string_xrefs

- `0x18000a2c2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18000a290  push    rbx
0x18000a292  sub     rsp, 20h
0x18000a296  cmp     dword ptr [rcx+138h], 0
0x18000a29d  jz      short loc_18000A2FE
0x18000a29f  lea     rbx, [rcx+120h]
0x18000a2a6  call    cs:__imp_GetCurrentThreadId
0x18000a2ac  cmp     [rbx+18h], eax
0x18000a2af  jz      short loc_18000A2CE
0x18000a2b1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000a2b8  test    rax, rax
0x18000a2bb  jz      short loc_18000A2CE
0x18000a2bd  mov     rdx, [rsp+28h]
0x18000a2c2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000a2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ce  mov     dword ptr [rbx+18h], 0
0x18000a2d5  mov     rcx, [rbx]
0x18000a2d8  jmp     short loc_18000A2E6
0x18000a2da  cmp     rax, rbx
0x18000a2dd  jz      short loc_18000A2F0
0x18000a2df  lea     rcx, [rax+10h]
0x18000a2e3  mov     [rbx], rcx
0x18000a2e6  mov     rax, [rcx]
0x18000a2e9  test    rax, rax
0x18000a2ec  jnz     short loc_18000A2DA
0x18000a2ee  jmp     short loc_18000A2F7
0x18000a2f0  mov     rax, [rbx+10h]
0x18000a2f4  mov     [rcx], rax
0x18000a2f7  mov     qword ptr [rbx], 0
0x18000a2fe  add     rsp, 20h
0x18000a302  pop     rbx
0x18000a303  retn
```

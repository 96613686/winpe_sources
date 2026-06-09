# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18002cc70`
- end: `0x18002cce4`
- name: `?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e054`
- `0x18002e170`
- `0x18002e3f0`
- `0x18002e670`

## callees

- `0x18002cc70`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc86`

## string_xrefs

- `0x18002cca2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18002cc70  push    rbx
0x18002cc72  sub     rsp, 20h
0x18002cc76  cmp     dword ptr [rcx+138h], 0
0x18002cc7d  jz      short loc_18002CCDE
0x18002cc7f  lea     rbx, [rcx+120h]
0x18002cc86  call    cs:__imp_GetCurrentThreadId
0x18002cc8c  cmp     [rbx+18h], eax
0x18002cc8f  jz      short loc_18002CCAE
0x18002cc91  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18002cc98  test    rax, rax
0x18002cc9b  jz      short loc_18002CCAE
0x18002cc9d  mov     rdx, [rsp+28h]
0x18002cca2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccae  mov     dword ptr [rbx+18h], 0
0x18002ccb5  mov     rcx, [rbx]
0x18002ccb8  jmp     short loc_18002CCC6
0x18002ccba  cmp     rax, rbx
0x18002ccbd  jz      short loc_18002CCD0
0x18002ccbf  lea     rcx, [rax+10h]
0x18002ccc3  mov     [rbx], rcx
0x18002ccc6  mov     rax, [rcx]
0x18002ccc9  test    rax, rax
0x18002cccc  jnz     short loc_18002CCBA
0x18002ccce  jmp     short loc_18002CCD7
0x18002ccd0  mov     rax, [rbx+10h]
0x18002ccd4  mov     [rcx], rax
0x18002ccd7  mov     qword ptr [rbx], 0
0x18002ccde  add     rsp, 20h
0x18002cce2  pop     rbx
0x18002cce3  retn
```

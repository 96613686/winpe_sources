# wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000bec0`
- end: `0x18000bf3b`
- name: `?IgnoreCurrentThread@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd2c`
- `0x18000ce70`
- `0x18000d110`
- `0x18000d3b0`

## callees

- `0x18000bec0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bed6`

## string_xrefs

- `0x18000bef8`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18000bec0  push    rbx
0x18000bec2  sub     rsp, 20h
0x18000bec6  cmp     dword ptr [rcx+138h], 0
0x18000becd  jz      short loc_18000BF34
0x18000becf  lea     rbx, [rcx+120h]
0x18000bed6  call    cs:__imp_GetCurrentThreadId
0x18000bedd  nop     dword ptr [rax+rax+00h]
0x18000bee2  cmp     [rbx+18h], eax
0x18000bee5  jz      short loc_18000BF04
0x18000bee7  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18000beee  test    rax, rax
0x18000bef1  jz      short loc_18000BF04
0x18000bef3  mov     rdx, [rsp+28h]
0x18000bef8  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000beff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf04  mov     dword ptr [rbx+18h], 0
0x18000bf0b  mov     rcx, [rbx]
0x18000bf0e  jmp     short loc_18000BF1C
0x18000bf10  cmp     rax, rbx
0x18000bf13  jz      short loc_18000BF26
0x18000bf15  lea     rcx, [rax+10h]
0x18000bf19  mov     [rbx], rcx
0x18000bf1c  mov     rax, [rcx]
0x18000bf1f  test    rax, rax
0x18000bf22  jnz     short loc_18000BF10
0x18000bf24  jmp     short loc_18000BF2D
0x18000bf26  mov     rax, [rbx+10h]
0x18000bf2a  mov     [rcx], rax
0x18000bf2d  mov     qword ptr [rbx], 0
0x18000bf34  add     rsp, 20h
0x18000bf38  pop     rbx
0x18000bf39  retn
```

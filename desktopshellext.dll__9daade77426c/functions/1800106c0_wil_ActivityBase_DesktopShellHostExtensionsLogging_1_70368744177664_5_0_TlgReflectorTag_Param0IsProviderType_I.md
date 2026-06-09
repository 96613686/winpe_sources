# wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800106c0`
- end: `0x180010732`
- name: `?IgnoreCurrentThread@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `114`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009cc0`
- `0x1800132a0`
- `0x180018348`
- `0x180039610`
- `0x180039840`

## callees

- `0x1800106c0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800106d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800106d6`

## string_xrefs

- `0x1800106f2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 **v1; // rbx
  __int64 v2; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = (__int64 **)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v1 + 6) = 0;
    while ( 1 )
    {
      v2 = **v1;
      if ( !v2 )
        break;
      if ( (__int64 **)v2 == v1 )
      {
        **v1 = (__int64)v1[2];
        break;
      }
      *v1 = (__int64 *)(v2 + 16);
    }
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x1800106c0  push    rbx
0x1800106c2  sub     rsp, 20h
0x1800106c6  cmp     dword ptr [rcx+138h], 0
0x1800106cd  jz      short loc_18001072C
0x1800106cf  lea     rbx, [rcx+120h]
0x1800106d6  call    cs:__imp_GetCurrentThreadId
0x1800106dc  cmp     [rbx+18h], eax
0x1800106df  jz      short loc_1800106FE
0x1800106e1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800106e8  test    rax, rax
0x1800106eb  jz      short loc_1800106FE
0x1800106ed  mov     rdx, [rsp+28h]
0x1800106f2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800106f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106fe  mov     dword ptr [rbx+18h], 0
0x180010705  mov     rcx, [rbx]
0x180010708  mov     rax, [rcx]
0x18001070b  test    rax, rax
0x18001070e  jz      short loc_180010725
0x180010710  cmp     rax, rbx
0x180010713  jz      short loc_18001071E
0x180010715  add     rax, 10h
0x180010719  mov     [rbx], rax
0x18001071c  jmp     short loc_180010705
0x18001071e  mov     rax, [rbx+10h]
0x180010722  mov     [rcx], rax
0x180010725  mov     qword ptr [rbx], 0
0x18001072c  add     rsp, 20h
0x180010730  pop     rbx
0x180010731  retn
```

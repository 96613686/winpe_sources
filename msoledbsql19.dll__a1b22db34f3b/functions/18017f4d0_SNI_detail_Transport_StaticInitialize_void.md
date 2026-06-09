# SNI::detail::Transport::StaticInitialize(void)

- ea: `0x18017f4d0`
- end: `0x18017f7d8`
- name: `?StaticInitialize@Transport@detail@SNI@@SAKXZ`
- size: `776`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18015ead0`
- `0x180164ab0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x18015a6f0`
- `0x18015a880`
- `0x18017f4d0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18017f703`
- `KERNEL32!FreeLibrary` at `0x18017f703`
- `KERNEL32!GetLastError` at `0x18017f5b5`
- `KERNEL32!GetLastError` at `0x18017f643`
- `KERNEL32!GetLastError` at `0x18017f5b5`
- `KERNEL32!GetLastError` at `0x18017f643`
- `KERNEL32!GetProcAddress` at `0x18017f5fd`
- `KERNEL32!GetProcAddress` at `0x18017f5fd`

## string_xrefs

- `0x18017f59d`: `kernel32.dll`
- `0x18017f5f3`: `SetFileCompletionNotificationModes`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SNI::detail::Transport::StaticInitialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD LastError; // ebx
  HMODULE v5; // rax
  DWORD v6; // eax
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h] BYREF

  v9 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266E60[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v9,
      off_180266E60[0],
      0);
  LastError = 0;
  ++SNI::detail::Transport::s_dwRefCount;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802655B8[0] )
    bidTraceW(off_180262270[0], 67584, off_1802655B8[0], SNI::detail::Transport::s_dwRefCount);
  if ( SNI::detail::Transport::s_dwRefCount == 1 )
  {
    v5 = SNILoadSystemLibA("kernel32.dll", a2, a3, a4);
    SNI::detail::Transport::s_hKernel32 = v5;
    if ( v5 )
    {
      SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes = (int (*)(void *, unsigned __int8))GetProcAddress(v5, "SetFileCompletionNotificationModes");
      if ( SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes )
        goto LABEL_33;
      if ( (bidGblFlags & 2) != 0 && off_1802655C8[0] )
        bidTraceW(off_180262280[0], 110592, off_1802655C8[0], 0);
      LastError = GetLastError();
    }
    else
    {
      v6 = GetLastError();
      LastError = v6;
      if ( (bidGblFlags & 2) != 0 && off_1802655C0[0] )
        bidTraceW(off_180262278[0], 97280, off_1802655C0[0], v6);
    }
    v8 = -1;
    if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266E68[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
        bidID,
        0,
        0,
        &v8,
        off_180266E68[0],
        0);
    --SNI::detail::Transport::s_dwRefCount;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802655E0[0] )
      bidTraceW(off_180262298[0], 143360, off_1802655E0[0], SNI::detail::Transport::s_dwRefCount);
    if ( !SNI::detail::Transport::s_dwRefCount )
    {
      if ( SNI::detail::Transport::s_hKernel32 )
      {
        FreeLibrary(SNI::detail::Transport::s_hKernel32);
        SNI::detail::Transport::s_hKernel32 = 0;
      }
      SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes = 0;
    }
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
    if ( (bidGblFlags & 2) != 0 && off_1802655D0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_180262288[0], 128000, off_1802655D0[0], 8);
    }
    SNISetLastError(8, LastError, 50100);
  }
LABEL_33:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802655D8[0] )
    bidTraceW(off_180262290[0], 0x20000, off_1802655D8[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
  return LastError;
}

```

## disassembly

```asm
0x18017f4d0  mov     [rsp+arg_0], rbx
0x18017f4d5  push    rdi
0x18017f4d6  sub     rsp, 60h
0x18017f4da  mov     rax, cs:__security_cookie
0x18017f4e1  xor     rax, rsp
0x18017f4e4  mov     [rsp+68h+var_18], rax
0x18017f4e9  mov     [rsp+68h+var_20], 0FFFFFFFFFFFFFFFFh
0x18017f4f2  mov     eax, cs:_bidGblFlags
0x18017f4f8  and     eax, 20004h
0x18017f4fd  xor     edi, edi
0x18017f4ff  cmp     eax, 20004h
0x18017f504  jnz     short loc_18017F54B
0x18017f506  mov     rax, cs:off_180266E60; "<SNI::detail::Transport::StaticInitiali"...
0x18017f50d  test    rax, rax
0x18017f510  jz      short loc_18017F54B
0x18017f512  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18017f51a  jz      short loc_18017F54B
0x18017f51c  mov     rax, cs:off_180248060
0x18017f523  mov     [rsp+68h+var_40], rdi
0x18017f528  mov     rcx, cs:off_180266E60; "<SNI::detail::Transport::StaticInitiali"...
0x18017f52f  mov     [rsp+68h+var_48], rcx
0x18017f534  lea     r9, [rsp+68h+var_20]
0x18017f539  xor     r8d, r8d
0x18017f53c  xor     edx, edx
0x18017f53e  mov     rcx, cs:_bidID
0x18017f545  call    cs:__guard_dispatch_icall_fptr
0x18017f54b  mov     ebx, edi
0x18017f54d  inc     cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x18017f553  mov     eax, cs:_bidGblFlags
0x18017f559  and     eax, 20002h
0x18017f55e  cmp     eax, 20002h
0x18017f563  jnz     short loc_18017F590
0x18017f565  mov     rax, cs:off_1802655B8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f56c  test    rax, rax
0x18017f56f  jz      short loc_18017F590
0x18017f571  mov     r9d, cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x18017f578  mov     r8, cs:off_1802655B8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f57f  mov     edx, 10800h
0x18017f584  mov     rcx, cs:off_180262270; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f58b  call    _bidTraceW
0x18017f590  cmp     cs:?s_dwRefCount@Transport@detail@SNI@@0KA, 1; ulong SNI::detail::Transport::s_dwRefCount
0x18017f597  jnz     loc_18017F779
0x18017f59d  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18017f5a4  call    SNILoadSystemLibA
0x18017f5a9  mov     cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * SNI::detail::Transport::s_hKernel32
0x18017f5b0  test    rax, rax
0x18017f5b3  jnz     short loc_18017F5F3
0x18017f5b5  call    cs:__imp_GetLastError
0x18017f5bb  mov     ebx, eax
0x18017f5bd  test    byte ptr cs:_bidGblFlags, 2
0x18017f5c4  jz      loc_18017F64B
0x18017f5ca  mov     rcx, cs:off_1802655C0; "<SNI::detail::Transport::StaticInitiali"...
0x18017f5d1  test    rcx, rcx
0x18017f5d4  jz      short loc_18017F64B
0x18017f5d6  mov     r9d, eax
0x18017f5d9  mov     r8, cs:off_1802655C0; "<SNI::detail::Transport::StaticInitiali"...
0x18017f5e0  mov     edx, 17C00h
0x18017f5e5  mov     rcx, cs:off_180262278; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f5ec  call    _bidTraceW
0x18017f5f1  jmp     short loc_18017F64B
0x18017f5f3  lea     rdx, aSetfilecomplet; "SetFileCompletionNotificationModes"
0x18017f5fa  mov     rcx, rax; hModule
0x18017f5fd  call    cs:__imp_GetProcAddress
0x18017f603  mov     cs:?s_pfnWin32SetFileCompletionNotificationModes@Transport@detail@SNI@@0P6AHPEAXE@ZEA, rax; int (*SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes)(void *,uchar)
0x18017f60a  test    rax, rax
0x18017f60d  jnz     loc_18017F779
0x18017f613  test    byte ptr cs:_bidGblFlags, 2
0x18017f61a  jz      short loc_18017F643
0x18017f61c  mov     rax, cs:off_1802655C8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f623  test    rax, rax
0x18017f626  jz      short loc_18017F643
0x18017f628  xor     r9d, r9d
0x18017f62b  mov     r8, cs:off_1802655C8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f632  mov     edx, 1B000h
0x18017f637  mov     rcx, cs:off_180262280; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f63e  call    _bidTraceW
0x18017f643  call    cs:__imp_GetLastError
0x18017f649  mov     ebx, eax
0x18017f64b  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x18017f654  mov     eax, cs:_bidGblFlags
0x18017f65a  and     eax, 20004h
0x18017f65f  cmp     eax, 20004h
0x18017f664  jnz     short loc_18017F6AB
0x18017f666  mov     rax, cs:off_180266E68; "<SNI::detail::Transport::StaticTerminat"...
0x18017f66d  test    rax, rax
0x18017f670  jz      short loc_18017F6AB
0x18017f672  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18017f67a  jz      short loc_18017F6AB
0x18017f67c  mov     rax, cs:off_180248060
0x18017f683  mov     [rsp+68h+var_40], rdi
0x18017f688  mov     rcx, cs:off_180266E68; "<SNI::detail::Transport::StaticTerminat"...
0x18017f68f  mov     [rsp+68h+var_48], rcx
0x18017f694  lea     r9, [rsp+68h+var_28]
0x18017f699  xor     r8d, r8d
0x18017f69c  xor     edx, edx
0x18017f69e  mov     rcx, cs:_bidID
0x18017f6a5  call    cs:__guard_dispatch_icall_fptr
0x18017f6ab  dec     cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x18017f6b1  mov     eax, cs:_bidGblFlags
0x18017f6b7  and     eax, 20002h
0x18017f6bc  cmp     eax, 20002h
0x18017f6c1  jnz     short loc_18017F6EE
0x18017f6c3  mov     rax, cs:off_1802655E0; "<SNI::detail::Transport::StaticTerminat"...
0x18017f6ca  test    rax, rax
0x18017f6cd  jz      short loc_18017F6EE
0x18017f6cf  mov     r9d, cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x18017f6d6  mov     r8, cs:off_1802655E0; "<SNI::detail::Transport::StaticTerminat"...
0x18017f6dd  mov     edx, 23000h
0x18017f6e2  mov     rcx, cs:off_180262298; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f6e9  call    _bidTraceW
0x18017f6ee  cmp     cs:?s_dwRefCount@Transport@detail@SNI@@0KA, 0; ulong SNI::detail::Transport::s_dwRefCount
0x18017f6f5  jnz     short loc_18017F717
0x18017f6f7  mov     rcx, cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA; hLibModule
0x18017f6fe  test    rcx, rcx
0x18017f701  jz      short loc_18017F710
0x18017f703  call    cs:__imp_FreeLibrary
0x18017f709  mov     cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * SNI::detail::Transport::s_hKernel32
0x18017f710  mov     cs:?s_pfnWin32SetFileCompletionNotificationModes@Transport@detail@SNI@@0P6AHPEAXE@ZEA, rdi; int (*SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes)(void *,uchar)
0x18017f717  lea     rcx, [rsp+68h+var_28]; this
0x18017f71c  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18017f721  nop
0x18017f722  test    byte ptr cs:_bidGblFlags, 2
0x18017f729  jz      short loc_18017F767
0x18017f72b  mov     rax, cs:off_1802655D0; "<SNI::detail::Transport::StaticInitiali"...
0x18017f732  test    rax, rax
0x18017f735  jz      short loc_18017F767
0x18017f737  mov     ecx, 0C3B4h; unsigned int
0x18017f73c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017f741  mov     dword ptr [rsp+68h+var_40], ebx
0x18017f745  mov     dword ptr [rsp+68h+var_48], eax
0x18017f749  mov     r9d, 8
0x18017f74f  mov     r8, cs:off_1802655D0; "<SNI::detail::Transport::StaticInitiali"...
0x18017f756  mov     edx, 1F400h
0x18017f75b  mov     rcx, cs:off_180262288; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f762  call    _bidTraceW
0x18017f767  mov     r8d, 0C3B4h
0x18017f76d  mov     edx, ebx
0x18017f76f  mov     ecx, 8
0x18017f774  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017f779  mov     eax, cs:_bidGblFlags
0x18017f77f  and     eax, 20002h
0x18017f784  cmp     eax, 20002h
0x18017f789  jnz     short loc_18017F7B3
0x18017f78b  mov     rax, cs:off_1802655D8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f792  test    rax, rax
0x18017f795  jz      short loc_18017F7B3
0x18017f797  mov     r9d, ebx
0x18017f79a  mov     r8, cs:off_1802655D8; "<SNI::detail::Transport::StaticInitiali"...
0x18017f7a1  mov     edx, 20000h
0x18017f7a6  mov     rcx, cs:off_180262290; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017f7ad  call    _bidTraceW
0x18017f7b2  nop
0x18017f7b3  lea     rcx, [rsp+68h+var_20]; this
0x18017f7b8  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18017f7bd  nop
0x18017f7be  mov     eax, ebx
0x18017f7c0  mov     rcx, [rsp+68h+var_18]
0x18017f7c5  xor     rcx, rsp; StackCookie
0x18017f7c8  call    __security_check_cookie
0x18017f7cd  mov     rbx, [rsp+68h+arg_0]
0x18017f7d2  add     rsp, 60h
0x18017f7d6  pop     rdi
0x18017f7d7  retn
```

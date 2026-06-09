# SNI::detail::Transport::StaticInitialize(void)

- ea: `0x10043b49c`
- end: `0x10043b692`
- name: `?StaticInitialize@Transport@detail@SNI@@SAKXZ`
- size: `502`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x10042207c`
- `0x100434d74`

## callees

- `0x100417768`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b49c`
- `0x10043b698`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043b56d`
- `KERNEL32!GetLastError` at `0x10043b5ed`
- `KERNEL32!GetLastError` at `0x10043b56d`
- `KERNEL32!GetLastError` at `0x10043b5ed`
- `KERNEL32!GetProcAddress` at `0x10043b5ac`
- `KERNEL32!GetProcAddress` at `0x10043b5ac`

## string_xrefs

- `0x10043b555`: `kernel32.dll`
- `0x10043b5a2`: `SetFileCompletionNotificationModes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNI::detail::Transport::StaticInitialize(void)
{
  DWORD LastError; // ebx
  HMODULE v1; // rax
  DWORD v2; // eax
  __int64 v4; // [rsp+60h] [rbp+8h] BYREF

  v4 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7E30[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v4,
      off_1005E7E30[0],
      0);
  LastError = 0;
  ++SNI::detail::Transport::s_dwRefCount;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5D00[0] )
    bidTraceW(0, 67584, off_1005E5D00[0], SNI::detail::Transport::s_dwRefCount);
  if ( SNI::detail::Transport::s_dwRefCount == 1 )
  {
    v1 = SNILoadSystemLibA("kernel32.dll");
    SNI::detail::Transport::s_hKernel32 = v1;
    if ( v1 )
    {
      SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes = (int (*)(void *, unsigned __int8))GetProcAddress(v1, "SetFileCompletionNotificationModes");
      if ( SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes )
        goto LABEL_22;
      if ( (bidGblFlags & 2) != 0 && off_1005E5D10[0] )
        bidTraceW(0, 110592, off_1005E5D10[0], 0);
      LastError = GetLastError();
    }
    else
    {
      v2 = GetLastError();
      LastError = v2;
      if ( (bidGblFlags & 2) != 0 && off_1005E5D08[0] )
        bidTraceW(0, 97280, off_1005E5D08[0], v2);
    }
    SNI::detail::Transport::StaticTerminate();
    if ( (bidGblFlags & 2) != 0 && off_1005E5D18[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 128000, off_1005E5D18[0], 9);
    }
    SNISetLastError(9, LastError, 50100);
  }
LABEL_22:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5D20[0] )
    bidTraceW(0, 0x20000, off_1005E5D20[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v4);
  return LastError;
}

```

## disassembly

```asm
0x10043b49c  mov     r11, rsp
0x10043b49f  push    rdi
0x10043b4a0  sub     rsp, 50h
0x10043b4a4  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10043b4ac  mov     [r11+10h], rbx
0x10043b4b0  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x10043b4b5  mov     eax, cs:_bidGblFlags
0x10043b4bb  mov     ecx, 20004h
0x10043b4c0  and     eax, ecx
0x10043b4c2  cmp     eax, ecx
0x10043b4c4  jnz     short loc_10043B509
0x10043b4c6  mov     rax, cs:off_1005E7E30; "<SNI::detail::Transport::StaticInitiali"...
0x10043b4cd  test    rax, rax
0x10043b4d0  jz      short loc_10043B509
0x10043b4d2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043b4da  jz      short loc_10043B509
0x10043b4dc  mov     rax, cs:off_1005D39F0
0x10043b4e3  and     qword ptr [r11-30h], 0
0x10043b4e8  mov     rcx, cs:off_1005E7E30; "<SNI::detail::Transport::StaticInitiali"...
0x10043b4ef  mov     [r11-38h], rcx
0x10043b4f3  lea     r9, [r11+8]
0x10043b4f7  xor     r8d, r8d
0x10043b4fa  xor     edx, edx
0x10043b4fc  mov     rcx, cs:_bidID
0x10043b503  call    cs:__guard_dispatch_icall_fptr
0x10043b509  xor     ebx, ebx
0x10043b50b  inc     cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x10043b511  mov     eax, cs:_bidGblFlags
0x10043b517  mov     edi, 20002h
0x10043b51c  and     eax, edi
0x10043b51e  cmp     eax, edi
0x10043b520  jnz     short loc_10043B548
0x10043b522  mov     rax, cs:off_1005E5D00; "<SNI::detail::Transport::StaticInitiali"...
0x10043b529  test    rax, rax
0x10043b52c  jz      short loc_10043B548
0x10043b52e  mov     r9d, cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x10043b535  mov     r8, cs:off_1005E5D00; "<SNI::detail::Transport::StaticInitiali"...
0x10043b53c  mov     edx, 10800h
0x10043b541  xor     ecx, ecx
0x10043b543  call    _bidTraceW
0x10043b548  cmp     cs:?s_dwRefCount@Transport@detail@SNI@@0KA, 1; ulong SNI::detail::Transport::s_dwRefCount
0x10043b54f  jnz     loc_10043B64C
0x10043b555  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10043b55c  call    SNILoadSystemLibA
0x10043b561  mov     cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * SNI::detail::Transport::s_hKernel32
0x10043b568  test    rax, rax
0x10043b56b  jnz     short loc_10043B5A2
0x10043b56d  call    cs:__imp_GetLastError
0x10043b573  mov     ebx, eax
0x10043b575  test    byte ptr cs:_bidGblFlags, 2
0x10043b57c  jz      short loc_10043B5F5
0x10043b57e  mov     rcx, cs:off_1005E5D08; "<SNI::detail::Transport::StaticInitiali"...
0x10043b585  test    rcx, rcx
0x10043b588  jz      short loc_10043B5F5
0x10043b58a  mov     r9d, eax
0x10043b58d  mov     r8, cs:off_1005E5D08; "<SNI::detail::Transport::StaticInitiali"...
0x10043b594  mov     edx, 17C00h
0x10043b599  xor     ecx, ecx
0x10043b59b  call    _bidTraceW
0x10043b5a0  jmp     short loc_10043B5F5
0x10043b5a2  lea     rdx, aSetfilecomplet; "SetFileCompletionNotificationModes"
0x10043b5a9  mov     rcx, rax; hModule
0x10043b5ac  call    cs:__imp_GetProcAddress
0x10043b5b2  mov     cs:?s_pfnWin32SetFileCompletionNotificationModes@Transport@detail@SNI@@0P6AHPEAXE@ZEA, rax; int (*SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes)(void *,uchar)
0x10043b5b9  test    rax, rax
0x10043b5bc  jnz     loc_10043B64C
0x10043b5c2  test    byte ptr cs:_bidGblFlags, 2
0x10043b5c9  jz      short loc_10043B5ED
0x10043b5cb  mov     rax, cs:off_1005E5D10; "<SNI::detail::Transport::StaticInitiali"...
0x10043b5d2  test    rax, rax
0x10043b5d5  jz      short loc_10043B5ED
0x10043b5d7  xor     r9d, r9d
0x10043b5da  mov     r8, cs:off_1005E5D10; "<SNI::detail::Transport::StaticInitiali"...
0x10043b5e1  mov     edx, 1B000h
0x10043b5e6  xor     ecx, ecx
0x10043b5e8  call    _bidTraceW
0x10043b5ed  call    cs:__imp_GetLastError
0x10043b5f3  mov     ebx, eax
0x10043b5f5  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x10043b5fa  test    byte ptr cs:_bidGblFlags, 2
0x10043b601  jz      short loc_10043B63A
0x10043b603  mov     rax, cs:off_1005E5D18; "<SNI::detail::Transport::StaticInitiali"...
0x10043b60a  test    rax, rax
0x10043b60d  jz      short loc_10043B63A
0x10043b60f  mov     ecx, 0C3B4h; unsigned int
0x10043b614  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10043b619  mov     [rsp+58h+var_30], ebx
0x10043b61d  mov     [rsp+58h+var_38], eax
0x10043b621  mov     r9d, 9
0x10043b627  mov     r8, cs:off_1005E5D18; "<SNI::detail::Transport::StaticInitiali"...
0x10043b62e  mov     edx, 1F400h
0x10043b633  xor     ecx, ecx
0x10043b635  call    _bidTraceW
0x10043b63a  mov     r8d, 0C3B4h
0x10043b640  mov     edx, ebx
0x10043b642  mov     ecx, 9
0x10043b647  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b64c  mov     eax, cs:_bidGblFlags
0x10043b652  and     eax, edi
0x10043b654  cmp     eax, edi
0x10043b656  jnz     short loc_10043B67B
0x10043b658  mov     rax, cs:off_1005E5D20; "<SNI::detail::Transport::StaticInitiali"...
0x10043b65f  test    rax, rax
0x10043b662  jz      short loc_10043B67B
0x10043b664  mov     r9d, ebx
0x10043b667  mov     r8, cs:off_1005E5D20; "<SNI::detail::Transport::StaticInitiali"...
0x10043b66e  mov     edx, 20000h
0x10043b673  xor     ecx, ecx
0x10043b675  call    _bidTraceW
0x10043b67a  nop
0x10043b67b  lea     rcx, [rsp+58h+arg_0]; this
0x10043b680  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10043b685  mov     eax, ebx
0x10043b687  mov     rbx, [rsp+58h+arg_8]
0x10043b68c  add     rsp, 50h
0x10043b690  pop     rdi
0x10043b691  retn
```

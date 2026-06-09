# CADMCOMW::ShutdownCallerWatch(void)

- ea: `0x180009678`
- end: `0x180009768`
- name: `?ShutdownCallerWatch@CADMCOMW@@AEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009920`

## callees

- `0x180009678`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800096d7`
- `KERNEL32!SetLastError` at `0x1800096d7`
- `KERNEL32!CloseHandle` at `0x180009744`
- `KERNEL32!CloseHandle` at `0x180009744`
- `KERNEL32!GetLastError` at `0x1800096c8`
- `KERNEL32!GetLastError` at `0x1800096ed`
- `KERNEL32!GetLastError` at `0x1800096c8`
- `KERNEL32!GetLastError` at `0x1800096ed`
- `KERNEL32!GetCurrentThreadId` at `0x180009688`
- `KERNEL32!GetCurrentThreadId` at `0x180009688`
- `KERNEL32!UnregisterWaitEx` at `0x1800096be`
- `KERNEL32!UnregisterWaitEx` at `0x1800096e3`
- `KERNEL32!UnregisterWaitEx` at `0x1800096be`
- `KERNEL32!UnregisterWaitEx` at `0x1800096e3`
- `IisRTL!PuDbgPrint` at `0x180009736`
- `IisRTL!PuDbgPrint` at `0x180009736`

## string_xrefs

- `0x18000972f`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x18000971d`: `CADMCOMW::ShutdownCallerWatch`

## pseudocode

```c
__int64 __fastcall CADMCOMW::ShutdownCallerWatch(CADMCOMW *this)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // ebp
  signed __int32 v4; // eax
  signed __int32 v5; // r14d
  void *v6; // rcx
  void *v7; // rsi
  signed int LastError; // eax

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 48, CurrentThreadId, 0);
  v5 = v4;
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)this + 23, 0);
  if ( !v6 )
    goto LABEL_13;
  v7 = (void *)_InterlockedExchange64((volatile __int64 *)this + 22, 0);
  if ( v4 == CurrentThreadId )
  {
    if ( UnregisterWaitEx(v6, 0) )
      goto LABEL_11;
    if ( GetLastError() == 997 )
    {
      SetLastError(0);
      goto LABEL_11;
    }
LABEL_7:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7239,
        "CADMCOMW::ShutdownCallerWatch",
        "UnregisterWaitEx() failed hr=0x%08x.\n",
        v2);
    goto LABEL_11;
  }
  if ( !UnregisterWaitEx(v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    goto LABEL_7;
LABEL_11:
  if ( v7 )
    CloseHandle(v7);
LABEL_13:
  if ( !v5 )
    _InterlockedCompareExchange((volatile signed __int32 *)this + 48, 0, CurrentThreadId);
  return v2;
}

```

## disassembly

```asm
0x180009678  push    rbx
0x18000967a  push    rbp
0x18000967b  push    rsi
0x18000967c  push    rdi
0x18000967d  push    r14
0x18000967f  sub     rsp, 30h
0x180009683  mov     rdi, rcx
0x180009686  xor     ebx, ebx
0x180009688  call    cs:__imp_GetCurrentThreadId
0x18000968e  mov     ebp, eax
0x180009690  xor     eax, eax
0x180009692  lock cmpxchg [rdi+0C0h], ebp
0x18000969a  xor     ecx, ecx
0x18000969c  mov     r14d, eax
0x18000969f  xchg    rcx, [rdi+0B8h]; WaitHandle
0x1800096a6  test    rcx, rcx
0x1800096a9  jz      loc_18000974A
0x1800096af  xor     esi, esi
0x1800096b1  xchg    rsi, [rdi+0B0h]
0x1800096b8  cmp     eax, ebp
0x1800096ba  jnz     short loc_1800096DF
0x1800096bc  xor     edx, edx; CompletionEvent
0x1800096be  call    cs:__imp_UnregisterWaitEx
0x1800096c4  test    eax, eax
0x1800096c6  jnz     short loc_18000973C
0x1800096c8  call    cs:__imp_GetLastError
0x1800096ce  cmp     eax, 3E5h
0x1800096d3  jnz     short loc_1800096ED
0x1800096d5  xor     ecx, ecx; dwErrCode
0x1800096d7  call    cs:__imp_SetLastError
0x1800096dd  jmp     short loc_18000973C
0x1800096df  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800096e3  call    cs:__imp_UnregisterWaitEx
0x1800096e9  test    eax, eax
0x1800096eb  jnz     short loc_18000973C
0x1800096ed  call    cs:__imp_GetLastError
0x1800096f3  mov     ebx, eax
0x1800096f5  test    eax, eax
0x1800096f7  jle     short loc_180009702
0x1800096f9  movzx   ebx, ax
0x1800096fc  or      ebx, 80070000h
0x180009702  test    byte ptr cs:g_dwDebugFlags, 3
0x180009709  jz      short loc_18000973C
0x18000970b  mov     rcx, cs:g_pDebug
0x180009712  lea     rax, aUnregisterwait; "UnregisterWaitEx() failed hr=0x%08x.\n"
0x180009719  mov     [rsp+58h+var_30], ebx
0x18000971d  lea     r9, aCadmcomwShutdo; "CADMCOMW::ShutdownCallerWatch"
0x180009724  mov     r8d, 1C47h
0x18000972a  mov     [rsp+58h+var_38], rax
0x18000972f  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180009736  call    cs:__imp_PuDbgPrint
0x18000973c  test    rsi, rsi
0x18000973f  jz      short loc_18000974A
0x180009741  mov     rcx, rsi; hObject
0x180009744  call    cs:__imp_CloseHandle
0x18000974a  test    r14d, r14d
0x18000974d  jnz     short loc_18000975B
0x18000974f  xor     ecx, ecx
0x180009751  mov     eax, ebp
0x180009753  lock cmpxchg [rdi+0C0h], ecx
0x18000975b  mov     eax, ebx
0x18000975d  add     rsp, 30h
0x180009761  pop     r14
0x180009763  pop     rdi
0x180009764  pop     rsi
0x180009765  pop     rbp
0x180009766  pop     rbx
0x180009767  retn
```

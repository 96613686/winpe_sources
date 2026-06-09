# DYNAMIC_IP_RESTRICTION_TABLE::Initialize(void)

- ea: `0x180022ca0`
- end: `0x180022ea6`
- name: `?Initialize@DYNAMIC_IP_RESTRICTION_TABLE@@QEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800029fc`

## callees

- `0x180001210`
- `0x180022ca0`
- `0x18002331c`
- `0x180049010`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180022e31`
- `KERNEL32!CreateTimerQueueTimer` at `0x180022e31`
- `KERNEL32!CreateEventW` at `0x180022d55`
- `KERNEL32!CreateEventW` at `0x180022dae`
- `KERNEL32!CreateEventW` at `0x180022d55`
- `KERNEL32!CreateEventW` at `0x180022dae`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180022d3d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180022d9a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180022d3d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180022d9a`
- `KERNEL32!GetLastError` at `0x180022e3b`
- `KERNEL32!GetLastError` at `0x180022e3b`
- `KERNEL32!DeleteCriticalSection` at `0x180022dc3`
- `KERNEL32!DeleteCriticalSection` at `0x180022dcf`
- `KERNEL32!DeleteCriticalSection` at `0x180022dc3`
- `KERNEL32!DeleteCriticalSection` at `0x180022dcf`
- `iisutil!PuDbgPrintError` at `0x180022e84`
- `iisutil!PuDbgPrintError` at `0x180022e84`

## string_xrefs

- `0x180022e60`: `CreateTimerQueueTimer() failed\n`

## pseudocode

```c
__int64 __fastcall DYNAMIC_IP_RESTRICTION_TABLE::Initialize(char *Parameter)
{
  unsigned int v2; // ebx
  __int64 v3; // r14
  __int64 v4; // rbx
  char *v5; // rdi
  HANDLE EventW; // rax
  HANDLE v7; // rax
  signed int LastError; // eax

  v2 = STBUFF::Resize((STBUFF *)(Parameter + 8), 0x308u);
  if ( (v2 & 0x80000000) == 0 )
  {
    v3 = *((_QWORD *)Parameter + 2);
    v4 = 0;
    do
    {
      v5 = (char *)operator new(0x60u);
      if ( !v5 )
        return (unsigned int)-2147024882;
      *(_QWORD *)v5 = &STTABLE_BUCKET::`vftable';
      *((_DWORD *)v5 + 6) = 0;
      *((_QWORD *)v5 + 11) = 0;
      *((_QWORD *)v5 + 2) = v5 + 8;
      *((_QWORD *)v5 + 1) = v5 + 8;
      *((_QWORD *)v5 + 11) = CompareClientKeys;
      if ( !*((_DWORD *)v5 + 6) )
      {
        *(_QWORD *)(v5 + 28) = 0;
        if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v5 + 1, 0x64u) )
          goto LABEL_14;
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)v5 + 10) = EventW;
        if ( !EventW )
        {
          DeleteCriticalSection((LPCRITICAL_SECTION)v5 + 1);
LABEL_14:
          v2 = -2147467259;
          (**(void (__fastcall ***)(void *, __int64))v5)(v5, 1);
          return v2;
        }
        *((_DWORD *)v5 + 6) = 1;
      }
      *(_QWORD *)(v3 + 8 * v4) = v5;
      v4 = (unsigned int)(v4 + 1);
      ++*((_DWORD *)Parameter + 26);
    }
    while ( (unsigned int)v4 < 0x61 );
    if ( !*((_DWORD *)Parameter + 28) )
    {
      *(_QWORD *)(Parameter + 116) = 0;
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(Parameter + 128), 0x64u) )
      {
        v7 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)Parameter + 21) = v7;
        if ( v7 )
          *((_DWORD *)Parameter + 28) = 1;
        else
          DeleteCriticalSection((LPCRITICAL_SECTION)(Parameter + 128));
      }
    }
    *((_QWORD *)Parameter + 22) = KeyToHash;
    v2 = 0;
    if ( !CreateTimerQueueTimer(
            (PHANDLE)Parameter + 23,
            0,
            DYNAMIC_IP_RESTRICTION_TABLE::RemoveEntryScavengerCallback,
            Parameter,
            0x493E0u,
            0x493E0u,
            0x10u) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ip_restr\\dynamic_ip_restriction.cxx",
          335,
          "DYNAMIC_IP_RESTRICTION_TABLE::Initialize",
          v2,
          "CreateTimerQueueTimer() failed\n");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180022ca0  mov     [rsp+arg_8], rbx
0x180022ca5  mov     [rsp+arg_10], rbp
0x180022caa  push    rsi
0x180022cab  push    rdi
0x180022cac  push    r14
0x180022cae  sub     rsp, 40h
0x180022cb2  mov     rsi, rcx
0x180022cb5  mov     edx, 308h; unsigned int
0x180022cba  add     rcx, 8; this
0x180022cbe  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180022cc3  mov     ebx, eax
0x180022cc5  test    eax, eax
0x180022cc7  js      loc_180022E91
0x180022ccd  mov     r14, [rsi+10h]
0x180022cd1  xor     ebx, ebx
0x180022cd3  mov     ecx, 60h ; '`'; Size
0x180022cd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022cdd  mov     [rsp+58h+arg_0], rax
0x180022ce2  mov     rdi, rax
0x180022ce5  test    rax, rax
0x180022ce8  jz      loc_180022E8C
0x180022cee  lea     rax, ??_7STTABLE_BUCKET@@6B@; const STTABLE_BUCKET::`vftable'
0x180022cf5  mov     [rdi], rax
0x180022cf8  mov     dword ptr [rdi+18h], 0
0x180022cff  mov     qword ptr [rdi+58h], 0
0x180022d07  test    rdi, rdi
0x180022d0a  jz      loc_180022E8C
0x180022d10  lea     rax, [rdi+8]
0x180022d14  mov     [rdi+10h], rax
0x180022d18  mov     [rax], rax
0x180022d1b  lea     rax, ?CompareClientKeys@@YAHPEAVSTBUFF@@0@Z; CompareClientKeys(STBUFF *,STBUFF *)
0x180022d22  mov     [rdi+58h], rax
0x180022d26  cmp     dword ptr [rdi+18h], 0
0x180022d2a  jnz     short loc_180022D6B
0x180022d2c  mov     edx, 64h ; 'd'; dwSpinCount
0x180022d31  mov     qword ptr [rdi+1Ch], 0
0x180022d39  lea     rcx, [rdi+28h]; lpCriticalSection
0x180022d3d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180022d43  test    eax, eax
0x180022d45  jz      loc_180022DD5
0x180022d4b  xor     r9d, r9d; lpName
0x180022d4e  xor     r8d, r8d; bInitialState
0x180022d51  xor     edx, edx; bManualReset
0x180022d53  xor     ecx, ecx; lpEventAttributes
0x180022d55  call    cs:__imp_CreateEventW
0x180022d5b  mov     [rdi+50h], rax
0x180022d5f  test    rax, rax
0x180022d62  jz      short loc_180022DCB
0x180022d64  mov     dword ptr [rdi+18h], 1
0x180022d6b  mov     [r14+rbx*8], rdi
0x180022d6f  inc     ebx
0x180022d71  inc     dword ptr [rsi+68h]
0x180022d74  cmp     ebx, 61h ; 'a'
0x180022d77  jb      loc_180022CD3
0x180022d7d  cmp     dword ptr [rsi+70h], 0
0x180022d81  jnz     short loc_180022DF9
0x180022d83  lea     rbx, [rsi+80h]
0x180022d8a  mov     qword ptr [rsi+74h], 0
0x180022d92  mov     rcx, rbx; lpCriticalSection
0x180022d95  mov     edx, 64h ; 'd'; dwSpinCount
0x180022d9a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180022da0  test    eax, eax
0x180022da2  jz      short loc_180022DF9
0x180022da4  xor     r9d, r9d; lpName
0x180022da7  xor     r8d, r8d; bInitialState
0x180022daa  xor     edx, edx; bManualReset
0x180022dac  xor     ecx, ecx; lpEventAttributes
0x180022dae  call    cs:__imp_CreateEventW
0x180022db4  mov     [rsi+0A8h], rax
0x180022dbb  test    rax, rax
0x180022dbe  jnz     short loc_180022DF2
0x180022dc0  mov     rcx, rbx; lpCriticalSection
0x180022dc3  call    cs:__imp_DeleteCriticalSection
0x180022dc9  jmp     short loc_180022DF9
0x180022dcb  lea     rcx, [rdi+28h]; lpCriticalSection
0x180022dcf  call    cs:__imp_DeleteCriticalSection
0x180022dd5  mov     rax, [rdi]
0x180022dd8  mov     edx, 1
0x180022ddd  mov     rcx, rdi
0x180022de0  mov     ebx, 80004005h
0x180022de5  mov     rax, [rax]
0x180022de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ded  jmp     loc_180022E91
0x180022df2  mov     dword ptr [rsi+70h], 1
0x180022df9  lea     rax, ?KeyToHash@@YAKPEAVSTBUFF@@@Z; KeyToHash(STBUFF *)
0x180022e00  mov     [rsp+58h+Flags], 10h; Flags
0x180022e08  mov     [rsi+0B0h], rax
0x180022e0f  lea     rcx, [rsi+0B8h]; phNewTimer
0x180022e16  mov     eax, 493E0h
0x180022e1b  lea     r8, ?RemoveEntryScavengerCallback@DYNAMIC_IP_RESTRICTION_TABLE@@SAXPEAXH@Z; Callback
0x180022e22  mov     [rsp+58h+Period], eax; Period
0x180022e26  mov     r9, rsi; Parameter
0x180022e29  xor     edx, edx; TimerQueue
0x180022e2b  mov     [rsp+58h+DueTime], eax; DueTime
0x180022e2f  xor     ebx, ebx
0x180022e31  call    cs:__imp_CreateTimerQueueTimer
0x180022e37  test    eax, eax
0x180022e39  jnz     short loc_180022E91
0x180022e3b  call    cs:__imp_GetLastError
0x180022e41  mov     ebx, eax
0x180022e43  test    eax, eax
0x180022e45  jle     short loc_180022E50
0x180022e47  movzx   ebx, ax
0x180022e4a  or      ebx, 80070000h
0x180022e50  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180022e57  jz      short loc_180022E91
0x180022e59  mov     rcx, cs:g_pDebug
0x180022e60  lea     rax, aCreatetimerque; "CreateTimerQueueTimer() failed\n"
0x180022e67  mov     qword ptr [rsp+58h+Period], rax
0x180022e6c  lea     r9, aDynamicIpRestr_2; "DYNAMIC_IP_RESTRICTION_TABLE::Initializ"...
0x180022e73  mov     r8d, 14Fh
0x180022e79  mov     [rsp+58h+DueTime], ebx
0x180022e7d  lea     rdx, aInetsrvIisIisr_10; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180022e84  call    cs:__imp_PuDbgPrintError
0x180022e8a  jmp     short loc_180022E91
0x180022e8c  mov     ebx, 8007000Eh
0x180022e91  mov     rbp, [rsp+58h+arg_10]
0x180022e96  mov     eax, ebx
0x180022e98  mov     rbx, [rsp+58h+arg_8]
0x180022e9d  add     rsp, 40h
0x180022ea1  pop     r14
0x180022ea3  pop     rdi
0x180022ea4  pop     rsi
0x180022ea5  retn
```

# APPLICATION_MANAGER::Create(ushort const *,ushort const *,MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,int,ushort const *,FastCgiApplicationStdErrMode)

- ea: `0x18000773c`
- end: `0x1800078c6`
- name: `?Create@APPLICATION_MANAGER@@QEAAJPEBG0PEAVMULTISZ@@HKKKKKKKHKH0W4FastCgiApplicationStdErrMode@@@Z`
- size: `394`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, struct MULTISZ *, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, unsigned int, int, const unsigned __int16 *, enum FastCgiApplicationStdErrMode)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009eb4`

## callees

- `0x18000773c`
- `0x180007b00`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000775b`
- `msvcrt!wcsrchr` at `0x18000775b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007885`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007885`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180007892`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180007892`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000779d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800077b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000779d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800077b7`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x1800077d6`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x1800077d6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007783`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007783`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::Create(
        __int64 a1,
        const wchar_t *a2,
        const unsigned __int16 *a3,
        const struct MULTISZ *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        __int64 a15,
        __int64 a16,
        int a17)
{
  wchar_t *v21; // rax
  int inited; // ebx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax

  v21 = wcsrchr(a2, 0x5Cu);
  if ( !v21 )
    return (unsigned int)-2147024883;
  inited = STRU::Copy((STRU *)(a1 + 392), a2, v21 - a2);
  if ( inited >= 0 )
  {
    inited = STRU::Copy((STRU *)(a1 + 160), a2);
    if ( inited >= 0 )
    {
      inited = STRU::Copy((STRU *)(a1 + 216), a3);
      if ( inited >= 0 )
      {
        if ( a4 && !MULTISZ::Copy((MULTISZ *)(a1 + 336), a4) )
          return (unsigned int)-2147024883;
        *(_DWORD *)(a1 + 504) = 1;
        inited = APPLICATION_MANAGER::InitCommon(a1, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a16, a17);
        if ( inited >= 0 )
        {
          if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 16), 0x3E8u)
            || (*(_DWORD *)(a1 + 56) = 1, TimerQueue = CreateTimerQueue(), (*(_QWORD *)(a1 + 152) = TimerQueue) == 0) )
          {
            LastError = GetLastError();
            inited = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000773c  push    rbx
0x18000773e  push    rbp
0x18000773f  push    rsi
0x180007740  push    rdi
0x180007741  push    r14
0x180007743  sub     rsp, 70h
0x180007747  mov     rsi, rdx
0x18000774a  mov     rdi, rcx
0x18000774d  mov     rcx, rsi; Str
0x180007750  mov     edx, 5Ch ; '\'; Ch
0x180007755  mov     rbp, r9
0x180007758  mov     r14, r8
0x18000775b  call    cs:__imp_wcsrchr
0x180007761  test    rax, rax
0x180007764  jnz     short loc_180007770
0x180007766  mov     ebx, 8007000Dh
0x18000776b  jmp     loc_1800078B9
0x180007770  sub     rax, rsi
0x180007773  lea     rcx, [rdi+188h]
0x18000777a  sar     rax, 1
0x18000777d  mov     rdx, rsi
0x180007780  mov     r8d, eax
0x180007783  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180007789  mov     ebx, eax
0x18000778b  test    eax, eax
0x18000778d  js      loc_1800078B9
0x180007793  lea     rcx, [rdi+0A0h]
0x18000779a  mov     rdx, rsi
0x18000779d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800077a3  mov     ebx, eax
0x1800077a5  test    eax, eax
0x1800077a7  js      loc_1800078B9
0x1800077ad  lea     rcx, [rdi+0D8h]
0x1800077b4  mov     rdx, r14
0x1800077b7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800077bd  mov     ebx, eax
0x1800077bf  test    eax, eax
0x1800077c1  js      loc_1800078B9
0x1800077c7  test    rbp, rbp
0x1800077ca  jz      short loc_1800077E0
0x1800077cc  lea     rcx, [rdi+150h]
0x1800077d3  mov     rdx, rbp
0x1800077d6  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x1800077dc  test    eax, eax
0x1800077de  jz      short loc_180007766
0x1800077e0  mov     eax, [rsp+98h+arg_80]
0x1800077e7  mov     esi, 1
0x1800077ec  mov     r9d, [rsp+98h+arg_28]
0x1800077f4  mov     rdx, rbp
0x1800077f7  mov     r8d, [rsp+98h+arg_20]
0x1800077ff  mov     rcx, rdi
0x180007802  mov     [rsp+98h+var_30], eax
0x180007806  mov     rax, [rsp+98h+arg_78]
0x18000780e  mov     [rsp+98h+var_38], rax
0x180007813  mov     eax, [rsp+98h+arg_68]
0x18000781a  mov     [rsp+98h+var_40], eax
0x18000781e  mov     eax, [rsp+98h+arg_60]
0x180007825  mov     [rsp+98h+var_48], eax
0x180007829  mov     eax, [rsp+98h+arg_58]
0x180007830  mov     [rsp+98h+var_50], eax
0x180007834  mov     eax, [rsp+98h+arg_50]
0x18000783b  mov     [rsp+98h+var_58], eax
0x18000783f  mov     eax, [rsp+98h+arg_48]
0x180007846  mov     [rsp+98h+var_60], eax
0x18000784a  mov     eax, [rsp+98h+arg_40]
0x180007851  mov     [rsp+98h+var_68], eax
0x180007855  mov     eax, [rsp+98h+arg_38]
0x18000785c  mov     [rsp+98h+var_70], eax
0x180007860  mov     eax, [rsp+98h+arg_30]
0x180007867  mov     [rsp+98h+var_78], eax
0x18000786b  mov     [rdi+1F8h], esi
0x180007871  call    ?InitCommon@APPLICATION_MANAGER@@QEAAJPEAVMULTISZ@@HKKKKKKKHKPEBGW4FastCgiApplicationStdErrMode@@@Z; APPLICATION_MANAGER::InitCommon(MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,ushort const *,FastCgiApplicationStdErrMode)
0x180007876  mov     ebx, eax
0x180007878  test    eax, eax
0x18000787a  js      short loc_1800078B9
0x18000787c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180007880  mov     edx, 3E8h; dwSpinCount
0x180007885  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000788b  test    eax, eax
0x18000788d  jz      short loc_1800078A4
0x18000788f  mov     [rdi+38h], esi
0x180007892  call    cs:__imp_CreateTimerQueue
0x180007898  mov     [rdi+98h], rax
0x18000789f  test    rax, rax
0x1800078a2  jnz     short loc_1800078B9
0x1800078a4  call    cs:__imp_GetLastError
0x1800078aa  mov     ebx, eax
0x1800078ac  test    eax, eax
0x1800078ae  jle     short loc_1800078B9
0x1800078b0  movzx   ebx, ax
0x1800078b3  or      ebx, 80070000h
0x1800078b9  mov     eax, ebx
0x1800078bb  add     rsp, 70h
0x1800078bf  pop     r14
0x1800078c1  pop     rdi
0x1800078c2  pop     rsi
0x1800078c3  pop     rbp
0x1800078c4  pop     rbx
0x1800078c5  retn
```

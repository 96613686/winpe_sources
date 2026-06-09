# TmSnapshotDiagnostics::TraceW(TRACE_LEVEL,long,void *,ushort *)

- ea: `0x18002523c`
- end: `0x180025353`
- name: `?TraceW@TmSnapshotDiagnostics@@SAXW4TRACE_LEVEL@@JPEAXPEAG@Z`
- size: `279`
- prototype: ``
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x1800257d8`
- `0x180025cb4`
- `0x180025e18`
- `0x180025e74`
- `0x180025ed0`
- `0x180025f2c`
- `0x180025f88`
- `0x180025fe4`
- `0x1800261b0`
- `0x180026560`
- `0x180026660`
- `0x1800267a4`
- `0x1800268a0`
- `0x180026930`
- `0x1800269b0`
- `0x180026a30`
- `0x180026b00`
- `0x180026bc0`
- `0x180026c40`
- `0x180026cd0`
- `0x180026d00`
- `0x180026df0`
- `0x180026e60`
- `0x180026ee0`
- `0x180026f20`
- `0x180026ff0`
- `0x180027110`
- `0x180027190`
- `0x1800272ac`
- `0x180027340`
- `0x18002739c`
- `0x1800273f8`
- `0x180027660`
- `0x180027874`
- `0x180027960`
- `0x1800279f0`
- `0x180027a70`
- `0x180027b20`
- `0x180027bc0`
- `0x180027c30`
- `0x180027c90`
- `0x180027ce0`
- `0x180027d40`
- `0x180027de0`
- `0x180027e60`

## callees

- `0x18002523c`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180025290`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180025290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252d2`
- `msvcrt!fclose` at `0x180025325`
- `msvcrt!fclose` at `0x180025325`
- `msvcrt!fflush` at `0x18002531c`
- `msvcrt!fflush` at `0x18002531c`
- `msvcrt!fwprintf` at `0x180025313`
- `msvcrt!fwprintf` at `0x180025313`
- `msvcrt!fopen` at `0x1800252a4`
- `msvcrt!fopen` at `0x1800252a4`

## pseudocode

```c
void __fastcall TmSnapshotDiagnostics::TraceW(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  FILE *v5; // r12
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // ebp
  unsigned int wDay; // r14d
  unsigned int wMonth; // r15d
  int v12; // [rsp+20h] [rbp-98h]
  int v13; // [rsp+28h] [rbp-90h]
  int v14; // [rsp+30h] [rbp-88h]
  int v15; // [rsp+38h] [rbp-80h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-78h]
  int v17; // [rsp+50h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-50h] BYREF

  if ( TmSnapshotDiagnostics::m_fIsInitialized && TmSnapshotDiagnostics::m_dwTraceLevel >= a1 )
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v5 = fopen(&TmSnapshotDiagnostics::m_pszFullName, "a+");
    if ( v5 )
    {
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      v17 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v15 = wMilliseconds;
      v14 = wSecond;
      v13 = wMinute;
      v12 = wHour;
      fwprintf(
        v5,
        L"%02ld-%02ld-%02ld:%02ld:%02ld:%04ld(%d), this = 0x%p, hr = %d, %s\n",
        wMonth,
        wDay,
        v12,
        v13,
        v14,
        v15,
        CurrentThreadId,
        a3,
        v17,
        a4);
      fflush(v5);
      fclose(v5);
    }
  }
}

```

## disassembly

```asm
0x18002523c  mov     [rsp+arg_0], rbx
0x180025241  push    rbp
0x180025242  push    rsi
0x180025243  push    rdi
0x180025244  push    r12
0x180025246  push    r13
0x180025248  push    r14
0x18002524a  push    r15
0x18002524c  sub     rsp, 80h
0x180025253  mov     rax, cs:__security_cookie
0x18002525a  xor     rax, rsp
0x18002525d  mov     [rsp+0B8h+var_40], rax
0x180025262  cmp     cs:?m_fIsInitialized@TmSnapshotDiagnostics@@0HA, 0; int TmSnapshotDiagnostics::m_fIsInitialized
0x180025269  mov     r13, r8
0x18002526c  mov     [rsp+0B8h+var_58], r9
0x180025271  jz      loc_18002532B
0x180025277  cmp     cs:?m_dwTraceLevel@TmSnapshotDiagnostics@@0W4TRACE_LEVEL@@A, ecx; TRACE_LEVEL TmSnapshotDiagnostics::m_dwTraceLevel
0x18002527d  jl      loc_18002532B
0x180025283  xorps   xmm0, xmm0
0x180025286  lea     rcx, [rsp+0B8h+SystemTime]; lpSystemTime
0x18002528b  movups  xmmword ptr [rsp+0B8h+SystemTime.wYear], xmm0
0x180025290  call    cs:__imp_GetLocalTime
0x180025296  lea     rdx, Mode; "a+"
0x18002529d  lea     rcx, ?m_pszFullName@TmSnapshotDiagnostics@@0PADA; FileName
0x1800252a4  call    cs:__imp_fopen
0x1800252aa  mov     r12, rax
0x1800252ad  test    rax, rax
0x1800252b0  jz      short loc_18002532B
0x1800252b2  movzx   ebx, [rsp+0B8h+SystemTime.wMilliseconds]
0x1800252b7  movzx   edi, [rsp+0B8h+SystemTime.wSecond]
0x1800252bc  movzx   esi, [rsp+0B8h+SystemTime.wMinute]
0x1800252c1  movzx   ebp, [rsp+0B8h+SystemTime.wHour]
0x1800252c6  movzx   r14d, [rsp+0B8h+SystemTime.wDay]
0x1800252cc  movzx   r15d, [rsp+0B8h+SystemTime.wMonth]
0x1800252d2  call    cs:__imp_GetCurrentThreadId
0x1800252d8  mov     rcx, [rsp+0B8h+var_58]
0x1800252dd  lea     rdx, a02ld02ld02ld02; "%02ld-%02ld-%02ld:%02ld:%02ld:%04ld(%d)"...
0x1800252e4  mov     [rsp+0B8h+var_60], rcx
0x1800252e9  mov     r9d, r14d
0x1800252ec  mov     [rsp+0B8h+var_68], 0
0x1800252f4  mov     r8d, r15d
0x1800252f7  mov     [rsp+0B8h+var_70], r13
0x1800252fc  mov     rcx, r12; Stream
0x1800252ff  mov     [rsp+0B8h+var_78], eax
0x180025303  mov     [rsp+0B8h+var_80], ebx
0x180025307  mov     [rsp+0B8h+var_88], edi
0x18002530b  mov     [rsp+0B8h+var_90], esi
0x18002530f  mov     [rsp+0B8h+var_98], ebp
0x180025313  call    cs:__imp_fwprintf
0x180025319  mov     rcx, r12; Stream
0x18002531c  call    cs:__imp_fflush
0x180025322  mov     rcx, r12; Stream
0x180025325  call    cs:__imp_fclose
0x18002532b  mov     rcx, [rsp+0B8h+var_40]
0x180025330  xor     rcx, rsp; StackCookie
0x180025333  call    __security_check_cookie
0x180025338  mov     rbx, [rsp+0B8h+arg_0]
0x180025340  add     rsp, 80h
0x180025347  pop     r15
0x180025349  pop     r14
0x18002534b  pop     r13
0x18002534d  pop     r12
0x18002534f  pop     rdi
0x180025350  pop     rsi
0x180025351  pop     rbp
0x180025352  retn
```

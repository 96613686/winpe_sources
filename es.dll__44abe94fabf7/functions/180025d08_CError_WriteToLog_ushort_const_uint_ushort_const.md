# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x180025d08`
- end: `0x180025f09`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `513`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025c58`
- `0x18002c73c`

## callees

- `0x180006194`
- `0x180018930`
- `0x180025d08`
- `0x180025f10`
- `0x18002600c`
- `0x180026170`
- `0x18002c594`
- `0x180038da8`
- `0x1800418e0`
- `0x18004192c`
- `0x180041fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025e8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025e8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ec4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ed1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ede`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ec4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ed1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ede`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025e6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025e6d`

## string_xrefs

- `0x180025ea5`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, const unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const unsigned __int16 *v4; // rax
  int v8; // r15d
  int v9; // r14d
  unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // r8
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  unsigned int v17; // r8d
  unsigned __int16 *v18; // r9
  void *v19; // r8
  unsigned __int64 v20; // r9
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // ebx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  unsigned __int16 v27; // [rsp+20h] [rbp-78h]
  unsigned int *v28; // [rsp+20h] [rbp-78h]
  unsigned __int16 v29[2]; // [rsp+40h] [rbp-58h] BYREF
  int v30; // [rsp+44h] [rbp-54h]
  __int64 v31; // [rsp+48h] [rbp-50h]
  unsigned __int16 *v32; // [rsp+50h] [rbp-48h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  v8 = 0;
  v9 = 0;
  v30 = 0;
  if ( dword_1800642A0 )
  {
    EnterCriticalSection(&CriticalSection);
    v9 = 1;
    v30 = 1;
    v4 = a4;
  }
  v10 = 0;
  word_1800648A0 = 0;
  if ( v4 )
  {
    StringCchVPrintfW(&word_1800648A0, 0x3FDu, v4, va);
    word_18006509A = 0;
    v31 = 0;
    v10 = (unsigned __int16 *)word_1800648A0;
  }
  if ( (_WORD)v10 )
    StringCchCatW(&word_1800648A0, 0x400u, L"\r\n");
  v11 = -1;
  do
    ++v11;
  while ( *(&word_1800648A0 + v11) );
  *(_DWORD *)v29 = 1024 - v11;
  AppendApplicationInfo(v10, (unsigned int)a2, (unsigned int *)v29);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v13, v12, (unsigned int *)v29);
  AppendHResult(*(_DWORD *)this, v12, v14, (unsigned int *)v29);
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v17, v18, (unsigned int *)v29);
  AppendComsvcsFileVersion(v16, v15, (unsigned int *)v29);
  v32 = &word_1800648A0;
  LogIt(*((_WORD *)this + 2), *((_DWORD *)this + 2), v19, v20, v27, (const unsigned __int16 **const)&v32);
  v23 = 3221225472LL;
  LOBYTE(v8) = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v9 )
    LeaveCriticalSection(&CriticalSection);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      v24 = *(_DWORD *)this;
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      LODWORD(v28) = CurrentThreadId;
      StringCchPrintfW(
        &word_1800658C0,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        v28,
        a2,
        a3,
        v24);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_1800658C0);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v23, v21, v22, v8, *((_DWORD *)this + 11));
  }
}

```

## disassembly

```asm
0x180025d08  mov     [rsp+arg_18], r9
0x180025d0d  push    rbx
0x180025d0e  push    rsi
0x180025d0f  push    rdi
0x180025d10  push    r12
0x180025d12  push    r13
0x180025d14  push    r14
0x180025d16  push    r15
0x180025d18  sub     rsp, 60h
0x180025d1c  mov     rax, r9
0x180025d1f  mov     r12d, r8d
0x180025d22  mov     r13, rdx
0x180025d25  mov     rsi, rcx
0x180025d28  xor     r15d, r15d
0x180025d2b  mov     r14d, r15d
0x180025d2e  mov     [rsp+98h+var_54], r15d
0x180025d33  cmp     cs:dword_1800642A0, r15d
0x180025d3a  jz      short loc_180025D5A
0x180025d3c  lea     rcx, CriticalSection; lpCriticalSection
0x180025d43  call    cs:__imp_EnterCriticalSection
0x180025d49  lea     r14d, [r15+1]
0x180025d4d  mov     [rsp+98h+var_54], r14d
0x180025d52  mov     rax, [rsp+98h+arg_18]
0x180025d5a  mov     ecx, r15d
0x180025d5d  mov     cs:word_1800648A0, cx
0x180025d64  lea     rdi, word_1800648A0
0x180025d6b  test    rax, rax
0x180025d6e  jz      short loc_180025DA1
0x180025d70  mov     [rsp+98h+var_50], r15
0x180025d75  lea     r9, [rsp+98h+arg_20]; char *
0x180025d7d  mov     r8, rax; unsigned __int16 *
0x180025d80  mov     edx, 3FDh; unsigned __int64
0x180025d85  mov     rcx, rdi; unsigned __int16 *
0x180025d88  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180025d8d  mov     cs:word_18006509A, r15w
0x180025d95  mov     [rsp+98h+var_50], r15
0x180025d9a  movzx   ecx, cs:word_1800648A0
0x180025da1  mov     ebx, 400h
0x180025da6  test    cx, cx
0x180025da9  jz      short loc_180025DBC
0x180025dab  lea     r8, asc_1800594A0; "\r\n"
0x180025db2  mov     edx, ebx; unsigned __int64
0x180025db4  mov     rcx, rdi; unsigned __int16 *
0x180025db7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025dbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025dc0  inc     rax
0x180025dc3  cmp     [rdi+rax*2], r15w
0x180025dc8  jnz     short loc_180025DC0
0x180025dca  sub     ebx, eax
0x180025dcc  mov     dword ptr [rsp+98h+var_58], ebx
0x180025dd0  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180025dd5  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x180025dda  cmp     [rsi+28h], r15d
0x180025dde  jz      short loc_180025DEA
0x180025de0  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180025de5  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x180025dea  lea     r9, [rsp+98h+var_58]; unsigned int *
0x180025def  mov     ecx, [rsi]; dwMessageId
0x180025df1  call    ?AppendHResult@@YAXJKPEAGPEAI@Z; AppendHResult(long,ulong,ushort *,uint *)
0x180025df6  cmp     [rsi], r15d
0x180025df9  jnz     short loc_180025E01
0x180025dfb  cmp     [rsi+28h], r15d
0x180025dff  jz      short loc_180025E16
0x180025e01  lea     rax, [rsp+98h+var_58]
0x180025e06  mov     [rsp+98h+var_78], rax; unsigned __int16
0x180025e0b  mov     edx, r12d; unsigned int
0x180025e0e  mov     rcx, r13; unsigned __int16 *
0x180025e11  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x180025e16  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180025e1b  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x180025e20  mov     [rsp+98h+var_48], rdi
0x180025e25  lea     rax, [rsp+98h+var_48]
0x180025e2a  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x180025e2f  mov     edx, [rsi+8]; unsigned int
0x180025e32  movzx   ecx, word ptr [rsi+4]; unsigned __int16
0x180025e36  call    ?LogIt@@YAXGKPEAX_KGQEAPEBG@Z; LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)
0x180025e3b  mov     eax, [rsi+8]
0x180025e3e  mov     ecx, 0C0000000h
0x180025e43  and     eax, ecx
0x180025e45  cmp     eax, ecx
0x180025e47  setz    r15b
0x180025e4b  test    r14d, r14d
0x180025e4e  jz      short loc_180025E5D
0x180025e50  lea     rcx, CriticalSection; lpCriticalSection
0x180025e57  call    cs:__imp_LeaveCriticalSection
0x180025e5d  cmp     dword ptr [rsi+28h], 0
0x180025e61  jz      loc_180025EF9
0x180025e67  cmp     dword ptr [rsi+2Ch], 0
0x180025e6b  jz      short loc_180025EE4
0x180025e6d  call    cs:__imp_IsDebuggerPresent
0x180025e73  test    eax, eax
0x180025e75  jnz     short loc_180025E80
0x180025e77  cmp     ds:7FFE02D4h, al
0x180025e7e  jz      short loc_180025EE4
0x180025e80  mov     ebx, [rsi]
0x180025e82  call    cs:__imp_GetCurrentThreadId
0x180025e88  mov     edi, eax
0x180025e8a  call    cs:__imp_GetCurrentProcessId
0x180025e90  mov     [rsp+98h+var_60], ebx
0x180025e94  mov     [rsp+98h+var_68], r12d
0x180025e99  mov     [rsp+98h+var_70], r13; struct _EXCEPTION_POINTERS *
0x180025e9e  mov     dword ptr [rsp+98h+var_78], edi
0x180025ea2  mov     r9d, eax
0x180025ea5  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x180025eac  mov     edx, 3FFh; unsigned __int64
0x180025eb1  lea     rcx, word_1800658C0; unsigned __int16 *
0x180025eb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025ebd  lea     rcx, OutputString; "\n#####################################"...
0x180025ec4  call    cs:__imp_OutputDebugStringW
0x180025eca  lea     rcx, word_1800658C0; lpOutputString
0x180025ed1  call    cs:__imp_OutputDebugStringW
0x180025ed7  lea     rcx, asc_1800595F0; "#######################################"...
0x180025ede  call    cs:__imp_OutputDebugStringW
0x180025ee4  cmp     dword ptr [rsi+28h], 0
0x180025ee8  jz      short loc_180025EF9
0x180025eea  mov     eax, [rsi+2Ch]
0x180025eed  mov     dword ptr [rsp+98h+var_78], eax; int
0x180025ef1  mov     r9d, r15d; int
0x180025ef4  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x180025ef9  add     rsp, 60h
0x180025efd  pop     r15
0x180025eff  pop     r14
0x180025f01  pop     r13
0x180025f03  pop     r12
0x180025f05  pop     rdi
0x180025f06  pop     rsi
0x180025f07  pop     rbx
0x180025f08  retn
0x180045141  push    rbp
0x180045143  sub     rsp, 40h
0x180045147  mov     rbp, rdx
0x18004514a  cmp     dword ptr [rbp+44h], 0
0x18004514e  jz      short loc_18004515E
0x180045150  lea     rcx, CriticalSection; lpCriticalSection
0x180045157  call    cs:__imp_LeaveCriticalSection
0x18004515d  nop
0x18004515e  add     rsp, 40h
0x180045162  pop     rbp
0x180045163  retn
```

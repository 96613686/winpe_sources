# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x18000fca8`
- end: `0x18000fecf`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `551`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e64c`
- `0x18000ed38`

## callees

- `0x18000abd4`
- `0x18000e000`
- `0x18000e828`
- `0x18000ea1c`
- `0x18000eb18`
- `0x18000eb9c`
- `0x18000ec8c`
- `0x18000f654`
- `0x18000f9d0`
- `0x18000fca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001438b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001438b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fe8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fe97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fea4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fe8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fe97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fea4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fe32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fe32`
- `msvcrt!_vsnwprintf` at `0x18000fd2e`
- `msvcrt!_vsnwprintf` at `0x18000fd2e`

## string_xrefs

- `0x18000fe6b`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, const unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const wchar_t *v4; // rax
  int v8; // edi
  unsigned __int16 *v9; // rcx
  unsigned int v10; // eax
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
  BOOL v24; // r14d
  int v25; // ebx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  unsigned __int16 v28; // [rsp+20h] [rbp-78h]
  unsigned int *v29; // [rsp+20h] [rbp-78h]
  unsigned int v30; // [rsp+40h] [rbp-58h] BYREF
  int v31; // [rsp+44h] [rbp-54h]
  int v32; // [rsp+48h] [rbp-50h]
  __int64 v33; // [rsp+50h] [rbp-48h]
  unsigned __int16 *v34; // [rsp+58h] [rbp-40h] BYREF
  va_list Args; // [rsp+C0h] [rbp+28h] BYREF

  va_start(Args, a4);
  v4 = a4;
  v8 = 0;
  v31 = 0;
  if ( dword_18001F980 )
  {
    EnterCriticalSection(&stru_18001F958);
    v8 = 1;
    v31 = 1;
    v4 = a4;
  }
  v9 = 0;
  word_18001FCC0 = 0;
  if ( v4 )
  {
    v33 = 0;
    v32 = 0;
    v10 = _vsnwprintf(&word_18001FCC0, 0x3FCu, v4, Args);
    if ( v10 > 0x3FC )
    {
      v32 = -2147024774;
    }
    else if ( v10 != 1020 )
    {
LABEL_9:
      word_1800204BA = 0;
      v33 = 0;
      v9 = (unsigned __int16 *)word_18001FCC0;
      goto LABEL_10;
    }
    word_1800204B8 = 0;
    goto LABEL_9;
  }
LABEL_10:
  if ( (_WORD)v9 )
    StringCchCatW(&word_18001FCC0, 1024, L"\r\n");
  v11 = -1;
  do
    ++v11;
  while ( *(&word_18001FCC0 + v11) );
  v30 = 1024 - v11;
  AppendApplicationInfo(v9, (unsigned int)a2, &v30);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v13, v12, &v30);
  AppendHResult(*(_DWORD *)this, v12, v14, &v30);
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v17, v18, &v30);
  AppendComsvcsFileVersion(v16, v15, &v30);
  v34 = &word_18001FCC0;
  LogIt(*((_WORD *)this + 2), *((_DWORD *)this + 2), v19, v20, v28, (const unsigned __int16 **const)&v34);
  v23 = 3221225472LL;
  v24 = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v8 )
    LeaveCriticalSection(&stru_18001F958);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      v25 = *(_DWORD *)this;
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      LODWORD(v29) = CurrentThreadId;
      StringCchPrintfW(
        &word_180020CE0,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        v29,
        a2,
        a3,
        v25);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_180020CE0);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v23, v21, v22, v24, *((_DWORD *)this + 11));
  }
}

```

## disassembly

```asm
0x18000fca8  mov     [rsp+arg_18], r9
0x18000fcad  push    rbx
0x18000fcae  push    rsi
0x18000fcaf  push    rdi
0x18000fcb0  push    r12
0x18000fcb2  push    r13
0x18000fcb4  push    r14
0x18000fcb6  push    r15
0x18000fcb8  sub     rsp, 60h
0x18000fcbc  mov     rax, r9
0x18000fcbf  mov     r15d, r8d
0x18000fcc2  mov     r12, rdx
0x18000fcc5  mov     rsi, rcx
0x18000fcc8  xor     r13d, r13d
0x18000fccb  mov     edi, r13d
0x18000fcce  mov     [rsp+98h+var_54], r13d
0x18000fcd3  cmp     cs:dword_18001F980, r13d
0x18000fcda  jz      short loc_18000FCF9
0x18000fcdc  lea     rcx, stru_18001F958; lpCriticalSection
0x18000fce3  call    cs:__imp_EnterCriticalSection
0x18000fce9  lea     edi, [r13+1]
0x18000fced  mov     [rsp+98h+var_54], edi
0x18000fcf1  mov     rax, [rsp+98h+arg_18]
0x18000fcf9  mov     ecx, r13d
0x18000fcfc  mov     cs:word_18001FCC0, cx
0x18000fd03  lea     r14, word_18001FCC0
0x18000fd0a  test    rax, rax
0x18000fd0d  jz      short loc_18000FD64
0x18000fd0f  mov     [rsp+98h+var_48], r13
0x18000fd14  lea     r9, [rsp+98h+Args]; Args
0x18000fd1c  mov     [rsp+98h+var_50], r13d
0x18000fd21  mov     r8, rax; Format
0x18000fd24  mov     ebx, 3FCh
0x18000fd29  mov     edx, ebx; BufferCount
0x18000fd2b  mov     rcx, r14; Buffer
0x18000fd2e  call    cs:__imp__vsnwprintf
0x18000fd34  test    eax, eax
0x18000fd36  js      short loc_18000FD40
0x18000fd38  cmp     eax, ebx
0x18000fd3a  ja      short loc_18000FD40
0x18000fd3c  jnz     short loc_18000FD50
0x18000fd3e  jmp     short loc_18000FD48
0x18000fd40  mov     [rsp+98h+var_50], 8007007Ah
0x18000fd48  mov     cs:word_1800204B8, r13w
0x18000fd50  mov     cs:word_1800204BA, r13w
0x18000fd58  mov     [rsp+98h+var_48], r13
0x18000fd5d  movzx   ecx, cs:word_18001FCC0
0x18000fd64  mov     ebx, 400h
0x18000fd69  test    cx, cx
0x18000fd6c  jz      short loc_18000FD7F
0x18000fd6e  lea     r8, asc_180018FA0; "\r\n"
0x18000fd75  mov     edx, ebx; unsigned __int64
0x18000fd77  mov     rcx, r14; unsigned __int16 *
0x18000fd7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fd7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fd83  inc     rax
0x18000fd86  cmp     [r14+rax*2], r13w
0x18000fd8b  jnz     short loc_18000FD83
0x18000fd8d  sub     ebx, eax
0x18000fd8f  mov     [rsp+98h+var_58], ebx
0x18000fd93  lea     r8, [rsp+98h+var_58]; unsigned int *
0x18000fd98  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x18000fd9d  cmp     [rsi+28h], r13d
0x18000fda1  jz      short loc_18000FDAD
0x18000fda3  lea     r8, [rsp+98h+var_58]; unsigned int *
0x18000fda8  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x18000fdad  lea     r9, [rsp+98h+var_58]; unsigned int *
0x18000fdb2  mov     ecx, [rsi]; dwMessageId
0x18000fdb4  call    ?AppendHResult@@YAXJKPEAGPEAI@Z; AppendHResult(long,ulong,ushort *,uint *)
0x18000fdb9  cmp     [rsi], r13d
0x18000fdbc  jnz     short loc_18000FDC4
0x18000fdbe  cmp     [rsi+28h], r13d
0x18000fdc2  jz      short loc_18000FDD9
0x18000fdc4  lea     rax, [rsp+98h+var_58]
0x18000fdc9  mov     [rsp+98h+var_78], rax; unsigned __int16
0x18000fdce  mov     edx, r15d; unsigned int
0x18000fdd1  mov     rcx, r12; unsigned __int16 *
0x18000fdd4  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x18000fdd9  lea     r8, [rsp+98h+var_58]; unsigned int *
0x18000fdde  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x18000fde3  mov     [rsp+98h+var_40], r14
0x18000fde8  lea     rax, [rsp+98h+var_40]
0x18000fded  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x18000fdf2  mov     edx, [rsi+8]; unsigned int
0x18000fdf5  movzx   ecx, word ptr [rsi+4]; unsigned __int16
0x18000fdf9  call    ?LogIt@@YAXGKPEAX_KGQEAPEBG@Z; LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)
0x18000fdfe  mov     eax, [rsi+8]
0x18000fe01  mov     ecx, 0C0000000h
0x18000fe06  and     eax, ecx
0x18000fe08  mov     r14d, r13d
0x18000fe0b  cmp     eax, ecx
0x18000fe0d  setz    r14b
0x18000fe11  test    edi, edi
0x18000fe13  jz      short loc_18000FE22
0x18000fe15  lea     rcx, stru_18001F958; lpCriticalSection
0x18000fe1c  call    cs:__imp_LeaveCriticalSection
0x18000fe22  cmp     [rsi+28h], r13d
0x18000fe26  jz      loc_18000FEBF
0x18000fe2c  cmp     [rsi+2Ch], r13d
0x18000fe30  jz      short loc_18000FEAA
0x18000fe32  call    cs:__imp_IsDebuggerPresent
0x18000fe38  test    eax, eax
0x18000fe3a  jnz     short loc_18000FE46
0x18000fe3c  cmp     ds:7FFE02D4h, r13b
0x18000fe44  jz      short loc_18000FEAA
0x18000fe46  mov     ebx, [rsi]
0x18000fe48  call    cs:__imp_GetCurrentThreadId
0x18000fe4e  mov     edi, eax
0x18000fe50  call    cs:__imp_GetCurrentProcessId
0x18000fe56  mov     [rsp+98h+var_60], ebx
0x18000fe5a  mov     [rsp+98h+var_68], r15d
0x18000fe5f  mov     [rsp+98h+var_70], r12; struct _EXCEPTION_POINTERS *
0x18000fe64  mov     dword ptr [rsp+98h+var_78], edi
0x18000fe68  mov     r9d, eax
0x18000fe6b  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x18000fe72  mov     edx, 3FFh; unsigned __int64
0x18000fe77  lea     rcx, word_180020CE0; unsigned __int16 *
0x18000fe7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fe83  lea     rcx, asc_180019670; "\n#####################################"...
0x18000fe8a  call    cs:__imp_OutputDebugStringW
0x18000fe90  lea     rcx, word_180020CE0; lpOutputString
0x18000fe97  call    cs:__imp_OutputDebugStringW
0x18000fe9d  lea     rcx, asc_180019700; "#######################################"...
0x18000fea4  call    cs:__imp_OutputDebugStringW
0x18000feaa  cmp     [rsi+28h], r13d
0x18000feae  jz      short loc_18000FEBF
0x18000feb0  mov     eax, [rsi+2Ch]
0x18000feb3  mov     dword ptr [rsp+98h+var_78], eax; int
0x18000feb7  mov     r9d, r14d; int
0x18000feba  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x18000febf  add     rsp, 60h
0x18000fec3  pop     r15
0x18000fec5  pop     r14
0x18000fec7  pop     r13
0x18000fec9  pop     r12
0x18000fecb  pop     rdi
0x18000fecc  pop     rsi
0x18000fecd  pop     rbx
0x18000fece  retn
0x180014375  push    rbp
0x180014377  sub     rsp, 40h
0x18001437b  mov     rbp, rdx
0x18001437e  cmp     dword ptr [rbp+44h], 0
0x180014382  jz      short loc_180014392
0x180014384  lea     rcx, stru_18001F958; lpCriticalSection
0x18001438b  call    cs:__imp_LeaveCriticalSection
0x180014391  nop
0x180014392  add     rsp, 40h
0x180014396  pop     rbp
0x180014397  retn
```

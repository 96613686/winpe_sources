# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x140004640`
- end: `0x140004867`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `551`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002fac`
- `0x1400036d0`

## callees

- `0x140002830`
- `0x1400028f4`
- `0x1400031c0`
- `0x1400033b4`
- `0x1400034b0`
- `0x140003534`
- `0x140003624`
- `0x140003fec`
- `0x140004368`
- `0x140004640`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400046c6`
- `msvcrt!_vsnwprintf` at `0x1400046c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400047e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400047e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400047ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400047ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004822`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000482f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000483c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004822`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000482f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000483c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000467b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000467b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400047b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007106`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400047b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007106`

## string_xrefs

- `0x140004803`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

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
  __int64 v20; // r9
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  BOOL v24; // r14d
  int v25; // ebx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  unsigned __int16 v28; // [rsp+20h] [rbp-78h]
  unsigned int *v29; // [rsp+20h] [rbp-78h]
  unsigned __int16 v30[2]; // [rsp+40h] [rbp-58h] BYREF
  int v31; // [rsp+44h] [rbp-54h]
  int v32; // [rsp+48h] [rbp-50h]
  __int64 v33; // [rsp+50h] [rbp-48h]
  unsigned __int16 *v34; // [rsp+58h] [rbp-40h] BYREF
  va_list Args; // [rsp+C0h] [rbp+28h] BYREF

  va_start(Args, a4);
  v4 = a4;
  v8 = 0;
  v31 = 0;
  if ( dword_1400106C0 )
  {
    EnterCriticalSection(&stru_140010698);
    v8 = 1;
    v31 = 1;
    v4 = a4;
  }
  v9 = 0;
  word_14000EAF0 = 0;
  if ( v4 )
  {
    v33 = 0;
    v32 = 0;
    v10 = _vsnwprintf(&word_14000EAF0, 0x3FCu, v4, Args);
    if ( v10 > 0x3FC )
    {
      v32 = -2147024774;
    }
    else if ( v10 != 1020 )
    {
LABEL_9:
      word_14000F2EA = 0;
      v33 = 0;
      v9 = (unsigned __int16 *)word_14000EAF0;
      goto LABEL_10;
    }
    word_14000F2E8 = 0;
    goto LABEL_9;
  }
LABEL_10:
  if ( (_WORD)v9 )
    StringCchCatW(&word_14000EAF0, 1024, L"\r\n");
  v11 = -1;
  do
    ++v11;
  while ( *(&word_14000EAF0 + v11) );
  *(_DWORD *)v30 = 1024 - v11;
  AppendApplicationInfo(v9, (__int64)a2, (unsigned int *)v30);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v13, v12, (unsigned int *)v30);
  AppendHResult(*(_DWORD *)this, v12, v14, (unsigned int *)v30);
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v17, v18, (unsigned int *)v30);
  AppendComsvcsFileVersion(v16, v15, (unsigned int *)v30);
  v34 = &word_14000EAF0;
  LogIt(*((_WORD *)this + 2), *((_DWORD *)this + 2), v19, v20, v28, (const unsigned __int16 **const)&v34);
  v23 = 3221225472LL;
  v24 = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v8 )
    LeaveCriticalSection(&stru_140010698);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      v25 = *(_DWORD *)this;
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      LODWORD(v29) = CurrentThreadId;
      StringCchPrintfW(
        &word_14000FB10,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        v29,
        a2,
        a3,
        v25);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_14000FB10);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v23, v21, v22, v24, *((_DWORD *)this + 11));
  }
}

```

## disassembly

```asm
0x140004640  mov     [rsp+arg_18], r9
0x140004645  push    rbx
0x140004646  push    rsi
0x140004647  push    rdi
0x140004648  push    r12
0x14000464a  push    r13
0x14000464c  push    r14
0x14000464e  push    r15
0x140004650  sub     rsp, 60h
0x140004654  mov     rax, r9
0x140004657  mov     r15d, r8d
0x14000465a  mov     r12, rdx
0x14000465d  mov     rsi, rcx
0x140004660  xor     r13d, r13d
0x140004663  mov     edi, r13d
0x140004666  mov     [rsp+98h+var_54], r13d
0x14000466b  cmp     cs:dword_1400106C0, r13d
0x140004672  jz      short loc_140004691
0x140004674  lea     rcx, stru_140010698; lpCriticalSection
0x14000467b  call    cs:__imp_EnterCriticalSection
0x140004681  lea     edi, [r13+1]
0x140004685  mov     [rsp+98h+var_54], edi
0x140004689  mov     rax, [rsp+98h+arg_18]
0x140004691  mov     ecx, r13d
0x140004694  mov     cs:word_14000EAF0, cx
0x14000469b  lea     r14, word_14000EAF0
0x1400046a2  test    rax, rax
0x1400046a5  jz      short loc_1400046FC
0x1400046a7  mov     [rsp+98h+var_48], r13
0x1400046ac  lea     r9, [rsp+98h+Args]; Args
0x1400046b4  mov     [rsp+98h+var_50], r13d
0x1400046b9  mov     r8, rax; Format
0x1400046bc  mov     ebx, 3FCh
0x1400046c1  mov     edx, ebx; BufferCount
0x1400046c3  mov     rcx, r14; Buffer
0x1400046c6  call    cs:__imp__vsnwprintf
0x1400046cc  test    eax, eax
0x1400046ce  js      short loc_1400046D8
0x1400046d0  cmp     eax, ebx
0x1400046d2  ja      short loc_1400046D8
0x1400046d4  jnz     short loc_1400046E8
0x1400046d6  jmp     short loc_1400046E0
0x1400046d8  mov     [rsp+98h+var_50], 8007007Ah
0x1400046e0  mov     cs:word_14000F2E8, r13w
0x1400046e8  mov     cs:word_14000F2EA, r13w
0x1400046f0  mov     [rsp+98h+var_48], r13
0x1400046f5  movzx   ecx, cs:word_14000EAF0
0x1400046fc  mov     ebx, 400h
0x140004701  test    cx, cx
0x140004704  jz      short loc_140004717
0x140004706  lea     r8, asc_14000A5D0; "\r\n"
0x14000470d  mov     edx, ebx; unsigned __int64
0x14000470f  mov     rcx, r14; unsigned __int16 *
0x140004712  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004717  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000471b  inc     rax
0x14000471e  cmp     [r14+rax*2], r13w
0x140004723  jnz     short loc_14000471B
0x140004725  sub     ebx, eax
0x140004727  mov     dword ptr [rsp+98h+var_58], ebx
0x14000472b  lea     r8, [rsp+98h+var_58]; unsigned int *
0x140004730  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x140004735  cmp     [rsi+28h], r13d
0x140004739  jz      short loc_140004745
0x14000473b  lea     r8, [rsp+98h+var_58]; unsigned int *
0x140004740  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x140004745  lea     r9, [rsp+98h+var_58]; unsigned int *
0x14000474a  mov     ecx, [rsi]; dwMessageId
0x14000474c  call    ?AppendHResult@@YAXJKPEAGPEAI@Z; AppendHResult(long,ulong,ushort *,uint *)
0x140004751  cmp     [rsi], r13d
0x140004754  jnz     short loc_14000475C
0x140004756  cmp     [rsi+28h], r13d
0x14000475a  jz      short loc_140004771
0x14000475c  lea     rax, [rsp+98h+var_58]
0x140004761  mov     [rsp+98h+var_78], rax; unsigned __int16
0x140004766  mov     edx, r15d; unsigned int
0x140004769  mov     rcx, r12; unsigned __int16 *
0x14000476c  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x140004771  lea     r8, [rsp+98h+var_58]; unsigned int *
0x140004776  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x14000477b  mov     [rsp+98h+var_40], r14
0x140004780  lea     rax, [rsp+98h+var_40]
0x140004785  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x14000478a  mov     edx, [rsi+8]; unsigned int
0x14000478d  movzx   ecx, word ptr [rsi+4]; unsigned __int16
0x140004791  call    ?LogIt@@YAXGKPEAX_KGQEAPEBG@Z; LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)
0x140004796  mov     eax, [rsi+8]
0x140004799  mov     ecx, 0C0000000h
0x14000479e  and     eax, ecx
0x1400047a0  mov     r14d, r13d
0x1400047a3  cmp     eax, ecx
0x1400047a5  setz    r14b
0x1400047a9  test    edi, edi
0x1400047ab  jz      short loc_1400047BA
0x1400047ad  lea     rcx, stru_140010698; lpCriticalSection
0x1400047b4  call    cs:__imp_LeaveCriticalSection
0x1400047ba  cmp     [rsi+28h], r13d
0x1400047be  jz      loc_140004857
0x1400047c4  cmp     [rsi+2Ch], r13d
0x1400047c8  jz      short loc_140004842
0x1400047ca  call    cs:__imp_IsDebuggerPresent
0x1400047d0  test    eax, eax
0x1400047d2  jnz     short loc_1400047DE
0x1400047d4  cmp     ds:7FFE02D4h, r13b
0x1400047dc  jz      short loc_140004842
0x1400047de  mov     ebx, [rsi]
0x1400047e0  call    cs:__imp_GetCurrentThreadId
0x1400047e6  mov     edi, eax
0x1400047e8  call    cs:__imp_GetCurrentProcessId
0x1400047ee  mov     [rsp+98h+var_60], ebx
0x1400047f2  mov     [rsp+98h+var_68], r15d
0x1400047f7  mov     [rsp+98h+var_70], r12; struct _EXCEPTION_POINTERS *
0x1400047fc  mov     dword ptr [rsp+98h+var_78], edi
0x140004800  mov     r9d, eax
0x140004803  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x14000480a  mov     edx, 3FFh; unsigned __int64
0x14000480f  lea     rcx, word_14000FB10; unsigned __int16 *
0x140004816  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000481b  lea     rcx, OutputString; "\n#####################################"...
0x140004822  call    cs:__imp_OutputDebugStringW
0x140004828  lea     rcx, word_14000FB10; lpOutputString
0x14000482f  call    cs:__imp_OutputDebugStringW
0x140004835  lea     rcx, asc_14000AD30; "#######################################"...
0x14000483c  call    cs:__imp_OutputDebugStringW
0x140004842  cmp     [rsi+28h], r13d
0x140004846  jz      short loc_140004857
0x140004848  mov     eax, [rsi+2Ch]
0x14000484b  mov     dword ptr [rsp+98h+var_78], eax; int
0x14000484f  mov     r9d, r14d; int
0x140004852  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x140004857  add     rsp, 60h
0x14000485b  pop     r15
0x14000485d  pop     r14
0x14000485f  pop     r13
0x140004861  pop     r12
0x140004863  pop     rdi
0x140004864  pop     rsi
0x140004865  pop     rbx
0x140004866  retn
0x1400070f0  push    rbp
0x1400070f2  sub     rsp, 40h
0x1400070f6  mov     rbp, rdx
0x1400070f9  cmp     dword ptr [rbp+44h], 0
0x1400070fd  jz      short loc_14000710D
0x1400070ff  lea     rcx, stru_140010698; lpCriticalSection
0x140007106  call    cs:__imp_LeaveCriticalSection
0x14000710c  nop
0x14000710d  add     rsp, 40h
0x140007111  pop     rbp
0x140007112  retn
```

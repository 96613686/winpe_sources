# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x180009098`
- end: `0x180009299`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `513`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `21`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800029c8`
- `0x180004d60`
- `0x180004f48`
- `0x180006b40`
- `0x180009f6c`
- `0x18000a0d0`
- `0x18000a220`
- `0x18000a310`
- `0x18000a420`
- `0x18000ab10`
- `0x18000b690`
- `0x18000bc38`
- `0x18000cd80`
- `0x18000e468`
- `0x18000f048`
- `0x180011d74`
- `0x18001a6e8`
- `0x1800319f8`
- `0x180031aa8`
- `0x180031b4c`
- `0x180031cdc`

## callees

- `0x180009098`
- `0x1800092a0`
- `0x1800093b4`
- `0x180009518`
- `0x180009ee0`
- `0x18000b380`
- `0x18001ec1c`
- `0x18002e288`
- `0x180031f0c`
- `0x180031f58`
- `0x1800328a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800557bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800557bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000921a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000921a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009212`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009254`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009261`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000926e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009254`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009261`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000926e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091fd`

## string_xrefs

- `0x180009235`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
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
  int v22; // r8d
  __int64 v23; // rcx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  unsigned __int16 v26; // [rsp+20h] [rbp-78h]
  unsigned int *v27; // [rsp+20h] [rbp-78h]
  struct _EXCEPTION_POINTERS *v28; // [rsp+28h] [rbp-70h]
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
  if ( dword_1800732D0 )
  {
    EnterCriticalSection(&stru_1800732A8);
    v9 = 1;
    v30 = 1;
    v4 = a4;
  }
  v10 = 0;
  word_180073A00 = 0;
  if ( v4 )
  {
    StringCchVPrintfW(&word_180073A00, 0x3FDu, v4, va);
    word_1800741FA = 0;
    v31 = 0;
    v10 = (unsigned __int16 *)word_180073A00;
  }
  if ( (_WORD)v10 )
    StringCchCatW(&word_180073A00, 0x400u, L"\r\n");
  v11 = -1;
  do
    ++v11;
  while ( *(&word_180073A00 + v11) );
  *(_DWORD *)v29 = 1024 - v11;
  AppendApplicationInfo(v10, (unsigned int)a2, (unsigned int *)v29);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v13, v12, (unsigned int *)v29);
  AppendHResult(*(_DWORD *)this, v12, v14, (unsigned int *)v29);
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v17, v18, (unsigned int *)v29);
  AppendComsvcsFileVersion(v16, v15, (unsigned int *)v29);
  v32 = &word_180073A00;
  LogIt(*((_WORD *)this + 2), *((_DWORD *)this + 2), v19, v20, v26, (const unsigned __int16 **const)&v32);
  v23 = 3221225472LL;
  LOBYTE(v8) = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v9 )
    LeaveCriticalSection(&stru_1800732A8);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      v28 = (struct _EXCEPTION_POINTERS *)a2;
      LODWORD(v27) = CurrentThreadId;
      StringCchPrintfW(
        &word_180074A20,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        v27);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_180074A20);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v23, v21, v22, v8, *((_DWORD *)this + 11), v28);
  }
}

```

## disassembly

```asm
0x180009098  mov     [rsp+arg_18], r9
0x18000909d  push    rbx
0x18000909e  push    rsi
0x18000909f  push    rdi
0x1800090a0  push    r12
0x1800090a2  push    r13
0x1800090a4  push    r14
0x1800090a6  push    r15
0x1800090a8  sub     rsp, 60h
0x1800090ac  mov     rax, r9
0x1800090af  mov     r12d, r8d
0x1800090b2  mov     r13, rdx
0x1800090b5  mov     rsi, rcx
0x1800090b8  xor     r15d, r15d
0x1800090bb  mov     r14d, r15d
0x1800090be  mov     [rsp+98h+var_54], r15d
0x1800090c3  cmp     cs:dword_1800732D0, r15d
0x1800090ca  jz      short loc_1800090EA
0x1800090cc  lea     rcx, stru_1800732A8; lpCriticalSection
0x1800090d3  call    cs:__imp_EnterCriticalSection
0x1800090d9  lea     r14d, [r15+1]
0x1800090dd  mov     [rsp+98h+var_54], r14d
0x1800090e2  mov     rax, [rsp+98h+arg_18]
0x1800090ea  mov     ecx, r15d
0x1800090ed  mov     cs:word_180073A00, cx
0x1800090f4  lea     rdi, word_180073A00
0x1800090fb  test    rax, rax
0x1800090fe  jz      short loc_180009131
0x180009100  mov     [rsp+98h+var_50], r15
0x180009105  lea     r9, [rsp+98h+arg_20]; char *
0x18000910d  mov     r8, rax; unsigned __int16 *
0x180009110  mov     edx, 3FDh; unsigned __int64
0x180009115  mov     rcx, rdi; unsigned __int16 *
0x180009118  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000911d  mov     cs:word_1800741FA, r15w
0x180009125  mov     [rsp+98h+var_50], r15
0x18000912a  movzx   ecx, cs:word_180073A00
0x180009131  mov     ebx, 400h
0x180009136  test    cx, cx
0x180009139  jz      short loc_18000914C
0x18000913b  lea     r8, asc_180064140; "\r\n"
0x180009142  mov     edx, ebx; unsigned __int64
0x180009144  mov     rcx, rdi; unsigned __int16 *
0x180009147  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000914c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009150  inc     rax
0x180009153  cmp     [rdi+rax*2], r15w
0x180009158  jnz     short loc_180009150
0x18000915a  sub     ebx, eax
0x18000915c  mov     dword ptr [rsp+98h+var_58], ebx
0x180009160  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180009165  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x18000916a  cmp     [rsi+28h], r15d
0x18000916e  jz      short loc_18000917A
0x180009170  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180009175  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x18000917a  lea     r9, [rsp+98h+var_58]; unsigned int *
0x18000917f  mov     ecx, [rsi]; dwMessageId
0x180009181  call    ?AppendHResult@@YAXJKPEAGPEAI@Z; AppendHResult(long,ulong,ushort *,uint *)
0x180009186  cmp     [rsi], r15d
0x180009189  jnz     short loc_180009191
0x18000918b  cmp     [rsi+28h], r15d
0x18000918f  jz      short loc_1800091A6
0x180009191  lea     rax, [rsp+98h+var_58]
0x180009196  mov     [rsp+98h+var_78], rax; unsigned __int16
0x18000919b  mov     edx, r12d; unsigned int
0x18000919e  mov     rcx, r13; unsigned __int16 *
0x1800091a1  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x1800091a6  lea     r8, [rsp+98h+var_58]; unsigned int *
0x1800091ab  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x1800091b0  mov     [rsp+98h+var_48], rdi
0x1800091b5  lea     rax, [rsp+98h+var_48]
0x1800091ba  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x1800091bf  mov     edx, [rsi+8]; unsigned int
0x1800091c2  movzx   ecx, word ptr [rsi+4]; unsigned __int16
0x1800091c6  call    ?LogIt@@YAXGKPEAX_KGQEAPEBG@Z; LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)
0x1800091cb  mov     eax, [rsi+8]
0x1800091ce  mov     ecx, 0C0000000h
0x1800091d3  and     eax, ecx
0x1800091d5  cmp     eax, ecx
0x1800091d7  setz    r15b
0x1800091db  test    r14d, r14d
0x1800091de  jz      short loc_1800091ED
0x1800091e0  lea     rcx, stru_1800732A8; lpCriticalSection
0x1800091e7  call    cs:__imp_LeaveCriticalSection
0x1800091ed  cmp     dword ptr [rsi+28h], 0
0x1800091f1  jz      loc_180009289
0x1800091f7  cmp     dword ptr [rsi+2Ch], 0
0x1800091fb  jz      short loc_180009274
0x1800091fd  call    cs:__imp_IsDebuggerPresent
0x180009203  test    eax, eax
0x180009205  jnz     short loc_180009210
0x180009207  cmp     ds:7FFE02D4h, al
0x18000920e  jz      short loc_180009274
0x180009210  mov     ebx, [rsi]
0x180009212  call    cs:__imp_GetCurrentThreadId
0x180009218  mov     edi, eax
0x18000921a  call    cs:__imp_GetCurrentProcessId
0x180009220  mov     [rsp+98h+var_60], ebx
0x180009224  mov     [rsp+98h+var_68], r12d
0x180009229  mov     [rsp+98h+var_70], r13; struct _EXCEPTION_POINTERS *
0x18000922e  mov     dword ptr [rsp+98h+var_78], edi
0x180009232  mov     r9d, eax
0x180009235  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x18000923c  mov     edx, 3FFh; unsigned __int64
0x180009241  lea     rcx, word_180074A20; unsigned __int16 *
0x180009248  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000924d  lea     rcx, OutputString; "\n#####################################"...
0x180009254  call    cs:__imp_OutputDebugStringW
0x18000925a  lea     rcx, word_180074A20; lpOutputString
0x180009261  call    cs:__imp_OutputDebugStringW
0x180009267  lea     rcx, asc_180064290; "#######################################"...
0x18000926e  call    cs:__imp_OutputDebugStringW
0x180009274  cmp     dword ptr [rsi+28h], 0
0x180009278  jz      short loc_180009289
0x18000927a  mov     eax, [rsi+2Ch]
0x18000927d  mov     dword ptr [rsp+98h+var_78], eax; int
0x180009281  mov     r9d, r15d; int
0x180009284  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x180009289  add     rsp, 60h
0x18000928d  pop     r15
0x18000928f  pop     r14
0x180009291  pop     r13
0x180009293  pop     r12
0x180009295  pop     rdi
0x180009296  pop     rsi
0x180009297  pop     rbx
0x180009298  retn
0x1800557a5  push    rbp
0x1800557a7  sub     rsp, 40h
0x1800557ab  mov     rbp, rdx
0x1800557ae  cmp     dword ptr [rbp+44h], 0
0x1800557b2  jz      short loc_1800557C2
0x1800557b4  lea     rcx, stru_1800732A8; lpCriticalSection
0x1800557bb  call    cs:__imp_LeaveCriticalSection
0x1800557c1  nop
0x1800557c2  add     rsp, 40h
0x1800557c6  pop     rbp
0x1800557c7  retn
```

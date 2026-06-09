# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140005600`
- end: `0x14000582a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004bd0`
- `0x140013330`

## callees

- `0x140005600`
- `0x140006fb8`
- `0x14000ad94`
- `0x14000b514`
- `0x14000bc1c`
- `0x14000bc2c`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400056c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005767`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400056c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000572b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000572b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000571a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400057ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000571a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400057ba`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005600  mov     [rsp+arg_8], rbx
0x140005605  mov     [rsp+arg_10], rbp
0x14000560a  push    rsi
0x14000560b  push    rdi
0x14000560c  push    r12
0x14000560e  push    r14
0x140005610  push    r15
0x140005612  sub     rsp, 250h
0x140005619  mov     rax, cs:__security_cookie
0x140005620  xor     rax, rsp
0x140005623  mov     [rsp+278h+var_38], rax
0x14000562b  mov     rax, 0C000000000000000h
0x140005635  mov     rbp, r9
0x140005638  mov     r8, rdx
0x14000563b  mov     rbx, rcx
0x14000563e  test    rax, r9
0x140005641  jnz     loc_140005811
0x140005647  xor     r12d, r12d
0x14000564a  lea     rax, [rsp+278h+Name]
0x14000564f  mov     ecx, 7FFFFFFEh
0x140005654  mov     edx, 104h
0x140005659  lea     esi, [r12+1]
0x14000565e  test    rcx, rcx
0x140005661  jz      short loc_140005681
0x140005663  movzx   r9d, word ptr [r8]
0x140005667  test    r9w, r9w
0x14000566b  jz      short loc_140005681
0x14000566d  mov     [rax], r9w
0x140005671  add     r8, 2
0x140005675  add     rax, 2
0x140005679  sub     rcx, rsi
0x14000567c  sub     rdx, rsi; unsigned __int64
0x14000567f  jnz     short loc_14000565E
0x140005681  test    rdx, rdx
0x140005684  lea     rcx, [rax-2]
0x140005688  lea     r8, aP0; "_p0"
0x14000568f  cmovnz  rcx, rax
0x140005693  mov     [rcx], r12w
0x140005697  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000569c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400056a1  mov     edx, ebp
0x1400056a3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400056ab  and     edx, 7FFFFFFFh; lInitialCount
0x1400056b1  mov     [rsp+278h+dwFlags], r12d; int
0x1400056b6  mov     r8d, esi
0x1400056b9  lea     r9, [rsp+278h+Name]; lpName
0x1400056be  cmova   r8d, edx; lMaximumCount
0x1400056c2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400056c4  call    cs:__imp_CreateSemaphoreExW
0x1400056ca  mov     r15, rax
0x1400056cd  test    rax, rax
0x1400056d0  jnz     short loc_140005700
0x1400056d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400056d7  mov     edi, eax
0x1400056d9  test    eax, eax
0x1400056db  jns     short loc_140005734
0x1400056dd  mov     rcx, [rsp+278h]; this
0x1400056e5  lea     r8, aWil; "wil"
0x1400056ec  mov     r9d, eax; char *
0x1400056ef  mov     edx, 8Bh; void *
0x1400056f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400056f9  mov     eax, edi
0x1400056fb  jmp     loc_1400057D2
0x140005700  call    cs:__imp_GetLastError
0x140005706  mov     rdi, [rbx]
0x140005709  test    rdi, rdi
0x14000570c  jz      short loc_140005731
0x14000570e  call    cs:__imp_GetLastError
0x140005714  mov     rcx, rdi; hObject
0x140005717  mov     r14d, eax
0x14000571a  call    cs:__imp_CloseHandle
0x140005720  test    eax, eax
0x140005722  jz      loc_140005817
0x140005728  mov     ecx, r14d; dwErrCode
0x14000572b  call    cs:__imp_SetLastError
0x140005731  mov     [rbx], r15
0x140005734  lea     r8, asc_14001C850; "h"
0x14000573b  shr     rbp, 1Fh
0x14000573f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140005744  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005749  test    ebp, ebp
0x14000574b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005753  lea     r9, [rsp+278h+Name]; lpName
0x140005758  mov     [rsp+278h+dwFlags], r12d; int
0x14000575d  cmovnz  esi, ebp
0x140005760  mov     edx, ebp; lInitialCount
0x140005762  mov     r8d, esi; lMaximumCount
0x140005765  xor     ecx, ecx; lpSemaphoreAttributes
0x140005767  call    cs:__imp_CreateSemaphoreExW
0x14000576d  mov     rsi, rax
0x140005770  test    rax, rax
0x140005773  jnz     short loc_1400057A0
0x140005775  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000577a  mov     ebx, eax
0x14000577c  test    eax, eax
0x14000577e  jns     short loc_1400057D0
0x140005780  mov     rcx, [rsp+278h]; this
0x140005788  lea     r8, aWil; "wil"
0x14000578f  mov     r9d, eax; char *
0x140005792  mov     edx, 90h; void *
0x140005797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000579c  mov     eax, ebx
0x14000579e  jmp     short loc_1400057D2
0x1400057a0  call    cs:__imp_GetLastError
0x1400057a6  mov     rdi, [rbx+8]
0x1400057aa  test    rdi, rdi
0x1400057ad  jz      short loc_1400057CC
0x1400057af  call    cs:__imp_GetLastError
0x1400057b5  mov     rcx, rdi; hObject
0x1400057b8  mov     ebp, eax
0x1400057ba  call    cs:__imp_CloseHandle
0x1400057c0  test    eax, eax
0x1400057c2  jz      short loc_1400057FE
0x1400057c4  mov     ecx, ebp; dwErrCode
0x1400057c6  call    cs:__imp_SetLastError
0x1400057cc  mov     [rbx+8], rsi
0x1400057d0  xor     eax, eax
0x1400057d2  mov     rcx, [rsp+278h+var_38]
0x1400057da  xor     rcx, rsp; StackCookie
0x1400057dd  call    __security_check_cookie
0x1400057e2  lea     r11, [rsp+278h+var_28]
0x1400057ea  mov     rbx, [r11+38h]
0x1400057ee  mov     rbp, [r11+40h]
0x1400057f2  mov     rsp, r11
0x1400057f5  pop     r15
0x1400057f7  pop     r14
0x1400057f9  pop     r12
0x1400057fb  pop     rdi
0x1400057fc  pop     rsi
0x1400057fd  retn
0x1400057fe  mov     rcx, [rsp+278h]; this
0x140005806  mov     edx, 0A0Bh; void *
0x14000580b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005811  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005817  mov     rcx, [rsp+278h]; this
0x14000581f  mov     edx, 0A0Bh; void *
0x140005824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000495c`
- end: `0x180004b86`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004528`

## callees

- `0x180001770`
- `0x18000495c`
- `0x180005378`
- `0x1800064b4`
- `0x180006df4`
- `0x18000733c`
- `0x18000734c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ac3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ac3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b16`

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
0x18000495c  mov     [rsp+arg_8], rbx
0x180004961  mov     [rsp+arg_10], rbp
0x180004966  push    rsi
0x180004967  push    rdi
0x180004968  push    r12
0x18000496a  push    r14
0x18000496c  push    r15
0x18000496e  sub     rsp, 250h
0x180004975  mov     rax, cs:__security_cookie
0x18000497c  xor     rax, rsp
0x18000497f  mov     [rsp+278h+var_38], rax
0x180004987  mov     rax, 0C000000000000000h
0x180004991  mov     rbp, r9
0x180004994  mov     r8, rdx
0x180004997  mov     rbx, rcx
0x18000499a  test    rax, r9
0x18000499d  jnz     loc_180004B6D
0x1800049a3  xor     r12d, r12d
0x1800049a6  lea     rax, [rsp+278h+Name]
0x1800049ab  mov     ecx, 7FFFFFFEh
0x1800049b0  mov     edx, 104h
0x1800049b5  lea     esi, [r12+1]
0x1800049ba  test    rcx, rcx
0x1800049bd  jz      short loc_1800049DD
0x1800049bf  movzx   r9d, word ptr [r8]
0x1800049c3  test    r9w, r9w
0x1800049c7  jz      short loc_1800049DD
0x1800049c9  mov     [rax], r9w
0x1800049cd  add     r8, 2
0x1800049d1  add     rax, 2
0x1800049d5  sub     rcx, rsi
0x1800049d8  sub     rdx, rsi; unsigned __int64
0x1800049db  jnz     short loc_1800049BA
0x1800049dd  test    rdx, rdx
0x1800049e0  lea     rcx, [rax-2]
0x1800049e4  lea     r8, aP0; "_p0"
0x1800049eb  cmovnz  rcx, rax
0x1800049ef  mov     [rcx], r12w
0x1800049f3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800049f8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800049fd  mov     edx, ebp
0x1800049ff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a07  and     edx, 7FFFFFFFh; lInitialCount
0x180004a0d  mov     [rsp+278h+dwFlags], r12d; int
0x180004a12  mov     r8d, esi
0x180004a15  lea     r9, [rsp+278h+Name]; lpName
0x180004a1a  cmova   r8d, edx; lMaximumCount
0x180004a1e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a20  call    cs:__imp_CreateSemaphoreExW
0x180004a26  mov     r15, rax
0x180004a29  test    rax, rax
0x180004a2c  jnz     short loc_180004A5C
0x180004a2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a33  mov     edi, eax
0x180004a35  test    eax, eax
0x180004a37  jns     short loc_180004A90
0x180004a39  mov     rcx, [rsp+278h]; this
0x180004a41  lea     r8, aWil; "wil"
0x180004a48  mov     r9d, eax; char *
0x180004a4b  mov     edx, 8Bh; void *
0x180004a50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a55  mov     eax, edi
0x180004a57  jmp     loc_180004B2E
0x180004a5c  call    cs:__imp_GetLastError
0x180004a62  mov     rdi, [rbx]
0x180004a65  test    rdi, rdi
0x180004a68  jz      short loc_180004A8D
0x180004a6a  call    cs:__imp_GetLastError
0x180004a70  mov     rcx, rdi; hObject
0x180004a73  mov     r14d, eax
0x180004a76  call    cs:__imp_CloseHandle
0x180004a7c  test    eax, eax
0x180004a7e  jz      loc_180004B73
0x180004a84  mov     ecx, r14d; dwErrCode
0x180004a87  call    cs:__imp_SetLastError
0x180004a8d  mov     [rbx], r15
0x180004a90  lea     r8, asc_180019CD8; "h"
0x180004a97  shr     rbp, 1Fh
0x180004a9b  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004aa0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004aa5  test    ebp, ebp
0x180004aa7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004aaf  lea     r9, [rsp+278h+Name]; lpName
0x180004ab4  mov     [rsp+278h+dwFlags], r12d; int
0x180004ab9  cmovnz  esi, ebp
0x180004abc  mov     edx, ebp; lInitialCount
0x180004abe  mov     r8d, esi; lMaximumCount
0x180004ac1  xor     ecx, ecx; lpSemaphoreAttributes
0x180004ac3  call    cs:__imp_CreateSemaphoreExW
0x180004ac9  mov     rsi, rax
0x180004acc  test    rax, rax
0x180004acf  jnz     short loc_180004AFC
0x180004ad1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ad6  mov     ebx, eax
0x180004ad8  test    eax, eax
0x180004ada  jns     short loc_180004B2C
0x180004adc  mov     rcx, [rsp+278h]; this
0x180004ae4  lea     r8, aWil; "wil"
0x180004aeb  mov     r9d, eax; char *
0x180004aee  mov     edx, 90h; void *
0x180004af3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004af8  mov     eax, ebx
0x180004afa  jmp     short loc_180004B2E
0x180004afc  call    cs:__imp_GetLastError
0x180004b02  mov     rdi, [rbx+8]
0x180004b06  test    rdi, rdi
0x180004b09  jz      short loc_180004B28
0x180004b0b  call    cs:__imp_GetLastError
0x180004b11  mov     rcx, rdi; hObject
0x180004b14  mov     ebp, eax
0x180004b16  call    cs:__imp_CloseHandle
0x180004b1c  test    eax, eax
0x180004b1e  jz      short loc_180004B5A
0x180004b20  mov     ecx, ebp; dwErrCode
0x180004b22  call    cs:__imp_SetLastError
0x180004b28  mov     [rbx+8], rsi
0x180004b2c  xor     eax, eax
0x180004b2e  mov     rcx, [rsp+278h+var_38]
0x180004b36  xor     rcx, rsp; StackCookie
0x180004b39  call    __security_check_cookie
0x180004b3e  lea     r11, [rsp+278h+var_28]
0x180004b46  mov     rbx, [r11+38h]
0x180004b4a  mov     rbp, [r11+40h]
0x180004b4e  mov     rsp, r11
0x180004b51  pop     r15
0x180004b53  pop     r14
0x180004b55  pop     r12
0x180004b57  pop     rdi
0x180004b58  pop     rsi
0x180004b59  retn
0x180004b5a  mov     rcx, [rsp+278h]; this
0x180004b62  mov     edx, 0A0Bh; void *
0x180004b67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b6d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b73  mov     rcx, [rsp+278h]; this
0x180004b7b  mov     edx, 0A0Bh; void *
0x180004b80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

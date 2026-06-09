# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004be0`
- end: `0x180004e11`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004418`
- `0x1800047e8`

## callees

- `0x180001cf0`
- `0x180004be0`
- `0x180005a68`
- `0x1800081c4`
- `0x180008fe8`
- `0x18000a12c`
- `0x18000a13c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004dae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d97`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ca9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d4f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ca9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da2`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004be0  mov     [rsp+arg_8], rbx
0x180004be5  push    rbp
0x180004be6  push    rsi
0x180004be7  push    rdi
0x180004be8  push    r12
0x180004bea  push    r13
0x180004bec  push    r14
0x180004bee  push    r15
0x180004bf0  sub     rsp, 250h
0x180004bf7  mov     rax, cs:__security_cookie
0x180004bfe  xor     rax, rsp
0x180004c01  mov     [rsp+288h+var_48], rax
0x180004c09  mov     rax, 0C000000000000000h
0x180004c13  mov     rsi, r9
0x180004c16  mov     r8, rdx
0x180004c19  mov     rbx, rcx
0x180004c1c  test    rax, r9
0x180004c1f  jnz     loc_180004DF8
0x180004c25  xor     r12d, r12d
0x180004c28  lea     rax, [rsp+288h+Name]
0x180004c2d  mov     r13d, 104h
0x180004c33  mov     ecx, 7FFFFFFEh
0x180004c38  mov     edx, r13d
0x180004c3b  lea     ebp, [r12+1]
0x180004c40  test    rcx, rcx
0x180004c43  jz      short loc_180004C63
0x180004c45  movzx   r9d, word ptr [r8]
0x180004c49  test    r9w, r9w
0x180004c4d  jz      short loc_180004C63
0x180004c4f  mov     [rax], r9w
0x180004c53  add     r8, 2
0x180004c57  add     rax, 2
0x180004c5b  sub     rcx, rbp
0x180004c5e  sub     rdx, rbp
0x180004c61  jnz     short loc_180004C40
0x180004c63  test    rdx, rdx
0x180004c66  lea     rcx, [rax-2]
0x180004c6a  lea     r8, aP0; "_p0"
0x180004c71  mov     rdx, r13; unsigned __int64
0x180004c74  cmovnz  rcx, rax
0x180004c78  mov     [rcx], r12w
0x180004c7c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004c81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004c86  mov     edx, esi
0x180004c88  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004c90  and     edx, 7FFFFFFFh; lInitialCount
0x180004c96  mov     [rsp+288h+dwFlags], r12d; int
0x180004c9b  mov     r8d, ebp
0x180004c9e  lea     r9, [rsp+288h+Name]; lpName
0x180004ca3  cmova   r8d, edx; lMaximumCount
0x180004ca7  xor     ecx, ecx; lpSemaphoreAttributes
0x180004ca9  call    cs:__imp_CreateSemaphoreExW
0x180004caf  mov     r15, rax
0x180004cb2  test    rax, rax
0x180004cb5  jnz     short loc_180004CE5
0x180004cb7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004cbc  mov     edi, eax
0x180004cbe  test    eax, eax
0x180004cc0  jns     short loc_180004D19
0x180004cc2  mov     rcx, [rsp+288h]; this
0x180004cca  lea     r8, aWil; "wil"
0x180004cd1  mov     r9d, eax; char *
0x180004cd4  mov     edx, 8Bh; void *
0x180004cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cde  mov     eax, edi
0x180004ce0  jmp     loc_180004DBA
0x180004ce5  call    cs:__imp_GetLastError
0x180004ceb  mov     rdi, [rbx]
0x180004cee  test    rdi, rdi
0x180004cf1  jz      short loc_180004D16
0x180004cf3  call    cs:__imp_GetLastError
0x180004cf9  mov     rcx, rdi; hObject
0x180004cfc  mov     r14d, eax
0x180004cff  call    cs:__imp_CloseHandle
0x180004d05  test    eax, eax
0x180004d07  jz      loc_180004DFE
0x180004d0d  mov     ecx, r14d; dwErrCode
0x180004d10  call    cs:__imp_SetLastError
0x180004d16  mov     [rbx], r15
0x180004d19  lea     r8, asc_180015D00; "h"
0x180004d20  shr     rsi, 1Fh
0x180004d24  mov     rdx, r13; unsigned __int64
0x180004d27  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004d2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004d31  test    esi, esi
0x180004d33  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004d3b  lea     r9, [rsp+288h+Name]; lpName
0x180004d40  mov     [rsp+288h+dwFlags], r12d; int
0x180004d45  cmovnz  ebp, esi
0x180004d48  mov     edx, esi; lInitialCount
0x180004d4a  mov     r8d, ebp; lMaximumCount
0x180004d4d  xor     ecx, ecx; lpSemaphoreAttributes
0x180004d4f  call    cs:__imp_CreateSemaphoreExW
0x180004d55  mov     rbp, rax
0x180004d58  test    rax, rax
0x180004d5b  jnz     short loc_180004D88
0x180004d5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d62  mov     ebx, eax
0x180004d64  test    eax, eax
0x180004d66  jns     short loc_180004DB8
0x180004d68  mov     rcx, [rsp+288h]; this
0x180004d70  lea     r8, aWil; "wil"
0x180004d77  mov     r9d, eax; char *
0x180004d7a  mov     edx, 90h; void *
0x180004d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d84  mov     eax, ebx
0x180004d86  jmp     short loc_180004DBA
0x180004d88  call    cs:__imp_GetLastError
0x180004d8e  mov     rdi, [rbx+8]
0x180004d92  test    rdi, rdi
0x180004d95  jz      short loc_180004DB4
0x180004d97  call    cs:__imp_GetLastError
0x180004d9d  mov     rcx, rdi; hObject
0x180004da0  mov     esi, eax
0x180004da2  call    cs:__imp_CloseHandle
0x180004da8  test    eax, eax
0x180004daa  jz      short loc_180004DE5
0x180004dac  mov     ecx, esi; dwErrCode
0x180004dae  call    cs:__imp_SetLastError
0x180004db4  mov     [rbx+8], rbp
0x180004db8  xor     eax, eax
0x180004dba  mov     rcx, [rsp+288h+var_48]
0x180004dc2  xor     rcx, rsp; StackCookie
0x180004dc5  call    __security_check_cookie
0x180004dca  mov     rbx, [rsp+288h+arg_8]
0x180004dd2  add     rsp, 250h
0x180004dd9  pop     r15
0x180004ddb  pop     r14
0x180004ddd  pop     r13
0x180004ddf  pop     r12
0x180004de1  pop     rdi
0x180004de2  pop     rsi
0x180004de3  pop     rbp
0x180004de4  retn
0x180004de5  mov     rcx, [rsp+288h]; this
0x180004ded  mov     edx, 0A0Bh; void *
0x180004df2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004df8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004dfe  mov     rcx, [rsp+288h]; this
0x180004e06  mov     edx, 0A0Bh; void *
0x180004e0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

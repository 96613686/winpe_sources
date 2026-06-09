# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18008c284`
- end: `0x18008c491`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18008bee0`

## callees

- `0x1800115f0`
- `0x18008c284`
- `0x18008caf8`
- `0x18008d8b4`
- `0x18008db60`
- `0x18008dfcc`
- `0x18008dfdc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008c397`
- `KERNEL32!CloseHandle` at `0x18008c421`
- `KERNEL32!CloseHandle` at `0x18008c397`
- `KERNEL32!CloseHandle` at `0x18008c421`
- `KERNEL32!GetLastError` at `0x18008c37d`
- `KERNEL32!GetLastError` at `0x18008c38b`
- `KERNEL32!GetLastError` at `0x18008c407`
- `KERNEL32!GetLastError` at `0x18008c416`
- `KERNEL32!GetLastError` at `0x18008c37d`
- `KERNEL32!GetLastError` at `0x18008c38b`
- `KERNEL32!GetLastError` at `0x18008c407`
- `KERNEL32!GetLastError` at `0x18008c416`
- `KERNEL32!CreateSemaphoreExW` at `0x18008c348`
- `KERNEL32!CreateSemaphoreExW` at `0x18008c3e4`
- `KERNEL32!CreateSemaphoreExW` at `0x18008c348`
- `KERNEL32!CreateSemaphoreExW` at `0x18008c3e4`
- `KERNEL32!SetLastError` at `0x18008c3a8`
- `KERNEL32!SetLastError` at `0x18008c42d`
- `KERNEL32!SetLastError` at `0x18008c3a8`
- `KERNEL32!SetLastError` at `0x18008c42d`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008c284  mov     [rsp+arg_8], rbx
0x18008c289  mov     [rsp+arg_10], rbp
0x18008c28e  push    rsi
0x18008c28f  push    rdi
0x18008c290  push    r12
0x18008c292  push    r14
0x18008c294  push    r15
0x18008c296  sub     rsp, 250h
0x18008c29d  mov     rax, cs:__security_cookie
0x18008c2a4  xor     rax, rsp
0x18008c2a7  mov     [rsp+278h+var_38], rax
0x18008c2af  mov     rax, 0C000000000000000h
0x18008c2b9  mov     rbp, r9
0x18008c2bc  mov     r8, rdx
0x18008c2bf  mov     rdi, rcx
0x18008c2c2  test    rax, r9
0x18008c2c5  jnz     loc_18008C478
0x18008c2cb  xor     r12d, r12d
0x18008c2ce  lea     rax, [rsp+278h+Name]
0x18008c2d3  mov     ecx, 7FFFFFFEh
0x18008c2d8  mov     edx, 104h
0x18008c2dd  lea     esi, [r12+1]
0x18008c2e2  test    rcx, rcx
0x18008c2e5  jz      short loc_18008C305
0x18008c2e7  movzx   r9d, word ptr [r8]
0x18008c2eb  test    r9w, r9w
0x18008c2ef  jz      short loc_18008C305
0x18008c2f1  mov     [rax], r9w
0x18008c2f5  add     r8, 2
0x18008c2f9  add     rax, 2
0x18008c2fd  sub     rcx, rsi
0x18008c300  sub     rdx, rsi; unsigned __int64
0x18008c303  jnz     short loc_18008C2E2
0x18008c305  test    rdx, rdx
0x18008c308  lea     rcx, [rax-2]
0x18008c30c  lea     r8, aP0; "_p0"
0x18008c313  cmovnz  rcx, rax
0x18008c317  mov     [rcx], r12w
0x18008c31b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18008c320  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008c325  mov     edx, ebp
0x18008c327  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18008c32f  and     edx, 7FFFFFFFh; lInitialCount
0x18008c335  mov     [rsp+278h+dwFlags], r12d; int
0x18008c33a  mov     r8d, esi
0x18008c33d  lea     r9, [rsp+278h+Name]; lpName
0x18008c342  cmova   r8d, edx; lMaximumCount
0x18008c346  xor     ecx, ecx; lpSemaphoreAttributes
0x18008c348  call    cs:__imp_CreateSemaphoreExW
0x18008c34e  mov     r15, rax
0x18008c351  test    rax, rax
0x18008c354  jnz     short loc_18008C37D
0x18008c356  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008c35b  mov     ebx, eax
0x18008c35d  test    eax, eax
0x18008c35f  jns     short loc_18008C3B1
0x18008c361  mov     edx, 8Bh; void *
0x18008c366  mov     rcx, [rsp+278h]; this
0x18008c36e  mov     r9d, ebx; char *
0x18008c371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c376  mov     eax, ebx
0x18008c378  jmp     loc_18008C439
0x18008c37d  call    cs:__imp_GetLastError
0x18008c383  mov     rbx, [rdi]
0x18008c386  test    rbx, rbx
0x18008c389  jz      short loc_18008C3AE
0x18008c38b  call    cs:__imp_GetLastError
0x18008c391  mov     rcx, rbx; hObject
0x18008c394  mov     r14d, eax
0x18008c397  call    cs:__imp_CloseHandle
0x18008c39d  test    eax, eax
0x18008c39f  jz      loc_18008C47E
0x18008c3a5  mov     ecx, r14d; dwErrCode
0x18008c3a8  call    cs:__imp_SetLastError
0x18008c3ae  mov     [rdi], r15
0x18008c3b1  lea     r8, asc_18009B408; "h"
0x18008c3b8  shr     rbp, 1Fh
0x18008c3bc  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18008c3c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008c3c6  test    ebp, ebp
0x18008c3c8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18008c3d0  lea     r9, [rsp+278h+Name]; lpName
0x18008c3d5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18008c3da  cmovnz  esi, ebp
0x18008c3dd  mov     edx, ebp; lInitialCount
0x18008c3df  mov     r8d, esi; lMaximumCount
0x18008c3e2  xor     ecx, ecx; lpSemaphoreAttributes
0x18008c3e4  call    cs:__imp_CreateSemaphoreExW
0x18008c3ea  mov     rsi, rax
0x18008c3ed  test    rax, rax
0x18008c3f0  jnz     short loc_18008C407
0x18008c3f2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008c3f7  mov     ebx, eax
0x18008c3f9  test    eax, eax
0x18008c3fb  jns     short loc_18008C437
0x18008c3fd  mov     edx, 90h
0x18008c402  jmp     loc_18008C366
0x18008c407  call    cs:__imp_GetLastError
0x18008c40d  mov     rbx, [rdi+8]
0x18008c411  test    rbx, rbx
0x18008c414  jz      short loc_18008C433
0x18008c416  call    cs:__imp_GetLastError
0x18008c41c  mov     rcx, rbx; hObject
0x18008c41f  mov     ebp, eax
0x18008c421  call    cs:__imp_CloseHandle
0x18008c427  test    eax, eax
0x18008c429  jz      short loc_18008C465
0x18008c42b  mov     ecx, ebp; dwErrCode
0x18008c42d  call    cs:__imp_SetLastError
0x18008c433  mov     [rdi+8], rsi
0x18008c437  xor     eax, eax
0x18008c439  mov     rcx, [rsp+278h+var_38]
0x18008c441  xor     rcx, rsp; StackCookie
0x18008c444  call    __security_check_cookie
0x18008c449  lea     r11, [rsp+278h+var_28]
0x18008c451  mov     rbx, [r11+38h]
0x18008c455  mov     rbp, [r11+40h]
0x18008c459  mov     rsp, r11
0x18008c45c  pop     r15
0x18008c45e  pop     r14
0x18008c460  pop     r12
0x18008c462  pop     rdi
0x18008c463  pop     rsi
0x18008c464  retn
0x18008c465  mov     rcx, [rsp+278h]; this
0x18008c46d  mov     edx, 0A0Bh; void *
0x18008c472  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c478  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18008c47e  mov     rcx, [rsp+278h]; this
0x18008c486  mov     edx, 0A0Bh; void *
0x18008c48b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

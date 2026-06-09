# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180003e38`
- end: `0x180004062`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a68`

## callees

- `0x180001540`
- `0x180003e38`
- `0x180004700`
- `0x18000553c`
- `0x180005fcc`
- `0x180006730`
- `0x180006740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003efc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f9f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003efc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ffe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff2`

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
0x180003e38  mov     [rsp+arg_8], rbx
0x180003e3d  mov     [rsp+arg_10], rbp
0x180003e42  push    rsi
0x180003e43  push    rdi
0x180003e44  push    r12
0x180003e46  push    r14
0x180003e48  push    r15
0x180003e4a  sub     rsp, 250h
0x180003e51  mov     rax, cs:__security_cookie
0x180003e58  xor     rax, rsp
0x180003e5b  mov     [rsp+278h+var_38], rax
0x180003e63  mov     rax, 0C000000000000000h
0x180003e6d  mov     rbp, r9
0x180003e70  mov     r8, rdx
0x180003e73  mov     rbx, rcx
0x180003e76  test    rax, r9
0x180003e79  jnz     loc_180004049
0x180003e7f  xor     r12d, r12d
0x180003e82  lea     rax, [rsp+278h+Name]
0x180003e87  mov     ecx, 7FFFFFFEh
0x180003e8c  mov     edx, 104h
0x180003e91  lea     esi, [r12+1]
0x180003e96  test    rcx, rcx
0x180003e99  jz      short loc_180003EB9
0x180003e9b  movzx   r9d, word ptr [r8]
0x180003e9f  test    r9w, r9w
0x180003ea3  jz      short loc_180003EB9
0x180003ea5  mov     [rax], r9w
0x180003ea9  add     r8, 2
0x180003ead  add     rax, 2
0x180003eb1  sub     rcx, rsi
0x180003eb4  sub     rdx, rsi; unsigned __int64
0x180003eb7  jnz     short loc_180003E96
0x180003eb9  test    rdx, rdx
0x180003ebc  lea     rcx, [rax-2]
0x180003ec0  lea     r8, aP0; "_p0"
0x180003ec7  cmovnz  rcx, rax
0x180003ecb  mov     [rcx], r12w
0x180003ecf  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180003ed4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003ed9  mov     edx, ebp
0x180003edb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003ee3  and     edx, 7FFFFFFFh; lInitialCount
0x180003ee9  mov     [rsp+278h+dwFlags], r12d; int
0x180003eee  mov     r8d, esi
0x180003ef1  lea     r9, [rsp+278h+Name]; lpName
0x180003ef6  cmova   r8d, edx; lMaximumCount
0x180003efa  xor     ecx, ecx; lpSemaphoreAttributes
0x180003efc  call    cs:__imp_CreateSemaphoreExW
0x180003f02  mov     r15, rax
0x180003f05  test    rax, rax
0x180003f08  jnz     short loc_180003F38
0x180003f0a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f0f  mov     edi, eax
0x180003f11  test    eax, eax
0x180003f13  jns     short loc_180003F6C
0x180003f15  mov     rcx, [rsp+278h]; this
0x180003f1d  lea     r8, aWil; "wil"
0x180003f24  mov     r9d, eax; char *
0x180003f27  mov     edx, 8Bh; void *
0x180003f2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f31  mov     eax, edi
0x180003f33  jmp     loc_18000400A
0x180003f38  call    cs:__imp_GetLastError
0x180003f3e  mov     rdi, [rbx]
0x180003f41  test    rdi, rdi
0x180003f44  jz      short loc_180003F69
0x180003f46  call    cs:__imp_GetLastError
0x180003f4c  mov     rcx, rdi; hObject
0x180003f4f  mov     r14d, eax
0x180003f52  call    cs:__imp_CloseHandle
0x180003f58  test    eax, eax
0x180003f5a  jz      loc_18000404F
0x180003f60  mov     ecx, r14d; dwErrCode
0x180003f63  call    cs:__imp_SetLastError
0x180003f69  mov     [rbx], r15
0x180003f6c  lea     r8, asc_180017FD0; "h"
0x180003f73  shr     rbp, 1Fh
0x180003f77  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180003f7c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003f81  test    ebp, ebp
0x180003f83  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003f8b  lea     r9, [rsp+278h+Name]; lpName
0x180003f90  mov     [rsp+278h+dwFlags], r12d; int
0x180003f95  cmovnz  esi, ebp
0x180003f98  mov     edx, ebp; lInitialCount
0x180003f9a  mov     r8d, esi; lMaximumCount
0x180003f9d  xor     ecx, ecx; lpSemaphoreAttributes
0x180003f9f  call    cs:__imp_CreateSemaphoreExW
0x180003fa5  mov     rsi, rax
0x180003fa8  test    rax, rax
0x180003fab  jnz     short loc_180003FD8
0x180003fad  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fb2  mov     ebx, eax
0x180003fb4  test    eax, eax
0x180003fb6  jns     short loc_180004008
0x180003fb8  mov     rcx, [rsp+278h]; this
0x180003fc0  lea     r8, aWil; "wil"
0x180003fc7  mov     r9d, eax; char *
0x180003fca  mov     edx, 90h; void *
0x180003fcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fd4  mov     eax, ebx
0x180003fd6  jmp     short loc_18000400A
0x180003fd8  call    cs:__imp_GetLastError
0x180003fde  mov     rdi, [rbx+8]
0x180003fe2  test    rdi, rdi
0x180003fe5  jz      short loc_180004004
0x180003fe7  call    cs:__imp_GetLastError
0x180003fed  mov     rcx, rdi; hObject
0x180003ff0  mov     ebp, eax
0x180003ff2  call    cs:__imp_CloseHandle
0x180003ff8  test    eax, eax
0x180003ffa  jz      short loc_180004036
0x180003ffc  mov     ecx, ebp; dwErrCode
0x180003ffe  call    cs:__imp_SetLastError
0x180004004  mov     [rbx+8], rsi
0x180004008  xor     eax, eax
0x18000400a  mov     rcx, [rsp+278h+var_38]
0x180004012  xor     rcx, rsp; StackCookie
0x180004015  call    __security_check_cookie
0x18000401a  lea     r11, [rsp+278h+var_28]
0x180004022  mov     rbx, [r11+38h]
0x180004026  mov     rbp, [r11+40h]
0x18000402a  mov     rsp, r11
0x18000402d  pop     r15
0x18000402f  pop     r14
0x180004031  pop     r12
0x180004033  pop     rdi
0x180004034  pop     rsi
0x180004035  retn
0x180004036  mov     rcx, [rsp+278h]; this
0x18000403e  mov     edx, 0A0Bh; void *
0x180004043  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004049  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000404f  mov     rcx, [rsp+278h]; this
0x180004057  mov     edx, 0A0Bh; void *
0x18000405c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

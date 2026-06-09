# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800048c8`
- end: `0x180004af2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800044f8`

## callees

- `0x180001600`
- `0x1800048c8`
- `0x180005168`
- `0x180006a54`
- `0x180007330`
- `0x1800078ac`
- `0x1800078bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000498c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a2f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000498c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a82`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x1800048c8  mov     [rsp+arg_8], rbx
0x1800048cd  mov     [rsp+arg_10], rbp
0x1800048d2  push    rsi
0x1800048d3  push    rdi
0x1800048d4  push    r12
0x1800048d6  push    r14
0x1800048d8  push    r15
0x1800048da  sub     rsp, 250h
0x1800048e1  mov     rax, cs:__security_cookie
0x1800048e8  xor     rax, rsp
0x1800048eb  mov     [rsp+278h+var_38], rax
0x1800048f3  mov     rax, 0C000000000000000h
0x1800048fd  mov     rbp, r9
0x180004900  mov     r8, rdx
0x180004903  mov     rbx, rcx
0x180004906  test    rax, r9
0x180004909  jnz     loc_180004AD9
0x18000490f  xor     r12d, r12d
0x180004912  lea     rax, [rsp+278h+Name]
0x180004917  mov     ecx, 7FFFFFFEh
0x18000491c  mov     edx, 104h
0x180004921  lea     esi, [r12+1]
0x180004926  test    rcx, rcx
0x180004929  jz      short loc_180004949
0x18000492b  movzx   r9d, word ptr [r8]
0x18000492f  test    r9w, r9w
0x180004933  jz      short loc_180004949
0x180004935  mov     [rax], r9w
0x180004939  add     r8, 2
0x18000493d  add     rax, 2
0x180004941  sub     rcx, rsi
0x180004944  sub     rdx, rsi; unsigned __int64
0x180004947  jnz     short loc_180004926
0x180004949  test    rdx, rdx
0x18000494c  lea     rcx, [rax-2]
0x180004950  lea     r8, aP0; "_p0"
0x180004957  cmovnz  rcx, rax
0x18000495b  mov     [rcx], r12w
0x18000495f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004964  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004969  mov     edx, ebp
0x18000496b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004973  and     edx, 7FFFFFFFh; lInitialCount
0x180004979  mov     [rsp+278h+dwFlags], r12d; int
0x18000497e  mov     r8d, esi
0x180004981  lea     r9, [rsp+278h+Name]; lpName
0x180004986  cmova   r8d, edx; lMaximumCount
0x18000498a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000498c  call    cs:__imp_CreateSemaphoreExW
0x180004992  mov     r15, rax
0x180004995  test    rax, rax
0x180004998  jnz     short loc_1800049C8
0x18000499a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000499f  mov     edi, eax
0x1800049a1  test    eax, eax
0x1800049a3  jns     short loc_1800049FC
0x1800049a5  mov     rcx, [rsp+278h]; this
0x1800049ad  lea     r8, aWil; "wil"
0x1800049b4  mov     r9d, eax; char *
0x1800049b7  mov     edx, 8Bh; void *
0x1800049bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049c1  mov     eax, edi
0x1800049c3  jmp     loc_180004A9A
0x1800049c8  call    cs:__imp_GetLastError
0x1800049ce  mov     rdi, [rbx]
0x1800049d1  test    rdi, rdi
0x1800049d4  jz      short loc_1800049F9
0x1800049d6  call    cs:__imp_GetLastError
0x1800049dc  mov     rcx, rdi; hObject
0x1800049df  mov     r14d, eax
0x1800049e2  call    cs:__imp_CloseHandle
0x1800049e8  test    eax, eax
0x1800049ea  jz      loc_180004ADF
0x1800049f0  mov     ecx, r14d; dwErrCode
0x1800049f3  call    cs:__imp_SetLastError
0x1800049f9  mov     [rbx], r15
0x1800049fc  lea     r8, asc_1800125F0; "h"
0x180004a03  shr     rbp, 1Fh
0x180004a07  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004a0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a11  test    ebp, ebp
0x180004a13  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a1b  lea     r9, [rsp+278h+Name]; lpName
0x180004a20  mov     [rsp+278h+dwFlags], r12d; int
0x180004a25  cmovnz  esi, ebp
0x180004a28  mov     edx, ebp; lInitialCount
0x180004a2a  mov     r8d, esi; lMaximumCount
0x180004a2d  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a2f  call    cs:__imp_CreateSemaphoreExW
0x180004a35  mov     rsi, rax
0x180004a38  test    rax, rax
0x180004a3b  jnz     short loc_180004A68
0x180004a3d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a42  mov     ebx, eax
0x180004a44  test    eax, eax
0x180004a46  jns     short loc_180004A98
0x180004a48  mov     rcx, [rsp+278h]; this
0x180004a50  lea     r8, aWil; "wil"
0x180004a57  mov     r9d, eax; char *
0x180004a5a  mov     edx, 90h; void *
0x180004a5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a64  mov     eax, ebx
0x180004a66  jmp     short loc_180004A9A
0x180004a68  call    cs:__imp_GetLastError
0x180004a6e  mov     rdi, [rbx+8]
0x180004a72  test    rdi, rdi
0x180004a75  jz      short loc_180004A94
0x180004a77  call    cs:__imp_GetLastError
0x180004a7d  mov     rcx, rdi; hObject
0x180004a80  mov     ebp, eax
0x180004a82  call    cs:__imp_CloseHandle
0x180004a88  test    eax, eax
0x180004a8a  jz      short loc_180004AC6
0x180004a8c  mov     ecx, ebp; dwErrCode
0x180004a8e  call    cs:__imp_SetLastError
0x180004a94  mov     [rbx+8], rsi
0x180004a98  xor     eax, eax
0x180004a9a  mov     rcx, [rsp+278h+var_38]
0x180004aa2  xor     rcx, rsp; StackCookie
0x180004aa5  call    __security_check_cookie
0x180004aaa  lea     r11, [rsp+278h+var_28]
0x180004ab2  mov     rbx, [r11+38h]
0x180004ab6  mov     rbp, [r11+40h]
0x180004aba  mov     rsp, r11
0x180004abd  pop     r15
0x180004abf  pop     r14
0x180004ac1  pop     r12
0x180004ac3  pop     rdi
0x180004ac4  pop     rsi
0x180004ac5  retn
0x180004ac6  mov     rcx, [rsp+278h]; this
0x180004ace  mov     edx, 0A0Bh; void *
0x180004ad3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ad9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004adf  mov     rcx, [rsp+278h]; this
0x180004ae7  mov     edx, 0A0Bh; void *
0x180004aec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

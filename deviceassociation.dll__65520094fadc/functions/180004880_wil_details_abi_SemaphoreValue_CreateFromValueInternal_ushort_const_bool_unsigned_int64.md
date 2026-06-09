# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004880`
- end: `0x180004a8d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000410c`
- `0x1800044b0`

## callees

- `0x180004880`
- `0x180005608`
- `0x180007490`
- `0x1800078b0`
- `0x18000843c`
- `0x18000844c`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004944`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004944`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004993`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004993`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a1d`

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
0x180004880  mov     [rsp+arg_8], rbx
0x180004885  mov     [rsp+arg_10], rbp
0x18000488a  push    rsi
0x18000488b  push    rdi
0x18000488c  push    r12
0x18000488e  push    r14
0x180004890  push    r15
0x180004892  sub     rsp, 250h
0x180004899  mov     rax, cs:__security_cookie
0x1800048a0  xor     rax, rsp
0x1800048a3  mov     [rsp+278h+var_38], rax
0x1800048ab  mov     rax, 0C000000000000000h
0x1800048b5  mov     rbp, r9
0x1800048b8  mov     r8, rdx
0x1800048bb  mov     rdi, rcx
0x1800048be  test    rax, r9
0x1800048c1  jnz     loc_180004A74
0x1800048c7  xor     r12d, r12d
0x1800048ca  lea     rax, [rsp+278h+Name]
0x1800048cf  mov     ecx, 7FFFFFFEh
0x1800048d4  mov     edx, 104h
0x1800048d9  lea     esi, [r12+1]
0x1800048de  test    rcx, rcx
0x1800048e1  jz      short loc_180004901
0x1800048e3  movzx   r9d, word ptr [r8]
0x1800048e7  test    r9w, r9w
0x1800048eb  jz      short loc_180004901
0x1800048ed  mov     [rax], r9w
0x1800048f1  add     r8, 2
0x1800048f5  add     rax, 2
0x1800048f9  sub     rcx, rsi
0x1800048fc  sub     rdx, rsi; unsigned __int64
0x1800048ff  jnz     short loc_1800048DE
0x180004901  test    rdx, rdx
0x180004904  lea     rcx, [rax-2]
0x180004908  lea     r8, aP0; "_p0"
0x18000490f  cmovnz  rcx, rax
0x180004913  mov     [rcx], r12w
0x180004917  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000491c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004921  mov     edx, ebp
0x180004923  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000492b  and     edx, 7FFFFFFFh; lInitialCount
0x180004931  mov     [rsp+278h+dwFlags], r12d; int
0x180004936  mov     r8d, esi
0x180004939  lea     r9, [rsp+278h+Name]; lpName
0x18000493e  cmova   r8d, edx; lMaximumCount
0x180004942  xor     ecx, ecx; lpSemaphoreAttributes
0x180004944  call    cs:__imp_CreateSemaphoreExW
0x18000494a  mov     r15, rax
0x18000494d  test    rax, rax
0x180004950  jnz     short loc_180004979
0x180004952  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004957  mov     ebx, eax
0x180004959  test    eax, eax
0x18000495b  jns     short loc_1800049AD
0x18000495d  mov     edx, 8Bh; void *
0x180004962  mov     rcx, [rsp+278h]; this
0x18000496a  mov     r9d, ebx; char *
0x18000496d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004972  mov     eax, ebx
0x180004974  jmp     loc_180004A35
0x180004979  call    cs:__imp_GetLastError
0x18000497f  mov     rbx, [rdi]
0x180004982  test    rbx, rbx
0x180004985  jz      short loc_1800049AA
0x180004987  call    cs:__imp_GetLastError
0x18000498d  mov     rcx, rbx; hObject
0x180004990  mov     r14d, eax
0x180004993  call    cs:__imp_CloseHandle
0x180004999  test    eax, eax
0x18000499b  jz      loc_180004A7A
0x1800049a1  mov     ecx, r14d; dwErrCode
0x1800049a4  call    cs:__imp_SetLastError
0x1800049aa  mov     [rdi], r15
0x1800049ad  lea     r8, asc_1800108E0; "h"
0x1800049b4  shr     rbp, 1Fh
0x1800049b8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800049bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800049c2  test    ebp, ebp
0x1800049c4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800049cc  lea     r9, [rsp+278h+Name]; lpName
0x1800049d1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800049d6  cmovnz  esi, ebp
0x1800049d9  mov     edx, ebp; lInitialCount
0x1800049db  mov     r8d, esi; lMaximumCount
0x1800049de  xor     ecx, ecx; lpSemaphoreAttributes
0x1800049e0  call    cs:__imp_CreateSemaphoreExW
0x1800049e6  mov     rsi, rax
0x1800049e9  test    rax, rax
0x1800049ec  jnz     short loc_180004A03
0x1800049ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049f3  mov     ebx, eax
0x1800049f5  test    eax, eax
0x1800049f7  jns     short loc_180004A33
0x1800049f9  mov     edx, 90h
0x1800049fe  jmp     loc_180004962
0x180004a03  call    cs:__imp_GetLastError
0x180004a09  mov     rbx, [rdi+8]
0x180004a0d  test    rbx, rbx
0x180004a10  jz      short loc_180004A2F
0x180004a12  call    cs:__imp_GetLastError
0x180004a18  mov     rcx, rbx; hObject
0x180004a1b  mov     ebp, eax
0x180004a1d  call    cs:__imp_CloseHandle
0x180004a23  test    eax, eax
0x180004a25  jz      short loc_180004A61
0x180004a27  mov     ecx, ebp; dwErrCode
0x180004a29  call    cs:__imp_SetLastError
0x180004a2f  mov     [rdi+8], rsi
0x180004a33  xor     eax, eax
0x180004a35  mov     rcx, [rsp+278h+var_38]
0x180004a3d  xor     rcx, rsp; StackCookie
0x180004a40  call    __security_check_cookie
0x180004a45  lea     r11, [rsp+278h+var_28]
0x180004a4d  mov     rbx, [r11+38h]
0x180004a51  mov     rbp, [r11+40h]
0x180004a55  mov     rsp, r11
0x180004a58  pop     r15
0x180004a5a  pop     r14
0x180004a5c  pop     r12
0x180004a5e  pop     rdi
0x180004a5f  pop     rsi
0x180004a60  retn
0x180004a61  mov     rcx, [rsp+278h]; this
0x180004a69  mov     edx, 0A0Bh; void *
0x180004a6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a74  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a7a  mov     rcx, [rsp+278h]; this
0x180004a82  mov     edx, 0A0Bh; void *
0x180004a87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

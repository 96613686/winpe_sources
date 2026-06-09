# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004290`
- end: `0x1800044c1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ac8`
- `0x180003e98`

## callees

- `0x1800016d0`
- `0x180004290`
- `0x180005108`
- `0x180007684`
- `0x1800080c8`
- `0x180008ebc`
- `0x180008ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004359`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043ff`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004359`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004447`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004452`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
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
0x180004290  mov     [rsp+arg_8], rbx
0x180004295  push    rbp
0x180004296  push    rsi
0x180004297  push    rdi
0x180004298  push    r12
0x18000429a  push    r13
0x18000429c  push    r14
0x18000429e  push    r15
0x1800042a0  sub     rsp, 250h
0x1800042a7  mov     rax, cs:__security_cookie
0x1800042ae  xor     rax, rsp
0x1800042b1  mov     [rsp+288h+var_48], rax
0x1800042b9  mov     rax, 0C000000000000000h
0x1800042c3  mov     rsi, r9
0x1800042c6  mov     r8, rdx
0x1800042c9  mov     rbx, rcx
0x1800042cc  test    rax, r9
0x1800042cf  jnz     loc_1800044A8
0x1800042d5  xor     r12d, r12d
0x1800042d8  lea     rax, [rsp+288h+Name]
0x1800042dd  mov     r13d, 104h
0x1800042e3  mov     ecx, 7FFFFFFEh
0x1800042e8  mov     edx, r13d
0x1800042eb  lea     ebp, [r12+1]
0x1800042f0  test    rcx, rcx
0x1800042f3  jz      short loc_180004313
0x1800042f5  movzx   r9d, word ptr [r8]
0x1800042f9  test    r9w, r9w
0x1800042fd  jz      short loc_180004313
0x1800042ff  mov     [rax], r9w
0x180004303  add     r8, 2
0x180004307  add     rax, 2
0x18000430b  sub     rcx, rbp
0x18000430e  sub     rdx, rbp
0x180004311  jnz     short loc_1800042F0
0x180004313  test    rdx, rdx
0x180004316  lea     rcx, [rax-2]
0x18000431a  lea     r8, aP0; "_p0"
0x180004321  mov     rdx, r13; unsigned __int64
0x180004324  cmovnz  rcx, rax
0x180004328  mov     [rcx], r12w
0x18000432c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004331  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004336  mov     edx, esi
0x180004338  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004340  and     edx, 7FFFFFFFh; lInitialCount
0x180004346  mov     [rsp+288h+dwFlags], r12d; int
0x18000434b  mov     r8d, ebp
0x18000434e  lea     r9, [rsp+288h+Name]; lpName
0x180004353  cmova   r8d, edx; lMaximumCount
0x180004357  xor     ecx, ecx; lpSemaphoreAttributes
0x180004359  call    cs:__imp_CreateSemaphoreExW
0x18000435f  mov     r15, rax
0x180004362  test    rax, rax
0x180004365  jnz     short loc_180004395
0x180004367  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000436c  mov     edi, eax
0x18000436e  test    eax, eax
0x180004370  jns     short loc_1800043C9
0x180004372  mov     rcx, [rsp+288h]; this
0x18000437a  lea     r8, aWil; "wil"
0x180004381  mov     r9d, eax; char *
0x180004384  mov     edx, 8Bh; void *
0x180004389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000438e  mov     eax, edi
0x180004390  jmp     loc_18000446A
0x180004395  call    cs:__imp_GetLastError
0x18000439b  mov     rdi, [rbx]
0x18000439e  test    rdi, rdi
0x1800043a1  jz      short loc_1800043C6
0x1800043a3  call    cs:__imp_GetLastError
0x1800043a9  mov     rcx, rdi; hObject
0x1800043ac  mov     r14d, eax
0x1800043af  call    cs:__imp_CloseHandle
0x1800043b5  test    eax, eax
0x1800043b7  jz      loc_1800044AE
0x1800043bd  mov     ecx, r14d; dwErrCode
0x1800043c0  call    cs:__imp_SetLastError
0x1800043c6  mov     [rbx], r15
0x1800043c9  lea     r8, asc_180025338; "h"
0x1800043d0  shr     rsi, 1Fh
0x1800043d4  mov     rdx, r13; unsigned __int64
0x1800043d7  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800043dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043e1  test    esi, esi
0x1800043e3  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043eb  lea     r9, [rsp+288h+Name]; lpName
0x1800043f0  mov     [rsp+288h+dwFlags], r12d; int
0x1800043f5  cmovnz  ebp, esi
0x1800043f8  mov     edx, esi; lInitialCount
0x1800043fa  mov     r8d, ebp; lMaximumCount
0x1800043fd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800043ff  call    cs:__imp_CreateSemaphoreExW
0x180004405  mov     rbp, rax
0x180004408  test    rax, rax
0x18000440b  jnz     short loc_180004438
0x18000440d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004412  mov     ebx, eax
0x180004414  test    eax, eax
0x180004416  jns     short loc_180004468
0x180004418  mov     rcx, [rsp+288h]; this
0x180004420  lea     r8, aWil; "wil"
0x180004427  mov     r9d, eax; char *
0x18000442a  mov     edx, 90h; void *
0x18000442f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004434  mov     eax, ebx
0x180004436  jmp     short loc_18000446A
0x180004438  call    cs:__imp_GetLastError
0x18000443e  mov     rdi, [rbx+8]
0x180004442  test    rdi, rdi
0x180004445  jz      short loc_180004464
0x180004447  call    cs:__imp_GetLastError
0x18000444d  mov     rcx, rdi; hObject
0x180004450  mov     esi, eax
0x180004452  call    cs:__imp_CloseHandle
0x180004458  test    eax, eax
0x18000445a  jz      short loc_180004495
0x18000445c  mov     ecx, esi; dwErrCode
0x18000445e  call    cs:__imp_SetLastError
0x180004464  mov     [rbx+8], rbp
0x180004468  xor     eax, eax
0x18000446a  mov     rcx, [rsp+288h+var_48]
0x180004472  xor     rcx, rsp; StackCookie
0x180004475  call    __security_check_cookie
0x18000447a  mov     rbx, [rsp+288h+arg_8]
0x180004482  add     rsp, 250h
0x180004489  pop     r15
0x18000448b  pop     r14
0x18000448d  pop     r13
0x18000448f  pop     r12
0x180004491  pop     rdi
0x180004492  pop     rsi
0x180004493  pop     rbp
0x180004494  retn
0x180004495  mov     rcx, [rsp+288h]; this
0x18000449d  mov     edx, 0A0Bh; void *
0x1800044a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800044ae  mov     rcx, [rsp+288h]; this
0x1800044b6  mov     edx, 0A0Bh; void *
0x1800044bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

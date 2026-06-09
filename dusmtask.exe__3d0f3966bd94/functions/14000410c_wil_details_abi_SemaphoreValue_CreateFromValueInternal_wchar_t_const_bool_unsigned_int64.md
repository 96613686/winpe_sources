# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x14000410c`
- end: `0x140004319`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003d68`

## callees

- `0x140001470`
- `0x14000410c`
- `0x1400049a8`
- `0x1400059c4`
- `0x14000676c`
- `0x140006ccc`
- `0x140006cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400041d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000426c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400041d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000426c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000428f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000428f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000429e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004230`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004230`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000421f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000421f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042a9`

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
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
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
0x14000410c  mov     [rsp+arg_8], rbx
0x140004111  mov     [rsp+arg_10], rbp
0x140004116  push    rsi
0x140004117  push    rdi
0x140004118  push    r12
0x14000411a  push    r14
0x14000411c  push    r15
0x14000411e  sub     rsp, 250h
0x140004125  mov     rax, cs:__security_cookie
0x14000412c  xor     rax, rsp
0x14000412f  mov     [rsp+278h+var_38], rax
0x140004137  mov     rax, 0C000000000000000h
0x140004141  mov     rbp, r9
0x140004144  mov     r8, rdx
0x140004147  mov     rdi, rcx
0x14000414a  test    rax, r9
0x14000414d  jnz     loc_140004300
0x140004153  xor     r12d, r12d
0x140004156  lea     rax, [rsp+278h+Name]
0x14000415b  mov     ecx, 7FFFFFFEh
0x140004160  mov     edx, 104h
0x140004165  lea     esi, [r12+1]
0x14000416a  test    rcx, rcx
0x14000416d  jz      short loc_14000418D
0x14000416f  movzx   r9d, word ptr [r8]
0x140004173  test    r9w, r9w
0x140004177  jz      short loc_14000418D
0x140004179  mov     [rax], r9w
0x14000417d  add     r8, 2
0x140004181  add     rax, 2
0x140004185  sub     rcx, rsi
0x140004188  sub     rdx, rsi; unsigned __int64
0x14000418b  jnz     short loc_14000416A
0x14000418d  test    rdx, rdx
0x140004190  lea     rcx, [rax-2]
0x140004194  lea     r8, aP0; "_p0"
0x14000419b  cmovnz  rcx, rax
0x14000419f  mov     [rcx], r12w
0x1400041a3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1400041a8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400041ad  mov     edx, ebp
0x1400041af  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400041b7  and     edx, 7FFFFFFFh; lInitialCount
0x1400041bd  mov     [rsp+278h+dwFlags], r12d; int
0x1400041c2  mov     r8d, esi
0x1400041c5  lea     r9, [rsp+278h+Name]; lpName
0x1400041ca  cmova   r8d, edx; lMaximumCount
0x1400041ce  xor     ecx, ecx; lpSemaphoreAttributes
0x1400041d0  call    cs:__imp_CreateSemaphoreExW
0x1400041d6  mov     r15, rax
0x1400041d9  test    rax, rax
0x1400041dc  jnz     short loc_140004205
0x1400041de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400041e3  mov     ebx, eax
0x1400041e5  test    eax, eax
0x1400041e7  jns     short loc_140004239
0x1400041e9  mov     edx, 8Bh; void *
0x1400041ee  mov     rcx, [rsp+278h]; this
0x1400041f6  mov     r9d, ebx; char *
0x1400041f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400041fe  mov     eax, ebx
0x140004200  jmp     loc_1400042C1
0x140004205  call    cs:__imp_GetLastError
0x14000420b  mov     rbx, [rdi]
0x14000420e  test    rbx, rbx
0x140004211  jz      short loc_140004236
0x140004213  call    cs:__imp_GetLastError
0x140004219  mov     rcx, rbx; hObject
0x14000421c  mov     r14d, eax
0x14000421f  call    cs:__imp_CloseHandle
0x140004225  test    eax, eax
0x140004227  jz      loc_140004306
0x14000422d  mov     ecx, r14d; dwErrCode
0x140004230  call    cs:__imp_SetLastError
0x140004236  mov     [rdi], r15
0x140004239  lea     r8, asc_140009AE8; "h"
0x140004240  shr     rbp, 1Fh
0x140004244  lea     rcx, [rsp+278h+Name]; wchar_t *
0x140004249  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000424e  test    ebp, ebp
0x140004250  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004258  lea     r9, [rsp+278h+Name]; lpName
0x14000425d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004262  cmovnz  esi, ebp
0x140004265  mov     edx, ebp; lInitialCount
0x140004267  mov     r8d, esi; lMaximumCount
0x14000426a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000426c  call    cs:__imp_CreateSemaphoreExW
0x140004272  mov     rsi, rax
0x140004275  test    rax, rax
0x140004278  jnz     short loc_14000428F
0x14000427a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000427f  mov     ebx, eax
0x140004281  test    eax, eax
0x140004283  jns     short loc_1400042BF
0x140004285  mov     edx, 90h
0x14000428a  jmp     loc_1400041EE
0x14000428f  call    cs:__imp_GetLastError
0x140004295  mov     rbx, [rdi+8]
0x140004299  test    rbx, rbx
0x14000429c  jz      short loc_1400042BB
0x14000429e  call    cs:__imp_GetLastError
0x1400042a4  mov     rcx, rbx; hObject
0x1400042a7  mov     ebp, eax
0x1400042a9  call    cs:__imp_CloseHandle
0x1400042af  test    eax, eax
0x1400042b1  jz      short loc_1400042ED
0x1400042b3  mov     ecx, ebp; dwErrCode
0x1400042b5  call    cs:__imp_SetLastError
0x1400042bb  mov     [rdi+8], rsi
0x1400042bf  xor     eax, eax
0x1400042c1  mov     rcx, [rsp+278h+var_38]
0x1400042c9  xor     rcx, rsp; StackCookie
0x1400042cc  call    __security_check_cookie
0x1400042d1  lea     r11, [rsp+278h+var_28]
0x1400042d9  mov     rbx, [r11+38h]
0x1400042dd  mov     rbp, [r11+40h]
0x1400042e1  mov     rsp, r11
0x1400042e4  pop     r15
0x1400042e6  pop     r14
0x1400042e8  pop     r12
0x1400042ea  pop     rdi
0x1400042eb  pop     rsi
0x1400042ec  retn
0x1400042ed  mov     rcx, [rsp+278h]; this
0x1400042f5  mov     edx, 0A0Bh; void *
0x1400042fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004300  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004306  mov     rcx, [rsp+278h]; this
0x14000430e  mov     edx, 0A0Bh; void *
0x140004313  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

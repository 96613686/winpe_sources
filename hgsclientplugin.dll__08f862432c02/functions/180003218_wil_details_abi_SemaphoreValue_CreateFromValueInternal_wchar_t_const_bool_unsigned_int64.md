# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180003218`
- end: `0x180003442`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002e48`

## callees

- `0x180001520`
- `0x180003218`
- `0x180003aa8`
- `0x1800049f4`
- `0x1800052d0`
- `0x18000581c`
- `0x18000582c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800032dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000337f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800032dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000337f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033d2`

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
0x180003218  mov     [rsp+arg_8], rbx
0x18000321d  mov     [rsp+arg_10], rbp
0x180003222  push    rsi
0x180003223  push    rdi
0x180003224  push    r12
0x180003226  push    r14
0x180003228  push    r15
0x18000322a  sub     rsp, 250h
0x180003231  mov     rax, cs:__security_cookie
0x180003238  xor     rax, rsp
0x18000323b  mov     [rsp+278h+var_38], rax
0x180003243  mov     rax, 0C000000000000000h
0x18000324d  mov     rbp, r9
0x180003250  mov     r8, rdx
0x180003253  mov     rbx, rcx
0x180003256  test    rax, r9
0x180003259  jnz     loc_180003429
0x18000325f  xor     r12d, r12d
0x180003262  lea     rax, [rsp+278h+Name]
0x180003267  mov     ecx, 7FFFFFFEh
0x18000326c  mov     edx, 104h
0x180003271  lea     esi, [r12+1]
0x180003276  test    rcx, rcx
0x180003279  jz      short loc_180003299
0x18000327b  movzx   r9d, word ptr [r8]
0x18000327f  test    r9w, r9w
0x180003283  jz      short loc_180003299
0x180003285  mov     [rax], r9w
0x180003289  add     r8, 2
0x18000328d  add     rax, 2
0x180003291  sub     rcx, rsi
0x180003294  sub     rdx, rsi; unsigned __int64
0x180003297  jnz     short loc_180003276
0x180003299  test    rdx, rdx
0x18000329c  lea     rcx, [rax-2]
0x1800032a0  lea     r8, aP0; "_p0"
0x1800032a7  cmovnz  rcx, rax
0x1800032ab  mov     [rcx], r12w
0x1800032af  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800032b4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800032b9  mov     edx, ebp
0x1800032bb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800032c3  and     edx, 7FFFFFFFh; lInitialCount
0x1800032c9  mov     [rsp+278h+dwFlags], r12d; int
0x1800032ce  mov     r8d, esi
0x1800032d1  lea     r9, [rsp+278h+Name]; lpName
0x1800032d6  cmova   r8d, edx; lMaximumCount
0x1800032da  xor     ecx, ecx; lpSemaphoreAttributes
0x1800032dc  call    cs:__imp_CreateSemaphoreExW
0x1800032e2  mov     r15, rax
0x1800032e5  test    rax, rax
0x1800032e8  jnz     short loc_180003318
0x1800032ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800032ef  mov     edi, eax
0x1800032f1  test    eax, eax
0x1800032f3  jns     short loc_18000334C
0x1800032f5  mov     rcx, [rsp+278h]; this
0x1800032fd  lea     r8, aWil; "wil"
0x180003304  mov     r9d, eax; char *
0x180003307  mov     edx, 8Bh; void *
0x18000330c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003311  mov     eax, edi
0x180003313  jmp     loc_1800033EA
0x180003318  call    cs:__imp_GetLastError
0x18000331e  mov     rdi, [rbx]
0x180003321  test    rdi, rdi
0x180003324  jz      short loc_180003349
0x180003326  call    cs:__imp_GetLastError
0x18000332c  mov     rcx, rdi; hObject
0x18000332f  mov     r14d, eax
0x180003332  call    cs:__imp_CloseHandle
0x180003338  test    eax, eax
0x18000333a  jz      loc_18000342F
0x180003340  mov     ecx, r14d; dwErrCode
0x180003343  call    cs:__imp_SetLastError
0x180003349  mov     [rbx], r15
0x18000334c  lea     r8, asc_18000D960; "h"
0x180003353  shr     rbp, 1Fh
0x180003357  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000335c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003361  test    ebp, ebp
0x180003363  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000336b  lea     r9, [rsp+278h+Name]; lpName
0x180003370  mov     [rsp+278h+dwFlags], r12d; int
0x180003375  cmovnz  esi, ebp
0x180003378  mov     edx, ebp; lInitialCount
0x18000337a  mov     r8d, esi; lMaximumCount
0x18000337d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000337f  call    cs:__imp_CreateSemaphoreExW
0x180003385  mov     rsi, rax
0x180003388  test    rax, rax
0x18000338b  jnz     short loc_1800033B8
0x18000338d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003392  mov     ebx, eax
0x180003394  test    eax, eax
0x180003396  jns     short loc_1800033E8
0x180003398  mov     rcx, [rsp+278h]; this
0x1800033a0  lea     r8, aWil; "wil"
0x1800033a7  mov     r9d, eax; char *
0x1800033aa  mov     edx, 90h; void *
0x1800033af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033b4  mov     eax, ebx
0x1800033b6  jmp     short loc_1800033EA
0x1800033b8  call    cs:__imp_GetLastError
0x1800033be  mov     rdi, [rbx+8]
0x1800033c2  test    rdi, rdi
0x1800033c5  jz      short loc_1800033E4
0x1800033c7  call    cs:__imp_GetLastError
0x1800033cd  mov     rcx, rdi; hObject
0x1800033d0  mov     ebp, eax
0x1800033d2  call    cs:__imp_CloseHandle
0x1800033d8  test    eax, eax
0x1800033da  jz      short loc_180003416
0x1800033dc  mov     ecx, ebp; dwErrCode
0x1800033de  call    cs:__imp_SetLastError
0x1800033e4  mov     [rbx+8], rsi
0x1800033e8  xor     eax, eax
0x1800033ea  mov     rcx, [rsp+278h+var_38]
0x1800033f2  xor     rcx, rsp; StackCookie
0x1800033f5  call    __security_check_cookie
0x1800033fa  lea     r11, [rsp+278h+var_28]
0x180003402  mov     rbx, [r11+38h]
0x180003406  mov     rbp, [r11+40h]
0x18000340a  mov     rsp, r11
0x18000340d  pop     r15
0x18000340f  pop     r14
0x180003411  pop     r12
0x180003413  pop     rdi
0x180003414  pop     rsi
0x180003415  retn
0x180003416  mov     rcx, [rsp+278h]; this
0x18000341e  mov     edx, 0A0Bh; void *
0x180003423  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003429  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000342f  mov     rcx, [rsp+278h]; this
0x180003437  mov     edx, 0A0Bh; void *
0x18000343c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

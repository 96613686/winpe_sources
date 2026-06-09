# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004110`
- end: `0x18000433a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003d40`
- `0x180007e80`

## callees

- `0x180004110`
- `0x180004988`
- `0x1800056c4`
- `0x1800060c8`
- `0x180006790`
- `0x1800067a0`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800041d4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004277`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800041d4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004277`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000423b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000423b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000421e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000421e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000422a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000422a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042ca`

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
0x180004110  mov     [rsp+arg_8], rbx
0x180004115  mov     [rsp+arg_10], rbp
0x18000411a  push    rsi
0x18000411b  push    rdi
0x18000411c  push    r12
0x18000411e  push    r14
0x180004120  push    r15
0x180004122  sub     rsp, 250h
0x180004129  mov     rax, cs:__security_cookie
0x180004130  xor     rax, rsp
0x180004133  mov     [rsp+278h+var_38], rax
0x18000413b  mov     rax, 0C000000000000000h
0x180004145  mov     rbp, r9
0x180004148  mov     r8, rdx
0x18000414b  mov     rbx, rcx
0x18000414e  test    rax, r9
0x180004151  jnz     loc_180004321
0x180004157  xor     r12d, r12d
0x18000415a  lea     rax, [rsp+278h+Name]
0x18000415f  mov     ecx, 7FFFFFFEh
0x180004164  mov     edx, 104h
0x180004169  lea     esi, [r12+1]
0x18000416e  test    rcx, rcx
0x180004171  jz      short loc_180004191
0x180004173  movzx   r9d, word ptr [r8]
0x180004177  test    r9w, r9w
0x18000417b  jz      short loc_180004191
0x18000417d  mov     [rax], r9w
0x180004181  add     r8, 2
0x180004185  add     rax, 2
0x180004189  sub     rcx, rsi
0x18000418c  sub     rdx, rsi; unsigned __int64
0x18000418f  jnz     short loc_18000416E
0x180004191  test    rdx, rdx
0x180004194  lea     rcx, [rax-2]
0x180004198  lea     r8, aP0; "_p0"
0x18000419f  cmovnz  rcx, rax
0x1800041a3  mov     [rcx], r12w
0x1800041a7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800041ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800041b1  mov     edx, ebp
0x1800041b3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800041bb  and     edx, 7FFFFFFFh; lInitialCount
0x1800041c1  mov     [rsp+278h+dwFlags], r12d; int
0x1800041c6  mov     r8d, esi
0x1800041c9  lea     r9, [rsp+278h+Name]; lpName
0x1800041ce  cmova   r8d, edx; lMaximumCount
0x1800041d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800041d4  call    cs:__imp_CreateSemaphoreExW
0x1800041da  mov     r15, rax
0x1800041dd  test    rax, rax
0x1800041e0  jnz     short loc_180004210
0x1800041e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800041e7  mov     edi, eax
0x1800041e9  test    eax, eax
0x1800041eb  jns     short loc_180004244
0x1800041ed  mov     rcx, [rsp+278h]; this
0x1800041f5  lea     r8, aWil; "wil"
0x1800041fc  mov     r9d, eax; char *
0x1800041ff  mov     edx, 8Bh; void *
0x180004204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004209  mov     eax, edi
0x18000420b  jmp     loc_1800042E2
0x180004210  call    cs:__imp_GetLastError
0x180004216  mov     rdi, [rbx]
0x180004219  test    rdi, rdi
0x18000421c  jz      short loc_180004241
0x18000421e  call    cs:__imp_GetLastError
0x180004224  mov     rcx, rdi; hObject
0x180004227  mov     r14d, eax
0x18000422a  call    cs:__imp_CloseHandle
0x180004230  test    eax, eax
0x180004232  jz      loc_180004327
0x180004238  mov     ecx, r14d; dwErrCode
0x18000423b  call    cs:__imp_SetLastError
0x180004241  mov     [rbx], r15
0x180004244  lea     r8, asc_180017B10; "h"
0x18000424b  shr     rbp, 1Fh
0x18000424f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004254  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004259  test    ebp, ebp
0x18000425b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004263  lea     r9, [rsp+278h+Name]; lpName
0x180004268  mov     [rsp+278h+dwFlags], r12d; int
0x18000426d  cmovnz  esi, ebp
0x180004270  mov     edx, ebp; lInitialCount
0x180004272  mov     r8d, esi; lMaximumCount
0x180004275  xor     ecx, ecx; lpSemaphoreAttributes
0x180004277  call    cs:__imp_CreateSemaphoreExW
0x18000427d  mov     rsi, rax
0x180004280  test    rax, rax
0x180004283  jnz     short loc_1800042B0
0x180004285  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000428a  mov     ebx, eax
0x18000428c  test    eax, eax
0x18000428e  jns     short loc_1800042E0
0x180004290  mov     rcx, [rsp+278h]; this
0x180004298  lea     r8, aWil; "wil"
0x18000429f  mov     r9d, eax; char *
0x1800042a2  mov     edx, 90h; void *
0x1800042a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042ac  mov     eax, ebx
0x1800042ae  jmp     short loc_1800042E2
0x1800042b0  call    cs:__imp_GetLastError
0x1800042b6  mov     rdi, [rbx+8]
0x1800042ba  test    rdi, rdi
0x1800042bd  jz      short loc_1800042DC
0x1800042bf  call    cs:__imp_GetLastError
0x1800042c5  mov     rcx, rdi; hObject
0x1800042c8  mov     ebp, eax
0x1800042ca  call    cs:__imp_CloseHandle
0x1800042d0  test    eax, eax
0x1800042d2  jz      short loc_18000430E
0x1800042d4  mov     ecx, ebp; dwErrCode
0x1800042d6  call    cs:__imp_SetLastError
0x1800042dc  mov     [rbx+8], rsi
0x1800042e0  xor     eax, eax
0x1800042e2  mov     rcx, [rsp+278h+var_38]
0x1800042ea  xor     rcx, rsp; StackCookie
0x1800042ed  call    __security_check_cookie
0x1800042f2  lea     r11, [rsp+278h+var_28]
0x1800042fa  mov     rbx, [r11+38h]
0x1800042fe  mov     rbp, [r11+40h]
0x180004302  mov     rsp, r11
0x180004305  pop     r15
0x180004307  pop     r14
0x180004309  pop     r12
0x18000430b  pop     rdi
0x18000430c  pop     rsi
0x18000430d  retn
0x18000430e  mov     rcx, [rsp+278h]; this
0x180004316  mov     edx, 0A0Bh; void *
0x18000431b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004321  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004327  mov     rcx, [rsp+278h]; this
0x18000432f  mov     edx, 0A0Bh; void *
0x180004334  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

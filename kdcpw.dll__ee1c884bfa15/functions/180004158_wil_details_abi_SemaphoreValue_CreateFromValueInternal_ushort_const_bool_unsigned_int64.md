# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004158`
- end: `0x180004365`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800039e4`
- `0x180003d88`

## callees

- `0x180001630`
- `0x180004158`
- `0x180005258`
- `0x180007bd4`
- `0x180007fec`
- `0x180008eac`
- `0x180008ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000421c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042b8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000421c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000425f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000425f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000427c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000427c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f5`

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
0x180004158  mov     [rsp+arg_8], rbx
0x18000415d  mov     [rsp+arg_10], rbp
0x180004162  push    rsi
0x180004163  push    rdi
0x180004164  push    r12
0x180004166  push    r14
0x180004168  push    r15
0x18000416a  sub     rsp, 250h
0x180004171  mov     rax, cs:__security_cookie
0x180004178  xor     rax, rsp
0x18000417b  mov     [rsp+278h+var_38], rax
0x180004183  mov     rax, 0C000000000000000h
0x18000418d  mov     rbp, r9
0x180004190  mov     r8, rdx
0x180004193  mov     rdi, rcx
0x180004196  test    rax, r9
0x180004199  jnz     loc_18000434C
0x18000419f  xor     r12d, r12d
0x1800041a2  lea     rax, [rsp+278h+Name]
0x1800041a7  mov     ecx, 7FFFFFFEh
0x1800041ac  mov     edx, 104h
0x1800041b1  lea     esi, [r12+1]
0x1800041b6  test    rcx, rcx
0x1800041b9  jz      short loc_1800041D9
0x1800041bb  movzx   r9d, word ptr [r8]
0x1800041bf  test    r9w, r9w
0x1800041c3  jz      short loc_1800041D9
0x1800041c5  mov     [rax], r9w
0x1800041c9  add     r8, 2
0x1800041cd  add     rax, 2
0x1800041d1  sub     rcx, rsi
0x1800041d4  sub     rdx, rsi; unsigned __int64
0x1800041d7  jnz     short loc_1800041B6
0x1800041d9  test    rdx, rdx
0x1800041dc  lea     rcx, [rax-2]
0x1800041e0  lea     r8, aP0; "_p0"
0x1800041e7  cmovnz  rcx, rax
0x1800041eb  mov     [rcx], r12w
0x1800041ef  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800041f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800041f9  mov     edx, ebp
0x1800041fb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004203  and     edx, 7FFFFFFFh; lInitialCount
0x180004209  mov     [rsp+278h+dwFlags], r12d; int
0x18000420e  mov     r8d, esi
0x180004211  lea     r9, [rsp+278h+Name]; lpName
0x180004216  cmova   r8d, edx; lMaximumCount
0x18000421a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000421c  call    cs:__imp_CreateSemaphoreExW
0x180004222  mov     r15, rax
0x180004225  test    rax, rax
0x180004228  jnz     short loc_180004251
0x18000422a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000422f  mov     ebx, eax
0x180004231  test    eax, eax
0x180004233  jns     short loc_180004285
0x180004235  mov     edx, 8Bh; void *
0x18000423a  mov     rcx, [rsp+278h]; this
0x180004242  mov     r9d, ebx; char *
0x180004245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000424a  mov     eax, ebx
0x18000424c  jmp     loc_18000430D
0x180004251  call    cs:__imp_GetLastError
0x180004257  mov     rbx, [rdi]
0x18000425a  test    rbx, rbx
0x18000425d  jz      short loc_180004282
0x18000425f  call    cs:__imp_GetLastError
0x180004265  mov     rcx, rbx; hObject
0x180004268  mov     r14d, eax
0x18000426b  call    cs:__imp_CloseHandle
0x180004271  test    eax, eax
0x180004273  jz      loc_180004352
0x180004279  mov     ecx, r14d; dwErrCode
0x18000427c  call    cs:__imp_SetLastError
0x180004282  mov     [rdi], r15
0x180004285  lea     r8, asc_18000ECA0; "h"
0x18000428c  shr     rbp, 1Fh
0x180004290  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004295  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000429a  test    ebp, ebp
0x18000429c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800042a4  lea     r9, [rsp+278h+Name]; lpName
0x1800042a9  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800042ae  cmovnz  esi, ebp
0x1800042b1  mov     edx, ebp; lInitialCount
0x1800042b3  mov     r8d, esi; lMaximumCount
0x1800042b6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800042b8  call    cs:__imp_CreateSemaphoreExW
0x1800042be  mov     rsi, rax
0x1800042c1  test    rax, rax
0x1800042c4  jnz     short loc_1800042DB
0x1800042c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800042cb  mov     ebx, eax
0x1800042cd  test    eax, eax
0x1800042cf  jns     short loc_18000430B
0x1800042d1  mov     edx, 90h
0x1800042d6  jmp     loc_18000423A
0x1800042db  call    cs:__imp_GetLastError
0x1800042e1  mov     rbx, [rdi+8]
0x1800042e5  test    rbx, rbx
0x1800042e8  jz      short loc_180004307
0x1800042ea  call    cs:__imp_GetLastError
0x1800042f0  mov     rcx, rbx; hObject
0x1800042f3  mov     ebp, eax
0x1800042f5  call    cs:__imp_CloseHandle
0x1800042fb  test    eax, eax
0x1800042fd  jz      short loc_180004339
0x1800042ff  mov     ecx, ebp; dwErrCode
0x180004301  call    cs:__imp_SetLastError
0x180004307  mov     [rdi+8], rsi
0x18000430b  xor     eax, eax
0x18000430d  mov     rcx, [rsp+278h+var_38]
0x180004315  xor     rcx, rsp; StackCookie
0x180004318  call    __security_check_cookie
0x18000431d  lea     r11, [rsp+278h+var_28]
0x180004325  mov     rbx, [r11+38h]
0x180004329  mov     rbp, [r11+40h]
0x18000432d  mov     rsp, r11
0x180004330  pop     r15
0x180004332  pop     r14
0x180004334  pop     r12
0x180004336  pop     rdi
0x180004337  pop     rsi
0x180004338  retn
0x180004339  mov     rcx, [rsp+278h]; this
0x180004341  mov     edx, 0A0Bh; void *
0x180004346  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000434c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004352  mov     rcx, [rsp+278h]; this
0x18000435a  mov     edx, 0A0Bh; void *
0x18000435f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

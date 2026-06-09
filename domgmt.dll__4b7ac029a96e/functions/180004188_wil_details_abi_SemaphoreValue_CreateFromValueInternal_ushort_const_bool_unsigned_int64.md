# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004188`
- end: `0x1800043b2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003db8`

## callees

- `0x180001ba0`
- `0x180004188`
- `0x180004a18`
- `0x180005964`
- `0x180006240`
- `0x1800067ac`
- `0x1800067bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000424c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042ef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000424c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004337`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000434e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000434e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004342`

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
0x180004188  mov     [rsp+arg_8], rbx
0x18000418d  mov     [rsp+arg_10], rbp
0x180004192  push    rsi
0x180004193  push    rdi
0x180004194  push    r12
0x180004196  push    r14
0x180004198  push    r15
0x18000419a  sub     rsp, 250h
0x1800041a1  mov     rax, cs:__security_cookie
0x1800041a8  xor     rax, rsp
0x1800041ab  mov     [rsp+278h+var_38], rax
0x1800041b3  mov     rax, 0C000000000000000h
0x1800041bd  mov     rbp, r9
0x1800041c0  mov     r8, rdx
0x1800041c3  mov     rbx, rcx
0x1800041c6  test    rax, r9
0x1800041c9  jnz     loc_180004399
0x1800041cf  xor     r12d, r12d
0x1800041d2  lea     rax, [rsp+278h+Name]
0x1800041d7  mov     ecx, 7FFFFFFEh
0x1800041dc  mov     edx, 104h
0x1800041e1  lea     esi, [r12+1]
0x1800041e6  test    rcx, rcx
0x1800041e9  jz      short loc_180004209
0x1800041eb  movzx   r9d, word ptr [r8]
0x1800041ef  test    r9w, r9w
0x1800041f3  jz      short loc_180004209
0x1800041f5  mov     [rax], r9w
0x1800041f9  add     r8, 2
0x1800041fd  add     rax, 2
0x180004201  sub     rcx, rsi
0x180004204  sub     rdx, rsi; unsigned __int64
0x180004207  jnz     short loc_1800041E6
0x180004209  test    rdx, rdx
0x18000420c  lea     rcx, [rax-2]
0x180004210  lea     r8, aP0; "_p0"
0x180004217  cmovnz  rcx, rax
0x18000421b  mov     [rcx], r12w
0x18000421f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004224  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004229  mov     edx, ebp
0x18000422b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004233  and     edx, 7FFFFFFFh; lInitialCount
0x180004239  mov     [rsp+278h+dwFlags], r12d; int
0x18000423e  mov     r8d, esi
0x180004241  lea     r9, [rsp+278h+Name]; lpName
0x180004246  cmova   r8d, edx; lMaximumCount
0x18000424a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000424c  call    cs:__imp_CreateSemaphoreExW
0x180004252  mov     r15, rax
0x180004255  test    rax, rax
0x180004258  jnz     short loc_180004288
0x18000425a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000425f  mov     edi, eax
0x180004261  test    eax, eax
0x180004263  jns     short loc_1800042BC
0x180004265  mov     rcx, [rsp+278h]; this
0x18000426d  lea     r8, aWil; "wil"
0x180004274  mov     r9d, eax; char *
0x180004277  mov     edx, 8Bh; void *
0x18000427c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004281  mov     eax, edi
0x180004283  jmp     loc_18000435A
0x180004288  call    cs:__imp_GetLastError
0x18000428e  mov     rdi, [rbx]
0x180004291  test    rdi, rdi
0x180004294  jz      short loc_1800042B9
0x180004296  call    cs:__imp_GetLastError
0x18000429c  mov     rcx, rdi; hObject
0x18000429f  mov     r14d, eax
0x1800042a2  call    cs:__imp_CloseHandle
0x1800042a8  test    eax, eax
0x1800042aa  jz      loc_18000439F
0x1800042b0  mov     ecx, r14d; dwErrCode
0x1800042b3  call    cs:__imp_SetLastError
0x1800042b9  mov     [rbx], r15
0x1800042bc  lea     r8, asc_1800106A0; "h"
0x1800042c3  shr     rbp, 1Fh
0x1800042c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800042cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800042d1  test    ebp, ebp
0x1800042d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800042db  lea     r9, [rsp+278h+Name]; lpName
0x1800042e0  mov     [rsp+278h+dwFlags], r12d; int
0x1800042e5  cmovnz  esi, ebp
0x1800042e8  mov     edx, ebp; lInitialCount
0x1800042ea  mov     r8d, esi; lMaximumCount
0x1800042ed  xor     ecx, ecx; lpSemaphoreAttributes
0x1800042ef  call    cs:__imp_CreateSemaphoreExW
0x1800042f5  mov     rsi, rax
0x1800042f8  test    rax, rax
0x1800042fb  jnz     short loc_180004328
0x1800042fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004302  mov     ebx, eax
0x180004304  test    eax, eax
0x180004306  jns     short loc_180004358
0x180004308  mov     rcx, [rsp+278h]; this
0x180004310  lea     r8, aWil; "wil"
0x180004317  mov     r9d, eax; char *
0x18000431a  mov     edx, 90h; void *
0x18000431f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004324  mov     eax, ebx
0x180004326  jmp     short loc_18000435A
0x180004328  call    cs:__imp_GetLastError
0x18000432e  mov     rdi, [rbx+8]
0x180004332  test    rdi, rdi
0x180004335  jz      short loc_180004354
0x180004337  call    cs:__imp_GetLastError
0x18000433d  mov     rcx, rdi; hObject
0x180004340  mov     ebp, eax
0x180004342  call    cs:__imp_CloseHandle
0x180004348  test    eax, eax
0x18000434a  jz      short loc_180004386
0x18000434c  mov     ecx, ebp; dwErrCode
0x18000434e  call    cs:__imp_SetLastError
0x180004354  mov     [rbx+8], rsi
0x180004358  xor     eax, eax
0x18000435a  mov     rcx, [rsp+278h+var_38]
0x180004362  xor     rcx, rsp; StackCookie
0x180004365  call    __security_check_cookie
0x18000436a  lea     r11, [rsp+278h+var_28]
0x180004372  mov     rbx, [r11+38h]
0x180004376  mov     rbp, [r11+40h]
0x18000437a  mov     rsp, r11
0x18000437d  pop     r15
0x18000437f  pop     r14
0x180004381  pop     r12
0x180004383  pop     rdi
0x180004384  pop     rsi
0x180004385  retn
0x180004386  mov     rcx, [rsp+278h]; this
0x18000438e  mov     edx, 0A0Bh; void *
0x180004393  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004399  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000439f  mov     rcx, [rsp+278h]; this
0x1800043a7  mov     edx, 0A0Bh; void *
0x1800043ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400041a0`
- end: `0x1400043ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400039d8`
- `0x140003da8`

## callees

- `0x140001570`
- `0x1400041a0`
- `0x140004f38`
- `0x140006ce4`
- `0x140007728`
- `0x1400083ac`
- `0x1400083bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004307`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000434f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000434f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004366`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000435a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000435a`

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
0x1400041a0  mov     [rsp+arg_8], rbx
0x1400041a5  mov     [rsp+arg_10], rbp
0x1400041aa  push    rsi
0x1400041ab  push    rdi
0x1400041ac  push    r12
0x1400041ae  push    r14
0x1400041b0  push    r15
0x1400041b2  sub     rsp, 250h
0x1400041b9  mov     rax, cs:__security_cookie
0x1400041c0  xor     rax, rsp
0x1400041c3  mov     [rsp+278h+var_38], rax
0x1400041cb  mov     rax, 0C000000000000000h
0x1400041d5  mov     rbp, r9
0x1400041d8  mov     r8, rdx
0x1400041db  mov     rbx, rcx
0x1400041de  test    rax, r9
0x1400041e1  jnz     loc_1400043B1
0x1400041e7  xor     r12d, r12d
0x1400041ea  lea     rax, [rsp+278h+Name]
0x1400041ef  mov     ecx, 7FFFFFFEh
0x1400041f4  mov     edx, 104h
0x1400041f9  lea     esi, [r12+1]
0x1400041fe  test    rcx, rcx
0x140004201  jz      short loc_140004221
0x140004203  movzx   r9d, word ptr [r8]
0x140004207  test    r9w, r9w
0x14000420b  jz      short loc_140004221
0x14000420d  mov     [rax], r9w
0x140004211  add     r8, 2
0x140004215  add     rax, 2
0x140004219  sub     rcx, rsi
0x14000421c  sub     rdx, rsi; unsigned __int64
0x14000421f  jnz     short loc_1400041FE
0x140004221  test    rdx, rdx
0x140004224  lea     rcx, [rax-2]
0x140004228  lea     r8, aP0; "_p0"
0x14000422f  cmovnz  rcx, rax
0x140004233  mov     [rcx], r12w
0x140004237  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000423c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004241  mov     edx, ebp
0x140004243  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000424b  and     edx, 7FFFFFFFh; lInitialCount
0x140004251  mov     [rsp+278h+dwFlags], r12d; int
0x140004256  mov     r8d, esi
0x140004259  lea     r9, [rsp+278h+Name]; lpName
0x14000425e  cmova   r8d, edx; lMaximumCount
0x140004262  xor     ecx, ecx; lpSemaphoreAttributes
0x140004264  call    cs:__imp_CreateSemaphoreExW
0x14000426a  mov     r15, rax
0x14000426d  test    rax, rax
0x140004270  jnz     short loc_1400042A0
0x140004272  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004277  mov     edi, eax
0x140004279  test    eax, eax
0x14000427b  jns     short loc_1400042D4
0x14000427d  mov     rcx, [rsp+278h]; this
0x140004285  lea     r8, aWil; "wil"
0x14000428c  mov     r9d, eax; char *
0x14000428f  mov     edx, 8Bh; void *
0x140004294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004299  mov     eax, edi
0x14000429b  jmp     loc_140004372
0x1400042a0  call    cs:__imp_GetLastError
0x1400042a6  mov     rdi, [rbx]
0x1400042a9  test    rdi, rdi
0x1400042ac  jz      short loc_1400042D1
0x1400042ae  call    cs:__imp_GetLastError
0x1400042b4  mov     rcx, rdi; hObject
0x1400042b7  mov     r14d, eax
0x1400042ba  call    cs:__imp_CloseHandle
0x1400042c0  test    eax, eax
0x1400042c2  jz      loc_1400043B7
0x1400042c8  mov     ecx, r14d; dwErrCode
0x1400042cb  call    cs:__imp_SetLastError
0x1400042d1  mov     [rbx], r15
0x1400042d4  lea     r8, asc_140021490; "h"
0x1400042db  shr     rbp, 1Fh
0x1400042df  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400042e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400042e9  test    ebp, ebp
0x1400042eb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400042f3  lea     r9, [rsp+278h+Name]; lpName
0x1400042f8  mov     [rsp+278h+dwFlags], r12d; int
0x1400042fd  cmovnz  esi, ebp
0x140004300  mov     edx, ebp; lInitialCount
0x140004302  mov     r8d, esi; lMaximumCount
0x140004305  xor     ecx, ecx; lpSemaphoreAttributes
0x140004307  call    cs:__imp_CreateSemaphoreExW
0x14000430d  mov     rsi, rax
0x140004310  test    rax, rax
0x140004313  jnz     short loc_140004340
0x140004315  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000431a  mov     ebx, eax
0x14000431c  test    eax, eax
0x14000431e  jns     short loc_140004370
0x140004320  mov     rcx, [rsp+278h]; this
0x140004328  lea     r8, aWil; "wil"
0x14000432f  mov     r9d, eax; char *
0x140004332  mov     edx, 90h; void *
0x140004337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000433c  mov     eax, ebx
0x14000433e  jmp     short loc_140004372
0x140004340  call    cs:__imp_GetLastError
0x140004346  mov     rdi, [rbx+8]
0x14000434a  test    rdi, rdi
0x14000434d  jz      short loc_14000436C
0x14000434f  call    cs:__imp_GetLastError
0x140004355  mov     rcx, rdi; hObject
0x140004358  mov     ebp, eax
0x14000435a  call    cs:__imp_CloseHandle
0x140004360  test    eax, eax
0x140004362  jz      short loc_14000439E
0x140004364  mov     ecx, ebp; dwErrCode
0x140004366  call    cs:__imp_SetLastError
0x14000436c  mov     [rbx+8], rsi
0x140004370  xor     eax, eax
0x140004372  mov     rcx, [rsp+278h+var_38]
0x14000437a  xor     rcx, rsp; StackCookie
0x14000437d  call    __security_check_cookie
0x140004382  lea     r11, [rsp+278h+var_28]
0x14000438a  mov     rbx, [r11+38h]
0x14000438e  mov     rbp, [r11+40h]
0x140004392  mov     rsp, r11
0x140004395  pop     r15
0x140004397  pop     r14
0x140004399  pop     r12
0x14000439b  pop     rdi
0x14000439c  pop     rsi
0x14000439d  retn
0x14000439e  mov     rcx, [rsp+278h]; this
0x1400043a6  mov     edx, 0A0Bh; void *
0x1400043ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400043b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400043b7  mov     rcx, [rsp+278h]; this
0x1400043bf  mov     edx, 0A0Bh; void *
0x1400043c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

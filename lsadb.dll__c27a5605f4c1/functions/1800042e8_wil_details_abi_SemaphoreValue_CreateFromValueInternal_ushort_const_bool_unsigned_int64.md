# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800042e8`
- end: `0x1800044f5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b74`
- `0x180003f18`

## callees

- `0x180001670`
- `0x1800042e8`
- `0x180005138`
- `0x180007ac4`
- `0x180007edc`
- `0x180008c7c`
- `0x180008c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000440c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004491`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000440c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000446b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000446b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004448`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004485`

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
0x1800042e8  mov     [rsp+arg_8], rbx
0x1800042ed  mov     [rsp+arg_10], rbp
0x1800042f2  push    rsi
0x1800042f3  push    rdi
0x1800042f4  push    r12
0x1800042f6  push    r14
0x1800042f8  push    r15
0x1800042fa  sub     rsp, 250h
0x180004301  mov     rax, cs:__security_cookie
0x180004308  xor     rax, rsp
0x18000430b  mov     [rsp+278h+var_38], rax
0x180004313  mov     rax, 0C000000000000000h
0x18000431d  mov     rbp, r9
0x180004320  mov     r8, rdx
0x180004323  mov     rdi, rcx
0x180004326  test    rax, r9
0x180004329  jnz     loc_1800044DC
0x18000432f  xor     r12d, r12d
0x180004332  lea     rax, [rsp+278h+Name]
0x180004337  mov     ecx, 7FFFFFFEh
0x18000433c  mov     edx, 104h
0x180004341  lea     esi, [r12+1]
0x180004346  test    rcx, rcx
0x180004349  jz      short loc_180004369
0x18000434b  movzx   r9d, word ptr [r8]
0x18000434f  test    r9w, r9w
0x180004353  jz      short loc_180004369
0x180004355  mov     [rax], r9w
0x180004359  add     r8, 2
0x18000435d  add     rax, 2
0x180004361  sub     rcx, rsi
0x180004364  sub     rdx, rsi; unsigned __int64
0x180004367  jnz     short loc_180004346
0x180004369  test    rdx, rdx
0x18000436c  lea     rcx, [rax-2]
0x180004370  lea     r8, aP0; "_p0"
0x180004377  cmovnz  rcx, rax
0x18000437b  mov     [rcx], r12w
0x18000437f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004384  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004389  mov     edx, ebp
0x18000438b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004393  and     edx, 7FFFFFFFh; lInitialCount
0x180004399  mov     [rsp+278h+dwFlags], r12d; int
0x18000439e  mov     r8d, esi
0x1800043a1  lea     r9, [rsp+278h+Name]; lpName
0x1800043a6  cmova   r8d, edx; lMaximumCount
0x1800043aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800043ac  call    cs:__imp_CreateSemaphoreExW
0x1800043b2  mov     r15, rax
0x1800043b5  test    rax, rax
0x1800043b8  jnz     short loc_1800043E1
0x1800043ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800043bf  mov     ebx, eax
0x1800043c1  test    eax, eax
0x1800043c3  jns     short loc_180004415
0x1800043c5  mov     edx, 8Bh; void *
0x1800043ca  mov     rcx, [rsp+278h]; this
0x1800043d2  mov     r9d, ebx; char *
0x1800043d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043da  mov     eax, ebx
0x1800043dc  jmp     loc_18000449D
0x1800043e1  call    cs:__imp_GetLastError
0x1800043e7  mov     rbx, [rdi]
0x1800043ea  test    rbx, rbx
0x1800043ed  jz      short loc_180004412
0x1800043ef  call    cs:__imp_GetLastError
0x1800043f5  mov     rcx, rbx; hObject
0x1800043f8  mov     r14d, eax
0x1800043fb  call    cs:__imp_CloseHandle
0x180004401  test    eax, eax
0x180004403  jz      loc_1800044E2
0x180004409  mov     ecx, r14d; dwErrCode
0x18000440c  call    cs:__imp_SetLastError
0x180004412  mov     [rdi], r15
0x180004415  lea     r8, asc_18003DBA0; "h"
0x18000441c  shr     rbp, 1Fh
0x180004420  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004425  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000442a  test    ebp, ebp
0x18000442c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004434  lea     r9, [rsp+278h+Name]; lpName
0x180004439  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000443e  cmovnz  esi, ebp
0x180004441  mov     edx, ebp; lInitialCount
0x180004443  mov     r8d, esi; lMaximumCount
0x180004446  xor     ecx, ecx; lpSemaphoreAttributes
0x180004448  call    cs:__imp_CreateSemaphoreExW
0x18000444e  mov     rsi, rax
0x180004451  test    rax, rax
0x180004454  jnz     short loc_18000446B
0x180004456  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000445b  mov     ebx, eax
0x18000445d  test    eax, eax
0x18000445f  jns     short loc_18000449B
0x180004461  mov     edx, 90h
0x180004466  jmp     loc_1800043CA
0x18000446b  call    cs:__imp_GetLastError
0x180004471  mov     rbx, [rdi+8]
0x180004475  test    rbx, rbx
0x180004478  jz      short loc_180004497
0x18000447a  call    cs:__imp_GetLastError
0x180004480  mov     rcx, rbx; hObject
0x180004483  mov     ebp, eax
0x180004485  call    cs:__imp_CloseHandle
0x18000448b  test    eax, eax
0x18000448d  jz      short loc_1800044C9
0x18000448f  mov     ecx, ebp; dwErrCode
0x180004491  call    cs:__imp_SetLastError
0x180004497  mov     [rdi+8], rsi
0x18000449b  xor     eax, eax
0x18000449d  mov     rcx, [rsp+278h+var_38]
0x1800044a5  xor     rcx, rsp; StackCookie
0x1800044a8  call    __security_check_cookie
0x1800044ad  lea     r11, [rsp+278h+var_28]
0x1800044b5  mov     rbx, [r11+38h]
0x1800044b9  mov     rbp, [r11+40h]
0x1800044bd  mov     rsp, r11
0x1800044c0  pop     r15
0x1800044c2  pop     r14
0x1800044c4  pop     r12
0x1800044c6  pop     rdi
0x1800044c7  pop     rsi
0x1800044c8  retn
0x1800044c9  mov     rcx, [rsp+278h]; this
0x1800044d1  mov     edx, 0A0Bh; void *
0x1800044d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800044e2  mov     rcx, [rsp+278h]; this
0x1800044ea  mov     edx, 0A0Bh; void *
0x1800044ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

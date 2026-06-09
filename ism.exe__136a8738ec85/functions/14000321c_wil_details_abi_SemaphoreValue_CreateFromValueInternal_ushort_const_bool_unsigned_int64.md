# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000321c`
- end: `0x140003437`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `539`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002e78`

## callees

- `0x140001460`
- `0x14000321c`
- `0x140003aa8`
- `0x140004914`
- `0x140005254`
- `0x14000579c`
- `0x1400057ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003340`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003340`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000339f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000339f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000332f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400033b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000332f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400033b9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400032e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000337c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400032e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000337c`

## string_xrefs

- `0x140003405`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140003425`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  void *v26; // rbx
  DWORD v27; // ebp
  const char *v28; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v22);
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
  v23 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v26 = (void *)*((_QWORD *)this + 1);
    if ( v26 )
    {
      v27 = GetLastError();
      if ( !CloseHandle(v26) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      SetLastError(v27);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v24);
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
0x14000321c  mov     [rsp+arg_8], rbx
0x140003221  mov     [rsp+arg_10], rbp
0x140003226  push    rsi
0x140003227  push    rdi
0x140003228  push    r12
0x14000322a  push    r14
0x14000322c  push    r15
0x14000322e  sub     rsp, 250h
0x140003235  mov     rax, cs:__security_cookie
0x14000323c  xor     rax, rsp
0x14000323f  mov     [rsp+278h+var_38], rax
0x140003247  mov     rax, 0C000000000000000h
0x140003251  mov     rbp, r9
0x140003254  mov     r8, rdx
0x140003257  mov     rdi, rcx
0x14000325a  test    rax, r9
0x14000325d  jnz     loc_140003417
0x140003263  xor     r12d, r12d
0x140003266  lea     rax, [rsp+278h+Name]
0x14000326b  mov     ecx, 7FFFFFFEh
0x140003270  mov     edx, 104h
0x140003275  lea     esi, [r12+1]
0x14000327a  test    rcx, rcx
0x14000327d  jz      short loc_14000329D
0x14000327f  movzx   r9d, word ptr [r8]
0x140003283  test    r9w, r9w
0x140003287  jz      short loc_14000329D
0x140003289  mov     [rax], r9w
0x14000328d  add     r8, 2
0x140003291  add     rax, 2
0x140003295  sub     rcx, rsi
0x140003298  sub     rdx, rsi; unsigned __int64
0x14000329b  jnz     short loc_14000327A
0x14000329d  test    rdx, rdx
0x1400032a0  lea     rcx, [rax-2]
0x1400032a4  lea     r8, aP0; "_p0"
0x1400032ab  cmovnz  rcx, rax
0x1400032af  mov     [rcx], r12w
0x1400032b3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400032b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400032bd  mov     edx, ebp
0x1400032bf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400032c7  and     edx, 7FFFFFFFh; lInitialCount
0x1400032cd  mov     [rsp+278h+dwFlags], r12d; int
0x1400032d2  mov     r8d, esi
0x1400032d5  lea     r9, [rsp+278h+Name]; lpName
0x1400032da  cmova   r8d, edx; lMaximumCount
0x1400032de  xor     ecx, ecx; lpSemaphoreAttributes
0x1400032e0  call    cs:__imp_CreateSemaphoreExW
0x1400032e6  mov     r15, rax
0x1400032e9  test    rax, rax
0x1400032ec  jnz     short loc_140003315
0x1400032ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400032f3  mov     ebx, eax
0x1400032f5  test    eax, eax
0x1400032f7  jns     short loc_140003349
0x1400032f9  mov     edx, 8Bh; void *
0x1400032fe  mov     rcx, [rsp+278h]; this
0x140003306  mov     r9d, ebx; char *
0x140003309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000330e  mov     eax, ebx
0x140003310  jmp     loc_1400033D1
0x140003315  call    cs:__imp_GetLastError
0x14000331b  mov     rbx, [rdi]
0x14000331e  test    rbx, rbx
0x140003321  jz      short loc_140003346
0x140003323  call    cs:__imp_GetLastError
0x140003329  mov     rcx, rbx; hObject
0x14000332c  mov     r14d, eax
0x14000332f  call    cs:__imp_CloseHandle
0x140003335  test    eax, eax
0x140003337  jz      loc_14000341D
0x14000333d  mov     ecx, r14d; dwErrCode
0x140003340  call    cs:__imp_SetLastError
0x140003346  mov     [rdi], r15
0x140003349  lea     r8, asc_1400077F8; "h"
0x140003350  shr     rbp, 1Fh
0x140003354  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003359  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000335e  test    ebp, ebp
0x140003360  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003368  lea     r9, [rsp+278h+Name]; lpName
0x14000336d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003372  cmovnz  esi, ebp
0x140003375  mov     edx, ebp; lInitialCount
0x140003377  mov     r8d, esi; lMaximumCount
0x14000337a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000337c  call    cs:__imp_CreateSemaphoreExW
0x140003382  mov     rsi, rax
0x140003385  test    rax, rax
0x140003388  jnz     short loc_14000339F
0x14000338a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000338f  mov     ebx, eax
0x140003391  test    eax, eax
0x140003393  jns     short loc_1400033CF
0x140003395  mov     edx, 90h
0x14000339a  jmp     loc_1400032FE
0x14000339f  call    cs:__imp_GetLastError
0x1400033a5  mov     rbx, [rdi+8]
0x1400033a9  test    rbx, rbx
0x1400033ac  jz      short loc_1400033CB
0x1400033ae  call    cs:__imp_GetLastError
0x1400033b4  mov     rcx, rbx; hObject
0x1400033b7  mov     ebp, eax
0x1400033b9  call    cs:__imp_CloseHandle
0x1400033bf  test    eax, eax
0x1400033c1  jz      short loc_1400033FD
0x1400033c3  mov     ecx, ebp; dwErrCode
0x1400033c5  call    cs:__imp_SetLastError
0x1400033cb  mov     [rdi+8], rsi
0x1400033cf  xor     eax, eax
0x1400033d1  mov     rcx, [rsp+278h+var_38]
0x1400033d9  xor     rcx, rsp; StackCookie
0x1400033dc  call    __security_check_cookie
0x1400033e1  lea     r11, [rsp+278h+var_28]
0x1400033e9  mov     rbx, [r11+38h]
0x1400033ed  mov     rbp, [r11+40h]
0x1400033f1  mov     rsp, r11
0x1400033f4  pop     r15
0x1400033f6  pop     r14
0x1400033f8  pop     r12
0x1400033fa  pop     rdi
0x1400033fb  pop     rsi
0x1400033fc  retn
0x1400033fd  mov     rcx, [rsp+278h]; this
0x140003405  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000340c  mov     edx, 0A0Bh; void *
0x140003411  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003417  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000341d  mov     rcx, [rsp+278h]; this
0x140003425  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000342c  mov     edx, 0A0Bh; void *
0x140003431  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

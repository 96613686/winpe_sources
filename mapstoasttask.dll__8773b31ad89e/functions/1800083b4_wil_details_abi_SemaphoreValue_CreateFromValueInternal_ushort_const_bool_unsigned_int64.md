# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800083b4`
- end: `0x1800085c1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008010`

## callees

- `0x1800015b0`
- `0x180007a6c`
- `0x1800083b4`
- `0x180008878`
- `0x180008e58`
- `0x18000909c`
- `0x1800093c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000855d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000855d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008546`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008478`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008514`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008478`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008551`

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
0x1800083b4  mov     [rsp+arg_8], rbx
0x1800083b9  mov     [rsp+arg_10], rbp
0x1800083be  push    rsi
0x1800083bf  push    rdi
0x1800083c0  push    r12
0x1800083c2  push    r14
0x1800083c4  push    r15
0x1800083c6  sub     rsp, 250h
0x1800083cd  mov     rax, cs:__security_cookie
0x1800083d4  xor     rax, rsp
0x1800083d7  mov     [rsp+278h+var_38], rax
0x1800083df  mov     rax, 0C000000000000000h
0x1800083e9  mov     rbp, r9
0x1800083ec  mov     r8, rdx
0x1800083ef  mov     rdi, rcx
0x1800083f2  test    rax, r9
0x1800083f5  jnz     loc_1800085A8
0x1800083fb  xor     r12d, r12d
0x1800083fe  lea     rax, [rsp+278h+Name]
0x180008403  mov     ecx, 7FFFFFFEh
0x180008408  mov     edx, 104h
0x18000840d  lea     esi, [r12+1]
0x180008412  test    rcx, rcx
0x180008415  jz      short loc_180008435
0x180008417  movzx   r9d, word ptr [r8]
0x18000841b  test    r9w, r9w
0x18000841f  jz      short loc_180008435
0x180008421  mov     [rax], r9w
0x180008425  add     r8, 2
0x180008429  add     rax, 2
0x18000842d  sub     rcx, rsi
0x180008430  sub     rdx, rsi; unsigned __int64
0x180008433  jnz     short loc_180008412
0x180008435  test    rdx, rdx
0x180008438  lea     rcx, [rax-2]
0x18000843c  lea     r8, aP0; "_p0"
0x180008443  cmovnz  rcx, rax
0x180008447  mov     [rcx], r12w
0x18000844b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180008450  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008455  mov     edx, ebp
0x180008457  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000845f  and     edx, 7FFFFFFFh; lInitialCount
0x180008465  mov     [rsp+278h+dwFlags], r12d; int
0x18000846a  mov     r8d, esi
0x18000846d  lea     r9, [rsp+278h+Name]; lpName
0x180008472  cmova   r8d, edx; lMaximumCount
0x180008476  xor     ecx, ecx; lpSemaphoreAttributes
0x180008478  call    cs:__imp_CreateSemaphoreExW
0x18000847e  mov     r15, rax
0x180008481  test    rax, rax
0x180008484  jnz     short loc_1800084AD
0x180008486  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000848b  mov     ebx, eax
0x18000848d  test    eax, eax
0x18000848f  jns     short loc_1800084E1
0x180008491  mov     edx, 8Bh; void *
0x180008496  mov     rcx, [rsp+278h]; this
0x18000849e  mov     r9d, ebx; char *
0x1800084a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084a6  mov     eax, ebx
0x1800084a8  jmp     loc_180008569
0x1800084ad  call    cs:__imp_GetLastError
0x1800084b3  mov     rbx, [rdi]
0x1800084b6  test    rbx, rbx
0x1800084b9  jz      short loc_1800084DE
0x1800084bb  call    cs:__imp_GetLastError
0x1800084c1  mov     rcx, rbx; hObject
0x1800084c4  mov     r14d, eax
0x1800084c7  call    cs:__imp_CloseHandle
0x1800084cd  test    eax, eax
0x1800084cf  jz      loc_1800085AE
0x1800084d5  mov     ecx, r14d; dwErrCode
0x1800084d8  call    cs:__imp_SetLastError
0x1800084de  mov     [rdi], r15
0x1800084e1  lea     r8, asc_18000C4B0; "h"
0x1800084e8  shr     rbp, 1Fh
0x1800084ec  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800084f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800084f6  test    ebp, ebp
0x1800084f8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008500  lea     r9, [rsp+278h+Name]; lpName
0x180008505  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000850a  cmovnz  esi, ebp
0x18000850d  mov     edx, ebp; lInitialCount
0x18000850f  mov     r8d, esi; lMaximumCount
0x180008512  xor     ecx, ecx; lpSemaphoreAttributes
0x180008514  call    cs:__imp_CreateSemaphoreExW
0x18000851a  mov     rsi, rax
0x18000851d  test    rax, rax
0x180008520  jnz     short loc_180008537
0x180008522  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008527  mov     ebx, eax
0x180008529  test    eax, eax
0x18000852b  jns     short loc_180008567
0x18000852d  mov     edx, 90h
0x180008532  jmp     loc_180008496
0x180008537  call    cs:__imp_GetLastError
0x18000853d  mov     rbx, [rdi+8]
0x180008541  test    rbx, rbx
0x180008544  jz      short loc_180008563
0x180008546  call    cs:__imp_GetLastError
0x18000854c  mov     rcx, rbx; hObject
0x18000854f  mov     ebp, eax
0x180008551  call    cs:__imp_CloseHandle
0x180008557  test    eax, eax
0x180008559  jz      short loc_180008595
0x18000855b  mov     ecx, ebp; dwErrCode
0x18000855d  call    cs:__imp_SetLastError
0x180008563  mov     [rdi+8], rsi
0x180008567  xor     eax, eax
0x180008569  mov     rcx, [rsp+278h+var_38]
0x180008571  xor     rcx, rsp; StackCookie
0x180008574  call    __security_check_cookie
0x180008579  lea     r11, [rsp+278h+var_28]
0x180008581  mov     rbx, [r11+38h]
0x180008585  mov     rbp, [r11+40h]
0x180008589  mov     rsp, r11
0x18000858c  pop     r15
0x18000858e  pop     r14
0x180008590  pop     r12
0x180008592  pop     rdi
0x180008593  pop     rsi
0x180008594  retn
0x180008595  mov     rcx, [rsp+278h]; this
0x18000859d  mov     edx, 0A0Bh; void *
0x1800085a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800085ae  mov     rcx, [rsp+278h]; this
0x1800085b6  mov     edx, 0A0Bh; void *
0x1800085bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

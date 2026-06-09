# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003964`
- end: `0x180003b8e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003518`

## callees

- `0x180001510`
- `0x180003964`
- `0x180004638`
- `0x1800068d4`
- `0x1800072c0`
- `0x1800078b4`
- `0x1800078c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a28`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003acb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a28`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003acb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b1e`

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
0x180003964  mov     [rsp+arg_8], rbx
0x180003969  mov     [rsp+arg_10], rbp
0x18000396e  push    rsi
0x18000396f  push    rdi
0x180003970  push    r12
0x180003972  push    r14
0x180003974  push    r15
0x180003976  sub     rsp, 250h
0x18000397d  mov     rax, cs:__security_cookie
0x180003984  xor     rax, rsp
0x180003987  mov     [rsp+278h+var_38], rax
0x18000398f  mov     rax, 0C000000000000000h
0x180003999  mov     rbp, r9
0x18000399c  mov     r8, rdx
0x18000399f  mov     rbx, rcx
0x1800039a2  test    rax, r9
0x1800039a5  jnz     loc_180003B75
0x1800039ab  xor     r12d, r12d
0x1800039ae  lea     rax, [rsp+278h+Name]
0x1800039b3  mov     ecx, 7FFFFFFEh
0x1800039b8  mov     edx, 104h
0x1800039bd  lea     esi, [r12+1]
0x1800039c2  test    rcx, rcx
0x1800039c5  jz      short loc_1800039E5
0x1800039c7  movzx   r9d, word ptr [r8]
0x1800039cb  test    r9w, r9w
0x1800039cf  jz      short loc_1800039E5
0x1800039d1  mov     [rax], r9w
0x1800039d5  add     r8, 2
0x1800039d9  add     rax, 2
0x1800039dd  sub     rcx, rsi
0x1800039e0  sub     rdx, rsi; unsigned __int64
0x1800039e3  jnz     short loc_1800039C2
0x1800039e5  test    rdx, rdx
0x1800039e8  lea     rcx, [rax-2]
0x1800039ec  lea     r8, aP0; "_p0"
0x1800039f3  cmovnz  rcx, rax
0x1800039f7  mov     [rcx], r12w
0x1800039fb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003a00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003a05  mov     edx, ebp
0x180003a07  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003a0f  and     edx, 7FFFFFFFh; lInitialCount
0x180003a15  mov     [rsp+278h+dwFlags], r12d; int
0x180003a1a  mov     r8d, esi
0x180003a1d  lea     r9, [rsp+278h+Name]; lpName
0x180003a22  cmova   r8d, edx; lMaximumCount
0x180003a26  xor     ecx, ecx; lpSemaphoreAttributes
0x180003a28  call    cs:__imp_CreateSemaphoreExW
0x180003a2e  mov     r15, rax
0x180003a31  test    rax, rax
0x180003a34  jnz     short loc_180003A64
0x180003a36  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a3b  mov     edi, eax
0x180003a3d  test    eax, eax
0x180003a3f  jns     short loc_180003A98
0x180003a41  mov     rcx, [rsp+278h]; this
0x180003a49  lea     r8, aWil; "wil"
0x180003a50  mov     r9d, eax; char *
0x180003a53  mov     edx, 8Bh; void *
0x180003a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a5d  mov     eax, edi
0x180003a5f  jmp     loc_180003B36
0x180003a64  call    cs:__imp_GetLastError
0x180003a6a  mov     rdi, [rbx]
0x180003a6d  test    rdi, rdi
0x180003a70  jz      short loc_180003A95
0x180003a72  call    cs:__imp_GetLastError
0x180003a78  mov     rcx, rdi; hObject
0x180003a7b  mov     r14d, eax
0x180003a7e  call    cs:__imp_CloseHandle
0x180003a84  test    eax, eax
0x180003a86  jz      loc_180003B7B
0x180003a8c  mov     ecx, r14d; dwErrCode
0x180003a8f  call    cs:__imp_SetLastError
0x180003a95  mov     [rbx], r15
0x180003a98  lea     r8, asc_18000ABA8; "h"
0x180003a9f  shr     rbp, 1Fh
0x180003aa3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003aa8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003aad  test    ebp, ebp
0x180003aaf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003ab7  lea     r9, [rsp+278h+Name]; lpName
0x180003abc  mov     [rsp+278h+dwFlags], r12d; int
0x180003ac1  cmovnz  esi, ebp
0x180003ac4  mov     edx, ebp; lInitialCount
0x180003ac6  mov     r8d, esi; lMaximumCount
0x180003ac9  xor     ecx, ecx; lpSemaphoreAttributes
0x180003acb  call    cs:__imp_CreateSemaphoreExW
0x180003ad1  mov     rsi, rax
0x180003ad4  test    rax, rax
0x180003ad7  jnz     short loc_180003B04
0x180003ad9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ade  mov     ebx, eax
0x180003ae0  test    eax, eax
0x180003ae2  jns     short loc_180003B34
0x180003ae4  mov     rcx, [rsp+278h]; this
0x180003aec  lea     r8, aWil; "wil"
0x180003af3  mov     r9d, eax; char *
0x180003af6  mov     edx, 90h; void *
0x180003afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b00  mov     eax, ebx
0x180003b02  jmp     short loc_180003B36
0x180003b04  call    cs:__imp_GetLastError
0x180003b0a  mov     rdi, [rbx+8]
0x180003b0e  test    rdi, rdi
0x180003b11  jz      short loc_180003B30
0x180003b13  call    cs:__imp_GetLastError
0x180003b19  mov     rcx, rdi; hObject
0x180003b1c  mov     ebp, eax
0x180003b1e  call    cs:__imp_CloseHandle
0x180003b24  test    eax, eax
0x180003b26  jz      short loc_180003B62
0x180003b28  mov     ecx, ebp; dwErrCode
0x180003b2a  call    cs:__imp_SetLastError
0x180003b30  mov     [rbx+8], rsi
0x180003b34  xor     eax, eax
0x180003b36  mov     rcx, [rsp+278h+var_38]
0x180003b3e  xor     rcx, rsp; StackCookie
0x180003b41  call    __security_check_cookie
0x180003b46  lea     r11, [rsp+278h+var_28]
0x180003b4e  mov     rbx, [r11+38h]
0x180003b52  mov     rbp, [r11+40h]
0x180003b56  mov     rsp, r11
0x180003b59  pop     r15
0x180003b5b  pop     r14
0x180003b5d  pop     r12
0x180003b5f  pop     rdi
0x180003b60  pop     rsi
0x180003b61  retn
0x180003b62  mov     rcx, [rsp+278h]; this
0x180003b6a  mov     edx, 0A0Bh; void *
0x180003b6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b75  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b7b  mov     rcx, [rsp+278h]; this
0x180003b83  mov     edx, 0A0Bh; void *
0x180003b88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

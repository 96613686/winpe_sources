# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003bb4`
- end: `0x180003dc1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037d4`

## callees

- `0x180001be0`
- `0x180003bb4`
- `0x180004858`
- `0x180005cd4`
- `0x180006a90`
- `0x1800075d4`
- `0x1800075e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c78`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d14`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c78`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d51`

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
0x180003bb4  mov     [rsp+arg_8], rbx
0x180003bb9  mov     [rsp+arg_10], rbp
0x180003bbe  push    rsi
0x180003bbf  push    rdi
0x180003bc0  push    r12
0x180003bc2  push    r14
0x180003bc4  push    r15
0x180003bc6  sub     rsp, 250h
0x180003bcd  mov     rax, cs:__security_cookie
0x180003bd4  xor     rax, rsp
0x180003bd7  mov     [rsp+278h+var_38], rax
0x180003bdf  mov     rax, 0C000000000000000h
0x180003be9  mov     rbp, r9
0x180003bec  mov     r8, rdx
0x180003bef  mov     rdi, rcx
0x180003bf2  test    rax, r9
0x180003bf5  jnz     loc_180003DA8
0x180003bfb  xor     r12d, r12d
0x180003bfe  lea     rax, [rsp+278h+Name]
0x180003c03  mov     ecx, 7FFFFFFEh
0x180003c08  mov     edx, 104h
0x180003c0d  lea     esi, [r12+1]
0x180003c12  test    rcx, rcx
0x180003c15  jz      short loc_180003C35
0x180003c17  movzx   r9d, word ptr [r8]
0x180003c1b  test    r9w, r9w
0x180003c1f  jz      short loc_180003C35
0x180003c21  mov     [rax], r9w
0x180003c25  add     r8, 2
0x180003c29  add     rax, 2
0x180003c2d  sub     rcx, rsi
0x180003c30  sub     rdx, rsi; unsigned __int64
0x180003c33  jnz     short loc_180003C12
0x180003c35  test    rdx, rdx
0x180003c38  lea     rcx, [rax-2]
0x180003c3c  lea     r8, aP0; "_p0"
0x180003c43  cmovnz  rcx, rax
0x180003c47  mov     [rcx], r12w
0x180003c4b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003c50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c55  mov     edx, ebp
0x180003c57  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003c5f  and     edx, 7FFFFFFFh; lInitialCount
0x180003c65  mov     [rsp+278h+dwFlags], r12d; int
0x180003c6a  mov     r8d, esi
0x180003c6d  lea     r9, [rsp+278h+Name]; lpName
0x180003c72  cmova   r8d, edx; lMaximumCount
0x180003c76  xor     ecx, ecx; lpSemaphoreAttributes
0x180003c78  call    cs:__imp_CreateSemaphoreExW
0x180003c7e  mov     r15, rax
0x180003c81  test    rax, rax
0x180003c84  jnz     short loc_180003CAD
0x180003c86  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c8b  mov     ebx, eax
0x180003c8d  test    eax, eax
0x180003c8f  jns     short loc_180003CE1
0x180003c91  mov     edx, 8Bh; void *
0x180003c96  mov     rcx, [rsp+278h]; this
0x180003c9e  mov     r9d, ebx; char *
0x180003ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ca6  mov     eax, ebx
0x180003ca8  jmp     loc_180003D69
0x180003cad  call    cs:__imp_GetLastError
0x180003cb3  mov     rbx, [rdi]
0x180003cb6  test    rbx, rbx
0x180003cb9  jz      short loc_180003CDE
0x180003cbb  call    cs:__imp_GetLastError
0x180003cc1  mov     rcx, rbx; hObject
0x180003cc4  mov     r14d, eax
0x180003cc7  call    cs:__imp_CloseHandle
0x180003ccd  test    eax, eax
0x180003ccf  jz      loc_180003DAE
0x180003cd5  mov     ecx, r14d; dwErrCode
0x180003cd8  call    cs:__imp_SetLastError
0x180003cde  mov     [rdi], r15
0x180003ce1  lea     r8, asc_18000AB38; "h"
0x180003ce8  shr     rbp, 1Fh
0x180003cec  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003cf1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003cf6  test    ebp, ebp
0x180003cf8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003d00  lea     r9, [rsp+278h+Name]; lpName
0x180003d05  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003d0a  cmovnz  esi, ebp
0x180003d0d  mov     edx, ebp; lInitialCount
0x180003d0f  mov     r8d, esi; lMaximumCount
0x180003d12  xor     ecx, ecx; lpSemaphoreAttributes
0x180003d14  call    cs:__imp_CreateSemaphoreExW
0x180003d1a  mov     rsi, rax
0x180003d1d  test    rax, rax
0x180003d20  jnz     short loc_180003D37
0x180003d22  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003d27  mov     ebx, eax
0x180003d29  test    eax, eax
0x180003d2b  jns     short loc_180003D67
0x180003d2d  mov     edx, 90h
0x180003d32  jmp     loc_180003C96
0x180003d37  call    cs:__imp_GetLastError
0x180003d3d  mov     rbx, [rdi+8]
0x180003d41  test    rbx, rbx
0x180003d44  jz      short loc_180003D63
0x180003d46  call    cs:__imp_GetLastError
0x180003d4c  mov     rcx, rbx; hObject
0x180003d4f  mov     ebp, eax
0x180003d51  call    cs:__imp_CloseHandle
0x180003d57  test    eax, eax
0x180003d59  jz      short loc_180003D95
0x180003d5b  mov     ecx, ebp; dwErrCode
0x180003d5d  call    cs:__imp_SetLastError
0x180003d63  mov     [rdi+8], rsi
0x180003d67  xor     eax, eax
0x180003d69  mov     rcx, [rsp+278h+var_38]
0x180003d71  xor     rcx, rsp; StackCookie
0x180003d74  call    __security_check_cookie
0x180003d79  lea     r11, [rsp+278h+var_28]
0x180003d81  mov     rbx, [r11+38h]
0x180003d85  mov     rbp, [r11+40h]
0x180003d89  mov     rsp, r11
0x180003d8c  pop     r15
0x180003d8e  pop     r14
0x180003d90  pop     r12
0x180003d92  pop     rdi
0x180003d93  pop     rsi
0x180003d94  retn
0x180003d95  mov     rcx, [rsp+278h]; this
0x180003d9d  mov     edx, 0A0Bh; void *
0x180003da2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003dae  mov     rcx, [rsp+278h]; this
0x180003db6  mov     edx, 0A0Bh; void *
0x180003dbb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

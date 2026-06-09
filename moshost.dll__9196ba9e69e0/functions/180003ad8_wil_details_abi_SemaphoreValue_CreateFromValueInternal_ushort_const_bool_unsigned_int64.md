# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003ad8`
- end: `0x180003ce5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003734`

## callees

- `0x180001d00`
- `0x180003ad8`
- `0x180004358`
- `0x180005294`
- `0x180005b70`
- `0x18000608c`
- `0x18000609c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b9c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c38`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b9c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c75`

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
0x180003ad8  mov     [rsp+arg_8], rbx
0x180003add  mov     [rsp+arg_10], rbp
0x180003ae2  push    rsi
0x180003ae3  push    rdi
0x180003ae4  push    r12
0x180003ae6  push    r14
0x180003ae8  push    r15
0x180003aea  sub     rsp, 250h
0x180003af1  mov     rax, cs:__security_cookie
0x180003af8  xor     rax, rsp
0x180003afb  mov     [rsp+278h+var_38], rax
0x180003b03  mov     rax, 0C000000000000000h
0x180003b0d  mov     rbp, r9
0x180003b10  mov     r8, rdx
0x180003b13  mov     rdi, rcx
0x180003b16  test    rax, r9
0x180003b19  jnz     loc_180003CCC
0x180003b1f  xor     r12d, r12d
0x180003b22  lea     rax, [rsp+278h+Name]
0x180003b27  mov     ecx, 7FFFFFFEh
0x180003b2c  mov     edx, 104h
0x180003b31  lea     esi, [r12+1]
0x180003b36  test    rcx, rcx
0x180003b39  jz      short loc_180003B59
0x180003b3b  movzx   r9d, word ptr [r8]
0x180003b3f  test    r9w, r9w
0x180003b43  jz      short loc_180003B59
0x180003b45  mov     [rax], r9w
0x180003b49  add     r8, 2
0x180003b4d  add     rax, 2
0x180003b51  sub     rcx, rsi
0x180003b54  sub     rdx, rsi; unsigned __int64
0x180003b57  jnz     short loc_180003B36
0x180003b59  test    rdx, rdx
0x180003b5c  lea     rcx, [rax-2]
0x180003b60  lea     r8, aP0; "_p0"
0x180003b67  cmovnz  rcx, rax
0x180003b6b  mov     [rcx], r12w
0x180003b6f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003b74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b79  mov     edx, ebp
0x180003b7b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003b83  and     edx, 7FFFFFFFh; lInitialCount
0x180003b89  mov     [rsp+278h+dwFlags], r12d; int
0x180003b8e  mov     r8d, esi
0x180003b91  lea     r9, [rsp+278h+Name]; lpName
0x180003b96  cmova   r8d, edx; lMaximumCount
0x180003b9a  xor     ecx, ecx; lpSemaphoreAttributes
0x180003b9c  call    cs:__imp_CreateSemaphoreExW
0x180003ba2  mov     r15, rax
0x180003ba5  test    rax, rax
0x180003ba8  jnz     short loc_180003BD1
0x180003baa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003baf  mov     ebx, eax
0x180003bb1  test    eax, eax
0x180003bb3  jns     short loc_180003C05
0x180003bb5  mov     edx, 8Bh; void *
0x180003bba  mov     rcx, [rsp+278h]; this
0x180003bc2  mov     r9d, ebx; char *
0x180003bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bca  mov     eax, ebx
0x180003bcc  jmp     loc_180003C8D
0x180003bd1  call    cs:__imp_GetLastError
0x180003bd7  mov     rbx, [rdi]
0x180003bda  test    rbx, rbx
0x180003bdd  jz      short loc_180003C02
0x180003bdf  call    cs:__imp_GetLastError
0x180003be5  mov     rcx, rbx; hObject
0x180003be8  mov     r14d, eax
0x180003beb  call    cs:__imp_CloseHandle
0x180003bf1  test    eax, eax
0x180003bf3  jz      loc_180003CD2
0x180003bf9  mov     ecx, r14d; dwErrCode
0x180003bfc  call    cs:__imp_SetLastError
0x180003c02  mov     [rdi], r15
0x180003c05  lea     r8, asc_180011328; "h"
0x180003c0c  shr     rbp, 1Fh
0x180003c10  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003c15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c1a  test    ebp, ebp
0x180003c1c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003c24  lea     r9, [rsp+278h+Name]; lpName
0x180003c29  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003c2e  cmovnz  esi, ebp
0x180003c31  mov     edx, ebp; lInitialCount
0x180003c33  mov     r8d, esi; lMaximumCount
0x180003c36  xor     ecx, ecx; lpSemaphoreAttributes
0x180003c38  call    cs:__imp_CreateSemaphoreExW
0x180003c3e  mov     rsi, rax
0x180003c41  test    rax, rax
0x180003c44  jnz     short loc_180003C5B
0x180003c46  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c4b  mov     ebx, eax
0x180003c4d  test    eax, eax
0x180003c4f  jns     short loc_180003C8B
0x180003c51  mov     edx, 90h
0x180003c56  jmp     loc_180003BBA
0x180003c5b  call    cs:__imp_GetLastError
0x180003c61  mov     rbx, [rdi+8]
0x180003c65  test    rbx, rbx
0x180003c68  jz      short loc_180003C87
0x180003c6a  call    cs:__imp_GetLastError
0x180003c70  mov     rcx, rbx; hObject
0x180003c73  mov     ebp, eax
0x180003c75  call    cs:__imp_CloseHandle
0x180003c7b  test    eax, eax
0x180003c7d  jz      short loc_180003CB9
0x180003c7f  mov     ecx, ebp; dwErrCode
0x180003c81  call    cs:__imp_SetLastError
0x180003c87  mov     [rdi+8], rsi
0x180003c8b  xor     eax, eax
0x180003c8d  mov     rcx, [rsp+278h+var_38]
0x180003c95  xor     rcx, rsp; StackCookie
0x180003c98  call    __security_check_cookie
0x180003c9d  lea     r11, [rsp+278h+var_28]
0x180003ca5  mov     rbx, [r11+38h]
0x180003ca9  mov     rbp, [r11+40h]
0x180003cad  mov     rsp, r11
0x180003cb0  pop     r15
0x180003cb2  pop     r14
0x180003cb4  pop     r12
0x180003cb6  pop     rdi
0x180003cb7  pop     rsi
0x180003cb8  retn
0x180003cb9  mov     rcx, [rsp+278h]; this
0x180003cc1  mov     edx, 0A0Bh; void *
0x180003cc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ccc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003cd2  mov     rcx, [rsp+278h]; this
0x180003cda  mov     edx, 0A0Bh; void *
0x180003cdf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

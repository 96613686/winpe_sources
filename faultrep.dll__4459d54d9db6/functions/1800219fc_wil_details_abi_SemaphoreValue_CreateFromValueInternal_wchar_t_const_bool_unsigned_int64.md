# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800219fc`
- end: `0x180021c26`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180021234`
- `0x180021604`

## callees

- `0x180002890`
- `0x18000a9a4`
- `0x18000e30c`
- `0x18000e5f8`
- `0x1800219fc`
- `0x1800223d8`
- `0x180024774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021b27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021b27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bab`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180021ac0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180021b63`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180021ac0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180021b63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021bb6`

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
  __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
  StringCchCatW(Name, v9, (wchar_t *)L"_p0");
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
  StringCchCatW(Name, v16, (wchar_t *)L"h");
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
0x1800219fc  mov     [rsp+arg_8], rbx
0x180021a01  mov     [rsp+arg_10], rbp
0x180021a06  push    rsi
0x180021a07  push    rdi
0x180021a08  push    r12
0x180021a0a  push    r14
0x180021a0c  push    r15
0x180021a0e  sub     rsp, 250h
0x180021a15  mov     rax, cs:__security_cookie
0x180021a1c  xor     rax, rsp
0x180021a1f  mov     [rsp+278h+var_38], rax
0x180021a27  mov     rax, 0C000000000000000h
0x180021a31  mov     rbp, r9
0x180021a34  mov     r8, rdx
0x180021a37  mov     rbx, rcx
0x180021a3a  test    rax, r9
0x180021a3d  jnz     loc_180021C0D
0x180021a43  xor     r12d, r12d
0x180021a46  lea     rax, [rsp+278h+Name]
0x180021a4b  mov     ecx, 7FFFFFFEh
0x180021a50  mov     edx, 104h
0x180021a55  lea     esi, [r12+1]
0x180021a5a  test    rcx, rcx
0x180021a5d  jz      short loc_180021A7D
0x180021a5f  movzx   r9d, word ptr [r8]
0x180021a63  test    r9w, r9w
0x180021a67  jz      short loc_180021A7D
0x180021a69  mov     [rax], r9w
0x180021a6d  add     r8, 2
0x180021a71  add     rax, 2
0x180021a75  sub     rcx, rsi
0x180021a78  sub     rdx, rsi; unsigned __int64
0x180021a7b  jnz     short loc_180021A5A
0x180021a7d  test    rdx, rdx
0x180021a80  lea     rcx, [rax-2]
0x180021a84  lea     r8, aP0; "_p0"
0x180021a8b  cmovnz  rcx, rax
0x180021a8f  mov     [rcx], r12w
0x180021a93  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180021a98  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180021a9d  mov     edx, ebp
0x180021a9f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180021aa7  and     edx, 7FFFFFFFh; lInitialCount
0x180021aad  mov     [rsp+278h+dwFlags], r12d; int
0x180021ab2  mov     r8d, esi
0x180021ab5  lea     r9, [rsp+278h+Name]; lpName
0x180021aba  cmova   r8d, edx; lMaximumCount
0x180021abe  xor     ecx, ecx; lpSemaphoreAttributes
0x180021ac0  call    cs:__imp_CreateSemaphoreExW
0x180021ac6  mov     r15, rax
0x180021ac9  test    rax, rax
0x180021acc  jnz     short loc_180021AFC
0x180021ace  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021ad3  mov     edi, eax
0x180021ad5  test    eax, eax
0x180021ad7  jns     short loc_180021B30
0x180021ad9  mov     rcx, [rsp+278h]; this
0x180021ae1  lea     r8, aWil; "wil"
0x180021ae8  mov     r9d, eax; char *
0x180021aeb  mov     edx, 8Bh; void *
0x180021af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021af5  mov     eax, edi
0x180021af7  jmp     loc_180021BCE
0x180021afc  call    cs:__imp_GetLastError
0x180021b02  mov     rdi, [rbx]
0x180021b05  test    rdi, rdi
0x180021b08  jz      short loc_180021B2D
0x180021b0a  call    cs:__imp_GetLastError
0x180021b10  mov     rcx, rdi; hObject
0x180021b13  mov     r14d, eax
0x180021b16  call    cs:__imp_CloseHandle
0x180021b1c  test    eax, eax
0x180021b1e  jz      loc_180021C13
0x180021b24  mov     ecx, r14d; dwErrCode
0x180021b27  call    cs:__imp_SetLastError
0x180021b2d  mov     [rbx], r15
0x180021b30  lea     r8, asc_1800538C0; "h"
0x180021b37  shr     rbp, 1Fh
0x180021b3b  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180021b40  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180021b45  test    ebp, ebp
0x180021b47  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180021b4f  lea     r9, [rsp+278h+Name]; lpName
0x180021b54  mov     [rsp+278h+dwFlags], r12d; int
0x180021b59  cmovnz  esi, ebp
0x180021b5c  mov     edx, ebp; lInitialCount
0x180021b5e  mov     r8d, esi; lMaximumCount
0x180021b61  xor     ecx, ecx; lpSemaphoreAttributes
0x180021b63  call    cs:__imp_CreateSemaphoreExW
0x180021b69  mov     rsi, rax
0x180021b6c  test    rax, rax
0x180021b6f  jnz     short loc_180021B9C
0x180021b71  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021b76  mov     ebx, eax
0x180021b78  test    eax, eax
0x180021b7a  jns     short loc_180021BCC
0x180021b7c  mov     rcx, [rsp+278h]; this
0x180021b84  lea     r8, aWil; "wil"
0x180021b8b  mov     r9d, eax; char *
0x180021b8e  mov     edx, 90h; void *
0x180021b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b98  mov     eax, ebx
0x180021b9a  jmp     short loc_180021BCE
0x180021b9c  call    cs:__imp_GetLastError
0x180021ba2  mov     rdi, [rbx+8]
0x180021ba6  test    rdi, rdi
0x180021ba9  jz      short loc_180021BC8
0x180021bab  call    cs:__imp_GetLastError
0x180021bb1  mov     rcx, rdi; hObject
0x180021bb4  mov     ebp, eax
0x180021bb6  call    cs:__imp_CloseHandle
0x180021bbc  test    eax, eax
0x180021bbe  jz      short loc_180021BFA
0x180021bc0  mov     ecx, ebp; dwErrCode
0x180021bc2  call    cs:__imp_SetLastError
0x180021bc8  mov     [rbx+8], rsi
0x180021bcc  xor     eax, eax
0x180021bce  mov     rcx, [rsp+278h+var_38]
0x180021bd6  xor     rcx, rsp; StackCookie
0x180021bd9  call    __security_check_cookie
0x180021bde  lea     r11, [rsp+278h+var_28]
0x180021be6  mov     rbx, [r11+38h]
0x180021bea  mov     rbp, [r11+40h]
0x180021bee  mov     rsp, r11
0x180021bf1  pop     r15
0x180021bf3  pop     r14
0x180021bf5  pop     r12
0x180021bf7  pop     rdi
0x180021bf8  pop     rsi
0x180021bf9  retn
0x180021bfa  mov     rcx, [rsp+278h]; this
0x180021c02  mov     edx, 0A0Bh; void *
0x180021c07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021c0d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021c13  mov     rcx, [rsp+278h]; this
0x180021c1b  mov     edx, 0A0Bh; void *
0x180021c20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

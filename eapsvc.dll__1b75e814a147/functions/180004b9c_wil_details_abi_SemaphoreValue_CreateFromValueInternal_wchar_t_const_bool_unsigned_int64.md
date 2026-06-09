# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004b9c`
- end: `0x180004da9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004428`
- `0x1800047cc`

## callees

- `0x180001f60`
- `0x180004b9c`
- `0x180005ad8`
- `0x180008274`
- `0x180008cb8`
- `0x180009a4c`
- `0x180009a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004c60`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004cfc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004c60`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004cfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004cc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004cc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004caf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004caf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d39`

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
0x180004b9c  mov     [rsp+arg_8], rbx
0x180004ba1  mov     [rsp+arg_10], rbp
0x180004ba6  push    rsi
0x180004ba7  push    rdi
0x180004ba8  push    r12
0x180004baa  push    r14
0x180004bac  push    r15
0x180004bae  sub     rsp, 250h
0x180004bb5  mov     rax, cs:__security_cookie
0x180004bbc  xor     rax, rsp
0x180004bbf  mov     [rsp+278h+var_38], rax
0x180004bc7  mov     rax, 0C000000000000000h
0x180004bd1  mov     rbp, r9
0x180004bd4  mov     r8, rdx
0x180004bd7  mov     rdi, rcx
0x180004bda  test    rax, r9
0x180004bdd  jnz     loc_180004D90
0x180004be3  xor     r12d, r12d
0x180004be6  lea     rax, [rsp+278h+Name]
0x180004beb  mov     ecx, 7FFFFFFEh
0x180004bf0  mov     edx, 104h
0x180004bf5  lea     esi, [r12+1]
0x180004bfa  test    rcx, rcx
0x180004bfd  jz      short loc_180004C1D
0x180004bff  movzx   r9d, word ptr [r8]
0x180004c03  test    r9w, r9w
0x180004c07  jz      short loc_180004C1D
0x180004c09  mov     [rax], r9w
0x180004c0d  add     r8, 2
0x180004c11  add     rax, 2
0x180004c15  sub     rcx, rsi
0x180004c18  sub     rdx, rsi; unsigned __int64
0x180004c1b  jnz     short loc_180004BFA
0x180004c1d  test    rdx, rdx
0x180004c20  lea     rcx, [rax-2]
0x180004c24  lea     r8, aP0; "_p0"
0x180004c2b  cmovnz  rcx, rax
0x180004c2f  mov     [rcx], r12w
0x180004c33  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004c38  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004c3d  mov     edx, ebp
0x180004c3f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004c47  and     edx, 7FFFFFFFh; lInitialCount
0x180004c4d  mov     [rsp+278h+dwFlags], r12d; int
0x180004c52  mov     r8d, esi
0x180004c55  lea     r9, [rsp+278h+Name]; lpName
0x180004c5a  cmova   r8d, edx; lMaximumCount
0x180004c5e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004c60  call    cs:__imp_CreateSemaphoreExW
0x180004c66  mov     r15, rax
0x180004c69  test    rax, rax
0x180004c6c  jnz     short loc_180004C95
0x180004c6e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c73  mov     ebx, eax
0x180004c75  test    eax, eax
0x180004c77  jns     short loc_180004CC9
0x180004c79  mov     edx, 8Bh; void *
0x180004c7e  mov     rcx, [rsp+278h]; this
0x180004c86  mov     r9d, ebx; char *
0x180004c89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c8e  mov     eax, ebx
0x180004c90  jmp     loc_180004D51
0x180004c95  call    cs:__imp_GetLastError
0x180004c9b  mov     rbx, [rdi]
0x180004c9e  test    rbx, rbx
0x180004ca1  jz      short loc_180004CC6
0x180004ca3  call    cs:__imp_GetLastError
0x180004ca9  mov     rcx, rbx; hObject
0x180004cac  mov     r14d, eax
0x180004caf  call    cs:__imp_CloseHandle
0x180004cb5  test    eax, eax
0x180004cb7  jz      loc_180004D96
0x180004cbd  mov     ecx, r14d; dwErrCode
0x180004cc0  call    cs:__imp_SetLastError
0x180004cc6  mov     [rdi], r15
0x180004cc9  lea     r8, asc_180018F18; "h"
0x180004cd0  shr     rbp, 1Fh
0x180004cd4  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004cd9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180004cde  test    ebp, ebp
0x180004ce0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004ce8  lea     r9, [rsp+278h+Name]; lpName
0x180004ced  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004cf2  cmovnz  esi, ebp
0x180004cf5  mov     edx, ebp; lInitialCount
0x180004cf7  mov     r8d, esi; lMaximumCount
0x180004cfa  xor     ecx, ecx; lpSemaphoreAttributes
0x180004cfc  call    cs:__imp_CreateSemaphoreExW
0x180004d02  mov     rsi, rax
0x180004d05  test    rax, rax
0x180004d08  jnz     short loc_180004D1F
0x180004d0a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d0f  mov     ebx, eax
0x180004d11  test    eax, eax
0x180004d13  jns     short loc_180004D4F
0x180004d15  mov     edx, 90h
0x180004d1a  jmp     loc_180004C7E
0x180004d1f  call    cs:__imp_GetLastError
0x180004d25  mov     rbx, [rdi+8]
0x180004d29  test    rbx, rbx
0x180004d2c  jz      short loc_180004D4B
0x180004d2e  call    cs:__imp_GetLastError
0x180004d34  mov     rcx, rbx; hObject
0x180004d37  mov     ebp, eax
0x180004d39  call    cs:__imp_CloseHandle
0x180004d3f  test    eax, eax
0x180004d41  jz      short loc_180004D7D
0x180004d43  mov     ecx, ebp; dwErrCode
0x180004d45  call    cs:__imp_SetLastError
0x180004d4b  mov     [rdi+8], rsi
0x180004d4f  xor     eax, eax
0x180004d51  mov     rcx, [rsp+278h+var_38]
0x180004d59  xor     rcx, rsp; StackCookie
0x180004d5c  call    __security_check_cookie
0x180004d61  lea     r11, [rsp+278h+var_28]
0x180004d69  mov     rbx, [r11+38h]
0x180004d6d  mov     rbp, [r11+40h]
0x180004d71  mov     rsp, r11
0x180004d74  pop     r15
0x180004d76  pop     r14
0x180004d78  pop     r12
0x180004d7a  pop     rdi
0x180004d7b  pop     rsi
0x180004d7c  retn
0x180004d7d  mov     rcx, [rsp+278h]; this
0x180004d85  mov     edx, 0A0Bh; void *
0x180004d8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004d96  mov     rcx, [rsp+278h]; this
0x180004d9e  mov     edx, 0A0Bh; void *
0x180004da3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

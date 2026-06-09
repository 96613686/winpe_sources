# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180005880`
- end: `0x180005aaa`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800050b8`
- `0x180005488`

## callees

- `0x1800024a0`
- `0x180005880`
- `0x1800066e8`
- `0x180008b94`
- `0x1800095d8`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005944`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800059e7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005944`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800059e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000598e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000598e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000599a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000599a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a3a`

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
0x180005880  mov     [rsp+arg_8], rbx
0x180005885  mov     [rsp+arg_10], rbp
0x18000588a  push    rsi
0x18000588b  push    rdi
0x18000588c  push    r12
0x18000588e  push    r14
0x180005890  push    r15
0x180005892  sub     rsp, 250h
0x180005899  mov     rax, cs:__security_cookie
0x1800058a0  xor     rax, rsp
0x1800058a3  mov     [rsp+278h+var_38], rax
0x1800058ab  mov     rax, 0C000000000000000h
0x1800058b5  mov     rbp, r9
0x1800058b8  mov     r8, rdx
0x1800058bb  mov     rbx, rcx
0x1800058be  test    rax, r9
0x1800058c1  jnz     loc_180005A91
0x1800058c7  xor     r12d, r12d
0x1800058ca  lea     rax, [rsp+278h+Name]
0x1800058cf  mov     ecx, 7FFFFFFEh
0x1800058d4  mov     edx, 104h
0x1800058d9  lea     esi, [r12+1]
0x1800058de  test    rcx, rcx
0x1800058e1  jz      short loc_180005901
0x1800058e3  movzx   r9d, word ptr [r8]
0x1800058e7  test    r9w, r9w
0x1800058eb  jz      short loc_180005901
0x1800058ed  mov     [rax], r9w
0x1800058f1  add     r8, 2
0x1800058f5  add     rax, 2
0x1800058f9  sub     rcx, rsi
0x1800058fc  sub     rdx, rsi; unsigned __int64
0x1800058ff  jnz     short loc_1800058DE
0x180005901  test    rdx, rdx
0x180005904  lea     rcx, [rax-2]
0x180005908  lea     r8, aP0; "_p0"
0x18000590f  cmovnz  rcx, rax
0x180005913  mov     [rcx], r12w
0x180005917  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000591c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005921  mov     edx, ebp
0x180005923  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000592b  and     edx, 7FFFFFFFh; lInitialCount
0x180005931  mov     [rsp+278h+dwFlags], r12d; int
0x180005936  mov     r8d, esi
0x180005939  lea     r9, [rsp+278h+Name]; lpName
0x18000593e  cmova   r8d, edx; lMaximumCount
0x180005942  xor     ecx, ecx; lpSemaphoreAttributes
0x180005944  call    cs:__imp_CreateSemaphoreExW
0x18000594a  mov     r15, rax
0x18000594d  test    rax, rax
0x180005950  jnz     short loc_180005980
0x180005952  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005957  mov     edi, eax
0x180005959  test    eax, eax
0x18000595b  jns     short loc_1800059B4
0x18000595d  mov     rcx, [rsp+278h]; this
0x180005965  lea     r8, aWil; "wil"
0x18000596c  mov     r9d, eax; char *
0x18000596f  mov     edx, 8Bh; void *
0x180005974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005979  mov     eax, edi
0x18000597b  jmp     loc_180005A52
0x180005980  call    cs:__imp_GetLastError
0x180005986  mov     rdi, [rbx]
0x180005989  test    rdi, rdi
0x18000598c  jz      short loc_1800059B1
0x18000598e  call    cs:__imp_GetLastError
0x180005994  mov     rcx, rdi; hObject
0x180005997  mov     r14d, eax
0x18000599a  call    cs:__imp_CloseHandle
0x1800059a0  test    eax, eax
0x1800059a2  jz      loc_180005A97
0x1800059a8  mov     ecx, r14d; dwErrCode
0x1800059ab  call    cs:__imp_SetLastError
0x1800059b1  mov     [rbx], r15
0x1800059b4  lea     r8, asc_18001A4A8; "h"
0x1800059bb  shr     rbp, 1Fh
0x1800059bf  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800059c4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800059c9  test    ebp, ebp
0x1800059cb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800059d3  lea     r9, [rsp+278h+Name]; lpName
0x1800059d8  mov     [rsp+278h+dwFlags], r12d; int
0x1800059dd  cmovnz  esi, ebp
0x1800059e0  mov     edx, ebp; lInitialCount
0x1800059e2  mov     r8d, esi; lMaximumCount
0x1800059e5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800059e7  call    cs:__imp_CreateSemaphoreExW
0x1800059ed  mov     rsi, rax
0x1800059f0  test    rax, rax
0x1800059f3  jnz     short loc_180005A20
0x1800059f5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800059fa  mov     ebx, eax
0x1800059fc  test    eax, eax
0x1800059fe  jns     short loc_180005A50
0x180005a00  mov     rcx, [rsp+278h]; this
0x180005a08  lea     r8, aWil; "wil"
0x180005a0f  mov     r9d, eax; char *
0x180005a12  mov     edx, 90h; void *
0x180005a17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a1c  mov     eax, ebx
0x180005a1e  jmp     short loc_180005A52
0x180005a20  call    cs:__imp_GetLastError
0x180005a26  mov     rdi, [rbx+8]
0x180005a2a  test    rdi, rdi
0x180005a2d  jz      short loc_180005A4C
0x180005a2f  call    cs:__imp_GetLastError
0x180005a35  mov     rcx, rdi; hObject
0x180005a38  mov     ebp, eax
0x180005a3a  call    cs:__imp_CloseHandle
0x180005a40  test    eax, eax
0x180005a42  jz      short loc_180005A7E
0x180005a44  mov     ecx, ebp; dwErrCode
0x180005a46  call    cs:__imp_SetLastError
0x180005a4c  mov     [rbx+8], rsi
0x180005a50  xor     eax, eax
0x180005a52  mov     rcx, [rsp+278h+var_38]
0x180005a5a  xor     rcx, rsp; StackCookie
0x180005a5d  call    __security_check_cookie
0x180005a62  lea     r11, [rsp+278h+var_28]
0x180005a6a  mov     rbx, [r11+38h]
0x180005a6e  mov     rbp, [r11+40h]
0x180005a72  mov     rsp, r11
0x180005a75  pop     r15
0x180005a77  pop     r14
0x180005a79  pop     r12
0x180005a7b  pop     rdi
0x180005a7c  pop     rsi
0x180005a7d  retn
0x180005a7e  mov     rcx, [rsp+278h]; this
0x180005a86  mov     edx, 0A0Bh; void *
0x180005a8b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a91  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005a97  mov     rcx, [rsp+278h]; this
0x180005a9f  mov     edx, 0A0Bh; void *
0x180005aa4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

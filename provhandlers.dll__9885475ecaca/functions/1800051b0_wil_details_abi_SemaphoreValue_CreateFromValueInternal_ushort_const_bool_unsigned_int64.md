# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800051b0`
- end: `0x1800053da`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d50`
- `0x180016630`

## callees

- `0x1800051b0`
- `0x180006218`
- `0x1800076a4`
- `0x180007e24`
- `0x18000872c`
- `0x18000873c`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005274`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005317`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005274`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005376`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005376`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800051b0  mov     [rsp+arg_8], rbx
0x1800051b5  mov     [rsp+arg_10], rbp
0x1800051ba  push    rsi
0x1800051bb  push    rdi
0x1800051bc  push    r12
0x1800051be  push    r14
0x1800051c0  push    r15
0x1800051c2  sub     rsp, 250h
0x1800051c9  mov     rax, cs:__security_cookie
0x1800051d0  xor     rax, rsp
0x1800051d3  mov     [rsp+278h+var_38], rax
0x1800051db  mov     rax, 0C000000000000000h
0x1800051e5  mov     rbp, r9
0x1800051e8  mov     r8, rdx
0x1800051eb  mov     rbx, rcx
0x1800051ee  test    rax, r9
0x1800051f1  jnz     loc_1800053C1
0x1800051f7  xor     r12d, r12d
0x1800051fa  lea     rax, [rsp+278h+Name]
0x1800051ff  mov     ecx, 7FFFFFFEh
0x180005204  mov     edx, 104h
0x180005209  lea     esi, [r12+1]
0x18000520e  test    rcx, rcx
0x180005211  jz      short loc_180005231
0x180005213  movzx   r9d, word ptr [r8]
0x180005217  test    r9w, r9w
0x18000521b  jz      short loc_180005231
0x18000521d  mov     [rax], r9w
0x180005221  add     r8, 2
0x180005225  add     rax, 2
0x180005229  sub     rcx, rsi
0x18000522c  sub     rdx, rsi; unsigned __int64
0x18000522f  jnz     short loc_18000520E
0x180005231  test    rdx, rdx
0x180005234  lea     rcx, [rax-2]
0x180005238  lea     r8, aP0; "_p0"
0x18000523f  cmovnz  rcx, rax
0x180005243  mov     [rcx], r12w
0x180005247  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000524c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005251  mov     edx, ebp
0x180005253  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000525b  and     edx, 7FFFFFFFh; lInitialCount
0x180005261  mov     [rsp+278h+dwFlags], r12d; int
0x180005266  mov     r8d, esi
0x180005269  lea     r9, [rsp+278h+Name]; lpName
0x18000526e  cmova   r8d, edx; lMaximumCount
0x180005272  xor     ecx, ecx; lpSemaphoreAttributes
0x180005274  call    cs:__imp_CreateSemaphoreExW
0x18000527a  mov     r15, rax
0x18000527d  test    rax, rax
0x180005280  jnz     short loc_1800052B0
0x180005282  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005287  mov     edi, eax
0x180005289  test    eax, eax
0x18000528b  jns     short loc_1800052E4
0x18000528d  mov     rcx, [rsp+278h]; this
0x180005295  lea     r8, aWil; "wil"
0x18000529c  mov     r9d, eax; char *
0x18000529f  mov     edx, 8Bh; void *
0x1800052a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052a9  mov     eax, edi
0x1800052ab  jmp     loc_180005382
0x1800052b0  call    cs:__imp_GetLastError
0x1800052b6  mov     rdi, [rbx]
0x1800052b9  test    rdi, rdi
0x1800052bc  jz      short loc_1800052E1
0x1800052be  call    cs:__imp_GetLastError
0x1800052c4  mov     rcx, rdi; hObject
0x1800052c7  mov     r14d, eax
0x1800052ca  call    cs:__imp_CloseHandle
0x1800052d0  test    eax, eax
0x1800052d2  jz      loc_1800053C7
0x1800052d8  mov     ecx, r14d; dwErrCode
0x1800052db  call    cs:__imp_SetLastError
0x1800052e1  mov     [rbx], r15
0x1800052e4  lea     r8, asc_180042360; "h"
0x1800052eb  shr     rbp, 1Fh
0x1800052ef  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800052f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800052f9  test    ebp, ebp
0x1800052fb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005303  lea     r9, [rsp+278h+Name]; lpName
0x180005308  mov     [rsp+278h+dwFlags], r12d; int
0x18000530d  cmovnz  esi, ebp
0x180005310  mov     edx, ebp; lInitialCount
0x180005312  mov     r8d, esi; lMaximumCount
0x180005315  xor     ecx, ecx; lpSemaphoreAttributes
0x180005317  call    cs:__imp_CreateSemaphoreExW
0x18000531d  mov     rsi, rax
0x180005320  test    rax, rax
0x180005323  jnz     short loc_180005350
0x180005325  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000532a  mov     ebx, eax
0x18000532c  test    eax, eax
0x18000532e  jns     short loc_180005380
0x180005330  mov     rcx, [rsp+278h]; this
0x180005338  lea     r8, aWil; "wil"
0x18000533f  mov     r9d, eax; char *
0x180005342  mov     edx, 90h; void *
0x180005347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000534c  mov     eax, ebx
0x18000534e  jmp     short loc_180005382
0x180005350  call    cs:__imp_GetLastError
0x180005356  mov     rdi, [rbx+8]
0x18000535a  test    rdi, rdi
0x18000535d  jz      short loc_18000537C
0x18000535f  call    cs:__imp_GetLastError
0x180005365  mov     rcx, rdi; hObject
0x180005368  mov     ebp, eax
0x18000536a  call    cs:__imp_CloseHandle
0x180005370  test    eax, eax
0x180005372  jz      short loc_1800053AE
0x180005374  mov     ecx, ebp; dwErrCode
0x180005376  call    cs:__imp_SetLastError
0x18000537c  mov     [rbx+8], rsi
0x180005380  xor     eax, eax
0x180005382  mov     rcx, [rsp+278h+var_38]
0x18000538a  xor     rcx, rsp; StackCookie
0x18000538d  call    __security_check_cookie
0x180005392  lea     r11, [rsp+278h+var_28]
0x18000539a  mov     rbx, [r11+38h]
0x18000539e  mov     rbp, [r11+40h]
0x1800053a2  mov     rsp, r11
0x1800053a5  pop     r15
0x1800053a7  pop     r14
0x1800053a9  pop     r12
0x1800053ab  pop     rdi
0x1800053ac  pop     rsi
0x1800053ad  retn
0x1800053ae  mov     rcx, [rsp+278h]; this
0x1800053b6  mov     edx, 0A0Bh; void *
0x1800053bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053c1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800053c7  mov     rcx, [rsp+278h]; this
0x1800053cf  mov     edx, 0A0Bh; void *
0x1800053d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

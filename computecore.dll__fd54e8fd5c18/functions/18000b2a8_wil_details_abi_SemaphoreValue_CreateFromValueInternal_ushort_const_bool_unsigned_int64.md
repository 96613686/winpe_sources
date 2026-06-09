# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000b2a8`
- end: `0x18000b4e7`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a918`
- `0x18000acf8`

## callees

- `0x1800067c0`
- `0x18000b2a8`
- `0x18000c690`
- `0x18000f1b4`
- `0x18000fc04`
- `0x1800115b4`
- `0x1800115c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b371`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b417`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b371`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b45f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b45f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b46a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b46a`

## string_xrefs

- `0x18000b4b5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b4d5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  const char *v20; // r9
  unsigned __int64 v21; // rsi
  wil::details *v22; // rcx
  HANDLE v23; // rbp
  int v24; // eax
  unsigned int v25; // ebx
  void *v26; // rdi
  DWORD v27; // esi
  const char *v28; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v21 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v21 )
    v10 = v21;
  v23 = CreateSemaphoreExW(0, v21, v10, Name, 0, 0x1F0003u);
  if ( v23 )
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
    *((_QWORD *)this + 1) = v23;
  }
  else
  {
    v24 = wil::details::GetLastErrorFailHr(v22);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v24,
        dwFlagsa);
      return v25;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b2a8  mov     [rsp+arg_8], rbx
0x18000b2ad  push    rbp
0x18000b2ae  push    rsi
0x18000b2af  push    rdi
0x18000b2b0  push    r12
0x18000b2b2  push    r13
0x18000b2b4  push    r14
0x18000b2b6  push    r15
0x18000b2b8  sub     rsp, 250h
0x18000b2bf  mov     rax, cs:__security_cookie
0x18000b2c6  xor     rax, rsp
0x18000b2c9  mov     [rsp+288h+var_48], rax
0x18000b2d1  mov     rax, 0C000000000000000h
0x18000b2db  mov     rsi, r9
0x18000b2de  mov     r8, rdx
0x18000b2e1  mov     rbx, rcx
0x18000b2e4  test    rax, r9
0x18000b2e7  jnz     loc_18000B4C7
0x18000b2ed  xor     r12d, r12d
0x18000b2f0  lea     rax, [rsp+288h+Name]
0x18000b2f5  mov     r13d, 104h
0x18000b2fb  mov     ecx, 7FFFFFFEh
0x18000b300  mov     edx, r13d
0x18000b303  lea     ebp, [r12+1]
0x18000b308  test    rcx, rcx
0x18000b30b  jz      short loc_18000B32B
0x18000b30d  movzx   r9d, word ptr [r8]
0x18000b311  test    r9w, r9w
0x18000b315  jz      short loc_18000B32B
0x18000b317  mov     [rax], r9w
0x18000b31b  add     r8, 2
0x18000b31f  add     rax, 2
0x18000b323  sub     rcx, rbp
0x18000b326  sub     rdx, rbp
0x18000b329  jnz     short loc_18000B308
0x18000b32b  test    rdx, rdx
0x18000b32e  lea     rcx, [rax-2]
0x18000b332  lea     r8, aP0; "_p0"
0x18000b339  mov     rdx, r13; unsigned __int64
0x18000b33c  cmovnz  rcx, rax
0x18000b340  mov     [rcx], r12w
0x18000b344  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000b349  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b34e  mov     edx, esi
0x18000b350  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b358  and     edx, 7FFFFFFFh; lInitialCount
0x18000b35e  mov     [rsp+288h+dwFlags], r12d; int
0x18000b363  mov     r8d, ebp
0x18000b366  lea     r9, [rsp+288h+Name]; lpName
0x18000b36b  cmova   r8d, edx; lMaximumCount
0x18000b36f  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b371  call    cs:__imp_CreateSemaphoreExW
0x18000b377  mov     r15, rax
0x18000b37a  test    rax, rax
0x18000b37d  jnz     short loc_18000B3AD
0x18000b37f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b384  mov     edi, eax
0x18000b386  test    eax, eax
0x18000b388  jns     short loc_18000B3E1
0x18000b38a  mov     rcx, [rsp+288h]; this
0x18000b392  lea     r8, aWil; "wil"
0x18000b399  mov     r9d, eax; char *
0x18000b39c  mov     edx, 8Bh; void *
0x18000b3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3a6  mov     eax, edi
0x18000b3a8  jmp     loc_18000B482
0x18000b3ad  call    cs:__imp_GetLastError
0x18000b3b3  mov     rdi, [rbx]
0x18000b3b6  test    rdi, rdi
0x18000b3b9  jz      short loc_18000B3DE
0x18000b3bb  call    cs:__imp_GetLastError
0x18000b3c1  mov     rcx, rdi; hObject
0x18000b3c4  mov     r14d, eax
0x18000b3c7  call    cs:__imp_CloseHandle
0x18000b3cd  test    eax, eax
0x18000b3cf  jz      loc_18000B4CD
0x18000b3d5  mov     ecx, r14d; dwErrCode
0x18000b3d8  call    cs:__imp_SetLastError
0x18000b3de  mov     [rbx], r15
0x18000b3e1  lea     r8, asc_1800ADA68; "h"
0x18000b3e8  shr     rsi, 1Fh
0x18000b3ec  mov     rdx, r13; unsigned __int64
0x18000b3ef  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000b3f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b3f9  test    esi, esi
0x18000b3fb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b403  lea     r9, [rsp+288h+Name]; lpName
0x18000b408  mov     [rsp+288h+dwFlags], r12d; int
0x18000b40d  cmovnz  ebp, esi
0x18000b410  mov     edx, esi; lInitialCount
0x18000b412  mov     r8d, ebp; lMaximumCount
0x18000b415  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b417  call    cs:__imp_CreateSemaphoreExW
0x18000b41d  mov     rbp, rax
0x18000b420  test    rax, rax
0x18000b423  jnz     short loc_18000B450
0x18000b425  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b42a  mov     ebx, eax
0x18000b42c  test    eax, eax
0x18000b42e  jns     short loc_18000B480
0x18000b430  mov     rcx, [rsp+288h]; this
0x18000b438  lea     r8, aWil; "wil"
0x18000b43f  mov     r9d, eax; char *
0x18000b442  mov     edx, 90h; void *
0x18000b447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b44c  mov     eax, ebx
0x18000b44e  jmp     short loc_18000B482
0x18000b450  call    cs:__imp_GetLastError
0x18000b456  mov     rdi, [rbx+8]
0x18000b45a  test    rdi, rdi
0x18000b45d  jz      short loc_18000B47C
0x18000b45f  call    cs:__imp_GetLastError
0x18000b465  mov     rcx, rdi; hObject
0x18000b468  mov     esi, eax
0x18000b46a  call    cs:__imp_CloseHandle
0x18000b470  test    eax, eax
0x18000b472  jz      short loc_18000B4AD
0x18000b474  mov     ecx, esi; dwErrCode
0x18000b476  call    cs:__imp_SetLastError
0x18000b47c  mov     [rbx+8], rbp
0x18000b480  xor     eax, eax
0x18000b482  mov     rcx, [rsp+288h+var_48]
0x18000b48a  xor     rcx, rsp; StackCookie
0x18000b48d  call    __security_check_cookie
0x18000b492  mov     rbx, [rsp+288h+arg_8]
0x18000b49a  add     rsp, 250h
0x18000b4a1  pop     r15
0x18000b4a3  pop     r14
0x18000b4a5  pop     r13
0x18000b4a7  pop     r12
0x18000b4a9  pop     rdi
0x18000b4aa  pop     rsi
0x18000b4ab  pop     rbp
0x18000b4ac  retn
0x18000b4ad  mov     rcx, [rsp+288h]; this
0x18000b4b5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b4bc  mov     edx, 0A0Bh; void *
0x18000b4c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b4c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b4cd  mov     rcx, [rsp+288h]; this
0x18000b4d5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b4dc  mov     edx, 0A0Bh; void *
0x18000b4e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

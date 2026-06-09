# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008afc`
- end: `0x180008d34`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008318`
- `0x1800086f8`

## callees

- `0x180002bf0`
- `0x180008afc`
- `0x18000bcb8`
- `0x18000ec54`
- `0x18000f698`
- `0x1800108c4`
- `0x1800108d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008bc0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008c63`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008bc0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cb6`

## string_xrefs

- `0x180008d02`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008d22`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008afc  mov     [rsp+arg_8], rbx
0x180008b01  mov     [rsp+arg_10], rbp
0x180008b06  push    rsi
0x180008b07  push    rdi
0x180008b08  push    r12
0x180008b0a  push    r14
0x180008b0c  push    r15
0x180008b0e  sub     rsp, 250h
0x180008b15  mov     rax, cs:__security_cookie
0x180008b1c  xor     rax, rsp
0x180008b1f  mov     [rsp+278h+var_38], rax
0x180008b27  mov     rax, 0C000000000000000h
0x180008b31  mov     rbp, r9
0x180008b34  mov     r8, rdx
0x180008b37  mov     rbx, rcx
0x180008b3a  test    rax, r9
0x180008b3d  jnz     loc_180008D14
0x180008b43  xor     r12d, r12d
0x180008b46  lea     rax, [rsp+278h+Name]
0x180008b4b  mov     ecx, 7FFFFFFEh
0x180008b50  mov     edx, 104h
0x180008b55  lea     esi, [r12+1]
0x180008b5a  test    rcx, rcx
0x180008b5d  jz      short loc_180008B7D
0x180008b5f  movzx   r9d, word ptr [r8]
0x180008b63  test    r9w, r9w
0x180008b67  jz      short loc_180008B7D
0x180008b69  mov     [rax], r9w
0x180008b6d  add     r8, 2
0x180008b71  add     rax, 2
0x180008b75  sub     rcx, rsi
0x180008b78  sub     rdx, rsi; unsigned __int64
0x180008b7b  jnz     short loc_180008B5A
0x180008b7d  test    rdx, rdx
0x180008b80  lea     rcx, [rax-2]
0x180008b84  lea     r8, aP0; "_p0"
0x180008b8b  cmovnz  rcx, rax
0x180008b8f  mov     [rcx], r12w
0x180008b93  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180008b98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b9d  mov     edx, ebp
0x180008b9f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008ba7  and     edx, 7FFFFFFFh; lInitialCount
0x180008bad  mov     [rsp+278h+dwFlags], r12d; int
0x180008bb2  mov     r8d, esi
0x180008bb5  lea     r9, [rsp+278h+Name]; lpName
0x180008bba  cmova   r8d, edx; lMaximumCount
0x180008bbe  xor     ecx, ecx; lpSemaphoreAttributes
0x180008bc0  call    cs:__imp_CreateSemaphoreExW
0x180008bc6  mov     r15, rax
0x180008bc9  test    rax, rax
0x180008bcc  jnz     short loc_180008BFC
0x180008bce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008bd3  mov     edi, eax
0x180008bd5  test    eax, eax
0x180008bd7  jns     short loc_180008C30
0x180008bd9  mov     rcx, [rsp+278h]; this
0x180008be1  lea     r8, aWil; "wil"
0x180008be8  mov     r9d, eax; char *
0x180008beb  mov     edx, 8Bh; void *
0x180008bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bf5  mov     eax, edi
0x180008bf7  jmp     loc_180008CCE
0x180008bfc  call    cs:__imp_GetLastError
0x180008c02  mov     rdi, [rbx]
0x180008c05  test    rdi, rdi
0x180008c08  jz      short loc_180008C2D
0x180008c0a  call    cs:__imp_GetLastError
0x180008c10  mov     rcx, rdi; hObject
0x180008c13  mov     r14d, eax
0x180008c16  call    cs:__imp_CloseHandle
0x180008c1c  test    eax, eax
0x180008c1e  jz      loc_180008D1A
0x180008c24  mov     ecx, r14d; dwErrCode
0x180008c27  call    cs:__imp_SetLastError
0x180008c2d  mov     [rbx], r15
0x180008c30  lea     r8, asc_1800D7810; "h"
0x180008c37  shr     rbp, 1Fh
0x180008c3b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180008c40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c45  test    ebp, ebp
0x180008c47  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008c4f  lea     r9, [rsp+278h+Name]; lpName
0x180008c54  mov     [rsp+278h+dwFlags], r12d; int
0x180008c59  cmovnz  esi, ebp
0x180008c5c  mov     edx, ebp; lInitialCount
0x180008c5e  mov     r8d, esi; lMaximumCount
0x180008c61  xor     ecx, ecx; lpSemaphoreAttributes
0x180008c63  call    cs:__imp_CreateSemaphoreExW
0x180008c69  mov     rsi, rax
0x180008c6c  test    rax, rax
0x180008c6f  jnz     short loc_180008C9C
0x180008c71  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c76  mov     ebx, eax
0x180008c78  test    eax, eax
0x180008c7a  jns     short loc_180008CCC
0x180008c7c  mov     rcx, [rsp+278h]; this
0x180008c84  lea     r8, aWil; "wil"
0x180008c8b  mov     r9d, eax; char *
0x180008c8e  mov     edx, 90h; void *
0x180008c93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c98  mov     eax, ebx
0x180008c9a  jmp     short loc_180008CCE
0x180008c9c  call    cs:__imp_GetLastError
0x180008ca2  mov     rdi, [rbx+8]
0x180008ca6  test    rdi, rdi
0x180008ca9  jz      short loc_180008CC8
0x180008cab  call    cs:__imp_GetLastError
0x180008cb1  mov     rcx, rdi; hObject
0x180008cb4  mov     ebp, eax
0x180008cb6  call    cs:__imp_CloseHandle
0x180008cbc  test    eax, eax
0x180008cbe  jz      short loc_180008CFA
0x180008cc0  mov     ecx, ebp; dwErrCode
0x180008cc2  call    cs:__imp_SetLastError
0x180008cc8  mov     [rbx+8], rsi
0x180008ccc  xor     eax, eax
0x180008cce  mov     rcx, [rsp+278h+var_38]
0x180008cd6  xor     rcx, rsp; StackCookie
0x180008cd9  call    __security_check_cookie
0x180008cde  lea     r11, [rsp+278h+var_28]
0x180008ce6  mov     rbx, [r11+38h]
0x180008cea  mov     rbp, [r11+40h]
0x180008cee  mov     rsp, r11
0x180008cf1  pop     r15
0x180008cf3  pop     r14
0x180008cf5  pop     r12
0x180008cf7  pop     rdi
0x180008cf8  pop     rsi
0x180008cf9  retn
0x180008cfa  mov     rcx, [rsp+278h]; this
0x180008d02  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008d09  mov     edx, 0A0Bh; void *
0x180008d0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d14  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008d1a  mov     rcx, [rsp+278h]; this
0x180008d22  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008d29  mov     edx, 0A0Bh; void *
0x180008d2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

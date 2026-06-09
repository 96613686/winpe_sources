# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004a78`
- end: `0x180004ca9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800046a8`
- `0x180012254`

## callees

- `0x1800022e0`
- `0x180004a78`
- `0x1800053c8`
- `0x180006294`
- `0x180006bd4`
- `0x18000714c`
- `0x18000715c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004b41`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004be7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004b41`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ba8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ba8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c3a`

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
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
  const char *v30; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
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
0x180004a78  mov     [rsp+arg_8], rbx
0x180004a7d  push    rbp
0x180004a7e  push    rsi
0x180004a7f  push    rdi
0x180004a80  push    r12
0x180004a82  push    r13
0x180004a84  push    r14
0x180004a86  push    r15
0x180004a88  sub     rsp, 250h
0x180004a8f  mov     rax, cs:__security_cookie
0x180004a96  xor     rax, rsp
0x180004a99  mov     [rsp+288h+var_48], rax
0x180004aa1  mov     rax, 0C000000000000000h
0x180004aab  mov     rsi, r9
0x180004aae  mov     r8, rdx
0x180004ab1  mov     rbx, rcx
0x180004ab4  test    rax, r9
0x180004ab7  jnz     loc_180004C90
0x180004abd  xor     r12d, r12d
0x180004ac0  lea     rax, [rsp+288h+Name]
0x180004ac5  mov     r13d, 104h
0x180004acb  mov     ecx, 7FFFFFFEh
0x180004ad0  mov     edx, r13d
0x180004ad3  lea     ebp, [r12+1]
0x180004ad8  test    rcx, rcx
0x180004adb  jz      short loc_180004AFB
0x180004add  movzx   r9d, word ptr [r8]
0x180004ae1  test    r9w, r9w
0x180004ae5  jz      short loc_180004AFB
0x180004ae7  mov     [rax], r9w
0x180004aeb  add     r8, 2
0x180004aef  add     rax, 2
0x180004af3  sub     rcx, rbp
0x180004af6  sub     rdx, rbp
0x180004af9  jnz     short loc_180004AD8
0x180004afb  test    rdx, rdx
0x180004afe  lea     rcx, [rax-2]
0x180004b02  lea     r8, aP0; "_p0"
0x180004b09  mov     rdx, r13; unsigned __int64
0x180004b0c  cmovnz  rcx, rax
0x180004b10  mov     [rcx], r12w
0x180004b14  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004b19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b1e  mov     edx, esi
0x180004b20  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004b28  and     edx, 7FFFFFFFh; lInitialCount
0x180004b2e  mov     [rsp+288h+dwFlags], r12d; int
0x180004b33  mov     r8d, ebp
0x180004b36  lea     r9, [rsp+288h+Name]; lpName
0x180004b3b  cmova   r8d, edx; lMaximumCount
0x180004b3f  xor     ecx, ecx; lpSemaphoreAttributes
0x180004b41  call    cs:__imp_CreateSemaphoreExW
0x180004b47  mov     r15, rax
0x180004b4a  test    rax, rax
0x180004b4d  jnz     short loc_180004B7D
0x180004b4f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004b54  mov     edi, eax
0x180004b56  test    eax, eax
0x180004b58  jns     short loc_180004BB1
0x180004b5a  mov     rcx, [rsp+288h]; this
0x180004b62  lea     r8, aWil; "wil"
0x180004b69  mov     r9d, eax; char *
0x180004b6c  mov     edx, 8Bh; void *
0x180004b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b76  mov     eax, edi
0x180004b78  jmp     loc_180004C52
0x180004b7d  call    cs:__imp_GetLastError
0x180004b83  mov     rdi, [rbx]
0x180004b86  test    rdi, rdi
0x180004b89  jz      short loc_180004BAE
0x180004b8b  call    cs:__imp_GetLastError
0x180004b91  mov     rcx, rdi; hObject
0x180004b94  mov     r14d, eax
0x180004b97  call    cs:__imp_CloseHandle
0x180004b9d  test    eax, eax
0x180004b9f  jz      loc_180004C96
0x180004ba5  mov     ecx, r14d; dwErrCode
0x180004ba8  call    cs:__imp_SetLastError
0x180004bae  mov     [rbx], r15
0x180004bb1  lea     r8, asc_180021FB8; "h"
0x180004bb8  shr     rsi, 1Fh
0x180004bbc  mov     rdx, r13; unsigned __int64
0x180004bbf  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004bc4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004bc9  test    esi, esi
0x180004bcb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004bd3  lea     r9, [rsp+288h+Name]; lpName
0x180004bd8  mov     [rsp+288h+dwFlags], r12d; int
0x180004bdd  cmovnz  ebp, esi
0x180004be0  mov     edx, esi; lInitialCount
0x180004be2  mov     r8d, ebp; lMaximumCount
0x180004be5  xor     ecx, ecx; lpSemaphoreAttributes
0x180004be7  call    cs:__imp_CreateSemaphoreExW
0x180004bed  mov     rbp, rax
0x180004bf0  test    rax, rax
0x180004bf3  jnz     short loc_180004C20
0x180004bf5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004bfa  mov     ebx, eax
0x180004bfc  test    eax, eax
0x180004bfe  jns     short loc_180004C50
0x180004c00  mov     rcx, [rsp+288h]; this
0x180004c08  lea     r8, aWil; "wil"
0x180004c0f  mov     r9d, eax; char *
0x180004c12  mov     edx, 90h; void *
0x180004c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c1c  mov     eax, ebx
0x180004c1e  jmp     short loc_180004C52
0x180004c20  call    cs:__imp_GetLastError
0x180004c26  mov     rdi, [rbx+8]
0x180004c2a  test    rdi, rdi
0x180004c2d  jz      short loc_180004C4C
0x180004c2f  call    cs:__imp_GetLastError
0x180004c35  mov     rcx, rdi; hObject
0x180004c38  mov     esi, eax
0x180004c3a  call    cs:__imp_CloseHandle
0x180004c40  test    eax, eax
0x180004c42  jz      short loc_180004C7D
0x180004c44  mov     ecx, esi; dwErrCode
0x180004c46  call    cs:__imp_SetLastError
0x180004c4c  mov     [rbx+8], rbp
0x180004c50  xor     eax, eax
0x180004c52  mov     rcx, [rsp+288h+var_48]
0x180004c5a  xor     rcx, rsp; StackCookie
0x180004c5d  call    __security_check_cookie
0x180004c62  mov     rbx, [rsp+288h+arg_8]
0x180004c6a  add     rsp, 250h
0x180004c71  pop     r15
0x180004c73  pop     r14
0x180004c75  pop     r13
0x180004c77  pop     r12
0x180004c79  pop     rdi
0x180004c7a  pop     rsi
0x180004c7b  pop     rbp
0x180004c7c  retn
0x180004c7d  mov     rcx, [rsp+288h]; this
0x180004c85  mov     edx, 0A0Bh; void *
0x180004c8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c96  mov     rcx, [rsp+288h]; this
0x180004c9e  mov     edx, 0A0Bh; void *
0x180004ca3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

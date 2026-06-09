# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000b940`
- end: `0x18000bb4d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b59c`

## callees

- `0x180001ce0`
- `0x18000b940`
- `0x18000c1f8`
- `0x18000cf84`
- `0x18000d230`
- `0x18000d71c`
- `0x18000d72c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ba39`
- `KERNEL32!GetLastError` at `0x18000ba47`
- `KERNEL32!GetLastError` at `0x18000bac3`
- `KERNEL32!GetLastError` at `0x18000bad2`
- `KERNEL32!GetLastError` at `0x18000ba39`
- `KERNEL32!GetLastError` at `0x18000ba47`
- `KERNEL32!GetLastError` at `0x18000bac3`
- `KERNEL32!GetLastError` at `0x18000bad2`
- `KERNEL32!CloseHandle` at `0x18000ba53`
- `KERNEL32!CloseHandle` at `0x18000badd`
- `KERNEL32!CloseHandle` at `0x18000ba53`
- `KERNEL32!CloseHandle` at `0x18000badd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ba04`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000baa0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ba04`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000baa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bae9`

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
0x18000b940  mov     [rsp+arg_8], rbx
0x18000b945  mov     [rsp+arg_10], rbp
0x18000b94a  push    rsi
0x18000b94b  push    rdi
0x18000b94c  push    r12
0x18000b94e  push    r14
0x18000b950  push    r15
0x18000b952  sub     rsp, 250h
0x18000b959  mov     rax, cs:__security_cookie
0x18000b960  xor     rax, rsp
0x18000b963  mov     [rsp+278h+var_38], rax
0x18000b96b  mov     rax, 0C000000000000000h
0x18000b975  mov     rbp, r9
0x18000b978  mov     r8, rdx
0x18000b97b  mov     rdi, rcx
0x18000b97e  test    rax, r9
0x18000b981  jnz     loc_18000BB34
0x18000b987  xor     r12d, r12d
0x18000b98a  lea     rax, [rsp+278h+Name]
0x18000b98f  mov     ecx, 7FFFFFFEh
0x18000b994  mov     edx, 104h
0x18000b999  lea     esi, [r12+1]
0x18000b99e  test    rcx, rcx
0x18000b9a1  jz      short loc_18000B9C1
0x18000b9a3  movzx   r9d, word ptr [r8]
0x18000b9a7  test    r9w, r9w
0x18000b9ab  jz      short loc_18000B9C1
0x18000b9ad  mov     [rax], r9w
0x18000b9b1  add     r8, 2
0x18000b9b5  add     rax, 2
0x18000b9b9  sub     rcx, rsi
0x18000b9bc  sub     rdx, rsi; unsigned __int64
0x18000b9bf  jnz     short loc_18000B99E
0x18000b9c1  test    rdx, rdx
0x18000b9c4  lea     rcx, [rax-2]
0x18000b9c8  lea     r8, aP0; "_p0"
0x18000b9cf  cmovnz  rcx, rax
0x18000b9d3  mov     [rcx], r12w
0x18000b9d7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000b9dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b9e1  mov     edx, ebp
0x18000b9e3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b9eb  and     edx, 7FFFFFFFh; lInitialCount
0x18000b9f1  mov     [rsp+278h+dwFlags], r12d; int
0x18000b9f6  mov     r8d, esi
0x18000b9f9  lea     r9, [rsp+278h+Name]; lpName
0x18000b9fe  cmova   r8d, edx; lMaximumCount
0x18000ba02  xor     ecx, ecx; lpSemaphoreAttributes
0x18000ba04  call    cs:__imp_CreateSemaphoreExW
0x18000ba0a  mov     r15, rax
0x18000ba0d  test    rax, rax
0x18000ba10  jnz     short loc_18000BA39
0x18000ba12  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ba17  mov     ebx, eax
0x18000ba19  test    eax, eax
0x18000ba1b  jns     short loc_18000BA6D
0x18000ba1d  mov     edx, 8Bh; void *
0x18000ba22  mov     rcx, [rsp+278h]; this
0x18000ba2a  mov     r9d, ebx; char *
0x18000ba2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba32  mov     eax, ebx
0x18000ba34  jmp     loc_18000BAF5
0x18000ba39  call    cs:__imp_GetLastError
0x18000ba3f  mov     rbx, [rdi]
0x18000ba42  test    rbx, rbx
0x18000ba45  jz      short loc_18000BA6A
0x18000ba47  call    cs:__imp_GetLastError
0x18000ba4d  mov     rcx, rbx; hObject
0x18000ba50  mov     r14d, eax
0x18000ba53  call    cs:__imp_CloseHandle
0x18000ba59  test    eax, eax
0x18000ba5b  jz      loc_18000BB3A
0x18000ba61  mov     ecx, r14d; dwErrCode
0x18000ba64  call    cs:__imp_SetLastError
0x18000ba6a  mov     [rdi], r15
0x18000ba6d  lea     r8, asc_18000FD88; "h"
0x18000ba74  shr     rbp, 1Fh
0x18000ba78  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000ba7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ba82  test    ebp, ebp
0x18000ba84  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000ba8c  lea     r9, [rsp+278h+Name]; lpName
0x18000ba91  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000ba96  cmovnz  esi, ebp
0x18000ba99  mov     edx, ebp; lInitialCount
0x18000ba9b  mov     r8d, esi; lMaximumCount
0x18000ba9e  xor     ecx, ecx; lpSemaphoreAttributes
0x18000baa0  call    cs:__imp_CreateSemaphoreExW
0x18000baa6  mov     rsi, rax
0x18000baa9  test    rax, rax
0x18000baac  jnz     short loc_18000BAC3
0x18000baae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bab3  mov     ebx, eax
0x18000bab5  test    eax, eax
0x18000bab7  jns     short loc_18000BAF3
0x18000bab9  mov     edx, 90h
0x18000babe  jmp     loc_18000BA22
0x18000bac3  call    cs:__imp_GetLastError
0x18000bac9  mov     rbx, [rdi+8]
0x18000bacd  test    rbx, rbx
0x18000bad0  jz      short loc_18000BAEF
0x18000bad2  call    cs:__imp_GetLastError
0x18000bad8  mov     rcx, rbx; hObject
0x18000badb  mov     ebp, eax
0x18000badd  call    cs:__imp_CloseHandle
0x18000bae3  test    eax, eax
0x18000bae5  jz      short loc_18000BB21
0x18000bae7  mov     ecx, ebp; dwErrCode
0x18000bae9  call    cs:__imp_SetLastError
0x18000baef  mov     [rdi+8], rsi
0x18000baf3  xor     eax, eax
0x18000baf5  mov     rcx, [rsp+278h+var_38]
0x18000bafd  xor     rcx, rsp; StackCookie
0x18000bb00  call    __security_check_cookie
0x18000bb05  lea     r11, [rsp+278h+var_28]
0x18000bb0d  mov     rbx, [r11+38h]
0x18000bb11  mov     rbp, [r11+40h]
0x18000bb15  mov     rsp, r11
0x18000bb18  pop     r15
0x18000bb1a  pop     r14
0x18000bb1c  pop     r12
0x18000bb1e  pop     rdi
0x18000bb1f  pop     rsi
0x18000bb20  retn
0x18000bb21  mov     rcx, [rsp+278h]; this
0x18000bb29  mov     edx, 0A0Bh; void *
0x18000bb2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb34  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bb3a  mov     rcx, [rsp+278h]; this
0x18000bb42  mov     edx, 0A0Bh; void *
0x18000bb47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

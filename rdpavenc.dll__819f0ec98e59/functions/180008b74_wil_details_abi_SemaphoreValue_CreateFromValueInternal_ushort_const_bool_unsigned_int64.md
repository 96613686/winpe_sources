# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008b74`
- end: `0x180008da5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008798`

## callees

- `0x180006580`
- `0x180008b74`
- `0x180009388`
- `0x18000a1b4`
- `0x18000aaf4`
- `0x18000b06c`
- `0x18000b07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008c3d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008ce3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008c3d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008ce3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d36`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
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
0x180008b74  mov     [rsp+arg_8], rbx
0x180008b79  push    rbp
0x180008b7a  push    rsi
0x180008b7b  push    rdi
0x180008b7c  push    r12
0x180008b7e  push    r13
0x180008b80  push    r14
0x180008b82  push    r15
0x180008b84  sub     rsp, 250h
0x180008b8b  mov     rax, cs:__security_cookie
0x180008b92  xor     rax, rsp
0x180008b95  mov     [rsp+288h+var_48], rax
0x180008b9d  mov     rax, 0C000000000000000h
0x180008ba7  mov     rsi, r9
0x180008baa  mov     r8, rdx
0x180008bad  mov     rbx, rcx
0x180008bb0  test    rax, r9
0x180008bb3  jnz     loc_180008D8C
0x180008bb9  xor     r12d, r12d
0x180008bbc  lea     rax, [rsp+288h+Name]
0x180008bc1  mov     r13d, 104h
0x180008bc7  mov     ecx, 7FFFFFFEh
0x180008bcc  mov     edx, r13d
0x180008bcf  lea     ebp, [r12+1]
0x180008bd4  test    rcx, rcx
0x180008bd7  jz      short loc_180008BF7
0x180008bd9  movzx   r9d, word ptr [r8]
0x180008bdd  test    r9w, r9w
0x180008be1  jz      short loc_180008BF7
0x180008be3  mov     [rax], r9w
0x180008be7  add     r8, 2
0x180008beb  add     rax, 2
0x180008bef  sub     rcx, rbp
0x180008bf2  sub     rdx, rbp
0x180008bf5  jnz     short loc_180008BD4
0x180008bf7  test    rdx, rdx
0x180008bfa  lea     rcx, [rax-2]
0x180008bfe  lea     r8, aP0; "_p0"
0x180008c05  mov     rdx, r13; unsigned __int64
0x180008c08  cmovnz  rcx, rax
0x180008c0c  mov     [rcx], r12w
0x180008c10  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180008c15  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c1a  mov     edx, esi
0x180008c1c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008c24  and     edx, 7FFFFFFFh; lInitialCount
0x180008c2a  mov     [rsp+288h+dwFlags], r12d; int
0x180008c2f  mov     r8d, ebp
0x180008c32  lea     r9, [rsp+288h+Name]; lpName
0x180008c37  cmova   r8d, edx; lMaximumCount
0x180008c3b  xor     ecx, ecx; lpSemaphoreAttributes
0x180008c3d  call    cs:__imp_CreateSemaphoreExW
0x180008c43  mov     r15, rax
0x180008c46  test    rax, rax
0x180008c49  jnz     short loc_180008C79
0x180008c4b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c50  mov     edi, eax
0x180008c52  test    eax, eax
0x180008c54  jns     short loc_180008CAD
0x180008c56  mov     rcx, [rsp+288h]; this
0x180008c5e  lea     r8, aWil; "wil"
0x180008c65  mov     r9d, eax; char *
0x180008c68  mov     edx, 8Bh; void *
0x180008c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c72  mov     eax, edi
0x180008c74  jmp     loc_180008D4E
0x180008c79  call    cs:__imp_GetLastError
0x180008c7f  mov     rdi, [rbx]
0x180008c82  test    rdi, rdi
0x180008c85  jz      short loc_180008CAA
0x180008c87  call    cs:__imp_GetLastError
0x180008c8d  mov     rcx, rdi; hObject
0x180008c90  mov     r14d, eax
0x180008c93  call    cs:__imp_CloseHandle
0x180008c99  test    eax, eax
0x180008c9b  jz      loc_180008D92
0x180008ca1  mov     ecx, r14d; dwErrCode
0x180008ca4  call    cs:__imp_SetLastError
0x180008caa  mov     [rbx], r15
0x180008cad  lea     r8, asc_18008EE50; "h"
0x180008cb4  shr     rsi, 1Fh
0x180008cb8  mov     rdx, r13; unsigned __int64
0x180008cbb  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180008cc0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008cc5  test    esi, esi
0x180008cc7  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008ccf  lea     r9, [rsp+288h+Name]; lpName
0x180008cd4  mov     [rsp+288h+dwFlags], r12d; int
0x180008cd9  cmovnz  ebp, esi
0x180008cdc  mov     edx, esi; lInitialCount
0x180008cde  mov     r8d, ebp; lMaximumCount
0x180008ce1  xor     ecx, ecx; lpSemaphoreAttributes
0x180008ce3  call    cs:__imp_CreateSemaphoreExW
0x180008ce9  mov     rbp, rax
0x180008cec  test    rax, rax
0x180008cef  jnz     short loc_180008D1C
0x180008cf1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008cf6  mov     ebx, eax
0x180008cf8  test    eax, eax
0x180008cfa  jns     short loc_180008D4C
0x180008cfc  mov     rcx, [rsp+288h]; this
0x180008d04  lea     r8, aWil; "wil"
0x180008d0b  mov     r9d, eax; char *
0x180008d0e  mov     edx, 90h; void *
0x180008d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d18  mov     eax, ebx
0x180008d1a  jmp     short loc_180008D4E
0x180008d1c  call    cs:__imp_GetLastError
0x180008d22  mov     rdi, [rbx+8]
0x180008d26  test    rdi, rdi
0x180008d29  jz      short loc_180008D48
0x180008d2b  call    cs:__imp_GetLastError
0x180008d31  mov     rcx, rdi; hObject
0x180008d34  mov     esi, eax
0x180008d36  call    cs:__imp_CloseHandle
0x180008d3c  test    eax, eax
0x180008d3e  jz      short loc_180008D79
0x180008d40  mov     ecx, esi; dwErrCode
0x180008d42  call    cs:__imp_SetLastError
0x180008d48  mov     [rbx+8], rbp
0x180008d4c  xor     eax, eax
0x180008d4e  mov     rcx, [rsp+288h+var_48]
0x180008d56  xor     rcx, rsp; StackCookie
0x180008d59  call    __security_check_cookie
0x180008d5e  mov     rbx, [rsp+288h+arg_8]
0x180008d66  add     rsp, 250h
0x180008d6d  pop     r15
0x180008d6f  pop     r14
0x180008d71  pop     r13
0x180008d73  pop     r12
0x180008d75  pop     rdi
0x180008d76  pop     rsi
0x180008d77  pop     rbp
0x180008d78  retn
0x180008d79  mov     rcx, [rsp+288h]; this
0x180008d81  mov     edx, 0A0Bh; void *
0x180008d86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d8c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008d92  mov     rcx, [rsp+288h]; this
0x180008d9a  mov     edx, 0A0Bh; void *
0x180008d9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

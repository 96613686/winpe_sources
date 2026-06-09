# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004d74`
- end: `0x180004f9e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004998`
- `0x180009954`

## callees

- `0x1800021d0`
- `0x180004d74`
- `0x1800058a8`
- `0x180006ba4`
- `0x1800074e4`
- `0x180007a2c`
- `0x180007a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004e38`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004edb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004e38`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f2e`

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
0x180004d74  mov     [rsp+arg_8], rbx
0x180004d79  mov     [rsp+arg_10], rbp
0x180004d7e  push    rsi
0x180004d7f  push    rdi
0x180004d80  push    r12
0x180004d82  push    r14
0x180004d84  push    r15
0x180004d86  sub     rsp, 250h
0x180004d8d  mov     rax, cs:__security_cookie
0x180004d94  xor     rax, rsp
0x180004d97  mov     [rsp+278h+var_38], rax
0x180004d9f  mov     rax, 0C000000000000000h
0x180004da9  mov     rbp, r9
0x180004dac  mov     r8, rdx
0x180004daf  mov     rbx, rcx
0x180004db2  test    rax, r9
0x180004db5  jnz     loc_180004F85
0x180004dbb  xor     r12d, r12d
0x180004dbe  lea     rax, [rsp+278h+Name]
0x180004dc3  mov     ecx, 7FFFFFFEh
0x180004dc8  mov     edx, 104h
0x180004dcd  lea     esi, [r12+1]
0x180004dd2  test    rcx, rcx
0x180004dd5  jz      short loc_180004DF5
0x180004dd7  movzx   r9d, word ptr [r8]
0x180004ddb  test    r9w, r9w
0x180004ddf  jz      short loc_180004DF5
0x180004de1  mov     [rax], r9w
0x180004de5  add     r8, 2
0x180004de9  add     rax, 2
0x180004ded  sub     rcx, rsi
0x180004df0  sub     rdx, rsi; unsigned __int64
0x180004df3  jnz     short loc_180004DD2
0x180004df5  test    rdx, rdx
0x180004df8  lea     rcx, [rax-2]
0x180004dfc  lea     r8, aP0; "_p0"
0x180004e03  cmovnz  rcx, rax
0x180004e07  mov     [rcx], r12w
0x180004e0b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004e10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004e15  mov     edx, ebp
0x180004e17  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004e1f  and     edx, 7FFFFFFFh; lInitialCount
0x180004e25  mov     [rsp+278h+dwFlags], r12d; int
0x180004e2a  mov     r8d, esi
0x180004e2d  lea     r9, [rsp+278h+Name]; lpName
0x180004e32  cmova   r8d, edx; lMaximumCount
0x180004e36  xor     ecx, ecx; lpSemaphoreAttributes
0x180004e38  call    cs:__imp_CreateSemaphoreExW
0x180004e3e  mov     r15, rax
0x180004e41  test    rax, rax
0x180004e44  jnz     short loc_180004E74
0x180004e46  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e4b  mov     edi, eax
0x180004e4d  test    eax, eax
0x180004e4f  jns     short loc_180004EA8
0x180004e51  mov     rcx, [rsp+278h]; this
0x180004e59  lea     r8, aWil; "wil"
0x180004e60  mov     r9d, eax; char *
0x180004e63  mov     edx, 8Bh; void *
0x180004e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e6d  mov     eax, edi
0x180004e6f  jmp     loc_180004F46
0x180004e74  call    cs:__imp_GetLastError
0x180004e7a  mov     rdi, [rbx]
0x180004e7d  test    rdi, rdi
0x180004e80  jz      short loc_180004EA5
0x180004e82  call    cs:__imp_GetLastError
0x180004e88  mov     rcx, rdi; hObject
0x180004e8b  mov     r14d, eax
0x180004e8e  call    cs:__imp_CloseHandle
0x180004e94  test    eax, eax
0x180004e96  jz      loc_180004F8B
0x180004e9c  mov     ecx, r14d; dwErrCode
0x180004e9f  call    cs:__imp_SetLastError
0x180004ea5  mov     [rbx], r15
0x180004ea8  lea     r8, asc_180037770; "h"
0x180004eaf  shr     rbp, 1Fh
0x180004eb3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004eb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004ebd  test    ebp, ebp
0x180004ebf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004ec7  lea     r9, [rsp+278h+Name]; lpName
0x180004ecc  mov     [rsp+278h+dwFlags], r12d; int
0x180004ed1  cmovnz  esi, ebp
0x180004ed4  mov     edx, ebp; lInitialCount
0x180004ed6  mov     r8d, esi; lMaximumCount
0x180004ed9  xor     ecx, ecx; lpSemaphoreAttributes
0x180004edb  call    cs:__imp_CreateSemaphoreExW
0x180004ee1  mov     rsi, rax
0x180004ee4  test    rax, rax
0x180004ee7  jnz     short loc_180004F14
0x180004ee9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004eee  mov     ebx, eax
0x180004ef0  test    eax, eax
0x180004ef2  jns     short loc_180004F44
0x180004ef4  mov     rcx, [rsp+278h]; this
0x180004efc  lea     r8, aWil; "wil"
0x180004f03  mov     r9d, eax; char *
0x180004f06  mov     edx, 90h; void *
0x180004f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f10  mov     eax, ebx
0x180004f12  jmp     short loc_180004F46
0x180004f14  call    cs:__imp_GetLastError
0x180004f1a  mov     rdi, [rbx+8]
0x180004f1e  test    rdi, rdi
0x180004f21  jz      short loc_180004F40
0x180004f23  call    cs:__imp_GetLastError
0x180004f29  mov     rcx, rdi; hObject
0x180004f2c  mov     ebp, eax
0x180004f2e  call    cs:__imp_CloseHandle
0x180004f34  test    eax, eax
0x180004f36  jz      short loc_180004F72
0x180004f38  mov     ecx, ebp; dwErrCode
0x180004f3a  call    cs:__imp_SetLastError
0x180004f40  mov     [rbx+8], rsi
0x180004f44  xor     eax, eax
0x180004f46  mov     rcx, [rsp+278h+var_38]
0x180004f4e  xor     rcx, rsp; StackCookie
0x180004f51  call    __security_check_cookie
0x180004f56  lea     r11, [rsp+278h+var_28]
0x180004f5e  mov     rbx, [r11+38h]
0x180004f62  mov     rbp, [r11+40h]
0x180004f66  mov     rsp, r11
0x180004f69  pop     r15
0x180004f6b  pop     r14
0x180004f6d  pop     r12
0x180004f6f  pop     rdi
0x180004f70  pop     rsi
0x180004f71  retn
0x180004f72  mov     rcx, [rsp+278h]; this
0x180004f7a  mov     edx, 0A0Bh; void *
0x180004f7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f85  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004f8b  mov     rcx, [rsp+278h]; this
0x180004f93  mov     edx, 0A0Bh; void *
0x180004f98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

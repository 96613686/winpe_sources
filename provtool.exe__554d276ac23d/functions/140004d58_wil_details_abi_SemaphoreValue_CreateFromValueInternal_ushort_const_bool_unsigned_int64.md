# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004d58`
- end: `0x140004f82`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003de0`

## callees

- `0x140004d58`
- `0x140005528`
- `0x140007734`
- `0x140008084`
- `0x1400087f4`
- `0x140008804`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e1c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004ebf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e1c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004ebf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f12`

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
0x140004d58  mov     [rsp+arg_8], rbx
0x140004d5d  mov     [rsp+arg_10], rbp
0x140004d62  push    rsi
0x140004d63  push    rdi
0x140004d64  push    r12
0x140004d66  push    r14
0x140004d68  push    r15
0x140004d6a  sub     rsp, 250h
0x140004d71  mov     rax, cs:__security_cookie
0x140004d78  xor     rax, rsp
0x140004d7b  mov     [rsp+278h+var_38], rax
0x140004d83  mov     rax, 0C000000000000000h
0x140004d8d  mov     rbp, r9
0x140004d90  mov     r8, rdx
0x140004d93  mov     rbx, rcx
0x140004d96  test    rax, r9
0x140004d99  jnz     loc_140004F69
0x140004d9f  xor     r12d, r12d
0x140004da2  lea     rax, [rsp+278h+Name]
0x140004da7  mov     ecx, 7FFFFFFEh
0x140004dac  mov     edx, 104h
0x140004db1  lea     esi, [r12+1]
0x140004db6  test    rcx, rcx
0x140004db9  jz      short loc_140004DD9
0x140004dbb  movzx   r9d, word ptr [r8]
0x140004dbf  test    r9w, r9w
0x140004dc3  jz      short loc_140004DD9
0x140004dc5  mov     [rax], r9w
0x140004dc9  add     r8, 2
0x140004dcd  add     rax, 2
0x140004dd1  sub     rcx, rsi
0x140004dd4  sub     rdx, rsi; unsigned __int64
0x140004dd7  jnz     short loc_140004DB6
0x140004dd9  test    rdx, rdx
0x140004ddc  lea     rcx, [rax-2]
0x140004de0  lea     r8, aP0; "_p0"
0x140004de7  cmovnz  rcx, rax
0x140004deb  mov     [rcx], r12w
0x140004def  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004df4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004df9  mov     edx, ebp
0x140004dfb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004e03  and     edx, 7FFFFFFFh; lInitialCount
0x140004e09  mov     [rsp+278h+dwFlags], r12d; int
0x140004e0e  mov     r8d, esi
0x140004e11  lea     r9, [rsp+278h+Name]; lpName
0x140004e16  cmova   r8d, edx; lMaximumCount
0x140004e1a  xor     ecx, ecx; lpSemaphoreAttributes
0x140004e1c  call    cs:__imp_CreateSemaphoreExW
0x140004e22  mov     r15, rax
0x140004e25  test    rax, rax
0x140004e28  jnz     short loc_140004E58
0x140004e2a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004e2f  mov     edi, eax
0x140004e31  test    eax, eax
0x140004e33  jns     short loc_140004E8C
0x140004e35  mov     rcx, [rsp+278h]; this
0x140004e3d  lea     r8, aWil; "wil"
0x140004e44  mov     r9d, eax; char *
0x140004e47  mov     edx, 8Bh; void *
0x140004e4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e51  mov     eax, edi
0x140004e53  jmp     loc_140004F2A
0x140004e58  call    cs:__imp_GetLastError
0x140004e5e  mov     rdi, [rbx]
0x140004e61  test    rdi, rdi
0x140004e64  jz      short loc_140004E89
0x140004e66  call    cs:__imp_GetLastError
0x140004e6c  mov     rcx, rdi; hObject
0x140004e6f  mov     r14d, eax
0x140004e72  call    cs:__imp_CloseHandle
0x140004e78  test    eax, eax
0x140004e7a  jz      loc_140004F6F
0x140004e80  mov     ecx, r14d; dwErrCode
0x140004e83  call    cs:__imp_SetLastError
0x140004e89  mov     [rbx], r15
0x140004e8c  lea     r8, asc_140012120; "h"
0x140004e93  shr     rbp, 1Fh
0x140004e97  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004e9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004ea1  test    ebp, ebp
0x140004ea3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004eab  lea     r9, [rsp+278h+Name]; lpName
0x140004eb0  mov     [rsp+278h+dwFlags], r12d; int
0x140004eb5  cmovnz  esi, ebp
0x140004eb8  mov     edx, ebp; lInitialCount
0x140004eba  mov     r8d, esi; lMaximumCount
0x140004ebd  xor     ecx, ecx; lpSemaphoreAttributes
0x140004ebf  call    cs:__imp_CreateSemaphoreExW
0x140004ec5  mov     rsi, rax
0x140004ec8  test    rax, rax
0x140004ecb  jnz     short loc_140004EF8
0x140004ecd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004ed2  mov     ebx, eax
0x140004ed4  test    eax, eax
0x140004ed6  jns     short loc_140004F28
0x140004ed8  mov     rcx, [rsp+278h]; this
0x140004ee0  lea     r8, aWil; "wil"
0x140004ee7  mov     r9d, eax; char *
0x140004eea  mov     edx, 90h; void *
0x140004eef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ef4  mov     eax, ebx
0x140004ef6  jmp     short loc_140004F2A
0x140004ef8  call    cs:__imp_GetLastError
0x140004efe  mov     rdi, [rbx+8]
0x140004f02  test    rdi, rdi
0x140004f05  jz      short loc_140004F24
0x140004f07  call    cs:__imp_GetLastError
0x140004f0d  mov     rcx, rdi; hObject
0x140004f10  mov     ebp, eax
0x140004f12  call    cs:__imp_CloseHandle
0x140004f18  test    eax, eax
0x140004f1a  jz      short loc_140004F56
0x140004f1c  mov     ecx, ebp; dwErrCode
0x140004f1e  call    cs:__imp_SetLastError
0x140004f24  mov     [rbx+8], rsi
0x140004f28  xor     eax, eax
0x140004f2a  mov     rcx, [rsp+278h+var_38]
0x140004f32  xor     rcx, rsp; StackCookie
0x140004f35  call    __security_check_cookie
0x140004f3a  lea     r11, [rsp+278h+var_28]
0x140004f42  mov     rbx, [r11+38h]
0x140004f46  mov     rbp, [r11+40h]
0x140004f4a  mov     rsp, r11
0x140004f4d  pop     r15
0x140004f4f  pop     r14
0x140004f51  pop     r12
0x140004f53  pop     rdi
0x140004f54  pop     rsi
0x140004f55  retn
0x140004f56  mov     rcx, [rsp+278h]; this
0x140004f5e  mov     edx, 0A0Bh; void *
0x140004f63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f69  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004f6f  mov     rcx, [rsp+278h]; this
0x140004f77  mov     edx, 0A0Bh; void *
0x140004f7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

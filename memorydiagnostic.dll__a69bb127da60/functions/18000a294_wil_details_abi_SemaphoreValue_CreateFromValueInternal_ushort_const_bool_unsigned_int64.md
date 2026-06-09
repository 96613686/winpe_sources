# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a294`
- end: `0x18000a4be`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008cc8`
- `0x180009098`

## callees

- `0x180002e50`
- `0x18000a294`
- `0x18000d078`
- `0x1800109d4`
- `0x180013460`
- `0x1800155f4`
- `0x180015604`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000a3ae`
- `KERNEL32!CloseHandle` at `0x18000a44e`
- `KERNEL32!CloseHandle` at `0x18000a3ae`
- `KERNEL32!CloseHandle` at `0x18000a44e`
- `KERNEL32!GetLastError` at `0x18000a394`
- `KERNEL32!GetLastError` at `0x18000a3a2`
- `KERNEL32!GetLastError` at `0x18000a434`
- `KERNEL32!GetLastError` at `0x18000a443`
- `KERNEL32!GetLastError` at `0x18000a394`
- `KERNEL32!GetLastError` at `0x18000a3a2`
- `KERNEL32!GetLastError` at `0x18000a434`
- `KERNEL32!GetLastError` at `0x18000a443`
- `KERNEL32!SetLastError` at `0x18000a3bf`
- `KERNEL32!SetLastError` at `0x18000a45a`
- `KERNEL32!SetLastError` at `0x18000a3bf`
- `KERNEL32!SetLastError` at `0x18000a45a`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a358`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a3fb`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a358`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a3fb`

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
0x18000a294  mov     [rsp+arg_8], rbx
0x18000a299  mov     [rsp+arg_10], rbp
0x18000a29e  push    rsi
0x18000a29f  push    rdi
0x18000a2a0  push    r12
0x18000a2a2  push    r14
0x18000a2a4  push    r15
0x18000a2a6  sub     rsp, 250h
0x18000a2ad  mov     rax, cs:__security_cookie
0x18000a2b4  xor     rax, rsp
0x18000a2b7  mov     [rsp+278h+var_38], rax
0x18000a2bf  mov     rax, 0C000000000000000h
0x18000a2c9  mov     rbp, r9
0x18000a2cc  mov     r8, rdx
0x18000a2cf  mov     rbx, rcx
0x18000a2d2  test    rax, r9
0x18000a2d5  jnz     loc_18000A4A5
0x18000a2db  xor     r12d, r12d
0x18000a2de  lea     rax, [rsp+278h+Name]
0x18000a2e3  mov     ecx, 7FFFFFFEh
0x18000a2e8  mov     edx, 104h
0x18000a2ed  lea     esi, [r12+1]
0x18000a2f2  test    rcx, rcx
0x18000a2f5  jz      short loc_18000A315
0x18000a2f7  movzx   r9d, word ptr [r8]
0x18000a2fb  test    r9w, r9w
0x18000a2ff  jz      short loc_18000A315
0x18000a301  mov     [rax], r9w
0x18000a305  add     r8, 2
0x18000a309  add     rax, 2
0x18000a30d  sub     rcx, rsi
0x18000a310  sub     rdx, rsi; unsigned __int64
0x18000a313  jnz     short loc_18000A2F2
0x18000a315  test    rdx, rdx
0x18000a318  lea     rcx, [rax-2]
0x18000a31c  lea     r8, aP0; "_p0"
0x18000a323  cmovnz  rcx, rax
0x18000a327  mov     [rcx], r12w
0x18000a32b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a330  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a335  mov     edx, ebp
0x18000a337  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a33f  and     edx, 7FFFFFFFh; lInitialCount
0x18000a345  mov     [rsp+278h+dwFlags], r12d; int
0x18000a34a  mov     r8d, esi
0x18000a34d  lea     r9, [rsp+278h+Name]; lpName
0x18000a352  cmova   r8d, edx; lMaximumCount
0x18000a356  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a358  call    cs:__imp_CreateSemaphoreExW
0x18000a35e  mov     r15, rax
0x18000a361  test    rax, rax
0x18000a364  jnz     short loc_18000A394
0x18000a366  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a36b  mov     edi, eax
0x18000a36d  test    eax, eax
0x18000a36f  jns     short loc_18000A3C8
0x18000a371  mov     rcx, [rsp+278h]; this
0x18000a379  lea     r8, aWil; "wil"
0x18000a380  mov     r9d, eax; char *
0x18000a383  mov     edx, 8Bh; void *
0x18000a388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a38d  mov     eax, edi
0x18000a38f  jmp     loc_18000A466
0x18000a394  call    cs:__imp_GetLastError
0x18000a39a  mov     rdi, [rbx]
0x18000a39d  test    rdi, rdi
0x18000a3a0  jz      short loc_18000A3C5
0x18000a3a2  call    cs:__imp_GetLastError
0x18000a3a8  mov     rcx, rdi; hObject
0x18000a3ab  mov     r14d, eax
0x18000a3ae  call    cs:__imp_CloseHandle
0x18000a3b4  test    eax, eax
0x18000a3b6  jz      loc_18000A4AB
0x18000a3bc  mov     ecx, r14d; dwErrCode
0x18000a3bf  call    cs:__imp_SetLastError
0x18000a3c5  mov     [rbx], r15
0x18000a3c8  lea     r8, asc_1800255B8; "h"
0x18000a3cf  shr     rbp, 1Fh
0x18000a3d3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a3d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3dd  test    ebp, ebp
0x18000a3df  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a3e7  lea     r9, [rsp+278h+Name]; lpName
0x18000a3ec  mov     [rsp+278h+dwFlags], r12d; int
0x18000a3f1  cmovnz  esi, ebp
0x18000a3f4  mov     edx, ebp; lInitialCount
0x18000a3f6  mov     r8d, esi; lMaximumCount
0x18000a3f9  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a3fb  call    cs:__imp_CreateSemaphoreExW
0x18000a401  mov     rsi, rax
0x18000a404  test    rax, rax
0x18000a407  jnz     short loc_18000A434
0x18000a409  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a40e  mov     ebx, eax
0x18000a410  test    eax, eax
0x18000a412  jns     short loc_18000A464
0x18000a414  mov     rcx, [rsp+278h]; this
0x18000a41c  lea     r8, aWil; "wil"
0x18000a423  mov     r9d, eax; char *
0x18000a426  mov     edx, 90h; void *
0x18000a42b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a430  mov     eax, ebx
0x18000a432  jmp     short loc_18000A466
0x18000a434  call    cs:__imp_GetLastError
0x18000a43a  mov     rdi, [rbx+8]
0x18000a43e  test    rdi, rdi
0x18000a441  jz      short loc_18000A460
0x18000a443  call    cs:__imp_GetLastError
0x18000a449  mov     rcx, rdi; hObject
0x18000a44c  mov     ebp, eax
0x18000a44e  call    cs:__imp_CloseHandle
0x18000a454  test    eax, eax
0x18000a456  jz      short loc_18000A492
0x18000a458  mov     ecx, ebp; dwErrCode
0x18000a45a  call    cs:__imp_SetLastError
0x18000a460  mov     [rbx+8], rsi
0x18000a464  xor     eax, eax
0x18000a466  mov     rcx, [rsp+278h+var_38]
0x18000a46e  xor     rcx, rsp; StackCookie
0x18000a471  call    __security_check_cookie
0x18000a476  lea     r11, [rsp+278h+var_28]
0x18000a47e  mov     rbx, [r11+38h]
0x18000a482  mov     rbp, [r11+40h]
0x18000a486  mov     rsp, r11
0x18000a489  pop     r15
0x18000a48b  pop     r14
0x18000a48d  pop     r12
0x18000a48f  pop     rdi
0x18000a490  pop     rsi
0x18000a491  retn
0x18000a492  mov     rcx, [rsp+278h]; this
0x18000a49a  mov     edx, 0A0Bh; void *
0x18000a49f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a4ab  mov     rcx, [rsp+278h]; this
0x18000a4b3  mov     edx, 0A0Bh; void *
0x18000a4b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

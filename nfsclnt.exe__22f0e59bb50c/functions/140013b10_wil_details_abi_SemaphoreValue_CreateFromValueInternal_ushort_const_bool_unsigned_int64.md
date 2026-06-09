# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140013b10`
- end: `0x140013d1d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14001339c`
- `0x140013740`

## callees

- `0x140013b10`
- `0x140014898`
- `0x140016720`
- `0x140016b40`
- `0x1400176cc`
- `0x1400176dc`
- `0x140018350`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140013bd4`
- `KERNEL32!CreateSemaphoreExW` at `0x140013c70`
- `KERNEL32!CreateSemaphoreExW` at `0x140013bd4`
- `KERNEL32!CreateSemaphoreExW` at `0x140013c70`
- `KERNEL32!GetLastError` at `0x140013c09`
- `KERNEL32!GetLastError` at `0x140013c17`
- `KERNEL32!GetLastError` at `0x140013c93`
- `KERNEL32!GetLastError` at `0x140013ca2`
- `KERNEL32!GetLastError` at `0x140013c09`
- `KERNEL32!GetLastError` at `0x140013c17`
- `KERNEL32!GetLastError` at `0x140013c93`
- `KERNEL32!GetLastError` at `0x140013ca2`
- `KERNEL32!CloseHandle` at `0x140013c23`
- `KERNEL32!CloseHandle` at `0x140013cad`
- `KERNEL32!CloseHandle` at `0x140013c23`
- `KERNEL32!CloseHandle` at `0x140013cad`
- `KERNEL32!SetLastError` at `0x140013c34`
- `KERNEL32!SetLastError` at `0x140013cb9`
- `KERNEL32!SetLastError` at `0x140013c34`
- `KERNEL32!SetLastError` at `0x140013cb9`

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
0x140013b10  mov     [rsp+arg_8], rbx
0x140013b15  mov     [rsp+arg_10], rbp
0x140013b1a  push    rsi
0x140013b1b  push    rdi
0x140013b1c  push    r12
0x140013b1e  push    r14
0x140013b20  push    r15
0x140013b22  sub     rsp, 250h
0x140013b29  mov     rax, cs:__security_cookie
0x140013b30  xor     rax, rsp
0x140013b33  mov     [rsp+278h+var_38], rax
0x140013b3b  mov     rax, 0C000000000000000h
0x140013b45  mov     rbp, r9
0x140013b48  mov     r8, rdx
0x140013b4b  mov     rdi, rcx
0x140013b4e  test    rax, r9
0x140013b51  jnz     loc_140013D04
0x140013b57  xor     r12d, r12d
0x140013b5a  lea     rax, [rsp+278h+Name]
0x140013b5f  mov     ecx, 7FFFFFFEh
0x140013b64  mov     edx, 104h
0x140013b69  lea     esi, [r12+1]
0x140013b6e  test    rcx, rcx
0x140013b71  jz      short loc_140013B91
0x140013b73  movzx   r9d, word ptr [r8]
0x140013b77  test    r9w, r9w
0x140013b7b  jz      short loc_140013B91
0x140013b7d  mov     [rax], r9w
0x140013b81  add     r8, 2
0x140013b85  add     rax, 2
0x140013b89  sub     rcx, rsi
0x140013b8c  sub     rdx, rsi; unsigned __int64
0x140013b8f  jnz     short loc_140013B6E
0x140013b91  test    rdx, rdx
0x140013b94  lea     rcx, [rax-2]
0x140013b98  lea     r8, aP0; "_p0"
0x140013b9f  cmovnz  rcx, rax
0x140013ba3  mov     [rcx], r12w
0x140013ba7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140013bac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140013bb1  mov     edx, ebp
0x140013bb3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140013bbb  and     edx, 7FFFFFFFh; lInitialCount
0x140013bc1  mov     [rsp+278h+dwFlags], r12d; int
0x140013bc6  mov     r8d, esi
0x140013bc9  lea     r9, [rsp+278h+Name]; lpName
0x140013bce  cmova   r8d, edx; lMaximumCount
0x140013bd2  xor     ecx, ecx; lpSemaphoreAttributes
0x140013bd4  call    cs:__imp_CreateSemaphoreExW
0x140013bda  mov     r15, rax
0x140013bdd  test    rax, rax
0x140013be0  jnz     short loc_140013C09
0x140013be2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140013be7  mov     ebx, eax
0x140013be9  test    eax, eax
0x140013beb  jns     short loc_140013C3D
0x140013bed  mov     edx, 8Bh; void *
0x140013bf2  mov     rcx, [rsp+278h]; this
0x140013bfa  mov     r9d, ebx; char *
0x140013bfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013c02  mov     eax, ebx
0x140013c04  jmp     loc_140013CC5
0x140013c09  call    cs:__imp_GetLastError
0x140013c0f  mov     rbx, [rdi]
0x140013c12  test    rbx, rbx
0x140013c15  jz      short loc_140013C3A
0x140013c17  call    cs:__imp_GetLastError
0x140013c1d  mov     rcx, rbx; hObject
0x140013c20  mov     r14d, eax
0x140013c23  call    cs:__imp_CloseHandle
0x140013c29  test    eax, eax
0x140013c2b  jz      loc_140013D0A
0x140013c31  mov     ecx, r14d; dwErrCode
0x140013c34  call    cs:__imp_SetLastError
0x140013c3a  mov     [rdi], r15
0x140013c3d  lea     r8, asc_14001CC88; "h"
0x140013c44  shr     rbp, 1Fh
0x140013c48  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140013c4d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140013c52  test    ebp, ebp
0x140013c54  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140013c5c  lea     r9, [rsp+278h+Name]; lpName
0x140013c61  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140013c66  cmovnz  esi, ebp
0x140013c69  mov     edx, ebp; lInitialCount
0x140013c6b  mov     r8d, esi; lMaximumCount
0x140013c6e  xor     ecx, ecx; lpSemaphoreAttributes
0x140013c70  call    cs:__imp_CreateSemaphoreExW
0x140013c76  mov     rsi, rax
0x140013c79  test    rax, rax
0x140013c7c  jnz     short loc_140013C93
0x140013c7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140013c83  mov     ebx, eax
0x140013c85  test    eax, eax
0x140013c87  jns     short loc_140013CC3
0x140013c89  mov     edx, 90h
0x140013c8e  jmp     loc_140013BF2
0x140013c93  call    cs:__imp_GetLastError
0x140013c99  mov     rbx, [rdi+8]
0x140013c9d  test    rbx, rbx
0x140013ca0  jz      short loc_140013CBF
0x140013ca2  call    cs:__imp_GetLastError
0x140013ca8  mov     rcx, rbx; hObject
0x140013cab  mov     ebp, eax
0x140013cad  call    cs:__imp_CloseHandle
0x140013cb3  test    eax, eax
0x140013cb5  jz      short loc_140013CF1
0x140013cb7  mov     ecx, ebp; dwErrCode
0x140013cb9  call    cs:__imp_SetLastError
0x140013cbf  mov     [rdi+8], rsi
0x140013cc3  xor     eax, eax
0x140013cc5  mov     rcx, [rsp+278h+var_38]
0x140013ccd  xor     rcx, rsp; StackCookie
0x140013cd0  call    __security_check_cookie
0x140013cd5  lea     r11, [rsp+278h+var_28]
0x140013cdd  mov     rbx, [r11+38h]
0x140013ce1  mov     rbp, [r11+40h]
0x140013ce5  mov     rsp, r11
0x140013ce8  pop     r15
0x140013cea  pop     r14
0x140013cec  pop     r12
0x140013cee  pop     rdi
0x140013cef  pop     rsi
0x140013cf0  retn
0x140013cf1  mov     rcx, [rsp+278h]; this
0x140013cf9  mov     edx, 0A0Bh; void *
0x140013cfe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013d04  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140013d0a  mov     rcx, [rsp+278h]; this
0x140013d12  mov     edx, 0A0Bh; void *
0x140013d17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

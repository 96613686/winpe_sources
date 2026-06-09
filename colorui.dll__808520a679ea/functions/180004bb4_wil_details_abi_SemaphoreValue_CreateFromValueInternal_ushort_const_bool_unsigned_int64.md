# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004bb4`
- end: `0x180004dde`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003828`
- `0x180003bf8`

## callees

- `0x180004bb4`
- `0x180006014`
- `0x1800099f8`
- `0x180009ed0`
- `0x18000b3f4`
- `0x18000b404`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004cb4`
- `KERNEL32!GetLastError` at `0x180004cc2`
- `KERNEL32!GetLastError` at `0x180004d54`
- `KERNEL32!GetLastError` at `0x180004d63`
- `KERNEL32!GetLastError` at `0x180004cb4`
- `KERNEL32!GetLastError` at `0x180004cc2`
- `KERNEL32!GetLastError` at `0x180004d54`
- `KERNEL32!GetLastError` at `0x180004d63`
- `KERNEL32!CloseHandle` at `0x180004cce`
- `KERNEL32!CloseHandle` at `0x180004d6e`
- `KERNEL32!CloseHandle` at `0x180004cce`
- `KERNEL32!CloseHandle` at `0x180004d6e`
- `KERNEL32!SetLastError` at `0x180004cdf`
- `KERNEL32!SetLastError` at `0x180004d7a`
- `KERNEL32!SetLastError` at `0x180004cdf`
- `KERNEL32!SetLastError` at `0x180004d7a`
- `KERNEL32!CreateSemaphoreExW` at `0x180004c78`
- `KERNEL32!CreateSemaphoreExW` at `0x180004d1b`
- `KERNEL32!CreateSemaphoreExW` at `0x180004c78`
- `KERNEL32!CreateSemaphoreExW` at `0x180004d1b`

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
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  __int64 v16; // rdx
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
  StringCbCatW(Name, v9, L"_p0");
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
  StringCbCatW(Name, v16, L"h");
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
0x180004bb4  mov     [rsp+arg_8], rbx
0x180004bb9  mov     [rsp+arg_10], rbp
0x180004bbe  push    rsi
0x180004bbf  push    rdi
0x180004bc0  push    r12
0x180004bc2  push    r14
0x180004bc4  push    r15
0x180004bc6  sub     rsp, 250h
0x180004bcd  mov     rax, cs:__security_cookie
0x180004bd4  xor     rax, rsp
0x180004bd7  mov     [rsp+278h+var_38], rax
0x180004bdf  mov     rax, 0C000000000000000h
0x180004be9  mov     rbp, r9
0x180004bec  mov     r8, rdx
0x180004bef  mov     rbx, rcx
0x180004bf2  test    rax, r9
0x180004bf5  jnz     loc_180004DC5
0x180004bfb  xor     r12d, r12d
0x180004bfe  lea     rax, [rsp+278h+Name]
0x180004c03  mov     ecx, 7FFFFFFEh
0x180004c08  mov     edx, 104h
0x180004c0d  lea     esi, [r12+1]
0x180004c12  test    rcx, rcx
0x180004c15  jz      short loc_180004C35
0x180004c17  movzx   r9d, word ptr [r8]
0x180004c1b  test    r9w, r9w
0x180004c1f  jz      short loc_180004C35
0x180004c21  mov     [rax], r9w
0x180004c25  add     r8, 2
0x180004c29  add     rax, 2
0x180004c2d  sub     rcx, rsi
0x180004c30  sub     rdx, rsi; unsigned __int64
0x180004c33  jnz     short loc_180004C12
0x180004c35  test    rdx, rdx
0x180004c38  lea     rcx, [rax-2]
0x180004c3c  lea     r8, aP0; "_p0"
0x180004c43  cmovnz  rcx, rax
0x180004c47  mov     [rcx], r12w
0x180004c4b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004c50  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180004c55  mov     edx, ebp
0x180004c57  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004c5f  and     edx, 7FFFFFFFh; lInitialCount
0x180004c65  mov     [rsp+278h+dwFlags], r12d; int
0x180004c6a  mov     r8d, esi
0x180004c6d  lea     r9, [rsp+278h+Name]; lpName
0x180004c72  cmova   r8d, edx; lMaximumCount
0x180004c76  xor     ecx, ecx; lpSemaphoreAttributes
0x180004c78  call    cs:__imp_CreateSemaphoreExW
0x180004c7e  mov     r15, rax
0x180004c81  test    rax, rax
0x180004c84  jnz     short loc_180004CB4
0x180004c86  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c8b  mov     edi, eax
0x180004c8d  test    eax, eax
0x180004c8f  jns     short loc_180004CE8
0x180004c91  mov     rcx, [rsp+278h]; this
0x180004c99  lea     r8, aWil; "wil"
0x180004ca0  mov     r9d, eax; char *
0x180004ca3  mov     edx, 8Bh; void *
0x180004ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cad  mov     eax, edi
0x180004caf  jmp     loc_180004D86
0x180004cb4  call    cs:__imp_GetLastError
0x180004cba  mov     rdi, [rbx]
0x180004cbd  test    rdi, rdi
0x180004cc0  jz      short loc_180004CE5
0x180004cc2  call    cs:__imp_GetLastError
0x180004cc8  mov     rcx, rdi; hObject
0x180004ccb  mov     r14d, eax
0x180004cce  call    cs:__imp_CloseHandle
0x180004cd4  test    eax, eax
0x180004cd6  jz      loc_180004DCB
0x180004cdc  mov     ecx, r14d; dwErrCode
0x180004cdf  call    cs:__imp_SetLastError
0x180004ce5  mov     [rbx], r15
0x180004ce8  lea     r8, asc_18001C560; "h"
0x180004cef  shr     rbp, 1Fh
0x180004cf3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004cf8  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180004cfd  test    ebp, ebp
0x180004cff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004d07  lea     r9, [rsp+278h+Name]; lpName
0x180004d0c  mov     [rsp+278h+dwFlags], r12d; int
0x180004d11  cmovnz  esi, ebp
0x180004d14  mov     edx, ebp; lInitialCount
0x180004d16  mov     r8d, esi; lMaximumCount
0x180004d19  xor     ecx, ecx; lpSemaphoreAttributes
0x180004d1b  call    cs:__imp_CreateSemaphoreExW
0x180004d21  mov     rsi, rax
0x180004d24  test    rax, rax
0x180004d27  jnz     short loc_180004D54
0x180004d29  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d2e  mov     ebx, eax
0x180004d30  test    eax, eax
0x180004d32  jns     short loc_180004D84
0x180004d34  mov     rcx, [rsp+278h]; this
0x180004d3c  lea     r8, aWil; "wil"
0x180004d43  mov     r9d, eax; char *
0x180004d46  mov     edx, 90h; void *
0x180004d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d50  mov     eax, ebx
0x180004d52  jmp     short loc_180004D86
0x180004d54  call    cs:__imp_GetLastError
0x180004d5a  mov     rdi, [rbx+8]
0x180004d5e  test    rdi, rdi
0x180004d61  jz      short loc_180004D80
0x180004d63  call    cs:__imp_GetLastError
0x180004d69  mov     rcx, rdi; hObject
0x180004d6c  mov     ebp, eax
0x180004d6e  call    cs:__imp_CloseHandle
0x180004d74  test    eax, eax
0x180004d76  jz      short loc_180004DB2
0x180004d78  mov     ecx, ebp; dwErrCode
0x180004d7a  call    cs:__imp_SetLastError
0x180004d80  mov     [rbx+8], rsi
0x180004d84  xor     eax, eax
0x180004d86  mov     rcx, [rsp+278h+var_38]
0x180004d8e  xor     rcx, rsp; StackCookie
0x180004d91  call    __security_check_cookie
0x180004d96  lea     r11, [rsp+278h+var_28]
0x180004d9e  mov     rbx, [r11+38h]
0x180004da2  mov     rbp, [r11+40h]
0x180004da6  mov     rsp, r11
0x180004da9  pop     r15
0x180004dab  pop     r14
0x180004dad  pop     r12
0x180004daf  pop     rdi
0x180004db0  pop     rsi
0x180004db1  retn
0x180004db2  mov     rcx, [rsp+278h]; this
0x180004dba  mov     edx, 0A0Bh; void *
0x180004dbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004dc5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004dcb  mov     rcx, [rsp+278h]; this
0x180004dd3  mov     edx, 0A0Bh; void *
0x180004dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

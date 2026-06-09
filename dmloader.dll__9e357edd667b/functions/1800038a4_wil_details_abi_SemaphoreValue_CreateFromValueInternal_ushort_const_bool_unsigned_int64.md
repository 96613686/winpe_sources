# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800038a4`
- end: `0x180003ab1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003114`
- `0x1800034b8`

## callees

- `0x1800015d0`
- `0x1800038a4`
- `0x1800047e8`
- `0x1800067e0`
- `0x180006bfc`
- `0x18000782c`
- `0x18000783c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003968`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a04`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003968`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000399d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000399d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a41`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x1800038a4  mov     [rsp+arg_8], rbx
0x1800038a9  mov     [rsp+arg_10], rbp
0x1800038ae  push    rsi
0x1800038af  push    rdi
0x1800038b0  push    r12
0x1800038b2  push    r14
0x1800038b4  push    r15
0x1800038b6  sub     rsp, 250h
0x1800038bd  mov     rax, cs:__security_cookie
0x1800038c4  xor     rax, rsp
0x1800038c7  mov     [rsp+278h+var_38], rax
0x1800038cf  mov     rax, 0C000000000000000h
0x1800038d9  mov     rbp, r9
0x1800038dc  mov     r8, rdx
0x1800038df  mov     rdi, rcx
0x1800038e2  test    rax, r9
0x1800038e5  jnz     loc_180003A98
0x1800038eb  xor     r12d, r12d
0x1800038ee  lea     rax, [rsp+278h+Name]
0x1800038f3  mov     ecx, 7FFFFFFEh
0x1800038f8  mov     edx, 104h
0x1800038fd  lea     esi, [r12+1]
0x180003902  test    rcx, rcx
0x180003905  jz      short loc_180003925
0x180003907  movzx   r9d, word ptr [r8]
0x18000390b  test    r9w, r9w
0x18000390f  jz      short loc_180003925
0x180003911  mov     [rax], r9w
0x180003915  add     r8, 2
0x180003919  add     rax, 2
0x18000391d  sub     rcx, rsi
0x180003920  sub     rdx, rsi; unsigned __int64
0x180003923  jnz     short loc_180003902
0x180003925  test    rdx, rdx
0x180003928  lea     rcx, [rax-2]
0x18000392c  lea     r8, aP0; "_p0"
0x180003933  cmovnz  rcx, rax
0x180003937  mov     [rcx], r12w
0x18000393b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003940  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003945  mov     edx, ebp
0x180003947  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000394f  and     edx, 7FFFFFFFh; lInitialCount
0x180003955  mov     [rsp+278h+dwFlags], r12d; int
0x18000395a  mov     r8d, esi
0x18000395d  lea     r9, [rsp+278h+Name]; lpName
0x180003962  cmova   r8d, edx; lMaximumCount
0x180003966  xor     ecx, ecx; lpSemaphoreAttributes
0x180003968  call    cs:__imp_CreateSemaphoreExW
0x18000396e  mov     r15, rax
0x180003971  test    rax, rax
0x180003974  jnz     short loc_18000399D
0x180003976  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000397b  mov     ebx, eax
0x18000397d  test    eax, eax
0x18000397f  jns     short loc_1800039D1
0x180003981  mov     edx, 8Bh; void *
0x180003986  mov     rcx, [rsp+278h]; this
0x18000398e  mov     r9d, ebx; char *
0x180003991  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003996  mov     eax, ebx
0x180003998  jmp     loc_180003A59
0x18000399d  call    cs:__imp_GetLastError
0x1800039a3  mov     rbx, [rdi]
0x1800039a6  test    rbx, rbx
0x1800039a9  jz      short loc_1800039CE
0x1800039ab  call    cs:__imp_GetLastError
0x1800039b1  mov     rcx, rbx; hObject
0x1800039b4  mov     r14d, eax
0x1800039b7  call    cs:__imp_CloseHandle
0x1800039bd  test    eax, eax
0x1800039bf  jz      loc_180003A9E
0x1800039c5  mov     ecx, r14d; dwErrCode
0x1800039c8  call    cs:__imp_SetLastError
0x1800039ce  mov     [rdi], r15
0x1800039d1  lea     r8, asc_180011FC0; "h"
0x1800039d8  shr     rbp, 1Fh
0x1800039dc  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800039e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800039e6  test    ebp, ebp
0x1800039e8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800039f0  lea     r9, [rsp+278h+Name]; lpName
0x1800039f5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800039fa  cmovnz  esi, ebp
0x1800039fd  mov     edx, ebp; lInitialCount
0x1800039ff  mov     r8d, esi; lMaximumCount
0x180003a02  xor     ecx, ecx; lpSemaphoreAttributes
0x180003a04  call    cs:__imp_CreateSemaphoreExW
0x180003a0a  mov     rsi, rax
0x180003a0d  test    rax, rax
0x180003a10  jnz     short loc_180003A27
0x180003a12  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a17  mov     ebx, eax
0x180003a19  test    eax, eax
0x180003a1b  jns     short loc_180003A57
0x180003a1d  mov     edx, 90h
0x180003a22  jmp     loc_180003986
0x180003a27  call    cs:__imp_GetLastError
0x180003a2d  mov     rbx, [rdi+8]
0x180003a31  test    rbx, rbx
0x180003a34  jz      short loc_180003A53
0x180003a36  call    cs:__imp_GetLastError
0x180003a3c  mov     rcx, rbx; hObject
0x180003a3f  mov     ebp, eax
0x180003a41  call    cs:__imp_CloseHandle
0x180003a47  test    eax, eax
0x180003a49  jz      short loc_180003A85
0x180003a4b  mov     ecx, ebp; dwErrCode
0x180003a4d  call    cs:__imp_SetLastError
0x180003a53  mov     [rdi+8], rsi
0x180003a57  xor     eax, eax
0x180003a59  mov     rcx, [rsp+278h+var_38]
0x180003a61  xor     rcx, rsp; StackCookie
0x180003a64  call    __security_check_cookie
0x180003a69  lea     r11, [rsp+278h+var_28]
0x180003a71  mov     rbx, [r11+38h]
0x180003a75  mov     rbp, [r11+40h]
0x180003a79  mov     rsp, r11
0x180003a7c  pop     r15
0x180003a7e  pop     r14
0x180003a80  pop     r12
0x180003a82  pop     rdi
0x180003a83  pop     rsi
0x180003a84  retn
0x180003a85  mov     rcx, [rsp+278h]; this
0x180003a8d  mov     edx, 0A0Bh; void *
0x180003a92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a98  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a9e  mov     rcx, [rsp+278h]; this
0x180003aa6  mov     edx, 0A0Bh; void *
0x180003aab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

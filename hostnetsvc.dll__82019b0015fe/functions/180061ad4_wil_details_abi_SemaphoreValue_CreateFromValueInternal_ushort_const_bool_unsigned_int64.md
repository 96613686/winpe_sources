# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180061ad4`
- end: `0x180061d05`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800616f8`
- `0x180070068`

## callees

- `0x18005f0c0`
- `0x180061ad4`
- `0x180062418`
- `0x180063094`
- `0x1800639d4`
- `0x180064008`
- `0x180064018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180061b9d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180061c43`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180061b9d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180061c43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061bf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061bf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061c96`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
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
0x180061ad4  mov     [rsp+arg_8], rbx
0x180061ad9  push    rbp
0x180061ada  push    rsi
0x180061adb  push    rdi
0x180061adc  push    r12
0x180061ade  push    r13
0x180061ae0  push    r14
0x180061ae2  push    r15
0x180061ae4  sub     rsp, 250h
0x180061aeb  mov     rax, cs:__security_cookie
0x180061af2  xor     rax, rsp
0x180061af5  mov     [rsp+288h+var_48], rax
0x180061afd  mov     rax, 0C000000000000000h
0x180061b07  mov     rsi, r9
0x180061b0a  mov     r8, rdx
0x180061b0d  mov     rbx, rcx
0x180061b10  test    rax, r9
0x180061b13  jnz     loc_180061CEC
0x180061b19  xor     r12d, r12d
0x180061b1c  lea     rax, [rsp+288h+Name]
0x180061b21  mov     r13d, 104h
0x180061b27  mov     ecx, 7FFFFFFEh
0x180061b2c  mov     edx, r13d
0x180061b2f  lea     ebp, [r12+1]
0x180061b34  test    rcx, rcx
0x180061b37  jz      short loc_180061B57
0x180061b39  movzx   r9d, word ptr [r8]
0x180061b3d  test    r9w, r9w
0x180061b41  jz      short loc_180061B57
0x180061b43  mov     [rax], r9w
0x180061b47  add     r8, 2
0x180061b4b  add     rax, 2
0x180061b4f  sub     rcx, rbp
0x180061b52  sub     rdx, rbp
0x180061b55  jnz     short loc_180061B34
0x180061b57  test    rdx, rdx
0x180061b5a  lea     rcx, [rax-2]
0x180061b5e  lea     r8, aP0; "_p0"
0x180061b65  mov     rdx, r13; unsigned __int64
0x180061b68  cmovnz  rcx, rax
0x180061b6c  mov     [rcx], r12w
0x180061b70  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180061b75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180061b7a  mov     edx, esi
0x180061b7c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180061b84  and     edx, 7FFFFFFFh; lInitialCount
0x180061b8a  mov     [rsp+288h+dwFlags], r12d; int
0x180061b8f  mov     r8d, ebp
0x180061b92  lea     r9, [rsp+288h+Name]; lpName
0x180061b97  cmova   r8d, edx; lMaximumCount
0x180061b9b  xor     ecx, ecx; lpSemaphoreAttributes
0x180061b9d  call    cs:__imp_CreateSemaphoreExW
0x180061ba3  mov     r15, rax
0x180061ba6  test    rax, rax
0x180061ba9  jnz     short loc_180061BD9
0x180061bab  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180061bb0  mov     edi, eax
0x180061bb2  test    eax, eax
0x180061bb4  jns     short loc_180061C0D
0x180061bb6  mov     rcx, [rsp+288h]; this
0x180061bbe  lea     r8, aWil; "wil"
0x180061bc5  mov     r9d, eax; char *
0x180061bc8  mov     edx, 8Bh; void *
0x180061bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061bd2  mov     eax, edi
0x180061bd4  jmp     loc_180061CAE
0x180061bd9  call    cs:__imp_GetLastError
0x180061bdf  mov     rdi, [rbx]
0x180061be2  test    rdi, rdi
0x180061be5  jz      short loc_180061C0A
0x180061be7  call    cs:__imp_GetLastError
0x180061bed  mov     rcx, rdi; hObject
0x180061bf0  mov     r14d, eax
0x180061bf3  call    cs:__imp_CloseHandle
0x180061bf9  test    eax, eax
0x180061bfb  jz      loc_180061CF2
0x180061c01  mov     ecx, r14d; dwErrCode
0x180061c04  call    cs:__imp_SetLastError
0x180061c0a  mov     [rbx], r15
0x180061c0d  lea     r8, asc_1802E2990; "h"
0x180061c14  shr     rsi, 1Fh
0x180061c18  mov     rdx, r13; unsigned __int64
0x180061c1b  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180061c20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180061c25  test    esi, esi
0x180061c27  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180061c2f  lea     r9, [rsp+288h+Name]; lpName
0x180061c34  mov     [rsp+288h+dwFlags], r12d; int
0x180061c39  cmovnz  ebp, esi
0x180061c3c  mov     edx, esi; lInitialCount
0x180061c3e  mov     r8d, ebp; lMaximumCount
0x180061c41  xor     ecx, ecx; lpSemaphoreAttributes
0x180061c43  call    cs:__imp_CreateSemaphoreExW
0x180061c49  mov     rbp, rax
0x180061c4c  test    rax, rax
0x180061c4f  jnz     short loc_180061C7C
0x180061c51  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180061c56  mov     ebx, eax
0x180061c58  test    eax, eax
0x180061c5a  jns     short loc_180061CAC
0x180061c5c  mov     rcx, [rsp+288h]; this
0x180061c64  lea     r8, aWil; "wil"
0x180061c6b  mov     r9d, eax; char *
0x180061c6e  mov     edx, 90h; void *
0x180061c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061c78  mov     eax, ebx
0x180061c7a  jmp     short loc_180061CAE
0x180061c7c  call    cs:__imp_GetLastError
0x180061c82  mov     rdi, [rbx+8]
0x180061c86  test    rdi, rdi
0x180061c89  jz      short loc_180061CA8
0x180061c8b  call    cs:__imp_GetLastError
0x180061c91  mov     rcx, rdi; hObject
0x180061c94  mov     esi, eax
0x180061c96  call    cs:__imp_CloseHandle
0x180061c9c  test    eax, eax
0x180061c9e  jz      short loc_180061CD9
0x180061ca0  mov     ecx, esi; dwErrCode
0x180061ca2  call    cs:__imp_SetLastError
0x180061ca8  mov     [rbx+8], rbp
0x180061cac  xor     eax, eax
0x180061cae  mov     rcx, [rsp+288h+var_48]
0x180061cb6  xor     rcx, rsp; StackCookie
0x180061cb9  call    __security_check_cookie
0x180061cbe  mov     rbx, [rsp+288h+arg_8]
0x180061cc6  add     rsp, 250h
0x180061ccd  pop     r15
0x180061ccf  pop     r14
0x180061cd1  pop     r13
0x180061cd3  pop     r12
0x180061cd5  pop     rdi
0x180061cd6  pop     rsi
0x180061cd7  pop     rbp
0x180061cd8  retn
0x180061cd9  mov     rcx, [rsp+288h]; this
0x180061ce1  mov     edx, 0A0Bh; void *
0x180061ce6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061cec  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180061cf2  mov     rcx, [rsp+288h]; this
0x180061cfa  mov     edx, 0A0Bh; void *
0x180061cff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

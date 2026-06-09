# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006498`
- end: `0x1800066c9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005cc8`
- `0x18000609c`

## callees

- `0x1800024e0`
- `0x180006498`
- `0x180007308`
- `0x180009474`
- `0x180009ec4`
- `0x18000ad4c`
- `0x18000ad5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006561`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006607`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006561`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006666`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000659d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000664f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000659d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000664f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000665a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000665a`

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
0x180006498  mov     [rsp+arg_8], rbx
0x18000649d  push    rbp
0x18000649e  push    rsi
0x18000649f  push    rdi
0x1800064a0  push    r12
0x1800064a2  push    r13
0x1800064a4  push    r14
0x1800064a6  push    r15
0x1800064a8  sub     rsp, 250h
0x1800064af  mov     rax, cs:__security_cookie
0x1800064b6  xor     rax, rsp
0x1800064b9  mov     [rsp+288h+var_48], rax
0x1800064c1  mov     rax, 0C000000000000000h
0x1800064cb  mov     rsi, r9
0x1800064ce  mov     r8, rdx
0x1800064d1  mov     rbx, rcx
0x1800064d4  test    rax, r9
0x1800064d7  jnz     loc_1800066B0
0x1800064dd  xor     r12d, r12d
0x1800064e0  lea     rax, [rsp+288h+Name]
0x1800064e5  mov     r13d, 104h
0x1800064eb  mov     ecx, 7FFFFFFEh
0x1800064f0  mov     edx, r13d
0x1800064f3  lea     ebp, [r12+1]
0x1800064f8  test    rcx, rcx
0x1800064fb  jz      short loc_18000651B
0x1800064fd  movzx   r9d, word ptr [r8]
0x180006501  test    r9w, r9w
0x180006505  jz      short loc_18000651B
0x180006507  mov     [rax], r9w
0x18000650b  add     r8, 2
0x18000650f  add     rax, 2
0x180006513  sub     rcx, rbp
0x180006516  sub     rdx, rbp
0x180006519  jnz     short loc_1800064F8
0x18000651b  test    rdx, rdx
0x18000651e  lea     rcx, [rax-2]
0x180006522  lea     r8, aP0; "_p0"
0x180006529  mov     rdx, r13; unsigned __int64
0x18000652c  cmovnz  rcx, rax
0x180006530  mov     [rcx], r12w
0x180006534  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180006539  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000653e  mov     edx, esi
0x180006540  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006548  and     edx, 7FFFFFFFh; lInitialCount
0x18000654e  mov     [rsp+288h+dwFlags], r12d; int
0x180006553  mov     r8d, ebp
0x180006556  lea     r9, [rsp+288h+Name]; lpName
0x18000655b  cmova   r8d, edx; lMaximumCount
0x18000655f  xor     ecx, ecx; lpSemaphoreAttributes
0x180006561  call    cs:__imp_CreateSemaphoreExW
0x180006567  mov     r15, rax
0x18000656a  test    rax, rax
0x18000656d  jnz     short loc_18000659D
0x18000656f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006574  mov     edi, eax
0x180006576  test    eax, eax
0x180006578  jns     short loc_1800065D1
0x18000657a  mov     rcx, [rsp+288h]; this
0x180006582  lea     r8, aWil; "wil"
0x180006589  mov     r9d, eax; char *
0x18000658c  mov     edx, 8Bh; void *
0x180006591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006596  mov     eax, edi
0x180006598  jmp     loc_180006672
0x18000659d  call    cs:__imp_GetLastError
0x1800065a3  mov     rdi, [rbx]
0x1800065a6  test    rdi, rdi
0x1800065a9  jz      short loc_1800065CE
0x1800065ab  call    cs:__imp_GetLastError
0x1800065b1  mov     rcx, rdi; hObject
0x1800065b4  mov     r14d, eax
0x1800065b7  call    cs:__imp_CloseHandle
0x1800065bd  test    eax, eax
0x1800065bf  jz      loc_1800066B6
0x1800065c5  mov     ecx, r14d; dwErrCode
0x1800065c8  call    cs:__imp_SetLastError
0x1800065ce  mov     [rbx], r15
0x1800065d1  lea     r8, asc_180065A98; "h"
0x1800065d8  shr     rsi, 1Fh
0x1800065dc  mov     rdx, r13; unsigned __int64
0x1800065df  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800065e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065e9  test    esi, esi
0x1800065eb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800065f3  lea     r9, [rsp+288h+Name]; lpName
0x1800065f8  mov     [rsp+288h+dwFlags], r12d; int
0x1800065fd  cmovnz  ebp, esi
0x180006600  mov     edx, esi; lInitialCount
0x180006602  mov     r8d, ebp; lMaximumCount
0x180006605  xor     ecx, ecx; lpSemaphoreAttributes
0x180006607  call    cs:__imp_CreateSemaphoreExW
0x18000660d  mov     rbp, rax
0x180006610  test    rax, rax
0x180006613  jnz     short loc_180006640
0x180006615  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000661a  mov     ebx, eax
0x18000661c  test    eax, eax
0x18000661e  jns     short loc_180006670
0x180006620  mov     rcx, [rsp+288h]; this
0x180006628  lea     r8, aWil; "wil"
0x18000662f  mov     r9d, eax; char *
0x180006632  mov     edx, 90h; void *
0x180006637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000663c  mov     eax, ebx
0x18000663e  jmp     short loc_180006672
0x180006640  call    cs:__imp_GetLastError
0x180006646  mov     rdi, [rbx+8]
0x18000664a  test    rdi, rdi
0x18000664d  jz      short loc_18000666C
0x18000664f  call    cs:__imp_GetLastError
0x180006655  mov     rcx, rdi; hObject
0x180006658  mov     esi, eax
0x18000665a  call    cs:__imp_CloseHandle
0x180006660  test    eax, eax
0x180006662  jz      short loc_18000669D
0x180006664  mov     ecx, esi; dwErrCode
0x180006666  call    cs:__imp_SetLastError
0x18000666c  mov     [rbx+8], rbp
0x180006670  xor     eax, eax
0x180006672  mov     rcx, [rsp+288h+var_48]
0x18000667a  xor     rcx, rsp; StackCookie
0x18000667d  call    __security_check_cookie
0x180006682  mov     rbx, [rsp+288h+arg_8]
0x18000668a  add     rsp, 250h
0x180006691  pop     r15
0x180006693  pop     r14
0x180006695  pop     r13
0x180006697  pop     r12
0x180006699  pop     rdi
0x18000669a  pop     rsi
0x18000669b  pop     rbp
0x18000669c  retn
0x18000669d  mov     rcx, [rsp+288h]; this
0x1800066a5  mov     edx, 0A0Bh; void *
0x1800066aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800066b6  mov     rcx, [rsp+288h]; this
0x1800066be  mov     edx, 0A0Bh; void *
0x1800066c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006498`
- end: `0x1800066c2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800060c8`

## callees

- `0x180001500`
- `0x180006498`
- `0x180006d28`
- `0x180007b04`
- `0x1800083e0`
- `0x18000893c`
- `0x18000894c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000655c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800065ff`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000655c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800065ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000665e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006647`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006652`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006652`

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
0x180006498  mov     [rsp+arg_8], rbx
0x18000649d  mov     [rsp+arg_10], rbp
0x1800064a2  push    rsi
0x1800064a3  push    rdi
0x1800064a4  push    r12
0x1800064a6  push    r14
0x1800064a8  push    r15
0x1800064aa  sub     rsp, 250h
0x1800064b1  mov     rax, cs:__security_cookie
0x1800064b8  xor     rax, rsp
0x1800064bb  mov     [rsp+278h+var_38], rax
0x1800064c3  mov     rax, 0C000000000000000h
0x1800064cd  mov     rbp, r9
0x1800064d0  mov     r8, rdx
0x1800064d3  mov     rbx, rcx
0x1800064d6  test    rax, r9
0x1800064d9  jnz     loc_1800066A9
0x1800064df  xor     r12d, r12d
0x1800064e2  lea     rax, [rsp+278h+Name]
0x1800064e7  mov     ecx, 7FFFFFFEh
0x1800064ec  mov     edx, 104h
0x1800064f1  lea     esi, [r12+1]
0x1800064f6  test    rcx, rcx
0x1800064f9  jz      short loc_180006519
0x1800064fb  movzx   r9d, word ptr [r8]
0x1800064ff  test    r9w, r9w
0x180006503  jz      short loc_180006519
0x180006505  mov     [rax], r9w
0x180006509  add     r8, 2
0x18000650d  add     rax, 2
0x180006511  sub     rcx, rsi
0x180006514  sub     rdx, rsi; unsigned __int64
0x180006517  jnz     short loc_1800064F6
0x180006519  test    rdx, rdx
0x18000651c  lea     rcx, [rax-2]
0x180006520  lea     r8, aP0; "_p0"
0x180006527  cmovnz  rcx, rax
0x18000652b  mov     [rcx], r12w
0x18000652f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006534  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006539  mov     edx, ebp
0x18000653b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006543  and     edx, 7FFFFFFFh; lInitialCount
0x180006549  mov     [rsp+278h+dwFlags], r12d; int
0x18000654e  mov     r8d, esi
0x180006551  lea     r9, [rsp+278h+Name]; lpName
0x180006556  cmova   r8d, edx; lMaximumCount
0x18000655a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000655c  call    cs:__imp_CreateSemaphoreExW
0x180006562  mov     r15, rax
0x180006565  test    rax, rax
0x180006568  jnz     short loc_180006598
0x18000656a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000656f  mov     edi, eax
0x180006571  test    eax, eax
0x180006573  jns     short loc_1800065CC
0x180006575  mov     rcx, [rsp+278h]; this
0x18000657d  lea     r8, aWil; "wil"
0x180006584  mov     r9d, eax; char *
0x180006587  mov     edx, 8Bh; void *
0x18000658c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006591  mov     eax, edi
0x180006593  jmp     loc_18000666A
0x180006598  call    cs:__imp_GetLastError
0x18000659e  mov     rdi, [rbx]
0x1800065a1  test    rdi, rdi
0x1800065a4  jz      short loc_1800065C9
0x1800065a6  call    cs:__imp_GetLastError
0x1800065ac  mov     rcx, rdi; hObject
0x1800065af  mov     r14d, eax
0x1800065b2  call    cs:__imp_CloseHandle
0x1800065b8  test    eax, eax
0x1800065ba  jz      loc_1800066AF
0x1800065c0  mov     ecx, r14d; dwErrCode
0x1800065c3  call    cs:__imp_SetLastError
0x1800065c9  mov     [rbx], r15
0x1800065cc  lea     r8, asc_180010550; "h"
0x1800065d3  shr     rbp, 1Fh
0x1800065d7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800065dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065e1  test    ebp, ebp
0x1800065e3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800065eb  lea     r9, [rsp+278h+Name]; lpName
0x1800065f0  mov     [rsp+278h+dwFlags], r12d; int
0x1800065f5  cmovnz  esi, ebp
0x1800065f8  mov     edx, ebp; lInitialCount
0x1800065fa  mov     r8d, esi; lMaximumCount
0x1800065fd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800065ff  call    cs:__imp_CreateSemaphoreExW
0x180006605  mov     rsi, rax
0x180006608  test    rax, rax
0x18000660b  jnz     short loc_180006638
0x18000660d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006612  mov     ebx, eax
0x180006614  test    eax, eax
0x180006616  jns     short loc_180006668
0x180006618  mov     rcx, [rsp+278h]; this
0x180006620  lea     r8, aWil; "wil"
0x180006627  mov     r9d, eax; char *
0x18000662a  mov     edx, 90h; void *
0x18000662f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006634  mov     eax, ebx
0x180006636  jmp     short loc_18000666A
0x180006638  call    cs:__imp_GetLastError
0x18000663e  mov     rdi, [rbx+8]
0x180006642  test    rdi, rdi
0x180006645  jz      short loc_180006664
0x180006647  call    cs:__imp_GetLastError
0x18000664d  mov     rcx, rdi; hObject
0x180006650  mov     ebp, eax
0x180006652  call    cs:__imp_CloseHandle
0x180006658  test    eax, eax
0x18000665a  jz      short loc_180006696
0x18000665c  mov     ecx, ebp; dwErrCode
0x18000665e  call    cs:__imp_SetLastError
0x180006664  mov     [rbx+8], rsi
0x180006668  xor     eax, eax
0x18000666a  mov     rcx, [rsp+278h+var_38]
0x180006672  xor     rcx, rsp; StackCookie
0x180006675  call    __security_check_cookie
0x18000667a  lea     r11, [rsp+278h+var_28]
0x180006682  mov     rbx, [r11+38h]
0x180006686  mov     rbp, [r11+40h]
0x18000668a  mov     rsp, r11
0x18000668d  pop     r15
0x18000668f  pop     r14
0x180006691  pop     r12
0x180006693  pop     rdi
0x180006694  pop     rsi
0x180006695  retn
0x180006696  mov     rcx, [rsp+278h]; this
0x18000669e  mov     edx, 0A0Bh; void *
0x1800066a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066a9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800066af  mov     rcx, [rsp+278h]; this
0x1800066b7  mov     edx, 0A0Bh; void *
0x1800066bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

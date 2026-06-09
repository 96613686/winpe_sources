# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800074c8`
- end: `0x1800076f9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006ce8`
- `0x1800070c4`

## callees

- `0x180003080`
- `0x1800074c8`
- `0x180008388`
- `0x18000a5b4`
- `0x18000b004`
- `0x18000be1c`
- `0x18000be2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007591`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007637`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007591`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007696`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000767f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000767f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000768a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000768a`

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
0x1800074c8  mov     [rsp+arg_8], rbx
0x1800074cd  push    rbp
0x1800074ce  push    rsi
0x1800074cf  push    rdi
0x1800074d0  push    r12
0x1800074d2  push    r13
0x1800074d4  push    r14
0x1800074d6  push    r15
0x1800074d8  sub     rsp, 250h
0x1800074df  mov     rax, cs:__security_cookie
0x1800074e6  xor     rax, rsp
0x1800074e9  mov     [rsp+288h+var_48], rax
0x1800074f1  mov     rax, 0C000000000000000h
0x1800074fb  mov     rsi, r9
0x1800074fe  mov     r8, rdx
0x180007501  mov     rbx, rcx
0x180007504  test    rax, r9
0x180007507  jnz     loc_1800076E0
0x18000750d  xor     r12d, r12d
0x180007510  lea     rax, [rsp+288h+Name]
0x180007515  mov     r13d, 104h
0x18000751b  mov     ecx, 7FFFFFFEh
0x180007520  mov     edx, r13d
0x180007523  lea     ebp, [r12+1]
0x180007528  test    rcx, rcx
0x18000752b  jz      short loc_18000754B
0x18000752d  movzx   r9d, word ptr [r8]
0x180007531  test    r9w, r9w
0x180007535  jz      short loc_18000754B
0x180007537  mov     [rax], r9w
0x18000753b  add     r8, 2
0x18000753f  add     rax, 2
0x180007543  sub     rcx, rbp
0x180007546  sub     rdx, rbp
0x180007549  jnz     short loc_180007528
0x18000754b  test    rdx, rdx
0x18000754e  lea     rcx, [rax-2]
0x180007552  lea     r8, aP0; "_p0"
0x180007559  mov     rdx, r13; unsigned __int64
0x18000755c  cmovnz  rcx, rax
0x180007560  mov     [rcx], r12w
0x180007564  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007569  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000756e  mov     edx, esi
0x180007570  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007578  and     edx, 7FFFFFFFh; lInitialCount
0x18000757e  mov     [rsp+288h+dwFlags], r12d; int
0x180007583  mov     r8d, ebp
0x180007586  lea     r9, [rsp+288h+Name]; lpName
0x18000758b  cmova   r8d, edx; lMaximumCount
0x18000758f  xor     ecx, ecx; lpSemaphoreAttributes
0x180007591  call    cs:__imp_CreateSemaphoreExW
0x180007597  mov     r15, rax
0x18000759a  test    rax, rax
0x18000759d  jnz     short loc_1800075CD
0x18000759f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800075a4  mov     edi, eax
0x1800075a6  test    eax, eax
0x1800075a8  jns     short loc_180007601
0x1800075aa  mov     rcx, [rsp+288h]; this
0x1800075b2  lea     r8, aWil; "wil"
0x1800075b9  mov     r9d, eax; char *
0x1800075bc  mov     edx, 8Bh; void *
0x1800075c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075c6  mov     eax, edi
0x1800075c8  jmp     loc_1800076A2
0x1800075cd  call    cs:__imp_GetLastError
0x1800075d3  mov     rdi, [rbx]
0x1800075d6  test    rdi, rdi
0x1800075d9  jz      short loc_1800075FE
0x1800075db  call    cs:__imp_GetLastError
0x1800075e1  mov     rcx, rdi; hObject
0x1800075e4  mov     r14d, eax
0x1800075e7  call    cs:__imp_CloseHandle
0x1800075ed  test    eax, eax
0x1800075ef  jz      loc_1800076E6
0x1800075f5  mov     ecx, r14d; dwErrCode
0x1800075f8  call    cs:__imp_SetLastError
0x1800075fe  mov     [rbx], r15
0x180007601  lea     r8, asc_180064860; "h"
0x180007608  shr     rsi, 1Fh
0x18000760c  mov     rdx, r13; unsigned __int64
0x18000760f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007614  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007619  test    esi, esi
0x18000761b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007623  lea     r9, [rsp+288h+Name]; lpName
0x180007628  mov     [rsp+288h+dwFlags], r12d; int
0x18000762d  cmovnz  ebp, esi
0x180007630  mov     edx, esi; lInitialCount
0x180007632  mov     r8d, ebp; lMaximumCount
0x180007635  xor     ecx, ecx; lpSemaphoreAttributes
0x180007637  call    cs:__imp_CreateSemaphoreExW
0x18000763d  mov     rbp, rax
0x180007640  test    rax, rax
0x180007643  jnz     short loc_180007670
0x180007645  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000764a  mov     ebx, eax
0x18000764c  test    eax, eax
0x18000764e  jns     short loc_1800076A0
0x180007650  mov     rcx, [rsp+288h]; this
0x180007658  lea     r8, aWil; "wil"
0x18000765f  mov     r9d, eax; char *
0x180007662  mov     edx, 90h; void *
0x180007667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000766c  mov     eax, ebx
0x18000766e  jmp     short loc_1800076A2
0x180007670  call    cs:__imp_GetLastError
0x180007676  mov     rdi, [rbx+8]
0x18000767a  test    rdi, rdi
0x18000767d  jz      short loc_18000769C
0x18000767f  call    cs:__imp_GetLastError
0x180007685  mov     rcx, rdi; hObject
0x180007688  mov     esi, eax
0x18000768a  call    cs:__imp_CloseHandle
0x180007690  test    eax, eax
0x180007692  jz      short loc_1800076CD
0x180007694  mov     ecx, esi; dwErrCode
0x180007696  call    cs:__imp_SetLastError
0x18000769c  mov     [rbx+8], rbp
0x1800076a0  xor     eax, eax
0x1800076a2  mov     rcx, [rsp+288h+var_48]
0x1800076aa  xor     rcx, rsp; StackCookie
0x1800076ad  call    __security_check_cookie
0x1800076b2  mov     rbx, [rsp+288h+arg_8]
0x1800076ba  add     rsp, 250h
0x1800076c1  pop     r15
0x1800076c3  pop     r14
0x1800076c5  pop     r13
0x1800076c7  pop     r12
0x1800076c9  pop     rdi
0x1800076ca  pop     rsi
0x1800076cb  pop     rbp
0x1800076cc  retn
0x1800076cd  mov     rcx, [rsp+288h]; this
0x1800076d5  mov     edx, 0A0Bh; void *
0x1800076da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800076e6  mov     rcx, [rsp+288h]; this
0x1800076ee  mov     edx, 0A0Bh; void *
0x1800076f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140006434`
- end: `0x14000665e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005738`
- `0x140005b08`

## callees

- `0x140002600`
- `0x140006434`
- `0x1400073e8`
- `0x140009724`
- `0x14000a25c`
- `0x14000af58`
- `0x14000af68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400064f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000659b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400064f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000659b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400065d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400065e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400065d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400065e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000655f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400065fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000655f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400065fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000654e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000654e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065ee`

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
0x140006434  mov     [rsp+arg_8], rbx
0x140006439  mov     [rsp+arg_10], rbp
0x14000643e  push    rsi
0x14000643f  push    rdi
0x140006440  push    r12
0x140006442  push    r14
0x140006444  push    r15
0x140006446  sub     rsp, 250h
0x14000644d  mov     rax, cs:__security_cookie
0x140006454  xor     rax, rsp
0x140006457  mov     [rsp+278h+var_38], rax
0x14000645f  mov     rax, 0C000000000000000h
0x140006469  mov     rbp, r9
0x14000646c  mov     r8, rdx
0x14000646f  mov     rbx, rcx
0x140006472  test    rax, r9
0x140006475  jnz     loc_140006645
0x14000647b  xor     r12d, r12d
0x14000647e  lea     rax, [rsp+278h+Name]
0x140006483  mov     ecx, 7FFFFFFEh
0x140006488  mov     edx, 104h
0x14000648d  lea     esi, [r12+1]
0x140006492  test    rcx, rcx
0x140006495  jz      short loc_1400064B5
0x140006497  movzx   r9d, word ptr [r8]
0x14000649b  test    r9w, r9w
0x14000649f  jz      short loc_1400064B5
0x1400064a1  mov     [rax], r9w
0x1400064a5  add     r8, 2
0x1400064a9  add     rax, 2
0x1400064ad  sub     rcx, rsi
0x1400064b0  sub     rdx, rsi; unsigned __int64
0x1400064b3  jnz     short loc_140006492
0x1400064b5  test    rdx, rdx
0x1400064b8  lea     rcx, [rax-2]
0x1400064bc  lea     r8, aP0; "_p0"
0x1400064c3  cmovnz  rcx, rax
0x1400064c7  mov     [rcx], r12w
0x1400064cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400064d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400064d5  mov     edx, ebp
0x1400064d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400064df  and     edx, 7FFFFFFFh; lInitialCount
0x1400064e5  mov     [rsp+278h+dwFlags], r12d; int
0x1400064ea  mov     r8d, esi
0x1400064ed  lea     r9, [rsp+278h+Name]; lpName
0x1400064f2  cmova   r8d, edx; lMaximumCount
0x1400064f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1400064f8  call    cs:__imp_CreateSemaphoreExW
0x1400064fe  mov     r15, rax
0x140006501  test    rax, rax
0x140006504  jnz     short loc_140006534
0x140006506  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000650b  mov     edi, eax
0x14000650d  test    eax, eax
0x14000650f  jns     short loc_140006568
0x140006511  mov     rcx, [rsp+278h]; this
0x140006519  lea     r8, aWil; "wil"
0x140006520  mov     r9d, eax; char *
0x140006523  mov     edx, 8Bh; void *
0x140006528  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000652d  mov     eax, edi
0x14000652f  jmp     loc_140006606
0x140006534  call    cs:__imp_GetLastError
0x14000653a  mov     rdi, [rbx]
0x14000653d  test    rdi, rdi
0x140006540  jz      short loc_140006565
0x140006542  call    cs:__imp_GetLastError
0x140006548  mov     rcx, rdi; hObject
0x14000654b  mov     r14d, eax
0x14000654e  call    cs:__imp_CloseHandle
0x140006554  test    eax, eax
0x140006556  jz      loc_14000664B
0x14000655c  mov     ecx, r14d; dwErrCode
0x14000655f  call    cs:__imp_SetLastError
0x140006565  mov     [rbx], r15
0x140006568  lea     r8, asc_140015F50; "h"
0x14000656f  shr     rbp, 1Fh
0x140006573  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140006578  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000657d  test    ebp, ebp
0x14000657f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140006587  lea     r9, [rsp+278h+Name]; lpName
0x14000658c  mov     [rsp+278h+dwFlags], r12d; int
0x140006591  cmovnz  esi, ebp
0x140006594  mov     edx, ebp; lInitialCount
0x140006596  mov     r8d, esi; lMaximumCount
0x140006599  xor     ecx, ecx; lpSemaphoreAttributes
0x14000659b  call    cs:__imp_CreateSemaphoreExW
0x1400065a1  mov     rsi, rax
0x1400065a4  test    rax, rax
0x1400065a7  jnz     short loc_1400065D4
0x1400065a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400065ae  mov     ebx, eax
0x1400065b0  test    eax, eax
0x1400065b2  jns     short loc_140006604
0x1400065b4  mov     rcx, [rsp+278h]; this
0x1400065bc  lea     r8, aWil; "wil"
0x1400065c3  mov     r9d, eax; char *
0x1400065c6  mov     edx, 90h; void *
0x1400065cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400065d0  mov     eax, ebx
0x1400065d2  jmp     short loc_140006606
0x1400065d4  call    cs:__imp_GetLastError
0x1400065da  mov     rdi, [rbx+8]
0x1400065de  test    rdi, rdi
0x1400065e1  jz      short loc_140006600
0x1400065e3  call    cs:__imp_GetLastError
0x1400065e9  mov     rcx, rdi; hObject
0x1400065ec  mov     ebp, eax
0x1400065ee  call    cs:__imp_CloseHandle
0x1400065f4  test    eax, eax
0x1400065f6  jz      short loc_140006632
0x1400065f8  mov     ecx, ebp; dwErrCode
0x1400065fa  call    cs:__imp_SetLastError
0x140006600  mov     [rbx+8], rsi
0x140006604  xor     eax, eax
0x140006606  mov     rcx, [rsp+278h+var_38]
0x14000660e  xor     rcx, rsp; StackCookie
0x140006611  call    __security_check_cookie
0x140006616  lea     r11, [rsp+278h+var_28]
0x14000661e  mov     rbx, [r11+38h]
0x140006622  mov     rbp, [r11+40h]
0x140006626  mov     rsp, r11
0x140006629  pop     r15
0x14000662b  pop     r14
0x14000662d  pop     r12
0x14000662f  pop     rdi
0x140006630  pop     rsi
0x140006631  retn
0x140006632  mov     rcx, [rsp+278h]; this
0x14000663a  mov     edx, 0A0Bh; void *
0x14000663f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006645  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000664b  mov     rcx, [rsp+278h]; this
0x140006653  mov     edx, 0A0Bh; void *
0x140006658  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

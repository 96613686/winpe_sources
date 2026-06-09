# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800056f4`
- end: `0x180005917`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d1c`
- `0x1800050c0`

## callees

- `0x180003550`
- `0x1800056f4`
- `0x18000698c`
- `0x180009554`
- `0x18000a56c`
- `0x18000a57c`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000581d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000581d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000588e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000588e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800057bd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000585c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800057bd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000585c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a8`

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
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  unsigned int v31; // r8d
  const char *v32; // r9
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800056f4  mov     [rsp+arg_8], rbx
0x1800056f9  push    rbp
0x1800056fa  push    rsi
0x1800056fb  push    rdi
0x1800056fc  push    r12
0x1800056fe  push    r13
0x180005700  push    r14
0x180005702  push    r15
0x180005704  sub     rsp, 250h
0x18000570b  mov     rax, cs:__security_cookie
0x180005712  xor     rax, rsp
0x180005715  mov     [rsp+288h+var_48], rax
0x18000571d  mov     rax, 0C000000000000000h
0x180005727  mov     rsi, r9
0x18000572a  mov     r8, rdx
0x18000572d  mov     rbx, rcx
0x180005730  test    rax, r9
0x180005733  jnz     loc_1800058FE
0x180005739  xor     r12d, r12d
0x18000573c  lea     rax, [rsp+288h+Name]
0x180005741  mov     r13d, 104h
0x180005747  mov     ecx, 7FFFFFFEh
0x18000574c  mov     edx, r13d
0x18000574f  lea     ebp, [r12+1]
0x180005754  test    rcx, rcx
0x180005757  jz      short loc_180005777
0x180005759  movzx   r9d, word ptr [r8]
0x18000575d  test    r9w, r9w
0x180005761  jz      short loc_180005777
0x180005763  mov     [rax], r9w
0x180005767  add     r8, 2
0x18000576b  add     rax, 2
0x18000576f  sub     rcx, rbp
0x180005772  sub     rdx, rbp
0x180005775  jnz     short loc_180005754
0x180005777  test    rdx, rdx
0x18000577a  lea     rcx, [rax-2]
0x18000577e  lea     r8, aP0; "_p0"
0x180005785  mov     rdx, r13; unsigned __int64
0x180005788  cmovnz  rcx, rax
0x18000578c  mov     [rcx], r12w
0x180005790  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180005795  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000579a  mov     edx, esi
0x18000579c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800057a4  and     edx, 7FFFFFFFh; lInitialCount
0x1800057aa  mov     [rsp+288h+dwFlags], r12d; int
0x1800057af  mov     r8d, ebp
0x1800057b2  lea     r9, [rsp+288h+Name]; lpName
0x1800057b7  cmova   r8d, edx; lMaximumCount
0x1800057bb  xor     ecx, ecx; lpSemaphoreAttributes
0x1800057bd  call    cs:__imp_CreateSemaphoreExW
0x1800057c3  mov     r15, rax
0x1800057c6  test    rax, rax
0x1800057c9  jnz     short loc_1800057F2
0x1800057cb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800057d0  mov     edi, eax
0x1800057d2  test    eax, eax
0x1800057d4  jns     short loc_180005826
0x1800057d6  mov     rcx, [rsp+288h]; this
0x1800057de  mov     r9d, eax; char *
0x1800057e1  mov     edx, 8Bh; void *
0x1800057e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057eb  mov     eax, edi
0x1800057ed  jmp     loc_1800058C0
0x1800057f2  call    cs:__imp_GetLastError
0x1800057f8  mov     rdi, [rbx]
0x1800057fb  test    rdi, rdi
0x1800057fe  jz      short loc_180005823
0x180005800  call    cs:__imp_GetLastError
0x180005806  mov     rcx, rdi; hObject
0x180005809  mov     r14d, eax
0x18000580c  call    cs:__imp_CloseHandle
0x180005812  test    eax, eax
0x180005814  jz      loc_180005904
0x18000581a  mov     ecx, r14d; dwErrCode
0x18000581d  call    cs:__imp_SetLastError
0x180005823  mov     [rbx], r15
0x180005826  lea     r8, asc_180010150; "h"
0x18000582d  shr     rsi, 1Fh
0x180005831  mov     rdx, r13; unsigned __int64
0x180005834  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180005839  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000583e  test    esi, esi
0x180005840  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005848  lea     r9, [rsp+288h+Name]; lpName
0x18000584d  mov     [rsp+288h+dwFlags], r12d; int
0x180005852  cmovnz  ebp, esi
0x180005855  mov     edx, esi; lInitialCount
0x180005857  mov     r8d, ebp; lMaximumCount
0x18000585a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000585c  call    cs:__imp_CreateSemaphoreExW
0x180005862  mov     rbp, rax
0x180005865  test    rax, rax
0x180005868  jnz     short loc_18000588E
0x18000586a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000586f  mov     ebx, eax
0x180005871  test    eax, eax
0x180005873  jns     short loc_1800058BE
0x180005875  mov     rcx, [rsp+288h]; this
0x18000587d  mov     r9d, eax; char *
0x180005880  mov     edx, 90h; void *
0x180005885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000588a  mov     eax, ebx
0x18000588c  jmp     short loc_1800058C0
0x18000588e  call    cs:__imp_GetLastError
0x180005894  mov     rdi, [rbx+8]
0x180005898  test    rdi, rdi
0x18000589b  jz      short loc_1800058BA
0x18000589d  call    cs:__imp_GetLastError
0x1800058a3  mov     rcx, rdi; hObject
0x1800058a6  mov     esi, eax
0x1800058a8  call    cs:__imp_CloseHandle
0x1800058ae  test    eax, eax
0x1800058b0  jz      short loc_1800058EB
0x1800058b2  mov     ecx, esi; dwErrCode
0x1800058b4  call    cs:__imp_SetLastError
0x1800058ba  mov     [rbx+8], rbp
0x1800058be  xor     eax, eax
0x1800058c0  mov     rcx, [rsp+288h+var_48]
0x1800058c8  xor     rcx, rsp; StackCookie
0x1800058cb  call    __security_check_cookie
0x1800058d0  mov     rbx, [rsp+288h+arg_8]
0x1800058d8  add     rsp, 250h
0x1800058df  pop     r15
0x1800058e1  pop     r14
0x1800058e3  pop     r13
0x1800058e5  pop     r12
0x1800058e7  pop     rdi
0x1800058e8  pop     rsi
0x1800058e9  pop     rbp
0x1800058ea  retn
0x1800058eb  mov     rcx, [rsp+288h]; this
0x1800058f3  mov     edx, 0A0Bh; void *
0x1800058f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005904  mov     rcx, [rsp+288h]; this
0x18000590c  mov     edx, 0A0Bh; void *
0x180005911  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005ea8`
- end: `0x1800060cb`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004c68`
- `0x18000500c`

## callees

- `0x180001710`
- `0x180005ea8`
- `0x1800077ac`
- `0x180009f0c`
- `0x18000ae3c`
- `0x18000f33c`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005f71`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006010`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005f71`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006051`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000605c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000605c`

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
0x180005ea8  mov     [rsp+arg_8], rbx
0x180005ead  push    rbp
0x180005eae  push    rsi
0x180005eaf  push    rdi
0x180005eb0  push    r12
0x180005eb2  push    r13
0x180005eb4  push    r14
0x180005eb6  push    r15
0x180005eb8  sub     rsp, 250h
0x180005ebf  mov     rax, cs:__security_cookie
0x180005ec6  xor     rax, rsp
0x180005ec9  mov     [rsp+288h+var_48], rax
0x180005ed1  mov     rax, 0C000000000000000h
0x180005edb  mov     rsi, r9
0x180005ede  mov     r8, rdx
0x180005ee1  mov     rbx, rcx
0x180005ee4  test    rax, r9
0x180005ee7  jnz     loc_1800060B2
0x180005eed  xor     r12d, r12d
0x180005ef0  lea     rax, [rsp+288h+Name]
0x180005ef5  mov     r13d, 104h
0x180005efb  mov     ecx, 7FFFFFFEh
0x180005f00  mov     edx, r13d
0x180005f03  lea     ebp, [r12+1]
0x180005f08  test    rcx, rcx
0x180005f0b  jz      short loc_180005F2B
0x180005f0d  movzx   r9d, word ptr [r8]
0x180005f11  test    r9w, r9w
0x180005f15  jz      short loc_180005F2B
0x180005f17  mov     [rax], r9w
0x180005f1b  add     r8, 2
0x180005f1f  add     rax, 2
0x180005f23  sub     rcx, rbp
0x180005f26  sub     rdx, rbp
0x180005f29  jnz     short loc_180005F08
0x180005f2b  test    rdx, rdx
0x180005f2e  lea     rcx, [rax-2]
0x180005f32  lea     r8, aP0; "_p0"
0x180005f39  mov     rdx, r13; unsigned __int64
0x180005f3c  cmovnz  rcx, rax
0x180005f40  mov     [rcx], r12w
0x180005f44  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180005f49  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005f4e  mov     edx, esi
0x180005f50  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005f58  and     edx, 7FFFFFFFh; lInitialCount
0x180005f5e  mov     [rsp+288h+dwFlags], r12d; int
0x180005f63  mov     r8d, ebp
0x180005f66  lea     r9, [rsp+288h+Name]; lpName
0x180005f6b  cmova   r8d, edx; lMaximumCount
0x180005f6f  xor     ecx, ecx; lpSemaphoreAttributes
0x180005f71  call    cs:__imp_CreateSemaphoreExW
0x180005f77  mov     r15, rax
0x180005f7a  test    rax, rax
0x180005f7d  jnz     short loc_180005FA6
0x180005f7f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f84  mov     edi, eax
0x180005f86  test    eax, eax
0x180005f88  jns     short loc_180005FDA
0x180005f8a  mov     rcx, [rsp+288h]; this
0x180005f92  mov     r9d, eax; char *
0x180005f95  mov     edx, 8Bh; void *
0x180005f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f9f  mov     eax, edi
0x180005fa1  jmp     loc_180006074
0x180005fa6  call    cs:__imp_GetLastError
0x180005fac  mov     rdi, [rbx]
0x180005faf  test    rdi, rdi
0x180005fb2  jz      short loc_180005FD7
0x180005fb4  call    cs:__imp_GetLastError
0x180005fba  mov     rcx, rdi; hObject
0x180005fbd  mov     r14d, eax
0x180005fc0  call    cs:__imp_CloseHandle
0x180005fc6  test    eax, eax
0x180005fc8  jz      loc_1800060B8
0x180005fce  mov     ecx, r14d; dwErrCode
0x180005fd1  call    cs:__imp_SetLastError
0x180005fd7  mov     [rbx], r15
0x180005fda  lea     r8, asc_18002F198; "h"
0x180005fe1  shr     rsi, 1Fh
0x180005fe5  mov     rdx, r13; unsigned __int64
0x180005fe8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180005fed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005ff2  test    esi, esi
0x180005ff4  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005ffc  lea     r9, [rsp+288h+Name]; lpName
0x180006001  mov     [rsp+288h+dwFlags], r12d; int
0x180006006  cmovnz  ebp, esi
0x180006009  mov     edx, esi; lInitialCount
0x18000600b  mov     r8d, ebp; lMaximumCount
0x18000600e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006010  call    cs:__imp_CreateSemaphoreExW
0x180006016  mov     rbp, rax
0x180006019  test    rax, rax
0x18000601c  jnz     short loc_180006042
0x18000601e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006023  mov     ebx, eax
0x180006025  test    eax, eax
0x180006027  jns     short loc_180006072
0x180006029  mov     rcx, [rsp+288h]; this
0x180006031  mov     r9d, eax; char *
0x180006034  mov     edx, 90h; void *
0x180006039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000603e  mov     eax, ebx
0x180006040  jmp     short loc_180006074
0x180006042  call    cs:__imp_GetLastError
0x180006048  mov     rdi, [rbx+8]
0x18000604c  test    rdi, rdi
0x18000604f  jz      short loc_18000606E
0x180006051  call    cs:__imp_GetLastError
0x180006057  mov     rcx, rdi; hObject
0x18000605a  mov     esi, eax
0x18000605c  call    cs:__imp_CloseHandle
0x180006062  test    eax, eax
0x180006064  jz      short loc_18000609F
0x180006066  mov     ecx, esi; dwErrCode
0x180006068  call    cs:__imp_SetLastError
0x18000606e  mov     [rbx+8], rbp
0x180006072  xor     eax, eax
0x180006074  mov     rcx, [rsp+288h+var_48]
0x18000607c  xor     rcx, rsp; StackCookie
0x18000607f  call    __security_check_cookie
0x180006084  mov     rbx, [rsp+288h+arg_8]
0x18000608c  add     rsp, 250h
0x180006093  pop     r15
0x180006095  pop     r14
0x180006097  pop     r13
0x180006099  pop     r12
0x18000609b  pop     rdi
0x18000609c  pop     rsi
0x18000609d  pop     rbp
0x18000609e  retn
0x18000609f  mov     rcx, [rsp+288h]; this
0x1800060a7  mov     edx, 0A0Bh; void *
0x1800060ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800060b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800060b8  mov     rcx, [rsp+288h]; this
0x1800060c0  mov     edx, 0A0Bh; void *
0x1800060c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

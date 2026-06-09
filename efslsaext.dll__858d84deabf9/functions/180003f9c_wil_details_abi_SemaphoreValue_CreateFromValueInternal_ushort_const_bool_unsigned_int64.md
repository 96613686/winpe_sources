# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003f9c`
- end: `0x1800041bf`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bf8`
- `0x18000cf30`

## callees

- `0x180003f9c`
- `0x1800048dc`
- `0x180005a4c`
- `0x180005c94`
- `0x1800062ec`
- `0x1800062fc`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004145`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000415c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000415c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004150`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004065`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004104`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004065`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004104`

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
0x180003f9c  mov     [rsp+arg_8], rbx
0x180003fa1  push    rbp
0x180003fa2  push    rsi
0x180003fa3  push    rdi
0x180003fa4  push    r12
0x180003fa6  push    r13
0x180003fa8  push    r14
0x180003faa  push    r15
0x180003fac  sub     rsp, 250h
0x180003fb3  mov     rax, cs:__security_cookie
0x180003fba  xor     rax, rsp
0x180003fbd  mov     [rsp+288h+var_48], rax
0x180003fc5  mov     rax, 0C000000000000000h
0x180003fcf  mov     rsi, r9
0x180003fd2  mov     r8, rdx
0x180003fd5  mov     rbx, rcx
0x180003fd8  test    rax, r9
0x180003fdb  jnz     loc_1800041A6
0x180003fe1  xor     r12d, r12d
0x180003fe4  lea     rax, [rsp+288h+Name]
0x180003fe9  mov     r13d, 104h
0x180003fef  mov     ecx, 7FFFFFFEh
0x180003ff4  mov     edx, r13d
0x180003ff7  lea     ebp, [r12+1]
0x180003ffc  test    rcx, rcx
0x180003fff  jz      short loc_18000401F
0x180004001  movzx   r9d, word ptr [r8]
0x180004005  test    r9w, r9w
0x180004009  jz      short loc_18000401F
0x18000400b  mov     [rax], r9w
0x18000400f  add     r8, 2
0x180004013  add     rax, 2
0x180004017  sub     rcx, rbp
0x18000401a  sub     rdx, rbp
0x18000401d  jnz     short loc_180003FFC
0x18000401f  test    rdx, rdx
0x180004022  lea     rcx, [rax-2]
0x180004026  lea     r8, aP0; "_p0"
0x18000402d  mov     rdx, r13; unsigned __int64
0x180004030  cmovnz  rcx, rax
0x180004034  mov     [rcx], r12w
0x180004038  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000403d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004042  mov     edx, esi
0x180004044  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000404c  and     edx, 7FFFFFFFh; lInitialCount
0x180004052  mov     [rsp+288h+dwFlags], r12d; int
0x180004057  mov     r8d, ebp
0x18000405a  lea     r9, [rsp+288h+Name]; lpName
0x18000405f  cmova   r8d, edx; lMaximumCount
0x180004063  xor     ecx, ecx; lpSemaphoreAttributes
0x180004065  call    cs:__imp_CreateSemaphoreExW
0x18000406b  mov     r15, rax
0x18000406e  test    rax, rax
0x180004071  jnz     short loc_18000409A
0x180004073  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004078  mov     edi, eax
0x18000407a  test    eax, eax
0x18000407c  jns     short loc_1800040CE
0x18000407e  mov     rcx, [rsp+288h]; this
0x180004086  mov     r9d, eax; char *
0x180004089  mov     edx, 8Bh; void *
0x18000408e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004093  mov     eax, edi
0x180004095  jmp     loc_180004168
0x18000409a  call    cs:__imp_GetLastError
0x1800040a0  mov     rdi, [rbx]
0x1800040a3  test    rdi, rdi
0x1800040a6  jz      short loc_1800040CB
0x1800040a8  call    cs:__imp_GetLastError
0x1800040ae  mov     rcx, rdi; hObject
0x1800040b1  mov     r14d, eax
0x1800040b4  call    cs:__imp_CloseHandle
0x1800040ba  test    eax, eax
0x1800040bc  jz      loc_1800041AC
0x1800040c2  mov     ecx, r14d; dwErrCode
0x1800040c5  call    cs:__imp_SetLastError
0x1800040cb  mov     [rbx], r15
0x1800040ce  lea     r8, asc_180017CA8; "h"
0x1800040d5  shr     rsi, 1Fh
0x1800040d9  mov     rdx, r13; unsigned __int64
0x1800040dc  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800040e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800040e6  test    esi, esi
0x1800040e8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800040f0  lea     r9, [rsp+288h+Name]; lpName
0x1800040f5  mov     [rsp+288h+dwFlags], r12d; int
0x1800040fa  cmovnz  ebp, esi
0x1800040fd  mov     edx, esi; lInitialCount
0x1800040ff  mov     r8d, ebp; lMaximumCount
0x180004102  xor     ecx, ecx; lpSemaphoreAttributes
0x180004104  call    cs:__imp_CreateSemaphoreExW
0x18000410a  mov     rbp, rax
0x18000410d  test    rax, rax
0x180004110  jnz     short loc_180004136
0x180004112  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004117  mov     ebx, eax
0x180004119  test    eax, eax
0x18000411b  jns     short loc_180004166
0x18000411d  mov     rcx, [rsp+288h]; this
0x180004125  mov     r9d, eax; char *
0x180004128  mov     edx, 90h; void *
0x18000412d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004132  mov     eax, ebx
0x180004134  jmp     short loc_180004168
0x180004136  call    cs:__imp_GetLastError
0x18000413c  mov     rdi, [rbx+8]
0x180004140  test    rdi, rdi
0x180004143  jz      short loc_180004162
0x180004145  call    cs:__imp_GetLastError
0x18000414b  mov     rcx, rdi; hObject
0x18000414e  mov     esi, eax
0x180004150  call    cs:__imp_CloseHandle
0x180004156  test    eax, eax
0x180004158  jz      short loc_180004193
0x18000415a  mov     ecx, esi; dwErrCode
0x18000415c  call    cs:__imp_SetLastError
0x180004162  mov     [rbx+8], rbp
0x180004166  xor     eax, eax
0x180004168  mov     rcx, [rsp+288h+var_48]
0x180004170  xor     rcx, rsp; StackCookie
0x180004173  call    __security_check_cookie
0x180004178  mov     rbx, [rsp+288h+arg_8]
0x180004180  add     rsp, 250h
0x180004187  pop     r15
0x180004189  pop     r14
0x18000418b  pop     r13
0x18000418d  pop     r12
0x18000418f  pop     rdi
0x180004190  pop     rsi
0x180004191  pop     rbp
0x180004192  retn
0x180004193  mov     rcx, [rsp+288h]; this
0x18000419b  mov     edx, 0A0Bh; void *
0x1800041a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041ac  mov     rcx, [rsp+288h]; this
0x1800041b4  mov     edx, 0A0Bh; void *
0x1800041b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

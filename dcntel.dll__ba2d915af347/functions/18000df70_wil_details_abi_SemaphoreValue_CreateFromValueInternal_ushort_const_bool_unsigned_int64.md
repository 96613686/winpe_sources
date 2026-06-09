# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000df70`
- end: `0x18000e1a1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d7a8`
- `0x18000db78`

## callees

- `0x180008dc0`
- `0x18000df70`
- `0x18000f378`
- `0x180011ce4`
- `0x180012734`
- `0x1800136f8`
- `0x180013708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e039`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e0df`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e039`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e0df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e13e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e132`

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
0x18000df70  mov     [rsp+arg_8], rbx
0x18000df75  push    rbp
0x18000df76  push    rsi
0x18000df77  push    rdi
0x18000df78  push    r12
0x18000df7a  push    r13
0x18000df7c  push    r14
0x18000df7e  push    r15
0x18000df80  sub     rsp, 250h
0x18000df87  mov     rax, cs:__security_cookie
0x18000df8e  xor     rax, rsp
0x18000df91  mov     [rsp+288h+var_48], rax
0x18000df99  mov     rax, 0C000000000000000h
0x18000dfa3  mov     rsi, r9
0x18000dfa6  mov     r8, rdx
0x18000dfa9  mov     rbx, rcx
0x18000dfac  test    rax, r9
0x18000dfaf  jnz     loc_18000E188
0x18000dfb5  xor     r12d, r12d
0x18000dfb8  lea     rax, [rsp+288h+Name]
0x18000dfbd  mov     r13d, 104h
0x18000dfc3  mov     ecx, 7FFFFFFEh
0x18000dfc8  mov     edx, r13d
0x18000dfcb  lea     ebp, [r12+1]
0x18000dfd0  test    rcx, rcx
0x18000dfd3  jz      short loc_18000DFF3
0x18000dfd5  movzx   r9d, word ptr [r8]
0x18000dfd9  test    r9w, r9w
0x18000dfdd  jz      short loc_18000DFF3
0x18000dfdf  mov     [rax], r9w
0x18000dfe3  add     r8, 2
0x18000dfe7  add     rax, 2
0x18000dfeb  sub     rcx, rbp
0x18000dfee  sub     rdx, rbp
0x18000dff1  jnz     short loc_18000DFD0
0x18000dff3  test    rdx, rdx
0x18000dff6  lea     rcx, [rax-2]
0x18000dffa  lea     r8, aP0; "_p0"
0x18000e001  mov     rdx, r13; unsigned __int64
0x18000e004  cmovnz  rcx, rax
0x18000e008  mov     [rcx], r12w
0x18000e00c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000e011  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e016  mov     edx, esi
0x18000e018  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000e020  and     edx, 7FFFFFFFh; lInitialCount
0x18000e026  mov     [rsp+288h+dwFlags], r12d; int
0x18000e02b  mov     r8d, ebp
0x18000e02e  lea     r9, [rsp+288h+Name]; lpName
0x18000e033  cmova   r8d, edx; lMaximumCount
0x18000e037  xor     ecx, ecx; lpSemaphoreAttributes
0x18000e039  call    cs:__imp_CreateSemaphoreExW
0x18000e03f  mov     r15, rax
0x18000e042  test    rax, rax
0x18000e045  jnz     short loc_18000E075
0x18000e047  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e04c  mov     edi, eax
0x18000e04e  test    eax, eax
0x18000e050  jns     short loc_18000E0A9
0x18000e052  mov     rcx, [rsp+288h]; this
0x18000e05a  lea     r8, aWil; "wil"
0x18000e061  mov     r9d, eax; char *
0x18000e064  mov     edx, 8Bh; void *
0x18000e069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e06e  mov     eax, edi
0x18000e070  jmp     loc_18000E14A
0x18000e075  call    cs:__imp_GetLastError
0x18000e07b  mov     rdi, [rbx]
0x18000e07e  test    rdi, rdi
0x18000e081  jz      short loc_18000E0A6
0x18000e083  call    cs:__imp_GetLastError
0x18000e089  mov     rcx, rdi; hObject
0x18000e08c  mov     r14d, eax
0x18000e08f  call    cs:__imp_CloseHandle
0x18000e095  test    eax, eax
0x18000e097  jz      loc_18000E18E
0x18000e09d  mov     ecx, r14d; dwErrCode
0x18000e0a0  call    cs:__imp_SetLastError
0x18000e0a6  mov     [rbx], r15
0x18000e0a9  lea     r8, asc_1801B4390; "h"
0x18000e0b0  shr     rsi, 1Fh
0x18000e0b4  mov     rdx, r13; unsigned __int64
0x18000e0b7  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000e0bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e0c1  test    esi, esi
0x18000e0c3  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000e0cb  lea     r9, [rsp+288h+Name]; lpName
0x18000e0d0  mov     [rsp+288h+dwFlags], r12d; int
0x18000e0d5  cmovnz  ebp, esi
0x18000e0d8  mov     edx, esi; lInitialCount
0x18000e0da  mov     r8d, ebp; lMaximumCount
0x18000e0dd  xor     ecx, ecx; lpSemaphoreAttributes
0x18000e0df  call    cs:__imp_CreateSemaphoreExW
0x18000e0e5  mov     rbp, rax
0x18000e0e8  test    rax, rax
0x18000e0eb  jnz     short loc_18000E118
0x18000e0ed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e0f2  mov     ebx, eax
0x18000e0f4  test    eax, eax
0x18000e0f6  jns     short loc_18000E148
0x18000e0f8  mov     rcx, [rsp+288h]; this
0x18000e100  lea     r8, aWil; "wil"
0x18000e107  mov     r9d, eax; char *
0x18000e10a  mov     edx, 90h; void *
0x18000e10f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e114  mov     eax, ebx
0x18000e116  jmp     short loc_18000E14A
0x18000e118  call    cs:__imp_GetLastError
0x18000e11e  mov     rdi, [rbx+8]
0x18000e122  test    rdi, rdi
0x18000e125  jz      short loc_18000E144
0x18000e127  call    cs:__imp_GetLastError
0x18000e12d  mov     rcx, rdi; hObject
0x18000e130  mov     esi, eax
0x18000e132  call    cs:__imp_CloseHandle
0x18000e138  test    eax, eax
0x18000e13a  jz      short loc_18000E175
0x18000e13c  mov     ecx, esi; dwErrCode
0x18000e13e  call    cs:__imp_SetLastError
0x18000e144  mov     [rbx+8], rbp
0x18000e148  xor     eax, eax
0x18000e14a  mov     rcx, [rsp+288h+var_48]
0x18000e152  xor     rcx, rsp; StackCookie
0x18000e155  call    __security_check_cookie
0x18000e15a  mov     rbx, [rsp+288h+arg_8]
0x18000e162  add     rsp, 250h
0x18000e169  pop     r15
0x18000e16b  pop     r14
0x18000e16d  pop     r13
0x18000e16f  pop     r12
0x18000e171  pop     rdi
0x18000e172  pop     rsi
0x18000e173  pop     rbp
0x18000e174  retn
0x18000e175  mov     rcx, [rsp+288h]; this
0x18000e17d  mov     edx, 0A0Bh; void *
0x18000e182  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e188  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e18e  mov     rcx, [rsp+288h]; this
0x18000e196  mov     edx, 0A0Bh; void *
0x18000e19b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

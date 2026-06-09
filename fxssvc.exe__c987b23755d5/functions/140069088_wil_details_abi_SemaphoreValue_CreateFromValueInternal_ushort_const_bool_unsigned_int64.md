# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140069088`
- end: `0x1400692ab`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400687a8`
- `0x140068b4c`

## callees

- `0x14000c450`
- `0x140069088`
- `0x140069d68`
- `0x14006bf04`
- `0x14006d33c`
- `0x14006d34c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140069151`
- `KERNEL32!CreateSemaphoreExW` at `0x1400691f0`
- `KERNEL32!CreateSemaphoreExW` at `0x140069151`
- `KERNEL32!CreateSemaphoreExW` at `0x1400691f0`
- `KERNEL32!GetLastError` at `0x140069186`
- `KERNEL32!GetLastError` at `0x140069194`
- `KERNEL32!GetLastError` at `0x140069222`
- `KERNEL32!GetLastError` at `0x140069231`
- `KERNEL32!GetLastError` at `0x140069186`
- `KERNEL32!GetLastError` at `0x140069194`
- `KERNEL32!GetLastError` at `0x140069222`
- `KERNEL32!GetLastError` at `0x140069231`
- `KERNEL32!SetLastError` at `0x1400691b1`
- `KERNEL32!SetLastError` at `0x140069248`
- `KERNEL32!SetLastError` at `0x1400691b1`
- `KERNEL32!SetLastError` at `0x140069248`
- `KERNEL32!CloseHandle` at `0x1400691a0`
- `KERNEL32!CloseHandle` at `0x14006923c`
- `KERNEL32!CloseHandle` at `0x1400691a0`
- `KERNEL32!CloseHandle` at `0x14006923c`

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
0x140069088  mov     [rsp+arg_8], rbx
0x14006908d  push    rbp
0x14006908e  push    rsi
0x14006908f  push    rdi
0x140069090  push    r12
0x140069092  push    r13
0x140069094  push    r14
0x140069096  push    r15
0x140069098  sub     rsp, 250h
0x14006909f  mov     rax, cs:__security_cookie
0x1400690a6  xor     rax, rsp
0x1400690a9  mov     [rsp+288h+var_48], rax
0x1400690b1  mov     rax, 0C000000000000000h
0x1400690bb  mov     rsi, r9
0x1400690be  mov     r8, rdx
0x1400690c1  mov     rbx, rcx
0x1400690c4  test    rax, r9
0x1400690c7  jnz     loc_140069292
0x1400690cd  xor     r12d, r12d
0x1400690d0  lea     rax, [rsp+288h+Name]
0x1400690d5  mov     r13d, 104h
0x1400690db  mov     ecx, 7FFFFFFEh
0x1400690e0  mov     edx, r13d
0x1400690e3  lea     ebp, [r12+1]
0x1400690e8  test    rcx, rcx
0x1400690eb  jz      short loc_14006910B
0x1400690ed  movzx   r9d, word ptr [r8]
0x1400690f1  test    r9w, r9w
0x1400690f5  jz      short loc_14006910B
0x1400690f7  mov     [rax], r9w
0x1400690fb  add     r8, 2
0x1400690ff  add     rax, 2
0x140069103  sub     rcx, rbp
0x140069106  sub     rdx, rbp
0x140069109  jnz     short loc_1400690E8
0x14006910b  test    rdx, rdx
0x14006910e  lea     rcx, [rax-2]
0x140069112  lea     r8, aP0; "_p0"
0x140069119  mov     rdx, r13; unsigned __int64
0x14006911c  cmovnz  rcx, rax
0x140069120  mov     [rcx], r12w
0x140069124  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140069129  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006912e  mov     edx, esi
0x140069130  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140069138  and     edx, 7FFFFFFFh; lInitialCount
0x14006913e  mov     [rsp+288h+dwFlags], r12d; int
0x140069143  mov     r8d, ebp
0x140069146  lea     r9, [rsp+288h+Name]; lpName
0x14006914b  cmova   r8d, edx; lMaximumCount
0x14006914f  xor     ecx, ecx; lpSemaphoreAttributes
0x140069151  call    cs:__imp_CreateSemaphoreExW
0x140069157  mov     r15, rax
0x14006915a  test    rax, rax
0x14006915d  jnz     short loc_140069186
0x14006915f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140069164  mov     edi, eax
0x140069166  test    eax, eax
0x140069168  jns     short loc_1400691BA
0x14006916a  mov     rcx, [rsp+288h]; this
0x140069172  mov     r9d, eax; char *
0x140069175  mov     edx, 8Bh; void *
0x14006917a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006917f  mov     eax, edi
0x140069181  jmp     loc_140069254
0x140069186  call    cs:__imp_GetLastError
0x14006918c  mov     rdi, [rbx]
0x14006918f  test    rdi, rdi
0x140069192  jz      short loc_1400691B7
0x140069194  call    cs:__imp_GetLastError
0x14006919a  mov     rcx, rdi; hObject
0x14006919d  mov     r14d, eax
0x1400691a0  call    cs:__imp_CloseHandle
0x1400691a6  test    eax, eax
0x1400691a8  jz      loc_140069298
0x1400691ae  mov     ecx, r14d; dwErrCode
0x1400691b1  call    cs:__imp_SetLastError
0x1400691b7  mov     [rbx], r15
0x1400691ba  lea     r8, asc_14008F5A4; "h"
0x1400691c1  shr     rsi, 1Fh
0x1400691c5  mov     rdx, r13; unsigned __int64
0x1400691c8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1400691cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400691d2  test    esi, esi
0x1400691d4  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400691dc  lea     r9, [rsp+288h+Name]; lpName
0x1400691e1  mov     [rsp+288h+dwFlags], r12d; int
0x1400691e6  cmovnz  ebp, esi
0x1400691e9  mov     edx, esi; lInitialCount
0x1400691eb  mov     r8d, ebp; lMaximumCount
0x1400691ee  xor     ecx, ecx; lpSemaphoreAttributes
0x1400691f0  call    cs:__imp_CreateSemaphoreExW
0x1400691f6  mov     rbp, rax
0x1400691f9  test    rax, rax
0x1400691fc  jnz     short loc_140069222
0x1400691fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140069203  mov     ebx, eax
0x140069205  test    eax, eax
0x140069207  jns     short loc_140069252
0x140069209  mov     rcx, [rsp+288h]; this
0x140069211  mov     r9d, eax; char *
0x140069214  mov     edx, 90h; void *
0x140069219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006921e  mov     eax, ebx
0x140069220  jmp     short loc_140069254
0x140069222  call    cs:__imp_GetLastError
0x140069228  mov     rdi, [rbx+8]
0x14006922c  test    rdi, rdi
0x14006922f  jz      short loc_14006924E
0x140069231  call    cs:__imp_GetLastError
0x140069237  mov     rcx, rdi; hObject
0x14006923a  mov     esi, eax
0x14006923c  call    cs:__imp_CloseHandle
0x140069242  test    eax, eax
0x140069244  jz      short loc_14006927F
0x140069246  mov     ecx, esi; dwErrCode
0x140069248  call    cs:__imp_SetLastError
0x14006924e  mov     [rbx+8], rbp
0x140069252  xor     eax, eax
0x140069254  mov     rcx, [rsp+288h+var_48]
0x14006925c  xor     rcx, rsp; StackCookie
0x14006925f  call    __security_check_cookie
0x140069264  mov     rbx, [rsp+288h+arg_8]
0x14006926c  add     rsp, 250h
0x140069273  pop     r15
0x140069275  pop     r14
0x140069277  pop     r13
0x140069279  pop     r12
0x14006927b  pop     rdi
0x14006927c  pop     rsi
0x14006927d  pop     rbp
0x14006927e  retn
0x14006927f  mov     rcx, [rsp+288h]; this
0x140069287  mov     edx, 0A0Bh; void *
0x14006928c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140069292  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140069298  mov     rcx, [rsp+288h]; this
0x1400692a0  mov     edx, 0A0Bh; void *
0x1400692a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005860`
- end: `0x180005a98`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005480`
- `0x18000f4c8`

## callees

- `0x180005860`
- `0x1800062e8`
- `0x180007674`
- `0x180007df4`
- `0x18000863c`
- `0x18000864c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005924`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800059c7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005924`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800059c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000598b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000598b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000597a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000597a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a1a`

## string_xrefs

- `0x180005a66`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005a86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
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
0x180005860  mov     [rsp+arg_8], rbx
0x180005865  mov     [rsp+arg_10], rbp
0x18000586a  push    rsi
0x18000586b  push    rdi
0x18000586c  push    r12
0x18000586e  push    r14
0x180005870  push    r15
0x180005872  sub     rsp, 250h
0x180005879  mov     rax, cs:__security_cookie
0x180005880  xor     rax, rsp
0x180005883  mov     [rsp+278h+var_38], rax
0x18000588b  mov     rax, 0C000000000000000h
0x180005895  mov     rbp, r9
0x180005898  mov     r8, rdx
0x18000589b  mov     rbx, rcx
0x18000589e  test    rax, r9
0x1800058a1  jnz     loc_180005A78
0x1800058a7  xor     r12d, r12d
0x1800058aa  lea     rax, [rsp+278h+Name]
0x1800058af  mov     ecx, 7FFFFFFEh
0x1800058b4  mov     edx, 104h
0x1800058b9  lea     esi, [r12+1]
0x1800058be  test    rcx, rcx
0x1800058c1  jz      short loc_1800058E1
0x1800058c3  movzx   r9d, word ptr [r8]
0x1800058c7  test    r9w, r9w
0x1800058cb  jz      short loc_1800058E1
0x1800058cd  mov     [rax], r9w
0x1800058d1  add     r8, 2
0x1800058d5  add     rax, 2
0x1800058d9  sub     rcx, rsi
0x1800058dc  sub     rdx, rsi; unsigned __int64
0x1800058df  jnz     short loc_1800058BE
0x1800058e1  test    rdx, rdx
0x1800058e4  lea     rcx, [rax-2]
0x1800058e8  lea     r8, aP0; "_p0"
0x1800058ef  cmovnz  rcx, rax
0x1800058f3  mov     [rcx], r12w
0x1800058f7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800058fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005901  mov     edx, ebp
0x180005903  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000590b  and     edx, 7FFFFFFFh; lInitialCount
0x180005911  mov     [rsp+278h+dwFlags], r12d; int
0x180005916  mov     r8d, esi
0x180005919  lea     r9, [rsp+278h+Name]; lpName
0x18000591e  cmova   r8d, edx; lMaximumCount
0x180005922  xor     ecx, ecx; lpSemaphoreAttributes
0x180005924  call    cs:__imp_CreateSemaphoreExW
0x18000592a  mov     r15, rax
0x18000592d  test    rax, rax
0x180005930  jnz     short loc_180005960
0x180005932  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005937  mov     edi, eax
0x180005939  test    eax, eax
0x18000593b  jns     short loc_180005994
0x18000593d  mov     rcx, [rsp+278h]; this
0x180005945  lea     r8, aWil; "wil"
0x18000594c  mov     r9d, eax; char *
0x18000594f  mov     edx, 8Bh; void *
0x180005954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005959  mov     eax, edi
0x18000595b  jmp     loc_180005A32
0x180005960  call    cs:__imp_GetLastError
0x180005966  mov     rdi, [rbx]
0x180005969  test    rdi, rdi
0x18000596c  jz      short loc_180005991
0x18000596e  call    cs:__imp_GetLastError
0x180005974  mov     rcx, rdi; hObject
0x180005977  mov     r14d, eax
0x18000597a  call    cs:__imp_CloseHandle
0x180005980  test    eax, eax
0x180005982  jz      loc_180005A7E
0x180005988  mov     ecx, r14d; dwErrCode
0x18000598b  call    cs:__imp_SetLastError
0x180005991  mov     [rbx], r15
0x180005994  lea     r8, asc_18003A648; "h"
0x18000599b  shr     rbp, 1Fh
0x18000599f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800059a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800059a9  test    ebp, ebp
0x1800059ab  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800059b3  lea     r9, [rsp+278h+Name]; lpName
0x1800059b8  mov     [rsp+278h+dwFlags], r12d; int
0x1800059bd  cmovnz  esi, ebp
0x1800059c0  mov     edx, ebp; lInitialCount
0x1800059c2  mov     r8d, esi; lMaximumCount
0x1800059c5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800059c7  call    cs:__imp_CreateSemaphoreExW
0x1800059cd  mov     rsi, rax
0x1800059d0  test    rax, rax
0x1800059d3  jnz     short loc_180005A00
0x1800059d5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800059da  mov     ebx, eax
0x1800059dc  test    eax, eax
0x1800059de  jns     short loc_180005A30
0x1800059e0  mov     rcx, [rsp+278h]; this
0x1800059e8  lea     r8, aWil; "wil"
0x1800059ef  mov     r9d, eax; char *
0x1800059f2  mov     edx, 90h; void *
0x1800059f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059fc  mov     eax, ebx
0x1800059fe  jmp     short loc_180005A32
0x180005a00  call    cs:__imp_GetLastError
0x180005a06  mov     rdi, [rbx+8]
0x180005a0a  test    rdi, rdi
0x180005a0d  jz      short loc_180005A2C
0x180005a0f  call    cs:__imp_GetLastError
0x180005a15  mov     rcx, rdi; hObject
0x180005a18  mov     ebp, eax
0x180005a1a  call    cs:__imp_CloseHandle
0x180005a20  test    eax, eax
0x180005a22  jz      short loc_180005A5E
0x180005a24  mov     ecx, ebp; dwErrCode
0x180005a26  call    cs:__imp_SetLastError
0x180005a2c  mov     [rbx+8], rsi
0x180005a30  xor     eax, eax
0x180005a32  mov     rcx, [rsp+278h+var_38]
0x180005a3a  xor     rcx, rsp; StackCookie
0x180005a3d  call    __security_check_cookie
0x180005a42  lea     r11, [rsp+278h+var_28]
0x180005a4a  mov     rbx, [r11+38h]
0x180005a4e  mov     rbp, [r11+40h]
0x180005a52  mov     rsp, r11
0x180005a55  pop     r15
0x180005a57  pop     r14
0x180005a59  pop     r12
0x180005a5b  pop     rdi
0x180005a5c  pop     rsi
0x180005a5d  retn
0x180005a5e  mov     rcx, [rsp+278h]; this
0x180005a66  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005a6d  mov     edx, 0A0Bh; void *
0x180005a72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005a7e  mov     rcx, [rsp+278h]; this
0x180005a86  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005a8d  mov     edx, 0A0Bh; void *
0x180005a92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

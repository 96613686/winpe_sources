# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004650`
- end: `0x180004888`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003fd0`

## callees

- `0x180001550`
- `0x180004650`
- `0x180004ef8`
- `0x1800066e4`
- `0x180006a34`
- `0x180006ffc`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004714`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800047b7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004714`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800047b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000475e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000475e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000477b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000477b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004816`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000476a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000480a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000476a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000480a`

## string_xrefs

- `0x180004856`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004876`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x180004650  mov     [rsp+arg_8], rbx
0x180004655  mov     [rsp+arg_10], rbp
0x18000465a  push    rsi
0x18000465b  push    rdi
0x18000465c  push    r12
0x18000465e  push    r14
0x180004660  push    r15
0x180004662  sub     rsp, 250h
0x180004669  mov     rax, cs:__security_cookie
0x180004670  xor     rax, rsp
0x180004673  mov     [rsp+278h+var_38], rax
0x18000467b  mov     rax, 0C000000000000000h
0x180004685  mov     rbp, r9
0x180004688  mov     r8, rdx
0x18000468b  mov     rbx, rcx
0x18000468e  test    rax, r9
0x180004691  jnz     loc_180004868
0x180004697  xor     r12d, r12d
0x18000469a  lea     rax, [rsp+278h+Name]
0x18000469f  mov     ecx, 7FFFFFFEh
0x1800046a4  mov     edx, 104h
0x1800046a9  lea     esi, [r12+1]
0x1800046ae  test    rcx, rcx
0x1800046b1  jz      short loc_1800046D1
0x1800046b3  movzx   r9d, word ptr [r8]
0x1800046b7  test    r9w, r9w
0x1800046bb  jz      short loc_1800046D1
0x1800046bd  mov     [rax], r9w
0x1800046c1  add     r8, 2
0x1800046c5  add     rax, 2
0x1800046c9  sub     rcx, rsi
0x1800046cc  sub     rdx, rsi; unsigned __int64
0x1800046cf  jnz     short loc_1800046AE
0x1800046d1  test    rdx, rdx
0x1800046d4  lea     rcx, [rax-2]
0x1800046d8  lea     r8, aP0; "_p0"
0x1800046df  cmovnz  rcx, rax
0x1800046e3  mov     [rcx], r12w
0x1800046e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800046ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800046f1  mov     edx, ebp
0x1800046f3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800046fb  and     edx, 7FFFFFFFh; lInitialCount
0x180004701  mov     [rsp+278h+dwFlags], r12d; int
0x180004706  mov     r8d, esi
0x180004709  lea     r9, [rsp+278h+Name]; lpName
0x18000470e  cmova   r8d, edx; lMaximumCount
0x180004712  xor     ecx, ecx; lpSemaphoreAttributes
0x180004714  call    cs:__imp_CreateSemaphoreExW
0x18000471a  mov     r15, rax
0x18000471d  test    rax, rax
0x180004720  jnz     short loc_180004750
0x180004722  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004727  mov     edi, eax
0x180004729  test    eax, eax
0x18000472b  jns     short loc_180004784
0x18000472d  mov     rcx, [rsp+278h]; this
0x180004735  lea     r8, aWil; "wil"
0x18000473c  mov     r9d, eax; char *
0x18000473f  mov     edx, 8Bh; void *
0x180004744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004749  mov     eax, edi
0x18000474b  jmp     loc_180004822
0x180004750  call    cs:__imp_GetLastError
0x180004756  mov     rdi, [rbx]
0x180004759  test    rdi, rdi
0x18000475c  jz      short loc_180004781
0x18000475e  call    cs:__imp_GetLastError
0x180004764  mov     rcx, rdi; hObject
0x180004767  mov     r14d, eax
0x18000476a  call    cs:__imp_CloseHandle
0x180004770  test    eax, eax
0x180004772  jz      loc_18000486E
0x180004778  mov     ecx, r14d; dwErrCode
0x18000477b  call    cs:__imp_SetLastError
0x180004781  mov     [rbx], r15
0x180004784  lea     r8, asc_180014CA8; "h"
0x18000478b  shr     rbp, 1Fh
0x18000478f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004794  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004799  test    ebp, ebp
0x18000479b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800047a3  lea     r9, [rsp+278h+Name]; lpName
0x1800047a8  mov     [rsp+278h+dwFlags], r12d; int
0x1800047ad  cmovnz  esi, ebp
0x1800047b0  mov     edx, ebp; lInitialCount
0x1800047b2  mov     r8d, esi; lMaximumCount
0x1800047b5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800047b7  call    cs:__imp_CreateSemaphoreExW
0x1800047bd  mov     rsi, rax
0x1800047c0  test    rax, rax
0x1800047c3  jnz     short loc_1800047F0
0x1800047c5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800047ca  mov     ebx, eax
0x1800047cc  test    eax, eax
0x1800047ce  jns     short loc_180004820
0x1800047d0  mov     rcx, [rsp+278h]; this
0x1800047d8  lea     r8, aWil; "wil"
0x1800047df  mov     r9d, eax; char *
0x1800047e2  mov     edx, 90h; void *
0x1800047e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047ec  mov     eax, ebx
0x1800047ee  jmp     short loc_180004822
0x1800047f0  call    cs:__imp_GetLastError
0x1800047f6  mov     rdi, [rbx+8]
0x1800047fa  test    rdi, rdi
0x1800047fd  jz      short loc_18000481C
0x1800047ff  call    cs:__imp_GetLastError
0x180004805  mov     rcx, rdi; hObject
0x180004808  mov     ebp, eax
0x18000480a  call    cs:__imp_CloseHandle
0x180004810  test    eax, eax
0x180004812  jz      short loc_18000484E
0x180004814  mov     ecx, ebp; dwErrCode
0x180004816  call    cs:__imp_SetLastError
0x18000481c  mov     [rbx+8], rsi
0x180004820  xor     eax, eax
0x180004822  mov     rcx, [rsp+278h+var_38]
0x18000482a  xor     rcx, rsp; StackCookie
0x18000482d  call    __security_check_cookie
0x180004832  lea     r11, [rsp+278h+var_28]
0x18000483a  mov     rbx, [r11+38h]
0x18000483e  mov     rbp, [r11+40h]
0x180004842  mov     rsp, r11
0x180004845  pop     r15
0x180004847  pop     r14
0x180004849  pop     r12
0x18000484b  pop     rdi
0x18000484c  pop     rsi
0x18000484d  retn
0x18000484e  mov     rcx, [rsp+278h]; this
0x180004856  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000485d  mov     edx, 0A0Bh; void *
0x180004862  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004868  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000486e  mov     rcx, [rsp+278h]; this
0x180004876  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000487d  mov     edx, 0A0Bh; void *
0x180004882  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800079c4`
- end: `0x180007bee`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800075e8`
- `0x180011efc`

## callees

- `0x1800079c4`
- `0x1800085a8`
- `0x1800098dc`
- `0x18000a048`
- `0x18000ad08`
- `0x18000ad18`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007a88`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007b2b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007a88`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007b2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800079c4  mov     [rsp+arg_8], rbx
0x1800079c9  mov     [rsp+arg_10], rbp
0x1800079ce  push    rsi
0x1800079cf  push    rdi
0x1800079d0  push    r12
0x1800079d2  push    r14
0x1800079d4  push    r15
0x1800079d6  sub     rsp, 250h
0x1800079dd  mov     rax, cs:__security_cookie
0x1800079e4  xor     rax, rsp
0x1800079e7  mov     [rsp+278h+var_38], rax
0x1800079ef  mov     rax, 0C000000000000000h
0x1800079f9  mov     rbp, r9
0x1800079fc  mov     r8, rdx
0x1800079ff  mov     rbx, rcx
0x180007a02  test    rax, r9
0x180007a05  jnz     loc_180007BD5
0x180007a0b  xor     r12d, r12d
0x180007a0e  lea     rax, [rsp+278h+Name]
0x180007a13  mov     ecx, 7FFFFFFEh
0x180007a18  mov     edx, 104h
0x180007a1d  lea     esi, [r12+1]
0x180007a22  test    rcx, rcx
0x180007a25  jz      short loc_180007A45
0x180007a27  movzx   r9d, word ptr [r8]
0x180007a2b  test    r9w, r9w
0x180007a2f  jz      short loc_180007A45
0x180007a31  mov     [rax], r9w
0x180007a35  add     r8, 2
0x180007a39  add     rax, 2
0x180007a3d  sub     rcx, rsi
0x180007a40  sub     rdx, rsi; unsigned __int64
0x180007a43  jnz     short loc_180007A22
0x180007a45  test    rdx, rdx
0x180007a48  lea     rcx, [rax-2]
0x180007a4c  lea     r8, aP0; "_p0"
0x180007a53  cmovnz  rcx, rax
0x180007a57  mov     [rcx], r12w
0x180007a5b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007a60  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007a65  mov     edx, ebp
0x180007a67  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007a6f  and     edx, 7FFFFFFFh; lInitialCount
0x180007a75  mov     [rsp+278h+dwFlags], r12d; int
0x180007a7a  mov     r8d, esi
0x180007a7d  lea     r9, [rsp+278h+Name]; lpName
0x180007a82  cmova   r8d, edx; lMaximumCount
0x180007a86  xor     ecx, ecx; lpSemaphoreAttributes
0x180007a88  call    cs:__imp_CreateSemaphoreExW
0x180007a8e  mov     r15, rax
0x180007a91  test    rax, rax
0x180007a94  jnz     short loc_180007AC4
0x180007a96  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007a9b  mov     edi, eax
0x180007a9d  test    eax, eax
0x180007a9f  jns     short loc_180007AF8
0x180007aa1  mov     rcx, [rsp+278h]; this
0x180007aa9  lea     r8, aWil; "wil"
0x180007ab0  mov     r9d, eax; char *
0x180007ab3  mov     edx, 8Bh; void *
0x180007ab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007abd  mov     eax, edi
0x180007abf  jmp     loc_180007B96
0x180007ac4  call    cs:__imp_GetLastError
0x180007aca  mov     rdi, [rbx]
0x180007acd  test    rdi, rdi
0x180007ad0  jz      short loc_180007AF5
0x180007ad2  call    cs:__imp_GetLastError
0x180007ad8  mov     rcx, rdi; hObject
0x180007adb  mov     r14d, eax
0x180007ade  call    cs:__imp_CloseHandle
0x180007ae4  test    eax, eax
0x180007ae6  jz      loc_180007BDB
0x180007aec  mov     ecx, r14d; dwErrCode
0x180007aef  call    cs:__imp_SetLastError
0x180007af5  mov     [rbx], r15
0x180007af8  lea     r8, asc_18004B1C8; "h"
0x180007aff  shr     rbp, 1Fh
0x180007b03  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007b08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007b0d  test    ebp, ebp
0x180007b0f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007b17  lea     r9, [rsp+278h+Name]; lpName
0x180007b1c  mov     [rsp+278h+dwFlags], r12d; int
0x180007b21  cmovnz  esi, ebp
0x180007b24  mov     edx, ebp; lInitialCount
0x180007b26  mov     r8d, esi; lMaximumCount
0x180007b29  xor     ecx, ecx; lpSemaphoreAttributes
0x180007b2b  call    cs:__imp_CreateSemaphoreExW
0x180007b31  mov     rsi, rax
0x180007b34  test    rax, rax
0x180007b37  jnz     short loc_180007B64
0x180007b39  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007b3e  mov     ebx, eax
0x180007b40  test    eax, eax
0x180007b42  jns     short loc_180007B94
0x180007b44  mov     rcx, [rsp+278h]; this
0x180007b4c  lea     r8, aWil; "wil"
0x180007b53  mov     r9d, eax; char *
0x180007b56  mov     edx, 90h; void *
0x180007b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b60  mov     eax, ebx
0x180007b62  jmp     short loc_180007B96
0x180007b64  call    cs:__imp_GetLastError
0x180007b6a  mov     rdi, [rbx+8]
0x180007b6e  test    rdi, rdi
0x180007b71  jz      short loc_180007B90
0x180007b73  call    cs:__imp_GetLastError
0x180007b79  mov     rcx, rdi; hObject
0x180007b7c  mov     ebp, eax
0x180007b7e  call    cs:__imp_CloseHandle
0x180007b84  test    eax, eax
0x180007b86  jz      short loc_180007BC2
0x180007b88  mov     ecx, ebp; dwErrCode
0x180007b8a  call    cs:__imp_SetLastError
0x180007b90  mov     [rbx+8], rsi
0x180007b94  xor     eax, eax
0x180007b96  mov     rcx, [rsp+278h+var_38]
0x180007b9e  xor     rcx, rsp; StackCookie
0x180007ba1  call    __security_check_cookie
0x180007ba6  lea     r11, [rsp+278h+var_28]
0x180007bae  mov     rbx, [r11+38h]
0x180007bb2  mov     rbp, [r11+40h]
0x180007bb6  mov     rsp, r11
0x180007bb9  pop     r15
0x180007bbb  pop     r14
0x180007bbd  pop     r12
0x180007bbf  pop     rdi
0x180007bc0  pop     rsi
0x180007bc1  retn
0x180007bc2  mov     rcx, [rsp+278h]; this
0x180007bca  mov     edx, 0A0Bh; void *
0x180007bcf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bd5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007bdb  mov     rcx, [rsp+278h]; this
0x180007be3  mov     edx, 0A0Bh; void *
0x180007be8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

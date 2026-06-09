# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cc94`
- end: `0x18000ceb7`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c8ec`

## callees

- `0x180001f90`
- `0x180007988`
- `0x18000cc94`
- `0x18000d518`
- `0x18000ef34`
- `0x180010398`
- `0x1800103a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce54`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000cd5d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000cdfc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000cd5d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000cdfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce48`

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
0x18000cc94  mov     [rsp+arg_8], rbx
0x18000cc99  push    rbp
0x18000cc9a  push    rsi
0x18000cc9b  push    rdi
0x18000cc9c  push    r12
0x18000cc9e  push    r13
0x18000cca0  push    r14
0x18000cca2  push    r15
0x18000cca4  sub     rsp, 250h
0x18000ccab  mov     rax, cs:__security_cookie
0x18000ccb2  xor     rax, rsp
0x18000ccb5  mov     [rsp+288h+var_48], rax
0x18000ccbd  mov     rax, 0C000000000000000h
0x18000ccc7  mov     rsi, r9
0x18000ccca  mov     r8, rdx
0x18000cccd  mov     rbx, rcx
0x18000ccd0  test    rax, r9
0x18000ccd3  jnz     loc_18000CE9E
0x18000ccd9  xor     r12d, r12d
0x18000ccdc  lea     rax, [rsp+288h+Name]
0x18000cce1  mov     r13d, 104h
0x18000cce7  mov     ecx, 7FFFFFFEh
0x18000ccec  mov     edx, r13d
0x18000ccef  lea     ebp, [r12+1]
0x18000ccf4  test    rcx, rcx
0x18000ccf7  jz      short loc_18000CD17
0x18000ccf9  movzx   r9d, word ptr [r8]
0x18000ccfd  test    r9w, r9w
0x18000cd01  jz      short loc_18000CD17
0x18000cd03  mov     [rax], r9w
0x18000cd07  add     r8, 2
0x18000cd0b  add     rax, 2
0x18000cd0f  sub     rcx, rbp
0x18000cd12  sub     rdx, rbp
0x18000cd15  jnz     short loc_18000CCF4
0x18000cd17  test    rdx, rdx
0x18000cd1a  lea     rcx, [rax-2]
0x18000cd1e  lea     r8, aP0; "_p0"
0x18000cd25  mov     rdx, r13; unsigned __int64
0x18000cd28  cmovnz  rcx, rax
0x18000cd2c  mov     [rcx], r12w
0x18000cd30  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000cd35  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd3a  mov     edx, esi
0x18000cd3c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000cd44  and     edx, 7FFFFFFFh; lInitialCount
0x18000cd4a  mov     [rsp+288h+dwFlags], r12d; int
0x18000cd4f  mov     r8d, ebp
0x18000cd52  lea     r9, [rsp+288h+Name]; lpName
0x18000cd57  cmova   r8d, edx; lMaximumCount
0x18000cd5b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000cd5d  call    cs:__imp_CreateSemaphoreExW
0x18000cd63  mov     r15, rax
0x18000cd66  test    rax, rax
0x18000cd69  jnz     short loc_18000CD92
0x18000cd6b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000cd70  mov     edi, eax
0x18000cd72  test    eax, eax
0x18000cd74  jns     short loc_18000CDC6
0x18000cd76  mov     rcx, [rsp+288h]; this
0x18000cd7e  mov     r9d, eax; char *
0x18000cd81  mov     edx, 8Bh; void *
0x18000cd86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd8b  mov     eax, edi
0x18000cd8d  jmp     loc_18000CE60
0x18000cd92  call    cs:__imp_GetLastError
0x18000cd98  mov     rdi, [rbx]
0x18000cd9b  test    rdi, rdi
0x18000cd9e  jz      short loc_18000CDC3
0x18000cda0  call    cs:__imp_GetLastError
0x18000cda6  mov     rcx, rdi; hObject
0x18000cda9  mov     r14d, eax
0x18000cdac  call    cs:__imp_CloseHandle
0x18000cdb2  test    eax, eax
0x18000cdb4  jz      loc_18000CEA4
0x18000cdba  mov     ecx, r14d; dwErrCode
0x18000cdbd  call    cs:__imp_SetLastError
0x18000cdc3  mov     [rbx], r15
0x18000cdc6  lea     r8, asc_1800157E0; "h"
0x18000cdcd  shr     rsi, 1Fh
0x18000cdd1  mov     rdx, r13; unsigned __int64
0x18000cdd4  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000cdd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cdde  test    esi, esi
0x18000cde0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000cde8  lea     r9, [rsp+288h+Name]; lpName
0x18000cded  mov     [rsp+288h+dwFlags], r12d; int
0x18000cdf2  cmovnz  ebp, esi
0x18000cdf5  mov     edx, esi; lInitialCount
0x18000cdf7  mov     r8d, ebp; lMaximumCount
0x18000cdfa  xor     ecx, ecx; lpSemaphoreAttributes
0x18000cdfc  call    cs:__imp_CreateSemaphoreExW
0x18000ce02  mov     rbp, rax
0x18000ce05  test    rax, rax
0x18000ce08  jnz     short loc_18000CE2E
0x18000ce0a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ce0f  mov     ebx, eax
0x18000ce11  test    eax, eax
0x18000ce13  jns     short loc_18000CE5E
0x18000ce15  mov     rcx, [rsp+288h]; this
0x18000ce1d  mov     r9d, eax; char *
0x18000ce20  mov     edx, 90h; void *
0x18000ce25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce2a  mov     eax, ebx
0x18000ce2c  jmp     short loc_18000CE60
0x18000ce2e  call    cs:__imp_GetLastError
0x18000ce34  mov     rdi, [rbx+8]
0x18000ce38  test    rdi, rdi
0x18000ce3b  jz      short loc_18000CE5A
0x18000ce3d  call    cs:__imp_GetLastError
0x18000ce43  mov     rcx, rdi; hObject
0x18000ce46  mov     esi, eax
0x18000ce48  call    cs:__imp_CloseHandle
0x18000ce4e  test    eax, eax
0x18000ce50  jz      short loc_18000CE8B
0x18000ce52  mov     ecx, esi; dwErrCode
0x18000ce54  call    cs:__imp_SetLastError
0x18000ce5a  mov     [rbx+8], rbp
0x18000ce5e  xor     eax, eax
0x18000ce60  mov     rcx, [rsp+288h+var_48]
0x18000ce68  xor     rcx, rsp; StackCookie
0x18000ce6b  call    __security_check_cookie
0x18000ce70  mov     rbx, [rsp+288h+arg_8]
0x18000ce78  add     rsp, 250h
0x18000ce7f  pop     r15
0x18000ce81  pop     r14
0x18000ce83  pop     r13
0x18000ce85  pop     r12
0x18000ce87  pop     rdi
0x18000ce88  pop     rsi
0x18000ce89  pop     rbp
0x18000ce8a  retn
0x18000ce8b  mov     rcx, [rsp+288h]; this
0x18000ce93  mov     edx, 0A0Bh; void *
0x18000ce98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ce9e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cea4  mov     rcx, [rsp+288h]; this
0x18000ceac  mov     edx, 0A0Bh; void *
0x18000ceb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

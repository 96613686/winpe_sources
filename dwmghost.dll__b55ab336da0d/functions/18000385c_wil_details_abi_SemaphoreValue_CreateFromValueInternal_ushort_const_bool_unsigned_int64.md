# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000385c`
- end: `0x180003a7f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800034ac`

## callees

- `0x180001190`
- `0x18000385c`
- `0x180004038`
- `0x180004e14`
- `0x1800051b0`
- `0x1800056fc`
- `0x18000570c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800039c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800039c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000395a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000395a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a10`

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
0x18000385c  mov     [rsp+arg_8], rbx
0x180003861  push    rbp
0x180003862  push    rsi
0x180003863  push    rdi
0x180003864  push    r12
0x180003866  push    r13
0x180003868  push    r14
0x18000386a  push    r15
0x18000386c  sub     rsp, 250h
0x180003873  mov     rax, cs:__security_cookie
0x18000387a  xor     rax, rsp
0x18000387d  mov     [rsp+288h+var_48], rax
0x180003885  mov     rax, 0C000000000000000h
0x18000388f  mov     rsi, r9
0x180003892  mov     r8, rdx
0x180003895  mov     rbx, rcx
0x180003898  test    rax, r9
0x18000389b  jnz     loc_180003A66
0x1800038a1  xor     r12d, r12d
0x1800038a4  lea     rax, [rsp+288h+Name]
0x1800038a9  mov     r13d, 104h
0x1800038af  mov     ecx, 7FFFFFFEh
0x1800038b4  mov     edx, r13d
0x1800038b7  lea     ebp, [r12+1]
0x1800038bc  test    rcx, rcx
0x1800038bf  jz      short loc_1800038DF
0x1800038c1  movzx   r9d, word ptr [r8]
0x1800038c5  test    r9w, r9w
0x1800038c9  jz      short loc_1800038DF
0x1800038cb  mov     [rax], r9w
0x1800038cf  add     r8, 2
0x1800038d3  add     rax, 2
0x1800038d7  sub     rcx, rbp
0x1800038da  sub     rdx, rbp
0x1800038dd  jnz     short loc_1800038BC
0x1800038df  test    rdx, rdx
0x1800038e2  lea     rcx, [rax-2]
0x1800038e6  lea     r8, aP0; "_p0"
0x1800038ed  mov     rdx, r13; unsigned __int64
0x1800038f0  cmovnz  rcx, rax
0x1800038f4  mov     [rcx], r12w
0x1800038f8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800038fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003902  mov     edx, esi
0x180003904  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000390c  and     edx, 7FFFFFFFh; lInitialCount
0x180003912  mov     [rsp+288h+dwFlags], r12d; int
0x180003917  mov     r8d, ebp
0x18000391a  lea     r9, [rsp+288h+Name]; lpName
0x18000391f  cmova   r8d, edx; lMaximumCount
0x180003923  xor     ecx, ecx; lpSemaphoreAttributes
0x180003925  call    cs:__imp_CreateSemaphoreExW
0x18000392b  mov     r15, rax
0x18000392e  test    rax, rax
0x180003931  jnz     short loc_18000395A
0x180003933  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003938  mov     edi, eax
0x18000393a  test    eax, eax
0x18000393c  jns     short loc_18000398E
0x18000393e  mov     rcx, [rsp+288h]; this
0x180003946  mov     r9d, eax; char *
0x180003949  mov     edx, 8Bh; void *
0x18000394e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003953  mov     eax, edi
0x180003955  jmp     loc_180003A28
0x18000395a  call    cs:__imp_GetLastError
0x180003960  mov     rdi, [rbx]
0x180003963  test    rdi, rdi
0x180003966  jz      short loc_18000398B
0x180003968  call    cs:__imp_GetLastError
0x18000396e  mov     rcx, rdi; hObject
0x180003971  mov     r14d, eax
0x180003974  call    cs:__imp_CloseHandle
0x18000397a  test    eax, eax
0x18000397c  jz      loc_180003A6C
0x180003982  mov     ecx, r14d; dwErrCode
0x180003985  call    cs:__imp_SetLastError
0x18000398b  mov     [rbx], r15
0x18000398e  lea     r8, asc_18000E3A0; "h"
0x180003995  shr     rsi, 1Fh
0x180003999  mov     rdx, r13; unsigned __int64
0x18000399c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800039a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800039a6  test    esi, esi
0x1800039a8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800039b0  lea     r9, [rsp+288h+Name]; lpName
0x1800039b5  mov     [rsp+288h+dwFlags], r12d; int
0x1800039ba  cmovnz  ebp, esi
0x1800039bd  mov     edx, esi; lInitialCount
0x1800039bf  mov     r8d, ebp; lMaximumCount
0x1800039c2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800039c4  call    cs:__imp_CreateSemaphoreExW
0x1800039ca  mov     rbp, rax
0x1800039cd  test    rax, rax
0x1800039d0  jnz     short loc_1800039F6
0x1800039d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800039d7  mov     ebx, eax
0x1800039d9  test    eax, eax
0x1800039db  jns     short loc_180003A26
0x1800039dd  mov     rcx, [rsp+288h]; this
0x1800039e5  mov     r9d, eax; char *
0x1800039e8  mov     edx, 90h; void *
0x1800039ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039f2  mov     eax, ebx
0x1800039f4  jmp     short loc_180003A28
0x1800039f6  call    cs:__imp_GetLastError
0x1800039fc  mov     rdi, [rbx+8]
0x180003a00  test    rdi, rdi
0x180003a03  jz      short loc_180003A22
0x180003a05  call    cs:__imp_GetLastError
0x180003a0b  mov     rcx, rdi; hObject
0x180003a0e  mov     esi, eax
0x180003a10  call    cs:__imp_CloseHandle
0x180003a16  test    eax, eax
0x180003a18  jz      short loc_180003A53
0x180003a1a  mov     ecx, esi; dwErrCode
0x180003a1c  call    cs:__imp_SetLastError
0x180003a22  mov     [rbx+8], rbp
0x180003a26  xor     eax, eax
0x180003a28  mov     rcx, [rsp+288h+var_48]
0x180003a30  xor     rcx, rsp; StackCookie
0x180003a33  call    __security_check_cookie
0x180003a38  mov     rbx, [rsp+288h+arg_8]
0x180003a40  add     rsp, 250h
0x180003a47  pop     r15
0x180003a49  pop     r14
0x180003a4b  pop     r13
0x180003a4d  pop     r12
0x180003a4f  pop     rdi
0x180003a50  pop     rsi
0x180003a51  pop     rbp
0x180003a52  retn
0x180003a53  mov     rcx, [rsp+288h]; this
0x180003a5b  mov     edx, 0A0Bh; void *
0x180003a60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a6c  mov     rcx, [rsp+288h]; this
0x180003a74  mov     edx, 0A0Bh; void *
0x180003a79  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

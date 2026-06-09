# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003888`
- end: `0x180003ab2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800034b8`

## callees

- `0x180001520`
- `0x180003888`
- `0x1800042b8`
- `0x180005224`
- `0x180005b00`
- `0x18000602c`
- `0x18000603c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a4e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000394c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800039ef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000394c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800039ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a42`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x180003888  mov     [rsp+arg_8], rbx
0x18000388d  mov     [rsp+arg_10], rbp
0x180003892  push    rsi
0x180003893  push    rdi
0x180003894  push    r12
0x180003896  push    r14
0x180003898  push    r15
0x18000389a  sub     rsp, 250h
0x1800038a1  mov     rax, cs:__security_cookie
0x1800038a8  xor     rax, rsp
0x1800038ab  mov     [rsp+278h+var_38], rax
0x1800038b3  mov     rax, 0C000000000000000h
0x1800038bd  mov     rbp, r9
0x1800038c0  mov     r8, rdx
0x1800038c3  mov     rbx, rcx
0x1800038c6  test    rax, r9
0x1800038c9  jnz     loc_180003A99
0x1800038cf  xor     r12d, r12d
0x1800038d2  lea     rax, [rsp+278h+Name]
0x1800038d7  mov     ecx, 7FFFFFFEh
0x1800038dc  mov     edx, 104h
0x1800038e1  lea     esi, [r12+1]
0x1800038e6  test    rcx, rcx
0x1800038e9  jz      short loc_180003909
0x1800038eb  movzx   r9d, word ptr [r8]
0x1800038ef  test    r9w, r9w
0x1800038f3  jz      short loc_180003909
0x1800038f5  mov     [rax], r9w
0x1800038f9  add     r8, 2
0x1800038fd  add     rax, 2
0x180003901  sub     rcx, rsi
0x180003904  sub     rdx, rsi; unsigned __int64
0x180003907  jnz     short loc_1800038E6
0x180003909  test    rdx, rdx
0x18000390c  lea     rcx, [rax-2]
0x180003910  lea     r8, aP0; "_p0"
0x180003917  cmovnz  rcx, rax
0x18000391b  mov     [rcx], r12w
0x18000391f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003924  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003929  mov     edx, ebp
0x18000392b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003933  and     edx, 7FFFFFFFh; lInitialCount
0x180003939  mov     [rsp+278h+dwFlags], r12d; int
0x18000393e  mov     r8d, esi
0x180003941  lea     r9, [rsp+278h+Name]; lpName
0x180003946  cmova   r8d, edx; lMaximumCount
0x18000394a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000394c  call    cs:__imp_CreateSemaphoreExW
0x180003952  mov     r15, rax
0x180003955  test    rax, rax
0x180003958  jnz     short loc_180003988
0x18000395a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000395f  mov     edi, eax
0x180003961  test    eax, eax
0x180003963  jns     short loc_1800039BC
0x180003965  mov     rcx, [rsp+278h]; this
0x18000396d  lea     r8, aWil; "wil"
0x180003974  mov     r9d, eax; char *
0x180003977  mov     edx, 8Bh; void *
0x18000397c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003981  mov     eax, edi
0x180003983  jmp     loc_180003A5A
0x180003988  call    cs:__imp_GetLastError
0x18000398e  mov     rdi, [rbx]
0x180003991  test    rdi, rdi
0x180003994  jz      short loc_1800039B9
0x180003996  call    cs:__imp_GetLastError
0x18000399c  mov     rcx, rdi; hObject
0x18000399f  mov     r14d, eax
0x1800039a2  call    cs:__imp_CloseHandle
0x1800039a8  test    eax, eax
0x1800039aa  jz      loc_180003A9F
0x1800039b0  mov     ecx, r14d; dwErrCode
0x1800039b3  call    cs:__imp_SetLastError
0x1800039b9  mov     [rbx], r15
0x1800039bc  lea     r8, asc_1800099A8; "h"
0x1800039c3  shr     rbp, 1Fh
0x1800039c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800039cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800039d1  test    ebp, ebp
0x1800039d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800039db  lea     r9, [rsp+278h+Name]; lpName
0x1800039e0  mov     [rsp+278h+dwFlags], r12d; int
0x1800039e5  cmovnz  esi, ebp
0x1800039e8  mov     edx, ebp; lInitialCount
0x1800039ea  mov     r8d, esi; lMaximumCount
0x1800039ed  xor     ecx, ecx; lpSemaphoreAttributes
0x1800039ef  call    cs:__imp_CreateSemaphoreExW
0x1800039f5  mov     rsi, rax
0x1800039f8  test    rax, rax
0x1800039fb  jnz     short loc_180003A28
0x1800039fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a02  mov     ebx, eax
0x180003a04  test    eax, eax
0x180003a06  jns     short loc_180003A58
0x180003a08  mov     rcx, [rsp+278h]; this
0x180003a10  lea     r8, aWil; "wil"
0x180003a17  mov     r9d, eax; char *
0x180003a1a  mov     edx, 90h; void *
0x180003a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a24  mov     eax, ebx
0x180003a26  jmp     short loc_180003A5A
0x180003a28  call    cs:__imp_GetLastError
0x180003a2e  mov     rdi, [rbx+8]
0x180003a32  test    rdi, rdi
0x180003a35  jz      short loc_180003A54
0x180003a37  call    cs:__imp_GetLastError
0x180003a3d  mov     rcx, rdi; hObject
0x180003a40  mov     ebp, eax
0x180003a42  call    cs:__imp_CloseHandle
0x180003a48  test    eax, eax
0x180003a4a  jz      short loc_180003A86
0x180003a4c  mov     ecx, ebp; dwErrCode
0x180003a4e  call    cs:__imp_SetLastError
0x180003a54  mov     [rbx+8], rsi
0x180003a58  xor     eax, eax
0x180003a5a  mov     rcx, [rsp+278h+var_38]
0x180003a62  xor     rcx, rsp; StackCookie
0x180003a65  call    __security_check_cookie
0x180003a6a  lea     r11, [rsp+278h+var_28]
0x180003a72  mov     rbx, [r11+38h]
0x180003a76  mov     rbp, [r11+40h]
0x180003a7a  mov     rsp, r11
0x180003a7d  pop     r15
0x180003a7f  pop     r14
0x180003a81  pop     r12
0x180003a83  pop     rdi
0x180003a84  pop     rsi
0x180003a85  retn
0x180003a86  mov     rcx, [rsp+278h]; this
0x180003a8e  mov     edx, 0A0Bh; void *
0x180003a93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a99  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a9f  mov     rcx, [rsp+278h]; this
0x180003aa7  mov     edx, 0A0Bh; void *
0x180003aac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

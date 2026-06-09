# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004c48`
- end: `0x180004e6b`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000443c`
- `0x1800047e0`

## callees

- `0x180002240`
- `0x180004c48`
- `0x180006508`
- `0x180009170`
- `0x18000958c`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d11`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004db0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004d11`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfc`

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
0x180004c48  mov     [rsp+arg_8], rbx
0x180004c4d  push    rbp
0x180004c4e  push    rsi
0x180004c4f  push    rdi
0x180004c50  push    r12
0x180004c52  push    r13
0x180004c54  push    r14
0x180004c56  push    r15
0x180004c58  sub     rsp, 250h
0x180004c5f  mov     rax, cs:__security_cookie
0x180004c66  xor     rax, rsp
0x180004c69  mov     [rsp+288h+var_48], rax
0x180004c71  mov     rax, 0C000000000000000h
0x180004c7b  mov     rsi, r9
0x180004c7e  mov     r8, rdx
0x180004c81  mov     rbx, rcx
0x180004c84  test    rax, r9
0x180004c87  jnz     loc_180004E52
0x180004c8d  xor     r12d, r12d
0x180004c90  lea     rax, [rsp+288h+Name]
0x180004c95  mov     r13d, 104h
0x180004c9b  mov     ecx, 7FFFFFFEh
0x180004ca0  mov     edx, r13d
0x180004ca3  lea     ebp, [r12+1]
0x180004ca8  test    rcx, rcx
0x180004cab  jz      short loc_180004CCB
0x180004cad  movzx   r9d, word ptr [r8]
0x180004cb1  test    r9w, r9w
0x180004cb5  jz      short loc_180004CCB
0x180004cb7  mov     [rax], r9w
0x180004cbb  add     r8, 2
0x180004cbf  add     rax, 2
0x180004cc3  sub     rcx, rbp
0x180004cc6  sub     rdx, rbp
0x180004cc9  jnz     short loc_180004CA8
0x180004ccb  test    rdx, rdx
0x180004cce  lea     rcx, [rax-2]
0x180004cd2  lea     r8, aP0; "_p0"
0x180004cd9  mov     rdx, r13; unsigned __int64
0x180004cdc  cmovnz  rcx, rax
0x180004ce0  mov     [rcx], r12w
0x180004ce4  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004ce9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004cee  mov     edx, esi
0x180004cf0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004cf8  and     edx, 7FFFFFFFh; lInitialCount
0x180004cfe  mov     [rsp+288h+dwFlags], r12d; int
0x180004d03  mov     r8d, ebp
0x180004d06  lea     r9, [rsp+288h+Name]; lpName
0x180004d0b  cmova   r8d, edx; lMaximumCount
0x180004d0f  xor     ecx, ecx; lpSemaphoreAttributes
0x180004d11  call    cs:__imp_CreateSemaphoreExW
0x180004d17  mov     r15, rax
0x180004d1a  test    rax, rax
0x180004d1d  jnz     short loc_180004D46
0x180004d1f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d24  mov     edi, eax
0x180004d26  test    eax, eax
0x180004d28  jns     short loc_180004D7A
0x180004d2a  mov     rcx, [rsp+288h]; this
0x180004d32  mov     r9d, eax; char *
0x180004d35  mov     edx, 8Bh; void *
0x180004d3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d3f  mov     eax, edi
0x180004d41  jmp     loc_180004E14
0x180004d46  call    cs:__imp_GetLastError
0x180004d4c  mov     rdi, [rbx]
0x180004d4f  test    rdi, rdi
0x180004d52  jz      short loc_180004D77
0x180004d54  call    cs:__imp_GetLastError
0x180004d5a  mov     rcx, rdi; hObject
0x180004d5d  mov     r14d, eax
0x180004d60  call    cs:__imp_CloseHandle
0x180004d66  test    eax, eax
0x180004d68  jz      loc_180004E58
0x180004d6e  mov     ecx, r14d; dwErrCode
0x180004d71  call    cs:__imp_SetLastError
0x180004d77  mov     [rbx], r15
0x180004d7a  lea     r8, asc_18002B0A0; "h"
0x180004d81  shr     rsi, 1Fh
0x180004d85  mov     rdx, r13; unsigned __int64
0x180004d88  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004d8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004d92  test    esi, esi
0x180004d94  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004d9c  lea     r9, [rsp+288h+Name]; lpName
0x180004da1  mov     [rsp+288h+dwFlags], r12d; int
0x180004da6  cmovnz  ebp, esi
0x180004da9  mov     edx, esi; lInitialCount
0x180004dab  mov     r8d, ebp; lMaximumCount
0x180004dae  xor     ecx, ecx; lpSemaphoreAttributes
0x180004db0  call    cs:__imp_CreateSemaphoreExW
0x180004db6  mov     rbp, rax
0x180004db9  test    rax, rax
0x180004dbc  jnz     short loc_180004DE2
0x180004dbe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004dc3  mov     ebx, eax
0x180004dc5  test    eax, eax
0x180004dc7  jns     short loc_180004E12
0x180004dc9  mov     rcx, [rsp+288h]; this
0x180004dd1  mov     r9d, eax; char *
0x180004dd4  mov     edx, 90h; void *
0x180004dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dde  mov     eax, ebx
0x180004de0  jmp     short loc_180004E14
0x180004de2  call    cs:__imp_GetLastError
0x180004de8  mov     rdi, [rbx+8]
0x180004dec  test    rdi, rdi
0x180004def  jz      short loc_180004E0E
0x180004df1  call    cs:__imp_GetLastError
0x180004df7  mov     rcx, rdi; hObject
0x180004dfa  mov     esi, eax
0x180004dfc  call    cs:__imp_CloseHandle
0x180004e02  test    eax, eax
0x180004e04  jz      short loc_180004E3F
0x180004e06  mov     ecx, esi; dwErrCode
0x180004e08  call    cs:__imp_SetLastError
0x180004e0e  mov     [rbx+8], rbp
0x180004e12  xor     eax, eax
0x180004e14  mov     rcx, [rsp+288h+var_48]
0x180004e1c  xor     rcx, rsp; StackCookie
0x180004e1f  call    __security_check_cookie
0x180004e24  mov     rbx, [rsp+288h+arg_8]
0x180004e2c  add     rsp, 250h
0x180004e33  pop     r15
0x180004e35  pop     r14
0x180004e37  pop     r13
0x180004e39  pop     r12
0x180004e3b  pop     rdi
0x180004e3c  pop     rsi
0x180004e3d  pop     rbp
0x180004e3e  retn
0x180004e3f  mov     rcx, [rsp+288h]; this
0x180004e47  mov     edx, 0A0Bh; void *
0x180004e4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004e52  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004e58  mov     rcx, [rsp+288h]; this
0x180004e60  mov     edx, 0A0Bh; void *
0x180004e65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

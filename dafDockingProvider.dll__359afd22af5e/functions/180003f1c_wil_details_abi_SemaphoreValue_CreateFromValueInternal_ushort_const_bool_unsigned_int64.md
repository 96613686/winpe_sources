# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003f1c`
- end: `0x180004129`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037a8`
- `0x180003b4c`

## callees

- `0x180003f1c`
- `0x180004bd8`
- `0x180006aa4`
- `0x180007328`
- `0x180007edc`
- `0x180007eec`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003fe0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000407c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003fe0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000407c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000402f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000402f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b9`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003f1c  mov     [rsp+arg_8], rbx
0x180003f21  mov     [rsp+arg_10], rbp
0x180003f26  push    rsi
0x180003f27  push    rdi
0x180003f28  push    r12
0x180003f2a  push    r14
0x180003f2c  push    r15
0x180003f2e  sub     rsp, 250h
0x180003f35  mov     rax, cs:__security_cookie
0x180003f3c  xor     rax, rsp
0x180003f3f  mov     [rsp+278h+var_38], rax
0x180003f47  mov     rax, 0C000000000000000h
0x180003f51  mov     rbp, r9
0x180003f54  mov     r8, rdx
0x180003f57  mov     rdi, rcx
0x180003f5a  test    rax, r9
0x180003f5d  jnz     loc_180004110
0x180003f63  xor     r12d, r12d
0x180003f66  lea     rax, [rsp+278h+Name]
0x180003f6b  mov     ecx, 7FFFFFFEh
0x180003f70  mov     edx, 104h
0x180003f75  lea     esi, [r12+1]
0x180003f7a  test    rcx, rcx
0x180003f7d  jz      short loc_180003F9D
0x180003f7f  movzx   r9d, word ptr [r8]
0x180003f83  test    r9w, r9w
0x180003f87  jz      short loc_180003F9D
0x180003f89  mov     [rax], r9w
0x180003f8d  add     r8, 2
0x180003f91  add     rax, 2
0x180003f95  sub     rcx, rsi
0x180003f98  sub     rdx, rsi; unsigned __int64
0x180003f9b  jnz     short loc_180003F7A
0x180003f9d  test    rdx, rdx
0x180003fa0  lea     rcx, [rax-2]
0x180003fa4  lea     r8, aP0; "_p0"
0x180003fab  cmovnz  rcx, rax
0x180003faf  mov     [rcx], r12w
0x180003fb3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003fb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003fbd  mov     edx, ebp
0x180003fbf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003fc7  and     edx, 7FFFFFFFh; lInitialCount
0x180003fcd  mov     [rsp+278h+dwFlags], r12d; int
0x180003fd2  mov     r8d, esi
0x180003fd5  lea     r9, [rsp+278h+Name]; lpName
0x180003fda  cmova   r8d, edx; lMaximumCount
0x180003fde  xor     ecx, ecx; lpSemaphoreAttributes
0x180003fe0  call    cs:__imp_CreateSemaphoreExW
0x180003fe6  mov     r15, rax
0x180003fe9  test    rax, rax
0x180003fec  jnz     short loc_180004015
0x180003fee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ff3  mov     ebx, eax
0x180003ff5  test    eax, eax
0x180003ff7  jns     short loc_180004049
0x180003ff9  mov     edx, 8Bh; void *
0x180003ffe  mov     rcx, [rsp+278h]; this
0x180004006  mov     r9d, ebx; char *
0x180004009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000400e  mov     eax, ebx
0x180004010  jmp     loc_1800040D1
0x180004015  call    cs:__imp_GetLastError
0x18000401b  mov     rbx, [rdi]
0x18000401e  test    rbx, rbx
0x180004021  jz      short loc_180004046
0x180004023  call    cs:__imp_GetLastError
0x180004029  mov     rcx, rbx; hObject
0x18000402c  mov     r14d, eax
0x18000402f  call    cs:__imp_CloseHandle
0x180004035  test    eax, eax
0x180004037  jz      loc_180004116
0x18000403d  mov     ecx, r14d; dwErrCode
0x180004040  call    cs:__imp_SetLastError
0x180004046  mov     [rdi], r15
0x180004049  lea     r8, asc_1800210C8; "h"
0x180004050  shr     rbp, 1Fh
0x180004054  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004059  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000405e  test    ebp, ebp
0x180004060  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004068  lea     r9, [rsp+278h+Name]; lpName
0x18000406d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004072  cmovnz  esi, ebp
0x180004075  mov     edx, ebp; lInitialCount
0x180004077  mov     r8d, esi; lMaximumCount
0x18000407a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000407c  call    cs:__imp_CreateSemaphoreExW
0x180004082  mov     rsi, rax
0x180004085  test    rax, rax
0x180004088  jnz     short loc_18000409F
0x18000408a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000408f  mov     ebx, eax
0x180004091  test    eax, eax
0x180004093  jns     short loc_1800040CF
0x180004095  mov     edx, 90h
0x18000409a  jmp     loc_180003FFE
0x18000409f  call    cs:__imp_GetLastError
0x1800040a5  mov     rbx, [rdi+8]
0x1800040a9  test    rbx, rbx
0x1800040ac  jz      short loc_1800040CB
0x1800040ae  call    cs:__imp_GetLastError
0x1800040b4  mov     rcx, rbx; hObject
0x1800040b7  mov     ebp, eax
0x1800040b9  call    cs:__imp_CloseHandle
0x1800040bf  test    eax, eax
0x1800040c1  jz      short loc_1800040FD
0x1800040c3  mov     ecx, ebp; dwErrCode
0x1800040c5  call    cs:__imp_SetLastError
0x1800040cb  mov     [rdi+8], rsi
0x1800040cf  xor     eax, eax
0x1800040d1  mov     rcx, [rsp+278h+var_38]
0x1800040d9  xor     rcx, rsp; StackCookie
0x1800040dc  call    __security_check_cookie
0x1800040e1  lea     r11, [rsp+278h+var_28]
0x1800040e9  mov     rbx, [r11+38h]
0x1800040ed  mov     rbp, [r11+40h]
0x1800040f1  mov     rsp, r11
0x1800040f4  pop     r15
0x1800040f6  pop     r14
0x1800040f8  pop     r12
0x1800040fa  pop     rdi
0x1800040fb  pop     rsi
0x1800040fc  retn
0x1800040fd  mov     rcx, [rsp+278h]; this
0x180004105  mov     edx, 0A0Bh; void *
0x18000410a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004110  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004116  mov     rcx, [rsp+278h]; this
0x18000411e  mov     edx, 0A0Bh; void *
0x180004123  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

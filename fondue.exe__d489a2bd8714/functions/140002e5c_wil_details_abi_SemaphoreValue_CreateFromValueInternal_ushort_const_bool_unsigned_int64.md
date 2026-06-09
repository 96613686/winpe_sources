# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002e5c`
- end: `0x140003069`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002ab8`

## callees

- `0x140002e5c`
- `0x1400036c8`
- `0x140004454`
- `0x140004704`
- `0x140004bfc`
- `0x140004c0c`
- `0x140004cd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140002f55`
- `KERNEL32!GetLastError` at `0x140002f63`
- `KERNEL32!GetLastError` at `0x140002fdf`
- `KERNEL32!GetLastError` at `0x140002fee`
- `KERNEL32!GetLastError` at `0x140002f55`
- `KERNEL32!GetLastError` at `0x140002f63`
- `KERNEL32!GetLastError` at `0x140002fdf`
- `KERNEL32!GetLastError` at `0x140002fee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003005`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003005`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002f20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002fbc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002f20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ff9`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x140002e5c  mov     [rsp+arg_8], rbx
0x140002e61  mov     [rsp+arg_10], rbp
0x140002e66  push    rsi
0x140002e67  push    rdi
0x140002e68  push    r12
0x140002e6a  push    r14
0x140002e6c  push    r15
0x140002e6e  sub     rsp, 250h
0x140002e75  mov     rax, cs:__security_cookie
0x140002e7c  xor     rax, rsp
0x140002e7f  mov     [rsp+278h+var_38], rax
0x140002e87  mov     rax, 0C000000000000000h
0x140002e91  mov     rbp, r9
0x140002e94  mov     r8, rdx
0x140002e97  mov     rdi, rcx
0x140002e9a  test    rax, r9
0x140002e9d  jnz     loc_140003050
0x140002ea3  xor     r12d, r12d
0x140002ea6  lea     rax, [rsp+278h+Name]
0x140002eab  mov     ecx, 7FFFFFFEh
0x140002eb0  mov     edx, 104h
0x140002eb5  lea     esi, [r12+1]
0x140002eba  test    rcx, rcx
0x140002ebd  jz      short loc_140002EDD
0x140002ebf  movzx   r9d, word ptr [r8]
0x140002ec3  test    r9w, r9w
0x140002ec7  jz      short loc_140002EDD
0x140002ec9  mov     [rax], r9w
0x140002ecd  add     r8, 2
0x140002ed1  add     rax, 2
0x140002ed5  sub     rcx, rsi
0x140002ed8  sub     rdx, rsi; unsigned __int64
0x140002edb  jnz     short loc_140002EBA
0x140002edd  test    rdx, rdx
0x140002ee0  lea     rcx, [rax-2]
0x140002ee4  lea     r8, aP0; "_p0"
0x140002eeb  cmovnz  rcx, rax
0x140002eef  mov     [rcx], r12w
0x140002ef3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140002ef8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002efd  mov     edx, ebp
0x140002eff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002f07  and     edx, 7FFFFFFFh; lInitialCount
0x140002f0d  mov     [rsp+278h+dwFlags], r12d; int
0x140002f12  mov     r8d, esi
0x140002f15  lea     r9, [rsp+278h+Name]; lpName
0x140002f1a  cmova   r8d, edx; lMaximumCount
0x140002f1e  xor     ecx, ecx; lpSemaphoreAttributes
0x140002f20  call    cs:__imp_CreateSemaphoreExW
0x140002f26  mov     r15, rax
0x140002f29  test    rax, rax
0x140002f2c  jnz     short loc_140002F55
0x140002f2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002f33  mov     ebx, eax
0x140002f35  test    eax, eax
0x140002f37  jns     short loc_140002F89
0x140002f39  mov     edx, 8Bh; void *
0x140002f3e  mov     rcx, [rsp+278h]; this
0x140002f46  mov     r9d, ebx; char *
0x140002f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f4e  mov     eax, ebx
0x140002f50  jmp     loc_140003011
0x140002f55  call    cs:__imp_GetLastError
0x140002f5b  mov     rbx, [rdi]
0x140002f5e  test    rbx, rbx
0x140002f61  jz      short loc_140002F86
0x140002f63  call    cs:__imp_GetLastError
0x140002f69  mov     rcx, rbx; hObject
0x140002f6c  mov     r14d, eax
0x140002f6f  call    cs:__imp_CloseHandle
0x140002f75  test    eax, eax
0x140002f77  jz      loc_140003056
0x140002f7d  mov     ecx, r14d; dwErrCode
0x140002f80  call    cs:__imp_SetLastError
0x140002f86  mov     [rdi], r15
0x140002f89  lea     r8, asc_140006890; "h"
0x140002f90  shr     rbp, 1Fh
0x140002f94  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140002f99  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002f9e  test    ebp, ebp
0x140002fa0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002fa8  lea     r9, [rsp+278h+Name]; lpName
0x140002fad  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140002fb2  cmovnz  esi, ebp
0x140002fb5  mov     edx, ebp; lInitialCount
0x140002fb7  mov     r8d, esi; lMaximumCount
0x140002fba  xor     ecx, ecx; lpSemaphoreAttributes
0x140002fbc  call    cs:__imp_CreateSemaphoreExW
0x140002fc2  mov     rsi, rax
0x140002fc5  test    rax, rax
0x140002fc8  jnz     short loc_140002FDF
0x140002fca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002fcf  mov     ebx, eax
0x140002fd1  test    eax, eax
0x140002fd3  jns     short loc_14000300F
0x140002fd5  mov     edx, 90h
0x140002fda  jmp     loc_140002F3E
0x140002fdf  call    cs:__imp_GetLastError
0x140002fe5  mov     rbx, [rdi+8]
0x140002fe9  test    rbx, rbx
0x140002fec  jz      short loc_14000300B
0x140002fee  call    cs:__imp_GetLastError
0x140002ff4  mov     rcx, rbx; hObject
0x140002ff7  mov     ebp, eax
0x140002ff9  call    cs:__imp_CloseHandle
0x140002fff  test    eax, eax
0x140003001  jz      short loc_14000303D
0x140003003  mov     ecx, ebp; dwErrCode
0x140003005  call    cs:__imp_SetLastError
0x14000300b  mov     [rdi+8], rsi
0x14000300f  xor     eax, eax
0x140003011  mov     rcx, [rsp+278h+var_38]
0x140003019  xor     rcx, rsp; StackCookie
0x14000301c  call    __security_check_cookie
0x140003021  lea     r11, [rsp+278h+var_28]
0x140003029  mov     rbx, [r11+38h]
0x14000302d  mov     rbp, [r11+40h]
0x140003031  mov     rsp, r11
0x140003034  pop     r15
0x140003036  pop     r14
0x140003038  pop     r12
0x14000303a  pop     rdi
0x14000303b  pop     rsi
0x14000303c  retn
0x14000303d  mov     rcx, [rsp+278h]; this
0x140003045  mov     edx, 0A0Bh; void *
0x14000304a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003050  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003056  mov     rcx, [rsp+278h]; this
0x14000305e  mov     edx, 0A0Bh; void *
0x140003063  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002f74`
- end: `0x140003181`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002b44`

## callees

- `0x140001470`
- `0x140002f74`
- `0x1400039c8`
- `0x140004d54`
- `0x140005000`
- `0x14000564c`
- `0x14000565c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000306d`
- `KERNEL32!GetLastError` at `0x14000307b`
- `KERNEL32!GetLastError` at `0x1400030f7`
- `KERNEL32!GetLastError` at `0x140003106`
- `KERNEL32!GetLastError` at `0x14000306d`
- `KERNEL32!GetLastError` at `0x14000307b`
- `KERNEL32!GetLastError` at `0x1400030f7`
- `KERNEL32!GetLastError` at `0x140003106`
- `KERNEL32!CloseHandle` at `0x140003087`
- `KERNEL32!CloseHandle` at `0x140003111`
- `KERNEL32!CloseHandle` at `0x140003087`
- `KERNEL32!CloseHandle` at `0x140003111`
- `KERNEL32!SetLastError` at `0x140003098`
- `KERNEL32!SetLastError` at `0x14000311d`
- `KERNEL32!SetLastError` at `0x140003098`
- `KERNEL32!SetLastError` at `0x14000311d`
- `KERNEL32!CreateSemaphoreExW` at `0x140003038`
- `KERNEL32!CreateSemaphoreExW` at `0x1400030d4`
- `KERNEL32!CreateSemaphoreExW` at `0x140003038`
- `KERNEL32!CreateSemaphoreExW` at `0x1400030d4`

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
0x140002f74  mov     [rsp+arg_8], rbx
0x140002f79  mov     [rsp+arg_10], rbp
0x140002f7e  push    rsi
0x140002f7f  push    rdi
0x140002f80  push    r12
0x140002f82  push    r14
0x140002f84  push    r15
0x140002f86  sub     rsp, 250h
0x140002f8d  mov     rax, cs:__security_cookie
0x140002f94  xor     rax, rsp
0x140002f97  mov     [rsp+278h+var_38], rax
0x140002f9f  mov     rax, 0C000000000000000h
0x140002fa9  mov     rbp, r9
0x140002fac  mov     r8, rdx
0x140002faf  mov     rdi, rcx
0x140002fb2  test    rax, r9
0x140002fb5  jnz     loc_140003168
0x140002fbb  xor     r12d, r12d
0x140002fbe  lea     rax, [rsp+278h+Name]
0x140002fc3  mov     ecx, 7FFFFFFEh
0x140002fc8  mov     edx, 104h
0x140002fcd  lea     esi, [r12+1]
0x140002fd2  test    rcx, rcx
0x140002fd5  jz      short loc_140002FF5
0x140002fd7  movzx   r9d, word ptr [r8]
0x140002fdb  test    r9w, r9w
0x140002fdf  jz      short loc_140002FF5
0x140002fe1  mov     [rax], r9w
0x140002fe5  add     r8, 2
0x140002fe9  add     rax, 2
0x140002fed  sub     rcx, rsi
0x140002ff0  sub     rdx, rsi; unsigned __int64
0x140002ff3  jnz     short loc_140002FD2
0x140002ff5  test    rdx, rdx
0x140002ff8  lea     rcx, [rax-2]
0x140002ffc  lea     r8, aP0; "_p0"
0x140003003  cmovnz  rcx, rax
0x140003007  mov     [rcx], r12w
0x14000300b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003010  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003015  mov     edx, ebp
0x140003017  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000301f  and     edx, 7FFFFFFFh; lInitialCount
0x140003025  mov     [rsp+278h+dwFlags], r12d; int
0x14000302a  mov     r8d, esi
0x14000302d  lea     r9, [rsp+278h+Name]; lpName
0x140003032  cmova   r8d, edx; lMaximumCount
0x140003036  xor     ecx, ecx; lpSemaphoreAttributes
0x140003038  call    cs:__imp_CreateSemaphoreExW
0x14000303e  mov     r15, rax
0x140003041  test    rax, rax
0x140003044  jnz     short loc_14000306D
0x140003046  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000304b  mov     ebx, eax
0x14000304d  test    eax, eax
0x14000304f  jns     short loc_1400030A1
0x140003051  mov     edx, 8Bh; void *
0x140003056  mov     rcx, [rsp+278h]; this
0x14000305e  mov     r9d, ebx; char *
0x140003061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003066  mov     eax, ebx
0x140003068  jmp     loc_140003129
0x14000306d  call    cs:__imp_GetLastError
0x140003073  mov     rbx, [rdi]
0x140003076  test    rbx, rbx
0x140003079  jz      short loc_14000309E
0x14000307b  call    cs:__imp_GetLastError
0x140003081  mov     rcx, rbx; hObject
0x140003084  mov     r14d, eax
0x140003087  call    cs:__imp_CloseHandle
0x14000308d  test    eax, eax
0x14000308f  jz      loc_14000316E
0x140003095  mov     ecx, r14d; dwErrCode
0x140003098  call    cs:__imp_SetLastError
0x14000309e  mov     [rdi], r15
0x1400030a1  lea     r8, asc_1400079A8; "h"
0x1400030a8  shr     rbp, 1Fh
0x1400030ac  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400030b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400030b6  test    ebp, ebp
0x1400030b8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400030c0  lea     r9, [rsp+278h+Name]; lpName
0x1400030c5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1400030ca  cmovnz  esi, ebp
0x1400030cd  mov     edx, ebp; lInitialCount
0x1400030cf  mov     r8d, esi; lMaximumCount
0x1400030d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400030d4  call    cs:__imp_CreateSemaphoreExW
0x1400030da  mov     rsi, rax
0x1400030dd  test    rax, rax
0x1400030e0  jnz     short loc_1400030F7
0x1400030e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400030e7  mov     ebx, eax
0x1400030e9  test    eax, eax
0x1400030eb  jns     short loc_140003127
0x1400030ed  mov     edx, 90h
0x1400030f2  jmp     loc_140003056
0x1400030f7  call    cs:__imp_GetLastError
0x1400030fd  mov     rbx, [rdi+8]
0x140003101  test    rbx, rbx
0x140003104  jz      short loc_140003123
0x140003106  call    cs:__imp_GetLastError
0x14000310c  mov     rcx, rbx; hObject
0x14000310f  mov     ebp, eax
0x140003111  call    cs:__imp_CloseHandle
0x140003117  test    eax, eax
0x140003119  jz      short loc_140003155
0x14000311b  mov     ecx, ebp; dwErrCode
0x14000311d  call    cs:__imp_SetLastError
0x140003123  mov     [rdi+8], rsi
0x140003127  xor     eax, eax
0x140003129  mov     rcx, [rsp+278h+var_38]
0x140003131  xor     rcx, rsp; StackCookie
0x140003134  call    __security_check_cookie
0x140003139  lea     r11, [rsp+278h+var_28]
0x140003141  mov     rbx, [r11+38h]
0x140003145  mov     rbp, [r11+40h]
0x140003149  mov     rsp, r11
0x14000314c  pop     r15
0x14000314e  pop     r14
0x140003150  pop     r12
0x140003152  pop     rdi
0x140003153  pop     rsi
0x140003154  retn
0x140003155  mov     rcx, [rsp+278h]; this
0x14000315d  mov     edx, 0A0Bh; void *
0x140003162  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003168  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000316e  mov     rcx, [rsp+278h]; this
0x140003176  mov     edx, 0A0Bh; void *
0x14000317b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

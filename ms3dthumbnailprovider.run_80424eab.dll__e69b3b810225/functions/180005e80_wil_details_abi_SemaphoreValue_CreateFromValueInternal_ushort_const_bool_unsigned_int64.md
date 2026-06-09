# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005e80`
- end: `0x18000608d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a88`

## callees

- `0x180001ef0`
- `0x180005e80`
- `0x180006918`
- `0x180008384`
- `0x1800093b8`
- `0x1800099a8`
- `0x1800099b8`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180005f44`
- `KERNEL32!CreateSemaphoreExW` at `0x180005fe0`
- `KERNEL32!CreateSemaphoreExW` at `0x180005f44`
- `KERNEL32!CreateSemaphoreExW` at `0x180005fe0`
- `KERNEL32!GetLastError` at `0x180005f79`
- `KERNEL32!GetLastError` at `0x180005f87`
- `KERNEL32!GetLastError` at `0x180006003`
- `KERNEL32!GetLastError` at `0x180006012`
- `KERNEL32!GetLastError` at `0x180005f79`
- `KERNEL32!GetLastError` at `0x180005f87`
- `KERNEL32!GetLastError` at `0x180006003`
- `KERNEL32!GetLastError` at `0x180006012`
- `KERNEL32!CloseHandle` at `0x180005f93`
- `KERNEL32!CloseHandle` at `0x18000601d`
- `KERNEL32!CloseHandle` at `0x180005f93`
- `KERNEL32!CloseHandle` at `0x18000601d`
- `KERNEL32!SetLastError` at `0x180005fa4`
- `KERNEL32!SetLastError` at `0x180006029`
- `KERNEL32!SetLastError` at `0x180005fa4`
- `KERNEL32!SetLastError` at `0x180006029`

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
0x180005e80  mov     [rsp+arg_8], rbx
0x180005e85  mov     [rsp+arg_10], rbp
0x180005e8a  push    rsi
0x180005e8b  push    rdi
0x180005e8c  push    r12
0x180005e8e  push    r14
0x180005e90  push    r15
0x180005e92  sub     rsp, 250h
0x180005e99  mov     rax, cs:__security_cookie
0x180005ea0  xor     rax, rsp
0x180005ea3  mov     [rsp+278h+var_38], rax
0x180005eab  mov     rax, 0C000000000000000h
0x180005eb5  mov     rbp, r9
0x180005eb8  mov     r8, rdx
0x180005ebb  mov     rdi, rcx
0x180005ebe  test    rax, r9
0x180005ec1  jnz     loc_180006074
0x180005ec7  xor     r12d, r12d
0x180005eca  lea     rax, [rsp+278h+Name]
0x180005ecf  mov     ecx, 7FFFFFFEh
0x180005ed4  mov     edx, 104h
0x180005ed9  lea     esi, [r12+1]
0x180005ede  test    rcx, rcx
0x180005ee1  jz      short loc_180005F01
0x180005ee3  movzx   r9d, word ptr [r8]
0x180005ee7  test    r9w, r9w
0x180005eeb  jz      short loc_180005F01
0x180005eed  mov     [rax], r9w
0x180005ef1  add     r8, 2
0x180005ef5  add     rax, 2
0x180005ef9  sub     rcx, rsi
0x180005efc  sub     rdx, rsi; unsigned __int64
0x180005eff  jnz     short loc_180005EDE
0x180005f01  test    rdx, rdx
0x180005f04  lea     rcx, [rax-2]
0x180005f08  lea     r8, aP0; "_p0"
0x180005f0f  cmovnz  rcx, rax
0x180005f13  mov     [rcx], r12w
0x180005f17  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005f1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005f21  mov     edx, ebp
0x180005f23  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005f2b  and     edx, 7FFFFFFFh; lInitialCount
0x180005f31  mov     [rsp+278h+dwFlags], r12d; int
0x180005f36  mov     r8d, esi
0x180005f39  lea     r9, [rsp+278h+Name]; lpName
0x180005f3e  cmova   r8d, edx; lMaximumCount
0x180005f42  xor     ecx, ecx; lpSemaphoreAttributes
0x180005f44  call    cs:__imp_CreateSemaphoreExW
0x180005f4a  mov     r15, rax
0x180005f4d  test    rax, rax
0x180005f50  jnz     short loc_180005F79
0x180005f52  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f57  mov     ebx, eax
0x180005f59  test    eax, eax
0x180005f5b  jns     short loc_180005FAD
0x180005f5d  mov     edx, 8Bh; void *
0x180005f62  mov     rcx, [rsp+278h]; this
0x180005f6a  mov     r9d, ebx; char *
0x180005f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f72  mov     eax, ebx
0x180005f74  jmp     loc_180006035
0x180005f79  call    cs:__imp_GetLastError
0x180005f7f  mov     rbx, [rdi]
0x180005f82  test    rbx, rbx
0x180005f85  jz      short loc_180005FAA
0x180005f87  call    cs:__imp_GetLastError
0x180005f8d  mov     rcx, rbx; hObject
0x180005f90  mov     r14d, eax
0x180005f93  call    cs:__imp_CloseHandle
0x180005f99  test    eax, eax
0x180005f9b  jz      loc_18000607A
0x180005fa1  mov     ecx, r14d; dwErrCode
0x180005fa4  call    cs:__imp_SetLastError
0x180005faa  mov     [rdi], r15
0x180005fad  lea     r8, asc_18000D1F8; "h"
0x180005fb4  shr     rbp, 1Fh
0x180005fb8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005fbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005fc2  test    ebp, ebp
0x180005fc4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005fcc  lea     r9, [rsp+278h+Name]; lpName
0x180005fd1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180005fd6  cmovnz  esi, ebp
0x180005fd9  mov     edx, ebp; lInitialCount
0x180005fdb  mov     r8d, esi; lMaximumCount
0x180005fde  xor     ecx, ecx; lpSemaphoreAttributes
0x180005fe0  call    cs:__imp_CreateSemaphoreExW
0x180005fe6  mov     rsi, rax
0x180005fe9  test    rax, rax
0x180005fec  jnz     short loc_180006003
0x180005fee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ff3  mov     ebx, eax
0x180005ff5  test    eax, eax
0x180005ff7  jns     short loc_180006033
0x180005ff9  mov     edx, 90h
0x180005ffe  jmp     loc_180005F62
0x180006003  call    cs:__imp_GetLastError
0x180006009  mov     rbx, [rdi+8]
0x18000600d  test    rbx, rbx
0x180006010  jz      short loc_18000602F
0x180006012  call    cs:__imp_GetLastError
0x180006018  mov     rcx, rbx; hObject
0x18000601b  mov     ebp, eax
0x18000601d  call    cs:__imp_CloseHandle
0x180006023  test    eax, eax
0x180006025  jz      short loc_180006061
0x180006027  mov     ecx, ebp; dwErrCode
0x180006029  call    cs:__imp_SetLastError
0x18000602f  mov     [rdi+8], rsi
0x180006033  xor     eax, eax
0x180006035  mov     rcx, [rsp+278h+var_38]
0x18000603d  xor     rcx, rsp; StackCookie
0x180006040  call    __security_check_cookie
0x180006045  lea     r11, [rsp+278h+var_28]
0x18000604d  mov     rbx, [r11+38h]
0x180006051  mov     rbp, [r11+40h]
0x180006055  mov     rsp, r11
0x180006058  pop     r15
0x18000605a  pop     r14
0x18000605c  pop     r12
0x18000605e  pop     rdi
0x18000605f  pop     rsi
0x180006060  retn
0x180006061  mov     rcx, [rsp+278h]; this
0x180006069  mov     edx, 0A0Bh; void *
0x18000606e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006074  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000607a  mov     rcx, [rsp+278h]; this
0x180006082  mov     edx, 0A0Bh; void *
0x180006087  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

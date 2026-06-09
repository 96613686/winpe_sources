# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009044`
- end: `0x180009251`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008828`
- `0x180008bcc`

## callees

- `0x180006018`
- `0x180009044`
- `0x180009d08`
- `0x18000bbd4`
- `0x18000cedc`
- `0x18000ceec`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009168`
- `KERNEL32!SetLastError` at `0x1800091ed`
- `KERNEL32!SetLastError` at `0x180009168`
- `KERNEL32!SetLastError` at `0x1800091ed`
- `KERNEL32!CloseHandle` at `0x180009157`
- `KERNEL32!CloseHandle` at `0x1800091e1`
- `KERNEL32!CloseHandle` at `0x180009157`
- `KERNEL32!CloseHandle` at `0x1800091e1`
- `KERNEL32!CreateSemaphoreExW` at `0x180009108`
- `KERNEL32!CreateSemaphoreExW` at `0x1800091a4`
- `KERNEL32!CreateSemaphoreExW` at `0x180009108`
- `KERNEL32!CreateSemaphoreExW` at `0x1800091a4`
- `KERNEL32!GetLastError` at `0x18000913d`
- `KERNEL32!GetLastError` at `0x18000914b`
- `KERNEL32!GetLastError` at `0x1800091c7`
- `KERNEL32!GetLastError` at `0x1800091d6`
- `KERNEL32!GetLastError` at `0x18000913d`
- `KERNEL32!GetLastError` at `0x18000914b`
- `KERNEL32!GetLastError` at `0x1800091c7`
- `KERNEL32!GetLastError` at `0x1800091d6`

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
0x180009044  mov     [rsp+arg_8], rbx
0x180009049  mov     [rsp+arg_10], rbp
0x18000904e  push    rsi
0x18000904f  push    rdi
0x180009050  push    r12
0x180009052  push    r14
0x180009054  push    r15
0x180009056  sub     rsp, 250h
0x18000905d  mov     rax, cs:__security_cookie
0x180009064  xor     rax, rsp
0x180009067  mov     [rsp+278h+var_38], rax
0x18000906f  mov     rax, 0C000000000000000h
0x180009079  mov     rbp, r9
0x18000907c  mov     r8, rdx
0x18000907f  mov     rdi, rcx
0x180009082  test    rax, r9
0x180009085  jnz     loc_180009238
0x18000908b  xor     r12d, r12d
0x18000908e  lea     rax, [rsp+278h+Name]
0x180009093  mov     ecx, 7FFFFFFEh
0x180009098  mov     edx, 104h
0x18000909d  lea     esi, [r12+1]
0x1800090a2  test    rcx, rcx
0x1800090a5  jz      short loc_1800090C5
0x1800090a7  movzx   r9d, word ptr [r8]
0x1800090ab  test    r9w, r9w
0x1800090af  jz      short loc_1800090C5
0x1800090b1  mov     [rax], r9w
0x1800090b5  add     r8, 2
0x1800090b9  add     rax, 2
0x1800090bd  sub     rcx, rsi
0x1800090c0  sub     rdx, rsi; unsigned __int64
0x1800090c3  jnz     short loc_1800090A2
0x1800090c5  test    rdx, rdx
0x1800090c8  lea     rcx, [rax-2]
0x1800090cc  lea     r8, aP0; "_p0"
0x1800090d3  cmovnz  rcx, rax
0x1800090d7  mov     [rcx], r12w
0x1800090db  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800090e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800090e5  mov     edx, ebp
0x1800090e7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800090ef  and     edx, 7FFFFFFFh; lInitialCount
0x1800090f5  mov     [rsp+278h+dwFlags], r12d; int
0x1800090fa  mov     r8d, esi
0x1800090fd  lea     r9, [rsp+278h+Name]; lpName
0x180009102  cmova   r8d, edx; lMaximumCount
0x180009106  xor     ecx, ecx; lpSemaphoreAttributes
0x180009108  call    cs:__imp_CreateSemaphoreExW
0x18000910e  mov     r15, rax
0x180009111  test    rax, rax
0x180009114  jnz     short loc_18000913D
0x180009116  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000911b  mov     ebx, eax
0x18000911d  test    eax, eax
0x18000911f  jns     short loc_180009171
0x180009121  mov     edx, 8Bh; void *
0x180009126  mov     rcx, [rsp+278h]; this
0x18000912e  mov     r9d, ebx; char *
0x180009131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009136  mov     eax, ebx
0x180009138  jmp     loc_1800091F9
0x18000913d  call    cs:__imp_GetLastError
0x180009143  mov     rbx, [rdi]
0x180009146  test    rbx, rbx
0x180009149  jz      short loc_18000916E
0x18000914b  call    cs:__imp_GetLastError
0x180009151  mov     rcx, rbx; hObject
0x180009154  mov     r14d, eax
0x180009157  call    cs:__imp_CloseHandle
0x18000915d  test    eax, eax
0x18000915f  jz      loc_18000923E
0x180009165  mov     ecx, r14d; dwErrCode
0x180009168  call    cs:__imp_SetLastError
0x18000916e  mov     [rdi], r15
0x180009171  lea     r8, asc_180019D00; "h"
0x180009178  shr     rbp, 1Fh
0x18000917c  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180009181  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009186  test    ebp, ebp
0x180009188  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009190  lea     r9, [rsp+278h+Name]; lpName
0x180009195  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000919a  cmovnz  esi, ebp
0x18000919d  mov     edx, ebp; lInitialCount
0x18000919f  mov     r8d, esi; lMaximumCount
0x1800091a2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800091a4  call    cs:__imp_CreateSemaphoreExW
0x1800091aa  mov     rsi, rax
0x1800091ad  test    rax, rax
0x1800091b0  jnz     short loc_1800091C7
0x1800091b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800091b7  mov     ebx, eax
0x1800091b9  test    eax, eax
0x1800091bb  jns     short loc_1800091F7
0x1800091bd  mov     edx, 90h
0x1800091c2  jmp     loc_180009126
0x1800091c7  call    cs:__imp_GetLastError
0x1800091cd  mov     rbx, [rdi+8]
0x1800091d1  test    rbx, rbx
0x1800091d4  jz      short loc_1800091F3
0x1800091d6  call    cs:__imp_GetLastError
0x1800091dc  mov     rcx, rbx; hObject
0x1800091df  mov     ebp, eax
0x1800091e1  call    cs:__imp_CloseHandle
0x1800091e7  test    eax, eax
0x1800091e9  jz      short loc_180009225
0x1800091eb  mov     ecx, ebp; dwErrCode
0x1800091ed  call    cs:__imp_SetLastError
0x1800091f3  mov     [rdi+8], rsi
0x1800091f7  xor     eax, eax
0x1800091f9  mov     rcx, [rsp+278h+var_38]
0x180009201  xor     rcx, rsp; StackCookie
0x180009204  call    __security_check_cookie
0x180009209  lea     r11, [rsp+278h+var_28]
0x180009211  mov     rbx, [r11+38h]
0x180009215  mov     rbp, [r11+40h]
0x180009219  mov     rsp, r11
0x18000921c  pop     r15
0x18000921e  pop     r14
0x180009220  pop     r12
0x180009222  pop     rdi
0x180009223  pop     rsi
0x180009224  retn
0x180009225  mov     rcx, [rsp+278h]; this
0x18000922d  mov     edx, 0A0Bh; void *
0x180009232  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009238  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000923e  mov     rcx, [rsp+278h]; this
0x180009246  mov     edx, 0A0Bh; void *
0x18000924b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140007f28`
- end: `0x140008152`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140007368`
- `0x140007738`

## callees

- `0x1400022a0`
- `0x140007f28`
- `0x140009674`
- `0x14000c8d4`
- `0x14000da24`
- `0x1400100dc`
- `0x1400100ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007fec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000808f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007fec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000808f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400080ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400080ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400080e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400080e2`

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
0x140007f28  mov     [rsp+arg_8], rbx
0x140007f2d  mov     [rsp+arg_10], rbp
0x140007f32  push    rsi
0x140007f33  push    rdi
0x140007f34  push    r12
0x140007f36  push    r14
0x140007f38  push    r15
0x140007f3a  sub     rsp, 250h
0x140007f41  mov     rax, cs:__security_cookie
0x140007f48  xor     rax, rsp
0x140007f4b  mov     [rsp+278h+var_38], rax
0x140007f53  mov     rax, 0C000000000000000h
0x140007f5d  mov     rbp, r9
0x140007f60  mov     r8, rdx
0x140007f63  mov     rbx, rcx
0x140007f66  test    rax, r9
0x140007f69  jnz     loc_140008139
0x140007f6f  xor     r12d, r12d
0x140007f72  lea     rax, [rsp+278h+Name]
0x140007f77  mov     ecx, 7FFFFFFEh
0x140007f7c  mov     edx, 104h
0x140007f81  lea     esi, [r12+1]
0x140007f86  test    rcx, rcx
0x140007f89  jz      short loc_140007FA9
0x140007f8b  movzx   r9d, word ptr [r8]
0x140007f8f  test    r9w, r9w
0x140007f93  jz      short loc_140007FA9
0x140007f95  mov     [rax], r9w
0x140007f99  add     r8, 2
0x140007f9d  add     rax, 2
0x140007fa1  sub     rcx, rsi
0x140007fa4  sub     rdx, rsi; unsigned __int64
0x140007fa7  jnz     short loc_140007F86
0x140007fa9  test    rdx, rdx
0x140007fac  lea     rcx, [rax-2]
0x140007fb0  lea     r8, aP0; "_p0"
0x140007fb7  cmovnz  rcx, rax
0x140007fbb  mov     [rcx], r12w
0x140007fbf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140007fc4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007fc9  mov     edx, ebp
0x140007fcb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140007fd3  and     edx, 7FFFFFFFh; lInitialCount
0x140007fd9  mov     [rsp+278h+dwFlags], r12d; int
0x140007fde  mov     r8d, esi
0x140007fe1  lea     r9, [rsp+278h+Name]; lpName
0x140007fe6  cmova   r8d, edx; lMaximumCount
0x140007fea  xor     ecx, ecx; lpSemaphoreAttributes
0x140007fec  call    cs:__imp_CreateSemaphoreExW
0x140007ff2  mov     r15, rax
0x140007ff5  test    rax, rax
0x140007ff8  jnz     short loc_140008028
0x140007ffa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007fff  mov     edi, eax
0x140008001  test    eax, eax
0x140008003  jns     short loc_14000805C
0x140008005  mov     rcx, [rsp+278h]; this
0x14000800d  lea     r8, aWil; "wil"
0x140008014  mov     r9d, eax; char *
0x140008017  mov     edx, 8Bh; void *
0x14000801c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008021  mov     eax, edi
0x140008023  jmp     loc_1400080FA
0x140008028  call    cs:__imp_GetLastError
0x14000802e  mov     rdi, [rbx]
0x140008031  test    rdi, rdi
0x140008034  jz      short loc_140008059
0x140008036  call    cs:__imp_GetLastError
0x14000803c  mov     rcx, rdi; hObject
0x14000803f  mov     r14d, eax
0x140008042  call    cs:__imp_CloseHandle
0x140008048  test    eax, eax
0x14000804a  jz      loc_14000813F
0x140008050  mov     ecx, r14d; dwErrCode
0x140008053  call    cs:__imp_SetLastError
0x140008059  mov     [rbx], r15
0x14000805c  lea     r8, asc_140013EA0; "h"
0x140008063  shr     rbp, 1Fh
0x140008067  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000806c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008071  test    ebp, ebp
0x140008073  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000807b  lea     r9, [rsp+278h+Name]; lpName
0x140008080  mov     [rsp+278h+dwFlags], r12d; int
0x140008085  cmovnz  esi, ebp
0x140008088  mov     edx, ebp; lInitialCount
0x14000808a  mov     r8d, esi; lMaximumCount
0x14000808d  xor     ecx, ecx; lpSemaphoreAttributes
0x14000808f  call    cs:__imp_CreateSemaphoreExW
0x140008095  mov     rsi, rax
0x140008098  test    rax, rax
0x14000809b  jnz     short loc_1400080C8
0x14000809d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400080a2  mov     ebx, eax
0x1400080a4  test    eax, eax
0x1400080a6  jns     short loc_1400080F8
0x1400080a8  mov     rcx, [rsp+278h]; this
0x1400080b0  lea     r8, aWil; "wil"
0x1400080b7  mov     r9d, eax; char *
0x1400080ba  mov     edx, 90h; void *
0x1400080bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400080c4  mov     eax, ebx
0x1400080c6  jmp     short loc_1400080FA
0x1400080c8  call    cs:__imp_GetLastError
0x1400080ce  mov     rdi, [rbx+8]
0x1400080d2  test    rdi, rdi
0x1400080d5  jz      short loc_1400080F4
0x1400080d7  call    cs:__imp_GetLastError
0x1400080dd  mov     rcx, rdi; hObject
0x1400080e0  mov     ebp, eax
0x1400080e2  call    cs:__imp_CloseHandle
0x1400080e8  test    eax, eax
0x1400080ea  jz      short loc_140008126
0x1400080ec  mov     ecx, ebp; dwErrCode
0x1400080ee  call    cs:__imp_SetLastError
0x1400080f4  mov     [rbx+8], rsi
0x1400080f8  xor     eax, eax
0x1400080fa  mov     rcx, [rsp+278h+var_38]
0x140008102  xor     rcx, rsp; StackCookie
0x140008105  call    __security_check_cookie
0x14000810a  lea     r11, [rsp+278h+var_28]
0x140008112  mov     rbx, [r11+38h]
0x140008116  mov     rbp, [r11+40h]
0x14000811a  mov     rsp, r11
0x14000811d  pop     r15
0x14000811f  pop     r14
0x140008121  pop     r12
0x140008123  pop     rdi
0x140008124  pop     rsi
0x140008125  retn
0x140008126  mov     rcx, [rsp+278h]; this
0x14000812e  mov     edx, 0A0Bh; void *
0x140008133  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008139  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000813f  mov     rcx, [rsp+278h]; this
0x140008147  mov     edx, 0A0Bh; void *
0x14000814c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

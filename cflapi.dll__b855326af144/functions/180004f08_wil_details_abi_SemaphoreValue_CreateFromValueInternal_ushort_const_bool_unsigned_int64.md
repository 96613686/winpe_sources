# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004f08`
- end: `0x180005132`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b38`
- `0x1800095cc`

## callees

- `0x180002490`
- `0x180004f08`
- `0x180005858`
- `0x1800067c4`
- `0x180007104`
- `0x180007798`
- `0x1800077a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004fcc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000506f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004fcc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000506f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005033`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005033`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050c2`

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
0x180004f08  mov     [rsp+arg_8], rbx
0x180004f0d  mov     [rsp+arg_10], rbp
0x180004f12  push    rsi
0x180004f13  push    rdi
0x180004f14  push    r12
0x180004f16  push    r14
0x180004f18  push    r15
0x180004f1a  sub     rsp, 250h
0x180004f21  mov     rax, cs:__security_cookie
0x180004f28  xor     rax, rsp
0x180004f2b  mov     [rsp+278h+var_38], rax
0x180004f33  mov     rax, 0C000000000000000h
0x180004f3d  mov     rbp, r9
0x180004f40  mov     r8, rdx
0x180004f43  mov     rbx, rcx
0x180004f46  test    rax, r9
0x180004f49  jnz     loc_180005119
0x180004f4f  xor     r12d, r12d
0x180004f52  lea     rax, [rsp+278h+Name]
0x180004f57  mov     ecx, 7FFFFFFEh
0x180004f5c  mov     edx, 104h
0x180004f61  lea     esi, [r12+1]
0x180004f66  test    rcx, rcx
0x180004f69  jz      short loc_180004F89
0x180004f6b  movzx   r9d, word ptr [r8]
0x180004f6f  test    r9w, r9w
0x180004f73  jz      short loc_180004F89
0x180004f75  mov     [rax], r9w
0x180004f79  add     r8, 2
0x180004f7d  add     rax, 2
0x180004f81  sub     rcx, rsi
0x180004f84  sub     rdx, rsi; unsigned __int64
0x180004f87  jnz     short loc_180004F66
0x180004f89  test    rdx, rdx
0x180004f8c  lea     rcx, [rax-2]
0x180004f90  lea     r8, aP0; "_p0"
0x180004f97  cmovnz  rcx, rax
0x180004f9b  mov     [rcx], r12w
0x180004f9f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004fa4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004fa9  mov     edx, ebp
0x180004fab  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004fb3  and     edx, 7FFFFFFFh; lInitialCount
0x180004fb9  mov     [rsp+278h+dwFlags], r12d; int
0x180004fbe  mov     r8d, esi
0x180004fc1  lea     r9, [rsp+278h+Name]; lpName
0x180004fc6  cmova   r8d, edx; lMaximumCount
0x180004fca  xor     ecx, ecx; lpSemaphoreAttributes
0x180004fcc  call    cs:__imp_CreateSemaphoreExW
0x180004fd2  mov     r15, rax
0x180004fd5  test    rax, rax
0x180004fd8  jnz     short loc_180005008
0x180004fda  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004fdf  mov     edi, eax
0x180004fe1  test    eax, eax
0x180004fe3  jns     short loc_18000503C
0x180004fe5  mov     rcx, [rsp+278h]; this
0x180004fed  lea     r8, aWil; "wil"
0x180004ff4  mov     r9d, eax; char *
0x180004ff7  mov     edx, 8Bh; void *
0x180004ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005001  mov     eax, edi
0x180005003  jmp     loc_1800050DA
0x180005008  call    cs:__imp_GetLastError
0x18000500e  mov     rdi, [rbx]
0x180005011  test    rdi, rdi
0x180005014  jz      short loc_180005039
0x180005016  call    cs:__imp_GetLastError
0x18000501c  mov     rcx, rdi; hObject
0x18000501f  mov     r14d, eax
0x180005022  call    cs:__imp_CloseHandle
0x180005028  test    eax, eax
0x18000502a  jz      loc_18000511F
0x180005030  mov     ecx, r14d; dwErrCode
0x180005033  call    cs:__imp_SetLastError
0x180005039  mov     [rbx], r15
0x18000503c  lea     r8, asc_180032450; "h"
0x180005043  shr     rbp, 1Fh
0x180005047  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000504c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005051  test    ebp, ebp
0x180005053  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000505b  lea     r9, [rsp+278h+Name]; lpName
0x180005060  mov     [rsp+278h+dwFlags], r12d; int
0x180005065  cmovnz  esi, ebp
0x180005068  mov     edx, ebp; lInitialCount
0x18000506a  mov     r8d, esi; lMaximumCount
0x18000506d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000506f  call    cs:__imp_CreateSemaphoreExW
0x180005075  mov     rsi, rax
0x180005078  test    rax, rax
0x18000507b  jnz     short loc_1800050A8
0x18000507d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005082  mov     ebx, eax
0x180005084  test    eax, eax
0x180005086  jns     short loc_1800050D8
0x180005088  mov     rcx, [rsp+278h]; this
0x180005090  lea     r8, aWil; "wil"
0x180005097  mov     r9d, eax; char *
0x18000509a  mov     edx, 90h; void *
0x18000509f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050a4  mov     eax, ebx
0x1800050a6  jmp     short loc_1800050DA
0x1800050a8  call    cs:__imp_GetLastError
0x1800050ae  mov     rdi, [rbx+8]
0x1800050b2  test    rdi, rdi
0x1800050b5  jz      short loc_1800050D4
0x1800050b7  call    cs:__imp_GetLastError
0x1800050bd  mov     rcx, rdi; hObject
0x1800050c0  mov     ebp, eax
0x1800050c2  call    cs:__imp_CloseHandle
0x1800050c8  test    eax, eax
0x1800050ca  jz      short loc_180005106
0x1800050cc  mov     ecx, ebp; dwErrCode
0x1800050ce  call    cs:__imp_SetLastError
0x1800050d4  mov     [rbx+8], rsi
0x1800050d8  xor     eax, eax
0x1800050da  mov     rcx, [rsp+278h+var_38]
0x1800050e2  xor     rcx, rsp; StackCookie
0x1800050e5  call    __security_check_cookie
0x1800050ea  lea     r11, [rsp+278h+var_28]
0x1800050f2  mov     rbx, [r11+38h]
0x1800050f6  mov     rbp, [r11+40h]
0x1800050fa  mov     rsp, r11
0x1800050fd  pop     r15
0x1800050ff  pop     r14
0x180005101  pop     r12
0x180005103  pop     rdi
0x180005104  pop     rsi
0x180005105  retn
0x180005106  mov     rcx, [rsp+278h]; this
0x18000510e  mov     edx, 0A0Bh; void *
0x180005113  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005119  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000511f  mov     rcx, [rsp+278h]; this
0x180005127  mov     edx, 0A0Bh; void *
0x18000512c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003524`
- end: `0x18000374e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003140`

## callees

- `0x180003524`
- `0x180003d98`
- `0x180004da4`
- `0x1800054c0`
- `0x180005b00`
- `0x180005b10`
- `0x18000c600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035e8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000368b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035e8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000368b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000364f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000364f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000363e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000363e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036de`

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
0x180003524  mov     [rsp+arg_8], rbx
0x180003529  mov     [rsp+arg_10], rbp
0x18000352e  push    rsi
0x18000352f  push    rdi
0x180003530  push    r12
0x180003532  push    r14
0x180003534  push    r15
0x180003536  sub     rsp, 250h
0x18000353d  mov     rax, cs:__security_cookie
0x180003544  xor     rax, rsp
0x180003547  mov     [rsp+278h+var_38], rax
0x18000354f  mov     rax, 0C000000000000000h
0x180003559  mov     rbp, r9
0x18000355c  mov     r8, rdx
0x18000355f  mov     rbx, rcx
0x180003562  test    rax, r9
0x180003565  jnz     loc_180003735
0x18000356b  xor     r12d, r12d
0x18000356e  lea     rax, [rsp+278h+Name]
0x180003573  mov     ecx, 7FFFFFFEh
0x180003578  mov     edx, 104h
0x18000357d  lea     esi, [r12+1]
0x180003582  test    rcx, rcx
0x180003585  jz      short loc_1800035A5
0x180003587  movzx   r9d, word ptr [r8]
0x18000358b  test    r9w, r9w
0x18000358f  jz      short loc_1800035A5
0x180003591  mov     [rax], r9w
0x180003595  add     r8, 2
0x180003599  add     rax, 2
0x18000359d  sub     rcx, rsi
0x1800035a0  sub     rdx, rsi; unsigned __int64
0x1800035a3  jnz     short loc_180003582
0x1800035a5  test    rdx, rdx
0x1800035a8  lea     rcx, [rax-2]
0x1800035ac  lea     r8, aP0; "_p0"
0x1800035b3  cmovnz  rcx, rax
0x1800035b7  mov     [rcx], r12w
0x1800035bb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800035c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800035c5  mov     edx, ebp
0x1800035c7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800035cf  and     edx, 7FFFFFFFh; lInitialCount
0x1800035d5  mov     [rsp+278h+dwFlags], r12d; int
0x1800035da  mov     r8d, esi
0x1800035dd  lea     r9, [rsp+278h+Name]; lpName
0x1800035e2  cmova   r8d, edx; lMaximumCount
0x1800035e6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035e8  call    cs:__imp_CreateSemaphoreExW
0x1800035ee  mov     r15, rax
0x1800035f1  test    rax, rax
0x1800035f4  jnz     short loc_180003624
0x1800035f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035fb  mov     edi, eax
0x1800035fd  test    eax, eax
0x1800035ff  jns     short loc_180003658
0x180003601  mov     rcx, [rsp+278h]; this
0x180003609  lea     r8, aWil; "wil"
0x180003610  mov     r9d, eax; char *
0x180003613  mov     edx, 8Bh; void *
0x180003618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000361d  mov     eax, edi
0x18000361f  jmp     loc_1800036F6
0x180003624  call    cs:__imp_GetLastError
0x18000362a  mov     rdi, [rbx]
0x18000362d  test    rdi, rdi
0x180003630  jz      short loc_180003655
0x180003632  call    cs:__imp_GetLastError
0x180003638  mov     rcx, rdi; hObject
0x18000363b  mov     r14d, eax
0x18000363e  call    cs:__imp_CloseHandle
0x180003644  test    eax, eax
0x180003646  jz      loc_18000373B
0x18000364c  mov     ecx, r14d; dwErrCode
0x18000364f  call    cs:__imp_SetLastError
0x180003655  mov     [rbx], r15
0x180003658  lea     r8, asc_18000FEB8; "h"
0x18000365f  shr     rbp, 1Fh
0x180003663  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003668  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000366d  test    ebp, ebp
0x18000366f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003677  lea     r9, [rsp+278h+Name]; lpName
0x18000367c  mov     [rsp+278h+dwFlags], r12d; int
0x180003681  cmovnz  esi, ebp
0x180003684  mov     edx, ebp; lInitialCount
0x180003686  mov     r8d, esi; lMaximumCount
0x180003689  xor     ecx, ecx; lpSemaphoreAttributes
0x18000368b  call    cs:__imp_CreateSemaphoreExW
0x180003691  mov     rsi, rax
0x180003694  test    rax, rax
0x180003697  jnz     short loc_1800036C4
0x180003699  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000369e  mov     ebx, eax
0x1800036a0  test    eax, eax
0x1800036a2  jns     short loc_1800036F4
0x1800036a4  mov     rcx, [rsp+278h]; this
0x1800036ac  lea     r8, aWil; "wil"
0x1800036b3  mov     r9d, eax; char *
0x1800036b6  mov     edx, 90h; void *
0x1800036bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036c0  mov     eax, ebx
0x1800036c2  jmp     short loc_1800036F6
0x1800036c4  call    cs:__imp_GetLastError
0x1800036ca  mov     rdi, [rbx+8]
0x1800036ce  test    rdi, rdi
0x1800036d1  jz      short loc_1800036F0
0x1800036d3  call    cs:__imp_GetLastError
0x1800036d9  mov     rcx, rdi; hObject
0x1800036dc  mov     ebp, eax
0x1800036de  call    cs:__imp_CloseHandle
0x1800036e4  test    eax, eax
0x1800036e6  jz      short loc_180003722
0x1800036e8  mov     ecx, ebp; dwErrCode
0x1800036ea  call    cs:__imp_SetLastError
0x1800036f0  mov     [rbx+8], rsi
0x1800036f4  xor     eax, eax
0x1800036f6  mov     rcx, [rsp+278h+var_38]
0x1800036fe  xor     rcx, rsp; StackCookie
0x180003701  call    __security_check_cookie
0x180003706  lea     r11, [rsp+278h+var_28]
0x18000370e  mov     rbx, [r11+38h]
0x180003712  mov     rbp, [r11+40h]
0x180003716  mov     rsp, r11
0x180003719  pop     r15
0x18000371b  pop     r14
0x18000371d  pop     r12
0x18000371f  pop     rdi
0x180003720  pop     rsi
0x180003721  retn
0x180003722  mov     rcx, [rsp+278h]; this
0x18000372a  mov     edx, 0A0Bh; void *
0x18000372f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003735  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000373b  mov     rcx, [rsp+278h]; this
0x180003743  mov     edx, 0A0Bh; void *
0x180003748  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

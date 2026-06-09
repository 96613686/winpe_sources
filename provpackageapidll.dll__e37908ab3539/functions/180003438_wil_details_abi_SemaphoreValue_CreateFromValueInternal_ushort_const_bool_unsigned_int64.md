# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003438`
- end: `0x180003669`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003068`

## callees

- `0x180001510`
- `0x180003438`
- `0x180003cc8`
- `0x180004a84`
- `0x180005360`
- `0x18000593c`
- `0x18000594c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003606`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000353d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003501`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035a7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003501`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035fa`

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
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
  const char *v30; // r9
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
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
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
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003438  mov     [rsp+arg_8], rbx
0x18000343d  push    rbp
0x18000343e  push    rsi
0x18000343f  push    rdi
0x180003440  push    r12
0x180003442  push    r13
0x180003444  push    r14
0x180003446  push    r15
0x180003448  sub     rsp, 250h
0x18000344f  mov     rax, cs:__security_cookie
0x180003456  xor     rax, rsp
0x180003459  mov     [rsp+288h+var_48], rax
0x180003461  mov     rax, 0C000000000000000h
0x18000346b  mov     rsi, r9
0x18000346e  mov     r8, rdx
0x180003471  mov     rbx, rcx
0x180003474  test    rax, r9
0x180003477  jnz     loc_180003650
0x18000347d  xor     r12d, r12d
0x180003480  lea     rax, [rsp+288h+Name]
0x180003485  mov     r13d, 104h
0x18000348b  mov     ecx, 7FFFFFFEh
0x180003490  mov     edx, r13d
0x180003493  lea     ebp, [r12+1]
0x180003498  test    rcx, rcx
0x18000349b  jz      short loc_1800034BB
0x18000349d  movzx   r9d, word ptr [r8]
0x1800034a1  test    r9w, r9w
0x1800034a5  jz      short loc_1800034BB
0x1800034a7  mov     [rax], r9w
0x1800034ab  add     r8, 2
0x1800034af  add     rax, 2
0x1800034b3  sub     rcx, rbp
0x1800034b6  sub     rdx, rbp
0x1800034b9  jnz     short loc_180003498
0x1800034bb  test    rdx, rdx
0x1800034be  lea     rcx, [rax-2]
0x1800034c2  lea     r8, aP0; "_p0"
0x1800034c9  mov     rdx, r13; unsigned __int64
0x1800034cc  cmovnz  rcx, rax
0x1800034d0  mov     [rcx], r12w
0x1800034d4  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800034d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800034de  mov     edx, esi
0x1800034e0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800034e8  and     edx, 7FFFFFFFh; lInitialCount
0x1800034ee  mov     [rsp+288h+dwFlags], r12d; int
0x1800034f3  mov     r8d, ebp
0x1800034f6  lea     r9, [rsp+288h+Name]; lpName
0x1800034fb  cmova   r8d, edx; lMaximumCount
0x1800034ff  xor     ecx, ecx; lpSemaphoreAttributes
0x180003501  call    cs:__imp_CreateSemaphoreExW
0x180003507  mov     r15, rax
0x18000350a  test    rax, rax
0x18000350d  jnz     short loc_18000353D
0x18000350f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003514  mov     edi, eax
0x180003516  test    eax, eax
0x180003518  jns     short loc_180003571
0x18000351a  mov     rcx, [rsp+288h]; this
0x180003522  lea     r8, aWil; "wil"
0x180003529  mov     r9d, eax; char *
0x18000352c  mov     edx, 8Bh; void *
0x180003531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003536  mov     eax, edi
0x180003538  jmp     loc_180003612
0x18000353d  call    cs:__imp_GetLastError
0x180003543  mov     rdi, [rbx]
0x180003546  test    rdi, rdi
0x180003549  jz      short loc_18000356E
0x18000354b  call    cs:__imp_GetLastError
0x180003551  mov     rcx, rdi; hObject
0x180003554  mov     r14d, eax
0x180003557  call    cs:__imp_CloseHandle
0x18000355d  test    eax, eax
0x18000355f  jz      loc_180003656
0x180003565  mov     ecx, r14d; dwErrCode
0x180003568  call    cs:__imp_SetLastError
0x18000356e  mov     [rbx], r15
0x180003571  lea     r8, asc_18001AE78; "h"
0x180003578  shr     rsi, 1Fh
0x18000357c  mov     rdx, r13; unsigned __int64
0x18000357f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003584  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003589  test    esi, esi
0x18000358b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003593  lea     r9, [rsp+288h+Name]; lpName
0x180003598  mov     [rsp+288h+dwFlags], r12d; int
0x18000359d  cmovnz  ebp, esi
0x1800035a0  mov     edx, esi; lInitialCount
0x1800035a2  mov     r8d, ebp; lMaximumCount
0x1800035a5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035a7  call    cs:__imp_CreateSemaphoreExW
0x1800035ad  mov     rbp, rax
0x1800035b0  test    rax, rax
0x1800035b3  jnz     short loc_1800035E0
0x1800035b5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035ba  mov     ebx, eax
0x1800035bc  test    eax, eax
0x1800035be  jns     short loc_180003610
0x1800035c0  mov     rcx, [rsp+288h]; this
0x1800035c8  lea     r8, aWil; "wil"
0x1800035cf  mov     r9d, eax; char *
0x1800035d2  mov     edx, 90h; void *
0x1800035d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035dc  mov     eax, ebx
0x1800035de  jmp     short loc_180003612
0x1800035e0  call    cs:__imp_GetLastError
0x1800035e6  mov     rdi, [rbx+8]
0x1800035ea  test    rdi, rdi
0x1800035ed  jz      short loc_18000360C
0x1800035ef  call    cs:__imp_GetLastError
0x1800035f5  mov     rcx, rdi; hObject
0x1800035f8  mov     esi, eax
0x1800035fa  call    cs:__imp_CloseHandle
0x180003600  test    eax, eax
0x180003602  jz      short loc_18000363D
0x180003604  mov     ecx, esi; dwErrCode
0x180003606  call    cs:__imp_SetLastError
0x18000360c  mov     [rbx+8], rbp
0x180003610  xor     eax, eax
0x180003612  mov     rcx, [rsp+288h+var_48]
0x18000361a  xor     rcx, rsp; StackCookie
0x18000361d  call    __security_check_cookie
0x180003622  mov     rbx, [rsp+288h+arg_8]
0x18000362a  add     rsp, 250h
0x180003631  pop     r15
0x180003633  pop     r14
0x180003635  pop     r13
0x180003637  pop     r12
0x180003639  pop     rdi
0x18000363a  pop     rsi
0x18000363b  pop     rbp
0x18000363c  retn
0x18000363d  mov     rcx, [rsp+288h]; this
0x180003645  mov     edx, 0A0Bh; void *
0x18000364a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003650  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003656  mov     rcx, [rsp+288h]; this
0x18000365e  mov     edx, 0A0Bh; void *
0x180003663  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

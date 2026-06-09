# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800086b0`
- end: `0x1800088e1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ee8`
- `0x1800082b8`

## callees

- `0x1800039f0`
- `0x1800086b0`
- `0x180009528`
- `0x18000bab4`
- `0x18000c504`
- `0x18000d438`
- `0x18000d448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000887e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000887e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008872`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008779`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000881f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008779`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000881f`

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
0x1800086b0  mov     [rsp+arg_8], rbx
0x1800086b5  push    rbp
0x1800086b6  push    rsi
0x1800086b7  push    rdi
0x1800086b8  push    r12
0x1800086ba  push    r13
0x1800086bc  push    r14
0x1800086be  push    r15
0x1800086c0  sub     rsp, 250h
0x1800086c7  mov     rax, cs:__security_cookie
0x1800086ce  xor     rax, rsp
0x1800086d1  mov     [rsp+288h+var_48], rax
0x1800086d9  mov     rax, 0C000000000000000h
0x1800086e3  mov     rsi, r9
0x1800086e6  mov     r8, rdx
0x1800086e9  mov     rbx, rcx
0x1800086ec  test    rax, r9
0x1800086ef  jnz     loc_1800088C8
0x1800086f5  xor     r12d, r12d
0x1800086f8  lea     rax, [rsp+288h+Name]
0x1800086fd  mov     r13d, 104h
0x180008703  mov     ecx, 7FFFFFFEh
0x180008708  mov     edx, r13d
0x18000870b  lea     ebp, [r12+1]
0x180008710  test    rcx, rcx
0x180008713  jz      short loc_180008733
0x180008715  movzx   r9d, word ptr [r8]
0x180008719  test    r9w, r9w
0x18000871d  jz      short loc_180008733
0x18000871f  mov     [rax], r9w
0x180008723  add     r8, 2
0x180008727  add     rax, 2
0x18000872b  sub     rcx, rbp
0x18000872e  sub     rdx, rbp
0x180008731  jnz     short loc_180008710
0x180008733  test    rdx, rdx
0x180008736  lea     rcx, [rax-2]
0x18000873a  lea     r8, aP0; "_p0"
0x180008741  mov     rdx, r13; unsigned __int64
0x180008744  cmovnz  rcx, rax
0x180008748  mov     [rcx], r12w
0x18000874c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180008751  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008756  mov     edx, esi
0x180008758  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008760  and     edx, 7FFFFFFFh; lInitialCount
0x180008766  mov     [rsp+288h+dwFlags], r12d; int
0x18000876b  mov     r8d, ebp
0x18000876e  lea     r9, [rsp+288h+Name]; lpName
0x180008773  cmova   r8d, edx; lMaximumCount
0x180008777  xor     ecx, ecx; lpSemaphoreAttributes
0x180008779  call    cs:__imp_CreateSemaphoreExW
0x18000877f  mov     r15, rax
0x180008782  test    rax, rax
0x180008785  jnz     short loc_1800087B5
0x180008787  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000878c  mov     edi, eax
0x18000878e  test    eax, eax
0x180008790  jns     short loc_1800087E9
0x180008792  mov     rcx, [rsp+288h]; this
0x18000879a  lea     r8, aWil; "wil"
0x1800087a1  mov     r9d, eax; char *
0x1800087a4  mov     edx, 8Bh; void *
0x1800087a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087ae  mov     eax, edi
0x1800087b0  jmp     loc_18000888A
0x1800087b5  call    cs:__imp_GetLastError
0x1800087bb  mov     rdi, [rbx]
0x1800087be  test    rdi, rdi
0x1800087c1  jz      short loc_1800087E6
0x1800087c3  call    cs:__imp_GetLastError
0x1800087c9  mov     rcx, rdi; hObject
0x1800087cc  mov     r14d, eax
0x1800087cf  call    cs:__imp_CloseHandle
0x1800087d5  test    eax, eax
0x1800087d7  jz      loc_1800088CE
0x1800087dd  mov     ecx, r14d; dwErrCode
0x1800087e0  call    cs:__imp_SetLastError
0x1800087e6  mov     [rbx], r15
0x1800087e9  lea     r8, asc_18003E5E0; "h"
0x1800087f0  shr     rsi, 1Fh
0x1800087f4  mov     rdx, r13; unsigned __int64
0x1800087f7  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800087fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008801  test    esi, esi
0x180008803  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000880b  lea     r9, [rsp+288h+Name]; lpName
0x180008810  mov     [rsp+288h+dwFlags], r12d; int
0x180008815  cmovnz  ebp, esi
0x180008818  mov     edx, esi; lInitialCount
0x18000881a  mov     r8d, ebp; lMaximumCount
0x18000881d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000881f  call    cs:__imp_CreateSemaphoreExW
0x180008825  mov     rbp, rax
0x180008828  test    rax, rax
0x18000882b  jnz     short loc_180008858
0x18000882d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008832  mov     ebx, eax
0x180008834  test    eax, eax
0x180008836  jns     short loc_180008888
0x180008838  mov     rcx, [rsp+288h]; this
0x180008840  lea     r8, aWil; "wil"
0x180008847  mov     r9d, eax; char *
0x18000884a  mov     edx, 90h; void *
0x18000884f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008854  mov     eax, ebx
0x180008856  jmp     short loc_18000888A
0x180008858  call    cs:__imp_GetLastError
0x18000885e  mov     rdi, [rbx+8]
0x180008862  test    rdi, rdi
0x180008865  jz      short loc_180008884
0x180008867  call    cs:__imp_GetLastError
0x18000886d  mov     rcx, rdi; hObject
0x180008870  mov     esi, eax
0x180008872  call    cs:__imp_CloseHandle
0x180008878  test    eax, eax
0x18000887a  jz      short loc_1800088B5
0x18000887c  mov     ecx, esi; dwErrCode
0x18000887e  call    cs:__imp_SetLastError
0x180008884  mov     [rbx+8], rbp
0x180008888  xor     eax, eax
0x18000888a  mov     rcx, [rsp+288h+var_48]
0x180008892  xor     rcx, rsp; StackCookie
0x180008895  call    __security_check_cookie
0x18000889a  mov     rbx, [rsp+288h+arg_8]
0x1800088a2  add     rsp, 250h
0x1800088a9  pop     r15
0x1800088ab  pop     r14
0x1800088ad  pop     r13
0x1800088af  pop     r12
0x1800088b1  pop     rdi
0x1800088b2  pop     rsi
0x1800088b3  pop     rbp
0x1800088b4  retn
0x1800088b5  mov     rcx, [rsp+288h]; this
0x1800088bd  mov     edx, 0A0Bh; void *
0x1800088c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800088c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800088ce  mov     rcx, [rsp+288h]; this
0x1800088d6  mov     edx, 0A0Bh; void *
0x1800088db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

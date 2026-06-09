# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005570`
- end: `0x18000577d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800048f8`
- `0x180004c9c`

## callees

- `0x180002270`
- `0x180005570`
- `0x180006b18`
- `0x180009984`
- `0x18000b68c`
- `0x18000c57c`
- `0x18000c58c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005702`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005719`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005719`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005634`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800056d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005634`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800056d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570d`

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
0x180005570  mov     [rsp+arg_8], rbx
0x180005575  mov     [rsp+arg_10], rbp
0x18000557a  push    rsi
0x18000557b  push    rdi
0x18000557c  push    r12
0x18000557e  push    r14
0x180005580  push    r15
0x180005582  sub     rsp, 250h
0x180005589  mov     rax, cs:__security_cookie
0x180005590  xor     rax, rsp
0x180005593  mov     [rsp+278h+var_38], rax
0x18000559b  mov     rax, 0C000000000000000h
0x1800055a5  mov     rbp, r9
0x1800055a8  mov     r8, rdx
0x1800055ab  mov     rdi, rcx
0x1800055ae  test    rax, r9
0x1800055b1  jnz     loc_180005764
0x1800055b7  xor     r12d, r12d
0x1800055ba  lea     rax, [rsp+278h+Name]
0x1800055bf  mov     ecx, 7FFFFFFEh
0x1800055c4  mov     edx, 104h
0x1800055c9  lea     esi, [r12+1]
0x1800055ce  test    rcx, rcx
0x1800055d1  jz      short loc_1800055F1
0x1800055d3  movzx   r9d, word ptr [r8]
0x1800055d7  test    r9w, r9w
0x1800055db  jz      short loc_1800055F1
0x1800055dd  mov     [rax], r9w
0x1800055e1  add     r8, 2
0x1800055e5  add     rax, 2
0x1800055e9  sub     rcx, rsi
0x1800055ec  sub     rdx, rsi; unsigned __int64
0x1800055ef  jnz     short loc_1800055CE
0x1800055f1  test    rdx, rdx
0x1800055f4  lea     rcx, [rax-2]
0x1800055f8  lea     r8, aP0; "_p0"
0x1800055ff  cmovnz  rcx, rax
0x180005603  mov     [rcx], r12w
0x180005607  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000560c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005611  mov     edx, ebp
0x180005613  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000561b  and     edx, 7FFFFFFFh; lInitialCount
0x180005621  mov     [rsp+278h+dwFlags], r12d; int
0x180005626  mov     r8d, esi
0x180005629  lea     r9, [rsp+278h+Name]; lpName
0x18000562e  cmova   r8d, edx; lMaximumCount
0x180005632  xor     ecx, ecx; lpSemaphoreAttributes
0x180005634  call    cs:__imp_CreateSemaphoreExW
0x18000563a  mov     r15, rax
0x18000563d  test    rax, rax
0x180005640  jnz     short loc_180005669
0x180005642  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005647  mov     ebx, eax
0x180005649  test    eax, eax
0x18000564b  jns     short loc_18000569D
0x18000564d  mov     edx, 8Bh; void *
0x180005652  mov     rcx, [rsp+278h]; this
0x18000565a  mov     r9d, ebx; char *
0x18000565d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005662  mov     eax, ebx
0x180005664  jmp     loc_180005725
0x180005669  call    cs:__imp_GetLastError
0x18000566f  mov     rbx, [rdi]
0x180005672  test    rbx, rbx
0x180005675  jz      short loc_18000569A
0x180005677  call    cs:__imp_GetLastError
0x18000567d  mov     rcx, rbx; hObject
0x180005680  mov     r14d, eax
0x180005683  call    cs:__imp_CloseHandle
0x180005689  test    eax, eax
0x18000568b  jz      loc_18000576A
0x180005691  mov     ecx, r14d; dwErrCode
0x180005694  call    cs:__imp_SetLastError
0x18000569a  mov     [rdi], r15
0x18000569d  lea     r8, asc_180016F00; "h"
0x1800056a4  shr     rbp, 1Fh
0x1800056a8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800056ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800056b2  test    ebp, ebp
0x1800056b4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800056bc  lea     r9, [rsp+278h+Name]; lpName
0x1800056c1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800056c6  cmovnz  esi, ebp
0x1800056c9  mov     edx, ebp; lInitialCount
0x1800056cb  mov     r8d, esi; lMaximumCount
0x1800056ce  xor     ecx, ecx; lpSemaphoreAttributes
0x1800056d0  call    cs:__imp_CreateSemaphoreExW
0x1800056d6  mov     rsi, rax
0x1800056d9  test    rax, rax
0x1800056dc  jnz     short loc_1800056F3
0x1800056de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800056e3  mov     ebx, eax
0x1800056e5  test    eax, eax
0x1800056e7  jns     short loc_180005723
0x1800056e9  mov     edx, 90h
0x1800056ee  jmp     loc_180005652
0x1800056f3  call    cs:__imp_GetLastError
0x1800056f9  mov     rbx, [rdi+8]
0x1800056fd  test    rbx, rbx
0x180005700  jz      short loc_18000571F
0x180005702  call    cs:__imp_GetLastError
0x180005708  mov     rcx, rbx; hObject
0x18000570b  mov     ebp, eax
0x18000570d  call    cs:__imp_CloseHandle
0x180005713  test    eax, eax
0x180005715  jz      short loc_180005751
0x180005717  mov     ecx, ebp; dwErrCode
0x180005719  call    cs:__imp_SetLastError
0x18000571f  mov     [rdi+8], rsi
0x180005723  xor     eax, eax
0x180005725  mov     rcx, [rsp+278h+var_38]
0x18000572d  xor     rcx, rsp; StackCookie
0x180005730  call    __security_check_cookie
0x180005735  lea     r11, [rsp+278h+var_28]
0x18000573d  mov     rbx, [r11+38h]
0x180005741  mov     rbp, [r11+40h]
0x180005745  mov     rsp, r11
0x180005748  pop     r15
0x18000574a  pop     r14
0x18000574c  pop     r12
0x18000574e  pop     rdi
0x18000574f  pop     rsi
0x180005750  retn
0x180005751  mov     rcx, [rsp+278h]; this
0x180005759  mov     edx, 0A0Bh; void *
0x18000575e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005764  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000576a  mov     rcx, [rsp+278h]; this
0x180005772  mov     edx, 0A0Bh; void *
0x180005777  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

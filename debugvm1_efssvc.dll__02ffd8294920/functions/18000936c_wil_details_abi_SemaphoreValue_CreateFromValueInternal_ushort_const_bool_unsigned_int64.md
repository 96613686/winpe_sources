# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000936c`
- end: `0x180009579`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008fc8`

## callees

- `0x18000936c`
- `0x180009bf0`
- `0x18000ab30`
- `0x18000ad78`
- `0x18000b204`
- `0x18000b214`
- `0x18000c3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009515`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094fe`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009430`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800094cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009430`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800094cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000947f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000947f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009509`

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
0x18000936c  mov     [rsp+arg_8], rbx
0x180009371  mov     [rsp+arg_10], rbp
0x180009376  push    rsi
0x180009377  push    rdi
0x180009378  push    r12
0x18000937a  push    r14
0x18000937c  push    r15
0x18000937e  sub     rsp, 250h
0x180009385  mov     rax, cs:__security_cookie
0x18000938c  xor     rax, rsp
0x18000938f  mov     [rsp+278h+var_38], rax
0x180009397  mov     rax, 0C000000000000000h
0x1800093a1  mov     rbp, r9
0x1800093a4  mov     r8, rdx
0x1800093a7  mov     rdi, rcx
0x1800093aa  test    rax, r9
0x1800093ad  jnz     loc_180009560
0x1800093b3  xor     r12d, r12d
0x1800093b6  lea     rax, [rsp+278h+Name]
0x1800093bb  mov     ecx, 7FFFFFFEh
0x1800093c0  mov     edx, 104h
0x1800093c5  lea     esi, [r12+1]
0x1800093ca  test    rcx, rcx
0x1800093cd  jz      short loc_1800093ED
0x1800093cf  movzx   r9d, word ptr [r8]
0x1800093d3  test    r9w, r9w
0x1800093d7  jz      short loc_1800093ED
0x1800093d9  mov     [rax], r9w
0x1800093dd  add     r8, 2
0x1800093e1  add     rax, 2
0x1800093e5  sub     rcx, rsi
0x1800093e8  sub     rdx, rsi; unsigned __int64
0x1800093eb  jnz     short loc_1800093CA
0x1800093ed  test    rdx, rdx
0x1800093f0  lea     rcx, [rax-2]
0x1800093f4  lea     r8, aP0; "_p0"
0x1800093fb  cmovnz  rcx, rax
0x1800093ff  mov     [rcx], r12w
0x180009403  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180009408  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000940d  mov     edx, ebp
0x18000940f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009417  and     edx, 7FFFFFFFh; lInitialCount
0x18000941d  mov     [rsp+278h+dwFlags], r12d; int
0x180009422  mov     r8d, esi
0x180009425  lea     r9, [rsp+278h+Name]; lpName
0x18000942a  cmova   r8d, edx; lMaximumCount
0x18000942e  xor     ecx, ecx; lpSemaphoreAttributes
0x180009430  call    cs:__imp_CreateSemaphoreExW
0x180009436  mov     r15, rax
0x180009439  test    rax, rax
0x18000943c  jnz     short loc_180009465
0x18000943e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009443  mov     ebx, eax
0x180009445  test    eax, eax
0x180009447  jns     short loc_180009499
0x180009449  mov     edx, 8Bh; void *
0x18000944e  mov     rcx, [rsp+278h]; this
0x180009456  mov     r9d, ebx; char *
0x180009459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000945e  mov     eax, ebx
0x180009460  jmp     loc_180009521
0x180009465  call    cs:__imp_GetLastError
0x18000946b  mov     rbx, [rdi]
0x18000946e  test    rbx, rbx
0x180009471  jz      short loc_180009496
0x180009473  call    cs:__imp_GetLastError
0x180009479  mov     rcx, rbx; hObject
0x18000947c  mov     r14d, eax
0x18000947f  call    cs:__imp_CloseHandle
0x180009485  test    eax, eax
0x180009487  jz      loc_180009566
0x18000948d  mov     ecx, r14d; dwErrCode
0x180009490  call    cs:__imp_SetLastError
0x180009496  mov     [rdi], r15
0x180009499  lea     r8, asc_180013150; "h"
0x1800094a0  shr     rbp, 1Fh
0x1800094a4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800094a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800094ae  test    ebp, ebp
0x1800094b0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800094b8  lea     r9, [rsp+278h+Name]; lpName
0x1800094bd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800094c2  cmovnz  esi, ebp
0x1800094c5  mov     edx, ebp; lInitialCount
0x1800094c7  mov     r8d, esi; lMaximumCount
0x1800094ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1800094cc  call    cs:__imp_CreateSemaphoreExW
0x1800094d2  mov     rsi, rax
0x1800094d5  test    rax, rax
0x1800094d8  jnz     short loc_1800094EF
0x1800094da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800094df  mov     ebx, eax
0x1800094e1  test    eax, eax
0x1800094e3  jns     short loc_18000951F
0x1800094e5  mov     edx, 90h
0x1800094ea  jmp     loc_18000944E
0x1800094ef  call    cs:__imp_GetLastError
0x1800094f5  mov     rbx, [rdi+8]
0x1800094f9  test    rbx, rbx
0x1800094fc  jz      short loc_18000951B
0x1800094fe  call    cs:__imp_GetLastError
0x180009504  mov     rcx, rbx; hObject
0x180009507  mov     ebp, eax
0x180009509  call    cs:__imp_CloseHandle
0x18000950f  test    eax, eax
0x180009511  jz      short loc_18000954D
0x180009513  mov     ecx, ebp; dwErrCode
0x180009515  call    cs:__imp_SetLastError
0x18000951b  mov     [rdi+8], rsi
0x18000951f  xor     eax, eax
0x180009521  mov     rcx, [rsp+278h+var_38]
0x180009529  xor     rcx, rsp; StackCookie
0x18000952c  call    __security_check_cookie
0x180009531  lea     r11, [rsp+278h+var_28]
0x180009539  mov     rbx, [r11+38h]
0x18000953d  mov     rbp, [r11+40h]
0x180009541  mov     rsp, r11
0x180009544  pop     r15
0x180009546  pop     r14
0x180009548  pop     r12
0x18000954a  pop     rdi
0x18000954b  pop     rsi
0x18000954c  retn
0x18000954d  mov     rcx, [rsp+278h]; this
0x180009555  mov     edx, 0A0Bh; void *
0x18000955a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009560  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009566  mov     rcx, [rsp+278h]; this
0x18000956e  mov     edx, 0A0Bh; void *
0x180009573  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

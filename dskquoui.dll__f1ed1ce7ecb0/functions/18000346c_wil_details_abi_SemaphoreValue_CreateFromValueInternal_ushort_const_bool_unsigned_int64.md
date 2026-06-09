# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000346c`
- end: `0x180003679`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800030c8`

## callees

- `0x180001510`
- `0x18000346c`
- `0x180003cd8`
- `0x180004a84`
- `0x180005360`
- `0x1800058ec`
- `0x1800058fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003530`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003530`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003615`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000357f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003609`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000357f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003609`

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
0x18000346c  mov     [rsp+arg_8], rbx
0x180003471  mov     [rsp+arg_10], rbp
0x180003476  push    rsi
0x180003477  push    rdi
0x180003478  push    r12
0x18000347a  push    r14
0x18000347c  push    r15
0x18000347e  sub     rsp, 250h
0x180003485  mov     rax, cs:__security_cookie
0x18000348c  xor     rax, rsp
0x18000348f  mov     [rsp+278h+var_38], rax
0x180003497  mov     rax, 0C000000000000000h
0x1800034a1  mov     rbp, r9
0x1800034a4  mov     r8, rdx
0x1800034a7  mov     rdi, rcx
0x1800034aa  test    rax, r9
0x1800034ad  jnz     loc_180003660
0x1800034b3  xor     r12d, r12d
0x1800034b6  lea     rax, [rsp+278h+Name]
0x1800034bb  mov     ecx, 7FFFFFFEh
0x1800034c0  mov     edx, 104h
0x1800034c5  lea     esi, [r12+1]
0x1800034ca  test    rcx, rcx
0x1800034cd  jz      short loc_1800034ED
0x1800034cf  movzx   r9d, word ptr [r8]
0x1800034d3  test    r9w, r9w
0x1800034d7  jz      short loc_1800034ED
0x1800034d9  mov     [rax], r9w
0x1800034dd  add     r8, 2
0x1800034e1  add     rax, 2
0x1800034e5  sub     rcx, rsi
0x1800034e8  sub     rdx, rsi; unsigned __int64
0x1800034eb  jnz     short loc_1800034CA
0x1800034ed  test    rdx, rdx
0x1800034f0  lea     rcx, [rax-2]
0x1800034f4  lea     r8, aP0; "_p0"
0x1800034fb  cmovnz  rcx, rax
0x1800034ff  mov     [rcx], r12w
0x180003503  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003508  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000350d  mov     edx, ebp
0x18000350f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003517  and     edx, 7FFFFFFFh; lInitialCount
0x18000351d  mov     [rsp+278h+dwFlags], r12d; int
0x180003522  mov     r8d, esi
0x180003525  lea     r9, [rsp+278h+Name]; lpName
0x18000352a  cmova   r8d, edx; lMaximumCount
0x18000352e  xor     ecx, ecx; lpSemaphoreAttributes
0x180003530  call    cs:__imp_CreateSemaphoreExW
0x180003536  mov     r15, rax
0x180003539  test    rax, rax
0x18000353c  jnz     short loc_180003565
0x18000353e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003543  mov     ebx, eax
0x180003545  test    eax, eax
0x180003547  jns     short loc_180003599
0x180003549  mov     edx, 8Bh; void *
0x18000354e  mov     rcx, [rsp+278h]; this
0x180003556  mov     r9d, ebx; char *
0x180003559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000355e  mov     eax, ebx
0x180003560  jmp     loc_180003621
0x180003565  call    cs:__imp_GetLastError
0x18000356b  mov     rbx, [rdi]
0x18000356e  test    rbx, rbx
0x180003571  jz      short loc_180003596
0x180003573  call    cs:__imp_GetLastError
0x180003579  mov     rcx, rbx; hObject
0x18000357c  mov     r14d, eax
0x18000357f  call    cs:__imp_CloseHandle
0x180003585  test    eax, eax
0x180003587  jz      loc_180003666
0x18000358d  mov     ecx, r14d; dwErrCode
0x180003590  call    cs:__imp_SetLastError
0x180003596  mov     [rdi], r15
0x180003599  lea     r8, asc_1800219E8; "h"
0x1800035a0  shr     rbp, 1Fh
0x1800035a4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800035a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800035ae  test    ebp, ebp
0x1800035b0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800035b8  lea     r9, [rsp+278h+Name]; lpName
0x1800035bd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800035c2  cmovnz  esi, ebp
0x1800035c5  mov     edx, ebp; lInitialCount
0x1800035c7  mov     r8d, esi; lMaximumCount
0x1800035ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035cc  call    cs:__imp_CreateSemaphoreExW
0x1800035d2  mov     rsi, rax
0x1800035d5  test    rax, rax
0x1800035d8  jnz     short loc_1800035EF
0x1800035da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035df  mov     ebx, eax
0x1800035e1  test    eax, eax
0x1800035e3  jns     short loc_18000361F
0x1800035e5  mov     edx, 90h
0x1800035ea  jmp     loc_18000354E
0x1800035ef  call    cs:__imp_GetLastError
0x1800035f5  mov     rbx, [rdi+8]
0x1800035f9  test    rbx, rbx
0x1800035fc  jz      short loc_18000361B
0x1800035fe  call    cs:__imp_GetLastError
0x180003604  mov     rcx, rbx; hObject
0x180003607  mov     ebp, eax
0x180003609  call    cs:__imp_CloseHandle
0x18000360f  test    eax, eax
0x180003611  jz      short loc_18000364D
0x180003613  mov     ecx, ebp; dwErrCode
0x180003615  call    cs:__imp_SetLastError
0x18000361b  mov     [rdi+8], rsi
0x18000361f  xor     eax, eax
0x180003621  mov     rcx, [rsp+278h+var_38]
0x180003629  xor     rcx, rsp; StackCookie
0x18000362c  call    __security_check_cookie
0x180003631  lea     r11, [rsp+278h+var_28]
0x180003639  mov     rbx, [r11+38h]
0x18000363d  mov     rbp, [r11+40h]
0x180003641  mov     rsp, r11
0x180003644  pop     r15
0x180003646  pop     r14
0x180003648  pop     r12
0x18000364a  pop     rdi
0x18000364b  pop     rsi
0x18000364c  retn
0x18000364d  mov     rcx, [rsp+278h]; this
0x180003655  mov     edx, 0A0Bh; void *
0x18000365a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003660  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003666  mov     rcx, [rsp+278h]; this
0x18000366e  mov     edx, 0A0Bh; void *
0x180003673  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

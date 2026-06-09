# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003e60`
- end: `0x14000406d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003830`

## callees

- `0x140003e60`
- `0x140004618`
- `0x140005584`
- `0x140005ca0`
- `0x140006474`
- `0x140006484`
- `0x14000a370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f24`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003fc0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f24`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003fc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004009`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ffd`

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
0x140003e60  mov     [rsp+arg_8], rbx
0x140003e65  mov     [rsp+arg_10], rbp
0x140003e6a  push    rsi
0x140003e6b  push    rdi
0x140003e6c  push    r12
0x140003e6e  push    r14
0x140003e70  push    r15
0x140003e72  sub     rsp, 250h
0x140003e79  mov     rax, cs:__security_cookie
0x140003e80  xor     rax, rsp
0x140003e83  mov     [rsp+278h+var_38], rax
0x140003e8b  mov     rax, 0C000000000000000h
0x140003e95  mov     rbp, r9
0x140003e98  mov     r8, rdx
0x140003e9b  mov     rdi, rcx
0x140003e9e  test    rax, r9
0x140003ea1  jnz     loc_140004054
0x140003ea7  xor     r12d, r12d
0x140003eaa  lea     rax, [rsp+278h+Name]
0x140003eaf  mov     ecx, 7FFFFFFEh
0x140003eb4  mov     edx, 104h
0x140003eb9  lea     esi, [r12+1]
0x140003ebe  test    rcx, rcx
0x140003ec1  jz      short loc_140003EE1
0x140003ec3  movzx   r9d, word ptr [r8]
0x140003ec7  test    r9w, r9w
0x140003ecb  jz      short loc_140003EE1
0x140003ecd  mov     [rax], r9w
0x140003ed1  add     r8, 2
0x140003ed5  add     rax, 2
0x140003ed9  sub     rcx, rsi
0x140003edc  sub     rdx, rsi; unsigned __int64
0x140003edf  jnz     short loc_140003EBE
0x140003ee1  test    rdx, rdx
0x140003ee4  lea     rcx, [rax-2]
0x140003ee8  lea     r8, aP0; "_p0"
0x140003eef  cmovnz  rcx, rax
0x140003ef3  mov     [rcx], r12w
0x140003ef7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003efc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003f01  mov     edx, ebp
0x140003f03  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003f0b  and     edx, 7FFFFFFFh; lInitialCount
0x140003f11  mov     [rsp+278h+dwFlags], r12d; int
0x140003f16  mov     r8d, esi
0x140003f19  lea     r9, [rsp+278h+Name]; lpName
0x140003f1e  cmova   r8d, edx; lMaximumCount
0x140003f22  xor     ecx, ecx; lpSemaphoreAttributes
0x140003f24  call    cs:__imp_CreateSemaphoreExW
0x140003f2a  mov     r15, rax
0x140003f2d  test    rax, rax
0x140003f30  jnz     short loc_140003F59
0x140003f32  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f37  mov     ebx, eax
0x140003f39  test    eax, eax
0x140003f3b  jns     short loc_140003F8D
0x140003f3d  mov     edx, 8Bh; void *
0x140003f42  mov     rcx, [rsp+278h]; this
0x140003f4a  mov     r9d, ebx; char *
0x140003f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f52  mov     eax, ebx
0x140003f54  jmp     loc_140004015
0x140003f59  call    cs:__imp_GetLastError
0x140003f5f  mov     rbx, [rdi]
0x140003f62  test    rbx, rbx
0x140003f65  jz      short loc_140003F8A
0x140003f67  call    cs:__imp_GetLastError
0x140003f6d  mov     rcx, rbx; hObject
0x140003f70  mov     r14d, eax
0x140003f73  call    cs:__imp_CloseHandle
0x140003f79  test    eax, eax
0x140003f7b  jz      loc_14000405A
0x140003f81  mov     ecx, r14d; dwErrCode
0x140003f84  call    cs:__imp_SetLastError
0x140003f8a  mov     [rdi], r15
0x140003f8d  lea     r8, asc_14000CAD8; "h"
0x140003f94  shr     rbp, 1Fh
0x140003f98  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003f9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003fa2  test    ebp, ebp
0x140003fa4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003fac  lea     r9, [rsp+278h+Name]; lpName
0x140003fb1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003fb6  cmovnz  esi, ebp
0x140003fb9  mov     edx, ebp; lInitialCount
0x140003fbb  mov     r8d, esi; lMaximumCount
0x140003fbe  xor     ecx, ecx; lpSemaphoreAttributes
0x140003fc0  call    cs:__imp_CreateSemaphoreExW
0x140003fc6  mov     rsi, rax
0x140003fc9  test    rax, rax
0x140003fcc  jnz     short loc_140003FE3
0x140003fce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003fd3  mov     ebx, eax
0x140003fd5  test    eax, eax
0x140003fd7  jns     short loc_140004013
0x140003fd9  mov     edx, 90h
0x140003fde  jmp     loc_140003F42
0x140003fe3  call    cs:__imp_GetLastError
0x140003fe9  mov     rbx, [rdi+8]
0x140003fed  test    rbx, rbx
0x140003ff0  jz      short loc_14000400F
0x140003ff2  call    cs:__imp_GetLastError
0x140003ff8  mov     rcx, rbx; hObject
0x140003ffb  mov     ebp, eax
0x140003ffd  call    cs:__imp_CloseHandle
0x140004003  test    eax, eax
0x140004005  jz      short loc_140004041
0x140004007  mov     ecx, ebp; dwErrCode
0x140004009  call    cs:__imp_SetLastError
0x14000400f  mov     [rdi+8], rsi
0x140004013  xor     eax, eax
0x140004015  mov     rcx, [rsp+278h+var_38]
0x14000401d  xor     rcx, rsp; StackCookie
0x140004020  call    __security_check_cookie
0x140004025  lea     r11, [rsp+278h+var_28]
0x14000402d  mov     rbx, [r11+38h]
0x140004031  mov     rbp, [r11+40h]
0x140004035  mov     rsp, r11
0x140004038  pop     r15
0x14000403a  pop     r14
0x14000403c  pop     r12
0x14000403e  pop     rdi
0x14000403f  pop     rsi
0x140004040  retn
0x140004041  mov     rcx, [rsp+278h]; this
0x140004049  mov     edx, 0A0Bh; void *
0x14000404e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004054  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000405a  mov     rcx, [rsp+278h]; this
0x140004062  mov     edx, 0A0Bh; void *
0x140004067  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

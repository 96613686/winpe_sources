# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000f2cc`
- end: `0x14000f4d9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000eb58`
- `0x14000eefc`

## callees

- `0x140002f60`
- `0x14000f2cc`
- `0x140010118`
- `0x140012554`
- `0x140012f98`
- `0x140013d7c`
- `0x140013d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000f390`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000f42c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000f390`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000f42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f45e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f3f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f475`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f3f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f469`

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
0x14000f2cc  mov     [rsp+arg_8], rbx
0x14000f2d1  mov     [rsp+arg_10], rbp
0x14000f2d6  push    rsi
0x14000f2d7  push    rdi
0x14000f2d8  push    r12
0x14000f2da  push    r14
0x14000f2dc  push    r15
0x14000f2de  sub     rsp, 250h
0x14000f2e5  mov     rax, cs:__security_cookie
0x14000f2ec  xor     rax, rsp
0x14000f2ef  mov     [rsp+278h+var_38], rax
0x14000f2f7  mov     rax, 0C000000000000000h
0x14000f301  mov     rbp, r9
0x14000f304  mov     r8, rdx
0x14000f307  mov     rdi, rcx
0x14000f30a  test    rax, r9
0x14000f30d  jnz     loc_14000F4C0
0x14000f313  xor     r12d, r12d
0x14000f316  lea     rax, [rsp+278h+Name]
0x14000f31b  mov     ecx, 7FFFFFFEh
0x14000f320  mov     edx, 104h
0x14000f325  lea     esi, [r12+1]
0x14000f32a  test    rcx, rcx
0x14000f32d  jz      short loc_14000F34D
0x14000f32f  movzx   r9d, word ptr [r8]
0x14000f333  test    r9w, r9w
0x14000f337  jz      short loc_14000F34D
0x14000f339  mov     [rax], r9w
0x14000f33d  add     r8, 2
0x14000f341  add     rax, 2
0x14000f345  sub     rcx, rsi
0x14000f348  sub     rdx, rsi; unsigned __int64
0x14000f34b  jnz     short loc_14000F32A
0x14000f34d  test    rdx, rdx
0x14000f350  lea     rcx, [rax-2]
0x14000f354  lea     r8, aP0; "_p0"
0x14000f35b  cmovnz  rcx, rax
0x14000f35f  mov     [rcx], r12w
0x14000f363  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000f368  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000f36d  mov     edx, ebp
0x14000f36f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000f377  and     edx, 7FFFFFFFh; lInitialCount
0x14000f37d  mov     [rsp+278h+dwFlags], r12d; int
0x14000f382  mov     r8d, esi
0x14000f385  lea     r9, [rsp+278h+Name]; lpName
0x14000f38a  cmova   r8d, edx; lMaximumCount
0x14000f38e  xor     ecx, ecx; lpSemaphoreAttributes
0x14000f390  call    cs:__imp_CreateSemaphoreExW
0x14000f396  mov     r15, rax
0x14000f399  test    rax, rax
0x14000f39c  jnz     short loc_14000F3C5
0x14000f39e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000f3a3  mov     ebx, eax
0x14000f3a5  test    eax, eax
0x14000f3a7  jns     short loc_14000F3F9
0x14000f3a9  mov     edx, 8Bh; void *
0x14000f3ae  mov     rcx, [rsp+278h]; this
0x14000f3b6  mov     r9d, ebx; char *
0x14000f3b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f3be  mov     eax, ebx
0x14000f3c0  jmp     loc_14000F481
0x14000f3c5  call    cs:__imp_GetLastError
0x14000f3cb  mov     rbx, [rdi]
0x14000f3ce  test    rbx, rbx
0x14000f3d1  jz      short loc_14000F3F6
0x14000f3d3  call    cs:__imp_GetLastError
0x14000f3d9  mov     rcx, rbx; hObject
0x14000f3dc  mov     r14d, eax
0x14000f3df  call    cs:__imp_CloseHandle
0x14000f3e5  test    eax, eax
0x14000f3e7  jz      loc_14000F4C6
0x14000f3ed  mov     ecx, r14d; dwErrCode
0x14000f3f0  call    cs:__imp_SetLastError
0x14000f3f6  mov     [rdi], r15
0x14000f3f9  lea     r8, asc_14005E780; "h"
0x14000f400  shr     rbp, 1Fh
0x14000f404  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000f409  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000f40e  test    ebp, ebp
0x14000f410  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000f418  lea     r9, [rsp+278h+Name]; lpName
0x14000f41d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14000f422  cmovnz  esi, ebp
0x14000f425  mov     edx, ebp; lInitialCount
0x14000f427  mov     r8d, esi; lMaximumCount
0x14000f42a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000f42c  call    cs:__imp_CreateSemaphoreExW
0x14000f432  mov     rsi, rax
0x14000f435  test    rax, rax
0x14000f438  jnz     short loc_14000F44F
0x14000f43a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000f43f  mov     ebx, eax
0x14000f441  test    eax, eax
0x14000f443  jns     short loc_14000F47F
0x14000f445  mov     edx, 90h
0x14000f44a  jmp     loc_14000F3AE
0x14000f44f  call    cs:__imp_GetLastError
0x14000f455  mov     rbx, [rdi+8]
0x14000f459  test    rbx, rbx
0x14000f45c  jz      short loc_14000F47B
0x14000f45e  call    cs:__imp_GetLastError
0x14000f464  mov     rcx, rbx; hObject
0x14000f467  mov     ebp, eax
0x14000f469  call    cs:__imp_CloseHandle
0x14000f46f  test    eax, eax
0x14000f471  jz      short loc_14000F4AD
0x14000f473  mov     ecx, ebp; dwErrCode
0x14000f475  call    cs:__imp_SetLastError
0x14000f47b  mov     [rdi+8], rsi
0x14000f47f  xor     eax, eax
0x14000f481  mov     rcx, [rsp+278h+var_38]
0x14000f489  xor     rcx, rsp; StackCookie
0x14000f48c  call    __security_check_cookie
0x14000f491  lea     r11, [rsp+278h+var_28]
0x14000f499  mov     rbx, [r11+38h]
0x14000f49d  mov     rbp, [r11+40h]
0x14000f4a1  mov     rsp, r11
0x14000f4a4  pop     r15
0x14000f4a6  pop     r14
0x14000f4a8  pop     r12
0x14000f4aa  pop     rdi
0x14000f4ab  pop     rsi
0x14000f4ac  retn
0x14000f4ad  mov     rcx, [rsp+278h]; this
0x14000f4b5  mov     edx, 0A0Bh; void *
0x14000f4ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f4c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000f4c6  mov     rcx, [rsp+278h]; this
0x14000f4ce  mov     edx, 0A0Bh; void *
0x14000f4d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cf80`
- end: `0x18000d2e4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `868`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b1b0`

## callees

- `0x1800017b0`
- `0x18000cf80`
- `0x18000eee0`
- `0x180013af0`
- `0x1800187e0`
- `0x1800187f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d0c9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d1e9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d0c9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d1e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d140`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d140`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d12a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d12a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d247`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  bool v16; // zf
  __int64 v17; // rax
  __int64 v18; // rcx
  WCHAR *v19; // rdx
  WCHAR *v20; // rcx
  LONG v21; // r15d
  LONG v22; // r8d
  wil::details *v23; // rcx
  HANDLE Semaphore; // r14
  int LastErrorFailHr; // eax
  unsigned int v26; // r8d
  unsigned int v27; // esi
  void *v29; // rsi
  DWORD LastError; // ebp
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned __int64 v33; // r12
  WCHAR *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  WCHAR *v37; // rax
  const wchar_t *v38; // rcx
  __int64 v39; // rbx
  WCHAR *v40; // rcx
  wil::details *v41; // rcx
  HANDLE v42; // rdi
  int v43; // eax
  unsigned int v44; // r8d
  unsigned int v45; // ebx
  void *v46; // rbx
  DWORD v47; // esi
  unsigned int v48; // r8d
  const char *v49; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v7 - 1;
  if ( v10 )
    v11 = v7;
  *v11 = 0;
  v12 = 260;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 260 - v12;
  if ( v12 )
  {
    v15 = L"_p0";
    v17 = v12;
    v16 = v14 == 260;
    v18 = 2147483646;
    v19 = &Name[v14];
    if ( !v16 )
    {
      do
      {
        if ( !v18 )
          break;
        if ( !*v15 )
          break;
        *v19++ = *v15++;
        --v18;
        --v17;
      }
      while ( v17 );
    }
    v20 = v19 - 1;
    if ( v17 )
      v20 = v19;
    *v20 = 0;
  }
  v21 = 1;
  v22 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v22 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v22, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v29 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
    v27 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        v26,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v27;
    }
  }
  v33 = a4 >> 31;
  v34 = Name;
  v35 = 260;
  do
  {
    if ( !*v34 )
      break;
    ++v34;
    --v35;
  }
  while ( v35 );
  v36 = 260 - v35;
  if ( v35 )
  {
    v37 = &Name[v36];
    v38 = L"h";
    v39 = 260 - v36;
    if ( 260 != v36 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v38 )
          break;
        *v37++ = *v38++;
        --v8;
        --v39;
      }
      while ( v39 );
    }
    v40 = v37 - 1;
    if ( v39 )
      v40 = v37;
    *v40 = 0;
  }
  if ( (_DWORD)v33 )
    v21 = v33;
  v42 = CreateSemaphoreExW(0, v33, v21, Name, 0, 0x1F0003u);
  if ( v42 )
  {
    GetLastError();
    v46 = (void *)*((_QWORD *)this + 1);
    if ( v46 )
    {
      v47 = GetLastError();
      if ( !CloseHandle(v46) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v48, v49);
      SetLastError(v47);
    }
    *((_QWORD *)this + 1) = v42;
  }
  else
  {
    v43 = wil::details::GetLastErrorFailHr(v41);
    v45 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v44, (const char *)(unsigned int)v43, dwFlagsa);
      return v45;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cf80  mov     r11, rsp
0x18000cf83  push    r12
0x18000cf85  push    r13
0x18000cf87  sub     rsp, 278h
0x18000cf8e  mov     rax, cs:__security_cookie
0x18000cf95  xor     rax, rsp
0x18000cf98  mov     [rsp+288h+var_48], rax
0x18000cfa0  mov     rax, 0C000000000000000h
0x18000cfaa  mov     r12, r9
0x18000cfad  mov     r8, rdx
0x18000cfb0  mov     r13, rcx
0x18000cfb3  test    rax, r9
0x18000cfb6  jnz     loc_18000D2CB
0x18000cfbc  mov     [r11+10h], rbx
0x18000cfc0  lea     rax, [rsp+288h+Name]
0x18000cfc5  mov     [r11-28h], rdi
0x18000cfc9  mov     ebx, 104h
0x18000cfce  mov     edi, 7FFFFFFEh
0x18000cfd3  mov     [r11-30h], r14
0x18000cfd7  mov     ecx, edi
0x18000cfd9  mov     [r11-38h], r15
0x18000cfdd  mov     edx, ebx
0x18000cfdf  nop
0x18000cfe0  test    rcx, rcx
0x18000cfe3  jz      short loc_18000D004
0x18000cfe5  movzx   r9d, word ptr [r8]
0x18000cfe9  test    r9w, r9w
0x18000cfed  jz      short loc_18000D004
0x18000cfef  mov     [rax], r9w
0x18000cff3  add     r8, 2
0x18000cff7  add     rax, 2
0x18000cffb  dec     rcx
0x18000cffe  sub     rdx, 1
0x18000d002  jnz     short loc_18000CFE0
0x18000d004  lea     rcx, [rax-2]
0x18000d008  test    rdx, rdx
0x18000d00b  cmovnz  rcx, rax
0x18000d00f  xor     eax, eax
0x18000d011  mov     [rcx], ax
0x18000d014  mov     rcx, rbx
0x18000d017  lea     rax, [rsp+288h+Name]
0x18000d01c  nop     dword ptr [rax+00h]
0x18000d020  cmp     word ptr [rax], 0
0x18000d024  jz      short loc_18000D030
0x18000d026  add     rax, 2
0x18000d02a  sub     rcx, 1
0x18000d02e  jnz     short loc_18000D020
0x18000d030  xor     eax, eax
0x18000d032  mov     rdx, rbx
0x18000d035  sub     rdx, rcx
0x18000d038  test    rcx, rcx
0x18000d03b  cmovz   rdx, rax
0x18000d03f  jz      short loc_18000D08C
0x18000d041  mov     rax, rbx
0x18000d044  lea     r8, aP0; "_p0"
0x18000d04b  sub     rax, rdx
0x18000d04e  mov     rcx, rdi
0x18000d051  lea     rdx, [rsp+rdx*2+288h+Name]
0x18000d056  jz      short loc_18000D07C
0x18000d058  test    rcx, rcx
0x18000d05b  jz      short loc_18000D07C
0x18000d05d  movzx   r9d, word ptr [r8]
0x18000d061  test    r9w, r9w
0x18000d065  jz      short loc_18000D07C
0x18000d067  mov     [rdx], r9w
0x18000d06b  add     r8, 2
0x18000d06f  add     rdx, 2
0x18000d073  dec     rcx
0x18000d076  sub     rax, 1
0x18000d07a  jnz     short loc_18000D058
0x18000d07c  test    rax, rax
0x18000d07f  lea     rcx, [rdx-2]
0x18000d083  cmovnz  rcx, rdx
0x18000d087  xor     eax, eax
0x18000d089  mov     [rcx], ax
0x18000d08c  mov     edx, r12d
0x18000d08f  mov     [rsp+288h+var_18], rbp
0x18000d097  and     edx, 7FFFFFFFh; lInitialCount
0x18000d09d  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000d0a5  mov     r15d, 1
0x18000d0ab  mov     [rsp+288h+var_20], rsi
0x18000d0b3  mov     r8d, r15d
0x18000d0b6  mov     [rsp+288h+dwFlags], 0; int
0x18000d0be  cmova   r8d, edx; lMaximumCount
0x18000d0c2  lea     r9, [rsp+288h+Name]; lpName
0x18000d0c7  xor     ecx, ecx; lpSemaphoreAttributes
0x18000d0c9  call    cs:__imp_CreateSemaphoreExW
0x18000d0d0  nop     dword ptr [rax+rax+00h]
0x18000d0d5  mov     r14, rax
0x18000d0d8  test    rax, rax
0x18000d0db  jnz     short loc_18000D104
0x18000d0dd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d0e2  mov     esi, eax
0x18000d0e4  test    eax, eax
0x18000d0e6  jns     short loc_18000D150
0x18000d0e8  mov     rcx, [rsp+288h]; this
0x18000d0f0  mov     r9d, eax; char *
0x18000d0f3  mov     edx, 8Bh; void *
0x18000d0f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0fd  mov     eax, esi
0x18000d0ff  jmp     loc_18000D26B
0x18000d104  call    cs:__imp_GetLastError
0x18000d10b  nop     dword ptr [rax+rax+00h]
0x18000d110  mov     rsi, [r13+0]
0x18000d114  test    rsi, rsi
0x18000d117  jz      short loc_18000D14C
0x18000d119  call    cs:__imp_GetLastError
0x18000d120  nop     dword ptr [rax+rax+00h]
0x18000d125  mov     rcx, rsi; hObject
0x18000d128  mov     ebp, eax
0x18000d12a  call    cs:__imp_CloseHandle
0x18000d131  nop     dword ptr [rax+rax+00h]
0x18000d136  test    eax, eax
0x18000d138  jz      loc_18000D2D1
0x18000d13e  mov     ecx, ebp; dwErrCode
0x18000d140  call    cs:__imp_SetLastError
0x18000d147  nop     dword ptr [rax+rax+00h]
0x18000d14c  mov     [r13+0], r14
0x18000d150  shr     r12, 1Fh
0x18000d154  lea     rax, [rsp+288h+Name]
0x18000d159  mov     rcx, rbx
0x18000d15c  nop     dword ptr [rax+00h]
0x18000d160  cmp     word ptr [rax], 0
0x18000d164  jz      short loc_18000D16F
0x18000d166  add     rax, 2
0x18000d16a  sub     rcx, r15
0x18000d16d  jnz     short loc_18000D160
0x18000d16f  xor     eax, eax
0x18000d171  mov     rdx, rbx
0x18000d174  sub     rdx, rcx
0x18000d177  test    rcx, rcx
0x18000d17a  cmovz   rdx, rax
0x18000d17e  jz      short loc_18000D1C5
0x18000d180  lea     rax, [rsp+288h+Name]
0x18000d185  lea     rax, [rax+rdx*2]
0x18000d189  lea     rcx, asc_18008D2B8; "h"
0x18000d190  sub     rbx, rdx
0x18000d193  jz      short loc_18000D1B5
0x18000d195  test    rdi, rdi
0x18000d198  jz      short loc_18000D1B5
0x18000d19a  movzx   edx, word ptr [rcx]
0x18000d19d  test    dx, dx
0x18000d1a0  jz      short loc_18000D1B5
0x18000d1a2  mov     [rax], dx
0x18000d1a5  add     rcx, 2
0x18000d1a9  add     rax, 2
0x18000d1ad  dec     rdi
0x18000d1b0  sub     rbx, r15
0x18000d1b3  jnz     short loc_18000D195
0x18000d1b5  test    rbx, rbx
0x18000d1b8  lea     rcx, [rax-2]
0x18000d1bc  cmovnz  rcx, rax
0x18000d1c0  xor     eax, eax
0x18000d1c2  mov     [rcx], ax
0x18000d1c5  test    r12d, r12d
0x18000d1c8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000d1d0  lea     r9, [rsp+288h+Name]; lpName
0x18000d1d5  mov     [rsp+288h+dwFlags], 0; int
0x18000d1dd  cmovnz  r15d, r12d
0x18000d1e1  mov     edx, r12d; lInitialCount
0x18000d1e4  mov     r8d, r15d; lMaximumCount
0x18000d1e7  xor     ecx, ecx; lpSemaphoreAttributes
0x18000d1e9  call    cs:__imp_CreateSemaphoreExW
0x18000d1f0  nop     dword ptr [rax+rax+00h]
0x18000d1f5  mov     rdi, rax
0x18000d1f8  test    rax, rax
0x18000d1fb  jnz     short loc_18000D221
0x18000d1fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d202  mov     ebx, eax
0x18000d204  test    eax, eax
0x18000d206  jns     short loc_18000D269
0x18000d208  mov     rcx, [rsp+288h]; this
0x18000d210  mov     r9d, eax; char *
0x18000d213  mov     edx, 90h; void *
0x18000d218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d21d  mov     eax, ebx
0x18000d21f  jmp     short loc_18000D26B
0x18000d221  call    cs:__imp_GetLastError
0x18000d228  nop     dword ptr [rax+rax+00h]
0x18000d22d  mov     rbx, [r13+8]
0x18000d231  test    rbx, rbx
0x18000d234  jz      short loc_18000D265
0x18000d236  call    cs:__imp_GetLastError
0x18000d23d  nop     dword ptr [rax+rax+00h]
0x18000d242  mov     rcx, rbx; hObject
0x18000d245  mov     esi, eax
0x18000d247  call    cs:__imp_CloseHandle
0x18000d24e  nop     dword ptr [rax+rax+00h]
0x18000d253  test    eax, eax
0x18000d255  jz      short loc_18000D2B8
0x18000d257  mov     ecx, esi; dwErrCode
0x18000d259  call    cs:__imp_SetLastError
0x18000d260  nop     dword ptr [rax+rax+00h]
0x18000d265  mov     [r13+8], rdi
0x18000d269  xor     eax, eax
0x18000d26b  mov     rsi, [rsp+288h+var_20]
0x18000d273  mov     rbp, [rsp+288h+var_18]
0x18000d27b  mov     rdi, [rsp+288h+var_28]
0x18000d283  mov     r14, [rsp+288h+var_30]
0x18000d28b  mov     rbx, [rsp+288h+arg_8]
0x18000d293  mov     r15, [rsp+288h+var_38]
0x18000d29b  mov     rcx, [rsp+288h+var_48]
0x18000d2a3  xor     rcx, rsp; StackCookie
0x18000d2a6  call    __security_check_cookie
0x18000d2ab  add     rsp, 278h
0x18000d2b2  pop     r13
0x18000d2b4  pop     r12
0x18000d2b6  retn
0x18000d2b8  mov     rcx, [rsp+288h]; this
0x18000d2c0  mov     edx, 0A0Bh; void *
0x18000d2c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d2cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d2d1  mov     rcx, [rsp+288h]; this
0x18000d2d9  mov     edx, 0A0Bh; void *
0x18000d2de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

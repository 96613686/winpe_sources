# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006f7c`
- end: `0x1800071f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004528`

## callees

- `0x180001770`
- `0x1800056a4`
- `0x180006494`
- `0x1800064b4`
- `0x180006df4`
- `0x180006f7c`
- `0x18000734c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007010`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000708c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007010`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000708c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000714b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000714b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000705d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000711a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000713c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000705d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000711a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000713c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180006f7c  push    rbp
0x180006f7e  push    rbx
0x180006f7f  push    rsi
0x180006f80  push    rdi
0x180006f81  push    r14
0x180006f83  push    r15
0x180006f85  lea     rbp, [rsp-158h]
0x180006f8d  sub     rsp, 258h
0x180006f94  mov     rax, cs:__security_cookie
0x180006f9b  xor     rax, rsp
0x180006f9e  mov     [rbp+180h+var_40], rax
0x180006fa5  xor     r15d, r15d
0x180006fa8  lea     rax, [rsp+280h+Name]
0x180006fad  mov     [r8], r15
0x180006fb0  mov     r14, r8
0x180006fb3  mov     edx, 104h
0x180006fb8  mov     r9d, 7FFFFFFEh
0x180006fbe  test    r9, r9
0x180006fc1  jz      short loc_180006FE2
0x180006fc3  movzx   r8d, word ptr [rcx]
0x180006fc7  test    r8w, r8w
0x180006fcb  jz      short loc_180006FE2
0x180006fcd  mov     [rax], r8w
0x180006fd1  add     rcx, 2
0x180006fd5  add     rax, 2
0x180006fd9  dec     r9
0x180006fdc  sub     rdx, 1; unsigned __int64
0x180006fe0  jnz     short loc_180006FBE
0x180006fe2  test    rdx, rdx
0x180006fe5  lea     rcx, [rax-2]
0x180006fe9  lea     r8, aP0; "_p0"
0x180006ff0  cmovnz  rcx, rax
0x180006ff4  mov     [rcx], r15w
0x180006ff8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006ffd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007002  mov     esi, 1F0003h
0x180007007  lea     r8, [rsp+280h+Name]; lpName
0x18000700c  mov     ecx, esi; dwDesiredAccess
0x18000700e  xor     edx, edx; bInheritHandle
0x180007010  call    cs:__imp_OpenSemaphoreW
0x180007016  mov     rbx, rax
0x180007019  test    rax, rax
0x18000701c  jz      loc_18000714B
0x180007022  lea     rdx, [rsp+280h+var_25C]; int *
0x180007027  mov     [rsp+280h+var_25C], r15d
0x18000702c  mov     rcx, rax; hHandle
0x18000702f  mov     [rsp+280h+var_260], r15d; int
0x180007034  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007039  mov     edi, eax
0x18000703b  test    eax, eax
0x18000703d  jns     short loc_180007072
0x18000703f  mov     rcx, [rbp+188h]; this
0x180007046  lea     r8, aWil; "wil"
0x18000704d  mov     r9d, eax; char *
0x180007050  mov     edx, 0D6h; void *
0x180007055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000705a  mov     rcx, rbx; hObject
0x18000705d  call    cs:__imp_CloseHandle
0x180007063  test    eax, eax
0x180007065  jz      loc_1800071C0
0x18000706b  mov     eax, edi
0x18000706d  jmp     loc_18000716B
0x180007072  lea     r8, asc_180019CD8; "h"
0x180007079  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000707e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007083  lea     r8, [rsp+280h+Name]; lpName
0x180007088  xor     edx, edx; bInheritHandle
0x18000708a  mov     ecx, esi; dwDesiredAccess
0x18000708c  call    cs:__imp_OpenSemaphoreW
0x180007092  mov     rdi, rax
0x180007095  test    rax, rax
0x180007098  jz      loc_180007126
0x18000709e  lea     rdx, [rsp+280h+var_260]; int *
0x1800070a3  mov     rcx, rax; hHandle
0x1800070a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800070ab  mov     esi, eax
0x1800070ad  test    eax, eax
0x1800070af  jns     short loc_1800070F2
0x1800070b1  mov     rcx, [rbp+188h]; this
0x1800070b8  lea     r8, aWil; "wil"
0x1800070bf  mov     r9d, eax; char *
0x1800070c2  mov     edx, 0DEh; void *
0x1800070c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070cc  mov     rcx, rdi; hObject
0x1800070cf  call    cs:__imp_CloseHandle
0x1800070d5  test    eax, eax
0x1800070d7  jz      loc_1800071D2
0x1800070dd  mov     rcx, rbx; hObject
0x1800070e0  call    cs:__imp_CloseHandle
0x1800070e6  test    eax, eax
0x1800070e8  jz      loc_1800071E4
0x1800070ee  mov     eax, esi
0x1800070f0  jmp     short loc_18000716B
0x1800070f2  mov     rcx, rdi; hObject
0x1800070f5  call    cs:__imp_CloseHandle
0x1800070fb  test    eax, eax
0x1800070fd  jz      loc_18000718A
0x180007103  movsxd  rax, [rsp+280h+var_25C]
0x180007108  movsxd  rcx, [rsp+280h+var_260]
0x18000710d  shl     rcx, 1Fh
0x180007111  or      rcx, rax
0x180007114  mov     [r14], rcx
0x180007117  mov     rcx, rbx; hObject
0x18000711a  call    cs:__imp_CloseHandle
0x180007120  test    eax, eax
0x180007122  jz      short loc_18000719C
0x180007124  jmp     short loc_180007156
0x180007126  mov     rcx, [rbp+188h]; this
0x18000712d  mov     edx, 0DCh; void *
0x180007132  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007137  mov     rcx, rbx; hObject
0x18000713a  mov     edi, eax
0x18000713c  call    cs:__imp_CloseHandle
0x180007142  test    eax, eax
0x180007144  jz      short loc_1800071AE
0x180007146  jmp     loc_18000706B
0x18000714b  call    cs:__imp_GetLastError
0x180007151  cmp     eax, 2
0x180007154  jnz     short loc_18000715A
0x180007156  xor     eax, eax
0x180007158  jmp     short loc_18000716B
0x18000715a  mov     rcx, [rbp+188h]; this
0x180007161  mov     edx, 0D0h; void *
0x180007166  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000716b  mov     rcx, [rbp+180h+var_40]
0x180007172  xor     rcx, rsp; StackCookie
0x180007175  call    __security_check_cookie
0x18000717a  add     rsp, 258h
0x180007181  pop     r15
0x180007183  pop     r14
0x180007185  pop     rdi
0x180007186  pop     rsi
0x180007187  pop     rbx
0x180007188  pop     rbp
0x180007189  retn
0x18000718a  mov     rcx, [rbp+188h]; this
0x180007191  mov     edx, 0A0Bh; void *
0x180007196  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000719c  mov     rcx, [rbp+188h]; this
0x1800071a3  mov     edx, 0A0Bh; void *
0x1800071a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071ae  mov     rcx, [rbp+188h]; this
0x1800071b5  mov     edx, 0A0Bh; void *
0x1800071ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071c0  mov     rcx, [rbp+188h]; this
0x1800071c7  mov     edx, 0A0Bh; void *
0x1800071cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071d2  mov     rcx, [rbp+188h]; this
0x1800071d9  mov     edx, 0A0Bh; void *
0x1800071de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071e4  mov     rcx, [rbp+188h]; this
0x1800071eb  mov     edx, 0A0Bh; void *
0x1800071f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

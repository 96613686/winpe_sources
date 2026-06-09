# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000919c`
- end: `0x180009408`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004428`
- `0x1800047cc`

## callees

- `0x180001f60`
- `0x180005e04`
- `0x180008254`
- `0x180008274`
- `0x180008cb8`
- `0x18000919c`
- `0x180009a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009230`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009230`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000932c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000934e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000932c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000934e`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000919c  push    rbp
0x18000919e  push    rbx
0x18000919f  push    rsi
0x1800091a0  push    rdi
0x1800091a1  push    r14
0x1800091a3  push    r15
0x1800091a5  lea     rbp, [rsp-158h]
0x1800091ad  sub     rsp, 258h
0x1800091b4  mov     rax, cs:__security_cookie
0x1800091bb  xor     rax, rsp
0x1800091be  mov     [rbp+180h+var_40], rax
0x1800091c5  xor     r15d, r15d
0x1800091c8  lea     rax, [rsp+280h+Name]
0x1800091cd  mov     [r8], r15
0x1800091d0  mov     r14, r8
0x1800091d3  mov     edx, 104h
0x1800091d8  mov     r9d, 7FFFFFFEh
0x1800091de  test    r9, r9
0x1800091e1  jz      short loc_180009202
0x1800091e3  movzx   r8d, word ptr [rcx]
0x1800091e7  test    r8w, r8w
0x1800091eb  jz      short loc_180009202
0x1800091ed  mov     [rax], r8w
0x1800091f1  add     rcx, 2
0x1800091f5  add     rax, 2
0x1800091f9  dec     r9
0x1800091fc  sub     rdx, 1; unsigned __int64
0x180009200  jnz     short loc_1800091DE
0x180009202  test    rdx, rdx
0x180009205  lea     rcx, [rax-2]
0x180009209  lea     r8, aP0; "_p0"
0x180009210  cmovnz  rcx, rax
0x180009214  mov     [rcx], r15w
0x180009218  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000921d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009222  mov     esi, 1F0003h
0x180009227  lea     r8, [rsp+280h+Name]; lpName
0x18000922c  mov     ecx, esi; dwDesiredAccess
0x18000922e  xor     edx, edx; bInheritHandle
0x180009230  call    cs:__imp_OpenSemaphoreW
0x180009236  mov     rbx, rax
0x180009239  test    rax, rax
0x18000923c  jz      loc_18000935D
0x180009242  lea     rdx, [rsp+280h+var_25C]; int *
0x180009247  mov     [rsp+280h+var_25C], r15d
0x18000924c  mov     rcx, rax; hHandle
0x18000924f  mov     [rsp+280h+var_260], r15d; int
0x180009254  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009259  mov     edi, eax
0x18000925b  test    eax, eax
0x18000925d  jns     short loc_18000928B
0x18000925f  mov     rcx, [rbp+188h]; this
0x180009266  mov     r9d, eax; char *
0x180009269  mov     edx, 0D6h; void *
0x18000926e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009273  mov     rcx, rbx; hObject
0x180009276  call    cs:__imp_CloseHandle
0x18000927c  test    eax, eax
0x18000927e  jz      loc_1800093D2
0x180009284  mov     eax, edi
0x180009286  jmp     loc_18000937D
0x18000928b  lea     r8, asc_180018F18; "h"
0x180009292  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009297  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000929c  lea     r8, [rsp+280h+Name]; lpName
0x1800092a1  xor     edx, edx; bInheritHandle
0x1800092a3  mov     ecx, esi; dwDesiredAccess
0x1800092a5  call    cs:__imp_OpenSemaphoreW
0x1800092ab  mov     rdi, rax
0x1800092ae  test    rax, rax
0x1800092b1  jz      loc_180009338
0x1800092b7  lea     rdx, [rsp+280h+var_260]; int *
0x1800092bc  mov     rcx, rax; hHandle
0x1800092bf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800092c4  mov     esi, eax
0x1800092c6  test    eax, eax
0x1800092c8  jns     short loc_180009304
0x1800092ca  mov     rcx, [rbp+188h]; this
0x1800092d1  mov     r9d, eax; char *
0x1800092d4  mov     edx, 0DEh; void *
0x1800092d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092de  mov     rcx, rdi; hObject
0x1800092e1  call    cs:__imp_CloseHandle
0x1800092e7  test    eax, eax
0x1800092e9  jz      loc_1800093E4
0x1800092ef  mov     rcx, rbx; hObject
0x1800092f2  call    cs:__imp_CloseHandle
0x1800092f8  test    eax, eax
0x1800092fa  jz      loc_1800093F6
0x180009300  mov     eax, esi
0x180009302  jmp     short loc_18000937D
0x180009304  mov     rcx, rdi; hObject
0x180009307  call    cs:__imp_CloseHandle
0x18000930d  test    eax, eax
0x18000930f  jz      loc_18000939C
0x180009315  movsxd  rax, [rsp+280h+var_25C]
0x18000931a  movsxd  rcx, [rsp+280h+var_260]
0x18000931f  shl     rcx, 1Fh
0x180009323  or      rcx, rax
0x180009326  mov     [r14], rcx
0x180009329  mov     rcx, rbx; hObject
0x18000932c  call    cs:__imp_CloseHandle
0x180009332  test    eax, eax
0x180009334  jz      short loc_1800093AE
0x180009336  jmp     short loc_180009368
0x180009338  mov     rcx, [rbp+188h]; this
0x18000933f  mov     edx, 0DCh; void *
0x180009344  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009349  mov     rcx, rbx; hObject
0x18000934c  mov     edi, eax
0x18000934e  call    cs:__imp_CloseHandle
0x180009354  test    eax, eax
0x180009356  jz      short loc_1800093C0
0x180009358  jmp     loc_180009284
0x18000935d  call    cs:__imp_GetLastError
0x180009363  cmp     eax, 2
0x180009366  jnz     short loc_18000936C
0x180009368  xor     eax, eax
0x18000936a  jmp     short loc_18000937D
0x18000936c  mov     rcx, [rbp+188h]; this
0x180009373  mov     edx, 0D0h; void *
0x180009378  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000937d  mov     rcx, [rbp+180h+var_40]
0x180009384  xor     rcx, rsp; StackCookie
0x180009387  call    __security_check_cookie
0x18000938c  add     rsp, 258h
0x180009393  pop     r15
0x180009395  pop     r14
0x180009397  pop     rdi
0x180009398  pop     rsi
0x180009399  pop     rbx
0x18000939a  pop     rbp
0x18000939b  retn
0x18000939c  mov     rcx, [rbp+188h]; this
0x1800093a3  mov     edx, 0A0Bh; void *
0x1800093a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093ae  mov     rcx, [rbp+188h]; this
0x1800093b5  mov     edx, 0A0Bh; void *
0x1800093ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093c0  mov     rcx, [rbp+188h]; this
0x1800093c7  mov     edx, 0A0Bh; void *
0x1800093cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093d2  mov     rcx, [rbp+188h]; this
0x1800093d9  mov     edx, 0A0Bh; void *
0x1800093de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093e4  mov     rcx, [rbp+188h]; this
0x1800093eb  mov     edx, 0A0Bh; void *
0x1800093f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093f6  mov     rcx, [rbp+188h]; this
0x1800093fd  mov     edx, 0A0Bh; void *
0x180009402  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

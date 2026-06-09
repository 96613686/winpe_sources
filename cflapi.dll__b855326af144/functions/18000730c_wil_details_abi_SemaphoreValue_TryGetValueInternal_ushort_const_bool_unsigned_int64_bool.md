# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000730c`
- end: `0x18000759b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b38`
- `0x1800095cc`

## callees

- `0x180002490`
- `0x180005c28`
- `0x1800067a4`
- `0x1800067c4`
- `0x180007104`
- `0x18000730c`
- `0x1800077a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000741c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000741c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000745f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000745f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074da`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000730c  push    rbp
0x18000730e  push    rbx
0x18000730f  push    rsi
0x180007310  push    rdi
0x180007311  push    r14
0x180007313  push    r15
0x180007315  lea     rbp, [rsp-158h]
0x18000731d  sub     rsp, 258h
0x180007324  mov     rax, cs:__security_cookie
0x18000732b  xor     rax, rsp
0x18000732e  mov     [rbp+180h+var_40], rax
0x180007335  xor     r15d, r15d
0x180007338  lea     rax, [rsp+280h+Name]
0x18000733d  mov     [r8], r15
0x180007340  mov     r14, r8
0x180007343  mov     edx, 104h
0x180007348  mov     r9d, 7FFFFFFEh
0x18000734e  test    r9, r9
0x180007351  jz      short loc_180007372
0x180007353  movzx   r8d, word ptr [rcx]
0x180007357  test    r8w, r8w
0x18000735b  jz      short loc_180007372
0x18000735d  mov     [rax], r8w
0x180007361  add     rcx, 2
0x180007365  add     rax, 2
0x180007369  dec     r9
0x18000736c  sub     rdx, 1; unsigned __int64
0x180007370  jnz     short loc_18000734E
0x180007372  test    rdx, rdx
0x180007375  lea     rcx, [rax-2]
0x180007379  lea     r8, aP0; "_p0"
0x180007380  cmovnz  rcx, rax
0x180007384  mov     [rcx], r15w
0x180007388  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000738d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007392  mov     esi, 1F0003h
0x180007397  lea     r8, [rsp+280h+Name]; lpName
0x18000739c  mov     ecx, esi; dwDesiredAccess
0x18000739e  xor     edx, edx; bInheritHandle
0x1800073a0  call    cs:__imp_OpenSemaphoreW
0x1800073a6  mov     rbx, rax
0x1800073a9  test    rax, rax
0x1800073ac  jz      loc_1800074E9
0x1800073b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800073b7  mov     [rsp+280h+var_25C], r15d
0x1800073bc  mov     rcx, rax; hHandle
0x1800073bf  mov     [rsp+280h+var_260], r15d; int
0x1800073c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800073c9  mov     edi, eax
0x1800073cb  test    eax, eax
0x1800073cd  jns     short loc_180007402
0x1800073cf  mov     rcx, [rbp+188h]; this
0x1800073d6  lea     r8, aWil; "wil"
0x1800073dd  mov     r9d, eax; char *
0x1800073e0  mov     edx, 0D6h; void *
0x1800073e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ea  mov     rcx, rbx; hObject
0x1800073ed  call    cs:__imp_CloseHandle
0x1800073f3  test    eax, eax
0x1800073f5  jz      loc_180007565
0x1800073fb  mov     eax, edi
0x1800073fd  jmp     loc_180007510
0x180007402  lea     r8, asc_180032450; "h"
0x180007409  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000740e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007413  lea     r8, [rsp+280h+Name]; lpName
0x180007418  xor     edx, edx; bInheritHandle
0x18000741a  mov     ecx, esi; dwDesiredAccess
0x18000741c  call    cs:__imp_OpenSemaphoreW
0x180007422  mov     rdi, rax
0x180007425  test    rax, rax
0x180007428  jz      loc_1800074BD
0x18000742e  lea     rdx, [rsp+280h+var_260]; int *
0x180007433  mov     rcx, rax; hHandle
0x180007436  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000743b  mov     esi, eax
0x18000743d  test    eax, eax
0x18000743f  jns     short loc_180007485
0x180007441  mov     rcx, [rbp+188h]; this
0x180007448  lea     r8, aWil; "wil"
0x18000744f  mov     r9d, eax; char *
0x180007452  mov     edx, 0DEh; void *
0x180007457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000745c  mov     rcx, rdi; hObject
0x18000745f  call    cs:__imp_CloseHandle
0x180007465  test    eax, eax
0x180007467  jz      loc_180007577
0x18000746d  mov     rcx, rbx; hObject
0x180007470  call    cs:__imp_CloseHandle
0x180007476  test    eax, eax
0x180007478  jz      loc_180007589
0x18000747e  mov     eax, esi
0x180007480  jmp     loc_180007510
0x180007485  mov     rcx, rdi; hObject
0x180007488  call    cs:__imp_CloseHandle
0x18000748e  test    eax, eax
0x180007490  jz      loc_18000752F
0x180007496  movsxd  rax, [rsp+280h+var_25C]
0x18000749b  movsxd  rcx, [rsp+280h+var_260]
0x1800074a0  shl     rcx, 1Fh
0x1800074a4  or      rcx, rax
0x1800074a7  mov     [r14], rcx
0x1800074aa  mov     rcx, rbx; hObject
0x1800074ad  call    cs:__imp_CloseHandle
0x1800074b3  test    eax, eax
0x1800074b5  jz      loc_180007541
0x1800074bb  jmp     short loc_1800074F4
0x1800074bd  mov     rcx, [rbp+188h]; this
0x1800074c4  lea     r8, aWil; "wil"
0x1800074cb  mov     edx, 0DCh; void *
0x1800074d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800074d5  mov     rcx, rbx; hObject
0x1800074d8  mov     edi, eax
0x1800074da  call    cs:__imp_CloseHandle
0x1800074e0  test    eax, eax
0x1800074e2  jz      short loc_180007553
0x1800074e4  jmp     loc_1800073FB
0x1800074e9  call    cs:__imp_GetLastError
0x1800074ef  cmp     eax, 2
0x1800074f2  jnz     short loc_1800074F8
0x1800074f4  xor     eax, eax
0x1800074f6  jmp     short loc_180007510
0x1800074f8  mov     rcx, [rbp+188h]; this
0x1800074ff  lea     r8, aWil; "wil"
0x180007506  mov     edx, 0D0h; void *
0x18000750b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007510  mov     rcx, [rbp+180h+var_40]
0x180007517  xor     rcx, rsp; StackCookie
0x18000751a  call    __security_check_cookie
0x18000751f  add     rsp, 258h
0x180007526  pop     r15
0x180007528  pop     r14
0x18000752a  pop     rdi
0x18000752b  pop     rsi
0x18000752c  pop     rbx
0x18000752d  pop     rbp
0x18000752e  retn
0x18000752f  mov     rcx, [rbp+188h]; this
0x180007536  mov     edx, 0A0Bh; void *
0x18000753b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007541  mov     rcx, [rbp+188h]; this
0x180007548  mov     edx, 0A0Bh; void *
0x18000754d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007553  mov     rcx, [rbp+188h]; this
0x18000755a  mov     edx, 0A0Bh; void *
0x18000755f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007565  mov     rcx, [rbp+188h]; this
0x18000756c  mov     edx, 0A0Bh; void *
0x180007571  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007577  mov     rcx, [rbp+188h]; this
0x18000757e  mov     edx, 0A0Bh; void *
0x180007583  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007589  mov     rcx, [rbp+188h]; this
0x180007590  mov     edx, 0A0Bh; void *
0x180007595  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400053bc`
- end: `0x140005652`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `662`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002e78`

## callees

- `0x140001460`
- `0x140003dd4`
- `0x1400048f4`
- `0x140004914`
- `0x140005254`
- `0x1400053bc`
- `0x1400057ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000557d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000557d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000554c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000556e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000554c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000556e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005450`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400054c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005450`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400054c5`

## string_xrefs

- `0x1400055c3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400055dc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400055f5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000560e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140005627`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140005640`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h] BYREF
  int v32[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v29, v30);
    return 0;
  }
  v32[0] = 0;
  v31 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v32);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v28);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v31);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    *a3 = v32[0] | (unsigned __int64)((__int64)v31 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v27);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v31);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  return v23;
}

```

## disassembly

```asm
0x1400053bc  push    rbp
0x1400053be  push    rbx
0x1400053bf  push    rsi
0x1400053c0  push    rdi
0x1400053c1  push    r14
0x1400053c3  push    r15
0x1400053c5  lea     rbp, [rsp-158h]
0x1400053cd  sub     rsp, 258h
0x1400053d4  mov     rax, cs:__security_cookie
0x1400053db  xor     rax, rsp
0x1400053de  mov     [rbp+180h+var_40], rax
0x1400053e5  xor     r15d, r15d
0x1400053e8  lea     rax, [rsp+280h+Name]
0x1400053ed  mov     [r8], r15
0x1400053f0  mov     r14, r8
0x1400053f3  mov     edx, 104h
0x1400053f8  mov     r9d, 7FFFFFFEh
0x1400053fe  test    r9, r9
0x140005401  jz      short loc_140005422
0x140005403  movzx   r8d, word ptr [rcx]
0x140005407  test    r8w, r8w
0x14000540b  jz      short loc_140005422
0x14000540d  mov     [rax], r8w
0x140005411  add     rcx, 2
0x140005415  add     rax, 2
0x140005419  dec     r9
0x14000541c  sub     rdx, 1; unsigned __int64
0x140005420  jnz     short loc_1400053FE
0x140005422  test    rdx, rdx
0x140005425  lea     rcx, [rax-2]
0x140005429  lea     r8, aP0; "_p0"
0x140005430  cmovnz  rcx, rax
0x140005434  mov     [rcx], r15w
0x140005438  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000543d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005442  mov     esi, 1F0003h
0x140005447  lea     r8, [rsp+280h+Name]; lpName
0x14000544c  mov     ecx, esi; dwDesiredAccess
0x14000544e  xor     edx, edx; bInheritHandle
0x140005450  call    cs:__imp_OpenSemaphoreW
0x140005456  mov     rbx, rax
0x140005459  test    rax, rax
0x14000545c  jz      loc_14000557D
0x140005462  lea     rdx, [rsp+280h+var_25C]; int *
0x140005467  mov     [rsp+280h+var_25C], r15d
0x14000546c  mov     rcx, rax; hHandle
0x14000546f  mov     [rsp+280h+var_260], r15d; int
0x140005474  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005479  mov     edi, eax
0x14000547b  test    eax, eax
0x14000547d  jns     short loc_1400054AB
0x14000547f  mov     rcx, [rbp+188h]; this
0x140005486  mov     r9d, eax; char *
0x140005489  mov     edx, 0D6h; void *
0x14000548e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005493  mov     rcx, rbx; hObject
0x140005496  call    cs:__imp_CloseHandle
0x14000549c  test    eax, eax
0x14000549e  jz      loc_140005607
0x1400054a4  mov     eax, edi
0x1400054a6  jmp     loc_14000559D
0x1400054ab  lea     r8, asc_1400077F8; "h"
0x1400054b2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400054b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400054bc  lea     r8, [rsp+280h+Name]; lpName
0x1400054c1  xor     edx, edx; bInheritHandle
0x1400054c3  mov     ecx, esi; dwDesiredAccess
0x1400054c5  call    cs:__imp_OpenSemaphoreW
0x1400054cb  mov     rdi, rax
0x1400054ce  test    rax, rax
0x1400054d1  jz      loc_140005558
0x1400054d7  lea     rdx, [rsp+280h+var_260]; int *
0x1400054dc  mov     rcx, rax; hHandle
0x1400054df  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400054e4  mov     esi, eax
0x1400054e6  test    eax, eax
0x1400054e8  jns     short loc_140005524
0x1400054ea  mov     rcx, [rbp+188h]; this
0x1400054f1  mov     r9d, eax; char *
0x1400054f4  mov     edx, 0DEh; void *
0x1400054f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400054fe  mov     rcx, rdi; hObject
0x140005501  call    cs:__imp_CloseHandle
0x140005507  test    eax, eax
0x140005509  jz      loc_140005620
0x14000550f  mov     rcx, rbx; hObject
0x140005512  call    cs:__imp_CloseHandle
0x140005518  test    eax, eax
0x14000551a  jz      loc_140005639
0x140005520  mov     eax, esi
0x140005522  jmp     short loc_14000559D
0x140005524  mov     rcx, rdi; hObject
0x140005527  call    cs:__imp_CloseHandle
0x14000552d  test    eax, eax
0x14000552f  jz      loc_1400055BC
0x140005535  movsxd  rax, [rsp+280h+var_25C]
0x14000553a  movsxd  rcx, [rsp+280h+var_260]
0x14000553f  shl     rcx, 1Fh
0x140005543  or      rcx, rax
0x140005546  mov     [r14], rcx
0x140005549  mov     rcx, rbx; hObject
0x14000554c  call    cs:__imp_CloseHandle
0x140005552  test    eax, eax
0x140005554  jz      short loc_1400055D5
0x140005556  jmp     short loc_140005588
0x140005558  mov     rcx, [rbp+188h]; this
0x14000555f  mov     edx, 0DCh; void *
0x140005564  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005569  mov     rcx, rbx; hObject
0x14000556c  mov     edi, eax
0x14000556e  call    cs:__imp_CloseHandle
0x140005574  test    eax, eax
0x140005576  jz      short loc_1400055EE
0x140005578  jmp     loc_1400054A4
0x14000557d  call    cs:__imp_GetLastError
0x140005583  cmp     eax, 2
0x140005586  jnz     short loc_14000558C
0x140005588  xor     eax, eax
0x14000558a  jmp     short loc_14000559D
0x14000558c  mov     rcx, [rbp+188h]; this
0x140005593  mov     edx, 0D0h; void *
0x140005598  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000559d  mov     rcx, [rbp+180h+var_40]
0x1400055a4  xor     rcx, rsp; StackCookie
0x1400055a7  call    __security_check_cookie
0x1400055ac  add     rsp, 258h
0x1400055b3  pop     r15
0x1400055b5  pop     r14
0x1400055b7  pop     rdi
0x1400055b8  pop     rsi
0x1400055b9  pop     rbx
0x1400055ba  pop     rbp
0x1400055bb  retn
0x1400055bc  mov     rcx, [rbp+188h]; this
0x1400055c3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400055ca  mov     edx, 0A0Bh; void *
0x1400055cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400055d5  mov     rcx, [rbp+188h]; this
0x1400055dc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400055e3  mov     edx, 0A0Bh; void *
0x1400055e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400055ee  mov     rcx, [rbp+188h]; this
0x1400055f5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400055fc  mov     edx, 0A0Bh; void *
0x140005601  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005607  mov     rcx, [rbp+188h]; this
0x14000560e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005615  mov     edx, 0A0Bh; void *
0x14000561a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005620  mov     rcx, [rbp+188h]; this
0x140005627  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000562e  mov     edx, 0A0Bh; void *
0x140005633  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005639  mov     rcx, [rbp+188h]; this
0x140005640  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005647  mov     edx, 0A0Bh; void *
0x14000564c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

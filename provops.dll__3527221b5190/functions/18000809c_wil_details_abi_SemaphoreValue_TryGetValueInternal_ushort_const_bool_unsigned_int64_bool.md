# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000809c`
- end: `0x180008355`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005480`
- `0x18000f4c8`

## callees

- `0x1800066f8`
- `0x180007654`
- `0x180007674`
- `0x180007df4`
- `0x18000809c`
- `0x18000864c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008130`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800081ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008130`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800081ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000817d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000823d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000826a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000817d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000823d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000826a`

## string_xrefs

- `0x1800082c6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800082df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800082f8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008311`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000832a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008343`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v26);
    return 0;
  }
  v28[0] = 0;
  v27 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v28);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v27);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    *a3 = v28[0] | (unsigned __int64)((__int64)v27 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x18000809c  push    rbp
0x18000809e  push    rbx
0x18000809f  push    rsi
0x1800080a0  push    rdi
0x1800080a1  push    r14
0x1800080a3  push    r15
0x1800080a5  lea     rbp, [rsp-158h]
0x1800080ad  sub     rsp, 258h
0x1800080b4  mov     rax, cs:__security_cookie
0x1800080bb  xor     rax, rsp
0x1800080be  mov     [rbp+180h+var_40], rax
0x1800080c5  xor     r15d, r15d
0x1800080c8  lea     rax, [rsp+280h+Name]
0x1800080cd  mov     [r8], r15
0x1800080d0  mov     r14, r8
0x1800080d3  mov     edx, 104h
0x1800080d8  mov     r9d, 7FFFFFFEh
0x1800080de  test    r9, r9
0x1800080e1  jz      short loc_180008102
0x1800080e3  movzx   r8d, word ptr [rcx]
0x1800080e7  test    r8w, r8w
0x1800080eb  jz      short loc_180008102
0x1800080ed  mov     [rax], r8w
0x1800080f1  add     rcx, 2
0x1800080f5  add     rax, 2
0x1800080f9  dec     r9
0x1800080fc  sub     rdx, 1; unsigned __int64
0x180008100  jnz     short loc_1800080DE
0x180008102  test    rdx, rdx
0x180008105  lea     rcx, [rax-2]
0x180008109  lea     r8, aP0; "_p0"
0x180008110  cmovnz  rcx, rax
0x180008114  mov     [rcx], r15w
0x180008118  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000811d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008122  mov     esi, 1F0003h
0x180008127  lea     r8, [rsp+280h+Name]; lpName
0x18000812c  mov     ecx, esi; dwDesiredAccess
0x18000812e  xor     edx, edx; bInheritHandle
0x180008130  call    cs:__imp_OpenSemaphoreW
0x180008136  mov     rbx, rax
0x180008139  test    rax, rax
0x18000813c  jz      loc_180008279
0x180008142  lea     rdx, [rsp+280h+var_25C]; int *
0x180008147  mov     [rsp+280h+var_25C], r15d
0x18000814c  mov     rcx, rax; hHandle
0x18000814f  mov     [rsp+280h+var_260], r15d; int
0x180008154  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008159  mov     edi, eax
0x18000815b  test    eax, eax
0x18000815d  jns     short loc_180008192
0x18000815f  mov     rcx, [rbp+188h]; this
0x180008166  lea     r8, aWil; "wil"
0x18000816d  mov     r9d, eax; char *
0x180008170  mov     edx, 0D6h; void *
0x180008175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000817a  mov     rcx, rbx; hObject
0x18000817d  call    cs:__imp_CloseHandle
0x180008183  test    eax, eax
0x180008185  jz      loc_18000830A
0x18000818b  mov     eax, edi
0x18000818d  jmp     loc_1800082A0
0x180008192  lea     r8, asc_18003A648; "h"
0x180008199  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000819e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800081a3  lea     r8, [rsp+280h+Name]; lpName
0x1800081a8  xor     edx, edx; bInheritHandle
0x1800081aa  mov     ecx, esi; dwDesiredAccess
0x1800081ac  call    cs:__imp_OpenSemaphoreW
0x1800081b2  mov     rdi, rax
0x1800081b5  test    rax, rax
0x1800081b8  jz      loc_18000824D
0x1800081be  lea     rdx, [rsp+280h+var_260]; int *
0x1800081c3  mov     rcx, rax; hHandle
0x1800081c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800081cb  mov     esi, eax
0x1800081cd  test    eax, eax
0x1800081cf  jns     short loc_180008215
0x1800081d1  mov     rcx, [rbp+188h]; this
0x1800081d8  lea     r8, aWil; "wil"
0x1800081df  mov     r9d, eax; char *
0x1800081e2  mov     edx, 0DEh; void *
0x1800081e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081ec  mov     rcx, rdi; hObject
0x1800081ef  call    cs:__imp_CloseHandle
0x1800081f5  test    eax, eax
0x1800081f7  jz      loc_180008323
0x1800081fd  mov     rcx, rbx; hObject
0x180008200  call    cs:__imp_CloseHandle
0x180008206  test    eax, eax
0x180008208  jz      loc_18000833C
0x18000820e  mov     eax, esi
0x180008210  jmp     loc_1800082A0
0x180008215  mov     rcx, rdi; hObject
0x180008218  call    cs:__imp_CloseHandle
0x18000821e  test    eax, eax
0x180008220  jz      loc_1800082BF
0x180008226  movsxd  rax, [rsp+280h+var_25C]
0x18000822b  movsxd  rcx, [rsp+280h+var_260]
0x180008230  shl     rcx, 1Fh
0x180008234  or      rcx, rax
0x180008237  mov     [r14], rcx
0x18000823a  mov     rcx, rbx; hObject
0x18000823d  call    cs:__imp_CloseHandle
0x180008243  test    eax, eax
0x180008245  jz      loc_1800082D8
0x18000824b  jmp     short loc_180008284
0x18000824d  mov     rcx, [rbp+188h]; this
0x180008254  lea     r8, aWil; "wil"
0x18000825b  mov     edx, 0DCh; void *
0x180008260  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008265  mov     rcx, rbx; hObject
0x180008268  mov     edi, eax
0x18000826a  call    cs:__imp_CloseHandle
0x180008270  test    eax, eax
0x180008272  jz      short loc_1800082F1
0x180008274  jmp     loc_18000818B
0x180008279  call    cs:__imp_GetLastError
0x18000827f  cmp     eax, 2
0x180008282  jnz     short loc_180008288
0x180008284  xor     eax, eax
0x180008286  jmp     short loc_1800082A0
0x180008288  mov     rcx, [rbp+188h]; this
0x18000828f  lea     r8, aWil; "wil"
0x180008296  mov     edx, 0D0h; void *
0x18000829b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800082a0  mov     rcx, [rbp+180h+var_40]
0x1800082a7  xor     rcx, rsp; StackCookie
0x1800082aa  call    __security_check_cookie
0x1800082af  add     rsp, 258h
0x1800082b6  pop     r15
0x1800082b8  pop     r14
0x1800082ba  pop     rdi
0x1800082bb  pop     rsi
0x1800082bc  pop     rbx
0x1800082bd  pop     rbp
0x1800082be  retn
0x1800082bf  mov     rcx, [rbp+188h]; this
0x1800082c6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800082cd  mov     edx, 0A0Bh; void *
0x1800082d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800082d8  mov     rcx, [rbp+188h]; this
0x1800082df  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800082e6  mov     edx, 0A0Bh; void *
0x1800082eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800082f1  mov     rcx, [rbp+188h]; this
0x1800082f8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800082ff  mov     edx, 0A0Bh; void *
0x180008304  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000830a  mov     rcx, [rbp+188h]; this
0x180008311  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008318  mov     edx, 0A0Bh; void *
0x18000831d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008323  mov     rcx, [rbp+188h]; this
0x18000832a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008331  mov     edx, 0A0Bh; void *
0x180008336  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000833c  mov     rcx, [rbp+188h]; this
0x180008343  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000834a  mov     edx, 0A0Bh; void *
0x18000834f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

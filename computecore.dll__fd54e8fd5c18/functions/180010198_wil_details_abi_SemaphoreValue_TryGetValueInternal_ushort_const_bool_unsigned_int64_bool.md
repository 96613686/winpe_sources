# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180010198`
- end: `0x18001045a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a918`
- `0x18000acf8`

## callees

- `0x1800067c0`
- `0x18000cd2c`
- `0x18000f194`
- `0x18000f1b4`
- `0x18000fc04`
- `0x180010198`
- `0x1800115c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001022f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001022f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001037e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001037e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001027c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001031d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001027c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001031d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036f`

## string_xrefs

- `0x1800103cb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800103e4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800103fd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010416`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001042f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010448`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  const char *v13; // r9
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x180010198  push    rbp
0x18001019a  push    rbx
0x18001019b  push    rsi
0x18001019c  push    rdi
0x18001019d  push    r14
0x18001019f  push    r15
0x1800101a1  lea     rbp, [rsp-158h]
0x1800101a9  sub     rsp, 258h
0x1800101b0  mov     rax, cs:__security_cookie
0x1800101b7  xor     rax, rsp
0x1800101ba  mov     [rbp+180h+var_40], rax
0x1800101c1  xor     r15d, r15d
0x1800101c4  lea     rax, [rsp+280h+Name]
0x1800101c9  mov     esi, 104h
0x1800101ce  mov     [r8], r15
0x1800101d1  mov     edx, esi
0x1800101d3  mov     r14, r8
0x1800101d6  mov     r9d, 7FFFFFFEh
0x1800101dc  test    r9, r9
0x1800101df  jz      short loc_180010200
0x1800101e1  movzx   r8d, word ptr [rcx]
0x1800101e5  test    r8w, r8w
0x1800101e9  jz      short loc_180010200
0x1800101eb  mov     [rax], r8w
0x1800101ef  add     rcx, 2
0x1800101f3  add     rax, 2
0x1800101f7  dec     r9
0x1800101fa  sub     rdx, 1
0x1800101fe  jnz     short loc_1800101DC
0x180010200  test    rdx, rdx
0x180010203  lea     rcx, [rax-2]
0x180010207  lea     r8, aP0; "_p0"
0x18001020e  mov     rdx, rsi; unsigned __int64
0x180010211  cmovnz  rcx, rax
0x180010215  mov     [rcx], r15w
0x180010219  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001021e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010223  lea     r8, [rsp+280h+Name]; lpName
0x180010228  xor     edx, edx; bInheritHandle
0x18001022a  mov     ecx, 1F0003h; dwDesiredAccess
0x18001022f  call    cs:__imp_OpenSemaphoreW
0x180010235  mov     rbx, rax
0x180010238  test    rax, rax
0x18001023b  jz      loc_18001037E
0x180010241  lea     rdx, [rsp+280h+var_25C]; int *
0x180010246  mov     [rsp+280h+var_25C], r15d
0x18001024b  mov     rcx, rax; hHandle
0x18001024e  mov     [rsp+280h+var_260], r15d; int
0x180010253  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010258  mov     edi, eax
0x18001025a  test    eax, eax
0x18001025c  jns     short loc_180010291
0x18001025e  mov     rcx, [rbp+188h]; this
0x180010265  lea     r8, aWil; "wil"
0x18001026c  mov     r9d, eax; char *
0x18001026f  mov     edx, 0D6h; void *
0x180010274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010279  mov     rcx, rbx; hObject
0x18001027c  call    cs:__imp_CloseHandle
0x180010282  test    eax, eax
0x180010284  jz      loc_18001040F
0x18001028a  mov     eax, edi
0x18001028c  jmp     loc_1800103A5
0x180010291  lea     r8, asc_1800ADA68; "h"
0x180010298  mov     rdx, rsi; unsigned __int64
0x18001029b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800102a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800102a5  lea     r8, [rsp+280h+Name]; lpName
0x1800102aa  xor     edx, edx; bInheritHandle
0x1800102ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800102b1  call    cs:__imp_OpenSemaphoreW
0x1800102b7  mov     rdi, rax
0x1800102ba  test    rax, rax
0x1800102bd  jz      loc_180010352
0x1800102c3  lea     rdx, [rsp+280h+var_260]; int *
0x1800102c8  mov     rcx, rax; hHandle
0x1800102cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800102d0  mov     esi, eax
0x1800102d2  test    eax, eax
0x1800102d4  jns     short loc_18001031A
0x1800102d6  mov     rcx, [rbp+188h]; this
0x1800102dd  lea     r8, aWil; "wil"
0x1800102e4  mov     r9d, eax; char *
0x1800102e7  mov     edx, 0DEh; void *
0x1800102ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102f1  mov     rcx, rdi; hObject
0x1800102f4  call    cs:__imp_CloseHandle
0x1800102fa  test    eax, eax
0x1800102fc  jz      loc_180010428
0x180010302  mov     rcx, rbx; hObject
0x180010305  call    cs:__imp_CloseHandle
0x18001030b  test    eax, eax
0x18001030d  jz      loc_180010441
0x180010313  mov     eax, esi
0x180010315  jmp     loc_1800103A5
0x18001031a  mov     rcx, rdi; hObject
0x18001031d  call    cs:__imp_CloseHandle
0x180010323  test    eax, eax
0x180010325  jz      loc_1800103C4
0x18001032b  movsxd  rax, [rsp+280h+var_25C]
0x180010330  movsxd  rcx, [rsp+280h+var_260]
0x180010335  shl     rcx, 1Fh
0x180010339  or      rcx, rax
0x18001033c  mov     [r14], rcx
0x18001033f  mov     rcx, rbx; hObject
0x180010342  call    cs:__imp_CloseHandle
0x180010348  test    eax, eax
0x18001034a  jz      loc_1800103DD
0x180010350  jmp     short loc_180010389
0x180010352  mov     rcx, [rbp+188h]; this
0x180010359  lea     r8, aWil; "wil"
0x180010360  mov     edx, 0DCh; void *
0x180010365  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001036a  mov     rcx, rbx; hObject
0x18001036d  mov     edi, eax
0x18001036f  call    cs:__imp_CloseHandle
0x180010375  test    eax, eax
0x180010377  jz      short loc_1800103F6
0x180010379  jmp     loc_18001028A
0x18001037e  call    cs:__imp_GetLastError
0x180010384  cmp     eax, 2
0x180010387  jnz     short loc_18001038D
0x180010389  xor     eax, eax
0x18001038b  jmp     short loc_1800103A5
0x18001038d  mov     rcx, [rbp+188h]; this
0x180010394  lea     r8, aWil; "wil"
0x18001039b  mov     edx, 0D0h; void *
0x1800103a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800103a5  mov     rcx, [rbp+180h+var_40]
0x1800103ac  xor     rcx, rsp; StackCookie
0x1800103af  call    __security_check_cookie
0x1800103b4  add     rsp, 258h
0x1800103bb  pop     r15
0x1800103bd  pop     r14
0x1800103bf  pop     rdi
0x1800103c0  pop     rsi
0x1800103c1  pop     rbx
0x1800103c2  pop     rbp
0x1800103c3  retn
0x1800103c4  mov     rcx, [rbp+188h]; this
0x1800103cb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800103d2  mov     edx, 0A0Bh; void *
0x1800103d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103dd  mov     rcx, [rbp+188h]; this
0x1800103e4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800103eb  mov     edx, 0A0Bh; void *
0x1800103f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103f6  mov     rcx, [rbp+188h]; this
0x1800103fd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010404  mov     edx, 0A0Bh; void *
0x180010409  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001040f  mov     rcx, [rbp+188h]; this
0x180010416  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001041d  mov     edx, 0A0Bh; void *
0x180010422  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010428  mov     rcx, [rbp+188h]; this
0x18001042f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010436  mov     edx, 0A0Bh; void *
0x18001043b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010441  mov     rcx, [rbp+188h]; this
0x180010448  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001044f  mov     edx, 0A0Bh; void *
0x180010454  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

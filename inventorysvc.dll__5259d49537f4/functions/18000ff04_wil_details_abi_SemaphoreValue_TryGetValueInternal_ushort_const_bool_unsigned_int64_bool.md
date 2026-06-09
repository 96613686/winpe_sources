# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ff04`
- end: `0x1800101bd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008318`
- `0x1800086f8`

## callees

- `0x180002bf0`
- `0x18000bfe4`
- `0x18000ec34`
- `0x18000ec54`
- `0x18000f698`
- `0x18000ff04`
- `0x1800108d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ff98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010014`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ff98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100d2`

## string_xrefs

- `0x18001012e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010147`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010160`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010179`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010192`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800101ab`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    *a3 = v28[0] | (unsigned __int64)((__int64)v27 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v27);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x18000ff04  push    rbp
0x18000ff06  push    rbx
0x18000ff07  push    rsi
0x18000ff08  push    rdi
0x18000ff09  push    r14
0x18000ff0b  push    r15
0x18000ff0d  lea     rbp, [rsp-158h]
0x18000ff15  sub     rsp, 258h
0x18000ff1c  mov     rax, cs:__security_cookie
0x18000ff23  xor     rax, rsp
0x18000ff26  mov     [rbp+180h+var_40], rax
0x18000ff2d  xor     r15d, r15d
0x18000ff30  lea     rax, [rsp+280h+Name]
0x18000ff35  mov     [r8], r15
0x18000ff38  mov     r14, r8
0x18000ff3b  mov     edx, 104h
0x18000ff40  mov     r9d, 7FFFFFFEh
0x18000ff46  test    r9, r9
0x18000ff49  jz      short loc_18000FF6A
0x18000ff4b  movzx   r8d, word ptr [rcx]
0x18000ff4f  test    r8w, r8w
0x18000ff53  jz      short loc_18000FF6A
0x18000ff55  mov     [rax], r8w
0x18000ff59  add     rcx, 2
0x18000ff5d  add     rax, 2
0x18000ff61  dec     r9
0x18000ff64  sub     rdx, 1; unsigned __int64
0x18000ff68  jnz     short loc_18000FF46
0x18000ff6a  test    rdx, rdx
0x18000ff6d  lea     rcx, [rax-2]
0x18000ff71  lea     r8, aP0; "_p0"
0x18000ff78  cmovnz  rcx, rax
0x18000ff7c  mov     [rcx], r15w
0x18000ff80  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ff85  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ff8a  mov     esi, 1F0003h
0x18000ff8f  lea     r8, [rsp+280h+Name]; lpName
0x18000ff94  mov     ecx, esi; dwDesiredAccess
0x18000ff96  xor     edx, edx; bInheritHandle
0x18000ff98  call    cs:__imp_OpenSemaphoreW
0x18000ff9e  mov     rbx, rax
0x18000ffa1  test    rax, rax
0x18000ffa4  jz      loc_1800100E1
0x18000ffaa  lea     rdx, [rsp+280h+var_25C]; int *
0x18000ffaf  mov     [rsp+280h+var_25C], r15d
0x18000ffb4  mov     rcx, rax; hHandle
0x18000ffb7  mov     [rsp+280h+var_260], r15d; int
0x18000ffbc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ffc1  mov     edi, eax
0x18000ffc3  test    eax, eax
0x18000ffc5  jns     short loc_18000FFFA
0x18000ffc7  mov     rcx, [rbp+188h]; this
0x18000ffce  lea     r8, aWil; "wil"
0x18000ffd5  mov     r9d, eax; char *
0x18000ffd8  mov     edx, 0D6h; void *
0x18000ffdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffe2  mov     rcx, rbx; hObject
0x18000ffe5  call    cs:__imp_CloseHandle
0x18000ffeb  test    eax, eax
0x18000ffed  jz      loc_180010172
0x18000fff3  mov     eax, edi
0x18000fff5  jmp     loc_180010108
0x18000fffa  lea     r8, asc_1800D7810; "h"
0x180010001  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010006  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001000b  lea     r8, [rsp+280h+Name]; lpName
0x180010010  xor     edx, edx; bInheritHandle
0x180010012  mov     ecx, esi; dwDesiredAccess
0x180010014  call    cs:__imp_OpenSemaphoreW
0x18001001a  mov     rdi, rax
0x18001001d  test    rax, rax
0x180010020  jz      loc_1800100B5
0x180010026  lea     rdx, [rsp+280h+var_260]; int *
0x18001002b  mov     rcx, rax; hHandle
0x18001002e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010033  mov     esi, eax
0x180010035  test    eax, eax
0x180010037  jns     short loc_18001007D
0x180010039  mov     rcx, [rbp+188h]; this
0x180010040  lea     r8, aWil; "wil"
0x180010047  mov     r9d, eax; char *
0x18001004a  mov     edx, 0DEh; void *
0x18001004f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010054  mov     rcx, rdi; hObject
0x180010057  call    cs:__imp_CloseHandle
0x18001005d  test    eax, eax
0x18001005f  jz      loc_18001018B
0x180010065  mov     rcx, rbx; hObject
0x180010068  call    cs:__imp_CloseHandle
0x18001006e  test    eax, eax
0x180010070  jz      loc_1800101A4
0x180010076  mov     eax, esi
0x180010078  jmp     loc_180010108
0x18001007d  mov     rcx, rdi; hObject
0x180010080  call    cs:__imp_CloseHandle
0x180010086  test    eax, eax
0x180010088  jz      loc_180010127
0x18001008e  movsxd  rax, [rsp+280h+var_25C]
0x180010093  movsxd  rcx, [rsp+280h+var_260]
0x180010098  shl     rcx, 1Fh
0x18001009c  or      rcx, rax
0x18001009f  mov     [r14], rcx
0x1800100a2  mov     rcx, rbx; hObject
0x1800100a5  call    cs:__imp_CloseHandle
0x1800100ab  test    eax, eax
0x1800100ad  jz      loc_180010140
0x1800100b3  jmp     short loc_1800100EC
0x1800100b5  mov     rcx, [rbp+188h]; this
0x1800100bc  lea     r8, aWil; "wil"
0x1800100c3  mov     edx, 0DCh; void *
0x1800100c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800100cd  mov     rcx, rbx; hObject
0x1800100d0  mov     edi, eax
0x1800100d2  call    cs:__imp_CloseHandle
0x1800100d8  test    eax, eax
0x1800100da  jz      short loc_180010159
0x1800100dc  jmp     loc_18000FFF3
0x1800100e1  call    cs:__imp_GetLastError
0x1800100e7  cmp     eax, 2
0x1800100ea  jnz     short loc_1800100F0
0x1800100ec  xor     eax, eax
0x1800100ee  jmp     short loc_180010108
0x1800100f0  mov     rcx, [rbp+188h]; this
0x1800100f7  lea     r8, aWil; "wil"
0x1800100fe  mov     edx, 0D0h; void *
0x180010103  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010108  mov     rcx, [rbp+180h+var_40]
0x18001010f  xor     rcx, rsp; StackCookie
0x180010112  call    __security_check_cookie
0x180010117  add     rsp, 258h
0x18001011e  pop     r15
0x180010120  pop     r14
0x180010122  pop     rdi
0x180010123  pop     rsi
0x180010124  pop     rbx
0x180010125  pop     rbp
0x180010126  retn
0x180010127  mov     rcx, [rbp+188h]; this
0x18001012e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010135  mov     edx, 0A0Bh; void *
0x18001013a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010140  mov     rcx, [rbp+188h]; this
0x180010147  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001014e  mov     edx, 0A0Bh; void *
0x180010153  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010159  mov     rcx, [rbp+188h]; this
0x180010160  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010167  mov     edx, 0A0Bh; void *
0x18001016c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010172  mov     rcx, [rbp+188h]; this
0x180010179  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010180  mov     edx, 0A0Bh; void *
0x180010185  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001018b  mov     rcx, [rbp+188h]; this
0x180010192  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010199  mov     edx, 0A0Bh; void *
0x18001019e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800101a4  mov     rcx, [rbp+188h]; this
0x1800101ab  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800101b2  mov     edx, 0A0Bh; void *
0x1800101b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

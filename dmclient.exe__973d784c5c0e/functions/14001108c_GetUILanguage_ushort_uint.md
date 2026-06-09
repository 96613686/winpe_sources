# GetUILanguage(ushort *,uint)

- ea: `0x14001108c`
- end: `0x1400113eb`
- name: `?GetUILanguage@@YAJPEAGI@Z`
- size: `863`
- prototype: `__int64 __fastcall(LPWSTR lpsz, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c928`
- `0x140010c40`
- `0x1400113f4`

## callees

- `0x140001418`
- `0x14001108c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400111d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400111d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400113bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400113bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400113d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400113d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001121b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001121b`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1400110d4`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140011207`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1400110d4`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140011207`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1400113b1`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1400113b1`

## string_xrefs

- `0x14001139f`: `StringCchCopy failed to copy the language string`

## pseudocode

```c
__int64 __fastcall GetUILanguage(LPWSTR lpsz)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rsi
  __int64 v10; // r9
  signed int LastError; // eax
  LPWSTR v12; // r8
  char *v13; // rdx
  const char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  WCHAR *v17; // rcx
  LPWSTR v18; // rcx
  HANDLE v19; // rax
  __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const char *v23; // [rsp+60h] [rbp-10h] BYREF
  __int64 v24; // [rsp+68h] [rbp-8h] BYREF
  ULONG pulNumLanguages; // [rsp+A0h] [rbp+30h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+A8h] [rbp+38h] BYREF
  int v27; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+48h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !lpsz )
    return (unsigned int)-2147467261;
  *(_OWORD *)lpsz = 0;
  *(_QWORD *)(lpsz + 7) = 0;
  if ( GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    v6 = 2LL * pcchLanguagesBuffer;
    ProcessHeap = GetProcessHeap();
    v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v6);
    v9 = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    if ( GetUserPreferredUILanguages(8u, &pulNumLanguages, v8, &pcchLanguagesBuffer) )
    {
      v15 = 2147483646;
      v16 = 11;
      v17 = v9;
      v12 = lpsz;
      do
      {
        if ( !v15 )
          break;
        v10 = *v17;
        if ( !(_WORD)v10 )
          break;
        *v12 = v10;
        ++v17;
        ++v12;
        --v15;
        --v16;
      }
      while ( v16 );
      v18 = v12 - 1;
      v2 = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
        v18 = v12;
      *v18 = 0;
      if ( v16 )
      {
        CharLowerBuffW(lpsz, 0xBu);
        goto LABEL_32;
      }
      if ( (unsigned int)dword_140028000 <= 2
        || (qword_140028010 & 0x400000000000LL) == 0
        || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      {
        goto LABEL_32;
      }
      v27 = 207;
      v23 = "GetUILanguage";
      v13 = byte_140022E73;
      v22 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v14 = "StringCchCopy failed to copy the language string";
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_140028000 <= 2
        || (qword_140028010 & 0x400000000000LL) == 0
        || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      {
        goto LABEL_32;
      }
      v27 = 193;
      v23 = "GetUILanguage";
      v13 = &byte_1400230A7;
      v22 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v14 = "GetUserPreferredUILanguages failed";
    }
    v21 = (__int64)v14;
    v28 = v2;
    v24 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      0x400000000000LL,
      (unsigned __int8 *)v13,
      (__int64)v12,
      v10,
      (const unsigned __int16 **)&v21,
      (__int64)&v28,
      (const unsigned __int16 **)&v22,
      (const unsigned __int16 **)&v23,
      (__int64)&v27,
      (__int64)&v24);
LABEL_32:
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v9);
    return v2;
  }
  v3 = GetLastError();
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( (unsigned int)dword_140028000 > 2
    && (qword_140028010 & 0x400000000000LL) != 0
    && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
  {
    v21 = 0x1000000;
    v22 = "GetUILanguage";
    v27 = 179;
    v23 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
    v24 = (__int64)"GetUserPreferredUILanguages failed";
    v28 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      0x400000000000LL,
      (unsigned __int8 *)byte_140023105,
      v4,
      v5,
      (const unsigned __int16 **)&v24,
      (__int64)&v28,
      (const unsigned __int16 **)&v23,
      (const unsigned __int16 **)&v22,
      (__int64)&v27,
      (__int64)&v21);
  }
  return v2;
}

```

## disassembly

```asm
0x14001108c  mov     [rsp-28h+pcchLanguagesBuffer], edx
0x140011090  push    rbp
0x140011091  push    rbx
0x140011092  push    rsi
0x140011093  push    rdi
0x140011094  push    r14
0x140011096  mov     rbp, rsp
0x140011099  sub     rsp, 70h
0x14001109d  xor     r14d, r14d
0x1400110a0  mov     rdi, rcx
0x1400110a3  mov     [rbp+pulNumLanguages], r14d
0x1400110a7  mov     [rbp+pcchLanguagesBuffer], r14d
0x1400110ab  test    rcx, rcx
0x1400110ae  jnz     short loc_1400110BA
0x1400110b0  mov     ebx, 80004003h
0x1400110b5  jmp     loc_1400113DD
0x1400110ba  xor     eax, eax
0x1400110bc  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1400110c0  xorps   xmm0, xmm0
0x1400110c3  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1400110c7  movups  xmmword ptr [rcx], xmm0
0x1400110ca  mov     [rcx+0Eh], rax
0x1400110ce  xor     r8d, r8d; pwszLanguagesBuffer
0x1400110d1  lea     ecx, [rax+8]; dwFlags
0x1400110d4  call    cs:__imp_GetUserPreferredUILanguages
0x1400110db  nop     dword ptr [rax+rax+00h]
0x1400110e0  test    eax, eax
0x1400110e2  jnz     loc_1400111BC
0x1400110e8  call    cs:__imp_GetLastError
0x1400110ef  nop     dword ptr [rax+rax+00h]
0x1400110f4  mov     ebx, eax
0x1400110f6  test    eax, eax
0x1400110f8  jle     short loc_140011103
0x1400110fa  movzx   ebx, ax
0x1400110fd  or      ebx, 80070000h
0x140011103  mov     eax, cs:dword_140028000
0x140011109  cmp     eax, 2
0x14001110c  jbe     loc_1400113DD
0x140011112  mov     rdx, cs:qword_140028018
0x140011119  mov     rcx, 400000000000h
0x140011123  mov     rax, cs:qword_140028010
0x14001112a  test    rcx, rax
0x14001112d  jz      loc_1400113DD
0x140011133  mov     rax, rdx
0x140011136  and     rax, rcx
0x140011139  cmp     rax, rdx
0x14001113c  jnz     loc_1400113DD
0x140011142  lea     rax, aGetuilanguage; "GetUILanguage"
0x140011149  mov     [rbp+var_20], 1000000h
0x140011151  mov     [rbp+var_18], rax
0x140011155  lea     rdx, byte_140023105
0x14001115c  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140011163  mov     [rbp+arg_10], 0B3h
0x14001116a  mov     [rbp+var_10], rax
0x14001116e  lea     rax, aGetuserpreferr; "GetUserPreferredUILanguages failed"
0x140011175  mov     [rbp+var_8], rax
0x140011179  lea     rax, [rbp+var_20]
0x14001117d  mov     [rsp+70h+var_28], rax
0x140011182  lea     rax, [rbp+arg_10]
0x140011186  mov     [rsp+70h+var_30], rax
0x14001118b  lea     rax, [rbp+var_18]
0x14001118f  mov     [rsp+70h+var_38], rax
0x140011194  lea     rax, [rbp+var_10]
0x140011198  mov     [rsp+70h+var_40], rax
0x14001119d  lea     rax, [rbp+arg_18]
0x1400111a1  mov     [rsp+70h+var_48], rax
0x1400111a6  lea     rax, [rbp+var_8]
0x1400111aa  mov     [rsp+70h+var_50], rax
0x1400111af  mov     [rbp+arg_18], ebx
0x1400111b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400111b7  jmp     loc_1400113DD
0x1400111bc  mov     ebx, [rbp+pcchLanguagesBuffer]
0x1400111bf  add     rbx, rbx
0x1400111c2  call    cs:__imp_GetProcessHeap
0x1400111c9  nop     dword ptr [rax+rax+00h]
0x1400111ce  mov     r8, rbx; dwBytes
0x1400111d1  mov     edx, 8; dwFlags
0x1400111d6  mov     rcx, rax; hHeap
0x1400111d9  call    cs:__imp_HeapAlloc
0x1400111e0  nop     dword ptr [rax+rax+00h]
0x1400111e5  mov     rsi, rax
0x1400111e8  test    rax, rax
0x1400111eb  jnz     short loc_1400111F7
0x1400111ed  mov     ebx, 8007000Eh
0x1400111f2  jmp     loc_1400113DD
0x1400111f7  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1400111fb  mov     r8, rsi; pwszLanguagesBuffer
0x1400111fe  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140011202  mov     ecx, 8; dwFlags
0x140011207  call    cs:__imp_GetUserPreferredUILanguages
0x14001120e  nop     dword ptr [rax+rax+00h]
0x140011213  test    eax, eax
0x140011215  jnz     loc_1400112EF
0x14001121b  call    cs:__imp_GetLastError
0x140011222  nop     dword ptr [rax+rax+00h]
0x140011227  mov     ebx, eax
0x140011229  test    eax, eax
0x14001122b  jle     short loc_140011236
0x14001122d  movzx   ebx, ax
0x140011230  or      ebx, 80070000h
0x140011236  mov     eax, cs:dword_140028000
0x14001123c  cmp     eax, 2
0x14001123f  jbe     loc_1400113BD
0x140011245  mov     rdx, cs:qword_140028018
0x14001124c  mov     rcx, 400000000000h
0x140011256  mov     rax, cs:qword_140028010
0x14001125d  test    rcx, rax
0x140011260  jz      loc_1400113BD
0x140011266  mov     rax, rdx
0x140011269  and     rax, rcx
0x14001126c  cmp     rax, rdx
0x14001126f  jnz     loc_1400113BD
0x140011275  lea     rax, aGetuilanguage; "GetUILanguage"
0x14001127c  mov     [rbp+arg_10], 0C1h
0x140011283  mov     [rbp+var_10], rax
0x140011287  lea     rdx, byte_1400230A7
0x14001128e  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140011295  mov     [rbp+var_18], rax
0x140011299  lea     rax, aGetuserpreferr; "GetUserPreferredUILanguages failed"
0x1400112a0  mov     [rbp+var_20], rax
0x1400112a4  lea     rax, [rbp+var_8]
0x1400112a8  mov     [rsp+70h+var_28], rax
0x1400112ad  lea     rax, [rbp+arg_10]
0x1400112b1  mov     [rsp+70h+var_30], rax
0x1400112b6  lea     rax, [rbp+var_10]
0x1400112ba  mov     [rsp+70h+var_38], rax
0x1400112bf  lea     rax, [rbp+var_18]
0x1400112c3  mov     [rsp+70h+var_40], rax
0x1400112c8  lea     rax, [rbp+arg_18]
0x1400112cc  mov     [rsp+70h+var_48], rax
0x1400112d1  lea     rax, [rbp+var_20]
0x1400112d5  mov     [rsp+70h+var_50], rax
0x1400112da  mov     [rbp+arg_18], ebx
0x1400112dd  mov     [rbp+var_8], 1000000h
0x1400112e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400112ea  jmp     loc_1400113BD
0x1400112ef  mov     r10d, 0Bh
0x1400112f5  mov     eax, 7FFFFFFEh
0x1400112fa  mov     edx, r10d
0x1400112fd  mov     rcx, rsi
0x140011300  mov     r8, rdi
0x140011303  test    rax, rax
0x140011306  jz      short loc_140011327
0x140011308  movzx   r9d, word ptr [rcx]
0x14001130c  test    r9w, r9w
0x140011310  jz      short loc_140011327
0x140011312  mov     [r8], r9w
0x140011316  add     rcx, 2
0x14001131a  add     r8, 2
0x14001131e  dec     rax
0x140011321  sub     rdx, 1
0x140011325  jnz     short loc_140011303
0x140011327  mov     rax, rdx
0x14001132a  lea     rcx, [r8-2]
0x14001132e  neg     rax
0x140011331  sbb     ebx, ebx
0x140011333  not     ebx
0x140011335  and     ebx, 8007007Ah
0x14001133b  test    rdx, rdx
0x14001133e  cmovnz  rcx, r8
0x140011342  mov     [rcx], r14w
0x140011346  jnz     short loc_1400113AB
0x140011348  mov     eax, cs:dword_140028000
0x14001134e  cmp     eax, 2
0x140011351  jbe     short loc_1400113BD
0x140011353  mov     rdx, cs:qword_140028018
0x14001135a  mov     rcx, 400000000000h
0x140011364  mov     rax, cs:qword_140028010
0x14001136b  test    rcx, rax
0x14001136e  jz      short loc_1400113BD
0x140011370  mov     rax, rdx
0x140011373  and     rax, rcx
0x140011376  cmp     rax, rdx
0x140011379  jnz     short loc_1400113BD
0x14001137b  lea     rax, aGetuilanguage; "GetUILanguage"
0x140011382  mov     [rbp+arg_10], 0CFh
0x140011389  mov     [rbp+var_10], rax
0x14001138d  lea     rdx, byte_140022E73
0x140011394  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001139b  mov     [rbp+var_18], rax
0x14001139f  lea     rax, aStringcchcopyF; "StringCchCopy failed to copy the langua"...
0x1400113a6  jmp     loc_1400112A0
0x1400113ab  mov     edx, r10d; cchLength
0x1400113ae  mov     rcx, rdi; lpsz
0x1400113b1  call    cs:__imp_CharLowerBuffW
0x1400113b8  nop     dword ptr [rax+rax+00h]
0x1400113bd  call    cs:__imp_GetProcessHeap
0x1400113c4  nop     dword ptr [rax+rax+00h]
0x1400113c9  mov     r8, rsi; lpMem
0x1400113cc  xor     edx, edx; dwFlags
0x1400113ce  mov     rcx, rax; hHeap
0x1400113d1  call    cs:__imp_HeapFree
0x1400113d8  nop     dword ptr [rax+rax+00h]
0x1400113dd  mov     eax, ebx
0x1400113df  add     rsp, 70h
0x1400113e3  pop     r14
0x1400113e5  pop     rdi
0x1400113e6  pop     rsi
0x1400113e7  pop     rbx
0x1400113e8  pop     rbp
0x1400113e9  retn
```

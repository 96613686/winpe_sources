# GetUILanguage(ushort *,uint)

- ea: `0x1400109d0`
- end: `0x140010cf8`
- name: `?GetUILanguage@@YAJPEAGI@Z`
- size: `808`
- prototype: `__int64 __fastcall(LPWSTR lpsz)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c47c`
- `0x1400105d8`
- `0x140010d00`

## callees

- `0x140001414`
- `0x1400109d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010b0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010b0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010cd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010cd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010ce5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010b41`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140010a18`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140010b33`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140010a18`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x140010b33`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010cd1`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010cd1`

## string_xrefs

- `0x140010cbf`: `StringCchCopy failed to copy the language string`

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
      if ( (unsigned int)dword_140027000 <= 2
        || (qword_140027010 & 0x400000000000LL) == 0
        || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      {
        goto LABEL_32;
      }
      v27 = 207;
      v23 = "GetUILanguage";
      v13 = byte_140021E6B;
      v22 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v14 = "StringCchCopy failed to copy the language string";
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_140027000 <= 2
        || (qword_140027010 & 0x400000000000LL) == 0
        || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      {
        goto LABEL_32;
      }
      v27 = 193;
      v23 = "GetUILanguage";
      v13 = &byte_14002209F;
      v22 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v14 = "GetUserPreferredUILanguages failed";
    }
    v21 = (__int64)v14;
    v28 = v2;
    v24 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      0x400000000000LL,
      (__int64)v13,
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
  if ( (unsigned int)dword_140027000 > 2
    && (qword_140027010 & 0x400000000000LL) != 0
    && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
  {
    v21 = 0x1000000;
    v22 = "GetUILanguage";
    v27 = 179;
    v23 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
    v24 = (__int64)"GetUserPreferredUILanguages failed";
    v28 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      0x400000000000LL,
      (__int64)byte_1400220FD,
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
0x1400109d0  mov     [rsp-28h+pcchLanguagesBuffer], edx
0x1400109d4  push    rbp
0x1400109d5  push    rbx
0x1400109d6  push    rsi
0x1400109d7  push    rdi
0x1400109d8  push    r14
0x1400109da  mov     rbp, rsp
0x1400109dd  sub     rsp, 70h
0x1400109e1  xor     r14d, r14d
0x1400109e4  mov     rdi, rcx
0x1400109e7  mov     [rbp+pulNumLanguages], r14d
0x1400109eb  mov     [rbp+pcchLanguagesBuffer], r14d
0x1400109ef  test    rcx, rcx
0x1400109f2  jnz     short loc_1400109FE
0x1400109f4  mov     ebx, 80004003h
0x1400109f9  jmp     loc_140010CEB
0x1400109fe  xor     eax, eax
0x140010a00  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x140010a04  xorps   xmm0, xmm0
0x140010a07  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140010a0b  movups  xmmword ptr [rcx], xmm0
0x140010a0e  mov     [rcx+0Eh], rax
0x140010a12  xor     r8d, r8d; pwszLanguagesBuffer
0x140010a15  lea     ecx, [rax+8]; dwFlags
0x140010a18  call    cs:__imp_GetUserPreferredUILanguages
0x140010a1e  test    eax, eax
0x140010a20  jnz     loc_140010AF4
0x140010a26  call    cs:__imp_GetLastError
0x140010a2c  mov     ebx, eax
0x140010a2e  test    eax, eax
0x140010a30  jle     short loc_140010A3B
0x140010a32  movzx   ebx, ax
0x140010a35  or      ebx, 80070000h
0x140010a3b  mov     eax, cs:dword_140027000
0x140010a41  cmp     eax, 2
0x140010a44  jbe     loc_140010CEB
0x140010a4a  mov     rdx, cs:qword_140027018
0x140010a51  mov     rcx, 400000000000h
0x140010a5b  mov     rax, cs:qword_140027010
0x140010a62  test    rcx, rax
0x140010a65  jz      loc_140010CEB
0x140010a6b  mov     rax, rdx
0x140010a6e  and     rax, rcx
0x140010a71  cmp     rax, rdx
0x140010a74  jnz     loc_140010CEB
0x140010a7a  lea     rax, aGetuilanguage; "GetUILanguage"
0x140010a81  mov     [rbp+var_20], 1000000h
0x140010a89  mov     [rbp+var_18], rax
0x140010a8d  lea     rdx, byte_1400220FD
0x140010a94  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010a9b  mov     [rbp+arg_10], 0B3h
0x140010aa2  mov     [rbp+var_10], rax
0x140010aa6  lea     rax, aGetuserpreferr; "GetUserPreferredUILanguages failed"
0x140010aad  mov     [rbp+var_8], rax
0x140010ab1  lea     rax, [rbp+var_20]
0x140010ab5  mov     [rsp+70h+var_28], rax
0x140010aba  lea     rax, [rbp+arg_10]
0x140010abe  mov     [rsp+70h+var_30], rax
0x140010ac3  lea     rax, [rbp+var_18]
0x140010ac7  mov     [rsp+70h+var_38], rax
0x140010acc  lea     rax, [rbp+var_10]
0x140010ad0  mov     [rsp+70h+var_40], rax
0x140010ad5  lea     rax, [rbp+arg_18]
0x140010ad9  mov     [rsp+70h+var_48], rax
0x140010ade  lea     rax, [rbp+var_8]
0x140010ae2  mov     [rsp+70h+var_50], rax
0x140010ae7  mov     [rbp+arg_18], ebx
0x140010aea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010aef  jmp     loc_140010CEB
0x140010af4  mov     ebx, [rbp+pcchLanguagesBuffer]
0x140010af7  add     rbx, rbx
0x140010afa  call    cs:__imp_GetProcessHeap
0x140010b00  mov     r8, rbx; dwBytes
0x140010b03  mov     edx, 8; dwFlags
0x140010b08  mov     rcx, rax; hHeap
0x140010b0b  call    cs:__imp_HeapAlloc
0x140010b11  mov     rsi, rax
0x140010b14  test    rax, rax
0x140010b17  jnz     short loc_140010B23
0x140010b19  mov     ebx, 8007000Eh
0x140010b1e  jmp     loc_140010CEB
0x140010b23  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x140010b27  mov     r8, rsi; pwszLanguagesBuffer
0x140010b2a  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140010b2e  mov     ecx, 8; dwFlags
0x140010b33  call    cs:__imp_GetUserPreferredUILanguages
0x140010b39  test    eax, eax
0x140010b3b  jnz     loc_140010C0F
0x140010b41  call    cs:__imp_GetLastError
0x140010b47  mov     ebx, eax
0x140010b49  test    eax, eax
0x140010b4b  jle     short loc_140010B56
0x140010b4d  movzx   ebx, ax
0x140010b50  or      ebx, 80070000h
0x140010b56  mov     eax, cs:dword_140027000
0x140010b5c  cmp     eax, 2
0x140010b5f  jbe     loc_140010CD7
0x140010b65  mov     rdx, cs:qword_140027018
0x140010b6c  mov     rcx, 400000000000h
0x140010b76  mov     rax, cs:qword_140027010
0x140010b7d  test    rcx, rax
0x140010b80  jz      loc_140010CD7
0x140010b86  mov     rax, rdx
0x140010b89  and     rax, rcx
0x140010b8c  cmp     rax, rdx
0x140010b8f  jnz     loc_140010CD7
0x140010b95  lea     rax, aGetuilanguage; "GetUILanguage"
0x140010b9c  mov     [rbp+arg_10], 0C1h
0x140010ba3  mov     [rbp+var_10], rax
0x140010ba7  lea     rdx, byte_14002209F
0x140010bae  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010bb5  mov     [rbp+var_18], rax
0x140010bb9  lea     rax, aGetuserpreferr; "GetUserPreferredUILanguages failed"
0x140010bc0  mov     [rbp+var_20], rax
0x140010bc4  lea     rax, [rbp+var_8]
0x140010bc8  mov     [rsp+70h+var_28], rax
0x140010bcd  lea     rax, [rbp+arg_10]
0x140010bd1  mov     [rsp+70h+var_30], rax
0x140010bd6  lea     rax, [rbp+var_10]
0x140010bda  mov     [rsp+70h+var_38], rax
0x140010bdf  lea     rax, [rbp+var_18]
0x140010be3  mov     [rsp+70h+var_40], rax
0x140010be8  lea     rax, [rbp+arg_18]
0x140010bec  mov     [rsp+70h+var_48], rax
0x140010bf1  lea     rax, [rbp+var_20]
0x140010bf5  mov     [rsp+70h+var_50], rax
0x140010bfa  mov     [rbp+arg_18], ebx
0x140010bfd  mov     [rbp+var_8], 1000000h
0x140010c05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010c0a  jmp     loc_140010CD7
0x140010c0f  mov     r10d, 0Bh
0x140010c15  mov     eax, 7FFFFFFEh
0x140010c1a  mov     edx, r10d
0x140010c1d  mov     rcx, rsi
0x140010c20  mov     r8, rdi
0x140010c23  test    rax, rax
0x140010c26  jz      short loc_140010C47
0x140010c28  movzx   r9d, word ptr [rcx]
0x140010c2c  test    r9w, r9w
0x140010c30  jz      short loc_140010C47
0x140010c32  mov     [r8], r9w
0x140010c36  add     rcx, 2
0x140010c3a  add     r8, 2
0x140010c3e  dec     rax
0x140010c41  sub     rdx, 1
0x140010c45  jnz     short loc_140010C23
0x140010c47  mov     rax, rdx
0x140010c4a  lea     rcx, [r8-2]
0x140010c4e  neg     rax
0x140010c51  sbb     ebx, ebx
0x140010c53  not     ebx
0x140010c55  and     ebx, 8007007Ah
0x140010c5b  test    rdx, rdx
0x140010c5e  cmovnz  rcx, r8
0x140010c62  mov     [rcx], r14w
0x140010c66  jnz     short loc_140010CCB
0x140010c68  mov     eax, cs:dword_140027000
0x140010c6e  cmp     eax, 2
0x140010c71  jbe     short loc_140010CD7
0x140010c73  mov     rdx, cs:qword_140027018
0x140010c7a  mov     rcx, 400000000000h
0x140010c84  mov     rax, cs:qword_140027010
0x140010c8b  test    rcx, rax
0x140010c8e  jz      short loc_140010CD7
0x140010c90  mov     rax, rdx
0x140010c93  and     rax, rcx
0x140010c96  cmp     rax, rdx
0x140010c99  jnz     short loc_140010CD7
0x140010c9b  lea     rax, aGetuilanguage; "GetUILanguage"
0x140010ca2  mov     [rbp+arg_10], 0CFh
0x140010ca9  mov     [rbp+var_10], rax
0x140010cad  lea     rdx, byte_140021E6B
0x140010cb4  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010cbb  mov     [rbp+var_18], rax
0x140010cbf  lea     rax, aStringcchcopyF; "StringCchCopy failed to copy the langua"...
0x140010cc6  jmp     loc_140010BC0
0x140010ccb  mov     edx, r10d; cchLength
0x140010cce  mov     rcx, rdi; lpsz
0x140010cd1  call    cs:__imp_CharLowerBuffW
0x140010cd7  call    cs:__imp_GetProcessHeap
0x140010cdd  mov     r8, rsi; lpMem
0x140010ce0  xor     edx, edx; dwFlags
0x140010ce2  mov     rcx, rax; hHeap
0x140010ce5  call    cs:__imp_HeapFree
0x140010ceb  mov     eax, ebx
0x140010ced  add     rsp, 70h
0x140010cf1  pop     r14
0x140010cf3  pop     rdi
0x140010cf4  pop     rsi
0x140010cf5  pop     rbx
0x140010cf6  pop     rbp
0x140010cf7  retn
```

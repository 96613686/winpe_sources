# CFile::MoveTempFile(void)

- ea: `0x18002a0f0`
- end: `0x18002a65a`
- name: `?MoveTempFile@CFile@@QEAAJXZ`
- size: `1386`
- prototype: `__int64 __fastcall(CFile *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029a84`
- `0x18007d050`
- `0x18008afa4`

## callees

- `0x18002a0f0`
- `0x18002a660`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800ab738`
- `0x1800b12d0`
- `0x1800cac00`
- `0x1800f55fc`
- `0x1800f5798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a31a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a31a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5db`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a1df`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a461`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a1df`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a461`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a279`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a545`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a279`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a545`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a193`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a193`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a2f3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a5bf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a2f3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a5bf`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002a3fa`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002a3fa`

## string_xrefs

- `0x18002a2e9`: `SetFileAttributesW`
- `0x18002a5b5`: `SetFileAttributesW`
- `0x18002a202`: `BITSSetFileAttributesAsApp`
- `0x18002a343`: `BITSSetFileAttributesAsApp`
- `0x18002a5aa`: `BITSSetFileAttributesAsApp`

## pseudocode

```c
__int64 __fastcall CFile::MoveTempFile(CFile *this)
{
  EVENT_LOG *v2; // rcx
  const wchar_t *v3; // r8
  signed int v4; // r12d
  DWORD v5; // r13d
  DWORD LastError; // eax
  unsigned int v7; // r15d
  const wchar_t *v8; // r14
  DWORD v9; // esi
  const unsigned __int16 *v10; // rbp
  DWORD v11; // eax
  int v12; // eax
  char v13; // al
  DWORD v14; // eax
  EVENT_LOG *v15; // rcx
  __int64 v16; // rdx
  EVENT_LOG *v17; // rcx
  int i; // esi
  int v19; // r8d
  const unsigned __int16 *v21; // rbx
  DWORD v22; // edi
  DWORD v23; // eax
  int v24; // eax
  const wchar_t *v25; // rsi
  char v26; // al
  DWORD dwFileAttributes; // [rsp+70h] [rbp+8h] BYREF
  DWORD TokenInformation; // [rsp+78h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = L"FALSE";
    if ( !*((_BYTE *)this + 260) )
      v3 = L"TRUE";
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)&WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
      *((_DWORD *)this + 6) + 12,
      *((_QWORD *)this + 2) + 12LL,
      (__int64)v3);
    v2 = WPP_GLOBAL_Control;
  }
  v4 = 0;
  v5 = 50;
  if ( *((_BYTE *)this + 260) )
  {
    dwFileAttributes = 0;
  }
  else
  {
    dwFileAttributes = GetFileAttributesW((LPCWSTR)(*((_QWORD *)this + 3) + 12LL));
    if ( dwFileAttributes == -1 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, LastError);
      Sleep(0x32u);
    }
    v2 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  v8 = L"BITSSetFileAttributesAsApp";
  while ( 1 )
  {
    if ( v7 >= 0xA )
    {
      if ( v2 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v2 + 2), 60, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
      return (unsigned int)v4;
    }
    v9 = *((_DWORD *)this + 74);
    v10 = (const unsigned __int16 *)(*((_QWORD *)this + 3) + 12LL);
    if ( v2 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)v2 + 2),
        44,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v10,
        *((_DWORD *)this + 74));
    ReturnLength = 0;
    TokenInformation = 0;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v11 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, v11);
      }
      goto LABEL_32;
    }
    if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
    {
      v12 = BITSSetFileAttributesAsApp(v10, v9);
    }
    else
    {
      v8 = L"SetFileAttributesW";
      v12 = SetFileAttributesW(v10, v9);
    }
    if ( v12 )
      break;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v8,
        v13);
    }
    v8 = L"BITSSetFileAttributesAsApp";
LABEL_32:
    v14 = GetLastError();
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, v14);
      v2 = WPP_GLOBAL_Control;
    }
    ++v7;
  }
  if ( !*((_BYTE *)this + 260) )
  {
    v17 = WPP_GLOBAL_Control;
    for ( i = 0; (unsigned int)i < 0xA; ++i )
    {
      if ( MoveFileExW((LPCWSTR)(*((_QWORD *)this + 3) + 12LL), (LPCWSTR)(*((_QWORD *)this + 2) + 12LL), 3u) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 61;
          goto LABEL_54;
        }
        goto LABEL_55;
      }
      v4 = GetLastError();
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          v19,
          *((_QWORD *)this + 3) + 12,
          *((_QWORD *)this + 2) + 12LL,
          v4);
        v17 = WPP_GLOBAL_Control;
      }
      if ( i > 3 && v4 != 32 )
        break;
      if ( (unsigned int)i < 9 )
      {
        Sleep(v5);
        v17 = WPP_GLOBAL_Control;
      }
      v5 *= 2;
    }
    if ( v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)v17 + 2), 63, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      v17 = WPP_GLOBAL_Control;
    }
    v21 = (const unsigned __int16 *)(*((_QWORD *)this + 3) + 12LL);
    v22 = dwFileAttributes;
    if ( v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)v17 + 2),
        44,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v21,
        dwFileAttributes);
    TokenInformation = 0;
    dwFileAttributes = 0;
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenIsAppContainer,
           &dwFileAttributes,
           4u,
           &TokenInformation) )
    {
      if ( dwFileAttributes && IsAppContainerFileFunctionalitySupported() )
      {
        v24 = BITSSetFileAttributesAsApp(v21, v22);
        v25 = L"BITSSetFileAttributesAsApp";
      }
      else
      {
        v25 = L"SetFileAttributesW";
        v24 = SetFileAttributesW(v21, v22);
      }
      if ( !v24
        && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v26 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
          (_DWORD)v25,
          v26);
      }
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v23 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, v23);
    }
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    return (unsigned int)v4;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 59;
LABEL_54:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
  }
LABEL_55:
  *((_BYTE *)this + 257) = 1;
  CFile::TriggerSerialization(this, 1);
  return 0;
}

```

## disassembly

```asm
0x18002a0f0  push    rbx
0x18002a0f2  push    rdi
0x18002a0f3  push    r12
0x18002a0f5  push    r13
0x18002a0f7  push    r14
0x18002a0f9  push    r15
0x18002a0fb  sub     rsp, 38h
0x18002a0ff  mov     rbx, rcx
0x18002a102  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a109  lea     rdx, WPP_GLOBAL_Control
0x18002a110  cmp     rcx, rdx
0x18002a113  jz      short loc_18002A171
0x18002a115  test    byte ptr [rcx+1Ch], 1
0x18002a119  jz      short loc_18002A171
0x18002a11b  cmp     byte ptr [rbx+104h], 0
0x18002a122  lea     rax, aTrue_2; "TRUE"
0x18002a129  mov     r9, [rbx+18h]
0x18002a12d  lea     r8, aFalse_2; "FALSE"
0x18002a134  mov     rcx, [rcx+10h]
0x18002a138  cmovz   r8, rax
0x18002a13c  mov     rax, [rbx+10h]
0x18002a140  add     r9, 0Ch
0x18002a144  mov     [rsp+68h+var_40], r8
0x18002a149  add     rax, 0Ch
0x18002a14d  mov     edx, 37h ; '7'
0x18002a152  mov     [rsp+68h+ReturnLength], rax
0x18002a157  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a15e  call    WPP_SF_SSS
0x18002a163  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a16a  lea     rdx, WPP_GLOBAL_Control
0x18002a171  xor     r12d, r12d
0x18002a174  mov     [rsp+68h+arg_18], rbp
0x18002a17c  mov     r13d, 32h ; '2'
0x18002a182  cmp     [rbx+104h], r12b
0x18002a189  jnz     short loc_18002A1F5
0x18002a18b  mov     rcx, [rbx+18h]
0x18002a18f  add     rcx, 0Ch; lpFileName
0x18002a193  call    cs:__imp_GetFileAttributesW
0x18002a199  mov     [rsp+68h+dwFileAttributes], eax
0x18002a19d  cmp     eax, 0FFFFFFFFh
0x18002a1a0  jnz     short loc_18002A1E5
0x18002a1a2  call    cs:__imp_GetLastError
0x18002a1a8  mov     r12d, eax
0x18002a1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1b2  lea     rbp, WPP_GLOBAL_Control
0x18002a1b9  cmp     rcx, rbp
0x18002a1bc  jz      short loc_18002A1DC
0x18002a1be  test    byte ptr [rcx+1Ch], 4
0x18002a1c2  jz      short loc_18002A1DC
0x18002a1c4  mov     rcx, [rcx+10h]
0x18002a1c8  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a1cf  mov     edx, 38h ; '8'
0x18002a1d4  mov     r9d, eax
0x18002a1d7  call    WPP_SF_d
0x18002a1dc  mov     ecx, r13d; dwMilliseconds
0x18002a1df  call    cs:__imp_Sleep
0x18002a1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1ec  lea     rdx, WPP_GLOBAL_Control
0x18002a1f3  jmp     short loc_18002A1FA
0x18002a1f5  mov     [rsp+68h+dwFileAttributes], r12d
0x18002a1fa  xor     r15d, r15d
0x18002a1fd  mov     [rsp+68h+var_38], rsi
0x18002a202  lea     r14, aBitssetfileatt; "BITSSetFileAttributesAsApp"
0x18002a209  cmp     r15d, 0Ah
0x18002a20d  jnb     loc_18002A60B
0x18002a213  mov     rbp, [rbx+18h]
0x18002a217  mov     esi, [rbx+128h]
0x18002a21d  add     rbp, 0Ch
0x18002a221  cmp     rcx, rdx
0x18002a224  jz      short loc_18002A248
0x18002a226  test    byte ptr [rcx+1Ch], 1
0x18002a22a  jz      short loc_18002A248
0x18002a22c  mov     rcx, [rcx+10h]
0x18002a230  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a237  mov     edx, 2Ch ; ','
0x18002a23c  mov     dword ptr [rsp+68h+ReturnLength], esi
0x18002a240  mov     r9, rbp
0x18002a243  call    WPP_SF_Sd
0x18002a248  xor     eax, eax
0x18002a24a  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18002a24f  mov     [rsp+68h+arg_10], eax
0x18002a256  mov     r9d, 4; TokenInformationLength
0x18002a25c  mov     [rsp+68h+TokenInformation], eax
0x18002a260  mov     edx, 1Dh; TokenInformationClass
0x18002a265  lea     rax, [rsp+68h+arg_10]
0x18002a26d  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18002a274  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002a279  call    cs:__imp_GetTokenInformation
0x18002a27f  test    eax, eax
0x18002a281  jnz     short loc_18002A2CB
0x18002a283  mov     rax, cs:WPP_GLOBAL_Control
0x18002a28a  lea     rbp, WPP_GLOBAL_Control
0x18002a291  cmp     rax, rbp
0x18002a294  jz      loc_18002A34A
0x18002a29a  test    byte ptr [rax+1Ch], 4
0x18002a29e  jz      loc_18002A34A
0x18002a2a4  call    cs:__imp_GetLastError
0x18002a2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2b1  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a2b8  mov     edx, 2Dh ; '-'
0x18002a2bd  mov     r9d, eax
0x18002a2c0  mov     rcx, [rcx+10h]
0x18002a2c4  call    WPP_SF_d
0x18002a2c9  jmp     short loc_18002A34A
0x18002a2cb  cmp     [rsp+68h+TokenInformation], 0
0x18002a2d0  jz      short loc_18002A2E7
0x18002a2d2  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x18002a2d7  test    al, al
0x18002a2d9  jz      short loc_18002A2E7
0x18002a2db  mov     edx, esi; unsigned int
0x18002a2dd  mov     rcx, rbp; unsigned __int16 *
0x18002a2e0  call    ?BITSSetFileAttributesAsApp@@YAHPEBGK@Z; BITSSetFileAttributesAsApp(ushort const *,ulong)
0x18002a2e5  jmp     short loc_18002A2F9
0x18002a2e7  mov     edx, esi; dwFileAttributes
0x18002a2e9  lea     r14, aSetfileattribu; "SetFileAttributesW"
0x18002a2f0  mov     rcx, rbp; lpFileName
0x18002a2f3  call    cs:__imp_SetFileAttributesW
0x18002a2f9  test    eax, eax
0x18002a2fb  jnz     loc_18002A397
0x18002a301  mov     rax, cs:WPP_GLOBAL_Control
0x18002a308  lea     rbp, WPP_GLOBAL_Control
0x18002a30f  cmp     rax, rbp
0x18002a312  jz      short loc_18002A343
0x18002a314  test    byte ptr [rax+1Ch], 2
0x18002a318  jz      short loc_18002A343
0x18002a31a  call    cs:__imp_GetLastError
0x18002a320  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a327  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a32e  mov     edx, 2Eh ; '.'
0x18002a333  mov     dword ptr [rsp+68h+ReturnLength], eax
0x18002a337  mov     r9, r14
0x18002a33a  mov     rcx, [rcx+10h]
0x18002a33e  call    WPP_SF_Sd
0x18002a343  lea     r14, aBitssetfileatt; "BITSSetFileAttributesAsApp"
0x18002a34a  call    cs:__imp_GetLastError
0x18002a350  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a357  lea     rdx, WPP_GLOBAL_Control
0x18002a35e  cmp     rcx, rdx
0x18002a361  jz      short loc_18002A38F
0x18002a363  test    byte ptr [rcx+1Ch], 4
0x18002a367  jz      short loc_18002A38F
0x18002a369  mov     rcx, [rcx+10h]
0x18002a36d  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a374  mov     edx, 3Ah ; ':'
0x18002a379  mov     r9d, eax
0x18002a37c  call    WPP_SF_d
0x18002a381  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a388  lea     rdx, WPP_GLOBAL_Control
0x18002a38f  inc     r15d
0x18002a392  jmp     loc_18002A209
0x18002a397  cmp     byte ptr [rbx+104h], 0
0x18002a39e  jz      short loc_18002A3CB
0x18002a3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3a7  lea     rbp, WPP_GLOBAL_Control
0x18002a3ae  cmp     rcx, rbp
0x18002a3b1  jz      loc_18002A49F
0x18002a3b7  test    byte ptr [rcx+1Ch], 1
0x18002a3bb  jz      loc_18002A49F
0x18002a3c1  mov     edx, 3Bh ; ';'
0x18002a3c6  jmp     loc_18002A48F
0x18002a3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3d2  lea     rbp, WPP_GLOBAL_Control
0x18002a3d9  xor     esi, esi
0x18002a3db  cmp     esi, 0Ah
0x18002a3de  jnb     loc_18002A4BA
0x18002a3e4  mov     rdx, [rbx+10h]
0x18002a3e8  mov     r8d, 3; dwFlags
0x18002a3ee  mov     rcx, [rbx+18h]
0x18002a3f2  add     rdx, 0Ch; lpNewFileName
0x18002a3f6  add     rcx, 0Ch; lpExistingFileName
0x18002a3fa  call    cs:__imp_MoveFileExW
0x18002a400  test    eax, eax
0x18002a402  jnz     short loc_18002A478
0x18002a404  call    cs:__imp_GetLastError
0x18002a40a  mov     r12d, eax
0x18002a40d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a414  cmp     rcx, rbp
0x18002a417  jz      short loc_18002A44E
0x18002a419  test    byte ptr [rcx+1Ch], 4
0x18002a41d  jz      short loc_18002A44E
0x18002a41f  mov     rax, [rbx+10h]
0x18002a423  mov     edx, 3Eh ; '>'
0x18002a428  mov     r9, [rbx+18h]
0x18002a42c  add     rax, 0Ch
0x18002a430  mov     rcx, [rcx+10h]
0x18002a434  add     r9, 0Ch
0x18002a438  mov     dword ptr [rsp+68h+var_40], r12d
0x18002a43d  mov     [rsp+68h+ReturnLength], rax
0x18002a442  call    WPP_SF_SSD
0x18002a447  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a44e  cmp     esi, 3
0x18002a451  jle     short loc_18002A459
0x18002a453  cmp     r12d, 20h ; ' '
0x18002a457  jnz     short loc_18002A4BA
0x18002a459  cmp     esi, 9
0x18002a45c  jnb     short loc_18002A46E
0x18002a45e  mov     ecx, r13d; dwMilliseconds
0x18002a461  call    cs:__imp_Sleep
0x18002a467  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a46e  add     r13d, r13d
0x18002a471  inc     esi
0x18002a473  jmp     loc_18002A3DB
0x18002a478  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a47f  cmp     rcx, rbp
0x18002a482  jz      short loc_18002A49F
0x18002a484  test    byte ptr [rcx+1Ch], 1
0x18002a488  jz      short loc_18002A49F
0x18002a48a  mov     edx, 3Dh ; '='
0x18002a48f  mov     rcx, [rcx+10h]
0x18002a493  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a49a  call    WPP_SF_
0x18002a49f  mov     edx, 1
0x18002a4a4  mov     byte ptr [rbx+101h], 1
0x18002a4ab  mov     rcx, rbx
0x18002a4ae  call    ?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z; CFile::TriggerSerialization(CFile::SerializationBehavior)
0x18002a4b3  xor     eax, eax
0x18002a4b5  jmp     loc_18002A63E
0x18002a4ba  cmp     rcx, rbp
0x18002a4bd  jz      short loc_18002A4E1
0x18002a4bf  test    byte ptr [rcx+1Ch], 4
0x18002a4c3  jz      short loc_18002A4E1
0x18002a4c5  mov     rcx, [rcx+10h]
0x18002a4c9  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a4d0  mov     edx, 3Fh ; '?'
0x18002a4d5  call    WPP_SF_
0x18002a4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4e1  mov     rbx, [rbx+18h]
0x18002a4e5  add     rbx, 0Ch
0x18002a4e9  mov     edi, [rsp+68h+dwFileAttributes]
0x18002a4ed  cmp     rcx, rbp
0x18002a4f0  jz      short loc_18002A514
0x18002a4f2  test    byte ptr [rcx+1Ch], 1
0x18002a4f6  jz      short loc_18002A514
0x18002a4f8  mov     rcx, [rcx+10h]
0x18002a4fc  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a503  mov     edx, 2Ch ; ','
0x18002a508  mov     dword ptr [rsp+68h+ReturnLength], edi
0x18002a50c  mov     r9, rbx
0x18002a50f  call    WPP_SF_Sd
0x18002a514  lea     rax, [rsp+68h+TokenInformation]
0x18002a519  mov     [rsp+68h+TokenInformation], 0
0x18002a521  mov     r9d, 4; TokenInformationLength
0x18002a527  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002a52c  lea     r8, [rsp+68h+dwFileAttributes]; TokenInformation
0x18002a531  mov     [rsp+68h+dwFileAttributes], 0
0x18002a539  mov     edx, 1Dh; TokenInformationClass
0x18002a53e  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18002a545  call    cs:__imp_GetTokenInformation
0x18002a54b  test    eax, eax
0x18002a54d  jnz     short loc_18002A590
0x18002a54f  mov     rax, cs:WPP_GLOBAL_Control
0x18002a556  cmp     rax, rbp
0x18002a559  jz      loc_18002A604
0x18002a55f  test    byte ptr [rax+1Ch], 4
0x18002a563  jz      loc_18002A604
0x18002a569  call    cs:__imp_GetLastError
0x18002a56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a576  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a57d  mov     edx, 2Dh ; '-'
0x18002a582  mov     r9d, eax
0x18002a585  mov     rcx, [rcx+10h]
0x18002a589  call    WPP_SF_d
0x18002a58e  jmp     short loc_18002A604
0x18002a590  cmp     [rsp+68h+dwFileAttributes], 0
0x18002a595  jz      short loc_18002A5B3
0x18002a597  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x18002a59c  test    al, al
0x18002a59e  jz      short loc_18002A5B3
0x18002a5a0  mov     edx, edi; unsigned int
0x18002a5a2  mov     rcx, rbx; unsigned __int16 *
0x18002a5a5  call    ?BITSSetFileAttributesAsApp@@YAHPEBGK@Z; BITSSetFileAttributesAsApp(ushort const *,ulong)
0x18002a5aa  lea     rsi, aBitssetfileatt; "BITSSetFileAttributesAsApp"
0x18002a5b1  jmp     short loc_18002A5C5
0x18002a5b3  mov     edx, edi; dwFileAttributes
0x18002a5b5  lea     rsi, aSetfileattribu; "SetFileAttributesW"
0x18002a5bc  mov     rcx, rbx; lpFileName
0x18002a5bf  call    cs:__imp_SetFileAttributesW
0x18002a5c5  test    eax, eax
0x18002a5c7  jnz     short loc_18002A604
0x18002a5c9  mov     rax, cs:WPP_GLOBAL_Control
0x18002a5d0  cmp     rax, rbp
0x18002a5d3  jz      short loc_18002A604
0x18002a5d5  test    byte ptr [rax+1Ch], 2
0x18002a5d9  jz      short loc_18002A604
0x18002a5db  call    cs:__imp_GetLastError
0x18002a5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5e8  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18002a5ef  mov     edx, 2Eh ; '.'
0x18002a5f4  mov     dword ptr [rsp+68h+ReturnLength], eax
0x18002a5f8  mov     r9, rsi
0x18002a5fb  mov     rcx, [rcx+10h]
0x18002a5ff  call    WPP_SF_Sd
0x18002a604  test    r12d, r12d
0x18002a607  jg      short loc_18002A630
0x18002a609  jmp     short loc_18002A63B
0x18002a60b  cmp     rcx, rdx
0x18002a60e  jz      short loc_18002A62B
0x18002a610  test    byte ptr [rcx+1Ch], 4
0x18002a614  jz      short loc_18002A62B
0x18002a616  mov     rcx, [rcx+10h]
  ... truncated ...
```

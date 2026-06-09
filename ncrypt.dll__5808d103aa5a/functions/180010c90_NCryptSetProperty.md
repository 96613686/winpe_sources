# NCryptSetProperty

- ea: `0x180010c90`
- end: `0x180011303`
- name: `NCryptSetProperty`
- size: `1651`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, PBYTE pbInput, DWORD cbInput, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000a650`
- `0x18000a670`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x180010c90`
- `0x180011cb0`
- `0x180011d30`
- `0x180015c4c`
- `0x18001f145`
- `0x18001f151`
- `0x18001f18d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001101b`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001101b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180010f12`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180010f12`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010db9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010efa`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010db9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180010efa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180010f38`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180010f38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011025`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180010e59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180010e59`

## string_xrefs

- `0x180010d56`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010ddc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010e94`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011086`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001114f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001118b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010d9f`: `Security Descr`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptSetProperty(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        PBYTE pbInput,
        DWORD cbInput,
        DWORD dwFlags)
{
  _QWORD *v6; // r13
  __int64 *v7; // r14
  _DWORD *v9; // r15
  __int16 v11; // dx
  __int64 v12; // rsi
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  _DWORD *v16; // r12
  __int64 v17; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // rcx
  signed int LastError; // eax
  unsigned int v24; // eax
  int v25; // r9d
  __int64 v26; // r9
  DWORD v27; // edi
  DWORD v28; // eax
  unsigned __int64 v29; // rbx
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  void *v32; // rsp
  void *v33; // rsp
  __int64 *v34; // rax
  int v35; // edx
  int v36; // r8d
  unsigned int v38; // eax
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r9
  __int64 v43; // rcx
  unsigned int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // [rsp+0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+40h] [rbp+0h] BYREF
  __int64 v49; // [rsp+48h] [rbp+8h] BYREF
  WORD pControl[2]; // [rsp+50h] [rbp+10h] BYREF
  DWORD dwBufferLength; // [rsp+54h] [rbp+14h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+58h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+5Ch] [rbp+1Ch] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR v55; // [rsp+68h] [rbp+28h]
  NCRYPT_HANDLE v56; // [rsp+70h] [rbp+30h]

  v55 = pszProperty;
  v56 = hObject;
  v6 = 0;
  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  v7 = 0;
  dwBufferLength = 0;
  v49 = 0;
  v9 = pbInput;
  *(_DWORD *)pControl = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, (_DWORD)pbInput, hObject, (__int64)pszProperty, dwFlags);
  v48 = ValidateAndReferenceProvider(hObject);
  v12 = v48;
  if ( !v48 )
  {
    v6 = (_QWORD *)ValidateClientKeyHandle();
    if ( !v6 )
    {
      v13 = -2146893786;
      v14 = 1754;
      v15 = 2148073510LL;
LABEL_7:
      DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v14);
      v16 = 0;
      goto LABEL_66;
    }
  }
  if ( !pszProperty )
  {
    v14 = 1762;
LABEL_10:
    v13 = -2146893785;
    v15 = 2148073511LL;
    goto LABEL_7;
  }
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( pszProperty[v18] != v11 );
  if ( v18 > 0x40 )
  {
    v14 = 1768;
    goto LABEL_10;
  }
  if ( !wcscmp_0(pszProperty, L"Security Descr") )
  {
    if ( !IsValidSecurityDescriptor(v9) )
    {
      v19 = 1782;
LABEL_18:
      v13 = -2146893819;
      v20 = 2148073477LL;
LABEL_19:
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v19);
      v16 = 0;
      goto LABEL_20;
    }
    if ( v6 )
    {
      v21 = v6[1];
      if ( v21 )
      {
        v22 = *(_WORD **)(v21 + 280);
        do
          ++v17;
        while ( v22[v17] );
        if ( 2 * v17 == 78 && !memcmp_0(v22, L"Microsoft Software Key Storage Provider", 0x50u) )
        {
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                 v9,
                 1u,
                 0xFu,
                 &StringSecurityDescriptor,
                 &StringSecurityDescriptorLen) )
          {
            v9 = StringSecurityDescriptor;
            cbInput = 2 * StringSecurityDescriptorLen + 2;
            goto LABEL_32;
          }
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
          v19 = 1809;
          v20 = v13;
          goto LABEL_19;
        }
      }
    }
    pControl[0] = 0;
    dwRevision = 0;
    if ( !IsValidSecurityDescriptor(v9) )
    {
      v19 = 1827;
      goto LABEL_18;
    }
    dwBufferLength = GetSecurityDescriptorLength(v9);
    v27 = dwBufferLength;
    if ( cbInput < dwBufferLength )
    {
      v19 = 1837;
      goto LABEL_18;
    }
    if ( !GetSecurityDescriptorControl(v9, pControl, &dwRevision) )
    {
      v28 = GetLastError();
      v19 = 1846;
LABEL_41:
      v13 = v28;
      v20 = v28;
      goto LABEL_19;
    }
    if ( (pControl[0] & 0x8000u) == 0 )
    {
      v29 = dwBufferLength;
      if ( !dwBufferLength
        || dwBufferLength > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)dwBufferLength + g_ulAdditionalProbeSize + 8 < dwBufferLength
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_107;
      }
      v30 = v29 + 23;
      if ( v29 + 23 <= v29 + 8 )
        v30 = 0xFFFFFFFFFFFFFF0LL;
      v31 = v30 & 0xFFFFFFFFFFFFFFF0uLL;
      v32 = alloca(v31);
      v33 = alloca(v31);
      v7 = &v48;
      if ( &v47 == (__int64 *)-64LL || (LODWORD(v48) = 1801679955, (v7 = &v49) == 0) )
      {
LABEL_107:
        if ( v29 + 8 >= v29 )
        {
          v34 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
          v7 = v34;
          if ( v34 )
          {
            *(_DWORD *)v34 = 1885431112;
            v7 = v34 + 1;
          }
        }
      }
      if ( !v7 )
      {
        v13 = -2146893810;
        v19 = 1856;
        v20 = 2148073486LL;
        goto LABEL_19;
      }
      if ( !MakeSelfRelativeSD(v9, v7, &dwBufferLength) )
      {
        v28 = GetLastError();
        v19 = 1864;
        goto LABEL_41;
      }
      v9 = v7;
    }
    cbInput = v27;
    goto LABEL_32;
  }
  if ( wcscmp_0(pszProperty, L"UI Policy") )
    goto LABEL_32;
  if ( cbInput < 0x20 )
  {
    v13 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v35,
        v36,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        93);
      v12 = v48;
    }
    goto LABEL_65;
  }
  if ( *v9 != 1 )
  {
    v13 = -2146893785;
    v39 = 1928;
    v40 = 2148073511LL;
    goto LABEL_79;
  }
  v38 = NCryptSerializeUIPolicy(v9, 0, 0, pControl);
  v13 = v38;
  if ( v38 )
  {
    v39 = 1903;
    v40 = v38;
LABEL_79:
    DebugTraceError(v40, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v39);
LABEL_65:
    v16 = 0;
    goto LABEL_66;
  }
  v41 = SafeAllocaAllocateFromHeap(*(unsigned int *)pControl);
  v49 = v41;
  v16 = (_DWORD *)v41;
  if ( !v41 )
  {
    v13 = -2146893810;
    v42 = 1911;
    v43 = 2148073486LL;
LABEL_82:
    DebugTraceError(v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v42);
    goto LABEL_66;
  }
  v44 = NCryptSerializeUIPolicy(v9, v41, *(unsigned int *)pControl, pControl);
  v13 = v44;
  if ( v44 )
  {
    v42 = 1921;
    v43 = v44;
    goto LABEL_82;
  }
  v9 = v16;
  cbInput = *(_DWORD *)pControl;
  while ( 1 )
  {
LABEL_32:
    if ( v6 )
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPCWSTR, _DWORD *, DWORD, DWORD))(v6[1] + 72LL))(
              *(_QWORD *)(v6[1] + 272LL),
              v6[2],
              v55,
              v9,
              cbInput,
              dwFlags);
      v13 = v24;
      if ( !v24 )
        goto LABEL_90;
      v26 = 1949;
    }
    else
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, _DWORD *, _QWORD, DWORD))(v48 + 64))(
              *(_QWORD *)(v48 + 272),
              v55,
              v9,
              cbInput,
              dwFlags);
      v13 = v24;
      if ( !v24 )
        goto LABEL_90;
      v26 = 1962;
    }
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v26);
LABEL_90:
    if ( v13 != -2146893778 )
      break;
    if ( (dwFlags & 0x40) != 0 )
    {
      v13 = -2146893790;
      DebugTraceError(
        2148073506LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        1975);
      goto LABEL_99;
    }
    if ( v6 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_HANDLE, const wchar_t *, _QWORD))(v6[1] + 192LL))(
              *(_QWORD *)(v6[1] + 272LL),
              v56,
              L"NCryptSetProperty",
              0);
      if ( v13 )
      {
        v45 = 1988;
LABEL_97:
        DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v45);
        goto LABEL_101;
      }
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v48 + 192))(
              *(_QWORD *)(v48 + 272),
              0,
              L"NCryptSetProperty",
              0);
      if ( v13 )
      {
        v45 = 2000;
        goto LABEL_97;
      }
    }
  }
  if ( !v13 )
  {
    v13 = 0;
    goto LABEL_99;
  }
LABEL_101:
  if ( v6 )
  {
    v46 = v6[1];
    if ( v46 )
      EtwLogNCryptOperationFailed(17, *(_QWORD *)(v46 + 280), v6[3], v25, v13);
  }
LABEL_99:
  v16 = (_DWORD *)v49;
LABEL_20:
  v12 = v48;
LABEL_66:
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v16 )
    MSCryptFree(v16);
  if ( v12 )
    DereferenceProvider(v12);
  return NormalizeNteStatus(v13);
}

```

## disassembly

```asm
0x180010c90  push    rbp
0x180010c92  push    rbx
0x180010c93  push    rsi
0x180010c94  push    rdi
0x180010c95  push    r12
0x180010c97  push    r13
0x180010c99  push    r14
0x180010c9b  push    r15
0x180010c9d  sub     rsp, 98h
0x180010ca4  lea     rbp, [rsp+40h]
0x180010ca9  mov     rax, cs:__security_cookie
0x180010cb0  xor     rax, rbp
0x180010cb3  mov     [rbp+90h+var_50], rax
0x180010cb7  mov     rdi, rdx
0x180010cba  mov     [rbp+90h+var_68], rdx
0x180010cbe  xor     edx, edx
0x180010cc0  mov     [rbp+90h+var_60], rcx
0x180010cc4  mov     r13d, edx
0x180010cc7  mov     [rbp+90h+StringSecurityDescriptor], rdx
0x180010ccb  mov     [rbp+90h+var_78], edx
0x180010cce  mov     r14d, edx
0x180010cd1  mov     [rbp+90h+dwBufferLength], edx
0x180010cd4  mov     r12d, r9d
0x180010cd7  mov     [rbp+90h+var_88], rdx
0x180010cdb  mov     r15, r8
0x180010cde  mov     dword ptr [rbp+90h+pControl], edx
0x180010ce1  mov     rbx, rcx
0x180010ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ceb  lea     rax, WPP_GLOBAL_Control
0x180010cf2  cmp     rcx, rax
0x180010cf5  jz      short loc_180010D1E
0x180010cf7  test    byte ptr [rcx+1Ch], 4
0x180010cfb  jz      short loc_180010D1E
0x180010cfd  mov     eax, [rbp+90h+dwFlags]
0x180010d03  lea     edx, [r14+11h]
0x180010d07  mov     rcx, [rcx+10h]
0x180010d0b  mov     r9, rbx
0x180010d0e  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180010d12  mov     [rsp+0D0h+StringSecurityDescriptorLen], rdi
0x180010d17  call    WPP_SF_PSD
0x180010d1c  xor     edx, edx
0x180010d1e  mov     rcx, rbx
0x180010d21  call    ValidateAndReferenceProvider
0x180010d26  mov     [rbp+90h+var_90], rax
0x180010d2a  mov     rsi, rax
0x180010d2d  test    rax, rax
0x180010d30  jnz     short loc_180010D6A
0x180010d32  call    ValidateClientKeyHandle
0x180010d37  mov     r13, rax
0x180010d3a  test    rax, rax
0x180010d3d  jnz     short loc_180010D6A
0x180010d3f  mov     ebx, 80090026h
0x180010d44  mov     r9d, 6DAh
0x180010d4a  mov     ecx, 80090026h
0x180010d4f  lea     rdx, aStatus; "Status"
0x180010d56  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d5d  call    DebugTraceError
0x180010d62  mov     r12, r14
0x180010d65  jmp     loc_1800110B5
0x180010d6a  test    rdi, rdi
0x180010d6d  jnz     short loc_180010D81
0x180010d6f  mov     r9d, 6E2h
0x180010d75  mov     ebx, 80090027h
0x180010d7a  mov     ecx, 80090027h
0x180010d7f  jmp     short loc_180010D4F
0x180010d81  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010d85  mov     rax, rbx
0x180010d88  inc     rax
0x180010d8b  cmp     [rdi+rax*2], dx
0x180010d8f  jnz     short loc_180010D88
0x180010d91  cmp     rax, 40h ; '@'
0x180010d95  jbe     short loc_180010D9F
0x180010d97  mov     r9d, 6E8h
0x180010d9d  jmp     short loc_180010D75
0x180010d9f  lea     rdx, aSecurityDescr; "Security Descr"
0x180010da6  mov     rcx, rdi; String1
0x180010da9  call    wcscmp_0
0x180010dae  test    eax, eax
0x180010db0  jnz     loc_180011041
0x180010db6  mov     rcx, r15; pSecurityDescriptor
0x180010db9  call    cs:__imp_IsValidSecurityDescriptor
0x180010dbf  xor     esi, esi
0x180010dc1  test    eax, eax
0x180010dc3  jnz     short loc_180010DF4
0x180010dc5  mov     r9d, 6F6h
0x180010dcb  mov     ebx, 80090005h
0x180010dd0  mov     ecx, 80090005h
0x180010dd5  lea     rdx, aStatus; "Status"
0x180010ddc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010de3  call    DebugTraceError
0x180010de8  mov     r12, rsi
0x180010deb  mov     rsi, [rbp+90h+var_90]
0x180010def  jmp     loc_1800110B5
0x180010df4  test    r13, r13
0x180010df7  jz      loc_180010EF0
0x180010dfd  mov     rax, [r13+8]
0x180010e01  test    rax, rax
0x180010e04  jz      loc_180010EF0
0x180010e0a  mov     rcx, [rax+118h]; Buf1
0x180010e11  inc     rbx
0x180010e14  cmp     [rcx+rbx*2], si
0x180010e18  jnz     short loc_180010E11
0x180010e1a  lea     rax, [rbx+rbx]
0x180010e1e  cmp     rax, 4Eh ; 'N'
0x180010e22  jnz     loc_180010EF0
0x180010e28  lea     r8d, [rax+2]; Size
0x180010e2c  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180010e33  call    memcmp_0
0x180010e38  test    eax, eax
0x180010e3a  jnz     loc_180010EF0
0x180010e40  mov     edx, 1; RequestedStringSDRevision
0x180010e45  lea     rax, [rbp+90h+var_78]
0x180010e49  lea     r9, [rbp+90h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180010e4d  mov     [rsp+0D0h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x180010e52  mov     rcx, r15; SecurityDescriptor
0x180010e55  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180010e59  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180010e5f  test    eax, eax
0x180010e61  jnz     short loc_180010E85
0x180010e63  call    cs:__imp_GetLastError
0x180010e69  mov     ebx, eax
0x180010e6b  test    eax, eax
0x180010e6d  jle     short loc_180010E78
0x180010e6f  movzx   ebx, ax
0x180010e72  or      ebx, 80070000h
0x180010e78  mov     r9d, 711h
0x180010e7e  mov     ecx, ebx
0x180010e80  jmp     loc_180010DD5
0x180010e85  mov     eax, [rbp+90h+var_78]
0x180010e88  mov     r15, [rbp+90h+StringSecurityDescriptor]
0x180010e8c  lea     r12d, ds:2[rax*2]
0x180010e94  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e9b  lea     rdi, aStatus; "Status"
0x180010ea2  test    r13, r13
0x180010ea5  jz      loc_1800111E0
0x180010eab  mov     rcx, [r13+8]
0x180010eaf  mov     r9, r15
0x180010eb2  mov     edx, [rbp+90h+dwFlags]
0x180010eb8  mov     r8, [rbp+90h+var_68]
0x180010ebc  mov     dword ptr [rsp+0D0h+var_A8], edx
0x180010ec0  mov     rax, [rcx+48h]
0x180010ec4  mov     rcx, [rcx+110h]
0x180010ecb  mov     rdx, [r13+10h]
0x180010ecf  mov     dword ptr [rsp+0D0h+StringSecurityDescriptorLen], r12d
0x180010ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed9  xor     ecx, ecx
0x180010edb  mov     ebx, eax
0x180010edd  test    eax, eax
0x180010edf  jz      loc_180011225
0x180010ee5  mov     r9d, 79Dh
0x180010eeb  jmp     loc_180011216
0x180010ef0  mov     rcx, r15; pSecurityDescriptor
0x180010ef3  mov     [rbp+90h+pControl], si
0x180010ef7  mov     [rbp+90h+dwRevision], esi
0x180010efa  call    cs:__imp_IsValidSecurityDescriptor
0x180010f00  test    eax, eax
0x180010f02  jnz     short loc_180010F0F
0x180010f04  mov     r9d, 723h
0x180010f0a  jmp     loc_180010DCB
0x180010f0f  mov     rcx, r15; pSecurityDescriptor
0x180010f12  call    cs:__imp_GetSecurityDescriptorLength
0x180010f18  mov     [rbp+90h+dwBufferLength], eax
0x180010f1b  mov     edi, eax
0x180010f1d  cmp     r12d, eax
0x180010f20  jnb     short loc_180010F2D
0x180010f22  mov     r9d, 72Dh
0x180010f28  jmp     loc_180010DCB
0x180010f2d  lea     r8, [rbp+90h+dwRevision]; lpdwRevision
0x180010f31  mov     rcx, r15; pSecurityDescriptor
0x180010f34  lea     rdx, [rbp+90h+pControl]; pControl
0x180010f38  call    cs:__imp_GetSecurityDescriptorControl
0x180010f3e  test    eax, eax
0x180010f40  jnz     short loc_180010F57
0x180010f42  call    cs:__imp_GetLastError
0x180010f48  mov     r9d, 736h
0x180010f4e  mov     ebx, eax
0x180010f50  mov     ecx, eax
0x180010f52  jmp     loc_180010DD5
0x180010f57  mov     eax, 8000h
0x180010f5c  test    [rbp+90h+pControl], ax
0x180010f60  jnz     loc_180011039
0x180010f66  mov     ebx, [rbp+90h+dwBufferLength]
0x180010f69  test    rbx, rbx
0x180010f6c  jz      short loc_180010FD0
0x180010f6e  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180010f75  ja      short loc_180010FD0
0x180010f77  mov     rcx, cs:g_ulAdditionalProbeSize
0x180010f7e  add     rcx, 8
0x180010f82  add     rcx, rbx
0x180010f85  cmp     rcx, rbx
0x180010f88  jb      short loc_180010FD0
0x180010f8a  call    VerifyStackAvailable
0x180010f8f  test    eax, eax
0x180010f91  jz      short loc_180010FD0
0x180010f93  lea     rax, [rbx+8]
0x180010f97  lea     rcx, [rax+0Fh]
0x180010f9b  cmp     rcx, rax
0x180010f9e  ja      short loc_180010FAA
0x180010fa0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180010faa  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180010fae  mov     rax, rcx
0x180010fb1  call    __chkstk_0
0x180010fb6  sub     rsp, rcx
0x180010fb9  lea     r14, [rsp+0D0h+var_90]
0x180010fbe  test    r14, r14
0x180010fc1  jz      short loc_180010FD0
0x180010fc3  mov     dword ptr [r14], 6B637453h
0x180010fca  add     r14, 8
0x180010fce  jnz     short loc_180010FF7
0x180010fd0  lea     rcx, [rbx+8]
0x180010fd4  cmp     rcx, rbx
0x180010fd7  jb      short loc_180010FF7
0x180010fd9  mov     rax, cs:g_pfnAllocate
0x180010fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe5  mov     r14, rax
0x180010fe8  test    rax, rax
0x180010feb  jz      short loc_180010FF7
0x180010fed  mov     dword ptr [rax], 70616548h
0x180010ff3  add     r14, 8
0x180010ff7  test    r14, r14
0x180010ffa  jnz     short loc_180011011
0x180010ffc  mov     ebx, 8009000Eh
0x180011001  mov     r9d, 740h
0x180011007  mov     ecx, 8009000Eh
0x18001100c  jmp     loc_180010DD5
0x180011011  lea     r8, [rbp+90h+dwBufferLength]; lpdwBufferLength
0x180011015  mov     rdx, r14; pSelfRelativeSecurityDescriptor
0x180011018  mov     rcx, r15; pAbsoluteSecurityDescriptor
0x18001101b  call    cs:__imp_MakeSelfRelativeSD
0x180011021  test    eax, eax
0x180011023  jnz     short loc_180011036
0x180011025  call    cs:__imp_GetLastError
0x18001102b  mov     r9d, 748h
0x180011031  jmp     loc_180010F4E
0x180011036  mov     r15, r14
0x180011039  mov     r12d, edi
0x18001103c  jmp     loc_180010E94
0x180011041  lea     rdx, aUiPolicy; "UI Policy"
0x180011048  mov     rcx, rdi; String1
0x18001104b  call    wcscmp_0
0x180011050  xor     edi, edi
0x180011052  test    eax, eax
0x180011054  jnz     loc_180010E94
0x18001105a  cmp     r12d, 20h ; ' '
0x18001105e  jnb     loc_18001111F
0x180011064  mov     ebx, 80090027h
0x180011069  mov     rcx, cs:WPP_GLOBAL_Control
0x180011070  lea     rax, WPP_GLOBAL_Control
0x180011077  cmp     rcx, rax
0x18001107a  jz      short loc_1800110B2
0x18001107c  test    byte ptr [rcx+1Ch], 1
0x180011080  jz      short loc_1800110B2
0x180011082  mov     rcx, [rcx+10h]
0x180011086  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001108d  mov     [rsp+0D0h+var_A0], 75Dh
0x180011095  lea     r9, aStatus; "Status"
0x18001109c  mov     [rsp+0D0h+var_A8], rsi
0x1800110a1  mov     dword ptr [rsp+0D0h+StringSecurityDescriptorLen], 80090027h
0x1800110a9  call    WPP_SF_sDsd
0x1800110ae  mov     rsi, [rbp+90h+var_90]
0x1800110b2  mov     r12, rdi
0x1800110b5  mov     rcx, [rbp+90h+StringSecurityDescriptor]; hMem
0x1800110b9  test    rcx, rcx
0x1800110bc  jz      short loc_1800110C4
0x1800110be  call    cs:__imp_LocalFree
0x1800110c4  test    r14, r14
0x1800110c7  jz      short loc_1800110E1
0x1800110c9  lea     rcx, [r14-8]
0x1800110cd  cmp     dword ptr [rcx], 70616548h
0x1800110d3  jnz     short loc_1800110E1
0x1800110d5  mov     rax, cs:g_pfnFree
0x1800110dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e1  test    r12, r12
0x1800110e4  jz      short loc_1800110EE
0x1800110e6  mov     rcx, r12
0x1800110e9  call    MSCryptFree
0x1800110ee  test    rsi, rsi
0x1800110f1  jz      short loc_1800110FB
0x1800110f3  mov     rcx, rsi
0x1800110f6  call    DereferenceProvider
0x1800110fb  mov     ecx, ebx
0x1800110fd  call    NormalizeNteStatus
0x180011102  mov     rcx, [rbp+90h+var_50]
0x180011106  xor     rcx, rbp; StackCookie
0x180011109  call    __security_check_cookie
0x18001110e  lea     rsp, [rbp+58h]
0x180011112  pop     r15
0x180011114  pop     r14
0x180011116  pop     r13
0x180011118  pop     r12
0x18001111a  pop     rdi
0x18001111b  pop     rsi
0x18001111c  pop     rbx
0x18001111d  pop     rbp
0x18001111e  retn
0x18001111f  cmp     dword ptr [r15], 1
0x180011123  jnz     loc_1800111CB
0x180011129  lea     r9, [rbp+90h+pControl]
0x18001112d  xor     r8d, r8d
0x180011130  xor     edx, edx
  ... truncated ...
```

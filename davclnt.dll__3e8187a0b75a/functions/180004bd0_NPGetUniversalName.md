# NPGetUniversalName

- ea: `0x180004bd0`
- end: `0x180005199`
- name: `NPGetUniversalName`
- size: `1481`
- prototype: `DWORD __stdcall(LPCWSTR lpLocalPath, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path`

## callees

- `0x1800033f0`
- `0x1800036d0`
- `0x180004bd0`
- `0x180006500`
- `0x180009c00`
- `0x180010a14`
- `0x180010be8`
- `0x180010c88`
- `0x180010d00`
- `0x18001104c`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005084`
- `KERNEL32!LocalAlloc` at `0x180004f75`
- `KERNEL32!LocalAlloc` at `0x180005076`
- `KERNEL32!LocalAlloc` at `0x180004f75`
- `KERNEL32!LocalAlloc` at `0x180005076`
- `KERNEL32!LocalFree` at `0x1800050eb`
- `KERNEL32!LocalFree` at `0x1800050eb`
- `netutils!NetpwPathCanonicalize` at `0x180004d75`
- `netutils!NetpwPathCanonicalize` at `0x180004d75`

## pseudocode

```c
DWORD __stdcall NPGetUniversalName(LPCWSTR lpLocalPath, DWORD dwInfoLevel, LPVOID lpBuffer, LPDWORD lpBufferSize)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  void *v10; // rcx
  DWORD v11; // eax
  DWORD LastError; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r12
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdi
  bool v20; // zf
  DWORD v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  DWORD v24; // r8d
  int v25; // r12d
  int v26; // eax
  __int64 v27; // rbx
  DWORD v28; // r15d
  wchar_t *v29; // r15
  DWORD v30; // edi
  wchar_t *v31; // rax
  wchar_t *v32; // rdi
  unsigned int v33; // r10d
  wchar_t *v34; // rbx
  unsigned int v35; // r10d
  size_t v36; // rdx
  wchar_t *v37; // r10
  wchar_t *v38; // r15
  wchar_t *v39; // rax
  DWORD nBufferLen; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR LocalName; // [rsp+48h] [rbp-B8h] BYREF
  int v44; // [rsp+4Ah] [rbp-B6h]
  WCHAR v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v46; // [rsp+52h] [rbp-AEh] BYREF
  wchar_t pszSrc[262]; // [rsp+54h] [rbp-ACh] BYREF

  nBufferLen = 0;
  LocalName = 0;
  v45 = 0;
  v44 = 0;
  memset_0(&v46, 0, 0x208u);
  v42 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    LOBYTE(v11) = -1;
    if ( lpBufferSize )
      v11 = *lpBufferSize;
    WPP_SF_Sdqqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      (_DWORD)lpLocalPath,
      dwInfoLevel,
      (char)lpBuffer,
      (char)lpBufferSize,
      v11);
  }
  if ( !(unsigned int)DavWorkstationStarted((__int64)v10, v8, v9) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    return 1222;
  }
  if ( dwInfoLevel - 1 > 1 )
  {
    LastError = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v14 = 187;
    goto LABEL_83;
  }
  if ( !lpLocalPath || !lpBufferSize || !lpBuffer && *lpBufferSize )
  {
    LastError = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v14 = 188;
LABEL_83:
    WPP_SF_(v13[2], v14, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    return LastError;
  }
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( lpLocalPath[v16] );
  v17 = v16 + 1;
  if ( v17 < 3 || lpLocalPath[1] != 58 || v17 > 3 && lpLocalPath[2] != 92 )
  {
    LastError = 1200;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v14 = 189;
    goto LABEL_83;
  }
  v42 = 0;
  v18 = NetpwPathCanonicalize(lpLocalPath, &v45, 522, 0, &v42, 0);
  if ( !v18 && (v42 == 0x4000 || (v42 & 0x2004) == 0x2004) )
  {
    pszSrc[258] = 0;
    v19 = -1;
    do
      v20 = *(&v45 + ++v19) == 0;
    while ( !v20 );
    LocalName = v45;
    v44 = v46;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
        (unsigned int)&v45,
        (__int64)&LocalName);
    nBufferLen = *lpBufferSize >> 1;
    v21 = NPGetConnection(&LocalName, (LPWSTR)lpBuffer, &nBufferLen);
    LastError = v21;
    if ( v21 != 234 )
    {
      if ( v21 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return LastError;
        v23 = 192;
        goto LABEL_38;
      }
      do
        v20 = *((_WORD *)lpBuffer + ++v15) == 0;
      while ( !v20 );
      v24 = v15 + 1;
      nBufferLen = v15 + 1;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_44:
        v25 = v19 + 1;
        v26 = v19 + 1 + v24;
        v27 = (unsigned int)(v26 - 3);
        v28 = dwInfoLevel - 1;
        if ( v28 )
        {
          if ( v28 != 1 )
          {
            LastError = 87;
            if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
              return LastError;
            v14 = 198;
            goto LABEL_83;
          }
          v29 = 0;
          if ( lpBuffer )
            v29 = (wchar_t *)((char *)lpBuffer + 24);
          v30 = 2 * (v27 + v26) + 20;
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
          {
            WPP_SF_d(v13[2], 196, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v30);
            v24 = nBufferLen;
          }
          if ( *lpBufferSize < v30 )
          {
LABEL_55:
            *lpBufferSize = v30;
            return 234;
          }
          v31 = (wchar_t *)LocalAlloc(0x40u, 2LL * v24);
          v32 = v31;
          if ( !v31 )
          {
            LastError = GetLastError();
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return LastError;
            v23 = 197;
            goto LABEL_38;
          }
          StringCchCopyW(v31, nBufferLen, (STRSAFE_LPCWSTR)lpBuffer);
          *((_QWORD *)lpBuffer + 1) = 0;
          v33 = v27;
          *((_QWORD *)lpBuffer + 2) = 0;
          v34 = &v29[v27];
          *(_QWORD *)lpBuffer = v29;
          StringCchCopyW(v29, v33, v32);
          StringCchCatW(*(STRSAFE_LPWSTR *)lpBuffer, v35, pszSrc);
          v36 = nBufferLen;
          *((_QWORD *)lpBuffer + 1) = v34;
          StringCchCopyW(v34, v36, v32);
          *((_QWORD *)lpBuffer + 2) = v37;
          StringCchCopyW(v37, (unsigned int)(v25 - 2), pszSrc);
        }
        else
        {
          v38 = 0;
          if ( lpBuffer )
            v38 = (wchar_t *)((char *)lpBuffer + 8);
          v30 = 2 * v27 + 8;
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
          {
            WPP_SF_d(v13[2], 194, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v30);
            v24 = nBufferLen;
          }
          if ( *lpBufferSize < v30 )
            goto LABEL_55;
          v39 = (wchar_t *)LocalAlloc(0x40u, 2LL * v24);
          v32 = v39;
          if ( !v39 )
          {
            LastError = GetLastError();
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return LastError;
            v23 = 195;
LABEL_38:
            WPP_SF_d(v22[2], v23, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
            return LastError;
          }
          StringCchCopyW(v39, nBufferLen, (STRSAFE_LPCWSTR)lpBuffer);
          *(_QWORD *)lpBuffer = v38;
          StringCchCopyW(v38, (unsigned int)v27, v32);
          StringCchCatW(*(STRSAFE_LPWSTR *)lpBuffer, (unsigned int)v27, pszSrc);
        }
        LastError = 0;
        LocalFree(v32);
        return LastError;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
        (_DWORD)lpBuffer,
        v24);
    }
    v13 = WPP_GLOBAL_Control;
    v24 = nBufferLen;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v18);
  return 1200;
}

```

## disassembly

```asm
0x180004bd0  push    rbp
0x180004bd2  push    rbx
0x180004bd3  push    rsi
0x180004bd4  push    rdi
0x180004bd5  push    r13
0x180004bd7  push    r14
0x180004bd9  push    r15
0x180004bdb  lea     rbp, [rsp-170h]
0x180004be3  sub     rsp, 270h
0x180004bea  mov     rax, cs:__security_cookie
0x180004bf1  xor     rax, rsp
0x180004bf4  mov     [rbp+1A0h+var_40], rax
0x180004bfb  xor     r13d, r13d
0x180004bfe  mov     rsi, r8
0x180004c01  mov     r15d, edx
0x180004c04  mov     [rsp+2A0h+nBufferLen], r13d
0x180004c09  mov     rbx, rcx
0x180004c0c  mov     [rsp+2A0h+LocalName], r13w
0x180004c12  xor     eax, eax
0x180004c14  mov     [rsp+2A0h+var_250], r13w
0x180004c1a  xor     edx, edx; Val
0x180004c1c  mov     [rsp+2A0h+var_256], eax
0x180004c20  mov     r8d, 208h; Size
0x180004c26  lea     rcx, [rsp+2A0h+var_24E]; void *
0x180004c2b  mov     r14, r9
0x180004c2e  call    memset_0
0x180004c33  mov     [rsp+2A0h+var_25C], r13d
0x180004c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c3f  lea     rdi, WPP_GLOBAL_Control
0x180004c46  cmp     rcx, rdi
0x180004c49  jz      short loc_180004C7D
0x180004c4b  test    byte ptr [rcx+1Ch], 20h
0x180004c4f  jz      short loc_180004C7D
0x180004c51  mov     eax, 0FFFFFFFFh
0x180004c56  test    r14, r14
0x180004c59  jz      short loc_180004C5E
0x180004c5b  mov     eax, [r14]
0x180004c5e  mov     rcx, [rcx+10h]
0x180004c62  mov     r9, rbx
0x180004c65  mov     [rsp+2A0h+var_268], eax
0x180004c69  mov     [rsp+2A0h+var_270], r14
0x180004c6e  mov     [rsp+2A0h+var_278], rsi
0x180004c73  mov     dword ptr [rsp+2A0h+var_280], r15d
0x180004c78  call    WPP_SF_Sdqqd
0x180004c7d  mov     [rsp+2A0h+arg_8], r12
0x180004c85  call    DavWorkstationStarted
0x180004c8a  test    eax, eax
0x180004c8c  jnz     short loc_180004CBF
0x180004c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c95  cmp     rcx, rdi
0x180004c98  jz      short loc_180004CB5
0x180004c9a  test    byte ptr [rcx+1Ch], 1
0x180004c9e  jz      short loc_180004CB5
0x180004ca0  mov     rcx, [rcx+10h]
0x180004ca4  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180004cab  mov     edx, 0BAh
0x180004cb0  call    WPP_SF_
0x180004cb5  mov     ebx, 4C6h
0x180004cba  jmp     loc_18000516E
0x180004cbf  lea     eax, [r15-1]
0x180004cc3  cmp     eax, 1
0x180004cc6  jbe     short loc_180004CF1
0x180004cc8  mov     ebx, 57h ; 'W'
0x180004ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cd4  cmp     rcx, rdi
0x180004cd7  jz      loc_18000516E
0x180004cdd  test    byte ptr [rcx+1Ch], 1
0x180004ce1  jz      loc_18000516E
0x180004ce7  mov     edx, 0BBh
0x180004cec  jmp     loc_18000515E
0x180004cf1  test    rbx, rbx
0x180004cf4  jz      loc_180005142
0x180004cfa  test    r14, r14
0x180004cfd  jz      loc_180005142
0x180004d03  test    rsi, rsi
0x180004d06  jnz     short loc_180004D11
0x180004d08  cmp     [r14], r13d
0x180004d0b  jnz     loc_180005142
0x180004d11  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180004d18  mov     rax, r12
0x180004d1b  nop     dword ptr [rax+rax+00h]
0x180004d20  inc     rax
0x180004d23  cmp     [rbx+rax*2], r13w
0x180004d28  jnz     short loc_180004D20
0x180004d2a  inc     eax
0x180004d2c  cmp     eax, 3
0x180004d2f  jb      loc_180005124
0x180004d35  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180004d3a  jnz     loc_180005124
0x180004d40  cmp     eax, 3
0x180004d43  jbe     short loc_180004D50
0x180004d45  cmp     word ptr [rbx+4], 5Ch ; '\'
0x180004d4a  jnz     loc_180005124
0x180004d50  lea     rax, [rsp+2A0h+var_25C]
0x180004d55  mov     dword ptr [rsp+2A0h+var_278], r13d
0x180004d5a  xor     r9d, r9d
0x180004d5d  mov     [rsp+2A0h+var_280], rax
0x180004d62  mov     r8d, 20Ah
0x180004d68  mov     [rsp+2A0h+var_25C], r13d
0x180004d6d  lea     rdx, [rsp+2A0h+var_250]
0x180004d72  mov     rcx, rbx
0x180004d75  call    cs:__imp_NetpwPathCanonicalize
0x180004d7b  test    eax, eax
0x180004d7d  jnz     loc_1800050F3
0x180004d83  mov     ecx, [rsp+2A0h+var_25C]
0x180004d87  cmp     ecx, 4000h
0x180004d8d  jz      short loc_180004DA1
0x180004d8f  and     ecx, 2004h
0x180004d95  cmp     ecx, 2004h
0x180004d9b  jnz     loc_1800050F3
0x180004da1  mov     [rbp+1A0h+var_48], r13w
0x180004da9  lea     rax, [rsp+2A0h+var_250]
0x180004dae  mov     rdi, r12
0x180004db1  cmp     [rax+rdi*2+2], r13w
0x180004db7  lea     rdi, [rdi+1]
0x180004dbb  jnz     short loc_180004DB1
0x180004dbd  movzx   eax, [rsp+2A0h+var_250]
0x180004dc2  mov     [rsp+2A0h+LocalName], ax
0x180004dc7  movzx   eax, [rsp+2A0h+var_24E]
0x180004dcc  mov     word ptr [rsp+2A0h+var_256], ax
0x180004dd1  mov     word ptr [rsp+2A0h+var_256+2], r13w
0x180004dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dde  lea     rax, WPP_GLOBAL_Control
0x180004de5  cmp     rcx, rax
0x180004de8  jz      short loc_180004E14
0x180004dea  test    byte ptr [rcx+1Ch], 2
0x180004dee  jz      short loc_180004E14
0x180004df0  mov     rcx, [rcx+10h]
0x180004df4  lea     rax, [rsp+2A0h+LocalName]
0x180004df9  mov     edx, 0BFh
0x180004dfe  mov     [rsp+2A0h+var_280], rax
0x180004e03  lea     r9, [rsp+2A0h+var_250]
0x180004e08  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180004e0f  call    WPP_SF_SS
0x180004e14  mov     eax, [r14]
0x180004e17  lea     r8, [rsp+2A0h+nBufferLen]; lpnBufferLen
0x180004e1c  shr     eax, 1
0x180004e1e  lea     rcx, [rsp+2A0h+LocalName]; lpLocalName
0x180004e23  mov     rdx, rsi; lpRemoteName
0x180004e26  mov     [rsp+2A0h+nBufferLen], eax
0x180004e2a  call    NPGetConnection
0x180004e2f  mov     ebx, eax
0x180004e31  cmp     eax, 0EAh
0x180004e36  jz      loc_180004ECB
0x180004e3c  test    eax, eax
0x180004e3e  jz      short loc_180004E7E
0x180004e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e47  lea     rax, WPP_GLOBAL_Control
0x180004e4e  cmp     rcx, rax
0x180004e51  jz      loc_18000516E
0x180004e57  test    byte ptr [rcx+1Ch], 1
0x180004e5b  jz      loc_18000516E
0x180004e61  mov     edx, 0C0h
0x180004e66  mov     rcx, [rcx+10h]
0x180004e6a  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180004e71  mov     r9d, ebx
0x180004e74  call    WPP_SF_d
0x180004e79  jmp     loc_18000516E
0x180004e7e  cmp     [rsi+r12*2+2], r13w
0x180004e84  lea     r12, [r12+1]
0x180004e89  jnz     short loc_180004E7E
0x180004e8b  lea     r8d, [r12+1]
0x180004e90  mov     [rsp+2A0h+nBufferLen], r8d
0x180004e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e9c  lea     rdx, WPP_GLOBAL_Control
0x180004ea3  cmp     rcx, rdx
0x180004ea6  jz      short loc_180004EDE
0x180004ea8  test    byte ptr [rcx+1Ch], 2
0x180004eac  jz      short loc_180004EDE
0x180004eae  mov     rcx, [rcx+10h]
0x180004eb2  mov     edx, 0C1h
0x180004eb7  mov     dword ptr [rsp+2A0h+var_280], r8d
0x180004ebc  mov     r9, rsi
0x180004ebf  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180004ec6  call    WPP_SF_Sd
0x180004ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ed2  lea     rdx, WPP_GLOBAL_Control
0x180004ed9  mov     r8d, [rsp+2A0h+nBufferLen]
0x180004ede  lea     r12d, [rdi+1]
0x180004ee2  lea     eax, [r12+r8]
0x180004ee6  lea     ebx, [rax-3]
0x180004ee9  sub     r15d, 1
0x180004eed  jz      loc_180005027
0x180004ef3  cmp     r15d, 1
0x180004ef7  jz      short loc_180004F1B
0x180004ef9  mov     ebx, 57h ; 'W'
0x180004efe  cmp     rcx, rdx
0x180004f01  jz      loc_18000516E
0x180004f07  test    byte ptr [rcx+1Ch], 1
0x180004f0b  jz      loc_18000516E
0x180004f11  mov     edx, 0C6h
0x180004f16  jmp     loc_18000515E
0x180004f1b  mov     r15, r13
0x180004f1e  test    rsi, rsi
0x180004f21  jz      short loc_180004F27
0x180004f23  lea     r15, [rsi+18h]
0x180004f27  add     eax, ebx
0x180004f29  lea     edi, ds:14h[rax*2]
0x180004f30  cmp     rcx, rdx
0x180004f33  jz      short loc_180004F58
0x180004f35  test    byte ptr [rcx+1Ch], 2
0x180004f39  jz      short loc_180004F58
0x180004f3b  mov     rcx, [rcx+10h]
0x180004f3f  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180004f46  mov     edx, 0C4h
0x180004f4b  mov     r9d, edi
0x180004f4e  call    WPP_SF_d
0x180004f53  mov     r8d, [rsp+2A0h+nBufferLen]
0x180004f58  cmp     [r14], edi
0x180004f5b  jnb     short loc_180004F6A
0x180004f5d  mov     [r14], edi
0x180004f60  mov     ebx, 0EAh
0x180004f65  jmp     loc_18000516E
0x180004f6a  mov     edx, r8d
0x180004f6d  mov     ecx, 40h ; '@'; uFlags
0x180004f72  add     rdx, rdx; uBytes
0x180004f75  call    cs:__imp_LocalAlloc
0x180004f7b  mov     rdi, rax
0x180004f7e  test    rax, rax
0x180004f81  jnz     short loc_180004FB6
0x180004f83  call    cs:__imp_GetLastError
0x180004f89  mov     ebx, eax
0x180004f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f92  lea     rax, WPP_GLOBAL_Control
0x180004f99  cmp     rcx, rax
0x180004f9c  jz      loc_18000516E
0x180004fa2  test    byte ptr [rcx+1Ch], 1
0x180004fa6  jz      loc_18000516E
0x180004fac  mov     edx, 0C5h
0x180004fb1  jmp     loc_180004E66
0x180004fb6  mov     edx, [rsp+2A0h+nBufferLen]; cchDest
0x180004fba  mov     r8, rsi; pszSrc
0x180004fbd  mov     rcx, rdi; pszDest
0x180004fc0  call    StringCchCopyW
0x180004fc5  mov     [rsi+8], r13
0x180004fc9  mov     r8, rdi; pszSrc
0x180004fcc  mov     r10d, ebx
0x180004fcf  mov     rcx, r15; pszDest
0x180004fd2  mov     [rsi+10h], r13
0x180004fd6  lea     rbx, [r15+rbx*2]
0x180004fda  mov     edx, r10d; cchDest
0x180004fdd  mov     [rsi], r15
0x180004fe0  call    StringCchCopyW
0x180004fe5  mov     rcx, [rsi]; pszDest
0x180004fe8  lea     r8, [rsp+2A0h+pszSrc]; pszSrc
0x180004fed  mov     edx, r10d; cchDest
0x180004ff0  call    StringCchCatW
0x180004ff5  mov     edx, [rsp+2A0h+nBufferLen]; cchDest
0x180004ff9  mov     r8, rdi; pszSrc
0x180004ffc  mov     rcx, rbx; pszDest
0x180004fff  mov     [rsi+8], rbx
0x180005003  lea     r10, [rbx+rdx*2]
0x180005007  call    StringCchCopyW
0x18000500c  lea     edx, [r12-2]; cchDest
0x180005011  mov     [rsi+10h], r10
0x180005015  lea     r8, [rsp+2A0h+pszSrc]; pszSrc
0x18000501a  mov     rcx, r10; pszDest
0x18000501d  call    StringCchCopyW
0x180005022  jmp     loc_1800050E5
0x180005027  mov     r15, r13
0x18000502a  test    rsi, rsi
0x18000502d  jz      short loc_180005033
0x18000502f  lea     r15, [rsi+8]
0x180005033  lea     edi, ds:8[rbx*2]
0x18000503a  cmp     rcx, rdx
0x18000503d  jz      short loc_180005062
0x18000503f  test    byte ptr [rcx+1Ch], 2
0x180005043  jz      short loc_180005062
0x180005045  mov     rcx, [rcx+10h]
0x180005049  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180005050  mov     edx, 0C2h
0x180005055  mov     r9d, edi
0x180005058  call    WPP_SF_d
0x18000505d  mov     r8d, [rsp+2A0h+nBufferLen]
0x180005062  cmp     [r14], edi
0x180005065  jb      loc_180004F5D
0x18000506b  mov     edx, r8d
0x18000506e  mov     ecx, 40h ; '@'; uFlags
0x180005073  add     rdx, rdx; uBytes
0x180005076  call    cs:__imp_LocalAlloc
0x18000507c  mov     rdi, rax
0x18000507f  test    rax, rax
0x180005082  jnz     short loc_1800050B7
0x180005084  call    cs:__imp_GetLastError
0x18000508a  mov     ebx, eax
0x18000508c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005093  lea     rax, WPP_GLOBAL_Control
0x18000509a  cmp     rcx, rax
0x18000509d  jz      loc_18000516E
0x1800050a3  test    byte ptr [rcx+1Ch], 1
0x1800050a7  jz      loc_18000516E
0x1800050ad  mov     edx, 0C3h
0x1800050b2  jmp     loc_180004E66
0x1800050b7  mov     edx, [rsp+2A0h+nBufferLen]; cchDest
0x1800050bb  mov     r8, rsi; pszSrc
0x1800050be  mov     rcx, rdi; pszDest
0x1800050c1  call    StringCchCopyW
0x1800050c6  mov     r8, rdi; pszSrc
0x1800050c9  mov     edx, ebx; cchDest
0x1800050cb  mov     rcx, r15; pszDest
  ... truncated ...
```

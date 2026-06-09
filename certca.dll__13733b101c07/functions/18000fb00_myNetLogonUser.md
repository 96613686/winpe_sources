# myNetLogonUser

- ea: `0x18000fb00`
- end: `0x18001000e`
- name: `myNetLogonUser`
- size: `1294`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR, LPCWSTR, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b3f0`
- `0x180010978`
- `0x18001246c`

## callees

- `0x180005f80`
- `0x18000d520`
- `0x18000fb00`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fe36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fecd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fe36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fecd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ffc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fff1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ffc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fff1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000fcd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000fcd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fce3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fca8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fcbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fda1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fca8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fcbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000fda1`
- `SspiCli!FreeContextBuffer` at `0x18000fc18`
- `SspiCli!FreeContextBuffer` at `0x18000fc44`
- `SspiCli!FreeContextBuffer` at `0x180010000`
- `SspiCli!FreeContextBuffer` at `0x18000fc18`
- `SspiCli!FreeContextBuffer` at `0x18000fc44`
- `SspiCli!FreeContextBuffer` at `0x180010000`
- `SspiCli!EnumerateSecurityPackagesW` at `0x18000fbb3`
- `SspiCli!EnumerateSecurityPackagesW` at `0x18000fbb3`
- `SspiCli!QueryCredentialsAttributesW` at `0x18000fe03`
- `SspiCli!QueryCredentialsAttributesW` at `0x18000fe03`
- `SspiCli!FreeCredentialsHandle` at `0x18000ff7c`
- `SspiCli!FreeCredentialsHandle` at `0x18000ff92`
- `SspiCli!FreeCredentialsHandle` at `0x18000ff7c`
- `SspiCli!FreeCredentialsHandle` at `0x18000ff92`
- `SspiCli!DeleteSecurityContext` at `0x18000ff50`
- `SspiCli!DeleteSecurityContext` at `0x18000ff66`
- `SspiCli!DeleteSecurityContext` at `0x18000ff50`
- `SspiCli!DeleteSecurityContext` at `0x18000ff66`
- `SspiCli!QuerySecurityContextToken` at `0x18000ff2b`
- `SspiCli!QuerySecurityContextToken` at `0x18000ff2b`
- `SspiCli!AcceptSecurityContext` at `0x18000ff19`
- `SspiCli!AcceptSecurityContext` at `0x18000ff19`
- `SspiCli!InitializeSecurityContextW` at `0x18000fe95`
- `SspiCli!InitializeSecurityContextW` at `0x18000fe95`
- `SspiCli!AcquireCredentialsHandleW` at `0x18000fc7f`
- `SspiCli!AcquireCredentialsHandleW` at `0x18000fde8`
- `SspiCli!AcquireCredentialsHandleW` at `0x18000fc7f`
- `SspiCli!AcquireCredentialsHandleW` at `0x18000fde8`

## pseudocode

```c
__int64 __fastcall myNetLogonUser(LPCWSTR lpString, LPCWSTR a2, LPCWSTR a3, void **a4)
{
  unsigned int v4; // r12d
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PSecPkgInfoW v10; // rcx
  __int64 v11; // rsi
  unsigned __int64 v12; // rdi
  int v13; // eax
  SIZE_T cbMaxToken; // rbx
  int v16; // eax
  __int64 v17; // r10
  __int64 v18; // r11
  const wchar_t *v19; // rcx
  WCHAR *v20; // rdx
  size_t i; // r10
  WCHAR *v22; // rcx
  _BYTE *v24; // rax
  SIZE_T v25; // rcx
  _BYTE *v26; // rax
  SIZE_T v27; // rcx
  unsigned int pcPackages; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nSize; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int pfContextAttr; // [rsp+68h] [rbp-98h] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h]
  SECURITY_INTEGER ptsExpiry; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v36; // [rsp+98h] [rbp-68h]
  SEC_WCHAR *pBuffer; // [rsp+A0h] [rbp-60h] BYREF
  size_t pcchLength; // [rsp+A8h] [rbp-58h] BYREF
  struct _SecBufferDesc pInput; // [rsp+B0h] [rbp-50h] BYREF
  __int128 pAuthData; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int128 v42; // [rsp+E0h] [rbp-20h]
  struct _SecBufferDesc v43; // [rsp+F0h] [rbp-10h] BYREF
  void **Token; // [rsp+100h] [rbp+0h]
  struct _SecHandle phCredential; // [rsp+108h] [rbp+8h] BYREF
  struct _SecHandle phContext; // [rsp+118h] [rbp+18h] BYREF
  struct _SecHandle v47; // [rsp+128h] [rbp+28h] BYREF
  struct _SecHandle phNewContext; // [rsp+138h] [rbp+38h] BYREF
  wchar_t Buffer[20]; // [rsp+148h] [rbp+48h] BYREF

  v4 = 0;
  Token = a4;
  pfContextAttr = 0;
  pcPackages = 0;
  ppPackageInfo = 0;
  ptsExpiry.QuadPart = 0;
  v32 = 0;
  v35 = 0;
  hMem = 0;
  pAuthData = 0;
  v36 = 0;
  v41 = 0;
  pBuffer = 0;
  v42 = 0;
  phNewContext.dwUpper = 0xFFFFFFFFLL;
  pInput = 0;
  phNewContext.dwLower = 0xFFFFFFFFLL;
  v43 = 0;
  phContext.dwUpper = 0xFFFFFFFFLL;
  phContext.dwLower = 0xFFFFFFFFLL;
  phCredential.dwUpper = 0xFFFFFFFFLL;
  phCredential.dwLower = 0xFFFFFFFFLL;
  v47.dwUpper = 0xFFFFFFFFLL;
  v47.dwLower = 0xFFFFFFFFLL;
  nSize = 17;
  if ( EnumerateSecurityPackagesW(&pcPackages, &ppPackageInfo) )
    return 0;
  v8 = pcPackages;
  v9 = 0;
  v10 = ppPackageInfo;
  if ( !pcPackages )
  {
LABEL_8:
    FreeContextBuffer(v10);
    return 0;
  }
  v11 = -1;
  while ( 1 )
  {
    v12 = v9;
    if ( v10[v12].Name )
      break;
LABEL_7:
    if ( ++v9 >= v8 )
      goto LABEL_8;
  }
  v13 = mylstrcmpNLSub(v10[v12].Name, L"Kerberos", -1, 1);
  v10 = ppPackageInfo;
  if ( v13 )
  {
    v8 = pcPackages;
    goto LABEL_7;
  }
  cbMaxToken = ppPackageInfo[v12].cbMaxToken;
  FreeContextBuffer(ppPackageInfo);
  if ( !AcquireCredentialsHandleW(0, (LPWSTR)L"Kerberos", 1u, 0, 0, 0, 0, &phCredential, &ptsExpiry) )
  {
    pAuthData = 0;
    v41 = 0;
    v42 = 0;
    if ( a2 )
    {
      *(_QWORD *)&v41 = a2;
      DWORD2(v41) = lstrlenW(a2);
    }
    if ( lpString )
    {
      *(_QWORD *)&pAuthData = lpString;
      v16 = lstrlenW(lpString);
      goto LABEL_29;
    }
    if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
    {
      pcchLength = 0;
      if ( (unsigned __int64)(nSize + 2) - 1 <= 0x7FFFFFFE && StringLengthWorkerW(Buffer, nSize + 2, &pcchLength) >= 0 )
      {
        v19 = L"$";
        v20 = &Buffer[pcchLength];
        for ( i = v17 - pcchLength; i; --i )
        {
          if ( !v18 )
            break;
          if ( !*v19 )
            break;
          *v20++ = *v19++;
          --v18;
        }
        v22 = v20 - 1;
        if ( i )
          v22 = v20;
        *v22 = 0;
        if ( i )
        {
          *(_QWORD *)&pAuthData = Buffer;
          while ( Buffer[++v11] != 0 )
            ;
          v16 = v11 + 1;
LABEL_29:
          DWORD2(pAuthData) = v16;
          if ( a3 )
          {
            *(_QWORD *)&v42 = a3;
            DWORD2(v42) = lstrlenW(a3);
          }
          HIDWORD(v42) = 2;
          if ( !AcquireCredentialsHandleW(0, (LPWSTR)L"Kerberos", 2u, 0, &pAuthData, 0, 0, &v47, &ptsExpiry)
            && !QueryCredentialsAttributesW(&phCredential, 1u, &pBuffer) )
          {
            pInput.ulVersion = 0;
            pInput.pBuffers = (PSecBuffer)&v32;
            pInput.cBuffers = 1;
            v32 = (unsigned int)cbMaxToken | 0x200000000LL;
            hMem = LocalAlloc(0, cbMaxToken);
            if ( hMem )
            {
              if ( !InitializeSecurityContextW(
                      &v47,
                      0,
                      pBuffer,
                      8u,
                      0,
                      0x10u,
                      0,
                      0,
                      &phNewContext,
                      &pInput,
                      &pfContextAttr,
                      &ptsExpiry) )
              {
                HIDWORD(v32) |= 0x80000000;
                v43.pBuffers = (PSecBuffer)&v35;
                v43.ulVersion = 0;
                v43.cBuffers = 1;
                v35 = (unsigned int)cbMaxToken | 0x200000000LL;
                v36 = LocalAlloc(0, cbMaxToken);
                if ( v36 )
                {
                  if ( !AcceptSecurityContext(
                          &phCredential,
                          0,
                          &pInput,
                          8u,
                          0x10u,
                          &phContext,
                          &v43,
                          &pfContextAttr,
                          &ptsExpiry)
                    && !QuerySecurityContextToken(&phContext, Token) )
                  {
                    v4 = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      GetLastError();
    }
  }
  if ( phNewContext.dwUpper != 0xFFFFFFFF || phNewContext.dwLower != 0xFFFFFFFF )
    DeleteSecurityContext(&phNewContext);
  if ( phContext.dwUpper != 0xFFFFFFFF || phContext.dwLower != 0xFFFFFFFF )
    DeleteSecurityContext(&phContext);
  if ( phCredential.dwUpper != 0xFFFFFFFF || phCredential.dwLower != 0xFFFFFFFF )
    FreeCredentialsHandle(&phCredential);
  if ( v47.dwUpper != 0xFFFFFFFF || v47.dwLower != 0xFFFFFFFF )
    FreeCredentialsHandle(&v47);
  v24 = hMem;
  if ( hMem )
  {
    v25 = cbMaxToken;
    if ( (_DWORD)cbMaxToken )
    {
      do
      {
        *v24++ = 0;
        --v25;
      }
      while ( v25 );
    }
    LocalFree(hMem);
  }
  v26 = v36;
  if ( v36 )
  {
    v27 = cbMaxToken;
    if ( (_DWORD)cbMaxToken )
    {
      do
      {
        *v26++ = 0;
        --v27;
      }
      while ( v27 );
    }
    LocalFree(v36);
  }
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  return v4;
}

```

## disassembly

```asm
0x18000fb00  push    rbp
0x18000fb02  push    rbx
0x18000fb03  push    rsi
0x18000fb04  push    rdi
0x18000fb05  push    r12
0x18000fb07  push    r13
0x18000fb09  push    r14
0x18000fb0b  push    r15
0x18000fb0d  lea     rbp, [rsp-88h]
0x18000fb15  sub     rsp, 188h
0x18000fb1c  mov     rax, cs:__security_cookie
0x18000fb23  xor     rax, rsp
0x18000fb26  mov     [rbp+0C0h+var_50], rax
0x18000fb2a  xor     r12d, r12d
0x18000fb2d  mov     [rbp+0C0h+Token], r9
0x18000fb31  mov     eax, 0FFFFFFFFh
0x18000fb36  mov     [rsp+1C0h+var_158], r12d
0x18000fb3b  xorps   xmm0, xmm0
0x18000fb3e  mov     [rsp+1C0h+pcPackages], r12d
0x18000fb43  mov     r15, rdx
0x18000fb46  mov     [rsp+1C0h+ppPackageInfo], r12
0x18000fb4b  mov     r14, rcx
0x18000fb4e  mov     qword ptr [rbp+0C0h+var_138], r12
0x18000fb52  xorps   xmm1, xmm1
0x18000fb55  mov     [rsp+1C0h+var_148], r12
0x18000fb5a  lea     rdx, [rsp+1C0h+ppPackageInfo]; ppPackageInfo
0x18000fb5f  mov     [rbp+0C0h+var_130], r12
0x18000fb63  lea     rcx, [rsp+1C0h+pcPackages]; pcPackages
0x18000fb68  mov     [rbp+0C0h+hMem], r12
0x18000fb6c  movups  [rbp+0C0h+var_100], xmm0
0x18000fb70  mov     [rbp+0C0h+var_128], r12
0x18000fb74  mov     r13, r8
0x18000fb77  movups  [rbp+0C0h+var_F0], xmm0
0x18000fb7b  mov     [rbp+0C0h+pBuffer], r12
0x18000fb7f  movups  [rbp+0C0h+var_E0], xmm0
0x18000fb83  mov     [rbp+0C0h+phNewContext.dwUpper], rax
0x18000fb87  movups  xmmword ptr [rbp+0C0h+pInput.ulVersion], xmm0
0x18000fb8b  mov     [rbp+0C0h+phNewContext.dwLower], rax
0x18000fb8f  movups  xmmword ptr [rbp+0C0h+var_D0.ulVersion], xmm1
0x18000fb93  mov     [rbp+0C0h+phContext.dwUpper], rax
0x18000fb97  mov     [rbp+0C0h+phContext.dwLower], rax
0x18000fb9b  mov     [rbp+0C0h+var_B8.dwUpper], rax
0x18000fb9f  mov     [rbp+0C0h+var_B8.dwLower], rax
0x18000fba3  mov     [rbp+0C0h+var_98.dwUpper], rax
0x18000fba7  mov     [rbp+0C0h+var_98.dwLower], rax
0x18000fbab  mov     [rsp+1C0h+nSize], 11h
0x18000fbb3  call    cs:__imp_EnumerateSecurityPackagesW
0x18000fbb9  test    eax, eax
0x18000fbbb  jnz     short loc_18000FC1E
0x18000fbbd  mov     eax, [rsp+1C0h+pcPackages]
0x18000fbc1  mov     ebx, r12d
0x18000fbc4  mov     rcx, [rsp+1C0h+ppPackageInfo]
0x18000fbc9  test    eax, eax
0x18000fbcb  jz      short loc_18000FC18
0x18000fbcd  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000fbd4  nop     dword ptr [rax+00h]
0x18000fbd8  nop     dword ptr [rax+rax+00000000h]
0x18000fbe0  mov     edi, ebx
0x18000fbe2  shl     rdi, 5
0x18000fbe6  mov     r10, [rdi+rcx+10h]
0x18000fbeb  test    r10, r10
0x18000fbee  jz      short loc_18000FC12
0x18000fbf0  mov     r9b, 1; bool
0x18000fbf3  lea     rdx, pszPackage; "Kerberos"
0x18000fbfa  mov     r8d, esi; int
0x18000fbfd  mov     rcx, r10; lpString1
0x18000fc00  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000fc05  mov     rcx, [rsp+1C0h+ppPackageInfo]; pvContextBuffer
0x18000fc0a  test    eax, eax
0x18000fc0c  jz      short loc_18000FC40
0x18000fc0e  mov     eax, [rsp+1C0h+pcPackages]
0x18000fc12  inc     ebx
0x18000fc14  cmp     ebx, eax
0x18000fc16  jb      short loc_18000FBE0
0x18000fc18  call    cs:__imp_FreeContextBuffer
0x18000fc1e  xor     eax, eax
0x18000fc20  mov     rcx, [rbp+0C0h+var_50]
0x18000fc24  xor     rcx, rsp; StackCookie
0x18000fc27  call    __security_check_cookie
0x18000fc2c  add     rsp, 188h
0x18000fc33  pop     r15
0x18000fc35  pop     r14
0x18000fc37  pop     r13
0x18000fc39  pop     r12
0x18000fc3b  pop     rdi
0x18000fc3c  pop     rsi
0x18000fc3d  pop     rbx
0x18000fc3e  pop     rbp
0x18000fc3f  retn
0x18000fc40  mov     ebx, [rdi+rcx+8]
0x18000fc44  call    cs:__imp_FreeContextBuffer
0x18000fc4a  lea     rax, [rbp+0C0h+var_138]
0x18000fc4e  xor     r9d, r9d; pvLogonId
0x18000fc51  mov     [rsp+1C0h+ptsExpiry], rax; ptsExpiry
0x18000fc56  lea     rdx, pszPackage; "Kerberos"
0x18000fc5d  lea     rax, [rbp+0C0h+var_B8]
0x18000fc61  mov     r8d, 1; fCredentialUse
0x18000fc67  mov     [rsp+1C0h+phCredential], rax; phCredential
0x18000fc6c  xor     ecx, ecx; pszPrincipal
0x18000fc6e  xor     eax, eax
0x18000fc70  mov     [rsp+1C0h+pvGetKeyArgument], rax; pvGetKeyArgument
0x18000fc75  mov     [rsp+1C0h+pGetKeyFn], rax; pGetKeyFn
0x18000fc7a  mov     [rsp+1C0h+pAuthData], rax; pAuthData
0x18000fc7f  call    cs:__imp_AcquireCredentialsHandleW
0x18000fc85  test    eax, eax
0x18000fc87  jnz     loc_18000FF3B
0x18000fc8d  xorps   xmm0, xmm0
0x18000fc90  movups  [rbp+0C0h+var_100], xmm0
0x18000fc94  movups  [rbp+0C0h+var_F0], xmm0
0x18000fc98  movups  [rbp+0C0h+var_E0], xmm0
0x18000fc9c  test    r15, r15
0x18000fc9f  jz      short loc_18000FCB1
0x18000fca1  mov     rcx, r15; lpString
0x18000fca4  mov     qword ptr [rbp+0C0h+var_F0], r15
0x18000fca8  call    cs:__imp_lstrlenW
0x18000fcae  mov     dword ptr [rbp+0C0h+var_F0+8], eax
0x18000fcb1  test    r14, r14
0x18000fcb4  jz      short loc_18000FCCB
0x18000fcb6  mov     rcx, r14; lpString
0x18000fcb9  mov     qword ptr [rbp+0C0h+var_100], r14
0x18000fcbd  call    cs:__imp_lstrlenW
0x18000fcc3  xor     r14d, r14d
0x18000fcc6  jmp     loc_18000FD92
0x18000fccb  lea     r8, [rsp+1C0h+nSize]; nSize
0x18000fcd0  mov     ecx, 4; NameType
0x18000fcd5  lea     rdx, [rbp+0C0h+Buffer]; lpBuffer
0x18000fcd9  call    cs:__imp_GetComputerNameExW
0x18000fcdf  test    eax, eax
0x18000fce1  jnz     short loc_18000FCEE
0x18000fce3  call    cs:__imp_GetLastError
0x18000fce9  jmp     loc_18000FF3B
0x18000fcee  mov     eax, [rsp+1C0h+nSize]
0x18000fcf2  xor     r14d, r14d
0x18000fcf5  add     eax, 2
0x18000fcf8  mov     [rbp+0C0h+pcchLength], r14
0x18000fcfc  mov     r10d, eax
0x18000fcff  mov     r11d, 7FFFFFFEh
0x18000fd05  dec     rax
0x18000fd08  cmp     rax, r11
0x18000fd0b  ja      loc_18000FF3B
0x18000fd11  lea     r8, [rbp+0C0h+pcchLength]; pcchLength
0x18000fd15  mov     edx, r10d; cchMax
0x18000fd18  lea     rcx, [rbp+0C0h+Buffer]; psz
0x18000fd1c  call    StringLengthWorkerW
0x18000fd21  test    eax, eax
0x18000fd23  js      loc_18000FF3B
0x18000fd29  mov     rax, [rbp+0C0h+pcchLength]
0x18000fd2d  lea     rdx, [rbp+0C0h+Buffer]
0x18000fd31  lea     rcx, asc_1800B417C; "$"
0x18000fd38  lea     rdx, [rdx+rax*2]
0x18000fd3c  sub     r10, rax
0x18000fd3f  jz      short loc_18000FD62
0x18000fd41  test    r11, r11
0x18000fd44  jz      short loc_18000FD62
0x18000fd46  movzx   eax, word ptr [rcx]
0x18000fd49  test    ax, ax
0x18000fd4c  jz      short loc_18000FD62
0x18000fd4e  mov     [rdx], ax
0x18000fd51  add     rcx, 2
0x18000fd55  add     rdx, 2
0x18000fd59  dec     r11
0x18000fd5c  sub     r10, 1
0x18000fd60  jnz     short loc_18000FD41
0x18000fd62  test    r10, r10
0x18000fd65  lea     rcx, [rdx-2]
0x18000fd69  cmovnz  rcx, rdx
0x18000fd6d  mov     [rcx], r14w
0x18000fd71  jz      loc_18000FF3B
0x18000fd77  lea     rax, [rbp+0C0h+Buffer]
0x18000fd7b  mov     qword ptr [rbp+0C0h+var_100], rax
0x18000fd7f  lea     rax, [rbp+0C0h+Buffer]
0x18000fd83  cmp     [rax+rsi*2+2], r12w
0x18000fd89  lea     rsi, [rsi+1]
0x18000fd8d  jnz     short loc_18000FD83
0x18000fd8f  lea     eax, [rsi+1]
0x18000fd92  mov     dword ptr [rbp+0C0h+var_100+8], eax
0x18000fd95  test    r13, r13
0x18000fd98  jz      short loc_18000FDAA
0x18000fd9a  mov     rcx, r13; lpString
0x18000fd9d  mov     qword ptr [rbp+0C0h+var_E0], r13
0x18000fda1  call    cs:__imp_lstrlenW
0x18000fda7  mov     dword ptr [rbp+0C0h+var_E0+8], eax
0x18000fdaa  lea     rax, [rbp+0C0h+var_138]
0x18000fdae  mov     dword ptr [rbp+0C0h+var_E0+0Ch], 2
0x18000fdb5  mov     [rsp+1C0h+ptsExpiry], rax; ptsExpiry
0x18000fdba  lea     rdx, pszPackage; "Kerberos"
0x18000fdc1  lea     rax, [rbp+0C0h+var_98]
0x18000fdc5  xor     r9d, r9d; pvLogonId
0x18000fdc8  mov     [rsp+1C0h+phCredential], rax; phCredential
0x18000fdcd  mov     r8d, 2; fCredentialUse
0x18000fdd3  mov     [rsp+1C0h+pvGetKeyArgument], r14; pvGetKeyArgument
0x18000fdd8  lea     rax, [rbp+0C0h+var_100]
0x18000fddc  mov     [rsp+1C0h+pGetKeyFn], r14; pGetKeyFn
0x18000fde1  xor     ecx, ecx; pszPrincipal
0x18000fde3  mov     [rsp+1C0h+pAuthData], rax; pAuthData
0x18000fde8  call    cs:__imp_AcquireCredentialsHandleW
0x18000fdee  test    eax, eax
0x18000fdf0  jnz     loc_18000FF3B
0x18000fdf6  lea     r8, [rbp+0C0h+pBuffer]; pBuffer
0x18000fdfa  mov     edx, 1; ulAttribute
0x18000fdff  lea     rcx, [rbp+0C0h+var_B8]; phCredential
0x18000fe03  call    cs:__imp_QueryCredentialsAttributesW
0x18000fe09  test    eax, eax
0x18000fe0b  jnz     loc_18000FF3B
0x18000fe11  lea     rax, [rsp+1C0h+var_148]
0x18000fe16  mov     [rbp+0C0h+pInput.ulVersion], r14d
0x18000fe1a  mov     rdx, rbx; uBytes
0x18000fe1d  mov     [rbp+0C0h+pInput.pBuffers], rax
0x18000fe21  xor     ecx, ecx; uFlags
0x18000fe23  mov     [rbp+0C0h+pInput.cBuffers], 1
0x18000fe2a  mov     dword ptr [rsp+1C0h+var_148], ebx
0x18000fe2e  mov     dword ptr [rsp+1C0h+var_148+4], 2
0x18000fe36  call    cs:__imp_LocalAlloc
0x18000fe3c  mov     [rbp+0C0h+hMem], rax
0x18000fe40  test    rax, rax
0x18000fe43  jz      loc_18000FF3B
0x18000fe49  mov     r8, [rbp+0C0h+pBuffer]; pszTargetName
0x18000fe4d  lea     rax, [rbp+0C0h+var_138]
0x18000fe51  mov     [rsp+1C0h+var_168], rax; ptsExpiry
0x18000fe56  lea     rcx, [rbp+0C0h+var_98]; phCredential
0x18000fe5a  lea     rax, [rsp+1C0h+var_158]
0x18000fe5f  mov     r9d, 8; fContextReq
0x18000fe65  mov     [rsp+1C0h+pfContextAttr], rax; pfContextAttr
0x18000fe6a  xor     edx, edx; phContext
0x18000fe6c  lea     rax, [rbp+0C0h+pInput]
0x18000fe70  mov     [rsp+1C0h+pOutput], rax; pOutput
0x18000fe75  lea     rax, [rbp+0C0h+phNewContext]
0x18000fe79  mov     [rsp+1C0h+ptsExpiry], rax; phNewContext
0x18000fe7e  mov     dword ptr [rsp+1C0h+phCredential], r14d; Reserved2
0x18000fe83  mov     [rsp+1C0h+pvGetKeyArgument], r14; pInput
0x18000fe88  mov     dword ptr [rsp+1C0h+pGetKeyFn], 10h; TargetDataRep
0x18000fe90  mov     dword ptr [rsp+1C0h+pAuthData], r14d; Reserved1
0x18000fe95  call    cs:__imp_InitializeSecurityContextW
0x18000fe9b  test    eax, eax
0x18000fe9d  jnz     loc_18000FF3B
0x18000fea3  or      dword ptr [rsp+1C0h+var_148+4], 80000000h
0x18000feab  lea     rax, [rbp+0C0h+var_130]
0x18000feaf  mov     rdx, rbx; uBytes
0x18000feb2  mov     [rbp+0C0h+var_D0.pBuffers], rax
0x18000feb6  xor     ecx, ecx; uFlags
0x18000feb8  mov     [rbp+0C0h+var_D0.ulVersion], r14d
0x18000febc  mov     [rbp+0C0h+var_D0.cBuffers], 1
0x18000fec3  mov     dword ptr [rbp+0C0h+var_130], ebx
0x18000fec6  mov     dword ptr [rbp+0C0h+var_130+4], 2
0x18000fecd  call    cs:__imp_LocalAlloc
0x18000fed3  mov     [rbp+0C0h+var_128], rax
0x18000fed7  test    rax, rax
0x18000feda  jz      short loc_18000FF3B
0x18000fedc  lea     rax, [rbp+0C0h+var_138]
0x18000fee0  mov     r9d, 8; fContextReq
0x18000fee6  mov     [rsp+1C0h+ptsExpiry], rax; ptsExpiry
0x18000feeb  lea     r8, [rbp+0C0h+pInput]; pInput
0x18000feef  lea     rax, [rsp+1C0h+var_158]
0x18000fef4  xor     edx, edx; phContext
0x18000fef6  mov     [rsp+1C0h+phCredential], rax; pfContextAttr
0x18000fefb  lea     rcx, [rbp+0C0h+var_B8]; phCredential
0x18000feff  lea     rax, [rbp+0C0h+var_D0]
0x18000ff03  mov     [rsp+1C0h+pvGetKeyArgument], rax; pOutput
0x18000ff08  lea     rax, [rbp+0C0h+phContext]
0x18000ff0c  mov     [rsp+1C0h+pGetKeyFn], rax; phNewContext
0x18000ff11  mov     dword ptr [rsp+1C0h+pAuthData], 10h; TargetDataRep
0x18000ff19  call    cs:__imp_AcceptSecurityContext
0x18000ff1f  test    eax, eax
0x18000ff21  jnz     short loc_18000FF3B
0x18000ff23  mov     rdx, [rbp+0C0h+Token]; Token
0x18000ff27  lea     rcx, [rbp+0C0h+phContext]; phContext
0x18000ff2b  call    cs:__imp_QuerySecurityContextToken
0x18000ff31  test    eax, eax
0x18000ff33  jnz     short loc_18000FF3B
0x18000ff35  mov     r12d, 1
0x18000ff3b  mov     edi, 0FFFFFFFFh
0x18000ff40  cmp     [rbp+0C0h+phNewContext.dwUpper], rdi
0x18000ff44  jnz     short loc_18000FF4C
0x18000ff46  cmp     [rbp+0C0h+phNewContext.dwLower], rdi
0x18000ff4a  jz      short loc_18000FF56
0x18000ff4c  lea     rcx, [rbp+0C0h+phNewContext]; phContext
0x18000ff50  call    cs:__imp_DeleteSecurityContext
0x18000ff56  cmp     [rbp+0C0h+phContext.dwUpper], rdi
0x18000ff5a  jnz     short loc_18000FF62
0x18000ff5c  cmp     [rbp+0C0h+phContext.dwLower], rdi
0x18000ff60  jz      short loc_18000FF6C
0x18000ff62  lea     rcx, [rbp+0C0h+phContext]; phContext
0x18000ff66  call    cs:__imp_DeleteSecurityContext
0x18000ff6c  cmp     [rbp+0C0h+var_B8.dwUpper], rdi
0x18000ff70  jnz     short loc_18000FF78
0x18000ff72  cmp     [rbp+0C0h+var_B8.dwLower], rdi
0x18000ff76  jz      short loc_18000FF82
0x18000ff78  lea     rcx, [rbp+0C0h+var_B8]; phCredential
0x18000ff7c  call    cs:__imp_FreeCredentialsHandle
0x18000ff82  cmp     [rbp+0C0h+var_98.dwUpper], rdi
0x18000ff86  jnz     short loc_18000FF8E
0x18000ff88  cmp     [rbp+0C0h+var_98.dwLower], rdi
0x18000ff8c  jz      short loc_18000FF98
0x18000ff8e  lea     rcx, [rbp+0C0h+var_98]; phCredential
0x18000ff92  call    cs:__imp_FreeCredentialsHandle
0x18000ff98  mov     rax, [rbp+0C0h+hMem]
0x18000ff9c  test    rax, rax
0x18000ff9f  jz      short loc_18000FFC7
0x18000ffa1  mov     rcx, rbx
0x18000ffa4  test    ebx, ebx
  ... truncated ...
```

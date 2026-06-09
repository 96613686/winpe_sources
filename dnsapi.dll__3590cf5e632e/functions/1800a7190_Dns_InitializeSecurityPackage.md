# Dns_InitializeSecurityPackage

- ea: `0x1800a7190`
- end: `0x1800a736c`
- name: `Dns_InitializeSecurityPackage`
- size: `476`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800662b0`
- `0x18006adbc`

## callees

- `0x1800257d0`
- `0x18008b5f0`
- `0x1800a7190`
- `0x1800dbadc`
- `0x1800dbb48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a71c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a71c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7345`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7345`
- `SspiCli!FreeContextBuffer` at `0x1800a7272`
- `SspiCli!FreeContextBuffer` at `0x1800a7272`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800a7204`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800a7204`
- `RPCRT4!UuidCreateSequential` at `0x1800a7282`
- `RPCRT4!UuidCreateSequential` at `0x1800a7282`

## pseudocode

```c
__int64 Dns_InitializeSecurityPackage()
{
  SECURITY_STATUS v0; // eax
  int v1; // ecx
  unsigned int v2; // ebx
  int v3; // edx
  PSecPkgInfoW ppPackageInfo; // [rsp+70h] [rbp+17h] BYREF
  UUID Uuid; // [rsp+78h] [rbp+1Fh] BYREF

  ppPackageInfo = 0;
  Uuid = 0;
  EnterCriticalSection(&g_csSecurityContextList);
  if ( g_fSecurityPackageInitialized )
  {
LABEL_15:
    v2 = 0;
    goto LABEL_16;
  }
  if ( !g_fVelocityDisableInternalExports )
  {
    g_hSspiCredentials.dwUpper = -1;
    g_hSspiCredentials.dwLower = -1;
  }
  v0 = QuerySecurityPackageInfoW((LPWSTR)L"negotiate", &ppPackageInfo);
  v2 = v0;
  if ( !g_fVelocityDisableInternalExports )
  {
    if ( v0 < 0 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_16;
      v3 = 25;
      goto LABEL_8;
    }
    goto LABEL_12;
  }
  if ( !v0 )
  {
LABEL_12:
    LODWORD(g_SecurityTokenMaxLength) = ppPackageInfo->cbMaxToken;
    FreeContextBuffer(ppPackageInfo);
    UuidCreateSequential(&Uuid);
    StringCchPrintfA(
      g_ContextUuid,
      0x50u,
      "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
      Uuid.Data1,
      Uuid.Data2,
      Uuid.Data3,
      Uuid.Data4[0],
      Uuid.Data4[1],
      Uuid.Data4[2],
      Uuid.Data4[3],
      Uuid.Data4[4],
      Uuid.Data4[5],
      Uuid.Data4[6],
      Uuid.Data4[7]);
    if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_Sd(
        1038,
        26,
        (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
        (unsigned int)L"negotiate",
        g_SecurityTokenMaxLength);
    g_fSecurityPackageInitialized = 1;
    goto LABEL_15;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v3 = 24;
LABEL_8:
    WPP_SF_SD(v1, v3, (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, (unsigned int)L"negotiate", v0);
  }
LABEL_16:
  LeaveCriticalSection(&g_csSecurityContextList);
  return v2;
}

```

## disassembly

```asm
0x1800a7190  push    rbp
0x1800a7192  push    rbx
0x1800a7193  push    rsi
0x1800a7194  push    rdi
0x1800a7195  lea     rbp, [rsp-3Fh]
0x1800a719a  sub     rsp, 98h
0x1800a71a1  mov     rax, cs:__security_cookie
0x1800a71a8  xor     rax, rsp
0x1800a71ab  mov     [rbp+57h+var_28], rax
0x1800a71af  xorps   xmm0, xmm0
0x1800a71b2  mov     [rbp+57h+ppPackageInfo], 0
0x1800a71ba  lea     rcx, g_csSecurityContextList; lpCriticalSection
0x1800a71c1  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800a71c5  call    cs:__imp_EnterCriticalSection
0x1800a71cc  nop     dword ptr [rax+rax+00h]
0x1800a71d1  cmp     cs:g_fSecurityPackageInitialized, 0
0x1800a71d8  jnz     loc_1800A733C
0x1800a71de  cmp     cs:g_fVelocityDisableInternalExports, 0
0x1800a71e5  jnz     short loc_1800A71F9
0x1800a71e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a71eb  mov     cs:g_hSspiCredentials.dwUpper, rax
0x1800a71f2  mov     cs:g_hSspiCredentials.dwLower, rax
0x1800a71f9  lea     rdx, [rbp+57h+ppPackageInfo]; ppPackageInfo
0x1800a71fd  lea     rcx, pszPackageName; "negotiate"
0x1800a7204  call    cs:__imp_QuerySecurityPackageInfoW
0x1800a720b  nop     dword ptr [rax+rax+00h]
0x1800a7210  cmp     cs:g_fVelocityDisableInternalExports, 0
0x1800a7217  mov     ebx, eax
0x1800a7219  jz      short loc_1800A724D
0x1800a721b  test    eax, eax
0x1800a721d  jz      short loc_1800A7265
0x1800a721f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a7226  jz      loc_1800A733E
0x1800a722c  mov     edx, 18h
0x1800a7231  lea     r9, pszPackageName; "negotiate"
0x1800a7238  mov     [rsp+0B0h+var_90], eax
0x1800a723c  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a7243  call    WPP_SF_SD
0x1800a7248  jmp     loc_1800A733E
0x1800a724d  test    eax, eax
0x1800a724f  jns     short loc_1800A7265
0x1800a7251  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a7258  jz      loc_1800A733E
0x1800a725e  mov     edx, 19h
0x1800a7263  jmp     short loc_1800A7231
0x1800a7265  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x1800a7269  mov     eax, [rcx+8]
0x1800a726c  mov     cs:g_SecurityTokenMaxLength, eax
0x1800a7272  call    cs:__imp_FreeContextBuffer
0x1800a7279  nop     dword ptr [rax+rax+00h]
0x1800a727e  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800a7282  call    cs:__imp_UuidCreateSequential
0x1800a7289  nop     dword ptr [rax+rax+00h]
0x1800a728e  movzx   ecx, [rbp+57h+Uuid.Data4+6]
0x1800a7292  movzx   edx, [rbp+57h+Uuid.Data4+5]
0x1800a7296  movzx   r8d, [rbp+57h+Uuid.Data4+4]
0x1800a729b  movzx   r9d, [rbp+57h+Uuid.Data4+3]
0x1800a72a0  movzx   eax, [rbp+57h+Uuid.Data4+7]
0x1800a72a4  movzx   r10d, [rbp+57h+Uuid.Data4+2]
0x1800a72a9  movzx   r11d, [rbp+57h+Uuid.Data4+1]
0x1800a72ae  movzx   ebx, [rbp+57h+Uuid.Data4]
0x1800a72b2  movzx   edi, [rbp+57h+Uuid.Data3]
0x1800a72b6  movzx   esi, [rbp+57h+Uuid.Data2]
0x1800a72ba  mov     [rsp+0B0h+var_48], eax
0x1800a72be  mov     [rsp+0B0h+var_50], ecx
0x1800a72c2  lea     rcx, g_ContextUuid; pszDest
0x1800a72c9  mov     [rsp+0B0h+var_58], edx
0x1800a72cd  mov     edx, 50h ; 'P'; cchDest
0x1800a72d2  mov     [rsp+0B0h+var_60], r8d
0x1800a72d7  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x1800a72de  mov     [rsp+0B0h+var_68], r9d
0x1800a72e3  mov     r9d, [rbp+57h+Uuid.Data1]
0x1800a72e7  mov     [rsp+0B0h+var_70], r10d
0x1800a72ec  mov     [rsp+0B0h+var_78], r11d
0x1800a72f1  mov     [rsp+0B0h+var_80], ebx
0x1800a72f5  mov     [rsp+0B0h+var_88], edi
0x1800a72f9  mov     [rsp+0B0h+var_90], esi
0x1800a72fd  call    StringCchPrintfA
0x1800a7302  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a7309  jz      short loc_1800A7332
0x1800a730b  mov     eax, cs:g_SecurityTokenMaxLength
0x1800a7311  lea     r9, pszPackageName; "negotiate"
0x1800a7318  mov     edx, 1Ah
0x1800a731d  mov     [rsp+0B0h+var_90], eax
0x1800a7321  mov     ecx, 40Eh
0x1800a7326  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a732d  call    WPP_SF_Sd
0x1800a7332  mov     cs:g_fSecurityPackageInitialized, 1
0x1800a733c  xor     ebx, ebx
0x1800a733e  lea     rcx, g_csSecurityContextList; lpCriticalSection
0x1800a7345  call    cs:__imp_LeaveCriticalSection
0x1800a734c  nop     dword ptr [rax+rax+00h]
0x1800a7351  mov     eax, ebx
0x1800a7353  mov     rcx, [rbp+57h+var_28]
0x1800a7357  xor     rcx, rsp; StackCookie
0x1800a735a  call    __security_check_cookie
0x1800a735f  add     rsp, 98h
0x1800a7366  pop     rdi
0x1800a7367  pop     rsi
0x1800a7368  pop     rbx
0x1800a7369  pop     rbp
0x1800a736a  retn
```

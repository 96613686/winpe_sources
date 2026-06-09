# _CatDBHasCryptSvcSidDaclAce

- ea: `0x180019c8c`
- end: `0x180019e7c`
- name: `_CatDBHasCryptSvcSidDaclAce`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b1c4`

## callees

- `0x1800015b0`
- `0x180003538`
- `0x18000a59c`
- `0x18000be40`
- `0x180019c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019dc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019dc4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019d08`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019d6d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019d08`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180019d6d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019e0a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019e0a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180019def`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180019def`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180019d99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180019d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019ccd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019ccd`

## pseudocode

```c
__int64 CatDBHasCryptSvcSidDaclAce()
{
  unsigned int v0; // esi
  unsigned int v1; // edx
  unsigned __int16 *v2; // rcx
  unsigned int v3; // r8d
  DWORD LastError; // eax
  void *v5; // rdi
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  PACL v10; // rcx
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  DWORD i; // ebx
  unsigned int v14; // edx
  unsigned __int16 *v15; // rcx
  int v17; // [rsp+28h] [rbp-38h]
  DWORD nLengthNeeded; // [rsp+30h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp-10h] BYREF
  WINBOOL bDaclPresent; // [rsp+54h] [rbp-Ch] BYREF

  Sid = 0;
  v0 = 0;
  nLengthNeeded = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !ConvertStringSidToSidW(L"S-1-5-80-242729624-280608522-2219052887-3187409060-2225943459", &Sid) )
  {
    v3 = 8517;
LABEL_3:
    ErrLog_LogError(v2, v1, v3, 0, 0, v17);
    goto LABEL_25;
  }
  if ( !GetFileSecurityW(g_pwszDatabaseFileBaseDirectory, 4u, 0, 0, &nLengthNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      SetLastError(LastError);
      v3 = 8530;
      goto LABEL_3;
    }
  }
  v5 = _CatDBAlloc(nLengthNeeded);
  if ( !v5 )
  {
    SetLastError(8u);
    v3 = 8539;
    goto LABEL_3;
  }
  if ( GetFileSecurityW(g_pwszDatabaseFileBaseDirectory, 4u, v5, nLengthNeeded, &nLengthNeeded) )
  {
    if ( GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v10 = pDacl;
      if ( pDacl )
      {
        for ( i = 0; i < v10->AceCount; ++i )
        {
          pAce = 0;
          if ( !GetAce(v10, i, &pAce) )
          {
            ErrLog_LogError(v15, v14, 0x2177u, 0, 0, v17);
            goto LABEL_24;
          }
          v8 = (unsigned int)pAce;
          if ( !*(_BYTE *)pAce && EqualSid(Sid, (char *)pAce + 8) )
          {
            v0 = 1;
            goto LABEL_24;
          }
          v10 = pDacl;
        }
        ErrLog_LogError((unsigned __int16 *)v10, v8, 0x2186u, 5u, 1, v17);
      }
      else
      {
        SetLastError(0x8000FFFF);
        ErrLog_LogError(v12, v11, 0x216Fu, 0, 0, v17);
      }
    }
    else
    {
      ErrLog_LogError(v9, v8, 0x216Au, 0, 0, v17);
    }
  }
  else
  {
    ErrLog_LogError(v7, v6, 0x2165u, 0, 0, v17);
  }
LABEL_24:
  _CatDBFree(v5);
LABEL_25:
  if ( Sid )
    LocalFree(Sid);
  return v0;
}

```

## disassembly

```asm
0x180019c8c  push    rbp
0x180019c8e  push    rbx
0x180019c8f  push    rsi
0x180019c90  push    rdi
0x180019c91  push    r14
0x180019c93  mov     rbp, rsp
0x180019c96  sub     rsp, 60h
0x180019c9a  mov     rax, cs:__security_cookie
0x180019ca1  xor     rax, rsp
0x180019ca4  mov     [rbp+var_8], rax
0x180019ca8  xor     r14d, r14d
0x180019cab  lea     rdx, [rbp+Sid]; Sid
0x180019caf  lea     rcx, StringSid; "S-1-5-80-242729624-280608522-2219052887"...
0x180019cb6  mov     [rbp+Sid], r14
0x180019cba  mov     esi, r14d
0x180019cbd  mov     [rbp+nLengthNeeded], r14d
0x180019cc1  mov     [rbp+pDacl], r14
0x180019cc5  mov     [rbp+bDaclPresent], r14d
0x180019cc9  mov     [rbp+bDaclDefaulted], r14d
0x180019ccd  call    cs:__imp_ConvertStringSidToSidW
0x180019cd3  xor     r9d, r9d; unsigned int
0x180019cd6  test    eax, eax
0x180019cd8  jnz     short loc_180019CEF
0x180019cda  mov     r8d, 2145h; unsigned int
0x180019ce0  mov     dword ptr [rsp+60h+lpnLengthNeeded], r14d; int
0x180019ce5  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019cea  jmp     loc_180019E54
0x180019cef  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; lpFileName
0x180019cf6  lea     rax, [rbp+nLengthNeeded]
0x180019cfa  xor     r8d, r8d; pSecurityDescriptor
0x180019cfd  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180019d02  lea     ebx, [r8+4]
0x180019d06  mov     edx, ebx; RequestedInformation
0x180019d08  call    cs:__imp_GetFileSecurityW
0x180019d0e  test    eax, eax
0x180019d10  jnz     short loc_180019D30
0x180019d12  call    cs:__imp_GetLastError
0x180019d18  cmp     eax, 7Ah ; 'z'
0x180019d1b  jz      short loc_180019D30
0x180019d1d  mov     ecx, eax; dwErrCode
0x180019d1f  call    cs:__imp_SetLastError
0x180019d25  xor     r9d, r9d
0x180019d28  mov     r8d, 2152h
0x180019d2e  jmp     short loc_180019CE0
0x180019d30  mov     ecx, [rbp+nLengthNeeded]; uBytes
0x180019d33  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180019d38  mov     rdi, rax
0x180019d3b  test    rax, rax
0x180019d3e  jnz     short loc_180019D54
0x180019d40  lea     ecx, [rax+8]; dwErrCode
0x180019d43  call    cs:__imp_SetLastError
0x180019d49  xor     r9d, r9d
0x180019d4c  mov     r8d, 215Bh
0x180019d52  jmp     short loc_180019CE0
0x180019d54  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180019d58  lea     rax, [rbp+nLengthNeeded]
0x180019d5c  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; lpFileName
0x180019d63  mov     r8, rdi; pSecurityDescriptor
0x180019d66  mov     edx, ebx; RequestedInformation
0x180019d68  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180019d6d  call    cs:__imp_GetFileSecurityW
0x180019d73  test    eax, eax
0x180019d75  jnz     short loc_180019D8A
0x180019d77  mov     dword ptr [rsp+60h+lpnLengthNeeded], r14d
0x180019d7c  xor     r9d, r9d
0x180019d7f  mov     r8d, 2165h
0x180019d85  jmp     loc_180019E47
0x180019d8a  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180019d8e  mov     rcx, rdi; pSecurityDescriptor
0x180019d91  lea     r8, [rbp+pDacl]; pDacl
0x180019d95  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180019d99  call    cs:__imp_GetSecurityDescriptorDacl
0x180019d9f  test    eax, eax
0x180019da1  jnz     short loc_180019DB6
0x180019da3  mov     dword ptr [rsp+60h+lpnLengthNeeded], r14d
0x180019da8  xor     r9d, r9d
0x180019dab  mov     r8d, 216Ah
0x180019db1  jmp     loc_180019E47
0x180019db6  mov     rcx, [rbp+pDacl]; unsigned __int16 *
0x180019dba  test    rcx, rcx
0x180019dbd  jnz     short loc_180019DDA
0x180019dbf  mov     ecx, 8000FFFFh; dwErrCode
0x180019dc4  call    cs:__imp_SetLastError
0x180019dca  xor     r9d, r9d
0x180019dcd  mov     dword ptr [rsp+60h+lpnLengthNeeded], r14d
0x180019dd2  mov     r8d, 216Fh
0x180019dd8  jmp     short loc_180019E47
0x180019dda  mov     ebx, r14d
0x180019ddd  movzx   eax, word ptr [rcx+4]
0x180019de1  cmp     ebx, eax
0x180019de3  jnb     short loc_180019E33
0x180019de5  lea     r8, [rbp+pAce]; pAce
0x180019de9  mov     [rbp+pAce], r14
0x180019ded  mov     edx, ebx; dwAceIndex
0x180019def  call    cs:__imp_GetAce
0x180019df5  test    eax, eax
0x180019df7  jz      short loc_180019E23
0x180019df9  mov     rdx, [rbp+pAce]
0x180019dfd  cmp     [rdx], r14b
0x180019e00  jnz     short loc_180019E14
0x180019e02  mov     rcx, [rbp+Sid]; pSid1
0x180019e06  add     rdx, 8; pSid2
0x180019e0a  call    cs:__imp_EqualSid
0x180019e10  test    eax, eax
0x180019e12  jnz     short loc_180019E1C
0x180019e14  mov     rcx, [rbp+pDacl]
0x180019e18  inc     ebx
0x180019e1a  jmp     short loc_180019DDD
0x180019e1c  mov     esi, 1
0x180019e21  jmp     short loc_180019E4C
0x180019e23  mov     dword ptr [rsp+60h+lpnLengthNeeded], r14d
0x180019e28  xor     r9d, r9d
0x180019e2b  mov     r8d, 2177h
0x180019e31  jmp     short loc_180019E47
0x180019e33  mov     dword ptr [rsp+60h+lpnLengthNeeded], 1; int
0x180019e3b  mov     r9d, 5; unsigned int
0x180019e41  mov     r8d, 2186h; unsigned int
0x180019e47  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019e4c  mov     rcx, rdi; void *
0x180019e4f  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180019e54  mov     rcx, [rbp+Sid]; hMem
0x180019e58  test    rcx, rcx
0x180019e5b  jz      short loc_180019E63
0x180019e5d  call    cs:__imp_LocalFree
0x180019e63  mov     eax, esi
0x180019e65  mov     rcx, [rbp+var_8]
0x180019e69  xor     rcx, rsp; StackCookie
0x180019e6c  call    __security_check_cookie
0x180019e71  add     rsp, 60h
0x180019e75  pop     r14
0x180019e77  pop     rdi
0x180019e78  pop     rsi
0x180019e79  pop     rbx
0x180019e7a  pop     rbp
0x180019e7b  retn
```

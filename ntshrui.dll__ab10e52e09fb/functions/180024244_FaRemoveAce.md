# FaRemoveAce

- ea: `0x180024244`
- end: `0x1800243c0`
- name: `FaRemoveAce`
- size: `380`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwAceIndex)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180024014`

## callees

- `0x180024244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002439e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002439e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ad`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002435c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002435c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002433d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002433d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180024392`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180024392`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002437d`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002437d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800242a4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002430f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800242a4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002430f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800242e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800242e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243a7`
- `api-ms-win-security-base-private-l1-1-0!MakeAbsoluteSD2` at `0x180024324`
- `api-ms-win-security-base-private-l1-1-0!MakeAbsoluteSD2` at `0x180024324`

## pseudocode

```c
DWORD __fastcall FaRemoveAce(LPCWSTR lpFileName, DWORD dwAceIndex)
{
  DWORD v5; // eax
  DWORD v6; // ecx
  HLOCAL v7; // rbx
  DWORD v8; // ecx
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+70h] [rbp+20h] BYREF
  DWORD v13; // [rsp+80h] [rbp+30h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+38h] BYREF

  pDacl = 0;
  pAce = 0;
  nLengthNeeded = 0;
  v13 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !lpFileName )
    return 87;
  if ( GetFileSecurityW(lpFileName, 4u, 0, 0, &nLengthNeeded) )
  {
    v5 = nLengthNeeded;
    goto LABEL_9;
  }
  if ( GetLastError() == 122 )
  {
    v5 = nLengthNeeded;
    if ( nLengthNeeded > 0x10000 )
    {
      v6 = 1336;
LABEL_7:
      SetLastError(v6);
      return GetLastError();
    }
LABEL_9:
    v13 = v5 + 128;
    v7 = LocalAlloc(0, v5 + 128);
    if ( !v7 )
    {
      v6 = 8;
      goto LABEL_7;
    }
    if ( GetFileSecurityW(lpFileName, 4u, v7, nLengthNeeded, &nLengthNeeded)
      && (unsigned int)MakeAbsoluteSD2(v7, &v13)
      && GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( !bDaclPresent || !pDacl )
        goto LABEL_21;
      if ( GetAce(pDacl, dwAceIndex, &pAce) )
      {
        if ( (*((_BYTE *)pAce + 1) & 0x1F) != 0 )
        {
          v8 = 87;
LABEL_22:
          SetLastError(v8);
          goto LABEL_23;
        }
        if ( !DeleteAce(pDacl, dwAceIndex) || !SetFileSecurityW(lpFileName, 4u, v7) )
          goto LABEL_23;
LABEL_21:
        v8 = 0;
        goto LABEL_22;
      }
    }
LABEL_23:
    LocalFree(v7);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180024244  mov     [rsp-18h+arg_8], rbx
0x180024249  push    rbp
0x18002424a  push    rsi
0x18002424b  push    rdi
0x18002424c  mov     rbp, rsp
0x18002424f  sub     rsp, 50h
0x180024253  mov     [rbp+pDacl], 0
0x18002425b  mov     esi, edx
0x18002425d  mov     [rbp+pAce], 0
0x180024265  mov     rdi, rcx
0x180024268  mov     [rbp+nLengthNeeded], 0
0x18002426f  mov     [rbp+arg_10], 0
0x180024276  mov     [rbp+bDaclPresent], 0
0x18002427d  mov     [rbp+bDaclDefaulted], 0
0x180024284  test    rcx, rcx
0x180024287  jnz     short loc_180024291
0x180024289  lea     eax, [rcx+57h]
0x18002428c  jmp     loc_1800243B3
0x180024291  xor     r9d, r9d; nLength
0x180024294  lea     rax, [rbp+nLengthNeeded]
0x180024298  xor     r8d, r8d; pSecurityDescriptor
0x18002429b  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800242a0  lea     edx, [r9+4]; RequestedInformation
0x1800242a4  call    cs:__imp_GetFileSecurityW
0x1800242aa  test    eax, eax
0x1800242ac  jnz     short loc_1800242D7
0x1800242ae  call    cs:__imp_GetLastError
0x1800242b4  cmp     eax, 7Ah ; 'z'
0x1800242b7  jnz     loc_1800243AD
0x1800242bd  mov     eax, [rbp+nLengthNeeded]
0x1800242c0  cmp     eax, 10000h
0x1800242c5  jbe     short loc_1800242DA
0x1800242c7  mov     ecx, 538h; dwErrCode
0x1800242cc  call    cs:__imp_SetLastError
0x1800242d2  jmp     loc_1800243AD
0x1800242d7  mov     eax, [rbp+nLengthNeeded]
0x1800242da  sub     eax, 0FFFFFF80h
0x1800242dd  xor     ecx, ecx; uFlags
0x1800242df  mov     edx, eax; uBytes
0x1800242e1  mov     [rbp+arg_10], eax
0x1800242e4  call    cs:__imp_LocalAlloc
0x1800242ea  mov     rbx, rax
0x1800242ed  test    rax, rax
0x1800242f0  jnz     short loc_1800242F7
0x1800242f2  lea     ecx, [rax+8]
0x1800242f5  jmp     short loc_1800242CC
0x1800242f7  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1800242fb  lea     rax, [rbp+nLengthNeeded]
0x1800242ff  mov     r8, rbx; pSecurityDescriptor
0x180024302  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180024307  mov     edx, 4; RequestedInformation
0x18002430c  mov     rcx, rdi; lpFileName
0x18002430f  call    cs:__imp_GetFileSecurityW
0x180024315  test    eax, eax
0x180024317  jz      loc_1800243A4
0x18002431d  lea     rdx, [rbp+arg_10]
0x180024321  mov     rcx, rbx
0x180024324  call    cs:__imp_MakeAbsoluteSD2
0x18002432a  test    eax, eax
0x18002432c  jz      short loc_1800243A4
0x18002432e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180024332  mov     rcx, rbx; pSecurityDescriptor
0x180024335  lea     r8, [rbp+pDacl]; pDacl
0x180024339  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18002433d  call    cs:__imp_GetSecurityDescriptorDacl
0x180024343  test    eax, eax
0x180024345  jz      short loc_1800243A4
0x180024347  cmp     [rbp+bDaclPresent], 0
0x18002434b  jz      short loc_18002439C
0x18002434d  mov     rcx, [rbp+pDacl]; pAcl
0x180024351  test    rcx, rcx
0x180024354  jz      short loc_18002439C
0x180024356  lea     r8, [rbp+pAce]; pAce
0x18002435a  mov     edx, esi; dwAceIndex
0x18002435c  call    cs:__imp_GetAce
0x180024362  test    eax, eax
0x180024364  jz      short loc_1800243A4
0x180024366  mov     rax, [rbp+pAce]
0x18002436a  test    byte ptr [rax+1], 1Fh
0x18002436e  jz      short loc_180024377
0x180024370  mov     ecx, 57h ; 'W'
0x180024375  jmp     short loc_18002439E
0x180024377  mov     rcx, [rbp+pDacl]; pAcl
0x18002437b  mov     edx, esi; dwAceIndex
0x18002437d  call    cs:__imp_DeleteAce
0x180024383  test    eax, eax
0x180024385  jz      short loc_1800243A4
0x180024387  mov     r8, rbx; pSecurityDescriptor
0x18002438a  mov     edx, 4; SecurityInformation
0x18002438f  mov     rcx, rdi; lpFileName
0x180024392  call    cs:__imp_SetFileSecurityW
0x180024398  test    eax, eax
0x18002439a  jz      short loc_1800243A4
0x18002439c  xor     ecx, ecx; dwErrCode
0x18002439e  call    cs:__imp_SetLastError
0x1800243a4  mov     rcx, rbx; hMem
0x1800243a7  call    cs:__imp_LocalFree
0x1800243ad  call    cs:__imp_GetLastError
0x1800243b3  mov     rbx, [rsp+50h+arg_8]
0x1800243b8  add     rsp, 50h
0x1800243bc  pop     rdi
0x1800243bd  pop     rsi
0x1800243be  pop     rbp
0x1800243bf  retn
```

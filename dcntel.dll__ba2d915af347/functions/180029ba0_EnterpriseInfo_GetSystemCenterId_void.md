# EnterpriseInfo::GetSystemCenterId(void)

- ea: `0x180029ba0`
- end: `0x180029e4a`
- name: `?GetSystemCenterId@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `682`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180009f14`
- `0x180014f2c`
- `0x1800157b8`
- `0x180029ba0`
- `0x18002a690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029d02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029d02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029cf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029df3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029cf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029df3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e01`
- `logoncli!DsGetDcNameW` at `0x180029c53`
- `logoncli!DsGetDcNameW` at `0x180029c80`
- `logoncli!DsGetDcNameW` at `0x180029c53`
- `logoncli!DsGetDcNameW` at `0x180029c80`
- `bcrypt!BCryptFinishHash` at `0x180029d73`
- `bcrypt!BCryptFinishHash` at `0x180029d73`
- `bcrypt!BCryptHashData` at `0x180029d55`
- `bcrypt!BCryptHashData` at `0x180029d55`
- `bcrypt!BCryptCreateHash` at `0x180029d33`
- `bcrypt!BCryptCreateHash` at `0x180029d33`
- `bcrypt!BCryptGetProperty` at `0x180029ce2`
- `bcrypt!BCryptGetProperty` at `0x180029ce2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180029cb0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180029cb0`
- `CRYPT32!CryptBinaryToStringW` at `0x180029d98`
- `CRYPT32!CryptBinaryToStringW` at `0x180029d98`
- `netutils!NetApiBufferFree` at `0x180029e11`
- `netutils!NetApiBufferFree` at `0x180029e21`
- `netutils!NetApiBufferFree` at `0x180029e11`
- `netutils!NetApiBufferFree` at `0x180029e21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _DOMAIN_CONTROLLER_INFOW *__fastcall EnterpriseInfo::GetSystemCenterId(
        __int64 a1,
        struct _DOMAIN_CONTROLLER_INFOW *a2)
{
  unsigned __int16 v3; // r8
  bool v4; // al
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  UCHAR *v7; // r14
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  char *DomainControllerName; // rsi
  __int64 v11; // rbx
  HANDLE v12; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh]
  ULONG pcbResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchString; // [rsp+4Ch] [rbp-B4h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-A8h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-A0h] BYREF
  PDOMAIN_CONTROLLER_INFOW v21[3]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszString[504]; // [rsp+80h] [rbp-80h] BYREF

  v21[1] = a2;
  *(_OWORD *)&a2->DomainControllerName = 0;
  *(_QWORD *)&a2->DomainControllerAddressType = 0;
  *(_QWORD *)&a2->DomainGuid.Data2 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  v15 = 1;
  DomainControllerInfo = 0;
  v21[0] = 0;
  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  memset_0(pszString, 0, 0x3E8u);
  pcchString = 500;
  if ( !DsGetDcNameW(0, 0, 0, 0, 0x10u, &DomainControllerInfo)
    && !DsGetDcNameW(0, DomainControllerInfo->DnsForestName, 0, 0, 0x10u, v21) )
  {
    v4 = IsWindowsVersionOrGreater(6u, 2u, v3);
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 32 * v4) >= 0
      && BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
    {
      v5 = *(_DWORD *)pbOutput;
      ProcessHeap = GetProcessHeap();
      v7 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v5);
      if ( v7 )
      {
        if ( BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0) >= 0
          && BCryptHashData(phHash, (PUCHAR)&v21[0]->DomainGuid, 0x10u, 0) >= 0
          && BCryptFinishHash(phHash, v7, *(ULONG *)pbOutput, 0) >= 0
          && CryptBinaryToStringW(v7, *(DWORD *)pbOutput, 0x40000001u, pszString, &pcchString) )
        {
          v9 = -1;
          do
            ++v9;
          while ( pszString[v9] );
          if ( v9 > *(_QWORD *)&a2->DomainGuid.Data2 )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              (char **)a2,
              v9,
              v8,
              pszString);
          }
          else
          {
            if ( *(_QWORD *)&a2->DomainGuid.Data2 <= 7u )
              DomainControllerName = (char *)a2;
            else
              DomainControllerName = (char *)a2->DomainControllerName;
            *(_QWORD *)&a2->DomainControllerAddressType = v9;
            v11 = 2 * v9;
            memmove_0(DomainControllerName, pszString, 2 * v9);
            *(_WORD *)&DomainControllerName[v11] = 0;
          }
        }
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v7);
      }
    }
  }
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( v21[0] )
    NetApiBufferFree(v21[0]);
  return a2;
}

```

## disassembly

```asm
0x180029ba0  push    rbp
0x180029ba2  push    rbx
0x180029ba3  push    rsi
0x180029ba4  push    rdi
0x180029ba5  push    r14
0x180029ba7  push    r15
0x180029ba9  lea     rbp, [rsp-388h]
0x180029bb1  sub     rsp, 488h
0x180029bb8  mov     rax, cs:__security_cookie
0x180029bbf  xor     rax, rsp
0x180029bc2  mov     [rbp+3B0h+var_40], rax
0x180029bc9  mov     rdi, rdx
0x180029bcc  mov     [rsp+4B0h+var_440], rdx
0x180029bd1  xor     r15d, r15d
0x180029bd4  mov     [rsp+4B0h+var_46C], r15d
0x180029bd9  xorps   xmm0, xmm0
0x180029bdc  movups  xmmword ptr [rdx], xmm0
0x180029bdf  mov     [rdx+10h], r15
0x180029be3  mov     [rdx+18h], r15
0x180029be7  lea     ebx, [r15+1]
0x180029beb  mov     r8d, ebx
0x180029bee  lea     rdx, asc_1801B4764; "#"
0x180029bf5  mov     rcx, rdi
0x180029bf8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029bfd  mov     [rsp+4B0h+var_46C], ebx
0x180029c01  mov     [rsp+4B0h+var_450], r15
0x180029c06  mov     [rsp+4B0h+var_448], r15
0x180029c0b  mov     [rsp+4B0h+phAlgorithm], r15
0x180029c10  mov     [rsp+4B0h+phHash], r15
0x180029c15  mov     dword ptr [rsp+4B0h+pbOutput], r15d
0x180029c1a  mov     [rsp+4B0h+pcbResult], r15d
0x180029c1f  xor     edx, edx; Val
0x180029c21  mov     r8d, 3E8h; Size
0x180029c27  lea     rcx, [rbp+3B0h+pszString]; void *
0x180029c2b  call    memset_0
0x180029c30  mov     [rsp+4B0h+pcchString], 1F4h
0x180029c38  lea     rax, [rsp+4B0h+var_450]
0x180029c3d  mov     [rsp+4B0h+DomainControllerInfo], rax; DomainControllerInfo
0x180029c42  lea     esi, [rbx+0Fh]
0x180029c45  mov     [rsp+4B0h+Flags], esi; Flags
0x180029c49  xor     r9d, r9d; SiteName
0x180029c4c  xor     r8d, r8d; DomainGuid
0x180029c4f  xor     edx, edx; DomainName
0x180029c51  xor     ecx, ecx; ComputerName
0x180029c53  call    cs:__imp_DsGetDcNameW
0x180029c59  test    eax, eax
0x180029c5b  jnz     loc_180029E07
0x180029c61  lea     rax, [rsp+4B0h+var_448]
0x180029c66  mov     [rsp+4B0h+DomainControllerInfo], rax; DomainControllerInfo
0x180029c6b  mov     [rsp+4B0h+Flags], esi; Flags
0x180029c6f  xor     r9d, r9d; SiteName
0x180029c72  xor     r8d, r8d; DomainGuid
0x180029c75  mov     rdx, [rsp+4B0h+var_450]
0x180029c7a  mov     rdx, [rdx+30h]; DomainName
0x180029c7e  xor     ecx, ecx; ComputerName
0x180029c80  call    cs:__imp_DsGetDcNameW
0x180029c86  test    eax, eax
0x180029c88  jnz     loc_180029E07
0x180029c8e  lea     edx, [rbx+1]; unsigned __int16
0x180029c91  lea     ecx, [rbx+5]; unsigned __int16
0x180029c94  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180029c99  movzx   r9d, al
0x180029c9d  shl     r9d, 5; dwFlags
0x180029ca1  xor     r8d, r8d; pszImplementation
0x180029ca4  lea     rdx, pszAlgId; "SHA256"
0x180029cab  lea     rcx, [rsp+4B0h+phAlgorithm]; phAlgorithm
0x180029cb0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180029cb6  test    eax, eax
0x180029cb8  js      loc_180029E07
0x180029cbe  mov     dword ptr [rsp+4B0h+DomainControllerInfo], r15d; dwFlags
0x180029cc3  lea     rax, [rsp+4B0h+pcbResult]
0x180029cc8  mov     qword ptr [rsp+4B0h+Flags], rax; pcbResult
0x180029ccd  lea     r9d, [r15+4]; cbOutput
0x180029cd1  lea     r8, [rsp+4B0h+pbOutput]; pbOutput
0x180029cd6  lea     rdx, pszProperty; "HashDigestLength"
0x180029cdd  mov     rcx, [rsp+4B0h+phAlgorithm]; hObject
0x180029ce2  call    cs:__imp_BCryptGetProperty
0x180029ce8  test    eax, eax
0x180029cea  js      loc_180029E07
0x180029cf0  mov     ebx, dword ptr [rsp+4B0h+pbOutput]
0x180029cf4  call    cs:__imp_GetProcessHeap
0x180029cfa  mov     r8d, ebx; dwBytes
0x180029cfd  xor     edx, edx; dwFlags
0x180029cff  mov     rcx, rax; hHeap
0x180029d02  call    cs:__imp_HeapAlloc
0x180029d08  mov     r14, rax
0x180029d0b  test    rax, rax
0x180029d0e  jz      loc_180029E07
0x180029d14  mov     [rsp+4B0h+dwFlags], r15d; dwFlags
0x180029d19  mov     dword ptr [rsp+4B0h+DomainControllerInfo], r15d; cbSecret
0x180029d1e  mov     qword ptr [rsp+4B0h+Flags], r15; pbSecret
0x180029d23  xor     r9d, r9d; cbHashObject
0x180029d26  xor     r8d, r8d; pbHashObject
0x180029d29  lea     rdx, [rsp+4B0h+phHash]; phHash
0x180029d2e  mov     rcx, [rsp+4B0h+phAlgorithm]; hAlgorithm
0x180029d33  call    cs:__imp_BCryptCreateHash
0x180029d39  test    eax, eax
0x180029d3b  js      loc_180029DF3
0x180029d41  mov     rdx, [rsp+4B0h+var_448]
0x180029d46  add     rdx, 14h; pbInput
0x180029d4a  xor     r9d, r9d; dwFlags
0x180029d4d  mov     r8d, esi; cbInput
0x180029d50  mov     rcx, [rsp+4B0h+phHash]; hHash
0x180029d55  call    cs:__imp_BCryptHashData
0x180029d5b  test    eax, eax
0x180029d5d  js      loc_180029DF3
0x180029d63  xor     r9d, r9d; dwFlags
0x180029d66  mov     r8d, dword ptr [rsp+4B0h+pbOutput]; cbOutput
0x180029d6b  mov     rdx, r14; pbOutput
0x180029d6e  mov     rcx, [rsp+4B0h+phHash]; hHash
0x180029d73  call    cs:__imp_BCryptFinishHash
0x180029d79  test    eax, eax
0x180029d7b  js      short loc_180029DF3
0x180029d7d  lea     rax, [rsp+4B0h+pcchString]
0x180029d82  mov     qword ptr [rsp+4B0h+Flags], rax; pcchString
0x180029d87  lea     r9, [rbp+3B0h+pszString]; pszString
0x180029d8b  mov     r8d, 40000001h; dwFlags
0x180029d91  mov     edx, dword ptr [rsp+4B0h+pbOutput]; cbBinary
0x180029d95  mov     rcx, r14; pbBinary
0x180029d98  call    cs:__imp_CryptBinaryToStringW
0x180029d9e  test    eax, eax
0x180029da0  jz      short loc_180029DF3
0x180029da2  lea     rax, [rbp+3B0h+pszString]
0x180029da6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180029daa  inc     rdx
0x180029dad  cmp     [rax+rdx*2], r15w
0x180029db2  jnz     short loc_180029DAA
0x180029db4  cmp     rdx, [rdi+18h]
0x180029db8  ja      short loc_180029DE7
0x180029dba  cmp     qword ptr [rdi+18h], 7
0x180029dbf  jbe     short loc_180029DC6
0x180029dc1  mov     rsi, [rdi]
0x180029dc4  jmp     short loc_180029DC9
0x180029dc6  mov     rsi, rdi
0x180029dc9  mov     [rdi+10h], rdx
0x180029dcd  lea     rbx, [rdx+rdx]
0x180029dd1  mov     r8, rbx; Size
0x180029dd4  lea     rdx, [rbp+3B0h+pszString]; Src
0x180029dd8  mov     rcx, rsi; void *
0x180029ddb  call    memmove_0
0x180029de0  mov     [rbx+rsi], r15w
0x180029de5  jmp     short loc_180029DF3
0x180029de7  lea     r9, [rbp+3B0h+pszString]
0x180029deb  mov     rcx, rdi
0x180029dee  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180029df3  call    cs:__imp_GetProcessHeap
0x180029df9  mov     rcx, rax; hHeap
0x180029dfc  mov     r8, r14; lpMem
0x180029dff  xor     edx, edx; dwFlags
0x180029e01  call    cs:__imp_HeapFree
0x180029e07  mov     rcx, [rsp+4B0h+var_450]; Buffer
0x180029e0c  test    rcx, rcx
0x180029e0f  jz      short loc_180029E17
0x180029e11  call    cs:__imp_NetApiBufferFree
0x180029e17  mov     rcx, [rsp+4B0h+var_448]; Buffer
0x180029e1c  test    rcx, rcx
0x180029e1f  jz      short loc_180029E27
0x180029e21  call    cs:__imp_NetApiBufferFree
0x180029e27  mov     rax, rdi
0x180029e2a  mov     rcx, [rbp+3B0h+var_40]
0x180029e31  xor     rcx, rsp; StackCookie
0x180029e34  call    __security_check_cookie
0x180029e39  add     rsp, 488h
0x180029e40  pop     r15
0x180029e42  pop     r14
0x180029e44  pop     rdi
0x180029e45  pop     rsi
0x180029e46  pop     rbx
0x180029e47  pop     rbp
0x180029e48  retn
```

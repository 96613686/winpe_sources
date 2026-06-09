# LsaDbrCreateTrustedDomain(void *,_LSAPR_TRUST_INFORMATION *,ulong,void * *)

- ea: `0x18000cf30`
- end: `0x18000cff9`
- name: `?LsaDbrCreateTrustedDomain@@YAJPEAXPEAU_LSAPR_TRUST_INFORMATION@@KPEAPEAX@Z`
- size: `201`
- prototype: `__int64 __fastcall(void *, struct _LSA_TRUST_INFORMATION *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000fb10`

## callees

- `0x18000a080`
- `0x18000a2bc`
- `0x18000cf30`
- `0x180035c68`
- `0x180035e40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfdd`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000cf95`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000cf95`

## pseudocode

```c
__int64 __fastcall LsaDbrCreateTrustedDomain(_BYTE *a1, struct _LSA_TRUST_INFORMATION *a2, unsigned int a3, void **a4)
{
  int TrustedDomain2; // ebx
  LSA_UNICODE_STRING Name; // xmm0
  LSA_UNICODE_STRING v11; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-38h] BYREF
  _OWORD v13[2]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+C0h] [rbp+48h] BYREF

  if ( LsaDbpValidateTrustedDomainInformationBasic(a2) && LsapValidateAccessMask(&v14) )
  {
    TrustedDomain2 = LsaDbpCheckIfCallerHasAccessToTDOs(a1);
    if ( TrustedDomain2 >= 0 )
    {
      v11 = 0;
      *(_OWORD *)hMem = 0;
      memset(v13, 0, 24);
      TrustedDomain2 = LsapRpcCopyUnicodeString(0, hMem, a2);
      if ( TrustedDomain2 >= 0 )
      {
        Name = a2->Name;
        *(_QWORD *)&v13[0] = a2->Sid;
        DWORD2(v13[0]) = 2;
        *(_QWORD *)((char *)v13 + 12) = 1;
        v11 = Name;
        TrustedDomain2 = LsaDbpCreateTrustedDomain2(a1, (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)&v11, 0, a3, a4);
        LocalFree(hMem[1]);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)TrustedDomain2;
}

```

## disassembly

```asm
0x18000cf30  push    rbp
0x18000cf32  push    rbx
0x18000cf33  push    rsi
0x18000cf34  push    rdi
0x18000cf35  push    r14
0x18000cf37  push    r15
0x18000cf39  mov     rbp, rsp
0x18000cf3c  sub     rsp, 78h
0x18000cf40  mov     rsi, rcx
0x18000cf43  mov     r14, r9
0x18000cf46  mov     rcx, rdx; struct _LSA_TRUST_INFORMATION *
0x18000cf49  mov     r15d, r8d
0x18000cf4c  mov     rdi, rdx
0x18000cf4f  call    ?LsaDbpValidateTrustedDomainInformationBasic@@YAEPEAU_LSA_TRUST_INFORMATION@@@Z; LsaDbpValidateTrustedDomainInformationBasic(_LSA_TRUST_INFORMATION *)
0x18000cf54  test    al, al
0x18000cf56  jz      loc_18000CFE5
0x18000cf5c  lea     rcx, [rbp+arg_10]; unsigned int *
0x18000cf60  call    ?LsapValidateAccessMask@@YAEPEAK@Z; LsapValidateAccessMask(ulong *)
0x18000cf65  test    al, al
0x18000cf67  jz      short loc_18000CFE5
0x18000cf69  mov     rcx, rsi; void *
0x18000cf6c  call    ?LsaDbpCheckIfCallerHasAccessToTDOs@@YAJQEAX@Z; LsaDbpCheckIfCallerHasAccessToTDOs(void * const)
0x18000cf71  mov     ebx, eax
0x18000cf73  test    eax, eax
0x18000cf75  js      short loc_18000CFEA
0x18000cf77  xorps   xmm0, xmm0
0x18000cf7a  lea     rdx, [rbp+hMem]
0x18000cf7e  xor     eax, eax
0x18000cf80  mov     r8, rdi
0x18000cf83  xor     ecx, ecx
0x18000cf85  mov     [rbp+var_18], rax
0x18000cf89  movups  [rbp+var_48], xmm0
0x18000cf8d  movups  xmmword ptr [rbp+hMem], xmm0
0x18000cf91  movups  [rbp+var_28], xmm0
0x18000cf95  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000cf9b  mov     ebx, eax
0x18000cf9d  test    eax, eax
0x18000cf9f  js      short loc_18000CFEA
0x18000cfa1  movups  xmm0, xmmword ptr [rdi]
0x18000cfa4  mov     rax, [rdi+10h]
0x18000cfa8  lea     rdx, [rbp+var_48]; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *
0x18000cfac  mov     r9d, r15d; unsigned int
0x18000cfaf  mov     qword ptr [rbp+var_28], rax
0x18000cfb3  xor     r8d, r8d; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *
0x18000cfb6  mov     dword ptr [rbp+var_28+8], 2
0x18000cfbd  mov     rcx, rsi; void *
0x18000cfc0  mov     qword ptr [rbp+var_28+0Ch], 1
0x18000cfc8  movdqu  [rbp+var_48], xmm0
0x18000cfcd  mov     [rsp+78h+var_58], r14; void **
0x18000cfd2  call    ?LsaDbpCreateTrustedDomain2@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION@@KPEAPEAX@Z; LsaDbpCreateTrustedDomain2(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *,ulong,void * *)
0x18000cfd7  mov     rcx, [rbp+hMem+8]; hMem
0x18000cfdb  mov     ebx, eax
0x18000cfdd  call    cs:__imp_LocalFree
0x18000cfe3  jmp     short loc_18000CFEA
0x18000cfe5  mov     ebx, 0C000000Dh
0x18000cfea  mov     eax, ebx
0x18000cfec  add     rsp, 78h
0x18000cff0  pop     r15
0x18000cff2  pop     r14
0x18000cff4  pop     rdi
0x18000cff5  pop     rsi
0x18000cff6  pop     rbx
0x18000cff7  pop     rbp
0x18000cff8  retn
```

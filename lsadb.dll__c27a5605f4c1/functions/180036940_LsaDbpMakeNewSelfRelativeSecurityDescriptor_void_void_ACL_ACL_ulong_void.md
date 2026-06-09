# LsaDbpMakeNewSelfRelativeSecurityDescriptor(void *,void *,_ACL *,_ACL *,ulong *,void * *)

- ea: `0x180036940`
- end: `0x180036a74`
- name: `?LsaDbpMakeNewSelfRelativeSecurityDescriptor@@YAJPEAX0PEAU_ACL@@1PEAKPEAPEAX@Z`
- size: `308`
- prototype: `__int64 __fastcall(PSID pOwner, PSID pGroup, PACL pDacl, PACL pSacl, LPDWORD lpdwBufferLength, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800115a8`
- `0x180036a7c`

## callees

- `0x180036940`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003698b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003698b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800369af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800369af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800369c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800369c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800369e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800369e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180036a05`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180036a05`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180036a14`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180036a14`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180036a41`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180036a41`
- `LSASRV!LsapAllocateLsaHeap` at `0x180036a1f`
- `LSASRV!LsapAllocateLsaHeap` at `0x180036a1f`
- `LSASRV!LsapFreeLsaHeap` at `0x180036a58`
- `LSASRV!LsapFreeLsaHeap` at `0x180036a58`

## pseudocode

```c
__int64 __fastcall LsaDbpMakeNewSelfRelativeSecurityDescriptor(
        PSID pOwner,
        PSID pGroup,
        PACL pDacl,
        PACL pSacl,
        LPDWORD lpdwBufferLength,
        void **a6)
{
  unsigned int v10; // ebx
  DWORD SecurityDescriptorLength; // eax
  void *LsaHeap; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v17; // [rsp+40h] [rbp-48h]

  v17 = 0;
  *lpdwBufferLength = 0;
  *a6 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    && (!pOwner || SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0))
    && (!pGroup || SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0))
    && (!pDacl || SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0))
    && (!pSacl || SetSecurityDescriptorSacl(pSecurityDescriptor, 1, pSacl, 0)) )
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    *lpdwBufferLength = SecurityDescriptorLength;
    LsaHeap = (void *)LsapAllocateLsaHeap(SecurityDescriptorLength);
    *a6 = LsaHeap;
    if ( LsaHeap )
    {
      v10 = 0;
      if ( !MakeSelfRelativeSD(pSecurityDescriptor, LsaHeap, lpdwBufferLength) )
      {
        v10 = -1073741823;
        if ( *a6 )
        {
          LsapFreeLsaHeap(*a6, v13, v14);
          *a6 = 0;
        }
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return v10;
}

```

## disassembly

```asm
0x180036940  push    rbx
0x180036942  push    rbp
0x180036943  push    rsi
0x180036944  push    rdi
0x180036945  push    r14
0x180036947  push    r15
0x180036949  sub     rsp, 58h
0x18003694d  mov     r15, [rsp+88h+lpdwBufferLength]
0x180036955  xor     eax, eax
0x180036957  mov     rdi, [rsp+88h+arg_28]
0x18003695f  xorps   xmm0, xmm0
0x180036962  mov     rsi, rdx
0x180036965  mov     [rsp+88h+var_48], rax
0x18003696a  mov     rbx, rcx
0x18003696d  mov     r14, r9
0x180036970  lea     edx, [rax+1]; dwRevision
0x180036973  mov     [r15], eax
0x180036976  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x18003697b  mov     [rdi], rax
0x18003697e  mov     rbp, r8
0x180036981  movups  [rsp+88h+pSecurityDescriptor], xmm0
0x180036986  movups  [rsp+88h+var_58], xmm0
0x18003698b  call    cs:__imp_InitializeSecurityDescriptor
0x180036991  test    eax, eax
0x180036993  jnz     short loc_18003699F
0x180036995  mov     ebx, 0C0000001h
0x18003699a  jmp     loc_180036A65
0x18003699f  test    rbx, rbx
0x1800369a2  jz      short loc_1800369B9
0x1800369a4  xor     r8d, r8d; bOwnerDefaulted
0x1800369a7  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1800369ac  mov     rdx, rbx; pOwner
0x1800369af  call    cs:__imp_SetSecurityDescriptorOwner
0x1800369b5  test    eax, eax
0x1800369b7  jz      short loc_180036995
0x1800369b9  test    rsi, rsi
0x1800369bc  jz      short loc_1800369D3
0x1800369be  xor     r8d, r8d; bGroupDefaulted
0x1800369c1  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1800369c6  mov     rdx, rsi; pGroup
0x1800369c9  call    cs:__imp_SetSecurityDescriptorGroup
0x1800369cf  test    eax, eax
0x1800369d1  jz      short loc_180036995
0x1800369d3  test    rbp, rbp
0x1800369d6  jz      short loc_1800369F1
0x1800369d8  xor     r9d, r9d; bDaclDefaulted
0x1800369db  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1800369e0  mov     r8, rbp; pDacl
0x1800369e3  lea     edx, [r9+1]; bDaclPresent
0x1800369e7  call    cs:__imp_SetSecurityDescriptorDacl
0x1800369ed  test    eax, eax
0x1800369ef  jz      short loc_180036995
0x1800369f1  test    r14, r14
0x1800369f4  jz      short loc_180036A0F
0x1800369f6  xor     r9d, r9d; bSaclDefaulted
0x1800369f9  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1800369fe  mov     r8, r14; pSacl
0x180036a01  lea     edx, [r9+1]; bSaclPresent
0x180036a05  call    cs:__imp_SetSecurityDescriptorSacl
0x180036a0b  test    eax, eax
0x180036a0d  jz      short loc_180036995
0x180036a0f  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x180036a14  call    cs:__imp_GetSecurityDescriptorLength
0x180036a1a  mov     ecx, eax
0x180036a1c  mov     [r15], ecx
0x180036a1f  call    cs:__imp_LsapAllocateLsaHeap
0x180036a25  mov     [rdi], rax
0x180036a28  test    rax, rax
0x180036a2b  jnz     short loc_180036A34
0x180036a2d  mov     ebx, 0C000009Ah
0x180036a32  jmp     short loc_180036A65
0x180036a34  mov     r8, r15; lpdwBufferLength
0x180036a37  lea     rcx, [rsp+88h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180036a3c  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180036a3f  xor     ebx, ebx
0x180036a41  call    cs:__imp_MakeSelfRelativeSD
0x180036a47  test    eax, eax
0x180036a49  jnz     short loc_180036A65
0x180036a4b  mov     rcx, [rdi]
0x180036a4e  mov     ebx, 0C0000001h
0x180036a53  test    rcx, rcx
0x180036a56  jz      short loc_180036A65
0x180036a58  call    cs:__imp_LsapFreeLsaHeap
0x180036a5e  mov     qword ptr [rdi], 0
0x180036a65  mov     eax, ebx
0x180036a67  add     rsp, 58h
0x180036a6b  pop     r15
0x180036a6d  pop     r14
0x180036a6f  pop     rdi
0x180036a70  pop     rsi
0x180036a71  pop     rbp
0x180036a72  pop     rbx
0x180036a73  retn
```

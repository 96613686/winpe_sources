# _IsDaclPrivateForUser(_ACL *,ushort const *)

- ea: `0x180063af0`
- end: `0x180063be4`
- name: `?_IsDaclPrivateForUser@@YAHPEAU_ACL@@PEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(PACL pacl, LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063ca0`
- `0x180063ef0`

## callees

- `0x180063af0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063b64`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063b2f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063b2f`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180063b45`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180063b9a`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180063b45`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180063b9a`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180063b5a`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180063bb2`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180063b5a`
- `ADVAPI32!GetEffectiveRightsFromAclW` at `0x180063bb2`

## pseudocode

```c
__int64 __fastcall _IsDaclPrivateForUser(PACL pacl, LPCWSTR StringSid)
{
  unsigned int v2; // edi
  int v4; // r14d
  __int64 i; // r15
  PSID Sid; // [rsp+20h] [rbp-30h] BYREF
  _TRUSTEE_W pTrustee; // [rsp+28h] [rbp-28h] BYREF
  DWORD pAccessRights; // [rsp+90h] [rbp+40h] BYREF
  DWORD v10; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v11; // [rsp+A8h] [rbp+58h]

  v2 = 0;
  v11 = 0;
  if ( pacl )
  {
    Sid = 0;
    pAccessRights = 0;
    memset(&pTrustee, 0, sizeof(pTrustee));
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
    {
      BuildTrusteeWithSidW(&pTrustee, Sid);
      pTrustee.TrusteeType = TRUSTEE_IS_USER;
      GetEffectiveRightsFromAclW(pacl, &pTrustee, &pAccessRights);
      LocalFree(Sid);
    }
    if ( (pAccessRights & 0x1F01FF) == 0x1F01FF )
    {
      v4 = 0;
      for ( i = 0; i != 4; ++i )
      {
        v10 = 0;
        BuildTrusteeWithSidW(&pTrustee, (&off_18007B870)[2 * i]);
        pTrustee.TrusteeType = (TRUSTEE_TYPE)(&off_18007B870)[2 * i + 1];
        GetEffectiveRightsFromAclW(pacl, &pTrustee, &v10);
        v4 |= v10;
      }
      v2 = v11;
      if ( (v4 & 0xFFEDFFFF) == 0 )
        return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180063af0  push    rbp
0x180063af2  push    rbx
0x180063af3  push    rsi
0x180063af4  push    rdi
0x180063af5  push    r13
0x180063af7  push    r14
0x180063af9  push    r15
0x180063afb  mov     rbp, rsp
0x180063afe  sub     rsp, 50h
0x180063b02  xor     edi, edi
0x180063b04  mov     rax, rdx
0x180063b07  mov     [rbp+arg_18], edi
0x180063b0a  mov     rsi, rcx
0x180063b0d  test    rcx, rcx
0x180063b10  jz      loc_180063BD3
0x180063b16  xorps   xmm0, xmm0
0x180063b19  mov     [rbp+Sid], rdi
0x180063b1d  lea     rdx, [rbp+Sid]; Sid
0x180063b21  mov     [rbp+pAccessRights], edi
0x180063b24  mov     rcx, rax; StringSid
0x180063b27  movups  xmmword ptr [rbp+pTrustee.pMultipleTrustee], xmm0
0x180063b2b  movups  xmmword ptr [rbp+pTrustee.TrusteeType], xmm0
0x180063b2f  call    cs:__imp_ConvertStringSidToSidW
0x180063b35  lea     r13d, [rdi+1]
0x180063b39  test    eax, eax
0x180063b3b  jz      short loc_180063B6A
0x180063b3d  mov     rdx, [rbp+Sid]; pSid
0x180063b41  lea     rcx, [rbp+pTrustee]; pTrustee
0x180063b45  call    cs:__imp_BuildTrusteeWithSidW
0x180063b4b  lea     r8, [rbp+pAccessRights]; pAccessRights
0x180063b4f  mov     [rbp+pTrustee.TrusteeType], r13d
0x180063b53  lea     rdx, [rbp+pTrustee]; pTrustee
0x180063b57  mov     rcx, rsi; pacl
0x180063b5a  call    cs:__imp_GetEffectiveRightsFromAclW
0x180063b60  mov     rcx, [rbp+Sid]; hMem
0x180063b64  call    cs:__imp_LocalFree
0x180063b6a  mov     eax, [rbp+pAccessRights]
0x180063b6d  mov     ecx, 1F01FFh
0x180063b72  and     eax, ecx
0x180063b74  cmp     eax, ecx
0x180063b76  jnz     short loc_180063BD3
0x180063b78  xor     r14d, r14d
0x180063b7b  lea     rdi, off_18007B870
0x180063b82  xor     r15d, r15d
0x180063b85  mov     rbx, r15
0x180063b88  mov     [rbp+arg_10], 0
0x180063b8f  add     rbx, rbx
0x180063b92  lea     rcx, [rbp+pTrustee]; pTrustee
0x180063b96  mov     rdx, [rdi+rbx*8]; pSid
0x180063b9a  call    cs:__imp_BuildTrusteeWithSidW
0x180063ba0  mov     eax, [rdi+rbx*8+8]
0x180063ba4  lea     r8, [rbp+arg_10]; pAccessRights
0x180063ba8  lea     rdx, [rbp+pTrustee]; pTrustee
0x180063bac  mov     [rbp+pTrustee.TrusteeType], eax
0x180063baf  mov     rcx, rsi; pacl
0x180063bb2  call    cs:__imp_GetEffectiveRightsFromAclW
0x180063bb8  or      r14d, [rbp+arg_10]
0x180063bbc  add     r15, r13
0x180063bbf  cmp     r15, 4
0x180063bc3  jnz     short loc_180063B85
0x180063bc5  mov     edi, [rbp+arg_18]
0x180063bc8  test    r14d, 0FFEDFFFFh
0x180063bcf  cmovz   edi, r13d
0x180063bd3  mov     eax, edi
0x180063bd5  add     rsp, 50h
0x180063bd9  pop     r15
0x180063bdb  pop     r14
0x180063bdd  pop     r13
0x180063bdf  pop     rdi
0x180063be0  pop     rsi
0x180063be1  pop     rbx
0x180063be2  pop     rbp
0x180063be3  retn
```

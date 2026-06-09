# LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)

- ea: `0x18000beb4`
- end: `0x18000bf69`
- name: `?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUST_INFORMATION *, struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2bc`
- `0x18000af18`
- `0x18000b7c8`
- `0x18000bf70`
- `0x18000bff4`
- `0x18000c1ac`
- `0x1800159b0`
- `0x180019db4`
- `0x18001a6d8`

## callees

- `0x180009ec4`
- `0x18000beb4`

## import_xrefs

- `LSASRV!LsapCompareDomainNames` at `0x18000bf2d`
- `LSASRV!LsapCompareDomainNames` at `0x18000bf2d`
- `ntdll!RtlEqualSid` at `0x18000bf04`
- `ntdll!RtlEqualSid` at `0x18000bf04`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupEntryTrustedDomainList(
        struct _LSAPR_TRUST_INFORMATION *a1,
        struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **a2)
{
  struct _LSAPR_TRUST_INFORMATION *v3; // r15
  int v4; // ebp
  __int64 v5; // r12
  HLOCAL *v6; // rbx
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v7; // rdi
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v8; // rsi
  HLOCAL v9; // rdx

  v3 = a1;
  LOBYTE(a1) = 1;
  v4 = LsaDbpBuildTrustedDomainCacheIfNecessary((__int64)a1, 0);
  if ( v4 >= 0 )
  {
    v5 = *((_QWORD *)v3 + 2);
    v6 = (HLOCAL *)hMem;
    v7 = 0;
    v8 = 0;
    while ( v6 != &hMem )
    {
      if ( v5 )
      {
        v9 = v6[6];
        if ( v9 && RtlEqualSid(*((PSID *)v3 + 2), v9) )
        {
LABEL_6:
          v8 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)v6;
          break;
        }
      }
      else if ( (unsigned __int8)LsapCompareDomainNames(v3, v6 + 2, v6 + 4) )
      {
        if ( v6[6] )
          goto LABEL_6;
        v7 = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)v6;
      }
      v6 = (HLOCAL *)*v6;
    }
    if ( v8 )
      v7 = v8;
    if ( v7 )
    {
      *a2 = v7;
    }
    else
    {
      *a2 = 0;
      return (unsigned int)-1073741601;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000beb4  push    rbx
0x18000beb6  push    rbp
0x18000beb7  push    rsi
0x18000beb8  push    rdi
0x18000beb9  push    r12
0x18000bebb  push    r13
0x18000bebd  push    r14
0x18000bebf  push    r15
0x18000bec1  sub     rsp, 28h
0x18000bec5  mov     r14, rdx
0x18000bec8  mov     r15, rcx
0x18000becb  xor     edx, edx; unsigned __int8
0x18000becd  mov     cl, 1; unsigned __int8
0x18000becf  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18000bed4  mov     ebp, eax
0x18000bed6  test    eax, eax
0x18000bed8  js      short loc_18000BF56
0x18000beda  mov     r12, [r15+10h]
0x18000bede  lea     r13, hMem
0x18000bee5  mov     rbx, cs:hMem
0x18000beec  xor     edi, edi
0x18000beee  xor     esi, esi
0x18000bef0  jmp     short loc_18000BF43
0x18000bef2  test    r12, r12
0x18000bef5  jz      short loc_18000BF22
0x18000bef7  mov     rdx, [rbx+30h]; Sid2
0x18000befb  test    rdx, rdx
0x18000befe  jz      short loc_18000BF40
0x18000bf00  mov     rcx, [r15+10h]; Sid1
0x18000bf04  call    cs:__imp_RtlEqualSid
0x18000bf0a  test    al, al
0x18000bf0c  jz      short loc_18000BF40
0x18000bf0e  mov     rsi, rbx
0x18000bf11  test    rsi, rsi
0x18000bf14  cmovnz  rdi, rsi
0x18000bf18  test    rdi, rdi
0x18000bf1b  jz      short loc_18000BF4A
0x18000bf1d  mov     [r14], rdi
0x18000bf20  jmp     short loc_18000BF56
0x18000bf22  lea     r8, [rbx+20h]
0x18000bf26  mov     rcx, r15
0x18000bf29  lea     rdx, [rbx+10h]
0x18000bf2d  call    cs:__imp_LsapCompareDomainNames
0x18000bf33  test    al, al
0x18000bf35  jz      short loc_18000BF40
0x18000bf37  cmp     [rbx+30h], rsi
0x18000bf3b  jnz     short loc_18000BF0E
0x18000bf3d  mov     rdi, rbx
0x18000bf40  mov     rbx, [rbx]
0x18000bf43  cmp     rbx, r13
0x18000bf46  jnz     short loc_18000BEF2
0x18000bf48  jmp     short loc_18000BF11
0x18000bf4a  mov     qword ptr [r14], 0
0x18000bf51  mov     ebp, 0C00000DFh
0x18000bf56  mov     eax, ebp
0x18000bf58  add     rsp, 28h
0x18000bf5c  pop     r15
0x18000bf5e  pop     r14
0x18000bf60  pop     r13
0x18000bf62  pop     r12
0x18000bf64  pop     rdi
0x18000bf65  pop     rsi
0x18000bf66  pop     rbp
0x18000bf67  pop     rbx
0x18000bf68  retn
```

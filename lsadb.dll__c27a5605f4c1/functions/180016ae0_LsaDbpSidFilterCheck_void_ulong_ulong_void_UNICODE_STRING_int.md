# LsaDbpSidFilterCheck(void *,ulong,ulong *,void *,_UNICODE_STRING *,int *)

- ea: `0x180016ae0`
- end: `0x180016c01`
- name: `?LsaDbpSidFilterCheck@@YAJPEAXKPEAK0PEAU_UNICODE_STRING@@PEAH@Z`
- size: `289`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, void *@<r9>, struct _UNICODE_STRING *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c0e0`
- `0x18000c8ec`
- `0x180016ae0`
- `0x180026674`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180016b4f`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180016baf`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180016b4f`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180016baf`

## pseudocode

```c
__int64 __fastcall LsaDbpSidFilterCheck(
        void *a1,
        unsigned int a2,
        unsigned int *a3,
        void *a4,
        struct _UNICODE_STRING *String1)
{
  __int64 v5; // rdi
  unsigned int *v7; // rbx
  __int64 result; // rax
  BOOL pfEqual; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v7 = a3;
  if ( (*((_BYTE *)&LsapSidFilteringMatrix + 4 * a2) & *(_BYTE *)a3 & 2) != 0 )
  {
    LOBYTE(a3) = 1;
    result = LsaDbpForestTrustFindMatch(0, a1, a3, 0, 0);
    if ( (_DWORD)result == -1073741198 )
      goto LABEL_10;
    if ( (int)result < 0 )
      return result;
    if ( (_DWORD)v5 == 1 )
    {
      pfEqual = 0;
      if ( a4 && EqualDomainSid(a1, a4, &pfEqual) && pfEqual )
LABEL_10:
        *v7 &= ~2u;
    }
  }
  if ( (*((_BYTE *)&LsapSidFilteringMatrix + 4 * v5) & *(_BYTE *)v7 & 4) != 0
    && ((((_DWORD)v5 - 1) & 0xFFFFFFFC) != 0 || (_DWORD)v5 == 3)
    && !LsaDbpNoMoreWin2KForest() )
  {
    *v7 &= ~4u;
  }
  if ( (*((_BYTE *)&LsapSidFilteringMatrix + 4 * v5) & *(_BYTE *)v7 & 0x10) != 0 )
  {
    pfEqual = 0;
    if ( a4 && EqualDomainSid(a1, a4, &pfEqual) && pfEqual )
      *v7 &= ~0x10u;
  }
  if ( (*((_BYTE *)&LsapSidFilteringMatrix + 4 * v5) & *(_BYTE *)v7 & 0x20) == 0 )
    return 0;
  result = LsaDbpSidOnFtInfo(String1, a1);
  if ( (int)result >= 0 )
  {
    *v7 &= ~0x20u;
    return 0;
  }
  if ( (_DWORD)result == -1073741198 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180016ae0  push    rbx
0x180016ae2  push    rbp
0x180016ae3  push    rsi
0x180016ae4  push    rdi
0x180016ae5  push    r12
0x180016ae7  push    r14
0x180016ae9  sub     rsp, 38h
0x180016aed  mov     eax, [r8]
0x180016af0  lea     r12, ?LsapSidFilteringMatrix@@3QBKB; ulong const near * const LsapSidFilteringMatrix
0x180016af7  mov     edi, edx
0x180016af9  mov     rsi, r9
0x180016afc  mov     rbx, r8
0x180016aff  mov     r14, rcx
0x180016b02  and     eax, [r12+rdi*4]
0x180016b06  test    al, 2
0x180016b08  jz      short loc_180016B68
0x180016b0a  mov     rdx, rcx
0x180016b0d  mov     [rsp+68h+var_48], 0
0x180016b16  xor     ecx, ecx
0x180016b18  xor     r9d, r9d
0x180016b1b  mov     r8b, 1
0x180016b1e  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x180016b23  cmp     eax, 0C0000272h
0x180016b28  jz      short loc_180016B65
0x180016b2a  test    eax, eax
0x180016b2c  js      loc_180016BF4
0x180016b32  cmp     edi, 1
0x180016b35  jnz     short loc_180016B68
0x180016b37  mov     [rsp+68h+pfEqual], 0
0x180016b3f  test    rsi, rsi
0x180016b42  jz      short loc_180016B5F
0x180016b44  lea     r8, [rsp+68h+pfEqual]; pfEqual
0x180016b49  mov     rdx, rsi; pSid2
0x180016b4c  mov     rcx, r14; pSid1
0x180016b4f  call    cs:__imp_EqualDomainSid
0x180016b55  test    eax, eax
0x180016b57  jz      short loc_180016B5F
0x180016b59  mov     eax, [rsp+68h+pfEqual]
0x180016b5d  jmp     short loc_180016B61
0x180016b5f  xor     eax, eax
0x180016b61  test    eax, eax
0x180016b63  jz      short loc_180016B68
0x180016b65  and     dword ptr [rbx], 0FFFFFFFDh
0x180016b68  mov     eax, [rbx]
0x180016b6a  and     eax, [r12+rdi*4]
0x180016b6e  test    al, 4
0x180016b70  jz      short loc_180016B8D
0x180016b72  lea     eax, [rdi-1]
0x180016b75  test    eax, 0FFFFFFFCh
0x180016b7a  jnz     short loc_180016B81
0x180016b7c  cmp     edi, 3
0x180016b7f  jnz     short loc_180016B8D
0x180016b81  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x180016b86  test    al, al
0x180016b88  jnz     short loc_180016B8D
0x180016b8a  and     dword ptr [rbx], 0FFFFFFFBh
0x180016b8d  mov     eax, [rbx]
0x180016b8f  and     eax, [r12+rdi*4]
0x180016b93  test    al, 10h
0x180016b95  jz      short loc_180016BC8
0x180016b97  mov     [rsp+68h+pfEqual], 0
0x180016b9f  test    rsi, rsi
0x180016ba2  jz      short loc_180016BBF
0x180016ba4  lea     r8, [rsp+68h+pfEqual]; pfEqual
0x180016ba9  mov     rdx, rsi; pSid2
0x180016bac  mov     rcx, r14; pSid1
0x180016baf  call    cs:__imp_EqualDomainSid
0x180016bb5  test    eax, eax
0x180016bb7  jz      short loc_180016BBF
0x180016bb9  mov     eax, [rsp+68h+pfEqual]
0x180016bbd  jmp     short loc_180016BC1
0x180016bbf  xor     eax, eax
0x180016bc1  test    eax, eax
0x180016bc3  jz      short loc_180016BC8
0x180016bc5  and     dword ptr [rbx], 0FFFFFFEFh
0x180016bc8  mov     eax, [rbx]
0x180016bca  and     eax, [r12+rdi*4]
0x180016bce  test    al, 20h
0x180016bd0  jz      short loc_180016BF2
0x180016bd2  mov     rcx, [rsp+68h+String1]; String1
0x180016bda  mov     rdx, r14; void *
0x180016bdd  call    ?LsaDbpSidOnFtInfo@@YAJPEAU_UNICODE_STRING@@PEAX@Z; LsaDbpSidOnFtInfo(_UNICODE_STRING *,void *)
0x180016be2  test    eax, eax
0x180016be4  jns     short loc_180016BEF
0x180016be6  cmp     eax, 0C0000272h
0x180016beb  jz      short loc_180016BF2
0x180016bed  jmp     short loc_180016BF4
0x180016bef  and     dword ptr [rbx], 0FFFFFFDFh
0x180016bf2  xor     eax, eax
0x180016bf4  add     rsp, 38h
0x180016bf8  pop     r14
0x180016bfa  pop     r12
0x180016bfc  pop     rdi
0x180016bfd  pop     rsi
0x180016bfe  pop     rbp
0x180016bff  pop     rbx
0x180016c00  retn
```

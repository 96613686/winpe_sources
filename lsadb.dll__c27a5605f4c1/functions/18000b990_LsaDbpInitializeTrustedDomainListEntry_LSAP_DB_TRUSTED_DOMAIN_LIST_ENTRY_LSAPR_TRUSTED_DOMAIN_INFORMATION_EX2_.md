# LsaDbpInitializeTrustedDomainListEntry(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong)

- ea: `0x18000b990`
- end: `0x18000bae0`
- name: `?LsaDbpInitializeTrustedDomainListEntry@@YAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@K@Z`
- size: `336`
- prototype: `__int64 __fastcall(struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000b7c8`
- `0x18000bae8`
- `0x18000c4f0`

## callees

- `0x180001fb8`
- `0x18000b990`
- `0x18000c0e0`
- `0x180025ba8`
- `0x18003a110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bab7`
- `LSASRV!LsapRpcCopySid` at `0x18000b9f4`
- `LSASRV!LsapRpcCopySid` at `0x18000b9f4`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b9bf`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b9d9`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b9bf`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x18000b9d9`

## pseudocode

```c
__int64 __fastcall LsaDbpInitializeTrustedDomainListEntry(
        struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *a1,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *a2,
        int a3)
{
  int v6; // esi
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // ebp
  __int64 v10; // rcx
  __int64 v11; // rdx
  HLOCAL *v12; // rcx
  __int128 v13; // xmm0
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  memset_0(a1, 0, 0x78u);
  v6 = LsapRpcCopyUnicodeString(0, (char *)a1 + 16, a2);
  if ( v6 >= 0 )
  {
    v6 = LsapRpcCopyUnicodeString(0, (char *)a1 + 32, (char *)a2 + 16);
    if ( v6 >= 0 && (v8 = *((_QWORD *)a2 + 4)) != 0 )
      v6 = LsapRpcCopySid(0, (char *)a1 + 48, v8, v7);
    else
      *((_QWORD *)a1 + 6) = 0;
    if ( v6 >= 0 )
    {
      v9 = *((_DWORD *)a2 + 12);
      if ( !LsaDbpNoMoreWin2KForest() || (v9 & 8) == 0 )
      {
        v12 = (HLOCAL *)((char *)a1 + 48);
        goto LABEL_14;
      }
      v10 = *((_QWORD *)a2 + 7);
      if ( v10 )
      {
        v11 = *((unsigned int *)a2 + 13);
        if ( (_DWORD)v11 )
        {
          hMem = 0;
          v6 = NetpUnmarshalFtinfo2(v10, v11, &hMem);
          if ( v6 >= 0 )
          {
            v6 = LsaDbpForestTrustCacheInsert(
                   (struct _UNICODE_STRING *)a2,
                   *((void **)a2 + 4),
                   (struct _LSA_FOREST_TRUST_INFORMATION2 *)hMem,
                   0);
            LocalFree(hMem);
          }
        }
      }
    }
  }
  v12 = (HLOCAL *)((char *)a1 + 48);
  if ( v6 < 0 )
  {
    LocalFree(*v12);
    LocalFree(*((HLOCAL *)a1 + 3));
    LocalFree(*((HLOCAL *)a1 + 5));
    memset_0(a1, 0, 0x78u);
    return (unsigned int)v6;
  }
LABEL_14:
  v13 = *((_OWORD *)a1 + 2);
  *((_DWORD *)a1 + 16) = *((_DWORD *)a2 + 12);
  *((_DWORD *)a1 + 14) = *((_DWORD *)a2 + 10);
  *((_DWORD *)a1 + 15) = *((_DWORD *)a2 + 11);
  *((_QWORD *)a1 + 11) = *v12;
  *((_DWORD *)a1 + 25) = a3;
  *(_OWORD *)((char *)a1 + 72) = v13;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b990  mov     [rsp+arg_8], rbx
0x18000b995  mov     [rsp+arg_10], rbp
0x18000b99a  push    rsi
0x18000b99b  push    rdi
0x18000b99c  push    r14
0x18000b99e  sub     rsp, 20h
0x18000b9a2  mov     rdi, rdx
0x18000b9a5  mov     r14d, r8d
0x18000b9a8  xor     edx, edx; Val
0x18000b9aa  mov     rbx, rcx
0x18000b9ad  lea     r8d, [rdx+78h]; Size
0x18000b9b1  call    memset_0
0x18000b9b6  mov     r8, rdi
0x18000b9b9  lea     rdx, [rbx+10h]
0x18000b9bd  xor     ecx, ecx
0x18000b9bf  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b9c5  mov     esi, eax
0x18000b9c7  test    eax, eax
0x18000b9c9  js      loc_18000BA6A
0x18000b9cf  lea     r8, [rdi+10h]
0x18000b9d3  xor     ecx, ecx
0x18000b9d5  lea     rdx, [rbx+20h]
0x18000b9d9  call    cs:__imp_LsapRpcCopyUnicodeString
0x18000b9df  mov     esi, eax
0x18000b9e1  test    eax, eax
0x18000b9e3  js      short loc_18000B9FE
0x18000b9e5  mov     r8, [rdi+20h]
0x18000b9e9  test    r8, r8
0x18000b9ec  jz      short loc_18000B9FE
0x18000b9ee  lea     rdx, [rbx+30h]
0x18000b9f2  xor     ecx, ecx
0x18000b9f4  call    cs:__imp_LsapRpcCopySid
0x18000b9fa  mov     esi, eax
0x18000b9fc  jmp     short loc_18000BA06
0x18000b9fe  mov     qword ptr [rbx+30h], 0
0x18000ba06  test    esi, esi
0x18000ba08  js      short loc_18000BA6A
0x18000ba0a  mov     ebp, [rdi+30h]
0x18000ba0d  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x18000ba12  test    al, al
0x18000ba14  jz      loc_18000BA9A
0x18000ba1a  test    bpl, 8
0x18000ba1e  jz      short loc_18000BA9A
0x18000ba20  mov     rcx, [rdi+38h]
0x18000ba24  test    rcx, rcx
0x18000ba27  jz      short loc_18000BA6A
0x18000ba29  mov     edx, [rdi+34h]
0x18000ba2c  test    edx, edx
0x18000ba2e  jz      short loc_18000BA6A
0x18000ba30  lea     r8, [rsp+38h+hMem]
0x18000ba35  mov     [rsp+38h+hMem], 0
0x18000ba3e  call    NetpUnmarshalFtinfo2
0x18000ba43  mov     esi, eax
0x18000ba45  test    eax, eax
0x18000ba47  js      short loc_18000BA6A
0x18000ba49  mov     r8, [rsp+38h+hMem]; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x18000ba4e  xor     r9d, r9d; unsigned __int8
0x18000ba51  mov     rdx, [rdi+20h]; void *
0x18000ba55  mov     rcx, rdi; struct _UNICODE_STRING *
0x18000ba58  call    ?LsaDbpForestTrustCacheInsert@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@E@Z; LsaDbpForestTrustCacheInsert(_UNICODE_STRING *,void *,_LSA_FOREST_TRUST_INFORMATION2 *,uchar)
0x18000ba5d  mov     rcx, [rsp+38h+hMem]; hMem
0x18000ba62  mov     esi, eax
0x18000ba64  call    cs:__imp_LocalFree
0x18000ba6a  lea     rcx, [rbx+30h]
0x18000ba6e  test    esi, esi
0x18000ba70  js      short loc_18000BAA0
0x18000ba72  mov     eax, [rdi+30h]
0x18000ba75  movups  xmm0, xmmword ptr [rbx+20h]
0x18000ba79  mov     [rbx+40h], eax
0x18000ba7c  mov     eax, [rdi+28h]
0x18000ba7f  mov     [rbx+38h], eax
0x18000ba82  mov     eax, [rdi+2Ch]
0x18000ba85  mov     [rbx+3Ch], eax
0x18000ba88  mov     rax, [rcx]
0x18000ba8b  mov     [rbx+58h], rax
0x18000ba8f  mov     [rbx+64h], r14d
0x18000ba93  movdqu  xmmword ptr [rbx+48h], xmm0
0x18000ba98  jmp     short loc_18000BACB
0x18000ba9a  lea     rcx, [rbx+30h]
0x18000ba9e  jmp     short loc_18000BA72
0x18000baa0  mov     rcx, [rcx]; hMem
0x18000baa3  call    cs:__imp_LocalFree
0x18000baa9  mov     rcx, [rbx+18h]; hMem
0x18000baad  call    cs:__imp_LocalFree
0x18000bab3  mov     rcx, [rbx+28h]; hMem
0x18000bab7  call    cs:__imp_LocalFree
0x18000babd  xor     edx, edx; Val
0x18000babf  mov     rcx, rbx; void *
0x18000bac2  lea     r8d, [rdx+78h]; Size
0x18000bac6  call    memset_0
0x18000bacb  mov     rbx, [rsp+38h+arg_8]
0x18000bad0  mov     eax, esi
0x18000bad2  mov     rbp, [rsp+38h+arg_10]
0x18000bad7  add     rsp, 20h
0x18000badb  pop     r14
0x18000badd  pop     rdi
0x18000bade  pop     rsi
0x18000badf  retn
```

# CSidResolver::_LookupSids(_UNICODE_STRING *,_LSA_TRANSLATED_NAME * *,_LSA_REFERENCED_DOMAIN_LIST * *,ulong,void * *)

- ea: `0x18006fb34`
- end: `0x18006fbc5`
- name: `?_LookupSids@CSidResolver@@AEAAJPEAU_UNICODE_STRING@@PEAPEAU_LSA_TRANSLATED_NAME@@PEAPEAU_LSA_REFERENCED_DOMAIN_LIST@@KPEAPEAX@Z`
- size: `145`
- prototype: `int(CSidResolver *__hidden this, struct _UNICODE_STRING *, struct _LSA_TRANSLATED_NAME **, struct _LSA_REFERENCED_DOMAIN_LIST **, unsigned int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006f368`
- `0x18006ff1c`

## callees

- `0x18006fb34`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006fbab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006fbab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006fb76`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006fb76`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x18006fb9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x18006fb9e`

## pseudocode

```c
__int64 __fastcall CSidResolver::_LookupSids(
        CSidResolver *this,
        struct _LSA_UNICODE_STRING *a2,
        struct _LSA_TRANSLATED_NAME **a3,
        struct _LSA_REFERENCED_DOMAIN_LIST **a4,
        ULONG Count,
        void **Sids)
{
  unsigned int v8; // ebx
  struct _LSA_OBJECT_ATTRIBUTES v10; // [rsp+30h] [rbp-38h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+70h] [rbp+8h] BYREF

  PolicyHandle = 0;
  memset(&v10, 0, sizeof(v10));
  v8 = LsaOpenPolicy(a2, &v10, 0x800u, &PolicyHandle);
  if ( !v8 )
  {
    v8 = LsaLookupSids(PolicyHandle, Count, Sids, a4, a3);
    LsaClose(PolicyHandle);
  }
  return v8;
}

```

## disassembly

```asm
0x18006fb34  mov     rax, rsp
0x18006fb37  mov     [rax+10h], rbx
0x18006fb3b  mov     [rax+18h], rsi
0x18006fb3f  mov     [rax+8], rcx
0x18006fb43  push    rdi
0x18006fb44  sub     rsp, 60h
0x18006fb48  xorps   xmm0, xmm0
0x18006fb4b  mov     qword ptr [rax+8], 0
0x18006fb53  mov     rdi, r9
0x18006fb56  mov     rsi, r8
0x18006fb59  mov     rcx, rdx; SystemName
0x18006fb5c  lea     r9, [rax+8]; PolicyHandle
0x18006fb60  mov     r8d, 800h; DesiredAccess
0x18006fb66  lea     rdx, [rax-38h]; ObjectAttributes
0x18006fb6a  movups  xmmword ptr [rax-38h], xmm0
0x18006fb6e  movups  xmmword ptr [rax-28h], xmm0
0x18006fb72  movups  xmmword ptr [rax-18h], xmm0
0x18006fb76  call    cs:__imp_LsaOpenPolicy
0x18006fb7c  mov     ebx, eax
0x18006fb7e  test    eax, eax
0x18006fb80  jnz     short loc_18006FBB1
0x18006fb82  mov     r8, [rsp+68h+Sids]; Sids
0x18006fb8a  mov     r9, rdi; ReferencedDomains
0x18006fb8d  mov     edx, [rsp+68h+Count]; Count
0x18006fb94  mov     rcx, [rsp+68h+PolicyHandle]; PolicyHandle
0x18006fb99  mov     [rsp+68h+Names], rsi; Names
0x18006fb9e  call    cs:__imp_LsaLookupSids
0x18006fba4  mov     rcx, [rsp+68h+PolicyHandle]; ObjectHandle
0x18006fba9  mov     ebx, eax
0x18006fbab  call    cs:__imp_LsaClose
0x18006fbb1  lea     r11, [rsp+68h+var_8]
0x18006fbb6  mov     eax, ebx
0x18006fbb8  mov     rbx, [r11+18h]
0x18006fbbc  mov     rsi, [r11+20h]
0x18006fbc0  mov     rsp, r11
0x18006fbc3  pop     rdi
0x18006fbc4  retn
```

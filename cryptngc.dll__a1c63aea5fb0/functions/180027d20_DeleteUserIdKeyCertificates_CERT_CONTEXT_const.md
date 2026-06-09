# DeleteUserIdKeyCertificates(_CERT_CONTEXT const *)

- ea: `0x180027d20`
- end: `0x180027e07`
- name: `?DeleteUserIdKeyCertificates@@YAJPEBU_CERT_CONTEXT@@@Z`
- size: `231`
- prototype: `int(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800276d8`

## callees

- `0x180006538`
- `0x180027d20`
- `0x180027e10`
- `0x180028f7c`
- `0x180032fcc`
- `0x18003ae7c`
- `0x18003b318`

## string_xrefs

- `0x180027d70`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027da1`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027dd0`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall DeleteUserIdKeyCertificates(const struct _CERT_CONTEXT *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HCERTSTORE v9; // [rsp+38h] [rbp+10h] BYREF
  HCERTSTORE hCertStore; // [rsp+40h] [rbp+18h] BYREF

  hCertStore = 0;
  v9 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v9,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hCertStore,
    0);
  v2 = OpenUserIdKeyCertificateStores(&hCertStore, &v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = DeleteCertificatesFromStore(hCertStore, &a1->pCertInfo->SubjectPublicKeyInfo);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v4,
        v7);
    v5 = DeleteCertificatesFromStore(v9, &a1->pCertInfo->SubjectPublicKeyInfo);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v5,
        v7);
    v3 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v2,
      v7);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v9);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
  return v3;
}

```

## disassembly

```asm
0x180027d20  mov     rax, rsp
0x180027d23  mov     [rax+8], rbx
0x180027d27  push    rdi; int
0x180027d28  sub     rsp, 20h
0x180027d2c  mov     rdi, rcx
0x180027d2f  mov     qword ptr [rax+18h], 0
0x180027d37  lea     rcx, [rax+10h]
0x180027d3b  mov     qword ptr [rax+10h], 0
0x180027d43  xor     edx, edx
0x180027d45  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027d4a  xor     edx, edx
0x180027d4c  lea     rcx, [rsp+28h+hCertStore]
0x180027d51  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027d56  lea     rdx, [rsp+28h+arg_8]; void **
0x180027d5b  lea     rcx, [rsp+28h+hCertStore]; void **
0x180027d60  call    ?OpenUserIdKeyCertificateStores@@YAJPEAPEAX0@Z; OpenUserIdKeyCertificateStores(void * *,void * *)
0x180027d65  mov     ebx, eax
0x180027d67  test    eax, eax
0x180027d69  jns     short loc_180027D86
0x180027d6b  mov     rcx, [rsp+28h]; this
0x180027d70  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027d77  mov     r9d, eax; char *
0x180027d7a  mov     edx, 123h; void *
0x180027d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d84  jmp     short loc_180027DE6
0x180027d86  mov     rdx, [rdi+18h]
0x180027d8a  mov     rcx, [rsp+28h+hCertStore]; hCertStore
0x180027d8f  add     rdx, 60h ; '`'; pvFindPara
0x180027d93  call    ?DeleteCertificatesFromStore@@YAJPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z; DeleteCertificatesFromStore(void *,_CERT_PUBLIC_KEY_INFO *)
0x180027d98  test    eax, eax
0x180027d9a  jns     short loc_180027DB5
0x180027d9c  mov     rcx, [rsp+28h]; this
0x180027da1  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027da8  mov     r9d, eax; char *
0x180027dab  mov     edx, 127h; void *
0x180027db0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027db5  mov     rdx, [rdi+18h]
0x180027db9  mov     rcx, [rsp+28h+arg_8]; hCertStore
0x180027dbe  add     rdx, 60h ; '`'; pvFindPara
0x180027dc2  call    ?DeleteCertificatesFromStore@@YAJPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z; DeleteCertificatesFromStore(void *,_CERT_PUBLIC_KEY_INFO *)
0x180027dc7  test    eax, eax
0x180027dc9  jns     short loc_180027DE4
0x180027dcb  mov     rcx, [rsp+28h]; this
0x180027dd0  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027dd7  mov     r9d, eax; char *
0x180027dda  mov     edx, 12Bh; void *
0x180027ddf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027de4  xor     ebx, ebx
0x180027de6  lea     rcx, [rsp+28h+arg_8]
0x180027deb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027df0  lea     rcx, [rsp+28h+hCertStore]
0x180027df5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027dfa  mov     eax, ebx
0x180027dfc  mov     rbx, [rsp+28h+arg_0]
0x180027e01  add     rsp, 20h
0x180027e05  pop     rdi
0x180027e06  retn
```

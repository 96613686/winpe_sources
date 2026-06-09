# OpenUserIdKeyCertificateStores(void * *,void * *)

- ea: `0x18003ae7c`
- end: `0x18003af66`
- name: `?OpenUserIdKeyCertificateStores@@YAJPEAPEAX0@Z`
- size: `234`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027a30`
- `0x180027d20`

## callees

- `0x180028360`
- `0x180028f7c`
- `0x18003ae7c`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18003aeab`
- `CRYPT32!CertOpenStore` at `0x18003aef2`
- `CRYPT32!CertOpenStore` at `0x18003aeab`
- `CRYPT32!CertOpenStore` at `0x18003aef2`

## string_xrefs

- `0x18003aec3`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18003af07`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall OpenUserIdKeyCertificateStores(void **a1, void **a2)
{
  const char *v4; // r9
  void *v5; // rbx
  unsigned int LastError; // ebx
  HCERTSTORE v7; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HCERTSTORE v11; // [rsp+50h] [rbp+18h] BYREF
  HCERTSTORE v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10200u, L"MY");
  v5 = v12;
  if ( v12 )
  {
    v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10200u, L"REQUEST");
    v11 = v7;
    if ( v7 )
    {
      *a1 = v5;
      *a2 = v7;
      v12 = 0;
      v11 = 0;
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x10F,
                    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                    v8);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x105,
                  (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                  v4);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastError;
}

```

## disassembly

```asm
0x18003ae7c  mov     [rsp+arg_0], rbx
0x18003ae81  mov     [rsp+arg_8], rsi
0x18003ae86  push    rdi
0x18003ae87  sub     rsp, 30h
0x18003ae8b  mov     rdi, rdx
0x18003ae8e  lea     rax, aMy_0; "MY"
0x18003ae95  xor     edx, edx; dwEncodingType
0x18003ae97  mov     [rsp+38h+pvPara], rax; pvPara
0x18003ae9c  mov     rsi, rcx
0x18003ae9f  mov     r9d, 10200h; dwFlags
0x18003aea5  xor     r8d, r8d; hCryptProv
0x18003aea8  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18003aeab  call    cs:__imp_CertOpenStore
0x18003aeb1  mov     [rsp+38h+arg_18], rax
0x18003aeb6  mov     rbx, rax
0x18003aeb9  test    rax, rax
0x18003aebc  jnz     short loc_18003AED8
0x18003aebe  mov     rcx, [rsp+38h]; this
0x18003aec3  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003aeca  mov     edx, 105h; void *
0x18003aecf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003aed4  mov     ebx, eax
0x18003aed6  jmp     short loc_18003AF4A
0x18003aed8  xor     edx, edx; dwEncodingType
0x18003aeda  lea     rax, aRequest; "REQUEST"
0x18003aee1  mov     r9d, 10200h; dwFlags
0x18003aee7  mov     [rsp+38h+pvPara], rax; pvPara
0x18003aeec  xor     r8d, r8d; hCryptProv
0x18003aeef  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18003aef2  call    cs:__imp_CertOpenStore
0x18003aef8  mov     [rsp+38h+arg_10], rax
0x18003aefd  test    rax, rax
0x18003af00  jnz     short loc_18003AF26
0x18003af02  mov     rcx, [rsp+38h]; this
0x18003af07  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003af0e  mov     edx, 10Fh; void *
0x18003af13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003af18  lea     rcx, [rsp+38h+arg_10]
0x18003af1d  mov     ebx, eax
0x18003af1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003af24  jmp     short loc_18003AF4A
0x18003af26  mov     [rsi], rbx
0x18003af29  lea     rcx, [rsp+38h+arg_10]
0x18003af2e  mov     [rdi], rax
0x18003af31  mov     [rsp+38h+arg_18], 0
0x18003af3a  mov     [rsp+38h+arg_10], 0
0x18003af43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003af48  xor     ebx, ebx
0x18003af4a  lea     rcx, [rsp+38h+arg_18]
0x18003af4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003af54  mov     rsi, [rsp+38h+arg_8]
0x18003af59  mov     eax, ebx
0x18003af5b  mov     rbx, [rsp+38h+arg_0]
0x18003af60  add     rsp, 30h
0x18003af64  pop     rdi
0x18003af65  retn
```

# CNG_PROVIDER_ENTRY::InitializeInternal(EncryptionProviderErrorType *)

- ea: `0x18004a650`
- end: `0x18004a9b8`
- name: `?InitializeInternal@CNG_PROVIDER_ENTRY@@UEAAJPEAW4EncryptionProviderErrorType@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(CNG_PROVIDER_ENTRY *__hidden this, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000c3f0`
- `0x180047a20`
- `0x180047ba4`
- `0x18004a650`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18004a7be`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004a7be`
- `ncrypt!NCryptOpenKey` at `0x18004a803`
- `ncrypt!NCryptOpenKey` at `0x18004a803`
- `ncrypt!NCryptKeyDerivation` at `0x18004a847`
- `ncrypt!NCryptKeyDerivation` at `0x18004a925`
- `ncrypt!NCryptKeyDerivation` at `0x18004a847`
- `ncrypt!NCryptKeyDerivation` at `0x18004a925`
- `ncrypt!NCryptFreeObject` at `0x18004a94b`
- `ncrypt!NCryptFreeObject` at `0x18004a94b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004a86e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004a86e`
- `bcrypt!BCryptGetProperty` at `0x18004a8b0`
- `bcrypt!BCryptGetProperty` at `0x18004a8b0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004a8e9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004a8e9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004a962`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004a962`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004a989`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004a989`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a97e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a97e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a72a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a752`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a7ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a72a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a752`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004a7ea`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a81b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a8c6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a8ff`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a81b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a8c6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a8ff`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004a6a0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004a6a0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004a6bc`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004a6bc`

## pseudocode

```c
__int64 __fastcall CNG_PROVIDER_ENTRY::InitializeInternal(
        CNG_PROVIDER_ENTRY *this,
        enum EncryptionProviderErrorType *a2)
{
  CONFIG_ELEMENT *v4; // rcx
  int v5; // r13d
  int AttributeEntry; // edi
  const wchar_t *Str; // rax
  int v8; // ecx
  const wchar_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  SECURITY_STATUS v12; // eax
  DWORD dwFlags; // ebx
  const WCHAR *v14; // rax
  void *Ptr; // rax
  NTSTATUS Property; // eax
  UCHAR *v17; // rax
  void *v18; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  struct ATTRIBUTE_ENTRY *v23; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[48]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v26[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v27[32]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v24, v27, 0x20u);
  memset(v26, 0, sizeof(v26));
  BUFFER::BUFFER((BUFFER *)v25, (unsigned __int8 *)v26, 0x20u);
  v4 = (CONFIG_ELEMENT *)*((_QWORD *)this + 4);
  pcbResult = 0;
  v5 = 0;
  v23 = 0;
  phKey = 0;
  phAlgorithm = 0;
  AttributeEntry = CONFIG_ELEMENT::GetAttributeEntry(
                     v4,
                     L"keyContainerName",
                     &v23,
                     (CNG_PROVIDER_ENTRY *)((char *)this + 136));
  if ( AttributeEntry < 0 )
  {
    *(_DWORD *)a2 = 1;
    goto LABEL_30;
  }
  if ( CONFIG_ELEMENT::GetAttributeEntry(
         *((CONFIG_ELEMENT **)this + 4),
         L"useMachineContainer",
         &v23,
         (struct STRU *)v24) < 0 )
  {
    v10 = (__int64)this;
    v8 = 1;
    v11 = 328;
  }
  else
  {
    Str = STRU::QueryStr((STRU *)v24);
    if ( !wcscmp_0(Str, L"false") )
    {
      v8 = 0;
    }
    else
    {
      v9 = STRU::QueryStr((STRU *)v24);
      if ( wcscmp_0(v9, L"true") )
      {
        *(_DWORD *)a2 = 1;
        AttributeEntry = -2147024883;
        goto LABEL_30;
      }
      v8 = 1;
    }
    v10 = 328;
    v11 = (__int64)this;
  }
  *(_DWORD *)(v11 + v10) = v8;
  AttributeEntry = PROVIDER_ENTRY::Impersonate(this);
  if ( AttributeEntry < 0 )
  {
    *(_DWORD *)a2 = 9;
    goto LABEL_30;
  }
  v5 = 1;
  v12 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 5, 0, 0);
  if ( v12 )
  {
    *(_DWORD *)a2 = 19;
LABEL_15:
    AttributeEntry = v12;
    goto LABEL_30;
  }
  dwFlags = *((_DWORD *)this + 82) != 0 ? 0x20 : 0;
  v14 = STRU::QueryStr((CNG_PROVIDER_ENTRY *)((char *)this + 136));
  v12 = NCryptOpenKey(*((_QWORD *)this + 5), &phKey, v14, 0, dwFlags);
  if ( v12 )
  {
    *(_DWORD *)a2 = 20;
    goto LABEL_15;
  }
  Ptr = BUFFER::QueryPtr((BUFFER *)v25);
  v12 = NCryptKeyDerivation(phKey, &qword_18006D2C8, Ptr, 32, &pcbResult, 0);
  if ( v12 )
  {
    *(_DWORD *)a2 = 21;
    goto LABEL_15;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property < 0 )
  {
    *(_DWORD *)a2 = 22;
LABEL_22:
    AttributeEntry = Property | 0x10000000;
    goto LABEL_30;
  }
  Property = BCryptGetProperty(phAlgorithm, L"BlockLength", (PUCHAR)this + 320, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    *(_DWORD *)a2 = 23;
    goto LABEL_22;
  }
  v17 = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v25);
  Property = BCryptGenerateSymmetricKey(phAlgorithm, (BCRYPT_KEY_HANDLE *)this + 6, 0, 0, v17, 0x20u, 0);
  if ( Property < 0 )
  {
    *(_DWORD *)a2 = 15;
    goto LABEL_22;
  }
  v18 = BUFFER::QueryPtr((CNG_PROVIDER_ENTRY *)((char *)this + 56));
  v12 = NCryptKeyDerivation(phKey, &qword_18006D288, v18, 32, &pcbResult, 0);
  if ( v12 )
  {
    *(_DWORD *)a2 = 15;
    goto LABEL_15;
  }
  *((_DWORD *)this + 81) = 1;
LABEL_30:
  if ( phKey )
  {
    NCryptFreeObject(phKey);
    phKey = 0;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( v5 )
    PROVIDER_ENTRY::Unimpersonate(this);
  BUFFER::~BUFFER((BUFFER *)v25);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)AttributeEntry;
}

```

## disassembly

```asm
0x18004a650  mov     [rsp-8+arg_10], rbx
0x18004a655  push    rbp
0x18004a656  push    rsi
0x18004a657  push    rdi
0x18004a658  push    r12
0x18004a65a  push    r13
0x18004a65c  push    r14
0x18004a65e  push    r15
0x18004a660  lea     rbp, [rsp-40h]
0x18004a665  sub     rsp, 140h
0x18004a66c  mov     rax, cs:__security_cookie
0x18004a673  xor     rax, rsp
0x18004a676  mov     [rbp+70h+var_40], rax
0x18004a67a  mov     rsi, rdx
0x18004a67d  mov     r14, rcx
0x18004a680  xor     edx, edx; Val
0x18004a682  lea     rcx, [rbp+70h+var_80]; void *
0x18004a686  lea     r8d, [rdx+40h]; Size
0x18004a68a  call    memset_0
0x18004a68f  mov     ebx, 20h ; ' '
0x18004a694  lea     rdx, [rbp+70h+var_80]
0x18004a698  mov     r8d, ebx
0x18004a69b  lea     rcx, [rsp+170h+var_110]
0x18004a6a0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004a6a6  xorps   xmm0, xmm0
0x18004a6a9  lea     rdx, [rbp+70h+var_A8]
0x18004a6ad  mov     r8d, ebx
0x18004a6b0  lea     rcx, [rbp+70h+var_D8]
0x18004a6b4  movups  [rbp+70h+var_A8], xmm0
0x18004a6b8  movups  [rbp+70h+var_98], xmm0
0x18004a6bc  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18004a6c2  mov     rcx, [r14+20h]; this
0x18004a6c6  lea     r9, [r14+88h]; struct STRU *
0x18004a6cd  xor     ebx, ebx
0x18004a6cf  lea     r8, [rsp+170h+var_118]; struct ATTRIBUTE_ENTRY **
0x18004a6d4  lea     rdx, aKeycontainerna; "keyContainerName"
0x18004a6db  mov     [rsp+170h+pcbResult], ebx
0x18004a6df  mov     r13d, ebx
0x18004a6e2  mov     [rsp+170h+var_118], rbx
0x18004a6e7  mov     [rsp+170h+phKey], rbx
0x18004a6ec  mov     [rsp+170h+phAlgorithm], rbx
0x18004a6f1  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x18004a6f6  mov     edi, eax
0x18004a6f8  test    eax, eax
0x18004a6fa  jns     short loc_18004A707
0x18004a6fc  mov     dword ptr [rsi], 1
0x18004a702  jmp     loc_18004A941
0x18004a707  mov     rcx, [r14+20h]; this
0x18004a70b  lea     r9, [rsp+170h+var_110]; struct STRU *
0x18004a710  lea     r8, [rsp+170h+var_118]; struct ATTRIBUTE_ENTRY **
0x18004a715  lea     rdx, aUsemachinecont; "useMachineContainer"
0x18004a71c  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x18004a721  test    eax, eax
0x18004a723  js      short loc_18004A785
0x18004a725  lea     rcx, [rsp+170h+var_110]
0x18004a72a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004a730  mov     rcx, rax; String1
0x18004a733  lea     rdx, aFalse; "false"
0x18004a73a  call    wcscmp_0
0x18004a73f  mov     r15d, 1
0x18004a745  test    eax, eax
0x18004a747  jnz     short loc_18004A74D
0x18004a749  mov     ecx, ebx
0x18004a74b  jmp     short loc_18004A76E
0x18004a74d  lea     rcx, [rsp+170h+var_110]
0x18004a752  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004a758  mov     rcx, rax; String1
0x18004a75b  lea     rdx, aTrue; "true"
0x18004a762  call    wcscmp_0
0x18004a767  test    eax, eax
0x18004a769  jnz     short loc_18004A778
0x18004a76b  mov     ecx, r15d
0x18004a76e  mov     edx, 148h
0x18004a773  mov     rax, r14
0x18004a776  jmp     short loc_18004A796
0x18004a778  mov     [rsi], r15d
0x18004a77b  mov     edi, 8007000Dh
0x18004a780  jmp     loc_18004A941
0x18004a785  mov     r15d, 1
0x18004a78b  mov     rdx, r14
0x18004a78e  mov     ecx, r15d
0x18004a791  mov     eax, 148h
0x18004a796  mov     [rax+rdx], ecx
0x18004a799  mov     rcx, r14; this
0x18004a79c  call    ?Impersonate@PROVIDER_ENTRY@@QEAAJXZ; PROVIDER_ENTRY::Impersonate(void)
0x18004a7a1  mov     edi, eax
0x18004a7a3  test    eax, eax
0x18004a7a5  jns     short loc_18004A7B2
0x18004a7a7  mov     dword ptr [rsi], 9
0x18004a7ad  jmp     loc_18004A941
0x18004a7b2  xor     r8d, r8d; dwFlags
0x18004a7b5  lea     rcx, [r14+28h]; phProvider
0x18004a7b9  xor     edx, edx; pszProviderName
0x18004a7bb  mov     r13d, r15d
0x18004a7be  call    cs:__imp_NCryptOpenStorageProvider
0x18004a7c4  test    eax, eax
0x18004a7c6  jz      short loc_18004A7D5
0x18004a7c8  mov     dword ptr [rsi], 13h
0x18004a7ce  mov     edi, eax
0x18004a7d0  jmp     loc_18004A941
0x18004a7d5  mov     eax, [r14+148h]
0x18004a7dc  lea     rcx, [r14+88h]
0x18004a7e3  neg     eax
0x18004a7e5  sbb     ebx, ebx
0x18004a7e7  and     ebx, 20h
0x18004a7ea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004a7f0  mov     rcx, [r14+28h]; hProvider
0x18004a7f4  lea     rdx, [rsp+170h+phKey]; phKey
0x18004a7f9  mov     r8, rax; pszKeyName
0x18004a7fc  mov     [rsp+170h+dwFlags], ebx; dwFlags
0x18004a800  xor     r9d, r9d; dwLegacyKeySpec
0x18004a803  call    cs:__imp_NCryptOpenKey
0x18004a809  xor     ebx, ebx
0x18004a80b  test    eax, eax
0x18004a80d  jz      short loc_18004A817
0x18004a80f  mov     dword ptr [rsi], 14h
0x18004a815  jmp     short loc_18004A7CE
0x18004a817  lea     rcx, [rbp+70h+var_D8]
0x18004a81b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a821  lea     rcx, [rsp+170h+pcbResult]
0x18004a826  mov     [rsp+170h+cbSecret], ebx
0x18004a82a  mov     qword ptr [rsp+170h+dwFlags], rcx
0x18004a82f  lea     rdx, qword_18006D2C8
0x18004a836  mov     rcx, [rsp+170h+phKey]
0x18004a83b  mov     r12d, 20h ; ' '
0x18004a841  mov     r9d, r12d
0x18004a844  mov     r8, rax
0x18004a847  call    cs:__imp_NCryptKeyDerivation
0x18004a84d  test    eax, eax
0x18004a84f  jz      short loc_18004A85C
0x18004a851  mov     dword ptr [rsi], 15h
0x18004a857  jmp     loc_18004A7CE
0x18004a85c  xor     r9d, r9d; dwFlags
0x18004a85f  lea     rdx, aAes; "AES"
0x18004a866  xor     r8d, r8d; pszImplementation
0x18004a869  lea     rcx, [rsp+170h+phAlgorithm]; phAlgorithm
0x18004a86e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004a874  test    eax, eax
0x18004a876  jns     short loc_18004A889
0x18004a878  mov     dword ptr [rsi], 16h
0x18004a87e  mov     edi, eax
0x18004a880  bts     edi, 1Ch
0x18004a884  jmp     loc_18004A941
0x18004a889  mov     rcx, [rsp+170h+phAlgorithm]; hObject
0x18004a88e  lea     rax, [rsp+170h+pcbResult]
0x18004a893  lea     r8, [r14+140h]; pbOutput
0x18004a89a  mov     [rsp+170h+cbSecret], ebx; dwFlags
0x18004a89e  mov     r9d, 4; cbOutput
0x18004a8a4  mov     qword ptr [rsp+170h+dwFlags], rax; pcbResult
0x18004a8a9  lea     rdx, pszProperty; "BlockLength"
0x18004a8b0  call    cs:__imp_BCryptGetProperty
0x18004a8b6  test    eax, eax
0x18004a8b8  jns     short loc_18004A8C2
0x18004a8ba  mov     dword ptr [rsi], 17h
0x18004a8c0  jmp     short loc_18004A87E
0x18004a8c2  lea     rcx, [rbp+70h+var_D8]
0x18004a8c6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a8cc  mov     rcx, [rsp+170h+phAlgorithm]; hAlgorithm
0x18004a8d1  lea     rdx, [r14+30h]; phKey
0x18004a8d5  mov     [rsp+170h+var_140], ebx; dwFlags
0x18004a8d9  xor     r9d, r9d; cbKeyObject
0x18004a8dc  mov     [rsp+170h+cbSecret], r12d; cbSecret
0x18004a8e1  xor     r8d, r8d; pbKeyObject
0x18004a8e4  mov     qword ptr [rsp+170h+dwFlags], rax; pbSecret
0x18004a8e9  call    cs:__imp_BCryptGenerateSymmetricKey
0x18004a8ef  test    eax, eax
0x18004a8f1  jns     short loc_18004A8FB
0x18004a8f3  mov     dword ptr [rsi], 0Fh
0x18004a8f9  jmp     short loc_18004A87E
0x18004a8fb  lea     rcx, [r14+38h]
0x18004a8ff  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a905  lea     rcx, [rsp+170h+pcbResult]
0x18004a90a  mov     [rsp+170h+cbSecret], ebx
0x18004a90e  mov     qword ptr [rsp+170h+dwFlags], rcx
0x18004a913  lea     rdx, qword_18006D288
0x18004a91a  mov     rcx, [rsp+170h+phKey]
0x18004a91f  mov     r9d, r12d
0x18004a922  mov     r8, rax
0x18004a925  call    cs:__imp_NCryptKeyDerivation
0x18004a92b  test    eax, eax
0x18004a92d  jz      short loc_18004A93A
0x18004a92f  mov     dword ptr [rsi], 0Fh
0x18004a935  jmp     loc_18004A7CE
0x18004a93a  mov     [r14+144h], r15d
0x18004a941  mov     rcx, [rsp+170h+phKey]; hObject
0x18004a946  test    rcx, rcx
0x18004a949  jz      short loc_18004A956
0x18004a94b  call    cs:__imp_NCryptFreeObject
0x18004a951  mov     [rsp+170h+phKey], rbx
0x18004a956  mov     rcx, [rsp+170h+phAlgorithm]; hAlgorithm
0x18004a95b  test    rcx, rcx
0x18004a95e  jz      short loc_18004A96D
0x18004a960  xor     edx, edx; dwFlags
0x18004a962  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004a968  mov     [rsp+170h+phAlgorithm], rbx
0x18004a96d  test    r13d, r13d
0x18004a970  jz      short loc_18004A97A
0x18004a972  mov     rcx, r14; this
0x18004a975  call    ?Unimpersonate@PROVIDER_ENTRY@@QEAAJXZ; PROVIDER_ENTRY::Unimpersonate(void)
0x18004a97a  lea     rcx, [rbp+70h+var_D8]
0x18004a97e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a984  lea     rcx, [rsp+170h+var_110]
0x18004a989  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004a98f  mov     eax, edi
0x18004a991  mov     rcx, [rbp+70h+var_40]
0x18004a995  xor     rcx, rsp; StackCookie
0x18004a998  call    __security_check_cookie
0x18004a99d  mov     rbx, [rsp+170h+arg_10]
0x18004a9a5  add     rsp, 140h
0x18004a9ac  pop     r15
0x18004a9ae  pop     r14
0x18004a9b0  pop     r13
0x18004a9b2  pop     r12
0x18004a9b4  pop     rdi
0x18004a9b5  pop     rsi
0x18004a9b6  pop     rbp
0x18004a9b7  retn
```

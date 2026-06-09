# win_dox::DigestReferenceForRelationships(void *,win_dox::OpcSignatureRelationshipReference const &,win_dox::OpcRelationshipSet const &)

- ea: `0x1800a686c`
- end: `0x1800a69a0`
- name: `?DigestReferenceForRelationships@win_dox@@YAXPEAXAEBVOpcSignatureRelationshipReference@1@AEBVOpcRelationshipSet@1@@Z`
- size: `308`
- prototype: `void __fastcall(HCRYPTXML hReference, void *, const struct win_dox::OpcSignatureRelationshipReference *, const struct win_dox::OpcRelationshipSet *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800a4630`
- `0x1800a5080`

## callees

- `0x18001568c`
- `0x180049320`
- `0x18004a008`
- `0x1800a5abc`
- `0x1800a686c`
- `0x1800a73f0`
- `0x1800a8404`
- `0x1800a8bb4`
- `0x1800cd1c4`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlDigestReference` at `0x1800a6937`
- `CRYPTXML!CryptXmlDigestReference` at `0x1800a6937`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall win_dox::DigestReferenceForRelationships(
        HCRYPTXML hReference,
        void *a2,
        const struct win_dox::OpcSignatureRelationshipReference *a3,
        const struct win_dox::OpcRelationshipSet *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 RelationshipSelectorEnumerator; // rax
  win_dox *v11; // rcx
  int (*C14NTransformEngine)(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *); // rbx
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  HRESULT v17; // eax
  int v18; // edx
  const char *v19; // r8
  unsigned int v20; // r9d
  _BYTE v21[8]; // [rsp+20h] [rbp-49h] BYREF
  void *Block; // [rsp+28h] [rbp-41h]
  __int64 v23; // [rsp+30h] [rbp-39h]
  _BYTE v24[8]; // [rsp+38h] [rbp-31h] BYREF
  void *v25; // [rsp+40h] [rbp-29h]
  __int64 v26; // [rsp+50h] [rbp-19h]
  _OWORD v27[2]; // [rsp+58h] [rbp-11h] BYREF
  CRYPT_XML_DATA_PROVIDER pDataProviderIn; // [rsp+78h] [rbp+Fh] BYREF
  win_dox *v29; // [rsp+E8h] [rbp+7Fh] BYREF

  v26 = -2;
  std::set<std::wstring>::set<std::wstring>(v24, a2, a3, a4);
  std::set<std::wstring>::set<std::wstring>(v21, v7, v8, v9);
  RelationshipSelectorEnumerator = win_dox::OpcSignatureRelationshipReference::GetRelationshipSelectorEnumerator(
                                     a2,
                                     &v29);
  win_dox::RelationshipIDsAndTypesFromSelectorEnumerator(RelationshipSelectorEnumerator, v24, v21);
  v11 = v29;
  if ( v29 )
    (*(void (__fastcall **)(win_dox *))(*(_QWORD *)v29 + 16LL))(v29);
  C14NTransformEngine = win_dox::GetC14NTransformEngine(v11);
  memset(v27, 0, sizeof(v27));
  win_dox::OpcRelationshipsTransform::CreateProvider(a3, v24, v21, v27);
  memset(&pDataProviderIn, 0, sizeof(pDataProviderIn));
  v13 = ((__int64 (__fastcall *)(const CRYPT_XML_ALGORITHM *, _OWORD *, CRYPT_XML_DATA_PROVIDER *))C14NTransformEngine)(
          &win_dox::gc_canonicalizationC14NTransform,
          v27,
          &pDataProviderIn);
  if ( v13 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v13, v14, v15, v16);
  v17 = CryptXmlDigestReference(hReference, 1u, &pDataProviderIn);
  if ( v17 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v17, v18, v19, v20);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
    v21,
    &v29,
    *(_QWORD *)Block);
  operator delete(Block);
  Block = 0;
  v23 = 0;
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
    v24,
    &v29,
    *(_QWORD *)v25);
  operator delete(v25);
}

```

## disassembly

```asm
0x1800a686c  push    rbp
0x1800a686e  push    rbx
0x1800a686f  push    rsi
0x1800a6870  push    rdi
0x1800a6871  lea     rbp, [rsp-3Fh]
0x1800a6876  sub     rsp, 0A8h
0x1800a687d  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x1800a6885  mov     rsi, r8
0x1800a6888  mov     rbx, rdx
0x1800a688b  mov     rdi, rcx
0x1800a688e  lea     rcx, [rbp+57h+var_88]
0x1800a6892  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800a6897  nop
0x1800a6898  lea     rcx, [rbp+57h+var_A0]
0x1800a689c  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800a68a1  nop
0x1800a68a2  lea     rdx, [rbp+57h+arg_18]
0x1800a68a6  mov     rcx, rbx
0x1800a68a9  call    ?GetRelationshipSelectorEnumerator@OpcSignatureRelationshipReference@win_dox@@QEBA?AV?$Enumerator@UIOpcRelationshipSelectorEnumerator@@@2@XZ; win_dox::OpcSignatureRelationshipReference::GetRelationshipSelectorEnumerator(void)
0x1800a68ae  nop
0x1800a68af  lea     r8, [rbp+57h+var_A0]
0x1800a68b3  lea     rdx, [rbp+57h+var_88]
0x1800a68b7  mov     rcx, rax
0x1800a68ba  call    ?RelationshipIDsAndTypesFromSelectorEnumerator@win_dox@@YAXAEAV?$Enumerator@UIOpcRelationshipSelectorEnumerator@@@1@PEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@std@@1@Z; win_dox::RelationshipIDsAndTypesFromSelectorEnumerator(win_dox::Enumerator<IOpcRelationshipSelectorEnumerator> &,std::set<std::wstring> *,std::set<std::wstring> *)
0x1800a68bf  nop
0x1800a68c0  mov     rcx, [rbp+57h+arg_18]
0x1800a68c4  test    rcx, rcx
0x1800a68c7  jz      short loc_1800A68D6
0x1800a68c9  mov     rax, [rcx]
0x1800a68cc  mov     rax, [rax+10h]
0x1800a68d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a68d5  nop
0x1800a68d6  call    ?GetC14NTransformEngine@win_dox@@YAP6AJPEBU_CRYPT_XML_ALGORITHM@@PEAU_CRYPT_XML_DATA_PROVIDER@@1@ZXZ; win_dox::GetC14NTransformEngine(void)
0x1800a68db  mov     rbx, rax
0x1800a68de  xorps   xmm0, xmm0
0x1800a68e1  movups  [rbp+57h+var_68], xmm0
0x1800a68e5  movups  [rbp+57h+var_58], xmm0
0x1800a68e9  lea     r9, [rbp+57h+var_68]
0x1800a68ed  lea     r8, [rbp+57h+var_A0]
0x1800a68f1  lea     rdx, [rbp+57h+var_88]
0x1800a68f5  mov     rcx, rsi
0x1800a68f8  call    ?CreateProvider@OpcRelationshipsTransform@win_dox@@SAXAEBVOpcRelationshipSet@2@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@std@@1PEAU_CRYPT_XML_DATA_PROVIDER@@@Z; win_dox::OpcRelationshipsTransform::CreateProvider(win_dox::OpcRelationshipSet const &,std::set<std::wstring> const &,std::set<std::wstring> const &,_CRYPT_XML_DATA_PROVIDER *)
0x1800a68fd  xorps   xmm0, xmm0
0x1800a6900  movups  xmmword ptr [rbp+57h+pDataProviderIn.pvCallbackState], xmm0
0x1800a6904  movups  xmmword ptr [rbp+57h+pDataProviderIn.pfnRead], xmm0
0x1800a6908  lea     r8, [rbp+57h+pDataProviderIn]
0x1800a690c  lea     rdx, [rbp+57h+var_68]
0x1800a6910  lea     rcx, ?gc_canonicalizationC14NTransform@win_dox@@3U_CRYPT_XML_ALGORITHM@@B; _CRYPT_XML_ALGORITHM const win_dox::gc_canonicalizationC14NTransform
0x1800a6917  mov     rax, rbx
0x1800a691a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a691f  test    eax, eax
0x1800a6921  jns     short loc_1800A692B
0x1800a6923  mov     ecx, eax; this
0x1800a6925  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a692b  lea     r8, [rbp+57h+pDataProviderIn]; pDataProviderIn
0x1800a692f  mov     edx, 1; dwFlags
0x1800a6934  mov     rcx, rdi; hReference
0x1800a6937  call    cs:__imp_CryptXmlDigestReference
0x1800a693d  test    eax, eax
0x1800a693f  jns     short loc_1800A6949
0x1800a6941  mov     ecx, eax; this
0x1800a6943  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a6949  mov     r9, [rbp+57h+Block]
0x1800a694d  mov     r8, [r9]
0x1800a6950  lea     rdx, [rbp+57h+arg_18]
0x1800a6954  lea     rcx, [rbp+57h+var_A0]
0x1800a6958  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::iterator,std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::iterator)
0x1800a695d  mov     rcx, [rbp+57h+Block]; Block
0x1800a6961  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6966  mov     [rbp+57h+Block], 0
0x1800a696e  mov     [rbp+57h+var_90], 0
0x1800a6976  mov     r9, [rbp+57h+var_80]
0x1800a697a  mov     r8, [r9]
0x1800a697d  lea     rdx, [rbp+57h+arg_18]
0x1800a6981  lea     rcx, [rbp+57h+var_88]
0x1800a6985  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::iterator,std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::iterator)
0x1800a698a  mov     rcx, [rbp+57h+var_80]; Block
0x1800a698e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6993  nop
0x1800a6994  add     rsp, 0A8h
0x1800a699b  pop     rdi
0x1800a699c  pop     rsi
0x1800a699d  pop     rbx
0x1800a699e  pop     rbp
0x1800a699f  retn
```

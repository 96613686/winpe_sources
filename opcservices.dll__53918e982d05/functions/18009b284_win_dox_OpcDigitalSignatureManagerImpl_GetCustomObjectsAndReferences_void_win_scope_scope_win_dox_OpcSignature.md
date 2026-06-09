# win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(void *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_dox::OpcSignatureCustomObjectSet *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>> *)

- ea: `0x18009b284`
- end: `0x18009b408`
- name: `?GetCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAVOpcSignatureCustomObjectSet@2@PEAV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@4@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2494`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x180015660`
- `0x18001568c`
- `0x1800563ac`
- `0x18009b284`
- `0x18009b410`
- `0x18009bc58`
- `0x18009bc90`
- `0x18009bd58`
- `0x1800cac28`
- `0x1800f8b68`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetSignature` at `0x18009b2b1`
- `CRYPTXML!CryptXmlGetSignature` at `0x18009b2b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(
        void *a1,
        void *a2,
        __m128i *a3,
        __int64 a4,
        __m128i *a5)
{
  HRESULT Signature; // eax
  const char *v8; // rdx
  const char *v9; // r8
  unsigned int v10; // r9d
  void *v11; // rax
  void *v12; // rbx
  const char *v13; // rdx
  unsigned int v14; // r8d
  void *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __m128i v19; // xmm1
  unsigned __int64 v20; // rax
  CRYPT_XML_SIGNATURE *ppStruct[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-28h] BYREF
  __m128i v25; // [rsp+50h] [rbp-18h] BYREF
  void *v26; // [rsp+90h] [rbp+28h] BYREF

  v26 = a1;
  ppStruct[1] = (CRYPT_XML_SIGNATURE *)-2LL;
  ppStruct[0] = 0;
  Signature = CryptXmlGetSignature(a2, (const CRYPT_XML_SIGNATURE **)ppStruct);
  if ( Signature < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Signature, (int)v8, v9, v10);
  v11 = operator new(0x10u, v8, (unsigned int)v9);
  v12 = v11;
  v26 = v11;
  if ( v11 )
    win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v11);
  else
    v12 = 0;
  win_scope::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>(
    v24,
    v12);
  LODWORD(v26) = 0;
  win_dox::SignatureXmlParser::ParseCustomObjects(ppStruct[0], v24, &v26);
  v15 = operator new(0x10u, v13, v14);
  v26 = v15;
  if ( v15 )
    v15 = (void *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v15);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v23,
    v15);
  v16 = (_QWORD *)win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                    &v25,
                    v23);
  win_dox::SignatureXmlParser::ParseSignatureReferences((__int64)ppStruct[0], a3, v16);
  v17 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v25,
          v24);
  v18 = win_dox::CreateInstanceFromInner<IOpcSignatureCustomObjectSet,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v26,
          v17);
  win_dox::OpcRelationship::operator=(a4, v18);
  if ( v26 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
  win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
    &v25,
    v23);
  v19 = *a5;
  *a5 = v25;
  v25 = v19;
  LODWORD(v20) = v19.m128i_i32[0];
  if ( v19.m128i_i64[0] )
  {
    v20 = _mm_srli_si128(v19, 8).m128i_u64[0];
    if ( v20 )
      LODWORD(v20) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v25);
  }
  if ( v23[0] && v23[1] )
    LODWORD(v20) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v23);
  if ( v24[0] && v24[1] )
    LODWORD(v20) = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v24);
  return v20;
}

```

## disassembly

```asm
0x18009b284  mov     [rsp-20h+arg_0], rcx
0x18009b289  push    rbp
0x18009b28a  push    rbx
0x18009b28b  push    rsi
0x18009b28c  push    rdi
0x18009b28d  mov     rbp, rsp
0x18009b290  sub     rsp, 68h
0x18009b294  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18009b29c  mov     rdi, r9
0x18009b29f  mov     rsi, r8
0x18009b2a2  mov     rcx, rdx; hCryptXml
0x18009b2a5  mov     [rbp+ppStruct], 0
0x18009b2ad  lea     rdx, [rbp+ppStruct]; ppStruct
0x18009b2b1  call    cs:__imp_CryptXmlGetSignature
0x18009b2b7  test    eax, eax
0x18009b2b9  jns     short loc_18009B2C3
0x18009b2bb  mov     ecx, eax; this
0x18009b2bd  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18009b2c3  mov     ecx, 10h; unsigned __int64
0x18009b2c8  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009b2cd  mov     rbx, rax
0x18009b2d0  mov     [rbp+arg_0], rax
0x18009b2d4  test    rax, rax
0x18009b2d7  jz      short loc_18009B2E3
0x18009b2d9  mov     rcx, rax
0x18009b2dc  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x18009b2e1  jmp     short loc_18009B2E5
0x18009b2e3  xor     ebx, ebx
0x18009b2e5  mov     rdx, rbx
0x18009b2e8  lea     rcx, [rbp+var_28]
0x18009b2ec  call    ??0?$scope@PEAVOpcSignatureCustomObjectImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureCustomObjectImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureCustomObjectImpl *)
0x18009b2f1  nop
0x18009b2f2  mov     dword ptr [rbp+arg_0], 0
0x18009b2f9  lea     r8, [rbp+arg_0]
0x18009b2fd  lea     rdx, [rbp+var_28]
0x18009b301  mov     rcx, [rbp+ppStruct]
0x18009b305  call    ?ParseCustomObjects@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@AEAV?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAK@Z; win_dox::SignatureXmlParser::ParseCustomObjects(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>> &,ulong *)
0x18009b30a  mov     ecx, 10h; unsigned __int64
0x18009b30f  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009b314  mov     [rbp+arg_0], rax
0x18009b318  test    rax, rax
0x18009b31b  jz      short loc_18009B326
0x18009b31d  mov     rcx, rax
0x18009b320  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x18009b325  nop
0x18009b326  mov     rdx, rax
0x18009b329  lea     rcx, [rbp+var_38]
0x18009b32d  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x18009b332  nop
0x18009b333  lea     rdx, [rbp+var_38]
0x18009b337  lea     rcx, [rbp+var_18]
0x18009b33b  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b340  mov     r8, rax
0x18009b343  mov     rdx, rsi
0x18009b346  mov     rcx, [rbp+ppStruct]
0x18009b34a  call    ?ParseSignatureReferences@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@PEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z; win_dox::SignatureXmlParser::ParseSignatureReferences(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009b34f  lea     rdx, [rbp+var_28]
0x18009b353  lea     rcx, [rbp+var_18]
0x18009b357  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b35c  mov     rdx, rax
0x18009b35f  lea     rcx, [rbp+arg_0]
0x18009b363  call    ??$CreateInstanceFromInner@UIOpcSignatureCustomObjectSet@@V?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureCustomObjectSet@0@V?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureCustomObjectSet,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009b368  nop
0x18009b369  mov     rdx, rax
0x18009b36c  mov     rcx, rdi
0x18009b36f  call    ??4OpcRelationship@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcRelationship::operator=(win_dox::OpcRelationship const &)
0x18009b374  nop
0x18009b375  mov     rcx, [rbp+arg_0]
0x18009b379  test    rcx, rcx
0x18009b37c  jz      short loc_18009B38B
0x18009b37e  mov     rax, [rcx]
0x18009b381  mov     rax, [rax+10h]
0x18009b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b38a  nop
0x18009b38b  lea     rdx, [rbp+var_38]
0x18009b38f  lea     rcx, [rbp+var_18]
0x18009b393  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b398  mov     rcx, [rbp+arg_20]
0x18009b39c  movups  xmm1, xmmword ptr [rcx]
0x18009b39f  movaps  xmm0, [rbp+var_18]
0x18009b3a3  movdqu  xmmword ptr [rcx], xmm0
0x18009b3a7  movdqa  [rbp+var_18], xmm1
0x18009b3ac  movq    rax, xmm1
0x18009b3b1  test    rax, rax
0x18009b3b4  jz      short loc_18009B3CF
0x18009b3b6  psrldq  xmm1, 8
0x18009b3bb  movq    rax, xmm1
0x18009b3c0  test    rax, rax
0x18009b3c3  jz      short loc_18009B3CF
0x18009b3c5  lea     rcx, [rbp+var_18]
0x18009b3c9  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b3ce  nop
0x18009b3cf  cmp     [rbp+var_38], 0
0x18009b3d4  jz      short loc_18009B3E7
0x18009b3d6  cmp     [rbp+var_30], 0
0x18009b3db  jz      short loc_18009B3E7
0x18009b3dd  lea     rcx, [rbp+var_38]
0x18009b3e1  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b3e6  nop
0x18009b3e7  cmp     [rbp+var_28], 0
0x18009b3ec  jz      short loc_18009B3FF
0x18009b3ee  cmp     [rbp+var_20], 0
0x18009b3f3  jz      short loc_18009B3FF
0x18009b3f5  lea     rcx, [rbp+var_28]
0x18009b3f9  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b3fe  nop
0x18009b3ff  add     rsp, 68h
0x18009b403  pop     rdi
0x18009b404  pop     rsi
0x18009b405  pop     rbx
0x18009b406  pop     rbp
0x18009b407  retn
```

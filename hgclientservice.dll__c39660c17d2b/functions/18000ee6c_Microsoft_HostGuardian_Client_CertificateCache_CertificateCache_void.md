# Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(void)

- ea: `0x18000ee6c`
- end: `0x18000eeea`
- name: `??1CertificateCache@Client@HostGuardian@Microsoft@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::CertificateCache *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ba8c`
- `0x18000c404`
- `0x18000c574`

## callees

- `0x180001bb4`
- `0x18000e9a0`
- `0x18000ec58`
- `0x18000ecc8`
- `0x18000ed3c`
- `0x18000ee6c`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(
        Microsoft::HostGuardian::Client::CertificateCache *this)
{
  char *v1; // rsi
  _QWORD *v3; // rdi
  void **v4; // r14
  void **v5; // rcx
  void **v6; // rbx

  v1 = (char *)this + 8;
  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v4 = (void **)v3[1];
  while ( !*((_BYTE *)v4 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,void *>>>(
      v1,
      v1,
      v4[2]);
    v5 = v4;
    v6 = v4;
    v4 = (void **)*v4;
    std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v5 + 5);
    operator delete(v6);
  }
  v3[1] = v3;
  *v3 = v3;
  v3[2] = v3;
  *((_QWORD *)v1 + 1) = 0;
  std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::wstring,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::wstring,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::wstring>>,0>>((char *)this + 24);
  __1___Tree_V___Tmap_traits_W4AttestationResultType__V__map_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__tuple_W4ShsAttestationFlag__V__vector_EV__allocator_E_std___std__U_FILETIME___2_U__less_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__tuple_W4ShsAttestationFlag__V__vector_EV__allocator_E_std___std__U_FILETIME___2__std___2__std__U__less_W4AttestationResultType___3_V__allocator_U__pair___CBW4AttestationResultType__V__map_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__tuple_W4ShsAttestationFlag__V__vector_EV__allocator_E_std___std__U_FILETIME___2_U__less_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__tuple_W4ShsAttestationFlag__V__vector_EV__allocator_E_std___std__U_FILETIME___2__std___2__std___std___3__0A__std___std__QEAA_XZ(v1);
}

```

## disassembly

```asm
0x18000ee6c  push    rbx
0x18000ee6e  push    rbp
0x18000ee6f  push    rsi
0x18000ee70  push    rdi
0x18000ee71  push    r14
0x18000ee73  sub     rsp, 20h
0x18000ee77  lea     rsi, [rcx+8]
0x18000ee7b  mov     rbp, rcx
0x18000ee7e  mov     rdi, [rsi]
0x18000ee81  mov     r14, [rdi+8]
0x18000ee85  jmp     short loc_18000EEB5
0x18000ee87  mov     r8, [r14+10h]
0x18000ee8b  mov     rdx, rsi
0x18000ee8e  mov     rcx, rsi
0x18000ee91  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@1@@Z
0x18000ee96  mov     rcx, r14
0x18000ee99  mov     rbx, r14
0x18000ee9c  mov     r14, [r14]
0x18000ee9f  add     rcx, 28h ; '('
0x18000eea3  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000eea8  mov     edx, 38h ; '8'
0x18000eead  mov     rcx, rbx; Block
0x18000eeb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eeb5  cmp     byte ptr [r14+19h], 0
0x18000eeba  jz      short loc_18000EE87
0x18000eebc  mov     [rdi+8], rdi
0x18000eec0  lea     rcx, [rbp+18h]
0x18000eec4  mov     [rdi], rdi
0x18000eec7  mov     [rdi+10h], rdi
0x18000eecb  mov     qword ptr [rsi+8], 0
0x18000eed3  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::wstring,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::wstring,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::wstring>>,0>>(void)
0x18000eed8  mov     rcx, rsi
0x18000eedb  add     rsp, 20h
0x18000eedf  pop     r14
0x18000eee1  pop     rdi
0x18000eee2  pop     rsi
0x18000eee3  pop     rbp
0x18000eee4  pop     rbx
0x18000eee5  jmp     ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ
```

# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x180011bfc`
- end: `0x180011e32`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `566`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int, int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, const void **, char, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800121e8`

## callees

- `0x1800017e0`
- `0x180003714`
- `0x180003b10`
- `0x18000fa7c`
- `0x1800104f0`
- `0x180010610`
- `0x180010bc8`
- `0x180011724`
- `0x180011bfc`
- `0x180018014`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Add(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        const union _CVDD *a5,
        const unsigned int *a6,
        const struct CODEVIEW_INFORMATION_1 *a7,
        unsigned int a8,
        unsigned int a9,
        const void **a10,
        char a11,
        const unsigned __int16 *a12,
        bool *a13)
{
  __int64 v17; // rdx
  const unsigned int *v18; // rbx
  __int64 *v19; // rcx
  const unsigned int *v20; // rax
  const unsigned int *v21; // rax
  const unsigned int *v23; // [rsp+68h] [rbp-140h] BYREF
  unsigned int v24; // [rsp+70h] [rbp-138h]
  unsigned int v25; // [rsp+74h] [rbp-134h]
  int v26; // [rsp+78h] [rbp-130h] BYREF
  const struct CODEVIEW_INFORMATION_1 *v27; // [rsp+80h] [rbp-128h] BYREF
  bool v28; // [rsp+88h] [rbp-120h]
  _BYTE v29[32]; // [rsp+90h] [rbp-118h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-F8h] BYREF
  void *v31[18]; // [rsp+D0h] [rbp-D8h] BYREF

  v26 = a3;
  v23 = a6;
  v27 = a7;
  v25 = a8;
  v24 = a9;
  std::wstring::wstring((__int64)v30, (__int64)a12);
  std::wstring::wstring((__int64)v29, (__int64)a2);
  v17 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
          (__int64)v31,
          (__int64)v29,
          (__int64)v30,
          a4,
          (__int64)a5,
          (__int64)a6,
          (__int64)a7,
          a3,
          a8,
          a9,
          a10,
          a11);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v17);
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(v31);
  std::wstring::~wstring((__int64)v29);
  std::wstring::~wstring((__int64)v30);
  v18 = (const unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v19 = (__int64 *)(*(_QWORD *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
                                 (_QWORD *)this + 2,
                                 (__int64)&v27,
                                 (unsigned int *)&v26)
                  + 40LL);
  if ( *((_QWORD *)v18 + 3) <= 7u )
    v20 = v18;
  else
    v20 = *(const unsigned int **)v18;
  v23 = v20;
  *(_QWORD *)(*(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
                           v19,
                           (__int64)v29,
                           &v23)
            + 40LL) = v18;
  if ( *((_QWORD *)v18 + 3) <= 7u )
    v21 = v18;
  else
    v21 = *(const unsigned int **)v18;
  v23 = v21;
  *(_QWORD *)(*(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
                           (__int64 *)this + 4,
                           (__int64)v29,
                           &v23)
            + 40LL) = v18;
  if ( a13 )
  {
    v23 = v18;
    std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(
      (_QWORD *)this + 6,
      (__int64)&v27,
      &v23);
    *a13 = v28;
  }
  if ( a10 && *(_DWORD *)a10 )
    a10[1] = (const void *)*((_QWORD *)v18 + 12);
  return 0;
}

```

## disassembly

```asm
0x180011bfc  push    rbx
0x180011bfe  push    rsi
0x180011bff  push    rdi
0x180011c00  push    r12
0x180011c02  push    r13
0x180011c04  push    r14
0x180011c06  push    r15
0x180011c08  sub     rsp, 170h
0x180011c0f  mov     rax, cs:__security_cookie
0x180011c16  xor     rax, rsp
0x180011c19  mov     [rsp+1A8h+var_48], rax
0x180011c21  mov     r12d, r9d
0x180011c24  mov     r15d, r8d
0x180011c27  mov     rbx, rdx
0x180011c2a  mov     rdi, rcx
0x180011c2d  mov     rsi, [rsp+1A8h+arg_48]
0x180011c35  mov     [rsp+1A8h+var_130], r8d
0x180011c3a  mov     r13, [rsp+1A8h+arg_20]
0x180011c42  mov     rax, [rsp+1A8h+arg_28]
0x180011c4a  mov     [rsp+1A8h+var_140], rax
0x180011c4f  mov     rax, [rsp+1A8h+arg_30]
0x180011c57  mov     [rsp+1A8h+var_128], rax
0x180011c5f  mov     eax, [rsp+1A8h+arg_38]
0x180011c66  mov     [rsp+1A8h+var_134], eax
0x180011c6a  mov     eax, [rsp+1A8h+arg_40]
0x180011c71  mov     [rsp+1A8h+var_138], eax
0x180011c75  mov     al, [rsp+1A8h+arg_50]
0x180011c7c  mov     [rsp+1A8h+var_148], al
0x180011c80  mov     rdx, [rsp+1A8h+arg_58]
0x180011c88  mov     r14, [rsp+1A8h+arg_60]
0x180011c90  lea     rcx, [rsp+1A8h+var_F8]
0x180011c98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011c9d  nop
0x180011c9e  mov     rdx, rbx
0x180011ca1  lea     rcx, [rsp+1A8h+var_118]
0x180011ca9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011cae  nop
0x180011caf  mov     al, [rsp+1A8h+var_148]
0x180011cb3  mov     [rsp+1A8h+var_150], al
0x180011cb7  mov     [rsp+1A8h+var_158], rsi
0x180011cbc  mov     eax, [rsp+1A8h+var_138]
0x180011cc0  mov     [rsp+1A8h+var_160], eax
0x180011cc4  mov     eax, [rsp+1A8h+var_134]
0x180011cc8  mov     [rsp+1A8h+var_168], eax
0x180011ccc  mov     [rsp+1A8h+var_170], r15d
0x180011cd1  mov     rax, [rsp+1A8h+var_128]
0x180011cd9  mov     [rsp+1A8h+var_178], rax
0x180011cde  mov     rax, [rsp+1A8h+var_140]
0x180011ce3  mov     [rsp+1A8h+var_180], rax
0x180011ce8  mov     [rsp+1A8h+var_188], r13
0x180011ced  mov     r9d, r12d
0x180011cf0  lea     r8, [rsp+1A8h+var_F8]
0x180011cf8  lea     rdx, [rsp+1A8h+var_118]
0x180011d00  lea     rcx, [rsp+1A8h+var_D8]
0x180011d08  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180011d0d  nop
0x180011d0e  mov     rdx, rax
0x180011d11  mov     rcx, rdi
0x180011d14  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x180011d19  nop
0x180011d1a  lea     rcx, [rsp+1A8h+var_D8]; this
0x180011d22  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180011d27  nop
0x180011d28  lea     rcx, [rsp+1A8h+var_118]
0x180011d30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d35  nop
0x180011d36  lea     rcx, [rsp+1A8h+var_F8]
0x180011d3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d43  mov     rax, [rdi]
0x180011d46  mov     rbx, [rax+8]
0x180011d4a  add     rbx, 10h
0x180011d4e  lea     rcx, [rdi+10h]
0x180011d52  lea     r8, [rsp+1A8h+var_130]
0x180011d57  lea     rdx, [rsp+1A8h+var_128]
0x180011d5f  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180011d64  mov     rcx, [rax]
0x180011d67  add     rcx, 28h ; '('
0x180011d6b  cmp     qword ptr [rbx+18h], 7
0x180011d70  jbe     short loc_180011D77
0x180011d72  mov     rax, [rbx]
0x180011d75  jmp     short loc_180011D7A
0x180011d77  mov     rax, rbx
0x180011d7a  mov     [rsp+1A8h+var_140], rax
0x180011d7f  lea     r8, [rsp+1A8h+var_140]
0x180011d84  lea     rdx, [rsp+1A8h+var_118]
0x180011d8c  call    ??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)
0x180011d91  mov     rax, [rax]
0x180011d94  mov     [rax+28h], rbx
0x180011d98  cmp     qword ptr [rbx+18h], 7
0x180011d9d  jbe     short loc_180011DA4
0x180011d9f  mov     rax, [rbx]
0x180011da2  jmp     short loc_180011DA7
0x180011da4  mov     rax, rbx
0x180011da7  mov     [rsp+1A8h+var_140], rax
0x180011dac  lea     rcx, [rdi+20h]
0x180011db0  lea     r8, [rsp+1A8h+var_140]
0x180011db5  lea     rdx, [rsp+1A8h+var_118]
0x180011dbd  call    ??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)
0x180011dc2  mov     rax, [rax]
0x180011dc5  mov     [rax+28h], rbx
0x180011dc9  test    r14, r14
0x180011dcc  jz      short loc_180011DF3
0x180011dce  mov     [rsp+1A8h+var_140], rbx
0x180011dd3  lea     rcx, [rdi+30h]
0x180011dd7  lea     r8, [rsp+1A8h+var_140]
0x180011ddc  lea     rdx, [rsp+1A8h+var_128]
0x180011de4  call    ??$_Emplace@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)
0x180011de9  mov     al, [rsp+1A8h+var_120]
0x180011df0  mov     [r14], al
0x180011df3  test    rsi, rsi
0x180011df6  jz      short loc_180011E05
0x180011df8  cmp     dword ptr [rsi], 0
0x180011dfb  jz      short loc_180011E05
0x180011dfd  mov     rax, [rbx+60h]
0x180011e01  mov     [rsi+8], rax
0x180011e05  xor     eax, eax
0x180011e07  jmp     short loc_180011E0E
0x180011e09  mov     eax, 8007000Eh
0x180011e0e  mov     rcx, [rsp+1A8h+var_48]
0x180011e16  xor     rcx, rsp; StackCookie
0x180011e19  call    __security_check_cookie
0x180011e1e  add     rsp, 170h
0x180011e25  pop     r15
0x180011e27  pop     r14
0x180011e29  pop     r13
0x180011e2b  pop     r12
0x180011e2d  pop     rdi
0x180011e2e  pop     rsi
0x180011e2f  pop     rbx
0x180011e30  retn
```

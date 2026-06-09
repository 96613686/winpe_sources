# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x1800123fc`
- end: `0x18001261d`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `545`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, struct EMBEDDED_PDB_INFORMATION *, bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800129cc`

## callees

- `0x180001800`
- `0x180003768`
- `0x180003b14`
- `0x18001016c`
- `0x1800102a8`
- `0x180010c84`
- `0x18001135c`
- `0x180011eec`
- `0x1800122cc`
- `0x1800123fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
  __int64 v17; // r8
  const unsigned int *v18; // rbx
  __int64 v19; // rcx
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
  _BYTE v31[144]; // [rsp+D0h] [rbp-D8h] BYREF

  v26 = a3;
  v23 = a6;
  v27 = a7;
  v25 = a8;
  v24 = a9;
  std::wstring::wstring(v30, a12);
  std::wstring::wstring(v29, a2);
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
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
    this,
    *(_QWORD *)this,
    v17);
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v31);
  std::wstring::~wstring(v29);
  std::wstring::~wstring(v30);
  v18 = (const unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v19 = *(_QWORD *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
                     (char *)this + 16,
                     &v27,
                     &v26)
      + 40LL;
  if ( *((_QWORD *)v18 + 3) <= 7u )
    v20 = v18;
  else
    v20 = *(const unsigned int **)v18;
  v23 = v20;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               v19,
               &v23) = v18;
  if ( *((_QWORD *)v18 + 3) <= 7u )
    v21 = v18;
  else
    v21 = *(const unsigned int **)v18;
  v23 = v21;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               (char *)this + 32,
               &v23) = v18;
  if ( a13 )
  {
    v23 = v18;
    std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(
      (char *)this + 48,
      &v27,
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
0x1800123fc  push    rbx
0x1800123fe  push    rsi
0x1800123ff  push    rdi
0x180012400  push    r12
0x180012402  push    r13
0x180012404  push    r14
0x180012406  push    r15
0x180012408  sub     rsp, 170h
0x18001240f  mov     rax, cs:__security_cookie
0x180012416  xor     rax, rsp
0x180012419  mov     [rsp+1A8h+var_48], rax
0x180012421  mov     r12d, r9d
0x180012424  mov     r15d, r8d
0x180012427  mov     rbx, rdx
0x18001242a  mov     rdi, rcx
0x18001242d  mov     rsi, [rsp+1A8h+arg_48]
0x180012435  mov     [rsp+1A8h+var_130], r8d
0x18001243a  mov     r13, [rsp+1A8h+arg_20]
0x180012442  mov     rax, [rsp+1A8h+arg_28]
0x18001244a  mov     [rsp+1A8h+var_140], rax
0x18001244f  mov     rax, [rsp+1A8h+arg_30]
0x180012457  mov     [rsp+1A8h+var_128], rax
0x18001245f  mov     eax, [rsp+1A8h+arg_38]
0x180012466  mov     [rsp+1A8h+var_134], eax
0x18001246a  mov     eax, [rsp+1A8h+arg_40]
0x180012471  mov     [rsp+1A8h+var_138], eax
0x180012475  mov     al, [rsp+1A8h+arg_50]
0x18001247c  mov     [rsp+1A8h+var_148], al
0x180012480  mov     rdx, [rsp+1A8h+arg_58]
0x180012488  mov     r14, [rsp+1A8h+arg_60]
0x180012490  lea     rcx, [rsp+1A8h+var_F8]
0x180012498  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001249d  nop
0x18001249e  mov     rdx, rbx
0x1800124a1  lea     rcx, [rsp+1A8h+var_118]
0x1800124a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800124ae  nop
0x1800124af  mov     al, [rsp+1A8h+var_148]
0x1800124b3  mov     [rsp+1A8h+var_150], al
0x1800124b7  mov     [rsp+1A8h+var_158], rsi
0x1800124bc  mov     eax, [rsp+1A8h+var_138]
0x1800124c0  mov     [rsp+1A8h+var_160], eax
0x1800124c4  mov     eax, [rsp+1A8h+var_134]
0x1800124c8  mov     [rsp+1A8h+var_168], eax
0x1800124cc  mov     [rsp+1A8h+var_170], r15d
0x1800124d1  mov     rax, [rsp+1A8h+var_128]
0x1800124d9  mov     [rsp+1A8h+var_178], rax
0x1800124de  mov     rax, [rsp+1A8h+var_140]
0x1800124e3  mov     [rsp+1A8h+var_180], rax
0x1800124e8  mov     [rsp+1A8h+var_188], r13
0x1800124ed  mov     r9d, r12d
0x1800124f0  lea     r8, [rsp+1A8h+var_F8]
0x1800124f8  lea     rdx, [rsp+1A8h+var_118]
0x180012500  lea     rcx, [rsp+1A8h+var_D8]
0x180012508  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18001250d  nop
0x18001250e  mov     r8, rax
0x180012511  mov     rdx, [rdi]
0x180012514  mov     rcx, rdi
0x180012517  call    ??$_Emplace@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@QEAU21@$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18001251c  nop
0x18001251d  lea     rcx, [rsp+1A8h+var_D8]; this
0x180012525  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x18001252a  nop
0x18001252b  lea     rcx, [rsp+1A8h+var_118]
0x180012533  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012538  nop
0x180012539  lea     rcx, [rsp+1A8h+var_F8]
0x180012541  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012546  mov     rax, [rdi]
0x180012549  mov     rbx, [rax+8]
0x18001254d  add     rbx, 10h
0x180012551  lea     rcx, [rdi+10h]
0x180012555  lea     r8, [rsp+1A8h+var_130]
0x18001255a  lea     rdx, [rsp+1A8h+var_128]
0x180012562  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180012567  mov     rcx, [rax]
0x18001256a  add     rcx, 28h ; '('
0x18001256e  cmp     qword ptr [rbx+18h], 7
0x180012573  jbe     short loc_18001257A
0x180012575  mov     rax, [rbx]
0x180012578  jmp     short loc_18001257D
0x18001257a  mov     rax, rbx
0x18001257d  mov     [rsp+1A8h+var_140], rax
0x180012582  lea     rdx, [rsp+1A8h+var_140]
0x180012587  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18001258c  mov     [rax], rbx
0x18001258f  cmp     qword ptr [rbx+18h], 7
0x180012594  jbe     short loc_18001259B
0x180012596  mov     rax, [rbx]
0x180012599  jmp     short loc_18001259E
0x18001259b  mov     rax, rbx
0x18001259e  mov     [rsp+1A8h+var_140], rax
0x1800125a3  lea     rcx, [rdi+20h]
0x1800125a7  lea     rdx, [rsp+1A8h+var_140]
0x1800125ac  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x1800125b1  mov     [rax], rbx
0x1800125b4  test    r14, r14
0x1800125b7  jz      short loc_1800125DE
0x1800125b9  mov     [rsp+1A8h+var_140], rbx
0x1800125be  lea     rcx, [rdi+30h]
0x1800125c2  lea     r8, [rsp+1A8h+var_140]
0x1800125c7  lea     rdx, [rsp+1A8h+var_128]
0x1800125cf  call    ??$_Emplace@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)
0x1800125d4  mov     al, [rsp+1A8h+var_120]
0x1800125db  mov     [r14], al
0x1800125de  test    rsi, rsi
0x1800125e1  jz      short loc_1800125F0
0x1800125e3  cmp     dword ptr [rsi], 0
0x1800125e6  jz      short loc_1800125F0
0x1800125e8  mov     rax, [rbx+60h]
0x1800125ec  mov     [rsi+8], rax
0x1800125f0  xor     eax, eax
0x1800125f2  jmp     short loc_1800125F9
0x1800125f4  mov     eax, 8007000Eh
0x1800125f9  mov     rcx, [rsp+1A8h+var_48]
0x180012601  xor     rcx, rsp; StackCookie
0x180012604  call    __security_check_cookie
0x180012609  add     rsp, 170h
0x180012610  pop     r15
0x180012612  pop     r14
0x180012614  pop     r13
0x180012616  pop     r12
0x180012618  pop     rdi
0x180012619  pop     rsi
0x18001261a  pop     rbx
0x18001261b  retn
```

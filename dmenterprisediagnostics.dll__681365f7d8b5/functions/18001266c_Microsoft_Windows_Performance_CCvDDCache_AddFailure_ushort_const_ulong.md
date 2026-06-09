# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x18001266c`
- end: `0x1800127be`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `338`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800129cc`

## callees

- `0x180001800`
- `0x180003768`
- `0x180003b14`
- `0x1800102a8`
- `0x180010c84`
- `0x18001135c`
- `0x180011eec`
- `0x1800122cc`
- `0x18001266c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  int v11; // [rsp+60h] [rbp-108h] BYREF
  _QWORD *v12; // [rsp+68h] [rbp-100h] BYREF
  _BYTE v13[32]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v14[32]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v15[144]; // [rsp+B0h] [rbp-B8h] BYREF

  v11 = a3;
  std::wstring::wstring(v14, &qword_18002AA30);
  std::wstring::wstring(v13, a2);
  v6 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
         (__int64)v15,
         (__int64)v13,
         (__int64)v14,
         0,
         0,
         0,
         0,
         a3,
         0,
         0,
         0,
         0);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
    this,
    *(_QWORD *)this,
    v6);
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v15);
  std::wstring::~wstring(v13);
  std::wstring::~wstring(v14);
  v7 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v8 = *(_QWORD *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
                    (char *)this + 16,
                    v13,
                    &v11)
     + 40LL;
  if ( v7[3] <= 7u )
    v9 = v7;
  else
    v9 = (_QWORD *)*v7;
  v12 = v9;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               v8,
               &v12) = 0;
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  v12 = v7;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               (char *)this + 32,
               &v12) = 0;
  return 0;
}

```

## disassembly

```asm
0x18001266c  push    rbx
0x18001266e  push    rsi
0x18001266f  push    rdi
0x180012670  sub     rsp, 150h
0x180012677  mov     rax, cs:__security_cookie
0x18001267e  xor     rax, rsp
0x180012681  mov     [rsp+168h+var_28], rax
0x180012689  mov     ebx, r8d
0x18001268c  mov     rsi, rdx
0x18001268f  mov     rdi, rcx
0x180012692  mov     [rsp+168h+var_108], ebx
0x180012696  lea     rdx, qword_18002AA30
0x18001269d  lea     rcx, [rsp+168h+var_D8]
0x1800126a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800126aa  nop
0x1800126ab  mov     rdx, rsi
0x1800126ae  lea     rcx, [rsp+168h+var_F8]
0x1800126b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800126b8  nop
0x1800126b9  xor     esi, esi
0x1800126bb  mov     [rsp+168h+var_110], sil
0x1800126c0  mov     [rsp+168h+var_118], rsi
0x1800126c5  mov     [rsp+168h+var_120], esi
0x1800126c9  mov     [rsp+168h+var_128], esi
0x1800126cd  mov     [rsp+168h+var_130], ebx
0x1800126d1  mov     [rsp+168h+var_138], rsi
0x1800126d6  mov     [rsp+168h+var_140], rsi
0x1800126db  mov     [rsp+168h+var_148], rsi
0x1800126e0  xor     r9d, r9d
0x1800126e3  lea     r8, [rsp+168h+var_D8]
0x1800126eb  lea     rdx, [rsp+168h+var_F8]
0x1800126f0  lea     rcx, [rsp+168h+var_B8]
0x1800126f8  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x1800126fd  nop
0x1800126fe  mov     r8, rax
0x180012701  mov     rdx, [rdi]
0x180012704  mov     rcx, rdi
0x180012707  call    ??$_Emplace@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@QEAU21@$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18001270c  nop
0x18001270d  lea     rcx, [rsp+168h+var_B8]; this
0x180012715  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x18001271a  nop
0x18001271b  lea     rcx, [rsp+168h+var_F8]
0x180012720  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012725  nop
0x180012726  lea     rcx, [rsp+168h+var_D8]
0x18001272e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012733  mov     rax, [rdi]
0x180012736  mov     rbx, [rax+8]
0x18001273a  add     rbx, 10h
0x18001273e  lea     rcx, [rdi+10h]
0x180012742  lea     r8, [rsp+168h+var_108]
0x180012747  lea     rdx, [rsp+168h+var_F8]
0x18001274c  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180012751  mov     rcx, [rax]
0x180012754  add     rcx, 28h ; '('
0x180012758  cmp     qword ptr [rbx+18h], 7
0x18001275d  jbe     short loc_180012764
0x18001275f  mov     rax, [rbx]
0x180012762  jmp     short loc_180012767
0x180012764  mov     rax, rbx
0x180012767  mov     [rsp+168h+var_100], rax
0x18001276c  lea     rdx, [rsp+168h+var_100]
0x180012771  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180012776  mov     [rax], rsi
0x180012779  cmp     qword ptr [rbx+18h], 7
0x18001277e  jbe     short loc_180012783
0x180012780  mov     rbx, [rbx]
0x180012783  mov     [rsp+168h+var_100], rbx
0x180012788  lea     rcx, [rdi+20h]
0x18001278c  lea     rdx, [rsp+168h+var_100]
0x180012791  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180012796  mov     [rax], rsi
0x180012799  xor     eax, eax
0x18001279b  jmp     short loc_1800127A2
0x18001279d  mov     eax, 8007000Eh
0x1800127a2  mov     rcx, [rsp+168h+var_28]
0x1800127aa  xor     rcx, rsp; StackCookie
0x1800127ad  call    __security_check_cookie
0x1800127b2  add     rsp, 150h
0x1800127b9  pop     rdi
0x1800127ba  pop     rsi
0x1800127bb  pop     rbx
0x1800127bc  retn
```

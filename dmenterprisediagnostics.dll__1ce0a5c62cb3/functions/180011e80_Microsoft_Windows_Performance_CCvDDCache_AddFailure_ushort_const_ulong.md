# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x180011e80`
- end: `0x180011fe4`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `356`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800121e8`

## callees

- `0x1800017e0`
- `0x180003714`
- `0x180003b10`
- `0x1800104f0`
- `0x180010610`
- `0x180010bc8`
- `0x180011724`
- `0x180011e80`
- `0x180018014`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // rdx
  _QWORD *v7; // rbx
  __int64 *v8; // rcx
  _QWORD *v9; // rax
  int v11; // [rsp+60h] [rbp-108h] BYREF
  _QWORD *v12; // [rsp+68h] [rbp-100h] BYREF
  _BYTE v13[32]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v14[32]; // [rsp+90h] [rbp-D8h] BYREF
  void *v15[18]; // [rsp+B0h] [rbp-B8h] BYREF

  v11 = a3;
  std::wstring::wstring((__int64)v14, (__int64)&qword_180029A30);
  std::wstring::wstring((__int64)v13, (__int64)a2);
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
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v6);
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(v15);
  std::wstring::~wstring((__int64)v13);
  std::wstring::~wstring((__int64)v14);
  v7 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v8 = (__int64 *)(*(_QWORD *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
                                (_QWORD *)this + 2,
                                (__int64)v14,
                                (unsigned int *)&v11)
                 + 40LL);
  if ( v7[3] <= 7u )
    v9 = v7;
  else
    v9 = (_QWORD *)*v7;
  v12 = v9;
  *(_QWORD *)(*(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
                           v8,
                           (__int64)v13,
                           &v12)
            + 40LL) = 0;
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  v12 = v7;
  *(_QWORD *)(*(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
                           (__int64 *)this + 4,
                           (__int64)v13,
                           &v12)
            + 40LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180011e80  push    rbx
0x180011e82  push    rsi
0x180011e83  push    rdi
0x180011e84  sub     rsp, 150h
0x180011e8b  mov     rax, cs:__security_cookie
0x180011e92  xor     rax, rsp
0x180011e95  mov     [rsp+168h+var_28], rax
0x180011e9d  mov     ebx, r8d
0x180011ea0  mov     rsi, rdx
0x180011ea3  mov     rdi, rcx
0x180011ea6  mov     [rsp+168h+var_108], ebx
0x180011eaa  lea     rdx, qword_180029A30
0x180011eb1  lea     rcx, [rsp+168h+var_D8]
0x180011eb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ebe  nop
0x180011ebf  mov     rdx, rsi
0x180011ec2  lea     rcx, [rsp+168h+var_F8]
0x180011ec7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ecc  nop
0x180011ecd  xor     esi, esi
0x180011ecf  mov     [rsp+168h+var_110], sil
0x180011ed4  mov     [rsp+168h+var_118], rsi
0x180011ed9  mov     [rsp+168h+var_120], esi
0x180011edd  mov     [rsp+168h+var_128], esi
0x180011ee1  mov     [rsp+168h+var_130], ebx
0x180011ee5  mov     [rsp+168h+var_138], rsi
0x180011eea  mov     [rsp+168h+var_140], rsi
0x180011eef  mov     [rsp+168h+var_148], rsi
0x180011ef4  xor     r9d, r9d
0x180011ef7  lea     r8, [rsp+168h+var_D8]
0x180011eff  lea     rdx, [rsp+168h+var_F8]
0x180011f04  lea     rcx, [rsp+168h+var_B8]
0x180011f0c  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180011f11  nop
0x180011f12  mov     rdx, rax
0x180011f15  mov     rcx, rdi
0x180011f18  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x180011f1d  nop
0x180011f1e  lea     rcx, [rsp+168h+var_B8]; this
0x180011f26  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180011f2b  nop
0x180011f2c  lea     rcx, [rsp+168h+var_F8]
0x180011f31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f36  nop
0x180011f37  lea     rcx, [rsp+168h+var_D8]
0x180011f3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f44  mov     rax, [rdi]
0x180011f47  mov     rbx, [rax+8]
0x180011f4b  add     rbx, 10h
0x180011f4f  lea     rcx, [rdi+10h]
0x180011f53  lea     r8, [rsp+168h+var_108]
0x180011f58  lea     rdx, [rsp+168h+var_D8]
0x180011f60  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180011f65  mov     rcx, [rax]
0x180011f68  add     rcx, 28h ; '('
0x180011f6c  cmp     qword ptr [rbx+18h], 7
0x180011f71  jbe     short loc_180011F78
0x180011f73  mov     rax, [rbx]
0x180011f76  jmp     short loc_180011F7B
0x180011f78  mov     rax, rbx
0x180011f7b  mov     [rsp+168h+var_100], rax
0x180011f80  lea     r8, [rsp+168h+var_100]
0x180011f85  lea     rdx, [rsp+168h+var_F8]
0x180011f8a  call    ??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)
0x180011f8f  mov     rax, [rax]
0x180011f92  mov     [rax+28h], rsi
0x180011f96  cmp     qword ptr [rbx+18h], 7
0x180011f9b  jbe     short loc_180011FA0
0x180011f9d  mov     rbx, [rbx]
0x180011fa0  mov     [rsp+168h+var_100], rbx
0x180011fa5  lea     rcx, [rdi+20h]
0x180011fa9  lea     r8, [rsp+168h+var_100]
0x180011fae  lea     rdx, [rsp+168h+var_F8]
0x180011fb3  call    ??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)
0x180011fb8  mov     rax, [rax]
0x180011fbb  mov     [rax+28h], rsi
0x180011fbf  xor     eax, eax
0x180011fc1  jmp     short loc_180011FC8
0x180011fc3  mov     eax, 8007000Eh
0x180011fc8  mov     rcx, [rsp+168h+var_28]
0x180011fd0  xor     rcx, rsp; StackCookie
0x180011fd3  call    __security_check_cookie
0x180011fd8  add     rsp, 150h
0x180011fdf  pop     rdi
0x180011fe0  pop     rsi
0x180011fe1  pop     rbx
0x180011fe2  retn
```

# PackageNode::RuntimeClassInitialize(IConfigManager2URI *)

- ea: `0x1800133d8`
- end: `0x1800136ca`
- name: `?RuntimeClassInitialize@PackageNode@@QEAAJPEAUIConfigManager2URI@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(PackageNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e004`

## callees

- `0x180001b14`
- `0x180006974`
- `0x1800082dc`
- `0x18000848c`
- `0x18000918c`
- `0x1800133d8`
- `0x180031968`
- `0x1800319ec`
- `0x180031ab0`
- `0x1800322c0`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800135df`
- `msvcrt!_wcsicmp` at `0x1800135df`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013600`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013671`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013600`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013671`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PackageNode::RuntimeClassInitialize(PackageNode *this, struct IConfigManager2URI *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  int v14; // esi
  void *v15; // rax
  int v16; // [rsp+20h] [rbp-B8h]
  int v17[2]; // [rsp+30h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD v19[3]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-80h] BYREF
  __int16 v21; // [rsp+78h] [rbp-60h]
  __int64 v22; // [rsp+88h] [rbp-50h]
  __int64 v23; // [rsp+90h] [rbp-48h]
  void *v24[3]; // [rsp+98h] [rbp-40h] BYREF
  unsigned __int64 v25; // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  String1 = 0;
  v17[0] = 0;
  v4 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, v17);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( v17[0] == 1 )
    {
      v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(
             a2,
             0,
             &String1);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v23 = 7;
        v22 = 0;
        v21 = 0;
        PackageCollector::PackageCollector((PackageCollector *)v20);
        PackageCollector::AddDefaultSearchPaths((PackageCollector *)v20);
        PackageCollector::Search((__int64)v20, v19);
        v9 = (_QWORD *)v19[0];
        v10 = (_QWORD *)v19[1];
        while ( 1 )
        {
          if ( v9 == v10 )
          {
            std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v19);
            PackageCollector::~PackageCollector((PackageCollector *)v20);
            if ( (unsigned int)dword_1800495B0 > 2
              && (qword_1800495C0 & 0x400000000000LL) != 0
              && (qword_1800495C8 & 0x400000000000LL) == qword_1800495C8 )
            {
              *(_QWORD *)v17 = String1;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                qword_1800495C8,
                (unsigned int)&unk_180041220,
                v11,
                v12,
                (__int64)v17);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2F,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
              (const char *)0x86000002LL,
              v16);
            return 2248146946LL;
          }
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 72LL))(*v9);
          v13 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v9 + 16LL))(*v9, v24);
          if ( *(_QWORD *)(v13 + 24) >= 8u )
            v13 = *(_QWORD *)v13;
          v14 = _wcsicmp(String1, (const wchar_t *)v13);
          if ( v25 >= 8 )
            operator delete(v24[0]);
          if ( !v14 )
            break;
          ++v9;
        }
        if ( (PackageNode *)((char *)this + 24) != (PackageNode *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 56LL))(*v9) )
          std::wstring::assign((char *)this + 24);
        v15 = (void *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v9 + 16LL))(*v9, v24);
        std::wstring::operator=((char *)this + 56, v15);
        if ( v25 >= 8 )
          operator delete(v24[0]);
        std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v19);
        PackageCollector::~PackageCollector((PackageCollector *)v20);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
          (const char *)(unsigned int)v7,
          v16);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
        (const char *)0x80070057LL,
        v16);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
      (const char *)(unsigned int)v4,
      v16);
    return v5;
  }
}

```

## disassembly

```asm
0x1800133d8  mov     [rsp+arg_10], rbx
0x1800133dd  push    rsi
0x1800133de  push    rdi
0x1800133df  push    r14
0x1800133e1  sub     rsp, 0C0h
0x1800133e8  mov     rax, cs:__security_cookie
0x1800133ef  xor     rax, rsp
0x1800133f2  mov     [rsp+0D8h+var_20], rax
0x1800133fa  mov     rdi, rdx
0x1800133fd  mov     r14, rcx
0x180013400  mov     [rsp+0D8h+String1], 0
0x180013409  mov     [rsp+0D8h+var_A8], 0
0x180013411  mov     rax, [rdx]
0x180013414  lea     rdx, [rsp+0D8h+var_A8]
0x180013419  mov     rcx, rdi
0x18001341c  mov     rax, [rax+88h]
0x180013423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013428  mov     ebx, eax
0x18001342a  test    eax, eax
0x18001342c  jns     short loc_180013451
0x18001342e  mov     rcx, [rsp+0D8h]; this
0x180013436  mov     r9d, eax; char *
0x180013439  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x180013440  mov     edx, 14h; void *
0x180013445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001344a  mov     eax, ebx
0x18001344c  jmp     loc_1800136A5
0x180013451  cmp     [rsp+0D8h+var_A8], 1
0x180013456  jz      short loc_180013480
0x180013458  mov     rcx, [rsp+0D8h]; this
0x180013460  mov     ebx, 80070057h
0x180013465  mov     r9d, ebx; char *
0x180013468  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x18001346f  mov     edx, 15h; void *
0x180013474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013479  mov     eax, ebx
0x18001347b  jmp     loc_1800136A5
0x180013480  mov     rax, [rdi]
0x180013483  lea     r8, [rsp+0D8h+String1]
0x180013488  xor     edx, edx
0x18001348a  mov     rcx, rdi
0x18001348d  mov     rax, [rax+58h]
0x180013491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013496  mov     ebx, eax
0x180013498  test    eax, eax
0x18001349a  jns     short loc_1800134BF
0x18001349c  mov     rcx, [rsp+0D8h]; this
0x1800134a4  mov     r9d, eax; char *
0x1800134a7  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x1800134ae  mov     edx, 16h; void *
0x1800134b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134b8  mov     eax, ebx
0x1800134ba  jmp     loc_1800136A5
0x1800134bf  mov     [rsp+0D8h+var_48], 7
0x1800134cb  mov     [rsp+0D8h+var_50], 0
0x1800134d7  xor     eax, eax
0x1800134d9  mov     [rsp+0D8h+var_60], ax
0x1800134de  lea     rcx, [rsp+0D8h+var_80]; this
0x1800134e3  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x1800134e8  nop
0x1800134e9  lea     rcx, [rsp+0D8h+var_80]; this
0x1800134ee  call    ?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ; PackageCollector::AddDefaultSearchPaths(void)
0x1800134f3  lea     rdx, [rsp+0D8h+var_98]
0x1800134f8  lea     rcx, [rsp+0D8h+var_80]
0x1800134fd  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x180013502  nop
0x180013503  mov     rbx, [rsp+0D8h+var_98]
0x180013508  mov     rdi, [rsp+0D8h+var_90]
0x18001350d  cmp     rbx, rdi
0x180013510  jnz     loc_1800135A7
0x180013516  lea     rcx, [rsp+0D8h+var_98]
0x18001351b  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180013520  nop
0x180013521  lea     rcx, [rsp+0D8h+var_80]; this
0x180013526  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x18001352b  nop
0x18001352c  mov     eax, cs:dword_1800495B0
0x180013532  cmp     eax, 2
0x180013535  jbe     short loc_18001357F
0x180013537  mov     rcx, cs:qword_1800495C8
0x18001353e  mov     rax, cs:qword_1800495C0
0x180013545  mov     rdx, 400000000000h
0x18001354f  test    rdx, rax
0x180013552  jz      short loc_18001357F
0x180013554  mov     rax, rcx
0x180013557  and     rax, rdx
0x18001355a  cmp     rax, rcx
0x18001355d  jnz     short loc_18001357F
0x18001355f  mov     rax, [rsp+0D8h+String1]
0x180013564  mov     qword ptr [rsp+0D8h+var_A8], rax
0x180013569  lea     rax, [rsp+0D8h+var_A8]
0x18001356e  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x180013573  lea     rdx, unk_180041220
0x18001357a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001357f  mov     rcx, [rsp+0D8h]; this
0x180013587  mov     ebx, 86000002h
0x18001358c  mov     r9d, ebx; char *
0x18001358f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x180013596  mov     edx, 2Fh ; '/'; void *
0x18001359b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800135a0  mov     eax, ebx
0x1800135a2  jmp     loc_1800136A5
0x1800135a7  mov     rcx, [rbx]
0x1800135aa  mov     rax, [rcx]
0x1800135ad  mov     rax, [rax+48h]
0x1800135b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b6  mov     rcx, [rbx]
0x1800135b9  mov     rax, [rcx]
0x1800135bc  lea     rdx, [rsp+0D8h+var_40]
0x1800135c4  mov     rax, [rax+10h]
0x1800135c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135cd  cmp     qword ptr [rax+18h], 8
0x1800135d2  jb      short loc_1800135D7
0x1800135d4  mov     rax, [rax]
0x1800135d7  mov     rdx, rax; String2
0x1800135da  mov     rcx, [rsp+0D8h+String1]; String1
0x1800135df  call    cs:__imp__wcsicmp
0x1800135e6  nop     dword ptr [rax+rax+00h]
0x1800135eb  mov     esi, eax
0x1800135ed  cmp     [rsp+0D8h+var_28], 8
0x1800135f6  jb      short loc_18001360C
0x1800135f8  mov     rcx, [rsp+0D8h+var_40]
0x180013600  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013607  nop     dword ptr [rax+rax+00h]
0x18001360c  test    esi, esi
0x18001360e  jnz     loc_180013698
0x180013614  mov     rcx, [rbx]
0x180013617  mov     rax, [rcx]
0x18001361a  mov     rax, [rax+38h]
0x18001361e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013623  lea     rcx, [r14+18h]; void *
0x180013627  cmp     rcx, rax
0x18001362a  jz      short loc_18001363B
0x18001362c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013630  xor     r8d, r8d
0x180013633  mov     rdx, rax
0x180013636  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001363b  mov     rcx, [rbx]
0x18001363e  mov     rax, [rcx]
0x180013641  lea     rdx, [rsp+0D8h+var_40]
0x180013649  mov     rax, [rax+10h]
0x18001364d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013652  lea     rcx, [r14+38h]; void *
0x180013656  mov     rdx, rax; Src
0x180013659  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001365e  cmp     [rsp+0D8h+var_28], 8
0x180013667  jb      short loc_18001367E
0x180013669  mov     rcx, [rsp+0D8h+var_40]
0x180013671  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013678  nop     dword ptr [rax+rax+00h]
0x18001367d  nop
0x18001367e  lea     rcx, [rsp+0D8h+var_98]
0x180013683  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180013688  nop
0x180013689  lea     rcx, [rsp+0D8h+var_80]; this
0x18001368e  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x180013693  nop
0x180013694  xor     eax, eax
0x180013696  jmp     short loc_1800136A5
0x180013698  add     rbx, 8
0x18001369c  jmp     loc_18001350D
0x1800136a1  mov     eax, [rsp+0D8h+var_A8]
0x1800136a5  mov     rcx, [rsp+0D8h+var_20]
0x1800136ad  xor     rcx, rsp; StackCookie
0x1800136b0  call    __security_check_cookie
0x1800136b5  mov     rbx, [rsp+0D8h+arg_10]
0x1800136bd  add     rsp, 0C0h
0x1800136c4  pop     r14
0x1800136c6  pop     rdi
0x1800136c7  pop     rsi
0x1800136c8  retn
```

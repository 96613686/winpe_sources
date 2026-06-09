# AssetElementNode::RuntimeClassInitialize(IConfigManager2URI *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026dbc`
- end: `0x1800272dd`
- name: `?RuntimeClassInitialize@AssetElementNode@@QEAAJPEAUIConfigManager2URI@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `1313`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800131d0`

## callees

- `0x180001c10`
- `0x180006974`
- `0x18000848c`
- `0x1800090e0`
- `0x18000918c`
- `0x180009fac`
- `0x180026dbc`
- `0x1800272e4`
- `0x180027d6c`
- `0x180028050`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027236`
- `msvcrt!_wcsicmp` at `0x180027236`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027004`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002703c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027004`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002703c`

## string_xrefs

- `0x18002722c`: `Temporary Runtime Package Command Files`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall AssetElementNode::RuntimeClassInitialize(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rcx
  struct IWpxConfig *v15; // rbx
  struct IWpxConfig **v16; // rdi
  struct IWpxConfig *v17; // rcx
  _QWORD *v18; // rbx
  __int64 v19; // r8
  _QWORD *DeploymentPath; // rax
  const wchar_t *v21; // rax
  __int64 *NamedElement; // rax
  __int64 *v23; // rdi
  __int64 v24; // r14
  __int64 v25; // rcx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  _WORD *v29; // rax
  __int64 v30; // r8
  int v31; // eax
  const wchar_t *v32; // rax
  int v33; // [rsp+20h] [rbp-E8h]
  int v34; // [rsp+30h] [rbp-D8h] BYREF
  struct IWpxConfig *v35; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C8h] BYREF
  void *Src; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B8h] BYREF
  int v39[2]; // [rsp+58h] [rbp-B0h] BYREF
  _WORD v40[8]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+70h] [rbp-98h]
  __int64 v42; // [rsp+78h] [rbp-90h]
  struct IWpxConfig **v43; // [rsp+80h] [rbp-88h] BYREF
  struct IWpxConfig *v44; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-78h]
  unsigned __int64 v46; // [rsp+98h] [rbp-70h]
  void *v47[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v48; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v34 = 0;
  Src = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v34);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v34 == 1 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)a2 + 88LL))(a2, 0, &Src);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v38 = 0;
        v43 = (struct IWpxConfig **)&v38;
        v44 = 0;
        LOBYTE(v45) = 1;
        v42 = 7;
        v41 = 0;
        v40[0] = 0;
        if ( *(_WORD *)Src )
        {
          v13 = -1;
          do
            ++v13;
          while ( *((_WORD *)Src + v13) );
        }
        std::wstring::assign(v40, Src);
        AssetElementNode::_GetWpxInfoForPath(v14, &v35, (__int64)v40, &v44);
        if ( (_BYTE)v45 )
        {
          v15 = v44;
          v16 = v43;
          v17 = *v43;
          if ( v44 != *v43 )
          {
            if ( v17 )
              (*(void (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v17 + 304LL))(v17);
            *v16 = v15;
          }
        }
        v18 = (_QWORD *)(a1 + 72);
        if ( a1 + 72 != a4 )
          std::wstring::assign((void *)(a1 + 72));
        *(_DWORD *)(a1 + 172) = 0;
        v46 = 7;
        v45 = 0;
        LOWORD(v43) = 0;
        if ( *(_WORD *)Src )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_WORD *)Src + v19) );
        }
        std::wstring::assign(&v43, Src);
        DeploymentPath = AssetElementNode::_GetDeploymentPath(a1, v47, &v35, (__int64)&v43);
        std::wstring::operator=((void *)(a1 + 136), DeploymentPath);
        if ( v48 >= 8 )
          operator delete(v47[0]);
        v48 = 7;
        v47[2] = 0;
        LOWORD(v47[0]) = 0;
        if ( v46 >= 8 )
          operator delete(v43);
        v21 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v35 + 16LL))(v35);
        NamedElement = AssetElementNode::s_GetNamedElement(&v36, v21, a3, (_QWORD *)(a1 + 24));
        v23 = (__int64 *)(a1 + 32);
        if ( (__int64 *)(a1 + 32) != NamedElement )
        {
          v24 = *NamedElement;
          *NamedElement = 0;
          v25 = *v23;
          if ( v24 != *v23 )
          {
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
            *v23 = v24;
          }
        }
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
        if ( *v23 )
        {
          v29 = (_WORD *)(*(__int64 (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v35 + 16LL))(v35);
          if ( *v29 )
          {
            v30 = -1;
            do
              ++v30;
            while ( v29[v30] );
          }
          std::wstring::assign((void *)(a1 + 104), v29);
          if ( (_QWORD *)(a1 + 40) != a3 )
            std::wstring::assign((void *)(a1 + 40));
          v36 = 0;
          v31 = (*(__int64 (__fastcall **)(struct IWpxConfig *, __int64 *))(*(_QWORD *)v35 + 296LL))(v35, &v36);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x148,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
              (const char *)(unsigned int)v31,
              v33);
          v32 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 184LL))(v36);
          if ( !v32 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x14A,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
              (const char *)0x80070057LL,
              v33);
          *(_DWORD *)(a1 + 168) = _wcsicmp(v32, L"Temporary Runtime Package Command Files") == 0;
          if ( v35 )
            (*(void (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v35 + 736LL))(v35);
          if ( v38 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 304LL))(v38);
          return 0;
        }
        else
        {
          if ( (unsigned int)dword_1800495B0 > 2
            && (qword_1800495C0 & 0x400000000000LL) != 0
            && (qword_1800495C8 & 0x400000000000LL) == qword_1800495C8 )
          {
            v36 = (*(__int64 (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v35 + 16LL))(v35);
            if ( *(_QWORD *)(a1 + 96) >= 8u )
              v18 = (_QWORD *)*v18;
            *(_QWORD *)v39 = v18;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v26,
              (unsigned int)byte_180041723,
              v27,
              v28,
              (__int64)v39,
              (__int64)&v36);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
            (const char *)0x86000002LL,
            v33);
          if ( v35 )
            (*(void (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v35 + 736LL))(v35);
          if ( v38 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 304LL))(v38);
          return 2248146946LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)(unsigned int)v11,
          v33);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)0x80070057LL,
        v33);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v8,
      v33);
    return v9;
  }
}

```

## disassembly

```asm
0x180026dbc  push    rbx
0x180026dbe  push    rsi
0x180026dbf  push    rdi
0x180026dc0  push    r12
0x180026dc2  push    r13
0x180026dc4  push    r14
0x180026dc6  push    r15
0x180026dc8  sub     rsp, 0D0h
0x180026dcf  mov     rax, cs:__security_cookie
0x180026dd6  xor     rax, rsp
0x180026dd9  mov     [rsp+108h+var_48], rax
0x180026de1  mov     r14, r9
0x180026de4  mov     r12, r8
0x180026de7  mov     rdi, rdx
0x180026dea  mov     rsi, rcx
0x180026ded  xor     r13d, r13d
0x180026df0  mov     [rsp+108h+var_D8], r13d
0x180026df5  mov     [rsp+108h+Src], r13
0x180026dfa  mov     rax, [rdx]
0x180026dfd  lea     rdx, [rsp+108h+var_D8]
0x180026e02  mov     rcx, rdi
0x180026e05  mov     rax, [rax+88h]
0x180026e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e11  mov     ebx, eax
0x180026e13  test    eax, eax
0x180026e15  jns     short loc_180026E39
0x180026e17  mov     rcx, [rsp+108h]; this
0x180026e1f  mov     r9d, eax; char *
0x180026e22  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026e29  lea     edx, [r13+1Dh]; void *
0x180026e2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e32  mov     eax, ebx
0x180026e34  jmp     loc_18002728C
0x180026e39  cmp     [rsp+108h+var_D8], 1
0x180026e3e  jz      short loc_180026E69
0x180026e40  mov     rcx, [rsp+108h]; this
0x180026e48  mov     r9d, 80070057h; char *
0x180026e4e  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026e55  mov     edx, 1Eh; void *
0x180026e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e5f  mov     eax, 80070057h
0x180026e64  jmp     loc_18002728C
0x180026e69  mov     rax, [rdi]
0x180026e6c  lea     r8, [rsp+108h+Src]
0x180026e71  xor     edx, edx
0x180026e73  mov     rcx, rdi
0x180026e76  mov     rax, [rax+58h]
0x180026e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e7f  mov     ebx, eax
0x180026e81  test    eax, eax
0x180026e83  jns     short loc_180026EA8
0x180026e85  mov     rcx, [rsp+108h]; this
0x180026e8d  mov     r9d, eax; char *
0x180026e90  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026e97  mov     edx, 1Fh; void *
0x180026e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ea1  mov     eax, ebx
0x180026ea3  jmp     loc_18002728C
0x180026ea8  mov     [rsp+108h+var_B8], r13
0x180026ead  lea     rax, [rsp+108h+var_B8]
0x180026eb2  mov     [rsp+108h+var_88], rax
0x180026eba  mov     [rsp+108h+var_80], r13
0x180026ec2  mov     byte ptr [rsp+108h+var_78], 1
0x180026eca  mov     rdx, [rsp+108h+Src]; Src
0x180026ecf  mov     edi, 7
0x180026ed4  mov     [rsp+108h+var_90], rdi
0x180026ed9  mov     [rsp+108h+var_98], r13
0x180026ede  mov     [rsp+108h+var_A8], r13w
0x180026ee4  or      r15, 0FFFFFFFFFFFFFFFFh
0x180026ee8  cmp     [rdx], r13w
0x180026eec  jnz     short loc_180026EF3
0x180026eee  mov     r8, r13
0x180026ef1  jmp     short loc_180026F00
0x180026ef3  mov     r8, r15
0x180026ef6  inc     r8
0x180026ef9  cmp     [rdx+r8*2], r13w
0x180026efe  jnz     short loc_180026EF6
0x180026f00  lea     rcx, [rsp+108h+var_A8]; void *
0x180026f05  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180026f0a  lea     r9, [rsp+108h+var_80]
0x180026f12  lea     r8, [rsp+108h+var_A8]
0x180026f17  lea     rdx, [rsp+108h+var_D0]
0x180026f1c  call    ?_GetWpxInfoForPath@AssetElementNode@@AEAA?AV?$unique_ptr@UIWpxSetting@@U?$ProvReleaser@UIWpxSetting@@@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAPEAUIWpxConfig@@@Z; AssetElementNode::_GetWpxInfoForPath(std::wstring,IWpxConfig * *)
0x180026f21  nop
0x180026f22  cmp     byte ptr [rsp+108h+var_78], r13b
0x180026f2a  jz      short loc_180026F60
0x180026f2c  mov     rbx, [rsp+108h+var_80]
0x180026f34  mov     rdi, [rsp+108h+var_88]
0x180026f3c  mov     rcx, [rdi]
0x180026f3f  cmp     rbx, rcx
0x180026f42  jz      short loc_180026F5B
0x180026f44  test    rcx, rcx
0x180026f47  jz      short loc_180026F58
0x180026f49  mov     rax, [rcx]
0x180026f4c  mov     rax, [rax+130h]
0x180026f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f58  mov     [rdi], rbx
0x180026f5b  mov     edi, 7
0x180026f60  lea     rbx, [rsi+48h]
0x180026f64  cmp     rbx, r14
0x180026f67  jz      short loc_180026F7A
0x180026f69  mov     r9, r15
0x180026f6c  xor     r8d, r8d
0x180026f6f  mov     rdx, r14
0x180026f72  mov     rcx, rbx; void *
0x180026f75  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180026f7a  mov     [rsi+0ACh], r13d
0x180026f81  mov     rdx, [rsp+108h+Src]; Src
0x180026f86  mov     [rsp+108h+var_70], rdi
0x180026f8e  mov     [rsp+108h+var_78], r13
0x180026f96  mov     word ptr [rsp+108h+var_88], r13w
0x180026f9f  cmp     [rdx], r13w
0x180026fa3  jnz     short loc_180026FAA
0x180026fa5  mov     r8, r13
0x180026fa8  jmp     short loc_180026FB7
0x180026faa  mov     r8, r15
0x180026fad  inc     r8
0x180026fb0  cmp     [rdx+r8*2], r13w
0x180026fb5  jnz     short loc_180026FAD
0x180026fb7  lea     rcx, [rsp+108h+var_88]; void *
0x180026fbf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180026fc4  nop
0x180026fc5  lea     r9, [rsp+108h+var_88]
0x180026fcd  lea     r8, [rsp+108h+var_D0]
0x180026fd2  lea     rdx, [rsp+108h+var_68]
0x180026fda  mov     rcx, rsi
0x180026fdd  call    ?_GetDeploymentPath@AssetElementNode@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@UIWpxSetting@@U?$ProvReleaser@UIWpxSetting@@@@@3@AEBV23@@Z; AssetElementNode::_GetDeploymentPath(std::unique_ptr<IWpxSetting,ProvReleaser<IWpxSetting>> &,std::wstring const &)
0x180026fe2  lea     rcx, [rsi+88h]; void *
0x180026fe9  mov     rdx, rax; Src
0x180026fec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180026ff1  cmp     [rsp+108h+var_50], 8
0x180026ffa  jb      short loc_180027010
0x180026ffc  mov     rcx, [rsp+108h+var_68]
0x180027004  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002700b  nop     dword ptr [rax+rax+00h]
0x180027010  mov     [rsp+108h+var_50], rdi
0x180027018  mov     [rsp+108h+var_58], r13
0x180027020  mov     word ptr [rsp+108h+var_68], r13w
0x180027029  cmp     [rsp+108h+var_70], 8
0x180027032  jb      short loc_180027048
0x180027034  mov     rcx, [rsp+108h+var_88]
0x18002703c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027043  nop     dword ptr [rax+rax+00h]
0x180027048  mov     rcx, [rsp+108h+var_D0]
0x18002704d  mov     rax, [rcx]
0x180027050  mov     rax, [rax+10h]
0x180027054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027059  lea     r9, [rsi+18h]
0x18002705d  mov     r8, r12
0x180027060  mov     rdx, rax
0x180027063  lea     rcx, [rsp+108h+var_C8]
0x180027068  call    ?s_GetNamedElement@AssetElementNode@@CA?AV?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@std@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@3@@Z; AssetElementNode::s_GetNamedElement(ushort const *,std::wstring const &,std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> *)
0x18002706d  lea     rdi, [rsi+20h]
0x180027071  cmp     rdi, rax
0x180027074  jz      short loc_180027098
0x180027076  mov     r14, [rax]
0x180027079  mov     [rax], r13
0x18002707c  mov     rcx, [rdi]
0x18002707f  cmp     r14, rcx
0x180027082  jz      short loc_180027098
0x180027084  test    rcx, rcx
0x180027087  jz      short loc_180027095
0x180027089  mov     rax, [rcx]
0x18002708c  mov     rax, [rax+50h]
0x180027090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027095  mov     [rdi], r14
0x180027098  mov     rcx, [rsp+108h+var_C8]
0x18002709d  test    rcx, rcx
0x1800270a0  jz      short loc_1800270AF
0x1800270a2  mov     rax, [rcx]
0x1800270a5  mov     rax, [rax+50h]
0x1800270a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ae  nop
0x1800270af  cmp     [rdi], r13
0x1800270b2  jnz     loc_18002718D
0x1800270b8  mov     eax, cs:dword_1800495B0
0x1800270be  cmp     eax, 2
0x1800270c1  jbe     short loc_180027130
0x1800270c3  mov     rcx, cs:qword_1800495C8
0x1800270ca  mov     rax, cs:qword_1800495C0
0x1800270d1  mov     rdx, 400000000000h
0x1800270db  test    rdx, rax
0x1800270de  jz      short loc_180027130
0x1800270e0  mov     rax, rcx
0x1800270e3  and     rax, rdx
0x1800270e6  cmp     rax, rcx
0x1800270e9  jnz     short loc_180027130
0x1800270eb  mov     rcx, [rsp+108h+var_D0]
0x1800270f0  mov     rax, [rcx]
0x1800270f3  mov     rax, [rax+10h]
0x1800270f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270fc  mov     [rsp+108h+var_C8], rax
0x180027101  cmp     qword ptr [rbx+18h], 8
0x180027106  jb      short loc_18002710B
0x180027108  mov     rbx, [rbx]
0x18002710b  mov     qword ptr [rsp+108h+var_B0], rbx
0x180027110  lea     rax, [rsp+108h+var_C8]
0x180027115  mov     [rsp+108h+var_E0], rax
0x18002711a  lea     rax, [rsp+108h+var_B0]
0x18002711f  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180027124  lea     rdx, byte_180041723
0x18002712b  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027130  mov     rcx, [rsp+108h]; this
0x180027138  mov     ebx, 86000002h
0x18002713d  mov     r9d, ebx; char *
0x180027140  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180027147  mov     edx, 2Fh ; '/'; void *
0x18002714c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027151  nop
0x180027152  mov     rcx, [rsp+108h+var_D0]
0x180027157  test    rcx, rcx
0x18002715a  jz      short loc_18002716C
0x18002715c  mov     rax, [rcx]
0x18002715f  mov     rax, [rax+2E0h]
0x180027166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002716b  nop
0x18002716c  mov     rcx, [rsp+108h+var_B8]
0x180027171  test    rcx, rcx
0x180027174  jz      short loc_180027186
0x180027176  mov     rdx, [rcx]
0x180027179  mov     rax, [rdx+130h]
0x180027180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027185  nop
0x180027186  mov     eax, ebx
0x180027188  jmp     loc_18002728C
0x18002718d  mov     rcx, [rsp+108h+var_D0]
0x180027192  mov     rax, [rcx]
0x180027195  mov     rax, [rax+10h]
0x180027199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002719e  cmp     [rax], r13w
0x1800271a2  jnz     short loc_1800271A9
0x1800271a4  mov     r8, r13
0x1800271a7  jmp     short loc_1800271B6
0x1800271a9  mov     r8, r15
0x1800271ac  inc     r8
0x1800271af  cmp     [rax+r8*2], r13w
0x1800271b4  jnz     short loc_1800271AC
0x1800271b6  lea     rcx, [rsi+68h]; void *
0x1800271ba  mov     rdx, rax; Src
0x1800271bd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800271c2  lea     rcx, [rsi+28h]; void *
0x1800271c6  cmp     rcx, r12
0x1800271c9  jz      short loc_1800271D9
0x1800271cb  mov     r9, r15
0x1800271ce  xor     r8d, r8d
0x1800271d1  mov     rdx, r12
0x1800271d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800271d9  mov     [rsp+108h+var_C8], r13
0x1800271de  mov     rcx, [rsp+108h+var_D0]
0x1800271e3  mov     rax, [rcx]
0x1800271e6  lea     rdx, [rsp+108h+var_C8]
0x1800271eb  mov     rax, [rax+128h]
0x1800271f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271f7  mov     rcx, [rsp+108h]; this
0x1800271ff  test    eax, eax
0x180027201  js      loc_1800272B0
0x180027207  mov     rcx, [rsp+108h+var_C8]
0x18002720c  mov     rax, [rcx]
0x18002720f  mov     rax, [rax+0B8h]
0x180027216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002721b  mov     rcx, [rsp+108h]; this
0x180027223  test    rax, rax
0x180027226  jz      loc_1800272C4
0x18002722c  lea     rdx, aTemporaryRunti; "Temporary Runtime Package Command Files"
0x180027233  mov     rcx, rax; String1
0x180027236  call    cs:__imp__wcsicmp
0x18002723d  nop     dword ptr [rax+rax+00h]
0x180027242  mov     ecx, r13d
0x180027245  test    eax, eax
0x180027247  setz    cl
0x18002724a  mov     [rsi+0A8h], ecx
0x180027250  mov     rcx, [rsp+108h+var_D0]
0x180027255  test    rcx, rcx
0x180027258  jz      short loc_18002726A
0x18002725a  mov     rax, [rcx]
0x18002725d  mov     rax, [rax+2E0h]
0x180027264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027269  nop
0x18002726a  mov     rcx, [rsp+108h+var_B8]
0x18002726f  test    rcx, rcx
0x180027272  jz      short loc_180027284
0x180027274  mov     rax, [rcx]
0x180027277  mov     rax, [rax+130h]
0x18002727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027283  nop
0x180027284  xor     eax, eax
0x180027286  jmp     short loc_18002728C
0x180027288  mov     eax, [rsp+108h+var_D8]
0x18002728c  mov     rcx, [rsp+108h+var_48]
0x180027294  xor     rcx, rsp; StackCookie
0x180027297  call    __security_check_cookie
0x18002729c  add     rsp, 0D0h
0x1800272a3  pop     r15
0x1800272a5  pop     r14
0x1800272a7  pop     r13
0x1800272a9  pop     r12
0x1800272ab  pop     rdi
0x1800272ac  pop     rsi
0x1800272ad  pop     rbx
0x1800272ae  retn
  ... truncated ...
```

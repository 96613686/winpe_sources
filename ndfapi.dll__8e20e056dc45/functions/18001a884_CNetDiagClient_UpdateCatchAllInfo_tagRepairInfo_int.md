# CNetDiagClient::UpdateCatchAllInfo(tagRepairInfo &,int)

- ea: `0x18001a884`
- end: `0x18001ad19`
- name: `?UpdateCatchAllInfo@CNetDiagClient@@IEAAJAEAUtagRepairInfo@@H@Z`
- size: `1173`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, struct tagRepairInfo *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180019af8`

## callees

- `0x1800171e4`
- `0x1800183e4`
- `0x180018a9c`
- `0x180018c5c`
- `0x18001a104`
- `0x18001a884`
- `0x18001afe8`
- `0x18001b0f8`
- `0x18001b2b4`
- `0x18001d5d0`
- `0x18001d688`
- `0x18001d808`
- `0x18001dbb4`
- `0x18001e244`
- `0x18001f646`
- `0x18001f66a`
- `0x18001f690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aca8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001acdd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aca8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001acdd`
- `ole32!IIDFromString` at `0x18001a993`
- `ole32!IIDFromString` at `0x18001a993`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CNetDiagClient::UpdateCatchAllInfo(CNetDiagClient *this, struct tagRepairInfo *a2)
{
  DiagnosisTextParserImpl *v4; // rbx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rdx
  char v8; // r14
  char v9; // bl
  unsigned int i; // esi
  struct DiagnosisTextParser::DiagnosisParameter *v11; // r12
  __int64 v12; // rax
  __int64 v13; // rsi
  IID v14; // xmm6
  __int64 v15; // rdx
  __int64 v16; // rax
  IID v17; // xmm6
  unsigned int v18; // ecx
  unsigned int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 *v23; // rsi
  __int64 *v24; // rbx
  __int64 *v25; // r14
  int Parameters; // [rsp+30h] [rbp-F8h]
  unsigned int v28; // [rsp+34h] [rbp-F4h] BYREF
  struct DiagnosisTextParser::DiagnosisParameter *v29; // [rsp+38h] [rbp-F0h] BYREF
  DiagnosisTextParserImpl *v30[2]; // [rsp+40h] [rbp-E8h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-D8h] BYREF
  unsigned int v32; // [rsp+60h] [rbp-C8h]
  IID iid; // [rsp+70h] [rbp-B8h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+90h] [rbp-98h]
  unsigned __int64 v36; // [rsp+98h] [rbp-90h]
  void *v37[2]; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-78h]
  unsigned __int64 v39; // [rsp+B8h] [rbp-70h]
  void *v40[3]; // [rsp+C0h] [rbp-68h] BYREF
  unsigned __int64 v41; // [rsp+D8h] [rbp-50h]

  *(_QWORD *)&v31.Data1 = a2;
  iid = 0;
  v41 = 7;
  v40[2] = 0;
  LOWORD(v40[0]) = 0;
  v39 = 7;
  v38 = 0;
  LOWORD(v37[0]) = 0;
  v29 = 0;
  v28 = 0;
  DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)v30);
  v4 = v30[0];
  if ( !v30[0] )
  {
    v5 = -2147024882;
    goto LABEL_42;
  }
  v5 = DiagnosisTextParserImpl::SetXML((void **)v30[0], a2->pwszDescription);
  if ( v5 < 0 )
  {
LABEL_42:
    Parameters = v5;
    goto LABEL_43;
  }
  if ( !v4 )
  {
    Parameters = -2147024882;
    goto LABEL_43;
  }
  Parameters = DiagnosisTextParserImpl::GetParameters(v6, (__int64 **)v4 + 4, (LPVOID **)&v29, &v28);
  if ( Parameters < 0 )
    goto LABEL_43;
  v8 = 0;
  v9 = 0;
  for ( i = 0; i < v28; ++i )
  {
    v11 = v29;
    if ( !wcsncmp_0(*((const wchar_t **)v29 + 2 * i), L"CatchAllRC", 0xBu) )
    {
      Parameters = IIDFromString(*((LPCOLESTR *)v11 + 2 * i + 1), &iid);
      if ( Parameters < 0 )
        goto LABEL_43;
      v8 = 1;
    }
    else
    {
      if ( !wcsncmp_0(*((const wchar_t **)v11 + 2 * i), L"CatchAllHCs", 0xCu) )
      {
        v9 = 1;
        try
        {
          std::wstring::assign(v40, *((void **)v11 + 2 * i + 1));
        }
        catch ( std::bad_alloc )
        {
          Parameters = -2147024882;
          goto LABEL_43;
        }
        catch ( exception )
        {
          Parameters = -2147467259;
          goto LABEL_43;
        }
      }
      if ( !v8 )
        continue;
    }
    if ( v9 )
      goto LABEL_17;
  }
  if ( !v8 || !v9 )
  {
    Parameters = 1;
    goto LABEL_43;
  }
LABEL_17:
  v12 = std::wstring::find(v40, v7, 0);
  try
  {
    v13 = v12;
    v36 = 7;
    v35 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src);
    std::wstring::operator=(v37, Src);
    if ( v36 >= 8 )
      operator delete(Src[0]);
  }
  catch ( std::bad_alloc )
  {
    Parameters = -2147024882;
    goto LABEL_43;
  }
  catch ( exception )
  {
    Parameters = -2147467259;
    goto LABEL_43;
  }
  try
  {
    v14 = iid;
    *(IID *)std::map<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>>::operator[](
              (char *)this + 64,
              v37) = v14;
  }
  catch ( std::bad_alloc )
  {
    Parameters = -2147024882;
    goto LABEL_43;
  }
  catch ( exception )
  {
    Parameters = -2147467259;
    goto LABEL_43;
  }
  while ( v13 != -1 )
  {
    v16 = std::wstring::find(v40, v15, v13 + 1);
    try
    {
      v13 = v16;
      v36 = 7;
      v35 = 0;
      LOWORD(Src[0]) = 0;
      std::wstring::assign(Src);
      std::wstring::operator=(v37, Src);
      if ( v36 >= 8 )
        operator delete(Src[0]);
    }
    catch ( std::bad_alloc )
    {
      Parameters = -2147024882;
      goto LABEL_43;
    }
    catch ( exception )
    {
      Parameters = -2147467259;
      goto LABEL_43;
    }
    try
    {
      v17 = iid;
      *(IID *)std::map<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>>::operator[](
                (char *)this + 64,
                v37) = v17;
    }
    catch ( std::bad_alloc )
    {
      Parameters = -2147024882;
      goto LABEL_43;
    }
    catch ( exception )
    {
      Parameters = -2147467259;
      goto LABEL_43;
    }
  }
  v31 = *(struct _GUID *)*(_QWORD *)&v31.Data1;
  v18 = 0;
  v19 = *((_DWORD *)this + 492);
  if ( v19 )
  {
    while ( 1 )
    {
      v20 = 152LL * v18;
      if ( *(_QWORD *)&v31.Data1 == *(_QWORD *)((char *)this + v20 + 168)
        && *(_QWORD *)v31.Data4 == *(_QWORD *)((char *)this + v20 + 176) )
      {
        break;
      }
      if ( ++v18 >= v19 )
        goto LABEL_43;
    }
    if ( v18 != -1 )
    {
      try
      {
        v31 = iid;
        v32 = v18;
        v21 = std::_Tree_buy<std::pair<_GUID const,int>>::_Buynode<std::pair<_GUID,int>>((char *)this + 96, &v31);
        std::_Tree<std::_Tmap_traits<_GUID,int,GuidLessThan,std::allocator<std::pair<_GUID const,int>>,1>>::_Insert_nohint<std::pair<_GUID const,int> &,std::_Tree_node<std::pair<_GUID const,int>,void *> *>(
          (char *)this + 96,
          &v31,
          v22,
          v21 + 28,
          v21);
      }
      catch ( std::bad_alloc )
      {
        Parameters = -2147024882;
        goto LABEL_43;
      }
      catch ( exception )
      {
        Parameters = -2147467259;
        goto LABEL_43;
      }
      v23 = (__int64 *)*((_QWORD *)this + 10);
      v24 = (__int64 *)v23[1];
      v25 = v23;
      if ( *((_BYTE *)v24 + 25) )
        goto LABEL_36;
      do
      {
        if ( memcmp_0(v24 + 4, &iid, 0x10u) >= 0 )
        {
          v25 = v24;
          v24 = (__int64 *)*v24;
        }
        else
        {
          v24 = (__int64 *)v24[2];
        }
      }
      while ( !*((_BYTE *)v24 + 25) );
      if ( v25 == v23 || memcmp_0(&iid, v25 + 4, 0x10u) < 0 )
      {
LABEL_36:
        v31 = iid;
        CNetDiagClient::LookUpCatchAllDescription(this, &v31);
      }
    }
  }
LABEL_43:
  if ( v29 )
    FreeDiagnosisParameters((LPVOID *)v29, v28);
  DiagnosisTextParser::~DiagnosisTextParser(v30);
  if ( v39 >= 8 )
    operator delete(v37[0]);
  v39 = 7;
  v38 = 0;
  LOWORD(v37[0]) = 0;
  if ( v41 >= 8 )
    operator delete(v40[0]);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x18001a884  mov     r11, rsp
0x18001a887  mov     [r11+18h], rbx
0x18001a88b  mov     [r11+20h], rsi
0x18001a88f  push    rdi
0x18001a890  push    r12
0x18001a892  push    r13
0x18001a894  push    r14
0x18001a896  push    r15
0x18001a898  sub     rsp, 100h
0x18001a89f  movaps  xmmword ptr [r11-38h], xmm6
0x18001a8a4  mov     rax, cs:__security_cookie
0x18001a8ab  xor     rax, rsp
0x18001a8ae  mov     [rsp+128h+var_48], rax
0x18001a8b6  mov     r15, rdx
0x18001a8b9  mov     qword ptr [rsp+128h+var_D8.Data1], rdx
0x18001a8be  mov     r13, rcx
0x18001a8c1  xor     edi, edi
0x18001a8c3  xorps   xmm0, xmm0
0x18001a8c6  movups  xmmword ptr [rsp+128h+iid.Data1], xmm0
0x18001a8cb  mov     qword ptr [r11-50h], 7
0x18001a8d3  mov     [r11-58h], rdi
0x18001a8d7  mov     [r11-68h], di
0x18001a8dc  mov     qword ptr [r11-70h], 7
0x18001a8e4  mov     [r11-78h], rdi
0x18001a8e8  mov     word ptr [rsp+128h+var_88], di
0x18001a8f0  mov     [rsp+128h+var_F0], rdi
0x18001a8f5  mov     [rsp+128h+var_F4], edi
0x18001a8f9  lea     rcx, [rsp+128h+var_E8]; this
0x18001a8fe  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x18001a903  nop
0x18001a904  mov     rbx, [rsp+128h+var_E8]
0x18001a909  test    rbx, rbx
0x18001a90c  jz      loc_18001AC6D
0x18001a912  mov     rdx, [r15+18h]; unsigned __int16 *
0x18001a916  mov     rcx, rbx; this
0x18001a919  call    ?SetXML@DiagnosisTextParserImpl@@QEAAJPEBG@Z; DiagnosisTextParserImpl::SetXML(ushort const *)
0x18001a91e  test    eax, eax
0x18001a920  js      loc_18001AC72
0x18001a926  test    rbx, rbx
0x18001a929  jz      loc_18001AC63
0x18001a92f  lea     rdx, [rbx+20h]
0x18001a933  lea     r9, [rsp+128h+var_F4]
0x18001a938  lea     r8, [rsp+128h+var_F0]
0x18001a93d  call    ?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z; DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)
0x18001a942  mov     [rsp+128h+var_F8], eax
0x18001a946  test    eax, eax
0x18001a948  js      loc_18001AC76
0x18001a94e  mov     r14b, dil
0x18001a951  mov     bl, dil
0x18001a954  mov     esi, edi
0x18001a956  mov     eax, [rsp+128h+var_F8]
0x18001a95a  cmp     esi, [rsp+128h+var_F4]
0x18001a95e  jnb     loc_18001A9F0
0x18001a964  mov     r15d, esi
0x18001a967  add     r15, r15
0x18001a96a  mov     r12, [rsp+128h+var_F0]
0x18001a96f  mov     r8d, 0Bh; MaxCount
0x18001a975  lea     rdx, aCatchallrc; "CatchAllRC"
0x18001a97c  mov     rcx, [r12+r15*8]; String1
0x18001a980  call    wcsncmp_0
0x18001a985  test    eax, eax
0x18001a987  jnz     short loc_18001A9AA
0x18001a989  lea     rdx, [rsp+128h+iid]; lpiid
0x18001a98e  mov     rcx, [r12+r15*8+8]; lpsz
0x18001a993  call    cs:__imp_IIDFromString
0x18001a999  mov     [rsp+128h+var_F8], eax
0x18001a99d  test    eax, eax
0x18001a99f  js      loc_18001AC76
0x18001a9a5  mov     r14b, 1
0x18001a9a8  jmp     short loc_18001A9DE
0x18001a9aa  mov     r8d, 0Ch; MaxCount
0x18001a9b0  lea     rdx, aCatchallhcs; "CatchAllHCs"
0x18001a9b7  mov     rcx, [r12+r15*8]; String1
0x18001a9bb  call    wcsncmp_0
0x18001a9c0  test    eax, eax
0x18001a9c2  jnz     short loc_18001A9D9
0x18001a9c4  mov     bl, 1
0x18001a9c6  mov     rdx, [r12+r15*8+8]; Src
0x18001a9cb  lea     rcx, [rsp+128h+var_68]; void *
0x18001a9d3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001a9d8  nop
0x18001a9d9  test    r14b, r14b
0x18001a9dc  jz      short loc_18001A9E2
0x18001a9de  test    bl, bl
0x18001a9e0  jnz     short loc_18001AA05
0x18001a9e2  inc     esi
0x18001a9e4  jmp     loc_18001A956
0x18001a9e9  xor     edi, edi
0x18001a9eb  jmp     loc_18001AC76
0x18001a9f0  test    r14b, r14b
0x18001a9f3  jz      loc_18001AC59
0x18001a9f9  mov     [rsp+128h+var_F8], eax
0x18001a9fd  test    bl, bl
0x18001a9ff  jz      loc_18001AC59
0x18001aa05  xor     r8d, r8d
0x18001aa08  lea     rcx, [rsp+128h+var_68]
0x18001aa10  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18001aa15  mov     rsi, rax
0x18001aa18  mov     [rsp+128h+var_90], 7
0x18001aa24  mov     [rsp+128h+var_98], rdi
0x18001aa2c  mov     word ptr [rsp+128h+Src], di
0x18001aa34  mov     r9, rax
0x18001aa37  xor     r8d, r8d
0x18001aa3a  lea     rdx, [rsp+128h+var_68]
0x18001aa42  lea     rcx, [rsp+128h+Src]; void *
0x18001aa4a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001aa4f  lea     rdx, [rsp+128h+Src]; Src
0x18001aa57  lea     rcx, [rsp+128h+var_88]; void *
0x18001aa5f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001aa64  cmp     [rsp+128h+var_90], 8
0x18001aa6d  jb      short loc_18001AA7E
0x18001aa6f  mov     rcx, [rsp+128h+Src]
0x18001aa77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aa7d  nop
0x18001aa7e  movaps  xmm6, xmmword ptr [rsp+128h+iid.Data1]
0x18001aa83  lea     rcx, [r13+40h]
0x18001aa87  lea     rdx, [rsp+128h+var_88]
0x18001aa8f  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@QEAAAEAU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>>::operator[](std::wstring const &)
0x18001aa94  movdqu  xmmword ptr [rax], xmm6
0x18001aa98  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001aa9c  jz      loc_18001AB41
0x18001aaa2  lea     rbx, [rsi+1]
0x18001aaa6  mov     r8, rbx
0x18001aaa9  lea     rcx, [rsp+128h+var_68]
0x18001aab1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18001aab6  mov     rsi, rax
0x18001aab9  mov     [rsp+128h+var_90], 7
0x18001aac5  mov     [rsp+128h+var_98], rdi
0x18001aacd  mov     word ptr [rsp+128h+Src], di
0x18001aad5  mov     r9, rax
0x18001aad8  sub     r9, rbx
0x18001aadb  mov     r8, rbx
0x18001aade  lea     rdx, [rsp+128h+var_68]
0x18001aae6  lea     rcx, [rsp+128h+Src]; void *
0x18001aaee  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001aaf3  lea     rdx, [rsp+128h+Src]; Src
0x18001aafb  lea     rcx, [rsp+128h+var_88]; void *
0x18001ab03  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ab08  cmp     [rsp+128h+var_90], 8
0x18001ab11  jb      short loc_18001AB22
0x18001ab13  mov     rcx, [rsp+128h+Src]
0x18001ab1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ab21  nop
0x18001ab22  movaps  xmm6, xmmword ptr [rsp+128h+iid.Data1]
0x18001ab27  lea     rcx, [r13+40h]
0x18001ab2b  lea     rdx, [rsp+128h+var_88]
0x18001ab33  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@QEAAAEAU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>>::operator[](std::wstring const &)
0x18001ab38  movdqu  xmmword ptr [rax], xmm6
0x18001ab3c  jmp     loc_18001AA98
0x18001ab41  mov     rax, qword ptr [rsp+128h+var_D8.Data1]
0x18001ab46  movups  xmm0, xmmword ptr [rax]
0x18001ab49  movdqu  xmmword ptr [rsp+128h+var_D8.Data1], xmm0
0x18001ab4f  mov     ecx, edi
0x18001ab51  mov     r8d, [r13+7B0h]
0x18001ab58  test    r8d, r8d
0x18001ab5b  jz      loc_18001AC76
0x18001ab61  mov     r9, qword ptr [rsp+128h+var_D8.Data4]
0x18001ab66  mov     r11, qword ptr [rsp+128h+var_D8.Data1]
0x18001ab6b  mov     eax, ecx
0x18001ab6d  imul    rdx, rax, 98h
0x18001ab74  cmp     r11, [rdx+r13+0A8h]
0x18001ab7c  jnz     loc_18001AC4C
0x18001ab82  cmp     r9, [rdx+r13+0B0h]
0x18001ab8a  jnz     loc_18001AC4C
0x18001ab90  cmp     ecx, 0FFFFFFFFh
0x18001ab93  jz      loc_18001AC76
0x18001ab99  movaps  xmm0, xmmword ptr [rsp+128h+iid.Data1]
0x18001ab9e  movdqu  xmmword ptr [rsp+128h+var_D8.Data1], xmm0
0x18001aba4  mov     [rsp+128h+var_C8], ecx
0x18001aba8  lea     rdx, [rsp+128h+var_D8]
0x18001abad  lea     rcx, [r13+60h]
0x18001abb1  call    ??$_Buynode@U?$pair@U_GUID@@H@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@H@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@H@std@@PEAX@1@$$QEAU?$pair@U_GUID@@H@1@@Z; std::_Tree_buy<std::pair<_GUID const,int>>::_Buynode<std::pair<_GUID,int>>(std::pair<_GUID,int> &&)
0x18001abb6  lea     r9, [rax+1Ch]
0x18001abba  mov     [rsp+128h+var_108], rax
0x18001abbf  lea     rdx, [rsp+128h+var_D8]
0x18001abc4  lea     rcx, [r13+60h]
0x18001abc8  call    ??$_Insert_nohint@AEAU?$pair@$$CBU_GUID@@H@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@H@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@HUGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@std@@$00@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBU_GUID@@H@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@H@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,int,GuidLessThan,std::allocator<std::pair<_GUID const,int>>,1>>::_Insert_nohint<std::pair<_GUID const,int> &,std::_Tree_node<std::pair<_GUID const,int>,void *> *>(bool,std::pair<_GUID const,int> &,std::_Tree_node<std::pair<_GUID const,int>,void *> *)
0x18001abcd  nop
0x18001abce  mov     rsi, [r13+50h]
0x18001abd2  mov     rbx, [rsi+8]
0x18001abd6  mov     r14, rsi
0x18001abd9  cmp     [rbx+19h], dil
0x18001abdd  jnz     short loc_18001AC32
0x18001abdf  mov     r12d, 10h
0x18001abe5  lea     rcx, [rbx+20h]; Buf1
0x18001abe9  mov     r8, r12; Size
0x18001abec  lea     rdx, [rsp+128h+iid]; Buf2
0x18001abf1  call    memcmp_0
0x18001abf6  test    eax, eax
0x18001abf8  jns     short loc_18001AC00
0x18001abfa  mov     rbx, [rbx+10h]
0x18001abfe  jmp     short loc_18001AC06
0x18001ac00  mov     r14, rbx
0x18001ac03  mov     rbx, [rbx]
0x18001ac06  mov     r15d, [rsp+128h+var_F8]
0x18001ac0b  cmp     [rbx+19h], dil
0x18001ac0f  jz      short loc_18001ABE5
0x18001ac11  cmp     r14, rsi
0x18001ac14  jz      short loc_18001AC32
0x18001ac16  lea     rdx, [r14+20h]; Buf2
0x18001ac1a  mov     r8, r12; Size
0x18001ac1d  lea     rcx, [rsp+128h+iid]; Buf1
0x18001ac22  call    memcmp_0
0x18001ac27  test    eax, eax
0x18001ac29  js      short loc_18001AC32
0x18001ac2b  mov     [rsp+128h+var_F8], r15d
0x18001ac30  jmp     short loc_18001AC76
0x18001ac32  movaps  xmm0, xmmword ptr [rsp+128h+iid.Data1]
0x18001ac37  movdqa  xmmword ptr [rsp+128h+var_D8.Data1], xmm0
0x18001ac3d  lea     rdx, [rsp+128h+var_D8]; struct _GUID
0x18001ac42  mov     rcx, r13; this
0x18001ac45  call    ?LookUpCatchAllDescription@CNetDiagClient@@IEAAJU_GUID@@@Z; CNetDiagClient::LookUpCatchAllDescription(_GUID)
0x18001ac4a  jmp     short loc_18001AC76
0x18001ac4c  inc     ecx
0x18001ac4e  cmp     ecx, r8d
0x18001ac51  jb      loc_18001AB6B
0x18001ac57  jmp     short loc_18001AC76
0x18001ac59  mov     [rsp+128h+var_F8], 1
0x18001ac61  jmp     short loc_18001AC76
0x18001ac63  mov     [rsp+128h+var_F8], 8007000Eh
0x18001ac6b  jmp     short loc_18001AC76
0x18001ac6d  mov     eax, 8007000Eh
0x18001ac72  mov     [rsp+128h+var_F8], eax
0x18001ac76  mov     rcx, [rsp+128h+var_F0]; struct DiagnosisTextParser::DiagnosisParameter *
0x18001ac7b  test    rcx, rcx
0x18001ac7e  jz      short loc_18001AC8A
0x18001ac80  mov     edx, [rsp+128h+var_F4]; unsigned int
0x18001ac84  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x18001ac89  nop
0x18001ac8a  lea     rcx, [rsp+128h+var_E8]; this
0x18001ac8f  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x18001ac94  nop
0x18001ac95  cmp     [rsp+128h+var_70], 8
0x18001ac9e  jb      short loc_18001ACAE
0x18001aca0  mov     rcx, [rsp+128h+var_88]
0x18001aca8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001acae  mov     [rsp+128h+var_70], 7
0x18001acba  mov     [rsp+128h+var_78], rdi
0x18001acc2  mov     word ptr [rsp+128h+var_88], di
0x18001acca  cmp     [rsp+128h+var_50], 8
0x18001acd3  jb      short loc_18001ACE3
0x18001acd5  mov     rcx, [rsp+128h+var_68]
0x18001acdd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ace3  mov     eax, [rsp+128h+var_F8]
0x18001ace7  mov     rcx, [rsp+128h+var_48]
0x18001acef  xor     rcx, rsp; StackCookie
0x18001acf2  call    __security_check_cookie
0x18001acf7  lea     r11, [rsp+128h+var_28]
0x18001acff  mov     rbx, [r11+40h]
0x18001ad03  mov     rsi, [r11+48h]
0x18001ad07  movaps  xmm6, xmmword ptr [r11-10h]
0x18001ad0c  mov     rsp, r11
0x18001ad0f  pop     r15
0x18001ad11  pop     r14
0x18001ad13  pop     r13
0x18001ad15  pop     r12
0x18001ad17  pop     rdi
0x18001ad18  retn
```

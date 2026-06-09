# CMVEngine::HandleStates(__MIDL___MIDL_itf_mvengine_0000_0000_0001 *,long,ulong)

- ea: `0x1800141f0`
- end: `0x180014806`
- name: `?HandleStates@CMVEngine@@UEAAJPEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@JK@Z`
- size: `1558`
- prototype: `__int64 __fastcall(CMVEngine *this, enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *, int, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800010c8`
- `0x18000b030`
- `0x18000f288`
- `0x18000f5f4`
- `0x180010ad8`
- `0x180010b5c`
- `0x180011bb0`
- `0x1800141f0`
- `0x180014cf8`
- `0x180018438`
- `0x18001c9e0`
- `0x18001d25c`
- `0x180020cb4`
- `0x1800214bc`
- `0x180021c5c`
- `0x180021cf4`
- `0x1800221dc`
- `0x1800396f0`
- `0x180039774`
- `0x180039828`
- `0x180039f98`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800146cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800146fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800146cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800146fb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014251`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014251`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014510`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014510`

## string_xrefs

- `0x1800144fb`: `InstallType`
- `0x18001459c`: `%PROGRAMDATA%\Microsoft\Provisioning`

## pseudocode

```c
__int64 __fastcall CMVEngine::HandleStates(
        CMVEngine *this,
        enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *a2,
        int a3,
        int a4)
{
  __int64 v6; // rdx
  int v7; // ecx
  unsigned int v8; // r15d
  _QWORD *v10; // r14
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  wil *v16; // rcx
  unsigned int v17; // r14d
  int pdwType; // [rsp+20h] [rbp-178h]
  int v19; // [rsp+40h] [rbp-158h] BYREF
  int pvData; // [rsp+44h] [rbp-154h] BYREF
  int v21; // [rsp+48h] [rbp-150h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-148h] BYREF
  void *v23[2]; // [rsp+58h] [rbp-140h] BYREF
  __int64 v24; // [rsp+68h] [rbp-130h]
  _QWORD v25[5]; // [rsp+70h] [rbp-128h] BYREF
  char v26; // [rsp+98h] [rbp-100h]
  __int128 v27; // [rsp+A0h] [rbp-F8h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-E8h]
  __int64 v29; // [rsp+C0h] [rbp-D8h]
  int v30; // [rsp+D8h] [rbp-C0h]
  _BYTE v31[24]; // [rsp+E0h] [rbp-B8h] BYREF
  int v32; // [rsp+F8h] [rbp-A0h] BYREF
  char v33; // [rsp+FCh] [rbp-9Ch]
  GUID v34; // [rsp+100h] [rbp-98h] BYREF
  _BYTE v35[32]; // [rsp+120h] [rbp-78h] BYREF
  int *p_pvData; // [rsp+140h] [rbp-58h]
  __int64 v37; // [rsp+148h] [rbp-50h]
  _BYTE v38[32]; // [rsp+150h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]
  enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *v40; // [rsp+1A8h] [rbp+10h] BYREF
  int v41; // [rsp+1B0h] [rbp+18h] BYREF

  v41 = a3;
  v40 = a2;
  v19 = 0;
  v32 = 0;
  v33 = 0;
  if ( (unsigned int)dword_18005A000 <= 5 )
    v34 = 0;
  else
    EventActivityIdControl(3u, &v34);
  v32 = 1;
  if ( (unsigned int)dword_18005A000 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &word_18004F64E, &v34, 0, 2, v35);
  v25[0] = this;
  v25[1] = &v40;
  v25[2] = &v41;
  v25[3] = &v32;
  v25[4] = &v19;
  v26 = 1;
  v6 = *((_QWORD *)this + 26);
  v7 = v41;
  *(_QWORD *)(v6 + 16) = v40;
  *(_DWORD *)(v6 + 28) = v7;
  CMVEngine::PreHandleStates(this);
  v21 = 0;
  v19 = CMVEngine::RetrieveHandlers((LPCWSTR *)this, &v21);
  if ( v19 < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      pvData = v19;
      p_pvData = &pvData;
      v37 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F2F1, &v34, 0, 3, v35);
    }
    v8 = v19;
    if ( v26 )
    {
      v26 = 0;
      lambda_d195deafaa0b3d3fcf6dcc6e77906008_::operator()(v25);
    }
    if ( v32 == 1 )
    {
      v32 = 2;
      _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &v34);
    }
    v32 = 3;
    return v8;
  }
  if ( v21 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F39D, &v34, 0, 2, v35);
    v19 = 0;
    if ( v26 )
    {
      v26 = 0;
      lambda_d195deafaa0b3d3fcf6dcc6e77906008_::operator()(v25);
    }
    if ( v32 == 1 )
    {
      v32 = 2;
      _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &v34);
    }
    v32 = 3;
    return 0;
  }
  PackageCollector::PackageCollector((PackageCollector *)v35);
  pvData = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
    L"InstallType",
    0x20000010u,
    0,
    &pvData,
    &pcbData);
  try
  {
    if ( pvData == 17 && a4 == 1 )
    {
      if ( (unsigned int)dword_18005A000 > 4 )
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004F69A, &v34, 0, 2, v38);
      *(_OWORD *)v23 = 0;
      v24 = 0;
      std::vector<std::wstring>::_Reserve(v23);
      v10 = v23[1];
      *((_QWORD *)v23[1] + 3) = 7;
      v10[2] = 0;
      *(_WORD *)v10 = 0;
      std::wstring::assign(v10, L"%PROGRAMDATA%\\Microsoft\\Provisioning");
      v23[1] = v10 + 4;
      v11 = (wchar_t *)std::vector<std::wstring>::vector<std::wstring>(v38, v23);
      PackageCollector::AddDefaultSearchPathsWithExclusions((__int64)v35, v11);
    }
    else
    {
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v12 = (wchar_t *)std::vector<std::wstring>::vector<std::wstring>(v38, v23);
      PackageCollector::AddDefaultSearchPathsWithExclusions((__int64)v35, v12);
    }
    std::vector<std::wstring>::_Tidy(v23);
    PackageCollector::Search(v35, v31);
    v27 = 0;
    *(_QWORD *)&v27 = std::_List_alloc<0,std::_List_base_types<std::pair<std::wstring const,std::wstring>>>::_Buynode0(
                        v13,
                        0,
                        0);
    v28 = 0;
    v29 = 0;
    v30 = 1065353216;
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Init(
      &v27,
      8);
    v14 = CMVEngine::HandleStatesForPackagesInternal(this, v31, &v27);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7F0,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)(unsigned int)v14,
        pdwType);
    v15 = CMVEngine::ResolveDeletedPackages(retaddr, &v27);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7F1,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)(unsigned int)v15,
        pdwType);
    if ( (_QWORD)v28 )
    {
      operator delete((void *)v28);
      v28 = 0;
      v29 = 0;
    }
    std::list<std::pair<std::wstring const,std::wstring>>::clear(&v27);
    operator delete((void *)v27);
    std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(v31);
    PackageCollector::~PackageCollector((PackageCollector *)v35);
  }
  catch ( ... )
  {
    pcbData = wil::ResultFromCaughtException(v16);
    if ( v26 )
    {
      v26 = 0;
      lambda_d195deafaa0b3d3fcf6dcc6e77906008_::operator()(v25);
    }
    if ( v32 == 1 )
    {
      v32 = 2;
      _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &v34);
    }
    return pcbData;
  }
  v17 = v19;
  if ( v26 )
  {
    v26 = 0;
    lambda_d195deafaa0b3d3fcf6dcc6e77906008_::operator()(v25);
  }
  if ( v32 == 1 )
  {
    v32 = 2;
    _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &v34);
  }
  return v17;
}

```

## disassembly

```asm
0x1800141f0  mov     r11, rsp
0x1800141f3  mov     [r11+20h], rbx
0x1800141f7  mov     [r11+18h], r8d
0x1800141fb  mov     [r11+10h], rdx
0x1800141ff  push    r12
0x180014201  push    r14
0x180014203  push    r15
0x180014205  sub     rsp, 180h
0x18001420c  mov     rax, cs:__security_cookie
0x180014213  xor     rax, rsp
0x180014216  mov     [rsp+198h+var_28], rax
0x18001421e  mov     r12d, r9d
0x180014221  mov     r15, rcx
0x180014224  xor     ebx, ebx
0x180014226  mov     [rsp+198h+var_158], ebx
0x18001422a  mov     [rsp+198h+var_A0], ebx
0x180014231  mov     [rsp+198h+var_9C], bl
0x180014238  mov     eax, cs:dword_18005A000
0x18001423e  lea     r14d, [rbx+3]
0x180014242  cmp     eax, 5
0x180014245  jbe     short loc_180014259
0x180014247  lea     rdx, [r11-98h]; ActivityId
0x18001424e  mov     ecx, r14d; ControlCode
0x180014251  call    cs:__imp_EventActivityIdControl
0x180014257  jmp     short loc_180014264
0x180014259  xorps   xmm0, xmm0
0x18001425c  movups  [rsp+198h+var_98], xmm0
0x180014264  mov     [rsp+198h+var_A0], 1
0x18001426f  mov     eax, cs:dword_18005A000
0x180014275  cmp     eax, 5
0x180014278  jbe     short loc_1800142E4
0x18001427a  cmp     [rsp+198h+var_9C], bl
0x180014281  jz      short loc_1800142B1
0x180014283  cmp     [rsp+198h+var_88], ebx
0x18001428a  jnz     short loc_1800142A7
0x18001428c  cmp     [rsp+198h+var_84], ebx
0x180014293  jnz     short loc_1800142A7
0x180014295  cmp     [rsp+198h+var_80], ebx
0x18001429c  jnz     short loc_1800142A7
0x18001429e  cmp     [rsp+198h+var_7C], ebx
0x1800142a5  jz      short loc_1800142B1
0x1800142a7  lea     r9, [rsp+198h+var_88]
0x1800142af  jmp     short loc_1800142B4
0x1800142b1  mov     r9, rbx
0x1800142b4  lea     rax, [rsp+198h+var_78]
0x1800142bc  mov     [rsp+198h+pvData], rax
0x1800142c1  mov     dword ptr [rsp+198h+pdwType], 2
0x1800142c9  lea     r8, [rsp+198h+var_98]
0x1800142d1  lea     rdx, word_18004F64E
0x1800142d8  lea     rcx, dword_18005A000
0x1800142df  call    _tlgWriteTransfer_EventWriteTransfer
0x1800142e4  mov     [rsp+198h+var_128], r15
0x1800142e9  lea     rax, [rsp+198h+arg_8]
0x1800142f1  mov     [rsp+198h+var_120], rax
0x1800142f6  lea     rax, [rsp+198h+arg_10]
0x1800142fe  mov     [rsp+198h+var_118], rax
0x180014306  lea     rax, [rsp+198h+var_A0]
0x18001430e  mov     [rsp+198h+var_110], rax
0x180014316  lea     rax, [rsp+198h+var_158]
0x18001431b  mov     [rsp+198h+var_108], rax
0x180014323  mov     [rsp+198h+var_100], 1
0x18001432b  mov     rdx, [r15+0D0h]
0x180014332  mov     ecx, [rsp+198h+arg_10]
0x180014339  mov     rax, [rsp+198h+arg_8]
0x180014341  mov     [rdx+10h], rax
0x180014345  mov     [rdx+1Ch], ecx
0x180014348  mov     rcx, r15; this
0x18001434b  call    ?PreHandleStates@CMVEngine@@AEAAXXZ; CMVEngine::PreHandleStates(void)
0x180014350  nop
0x180014351  mov     [rsp+198h+var_150], ebx
0x180014355  lea     rdx, [rsp+198h+var_150]; int *
0x18001435a  mov     rcx, r15; this
0x18001435d  call    ?RetrieveHandlers@CMVEngine@@AEAAJPEAH@Z; CMVEngine::RetrieveHandlers(int *)
0x180014362  mov     [rsp+198h+var_158], eax
0x180014366  test    eax, eax
0x180014368  jns     loc_180014423
0x18001436e  mov     eax, cs:dword_18005A000
0x180014374  cmp     eax, 2
0x180014377  jbe     short loc_1800143CA
0x180014379  mov     eax, [rsp+198h+var_158]
0x18001437d  mov     [rsp+198h+var_154], eax
0x180014381  lea     rax, [rsp+198h+var_154]
0x180014386  mov     [rsp+198h+var_58], rax
0x18001438e  mov     [rsp+198h+var_50], 4
0x18001439a  lea     rax, [rsp+198h+var_78]
0x1800143a2  mov     [rsp+198h+pvData], rax
0x1800143a7  mov     dword ptr [rsp+198h+pdwType], r14d
0x1800143ac  xor     r9d, r9d
0x1800143af  lea     r8, [rsp+198h+var_98]
0x1800143b7  lea     rdx, byte_18004F2F1
0x1800143be  lea     rcx, dword_18005A000
0x1800143c5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800143ca  mov     r15d, [rsp+198h+var_158]
0x1800143cf  cmp     [rsp+198h+var_100], bl
0x1800143d6  jz      short loc_1800143EA
0x1800143d8  mov     [rsp+198h+var_100], bl
0x1800143df  lea     rcx, [rsp+198h+var_128]
0x1800143e4  call    _lambda_d195deafaa0b3d3fcf6dcc6e77906008___operator__
0x1800143e9  nop
0x1800143ea  cmp     [rsp+198h+var_A0], 1
0x1800143f2  jnz     short loc_180014413
0x1800143f4  mov     [rsp+198h+var_A0], 2
0x1800143ff  lea     rdx, [rsp+198h+var_98]
0x180014407  lea     rcx, dword_18005A000
0x18001440e  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x180014413  mov     [rsp+198h+var_A0], r14d
0x18001441b  mov     eax, r15d
0x18001441e  jmp     loc_1800147B6
0x180014423  cmp     [rsp+198h+var_150], ebx
0x180014427  jz      loc_1800144C2
0x18001442d  mov     eax, cs:dword_18005A000
0x180014433  cmp     eax, r14d
0x180014436  jbe     short loc_18001446B
0x180014438  lea     rax, [rsp+198h+var_78]
0x180014440  mov     [rsp+198h+pvData], rax
0x180014445  mov     dword ptr [rsp+198h+pdwType], 2
0x18001444d  xor     r9d, r9d
0x180014450  lea     r8, [rsp+198h+var_98]
0x180014458  lea     rdx, byte_18004F39D
0x18001445f  lea     rcx, dword_18005A000
0x180014466  call    _tlgWriteTransfer_EventWriteTransfer
0x18001446b  mov     [rsp+198h+var_158], ebx
0x18001446f  cmp     [rsp+198h+var_100], bl
0x180014476  jz      short loc_18001448A
0x180014478  mov     [rsp+198h+var_100], bl
0x18001447f  lea     rcx, [rsp+198h+var_128]
0x180014484  call    _lambda_d195deafaa0b3d3fcf6dcc6e77906008___operator__
0x180014489  nop
0x18001448a  cmp     [rsp+198h+var_A0], 1
0x180014492  jnz     short loc_1800144B3
0x180014494  mov     [rsp+198h+var_A0], 2
0x18001449f  lea     rdx, [rsp+198h+var_98]
0x1800144a7  lea     rcx, dword_18005A000
0x1800144ae  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x1800144b3  mov     [rsp+198h+var_A0], r14d
0x1800144bb  xor     eax, eax
0x1800144bd  jmp     loc_1800147B6
0x1800144c2  lea     rcx, [rsp+198h+var_78]; this
0x1800144ca  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x1800144cf  nop
0x1800144d0  mov     [rsp+198h+var_154], ebx
0x1800144d4  mov     [rsp+198h+var_148], 4
0x1800144dc  lea     rax, [rsp+198h+var_148]
0x1800144e1  mov     [rsp+198h+pcbData], rax; pcbData
0x1800144e6  lea     rax, [rsp+198h+var_154]
0x1800144eb  mov     [rsp+198h+pvData], rax; pvData
0x1800144f0  mov     [rsp+198h+pdwType], rbx; int
0x1800144f5  mov     r9d, 20000010h; dwFlags
0x1800144fb  lea     r8, Value; "InstallType"
0x180014502  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014509  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180014510  call    cs:__imp_RegGetValueW
0x180014516  cmp     [rsp+198h+var_154], 11h
0x18001451b  jnz     loc_1800145D9
0x180014521  cmp     r12d, 1
0x180014525  jnz     loc_1800145D9
0x18001452b  mov     eax, cs:dword_18005A000
0x180014531  cmp     eax, 4
0x180014534  jbe     short loc_180014569
0x180014536  lea     rax, [rsp+198h+var_48]
0x18001453e  mov     [rsp+198h+pvData], rax
0x180014543  mov     dword ptr [rsp+198h+pdwType], 2
0x18001454b  xor     r9d, r9d
0x18001454e  lea     r8, [rsp+198h+var_98]
0x180014556  lea     rdx, word_18004F69A
0x18001455d  lea     rcx, dword_18005A000
0x180014564  call    _tlgWriteTransfer_EventWriteTransfer
0x180014569  xorps   xmm0, xmm0
0x18001456c  movdqu  xmmword ptr [rsp+198h+var_140], xmm0
0x180014572  mov     [rsp+198h+var_130], rbx
0x180014577  lea     rcx, [rsp+198h+var_140]
0x18001457c  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180014581  mov     r14, [rsp+198h+var_140+8]
0x180014586  mov     qword ptr [r14+18h], 7
0x18001458e  mov     [r14+10h], rbx
0x180014592  mov     [r14], bx
0x180014596  mov     r8d, 24h ; '$'
0x18001459c  lea     rdx, aProgramdataMic; "%PROGRAMDATA%\\Microsoft\\Provisioning"
0x1800145a3  mov     rcx, r14; void *
0x1800145a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800145ab  lea     rax, [r14+20h]
0x1800145af  mov     [rsp+198h+var_140+8], rax
0x1800145b4  lea     rdx, [rsp+198h+var_140]
0x1800145b9  lea     rcx, [rsp+198h+var_48]
0x1800145c1  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800145c6  mov     rdx, rax
0x1800145c9  lea     rcx, [rsp+198h+var_78]
0x1800145d1  call    ?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::wstring>)
0x1800145d6  nop
0x1800145d7  jmp     short loc_18001460A
0x1800145d9  xorps   xmm0, xmm0
0x1800145dc  movdqu  xmmword ptr [rsp+198h+var_140], xmm0
0x1800145e2  mov     [rsp+198h+var_130], rbx
0x1800145e7  lea     rdx, [rsp+198h+var_140]
0x1800145ec  lea     rcx, [rsp+198h+var_48]
0x1800145f4  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800145f9  mov     rdx, rax
0x1800145fc  lea     rcx, [rsp+198h+var_78]
0x180014604  call    ?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::wstring>)
0x180014609  nop
0x18001460a  lea     rcx, [rsp+198h+var_140]
0x18001460f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014614  lea     rdx, [rsp+198h+var_B8]
0x18001461c  lea     rcx, [rsp+198h+var_78]
0x180014624  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x180014629  nop
0x18001462a  xorps   xmm0, xmm0
0x18001462d  movdqa  [rsp+198h+var_F8], xmm0
0x180014636  xor     r8d, r8d
0x180014639  xor     edx, edx
0x18001463b  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<std::pair<std::wstring const,std::wstring>>>::_Buynode0(std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180014640  mov     qword ptr [rsp+198h+var_F8], rax
0x180014648  xorps   xmm0, xmm0
0x18001464b  movdqa  [rsp+198h+var_E8], xmm0
0x180014654  mov     [rsp+198h+var_D8], rbx
0x18001465c  mov     [rsp+198h+var_C0], 3F800000h
0x180014667  mov     edx, 8
0x18001466c  lea     rcx, [rsp+198h+var_F8]
0x180014674  call    ?_Init@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Init(unsigned __int64)
0x180014679  nop
0x18001467a  lea     r8, [rsp+198h+var_F8]
0x180014682  lea     rdx, [rsp+198h+var_B8]
0x18001468a  mov     rcx, r15
0x18001468d  call    ?HandleStatesForPackagesInternal@CMVEngine@@AEAAJAEBV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; CMVEngine::HandleStatesForPackagesInternal(std::vector<std::unique_ptr<ProvPackage>> const &,std::unordered_map<std::wstring,std::wstring> *)
0x180014692  mov     rcx, [rsp+198h]; this
0x18001469a  test    eax, eax
0x18001469c  js      loc_1800147DC
0x1800146a2  lea     rdx, [rsp+198h+var_F8]
0x1800146aa  call    ?ResolveDeletedPackages@CMVEngine@@AEAAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; CMVEngine::ResolveDeletedPackages(std::unordered_map<std::wstring,std::wstring> const &)
0x1800146af  mov     rcx, [rsp+198h]; this
0x1800146b7  test    eax, eax
0x1800146b9  js      loc_1800147F0
0x1800146bf  mov     rcx, qword ptr [rsp+198h+var_E8]
0x1800146c7  test    rcx, rcx
0x1800146ca  jz      short loc_1800146E6
0x1800146cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800146d2  xorps   xmm0, xmm0
0x1800146d5  movdqa  [rsp+198h+var_E8], xmm0
0x1800146de  mov     [rsp+198h+var_D8], rbx
0x1800146e6  lea     rcx, [rsp+198h+var_F8]
0x1800146ee  call    ?clear@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAXXZ; std::list<std::pair<std::wstring const,std::wstring>>::clear(void)
0x1800146f3  mov     rcx, qword ptr [rsp+198h+var_F8]
0x1800146fb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014701  nop
0x180014702  lea     rcx, [rsp+198h+var_B8]
0x18001470a  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x18001470f  nop
0x180014710  lea     rcx, [rsp+198h+var_78]; this
0x180014718  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x18001471d  nop
0x18001471e  mov     r14d, [rsp+198h+var_158]
0x180014723  cmp     [rsp+198h+var_100], bl
0x18001472a  jz      short loc_18001473E
0x18001472c  mov     [rsp+198h+var_100], bl
0x180014733  lea     rcx, [rsp+198h+var_128]
0x180014738  call    _lambda_d195deafaa0b3d3fcf6dcc6e77906008___operator__
0x18001473d  nop
0x18001473e  cmp     [rsp+198h+var_A0], 1
0x180014746  jnz     short loc_180014767
0x180014748  mov     [rsp+198h+var_A0], 2
0x180014753  lea     rdx, [rsp+198h+var_98]
0x18001475b  lea     rcx, dword_18005A000
0x180014762  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x180014767  mov     eax, r14d
0x18001476a  jmp     short loc_1800147B6
0x18001476c  xor     ebx, ebx
0x18001476e  cmp     [rsp+198h+var_100], bl
0x180014775  jz      short loc_180014789
0x180014777  mov     [rsp+198h+var_100], bl
0x18001477e  lea     rcx, [rsp+198h+var_128]
0x180014783  call    _lambda_d195deafaa0b3d3fcf6dcc6e77906008___operator__
0x180014788  nop
0x180014789  cmp     [rsp+198h+var_A0], 1
0x180014791  jnz     short loc_1800147B2
0x180014793  mov     [rsp+198h+var_A0], 2
0x18001479e  lea     rdx, [rsp+198h+var_98]
0x1800147a6  lea     rcx, dword_18005A000
0x1800147ad  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x1800147b2  mov     eax, [rsp+198h+var_148]
0x1800147b6  mov     rcx, [rsp+198h+var_28]
0x1800147be  xor     rcx, rsp; StackCookie
0x1800147c1  call    __security_check_cookie
0x1800147c6  mov     rbx, [rsp+198h+arg_18]
0x1800147ce  add     rsp, 180h
0x1800147d5  pop     r15
0x1800147d7  pop     r14
0x1800147d9  pop     r12
0x1800147db  retn
0x1800147dc  mov     r9d, eax; char *
0x1800147df  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800147e6  mov     edx, 7F0h; void *
0x1800147eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800147f0  mov     r9d, eax; char *
0x1800147f3  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800147fa  mov     edx, 7F1h; void *
0x1800147ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

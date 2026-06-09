# RegisterViewExtension(int,CObjectRegParams &,int)

- ea: `0x18005b880`
- end: `0x18005bc19`
- name: `?RegisterViewExtension@@YAJHAEAVCObjectRegParams@@H@Z`
- size: `921`
- prototype: `int(int, struct CObjectRegParams *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8b90`

## callees

- `0x180004998`
- `0x1800074d0`
- `0x18003bf5c`
- `0x180053eec`
- `0x18005b880`
- `0x18005d738`
- `0x18007ce7c`
- `0x18008f5c0`
- `0x1800c90f4`
- `0x1800c9b14`
- `0x1800caa44`
- `0x1801152d8`

## import_xrefs

- `mmcbase!MMCUpdateRegistry` at `0x18005b8cd`
- `mmcbase!MMCUpdateRegistry` at `0x18005b8cd`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b8f4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b93d`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b9ee`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005bbb1`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b8f4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b93d`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005b9ee`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005bbb1`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005b8ab`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005b8ab`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005b8da`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005b923`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005ba15`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005bb01`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005bb9b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005b8da`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005b923`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005ba15`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005bb01`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005bb9b`
- `mmcbase!GetStringModule` at `0x18005b94a`
- `mmcbase!GetStringModule` at `0x18005b94a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005b9c9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005b9c9`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005b8be`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005b8be`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b8e5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b92e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b9df`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005ba20`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005bb0c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005bba6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b8e5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b92e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005b9df`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005ba20`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005bb0c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005bba6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005b9d4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005bbf5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005b9d4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005bbf5`
- `ole32!StringFromCLSID` at `0x18005b916`
- `ole32!StringFromCLSID` at `0x18005b916`

## string_xrefs

- `0x18005ba2e`: `VCLSID`
- `0x18005b8b2`: `RegisterViewExtension`
- `0x18005bb64`: `HKLM\n{\n    NoRemove Software\n    {\n        NoRemove Microsoft\n        {\n            NoRemove MMC\n            {\n                NoRemove SnapIns\n                {\n                    ForceRemove %VCLSID%\n                    {\n                        val NameString = s '%VSnapinName%'\n                        val NameStringIndirect = s '%VSnapinNameIndirect%'\n                    }\n                }\n            }\n        }\n    }\n}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RegisterViewExtension(int a1, struct CObjectRegParams *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  HMODULE StringModule; // rbx
  mmcerror::SC *v8; // rax
  unsigned int v9; // eax
  const unsigned __int16 *v10; // rdx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdi
  const unsigned __int16 *v17; // rsi
  unsigned int v18; // eax
  unsigned int v19; // eax
  _BYTE v21[24]; // [rsp+30h] [rbp-D0h] BYREF
  void **v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  void **v26; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v30; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v31[11]; // [rsp+98h] [rbp-68h]
  _BYTE v32[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[48]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v34[32]; // [rsp+130h] [rbp+30h] BYREF
  LPOLESTR lpsz; // [rsp+198h] [rbp+98h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v21, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v21, L"RegisterViewExtension");
  v4 = MMCUpdateRegistry(a1, a2, 0);
  mmcerror::SC::operator=(v21, v4);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
  {
    v5 = mmcerror::SC::ToHr((mmcerror::SC *)v21);
  }
  else
  {
    lpsz = 0;
    v6 = StringFromCLSID((const IID *const)a2, &lpsz);
    mmcerror::SC::operator=(v21, v6);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
    {
      v5 = mmcerror::SC::ToHr((mmcerror::SC *)v21);
    }
    else
    {
      StringModule = GetStringModule();
      v26 = &CStr::`vftable';
      v27 = &CStr::s_rgwchEmptyStringBuffer;
      v28 = 0;
      v29 = 0;
      CStr::LoadStringW((CStr *)&v26, StringModule, 0x3761u);
      v22 = &CStr::`vftable';
      v23 = &CStr::s_rgwchEmptyStringBuffer;
      v24 = 0;
      v25 = 0;
      v8 = ScFormatIndirectSnapInName((mmcerror::SC *)v34, StringModule, 0x3761u, (CStr *)&v22);
      mmcerror::SC::operator=(v21, v8);
      mmcerror::SC::~SC((mmcerror::SC *)v34);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
      {
        v5 = mmcerror::SC::ToHr((mmcerror::SC *)v21);
      }
      else
      {
        ATL::CRegObject::CRegObject((ATL::CRegObject *)v32);
        v9 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)v33);
        mmcerror::SC::operator=(v21, v9);
        if ( !(unsigned __int8)mmcerror::SC::operator bool(v21) )
        {
          v30 = L"VCLSID";
          v31[0] = lpsz;
          v31[1] = L"VSnapinName";
          v31[2] = v27;
          v31[3] = L"VSnapinNameIndirect";
          v31[4] = v23;
          v31[5] = L"VClassName";
          v11 = (unsigned __int16 *)((char *)a2 + 80);
          if ( *((_QWORD *)a2 + 13) >= 8u )
            v11 = *(unsigned __int16 **)v11;
          v31[6] = v11;
          v31[7] = L"VProgID";
          v12 = (unsigned __int16 *)((char *)a2 + 112);
          if ( *((_QWORD *)a2 + 17) >= 8u )
            v12 = *(unsigned __int16 **)v12;
          v31[8] = v12;
          v31[9] = L"VVersionIndependentProgID";
          v13 = (unsigned __int16 *)((char *)a2 + 144);
          if ( *((_QWORD *)a2 + 21) >= 8u )
            v13 = *(unsigned __int16 **)v13;
          v31[10] = v13;
          v14 = 0;
          v15 = WPP_GLOBAL_Control;
          while ( v14 < 6 )
          {
            v16 = v31[2 * (int)v14];
            v17 = v31[2 * (int)v14 - 1];
            v18 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v32, v17, v16);
            mmcerror::SC::operator=(v21, v18);
            if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
              goto LABEL_25;
            v15 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
            {
              WPP_SF_SS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                10,
                (unsigned int)WPP_4ceaea86f5ba3dd5b16b8a255ca070b4_Traceguids,
                (_DWORD)v17,
                (__int64)v16);
              v15 = WPP_GLOBAL_Control;
            }
            ++v14;
          }
          if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && *(_BYTE *)(v15 + 25) >= 4u )
            WPP_SF_S(
              *(_QWORD *)(v15 + 16),
              11,
              WPP_4ceaea86f5ba3dd5b16b8a255ca070b4_Traceguids,
              L"HKLM\n"
               "{\n"
               "    NoRemove Software\n"
               "    {\n"
               "        NoRemove Microsoft\n"
               "        {\n"
               "            NoRemove MMC\n"
               "            {\n"
               "                NoRemove SnapIns\n"
               "                {\n"
               "                    ForceRemove %VCLSID%\n"
               "                    {\n"
               "                        val NameString = s '%VSnapinName%'\n"
               "                        val NameStringIndirect = s '%VSnapinNameIndirect%'\n"
               "                    }\n"
               "                }\n"
               "            }\n"
               "        }\n"
               "    }\n"
               "}");
          v19 = ATL::CRegObject::RegisterWithString((ATL::CRegObject *)v32, v10, a1 != 0);
          mmcerror::SC::operator=(v21, v19);
          mmcerror::SC::operator bool(v21);
        }
LABEL_25:
        v5 = mmcerror::SC::ToHr((mmcerror::SC *)v21);
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)v32);
      }
      v22 = &CStr::`vftable';
      CStr::Empty((CStr *)&v22);
      v26 = &CStr::`vftable';
      CStr::Empty((CStr *)&v26);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
  }
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  return v5;
}

```

## disassembly

```asm
0x18005b880  mov     [rsp-8+arg_0], rbx
0x18005b885  mov     [rsp-8+arg_8], rsi
0x18005b88a  push    rbp
0x18005b88b  push    rdi
0x18005b88c  push    r12
0x18005b88e  push    r14
0x18005b890  push    r15
0x18005b892  lea     rbp, [rsp-50h]
0x18005b897  sub     rsp, 150h
0x18005b89e  mov     rdi, rdx
0x18005b8a1  mov     r14d, ecx
0x18005b8a4  xor     edx, edx
0x18005b8a6  lea     rcx, [rsp+170h+var_140]
0x18005b8ab  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18005b8b1  nop
0x18005b8b2  lea     rdx, aRegisterviewex; "RegisterViewExtension"
0x18005b8b9  lea     rcx, [rsp+170h+var_140]
0x18005b8be  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18005b8c4  xor     r8d, r8d
0x18005b8c7  mov     rdx, rdi
0x18005b8ca  mov     ecx, r14d
0x18005b8cd  call    cs:__imp_?MMCUpdateRegistry@@YAJHPEBVCObjectRegParams@@PEBVCControlRegParams@@@Z; MMCUpdateRegistry(int,CObjectRegParams const *,CControlRegParams const *)
0x18005b8d3  mov     edx, eax
0x18005b8d5  lea     rcx, [rsp+170h+var_140]
0x18005b8da  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005b8e0  lea     rcx, [rsp+170h+var_140]
0x18005b8e5  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005b8eb  test    al, al
0x18005b8ed  jz      short loc_18005B901
0x18005b8ef  lea     rcx, [rsp+170h+var_140]
0x18005b8f4  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005b8fa  mov     ebx, eax
0x18005b8fc  jmp     loc_18005BBF0
0x18005b901  mov     [rbp+70h+lpsz], 0
0x18005b90c  lea     rdx, [rbp+70h+lpsz]; lplpsz
0x18005b913  mov     rcx, rdi; rclsid
0x18005b916  call    cs:__imp_StringFromCLSID
0x18005b91c  mov     edx, eax
0x18005b91e  lea     rcx, [rsp+170h+var_140]
0x18005b923  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005b929  lea     rcx, [rsp+170h+var_140]
0x18005b92e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005b934  test    al, al
0x18005b936  jz      short loc_18005B94A
0x18005b938  lea     rcx, [rsp+170h+var_140]
0x18005b93d  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005b943  mov     ebx, eax
0x18005b945  jmp     loc_18005BBE3
0x18005b94a  call    cs:__imp_?GetStringModule@@YAPEAUHINSTANCE__@@XZ; GetStringModule(void)
0x18005b950  mov     rbx, rax
0x18005b953  lea     r12, ??_7CStr@@6B@; const CStr::`vftable'
0x18005b95a  mov     [rsp+170h+var_108], r12
0x18005b95f  lea     rsi, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18005b966  mov     [rsp+170h+var_100], rsi
0x18005b96b  mov     [rsp+170h+var_F8], 0
0x18005b974  mov     [rbp+70h+var_F0], 0
0x18005b97b  mov     r15d, 3761h
0x18005b981  mov     r8d, r15d; uID
0x18005b984  mov     rdx, rax; hInstance
0x18005b987  lea     rcx, [rsp+170h+var_108]; this
0x18005b98c  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x18005b991  mov     [rsp+170h+var_128], r12
0x18005b996  mov     [rsp+170h+var_120], rsi
0x18005b99b  mov     [rsp+170h+var_118], 0
0x18005b9a4  mov     [rsp+170h+var_110], 0
0x18005b9ac  lea     r9, [rsp+170h+var_128]
0x18005b9b1  mov     r8d, r15d
0x18005b9b4  mov     rdx, rbx
0x18005b9b7  lea     rcx, [rbp+70h+var_40]
0x18005b9bb  call    ?ScFormatIndirectSnapInName@@YA?AVSC@mmcerror@@PEAUHINSTANCE__@@HAEAVCStr@@@Z; ScFormatIndirectSnapInName(HINSTANCE__ *,int,CStr &)
0x18005b9c0  nop
0x18005b9c1  mov     rdx, rax
0x18005b9c4  lea     rcx, [rsp+170h+var_140]
0x18005b9c9  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005b9cf  nop
0x18005b9d0  lea     rcx, [rbp+70h+var_40]
0x18005b9d4  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005b9da  lea     rcx, [rsp+170h+var_140]
0x18005b9df  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005b9e5  test    al, al
0x18005b9e7  jz      short loc_18005B9FB
0x18005b9e9  lea     rcx, [rsp+170h+var_140]
0x18005b9ee  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005b9f4  mov     ebx, eax
0x18005b9f6  jmp     loc_18005BBC3
0x18005b9fb  lea     rcx, [rbp+70h+var_80]; this
0x18005b9ff  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x18005ba04  nop
0x18005ba05  lea     rcx, [rbp+70h+var_70]; this
0x18005ba09  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18005ba0e  mov     edx, eax
0x18005ba10  lea     rcx, [rsp+170h+var_140]
0x18005ba15  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005ba1b  lea     rcx, [rsp+170h+var_140]
0x18005ba20  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005ba26  test    al, al
0x18005ba28  jnz     loc_18005BBAC
0x18005ba2e  lea     rax, aVclsid; "VCLSID"
0x18005ba35  mov     [rbp+70h+var_E0], rax
0x18005ba39  mov     rax, [rbp+70h+lpsz]
0x18005ba40  mov     [rbp+70h+var_D8], rax
0x18005ba44  lea     rax, aVsnapinname; "VSnapinName"
0x18005ba4b  mov     [rbp+70h+var_D0], rax
0x18005ba4f  mov     rax, [rsp+170h+var_100]
0x18005ba54  mov     [rbp+70h+var_C8], rax
0x18005ba58  lea     rax, aVsnapinnameind; "VSnapinNameIndirect"
0x18005ba5f  mov     [rbp+70h+var_C0], rax
0x18005ba63  mov     rax, [rsp+170h+var_120]
0x18005ba68  mov     [rbp+70h+var_B8], rax
0x18005ba6c  lea     rax, aVclassname; "VClassName"
0x18005ba73  mov     [rbp+70h+var_B0], rax
0x18005ba77  lea     rax, [rdi+50h]
0x18005ba7b  cmp     qword ptr [rax+18h], 8
0x18005ba80  jb      short loc_18005BA85
0x18005ba82  mov     rax, [rax]
0x18005ba85  mov     [rbp+70h+var_A8], rax
0x18005ba89  lea     rax, aVprogid; "VProgID"
0x18005ba90  mov     [rbp+70h+var_A0], rax
0x18005ba94  lea     rax, [rdi+70h]
0x18005ba98  cmp     qword ptr [rax+18h], 8
0x18005ba9d  jb      short loc_18005BAA2
0x18005ba9f  mov     rax, [rax]
0x18005baa2  mov     [rbp+70h+var_98], rax
0x18005baa6  lea     rax, aVversionindepe; "VVersionIndependentProgID"
0x18005baad  mov     [rbp+70h+var_90], rax
0x18005bab1  lea     rax, [rdi+90h]
0x18005bab8  cmp     qword ptr [rax+18h], 8
0x18005babd  jb      short loc_18005BAC2
0x18005babf  mov     rax, [rax]
0x18005bac2  mov     [rbp+70h+var_88], rax
0x18005bac6  xor     ebx, ebx
0x18005bac8  lea     r15, WPP_GLOBAL_Control
0x18005bacf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bad6  cmp     ebx, 6
0x18005bad9  jnb     short loc_18005BB54
0x18005badb  movsxd  rax, ebx
0x18005bade  add     rax, rax
0x18005bae1  mov     rdi, [rbp+rax*8+70h+var_D8]
0x18005bae6  mov     rsi, [rbp+rax*8+70h+var_E0]
0x18005baeb  mov     r8, rdi; unsigned __int16 *
0x18005baee  mov     rdx, rsi; unsigned __int16 *
0x18005baf1  lea     rcx, [rbp+70h+var_80]; this
0x18005baf5  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18005bafa  mov     edx, eax
0x18005bafc  lea     rcx, [rsp+170h+var_140]
0x18005bb01  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005bb07  lea     rcx, [rsp+170h+var_140]
0x18005bb0c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005bb12  test    al, al
0x18005bb14  jnz     loc_18005BBAC
0x18005bb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb21  cmp     rcx, r15
0x18005bb24  jz      short loc_18005BB50
0x18005bb26  cmp     byte ptr [rcx+19h], 4
0x18005bb2a  jb      short loc_18005BB50
0x18005bb2c  mov     edx, 0Ah
0x18005bb31  mov     [rsp+170h+var_150], rdi
0x18005bb36  mov     r9, rsi
0x18005bb39  lea     r8, WPP_4ceaea86f5ba3dd5b16b8a255ca070b4_Traceguids
0x18005bb40  mov     rcx, [rcx+10h]
0x18005bb44  call    WPP_SF_SS
0x18005bb49  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb50  inc     ebx
0x18005bb52  jmp     short loc_18005BAD6
0x18005bb54  cmp     rcx, r15
0x18005bb57  jz      short loc_18005BB7B
0x18005bb59  cmp     byte ptr [rcx+19h], 4
0x18005bb5d  jb      short loc_18005BB7B
0x18005bb5f  mov     edx, 0Bh
0x18005bb64  lea     r9, aHklmNoremoveSo; "HKLM\n{\n    NoRemove Software\n    {\n"...
0x18005bb6b  lea     r8, WPP_4ceaea86f5ba3dd5b16b8a255ca070b4_Traceguids
0x18005bb72  mov     rcx, [rcx+10h]
0x18005bb76  call    WPP_SF_S
0x18005bb7b  lea     rcx, [rbp+70h+var_80]; this
0x18005bb7f  test    r14d, r14d
0x18005bb82  jz      short loc_18005BB8C
0x18005bb84  mov     r8d, 1
0x18005bb8a  jmp     short loc_18005BB8F
0x18005bb8c  xor     r8d, r8d; int
0x18005bb8f  call    ?RegisterWithString@CRegObject@ATL@@IEAAJPEBGH@Z; ATL::CRegObject::RegisterWithString(ushort const *,int)
0x18005bb94  mov     edx, eax
0x18005bb96  lea     rcx, [rsp+170h+var_140]
0x18005bb9b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005bba1  lea     rcx, [rsp+170h+var_140]
0x18005bba6  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005bbac  lea     rcx, [rsp+170h+var_140]
0x18005bbb1  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005bbb7  mov     ebx, eax
0x18005bbb9  lea     rcx, [rbp+70h+var_80]; this
0x18005bbbd  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18005bbc2  nop
0x18005bbc3  mov     [rsp+170h+var_128], r12
0x18005bbc8  lea     rcx, [rsp+170h+var_128]; this
0x18005bbcd  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18005bbd2  nop
0x18005bbd3  mov     [rsp+170h+var_108], r12
0x18005bbd8  lea     rcx, [rsp+170h+var_108]; this
0x18005bbdd  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18005bbe2  nop
0x18005bbe3  lea     rcx, [rbp+70h+lpsz]
0x18005bbea  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18005bbef  nop
0x18005bbf0  lea     rcx, [rsp+170h+var_140]
0x18005bbf5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005bbfb  mov     eax, ebx
0x18005bbfd  lea     r11, [rsp+170h+var_20]
0x18005bc05  mov     rbx, [r11+30h]
0x18005bc09  mov     rsi, [r11+38h]
0x18005bc0d  mov     rsp, r11
0x18005bc10  pop     r15
0x18005bc12  pop     r14
0x18005bc14  pop     r12
0x18005bc16  pop     rdi
0x18005bc17  pop     rbp
0x18005bc18  retn
```

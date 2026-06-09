# EapLm::Peer::LegacyEapMethodConfig::ConfigBlob2Xml(uint,ConstBuffer const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x180017ea0`
- end: `0x1800182a4`
- name: `?ConfigBlob2Xml@LegacyEapMethodConfig@Peer@EapLm@@UEAA_NIAEBUConstBuffer@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `1028`
- prototype: `char __fastcall(__int64, unsigned int, _QWORD *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000d0e8`
- `0x18000d184`
- `0x18001549c`
- `0x180015f10`
- `0x1800162a4`
- `0x180016400`
- `0x180017ea0`
- `0x18001b154`
- `0x18001b328`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180017eee`
- `ntdll!EtwEventEnabled` at `0x18001803f`
- `ntdll!EtwEventEnabled` at `0x180018183`
- `ntdll!EtwEventEnabled` at `0x180018231`
- `ntdll!EtwEventEnabled` at `0x180017eee`
- `ntdll!EtwEventEnabled` at `0x18001803f`
- `ntdll!EtwEventEnabled` at `0x180018183`
- `ntdll!EtwEventEnabled` at `0x180018231`

## string_xrefs

- `0x180017f04`: `RasEapCreateConnectionPropertiesXml Entry:\n flags(%d), blob(%Id) bytes`
- `0x180017fab`: `ConfigBlob2Xml`
- `0x18001823b`: `LegacyEapMethodConfig::ConfigBlob2Xml See method logs for details`
- `0x18001804c`: `RasEapCreateConnectionPropertiesXml failed %d`
- `0x18001818d`: `RasEapCreateConnectionPropertiesXml Exit`

## pseudocode

```c
char __fastcall EapLm::Peer::LegacyEapMethodConfig::ConfigBlob2Xml(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        struct IUnknown **a4)
{
  __int64 (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD, __int64 *); // r15
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  struct IUnknown **v14; // rax
  __int64 v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v17; // [rsp+40h] [rbp-C0h] BYREF
  void **v18; // [rsp+48h] [rbp-B8h] BYREF
  char v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+54h] [rbp-ACh]
  int v21; // [rsp+60h] [rbp-A0h]
  char v22[2048]; // [rsp+70h] [rbp-90h] BYREF

  v16[0] = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v22,
              0x800u,
              "RasEapCreateConnectionPropertiesXml Entry:\n flags(%d), blob(%Id) bytes",
              a2,
              a3[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v22);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dP(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2, a3[1]);
  ATL::CComPtrBase<IXMLDOMDocument2>::Release(a4);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 200), 1);
  v8 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)(a1 + 200) + 216LL);
  if ( !v8 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupportedInfo, "ConfigBlob2Xml");
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_49;
    v10 = 49;
    goto LABEL_31;
  }
  v11 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a3[1]);
  v12 = v8(*(unsigned __int8 *)(a1 + 16), a2, *a3, v11, v16);
  v13 = v12;
  if ( v12 == 50 || v12 == 127 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v22, 0x800u, "LegacyEapMethodConfig::ConfigBlob2Xml See method logs for details") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v22);
    }
    goto LABEL_49;
  }
  if ( v12 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v22, 0x800u, "RasEapCreateConnectionPropertiesXml failed %d", v13) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v22);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v13);
    v19 = *(_BYTE *)(a1 + 16);
    v20 = *(_QWORD *)(a1 + 20);
    if ( v19 != -2 )
      v20 = 0;
    v18 = &EapHost::EapMethodType::`vftable';
    v21 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)&v18, v13);
  }
  if ( !v16[0] )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_49;
    v10 = 52;
LABEL_31:
    WPP_SF_(v9[2], v10, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
LABEL_49:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v16);
    return 0;
  }
  v16[1] = v16[0];
  (*(void (**)(void))(*(_QWORD *)v16[0] + 8LL))();
  v14 = (struct IUnknown **)EapHost::BaseXmlHelper::CopyXml(&v17);
  if ( *a4 != *v14 )
    ATL::AtlComPtrAssign(a4, *v14);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v17);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "RasEapCreateConnectionPropertiesXml Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v22);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v16);
  return 1;
}

```

## disassembly

```asm
0x180017ea0  push    rbp
0x180017ea2  push    rbx
0x180017ea3  push    rsi
0x180017ea4  push    rdi
0x180017ea5  push    r13
0x180017ea7  push    r14
0x180017ea9  push    r15
0x180017eab  lea     rbp, [rsp-780h]
0x180017eb3  sub     rsp, 880h
0x180017eba  mov     rax, cs:__security_cookie
0x180017ec1  xor     rax, rsp
0x180017ec4  mov     [rbp+7B0h+var_40], rax
0x180017ecb  mov     rsi, r9
0x180017ece  mov     rbx, r8
0x180017ed1  mov     r14d, edx
0x180017ed4  mov     rdi, rcx
0x180017ed7  mov     [rsp+8B0h+var_880], 0
0x180017ee0  lea     rdx, DebugInfoEvent
0x180017ee7  mov     rcx, cs:eaphost_Context
0x180017eee  call    cs:__imp_EtwEventEnabled
0x180017ef4  test    al, al
0x180017ef6  jz      short loc_180017F3F
0x180017ef8  mov     rax, [rbx+8]
0x180017efc  mov     [rsp+8B0h+var_890], rax
0x180017f01  mov     r9d, r14d
0x180017f04  lea     r8, aRaseapcreateco_3; "RasEapCreateConnectionPropertiesXml Ent"...
0x180017f0b  mov     edx, 800h; unsigned __int64
0x180017f10  lea     rcx, [rsp+8B0h+var_840]; char *
0x180017f15  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180017f1a  test    eax, eax
0x180017f1c  js      short loc_180017F3F
0x180017f1e  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180017f25  jge     short loc_180017F3F
0x180017f27  lea     r8, [rsp+8B0h+var_840]
0x180017f2c  lea     rdx, DebugInfoEvent
0x180017f33  lea     rcx, eaphost_Context
0x180017f3a  call    McTemplateU0s_EtwEventWriteTransfer
0x180017f3f  lea     r13, WPP_GLOBAL_Control
0x180017f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f4d  cmp     rcx, r13
0x180017f50  jz      short loc_180017F79
0x180017f52  test    byte ptr [rcx+1Ch], 4
0x180017f56  jz      short loc_180017F79
0x180017f58  mov     edx, 30h ; '0'
0x180017f5d  mov     rax, [rbx+8]
0x180017f61  mov     [rsp+8B0h+var_890], rax
0x180017f66  mov     r9d, r14d
0x180017f69  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180017f70  mov     rcx, [rcx+10h]
0x180017f74  call    WPP_SF_dP
0x180017f79  mov     rcx, rsi
0x180017f7c  call    ?Release@?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMDocument2>::Release(void)
0x180017f81  mov     dl, 1; bool
0x180017f83  mov     rcx, [rdi+0C8h]; this
0x180017f8a  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180017f8f  mov     rax, [rdi+0C8h]
0x180017f96  mov     r15, [rax+0D8h]
0x180017f9d  test    r15, r15
0x180017fa0  jnz     short loc_180017FE9
0x180017fa2  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x180017fa9  jz      short loc_180017FC5
0x180017fab  lea     r8, aConfigblob2xml; "ConfigBlob2Xml"
0x180017fb2  lea     rdx, PeerFunctionNotSupportedInfo
0x180017fb9  lea     rcx, eaphost_Context
0x180017fc0  call    McTemplateU0s_EtwEventWriteTransfer
0x180017fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fcc  cmp     rcx, r13
0x180017fcf  jz      loc_180018277
0x180017fd5  test    byte ptr [rcx+1Ch], 4
0x180017fd9  jz      loc_180018277
0x180017fdf  mov     edx, 31h ; '1'
0x180017fe4  jmp     loc_180018120
0x180017fe9  mov     rcx, [rbx+8]
0x180017fed  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180017ff2  movzx   ecx, byte ptr [rdi+10h]
0x180017ff6  lea     rdx, [rsp+8B0h+var_880]
0x180017ffb  mov     [rsp+8B0h+var_890], rdx
0x180018000  mov     r9d, eax
0x180018003  mov     r8, [rbx]
0x180018006  mov     edx, r14d
0x180018009  mov     rax, r15
0x18001800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018011  mov     ebx, eax
0x180018013  mov     edx, 32h ; '2'
0x180018018  cmp     eax, edx
0x18001801a  jz      loc_180018201
0x180018020  cmp     eax, 7Fh
0x180018023  jz      loc_180018201
0x180018029  test    eax, eax
0x18001802b  jz      loc_1800180F7
0x180018031  lea     rdx, DebugErrorEvent
0x180018038  mov     rcx, cs:eaphost_Context
0x18001803f  call    cs:__imp_EtwEventEnabled
0x180018045  test    al, al
0x180018047  jz      short loc_180018087
0x180018049  mov     r9d, ebx
0x18001804c  lea     r8, aRaseapcreateco_2; "RasEapCreateConnectionPropertiesXml fai"...
0x180018053  mov     edx, 800h; unsigned __int64
0x180018058  lea     rcx, [rsp+8B0h+var_840]; char *
0x18001805d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018062  test    eax, eax
0x180018064  js      short loc_180018087
0x180018066  test    cs:byte_18004AF81, 8
0x18001806d  jz      short loc_180018087
0x18001806f  lea     r8, [rsp+8B0h+var_840]
0x180018074  lea     rdx, DebugErrorEvent
0x18001807b  lea     rcx, eaphost_Context
0x180018082  call    McTemplateU0s_EtwEventWriteTransfer
0x180018087  mov     rcx, cs:WPP_GLOBAL_Control
0x18001808e  cmp     rcx, r13
0x180018091  jz      short loc_1800180B1
0x180018093  test    byte ptr [rcx+1Ch], 1
0x180018097  jz      short loc_1800180B1
0x180018099  mov     edx, 33h ; '3'
0x18001809e  mov     r9d, ebx
0x1800180a1  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800180a8  mov     rcx, [rcx+10h]
0x1800180ac  call    WPP_SF_d
0x1800180b1  mov     cl, [rdi+10h]
0x1800180b4  mov     [rsp+8B0h+var_860], cl
0x1800180b8  mov     eax, [rdi+14h]
0x1800180bb  mov     dword ptr [rsp+8B0h+var_85C], eax
0x1800180bf  mov     eax, [rdi+18h]
0x1800180c2  mov     dword ptr [rsp+8B0h+var_85C+4], eax
0x1800180c6  cmp     cl, 0FEh
0x1800180c9  jz      short loc_1800180D4
0x1800180cb  mov     [rsp+8B0h+var_85C], 0
0x1800180d4  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800180db  mov     [rsp+8B0h+var_868], rax
0x1800180e0  mov     eax, [rdi+1Ch]
0x1800180e3  mov     [rsp+8B0h+var_850], eax
0x1800180e7  mov     r8d, ebx; unsigned int
0x1800180ea  lea     rdx, [rsp+8B0h+var_868]; struct EapHost::EapMethodType *
0x1800180ef  mov     ecx, ebx; unsigned int
0x1800180f1  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x1800180f7  mov     rcx, [rsp+8B0h+var_880]
0x1800180fc  test    rcx, rcx
0x1800180ff  jnz     short loc_180018135
0x180018101  mov     rcx, cs:WPP_GLOBAL_Control
0x180018108  cmp     rcx, r13
0x18001810b  jz      loc_180018277
0x180018111  test    byte ptr [rcx+1Ch], 4
0x180018115  jz      loc_180018277
0x18001811b  mov     edx, 34h ; '4'
0x180018120  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018127  mov     rcx, [rcx+10h]
0x18001812b  call    WPP_SF_
0x180018130  jmp     loc_180018277
0x180018135  mov     [rsp+8B0h+var_878], rcx
0x18001813a  test    rcx, rcx
0x18001813d  jz      short loc_18001814C
0x18001813f  mov     rax, [rcx]
0x180018142  mov     rax, [rax+8]
0x180018146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001814b  nop
0x18001814c  lea     rdx, [rsp+8B0h+var_878]
0x180018151  lea     rcx, [rsp+8B0h+var_870]; struct IUnknown **
0x180018156  call    ?CopyXml@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@V34@@Z; EapHost::BaseXmlHelper::CopyXml(ATL::CComPtr<IXMLDOMDocument2>)
0x18001815b  mov     rdx, [rax]; struct IUnknown *
0x18001815e  cmp     [rsi], rdx
0x180018161  jz      short loc_18001816B
0x180018163  mov     rcx, rsi; struct IUnknown **
0x180018166  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001816b  lea     rcx, [rsp+8B0h+var_870]
0x180018170  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180018175  lea     rdx, DebugInfoEvent
0x18001817c  mov     rcx, cs:eaphost_Context
0x180018183  call    cs:__imp_EtwEventEnabled
0x180018189  test    al, al
0x18001818b  jz      short loc_1800181C8
0x18001818d  lea     r8, aRaseapcreateco_1; "RasEapCreateConnectionPropertiesXml Exi"...
0x180018194  mov     edx, 800h; unsigned __int64
0x180018199  lea     rcx, [rsp+8B0h+var_840]; char *
0x18001819e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800181a3  test    eax, eax
0x1800181a5  js      short loc_1800181C8
0x1800181a7  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800181ae  jge     short loc_1800181C8
0x1800181b0  lea     r8, [rsp+8B0h+var_840]
0x1800181b5  lea     rdx, DebugInfoEvent
0x1800181bc  lea     rcx, eaphost_Context
0x1800181c3  call    McTemplateU0s_EtwEventWriteTransfer
0x1800181c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181cf  cmp     rcx, r13
0x1800181d2  jz      short loc_1800181F0
0x1800181d4  test    byte ptr [rcx+1Ch], 4
0x1800181d8  jz      short loc_1800181F0
0x1800181da  mov     edx, 35h ; '5'
0x1800181df  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800181e6  mov     rcx, [rcx+10h]
0x1800181ea  call    WPP_SF_
0x1800181ef  nop
0x1800181f0  lea     rcx, [rsp+8B0h+var_880]
0x1800181f5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800181fa  mov     al, 1
0x1800181fc  jmp     loc_180018283
0x180018201  mov     rcx, cs:WPP_GLOBAL_Control
0x180018208  cmp     rcx, r13
0x18001820b  jz      short loc_180018223
0x18001820d  test    byte ptr [rcx+1Ch], 4
0x180018211  jz      short loc_180018223
0x180018213  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001821a  mov     rcx, [rcx+10h]
0x18001821e  call    WPP_SF_
0x180018223  lea     rdx, DebugInfoEvent
0x18001822a  mov     rcx, cs:eaphost_Context
0x180018231  call    cs:__imp_EtwEventEnabled
0x180018237  test    al, al
0x180018239  jz      short loc_180018277
0x18001823b  lea     r8, aLegacyeapmetho; "LegacyEapMethodConfig::ConfigBlob2Xml S"...
0x180018242  mov     edx, 800h; unsigned __int64
0x180018247  lea     rcx, [rsp+8B0h+var_840]; char *
0x18001824c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018251  test    eax, eax
0x180018253  js      short loc_180018277
0x180018255  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001825c  jge     short loc_180018277
0x18001825e  lea     r8, [rsp+8B0h+var_840]
0x180018263  lea     rdx, DebugInfoEvent
0x18001826a  lea     rcx, eaphost_Context
0x180018271  call    McTemplateU0s_EtwEventWriteTransfer
0x180018276  nop
0x180018277  lea     rcx, [rsp+8B0h+var_880]
0x18001827c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180018281  xor     al, al
0x180018283  mov     rcx, [rbp+7B0h+var_40]
0x18001828a  xor     rcx, rsp; StackCookie
0x18001828d  call    __security_check_cookie
0x180018292  add     rsp, 880h
0x180018299  pop     r15
0x18001829b  pop     r14
0x18001829d  pop     r13
0x18001829f  pop     rdi
0x1800182a0  pop     rsi
0x1800182a1  pop     rbx
0x1800182a2  pop     rbp
0x1800182a3  retn
```

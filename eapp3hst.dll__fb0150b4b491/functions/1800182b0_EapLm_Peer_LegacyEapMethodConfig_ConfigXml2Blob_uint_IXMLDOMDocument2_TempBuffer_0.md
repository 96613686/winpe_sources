# EapLm::Peer::LegacyEapMethodConfig::ConfigXml2Blob(uint,IXMLDOMDocument2 &,TempBuffer<0> &)

- ea: `0x1800182b0`
- end: `0x18001876e`
- name: `?ConfigXml2Blob@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `1214`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000bf94`
- `0x18000d0e8`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x1800182b0`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800182f2`
- `ntdll!EtwEventEnabled` at `0x180018530`
- `ntdll!EtwEventEnabled` at `0x18001861c`
- `ntdll!EtwEventEnabled` at `0x1800182f2`
- `ntdll!EtwEventEnabled` at `0x180018530`
- `ntdll!EtwEventEnabled` at `0x18001861c`

## string_xrefs

- `0x180018301`: `RasEapCreateConnectionProperties Entry:\n flags(%d)`
- `0x1800183a1`: `ConfigXml2Blob`
- `0x18001853d`: `RasEapCreateConnectionProperties failed %d`
- `0x18001862b`: `RasEapCreateConnectionProperties Exit:\n returning - bytes(%d)`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::LegacyEapMethodConfig::ConfigXml2Blob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rax
  __int64 (__fastcall *v8)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, const void **, unsigned int *); // r12
  void (__fastcall *v9)(const void *); // r13
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // edi
  unsigned int v16; // [rsp+40h] [rbp-8B8h] BYREF
  const void *v17; // [rsp+48h] [rbp-8B0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-8A8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-8A0h] BYREF
  void **v20; // [rsp+60h] [rbp-898h] BYREF
  char v21; // [rsp+68h] [rbp-890h]
  __int64 v22; // [rsp+6Ch] [rbp-88Ch]
  int v23; // [rsp+78h] [rbp-880h]
  __int64 v24; // [rsp+80h] [rbp-878h]
  void (__fastcall *v25)(const void *); // [rsp+88h] [rbp-870h]
  void **v26; // [rsp+90h] [rbp-868h]
  char v27; // [rsp+98h] [rbp-860h]
  __int64 v28; // [rsp+9Ch] [rbp-85Ch]
  int v29; // [rsp+A8h] [rbp-850h]
  char v30[2048]; // [rsp+B0h] [rbp-848h] BYREF

  v24 = a4;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v30, 0x800u, "RasEapCreateConnectionProperties Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v30);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 184), 1);
  v7 = *(_QWORD *)(a1 + 184);
  v8 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, const void **, unsigned int *))(v7 + 216);
  if ( !v8 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupported, "ConfigXml2Blob");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v21 = *(_BYTE *)(a1 + 16);
    v22 = *(_QWORD *)(a1 + 20);
    if ( v21 != -2 )
      v22 = 0;
    v20 = &EapHost::EapMethodType::`vftable';
    v23 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)&v20, 0x80420020);
  }
  v9 = *(void (__fastcall **)(const void *))(v7 + 232);
  v19 = 0;
  v27 = *(_BYTE *)(a1 + 16);
  v28 = *(_QWORD *)(a1 + 20);
  if ( v27 != -2 )
    v28 = 0;
  v26 = &EapHost::EapMethodType::`vftable';
  v29 = *(_DWORD *)(a1 + 28);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 360LL))(a3, &v19);
  v11 = v10;
  if ( v10 < 0 || v10 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    EapHost::EapException::Throw(v11, 0, 0);
  }
  v18 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 104LL))(v19, &v18);
  v13 = v12;
  if ( v12 < 0 || v12 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    if ( (v13 & 0x1FFF0000) == 0x70000 )
      v13 = (unsigned __int16)v13;
    EapHost::EapException::Throw(v13, 0, 0);
  }
  v25 = v9;
  v17 = 0;
  v16 = 0;
  v14 = v8(*(unsigned __int8 *)(a1 + 16), a2, v18, 0, 0, &v17, &v16);
  if ( v14 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v30, 0x800u, "RasEapCreateConnectionProperties failed %d", v14) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v30);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v14);
    v21 = *(_BYTE *)(a1 + 16);
    v22 = *(_QWORD *)(a1 + 20);
    if ( v21 != -2 )
      v22 = 0;
    v20 = &EapHost::EapMethodType::`vftable';
    v23 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v14, (const struct EapHost::EapMethodType *)&v20, v14);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    TempBuffer<0>::Assign(v24, v16, v17);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v25(v17);
      throw;
    }
  }
  v9(v17);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v30, 0x800u, "RasEapCreateConnectionProperties Exit:\n returning - bytes(%d)", v16) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v30);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v16);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v18);
  return ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v19);
}

```

## disassembly

```asm
0x1800182b0  push    rbx
0x1800182b2  push    rsi
0x1800182b3  push    rdi
0x1800182b4  push    r12
0x1800182b6  push    r13
0x1800182b8  push    r15
0x1800182ba  sub     rsp, 8C8h
0x1800182c1  mov     rax, cs:__security_cookie
0x1800182c8  xor     rax, rsp
0x1800182cb  mov     [rsp+8F8h+var_48], rax
0x1800182d3  mov     [rsp+8F8h+var_878], r9
0x1800182db  mov     rdi, r8
0x1800182de  mov     r15d, edx
0x1800182e1  mov     rbx, rcx
0x1800182e4  lea     rdx, DebugInfoEvent
0x1800182eb  mov     rcx, cs:eaphost_Context
0x1800182f2  call    cs:__imp_EtwEventEnabled
0x1800182f8  xor     esi, esi
0x1800182fa  test    al, al
0x1800182fc  jz      short loc_180018342
0x1800182fe  mov     r9d, r15d
0x180018301  lea     r8, aRaseapcreateco; "RasEapCreateConnectionProperties Entry:"...
0x180018308  mov     edx, 800h; unsigned __int64
0x18001830d  lea     rcx, [rsp+8F8h+var_848]; char *
0x180018315  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001831a  test    eax, eax
0x18001831c  js      short loc_180018342
0x18001831e  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180018325  jge     short loc_180018342
0x180018327  lea     r8, [rsp+8F8h+var_848]
0x18001832f  lea     rdx, DebugInfoEvent
0x180018336  lea     rcx, eaphost_Context
0x18001833d  call    McTemplateU0s_EtwEventWriteTransfer
0x180018342  lea     r13, WPP_GLOBAL_Control
0x180018349  mov     rcx, cs:WPP_GLOBAL_Control
0x180018350  cmp     rcx, r13
0x180018353  jz      short loc_180018373
0x180018355  test    byte ptr [rcx+1Ch], 4
0x180018359  jz      short loc_180018373
0x18001835b  mov     edx, 24h ; '$'
0x180018360  mov     r9d, r15d
0x180018363  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001836a  mov     rcx, [rcx+10h]
0x18001836e  call    WPP_SF_d
0x180018373  mov     dl, 1; bool
0x180018375  mov     rcx, [rbx+0B8h]; this
0x18001837c  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180018381  mov     rax, [rbx+0B8h]
0x180018388  mov     r12, [rax+0D8h]
0x18001838f  test    r12, r12
0x180018392  jnz     loc_180018427
0x180018398  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001839f  jz      short loc_1800183BB
0x1800183a1  lea     r8, aConfigxml2blob; "ConfigXml2Blob"
0x1800183a8  lea     rdx, PeerFunctionNotSupported
0x1800183af  lea     rcx, eaphost_Context
0x1800183b6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800183bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183c2  cmp     rcx, r13
0x1800183c5  jz      short loc_1800183E2
0x1800183c7  test    byte ptr [rcx+1Ch], 1
0x1800183cb  jz      short loc_1800183E2
0x1800183cd  mov     edx, 25h ; '%'
0x1800183d2  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800183d9  mov     rcx, [rcx+10h]
0x1800183dd  call    WPP_SF_
0x1800183e2  mov     cl, [rbx+10h]
0x1800183e5  mov     [rsp+8F8h+var_890], cl
0x1800183e9  mov     eax, [rbx+14h]
0x1800183ec  mov     dword ptr [rsp+8F8h+var_88C], eax
0x1800183f0  mov     eax, [rbx+18h]
0x1800183f3  mov     dword ptr [rsp+8F8h+var_88C+4], eax
0x1800183f7  cmp     cl, 0FEh
0x1800183fa  jz      short loc_180018401
0x1800183fc  mov     [rsp+8F8h+var_88C], rsi
0x180018401  lea     rsi, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180018408  mov     [rsp+8F8h+var_898], rsi
0x18001840d  mov     eax, [rbx+1Ch]
0x180018410  mov     [rsp+8F8h+var_880], eax
0x180018414  mov     ecx, 80420020h; unsigned int
0x180018419  mov     r8d, ecx; unsigned int
0x18001841c  lea     rdx, [rsp+8F8h+var_898]; struct EapHost::EapMethodType *
0x180018421  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180018427  mov     r13, [rax+0E8h]
0x18001842e  mov     [rsp+8F8h+var_8A0], rsi
0x180018433  mov     cl, [rbx+10h]
0x180018436  mov     [rsp+8F8h+var_860], cl
0x18001843d  mov     eax, [rbx+14h]
0x180018440  mov     dword ptr [rsp+8F8h+var_85C], eax
0x180018447  mov     eax, [rbx+18h]
0x18001844a  mov     dword ptr [rsp+8F8h+var_85C+4], eax
0x180018451  cmp     cl, 0FEh
0x180018454  jz      short loc_18001845E
0x180018456  mov     [rsp+8F8h+var_85C], rsi
0x18001845e  lea     rsi, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180018465  mov     [rsp+8F8h+var_868], rsi
0x18001846d  mov     eax, [rbx+1Ch]
0x180018470  mov     [rsp+8F8h+var_850], eax
0x180018477  mov     rax, [rdi]
0x18001847a  lea     rdx, [rsp+8F8h+var_8A0]
0x18001847f  mov     rcx, rdi
0x180018482  mov     rax, [rax+168h]
0x180018489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001848e  mov     edi, eax
0x180018490  test    eax, eax
0x180018492  js      loc_180018722
0x180018498  cmp     eax, 1
0x18001849b  jz      loc_180018722
0x1800184a1  mov     [rsp+8F8h+var_8A8], 0
0x1800184aa  mov     rcx, [rsp+8F8h+var_8A0]
0x1800184af  mov     rax, [rcx]
0x1800184b2  lea     rdx, [rsp+8F8h+var_8A8]
0x1800184b7  mov     rax, [rax+68h]
0x1800184bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184c0  mov     edi, eax
0x1800184c2  test    eax, eax
0x1800184c4  js      loc_1800186D6
0x1800184ca  cmp     eax, 1
0x1800184cd  jz      loc_1800186D6
0x1800184d3  mov     [rsp+8F8h+var_870], r13
0x1800184db  xor     edx, edx
0x1800184dd  mov     [rsp+8F8h+var_8B0], rdx
0x1800184e2  mov     [rsp+8F8h+var_8B8], edx
0x1800184e6  movzx   ecx, byte ptr [rbx+10h]
0x1800184ea  lea     rax, [rsp+8F8h+var_8B8]
0x1800184ef  mov     [rsp+8F8h+var_8C8], rax
0x1800184f4  lea     rax, [rsp+8F8h+var_8B0]
0x1800184f9  mov     [rsp+8F8h+var_8D0], rax
0x1800184fe  mov     [rsp+8F8h+var_8D8], edx
0x180018502  xor     r9d, r9d
0x180018505  mov     r8, [rsp+8F8h+var_8A8]
0x18001850a  mov     edx, r15d
0x18001850d  mov     rax, r12
0x180018510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018515  mov     edi, eax
0x180018517  xor     r15d, r15d
0x18001851a  test    eax, eax
0x18001851c  jz      loc_1800185EA
0x180018522  lea     rdx, DebugErrorEvent
0x180018529  mov     rcx, cs:eaphost_Context
0x180018530  call    cs:__imp_EtwEventEnabled
0x180018536  test    al, al
0x180018538  jz      short loc_18001857E
0x18001853a  mov     r9d, edi
0x18001853d  lea     r8, aRaseapcreateco_0; "RasEapCreateConnectionProperties failed"...
0x180018544  mov     edx, 800h; unsigned __int64
0x180018549  lea     rcx, [rsp+8F8h+var_848]; char *
0x180018551  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018556  test    eax, eax
0x180018558  js      short loc_18001857E
0x18001855a  test    cs:byte_18004AF81, 8
0x180018561  jz      short loc_18001857E
0x180018563  lea     r8, [rsp+8F8h+var_848]
0x18001856b  lea     rdx, DebugErrorEvent
0x180018572  lea     rcx, eaphost_Context
0x180018579  call    McTemplateU0s_EtwEventWriteTransfer
0x18001857e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018585  lea     rax, WPP_GLOBAL_Control
0x18001858c  cmp     rcx, rax
0x18001858f  jz      short loc_1800185AF
0x180018591  test    byte ptr [rcx+1Ch], 1
0x180018595  jz      short loc_1800185AF
0x180018597  mov     edx, 28h ; '('
0x18001859c  mov     r9d, edi
0x18001859f  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800185a6  mov     rcx, [rcx+10h]
0x1800185aa  call    WPP_SF_d
0x1800185af  mov     cl, [rbx+10h]
0x1800185b2  mov     [rsp+8F8h+var_890], cl
0x1800185b6  mov     eax, [rbx+14h]
0x1800185b9  mov     dword ptr [rsp+8F8h+var_88C], eax
0x1800185bd  mov     eax, [rbx+18h]
0x1800185c0  mov     dword ptr [rsp+8F8h+var_88C+4], eax
0x1800185c4  cmp     cl, 0FEh
0x1800185c7  jz      short loc_1800185CE
0x1800185c9  mov     [rsp+8F8h+var_88C], r15
0x1800185ce  mov     [rsp+8F8h+var_898], rsi
0x1800185d3  mov     eax, [rbx+1Ch]
0x1800185d6  mov     [rsp+8F8h+var_880], eax
0x1800185da  mov     r8d, edi; unsigned int
0x1800185dd  lea     rdx, [rsp+8F8h+var_898]; struct EapHost::EapMethodType *
0x1800185e2  mov     ecx, edi; unsigned int
0x1800185e4  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x1800185ea  mov     edx, [rsp+8F8h+var_8B8]
0x1800185ee  mov     r8, [rsp+8F8h+var_8B0]
0x1800185f3  mov     rcx, [rsp+8F8h+var_878]
0x1800185fb  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180018600  nop
0x180018601  mov     rcx, [rsp+8F8h+var_8B0]
0x180018606  mov     rax, r13
0x180018609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001860e  lea     rdx, DebugInfoEvent
0x180018615  mov     rcx, cs:eaphost_Context
0x18001861c  call    cs:__imp_EtwEventEnabled
0x180018622  test    al, al
0x180018624  jz      short loc_18001866C
0x180018626  mov     r9d, [rsp+8F8h+var_8B8]
0x18001862b  lea     r8, aRaseapcreateco_4; "RasEapCreateConnectionProperties Exit:"...
0x180018632  mov     edx, 800h; unsigned __int64
0x180018637  lea     rcx, [rsp+8F8h+var_848]; char *
0x18001863f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018644  test    eax, eax
0x180018646  js      short loc_18001866C
0x180018648  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18001864f  jge     short loc_18001866C
0x180018651  lea     r8, [rsp+8F8h+var_848]
0x180018659  lea     rdx, DebugInfoEvent
0x180018660  lea     rcx, eaphost_Context
0x180018667  call    McTemplateU0s_EtwEventWriteTransfer
0x18001866c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018673  lea     rax, WPP_GLOBAL_Control
0x18001867a  cmp     rcx, rax
0x18001867d  jz      short loc_1800186A0
0x18001867f  test    byte ptr [rcx+1Ch], 4
0x180018683  jz      short loc_1800186A0
0x180018685  mov     edx, 29h ; ')'
0x18001868a  mov     r9d, [rsp+8F8h+var_8B8]
0x18001868f  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018696  mov     rcx, [rcx+10h]
0x18001869a  call    WPP_SF_d
0x18001869f  nop
0x1800186a0  lea     rcx, [rsp+8F8h+var_8A8]
0x1800186a5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800186aa  nop
0x1800186ab  lea     rcx, [rsp+8F8h+var_8A0]
0x1800186b0  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800186b5  mov     rcx, [rsp+8F8h+var_48]
0x1800186bd  xor     rcx, rsp; StackCookie
0x1800186c0  call    __security_check_cookie
0x1800186c5  add     rsp, 8C8h
0x1800186cc  pop     r15
0x1800186ce  pop     r13
0x1800186d0  pop     r12
0x1800186d2  pop     rdi
0x1800186d3  pop     rsi
0x1800186d4  pop     rbx
0x1800186d5  retn
0x1800186d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186dd  lea     rax, WPP_GLOBAL_Control
0x1800186e4  cmp     rcx, rax
0x1800186e7  jz      short loc_180018704
0x1800186e9  test    byte ptr [rcx+1Ch], 1
0x1800186ed  jz      short loc_180018704
0x1800186ef  mov     edx, 27h ; '''
0x1800186f4  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800186fb  mov     rcx, [rcx+10h]
0x1800186ff  call    WPP_SF_
0x180018704  mov     eax, edi
0x180018706  and     eax, 1FFF0000h
0x18001870b  cmp     eax, 70000h
0x180018710  jnz     short loc_180018715
0x180018712  movzx   edi, di
0x180018715  xor     r8d, r8d; unsigned int
0x180018718  xor     edx, edx; struct EapHost::EapMethodType *
0x18001871a  mov     ecx, edi; unsigned int
0x18001871c  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180018722  mov     rcx, cs:WPP_GLOBAL_Control
0x180018729  lea     rax, WPP_GLOBAL_Control
0x180018730  cmp     rcx, rax
0x180018733  jz      short loc_180018750
0x180018735  test    byte ptr [rcx+1Ch], 1
0x180018739  jz      short loc_180018750
0x18001873b  mov     edx, 26h ; '&'
0x180018740  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018747  mov     rcx, [rcx+10h]
0x18001874b  call    WPP_SF_
0x180018750  mov     eax, edi
0x180018752  and     eax, 1FFF0000h
0x180018757  cmp     eax, 70000h
0x18001875c  jnz     short loc_180018761
0x18001875e  movzx   edi, di
0x180018761  xor     r8d, r8d; unsigned int
0x180018764  xor     edx, edx; struct EapHost::EapMethodType *
0x180018766  mov     ecx, edi; unsigned int
0x180018768  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```

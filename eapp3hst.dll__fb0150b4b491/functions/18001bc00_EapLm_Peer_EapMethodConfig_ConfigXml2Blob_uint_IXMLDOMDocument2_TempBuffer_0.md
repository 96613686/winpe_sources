# EapLm::Peer::EapMethodConfig::ConfigXml2Blob(uint,IXMLDOMDocument2 &,TempBuffer<0> &)

- ea: `0x18001bc00`
- end: `0x18001befc`
- name: `?ConfigXml2Blob@EapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `764`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001bc00`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001bc3c`
- `ntdll!EtwEventEnabled` at `0x18001be58`
- `ntdll!EtwEventEnabled` at `0x18001bc3c`
- `ntdll!EtwEventEnabled` at `0x18001be58`

## string_xrefs

- `0x18001bd00`: `ConfigXml2Blob`
- `0x18001be1e`: `EapPeerConfigXml2Blob`
- `0x18001bc49`: `EapPeerConfigXml2Blob Entry:\n flags(%d)`
- `0x18001be67`: `EapPeerConfigXml2Blob Exit:\n returning - bytes (%d)`

## pseudocode

```c
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::ConfigXml2Blob(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  _QWORD *v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _BYTE *, __int64, const void **, unsigned int *, struct _EAP_ERROR **); // r10
  void (__fastcall *v10)(const void *); // r15
  void (__fastcall *v11)(struct _EAP_ERROR *); // r14
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  _UNKNOWN **result; // rax
  unsigned int v15; // [rsp+40h] [rbp-8F8h] BYREF
  const void *v16; // [rsp+48h] [rbp-8F0h] BYREF
  struct _EAP_ERROR *v17; // [rsp+50h] [rbp-8E8h] BYREF
  _BYTE v18[20]; // [rsp+60h] [rbp-8D8h] BYREF
  int v19; // [rsp+78h] [rbp-8C0h]
  void (__fastcall *v20)(const void *); // [rsp+80h] [rbp-8B8h]
  char v21[96]; // [rsp+90h] [rbp-8A8h] BYREF
  char v22[2048]; // [rsp+F0h] [rbp-848h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "EapPeerConfigXml2Blob Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v22);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2);
  HeapAllocator::Free(*(void **)a4);
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 184), 1);
  v8 = *(_QWORD **)(a1 + 184);
  v9 = (__int64 (__fastcall *)(_QWORD, _BYTE *, __int64, const void **, unsigned int *, struct _EAP_ERROR **))v8[27];
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupported, "ConfigXml2Blob");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v18[8] = *(_BYTE *)(a1 + 16);
    *(_DWORD *)&v18[12] = *(_DWORD *)(a1 + 20);
    *(_DWORD *)&v18[16] = *(_DWORD *)(a1 + 24);
    if ( v18[8] != 0xFE )
      *(_QWORD *)&v18[12] = 0;
    *(_QWORD *)v18 = &EapHost::EapMethodType::`vftable';
    v19 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v18, 0x80420020);
  }
  v10 = (void (__fastcall *)(const void *))v8[29];
  v20 = v10;
  v11 = (void (__fastcall *)(struct _EAP_ERROR *))v8[28];
  v15 = 0;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)v18 = *(_OWORD *)(a1 + 16);
  v12 = v9(a2, v18, a3, &v16, &v15, &v17);
  if ( v12 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v21, v17, v12);
    v11(v17);
    EapHost::EapException::Throw(L"EapPeerConfigXml2Blob", v13, (const struct EapHost::EapError *)v21);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    TempBuffer<0>::Assign(a4, v15, v16);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v20(v16);
      throw;
    }
  }
  v10(v16);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "EapPeerConfigXml2Blob Exit:\n returning - bytes (%d)", v15) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v22);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          30,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids,
                          v15);
  return result;
}

```

## disassembly

```asm
0x18001bc00  push    rbx
0x18001bc02  push    rsi
0x18001bc03  push    rdi
0x18001bc04  push    r12
0x18001bc06  push    r14
0x18001bc08  push    r15
0x18001bc0a  sub     rsp, 908h
0x18001bc11  mov     rax, cs:__security_cookie
0x18001bc18  xor     rax, rsp
0x18001bc1b  mov     [rsp+938h+var_48], rax
0x18001bc23  mov     rdi, r9
0x18001bc26  mov     r12, r8
0x18001bc29  mov     esi, edx
0x18001bc2b  mov     rbx, rcx
0x18001bc2e  lea     rdx, DebugInfoEvent
0x18001bc35  mov     rcx, cs:eaphost_Context
0x18001bc3c  call    cs:__imp_EtwEventEnabled
0x18001bc42  test    al, al
0x18001bc44  jz      short loc_18001BC8A
0x18001bc46  mov     r9d, esi
0x18001bc49  lea     r8, aEappeerconfigx_1; "EapPeerConfigXml2Blob Entry:\n flags(%d"...
0x18001bc50  mov     edx, 800h; unsigned __int64
0x18001bc55  lea     rcx, [rsp+938h+var_848]; char *
0x18001bc5d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001bc62  test    eax, eax
0x18001bc64  js      short loc_18001BC8A
0x18001bc66  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001bc6d  jge     short loc_18001BC8A
0x18001bc6f  lea     r8, [rsp+938h+var_848]
0x18001bc77  lea     rdx, DebugInfoEvent
0x18001bc7e  lea     rcx, eaphost_Context
0x18001bc85  call    McTemplateU0s_EtwEventWriteTransfer
0x18001bc8a  lea     r14, WPP_GLOBAL_Control
0x18001bc91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc98  cmp     rcx, r14
0x18001bc9b  jz      short loc_18001BCBB
0x18001bc9d  test    byte ptr [rcx+1Ch], 4
0x18001bca1  jz      short loc_18001BCBB
0x18001bca3  mov     edx, 1Ch
0x18001bca8  mov     r9d, esi
0x18001bcab  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001bcb2  mov     rcx, [rcx+10h]
0x18001bcb6  call    WPP_SF_d
0x18001bcbb  mov     rcx, [rdi]; void *
0x18001bcbe  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001bcc3  mov     qword ptr [rdi], 0
0x18001bcca  mov     qword ptr [rdi+8], 0
0x18001bcd2  mov     dl, 1; bool
0x18001bcd4  mov     rcx, [rbx+0B8h]; this
0x18001bcdb  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001bce0  mov     rax, [rbx+0B8h]
0x18001bce7  mov     r10, [rax+0D8h]
0x18001bcee  test    r10, r10
0x18001bcf1  jnz     loc_18001BD8A
0x18001bcf7  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001bcfe  jz      short loc_18001BD1A
0x18001bd00  lea     r8, aConfigxml2blob; "ConfigXml2Blob"
0x18001bd07  lea     rdx, PeerFunctionNotSupported
0x18001bd0e  lea     rcx, eaphost_Context
0x18001bd15  call    McTemplateU0s_EtwEventWriteTransfer
0x18001bd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd21  cmp     rcx, r14
0x18001bd24  jz      short loc_18001BD41
0x18001bd26  test    byte ptr [rcx+1Ch], 1
0x18001bd2a  jz      short loc_18001BD41
0x18001bd2c  mov     edx, 1Dh
0x18001bd31  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001bd38  mov     rcx, [rcx+10h]
0x18001bd3c  call    WPP_SF_
0x18001bd41  mov     cl, [rbx+10h]
0x18001bd44  mov     byte ptr [rsp+938h+var_8D8+8], cl
0x18001bd48  mov     eax, [rbx+14h]
0x18001bd4b  mov     dword ptr [rsp+938h+var_8D8+0Ch], eax
0x18001bd4f  mov     eax, [rbx+18h]
0x18001bd52  mov     [rsp+70h], eax
0x18001bd56  cmp     cl, 0FEh
0x18001bd59  jz      short loc_18001BD64
0x18001bd5b  mov     qword ptr [rsp+938h+var_8D8+0Ch], 0
0x18001bd64  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001bd6b  mov     qword ptr [rsp+938h+var_8D8], rax
0x18001bd70  mov     eax, [rbx+1Ch]
0x18001bd73  mov     [rsp+938h+var_8C0], eax
0x18001bd77  mov     ecx, 80420020h; unsigned int
0x18001bd7c  mov     r8d, ecx; unsigned int
0x18001bd7f  lea     rdx, [rsp+938h+var_8D8]; struct EapHost::EapMethodType *
0x18001bd84  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001bd8a  mov     r15, [rax+0E8h]
0x18001bd91  mov     [rsp+938h+var_8B8], r15
0x18001bd99  mov     r14, [rax+0E0h]
0x18001bda0  mov     [rsp+938h+var_8F8], 0
0x18001bda8  mov     [rsp+938h+var_8F0], 0
0x18001bdb1  mov     [rsp+938h+var_8E8], 0
0x18001bdba  movups  xmm0, xmmword ptr [rbx+10h]
0x18001bdbe  movdqu  [rsp+938h+var_8D8], xmm0
0x18001bdc4  lea     rax, [rsp+938h+var_8E8]
0x18001bdc9  mov     [rsp+938h+var_910], rax
0x18001bdce  lea     rax, [rsp+938h+var_8F8]
0x18001bdd3  mov     [rsp+938h+var_918], rax
0x18001bdd8  lea     r9, [rsp+938h+var_8F0]
0x18001bddd  mov     r8, r12
0x18001bde0  lea     rdx, [rsp+938h+var_8D8]
0x18001bde5  mov     ecx, esi
0x18001bde7  mov     rax, r10
0x18001bdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdef  test    eax, eax
0x18001bdf1  jz      short loc_18001BE2B
0x18001bdf3  mov     r8d, eax; unsigned int
0x18001bdf6  mov     rdx, [rsp+938h+var_8E8]; struct _EAP_ERROR *
0x18001bdfb  lea     rcx, [rsp+938h+var_8A8]; this
0x18001be03  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001be08  nop
0x18001be09  mov     rcx, [rsp+938h+var_8E8]
0x18001be0e  mov     rax, r14
0x18001be11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be16  lea     r8, [rsp+938h+var_8A8]; struct EapHost::EapError *
0x18001be1e  lea     rcx, aEappeerconfigx_0; "EapPeerConfigXml2Blob"
0x18001be25  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001be2b  mov     edx, [rsp+938h+var_8F8]
0x18001be2f  mov     r8, [rsp+938h+var_8F0]
0x18001be34  mov     rcx, rdi
0x18001be37  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001be3c  nop
0x18001be3d  mov     rcx, [rsp+938h+var_8F0]
0x18001be42  mov     rax, r15
0x18001be45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4a  lea     rdx, DebugInfoEvent
0x18001be51  mov     rcx, cs:eaphost_Context
0x18001be58  call    cs:__imp_EtwEventEnabled
0x18001be5e  test    al, al
0x18001be60  jz      short loc_18001BEA8
0x18001be62  mov     r9d, [rsp+938h+var_8F8]
0x18001be67  lea     r8, aEappeerconfigx; "EapPeerConfigXml2Blob Exit:\n returning"...
0x18001be6e  mov     edx, 800h; unsigned __int64
0x18001be73  lea     rcx, [rsp+938h+var_848]; char *
0x18001be7b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001be80  test    eax, eax
0x18001be82  js      short loc_18001BEA8
0x18001be84  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001be8b  jge     short loc_18001BEA8
0x18001be8d  lea     r8, [rsp+938h+var_848]
0x18001be95  lea     rdx, DebugInfoEvent
0x18001be9c  lea     rcx, eaphost_Context
0x18001bea3  call    McTemplateU0s_EtwEventWriteTransfer
0x18001bea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beaf  lea     rax, WPP_GLOBAL_Control
0x18001beb6  cmp     rcx, rax
0x18001beb9  jz      short loc_18001BEDB
0x18001bebb  test    byte ptr [rcx+1Ch], 4
0x18001bebf  jz      short loc_18001BEDB
0x18001bec1  mov     edx, 1Eh
0x18001bec6  mov     r9d, [rsp+938h+var_8F8]
0x18001becb  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001bed2  mov     rcx, [rcx+10h]
0x18001bed6  call    WPP_SF_d
0x18001bedb  mov     rcx, [rsp+938h+var_48]
0x18001bee3  xor     rcx, rsp; StackCookie
0x18001bee6  call    __security_check_cookie
0x18001beeb  add     rsp, 908h
0x18001bef2  pop     r15
0x18001bef4  pop     r14
0x18001bef6  pop     r12
0x18001bef8  pop     rdi
0x18001bef9  pop     rsi
0x18001befa  pop     rbx
0x18001befb  retn
```

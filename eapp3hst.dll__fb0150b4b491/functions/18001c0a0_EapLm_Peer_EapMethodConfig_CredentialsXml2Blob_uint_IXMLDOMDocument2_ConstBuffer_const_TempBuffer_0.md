# EapLm::Peer::EapMethodConfig::CredentialsXml2Blob(uint,IXMLDOMDocument2 &,ConstBuffer const &,TempBuffer<0> &)

- ea: `0x18001c0a0`
- end: `0x18001c3bb`
- name: `?CredentialsXml2Blob@EapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEBUConstBuffer@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `795`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001c0a0`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001c0eb`
- `ntdll!EtwEventEnabled` at `0x18001c315`
- `ntdll!EtwEventEnabled` at `0x18001c0eb`
- `ntdll!EtwEventEnabled` at `0x18001c315`

## string_xrefs

- `0x18001c0fb`: `EapPeerCredentialsXml2Blob Entry:\n flags(%d)`
- `0x18001c1aa`: `CredentialsXml2Blob`
- `0x18001c2db`: `EapPeerCredentialXml2Blob`
- `0x18001c324`: `EapPeerCredentialsXml2Blob Exit:\n returning - bytes (%d)`

## pseudocode

```c
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::CredentialsXml2Blob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5)
{
  _QWORD *v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _BYTE *, __int64, _QWORD, int, const void **, unsigned int *, struct _EAP_ERROR **); // r14
  void (__fastcall *v10)(const void *); // r12
  void (__fastcall *v11)(struct _EAP_ERROR *); // r15
  int v12; // eax
  unsigned int v13; // eax
  const wchar_t *v14; // rdx
  _UNKNOWN **result; // rax
  unsigned int v16; // [rsp+50h] [rbp-8F8h] BYREF
  const void *v17; // [rsp+58h] [rbp-8F0h] BYREF
  struct _EAP_ERROR *v18; // [rsp+60h] [rbp-8E8h] BYREF
  _BYTE v19[20]; // [rsp+70h] [rbp-8D8h] BYREF
  int v20; // [rsp+88h] [rbp-8C0h]
  __int64 v21; // [rsp+90h] [rbp-8B8h]
  void (__fastcall *v22)(const void *); // [rsp+98h] [rbp-8B0h]
  char v23[96]; // [rsp+A0h] [rbp-8A8h] BYREF
  char v24[2048]; // [rsp+100h] [rbp-848h] BYREF

  v21 = a3;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v24, 0x800u, "EapPeerCredentialsXml2Blob Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v24);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2);
  HeapAllocator::Free(*(void **)a5);
  *(_QWORD *)a5 = 0;
  *(_QWORD *)(a5 + 8) = 0;
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 192), 1);
  v8 = *(_QWORD **)(a1 + 192);
  v9 = (__int64 (__fastcall *)(_QWORD, _BYTE *, __int64, _QWORD, int, const void **, unsigned int *, struct _EAP_ERROR **))v8[27];
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupported, "CredentialsXml2Blob");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v19[8] = *(_BYTE *)(a1 + 16);
    *(_DWORD *)&v19[12] = *(_DWORD *)(a1 + 20);
    *(_DWORD *)&v19[16] = *(_DWORD *)(a1 + 24);
    if ( v19[8] != 0xFE )
      *(_QWORD *)&v19[12] = 0;
    *(_QWORD *)v19 = &EapHost::EapMethodType::`vftable';
    v20 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v19, 0x80420020);
  }
  v10 = (void (__fastcall *)(const void *))v8[29];
  v22 = v10;
  v11 = (void (__fastcall *)(struct _EAP_ERROR *))v8[28];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  *(_OWORD *)v19 = *(_OWORD *)(a1 + 16);
  v13 = v9(a2, v19, v21, *a4, v12, &v17, &v16, &v18);
  if ( v13 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v23, v18, v13);
    v11(v18);
    EapHost::EapException::Throw(L"EapPeerCredentialXml2Blob", v14, (const struct EapHost::EapError *)v23);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    TempBuffer<0>::Assign(a5, v16, v17);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v22(v17);
      throw;
    }
  }
  v10(v17);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v24, 0x800u, "EapPeerCredentialsXml2Blob Exit:\n returning - bytes (%d)", v16) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v24);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          33,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids,
                          v16);
  return result;
}

```

## disassembly

```asm
0x18001c0a0  push    rbx
0x18001c0a2  push    rsi
0x18001c0a3  push    rdi
0x18001c0a4  push    r12
0x18001c0a6  push    r13
0x18001c0a8  push    r14
0x18001c0aa  push    r15
0x18001c0ac  sub     rsp, 910h
0x18001c0b3  mov     rax, cs:__security_cookie
0x18001c0ba  xor     rax, rsp
0x18001c0bd  mov     [rsp+948h+var_48], rax
0x18001c0c5  mov     r13, r9
0x18001c0c8  mov     [rsp+948h+var_8B8], r8
0x18001c0d0  mov     esi, edx
0x18001c0d2  mov     rbx, rcx
0x18001c0d5  mov     rdi, [rsp+948h+arg_20]
0x18001c0dd  lea     rdx, DebugInfoEvent
0x18001c0e4  mov     rcx, cs:eaphost_Context
0x18001c0eb  call    cs:__imp_EtwEventEnabled
0x18001c0f1  xor     r15d, r15d
0x18001c0f4  test    al, al
0x18001c0f6  jz      short loc_18001C13C
0x18001c0f8  mov     r9d, esi
0x18001c0fb  lea     r8, aEappeercredent_0; "EapPeerCredentialsXml2Blob Entry:\n fla"...
0x18001c102  mov     edx, 800h; unsigned __int64
0x18001c107  lea     rcx, [rsp+948h+var_848]; char *
0x18001c10f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001c114  test    eax, eax
0x18001c116  js      short loc_18001C13C
0x18001c118  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18001c11f  jge     short loc_18001C13C
0x18001c121  lea     r8, [rsp+948h+var_848]
0x18001c129  lea     rdx, DebugInfoEvent
0x18001c130  lea     rcx, eaphost_Context
0x18001c137  call    McTemplateU0s_EtwEventWriteTransfer
0x18001c13c  lea     r12, WPP_GLOBAL_Control
0x18001c143  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c14a  cmp     rcx, r12
0x18001c14d  jz      short loc_18001C16D
0x18001c14f  test    byte ptr [rcx+1Ch], 4
0x18001c153  jz      short loc_18001C16D
0x18001c155  mov     edx, 1Fh
0x18001c15a  mov     r9d, esi
0x18001c15d  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001c164  mov     rcx, [rcx+10h]
0x18001c168  call    WPP_SF_d
0x18001c16d  mov     rcx, [rdi]; void *
0x18001c170  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001c175  mov     [rdi], r15
0x18001c178  mov     [rdi+8], r15
0x18001c17c  mov     dl, 1; bool
0x18001c17e  mov     rcx, [rbx+0C0h]; this
0x18001c185  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001c18a  mov     rax, [rbx+0C0h]
0x18001c191  mov     r14, [rax+0D8h]
0x18001c198  test    r14, r14
0x18001c19b  jnz     loc_18001C236
0x18001c1a1  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001c1a8  jz      short loc_18001C1C4
0x18001c1aa  lea     r8, aCredentialsxml; "CredentialsXml2Blob"
0x18001c1b1  lea     rdx, PeerFunctionNotSupported
0x18001c1b8  lea     rcx, eaphost_Context
0x18001c1bf  call    McTemplateU0s_EtwEventWriteTransfer
0x18001c1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1cb  cmp     rcx, r12
0x18001c1ce  jz      short loc_18001C1EB
0x18001c1d0  test    byte ptr [rcx+1Ch], 1
0x18001c1d4  jz      short loc_18001C1EB
0x18001c1d6  mov     edx, 20h ; ' '
0x18001c1db  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001c1e2  mov     rcx, [rcx+10h]
0x18001c1e6  call    WPP_SF_
0x18001c1eb  mov     cl, [rbx+10h]
0x18001c1ee  mov     byte ptr [rsp+948h+var_8D8+8], cl
0x18001c1f2  mov     eax, [rbx+14h]
0x18001c1f5  mov     dword ptr [rsp+948h+var_8D8+0Ch], eax
0x18001c1f9  mov     eax, [rbx+18h]
0x18001c1fc  mov     [rsp+80h], eax
0x18001c203  cmp     cl, 0FEh
0x18001c206  jz      short loc_18001C20D
0x18001c208  mov     qword ptr [rsp+948h+var_8D8+0Ch], r15
0x18001c20d  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001c214  mov     qword ptr [rsp+948h+var_8D8], rax
0x18001c219  mov     eax, [rbx+1Ch]
0x18001c21c  mov     [rsp+948h+var_8C0], eax
0x18001c223  mov     ecx, 80420020h; unsigned int
0x18001c228  mov     r8d, ecx; unsigned int
0x18001c22b  lea     rdx, [rsp+948h+var_8D8]; struct EapHost::EapMethodType *
0x18001c230  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001c236  mov     r12, [rax+0E8h]
0x18001c23d  mov     [rsp+948h+var_8B0], r12
0x18001c245  mov     r15, [rax+0E0h]
0x18001c24c  xor     eax, eax
0x18001c24e  mov     [rsp+948h+var_8F8], eax
0x18001c252  mov     [rsp+948h+var_8F0], rax
0x18001c257  mov     [rsp+948h+var_8E8], rax
0x18001c25c  mov     rcx, [r13+8]
0x18001c260  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001c265  movups  xmm0, xmmword ptr [rbx+10h]
0x18001c269  movdqu  [rsp+948h+var_8D8], xmm0
0x18001c26f  lea     rcx, [rsp+948h+var_8E8]
0x18001c274  mov     [rsp+948h+var_910], rcx
0x18001c279  lea     rcx, [rsp+948h+var_8F8]
0x18001c27e  mov     [rsp+948h+var_918], rcx
0x18001c283  lea     rcx, [rsp+948h+var_8F0]
0x18001c288  mov     [rsp+948h+var_920], rcx
0x18001c28d  mov     [rsp+948h+var_928], eax
0x18001c291  mov     r9, [r13+0]
0x18001c295  mov     r8, [rsp+948h+var_8B8]
0x18001c29d  lea     rdx, [rsp+948h+var_8D8]
0x18001c2a2  mov     ecx, esi
0x18001c2a4  mov     rax, r14
0x18001c2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ac  test    eax, eax
0x18001c2ae  jz      short loc_18001C2E8
0x18001c2b0  mov     r8d, eax; unsigned int
0x18001c2b3  mov     rdx, [rsp+948h+var_8E8]; struct _EAP_ERROR *
0x18001c2b8  lea     rcx, [rsp+948h+var_8A8]; this
0x18001c2c0  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001c2c5  nop
0x18001c2c6  mov     rcx, [rsp+948h+var_8E8]
0x18001c2cb  mov     rax, r15
0x18001c2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d3  lea     r8, [rsp+948h+var_8A8]; struct EapHost::EapError *
0x18001c2db  lea     rcx, aEappeercredent_1; "EapPeerCredentialXml2Blob"
0x18001c2e2  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001c2e8  mov     edx, [rsp+948h+var_8F8]
0x18001c2ec  mov     r8, [rsp+948h+var_8F0]
0x18001c2f1  mov     rcx, rdi
0x18001c2f4  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001c2f9  nop
0x18001c2fa  mov     rcx, [rsp+948h+var_8F0]
0x18001c2ff  mov     rax, r12
0x18001c302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c307  lea     rdx, DebugInfoEvent
0x18001c30e  mov     rcx, cs:eaphost_Context
0x18001c315  call    cs:__imp_EtwEventEnabled
0x18001c31b  test    al, al
0x18001c31d  jz      short loc_18001C365
0x18001c31f  mov     r9d, [rsp+948h+var_8F8]
0x18001c324  lea     r8, aEappeercredent; "EapPeerCredentialsXml2Blob Exit:\n retu"...
0x18001c32b  mov     edx, 800h; unsigned __int64
0x18001c330  lea     rcx, [rsp+948h+var_848]; char *
0x18001c338  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001c33d  test    eax, eax
0x18001c33f  js      short loc_18001C365
0x18001c341  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001c348  jge     short loc_18001C365
0x18001c34a  lea     r8, [rsp+948h+var_848]
0x18001c352  lea     rdx, DebugInfoEvent
0x18001c359  lea     rcx, eaphost_Context
0x18001c360  call    McTemplateU0s_EtwEventWriteTransfer
0x18001c365  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c36c  lea     rax, WPP_GLOBAL_Control
0x18001c373  cmp     rcx, rax
0x18001c376  jz      short loc_18001C398
0x18001c378  test    byte ptr [rcx+1Ch], 4
0x18001c37c  jz      short loc_18001C398
0x18001c37e  mov     edx, 21h ; '!'
0x18001c383  mov     r9d, [rsp+948h+var_8F8]
0x18001c388  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001c38f  mov     rcx, [rcx+10h]
0x18001c393  call    WPP_SF_d
0x18001c398  mov     rcx, [rsp+948h+var_48]
0x18001c3a0  xor     rcx, rsp; StackCookie
0x18001c3a3  call    __security_check_cookie
0x18001c3a8  add     rsp, 910h
0x18001c3af  pop     r15
0x18001c3b1  pop     r14
0x18001c3b3  pop     r13
0x18001c3b5  pop     r12
0x18001c3b7  pop     rdi
0x18001c3b8  pop     rsi
0x18001c3b9  pop     rbx
0x18001c3ba  retn
```

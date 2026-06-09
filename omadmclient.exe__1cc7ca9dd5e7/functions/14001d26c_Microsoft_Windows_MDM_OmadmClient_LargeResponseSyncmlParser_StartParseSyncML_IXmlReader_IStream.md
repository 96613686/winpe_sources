# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::StartParseSyncML(IXmlReader *,IStream *)

- ea: `0x14001d26c`
- end: `0x14001d5a9`
- name: `?StartParseSyncML@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIXmlReader@@PEAUIStream@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, struct IXmlReader *, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019f78`

## callees

- `0x14000b0f4`
- `0x14001cff0`
- `0x14001d26c`
- `0x140069010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14001d316`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14001d316`
- `XmlLite!CreateXmlWriter` at `0x14001d2a8`
- `XmlLite!CreateXmlWriter` at `0x14001d2a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::StartParseSyncML(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this,
        struct IXmlReader *a2,
        IUnknown *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // edi
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-20h]
  IXmlWriterOutput *ppOutput; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *ppvObject; // [rsp+78h] [rbp+38h] BYREF

  ppvObject = 0;
  ppOutput = 0;
  v6 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v6,
      v16);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v9 = CreateXmlWriterOutputWithEncodingName(a3, 0, L"UTF-8", &ppOutput);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v9,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v10 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v10,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v11 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v11,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v12 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseSyncBodyElement(
          this,
          a2,
          (struct IStream *)a3);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v12,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v13 = ((__int64 (__fastcall *)(IUnknown *, const char *, __int64))a3->lpVtbl[1].AddRef)(a3, "</SyncML>", 10);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CB,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v13,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v7;
  }
  v14 = ((__int64 (__fastcall *)(IUnknown *, _QWORD))a3->lpVtbl[2].Release)(a3, 0);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v14,
      v16);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return v15;
  }
}

```

## disassembly

```asm
0x14001d26c  mov     [rsp-18h+arg_0], rbx
0x14001d271  mov     [rsp-18h+arg_8], rsi
0x14001d276  push    rbp
0x14001d277  push    rdi
0x14001d278  push    r14
0x14001d27a  mov     rbp, rsp
0x14001d27d  sub     rsp, 40h
0x14001d281  mov     rbx, r8
0x14001d284  mov     rsi, rdx
0x14001d287  mov     r14, rcx
0x14001d28a  mov     [rbp+ppvObject], 0
0x14001d292  mov     [rbp+ppOutput], 0
0x14001d29a  xor     r8d, r8d; pMalloc
0x14001d29d  lea     rdx, [rbp+ppvObject]; ppvObject
0x14001d2a1  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x14001d2a8  call    cs:__imp_CreateXmlWriter
0x14001d2af  nop     dword ptr [rax+rax+00h]
0x14001d2b4  mov     edi, eax
0x14001d2b6  test    eax, eax
0x14001d2b8  jns     short loc_14001D306
0x14001d2ba  mov     rcx, [rbp+18h]; this
0x14001d2be  mov     r9d, eax; char *
0x14001d2c1  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d2c8  mov     edx, 2B4h; void *
0x14001d2cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d2d2  nop
0x14001d2d3  mov     rcx, [rbp+ppOutput]
0x14001d2d7  test    rcx, rcx
0x14001d2da  jz      short loc_14001D2E9
0x14001d2dc  mov     rax, [rcx]
0x14001d2df  mov     rax, [rax+10h]
0x14001d2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d2e8  nop
0x14001d2e9  mov     rcx, [rbp+ppvObject]
0x14001d2ed  test    rcx, rcx
0x14001d2f0  jz      short loc_14001D2FF
0x14001d2f2  mov     rax, [rcx]
0x14001d2f5  mov     rax, [rax+10h]
0x14001d2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d2fe  nop
0x14001d2ff  mov     eax, edi
0x14001d301  jmp     loc_14001D595
0x14001d306  lea     r9, [rbp+ppOutput]; ppOutput
0x14001d30a  lea     r8, aUtf8_0; "UTF-8"
0x14001d311  xor     edx, edx; pMalloc
0x14001d313  mov     rcx, rbx; pOutputStream
0x14001d316  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x14001d31d  nop     dword ptr [rax+rax+00h]
0x14001d322  mov     edi, eax
0x14001d324  test    eax, eax
0x14001d326  jns     short loc_14001D36F
0x14001d328  mov     rcx, [rbp+18h]; this
0x14001d32c  mov     r9d, eax; char *
0x14001d32f  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d336  mov     edx, 2BBh; void *
0x14001d33b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d340  nop
0x14001d341  mov     rcx, [rbp+ppOutput]
0x14001d345  test    rcx, rcx
0x14001d348  jz      short loc_14001D357
0x14001d34a  mov     rax, [rcx]
0x14001d34d  mov     rax, [rax+10h]
0x14001d351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d356  nop
0x14001d357  mov     rcx, [rbp+ppvObject]
0x14001d35b  test    rcx, rcx
0x14001d35e  jz      short loc_14001D36D
0x14001d360  mov     rax, [rcx]
0x14001d363  mov     rax, [rax+10h]
0x14001d367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d36c  nop
0x14001d36d  jmp     short loc_14001D2FF
0x14001d36f  mov     rcx, [rbp+ppvObject]
0x14001d373  mov     rax, [rcx]
0x14001d376  mov     rdx, [rbp+ppOutput]
0x14001d37a  mov     rax, [rax+18h]
0x14001d37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d383  mov     edi, eax
0x14001d385  test    eax, eax
0x14001d387  jns     short loc_14001D3D3
0x14001d389  mov     rcx, [rbp+18h]; this
0x14001d38d  mov     r9d, eax; char *
0x14001d390  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d397  mov     edx, 2BEh; void *
0x14001d39c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d3a1  nop
0x14001d3a2  mov     rcx, [rbp+ppOutput]
0x14001d3a6  test    rcx, rcx
0x14001d3a9  jz      short loc_14001D3B8
0x14001d3ab  mov     rax, [rcx]
0x14001d3ae  mov     rax, [rax+10h]
0x14001d3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d3b7  nop
0x14001d3b8  mov     rcx, [rbp+ppvObject]
0x14001d3bc  test    rcx, rcx
0x14001d3bf  jz      short loc_14001D3CE
0x14001d3c1  mov     rax, [rcx]
0x14001d3c4  mov     rax, [rax+10h]
0x14001d3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d3cd  nop
0x14001d3ce  jmp     loc_14001D2FF
0x14001d3d3  mov     rcx, [rbp+ppvObject]
0x14001d3d7  mov     rax, [rcx]
0x14001d3da  mov     edx, 4
0x14001d3df  lea     r8d, [rdx-3]
0x14001d3e3  mov     rax, [rax+28h]
0x14001d3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d3ec  mov     edi, eax
0x14001d3ee  test    eax, eax
0x14001d3f0  jns     short loc_14001D43C
0x14001d3f2  mov     rcx, [rbp+18h]; this
0x14001d3f6  mov     r9d, eax; char *
0x14001d3f9  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d400  mov     edx, 2C3h; void *
0x14001d405  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d40a  nop
0x14001d40b  mov     rcx, [rbp+ppOutput]
0x14001d40f  test    rcx, rcx
0x14001d412  jz      short loc_14001D421
0x14001d414  mov     rax, [rcx]
0x14001d417  mov     rax, [rax+10h]
0x14001d41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d420  nop
0x14001d421  mov     rcx, [rbp+ppvObject]
0x14001d425  test    rcx, rcx
0x14001d428  jz      short loc_14001D437
0x14001d42a  mov     rax, [rcx]
0x14001d42d  mov     rax, [rax+10h]
0x14001d431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d436  nop
0x14001d437  jmp     loc_14001D2FF
0x14001d43c  mov     r8, rbx; struct IStream *
0x14001d43f  mov     rdx, rsi; struct IXmlReader *
0x14001d442  mov     rcx, r14; this
0x14001d445  call    ?ParseSyncBodyElement@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIXmlReader@@PEAUIStream@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseSyncBodyElement(IXmlReader *,IStream *)
0x14001d44a  mov     edi, eax
0x14001d44c  test    eax, eax
0x14001d44e  jns     short loc_14001D49A
0x14001d450  mov     rcx, [rbp+18h]; this
0x14001d454  mov     r9d, eax; char *
0x14001d457  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d45e  mov     edx, 2C7h; void *
0x14001d463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d468  nop
0x14001d469  mov     rcx, [rbp+ppOutput]
0x14001d46d  test    rcx, rcx
0x14001d470  jz      short loc_14001D47F
0x14001d472  mov     rax, [rcx]
0x14001d475  mov     rax, [rax+10h]
0x14001d479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d47e  nop
0x14001d47f  mov     rcx, [rbp+ppvObject]
0x14001d483  test    rcx, rcx
0x14001d486  jz      short loc_14001D495
0x14001d488  mov     rax, [rcx]
0x14001d48b  mov     rax, [rax+10h]
0x14001d48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d494  nop
0x14001d495  jmp     loc_14001D2FF
0x14001d49a  mov     rax, [rbx]
0x14001d49d  xor     r9d, r9d
0x14001d4a0  lea     r8d, [r9+0Ah]
0x14001d4a4  lea     rdx, aSyncml_0; "</SyncML>"
0x14001d4ab  mov     rcx, rbx
0x14001d4ae  mov     rax, [rax+20h]
0x14001d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d4b7  mov     edi, eax
0x14001d4b9  test    eax, eax
0x14001d4bb  jns     short loc_14001D507
0x14001d4bd  mov     rcx, [rbp+18h]; this
0x14001d4c1  mov     r9d, eax; char *
0x14001d4c4  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d4cb  mov     edx, 2CBh; void *
0x14001d4d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d4d5  nop
0x14001d4d6  mov     rcx, [rbp+ppOutput]
0x14001d4da  test    rcx, rcx
0x14001d4dd  jz      short loc_14001D4EC
0x14001d4df  mov     rax, [rcx]
0x14001d4e2  mov     rax, [rax+10h]
0x14001d4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d4eb  nop
0x14001d4ec  mov     rcx, [rbp+ppvObject]
0x14001d4f0  test    rcx, rcx
0x14001d4f3  jz      short loc_14001D502
0x14001d4f5  mov     rax, [rcx]
0x14001d4f8  mov     rax, [rax+10h]
0x14001d4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d501  nop
0x14001d502  jmp     loc_14001D2FF
0x14001d507  mov     rax, [rbx]
0x14001d50a  xor     edx, edx
0x14001d50c  mov     rcx, rbx
0x14001d50f  mov     rax, [rax+40h]
0x14001d513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d518  mov     ebx, eax
0x14001d51a  test    eax, eax
0x14001d51c  jns     short loc_14001D567
0x14001d51e  mov     rcx, [rbp+18h]; this
0x14001d522  mov     r9d, eax; char *
0x14001d525  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001d52c  mov     edx, 2CEh; void *
0x14001d531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d536  nop
0x14001d537  mov     rcx, [rbp+ppOutput]
0x14001d53b  test    rcx, rcx
0x14001d53e  jz      short loc_14001D54D
0x14001d540  mov     rax, [rcx]
0x14001d543  mov     rax, [rax+10h]
0x14001d547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d54c  nop
0x14001d54d  mov     rcx, [rbp+ppvObject]
0x14001d551  test    rcx, rcx
0x14001d554  jz      short loc_14001D563
0x14001d556  mov     rax, [rcx]
0x14001d559  mov     rax, [rax+10h]
0x14001d55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d562  nop
0x14001d563  mov     eax, ebx
0x14001d565  jmp     short loc_14001D595
0x14001d567  mov     rcx, [rbp+ppOutput]
0x14001d56b  test    rcx, rcx
0x14001d56e  jz      short loc_14001D57D
0x14001d570  mov     rax, [rcx]
0x14001d573  mov     rax, [rax+10h]
0x14001d577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d57c  nop
0x14001d57d  mov     rcx, [rbp+ppvObject]
0x14001d581  test    rcx, rcx
0x14001d584  jz      short loc_14001D593
0x14001d586  mov     rax, [rcx]
0x14001d589  mov     rax, [rax+10h]
0x14001d58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d592  nop
0x14001d593  xor     eax, eax
0x14001d595  mov     rbx, [rsp+40h+arg_0]
0x14001d59a  mov     rsi, [rsp+40h+arg_8]
0x14001d59f  add     rsp, 40h
0x14001d5a3  pop     r14
0x14001d5a5  pop     rdi
0x14001d5a6  pop     rbp
0x14001d5a7  retn
```

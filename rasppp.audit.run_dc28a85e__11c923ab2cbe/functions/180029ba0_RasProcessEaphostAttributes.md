# RasProcessEaphostAttributes

- ea: `0x180029ba0`
- end: `0x180029fb0`
- name: `RasProcessEaphostAttributes`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180028964`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180028964`
- `0x180028c68`
- `0x180029094`
- `0x180029ba0`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e80`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029c93`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029e24`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029c93`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029e24`
- `eappprxy!EapHostPeerGetResponseAttributes` at `0x180029c6f`
- `eappprxy!EapHostPeerGetResponseAttributes` at `0x180029c6f`
- `eappprxy!EapHostPeerSetResponseAttributes` at `0x180029e00`
- `eappprxy!EapHostPeerSetResponseAttributes` at `0x180029e00`

## string_xrefs

- `0x180029dcb`: `RasCreateEapAttributesWithResultTLV failed.`

## pseudocode

```c
__int64 __fastcall RasProcessEaphostAttributes(__int64 a1, int a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  __int64 v6; // r14
  unsigned int ResponseAttributes; // ebx
  __int64 v10; // rdx
  DWORD i; // ebx
  BYTE *pValue; // rdi
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  EAP_ATTRIBUTE *v15; // rsi
  DWORD dwNumberOfAttributes; // eax
  DWORD v17; // edi
  BYTE *v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rdx
  EAP_ERROR *ppEapError; // [rsp+40h] [rbp-C0h] BYREF
  EapHostPeerResponseAction pEapOutput; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+4Ch] [rbp-B4h]
  EapAttributes v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  EapAttributes pAttribs; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v6 = a3;
  v26 = a3;
  v27 = a5;
  v29 = 0;
  v24 = a4;
  memset_0(v30, 0, sizeof(v30));
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"RasProcessEaphostAttributes -- Entering.");
  ppEapError = 0;
  pEapOutput = EapHostPeerResponseNone;
  pAttribs = 0;
  v25 = 0;
  if ( !a1 || !a6 )
  {
    ResponseAttributes = 87;
    goto LABEL_40;
  }
  ResponseAttributes = EapHostPeerGetResponseAttributes(*(_DWORD *)(a1 + 484), &pAttribs, &ppEapError);
  PrintEapError("EapHostPeerGetResponseAttributes", ppEapError);
  EapHostPeerFreeEapError(ppEapError);
  if ( ResponseAttributes )
    goto LABEL_40;
  v10 = *((_QWORD *)&xmmword_18004D740 + 1);
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"Checking attributes for statusTLV");
    v10 = *((_QWORD *)&xmmword_18004D740 + 1);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= pAttribs.dwNumberOfAttributes )
      goto LABEL_24;
    if ( pAttribs.pAttribs[i].eaType != eatEAPTLV )
    {
      if ( v10 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"Ignoring attribute type %d", (unsigned int)pAttribs.pAttribs[i].eaType);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_18004D740 + 1),
          &v29);
        v10 = *((_QWORD *)&xmmword_18004D740 + 1);
      }
      continue;
    }
    pValue = pAttribs.pAttribs[i].pValue;
    if ( pValue )
    {
      if ( (*pValue & 0x80u) != 0 && pValue[1] == 3 )
        break;
    }
  }
  if ( v10 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v10,
      L"Found statusTLV attribute");
    if ( *((_QWORD *)&xmmword_18004D740 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        *((_QWORD *)&xmmword_18004D740 + 1),
        L"Creating attributes with statusTLV only.");
  }
  ResponseAttributes = RasCreateEapAttributesWithResultTLV((__int64)&v25, (pValue[4] << 8) + pValue[5]);
  if ( ResponseAttributes )
  {
    v13 = xmmword_18004D740;
    if ( !(_QWORD)xmmword_18004D740 )
      goto LABEL_40;
    v14 = L"RasCreateEapAttributesWithResultTLV failed.";
    goto LABEL_23;
  }
LABEL_24:
  ResponseAttributes = EapHostPeerSetResponseAttributes(*(_DWORD *)(a1 + 484), &v25, &pEapOutput, &ppEapError);
  PrintEapError("EapHostPeerSetResponseAttributes", ppEapError);
  EapHostPeerFreeEapError(ppEapError);
  v15 = v25.pAttribs;
  if ( v25.pAttribs )
  {
    dwNumberOfAttributes = v25.dwNumberOfAttributes;
    v17 = 0;
    if ( v25.dwNumberOfAttributes )
    {
      do
      {
        v18 = v15[v17].pValue;
        if ( v18 )
        {
          LocalFree(v18);
          v15[v17].pValue = 0;
          v15 = v25.pAttribs;
          dwNumberOfAttributes = v25.dwNumberOfAttributes;
        }
        ++v17;
      }
      while ( v17 < dwNumberOfAttributes );
      v6 = v26;
    }
    LocalFree(v15);
    v25 = 0;
  }
  if ( ResponseAttributes )
  {
    v13 = xmmword_18004D740;
    if ( (_QWORD)xmmword_18004D740 )
    {
      v14 = L"EapHostPeerSetResponseAttributes (with statusTLV) failed with the above error.";
LABEL_23:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(gRasEapEtwContext, v13, v14);
    }
LABEL_40:
    if ( (_QWORD)xmmword_18004D740 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"RasProcessEaphostAttributes -- Leaving: 0x%x.", ResponseAttributes);
      v20 = xmmword_18004D740;
LABEL_42:
      ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v20, &v29);
    }
  }
  else
  {
    v19 = HandleEapResponse(a1, pEapOutput, 0, a2, v6, v24, v27, a6);
    ResponseAttributes = v19;
    if ( v19 )
    {
      if ( (_QWORD)xmmword_18004D740 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"HandleEapResponse returned error: 0x%x.", v19);
        v13 = xmmword_18004D740;
        v14 = (const wchar_t *)&v29;
        goto LABEL_23;
      }
    }
    else if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"RasProcessEaphostAttributes -- Leaving: 0x%x.", 0);
      v20 = *((_QWORD *)&xmmword_18004D740 + 1);
      goto LABEL_42;
    }
  }
  return ResponseAttributes;
}

```

## disassembly

```asm
0x180029ba0  push    rbp
0x180029ba2  push    rbx
0x180029ba3  push    rsi
0x180029ba4  push    rdi
0x180029ba5  push    r12
0x180029ba7  push    r13
0x180029ba9  push    r14
0x180029bab  push    r15
0x180029bad  lea     rbp, [rsp-798h]
0x180029bb5  sub     rsp, 898h
0x180029bbc  mov     rax, cs:__security_cookie
0x180029bc3  xor     rax, rsp
0x180029bc6  mov     [rbp+7D0h+var_50], rax
0x180029bcd  mov     rax, [rbp+7D0h+arg_20]
0x180029bd4  mov     r14, r8
0x180029bd7  mov     r12, [rbp+7D0h+arg_28]
0x180029bde  mov     r13, rdx
0x180029be1  mov     [rsp+8D0h+var_870], r8
0x180029be6  mov     r15, rcx
0x180029be9  xor     esi, esi
0x180029beb  mov     [rsp+8D0h+var_868], rax
0x180029bf0  xor     edx, edx; Val
0x180029bf2  mov     [rbp+7D0h+var_850], esi
0x180029bf5  mov     r8d, 7FCh; Size
0x180029bfb  mov     [rsp+8D0h+var_884], r9d
0x180029c00  lea     rcx, [rbp+7D0h+var_84C]; void *
0x180029c04  call    memset_0
0x180029c09  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029c10  test    rdx, rdx
0x180029c13  jz      short loc_180029C2F
0x180029c15  mov     rcx, cs:gRasEapEtwContext
0x180029c1c  lea     r8, aRasprocesseaph_1; "RasProcessEaphostAttributes -- Entering"...
0x180029c23  mov     rax, cs:gRasEapTemplateFunc
0x180029c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c2f  mov     [rsp+8D0h+ppEapError], rsi
0x180029c34  xorps   xmm0, xmm0
0x180029c37  mov     [rsp+8D0h+pEapOutput], 6
0x180029c3f  xorps   xmm1, xmm1
0x180029c42  movups  xmmword ptr [rsp+8D0h+pAttribs.dwNumberOfAttributes], xmm0
0x180029c47  movups  xmmword ptr [rsp+8D0h+var_880.dwNumberOfAttributes], xmm1
0x180029c4c  test    r15, r15
0x180029c4f  jz      loc_180029F47
0x180029c55  test    r12, r12
0x180029c58  jz      loc_180029F47
0x180029c5e  mov     ecx, [r15+1E4h]; sessionHandle
0x180029c65  lea     r8, [rsp+8D0h+ppEapError]; ppEapError
0x180029c6a  lea     rdx, [rsp+8D0h+pAttribs]; pAttribs
0x180029c6f  call    cs:__imp_EapHostPeerGetResponseAttributes
0x180029c76  nop     dword ptr [rax+rax+00h]
0x180029c7b  mov     rdx, [rsp+8D0h+ppEapError]
0x180029c80  lea     rcx, aEaphostpeerget_1; "EapHostPeerGetResponseAttributes"
0x180029c87  mov     ebx, eax
0x180029c89  call    PrintEapError
0x180029c8e  mov     rcx, [rsp+8D0h+ppEapError]; pEapError
0x180029c93  call    cs:__imp_EapHostPeerFreeEapError
0x180029c9a  nop     dword ptr [rax+rax+00h]
0x180029c9f  test    ebx, ebx
0x180029ca1  jnz     loc_180029F4C
0x180029ca7  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029cae  test    rdx, rdx
0x180029cb1  jz      short loc_180029CD4
0x180029cb3  mov     rcx, cs:gRasEapEtwContext
0x180029cba  lea     r8, aCheckingAttrib; "Checking attributes for statusTLV"
0x180029cc1  mov     rax, cs:gRasEapTemplateFunc
0x180029cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ccd  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029cd4  mov     ebx, esi
0x180029cd6  cmp     ebx, [rsp+8D0h+pAttribs.dwNumberOfAttributes]
0x180029cda  jnb     loc_180029DEA
0x180029ce0  mov     rdi, [rsp+8D0h+pAttribs.pAttribs]
0x180029ce5  mov     ecx, ebx
0x180029ce7  add     rcx, rcx
0x180029cea  cmp     dword ptr [rdi+rcx*8], 1FA6h
0x180029cf1  jz      short loc_180029D37
0x180029cf3  test    rdx, rdx
0x180029cf6  jz      short loc_180029D4C
0x180029cf8  mov     word ptr [rbp+7D0h+var_850], si
0x180029cfc  lea     rdx, aIgnoringAttrib; "Ignoring attribute type %d"
0x180029d03  mov     r8d, [rdi+rcx*8]
0x180029d07  lea     rcx, [rbp+7D0h+var_850]
0x180029d0b  call    FormatRRASErrorString
0x180029d10  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029d17  lea     r8, [rbp+7D0h+var_850]
0x180029d1b  mov     rcx, cs:gRasEapEtwContext
0x180029d22  mov     rax, cs:gRasEapTemplateFunc
0x180029d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d2e  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029d35  jmp     short loc_180029D4C
0x180029d37  mov     rdi, [rdi+rcx*8+8]
0x180029d3c  test    rdi, rdi
0x180029d3f  jz      short loc_180029D4C
0x180029d41  cmp     [rdi], sil
0x180029d44  jge     short loc_180029D4C
0x180029d46  cmp     byte ptr [rdi+1], 3
0x180029d4a  jz      short loc_180029D50
0x180029d4c  inc     ebx
0x180029d4e  jmp     short loc_180029CD6
0x180029d50  test    rdx, rdx
0x180029d53  jz      short loc_180029D95
0x180029d55  mov     rcx, cs:gRasEapEtwContext
0x180029d5c  lea     r8, aFoundStatustlv; "Found statusTLV attribute"
0x180029d63  mov     rax, cs:gRasEapTemplateFunc
0x180029d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d6f  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029d76  test    rdx, rdx
0x180029d79  jz      short loc_180029D95
0x180029d7b  mov     rcx, cs:gRasEapEtwContext
0x180029d82  lea     r8, aCreatingAttrib; "Creating attributes with statusTLV only"...
0x180029d89  mov     rax, cs:gRasEapTemplateFunc
0x180029d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d95  movzx   r8d, byte ptr [rdi+4]
0x180029d9a  mov     ecx, 100h
0x180029d9f  movzx   edx, byte ptr [rdi+5]
0x180029da3  imul    r8d, ecx
0x180029da7  lea     rcx, [rsp+8D0h+var_880]
0x180029dac  add     dx, r8w
0x180029db0  call    RasCreateEapAttributesWithResultTLV
0x180029db5  mov     ebx, eax
0x180029db7  test    eax, eax
0x180029db9  jz      short loc_180029DEA
0x180029dbb  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029dc2  test    rdx, rdx
0x180029dc5  jz      loc_180029F4C
0x180029dcb  lea     r8, aRascreateeapat; "RasCreateEapAttributesWithResultTLV fai"...
0x180029dd2  mov     rcx, cs:gRasEapEtwContext
0x180029dd9  mov     rax, cs:gRasEapTemplateFunc
0x180029de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de5  jmp     loc_180029F4C
0x180029dea  mov     ecx, [r15+1E4h]; sessionHandle
0x180029df1  lea     r9, [rsp+8D0h+ppEapError]; ppEapError
0x180029df6  lea     r8, [rsp+8D0h+pEapOutput]; pEapOutput
0x180029dfb  lea     rdx, [rsp+8D0h+var_880]; pAttribs
0x180029e00  call    cs:__imp_EapHostPeerSetResponseAttributes
0x180029e07  nop     dword ptr [rax+rax+00h]
0x180029e0c  mov     rdx, [rsp+8D0h+ppEapError]
0x180029e11  lea     rcx, aEaphostpeerset_0; "EapHostPeerSetResponseAttributes"
0x180029e18  mov     ebx, eax
0x180029e1a  call    PrintEapError
0x180029e1f  mov     rcx, [rsp+8D0h+ppEapError]; pEapError
0x180029e24  call    cs:__imp_EapHostPeerFreeEapError
0x180029e2b  nop     dword ptr [rax+rax+00h]
0x180029e30  mov     rsi, [rsp+8D0h+var_880.pAttribs]
0x180029e35  test    rsi, rsi
0x180029e38  jz      short loc_180029E94
0x180029e3a  mov     eax, [rsp+8D0h+var_880.dwNumberOfAttributes]
0x180029e3e  xor     edi, edi
0x180029e40  test    eax, eax
0x180029e42  jz      short loc_180029E7D
0x180029e44  mov     r14d, edi
0x180029e47  add     r14, r14
0x180029e4a  mov     rcx, [rsi+r14*8+8]; hMem
0x180029e4f  test    rcx, rcx
0x180029e52  jz      short loc_180029E72
0x180029e54  call    cs:__imp_LocalFree
0x180029e5b  nop     dword ptr [rax+rax+00h]
0x180029e60  mov     qword ptr [rsi+r14*8+8], 0
0x180029e69  mov     rsi, [rsp+8D0h+var_880.pAttribs]
0x180029e6e  mov     eax, [rsp+8D0h+var_880.dwNumberOfAttributes]
0x180029e72  inc     edi
0x180029e74  cmp     edi, eax
0x180029e76  jb      short loc_180029E44
0x180029e78  mov     r14, [rsp+8D0h+var_870]
0x180029e7d  mov     rcx, rsi; hMem
0x180029e80  call    cs:__imp_LocalFree
0x180029e87  nop     dword ptr [rax+rax+00h]
0x180029e8c  xorps   xmm0, xmm0
0x180029e8f  movups  xmmword ptr [rsp+8D0h+var_880.dwNumberOfAttributes], xmm0
0x180029e94  xor     esi, esi
0x180029e96  test    ebx, ebx
0x180029e98  jz      short loc_180029EB6
0x180029e9a  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029ea1  test    rdx, rdx
0x180029ea4  jz      loc_180029F4C
0x180029eaa  lea     r8, aEaphostpeerset; "EapHostPeerSetResponseAttributes (with "...
0x180029eb1  jmp     loc_180029DD2
0x180029eb6  mov     rax, [rsp+8D0h+var_868]
0x180029ebb  mov     r9, r13
0x180029ebe  mov     edx, [rsp+8D0h+pEapOutput]
0x180029ec2  xor     r8d, r8d
0x180029ec5  mov     [rsp+8D0h+var_898], r12
0x180029eca  mov     rcx, r15
0x180029ecd  mov     [rsp+8D0h+var_8A0], rax
0x180029ed2  mov     eax, [rsp+8D0h+var_884]
0x180029ed6  mov     [rsp+8D0h+var_8A8], eax
0x180029eda  mov     [rsp+8D0h+var_8B0], r14
0x180029edf  call    HandleEapResponse
0x180029ee4  mov     ebx, eax
0x180029ee6  test    eax, eax
0x180029ee8  jz      short loc_180029F1E
0x180029eea  cmp     qword ptr cs:xmmword_18004D740, rsi
0x180029ef1  jz      loc_180029F8A
0x180029ef7  mov     r8d, eax
0x180029efa  mov     word ptr [rbp+7D0h+var_850], si
0x180029efe  lea     rdx, aHandleeaprespo; "HandleEapResponse returned error: 0x%x."
0x180029f05  lea     rcx, [rbp+7D0h+var_850]
0x180029f09  call    FormatRRASErrorString
0x180029f0e  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029f15  lea     r8, [rbp+7D0h+var_850]
0x180029f19  jmp     loc_180029DD2
0x180029f1e  cmp     qword ptr cs:xmmword_18004D740+8, rsi
0x180029f25  jz      short loc_180029F8A
0x180029f27  mov     r8d, eax
0x180029f2a  mov     word ptr [rbp+7D0h+var_850], si
0x180029f2e  lea     rdx, aRasprocesseaph_4; "RasProcessEaphostAttributes -- Leaving:"...
0x180029f35  lea     rcx, [rbp+7D0h+var_850]
0x180029f39  call    FormatRRASErrorString
0x180029f3e  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029f45  jmp     short loc_180029F73
0x180029f47  mov     ebx, 57h ; 'W'
0x180029f4c  cmp     qword ptr cs:xmmword_18004D740, rsi
0x180029f53  jz      short loc_180029F8A
0x180029f55  mov     r8d, ebx
0x180029f58  mov     word ptr [rbp+7D0h+var_850], si
0x180029f5c  lea     rdx, aRasprocesseaph_4; "RasProcessEaphostAttributes -- Leaving:"...
0x180029f63  lea     rcx, [rbp+7D0h+var_850]
0x180029f67  call    FormatRRASErrorString
0x180029f6c  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029f73  mov     rcx, cs:gRasEapEtwContext
0x180029f7a  lea     r8, [rbp+7D0h+var_850]
0x180029f7e  mov     rax, cs:gRasEapTemplateFunc
0x180029f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f8a  mov     eax, ebx
0x180029f8c  mov     rcx, [rbp+7D0h+var_50]
0x180029f93  xor     rcx, rsp; StackCookie
0x180029f96  call    __security_check_cookie
0x180029f9b  add     rsp, 898h
0x180029fa2  pop     r15
0x180029fa4  pop     r14
0x180029fa6  pop     r13
0x180029fa8  pop     r12
0x180029faa  pop     rdi
0x180029fab  pop     rsi
0x180029fac  pop     rbx
0x180029fad  pop     rbp
0x180029fae  retn
```

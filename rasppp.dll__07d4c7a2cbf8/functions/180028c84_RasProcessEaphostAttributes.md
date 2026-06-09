# RasProcessEaphostAttributes

- ea: `0x180028c84`
- end: `0x18002906f`
- name: `RasProcessEaphostAttributes`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180027aa4`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180027aa4`
- `0x180027da8`
- `0x1800281c8`
- `0x180028c84`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f46`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028d71`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028ef6`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028d71`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028ef6`
- `eappprxy!EapHostPeerGetResponseAttributes` at `0x180028d53`
- `eappprxy!EapHostPeerGetResponseAttributes` at `0x180028d53`
- `eappprxy!EapHostPeerSetResponseAttributes` at `0x180028ed8`
- `eappprxy!EapHostPeerSetResponseAttributes` at `0x180028ed8`

## string_xrefs

- `0x180028ea3`: `RasCreateEapAttributesWithResultTLV failed.`

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
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
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
  v10 = *((_QWORD *)&xmmword_18004C740 + 1);
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
      L"Checking attributes for statusTLV");
    v10 = *((_QWORD *)&xmmword_18004C740 + 1);
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
          *((_QWORD *)&xmmword_18004C740 + 1),
          &v29);
        v10 = *((_QWORD *)&xmmword_18004C740 + 1);
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
    if ( *((_QWORD *)&xmmword_18004C740 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        *((_QWORD *)&xmmword_18004C740 + 1),
        L"Creating attributes with statusTLV only.");
  }
  ResponseAttributes = RasCreateEapAttributesWithResultTLV((__int64)&v25, (pValue[4] << 8) + pValue[5]);
  if ( ResponseAttributes )
  {
    v13 = xmmword_18004C740;
    if ( !(_QWORD)xmmword_18004C740 )
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
    v13 = xmmword_18004C740;
    if ( (_QWORD)xmmword_18004C740 )
    {
      v14 = L"EapHostPeerSetResponseAttributes (with statusTLV) failed with the above error.";
LABEL_23:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(gRasEapEtwContext, v13, v14);
    }
LABEL_40:
    if ( (_QWORD)xmmword_18004C740 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"RasProcessEaphostAttributes -- Leaving: 0x%x.", ResponseAttributes);
      v20 = xmmword_18004C740;
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
      if ( (_QWORD)xmmword_18004C740 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"HandleEapResponse returned error: 0x%x.", v19);
        v13 = xmmword_18004C740;
        v14 = (const wchar_t *)&v29;
        goto LABEL_23;
      }
    }
    else if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"RasProcessEaphostAttributes -- Leaving: 0x%x.", 0);
      v20 = *((_QWORD *)&xmmword_18004C740 + 1);
      goto LABEL_42;
    }
  }
  return ResponseAttributes;
}

```

## disassembly

```asm
0x180028c84  push    rbp
0x180028c86  push    rbx
0x180028c87  push    rsi
0x180028c88  push    rdi
0x180028c89  push    r12
0x180028c8b  push    r13
0x180028c8d  push    r14
0x180028c8f  push    r15
0x180028c91  lea     rbp, [rsp-798h]
0x180028c99  sub     rsp, 898h
0x180028ca0  mov     rax, cs:__security_cookie
0x180028ca7  xor     rax, rsp
0x180028caa  mov     [rbp+7D0h+var_50], rax
0x180028cb1  mov     rax, [rbp+7D0h+arg_20]
0x180028cb8  mov     r14, r8
0x180028cbb  mov     r12, [rbp+7D0h+arg_28]
0x180028cc2  mov     r13, rdx
0x180028cc5  mov     [rsp+8D0h+var_870], r8
0x180028cca  mov     r15, rcx
0x180028ccd  xor     esi, esi
0x180028ccf  mov     [rsp+8D0h+var_868], rax
0x180028cd4  xor     edx, edx; Val
0x180028cd6  mov     [rbp+7D0h+var_850], esi
0x180028cd9  mov     r8d, 7FCh; Size
0x180028cdf  mov     [rsp+8D0h+var_884], r9d
0x180028ce4  lea     rcx, [rbp+7D0h+var_84C]; void *
0x180028ce8  call    memset_0
0x180028ced  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028cf4  test    rdx, rdx
0x180028cf7  jz      short loc_180028D13
0x180028cf9  mov     rcx, cs:gRasEapEtwContext
0x180028d00  lea     r8, aRasprocesseaph_1; "RasProcessEaphostAttributes -- Entering"...
0x180028d07  mov     rax, cs:gRasEapTemplateFunc
0x180028d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d13  mov     [rsp+8D0h+ppEapError], rsi
0x180028d18  xorps   xmm0, xmm0
0x180028d1b  mov     [rsp+8D0h+pEapOutput], 6
0x180028d23  xorps   xmm1, xmm1
0x180028d26  movups  xmmword ptr [rsp+8D0h+pAttribs.dwNumberOfAttributes], xmm0
0x180028d2b  movups  xmmword ptr [rsp+8D0h+var_880.dwNumberOfAttributes], xmm1
0x180028d30  test    r15, r15
0x180028d33  jz      loc_180029007
0x180028d39  test    r12, r12
0x180028d3c  jz      loc_180029007
0x180028d42  mov     ecx, [r15+1E4h]; sessionHandle
0x180028d49  lea     r8, [rsp+8D0h+ppEapError]; ppEapError
0x180028d4e  lea     rdx, [rsp+8D0h+pAttribs]; pAttribs
0x180028d53  call    cs:__imp_EapHostPeerGetResponseAttributes
0x180028d59  mov     rdx, [rsp+8D0h+ppEapError]
0x180028d5e  lea     rcx, aEaphostpeerget_1; "EapHostPeerGetResponseAttributes"
0x180028d65  mov     ebx, eax
0x180028d67  call    PrintEapError
0x180028d6c  mov     rcx, [rsp+8D0h+ppEapError]; pEapError
0x180028d71  call    cs:__imp_EapHostPeerFreeEapError
0x180028d77  test    ebx, ebx
0x180028d79  jnz     loc_18002900C
0x180028d7f  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028d86  test    rdx, rdx
0x180028d89  jz      short loc_180028DAC
0x180028d8b  mov     rcx, cs:gRasEapEtwContext
0x180028d92  lea     r8, aCheckingAttrib; "Checking attributes for statusTLV"
0x180028d99  mov     rax, cs:gRasEapTemplateFunc
0x180028da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028da5  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028dac  mov     ebx, esi
0x180028dae  cmp     ebx, [rsp+8D0h+pAttribs.dwNumberOfAttributes]
0x180028db2  jnb     loc_180028EC2
0x180028db8  mov     rdi, [rsp+8D0h+pAttribs.pAttribs]
0x180028dbd  mov     ecx, ebx
0x180028dbf  add     rcx, rcx
0x180028dc2  cmp     dword ptr [rdi+rcx*8], 1FA6h
0x180028dc9  jz      short loc_180028E0F
0x180028dcb  test    rdx, rdx
0x180028dce  jz      short loc_180028E24
0x180028dd0  mov     word ptr [rbp+7D0h+var_850], si
0x180028dd4  lea     rdx, aIgnoringAttrib; "Ignoring attribute type %d"
0x180028ddb  mov     r8d, [rdi+rcx*8]
0x180028ddf  lea     rcx, [rbp+7D0h+var_850]
0x180028de3  call    FormatRRASErrorString
0x180028de8  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028def  lea     r8, [rbp+7D0h+var_850]
0x180028df3  mov     rcx, cs:gRasEapEtwContext
0x180028dfa  mov     rax, cs:gRasEapTemplateFunc
0x180028e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e06  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028e0d  jmp     short loc_180028E24
0x180028e0f  mov     rdi, [rdi+rcx*8+8]
0x180028e14  test    rdi, rdi
0x180028e17  jz      short loc_180028E24
0x180028e19  cmp     [rdi], sil
0x180028e1c  jge     short loc_180028E24
0x180028e1e  cmp     byte ptr [rdi+1], 3
0x180028e22  jz      short loc_180028E28
0x180028e24  inc     ebx
0x180028e26  jmp     short loc_180028DAE
0x180028e28  test    rdx, rdx
0x180028e2b  jz      short loc_180028E6D
0x180028e2d  mov     rcx, cs:gRasEapEtwContext
0x180028e34  lea     r8, aFoundStatustlv; "Found statusTLV attribute"
0x180028e3b  mov     rax, cs:gRasEapTemplateFunc
0x180028e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e47  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028e4e  test    rdx, rdx
0x180028e51  jz      short loc_180028E6D
0x180028e53  mov     rcx, cs:gRasEapEtwContext
0x180028e5a  lea     r8, aCreatingAttrib; "Creating attributes with statusTLV only"...
0x180028e61  mov     rax, cs:gRasEapTemplateFunc
0x180028e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e6d  movzx   r8d, byte ptr [rdi+4]
0x180028e72  mov     ecx, 100h
0x180028e77  movzx   edx, byte ptr [rdi+5]
0x180028e7b  imul    r8d, ecx
0x180028e7f  lea     rcx, [rsp+8D0h+var_880]
0x180028e84  add     dx, r8w
0x180028e88  call    RasCreateEapAttributesWithResultTLV
0x180028e8d  mov     ebx, eax
0x180028e8f  test    eax, eax
0x180028e91  jz      short loc_180028EC2
0x180028e93  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028e9a  test    rdx, rdx
0x180028e9d  jz      loc_18002900C
0x180028ea3  lea     r8, aRascreateeapat; "RasCreateEapAttributesWithResultTLV fai"...
0x180028eaa  mov     rcx, cs:gRasEapEtwContext
0x180028eb1  mov     rax, cs:gRasEapTemplateFunc
0x180028eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ebd  jmp     loc_18002900C
0x180028ec2  mov     ecx, [r15+1E4h]; sessionHandle
0x180028ec9  lea     r9, [rsp+8D0h+ppEapError]; ppEapError
0x180028ece  lea     r8, [rsp+8D0h+pEapOutput]; pEapOutput
0x180028ed3  lea     rdx, [rsp+8D0h+var_880]; pAttribs
0x180028ed8  call    cs:__imp_EapHostPeerSetResponseAttributes
0x180028ede  mov     rdx, [rsp+8D0h+ppEapError]
0x180028ee3  lea     rcx, aEaphostpeerset_0; "EapHostPeerSetResponseAttributes"
0x180028eea  mov     ebx, eax
0x180028eec  call    PrintEapError
0x180028ef1  mov     rcx, [rsp+8D0h+ppEapError]; pEapError
0x180028ef6  call    cs:__imp_EapHostPeerFreeEapError
0x180028efc  mov     rsi, [rsp+8D0h+var_880.pAttribs]
0x180028f01  test    rsi, rsi
0x180028f04  jz      short loc_180028F54
0x180028f06  mov     eax, [rsp+8D0h+var_880.dwNumberOfAttributes]
0x180028f0a  xor     edi, edi
0x180028f0c  test    eax, eax
0x180028f0e  jz      short loc_180028F43
0x180028f10  mov     r14d, edi
0x180028f13  add     r14, r14
0x180028f16  mov     rcx, [rsi+r14*8+8]; hMem
0x180028f1b  test    rcx, rcx
0x180028f1e  jz      short loc_180028F38
0x180028f20  call    cs:__imp_LocalFree
0x180028f26  mov     qword ptr [rsi+r14*8+8], 0
0x180028f2f  mov     rsi, [rsp+8D0h+var_880.pAttribs]
0x180028f34  mov     eax, [rsp+8D0h+var_880.dwNumberOfAttributes]
0x180028f38  inc     edi
0x180028f3a  cmp     edi, eax
0x180028f3c  jb      short loc_180028F10
0x180028f3e  mov     r14, [rsp+8D0h+var_870]
0x180028f43  mov     rcx, rsi; hMem
0x180028f46  call    cs:__imp_LocalFree
0x180028f4c  xorps   xmm0, xmm0
0x180028f4f  movups  xmmword ptr [rsp+8D0h+var_880.dwNumberOfAttributes], xmm0
0x180028f54  xor     esi, esi
0x180028f56  test    ebx, ebx
0x180028f58  jz      short loc_180028F76
0x180028f5a  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028f61  test    rdx, rdx
0x180028f64  jz      loc_18002900C
0x180028f6a  lea     r8, aEaphostpeerset; "EapHostPeerSetResponseAttributes (with "...
0x180028f71  jmp     loc_180028EAA
0x180028f76  mov     rax, [rsp+8D0h+var_868]
0x180028f7b  mov     r9, r13
0x180028f7e  mov     edx, [rsp+8D0h+pEapOutput]
0x180028f82  xor     r8d, r8d
0x180028f85  mov     [rsp+8D0h+var_898], r12
0x180028f8a  mov     rcx, r15
0x180028f8d  mov     [rsp+8D0h+var_8A0], rax
0x180028f92  mov     eax, [rsp+8D0h+var_884]
0x180028f96  mov     [rsp+8D0h+var_8A8], eax
0x180028f9a  mov     [rsp+8D0h+var_8B0], r14
0x180028f9f  call    HandleEapResponse
0x180028fa4  mov     ebx, eax
0x180028fa6  test    eax, eax
0x180028fa8  jz      short loc_180028FDE
0x180028faa  cmp     qword ptr cs:xmmword_18004C740, rsi
0x180028fb1  jz      loc_18002904A
0x180028fb7  mov     r8d, eax
0x180028fba  mov     word ptr [rbp+7D0h+var_850], si
0x180028fbe  lea     rdx, aHandleeaprespo; "HandleEapResponse returned error: 0x%x."
0x180028fc5  lea     rcx, [rbp+7D0h+var_850]
0x180028fc9  call    FormatRRASErrorString
0x180028fce  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028fd5  lea     r8, [rbp+7D0h+var_850]
0x180028fd9  jmp     loc_180028EAA
0x180028fde  cmp     qword ptr cs:xmmword_18004C740+8, rsi
0x180028fe5  jz      short loc_18002904A
0x180028fe7  mov     r8d, eax
0x180028fea  mov     word ptr [rbp+7D0h+var_850], si
0x180028fee  lea     rdx, aRasprocesseaph_4; "RasProcessEaphostAttributes -- Leaving:"...
0x180028ff5  lea     rcx, [rbp+7D0h+var_850]
0x180028ff9  call    FormatRRASErrorString
0x180028ffe  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180029005  jmp     short loc_180029033
0x180029007  mov     ebx, 57h ; 'W'
0x18002900c  cmp     qword ptr cs:xmmword_18004C740, rsi
0x180029013  jz      short loc_18002904A
0x180029015  mov     r8d, ebx
0x180029018  mov     word ptr [rbp+7D0h+var_850], si
0x18002901c  lea     rdx, aRasprocesseaph_4; "RasProcessEaphostAttributes -- Leaving:"...
0x180029023  lea     rcx, [rbp+7D0h+var_850]
0x180029027  call    FormatRRASErrorString
0x18002902c  mov     rdx, qword ptr cs:xmmword_18004C740
0x180029033  mov     rcx, cs:gRasEapEtwContext
0x18002903a  lea     r8, [rbp+7D0h+var_850]
0x18002903e  mov     rax, cs:gRasEapTemplateFunc
0x180029045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002904a  mov     eax, ebx
0x18002904c  mov     rcx, [rbp+7D0h+var_50]
0x180029053  xor     rcx, rsp; StackCookie
0x180029056  call    __security_check_cookie
0x18002905b  add     rsp, 898h
0x180029062  pop     r15
0x180029064  pop     r14
0x180029066  pop     r13
0x180029068  pop     r12
0x18002906a  pop     rdi
0x18002906b  pop     rsi
0x18002906c  pop     rbx
0x18002906d  pop     rbp
0x18002906e  retn
```

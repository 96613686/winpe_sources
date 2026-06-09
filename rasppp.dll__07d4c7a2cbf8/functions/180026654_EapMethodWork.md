# EapMethodWork

- ea: `0x180026654`
- end: `0x180026956`
- name: `EapMethodWork`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002695c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180026654`
- `0x180027484`
- `0x180027aa4`
- `0x180027da8`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `eappprxy!EapHostPeerFreeEapError` at `0x180026868`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800268c9`
- `eappprxy!EapHostPeerFreeEapError` at `0x180026868`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800268c9`
- `eappprxy!EapHostPeerSetUIContext` at `0x180026842`
- `eappprxy!EapHostPeerSetUIContext` at `0x180026842`
- `eappprxy!EapHostPeerProcessReceivedPacket` at `0x18002689f`
- `eappprxy!EapHostPeerProcessReceivedPacket` at `0x18002689f`

## string_xrefs

- `0x1800267b9`: `Failed to construct EAP UI context during %hs with error: 0x%x. Failing auth.`

## pseudocode

```c
__int64 __fastcall EapMethodWork(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5, __int64 a6)
{
  EapHostPeerResponseAction v8; // edi
  int v9; // r15d
  int v10; // r13d
  const BYTE *v12; // rdi
  DWORD *v13; // rax
  DWORD dwReasonCode; // edi
  bool v15; // zf
  const char *v16; // r8
  DWORD v17; // r15d
  EapHostPeerResponseAction pEapOutput; // [rsp+40h] [rbp-C0h] BYREF
  EAP_ERROR *pEapError; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v21 = a3;
  v20 = a4;
  v8 = EapHostPeerResponseNone;
  v22 = 0;
  pEapOutput = EapHostPeerResponseNone;
  pEapError = 0;
  v9 = a4;
  v10 = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( !a6 )
  {
    dwReasonCode = EapHostPeerProcessReceivedPacket(
                     *(_DWORD *)(a1 + 484),
                     (*(unsigned __int8 *)(a2 + 2) << 8) + *(unsigned __int8 *)(a2 + 3),
                     (const BYTE *const)a2,
                     &pEapOutput,
                     &pEapError);
    PrintEapError("EapHostPeerProcessReceivedPacket", pEapError);
    if ( dwReasonCode )
    {
      if ( pEapError )
        dwReasonCode = pEapError->dwReasonCode;
      EapHostPeerFreeEapError(pEapError);
      if ( (_QWORD)xmmword_18004C740 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          xmmword_18004C740,
          L"Silently discarding invalid EAP packet.");
      goto LABEL_25;
    }
LABEL_32:
    v8 = pEapOutput;
    return HandleEapResponse(a1, v8, v10, a2, v21, v9, a6, (__int64)a5);
  }
  if ( *(_DWORD *)(a6 + 176) )
  {
    v8 = EapHostPeerResponseResult;
    pEapOutput = EapHostPeerResponseResult;
    v10 = 1;
    return HandleEapResponse(a1, v8, v10, a2, v21, v9, a6, (__int64)a5);
  }
  if ( !*(_DWORD *)(a6 + 188) )
  {
    if ( *(_DWORD *)(a6 + 184) )
    {
LABEL_14:
      dwReasonCode = ConstructEapUserBlobFromRawCredentials(a6, a1, 1, 0);
      if ( dwReasonCode )
      {
        if ( (_QWORD)xmmword_18004C740 )
        {
          v15 = *(_DWORD *)(a6 + 180) == 0;
          LOWORD(v22) = 0;
          v16 = "auth retry";
          if ( v15 )
            v16 = "change password";
          FormatRRASErrorString(
            &v22,
            L"Failed to construct EAP UI context during %hs with error: 0x%x. Failing auth.",
            v16,
            dwReasonCode);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004C740, &v22);
        }
        return dwReasonCode;
      }
      v13 = *(DWORD **)(a1 + 344);
      v12 = (const BYTE *)(v13 + 1);
      goto LABEL_21;
    }
    if ( !*(_DWORD *)(a6 + 180) )
      return HandleEapResponse(a1, v8, v10, a2, v21, v9, a6, (__int64)a5);
  }
  if ( *(_DWORD *)(a6 + 184) || *(_DWORD *)(a6 + 180) )
    goto LABEL_14;
  if ( *(_DWORD *)(a6 + 192) == *(_DWORD *)(a1 + 376) )
  {
    v12 = *(const BYTE **)(a6 + 200);
    v13 = (DWORD *)(a6 + 208);
LABEL_21:
    v17 = *v13;
    if ( *((_QWORD *)&xmmword_18004C740 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        *((_QWORD *)&xmmword_18004C740 + 1),
        L"Setting new UI Context data",
        0);
    dwReasonCode = EapHostPeerSetUIContext(*(_DWORD *)(a1 + 484), v17, v12, &pEapOutput, &pEapError);
    PrintEapError("EapHostPeerSetUIContext", pEapError);
    if ( dwReasonCode )
    {
      EapHostPeerFreeEapError(pEapError);
LABEL_25:
      *a5 = 0;
      return dwReasonCode;
    }
    v9 = v20;
    goto LABEL_32;
  }
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
      L"Out of date data received from UI",
      0);
  return 0;
}

```

## disassembly

```asm
0x180026654  mov     [rsp-8+arg_18], rbx
0x180026659  push    rbp
0x18002665a  push    rsi
0x18002665b  push    rdi
0x18002665c  push    r12
0x18002665e  push    r13
0x180026660  push    r14
0x180026662  push    r15
0x180026664  lea     rbp, [rsp-770h]
0x18002666c  sub     rsp, 870h
0x180026673  mov     rax, cs:__security_cookie
0x18002667a  xor     rax, rsp
0x18002667d  mov     [rbp+7A0h+var_40], rax
0x180026684  mov     r14, [rbp+7A0h+arg_20]
0x18002668b  mov     r12, rdx
0x18002668e  mov     rbx, [rbp+7A0h+arg_28]
0x180026695  mov     rsi, rcx
0x180026698  mov     [rsp+8A0h+var_848], r8
0x18002669d  lea     rcx, [rsp+8A0h+var_83C]; void *
0x1800266a2  xor     eax, eax
0x1800266a4  mov     [rsp+8A0h+var_850], r9d
0x1800266a9  mov     edi, 6
0x1800266ae  mov     [rsp+8A0h+var_840], eax
0x1800266b2  xor     edx, edx; Val
0x1800266b4  mov     [rsp+8A0h+pEapOutput], edi
0x1800266b8  mov     r8d, 7FCh; Size
0x1800266be  mov     [rsp+8A0h+pEapError], 0
0x1800266c7  mov     r15d, r9d
0x1800266ca  xor     r13d, r13d
0x1800266cd  call    memset_0
0x1800266d2  xor     r9d, r9d
0x1800266d5  test    rbx, rbx
0x1800266d8  jz      loc_180026876
0x1800266de  cmp     [rbx+0B0h], r9d
0x1800266e5  jz      short loc_1800266F8
0x1800266e7  lea     edi, [r13+2]
0x1800266eb  mov     [rsp+8A0h+pEapOutput], edi
0x1800266ef  lea     r13d, [r9+1]
0x1800266f3  jmp     loc_180026903
0x1800266f8  cmp     [rbx+0BCh], r9d
0x1800266ff  jnz     short loc_180026717
0x180026701  cmp     [rbx+0B8h], r9d
0x180026708  jnz     short loc_180026777
0x18002670a  cmp     [rbx+0B4h], r9d
0x180026711  jz      loc_180026903
0x180026717  cmp     [rbx+0B8h], r9d
0x18002671e  jnz     short loc_180026777
0x180026720  cmp     [rbx+0B4h], r9d
0x180026727  jnz     short loc_180026777
0x180026729  mov     eax, [rsi+178h]
0x18002672f  cmp     [rbx+0C0h], eax
0x180026735  jz      short loc_180026764
0x180026737  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x18002673e  test    rdx, rdx
0x180026741  jz      short loc_18002675D
0x180026743  mov     rcx, cs:gRasEapEtwContext
0x18002674a  lea     r8, aOutOfDateDataR; "Out of date data received from UI"
0x180026751  mov     rax, cs:gRasEapTemplateFunc
0x180026758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002675d  xor     eax, eax
0x18002675f  jmp     loc_18002692C
0x180026764  mov     rdi, [rbx+0C8h]
0x18002676b  lea     rax, [rbx+0D0h]
0x180026772  jmp     loc_1800267FE
0x180026777  mov     r8d, 1
0x18002677d  mov     rdx, rsi
0x180026780  mov     rcx, rbx
0x180026783  call    ConstructEapUserBlobFromRawCredentials
0x180026788  xor     r9d, r9d
0x18002678b  mov     edi, eax
0x18002678d  test    eax, eax
0x18002678f  jz      short loc_1800267F3
0x180026791  cmp     qword ptr cs:xmmword_18004C740, r9
0x180026798  jz      short loc_1800267EC
0x18002679a  cmp     [rbx+0B4h], r9d
0x1800267a1  lea     rax, aChangePassword; "change password"
0x1800267a8  mov     word ptr [rsp+8A0h+var_840], r9w
0x1800267ae  lea     r8, aAuthRetry; "auth retry"
0x1800267b5  cmovz   r8, rax
0x1800267b9  lea     rdx, aFailedToConstr; "Failed to construct EAP UI context duri"...
0x1800267c0  mov     r9d, edi
0x1800267c3  lea     rcx, [rsp+8A0h+var_840]
0x1800267c8  call    FormatRRASErrorString
0x1800267cd  mov     rdx, qword ptr cs:xmmword_18004C740
0x1800267d4  lea     r8, [rsp+8A0h+var_840]
0x1800267d9  mov     rcx, cs:gRasEapEtwContext
0x1800267e0  mov     rax, cs:gRasEapTemplateFunc
0x1800267e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267ec  mov     eax, edi
0x1800267ee  jmp     loc_18002692C
0x1800267f3  mov     rax, [rsi+158h]
0x1800267fa  lea     rdi, [rax+4]
0x1800267fe  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180026805  mov     r15d, [rax]
0x180026808  test    rdx, rdx
0x18002680b  jz      short loc_180026827
0x18002680d  mov     rcx, cs:gRasEapEtwContext
0x180026814  lea     r8, aSettingNewUiCo; "Setting new UI Context data"
0x18002681b  mov     rax, cs:gRasEapTemplateFunc
0x180026822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026827  mov     ecx, [rsi+1E4h]; sessionHandle
0x18002682d  lea     rax, [rsp+8A0h+pEapError]
0x180026832  lea     r9, [rsp+8A0h+pEapOutput]; pEapOutput
0x180026837  mov     [rsp+8A0h+ppEapError], rax; ppEapError
0x18002683c  mov     r8, rdi; pUIContextData
0x18002683f  mov     edx, r15d; dwSizeOfUIContextData
0x180026842  call    cs:__imp_EapHostPeerSetUIContext
0x180026848  mov     rdx, [rsp+8A0h+pEapError]
0x18002684d  lea     rcx, aEaphostpeerset_1; "EapHostPeerSetUIContext"
0x180026854  mov     edi, eax
0x180026856  call    PrintEapError
0x18002685b  test    edi, edi
0x18002685d  jz      loc_1800268FA
0x180026863  mov     rcx, [rsp+8A0h+pEapError]; pEapError
0x180026868  call    cs:__imp_EapHostPeerFreeEapError
0x18002686e  mov     [r14], r13d
0x180026871  jmp     loc_1800267EC
0x180026876  movzx   eax, byte ptr [r12+2]
0x18002687c  lea     r9, [rsp+8A0h+pEapOutput]; pEapOutput
0x180026881  movzx   edx, byte ptr [r12+3]
0x180026887  mov     r8, r12; pReceivePacket
0x18002688a  mov     ecx, [rsi+1E4h]; sessionHandle
0x180026890  shl     eax, 8
0x180026893  add     edx, eax; cbReceivePacket
0x180026895  lea     rax, [rsp+8A0h+pEapError]
0x18002689a  mov     [rsp+8A0h+ppEapError], rax; ppEapError
0x18002689f  call    cs:__imp_EapHostPeerProcessReceivedPacket
0x1800268a5  mov     rdx, [rsp+8A0h+pEapError]
0x1800268aa  lea     rcx, aEaphostpeerpro; "EapHostPeerProcessReceivedPacket"
0x1800268b1  mov     edi, eax
0x1800268b3  call    PrintEapError
0x1800268b8  test    edi, edi
0x1800268ba  jz      short loc_1800268FF
0x1800268bc  mov     rcx, [rsp+8A0h+pEapError]; pEapError
0x1800268c1  test    rcx, rcx
0x1800268c4  jz      short loc_1800268C9
0x1800268c6  mov     edi, [rcx+14h]
0x1800268c9  call    cs:__imp_EapHostPeerFreeEapError
0x1800268cf  mov     rdx, qword ptr cs:xmmword_18004C740
0x1800268d6  test    rdx, rdx
0x1800268d9  jz      short loc_18002686E
0x1800268db  mov     rcx, cs:gRasEapEtwContext
0x1800268e2  lea     r8, aSilentlyDiscar_1; "Silently discarding invalid EAP packet."
0x1800268e9  mov     rax, cs:gRasEapTemplateFunc
0x1800268f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268f5  jmp     loc_18002686E
0x1800268fa  mov     r15d, [rsp+8A0h+var_850]
0x1800268ff  mov     edi, [rsp+8A0h+pEapOutput]
0x180026903  mov     rax, [rsp+8A0h+var_848]
0x180026908  mov     r9, r12
0x18002690b  mov     [rsp+8A0h+var_868], r14
0x180026910  mov     r8d, r13d
0x180026913  mov     [rsp+8A0h+var_870], rbx
0x180026918  mov     edx, edi
0x18002691a  mov     [rsp+8A0h+var_878], r15d
0x18002691f  mov     rcx, rsi
0x180026922  mov     [rsp+8A0h+ppEapError], rax
0x180026927  call    HandleEapResponse
0x18002692c  mov     rcx, [rbp+7A0h+var_40]
0x180026933  xor     rcx, rsp; StackCookie
0x180026936  call    __security_check_cookie
0x18002693b  mov     rbx, [rsp+8A0h+arg_18]
0x180026943  add     rsp, 870h
0x18002694a  pop     r15
0x18002694c  pop     r14
0x18002694e  pop     r13
0x180026950  pop     r12
0x180026952  pop     rdi
0x180026953  pop     rsi
0x180026954  pop     rbp
0x180026955  retn
```

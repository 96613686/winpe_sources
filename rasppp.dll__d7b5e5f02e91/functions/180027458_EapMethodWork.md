# EapMethodWork

- ea: `0x180027458`
- end: `0x180027773`
- name: `EapMethodWork`
- size: `795`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002777c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180027458`
- `0x1800282f8`
- `0x180028964`
- `0x180028c68`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `eappprxy!EapHostPeerFreeEapError` at `0x180027672`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800276df`
- `eappprxy!EapHostPeerFreeEapError` at `0x180027672`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800276df`
- `eappprxy!EapHostPeerSetUIContext` at `0x180027646`
- `eappprxy!EapHostPeerSetUIContext` at `0x180027646`
- `eappprxy!EapHostPeerProcessReceivedPacket` at `0x1800276af`
- `eappprxy!EapHostPeerProcessReceivedPacket` at `0x1800276af`

## string_xrefs

- `0x1800275bd`: `Failed to construct EAP UI context during %hs with error: 0x%x. Failing auth.`

## pseudocode

```c
__int64 __fastcall EapMethodWork(__int64 a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5, __int64 a6)
{
  EapHostPeerResponseAction v8; // edi
  unsigned int v9; // r15d
  int v10; // r13d
  const BYTE *v12; // rdi
  DWORD *v13; // rax
  unsigned int dwReasonCode; // edi
  bool v15; // zf
  const char *v16; // r8
  DWORD v17; // r15d
  EapHostPeerResponseAction pEapOutput; // [rsp+40h] [rbp-C0h] BYREF
  EAP_ERROR *pEapError; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-B0h]
  void *v21; // [rsp+58h] [rbp-A8h]
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
    PrintEapError((int *)"EapHostPeerProcessReceivedPacket", (int *)pEapError);
    if ( dwReasonCode )
    {
      if ( pEapError )
        dwReasonCode = pEapError->dwReasonCode;
      EapHostPeerFreeEapError(pEapError);
      if ( (_QWORD)xmmword_18004D740 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          xmmword_18004D740,
          L"Silently discarding invalid EAP packet.");
      goto LABEL_25;
    }
LABEL_32:
    v8 = pEapOutput;
    return HandleEapResponse(a1, v8, v10, (_BYTE *)a2, v21, v9, a6, a5);
  }
  if ( *(_DWORD *)(a6 + 176) )
  {
    v8 = EapHostPeerResponseResult;
    pEapOutput = EapHostPeerResponseResult;
    v10 = 1;
    return HandleEapResponse(a1, v8, v10, (_BYTE *)a2, v21, v9, a6, a5);
  }
  if ( !*(_DWORD *)(a6 + 188) )
  {
    if ( *(_DWORD *)(a6 + 184) )
    {
LABEL_14:
      dwReasonCode = ConstructEapUserBlobFromRawCredentials((_QWORD *)a6, a1, 1u);
      if ( dwReasonCode )
      {
        if ( (_QWORD)xmmword_18004D740 )
        {
          v15 = *(_DWORD *)(a6 + 180) == 0;
          LOWORD(v22) = 0;
          v16 = "auth retry";
          if ( v15 )
            v16 = "change password";
          FormatRRASErrorString(
            (wchar_t *)&v22,
            L"Failed to construct EAP UI context during %hs with error: 0x%x. Failing auth.",
            v16,
            dwReasonCode);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004D740, &v22);
        }
        return dwReasonCode;
      }
      v13 = *(DWORD **)(a1 + 344);
      v12 = (const BYTE *)(v13 + 1);
      goto LABEL_21;
    }
    if ( !*(_DWORD *)(a6 + 180) )
      return HandleEapResponse(a1, v8, v10, (_BYTE *)a2, v21, v9, a6, a5);
  }
  if ( *(_DWORD *)(a6 + 184) || *(_DWORD *)(a6 + 180) )
    goto LABEL_14;
  if ( *(_DWORD *)(a6 + 192) == *(_DWORD *)(a1 + 376) )
  {
    v12 = *(const BYTE **)(a6 + 200);
    v13 = (DWORD *)(a6 + 208);
LABEL_21:
    v17 = *v13;
    if ( *((_QWORD *)&xmmword_18004D740 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        *((_QWORD *)&xmmword_18004D740 + 1),
        L"Setting new UI Context data",
        0);
    dwReasonCode = EapHostPeerSetUIContext(*(_DWORD *)(a1 + 484), v17, v12, &pEapOutput, &pEapError);
    PrintEapError((int *)"EapHostPeerSetUIContext", (int *)pEapError);
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
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"Out of date data received from UI",
      0);
  return 0;
}

```

## disassembly

```asm
0x180027458  mov     [rsp-8+arg_18], rbx
0x18002745d  push    rbp
0x18002745e  push    rsi
0x18002745f  push    rdi
0x180027460  push    r12
0x180027462  push    r13
0x180027464  push    r14
0x180027466  push    r15
0x180027468  lea     rbp, [rsp-770h]
0x180027470  sub     rsp, 870h
0x180027477  mov     rax, cs:__security_cookie
0x18002747e  xor     rax, rsp
0x180027481  mov     [rbp+7A0h+var_40], rax
0x180027488  mov     r14, [rbp+7A0h+arg_20]
0x18002748f  mov     r12, rdx
0x180027492  mov     rbx, [rbp+7A0h+arg_28]
0x180027499  mov     rsi, rcx
0x18002749c  mov     [rsp+8A0h+var_848], r8
0x1800274a1  lea     rcx, [rsp+8A0h+var_83C]; void *
0x1800274a6  xor     eax, eax
0x1800274a8  mov     [rsp+8A0h+var_850], r9d
0x1800274ad  mov     edi, 6
0x1800274b2  mov     [rsp+8A0h+var_840], eax
0x1800274b6  xor     edx, edx; Val
0x1800274b8  mov     [rsp+8A0h+pEapOutput], edi
0x1800274bc  mov     r8d, 7FCh; Size
0x1800274c2  mov     [rsp+8A0h+pEapError], 0
0x1800274cb  mov     r15d, r9d
0x1800274ce  xor     r13d, r13d
0x1800274d1  call    memset_0
0x1800274d6  xor     r9d, r9d
0x1800274d9  test    rbx, rbx
0x1800274dc  jz      loc_180027686
0x1800274e2  cmp     [rbx+0B0h], r9d
0x1800274e9  jz      short loc_1800274FC
0x1800274eb  lea     edi, [r13+2]
0x1800274ef  mov     [rsp+8A0h+pEapOutput], edi
0x1800274f3  lea     r13d, [r9+1]
0x1800274f7  jmp     loc_18002771F
0x1800274fc  cmp     [rbx+0BCh], r9d
0x180027503  jnz     short loc_18002751B
0x180027505  cmp     [rbx+0B8h], r9d
0x18002750c  jnz     short loc_18002757B
0x18002750e  cmp     [rbx+0B4h], r9d
0x180027515  jz      loc_18002771F
0x18002751b  cmp     [rbx+0B8h], r9d
0x180027522  jnz     short loc_18002757B
0x180027524  cmp     [rbx+0B4h], r9d
0x18002752b  jnz     short loc_18002757B
0x18002752d  mov     eax, [rsi+178h]
0x180027533  cmp     [rbx+0C0h], eax
0x180027539  jz      short loc_180027568
0x18002753b  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180027542  test    rdx, rdx
0x180027545  jz      short loc_180027561
0x180027547  mov     rcx, cs:gRasEapEtwContext
0x18002754e  lea     r8, aOutOfDateDataR; "Out of date data received from UI"
0x180027555  mov     rax, cs:gRasEapTemplateFunc
0x18002755c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027561  xor     eax, eax
0x180027563  jmp     loc_180027748
0x180027568  mov     rdi, [rbx+0C8h]
0x18002756f  lea     rax, [rbx+0D0h]
0x180027576  jmp     loc_180027602
0x18002757b  mov     r8d, 1
0x180027581  mov     rdx, rsi
0x180027584  mov     rcx, rbx
0x180027587  call    ConstructEapUserBlobFromRawCredentials
0x18002758c  xor     r9d, r9d
0x18002758f  mov     edi, eax
0x180027591  test    eax, eax
0x180027593  jz      short loc_1800275F7
0x180027595  cmp     qword ptr cs:xmmword_18004D740, r9
0x18002759c  jz      short loc_1800275F0
0x18002759e  cmp     [rbx+0B4h], r9d
0x1800275a5  lea     rax, aChangePassword; "change password"
0x1800275ac  mov     word ptr [rsp+8A0h+var_840], r9w
0x1800275b2  lea     r8, aAuthRetry; "auth retry"
0x1800275b9  cmovz   r8, rax
0x1800275bd  lea     rdx, aFailedToConstr; "Failed to construct EAP UI context duri"...
0x1800275c4  mov     r9d, edi
0x1800275c7  lea     rcx, [rsp+8A0h+var_840]
0x1800275cc  call    FormatRRASErrorString
0x1800275d1  mov     rdx, qword ptr cs:xmmword_18004D740
0x1800275d8  lea     r8, [rsp+8A0h+var_840]
0x1800275dd  mov     rcx, cs:gRasEapEtwContext
0x1800275e4  mov     rax, cs:gRasEapTemplateFunc
0x1800275eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f0  mov     eax, edi
0x1800275f2  jmp     loc_180027748
0x1800275f7  mov     rax, [rsi+158h]
0x1800275fe  lea     rdi, [rax+4]
0x180027602  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180027609  mov     r15d, [rax]
0x18002760c  test    rdx, rdx
0x18002760f  jz      short loc_18002762B
0x180027611  mov     rcx, cs:gRasEapEtwContext
0x180027618  lea     r8, aSettingNewUiCo; "Setting new UI Context data"
0x18002761f  mov     rax, cs:gRasEapTemplateFunc
0x180027626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002762b  mov     ecx, [rsi+1E4h]; sessionHandle
0x180027631  lea     rax, [rsp+8A0h+pEapError]
0x180027636  lea     r9, [rsp+8A0h+pEapOutput]; pEapOutput
0x18002763b  mov     [rsp+8A0h+ppEapError], rax; ppEapError
0x180027640  mov     r8, rdi; pUIContextData
0x180027643  mov     edx, r15d; dwSizeOfUIContextData
0x180027646  call    cs:__imp_EapHostPeerSetUIContext
0x18002764d  nop     dword ptr [rax+rax+00h]
0x180027652  mov     rdx, [rsp+8A0h+pEapError]
0x180027657  lea     rcx, aEaphostpeerset_1; "EapHostPeerSetUIContext"
0x18002765e  mov     edi, eax
0x180027660  call    PrintEapError
0x180027665  test    edi, edi
0x180027667  jz      loc_180027716
0x18002766d  mov     rcx, [rsp+8A0h+pEapError]; pEapError
0x180027672  call    cs:__imp_EapHostPeerFreeEapError
0x180027679  nop     dword ptr [rax+rax+00h]
0x18002767e  mov     [r14], r13d
0x180027681  jmp     loc_1800275F0
0x180027686  movzx   eax, byte ptr [r12+2]
0x18002768c  lea     r9, [rsp+8A0h+pEapOutput]; pEapOutput
0x180027691  movzx   edx, byte ptr [r12+3]
0x180027697  mov     r8, r12; pReceivePacket
0x18002769a  mov     ecx, [rsi+1E4h]; sessionHandle
0x1800276a0  shl     eax, 8
0x1800276a3  add     edx, eax; cbReceivePacket
0x1800276a5  lea     rax, [rsp+8A0h+pEapError]
0x1800276aa  mov     [rsp+8A0h+ppEapError], rax; ppEapError
0x1800276af  call    cs:__imp_EapHostPeerProcessReceivedPacket
0x1800276b6  nop     dword ptr [rax+rax+00h]
0x1800276bb  mov     rdx, [rsp+8A0h+pEapError]
0x1800276c0  lea     rcx, aEaphostpeerpro; "EapHostPeerProcessReceivedPacket"
0x1800276c7  mov     edi, eax
0x1800276c9  call    PrintEapError
0x1800276ce  test    edi, edi
0x1800276d0  jz      short loc_18002771B
0x1800276d2  mov     rcx, [rsp+8A0h+pEapError]; pEapError
0x1800276d7  test    rcx, rcx
0x1800276da  jz      short loc_1800276DF
0x1800276dc  mov     edi, [rcx+14h]
0x1800276df  call    cs:__imp_EapHostPeerFreeEapError
0x1800276e6  nop     dword ptr [rax+rax+00h]
0x1800276eb  mov     rdx, qword ptr cs:xmmword_18004D740
0x1800276f2  test    rdx, rdx
0x1800276f5  jz      short loc_18002767E
0x1800276f7  mov     rcx, cs:gRasEapEtwContext
0x1800276fe  lea     r8, aSilentlyDiscar_1; "Silently discarding invalid EAP packet."
0x180027705  mov     rax, cs:gRasEapTemplateFunc
0x18002770c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027711  jmp     loc_18002767E
0x180027716  mov     r15d, [rsp+8A0h+var_850]
0x18002771b  mov     edi, [rsp+8A0h+pEapOutput]
0x18002771f  mov     rax, [rsp+8A0h+var_848]
0x180027724  mov     r9, r12
0x180027727  mov     [rsp+8A0h+var_868], r14
0x18002772c  mov     r8d, r13d
0x18002772f  mov     [rsp+8A0h+var_870], rbx
0x180027734  mov     edx, edi
0x180027736  mov     [rsp+8A0h+var_878], r15d
0x18002773b  mov     rcx, rsi
0x18002773e  mov     [rsp+8A0h+ppEapError], rax
0x180027743  call    HandleEapResponse
0x180027748  mov     rcx, [rbp+7A0h+var_40]
0x18002774f  xor     rcx, rsp; StackCookie
0x180027752  call    __security_check_cookie
0x180027757  mov     rbx, [rsp+8A0h+arg_18]
0x18002775f  add     rsp, 870h
0x180027766  pop     r15
0x180027768  pop     r14
0x18002776a  pop     r13
0x18002776c  pop     r12
0x18002776e  pop     rdi
0x18002776f  pop     rsi
0x180027770  pop     rbp
0x180027771  retn
```

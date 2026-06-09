# RasGetEapHostAuthResult

- ea: `0x180029244`
- end: `0x180029531`
- name: `RasGetEapHostAuthResult`
- size: `749`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180028964`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002881c`
- `0x180028c68`
- `0x180029244`
- `0x18002b0dc`
- `0x18002bdf4`
- `0x180034010`

## import_xrefs

- `eappprxy!EapHostPeerFreeEapError` at `0x180029319`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029319`
- `eappprxy!EapHostPeerGetResult` at `0x1800292f5`
- `eappprxy!EapHostPeerGetResult` at `0x1800292f5`

## string_xrefs

- `0x1800293b0`: `EAP Authentication complete :).`

## pseudocode

```c
__int64 __fastcall RasGetEapHostAuthResult(__int64 a1, int a2, __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r8
  EAP_ATTRIBUTES *pAttribArray; // rdx
  DWORD dwWinError; // ecx
  unsigned int v10; // eax
  bool v11; // zf
  __int64 v12; // rdx
  EAP_ERROR *ppEapError; // [rsp+20h] [rbp-E0h] BYREF
  EapHostPeerMethodResult ppResult; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"RasGetEapHostAuthResult -- Entering.");
  ppEapError = 0;
  memset_0(&ppResult, 0, sizeof(ppResult));
  if ( a1 && a3 )
  {
    v6 = EapHostPeerGetResult(
           *(_DWORD *)(a1 + 484),
           (EapHostPeerMethodResultReason)(a2 != 0
                                         ? EapHostPeerMethodResultAltSuccessReceived
                                         : EapHostPeerMethodResultFromMethod),
           &ppResult,
           &ppEapError);
    PrintEapError((int *)"EapHostPeerGetResult", (int *)ppEapError);
    EapHostPeerFreeEapError(ppEapError);
    if ( !v6 )
    {
      pAttribArray = ppResult.pAttribArray;
      *(_DWORD *)a3 = 1;
      if ( pAttribArray )
      {
        v6 = ConvertEapAttributesToRasAttributes((_QWORD *)(a3 + 288), (__int64)pAttribArray);
        if ( v6 )
        {
          if ( (_QWORD)xmmword_18004D740 )
          {
            LOWORD(v16) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v16,
              L"ConvertEapAttributesToRasAttributes returned: 0x%x. Mapping to NO_ERROR as this is non fatal.",
              v6);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(
              gRasEapEtwContext,
              xmmword_18004D740,
              &v16);
          }
          v6 = 0;
        }
      }
      if ( ppResult.fIsSuccess )
      {
        if ( *((_QWORD *)&xmmword_18004D740 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            *((_QWORD *)&xmmword_18004D740 + 1),
            L"EAP Authentication complete :).");
        if ( ppResult.fSaveUserData )
        {
          *(_DWORD *)(a3 + 364) = ppResult.fSaveUserData;
          *(_QWORD *)(a3 + 368) = ppResult.pUserData;
          *(_DWORD *)(a3 + 376) = ppResult.dwSizeofUserData;
        }
        if ( ppResult.fSaveConnectionData )
        {
          *(_DWORD *)(a3 + 384) = ppResult.fSaveConnectionData;
          *(_QWORD *)(a3 + 392) = ppResult.pConnectionData;
          *(_DWORD *)(a3 + 400) = ppResult.dwSizeofConnectionData;
        }
        *(_DWORD *)(a3 + 360) = ppResult.pEapMethodInfo->eaptype.eapType.type;
        *(_DWORD *)(a3 + 8) = 0;
      }
      else
      {
        if ( ppResult.pEapError )
          dwWinError = ppResult.pEapError->dwWinError;
        else
          dwWinError = ppResult.dwFailureReasonCode;
        v10 = MapEapHostErrorToRasError(dwWinError, (__int64)pAttribArray, v7);
        v11 = (_QWORD)xmmword_18004D740 == 0;
        *(_DWORD *)(a3 + 8) = v10;
        if ( !v11 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v16,
            L"EAP Authentication failed with error: Internal = 0x%x, External = 0x%x.",
            ppResult.dwFailureReasonCode,
            v10);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004D740, &v16);
        }
      }
      *(_DWORD *)(a1 + 500) = 1;
      *(_DWORD *)(a3 + 416) = 1;
      if ( *((_QWORD *)&xmmword_18004D740 + 1) )
      {
        LOWORD(v16) = 0;
        FormatRRASErrorString((wchar_t *)&v16, L"RasGetEapHostAuthResult -- Leaving: 0x%x.", 0);
        v12 = *((_QWORD *)&xmmword_18004D740 + 1);
LABEL_30:
        ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v12, &v16);
        return v6;
      }
      return v6;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (_QWORD)xmmword_18004D740 )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString((wchar_t *)&v16, L"RasGetEapHostAuthResult -- Leaving: 0x%x.", v6);
    v12 = xmmword_18004D740;
    goto LABEL_30;
  }
  return v6;
}

```

## disassembly

```asm
0x180029244  mov     [rsp-8+arg_8], rbx
0x180029249  push    rbp
0x18002924a  push    rsi
0x18002924b  push    rdi
0x18002924c  lea     rbp, [rsp-790h]
0x180029254  sub     rsp, 890h
0x18002925b  mov     rax, cs:__security_cookie
0x180029262  xor     rax, rsp
0x180029265  mov     [rbp+7A0h+var_20], rax
0x18002926c  mov     rdi, r8
0x18002926f  mov     ebx, edx
0x180029271  mov     rsi, rcx
0x180029274  xor     eax, eax
0x180029276  xor     edx, edx; Val
0x180029278  mov     [rbp+7A0h+var_820], eax
0x18002927b  mov     r8d, 7FCh; Size
0x180029281  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180029285  call    memset_0
0x18002928a  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180029291  test    rdx, rdx
0x180029294  jz      short loc_1800292B0
0x180029296  mov     rcx, cs:gRasEapEtwContext
0x18002929d  lea     r8, aRasgeteaphosta_0; "RasGetEapHostAuthResult -- Entering."
0x1800292a4  mov     rax, cs:gRasEapTemplateFunc
0x1800292ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292b0  xor     edx, edx; Val
0x1800292b2  mov     [rsp+8A0h+ppEapError], 0
0x1800292bb  lea     rcx, [rsp+8A0h+ppResult]; void *
0x1800292c0  lea     r8d, [rdx+48h]; Size
0x1800292c4  call    memset_0
0x1800292c9  test    rsi, rsi
0x1800292cc  jz      loc_1800294C6
0x1800292d2  test    rdi, rdi
0x1800292d5  jz      loc_1800294C6
0x1800292db  mov     ecx, [rsi+1E4h]; sessionHandle
0x1800292e1  lea     r9, [rsp+8A0h+ppEapError]; ppEapError
0x1800292e6  neg     ebx
0x1800292e8  lea     r8, [rsp+8A0h+ppResult]; ppResult
0x1800292ed  sbb     edx, edx
0x1800292ef  and     edx, 0FFFFFFFEh
0x1800292f2  add     edx, 3; reason
0x1800292f5  call    cs:__imp_EapHostPeerGetResult
0x1800292fc  nop     dword ptr [rax+rax+00h]
0x180029301  mov     rdx, [rsp+8A0h+ppEapError]
0x180029306  lea     rcx, aEaphostpeerget; "EapHostPeerGetResult"
0x18002930d  mov     ebx, eax
0x18002930f  call    PrintEapError
0x180029314  mov     rcx, [rsp+8A0h+ppEapError]; pEapError
0x180029319  call    cs:__imp_EapHostPeerFreeEapError
0x180029320  nop     dword ptr [rax+rax+00h]
0x180029325  test    ebx, ebx
0x180029327  jnz     loc_1800294CB
0x18002932d  mov     rdx, [rsp+8A0h+ppResult.pAttribArray]
0x180029332  mov     dword ptr [rdi], 1
0x180029338  test    rdx, rdx
0x18002933b  jz      short loc_180029392
0x18002933d  lea     rcx, [rdi+120h]
0x180029344  call    ConvertEapAttributesToRasAttributes
0x180029349  mov     ebx, eax
0x18002934b  test    eax, eax
0x18002934d  jz      short loc_180029392
0x18002934f  cmp     qword ptr cs:xmmword_18004D740, 0
0x180029357  jz      short loc_180029390
0x180029359  xor     eax, eax
0x18002935b  lea     rdx, aConverteapattr; "ConvertEapAttributesToRasAttributes ret"...
0x180029362  mov     r8d, ebx
0x180029365  mov     word ptr [rbp+7A0h+var_820], ax
0x180029369  lea     rcx, [rbp+7A0h+var_820]
0x18002936d  call    FormatRRASErrorString
0x180029372  mov     rdx, qword ptr cs:xmmword_18004D740
0x180029379  lea     r8, [rbp+7A0h+var_820]
0x18002937d  mov     rcx, cs:gRasEapEtwContext
0x180029384  mov     rax, cs:gRasEapTemplateFunc
0x18002938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029390  xor     ebx, ebx
0x180029392  cmp     [rsp+8A0h+ppResult.fIsSuccess], 0
0x180029397  jz      loc_180029422
0x18002939d  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800293a4  test    rdx, rdx
0x1800293a7  jz      short loc_1800293C3
0x1800293a9  mov     rcx, cs:gRasEapEtwContext
0x1800293b0  lea     r8, aEapAuthenticat; "EAP Authentication complete :)."
0x1800293b7  mov     rax, cs:gRasEapTemplateFunc
0x1800293be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293c3  mov     eax, [rsp+8A0h+ppResult.fSaveUserData]
0x1800293c7  test    eax, eax
0x1800293c9  jz      short loc_1800293E7
0x1800293cb  mov     [rdi+16Ch], eax
0x1800293d1  mov     rax, [rsp+8A0h+ppResult.pUserData]
0x1800293d6  mov     [rdi+170h], rax
0x1800293dd  mov     eax, [rsp+8A0h+ppResult.dwSizeofUserData]
0x1800293e1  mov     [rdi+178h], eax
0x1800293e7  mov     eax, [rsp+8A0h+ppResult.fSaveConnectionData]
0x1800293eb  test    eax, eax
0x1800293ed  jz      short loc_18002940B
0x1800293ef  mov     [rdi+180h], eax
0x1800293f5  mov     rax, [rsp+8A0h+ppResult.pConnectionData]
0x1800293fa  mov     [rdi+188h], rax
0x180029401  mov     eax, [rsp+8A0h+ppResult.dwSizeofConnectionData]
0x180029405  mov     [rdi+190h], eax
0x18002940b  mov     rax, [rsp+8A0h+ppResult.pEapMethodInfo]
0x180029410  movzx   ecx, byte ptr [rax]
0x180029413  mov     [rdi+168h], ecx
0x180029419  mov     dword ptr [rdi+8], 0
0x180029420  jmp     short loc_180029482
0x180029422  mov     rax, [rsp+8A0h+ppResult.pEapError]
0x180029427  test    rax, rax
0x18002942a  jz      short loc_180029430
0x18002942c  mov     ecx, [rax]
0x18002942e  jmp     short loc_180029434
0x180029430  mov     ecx, [rsp+8A0h+ppResult.dwFailureReasonCode]
0x180029434  call    MapEapHostErrorToRasError
0x180029439  cmp     qword ptr cs:xmmword_18004D740, 0
0x180029441  mov     [rdi+8], eax
0x180029444  jz      short loc_180029482
0x180029446  mov     r8d, [rsp+8A0h+ppResult.dwFailureReasonCode]
0x18002944b  lea     rdx, aEapAuthenticat_0; "EAP Authentication failed with error: I"...
0x180029452  xor     ecx, ecx
0x180029454  mov     r9d, eax
0x180029457  mov     word ptr [rbp+7A0h+var_820], cx
0x18002945b  lea     rcx, [rbp+7A0h+var_820]
0x18002945f  call    FormatRRASErrorString
0x180029464  mov     rdx, qword ptr cs:xmmword_18004D740
0x18002946b  lea     r8, [rbp+7A0h+var_820]
0x18002946f  mov     rcx, cs:gRasEapEtwContext
0x180029476  mov     rax, cs:gRasEapTemplateFunc
0x18002947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029482  mov     dword ptr [rsi+1F4h], 1
0x18002948c  mov     dword ptr [rdi+1A0h], 1
0x180029496  test    ebx, ebx
0x180029498  jnz     short loc_1800294CB
0x18002949a  cmp     qword ptr cs:xmmword_18004D740+8, 0
0x1800294a2  jz      short loc_18002950C
0x1800294a4  xor     eax, eax
0x1800294a6  lea     rdx, aRasgeteaphosta; "RasGetEapHostAuthResult -- Leaving: 0x%"...
0x1800294ad  xor     r8d, r8d
0x1800294b0  mov     word ptr [rbp+7A0h+var_820], ax
0x1800294b4  lea     rcx, [rbp+7A0h+var_820]
0x1800294b8  call    FormatRRASErrorString
0x1800294bd  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800294c4  jmp     short loc_1800294F5
0x1800294c6  mov     ebx, 57h ; 'W'
0x1800294cb  cmp     qword ptr cs:xmmword_18004D740, 0
0x1800294d3  jz      short loc_18002950C
0x1800294d5  xor     eax, eax
0x1800294d7  lea     rdx, aRasgeteaphosta; "RasGetEapHostAuthResult -- Leaving: 0x%"...
0x1800294de  mov     r8d, ebx
0x1800294e1  mov     word ptr [rbp+7A0h+var_820], ax
0x1800294e5  lea     rcx, [rbp+7A0h+var_820]
0x1800294e9  call    FormatRRASErrorString
0x1800294ee  mov     rdx, qword ptr cs:xmmword_18004D740
0x1800294f5  mov     rcx, cs:gRasEapEtwContext
0x1800294fc  lea     r8, [rbp+7A0h+var_820]
0x180029500  mov     rax, cs:gRasEapTemplateFunc
0x180029507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002950c  mov     eax, ebx
0x18002950e  mov     rcx, [rbp+7A0h+var_20]
0x180029515  xor     rcx, rsp; StackCookie
0x180029518  call    __security_check_cookie
0x18002951d  mov     rbx, [rsp+8A0h+arg_8]
0x180029525  add     rsp, 890h
0x18002952c  pop     rdi
0x18002952d  pop     rsi
0x18002952e  pop     rbp
0x18002952f  retn
```

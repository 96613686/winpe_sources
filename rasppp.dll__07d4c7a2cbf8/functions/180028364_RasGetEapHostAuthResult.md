# RasGetEapHostAuthResult

- ea: `0x180028364`
- end: `0x180028644`
- name: `RasGetEapHostAuthResult`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180027aa4`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180027964`
- `0x180027da8`
- `0x180028364`
- `0x18002a138`
- `0x18002adbc`
- `0x180033010`

## import_xrefs

- `eappprxy!EapHostPeerFreeEapError` at `0x180028433`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028433`
- `eappprxy!EapHostPeerGetResult` at `0x180028415`
- `eappprxy!EapHostPeerGetResult` at `0x180028415`

## string_xrefs

- `0x1800284c4`: `EAP Authentication complete :).`

## pseudocode

```c
__int64 __fastcall RasGetEapHostAuthResult(__int64 a1, int a2, __int64 a3)
{
  DWORD v6; // ebx
  EAP_ATTRIBUTES *pAttribArray; // rdx
  __int64 dwWinError; // rcx
  unsigned int v9; // eax
  bool v10; // zf
  __int64 v11; // rdx
  EAP_ERROR *ppEapError; // [rsp+20h] [rbp-E0h] BYREF
  EapHostPeerMethodResult ppResult; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
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
    PrintEapError("EapHostPeerGetResult", ppEapError);
    EapHostPeerFreeEapError(ppEapError);
    if ( !v6 )
    {
      pAttribArray = ppResult.pAttribArray;
      *(_DWORD *)a3 = 1;
      if ( pAttribArray )
      {
        v6 = ConvertEapAttributesToRasAttributes(a3 + 288);
        if ( v6 )
        {
          if ( (_QWORD)xmmword_18004C740 )
          {
            LOWORD(v15) = 0;
            FormatRRASErrorString(
              &v15,
              L"ConvertEapAttributesToRasAttributes returned: 0x%x. Mapping to NO_ERROR as this is non fatal.",
              v6);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(
              gRasEapEtwContext,
              xmmword_18004C740,
              &v15);
          }
          v6 = 0;
        }
      }
      if ( ppResult.fIsSuccess )
      {
        if ( *((_QWORD *)&xmmword_18004C740 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            *((_QWORD *)&xmmword_18004C740 + 1),
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
        v9 = MapEapHostErrorToRasError(dwWinError);
        v10 = (_QWORD)xmmword_18004C740 == 0;
        *(_DWORD *)(a3 + 8) = v9;
        if ( !v10 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(
            &v15,
            L"EAP Authentication failed with error: Internal = 0x%x, External = 0x%x.",
            ppResult.dwFailureReasonCode,
            v9);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004C740, &v15);
        }
      }
      *(_DWORD *)(a1 + 500) = 1;
      *(_DWORD *)(a3 + 416) = 1;
      if ( *((_QWORD *)&xmmword_18004C740 + 1) )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"RasGetEapHostAuthResult -- Leaving: 0x%x.", 0);
        v11 = *((_QWORD *)&xmmword_18004C740 + 1);
LABEL_30:
        ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v11, &v15);
        return v6;
      }
      return v6;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (_QWORD)xmmword_18004C740 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"RasGetEapHostAuthResult -- Leaving: 0x%x.", v6);
    v11 = xmmword_18004C740;
    goto LABEL_30;
  }
  return v6;
}

```

## disassembly

```asm
0x180028364  mov     [rsp-8+arg_8], rbx
0x180028369  push    rbp
0x18002836a  push    rsi
0x18002836b  push    rdi
0x18002836c  lea     rbp, [rsp-790h]
0x180028374  sub     rsp, 890h
0x18002837b  mov     rax, cs:__security_cookie
0x180028382  xor     rax, rsp
0x180028385  mov     [rbp+7A0h+var_20], rax
0x18002838c  mov     rdi, r8
0x18002838f  mov     ebx, edx
0x180028391  mov     rsi, rcx
0x180028394  xor     eax, eax
0x180028396  xor     edx, edx; Val
0x180028398  mov     [rbp+7A0h+var_820], eax
0x18002839b  mov     r8d, 7FCh; Size
0x1800283a1  lea     rcx, [rbp+7A0h+var_81C]; void *
0x1800283a5  call    memset_0
0x1800283aa  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800283b1  test    rdx, rdx
0x1800283b4  jz      short loc_1800283D0
0x1800283b6  mov     rcx, cs:gRasEapEtwContext
0x1800283bd  lea     r8, aRasgeteaphosta_0; "RasGetEapHostAuthResult -- Entering."
0x1800283c4  mov     rax, cs:gRasEapTemplateFunc
0x1800283cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283d0  xor     edx, edx; Val
0x1800283d2  mov     [rsp+8A0h+ppEapError], 0
0x1800283db  lea     rcx, [rsp+8A0h+ppResult]; void *
0x1800283e0  lea     r8d, [rdx+48h]; Size
0x1800283e4  call    memset_0
0x1800283e9  test    rsi, rsi
0x1800283ec  jz      loc_1800285DA
0x1800283f2  test    rdi, rdi
0x1800283f5  jz      loc_1800285DA
0x1800283fb  mov     ecx, [rsi+1E4h]; sessionHandle
0x180028401  lea     r9, [rsp+8A0h+ppEapError]; ppEapError
0x180028406  neg     ebx
0x180028408  lea     r8, [rsp+8A0h+ppResult]; ppResult
0x18002840d  sbb     edx, edx
0x18002840f  and     edx, 0FFFFFFFEh
0x180028412  add     edx, 3; reason
0x180028415  call    cs:__imp_EapHostPeerGetResult
0x18002841b  mov     rdx, [rsp+8A0h+ppEapError]
0x180028420  lea     rcx, aEaphostpeerget; "EapHostPeerGetResult"
0x180028427  mov     ebx, eax
0x180028429  call    PrintEapError
0x18002842e  mov     rcx, [rsp+8A0h+ppEapError]; pEapError
0x180028433  call    cs:__imp_EapHostPeerFreeEapError
0x180028439  test    ebx, ebx
0x18002843b  jnz     loc_1800285DF
0x180028441  mov     rdx, [rsp+8A0h+ppResult.pAttribArray]
0x180028446  mov     dword ptr [rdi], 1
0x18002844c  test    rdx, rdx
0x18002844f  jz      short loc_1800284A6
0x180028451  lea     rcx, [rdi+120h]
0x180028458  call    ConvertEapAttributesToRasAttributes
0x18002845d  mov     ebx, eax
0x18002845f  test    eax, eax
0x180028461  jz      short loc_1800284A6
0x180028463  cmp     qword ptr cs:xmmword_18004C740, 0
0x18002846b  jz      short loc_1800284A4
0x18002846d  xor     eax, eax
0x18002846f  lea     rdx, aConverteapattr; "ConvertEapAttributesToRasAttributes ret"...
0x180028476  mov     r8d, ebx
0x180028479  mov     word ptr [rbp+7A0h+var_820], ax
0x18002847d  lea     rcx, [rbp+7A0h+var_820]
0x180028481  call    FormatRRASErrorString
0x180028486  mov     rdx, qword ptr cs:xmmword_18004C740
0x18002848d  lea     r8, [rbp+7A0h+var_820]
0x180028491  mov     rcx, cs:gRasEapEtwContext
0x180028498  mov     rax, cs:gRasEapTemplateFunc
0x18002849f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284a4  xor     ebx, ebx
0x1800284a6  cmp     [rsp+8A0h+ppResult.fIsSuccess], 0
0x1800284ab  jz      loc_180028536
0x1800284b1  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800284b8  test    rdx, rdx
0x1800284bb  jz      short loc_1800284D7
0x1800284bd  mov     rcx, cs:gRasEapEtwContext
0x1800284c4  lea     r8, aEapAuthenticat; "EAP Authentication complete :)."
0x1800284cb  mov     rax, cs:gRasEapTemplateFunc
0x1800284d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d7  mov     eax, [rsp+8A0h+ppResult.fSaveUserData]
0x1800284db  test    eax, eax
0x1800284dd  jz      short loc_1800284FB
0x1800284df  mov     [rdi+16Ch], eax
0x1800284e5  mov     rax, [rsp+8A0h+ppResult.pUserData]
0x1800284ea  mov     [rdi+170h], rax
0x1800284f1  mov     eax, [rsp+8A0h+ppResult.dwSizeofUserData]
0x1800284f5  mov     [rdi+178h], eax
0x1800284fb  mov     eax, [rsp+8A0h+ppResult.fSaveConnectionData]
0x1800284ff  test    eax, eax
0x180028501  jz      short loc_18002851F
0x180028503  mov     [rdi+180h], eax
0x180028509  mov     rax, [rsp+8A0h+ppResult.pConnectionData]
0x18002850e  mov     [rdi+188h], rax
0x180028515  mov     eax, [rsp+8A0h+ppResult.dwSizeofConnectionData]
0x180028519  mov     [rdi+190h], eax
0x18002851f  mov     rax, [rsp+8A0h+ppResult.pEapMethodInfo]
0x180028524  movzx   ecx, byte ptr [rax]
0x180028527  mov     [rdi+168h], ecx
0x18002852d  mov     dword ptr [rdi+8], 0
0x180028534  jmp     short loc_180028596
0x180028536  mov     rax, [rsp+8A0h+ppResult.pEapError]
0x18002853b  test    rax, rax
0x18002853e  jz      short loc_180028544
0x180028540  mov     ecx, [rax]
0x180028542  jmp     short loc_180028548
0x180028544  mov     ecx, [rsp+8A0h+ppResult.dwFailureReasonCode]
0x180028548  call    MapEapHostErrorToRasError
0x18002854d  cmp     qword ptr cs:xmmword_18004C740, 0
0x180028555  mov     [rdi+8], eax
0x180028558  jz      short loc_180028596
0x18002855a  mov     r8d, [rsp+8A0h+ppResult.dwFailureReasonCode]
0x18002855f  lea     rdx, aEapAuthenticat_0; "EAP Authentication failed with error: I"...
0x180028566  xor     ecx, ecx
0x180028568  mov     r9d, eax
0x18002856b  mov     word ptr [rbp+7A0h+var_820], cx
0x18002856f  lea     rcx, [rbp+7A0h+var_820]
0x180028573  call    FormatRRASErrorString
0x180028578  mov     rdx, qword ptr cs:xmmword_18004C740
0x18002857f  lea     r8, [rbp+7A0h+var_820]
0x180028583  mov     rcx, cs:gRasEapEtwContext
0x18002858a  mov     rax, cs:gRasEapTemplateFunc
0x180028591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028596  mov     dword ptr [rsi+1F4h], 1
0x1800285a0  mov     dword ptr [rdi+1A0h], 1
0x1800285aa  test    ebx, ebx
0x1800285ac  jnz     short loc_1800285DF
0x1800285ae  cmp     qword ptr cs:xmmword_18004C740+8, 0
0x1800285b6  jz      short loc_180028620
0x1800285b8  xor     eax, eax
0x1800285ba  lea     rdx, aRasgeteaphosta; "RasGetEapHostAuthResult -- Leaving: 0x%"...
0x1800285c1  xor     r8d, r8d
0x1800285c4  mov     word ptr [rbp+7A0h+var_820], ax
0x1800285c8  lea     rcx, [rbp+7A0h+var_820]
0x1800285cc  call    FormatRRASErrorString
0x1800285d1  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800285d8  jmp     short loc_180028609
0x1800285da  mov     ebx, 57h ; 'W'
0x1800285df  cmp     qword ptr cs:xmmword_18004C740, 0
0x1800285e7  jz      short loc_180028620
0x1800285e9  xor     eax, eax
0x1800285eb  lea     rdx, aRasgeteaphosta; "RasGetEapHostAuthResult -- Leaving: 0x%"...
0x1800285f2  mov     r8d, ebx
0x1800285f5  mov     word ptr [rbp+7A0h+var_820], ax
0x1800285f9  lea     rcx, [rbp+7A0h+var_820]
0x1800285fd  call    FormatRRASErrorString
0x180028602  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028609  mov     rcx, cs:gRasEapEtwContext
0x180028610  lea     r8, [rbp+7A0h+var_820]
0x180028614  mov     rax, cs:gRasEapTemplateFunc
0x18002861b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028620  mov     eax, ebx
0x180028622  mov     rcx, [rbp+7A0h+var_20]
0x180028629  xor     rcx, rsp; StackCookie
0x18002862c  call    __security_check_cookie
0x180028631  mov     rbx, [rsp+8A0h+arg_8]
0x180028639  add     rsp, 890h
0x180028640  pop     rdi
0x180028641  pop     rsi
0x180028642  pop     rbp
0x180028643  retn
```

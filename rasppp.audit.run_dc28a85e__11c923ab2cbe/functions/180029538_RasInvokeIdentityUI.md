# RasInvokeIdentityUI

- ea: `0x180029538`
- end: `0x18002983b`
- name: `RasInvokeIdentityUI`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180028964`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180028c68`
- `0x180028d20`
- `0x180029538`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002970c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002970c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029724`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029654`
- `eappprxy!EapHostPeerFreeEapError` at `0x180029654`
- `eappprxy!EapHostPeerGetUIContext` at `0x180029630`
- `eappprxy!EapHostPeerGetUIContext` at `0x180029630`

## string_xrefs

- `0x1800295e6`: `EAP method wants to bring up UI on the server side. This is not a valid operation. Returning error: 0x%.x`

## pseudocode

```c
__int64 __fastcall RasInvokeIdentityUI(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  __int64 v7; // rax
  DWORD UIContext; // ebx
  void *v9; // rcx
  HLOCAL v10; // rax
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  DWORD pdwSizeOfUIContextData; // [rsp+20h] [rbp-E0h] BYREF
  BYTE *ppUIContextData; // [rsp+28h] [rbp-D8h] BYREF
  EAP_ERROR *ppEapError; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[2044]; // [rsp+44h] [rbp-BCh] BYREF

  pdwSizeOfUIContextData = 0;
  ppUIContextData = 0;
  ppEapError = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v7 = *((_QWORD *)&xmmword_18004D740 + 1);
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"RasInvokeIdentityUI -- Entering.");
    v7 = *((_QWORD *)&xmmword_18004D740 + 1);
  }
  if ( *(_DWORD *)(a1 + 16) )
  {
    UIContext = 703;
    if ( v7 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(
        &v18,
        L"EAP method wants to bring up UI on the server side. This is not a valid operation. Returning error: 0x%.x",
        703);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        *((_QWORD *)&xmmword_18004D740 + 1),
        &v18);
    }
    goto LABEL_21;
  }
  UIContext = EapHostPeerGetUIContext(*(_DWORD *)(a1 + 484), &pdwSizeOfUIContextData, &ppUIContextData, &ppEapError);
  PrintEapError("EapHostPeerGetUIContext", ppEapError);
  EapHostPeerFreeEapError(ppEapError);
  if ( UIContext )
  {
    if ( (_QWORD)xmmword_18004D740 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        xmmword_18004D740,
        L"RasInvokeIdentityUI: Unable to retreive UI context. Using NULL context.");
    ppUIContextData = 0;
    pdwSizeOfUIContextData = 0;
  }
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"EAP method wants to invoke interactive UI.");
  v9 = *(void **)(a1 + 504);
  if ( v9 )
  {
    LocalFree(v9);
    *(_QWORD *)(a1 + 504) = 0;
  }
  *(_DWORD *)(a1 + 512) = 0;
  *(_DWORD *)(a6 + 352) = 0;
  *(_QWORD *)(a6 + 344) = 0;
  if ( ppUIContextData && pdwSizeOfUIContextData )
  {
    v10 = LocalAlloc(0x40u, pdwSizeOfUIContextData);
    *(_QWORD *)(a1 + 504) = v10;
    if ( v10 )
    {
      memcpy_0(v10, ppUIContextData, pdwSizeOfUIContextData);
      *(_DWORD *)(a1 + 512) = pdwSizeOfUIContextData;
      UIContext = ProcessInteractiveUIInformation(a1, v12, a6);
    }
    else
    {
      LastError = GetLastError();
      UIContext = LastError;
      if ( (_QWORD)xmmword_18004D740 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Failed to allocate memory for caching UI context with error: 0x%x.", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004D740, &v18);
      }
    }
  }
  if ( UIContext )
  {
LABEL_21:
    if ( (_QWORD)xmmword_18004D740 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"RasInvokeIdentityUI -- Leaving: 0x%x.", UIContext);
      v13 = xmmword_18004D740;
LABEL_25:
      ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v13, &v18);
      return UIContext;
    }
    return UIContext;
  }
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"RasInvokeIdentityUI -- Leaving: 0x%x.", 0);
    v13 = *((_QWORD *)&xmmword_18004D740 + 1);
    goto LABEL_25;
  }
  return UIContext;
}

```

## disassembly

```asm
0x180029538  mov     [rsp-8+arg_8], rbx
0x18002953d  mov     [rsp-8+arg_10], rsi
0x180029542  push    rbp
0x180029543  push    rdi
0x180029544  push    r14
0x180029546  lea     rbp, [rsp-750h]
0x18002954e  sub     rsp, 850h
0x180029555  mov     rax, cs:__security_cookie
0x18002955c  xor     rax, rsp
0x18002955f  mov     [rbp+760h+var_20], rax
0x180029566  mov     rsi, [rbp+760h+arg_28]
0x18002956d  xor     r14d, r14d
0x180029570  mov     rdi, rcx
0x180029573  mov     [rsp+860h+pdwSizeOfUIContextData], r14d
0x180029578  lea     rcx, [rsp+860h+var_81C]; void *
0x18002957d  mov     [rsp+860h+ppUIContextData], r14
0x180029582  xor     edx, edx; Val
0x180029584  mov     [rsp+860h+ppEapError], r14
0x180029589  mov     r8d, 7FCh; Size
0x18002958f  mov     [rsp+860h+var_820], r14d
0x180029594  call    memset_0
0x180029599  mov     rax, qword ptr cs:xmmword_18004D740+8
0x1800295a0  test    rax, rax
0x1800295a3  jz      short loc_1800295C9
0x1800295a5  mov     rcx, cs:gRasEapEtwContext
0x1800295ac  lea     r8, aRasinvokeident_0; "RasInvokeIdentityUI -- Entering."
0x1800295b3  mov     rdx, rax
0x1800295b6  mov     rax, cs:gRasEapTemplateFunc
0x1800295bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295c2  mov     rax, qword ptr cs:xmmword_18004D740+8
0x1800295c9  cmp     [rdi+10h], r14d
0x1800295cd  jz      short loc_18002961B
0x1800295cf  mov     ebx, 2BFh
0x1800295d4  test    rax, rax
0x1800295d7  jz      loc_1800297A3
0x1800295dd  mov     r8d, ebx
0x1800295e0  mov     word ptr [rsp+860h+var_820], r14w
0x1800295e6  lea     rdx, aEapMethodWants; "EAP method wants to bring up UI on the "...
0x1800295ed  lea     rcx, [rsp+860h+var_820]
0x1800295f2  call    FormatRRASErrorString
0x1800295f7  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800295fe  lea     r8, [rsp+860h+var_820]
0x180029603  mov     rcx, cs:gRasEapEtwContext
0x18002960a  mov     rax, cs:gRasEapTemplateFunc
0x180029611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029616  jmp     loc_1800297A3
0x18002961b  mov     ecx, [rdi+1E4h]; sessionHandle
0x180029621  lea     r9, [rsp+860h+ppEapError]; ppEapError
0x180029626  lea     r8, [rsp+860h+ppUIContextData]; ppUIContextData
0x18002962b  lea     rdx, [rsp+860h+pdwSizeOfUIContextData]; pdwSizeOfUIContextData
0x180029630  call    cs:__imp_EapHostPeerGetUIContext
0x180029637  nop     dword ptr [rax+rax+00h]
0x18002963c  mov     rdx, [rsp+860h+ppEapError]
0x180029641  lea     rcx, aEaphostpeerget_0; "EapHostPeerGetUIContext"
0x180029648  mov     ebx, eax
0x18002964a  call    PrintEapError
0x18002964f  mov     rcx, [rsp+860h+ppEapError]; pEapError
0x180029654  call    cs:__imp_EapHostPeerFreeEapError
0x18002965b  nop     dword ptr [rax+rax+00h]
0x180029660  test    ebx, ebx
0x180029662  jz      short loc_180029694
0x180029664  mov     rdx, qword ptr cs:xmmword_18004D740
0x18002966b  test    rdx, rdx
0x18002966e  jz      short loc_18002968A
0x180029670  mov     rcx, cs:gRasEapEtwContext
0x180029677  lea     r8, aRasinvokeident_1; "RasInvokeIdentityUI: Unable to retreive"...
0x18002967e  mov     rax, cs:gRasEapTemplateFunc
0x180029685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002968a  mov     [rsp+860h+ppUIContextData], r14
0x18002968f  mov     [rsp+860h+pdwSizeOfUIContextData], r14d
0x180029694  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x18002969b  test    rdx, rdx
0x18002969e  jz      short loc_1800296BA
0x1800296a0  mov     rcx, cs:gRasEapEtwContext
0x1800296a7  lea     r8, aEapMethodWants_0; "EAP method wants to invoke interactive "...
0x1800296ae  mov     rax, cs:gRasEapTemplateFunc
0x1800296b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296ba  mov     rcx, [rdi+1F8h]; hMem
0x1800296c1  test    rcx, rcx
0x1800296c4  jz      short loc_1800296D9
0x1800296c6  call    cs:__imp_LocalFree
0x1800296cd  nop     dword ptr [rax+rax+00h]
0x1800296d2  mov     [rdi+1F8h], r14
0x1800296d9  mov     [rdi+200h], r14d
0x1800296e0  mov     [rsi+160h], r14d
0x1800296e7  mov     [rsi+158h], r14
0x1800296ee  cmp     [rsp+860h+ppUIContextData], r14
0x1800296f3  jz      loc_18002979F
0x1800296f9  mov     eax, [rsp+860h+pdwSizeOfUIContextData]
0x1800296fd  test    eax, eax
0x1800296ff  jz      loc_18002979F
0x180029705  mov     edx, eax; uBytes
0x180029707  mov     ecx, 40h ; '@'; uFlags
0x18002970c  call    cs:__imp_LocalAlloc
0x180029713  nop     dword ptr [rax+rax+00h]
0x180029718  mov     [rdi+1F8h], rax
0x18002971f  test    rax, rax
0x180029722  jnz     short loc_180029776
0x180029724  call    cs:__imp_GetLastError
0x18002972b  nop     dword ptr [rax+rax+00h]
0x180029730  cmp     qword ptr cs:xmmword_18004D740, r14
0x180029737  mov     ebx, eax
0x180029739  jz      short loc_18002979F
0x18002973b  mov     r8d, eax
0x18002973e  mov     word ptr [rsp+860h+var_820], r14w
0x180029744  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for caching U"...
0x18002974b  lea     rcx, [rsp+860h+var_820]
0x180029750  call    FormatRRASErrorString
0x180029755  mov     rdx, qword ptr cs:xmmword_18004D740
0x18002975c  lea     r8, [rsp+860h+var_820]
0x180029761  mov     rcx, cs:gRasEapEtwContext
0x180029768  mov     rax, cs:gRasEapTemplateFunc
0x18002976f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029774  jmp     short loc_18002979F
0x180029776  mov     r8d, [rsp+860h+pdwSizeOfUIContextData]; Size
0x18002977b  mov     rcx, rax; void *
0x18002977e  mov     rdx, [rsp+860h+ppUIContextData]; Src
0x180029783  call    memcpy_0
0x180029788  mov     eax, [rsp+860h+pdwSizeOfUIContextData]
0x18002978c  mov     r8, rsi
0x18002978f  mov     rcx, rdi
0x180029792  mov     [rdi+200h], eax
0x180029798  call    ProcessInteractiveUIInformation
0x18002979d  mov     ebx, eax
0x18002979f  test    ebx, ebx
0x1800297a1  jz      short loc_1800297CF
0x1800297a3  cmp     qword ptr cs:xmmword_18004D740, r14
0x1800297aa  jz      short loc_180029811
0x1800297ac  mov     r8d, ebx
0x1800297af  mov     word ptr [rsp+860h+var_820], r14w
0x1800297b5  lea     rdx, aRasinvokeident; "RasInvokeIdentityUI -- Leaving: 0x%x."
0x1800297bc  lea     rcx, [rsp+860h+var_820]
0x1800297c1  call    FormatRRASErrorString
0x1800297c6  mov     rdx, qword ptr cs:xmmword_18004D740
0x1800297cd  jmp     short loc_1800297F9
0x1800297cf  cmp     qword ptr cs:xmmword_18004D740+8, r14
0x1800297d6  jz      short loc_180029811
0x1800297d8  xor     r8d, r8d
0x1800297db  mov     word ptr [rsp+860h+var_820], r14w
0x1800297e1  lea     rdx, aRasinvokeident; "RasInvokeIdentityUI -- Leaving: 0x%x."
0x1800297e8  lea     rcx, [rsp+860h+var_820]
0x1800297ed  call    FormatRRASErrorString
0x1800297f2  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800297f9  mov     rcx, cs:gRasEapEtwContext
0x180029800  lea     r8, [rsp+860h+var_820]
0x180029805  mov     rax, cs:gRasEapTemplateFunc
0x18002980c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029811  mov     eax, ebx
0x180029813  mov     rcx, [rbp+760h+var_20]
0x18002981a  xor     rcx, rsp; StackCookie
0x18002981d  call    __security_check_cookie
0x180029822  lea     r11, [rsp+860h+var_10]
0x18002982a  mov     rbx, [r11+28h]
0x18002982e  mov     rsi, [r11+30h]
0x180029832  mov     rsp, r11
0x180029835  pop     r14
0x180029837  pop     rdi
0x180029838  pop     rbp
0x180029839  retn
```

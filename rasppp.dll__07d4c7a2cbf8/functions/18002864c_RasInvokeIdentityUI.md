# RasInvokeIdentityUI

- ea: `0x18002864c`
- end: `0x180028930`
- name: `RasInvokeIdentityUI`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180027aa4`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180027da8`
- `0x180027e60`
- `0x18002864c`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002880e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002880e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028820`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028762`
- `eappprxy!EapHostPeerFreeEapError` at `0x180028762`
- `eappprxy!EapHostPeerGetUIContext` at `0x180028744`
- `eappprxy!EapHostPeerGetUIContext` at `0x180028744`

## string_xrefs

- `0x1800286fa`: `EAP method wants to bring up UI on the server side. This is not a valid operation. Returning error: 0x%.x`

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
  v7 = *((_QWORD *)&xmmword_18004C740 + 1);
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
      L"RasInvokeIdentityUI -- Entering.");
    v7 = *((_QWORD *)&xmmword_18004C740 + 1);
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
        *((_QWORD *)&xmmword_18004C740 + 1),
        &v18);
    }
    goto LABEL_21;
  }
  UIContext = EapHostPeerGetUIContext(*(_DWORD *)(a1 + 484), &pdwSizeOfUIContextData, &ppUIContextData, &ppEapError);
  PrintEapError("EapHostPeerGetUIContext", ppEapError);
  EapHostPeerFreeEapError(ppEapError);
  if ( UIContext )
  {
    if ( (_QWORD)xmmword_18004C740 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        xmmword_18004C740,
        L"RasInvokeIdentityUI: Unable to retreive UI context. Using NULL context.");
    ppUIContextData = 0;
    pdwSizeOfUIContextData = 0;
  }
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
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
      if ( (_QWORD)xmmword_18004C740 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Failed to allocate memory for caching UI context with error: 0x%x.", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004C740, &v18);
      }
    }
  }
  if ( UIContext )
  {
LABEL_21:
    if ( (_QWORD)xmmword_18004C740 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"RasInvokeIdentityUI -- Leaving: 0x%x.", UIContext);
      v13 = xmmword_18004C740;
LABEL_25:
      ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v13, &v18);
      return UIContext;
    }
    return UIContext;
  }
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"RasInvokeIdentityUI -- Leaving: 0x%x.", 0);
    v13 = *((_QWORD *)&xmmword_18004C740 + 1);
    goto LABEL_25;
  }
  return UIContext;
}

```

## disassembly

```asm
0x18002864c  mov     [rsp-8+arg_8], rbx
0x180028651  mov     [rsp-8+arg_10], rsi
0x180028656  push    rbp
0x180028657  push    rdi
0x180028658  push    r14
0x18002865a  lea     rbp, [rsp-750h]
0x180028662  sub     rsp, 850h
0x180028669  mov     rax, cs:__security_cookie
0x180028670  xor     rax, rsp
0x180028673  mov     [rbp+760h+var_20], rax
0x18002867a  mov     rsi, [rbp+760h+arg_28]
0x180028681  xor     r14d, r14d
0x180028684  mov     rdi, rcx
0x180028687  mov     [rsp+860h+pdwSizeOfUIContextData], r14d
0x18002868c  lea     rcx, [rsp+860h+var_81C]; void *
0x180028691  mov     [rsp+860h+ppUIContextData], r14
0x180028696  xor     edx, edx; Val
0x180028698  mov     [rsp+860h+ppEapError], r14
0x18002869d  mov     r8d, 7FCh; Size
0x1800286a3  mov     [rsp+860h+var_820], r14d
0x1800286a8  call    memset_0
0x1800286ad  mov     rax, qword ptr cs:xmmword_18004C740+8
0x1800286b4  test    rax, rax
0x1800286b7  jz      short loc_1800286DD
0x1800286b9  mov     rcx, cs:gRasEapEtwContext
0x1800286c0  lea     r8, aRasinvokeident_0; "RasInvokeIdentityUI -- Entering."
0x1800286c7  mov     rdx, rax
0x1800286ca  mov     rax, cs:gRasEapTemplateFunc
0x1800286d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286d6  mov     rax, qword ptr cs:xmmword_18004C740+8
0x1800286dd  cmp     [rdi+10h], r14d
0x1800286e1  jz      short loc_18002872F
0x1800286e3  mov     ebx, 2BFh
0x1800286e8  test    rax, rax
0x1800286eb  jz      loc_180028899
0x1800286f1  mov     r8d, ebx
0x1800286f4  mov     word ptr [rsp+860h+var_820], r14w
0x1800286fa  lea     rdx, aEapMethodWants; "EAP method wants to bring up UI on the "...
0x180028701  lea     rcx, [rsp+860h+var_820]
0x180028706  call    FormatRRASErrorString
0x18002870b  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180028712  lea     r8, [rsp+860h+var_820]
0x180028717  mov     rcx, cs:gRasEapEtwContext
0x18002871e  mov     rax, cs:gRasEapTemplateFunc
0x180028725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002872a  jmp     loc_180028899
0x18002872f  mov     ecx, [rdi+1E4h]; sessionHandle
0x180028735  lea     r9, [rsp+860h+ppEapError]; ppEapError
0x18002873a  lea     r8, [rsp+860h+ppUIContextData]; ppUIContextData
0x18002873f  lea     rdx, [rsp+860h+pdwSizeOfUIContextData]; pdwSizeOfUIContextData
0x180028744  call    cs:__imp_EapHostPeerGetUIContext
0x18002874a  mov     rdx, [rsp+860h+ppEapError]
0x18002874f  lea     rcx, aEaphostpeerget_0; "EapHostPeerGetUIContext"
0x180028756  mov     ebx, eax
0x180028758  call    PrintEapError
0x18002875d  mov     rcx, [rsp+860h+ppEapError]; pEapError
0x180028762  call    cs:__imp_EapHostPeerFreeEapError
0x180028768  test    ebx, ebx
0x18002876a  jz      short loc_18002879C
0x18002876c  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028773  test    rdx, rdx
0x180028776  jz      short loc_180028792
0x180028778  mov     rcx, cs:gRasEapEtwContext
0x18002877f  lea     r8, aRasinvokeident_1; "RasInvokeIdentityUI: Unable to retreive"...
0x180028786  mov     rax, cs:gRasEapTemplateFunc
0x18002878d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028792  mov     [rsp+860h+ppUIContextData], r14
0x180028797  mov     [rsp+860h+pdwSizeOfUIContextData], r14d
0x18002879c  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800287a3  test    rdx, rdx
0x1800287a6  jz      short loc_1800287C2
0x1800287a8  mov     rcx, cs:gRasEapEtwContext
0x1800287af  lea     r8, aEapMethodWants_0; "EAP method wants to invoke interactive "...
0x1800287b6  mov     rax, cs:gRasEapTemplateFunc
0x1800287bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287c2  mov     rcx, [rdi+1F8h]; hMem
0x1800287c9  test    rcx, rcx
0x1800287cc  jz      short loc_1800287DB
0x1800287ce  call    cs:__imp_LocalFree
0x1800287d4  mov     [rdi+1F8h], r14
0x1800287db  mov     [rdi+200h], r14d
0x1800287e2  mov     [rsi+160h], r14d
0x1800287e9  mov     [rsi+158h], r14
0x1800287f0  cmp     [rsp+860h+ppUIContextData], r14
0x1800287f5  jz      loc_180028895
0x1800287fb  mov     eax, [rsp+860h+pdwSizeOfUIContextData]
0x1800287ff  test    eax, eax
0x180028801  jz      loc_180028895
0x180028807  mov     edx, eax; uBytes
0x180028809  mov     ecx, 40h ; '@'; uFlags
0x18002880e  call    cs:__imp_LocalAlloc
0x180028814  mov     [rdi+1F8h], rax
0x18002881b  test    rax, rax
0x18002881e  jnz     short loc_18002886C
0x180028820  call    cs:__imp_GetLastError
0x180028826  cmp     qword ptr cs:xmmword_18004C740, r14
0x18002882d  mov     ebx, eax
0x18002882f  jz      short loc_180028895
0x180028831  mov     r8d, eax
0x180028834  mov     word ptr [rsp+860h+var_820], r14w
0x18002883a  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for caching U"...
0x180028841  lea     rcx, [rsp+860h+var_820]
0x180028846  call    FormatRRASErrorString
0x18002884b  mov     rdx, qword ptr cs:xmmword_18004C740
0x180028852  lea     r8, [rsp+860h+var_820]
0x180028857  mov     rcx, cs:gRasEapEtwContext
0x18002885e  mov     rax, cs:gRasEapTemplateFunc
0x180028865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002886a  jmp     short loc_180028895
0x18002886c  mov     r8d, [rsp+860h+pdwSizeOfUIContextData]; Size
0x180028871  mov     rcx, rax; void *
0x180028874  mov     rdx, [rsp+860h+ppUIContextData]; Src
0x180028879  call    memcpy_0
0x18002887e  mov     eax, [rsp+860h+pdwSizeOfUIContextData]
0x180028882  mov     r8, rsi
0x180028885  mov     rcx, rdi
0x180028888  mov     [rdi+200h], eax
0x18002888e  call    ProcessInteractiveUIInformation
0x180028893  mov     ebx, eax
0x180028895  test    ebx, ebx
0x180028897  jz      short loc_1800288C5
0x180028899  cmp     qword ptr cs:xmmword_18004C740, r14
0x1800288a0  jz      short loc_180028907
0x1800288a2  mov     r8d, ebx
0x1800288a5  mov     word ptr [rsp+860h+var_820], r14w
0x1800288ab  lea     rdx, aRasinvokeident; "RasInvokeIdentityUI -- Leaving: 0x%x."
0x1800288b2  lea     rcx, [rsp+860h+var_820]
0x1800288b7  call    FormatRRASErrorString
0x1800288bc  mov     rdx, qword ptr cs:xmmword_18004C740
0x1800288c3  jmp     short loc_1800288EF
0x1800288c5  cmp     qword ptr cs:xmmword_18004C740+8, r14
0x1800288cc  jz      short loc_180028907
0x1800288ce  xor     r8d, r8d
0x1800288d1  mov     word ptr [rsp+860h+var_820], r14w
0x1800288d7  lea     rdx, aRasinvokeident; "RasInvokeIdentityUI -- Leaving: 0x%x."
0x1800288de  lea     rcx, [rsp+860h+var_820]
0x1800288e3  call    FormatRRASErrorString
0x1800288e8  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x1800288ef  mov     rcx, cs:gRasEapEtwContext
0x1800288f6  lea     r8, [rsp+860h+var_820]
0x1800288fb  mov     rax, cs:gRasEapTemplateFunc
0x180028902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028907  mov     eax, ebx
0x180028909  mov     rcx, [rbp+760h+var_20]
0x180028910  xor     rcx, rsp; StackCookie
0x180028913  call    __security_check_cookie
0x180028918  lea     r11, [rsp+860h+var_10]
0x180028920  mov     rbx, [r11+28h]
0x180028924  mov     rsi, [r11+30h]
0x180028928  mov     rsp, r11
0x18002892b  pop     r14
0x18002892d  pop     rdi
0x18002892e  pop     rbp
0x18002892f  retn
```

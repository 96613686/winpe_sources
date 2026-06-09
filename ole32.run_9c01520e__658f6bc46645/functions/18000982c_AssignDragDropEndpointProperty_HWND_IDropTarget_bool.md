# AssignDragDropEndpointProperty(HWND__ *,IDropTarget *,bool)

- ea: `0x18000982c`
- end: `0x180009954`
- name: `?AssignDragDropEndpointProperty@@YAJPEAUHWND__@@PEAUIDropTarget@@_N@Z`
- size: `296`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, IDropTarget *pDropTarget, bool fBrokeredInstance)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009654`
- `0x180044d0c`

## callees

- `0x18000982c`
- `0x18000a3a0`
- `0x18000a424`
- `0x18001217c`
- `0x180041a90`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009899`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000991e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000991e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000987c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000987c`
- `USER32!GetWindowThreadProcessId` at `0x180009912`
- `USER32!GetWindowThreadProcessId` at `0x180009912`

## string_xrefs

- `0x180009939`: `com\ole32\com\rot\getif.cxx`

## pseudocode

```c
__int64 __fastcall AssignDragDropEndpointProperty(
        HWND__ *hWnd,
        IDropTarget *pDropTarget,
        wil::ReportingKind fBrokeredInstance,
        unsigned __int64 a4)
{
  CPrivDragDrop *v7; // rax
  CPrivDragDrop *v9; // rax
  const _GUID *v10; // rdx
  int v11; // r9d
  CPrivDragDrop *v12; // rdi
  unsigned int v13; // ebx
  unsigned int hwndProcessID; // [rsp+30h] [rbp-18h] BYREF
  unsigned int size[5]; // [rsp+34h] [rbp-14h] BYREF
  void *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int isAppSilo; // [rsp+68h] [rbp+20h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::GetImpl'::`2'::impl,
    1,
    fBrokeredInstance,
    a4);
  isAppSilo = 0;
  size[0] = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppSilo, &isAppSilo, 4u, size)
    && isAppSilo
    && (hwndProcessID = 0, GetWindowThreadProcessId(hWnd, &hwndProcessID), GetCurrentProcessId() != hwndProcessID) )
  {
    v13 = -2147024891;
    wil::details::in1diag3::Return_Hr(retaddr, 0x15Bu, "com\\ole32\\com\\rot\\getif.cxx", -2147024891);
  }
  else
  {
    v7 = (CPrivDragDrop *)HeapAlloc(g_hHeap, 0, 0x40u);
    if ( !v7 )
      return 2147942414LL;
    CPrivDragDrop::CPrivDragDrop(v7, hWnd, pDropTarget, fBrokeredInstance, 1);
    v12 = v9;
    if ( !v9 )
      return 2147942414LL;
    v13 = AssignEndpointObject<CPrivDragDrop>(hWnd, v10, v9, v11);
    ((void (__fastcall *)(CPrivDragDrop *))v12->lpVtbl->Release)(v12);
  }
  return v13;
}

```

## disassembly

```asm
0x18000982c  mov     [rsp+arg_0], rbx
0x180009831  mov     [rsp+arg_8], rsi
0x180009836  push    rdi
0x180009837  sub     rsp, 40h
0x18000983b  mov     dil, fBrokeredInstance
0x18000983e  mov     rsi, pDropTarget
0x180009841  mov     rbx, hWnd
0x180009844  mov     dl, 1; __annotation("WILSTG:|42932704|Feature_AppSiloDragAndDrop|AlwaysEnabled")
0x180009846  lea     hWnd, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@3@XZ@4V453@A; this
0x18000984d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180009852  and     [rsp+48h+isAppSilo], 0
0x180009857  lea     rax, [rsp+48h+size]
0x18000985c  and     [rsp+48h+size], 0
0x180009861  lea     r8, [rsp+48h+isAppSilo]; TokenInformation
0x180009866  mov     r9d, 4; TokenInformationLength
0x18000986c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180009871  mov     hWnd, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180009878  lea     edx, [r9+2Ch]; TokenInformationClass
0x18000987c  call    cs:__imp_GetTokenInformation
0x180009883  nop     dword ptr [rax+rax+00h]
0x180009888  test    eax, eax
0x18000988a  jnz     short loc_1800098FE
0x18000988c  mov     hWnd, cs:?g_hHeap@@3QEAXEA; hHeap
0x180009893  xor     edx, edx; dwFlags
0x180009895  lea     r8d, [pDropTarget+40h]; dwBytes
0x180009899  call    cs:__imp_HeapAlloc
0x1800098a0  nop     dword ptr [rax+rax+00h]
0x1800098a5  test    rax, rax
0x1800098a8  jnz     short loc_1800098B1
0x1800098aa  mov     eax, 8007000Eh
0x1800098af  jmp     short loc_1800098ED
0x1800098b1  mov     r9b, dil; fBrokerInstance
0x1800098b4  mov     byte ptr [rsp+48h+ReturnLength], 1; dropTargetIsRPCSSRegistered
0x1800098b9  mov     r8, rsi; pDropTarget
0x1800098bc  mov     pDropTarget, rbx; hwnd
0x1800098bf  mov     hWnd, rax; this
0x1800098c2  call    ??0CPrivDragDrop@@QEAA@PEAUHWND__@@PEAUIDropTarget@@_N2@Z; CPrivDragDrop::CPrivDragDrop(HWND__ *,IDropTarget *,bool,bool)
0x1800098c7  mov     rdi, rax
0x1800098ca  test    rax, rax
0x1800098cd  jz      short loc_1800098AA
0x1800098cf  mov     r8, rax; hWnd
0x1800098d2  mov     hWnd, rbx; hWnd
0x1800098d5  call    ??$AssignEndpointObject@VCPrivDragDrop@@@@YAJPEAUHWND__@@AEBU_GUID@@PEAVCPrivDragDrop@@H@Z; AssignEndpointObject<CPrivDragDrop>(HWND__ *,_GUID const &,CPrivDragDrop *,int)
0x1800098da  mov     hWnd, [rdi]
0x1800098dd  mov     ebx, eax
0x1800098df  mov     rax, [hWnd+10h]
0x1800098e3  mov     hWnd, rdi
0x1800098e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098eb  mov     eax, ebx
0x1800098ed  mov     rbx, [rsp+48h+arg_0]
0x1800098f2  mov     rsi, [rsp+48h+arg_8]
0x1800098f7  add     rsp, 40h
0x1800098fb  pop     rdi
0x1800098fc  retn
0x1800098fe  cmp     [rsp+48h+isAppSilo], 0
0x180009903  jz      short loc_18000988C
0x180009905  and     [rsp+48h+hwndProcessID], 0
0x18000990a  lea     pDropTarget, [rsp+48h+hwndProcessID]; lpdwProcessId
0x18000990f  mov     hWnd, rbx; hWnd
0x180009912  call    cs:__imp_GetWindowThreadProcessId
0x180009919  nop     dword ptr [rax+rax+00h]
0x18000991e  call    cs:__imp_GetCurrentProcessId
0x180009925  nop     dword ptr [rax+rax+00h]
0x18000992a  cmp     eax, [rsp+48h+hwndProcessID]
0x18000992e  jz      loc_18000988C
0x180009934  mov     hWnd, [rsp+48h]; callerReturnAddress
0x180009939  lea     r8, aComOle32ComRot; "com\\ole32\\com\\rot\\getif.cxx"
0x180009940  mov     ebx, 80070005h
0x180009945  mov     edx, 15Bh; lineNumber
0x18000994a  mov     r9d, ebx; hr
0x18000994d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009952  jmp     short loc_1800098EB
```

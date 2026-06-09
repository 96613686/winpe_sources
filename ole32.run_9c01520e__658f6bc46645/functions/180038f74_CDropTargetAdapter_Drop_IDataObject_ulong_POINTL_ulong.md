# CDropTargetAdapter::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x180038f74`
- end: `0x180039250`
- name: `?Drop@CDropTargetAdapter@@QEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `732`
- prototype: `HRESULT __fastcall(CDropTargetAdapter *this, IDataObject *pDataObject, unsigned int grfKeyState, _POINTL ptl, unsigned int *pdwEffect)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029908`

## callees

- `0x18000a690`
- `0x18000ba70`
- `0x18001ad50`
- `0x180038f74`
- `0x180041a90`
- `0x180044db0`
- `0x18008a56c`
- `0x18008be38`
- `0x180093150`
- `0x1800abc80`
- `0x1800ac0a8`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039027`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039027`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800391ec`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800391ec`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003919c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003919c`
- `USER32!PostMessageW` at `0x180039208`
- `USER32!PostMessageW` at `0x180039208`
- `USER32!SetThreadDpiAwarenessContext` at `0x180039097`
- `USER32!SetThreadDpiAwarenessContext` at `0x180039226`
- `USER32!SetThreadDpiAwarenessContext` at `0x180039097`
- `USER32!SetThreadDpiAwarenessContext` at `0x180039226`
- `USER32!GetWindowDpiAwarenessContext` at `0x180039088`
- `USER32!GetWindowDpiAwarenessContext` at `0x180039088`
- `USER32!GetThreadDpiAwarenessContext` at `0x180038fbf`
- `USER32!GetThreadDpiAwarenessContext` at `0x180038fbf`
- `USER32!ScreenToClient` at `0x1800391cc`
- `USER32!ScreenToClient` at `0x1800391cc`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x180039079`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x180039079`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CDropTargetAdapter::Drop(
        CDropTargetAdapter *this,
        IDataObject *pDataObject,
        unsigned int grfKeyState,
        _POINTL ptl,
        unsigned int *pdwEffect)
{
  unsigned int v5; // esi
  unsigned int v8; // edi
  __int64 ThreadDpiAwarenessContext; // r12
  int v10; // r13d
  wil::ReportingKind v11; // r8
  unsigned __int64 v12; // r9
  HWND__ *hwndOLE; // rsi
  __int64 WindowDpiAwarenessContext; // rax
  __int64 v15; // rax
  unsigned int *v16; // r14
  HWND__ *hwndSource; // rax
  HRESULT v18; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  _DWORD *v20; // rax
  _DWORD *v21; // rsi
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > tokenHandle; // [rsp+58h] [rbp-31h] BYREF
  tagSTGMEDIUM medium; // [rsp+60h] [rbp-29h] BYREF
  _BYTE formatetc[40]; // [rsp+78h] [rbp-11h] OVERLAPPED BYREF
  tagPOINT pt; // [rsp+E8h] [rbp+5Fh] BYREF
  unsigned int v27; // [rsp+F8h] [rbp+6Fh]
  _POINTL v28; // [rsp+100h] [rbp+77h] BYREF

  v28 = ptl;
  v27 = grfKeyState;
  v5 = grfKeyState;
  *(_OWORD *)&medium.hBitmap = 0;
  memset(formatetc, 0, sizeof(formatetc));
  v8 = -2147467259;
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  v10 = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::GetImpl'::`2'::impl,
    1,
    v11,
    v12);
  if ( this->_hwndOLE )
  {
    pt.x = 0;
    LODWORD(tokenHandle.m_ptr) = 0;
    *(_QWORD *)&medium.tymed = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&medium,
      0);
    if ( GetProcessTokenByHandle(this->_hwndOLE, (void **)&medium) >= 0
      && GetTokenInformation(*(HANDLE *)&medium.tymed, TokenIsAppSilo, &pt, 4u, (PDWORD)&tokenHandle) >= 0
      && pt.x )
    {
      BrokerDragDropFilesForAppSilos(*(void **)&medium.tymed, pDataObject);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&medium);
    if ( this->_hwndOLE )
      goto LABEL_9;
  }
  if ( this->_hwnd31 || IsContainerDragOperation() )
  {
LABEL_9:
    hwndOLE = this->_hwndOLE;
    if ( !this->_hwndOLE )
      hwndOLE = this->_hwnd31;
    PhysicalToLogicalDpiPointForWindow(hwndOLE, &v28);
    WindowDpiAwarenessContext = GetWindowDpiAwarenessContext(hwndOLE);
    v15 = SetThreadDpiAwarenessContext(WindowDpiAwarenessContext);
    v5 = v27;
    v10 = 1;
    ThreadDpiAwarenessContext = v15;
  }
  v16 = pdwEffect;
  if ( (this->_hwndOLE || IsContainerDragOperation()) && this->_dwEffectLast )
  {
    hwndSource = GetPrivateClipboardWindow(CLIP_QUERY);
    v18 = PrivDragDrop(
            this->_hwndOLE,
            0,
            (tagDRAGOP)(this->_pdo->_fSourceIsAppContainer != 0 ? DRAGOP_DROP_FROM_APPCONTAINER : DRAGOP_DROP),
            this->_pdo->_DOBuffer,
            pDataObject,
            v5,
            v28,
            v16,
            hwndSource,
            &this->_hDDInfo);
    goto LABEL_19;
  }
  if ( this->_hwndOLE || IsContainerDragOperation() )
  {
    *v16 = 0;
    v18 = CDropTargetAdapter::DragLeave(this);
LABEL_19:
    v8 = v18;
    if ( !v18 && *v16 || v18 == 1 )
      goto LABEL_29;
  }
  if ( this->_hwnd31 )
  {
    *(_DWORD *)&formatetc[28] = -1;
    *(_DWORD *)&formatetc[24] = 1;
    *(_WORD *)&formatetc[8] = 15;
    lpVtbl = pDataObject->lpVtbl;
    *(_DWORD *)&formatetc[32] = 1;
    v8 = ((__int64 (__fastcall *)(IDataObject *, _BYTE *, HBITMAP *))lpVtbl[1].QueryInterface)(
           pDataObject,
           &formatetc[8],
           &medium.hBitmap);
    if ( !v8 )
    {
      v20 = GlobalLock(medium.pUnkForRelease);
      v21 = v20;
      pt = (tagPOINT)v28;
      if ( v20 )
      {
        v20[3] = IsNCDrop(this->_hwnd31, (tagPOINT)v28);
        if ( ScreenToClient(this->_hwnd31, &pt) )
          *(tagPOINT *)(v21 + 1) = pt;
        GlobalUnlock(medium.pUnkForRelease);
      }
      *v16 = PostMessageW(this->_hwnd31, 0x233u, (WPARAM)medium.pUnkForRelease, 0);
    }
  }
LABEL_29:
  if ( v10 )
    SetThreadDpiAwarenessContext(ThreadDpiAwarenessContext);
  return v8;
}

```

## disassembly

```asm
0x180038f74  mov     rax, rsp
0x180038f77  mov     [rax+10h], rbx
0x180038f7b  mov     [rax+20h], ptl
0x180038f7f  mov     [rax+18h], grfKeyState
0x180038f83  push    rbp
0x180038f84  push    rsi
0x180038f85  push    rdi
0x180038f86  push    r12
0x180038f88  push    r13
0x180038f8a  push    r14
0x180038f8c  push    r15
0x180038f8e  lea     rbp, [rax-57h]
0x180038f92  sub     rsp, 0A0h
0x180038f99  xorps   xmm1, xmm1
0x180038f9c  xorps   xmm0, xmm0
0x180038f9f  xor     eax, eax
0x180038fa1  mov     esi, grfKeyState
0x180038fa4  movups  xmmword ptr [rbp+4Fh+medium.8], xmm0
0x180038fa8  mov     qword ptr [rbp+4Fh+formatetc.cfFormat], rax
0x180038fac  mov     r15, pDataObject
0x180038faf  movups  xmmword ptr [rbp+4Fh+formatetc.ptd], xmm1
0x180038fb3  mov     rbx, this
0x180038fb6  mov     edi, 80004005h
0x180038fbb  movups  xmmword ptr [rbp+4Fh+formatetc.tymed], xmm1
0x180038fbf  call    cs:__imp_GetThreadDpiAwarenessContext
0x180038fc6  nop     dword ptr [rax+rax+00h]
0x180038fcb  xor     r14d, r14d
0x180038fce  mov     r12, rax
0x180038fd1  mov     r13d, r14d
0x180038fd4  mov     dl, 1; __annotation("WILSTG:|42932704|Feature_AppSiloDragAndDrop|AlwaysEnabled")
0x180038fd6  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@3@XZ@4V453@A; this
0x180038fdd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180038fe2  cmp     [rbx], r14
0x180038fe5  jz      short loc_180039057
0x180038fe7  xor     edx, edx; ptr
0x180038fe9  mov     [rbp+4Fh+pt.x], r14d
0x180038fed  lea     this, [rbp+4Fh+medium]; this
0x180038ff1  mov     dword ptr [rbp+4Fh+tokenHandle.m_ptr], r14d
0x180038ff5  mov     qword ptr [rbp+4Fh+medium.tymed], r14
0x180038ff9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180038ffe  mov     this, [rbx]; hwnd
0x180039001  lea     pDataObject, [rbp+4Fh+medium]; tokenHandle
0x180039005  call    ?GetProcessTokenByHandle@@YAJPEAUHWND__@@PEAPEAX@Z; GetProcessTokenByHandle(HWND__ *,void * *)
0x18003900a  test    eax, eax
0x18003900c  js      short loc_180039049
0x18003900e  mov     this, qword ptr [rbp+4Fh+medium.tymed]; TokenHandle
0x180039012  lea     rax, [rbp+4Fh+tokenHandle]
0x180039016  lea     r9d, [r14+4]; TokenInformationLength
0x18003901a  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003901f  lea     r8, [rbp+4Fh+pt]; TokenInformation
0x180039023  lea     edx, [r14+30h]; TokenInformationClass
0x180039027  call    cs:__imp_GetTokenInformation
0x18003902e  nop     dword ptr [rax+rax+00h]
0x180039033  test    eax, eax
0x180039035  js      short loc_180039049
0x180039037  cmp     [rbp+4Fh+pt.x], r14d
0x18003903b  jz      short loc_180039049
0x18003903d  mov     this, qword ptr [rbp+4Fh+medium.tymed]; tokenHandle
0x180039041  mov     pDataObject, r15; dataObject
0x180039044  call    ?BrokerDragDropFilesForAppSilos@@YAJPEAXPEAUIDataObject@@@Z; BrokerDragDropFilesForAppSilos(void *,IDataObject *)
0x180039049  lea     this, [rbp+4Fh+medium]; this
0x18003904d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039052  cmp     [rbx], r14
0x180039055  jnz     short loc_180039066
0x180039057  cmp     [rbx+8], r14
0x18003905b  jnz     short loc_180039066
0x18003905d  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180039062  test    al, al
0x180039064  jz      short loc_1800390AF
0x180039066  mov     rsi, [rbx]
0x180039069  test    rsi, rsi
0x18003906c  jnz     short loc_180039072
0x18003906e  mov     rsi, [rbx+8]
0x180039072  lea     pDataObject, [rbp+4Fh+arg_18]
0x180039076  mov     this, rsi
0x180039079  call    cs:__imp_PhysicalToLogicalDpiPointForWindow
0x180039080  nop     dword ptr [rax+rax+00h]
0x180039085  mov     this, rsi
0x180039088  call    cs:__imp_GetWindowDpiAwarenessContext
0x18003908f  nop     dword ptr [rax+rax+00h]
0x180039094  mov     this, rax
0x180039097  call    cs:__imp_SetThreadDpiAwarenessContext
0x18003909e  nop     dword ptr [rax+rax+00h]
0x1800390a3  mov     esi, [rbp+4Fh+arg_10]
0x1800390a6  mov     r13d, 1
0x1800390ac  mov     r12, rax
0x1800390af  cmp     qword ptr [rbx], 0
0x1800390b3  mov     r14, [rbp+4Fh+arg_20]
0x1800390b7  jnz     short loc_1800390C2
0x1800390b9  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x1800390be  test    al, al
0x1800390c0  jz      short loc_18003911E
0x1800390c2  cmp     dword ptr [rbx+10h], 0
0x1800390c6  jz      short loc_18003911E
0x1800390c8  xor     ecx, ecx; fFlags
0x1800390ca  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x1800390cf  mov     this, [rbx]; hwnd
0x1800390d2  lea     pDataObject, [rbx+20h]
0x1800390d6  mov     qword ptr [rsp+0D0h+returnLength], pDataObject; phDDInfo
0x1800390db  mov     r10, rax
0x1800390de  mov     rax, [rbx+18h]
0x1800390e2  mov     [rsp+0D0h+hwndSource], r10; hwndSource
0x1800390e7  mov     [rsp+0D0h+var_98], r14; pdwEffect
0x1800390ec  mov     ptl, [rax+18h]; pIFDDataObject
0x1800390f0  mov     eax, [rax+0C8h]
0x1800390f6  neg     eax
0x1800390f8  mov     rax, qword ptr [rbp+4Fh+arg_18.x]
0x1800390fc  sbb     grfKeyState, grfKeyState
0x1800390ff  mov     qword ptr [rsp+0D0h+var_A0.x], rax; ptl
0x180039104  and     grfKeyState, 2
0x180039108  mov     [rsp+0D0h+var_A8], esi; grfKeyState
0x18003910c  add     grfKeyState, 4; dop
0x180039110  mov     [rsp+0D0h+ReturnLength], r15; pIDataObject
0x180039115  xor     edx, edx; pWinRtTarget
0x180039117  call    ?PrivDragDrop@@YAJPEAUHWND__@@PEAUIDropTarget@@W4tagDRAGOP@@PEAUtagInterfaceData@@PEAUIDataObject@@KU_POINTL@@PEAK0PEAPEAX@Z; PrivDragDrop(HWND__ *,IDropTarget *,tagDRAGOP,tagInterfaceData *,IDataObject *,ulong,_POINTL,ulong *,HWND__ *,void * *)
0x18003911c  jmp     short loc_180039139
0x18003911e  cmp     qword ptr [rbx], 0
0x180039122  jnz     short loc_18003912D
0x180039124  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180039129  test    al, al
0x18003912b  jz      short loc_180039151
0x18003912d  and     dword ptr [r14], 0
0x180039131  mov     this, rbx; this
0x180039134  call    ?DragLeave@CDropTargetAdapter@@QEAAJXZ; CDropTargetAdapter::DragLeave(void)
0x180039139  mov     edi, eax
0x18003913b  test    eax, eax
0x18003913d  jnz     short loc_180039148
0x18003913f  cmp     [r14], eax
0x180039142  jnz     loc_18003921E
0x180039148  cmp     edi, 1
0x18003914b  jz      loc_18003921E
0x180039151  cmp     qword ptr [rbx+8], 0
0x180039156  jz      loc_18003921E
0x18003915c  or      dword ptr [rbp+4Fh+formatetc+1Ch], 0FFFFFFFFh
0x180039160  lea     r8, [rbp+4Fh+medium.8]
0x180039164  mov     eax, 0Fh
0x180039169  mov     [rbp+4Fh+formatetc.tymed], 1
0x180039170  mov     word ptr [rbp+4Fh+formatetc.ptd], ax
0x180039174  lea     pDataObject, [rbp+4Fh+formatetc.ptd]
0x180039178  mov     rax, [r15]
0x18003917b  mov     this, r15
0x18003917e  mov     [rbp+4Fh+var_40], 1
0x180039185  mov     rax, [rax+18h]
0x180039189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003918e  mov     edi, eax
0x180039190  test    eax, eax
0x180039192  jnz     loc_18003921E
0x180039198  mov     this, [rbp+4Fh+medium.pUnkForRelease]; hMem
0x18003919c  call    cs:__imp_GlobalLock
0x1800391a3  nop     dword ptr [rax+rax+00h]
0x1800391a8  mov     pDataObject, qword ptr [rbp+4Fh+arg_18.x]; pt
0x1800391ac  mov     rsi, rax
0x1800391af  mov     qword ptr [rbp+4Fh+pt.x], pDataObject
0x1800391b3  test    rax, rax
0x1800391b6  jz      short loc_1800391F8
0x1800391b8  mov     this, [rbx+8]; hwnd
0x1800391bc  call    ?IsNCDrop@@YAHPEAUHWND__@@UtagPOINT@@@Z; IsNCDrop(HWND__ *,tagPOINT)
0x1800391c1  mov     [rsi+0Ch], eax
0x1800391c4  lea     pDataObject, [rbp+4Fh+pt]; lpPoint
0x1800391c8  mov     this, [rbx+8]; hWnd
0x1800391cc  call    cs:__imp_ScreenToClient
0x1800391d3  nop     dword ptr [rax+rax+00h]
0x1800391d8  test    eax, eax
0x1800391da  jz      short loc_1800391E8
0x1800391dc  mov     eax, [rbp+4Fh+pt.x]
0x1800391df  mov     [rsi+4], eax
0x1800391e2  mov     eax, [rbp+4Fh+pt.y]
0x1800391e5  mov     [rsi+8], eax
0x1800391e8  mov     this, [rbp+4Fh+medium.pUnkForRelease]; hMem
0x1800391ec  call    cs:__imp_GlobalUnlock
0x1800391f3  nop     dword ptr [rax+rax+00h]
0x1800391f8  mov     r8, [rbp+4Fh+medium.pUnkForRelease]; wParam
0x1800391fc  xor     r9d, r9d; lParam
0x1800391ff  mov     this, [rbx+8]; hWnd
0x180039203  mov     edx, 233h; Msg
0x180039208  call    cs:__imp_PostMessageW
0x18003920f  nop     dword ptr [rax+rax+00h]
0x180039214  xor     ecx, ecx
0x180039216  test    eax, eax
0x180039218  setnz   cl
0x18003921b  mov     [r14], ecx
0x18003921e  test    r13d, r13d
0x180039221  jz      short loc_180039232
0x180039223  mov     this, r12
0x180039226  call    cs:__imp_SetThreadDpiAwarenessContext
0x18003922d  nop     dword ptr [rax+rax+00h]
0x180039232  mov     rbx, [rsp+0D0h+arg_8]
0x18003923a  mov     eax, edi
0x18003923c  add     rsp, 0A0h
0x180039243  pop     r15
0x180039245  pop     r14
0x180039247  pop     r13
0x180039249  pop     r12
0x18003924b  pop     rdi
0x18003924c  pop     rsi
0x18003924d  pop     rbp
0x18003924e  retn
```

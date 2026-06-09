# CDragOperation::GetDropTarget(HWND__ *,HWND__ *,IDropTarget *)

- ea: `0x180041178`
- end: `0x180041310`
- name: `?GetDropTarget@CDragOperation@@AEAAJPEAUHWND__@@0PEAUIDropTarget@@@Z`
- size: `408`
- prototype: `HRESULT __fastcall(CDragOperation *this, HWND__ *hwnd31, HWND__ *hwndDropTarget, IDropTarget *nonRPCSSRegisteredDropTarget)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bd4c`

## callees

- `0x18000c3dc`
- `0x18000ccac`
- `0x180041178`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004129a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004129a`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800411ef`
- `USER32!SetThreadDpiAwarenessContext` at `0x18004125d`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800411ef`
- `USER32!SetThreadDpiAwarenessContext` at `0x18004125d`
- `USER32!GetWindowDpiAwarenessContext` at `0x1800411e6`
- `USER32!GetWindowDpiAwarenessContext` at `0x1800411e6`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x1800411dd`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x1800411dd`

## pseudocode

```c
__int64 __fastcall CDragOperation::GetDropTarget(
        CDragOperation *this,
        HWND__ *hwnd31,
        HWND__ *hwndDropTarget,
        IDropTarget *nonRPCSSRegisteredDropTarget)
{
  HWND__ *v5; // rbp
  unsigned int v8; // esi
  __int64 WindowDpiAwarenessContext; // rax
  __int64 v10; // rbx
  CDropTargetAdapter *v11; // rax
  unsigned int v12; // edx
  unsigned int *pdwEffect; // rcx
  _POINTL ptl; // [rsp+80h] [rbp+8h] BYREF
  void *hDDInfo; // [rsp+90h] [rbp+18h] BYREF

  hDDInfo = 0;
  this->_pDropTargetAdapter = 0;
  v5 = hwndDropTarget;
  if ( !hwndDropTarget )
  {
    v8 = -2147467259;
    if ( !IsContainerDragOperation() || !nonRPCSSRegisteredDropTarget )
      goto LABEL_9;
  }
  ptl = (_POINTL)this->_cpt;
  PhysicalToLogicalDpiPointForWindow(v5, &ptl);
  WindowDpiAwarenessContext = GetWindowDpiAwarenessContext(v5);
  v10 = SetThreadDpiAwarenessContext(WindowDpiAwarenessContext);
  v8 = PrivDragDrop(
         v5,
         nonRPCSSRegisteredDropTarget,
         (tagDRAGOP)(this->_fSourceIsAppContainer != 0 ? DRAGOP_ENTER_FROM_APPCONTAINER : DRAGOP_ENTER),
         this->_DOBuffer,
         this->_pDataObject,
         this->_grfKeyState,
         ptl,
         this->_pdwEffect,
         0,
         &hDDInfo);
  SetThreadDpiAwarenessContext(v10);
  if ( v8 )
  {
    v5 = 0;
    if ( v8 == -2147024891 )
      return v8;
  }
  if ( !v5 )
  {
LABEL_9:
    if ( !hwnd31 && (!IsContainerDragOperation() || !nonRPCSSRegisteredDropTarget) )
      return v8;
  }
  v11 = (CDropTargetAdapter *)HeapAlloc(g_hHeap, 0, 0x38u);
  if ( v11 )
  {
    v8 = 0;
    v12 = *this->_pdwEffect;
    v11->_hDDInfo = hDDInfo;
    v11->_hwndOLE = v5;
    v11->_hwnd31 = hwnd31;
    v11->_dwEffectLast = v12;
    v11->_pdo = this;
    v11->_checkedForEnterpriseDropTarget = 0;
    v11->_hrEnterpriseDropTargetCheck = -2147418113;
    *(_QWORD *)&v11->_isEnterpriseDropTarget = 0;
    pdwEffect = this->_pdwEffect;
    if ( !*pdwEffect && hwnd31 )
      *pdwEffect = 1;
  }
  else
  {
    v8 = -2147024882;
    v11 = 0;
  }
  this->_pDropTargetAdapter = v11;
  return v8;
}

```

## disassembly

```asm
0x180041178  mov     rax, rsp
0x18004117b  mov     [rax+10h], rbx
0x18004117f  push    rbp
0x180041180  push    rsi
0x180041181  push    rdi
0x180041182  push    r14
0x180041184  push    r15
0x180041186  sub     rsp, 50h
0x18004118a  mov     qword ptr [rax+18h], 0
0x180041192  mov     r15, nonRPCSSRegisteredDropTarget
0x180041195  mov     qword ptr [this+30h], 0
0x18004119d  mov     rbp, hwndDropTarget
0x1800411a0  mov     r14, hwnd31
0x1800411a3  mov     rdi, this
0x1800411a6  test    hwndDropTarget, hwndDropTarget
0x1800411a9  jnz     short loc_1800411C6
0x1800411ab  mov     esi, 80004005h
0x1800411b0  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x1800411b5  test    al, al
0x1800411b7  jz      loc_18004127A
0x1800411bd  test    r15, r15
0x1800411c0  jz      loc_18004127A
0x1800411c6  mov     rax, [rdi+50h]
0x1800411ca  lea     hwnd31, [rsp+78h+ptl]
0x1800411d2  mov     this, rbp
0x1800411d5  mov     qword ptr [rsp+78h+ptl.x], rax
0x1800411dd  call    cs:__imp_PhysicalToLogicalDpiPointForWindow
0x1800411e3  mov     this, rbp
0x1800411e6  call    cs:__imp_GetWindowDpiAwarenessContext
0x1800411ec  mov     this, rax
0x1800411ef  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800411f5  mov     ecx, [rdi+0C8h]
0x1800411fb  mov     hwnd31, r15; pWinRtTarget
0x1800411fe  mov     nonRPCSSRegisteredDropTarget, [rdi+18h]; pIFDDataObject
0x180041202  neg     ecx
0x180041204  mov     this, [rdi+60h]
0x180041208  mov     rbx, rax
0x18004120b  sbb     r8d, r8d
0x18004120e  lea     rax, [rsp+78h+hDDInfo]
0x180041216  mov     [rsp+78h+phDDInfo], rax; phDDInfo
0x18004121b  and     r8d, 4
0x18004121f  mov     rax, [rdi+10h]
0x180041223  inc     r8d; dop
0x180041226  mov     [rsp+78h+hwndSource], 0; hwndSource
0x18004122f  mov     [rsp+78h+pdwEffect], this; pdwEffect
0x180041234  mov     this, qword ptr [rsp+78h+ptl.x]
0x18004123c  mov     qword ptr [rsp+78h+var_48.x], this; ptl
0x180041241  mov     ecx, [rdi+80h]
0x180041247  mov     [rsp+78h+grfKeyState], ecx; grfKeyState
0x18004124b  mov     this, rbp; hwnd
0x18004124e  mov     [rsp+78h+pIDataObject], rax; pIDataObject
0x180041253  call    ?PrivDragDrop@@YAJPEAUHWND__@@PEAUIDropTarget@@W4tagDRAGOP@@PEAUtagInterfaceData@@PEAUIDataObject@@KU_POINTL@@PEAK0PEAPEAX@Z; PrivDragDrop(HWND__ *,IDropTarget *,tagDRAGOP,tagInterfaceData *,IDataObject *,ulong,_POINTL,ulong *,HWND__ *,void * *)
0x180041258  mov     this, rbx
0x18004125b  mov     esi, eax
0x18004125d  call    cs:__imp_SetThreadDpiAwarenessContext
0x180041263  test    esi, esi
0x180041265  jz      short loc_180041275
0x180041267  xor     ebp, ebp
0x180041269  cmp     esi, 80070005h
0x18004126f  jz      loc_1800412FA
0x180041275  test    rbp, rbp
0x180041278  jnz     short loc_18004128D
0x18004127a  test    r14, r14
0x18004127d  jnz     short loc_18004128D
0x18004127f  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180041284  test    al, al
0x180041286  jz      short loc_1800412FA
0x180041288  test    r15, r15
0x18004128b  jz      short loc_1800412FA
0x18004128d  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180041294  xor     edx, edx; dwFlags
0x180041296  lea     r8d, [hwnd31+38h]; dwBytes
0x18004129a  call    cs:__imp_HeapAlloc
0x1800412a0  test    rax, rax
0x1800412a3  jz      short loc_1800412EF
0x1800412a5  mov     this, [rdi+60h]
0x1800412a9  xor     esi, esi
0x1800412ab  mov     edx, [this]
0x1800412ad  mov     this, [rsp+78h+hDDInfo]
0x1800412b5  mov     [rax+20h], this
0x1800412b9  mov     [rax], rbp
0x1800412bc  mov     [rax+8], r14
0x1800412c0  mov     [rax+10h], edx
0x1800412c3  mov     [rax+18h], rdi
0x1800412c7  mov     byte ptr [rax+28h], 0
0x1800412cb  mov     dword ptr [rax+2Ch], 8000FFFFh
0x1800412d2  mov     qword ptr [rax+30h], 0
0x1800412da  mov     this, [rdi+60h]
0x1800412de  cmp     [this], esi
0x1800412e0  jnz     short loc_1800412F6
0x1800412e2  test    r14, r14
0x1800412e5  jz      short loc_1800412F6
0x1800412e7  mov     dword ptr [this], 1
0x1800412ed  jmp     short loc_1800412F6
0x1800412ef  mov     esi, 8007000Eh
0x1800412f4  xor     eax, eax
0x1800412f6  mov     [rdi+30h], rax
0x1800412fa  mov     rbx, [rsp+78h+arg_8]
0x180041302  mov     eax, esi
0x180041304  add     rsp, 50h
0x180041308  pop     r15
0x18004130a  pop     r14
0x18004130c  pop     rdi
0x18004130d  pop     rsi
0x18004130e  pop     rbp
0x18004130f  retn
```

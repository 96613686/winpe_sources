# CDragOperation::GetDropTarget(HWND__ *,HWND__ *,IDropTarget *)

- ea: `0x180043524`
- end: `0x1800436d7`
- name: `?GetDropTarget@CDragOperation@@AEAAJPEAUHWND__@@0PEAUIDropTarget@@@Z`
- size: `435`
- prototype: `HRESULT __fastcall(CDragOperation *this, HWND__ *hwnd31, HWND__ *hwndDropTarget, IDropTarget *nonRPCSSRegisteredDropTarget)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b140`

## callees

- `0x18000a690`
- `0x18000ba70`
- `0x180043524`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043657`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043657`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800435a1`
- `USER32!SetThreadDpiAwarenessContext` at `0x180043614`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800435a1`
- `USER32!SetThreadDpiAwarenessContext` at `0x180043614`
- `USER32!GetWindowDpiAwarenessContext` at `0x180043592`
- `USER32!GetWindowDpiAwarenessContext` at `0x180043592`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x180043583`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x180043583`

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
  void *v13; // rcx
  CDropTargetAdapter *v14; // rcx
  unsigned int *pdwEffect; // rdx
  _POINTL ptl; // [rsp+80h] [rbp+8h] BYREF
  void *hDDInfo; // [rsp+90h] [rbp+18h] BYREF

  hDDInfo = 0;
  this->_pDropTargetAdapter = 0;
  v5 = hwndDropTarget;
  v8 = -2147467259;
  if ( !hwndDropTarget && (!IsContainerDragOperation() || !nonRPCSSRegisteredDropTarget) )
    goto LABEL_9;
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
    v13 = hDDInfo;
    v11->_isEnterpriseDropTarget = 0;
    v11->_supportsEvaluatingEdpPolicy = 0;
    v11->_hDDInfo = v13;
    v14 = v11;
    v11->_hwndOLE = v5;
    v11->_hwnd31 = hwnd31;
    v11->_dwEffectLast = v12;
    v11->_pdo = this;
    v11->_checkedForEnterpriseDropTarget = 0;
    v11->_hrEnterpriseDropTargetCheck = -2147418113;
    pdwEffect = this->_pdwEffect;
    if ( !*pdwEffect && hwnd31 )
      *pdwEffect = 1;
  }
  else
  {
    v14 = 0;
    v8 = -2147024882;
  }
  this->_pDropTargetAdapter = v14;
  return v8;
}

```

## disassembly

```asm
0x180043524  mov     rax, rsp
0x180043527  mov     [rax+10h], rbx
0x18004352b  push    rbp
0x18004352c  push    rsi
0x18004352d  push    rdi
0x18004352e  push    r14
0x180043530  push    r15
0x180043532  sub     rsp, 50h
0x180043536  and     qword ptr [rax+18h], 0
0x18004353b  mov     r15, nonRPCSSRegisteredDropTarget
0x18004353e  and     qword ptr [this+30h], 0
0x180043543  mov     rbp, hwndDropTarget
0x180043546  mov     r14, hwnd31
0x180043549  mov     rdi, this
0x18004354c  mov     esi, 80004005h
0x180043551  test    hwndDropTarget, hwndDropTarget
0x180043554  jnz     short loc_18004356C
0x180043556  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18004355b  test    al, al
0x18004355d  jz      loc_180043637
0x180043563  test    r15, r15
0x180043566  jz      loc_180043637
0x18004356c  mov     rax, [rdi+50h]
0x180043570  lea     hwnd31, [rsp+78h+ptl]
0x180043578  mov     this, rbp
0x18004357b  mov     qword ptr [rsp+78h+ptl.x], rax
0x180043583  call    cs:__imp_PhysicalToLogicalDpiPointForWindow
0x18004358a  nop     dword ptr [rax+rax+00h]
0x18004358f  mov     this, rbp
0x180043592  call    cs:__imp_GetWindowDpiAwarenessContext
0x180043599  nop     dword ptr [rax+rax+00h]
0x18004359e  mov     this, rax
0x1800435a1  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800435a8  nop     dword ptr [rax+rax+00h]
0x1800435ad  mov     ecx, [rdi+0C8h]
0x1800435b3  mov     rbx, rax
0x1800435b6  mov     hwnd31, [rdi+60h]
0x1800435ba  lea     rax, [rsp+78h+hDDInfo]
0x1800435c2  mov     r10d, [rdi+80h]
0x1800435c9  neg     ecx
0x1800435cb  mov     this, qword ptr [rsp+78h+ptl.x]
0x1800435d3  mov     r11, [rdi+10h]
0x1800435d7  sbb     r8d, r8d
0x1800435da  mov     nonRPCSSRegisteredDropTarget, [rdi+18h]; pIFDDataObject
0x1800435de  and     r8d, 4
0x1800435e2  mov     [rsp+78h+phDDInfo], rax; phDDInfo
0x1800435e7  inc     r8d; dop
0x1800435ea  and     [rsp+78h+var_38], 0
0x1800435f0  mov     [rsp+78h+pdwEffect], hwnd31; pdwEffect
0x1800435f5  mov     hwnd31, r15; pWinRtTarget
0x1800435f8  mov     qword ptr [rsp+78h+var_48.x], this; ptl
0x1800435fd  mov     this, rbp; hwnd
0x180043600  mov     [rsp+78h+grfKeyState], r10d; grfKeyState
0x180043605  mov     [rsp+78h+pIDataObject], r11; pIDataObject
0x18004360a  call    ?PrivDragDrop@@YAJPEAUHWND__@@PEAUIDropTarget@@W4tagDRAGOP@@PEAUtagInterfaceData@@PEAUIDataObject@@KU_POINTL@@PEAK0PEAPEAX@Z; PrivDragDrop(HWND__ *,IDropTarget *,tagDRAGOP,tagInterfaceData *,IDataObject *,ulong,_POINTL,ulong *,HWND__ *,void * *)
0x18004360f  mov     this, rbx
0x180043612  mov     esi, eax
0x180043614  call    cs:__imp_SetThreadDpiAwarenessContext
0x18004361b  nop     dword ptr [rax+rax+00h]
0x180043620  test    esi, esi
0x180043622  jz      short loc_180043632
0x180043624  xor     ebp, ebp
0x180043626  cmp     esi, 80070005h
0x18004362c  jz      loc_1800436C0
0x180043632  test    rbp, rbp
0x180043635  jnz     short loc_18004364A
0x180043637  test    r14, r14
0x18004363a  jnz     short loc_18004364A
0x18004363c  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x180043641  test    al, al
0x180043643  jz      short loc_1800436C0
0x180043645  test    r15, r15
0x180043648  jz      short loc_1800436C0
0x18004364a  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180043651  xor     edx, edx; dwFlags
0x180043653  lea     r8d, [hwnd31+38h]; dwBytes
0x180043657  call    cs:__imp_HeapAlloc
0x18004365e  nop     dword ptr [rax+rax+00h]
0x180043663  test    rax, rax
0x180043666  jz      short loc_1800436B5
0x180043668  mov     this, [rdi+60h]
0x18004366c  xor     esi, esi
0x18004366e  mov     edx, [this]
0x180043670  mov     this, [rsp+78h+hDDInfo]
0x180043678  and     dword ptr [rax+30h], 0
0x18004367c  and     dword ptr [rax+34h], 0
0x180043680  mov     [rax+20h], this
0x180043684  mov     this, rax
0x180043687  mov     [rax], rbp
0x18004368a  mov     [rax+8], r14
0x18004368e  mov     [rax+10h], edx
0x180043691  mov     [rax+18h], rdi
0x180043695  mov     byte ptr [rax+28h], 0
0x180043699  mov     dword ptr [rax+2Ch], 8000FFFFh
0x1800436a0  mov     hwnd31, [rdi+60h]
0x1800436a4  cmp     [hwnd31], esi
0x1800436a6  jnz     short loc_1800436BC
0x1800436a8  test    r14, r14
0x1800436ab  jz      short loc_1800436BC
0x1800436ad  mov     dword ptr [hwnd31], 1
0x1800436b3  jmp     short loc_1800436BC
0x1800436b5  xor     ecx, ecx
0x1800436b7  mov     esi, 8007000Eh
0x1800436bc  mov     [rdi+30h], this
0x1800436c0  mov     rbx, [rsp+78h+arg_8]
0x1800436c8  mov     eax, esi
0x1800436ca  add     rsp, 50h
0x1800436ce  pop     r15
0x1800436d0  pop     r14
0x1800436d2  pop     rdi
0x1800436d3  pop     rsi
0x1800436d4  pop     rbp
0x1800436d5  retn
```

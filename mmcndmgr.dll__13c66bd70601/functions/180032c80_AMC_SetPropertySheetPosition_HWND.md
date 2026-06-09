# AMC::SetPropertySheetPosition(HWND__ *)

- ea: `0x180032c80`
- end: `0x180033018`
- name: `?SetPropertySheetPosition@AMC@@YAXPEAUHWND__@@@Z`
- size: `920`
- prototype: `void __fastcall(HWND hWnd, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800324e4`

## callees

- `0x180004890`
- `0x180032c80`
- `0x1800499e0`
- `0x1800e2448`
- `0x180134540`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180032ff1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032ff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032dc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032dc8`
- `USER32!FindWindowExW` at `0x180032e3f`
- `USER32!FindWindowExW` at `0x180032e3f`
- `USER32!GetWindowThreadProcessId` at `0x180032dc2`
- `USER32!GetWindowThreadProcessId` at `0x180032dc2`
- `USER32!CopyRect` at `0x180032eed`
- `USER32!CopyRect` at `0x180032eed`
- `USER32!SystemParametersInfoW` at `0x180032f01`
- `USER32!SystemParametersInfoW` at `0x180032f01`
- `USER32!SetRect` at `0x180032f22`
- `USER32!SetRect` at `0x180032f22`
- `USER32!GetMonitorInfoW` at `0x180032edb`
- `USER32!GetMonitorInfoW` at `0x180032edb`
- `USER32!MonitorFromPoint` at `0x180032ead`
- `USER32!MonitorFromPoint` at `0x180032f55`
- `USER32!MonitorFromPoint` at `0x180032f67`
- `USER32!MonitorFromPoint` at `0x180032ead`
- `USER32!MonitorFromPoint` at `0x180032f55`
- `USER32!MonitorFromPoint` at `0x180032f67`
- `USER32!MoveWindow` at `0x180032f98`
- `USER32!MoveWindow` at `0x180032f98`
- `USER32!GetSystemMetrics` at `0x180032d81`
- `USER32!GetSystemMetrics` at `0x180032d8f`
- `USER32!GetSystemMetrics` at `0x180032d81`
- `USER32!GetSystemMetrics` at `0x180032d8f`
- `USER32!GetWindowRect` at `0x180032cb5`
- `USER32!GetWindowRect` at `0x180032d17`
- `USER32!GetWindowRect` at `0x180032de7`
- `USER32!GetWindowRect` at `0x180032cb5`
- `USER32!GetWindowRect` at `0x180032d17`
- `USER32!GetWindowRect` at `0x180032de7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AMC::SetPropertySheetPosition(HWND hWnd, HWND a2)
{
  int v3; // r15d
  int v4; // r14d
  int top; // ebx
  int left; // edi
  HWND v7; // rcx
  int SystemMetrics; // r12d
  int v9; // r12d
  HWND i; // rdx
  HWND Window; // rax
  HWND v12; // rsi
  unsigned int j; // ecx
  __int64 *v14; // rax
  _DWORD *v15; // rdx
  int v16; // ecx
  LONG v17; // edi
  LONG v18; // ebx
  LONG v19; // esi
  LONG v20; // r12d
  HMONITOR v21; // rax
  int yBottom; // [rsp+20h] [rbp-99h]
  DWORD dwProcessId[2]; // [rsp+30h] [rbp-89h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-81h] BYREF
  __int64 v25; // [rsp+40h] [rbp-79h]
  _BYTE v26[16]; // [rsp+48h] [rbp-71h] BYREF
  struct tagRECT v27; // [rsp+58h] [rbp-61h] BYREF
  struct tagRECT rcDst; // [rsp+68h] [rbp-51h] BYREF
  tagRECT Rect; // [rsp+78h] [rbp-41h] BYREF
  struct tagRECT v30; // [rsp+88h] [rbp-31h] BYREF
  tagMONITORINFO mi; // [rsp+98h] [rbp-21h] BYREF

  Rect = 0;
  GetWindowRect(hWnd, &Rect);
  v3 = Rect.right - Rect.left;
  v4 = Rect.bottom - Rect.top;
  if ( byte_1801C7F34 )
  {
    top = ::Rect.top;
    left = ::Rect.left;
  }
  else
  {
    top = 0;
    ::Rect.top = 0;
    left = 0;
    ::Rect.left = 0;
    *(_QWORD *)&::Rect.right = 0;
    if ( CScopeTree::m_pScopeTree )
    {
      v7 = *(HWND *)(*((_QWORD *)CScopeTree::m_pScopeTree + 23) + 8LL);
      v27 = 0;
      GetWindowRect(v7, &v27);
      top = (v27.top + v27.bottom) / 2 - v4 / 2;
      ::Rect.top = top;
      left = (v27.left + v27.right) / 2 - v3 / 2;
      ::Rect.left = left;
      ::Rect.right = left + v3;
      ::Rect.bottom = top + v4;
    }
    byte_1801C7F34 = 1;
  }
  SystemMetrics = GetSystemMetrics(8);
  v9 = GetSystemMetrics(4) + SystemMetrics;
  v25 = 0;
  v24 = (_QWORD *)std::_Tree_alloc<0,std::_Tree_base_types<unsigned int>>::_Buyheadnode();
  for ( i = 0; ; i = v12 )
  {
    Window = FindWindowExW(0, i, (LPCWSTR)0x8002, 0);
    v12 = Window;
    if ( !Window )
      break;
    dwProcessId[0] = 0;
    GetWindowThreadProcessId(Window, dwProcessId);
    if ( dwProcessId[0] == GetCurrentProcessId() && v12 != hWnd )
    {
      v30 = 0;
      GetWindowRect(v12, &v30);
      if ( v30.top >= top )
      {
        v27.left = (v30.top - top) / v9;
        if ( v30.left == left + v9 * v27.left && v30.top == top + v9 * v27.left )
        {
          LOBYTE(yBottom) = byte_1801C7877;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
            &v24,
            v26,
            (unsigned int)v30.top,
            &v27,
            yBottom);
        }
      }
    }
  }
  for ( j = 0; ; ++j )
  {
    v14 = (__int64 *)v24[1];
    v15 = v24;
    while ( !*((_BYTE *)v14 + 25) )
    {
      if ( *((_DWORD *)v14 + 7) >= j )
      {
        v15 = v14;
        v14 = (__int64 *)*v14;
      }
      else
      {
        v14 = (__int64 *)v14[2];
      }
    }
    if ( v15 == (_DWORD *)v24 || j < v15[7] )
      v15 = v24;
    if ( v15 == (_DWORD *)v24 )
      break;
  }
  v16 = v9 * j;
  v17 = v16 + left;
  v18 = v16 + top;
  v19 = v18 + v4;
  v20 = v17 + v3;
  *(_QWORD *)&v27.left = __PAIR64__(v18, v17);
  v21 = MonitorFromPoint((POINT)__PAIR64__(v18, v17), 2u);
  mi.cbSize = 40;
  memset(&mi.rcMonitor, 0, 36);
  rcDst = 0;
  if ( v21 && GetMonitorInfoW(v21, &mi) )
  {
    CopyRect(&rcDst, &mi.rcWork);
  }
  else if ( !SystemParametersInfoW(0x30u, 0, &rcDst, 0) )
  {
    SetRect(&rcDst, 0, 0, 639, 479);
  }
  if ( v17 < rcDst.left )
  {
    v17 = rcDst.left;
    v20 = v3 + rcDst.left;
  }
  if ( v18 < rcDst.top )
  {
    v18 = rcDst.top;
    v19 = v4 + rcDst.top;
  }
  *(_QWORD *)&v27.left = __PAIR64__(v18, v17);
  dwProcessId[0] = v20;
  dwProcessId[1] = v19;
  if ( !MonitorFromPoint((POINT)__PAIR64__(v18, v17), 0) || !MonitorFromPoint(*(POINT *)dwProcessId, 0) )
  {
    v17 = rcDst.left;
    v18 = rcDst.top;
    v19 = v4 + rcDst.top;
    v20 = v3 + rcDst.left;
  }
  MoveWindow(hWnd, v17, v18, v3, v4, 1);
  ::Rect.left = v17;
  ::Rect.top = v18;
  ::Rect.right = v20;
  ::Rect.bottom = v19;
  std::_Tree<std::_Tmap_traits<CNode *,CMMCClipBoardDataObject *,std::less<CNode *>,std::allocator<std::pair<CNode * const,CMMCClipBoardDataObject *>>,1>>::_Erase(
    &v24,
    v24[1]);
  v24[1] = v24;
  *v24 = v24;
  v24[2] = v24;
  v25 = 0;
  operator delete(v24);
}

```

## disassembly

```asm
0x180032c80  push    rbp
0x180032c82  push    rbx
0x180032c83  push    rsi
0x180032c84  push    rdi
0x180032c85  push    r12
0x180032c87  push    r13
0x180032c89  push    r14
0x180032c8b  push    r15
0x180032c8d  lea     rbp, [rsp-1Fh]
0x180032c92  sub     rsp, 0D8h
0x180032c99  mov     rax, cs:__security_cookie
0x180032ca0  xor     rax, rsp
0x180032ca3  mov     [rbp+57h+var_50], rax
0x180032ca7  mov     r13, rcx
0x180032caa  xorps   xmm0, xmm0
0x180032cad  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180032cb1  lea     rdx, [rbp+57h+Rect]; lpRect
0x180032cb5  call    cs:__imp_GetWindowRect
0x180032cbb  mov     r15d, [rbp+57h+Rect.right]
0x180032cbf  sub     r15d, [rbp+57h+Rect.left]
0x180032cc3  mov     r14d, [rbp+57h+Rect.bottom]
0x180032cc7  sub     r14d, [rbp+57h+Rect.top]
0x180032ccb  xor     esi, esi
0x180032ccd  lea     r12d, [rsi+2]
0x180032cd1  cmp     cs:byte_1801C7F34, sil
0x180032cd8  jnz     loc_180032D70
0x180032cde  mov     ebx, esi
0x180032ce0  mov     cs:Rect.top, ebx
0x180032ce6  mov     edi, esi
0x180032ce8  mov     cs:Rect.left, esi
0x180032cee  mov     qword ptr cs:Rect.right, rsi
0x180032cf5  mov     rax, cs:?m_pScopeTree@CScopeTree@@0PEAV1@EA; CScopeTree * CScopeTree::m_pScopeTree
0x180032cfc  test    rax, rax
0x180032cff  jz      short loc_180032D67
0x180032d01  mov     rax, [rax+0B8h]
0x180032d08  mov     rcx, [rax+8]; hWnd
0x180032d0c  xorps   xmm0, xmm0
0x180032d0f  movups  xmmword ptr [rbp+57h+var_B8.left], xmm0
0x180032d13  lea     rdx, [rbp+57h+var_B8]; lpRect
0x180032d17  call    cs:__imp_GetWindowRect
0x180032d1d  mov     eax, [rbp+57h+var_B8.bottom]
0x180032d20  add     eax, [rbp+57h+var_B8.top]
0x180032d23  cdq
0x180032d24  idiv    r12d
0x180032d27  mov     ebx, eax
0x180032d29  mov     eax, r14d
0x180032d2c  cdq
0x180032d2d  idiv    r12d
0x180032d30  sub     ebx, eax
0x180032d32  mov     cs:Rect.top, ebx
0x180032d38  mov     eax, [rbp+57h+var_B8.right]
0x180032d3b  add     eax, [rbp+57h+var_B8.left]
0x180032d3e  cdq
0x180032d3f  idiv    r12d
0x180032d42  mov     edi, eax
0x180032d44  mov     eax, r15d
0x180032d47  cdq
0x180032d48  idiv    r12d
0x180032d4b  sub     edi, eax
0x180032d4d  mov     cs:Rect.left, edi
0x180032d53  lea     ecx, [rdi+r15]
0x180032d57  mov     cs:Rect.right, ecx
0x180032d5d  lea     ecx, [rbx+r14]
0x180032d61  mov     cs:Rect.bottom, ecx
0x180032d67  mov     cs:byte_1801C7F34, 1
0x180032d6e  jmp     short loc_180032D7C
0x180032d70  mov     ebx, cs:Rect.top
0x180032d76  mov     edi, cs:Rect.left
0x180032d7c  mov     ecx, 8; nIndex
0x180032d81  call    cs:__imp_GetSystemMetrics
0x180032d87  mov     r12d, eax
0x180032d8a  mov     ecx, 4; nIndex
0x180032d8f  call    cs:__imp_GetSystemMetrics
0x180032d95  add     r12d, eax
0x180032d98  mov     [rsp+110h+var_D8], rsi
0x180032d9d  mov     [rbp+57h+var_D0], rsi
0x180032da1  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@IV?$allocator@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<uint>>::_Buyheadnode(void)
0x180032da6  mov     [rsp+110h+var_D8], rax
0x180032dab  xor     edx, edx
0x180032dad  jmp     loc_180032E34
0x180032db2  mov     [rsp+110h+dwProcessId], 0
0x180032dba  lea     rdx, [rsp+110h+dwProcessId]; lpdwProcessId
0x180032dbf  mov     rcx, rsi; hWnd
0x180032dc2  call    cs:__imp_GetWindowThreadProcessId
0x180032dc8  call    cs:__imp_GetCurrentProcessId
0x180032dce  cmp     [rsp+110h+dwProcessId], eax
0x180032dd2  jnz     short loc_180032E31
0x180032dd4  cmp     rsi, r13
0x180032dd7  jz      short loc_180032E31
0x180032dd9  xorps   xmm0, xmm0
0x180032ddc  movups  xmmword ptr [rbp+57h+var_88.left], xmm0
0x180032de0  lea     rdx, [rbp+57h+var_88]; lpRect
0x180032de4  mov     rcx, rsi; hWnd
0x180032de7  call    cs:__imp_GetWindowRect
0x180032ded  mov     r8d, [rbp+57h+var_88.top]
0x180032df1  cmp     r8d, ebx
0x180032df4  jl      short loc_180032E31
0x180032df6  mov     eax, r8d
0x180032df9  sub     eax, ebx
0x180032dfb  cdq
0x180032dfc  idiv    r12d
0x180032dff  mov     [rbp+57h+var_B8.left], eax
0x180032e02  imul    eax, r12d
0x180032e06  lea     ecx, [rdi+rax]
0x180032e09  cmp     [rbp+57h+var_88.left], ecx
0x180032e0c  jnz     short loc_180032E31
0x180032e0e  add     eax, ebx
0x180032e10  cmp     r8d, eax
0x180032e13  jnz     short loc_180032E31
0x180032e15  mov     al, cs:byte_1801C7877
0x180032e1b  mov     byte ptr [rsp+110h+yBottom], al
0x180032e1f  lea     r9, [rbp+57h+var_B8]
0x180032e23  lea     rdx, [rbp+57h+var_C8]
0x180032e27  lea     rcx, [rsp+110h+var_D8]
0x180032e2c  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x180032e31  mov     rdx, rsi; hWndChildAfter
0x180032e34  xor     r9d, r9d; lpszWindow
0x180032e37  mov     r8d, 8002h; lpszClass
0x180032e3d  xor     ecx, ecx; hWndParent
0x180032e3f  call    cs:__imp_FindWindowExW
0x180032e45  test    rax, rax
0x180032e48  mov     rsi, rax
0x180032e4b  jnz     loc_180032DB2
0x180032e51  xor     ecx, ecx
0x180032e53  mov     r8, [rsp+110h+var_D8]
0x180032e58  mov     rax, [r8+8]
0x180032e5c  mov     rdx, r8
0x180032e5f  jmp     short loc_180032E72
0x180032e61  cmp     [rax+1Ch], ecx
0x180032e64  jnb     short loc_180032E6C
0x180032e66  mov     rax, [rax+10h]
0x180032e6a  jmp     short loc_180032E72
0x180032e6c  mov     rdx, rax
0x180032e6f  mov     rax, [rax]
0x180032e72  cmp     byte ptr [rax+19h], 0
0x180032e76  jz      short loc_180032E61
0x180032e78  cmp     rdx, r8
0x180032e7b  jz      short loc_180032E82
0x180032e7d  cmp     ecx, [rdx+1Ch]
0x180032e80  jnb     short loc_180032E85
0x180032e82  mov     rdx, r8
0x180032e85  cmp     rdx, r8
0x180032e88  jz      short loc_180032E8E
0x180032e8a  inc     ecx
0x180032e8c  jmp     short loc_180032E58
0x180032e8e  imul    ecx, r12d
0x180032e92  add     edi, ecx
0x180032e94  add     ebx, ecx
0x180032e96  lea     esi, [rbx+r14]
0x180032e9a  lea     r12d, [rdi+r15]
0x180032e9e  mov     [rbp+57h+var_B8.left], edi
0x180032ea1  mov     [rbp+57h+var_B8.top], ebx
0x180032ea4  mov     edx, 2; dwFlags
0x180032ea9  mov     rcx, qword ptr [rbp+57h+var_B8.left]; pt
0x180032ead  call    cs:__imp_MonitorFromPoint
0x180032eb3  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180032eba  xorps   xmm0, xmm0
0x180032ebd  xor     ecx, ecx
0x180032ebf  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x180032ec3  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x180032ec7  mov     [rbp+57h+mi.dwFlags], ecx
0x180032eca  movdqu  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180032ecf  test    rax, rax
0x180032ed2  jz      short loc_180032EF5
0x180032ed4  lea     rdx, [rbp+57h+mi]; lpmi
0x180032ed8  mov     rcx, rax; hMonitor
0x180032edb  call    cs:__imp_GetMonitorInfoW
0x180032ee1  test    eax, eax
0x180032ee3  jz      short loc_180032EF5
0x180032ee5  lea     rdx, [rbp+57h+mi.rcWork]; lprcSrc
0x180032ee9  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180032eed  call    cs:__imp_CopyRect
0x180032ef3  jmp     short loc_180032F28
0x180032ef5  xor     r9d, r9d; fWinIni
0x180032ef8  lea     r8, [rbp+57h+rcDst]; pvParam
0x180032efc  xor     edx, edx; uiParam
0x180032efe  lea     ecx, [rdx+30h]; uiAction
0x180032f01  call    cs:__imp_SystemParametersInfoW
0x180032f07  test    eax, eax
0x180032f09  jnz     short loc_180032F28
0x180032f0b  mov     [rsp+110h+yBottom], 1DFh; yBottom
0x180032f13  mov     r9d, 27Fh; xRight
0x180032f19  xor     r8d, r8d; yTop
0x180032f1c  xor     edx, edx; xLeft
0x180032f1e  lea     rcx, [rbp+57h+rcDst]; lprc
0x180032f22  call    cs:__imp_SetRect
0x180032f28  cmp     edi, [rbp+57h+rcDst.left]
0x180032f2b  jge     short loc_180032F34
0x180032f2d  mov     edi, [rbp+57h+rcDst.left]
0x180032f30  lea     r12d, [r15+rdi]
0x180032f34  cmp     ebx, [rbp+57h+rcDst.top]
0x180032f37  jge     short loc_180032F40
0x180032f39  mov     ebx, [rbp+57h+rcDst.top]
0x180032f3c  lea     esi, [r14+rbx]
0x180032f40  mov     [rbp+57h+var_B8.left], edi
0x180032f43  mov     [rbp+57h+var_B8.top], ebx
0x180032f46  mov     [rsp+110h+dwProcessId], r12d
0x180032f4b  mov     [rsp+110h+dwProcessId+4], esi
0x180032f4f  xor     edx, edx; dwFlags
0x180032f51  mov     rcx, qword ptr [rbp+57h+var_B8.left]; pt
0x180032f55  call    cs:__imp_MonitorFromPoint
0x180032f5b  test    rax, rax
0x180032f5e  jz      short loc_180032F72
0x180032f60  xor     edx, edx; dwFlags
0x180032f62  mov     rcx, qword ptr [rsp+110h+dwProcessId]; pt
0x180032f67  call    cs:__imp_MonitorFromPoint
0x180032f6d  test    rax, rax
0x180032f70  jnz     short loc_180032F80
0x180032f72  mov     edi, [rbp+57h+rcDst.left]
0x180032f75  mov     ebx, [rbp+57h+rcDst.top]
0x180032f78  lea     esi, [r14+rbx]
0x180032f7c  lea     r12d, [r15+rdi]
0x180032f80  mov     [rsp+110h+bRepaint], 1; bRepaint
0x180032f88  mov     [rsp+110h+yBottom], r14d; nHeight
0x180032f8d  mov     r9d, r15d; nWidth
0x180032f90  mov     r8d, ebx; Y
0x180032f93  mov     edx, edi; X
0x180032f95  mov     rcx, r13; hWnd
0x180032f98  call    cs:__imp_MoveWindow
0x180032f9e  mov     cs:Rect.left, edi
0x180032fa4  mov     cs:Rect.top, ebx
0x180032faa  mov     cs:Rect.right, r12d
0x180032fb1  mov     cs:Rect.bottom, esi
0x180032fb7  mov     rdx, [rsp+110h+var_D8]
0x180032fbc  mov     rdx, [rdx+8]
0x180032fc0  lea     rcx, [rsp+110h+var_D8]
0x180032fc5  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEAVCNode@@PEAVCMMCClipBoardDataObject@@U?$less@PEAVCNode@@@std@@V?$allocator@U?$pair@QEAVCNode@@PEAVCMMCClipBoardDataObject@@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAVCNode@@PEAVCMMCClipBoardDataObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<CNode *,CMMCClipBoardDataObject *,std::less<CNode *>,std::allocator<std::pair<CNode * const,CMMCClipBoardDataObject *>>,1>>::_Erase(std::_Tree_node<std::pair<CNode * const,CMMCClipBoardDataObject *>,void *> *)
0x180032fca  mov     rax, [rsp+110h+var_D8]
0x180032fcf  mov     [rax+8], rax
0x180032fd3  mov     rax, [rsp+110h+var_D8]
0x180032fd8  mov     [rax], rax
0x180032fdb  mov     rax, [rsp+110h+var_D8]
0x180032fe0  mov     [rax+10h], rax
0x180032fe4  mov     [rbp+57h+var_D0], 0
0x180032fec  mov     rcx, [rsp+110h+var_D8]
0x180032ff1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032ff7  nop
0x180032ff8  mov     rcx, [rbp+57h+var_50]
0x180032ffc  xor     rcx, rsp; StackCookie
0x180032fff  call    __security_check_cookie
0x180033004  add     rsp, 0D8h
0x18003300b  pop     r15
0x18003300d  pop     r14
0x18003300f  pop     r13
0x180033011  pop     r12
0x180033013  pop     rdi
0x180033014  pop     rsi
0x180033015  pop     rbx
0x180033016  pop     rbp
0x180033017  retn
```

# TV_OnCreate(HWND__ *,tagCREATESTRUCTW *)

- ea: `0x1800201f0`
- end: `0x180020491`
- name: `?TV_OnCreate@@YA_JPEAUHWND__@@PEAUtagCREATESTRUCTW@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(HWND, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x180005914`
- `0x180011f44`
- `0x1800201f0`
- `0x1800216a4`
- `0x180025e44`
- `0x1800553b4`
- `0x18006a690`
- `0x18006cfe0`
- `0x1800c6d54`
- `0x1800e4800`
- `0x1800eecb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020203`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020203`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020455`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020217`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002044f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020463`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002044f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020463`
- `USER32!GetSysColorBrush` at `0x180020301`
- `USER32!GetSysColorBrush` at `0x18002036c`
- `USER32!GetSysColorBrush` at `0x180020301`
- `USER32!GetSysColorBrush` at `0x18002036c`
- `USER32!SetScrollRange` at `0x1800203ee`
- `USER32!SetScrollRange` at `0x180020405`
- `USER32!SetScrollRange` at `0x1800203ee`
- `USER32!SetScrollRange` at `0x180020405`
- `USER32!SetWindowLongPtrW` at `0x18002028f`
- `USER32!SetWindowLongPtrW` at `0x18002028f`
- `USER32!__imp_IsWindowGdiScaled` at `0x1800203b3`
- `USER32!__imp_IsWindowGdiScaled` at `0x1800203b3`
- `USER32!__imp_EnableWindowGDIScaledDpiMessage` at `0x18002047a`
- `USER32!__imp_EnableWindowGDIScaledDpiMessage` at `0x18002047a`
- `UxTheme!OpenThemeData` at `0x180020335`
- `UxTheme!OpenThemeData` at `0x180020383`
- `UxTheme!OpenThemeData` at `0x180020335`
- `UxTheme!OpenThemeData` at `0x180020383`

## pseudocode

```c
__int64 __fastcall TV_OnCreate(HWND a1, struct tagCREATESTRUCTW *a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rbx
  HDPA *v6; // rsi
  HDPA v7; // rax
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rdi
  void *v11; // rcx
  HBRUSH SysColorBrush; // rax
  HWND v13; // rcx
  HTHEME v14; // rax
  void *v15; // rsi
  CCompositedDraw *v16; // rcx
  HBRUSH v17; // rax
  HWND v18; // rcx
  HTHEME v19; // rax
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // eax
  HANDLE v24; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0x260u);
  if ( !v5 )
    return -1;
  v5[37] = GetProcessHeap();
  v6 = (HDPA *)(v5 + 21);
  if ( !(unsigned int)TV_CreateRoot((struct _TREE *)v5) )
    goto LABEL_18;
  v7 = DPA_CreateEx(8, 0);
  *v6 = v7;
  if ( !v7 )
    goto LABEL_18;
  v9 = DirectUI::AccHAllocAndZero((DirectUI *)0x38, v8);
  if ( v9 )
    *v9 = &CCompositedDraw::`vftable';
  v5[73] = v9;
  if ( v9 )
  {
    v10 = 0;
    SetWindowLongPtrW(a1, 0, (LONG_PTR)v5);
    v11 = (void *)v5[37];
    ++*((_DWORD *)v5 + 150);
    v5[71] = TV_ConstructAnimationEngine(v11);
    CIInitialize(v5);
    if ( (a2->dwExStyle & 0x2000) != 0 )
      *((_DWORD *)v5 + 4) |= 0x40u;
    *((_DWORD *)v5 + 16) |= 0x10u;
    *((_DWORD *)v5 + 84) = -16777216;
    *((_DWORD *)v5 + 82) = -1;
    *((_DWORD *)v5 + 83) = -1;
    *((_DWORD *)v5 + 85) = -16777216;
    *((_DWORD *)v5 + 86) = -16777216;
    SysColorBrush = GetSysColorBrush(17);
    v13 = (HWND)*v5;
    v5[38] = SysColorBrush;
    *((_WORD *)v5 + 180) = 3;
    *((_DWORD *)v5 + 101) = 150;
    *((_DWORD *)v5 + 102) = 15;
    v14 = OpenThemeData(v13, L"TreeView");
    v15 = v14;
    if ( v14 )
      TV_InitThemeMetrics((struct _TREE *)v5, v14);
    v16 = (CCompositedDraw *)v5[73];
    v5[61] = v15;
    CCompositedDraw::InitializeCompositedDraw(v16, a1, v15);
    v17 = GetSysColorBrush(8);
    v18 = (HWND)*v5;
    v5[39] = v17;
    v19 = OpenThemeData(v18, L"Tooltip");
    v20 = *v5;
    v5[74] = v19;
    *((_WORD *)v5 + 187) = 1;
    *((_DWORD *)v5 + 100) = -1;
    *((_DWORD *)v5 + 124) = 1;
    *((_DWORD *)v5 + 144) = 0x7FFFFFFF;
    if ( (unsigned int)IsWindowGdiScaled(v20) )
      EnableWindowGDIScaledDpiMessage(*v5, 1);
    TV_OnSetFont((struct _TREE *)v5, 0, v21);
    v22 = *((_DWORD *)v5 + 4);
    if ( (v22 & 2) != 0 )
      *((_DWORD *)v5 + 4) = v22 & 0xFFFFEFFF;
    TV_CreateToolTips((struct _TREE *)v5);
    SetScrollRange(a1, 0, 0, 0, 1);
    SetScrollRange(a1, 1, 0, 0, 1);
  }
  else
  {
LABEL_18:
    v10 = -1;
    if ( *v6 )
      DPA_Destroy(*v6);
    HeapFree((HANDLE)v5[37], 0, (LPVOID)v5[9]);
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v5);
  }
  return v10;
}

```

## disassembly

```asm
0x1800201f0  push    rbx
0x1800201f2  push    rbp
0x1800201f3  push    rsi
0x1800201f4  push    rdi
0x1800201f5  push    r14
0x1800201f7  push    r15
0x1800201f9  sub     rsp, 38h
0x1800201fd  mov     r14, rdx
0x180020200  mov     rbp, rcx
0x180020203  call    cs:__imp_GetProcessHeap
0x180020209  mov     edx, 8; dwFlags
0x18002020e  mov     r8d, 260h; dwBytes
0x180020214  mov     rcx, rax; hHeap
0x180020217  call    cs:__imp_HeapAlloc
0x18002021d  mov     rbx, rax
0x180020220  test    rax, rax
0x180020223  jz      loc_18002041B
0x180020229  call    cs:__imp_GetProcessHeap
0x18002022f  mov     rcx, rbx; struct _TREE *
0x180020232  mov     [rbx+128h], rax
0x180020239  lea     rsi, [rbx+0A8h]
0x180020240  call    ?TV_CreateRoot@@YAHPEAU_TREE@@@Z; TV_CreateRoot(_TREE *)
0x180020245  test    eax, eax
0x180020247  jz      loc_180020431
0x18002024d  xor     edx, edx; hheap
0x18002024f  lea     ecx, [rdx+8]; cpGrow
0x180020252  call    DPA_CreateEx
0x180020257  mov     [rsi], rax
0x18002025a  test    rax, rax
0x18002025d  jz      loc_180020431
0x180020263  mov     ecx, 38h ; '8'; this
0x180020268  call    ?AccHAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::AccHAllocAndZero(unsigned __int64)
0x18002026d  test    rax, rax
0x180020270  jz      loc_180020421
0x180020276  lea     rcx, ??_7CCompositedDraw@@6B@; const CCompositedDraw::`vftable'
0x18002027d  mov     [rax], rcx
0x180020280  jmp     loc_180020421
0x180020285  mov     r8, rbx; dwNewLong
0x180020288  xor     edx, edx; nIndex
0x18002028a  mov     rcx, rbp; hWnd
0x18002028d  xor     edi, edi
0x18002028f  call    cs:__imp_SetWindowLongPtrW
0x180020295  mov     rcx, [rbx+128h]; void *
0x18002029c  lea     r15d, [rdi+1]
0x1800202a0  add     [rbx+258h], r15d
0x1800202a7  call    ?TV_ConstructAnimationEngine@@YAPEAVCAnimationEngine@@PEAX@Z; TV_ConstructAnimationEngine(void *)
0x1800202ac  mov     r8, r14
0x1800202af  mov     [rbx+238h], rax
0x1800202b6  mov     rdx, rbp
0x1800202b9  mov     rcx, rbx
0x1800202bc  call    CIInitialize
0x1800202c1  test    dword ptr [r14+48h], 2000h
0x1800202c9  jnz     loc_18002046B
0x1800202cf  or      dword ptr [rbx+40h], 10h
0x1800202d3  mov     eax, 0FF000000h
0x1800202d8  or      r14d, 0FFFFFFFFh
0x1800202dc  mov     [rbx+150h], eax
0x1800202e2  mov     ecx, 11h; nIndex
0x1800202e7  mov     [rbx+148h], r14d
0x1800202ee  mov     [rbx+14Ch], r14d
0x1800202f5  mov     [rbx+154h], eax
0x1800202fb  mov     [rbx+158h], eax
0x180020301  call    cs:__imp_GetSysColorBrush
0x180020307  mov     rcx, [rbx]; hwnd
0x18002030a  lea     rdx, aTreeview; "TreeView"
0x180020311  mov     [rbx+130h], rax
0x180020318  mov     word ptr [rbx+168h], 3
0x180020321  mov     dword ptr [rbx+194h], 96h
0x18002032b  mov     dword ptr [rbx+198h], 0Fh
0x180020335  call    cs:__imp_OpenThemeData
0x18002033b  mov     rsi, rax
0x18002033e  test    rax, rax
0x180020341  jz      short loc_18002034E
0x180020343  mov     rdx, rax; hTheme
0x180020346  mov     rcx, rbx; struct _TREE *
0x180020349  call    ?TV_InitThemeMetrics@@YAXPEAU_TREE@@PEAX@Z; TV_InitThemeMetrics(_TREE *,void *)
0x18002034e  mov     rcx, [rbx+248h]; this
0x180020355  mov     r8, rsi; void *
0x180020358  mov     rdx, rbp; HWND
0x18002035b  mov     [rbx+1E8h], rsi
0x180020362  call    ?InitializeCompositedDraw@CCompositedDraw@@QEAAXPEAUHWND__@@PEAX@Z; CCompositedDraw::InitializeCompositedDraw(HWND__ *,void *)
0x180020367  mov     ecx, 8; nIndex
0x18002036c  call    cs:__imp_GetSysColorBrush
0x180020372  mov     rcx, [rbx]; hwnd
0x180020375  lea     rdx, aTooltip_0; "Tooltip"
0x18002037c  mov     [rbx+138h], rax
0x180020383  call    cs:__imp_OpenThemeData
0x180020389  mov     rcx, [rbx]
0x18002038c  mov     [rbx+250h], rax
0x180020393  mov     [rbx+176h], r15w
0x18002039b  mov     [rbx+190h], r14d
0x1800203a2  mov     [rbx+1F0h], r15d
0x1800203a9  mov     dword ptr [rbx+240h], 7FFFFFFFh
0x1800203b3  call    cs:__imp_IsWindowGdiScaled
0x1800203b9  test    eax, eax
0x1800203bb  jnz     loc_180020474
0x1800203c1  xor     edx, edx; h
0x1800203c3  mov     rcx, rbx; struct _TREE *
0x1800203c6  call    ?TV_OnSetFont@@YAXPEAU_TREE@@PEAUHFONT__@@H@Z; TV_OnSetFont(_TREE *,HFONT__ *,int)
0x1800203cb  mov     eax, [rbx+10h]
0x1800203ce  test    al, 2
0x1800203d0  jnz     loc_180020485
0x1800203d6  mov     rcx, rbx; struct _TREE *
0x1800203d9  call    ?TV_CreateToolTips@@YAXPEAU_TREE@@@Z; TV_CreateToolTips(_TREE *)
0x1800203de  xor     r9d, r9d; nMaxPos
0x1800203e1  mov     [rsp+68h+bRedraw], r15d; bRedraw
0x1800203e6  xor     r8d, r8d; nMinPos
0x1800203e9  xor     edx, edx; nBar
0x1800203eb  mov     rcx, rbp; hWnd
0x1800203ee  call    cs:__imp_SetScrollRange
0x1800203f4  xor     r9d, r9d; nMaxPos
0x1800203f7  mov     [rsp+68h+bRedraw], r15d; bRedraw
0x1800203fc  xor     r8d, r8d; nMinPos
0x1800203ff  mov     edx, r15d; nBar
0x180020402  mov     rcx, rbp; hWnd
0x180020405  call    cs:__imp_SetScrollRange
0x18002040b  mov     rax, rdi
0x18002040e  add     rsp, 38h
0x180020412  pop     r15
0x180020414  pop     r14
0x180020416  pop     rdi
0x180020417  pop     rsi
0x180020418  pop     rbp
0x180020419  pop     rbx
0x18002041a  retn
0x18002041b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002041f  jmp     short loc_18002040B
0x180020421  mov     [rbx+248h], rax
0x180020428  test    rax, rax
0x18002042b  jnz     loc_180020285
0x180020431  mov     rcx, [rsi]; hdpa
0x180020434  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020438  test    rcx, rcx
0x18002043b  jz      short loc_180020442
0x18002043d  call    DPA_Destroy
0x180020442  mov     r8, [rbx+48h]; lpMem
0x180020446  xor     edx, edx; dwFlags
0x180020448  mov     rcx, [rbx+128h]; hHeap
0x18002044f  call    cs:__imp_HeapFree
0x180020455  call    cs:__imp_GetProcessHeap
0x18002045b  mov     r8, rbx; lpMem
0x18002045e  xor     edx, edx; dwFlags
0x180020460  mov     rcx, rax; hHeap
0x180020463  call    cs:__imp_HeapFree
0x180020469  jmp     short loc_18002040B
0x18002046b  or      dword ptr [rbx+10h], 40h
0x18002046f  jmp     loc_1800202CF
0x180020474  mov     rcx, [rbx]
0x180020477  mov     edx, r15d
0x18002047a  call    cs:__imp_EnableWindowGDIScaledDpiMessage
0x180020480  jmp     loc_1800203C1
0x180020485  btr     eax, 0Ch
0x180020489  mov     [rbx+10h], eax
0x18002048c  jmp     loc_1800203D6
```

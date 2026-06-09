# UninitializeFlatSB

- ea: `0x180035020`
- end: `0x1800352f9`
- name: `UninitializeFlatSB`
- size: `729`
- prototype: `HRESULT __stdcall(HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800529fc`

## callees

- `0x1800115f0`
- `0x180018090`
- `0x18001a590`
- `0x180030440`
- `0x1800306e0`
- `0x180035020`

## import_xrefs

- `GDI32!DeleteObject` at `0x180035236`
- `GDI32!DeleteObject` at `0x180035243`
- `GDI32!DeleteObject` at `0x180035236`
- `GDI32!DeleteObject` at `0x180035243`
- `KERNEL32!LocalFree` at `0x18003524c`
- `KERNEL32!LocalFree` at `0x18003524c`
- `USER32!SetScrollInfo` at `0x180035274`
- `USER32!SetScrollInfo` at `0x1800352a1`
- `USER32!SetScrollInfo` at `0x180035274`
- `USER32!SetScrollInfo` at `0x1800352a1`
- `USER32!EnableScrollBar` at `0x18003528a`
- `USER32!EnableScrollBar` at `0x1800352af`
- `USER32!EnableScrollBar` at `0x18003528a`
- `USER32!EnableScrollBar` at `0x1800352af`
- `USER32!GetScrollInfo` at `0x180035102`
- `USER32!GetScrollInfo` at `0x1800351b9`
- `USER32!GetScrollInfo` at `0x180035102`
- `USER32!GetScrollInfo` at `0x1800351b9`

## pseudocode

```c
HRESULT __stdcall UninitializeFlatSB(HWND a1)
{
  BOOL v1; // esi
  DWORD_PTR v3; // r15
  BOOL ScrollInfo; // r12d
  int v6; // eax
  UINT v7; // r13d
  int v8; // eax
  int v9; // r14d
  DWORD_PTR v10; // [rsp+20h] [rbp-49h] BYREF
  DWORD_PTR pdwRefData; // [rsp+28h] [rbp-41h] BYREF
  SCROLLINFO v12; // [rsp+30h] [rbp-39h] BYREF
  SCROLLINFO v13; // [rsp+50h] [rbp-19h] BYREF

  memset(&v13, 0, sizeof(v13));
  v1 = 0;
  memset(&v12, 0, sizeof(v12));
  pdwRefData = 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &pdwRefData);
  v3 = pdwRefData;
  if ( !pdwRefData )
    return 1;
  if ( pdwRefData == -1 )
  {
    RemoveWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0);
    return 1;
  }
  if ( *(_DWORD *)(pdwRefData + 108) )
    return -2147467259;
  LODWORD(pdwRefData) = *(_DWORD *)(pdwRefData + 8);
  v13.cbSize = 28;
  v12.cbSize = 28;
  v10 = 0;
  v13.fMask = 31;
  v12.fMask = 31;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &v10);
  if ( v10 )
  {
    if ( v10 == -1 || *(HWND *)(v10 + 264) != a1 )
    {
      ScrollInfo = 0;
    }
    else
    {
      if ( (v13.fMask & 1) != 0 )
      {
        v13.nMin = *(_DWORD *)(v10 + 276);
        v13.nMax = *(_DWORD *)(v10 + 280);
      }
      if ( (v13.fMask & 4) != 0 )
        v13.nPos = *(_DWORD *)(v10 + 288);
      if ( (v13.fMask & 2) != 0 )
        v13.nPage = *(_DWORD *)(v10 + 284);
      if ( (v13.fMask & 0x10) != 0 )
      {
        if ( !*(_QWORD *)(v10 + 88) || *(_DWORD *)(v10 + 104) )
          v6 = *(_DWORD *)(v10 + 288);
        else
          v6 = *(_DWORD *)(v10 + 80);
        v13.nTrackPos = v6;
      }
      ScrollInfo = 1;
    }
  }
  else
  {
    ScrollInfo = GetScrollInfo(a1, 0, &v13);
  }
  v7 = *(_DWORD *)(v3 + 272) & 3;
  v10 = 0;
  if ( v12.cbSize >= 0x1C )
  {
    GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &v10);
    if ( v10 )
    {
      if ( v10 != -1 && *(HWND *)(v10 + 264) == a1 )
      {
        if ( (v12.fMask & 1) != 0 )
        {
          v12.nMin = *(_DWORD *)(v10 + 292);
          v12.nMax = *(_DWORD *)(v10 + 296);
        }
        if ( (v12.fMask & 4) != 0 )
          v12.nPos = *(_DWORD *)(v10 + 304);
        if ( (v12.fMask & 2) != 0 )
          v12.nPage = *(_DWORD *)(v10 + 300);
        if ( (v12.fMask & 0x10) != 0 )
        {
          if ( *(_QWORD *)(v10 + 88) && *(_DWORD *)(v10 + 104) )
            v8 = *(_DWORD *)(v10 + 80);
          else
            v8 = *(_DWORD *)(v10 + 304);
          v12.nTrackPos = v8;
        }
        v1 = 1;
      }
    }
    else
    {
      v1 = GetScrollInfo(a1, 1, &v12);
    }
  }
  v9 = *(_DWORD *)(v3 + 272);
  DeleteObject(*(HGDIOBJ *)(v3 + 248));
  DeleteObject(*(HGDIOBJ *)(v3 + 240));
  LocalFree((HLOCAL)v3);
  RemoveWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0);
  if ( v1 )
  {
    SetScrollInfo(a1, 1, &v12, 0);
    EnableScrollBar(a1, 1u, (v9 >> 2) & 3);
  }
  if ( ScrollInfo )
  {
    SetScrollInfo(a1, 0, &v13, 0);
    EnableScrollBar(a1, 0, v7);
  }
  SetWindowBits(a1, -16);
  CCInvalidateFrame(a1);
  return 0;
}

```

## disassembly

```asm
0x180035020  push    rbp
0x180035022  push    rbx
0x180035023  push    rsi
0x180035024  push    rdi
0x180035025  push    r12
0x180035027  push    r13
0x180035029  push    r14
0x18003502b  push    r15
0x18003502d  lea     rbp, [rsp-1Fh]
0x180035032  sub     rsp, 88h
0x180035039  mov     rax, cs:__security_cookie
0x180035040  xor     rax, rsp
0x180035043  mov     [rbp+57h+var_50], rax
0x180035047  xorps   xmm0, xmm0
0x18003504a  lea     rdi, FlatSB_SubclassWndProc
0x180035051  xorps   xmm1, xmm1
0x180035054  lea     r9, [rbp+57h+pdwRefData]; pdwRefData
0x180035058  movups  xmmword ptr [rbp+57h+var_70.cbSize], xmm0
0x18003505c  xor     esi, esi
0x18003505e  mov     rdx, rdi; pfnSubclass
0x180035061  movups  xmmword ptr [rbp+57h+var_90.cbSize], xmm1
0x180035065  xor     eax, eax
0x180035067  mov     [rbp+57h+pdwRefData], rsi
0x18003506b  xor     r8d, r8d; uIdSubclass
0x18003506e  mov     rbx, rcx
0x180035071  movups  xmmword ptr [rbp+57h+var_70.nMax], xmm0
0x180035075  movups  xmmword ptr [rbp+57h+var_90.nMax], xmm1
0x180035079  call    GetWindowSubclass
0x18003507e  mov     r15, [rbp+57h+pdwRefData]
0x180035082  test    r15, r15
0x180035085  jnz     short loc_180035091
0x180035087  mov     eax, 1
0x18003508c  jmp     loc_1800352D9
0x180035091  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180035095  jnz     short loc_1800350A7
0x180035097  xor     r8d, r8d; uIdSubclass
0x18003509a  mov     rdx, rdi; pfnSubclass
0x18003509d  mov     rcx, rbx; hWnd
0x1800350a0  call    RemoveWindowSubclass
0x1800350a5  jmp     short loc_180035087
0x1800350a7  cmp     [r15+6Ch], esi
0x1800350ab  jz      short loc_1800350B7
0x1800350ad  mov     eax, 80004005h
0x1800350b2  jmp     loc_1800352D9
0x1800350b7  mov     eax, [r15+8]
0x1800350bb  lea     r9, [rbp+57h+var_A0]; pdwRefData
0x1800350bf  mov     r14d, 1Ch
0x1800350c5  mov     dword ptr [rbp+57h+pdwRefData], eax
0x1800350c8  xor     r8d, r8d; uIdSubclass
0x1800350cb  mov     [rbp+57h+var_70.cbSize], r14d
0x1800350cf  mov     rdx, rdi; pfnSubclass
0x1800350d2  mov     [rbp+57h+var_90.cbSize], r14d
0x1800350d6  mov     rcx, rbx; hWnd
0x1800350d9  mov     [rbp+57h+var_A0], rsi
0x1800350dd  lea     eax, [r14+3]
0x1800350e1  mov     [rbp+57h+var_70.fMask], eax
0x1800350e4  mov     [rbp+57h+var_90.fMask], eax
0x1800350e7  call    GetWindowSubclass
0x1800350ec  mov     rcx, [rbp+57h+var_A0]
0x1800350f0  lea     edi, [r14-1Bh]
0x1800350f4  test    rcx, rcx
0x1800350f7  jnz     short loc_18003510D
0x1800350f9  lea     r8, [rbp+57h+var_70]; lpsi
0x1800350fd  xor     edx, edx; nBar
0x1800350ff  mov     rcx, rbx; hwnd
0x180035102  call    cs:__imp_GetScrollInfo
0x180035108  mov     r12d, eax
0x18003510b  jmp     short loc_180035178
0x18003510d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035111  jnz     short loc_180035118
0x180035113  mov     r12d, esi
0x180035116  jmp     short loc_180035178
0x180035118  cmp     [rcx+108h], rbx
0x18003511f  jnz     short loc_180035113
0x180035121  mov     edx, [rbp+57h+var_70.fMask]
0x180035124  test    dil, dl
0x180035127  jz      short loc_18003513B
0x180035129  mov     eax, [rcx+114h]
0x18003512f  mov     [rbp+57h+var_70.nMin], eax
0x180035132  mov     eax, [rcx+118h]
0x180035138  mov     [rbp+57h+var_70.nMax], eax
0x18003513b  test    dl, 4
0x18003513e  jz      short loc_180035149
0x180035140  mov     eax, [rcx+120h]
0x180035146  mov     [rbp+57h+var_70.nPos], eax
0x180035149  test    dl, 2
0x18003514c  jz      short loc_180035157
0x18003514e  mov     eax, [rcx+11Ch]
0x180035154  mov     [rbp+57h+var_70.nPage], eax
0x180035157  test    dl, 10h
0x18003515a  jz      short loc_180035175
0x18003515c  cmp     [rcx+58h], rsi
0x180035160  jz      short loc_18003516C
0x180035162  cmp     [rcx+68h], esi
0x180035165  jnz     short loc_18003516C
0x180035167  mov     eax, [rcx+50h]
0x18003516a  jmp     short loc_180035172
0x18003516c  mov     eax, [rcx+120h]
0x180035172  mov     [rbp+57h+var_70.nTrackPos], eax
0x180035175  mov     r12d, edi
0x180035178  mov     r13d, [r15+110h]
0x18003517f  and     r13d, 3
0x180035183  mov     [rbp+57h+var_A0], rsi
0x180035187  cmp     [rbp+57h+var_90.cbSize], r14d
0x18003518b  jb      loc_180035228
0x180035191  lea     r9, [rbp+57h+var_A0]; pdwRefData
0x180035195  xor     r8d, r8d; uIdSubclass
0x180035198  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x18003519f  mov     rcx, rbx; hWnd
0x1800351a2  call    GetWindowSubclass
0x1800351a7  mov     rcx, [rbp+57h+var_A0]
0x1800351ab  test    rcx, rcx
0x1800351ae  jnz     short loc_1800351C3
0x1800351b0  lea     r8, [rbp+57h+var_90]; lpsi
0x1800351b4  mov     edx, edi; nBar
0x1800351b6  mov     rcx, rbx; hwnd
0x1800351b9  call    cs:__imp_GetScrollInfo
0x1800351bf  mov     esi, eax
0x1800351c1  jmp     short loc_180035228
0x1800351c3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800351c7  jz      short loc_180035228
0x1800351c9  cmp     [rcx+108h], rbx
0x1800351d0  jnz     short loc_180035228
0x1800351d2  mov     edx, [rbp+57h+var_90.fMask]
0x1800351d5  test    dil, dl
0x1800351d8  jz      short loc_1800351EC
0x1800351da  mov     eax, [rcx+124h]
0x1800351e0  mov     [rbp+57h+var_90.nMin], eax
0x1800351e3  mov     eax, [rcx+128h]
0x1800351e9  mov     [rbp+57h+var_90.nMax], eax
0x1800351ec  test    dl, 4
0x1800351ef  jz      short loc_1800351FA
0x1800351f1  mov     eax, [rcx+130h]
0x1800351f7  mov     [rbp+57h+var_90.nPos], eax
0x1800351fa  test    dl, 2
0x1800351fd  jz      short loc_180035208
0x1800351ff  mov     eax, [rcx+12Ch]
0x180035205  mov     [rbp+57h+var_90.nPage], eax
0x180035208  test    dl, 10h
0x18003520b  jz      short loc_180035226
0x18003520d  cmp     [rcx+58h], rsi
0x180035211  jz      short loc_18003521D
0x180035213  cmp     [rcx+68h], esi
0x180035216  jz      short loc_18003521D
0x180035218  mov     eax, [rcx+50h]
0x18003521b  jmp     short loc_180035223
0x18003521d  mov     eax, [rcx+130h]
0x180035223  mov     [rbp+57h+var_90.nTrackPos], eax
0x180035226  mov     esi, edi
0x180035228  mov     rcx, [r15+0F8h]; ho
0x18003522f  mov     r14d, [r15+110h]
0x180035236  call    cs:__imp_DeleteObject
0x18003523c  mov     rcx, [r15+0F0h]; ho
0x180035243  call    cs:__imp_DeleteObject
0x180035249  mov     rcx, r15; hMem
0x18003524c  call    cs:__imp_LocalFree
0x180035252  xor     r8d, r8d; uIdSubclass
0x180035255  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x18003525c  mov     rcx, rbx; hWnd
0x18003525f  call    RemoveWindowSubclass
0x180035264  test    esi, esi
0x180035266  jz      short loc_180035290
0x180035268  xor     r9d, r9d; redraw
0x18003526b  lea     r8, [rbp+57h+var_90]; lpsi
0x18003526f  mov     edx, edi; nBar
0x180035271  mov     rcx, rbx; hwnd
0x180035274  call    cs:__imp_SetScrollInfo
0x18003527a  sar     r14d, 2
0x18003527e  mov     edx, edi; wSBflags
0x180035280  and     r14d, 3
0x180035284  mov     rcx, rbx; hWnd
0x180035287  mov     r8d, r14d; wArrows
0x18003528a  call    cs:__imp_EnableScrollBar
0x180035290  test    r12d, r12d
0x180035293  jz      short loc_1800352B5
0x180035295  xor     r9d, r9d; redraw
0x180035298  lea     r8, [rbp+57h+var_70]; lpsi
0x18003529c  xor     edx, edx; nBar
0x18003529e  mov     rcx, rbx; hwnd
0x1800352a1  call    cs:__imp_SetScrollInfo
0x1800352a7  mov     r8d, r13d; wArrows
0x1800352aa  xor     edx, edx; wSBflags
0x1800352ac  mov     rcx, rbx; hWnd
0x1800352af  call    cs:__imp_EnableScrollBar
0x1800352b5  mov     r9d, dword ptr [rbp+57h+pdwRefData]
0x1800352b9  mov     r8d, 300000h
0x1800352bf  and     r9d, r8d
0x1800352c2  mov     edx, 0FFFFFFF0h; nIndex
0x1800352c7  mov     rcx, rbx; hWnd
0x1800352ca  call    SetWindowBits
0x1800352cf  mov     rcx, rbx
0x1800352d2  call    CCInvalidateFrame
0x1800352d7  xor     eax, eax
0x1800352d9  mov     rcx, [rbp+57h+var_50]
0x1800352dd  xor     rcx, rsp; StackCookie
0x1800352e0  call    __security_check_cookie
0x1800352e5  add     rsp, 88h
0x1800352ec  pop     r15
0x1800352ee  pop     r14
0x1800352f0  pop     r13
0x1800352f2  pop     r12
0x1800352f4  pop     rdi
0x1800352f5  pop     rsi
0x1800352f6  pop     rbx
0x1800352f7  pop     rbp
0x1800352f8  retn
```

# UpdatePreviewRect(void)

- ea: `0x1800112c4`
- end: `0x1800114cc`
- name: `?UpdatePreviewRect@@YAXXZ`
- size: `520`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800110b0`

## callees

- `0x1800015b0`
- `0x1800112c4`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180011429`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180011429`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001130a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001132d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180011355`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180011371`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001130a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001132d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180011355`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180011371`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18001140d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x18001140d`

## pseudocode

```c
void UpdatePreviewRect(void)
{
  __int16 *v0; // r14
  __int64 v1; // rbp
  int v2; // r15d
  int SystemMetrics; // eax
  int v4; // ebx
  int v5; // esi
  int v6; // eax
  int v7; // ebx
  int v8; // edi
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // ecx
  int v13; // r9d
  int v14; // edx
  int v15; // edx
  HMONITOR v16; // rax
  unsigned int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  tagMONITORINFO mi; // [rsp+20h] [rbp-68h] BYREF

  v0 = (__int16 *)FontInfo;
  memset(&mi, 0, sizeof(mi));
  v1 = 5LL * g_currentFontIndex;
  v2 = (GetSystemMetrics(28) - NonClientSize.x) / v0[4 * v1 + 4];
  SystemMetrics = GetSystemMetrics(29);
  v4 = v0[4 * v1 + 4];
  v5 = (SystemMetrics - NonClientSize.y) / v0[4 * v1 + 5];
  v6 = GetSystemMetrics(16) / v4;
  v7 = v0[4 * v1 + 5];
  v8 = v6;
  v9 = GetSystemMetrics(17) / v7;
  v10 = *((__int16 *)gpStateInfo + 2);
  v11 = *((_DWORD *)gpStateInfo + 2);
  if ( v10 >= v8 )
    v10 = v8;
  if ( v2 < v10 )
    v2 = v10;
  v12 = *((__int16 *)gpStateInfo + 3);
  WindowRect.left = *((_DWORD *)gpStateInfo + 2);
  v13 = *((_DWORD *)gpStateInfo + 3);
  if ( v12 >= v9 )
    v12 = v9;
  WindowRect.top = *((_DWORD *)gpStateInfo + 3);
  if ( v5 < v12 )
    v5 = v12;
  v14 = NonClientSize.x + v2 * v0[4 * v1 + 4];
  if ( v14 < 2 * NonClientSize.x )
    v14 = 2 * NonClientSize.x;
  WindowRect.right = v11 + v14;
  v15 = NonClientSize.y + v5 * v0[4 * v1 + 5];
  if ( v15 < 2 * NonClientSize.y )
    v15 = 2 * NonClientSize.y;
  WindowRect.bottom = v13 + v15;
  v16 = MonitorFromRect(&WindowRect, 2u);
  mi.cbSize = 40;
  GetMonitorInfoW(v16, &mi);
  gcxScreen = mi.rcWork.right - mi.rcWork.left;
  gcyScreen = mi.rcWork.bottom - mi.rcWork.top;
  WindowRect.right -= WindowRect.left;
  WindowRect.left -= mi.rcWork.left;
  WindowRect.bottom -= WindowRect.top;
  WindowRect.top -= mi.rcWork.top;
  if ( v2 >= *(__int16 *)gpStateInfo )
    v17 = PreviewFlags & 0xFFFFFFFE;
  else
    v17 = PreviewFlags | 1;
  v18 = v17 & 0xFFFFFFFD;
  v19 = v17 | 2;
  if ( v5 >= *((__int16 *)gpStateInfo + 1) )
    v19 = v18;
  PreviewFlags = v19;
}

```

## disassembly

```asm
0x1800112c4  push    rbx
0x1800112c6  push    rbp
0x1800112c7  push    rsi
0x1800112c8  push    rdi
0x1800112c9  push    r14
0x1800112cb  push    r15
0x1800112cd  sub     rsp, 58h
0x1800112d1  mov     rax, cs:__security_cookie
0x1800112d8  xor     rax, rsp
0x1800112db  mov     [rsp+88h+var_40], rax
0x1800112e0  mov     r14, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x1800112e7  xor     eax, eax
0x1800112e9  xorps   xmm0, xmm0
0x1800112ec  mov     qword ptr [rsp+88h+mi.rcWork.bottom], rax
0x1800112f1  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x1800112f7  mov     ecx, 1Ch; nIndex
0x1800112fc  movups  xmmword ptr [rsp+88h+mi.cbSize], xmm0
0x180011301  movups  xmmword ptr [rsp+88h+mi.rcMonitor.bottom], xmm0
0x180011306  lea     rbp, [rax+rax*4]
0x18001130a  call    cs:__imp_GetSystemMetrics
0x180011311  nop     dword ptr [rax+rax+00h]
0x180011316  sub     eax, dword ptr cs:?NonClientSize@@3UtagPOINT@@A; tagPOINT NonClientSize
0x18001131c  movsx   ecx, word ptr [r14+rbp*8+8]
0x180011322  cdq
0x180011323  idiv    ecx
0x180011325  mov     ecx, 1Dh; nIndex
0x18001132a  mov     r15d, eax
0x18001132d  call    cs:__imp_GetSystemMetrics
0x180011334  nop     dword ptr [rax+rax+00h]
0x180011339  sub     eax, dword ptr cs:?NonClientSize@@3UtagPOINT@@A+4; tagPOINT NonClientSize
0x18001133f  movsx   ecx, word ptr [r14+rbp*8+0Ah]
0x180011345  cdq
0x180011346  movsx   ebx, word ptr [r14+rbp*8+8]
0x18001134c  idiv    ecx
0x18001134e  mov     ecx, 10h; nIndex
0x180011353  mov     esi, eax
0x180011355  call    cs:__imp_GetSystemMetrics
0x18001135c  nop     dword ptr [rax+rax+00h]
0x180011361  cdq
0x180011362  mov     ecx, 11h; nIndex
0x180011367  idiv    ebx
0x180011369  movsx   ebx, word ptr [r14+rbp*8+0Ah]
0x18001136f  mov     edi, eax
0x180011371  call    cs:__imp_GetSystemMetrics
0x180011378  nop     dword ptr [rax+rax+00h]
0x18001137d  cdq
0x18001137e  idiv    ebx
0x180011380  mov     rdx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180011387  movsx   ecx, word ptr [rdx+4]
0x18001138b  mov     r8d, [rdx+8]
0x18001138f  cmp     ecx, edi
0x180011391  cmovge  ecx, edi
0x180011394  cmp     r15d, ecx
0x180011397  cmovl   r15d, ecx
0x18001139b  movsx   ecx, word ptr [rdx+6]
0x18001139f  cmp     ecx, eax
0x1800113a1  mov     cs:?WindowRect@@3UtagRECT@@A.left, r8d; tagRECT WindowRect ...
0x1800113a8  mov     r9d, [rdx+0Ch]
0x1800113ac  cmovge  ecx, eax
0x1800113af  mov     cs:?WindowRect@@3UtagRECT@@A.top, r9d; tagRECT WindowRect ...
0x1800113b6  mov     rax, cs:?NonClientSize@@3UtagPOINT@@A; tagPOINT NonClientSize
0x1800113bd  cmp     esi, ecx
0x1800113bf  movsx   edx, word ptr [r14+rbp*8+8]
0x1800113c5  cmovl   esi, ecx
0x1800113c8  imul    edx, r15d
0x1800113cc  add     edx, eax
0x1800113ce  add     eax, eax
0x1800113d0  cmp     edx, eax
0x1800113d2  jge     short loc_1800113D6
0x1800113d4  mov     edx, eax
0x1800113d6  mov     ecx, dword ptr cs:?NonClientSize@@3UtagPOINT@@A+4; tagPOINT NonClientSize
0x1800113dc  add     edx, r8d
0x1800113df  mov     cs:?WindowRect@@3UtagRECT@@A.right, edx; tagRECT WindowRect ...
0x1800113e5  movsx   edx, word ptr [r14+rbp*8+0Ah]
0x1800113eb  imul    edx, esi
0x1800113ee  add     edx, ecx
0x1800113f0  add     ecx, ecx
0x1800113f2  cmp     edx, ecx
0x1800113f4  jge     short loc_1800113F8
0x1800113f6  mov     edx, ecx
0x1800113f8  add     edx, r9d
0x1800113fb  lea     rcx, ?WindowRect@@3UtagRECT@@A; lprc
0x180011402  mov     cs:?WindowRect@@3UtagRECT@@A.bottom, edx; tagRECT WindowRect ...
0x180011408  mov     edx, 2; dwFlags
0x18001140d  call    cs:__imp_MonitorFromRect
0x180011414  nop     dword ptr [rax+rax+00h]
0x180011419  lea     rdx, [rsp+88h+mi]; lpmi
0x18001141e  mov     [rsp+88h+mi.cbSize], 28h ; '('
0x180011426  mov     rcx, rax; hMonitor
0x180011429  call    cs:__imp_GetMonitorInfoW
0x180011430  nop     dword ptr [rax+rax+00h]
0x180011435  mov     eax, [rsp+88h+mi.rcWork.right]
0x180011439  sub     eax, [rsp+88h+mi.rcWork.left]
0x18001143d  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180011444  mov     edx, cs:?PreviewFlags@@3KA; ulong PreviewFlags
0x18001144a  mov     cs:?gcxScreen@@3JA, eax; long gcxScreen
0x180011450  mov     eax, [rsp+88h+mi.rcWork.bottom]
0x180011454  sub     eax, [rsp+88h+mi.rcWork.top]
0x180011458  mov     cs:?gcyScreen@@3JA, eax; long gcyScreen
0x18001145e  mov     eax, cs:?WindowRect@@3UtagRECT@@A.left; tagRECT WindowRect ...
0x180011464  sub     cs:?WindowRect@@3UtagRECT@@A.right, eax; tagRECT WindowRect ...
0x18001146a  sub     eax, [rsp+88h+mi.rcWork.left]
0x18001146e  mov     cs:?WindowRect@@3UtagRECT@@A.left, eax; tagRECT WindowRect ...
0x180011474  mov     eax, cs:?WindowRect@@3UtagRECT@@A.top; tagRECT WindowRect ...
0x18001147a  sub     cs:?WindowRect@@3UtagRECT@@A.bottom, eax; tagRECT WindowRect ...
0x180011480  sub     eax, [rsp+88h+mi.rcWork.top]
0x180011484  mov     cs:?WindowRect@@3UtagRECT@@A.top, eax; tagRECT WindowRect ...
0x18001148a  movsx   eax, word ptr [rcx]
0x18001148d  cmp     r15d, eax
0x180011490  jge     short loc_180011497
0x180011492  or      edx, 1
0x180011495  jmp     short loc_18001149A
0x180011497  and     edx, 0FFFFFFFEh
0x18001149a  movsx   ecx, word ptr [rcx+2]
0x18001149e  mov     eax, edx
0x1800114a0  and     eax, 0FFFFFFFDh
0x1800114a3  or      edx, 2
0x1800114a6  cmp     esi, ecx
0x1800114a8  cmovge  edx, eax
0x1800114ab  mov     cs:?PreviewFlags@@3KA, edx; ulong PreviewFlags
0x1800114b1  mov     rcx, [rsp+88h+var_40]
0x1800114b6  xor     rcx, rsp; StackCookie
0x1800114b9  call    __security_check_cookie
0x1800114be  add     rsp, 58h
0x1800114c2  pop     r15
0x1800114c4  pop     r14
0x1800114c6  pop     rdi
0x1800114c7  pop     rsi
0x1800114c8  pop     rbp
0x1800114c9  pop     rbx
0x1800114ca  retn
```

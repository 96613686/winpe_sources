# SetOffDesktop

- ea: `0x180048778`
- end: `0x180048980`
- name: `SetOffDesktop`
- size: `520`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a268`
- `0x18000ac58`
- `0x18000de8c`
- `0x18000e194`
- `0x18000e360`
- `0x18000f9b0`
- `0x180010234`
- `0x18001c0b0`
- `0x18001f108`
- `0x180025e48`
- `0x180029dc8`
- `0x18002a320`
- `0x180047c8c`

## callees

- `0x180048778`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18004885a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18004885a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004895f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004895f`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800487c0`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800487c0`
- `USER32!RemovePropW` at `0x18004896f`
- `USER32!RemovePropW` at `0x18004896f`
- `USER32!GetPropW` at `0x1800487dc`
- `USER32!GetPropW` at `0x1800487dc`
- `USER32!SetPropW` at `0x1800488f5`
- `USER32!SetPropW` at `0x1800488f5`
- `USER32!SetWindowPos` at `0x18004882a`
- `USER32!SetWindowPos` at `0x1800488cb`
- `USER32!SetWindowPos` at `0x180048956`
- `USER32!SetWindowPos` at `0x18004882a`
- `USER32!SetWindowPos` at `0x1800488cb`
- `USER32!SetWindowPos` at `0x180048956`
- `USER32!ShowWindow` at `0x180048840`
- `USER32!ShowWindow` at `0x180048880`
- `USER32!ShowWindow` at `0x1800488db`
- `USER32!ShowWindow` at `0x180048840`
- `USER32!ShowWindow` at `0x180048880`
- `USER32!ShowWindow` at `0x1800488db`
- `USER32!GetWindowRect` at `0x18004888c`
- `USER32!GetWindowRect` at `0x18004888c`
- `USER32!IsWindowVisible` at `0x18004886f`
- `USER32!IsWindowVisible` at `0x18004886f`
- `rtutils!TracePrintfExA` at `0x1800487a7`
- `rtutils!TracePrintfExA` at `0x1800487a7`

## pseudocode

```c
__int64 __fastcall SetOffDesktop(HWND hWnd, int a2, _OWORD *a3)
{
  const WCHAR *v6; // rdx
  ATOM v7; // ax
  int *PropW; // rax
  int *v9; // rbx
  struct tagRECT *v10; // rbx
  BOOL v11; // esi
  const WCHAR *v12; // rdx

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "SetOffDesktop(h=$%08x,a=%d)", (_DWORD)hWnd, a2);
  v6 = qword_180064868;
  if ( !qword_180064868 )
  {
    v7 = GlobalAddAtomW(L"RASSETOFFDESKTOP");
    v6 = (const WCHAR *)v7;
    qword_180064868 = (LPCWSTR)v7;
    if ( !v7 )
      return 0;
  }
  PropW = (int *)GetPropW(hWnd, v6);
  v9 = PropW;
  if ( a2 != 1 )
  {
    if ( ((a2 - 2) & 0xFFFFFFFD) == 0 )
    {
      if ( PropW )
      {
        if ( a2 == 2 )
          SetWindowPos(hWnd, 0, *PropW, PropW[1], PropW[2] - *PropW, PropW[3] - PropW[1], 4u);
        GlobalFree(v9);
        RemovePropW(hWnd, qword_180064868);
      }
      return 0;
    }
    if ( a2 == 5 )
    {
      if ( !PropW )
        return 0;
      *a3 = *(_OWORD *)PropW;
    }
    return 1;
  }
  if ( PropW )
  {
    SetWindowPos(hWnd, 0, (*PropW + PropW[2]) / 2, (PropW[1] + PropW[3]) / 2, 0, 0, 4u);
    if ( v9[4] )
    {
      ShowWindow(hWnd, 5);
      v9[4] = 0;
    }
    return 1;
  }
  v10 = (struct tagRECT *)GlobalAlloc(0x40u, 0x14u);
  if ( v10 )
  {
    v11 = IsWindowVisible(hWnd);
    if ( !v11 )
      ShowWindow(hWnd, 0);
    GetWindowRect(hWnd, v10);
    SetWindowPos(hWnd, 0, (v10->left + v10->right) / 2, (v10->top + v10->bottom) / 2, 0, 0, 4u);
    if ( !v11 )
      ShowWindow(hWnd, 5);
    v12 = qword_180064868;
    v10[1].left = 0;
    SetPropW(hWnd, v12, v10);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180048778  push    rbx
0x18004877a  push    rbp
0x18004877b  push    rsi
0x18004877c  push    rdi
0x18004877d  sub     rsp, 48h
0x180048781  mov     rdi, rcx
0x180048784  mov     rbp, r8
0x180048787  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18004878d  mov     esi, edx
0x18004878f  cmp     ecx, 0FFFFFFFFh
0x180048792  jz      short loc_1800487AD
0x180048794  mov     [rsp+68h+var_48], edx
0x180048798  lea     r8, aSetoffdesktopH; "SetOffDesktop(h=$%08x,a=%d)"
0x18004879f  mov     edx, 0Ch; dwFlags
0x1800487a4  mov     r9, rdi
0x1800487a7  call    cs:__imp_TracePrintfExA
0x1800487ad  mov     rdx, cs:qword_180064868
0x1800487b4  test    rdx, rdx
0x1800487b7  jnz     short loc_1800487D9
0x1800487b9  lea     rcx, aRassetoffdeskt; "RASSETOFFDESKTOP"
0x1800487c0  call    cs:__imp_GlobalAddAtomW
0x1800487c6  movzx   edx, ax; lpString
0x1800487c9  mov     cs:qword_180064868, rdx
0x1800487d0  test    rdx, rdx
0x1800487d3  jz      loc_180048975
0x1800487d9  mov     rcx, rdi; hWnd
0x1800487dc  call    cs:__imp_GetPropW
0x1800487e2  mov     rbx, rax
0x1800487e5  cmp     esi, 1
0x1800487e8  jnz     loc_1800488FD
0x1800487ee  test    rax, rax
0x1800487f1  jz      short loc_180048852
0x1800487f3  mov     eax, [rax+0Ch]
0x1800487f6  lea     ecx, [rsi+1]
0x1800487f9  add     eax, [rbx+4]
0x1800487fc  cdq
0x1800487fd  mov     [rsp+68h+uFlags], 4; uFlags
0x180048805  idiv    ecx
0x180048807  mov     [rsp+68h+cy], 0; cy
0x18004880f  mov     r9d, eax; Y
0x180048812  mov     [rsp+68h+var_48], 0; cx
0x18004881a  mov     eax, [rbx+8]
0x18004881d  add     eax, [rbx]
0x18004881f  cdq
0x180048820  idiv    ecx
0x180048822  xor     edx, edx; hWndInsertAfter
0x180048824  mov     rcx, rdi; hWnd
0x180048827  mov     r8d, eax; X
0x18004882a  call    cs:__imp_SetWindowPos
0x180048830  cmp     dword ptr [rbx+10h], 0
0x180048834  jz      loc_18004891A
0x18004883a  lea     edx, [rsi+4]; nCmdShow
0x18004883d  mov     rcx, rdi; hWnd
0x180048840  call    cs:__imp_ShowWindow
0x180048846  mov     dword ptr [rbx+10h], 0
0x18004884d  jmp     loc_18004891A
0x180048852  mov     edx, 14h; dwBytes
0x180048857  lea     ecx, [rdx+2Ch]; uFlags
0x18004885a  call    cs:__imp_GlobalAlloc
0x180048860  mov     rbx, rax
0x180048863  test    rax, rax
0x180048866  jz      loc_180048975
0x18004886c  mov     rcx, rdi; hWnd
0x18004886f  call    cs:__imp_IsWindowVisible
0x180048875  mov     esi, eax
0x180048877  test    eax, eax
0x180048879  jnz     short loc_180048886
0x18004887b  xor     edx, edx; nCmdShow
0x18004887d  mov     rcx, rdi; hWnd
0x180048880  call    cs:__imp_ShowWindow
0x180048886  mov     rdx, rbx; lpRect
0x180048889  mov     rcx, rdi; hWnd
0x18004888c  call    cs:__imp_GetWindowRect
0x180048892  mov     eax, [rbx+0Ch]
0x180048895  mov     ecx, 2
0x18004889a  add     eax, [rbx+4]
0x18004889d  cdq
0x18004889e  mov     [rsp+68h+uFlags], 4; uFlags
0x1800488a6  idiv    ecx
0x1800488a8  mov     [rsp+68h+cy], 0; cy
0x1800488b0  mov     r9d, eax; Y
0x1800488b3  mov     [rsp+68h+var_48], 0; cx
0x1800488bb  mov     eax, [rbx+8]
0x1800488be  add     eax, [rbx]
0x1800488c0  cdq
0x1800488c1  idiv    ecx
0x1800488c3  xor     edx, edx; hWndInsertAfter
0x1800488c5  mov     rcx, rdi; hWnd
0x1800488c8  mov     r8d, eax; X
0x1800488cb  call    cs:__imp_SetWindowPos
0x1800488d1  test    esi, esi
0x1800488d3  jnz     short loc_1800488E1
0x1800488d5  lea     edx, [rsi+5]; nCmdShow
0x1800488d8  mov     rcx, rdi; hWnd
0x1800488db  call    cs:__imp_ShowWindow
0x1800488e1  mov     rdx, cs:qword_180064868; lpString
0x1800488e8  mov     r8, rbx; hData
0x1800488eb  mov     rcx, rdi; hWnd
0x1800488ee  mov     dword ptr [rbx+10h], 0
0x1800488f5  call    cs:__imp_SetPropW
0x1800488fb  jmp     short loc_18004891A
0x1800488fd  lea     ecx, [rsi-2]
0x180048900  test    ecx, 0FFFFFFFDh
0x180048906  jz      short loc_180048921
0x180048908  cmp     esi, 5
0x18004890b  jnz     short loc_18004891A
0x18004890d  test    rbx, rbx
0x180048910  jz      short loc_180048975
0x180048912  movups  xmm0, xmmword ptr [rax]
0x180048915  movdqu  xmmword ptr [rbp+0], xmm0
0x18004891a  mov     eax, 1
0x18004891f  jmp     short loc_180048977
0x180048921  test    rbx, rbx
0x180048924  jz      short loc_180048975
0x180048926  mov     ecx, 2
0x18004892b  cmp     esi, ecx
0x18004892d  jnz     short loc_18004895C
0x18004892f  mov     ecx, [rax+0Ch]
0x180048932  xor     edx, edx; hWndInsertAfter
0x180048934  mov     r9d, [rax+4]; Y
0x180048938  sub     ecx, r9d
0x18004893b  mov     eax, [rax+8]
0x18004893e  sub     eax, [rbx]
0x180048940  mov     r8d, [rbx]; X
0x180048943  mov     [rsp+68h+uFlags], 4; uFlags
0x18004894b  mov     [rsp+68h+cy], ecx; cy
0x18004894f  mov     rcx, rdi; hWnd
0x180048952  mov     [rsp+68h+var_48], eax; cx
0x180048956  call    cs:__imp_SetWindowPos
0x18004895c  mov     rcx, rbx; hMem
0x18004895f  call    cs:__imp_GlobalFree
0x180048965  mov     rdx, cs:qword_180064868; lpString
0x18004896c  mov     rcx, rdi; hWnd
0x18004896f  call    cs:__imp_RemovePropW
0x180048975  xor     eax, eax
0x180048977  add     rsp, 48h
0x18004897b  pop     rdi
0x18004897c  pop     rsi
0x18004897d  pop     rbp
0x18004897e  pop     rbx
0x18004897f  retn
```

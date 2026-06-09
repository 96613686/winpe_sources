# ICCompressorChoose

- ea: `0x180004590`
- end: `0x1800047e0`
- name: `ICCompressorChoose`
- size: `592`
- prototype: `BOOL __stdcall(HWND hwnd, UINT uiFlags, LPVOID pvIn, LPVOID lpData, PCOMPVARS pc, LPSTR lpszTitle)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002640`
- `0x180003a60`
- `0x180004590`
- `0x180005be0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180004623`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000479b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180004623`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000479b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000474a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000474a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180004741`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180004753`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180004741`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180004753`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000475c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000475c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000461a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180004792`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000461a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180004792`
- `USER32!DialogBoxParamW` at `0x1800046e8`
- `USER32!DialogBoxParamW` at `0x1800046e8`

## pseudocode

```c
BOOL __stdcall ICCompressorChoose(HWND hwnd, UINT uiFlags, LPVOID pvIn, LPVOID lpData, PCOMPVARS pc, LPSTR lpszTitle)
{
  HGLOBAL v10; // rax
  _DWORD *v11; // rax
  LPARAM dwInitParam; // rdi
  LONG cbState; // eax
  __int64 v14; // rcx
  INT_PTR v15; // rax
  INT_PTR v16; // rbp
  LONG v17; // eax
  HGLOBAL v18; // rax
  HGLOBAL v19; // rax
  HIC hic; // rcx
  unsigned int v21; // eax
  HGLOBAL v22; // rax
  struct tagBITMAPINFO *v23; // rax

  if ( pc && pc->cbSize == 96 )
  {
    if ( (pc->dwFlags & 1) == 0 )
    {
      pc->hic = 0;
      *(_QWORD *)&pc->fccType = 0;
      pc->lQ = -1;
      pc->lKey = -1;
      pc->lDataRate = 300;
      pc->lpbiOut = 0;
      pc->lpBitsOut = 0;
      pc->lpBitsPrev = 0;
      pc->dwFlags = 0;
      pc->lpState = 0;
      pc->cbState = 0;
    }
    if ( !pc->fccType )
      pc->fccType = 1667524982;
    v10 = GlobalAlloc(0x42u, 0x378u);
    v11 = GlobalLock(v10);
    dwInitParam = (LPARAM)v11;
    if ( v11 )
    {
      *v11 = pc->fccType;
      v11[1] = pc->fccHandler;
      v11[2] = uiFlags;
      *((_QWORD *)v11 + 2) = pvIn;
      v11[12] = pc->lQ;
      v11[13] = pc->lKey;
      v11[14] = pc->lDataRate;
      *((_QWORD *)v11 + 80) = lpData;
      *((_QWORD *)v11 + 79) = lpszTitle;
      *((_QWORD *)v11 + 107) = 0;
      *((_QWORD *)v11 + 109) = pc->lpState;
      cbState = pc->cbState;
      pc->lpState = 0;
      v14 = *(_QWORD *)(dwInitParam + 640);
      *(_DWORD *)(dwInitParam + 880) = cbState;
      if ( v14
        && ((*(unsigned int (__fastcall **)(__int64, LPARAM, __int64))(*(_QWORD *)v14 + 32LL))(
              v14,
              dwInitParam + 648,
              204)
         || *(_DWORD *)(dwInitParam + 648) != 1935960438) )
      {
        *(_QWORD *)(dwInitParam + 640) = 0;
      }
      v15 = DialogBoxParamW(ghInst, L"ICCDLG", hwnd, (DLGPROC)ICCompressorChooseDlgProc, dwInitParam);
      v16 = 0;
      if ( v15 != -1 )
        v16 = v15;
      if ( v16 )
      {
        ICCompressorFree(pc);
        pc->lQ = *(_DWORD *)(dwInitParam + 48);
        pc->lKey = *(_DWORD *)(dwInitParam + 52);
        pc->lDataRate = *(_DWORD *)(dwInitParam + 56);
        pc->hic = *(HIC *)(dwInitParam + 40);
        pc->fccHandler = *(_DWORD *)(dwInitParam + 4);
        pc->lpState = *(LPVOID *)(dwInitParam + 872);
        v17 = *(_DWORD *)(dwInitParam + 880);
        pc->dwFlags |= 1u;
        pc->cbState = v17;
      }
      v18 = GlobalHandle((LPCVOID)dwInitParam);
      GlobalUnlock(v18);
      v19 = GlobalHandle((LPCVOID)dwInitParam);
      GlobalFree(v19);
      if ( v16 )
      {
        hic = pc->hic;
        if ( !hic || !pvIn )
          return 1;
        v21 = ICSendMessage(hic, 0x4004u, (DWORD_PTR)pvIn, 0);
        if ( v21 )
        {
          v22 = GlobalAlloc(2u, v21);
          v23 = (struct tagBITMAPINFO *)GlobalLock(v22);
          pc->lpbiOut = v23;
          if ( v23 )
          {
            ICSendMessage(pc->hic, 0x4004u, (DWORD_PTR)pvIn, (DWORD_PTR)v23);
            return 1;
          }
        }
        ICClose(pc->hic);
        pc->hic = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004590  push    rbx
0x180004592  push    rbp
0x180004593  push    rsi
0x180004594  push    rdi
0x180004595  push    r12
0x180004597  push    r14
0x180004599  push    r15
0x18000459b  sub     rsp, 30h
0x18000459f  mov     rbx, [rsp+68h+pc]
0x1800045a7  xor     r12d, r12d
0x1800045aa  mov     rbp, r9
0x1800045ad  mov     rsi, r8
0x1800045b0  mov     r14d, edx
0x1800045b3  mov     r15, rcx
0x1800045b6  test    rbx, rbx
0x1800045b9  jz      loc_1800047CF
0x1800045bf  cmp     dword ptr [rbx], 60h ; '`'
0x1800045c2  jnz     loc_1800047CF
0x1800045c8  test    byte ptr [rbx+4], 1
0x1800045cc  jnz     short loc_180004603
0x1800045ce  mov     [rbx+8], r12
0x1800045d2  mov     [rbx+10h], r12
0x1800045d6  mov     dword ptr [rbx+44h], 0FFFFFFFFh
0x1800045dd  mov     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x1800045e4  mov     dword ptr [rbx+40h], 12Ch
0x1800045eb  mov     [rbx+20h], r12
0x1800045ef  mov     [rbx+28h], r12
0x1800045f3  mov     [rbx+30h], r12
0x1800045f7  mov     [rbx+4], r12d
0x1800045fb  mov     [rbx+50h], r12
0x1800045ff  mov     [rbx+58h], r12d
0x180004603  cmp     [rbx+10h], r12d
0x180004607  jnz     short loc_180004610
0x180004609  mov     dword ptr [rbx+10h], 63646976h
0x180004610  mov     edx, 378h; dwBytes
0x180004615  mov     ecx, 42h ; 'B'; uFlags
0x18000461a  call    cs:__imp_GlobalAlloc
0x180004620  mov     rcx, rax; hMem
0x180004623  call    cs:__imp_GlobalLock
0x180004629  mov     rdi, rax
0x18000462c  test    rax, rax
0x18000462f  jz      loc_1800047CF
0x180004635  mov     eax, [rbx+10h]
0x180004638  mov     [rdi], eax
0x18000463a  mov     eax, [rbx+14h]
0x18000463d  mov     [rdi+4], eax
0x180004640  mov     [rdi+8], r14d
0x180004644  mov     [rdi+10h], rsi
0x180004648  mov     eax, [rbx+44h]
0x18000464b  mov     [rdi+30h], eax
0x18000464e  mov     eax, [rbx+3Ch]
0x180004651  mov     [rdi+34h], eax
0x180004654  mov     eax, [rbx+40h]
0x180004657  mov     [rdi+38h], eax
0x18000465a  mov     rax, [rsp+68h+lpszTitle]
0x180004662  mov     [rdi+280h], rbp
0x180004669  mov     [rdi+278h], rax
0x180004670  mov     [rdi+358h], r12
0x180004677  mov     rax, [rbx+50h]
0x18000467b  mov     [rdi+368h], rax
0x180004682  mov     eax, [rbx+58h]
0x180004685  mov     [rbx+50h], r12
0x180004689  mov     rcx, [rdi+280h]
0x180004690  mov     [rdi+370h], eax
0x180004696  test    rcx, rcx
0x180004699  jz      short loc_1800046CB
0x18000469b  mov     rax, [rcx]
0x18000469e  lea     rbp, [rdi+288h]
0x1800046a5  mov     r8d, 0CCh
0x1800046ab  mov     rdx, rbp
0x1800046ae  mov     rax, [rax+20h]
0x1800046b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b7  test    eax, eax
0x1800046b9  jnz     short loc_1800046C4
0x1800046bb  cmp     dword ptr [rbp+0], 73646976h
0x1800046c2  jz      short loc_1800046CB
0x1800046c4  mov     [rdi+280h], r12
0x1800046cb  mov     rcx, cs:ghInst; hInstance
0x1800046d2  lea     r9, ICCompressorChooseDlgProc; lpDialogFunc
0x1800046d9  mov     r8, r15; hWndParent
0x1800046dc  mov     [rsp+68h+dwInitParam], rdi; dwInitParam
0x1800046e1  lea     rdx, TemplateName; "ICCDLG"
0x1800046e8  call    cs:__imp_DialogBoxParamW
0x1800046ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800046f2  mov     rbp, r12
0x1800046f5  cmovnz  rbp, rax
0x1800046f9  test    rbp, rbp
0x1800046fc  jz      short loc_18000473E
0x1800046fe  mov     rcx, rbx; pc
0x180004701  call    ICCompressorFree
0x180004706  mov     eax, [rdi+30h]
0x180004709  mov     [rbx+44h], eax
0x18000470c  mov     eax, [rdi+34h]
0x18000470f  mov     [rbx+3Ch], eax
0x180004712  mov     eax, [rdi+38h]
0x180004715  mov     [rbx+40h], eax
0x180004718  mov     rax, [rdi+28h]
0x18000471c  mov     [rbx+8], rax
0x180004720  mov     eax, [rdi+4]
0x180004723  mov     [rbx+14h], eax
0x180004726  mov     rax, [rdi+368h]
0x18000472d  mov     [rbx+50h], rax
0x180004731  mov     eax, [rdi+370h]
0x180004737  or      dword ptr [rbx+4], 1
0x18000473b  mov     [rbx+58h], eax
0x18000473e  mov     rcx, rdi; pMem
0x180004741  call    cs:__imp_GlobalHandle
0x180004747  mov     rcx, rax; hMem
0x18000474a  call    cs:__imp_GlobalUnlock
0x180004750  mov     rcx, rdi; pMem
0x180004753  call    cs:__imp_GlobalHandle
0x180004759  mov     rcx, rax; hMem
0x18000475c  call    cs:__imp_GlobalFree
0x180004762  test    rbp, rbp
0x180004765  jz      short loc_1800047CF
0x180004767  mov     rcx, [rbx+8]; hic
0x18000476b  test    rcx, rcx
0x18000476e  jz      short loc_1800047BB
0x180004770  test    rsi, rsi
0x180004773  jz      short loc_1800047BB
0x180004775  mov     edi, 4004h
0x18000477a  xor     r9d, r9d; dw2
0x18000477d  mov     edx, edi; msg
0x18000477f  mov     r8, rsi; dw1
0x180004782  call    ICSendMessage
0x180004787  test    eax, eax
0x180004789  jz      short loc_1800047C2
0x18000478b  mov     edx, eax; dwBytes
0x18000478d  mov     ecx, 2; uFlags
0x180004792  call    cs:__imp_GlobalAlloc
0x180004798  mov     rcx, rax; hMem
0x18000479b  call    cs:__imp_GlobalLock
0x1800047a1  mov     [rbx+20h], rax
0x1800047a5  test    rax, rax
0x1800047a8  jz      short loc_1800047C2
0x1800047aa  mov     rcx, [rbx+8]; hic
0x1800047ae  mov     r9, rax; dw2
0x1800047b1  mov     r8, rsi; dw1
0x1800047b4  mov     edx, edi; msg
0x1800047b6  call    ICSendMessage
0x1800047bb  mov     eax, 1
0x1800047c0  jmp     short loc_1800047D1
0x1800047c2  mov     rcx, [rbx+8]; hic
0x1800047c6  call    ICClose
0x1800047cb  mov     [rbx+8], r12
0x1800047cf  xor     eax, eax
0x1800047d1  add     rsp, 30h
0x1800047d5  pop     r15
0x1800047d7  pop     r14
0x1800047d9  pop     r12
0x1800047db  pop     rdi
0x1800047dc  pop     rsi
0x1800047dd  pop     rbp
0x1800047de  pop     rbx
0x1800047df  retn
```

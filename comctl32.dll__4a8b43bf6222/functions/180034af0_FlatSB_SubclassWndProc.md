# FlatSB_SubclassWndProc

- ea: `0x180034af0`
- end: `0x180034cc3`
- name: `FlatSB_SubclassWndProc`
- size: `467`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180018090`
- `0x180030230`
- `0x1800306e0`
- `0x180031ac8`
- `0x180032f20`
- `0x1800335f0`
- `0x180033e1c`
- `0x180033f88`
- `0x1800342c4`
- `0x180034af0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180034c3a`
- `GDI32!DeleteObject` at `0x180034c47`
- `GDI32!DeleteObject` at `0x180034c3a`
- `GDI32!DeleteObject` at `0x180034c47`
- `KERNEL32!LocalFree` at `0x180034c50`
- `KERNEL32!LocalFree` at `0x180034c50`
- `USER32!GetKeyState` at `0x180034bd0`
- `USER32!GetKeyState` at `0x180034bd0`

## pseudocode

```c
LRESULT __fastcall FlatSB_SubclassWndProc(
        HWND hWnd,
        UINT uMsg,
        WPARAM wParam,
        struct tagRECT *lParam,
        UINT_PTR uIdSubclass,
        DWORD_PTR dwRefData)
{
  struct tagRECT *v6; // rbp
  WPARAM v7; // rdi
  UINT v8; // r14d
  HWND v9; // rsi
  unsigned __int16 KeyState; // ax
  LRESULT v12; // rdi

  v6 = lParam;
  v7 = wParam;
  v8 = uMsg;
  v9 = hWnd;
  if ( !dwRefData )
    return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
  if ( dwRefData == -1 )
  {
    if ( uMsg != 130 )
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    goto LABEL_24;
  }
  if ( uMsg == 26 )
  {
    FlatSB_InitWSBMetrics(dwRefData);
    CCInvalidateFrame(v9);
    uMsg = 26;
    goto LABEL_29;
  }
  if ( uMsg != 31 )
  {
    if ( uMsg != 130 )
    {
      switch ( uMsg )
      {
        case 0x83u:
          return FlatSB_NCCalcProc((_DWORD *)dwRefData, hWnd, wParam, lParam);
        case 0x84u:
          return FlatSB_NCHitTestProc(dwRefData, hWnd);
        case 0x85u:
          return FlatSB_NCPaintProc(dwRefData, hWnd);
        case 0x112u:
          uMsg = 274;
          if ( (((wParam & 0xFFF0) - 61552) & 0xFFFFFFEF) == 0 )
          {
            DefSubclassProc(hWnd, 0x112u, 0, (LPARAM)lParam);
            KeyState = GetKeyState(16);
            FlatSB_Internal_SBTrackInit(dwRefData, v9, v6, v7 & 0xF, KeyState >> 15);
            return 0;
          }
          return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
      }
      if ( uMsg - 276 > 1 )
        return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
      if ( !lParam && !*(_DWORD *)(dwRefData + 120) && (_WORD)wParam == 8 )
        FlatSB_NCPaintProc(dwRefData, hWnd);
      uMsg = v8;
LABEL_29:
      lParam = v6;
      wParam = v7;
      hWnd = v9;
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    }
    DeleteObject(*(HGDIOBJ *)(dwRefData + 248));
    DeleteObject(*(HGDIOBJ *)(dwRefData + 240));
    LocalFree((HLOCAL)dwRefData);
LABEL_24:
    RemoveWindowSubclass(v9, FlatSB_SubclassWndProc, 0);
    uMsg = 130;
    goto LABEL_29;
  }
  v12 = DefSubclassProc(hWnd, 0x1Fu, wParam, (LPARAM)lParam);
  if ( *(_QWORD *)(dwRefData + 88) )
    FlatSB_Internal_EndScroll(dwRefData, 1);
  return v12;
}

```

## disassembly

```asm
0x180034af0  push    rbx
0x180034af2  push    rbp
0x180034af3  push    rsi
0x180034af4  push    rdi
0x180034af5  push    r14
0x180034af7  sub     rsp, 30h
0x180034afb  mov     rbx, [rsp+58h+dwRefData]
0x180034b03  mov     rbp, r9
0x180034b06  mov     rdi, r8
0x180034b09  mov     r14d, edx
0x180034b0c  mov     rsi, rcx
0x180034b0f  test    rbx, rbx
0x180034b12  jz      loc_180034CB3
0x180034b18  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180034b1c  jnz     short loc_180034B2F
0x180034b1e  cmp     edx, 82h
0x180034b24  jz      loc_180034C56
0x180034b2a  jmp     loc_180034CB3
0x180034b2f  mov     eax, r14d
0x180034b32  sub     eax, 1Ah
0x180034b35  jz      loc_180034C95
0x180034b3b  sub     eax, 5
0x180034b3e  jz      loc_180034C6F
0x180034b44  sub     eax, 63h ; 'c'
0x180034b47  jz      loc_180034C33
0x180034b4d  sub     eax, 1
0x180034b50  jz      loc_180034C23
0x180034b56  sub     eax, 1
0x180034b59  jz      loc_180034C0B
0x180034b5f  sub     eax, 1
0x180034b62  jz      loc_180034BFB
0x180034b68  sub     eax, 8Dh
0x180034b6d  jz      short loc_180034BA7
0x180034b6f  sub     eax, 2
0x180034b72  jz      short loc_180034B7D
0x180034b74  cmp     eax, 1
0x180034b77  jnz     loc_180034CB3
0x180034b7d  test    rbp, rbp
0x180034b80  jnz     short loc_180034B9F
0x180034b82  cmp     [rbx+78h], ebp
0x180034b85  jnz     short loc_180034B9F
0x180034b87  cmp     di, 8
0x180034b8b  jnz     short loc_180034B9F
0x180034b8d  xor     r9d, r9d
0x180034b90  lea     r8d, [rbp+1]
0x180034b94  mov     rdx, rsi
0x180034b97  mov     rcx, rbx
0x180034b9a  call    FlatSB_NCPaintProc
0x180034b9f  mov     edx, r14d
0x180034ba2  jmp     loc_180034CAA
0x180034ba7  mov     eax, edi
0x180034ba9  mov     edx, 112h; uMsg
0x180034bae  and     eax, 0FFF0h
0x180034bb3  sub     eax, 0F070h
0x180034bb8  test    eax, 0FFFFFFEFh
0x180034bbd  jnz     loc_180034CB3
0x180034bc3  xor     r8d, r8d; wParam
0x180034bc6  call    DefSubclassProc
0x180034bcb  mov     ecx, 10h; nVirtKey
0x180034bd0  call    cs:__imp_GetKeyState
0x180034bd6  movzx   eax, ax
0x180034bd9  and     edi, 0Fh
0x180034bdc  shr     eax, 0Fh
0x180034bdf  mov     r8, rbp
0x180034be2  mov     r9d, edi
0x180034be5  mov     [rsp+58h+var_38], eax
0x180034be9  mov     rdx, rsi
0x180034bec  mov     rcx, rbx
0x180034bef  call    FlatSB_Internal_SBTrackInit
0x180034bf4  xor     eax, eax
0x180034bf6  jmp     loc_180034CB8
0x180034bfb  mov     rdx, rsi
0x180034bfe  mov     rcx, rbx
0x180034c01  call    FlatSB_NCPaintProc
0x180034c06  jmp     loc_180034CB8
0x180034c0b  mov     rdx, rsi
0x180034c0e  mov     [rsp+58h+var_38], 0
0x180034c16  mov     rcx, rbx
0x180034c19  call    FlatSB_NCHitTestProc
0x180034c1e  jmp     loc_180034CB8
0x180034c23  mov     rdx, rsi
0x180034c26  mov     rcx, rbx
0x180034c29  call    FlatSB_NCCalcProc
0x180034c2e  jmp     loc_180034CB8
0x180034c33  mov     rcx, [rbx+0F8h]; ho
0x180034c3a  call    cs:__imp_DeleteObject
0x180034c40  mov     rcx, [rbx+0F0h]; ho
0x180034c47  call    cs:__imp_DeleteObject
0x180034c4d  mov     rcx, rbx; hMem
0x180034c50  call    cs:__imp_LocalFree
0x180034c56  xor     r8d, r8d; uIdSubclass
0x180034c59  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034c60  mov     rcx, rsi; hWnd
0x180034c63  call    RemoveWindowSubclass
0x180034c68  mov     edx, 82h
0x180034c6d  jmp     short loc_180034CAA
0x180034c6f  mov     edx, 1Fh; uMsg
0x180034c74  call    DefSubclassProc
0x180034c79  cmp     qword ptr [rbx+58h], 0
0x180034c7e  mov     rdi, rax
0x180034c81  jz      short loc_180034C90
0x180034c83  mov     edx, 1
0x180034c88  mov     rcx, rbx
0x180034c8b  call    FlatSB_Internal_EndScroll
0x180034c90  mov     rax, rdi
0x180034c93  jmp     short loc_180034CB8
0x180034c95  mov     rcx, rbx
0x180034c98  call    FlatSB_InitWSBMetrics
0x180034c9d  mov     rcx, rsi
0x180034ca0  call    CCInvalidateFrame
0x180034ca5  mov     edx, 1Ah; uMsg
0x180034caa  mov     r9, rbp; lParam
0x180034cad  mov     r8, rdi; wParam
0x180034cb0  mov     rcx, rsi; hWnd
0x180034cb3  call    DefSubclassProc
0x180034cb8  add     rsp, 30h
0x180034cbc  pop     r14
0x180034cbe  pop     rdi
0x180034cbf  pop     rsi
0x180034cc0  pop     rbp
0x180034cc1  pop     rbx
0x180034cc2  retn
```

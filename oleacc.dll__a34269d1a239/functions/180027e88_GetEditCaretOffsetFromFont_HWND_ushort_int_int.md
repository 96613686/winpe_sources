# GetEditCaretOffsetFromFont(HWND__ *,ushort,int,int *)

- ea: `0x180027e88`
- end: `0x180027fdc`
- name: `?GetEditCaretOffsetFromFont@@YAHPEAUHWND__@@GHPEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027e2c`

## callees

- `0x18001e4c0`
- `0x180027e88`

## import_xrefs

- `USER32!GetDC` at `0x180027ecf`
- `USER32!GetDC` at `0x180027ecf`
- `USER32!ReleaseDC` at `0x180027fb1`
- `USER32!ReleaseDC` at `0x180027fb1`
- `USER32!SystemParametersInfoW` at `0x180027eeb`
- `USER32!SystemParametersInfoW` at `0x180027eeb`
- `GDI32!CreateFontW` at `0x180027f42`
- `GDI32!CreateFontW` at `0x180027f42`
- `GDI32!DeleteObject` at `0x180027fa5`
- `GDI32!DeleteObject` at `0x180027fa5`
- `GDI32!SelectObject` at `0x180027f56`
- `GDI32!SelectObject` at `0x180027f9c`
- `GDI32!SelectObject` at `0x180027f56`
- `GDI32!SelectObject` at `0x180027f9c`
- `GDI32!GetCharABCWidthsW` at `0x180027f7b`
- `GDI32!GetCharABCWidthsW` at `0x180027f7b`

## pseudocode

```c
__int64 __fastcall GetEditCaretOffsetFromFont(HWND hWnd, __int16 a2, int a3, int *a4)
{
  unsigned int v4; // ebx
  HDC DC; // rsi
  int cWeight; // eax
  HFONT FontW; // rax
  HFONT v12; // r15
  HGDIOBJ v13; // r12
  int pvParam; // [rsp+70h] [rbp-58h] BYREF
  _ABC ABC; // [rsp+78h] [rbp-50h] BYREF

  v4 = 0;
  if ( a2 == -4083 )
  {
    pvParam = 0;
    DC = GetDC(hWnd);
    SystemParametersInfoW(0x2006u, 0, &pvParam, 0);
    cWeight = 400;
    if ( pvParam > 1 )
      cWeight = 700;
    FontW = CreateFontW(a3, 0, 0, 0, cWeight, 0, 0, 0, 1u, 0, 0, 0, 0, L"Microsoft Sans Serif");
    v12 = FontW;
    if ( FontW )
    {
      v13 = SelectObject(DC, FontW);
      *(_QWORD *)&ABC.abcA = 0;
      ABC.abcC = 0;
      if ( GetCharABCWidthsW(DC, 0xF00Du, 0xF00Du, &ABC) )
      {
        v4 = 1;
        *a4 = 1 - ABC.abcB;
      }
      SelectObject(DC, v13);
      DeleteObject(v12);
    }
    ReleaseDC(hWnd, DC);
    return v4;
  }
  else
  {
    *a4 = 0;
    return 1;
  }
}

```

## disassembly

```asm
0x180027e88  push    rbx
0x180027e8a  push    rbp
0x180027e8b  push    rsi
0x180027e8c  push    r12
0x180027e8e  push    r13
0x180027e90  push    r14
0x180027e92  push    r15
0x180027e94  sub     rsp, 90h
0x180027e9b  mov     rax, cs:__security_cookie
0x180027ea2  xor     rax, rsp
0x180027ea5  mov     [rsp+0C8h+var_40], rax
0x180027ead  mov     r13d, 0F00Dh
0x180027eb3  xor     ebx, ebx
0x180027eb5  mov     r14, r9
0x180027eb8  mov     r15d, r8d
0x180027ebb  mov     rbp, rcx
0x180027ebe  cmp     dx, r13w
0x180027ec2  jz      short loc_180027ECF
0x180027ec4  mov     [r9], ebx
0x180027ec7  lea     eax, [rbx+1]
0x180027eca  jmp     loc_180027FB9
0x180027ecf  call    cs:__imp_GetDC
0x180027ed5  xor     r9d, r9d; fWinIni
0x180027ed8  mov     [rsp+0C8h+pvParam], ebx
0x180027edc  lea     r8, [rsp+0C8h+pvParam]; pvParam
0x180027ee1  xor     edx, edx; uiParam
0x180027ee3  mov     ecx, 2006h; uiAction
0x180027ee8  mov     rsi, rax
0x180027eeb  call    cs:__imp_SystemParametersInfoW
0x180027ef1  cmp     [rsp+0C8h+pvParam], 1
0x180027ef6  mov     eax, 190h
0x180027efb  mov     ecx, 2BCh
0x180027f00  cmovg   eax, ecx
0x180027f03  lea     rcx, pszFaceName; "Microsoft Sans Serif"
0x180027f0a  mov     [rsp+0C8h+pszFaceName], rcx; pszFaceName
0x180027f0f  xor     r9d, r9d; cOrientation
0x180027f12  mov     [rsp+0C8h+iPitchAndFamily], ebx; iPitchAndFamily
0x180027f16  xor     r8d, r8d; cEscapement
0x180027f19  mov     [rsp+0C8h+iQuality], ebx; iQuality
0x180027f1d  xor     edx, edx; cWidth
0x180027f1f  mov     [rsp+0C8h+iClipPrecision], ebx; iClipPrecision
0x180027f23  mov     ecx, r15d; cHeight
0x180027f26  mov     [rsp+0C8h+iOutPrecision], ebx; iOutPrecision
0x180027f2a  mov     [rsp+0C8h+iCharSet], 1; iCharSet
0x180027f32  mov     [rsp+0C8h+bStrikeOut], ebx; bStrikeOut
0x180027f36  mov     [rsp+0C8h+bUnderline], ebx; bUnderline
0x180027f3a  mov     [rsp+0C8h+bItalic], ebx; bItalic
0x180027f3e  mov     [rsp+0C8h+cWeight], eax; cWeight
0x180027f42  call    cs:__imp_CreateFontW
0x180027f48  mov     r15, rax
0x180027f4b  test    rax, rax
0x180027f4e  jz      short loc_180027FAB
0x180027f50  mov     rdx, rax; h
0x180027f53  mov     rcx, rsi; hdc
0x180027f56  call    cs:__imp_SelectObject
0x180027f5c  lea     r9, [rsp+0C8h+ABC]; lpABC
0x180027f61  mov     r8d, r13d; wLast
0x180027f64  mov     r12, rax
0x180027f67  mov     edx, r13d; wFirst
0x180027f6a  xor     eax, eax
0x180027f6c  mov     rcx, rsi; hdc
0x180027f6f  mov     qword ptr [rsp+0C8h+ABC.abcA], rax
0x180027f74  mov     [rsp+0C8h+ABC.abcC], eax
0x180027f7b  call    cs:__imp_GetCharABCWidthsW
0x180027f81  test    eax, eax
0x180027f83  jz      short loc_180027F96
0x180027f85  mov     eax, 1
0x180027f8a  mov     ebx, 1
0x180027f8f  sub     eax, [rsp+0C8h+ABC.abcB]
0x180027f93  mov     [r14], eax
0x180027f96  mov     rdx, r12; h
0x180027f99  mov     rcx, rsi; hdc
0x180027f9c  call    cs:__imp_SelectObject
0x180027fa2  mov     rcx, r15; ho
0x180027fa5  call    cs:__imp_DeleteObject
0x180027fab  mov     rdx, rsi; hDC
0x180027fae  mov     rcx, rbp; hWnd
0x180027fb1  call    cs:__imp_ReleaseDC
0x180027fb7  mov     eax, ebx
0x180027fb9  mov     rcx, [rsp+0C8h+var_40]
0x180027fc1  xor     rcx, rsp; StackCookie
0x180027fc4  call    __security_check_cookie
0x180027fc9  add     rsp, 90h
0x180027fd0  pop     r15
0x180027fd2  pop     r14
0x180027fd4  pop     r13
0x180027fd6  pop     r12
0x180027fd8  pop     rsi
0x180027fd9  pop     rbp
0x180027fda  pop     rbx
0x180027fdb  retn
```

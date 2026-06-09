# CNativeFont::_GetNativeDialogFont(HWND__ *)

- ea: `0x180089c68`
- end: `0x180089d8e`
- name: `?_GetNativeDialogFont@CNativeFont@@IEAAJPEAUHWND__@@@Z`
- size: `294`
- prototype: `int(CNativeFont *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180089f50`

## callees

- `0x1800115f0`
- `0x180089c68`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetObjectW` at `0x180089ce7`
- `GDI32!GetObjectW` at `0x180089ce7`
- `GDI32!CreateFontIndirectW` at `0x180089d3f`
- `GDI32!CreateFontIndirectW` at `0x180089d3f`
- `USER32!SystemParametersInfoW` at `0x180089cfa`
- `USER32!SystemParametersInfoW` at `0x180089cfa`
- `USER32!SendMessageW` at `0x180089cab`
- `USER32!SendMessageW` at `0x180089cab`

## pseudocode

```c
_BOOL8 __fastcall CNativeFont::_GetNativeDialogFont(CNativeFont *this, HWND a2)
{
  HFONT v2; // rbx
  int v4; // eax
  HFONT v5; // rax
  LOGFONTW pvParam; // [rsp+20h] [rbp-D8h] BYREF
  _DWORD pv[24]; // [rsp+80h] [rbp-78h] BYREF

  v2 = (HFONT)*((_QWORD *)this + 9);
  if ( !v2 )
  {
    v2 = (HFONT)SendMessageW(a2, 0x31u, 0, 0);
    memset(pv, 0, 0x5Cu);
    memset(&pvParam, 0, sizeof(pvParam));
    GetObjectW(v2, 92, pv);
    SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
    if ( (*((_BYTE *)this + 24) & 0x20) != 0 )
    {
      v4 = CNativeFont::_s_uiFontAssocStatus;
      if ( !CNativeFont::_s_uiFontAssocStatus )
      {
        v4 = 2;
        CNativeFont::_s_uiFontAssocStatus = 2;
      }
      if ( v4 == 2 )
        goto LABEL_11;
    }
    if ( pvParam.lfCharSet == HIBYTE(pv[5]) )
    {
LABEL_11:
      *((_QWORD *)this + 8) = v2;
    }
    else
    {
      pvParam.lfHeight = pv[0];
      *((_QWORD *)this + 8) = v2;
      v5 = CreateFontIndirectW(&pvParam);
      if ( v5 )
      {
        if ( v5 != v2 )
          *((_QWORD *)this + 10) = v2;
        v2 = v5;
      }
    }
    *((_QWORD *)this + 9) = v2;
  }
  return v2 == *((HFONT *)this + 8);
}

```

## disassembly

```asm
0x180089c68  mov     [rsp+arg_10], rbx
0x180089c6d  mov     [rsp+arg_18], rsi
0x180089c72  push    rdi
0x180089c73  sub     rsp, 0F0h
0x180089c7a  mov     rax, cs:__security_cookie
0x180089c81  xor     rax, rsp
0x180089c84  mov     [rsp+0F8h+var_18], rax
0x180089c8c  mov     rbx, [rcx+48h]
0x180089c90  mov     rax, rdx
0x180089c93  mov     rdi, rcx
0x180089c96  test    rbx, rbx
0x180089c99  jnz     loc_180089D60
0x180089c9f  xor     r9d, r9d; lParam
0x180089ca2  lea     edx, [rbx+31h]; Msg
0x180089ca5  xor     r8d, r8d; wParam
0x180089ca8  mov     rcx, rax; hWnd
0x180089cab  call    cs:__imp_SendMessageW
0x180089cb1  mov     esi, 5Ch ; '\'
0x180089cb6  lea     rcx, [rsp+0F8h+pv]; void *
0x180089cbe  mov     r8d, esi; Size
0x180089cc1  xor     edx, edx; Val
0x180089cc3  mov     rbx, rax
0x180089cc6  call    memset
0x180089ccb  mov     r8d, esi; Size
0x180089cce  lea     rcx, [rsp+0F8h+pvParam]; void *
0x180089cd3  xor     edx, edx; Val
0x180089cd5  call    memset
0x180089cda  lea     r8, [rsp+0F8h+pv]; pv
0x180089ce2  mov     edx, esi; c
0x180089ce4  mov     rcx, rbx; h
0x180089ce7  call    cs:__imp_GetObjectW
0x180089ced  xor     r9d, r9d; fWinIni
0x180089cf0  lea     r8, [rsp+0F8h+pvParam]; pvParam
0x180089cf5  mov     edx, esi; uiParam
0x180089cf7  lea     ecx, [rsi-3Dh]; uiAction
0x180089cfa  call    cs:__imp_SystemParametersInfoW
0x180089d00  test    byte ptr [rdi+18h], 20h
0x180089d04  jz      short loc_180089D1E
0x180089d06  mov     eax, cs:?_s_uiFontAssocStatus@CNativeFont@@1W4FASTATUS@@A; FASTATUS CNativeFont::_s_uiFontAssocStatus
0x180089d0c  test    eax, eax
0x180089d0e  jnz     short loc_180089D19
0x180089d10  lea     eax, [rsi-5Ah]
0x180089d13  mov     cs:?_s_uiFontAssocStatus@CNativeFont@@1W4FASTATUS@@A, eax; FASTATUS CNativeFont::_s_uiFontAssocStatus
0x180089d19  cmp     eax, 2
0x180089d1c  jz      short loc_180089D58
0x180089d1e  mov     al, [rsp+0F8h+var_61]
0x180089d25  cmp     [rsp+0F8h+var_C1], al
0x180089d29  jz      short loc_180089D58
0x180089d2b  mov     eax, [rsp+0F8h+pv]
0x180089d32  lea     rcx, [rsp+0F8h+pvParam]; lplf
0x180089d37  mov     [rsp+0F8h+pvParam], eax
0x180089d3b  mov     [rdi+40h], rbx
0x180089d3f  call    cs:__imp_CreateFontIndirectW
0x180089d45  test    rax, rax
0x180089d48  jz      short loc_180089D5C
0x180089d4a  cmp     rax, rbx
0x180089d4d  jz      short loc_180089D53
0x180089d4f  mov     [rdi+50h], rbx
0x180089d53  mov     rbx, rax
0x180089d56  jmp     short loc_180089D5C
0x180089d58  mov     [rdi+40h], rbx
0x180089d5c  mov     [rdi+48h], rbx
0x180089d60  xor     eax, eax
0x180089d62  cmp     rbx, [rdi+40h]
0x180089d66  setz    al
0x180089d69  mov     rcx, [rsp+0F8h+var_18]
0x180089d71  xor     rcx, rsp; StackCookie
0x180089d74  call    __security_check_cookie
0x180089d79  lea     r11, [rsp+0F8h+var_8]
0x180089d81  mov     rbx, [r11+20h]
0x180089d85  mov     rsi, [r11+28h]
0x180089d89  mov     rsp, r11
0x180089d8c  pop     rdi
0x180089d8d  retn
```

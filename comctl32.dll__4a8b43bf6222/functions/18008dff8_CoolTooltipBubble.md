# CoolTooltipBubble

- ea: `0x18008dff8`
- end: `0x18008e0d1`
- name: `CoolTooltipBubble`
- size: `217`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004ca94`

## callees

- `0x18008dff8`
- `0x18008e1e0`

## import_xrefs

- `USER32!SetWindowPos` at `0x18008e0c2`
- `USER32!SetWindowPos` at `0x18008e0c2`
- `USER32!SystemParametersInfoW` at `0x18008e024`
- `USER32!SystemParametersInfoW` at `0x18008e048`
- `USER32!SystemParametersInfoW` at `0x18008e024`
- `USER32!SystemParametersInfoW` at `0x18008e048`
- `USER32!GetMessagePos` at `0x18008e065`
- `USER32!GetMessagePos` at `0x18008e065`

## pseudocode

```c
int __fastcall CoolTooltipBubble(HWND hWnd, __int64 a2, int a3, int a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  DWORD MessagePos; // eax
  _DWORD pvParam[14]; // [rsp+40h] [rbp-38h] BYREF

  pvParam[0] = 1;
  SystemParametersInfoW(0x1016u, 0, pvParam, 0);
  if ( pvParam[0] )
  {
    pvParam[0] = 0;
    SystemParametersInfoW(0x1018u, 0, pvParam, 0);
    if ( pvParam[0] && a3 )
    {
      v9 = 0x80000;
      return NT5_AnimateWindow(hWnd, v8, v9);
    }
    if ( a4 )
    {
      MessagePos = GetMessagePos();
      v8 = 4;
      v9 = 8;
      if ( SHIWORD(MessagePos) <= *(_DWORD *)(a2 + 4) + (*(_DWORD *)(a2 + 12) - *(_DWORD *)(a2 + 4)) / 2 )
        v9 = 4;
      LODWORD(v9) = v9 | 0x40000;
      return NT5_AnimateWindow(hWnd, v8, v9);
    }
  }
  return SetWindowPos(hWnd, 0, 0, 0, 0, 0, 0x57u);
}

```

## disassembly

```asm
0x18008dff8  push    rbx
0x18008dffa  push    rbp
0x18008dffb  push    rsi
0x18008dffc  push    rdi
0x18008dffd  sub     rsp, 58h
0x18008e001  mov     edi, r9d
0x18008e004  mov     [rsp+78h+pvParam], 1
0x18008e00c  mov     esi, r8d
0x18008e00f  mov     rbp, rdx
0x18008e012  mov     rbx, rcx
0x18008e015  lea     r8, [rsp+78h+pvParam]; pvParam
0x18008e01a  xor     r9d, r9d; fWinIni
0x18008e01d  xor     edx, edx; uiParam
0x18008e01f  mov     ecx, 1016h; uiAction
0x18008e024  call    cs:__imp_SystemParametersInfoW
0x18008e02a  cmp     [rsp+78h+pvParam], 0
0x18008e02f  jz      short loc_18008E09F
0x18008e031  xor     r9d, r9d; fWinIni
0x18008e034  mov     [rsp+78h+pvParam], 0
0x18008e03c  lea     r8, [rsp+78h+pvParam]; pvParam
0x18008e041  xor     edx, edx; uiParam
0x18008e043  mov     ecx, 1018h; uiAction
0x18008e048  call    cs:__imp_SystemParametersInfoW
0x18008e04e  cmp     [rsp+78h+pvParam], 0
0x18008e053  jz      short loc_18008E061
0x18008e055  test    esi, esi
0x18008e057  jz      short loc_18008E061
0x18008e059  mov     r8d, 80000h
0x18008e05f  jmp     short loc_18008E095
0x18008e061  test    edi, edi
0x18008e063  jz      short loc_18008E09F
0x18008e065  call    cs:__imp_GetMessagePos
0x18008e06b  mov     ecx, eax
0x18008e06d  mov     eax, [rbp+0Ch]
0x18008e070  sub     eax, [rbp+4]
0x18008e073  cdq
0x18008e074  shr     ecx, 10h
0x18008e077  sub     eax, edx
0x18008e079  movsx   ecx, cx
0x18008e07c  sar     eax, 1
0x18008e07e  mov     edx, 4
0x18008e083  add     eax, [rbp+4]
0x18008e086  cmp     ecx, eax
0x18008e088  lea     r8d, [rdx+4]
0x18008e08c  cmovle  r8d, edx
0x18008e090  bts     r8d, 12h
0x18008e095  mov     rcx, rbx
0x18008e098  call    NT5_AnimateWindow
0x18008e09d  jmp     short loc_18008E0C8
0x18008e09f  mov     [rsp+78h+uFlags], 57h ; 'W'; uFlags
0x18008e0a7  xor     r9d, r9d; Y
0x18008e0aa  mov     [rsp+78h+cy], 0; cy
0x18008e0b2  xor     r8d, r8d; X
0x18008e0b5  xor     edx, edx; hWndInsertAfter
0x18008e0b7  mov     [rsp+78h+var_58], 0; cx
0x18008e0bf  mov     rcx, rbx; hWnd
0x18008e0c2  call    cs:__imp_SetWindowPos
0x18008e0c8  add     rsp, 58h
0x18008e0cc  pop     rdi
0x18008e0cd  pop     rsi
0x18008e0ce  pop     rbp
0x18008e0cf  pop     rbx
0x18008e0d0  retn
```

# CPackage::_IconCalcSize(tagRECT *,ushort const *)

- ea: `0x18000b94c`
- end: `0x18000ba9a`
- name: `?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z`
- size: `334`
- prototype: `HDC __fastcall(CPackage *this, struct tagRECT *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c8c`
- `0x18000a474`
- `0x18000a624`
- `0x18000afb4`
- `0x18000baa0`

## callees

- `0x18000b94c`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ba16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ba16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b9c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b9c4`
- `USER32!GetDC` at `0x18000b97d`
- `USER32!GetDC` at `0x18000b97d`
- `USER32!DrawTextW` at `0x18000b9f4`
- `USER32!DrawTextW` at `0x18000b9f4`
- `USER32!ReleaseDC` at `0x18000ba6d`
- `USER32!ReleaseDC` at `0x18000ba6d`
- `USER32!SetRect` at `0x18000b9b7`
- `USER32!SetRect` at `0x18000b9b7`
- `GDI32!SelectObject` at `0x18000b9d4`
- `GDI32!SelectObject` at `0x18000ba09`
- `GDI32!SelectObject` at `0x18000b9d4`
- `GDI32!SelectObject` at `0x18000ba09`

## pseudocode

```c
HDC __fastcall CPackage::_IconCalcSize(CPackage *this, struct tagRECT *a2, const unsigned __int16 *a3)
{
  HDC result; // rax
  HDC v6; // rbx
  HGDIOBJ v7; // rsi
  LONG right; // r8d
  int v9; // r9d
  struct tagRECT rc; // [rsp+30h] [rbp-38h] BYREF

  rc = 0;
  result = GetDC(0);
  v6 = result;
  if ( result )
  {
    if ( *a3 )
    {
      SetRect(&rc, 0, 0, g_cxArrange, g_cyArrange);
      AcquireSRWLockShared(&PackagerFontLock);
      v7 = SelectObject(v6, g_hfontTitle);
      rc.bottom = DrawTextW(v6, a3, -1, &rc, 0xC30u);
      if ( v7 )
        SelectObject(v6, v7);
      ReleaseSRWLockShared(&PackagerFontLock);
    }
    right = g_cxIcon;
    if ( ++rc.right > g_cxIcon )
      right = rc.right;
    v9 = g_cyIcon + 1 + rc.bottom;
    a2->right = right + right / 4;
    a2->bottom = v9 + v9 / 8;
    ReleaseDC(0, v6);
    return (HDC)1;
  }
  return result;
}

```

## disassembly

```asm
0x18000b94c  mov     [rsp+arg_0], rbx
0x18000b951  mov     [rsp+arg_18], rbp
0x18000b956  push    rsi
0x18000b957  push    rdi
0x18000b958  push    r14
0x18000b95a  sub     rsp, 50h
0x18000b95e  mov     rax, cs:__security_cookie
0x18000b965  xor     rax, rsp
0x18000b968  mov     [rsp+68h+var_28], rax
0x18000b96d  xorps   xmm0, xmm0
0x18000b970  xor     ecx, ecx; hWnd
0x18000b972  movups  xmmword ptr [rsp+68h+rc.left], xmm0
0x18000b977  mov     rdi, r8
0x18000b97a  mov     rbp, rdx
0x18000b97d  call    cs:__imp_GetDC
0x18000b983  xor     r14d, r14d
0x18000b986  mov     rbx, rax
0x18000b989  test    rax, rax
0x18000b98c  jz      loc_18000BA78
0x18000b992  cmp     [rdi], r14w
0x18000b996  jz      loc_18000BA1C
0x18000b99c  mov     eax, cs:?g_cyArrange@@3HA; int g_cyArrange
0x18000b9a2  lea     rcx, [rsp+68h+rc]; lprc
0x18000b9a7  mov     r9d, cs:?g_cxArrange@@3HA; xRight
0x18000b9ae  xor     r8d, r8d; yTop
0x18000b9b1  xor     edx, edx; xLeft
0x18000b9b3  mov     [rsp+68h+yBottom], eax; yBottom
0x18000b9b7  call    cs:__imp_SetRect
0x18000b9bd  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000b9c4  call    cs:__imp_AcquireSRWLockShared
0x18000b9ca  mov     rdx, cs:?g_hfontTitle@@3PEAUHFONT__@@EA; h
0x18000b9d1  mov     rcx, rbx; hdc
0x18000b9d4  call    cs:__imp_SelectObject
0x18000b9da  lea     r9, [rsp+68h+rc]; lprc
0x18000b9df  mov     [rsp+68h+yBottom], 0C30h; format
0x18000b9e7  or      r8d, 0FFFFFFFFh; cchText
0x18000b9eb  mov     rdx, rdi; lpchText
0x18000b9ee  mov     rcx, rbx; hdc
0x18000b9f1  mov     rsi, rax
0x18000b9f4  call    cs:__imp_DrawTextW
0x18000b9fa  mov     [rsp+68h+rc.bottom], eax
0x18000b9fe  test    rsi, rsi
0x18000ba01  jz      short loc_18000BA0F
0x18000ba03  mov     rdx, rsi; h
0x18000ba06  mov     rcx, rbx; hdc
0x18000ba09  call    cs:__imp_SelectObject
0x18000ba0f  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ba16  call    cs:__imp_ReleaseSRWLockShared
0x18000ba1c  mov     eax, [rsp+68h+rc.right]
0x18000ba20  mov     r8d, cs:?g_cxIcon@@3HA; int g_cxIcon
0x18000ba27  inc     eax
0x18000ba29  mov     r9d, [rsp+68h+rc.bottom]
0x18000ba2e  cmp     eax, r8d
0x18000ba31  mov     [rsp+68h+rc.right], eax
0x18000ba35  cmovg   r8d, eax
0x18000ba39  mov     eax, cs:?g_cyIcon@@3HA; int g_cyIcon
0x18000ba3f  inc     eax
0x18000ba41  xor     ecx, ecx; hWnd
0x18000ba43  add     r9d, eax
0x18000ba46  mov     eax, r8d
0x18000ba49  cdq
0x18000ba4a  and     edx, 3
0x18000ba4d  add     eax, edx
0x18000ba4f  sar     eax, 2
0x18000ba52  add     eax, r8d
0x18000ba55  mov     [rbp+8], eax
0x18000ba58  mov     eax, r9d
0x18000ba5b  cdq
0x18000ba5c  and     edx, 7
0x18000ba5f  add     eax, edx
0x18000ba61  mov     rdx, rbx; hDC
0x18000ba64  sar     eax, 3
0x18000ba67  add     eax, r9d
0x18000ba6a  mov     [rbp+0Ch], eax
0x18000ba6d  call    cs:__imp_ReleaseDC
0x18000ba73  mov     eax, 1
0x18000ba78  mov     rcx, [rsp+68h+var_28]
0x18000ba7d  xor     rcx, rsp; StackCookie
0x18000ba80  call    __security_check_cookie
0x18000ba85  lea     r11, [rsp+68h+var_18]
0x18000ba8a  mov     rbx, [r11+20h]
0x18000ba8e  mov     rbp, [r11+38h]
0x18000ba92  mov     rsp, r11
0x18000ba95  pop     r14
0x18000ba97  pop     rdi
0x18000ba98  pop     rsi
0x18000ba99  retn
```

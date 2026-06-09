# MCCreateHandler

- ea: `0x180042bec`
- end: `0x180042dae`
- name: `MCCreateHandler`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180046d90`

## callees

- `0x1800115f0`
- `0x1800184b8`
- `0x180042bec`
- `0x180043fe4`
- `0x1800441b4`
- `0x180046298`
- `0x1800468c8`
- `0x180049c98`

## import_xrefs

- `GDI32!GetStockObject` at `0x180042d0e`
- `GDI32!GetStockObject` at `0x180042d0e`
- `GDI32!CreatePen` at `0x180042c65`
- `GDI32!CreatePen` at `0x180042c65`
- `KERNEL32!GetLocalTime` at `0x180042ca2`
- `KERNEL32!GetLocalTime` at `0x180042ca2`
- `USER32!SendMessageW` at `0x180042cfe`
- `USER32!SendMessageW` at `0x180042cfe`
- `USER32!SetTimer` at `0x180042d7e`
- `USER32!SetTimer` at `0x180042d7e`

## pseudocode

```c
__int64 __fastcall MCCreateHandler(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v7; // rax
  __int128 v8; // xmm0
  HWND v9; // rcx
  void *StockObject; // rax
  int v11; // ecx
  int v12; // eax
  __int128 v13; // [rsp+20h] [rbp-38h] BYREF

  v3 = (*(_DWORD *)(a3 + 48) & 0xFE00) == 0;
  v13 = 0;
  if ( !v3 )
    return -1;
  CIInitialize(a1, a2, a3);
  UpdateLocaleInfo(a1, a1 + 56);
  v7 = *(_QWORD *)(a3 + 8);
  *(_DWORD *)(a1 + 2392) &= ~2u;
  *(_QWORD *)(a1 + 1632) = v7;
  *(_DWORD *)(a1 + 2392) |= ~(*(_DWORD *)(a1 + 16) >> 26) & 2;
  *(_QWORD *)(a1 + 1664) = CreatePen(0, 2, 0xFFu);
  MCReloadMenus(a1);
  *(_OWORD *)(a1 + 1768) = c_stEpoch;
  *(_OWORD *)(a1 + 1784) = c_stArmageddon;
  GetLocalTime((LPSYSTEMTIME)(a1 + 1804));
  v3 = (*(_BYTE *)(a1 + 16) & 2) == 0;
  v8 = *(_OWORD *)(a1 + 1804);
  *(_OWORD *)(a1 + 1820) = v8;
  if ( !v3 )
    *(_OWORD *)(a1 + 1836) = v8;
  *(_OWORD *)(a1 + 1932) = v8;
  *(_DWORD *)(a1 + 1800) = 7;
  *(_OWORD *)(a1 + 1948) = v8;
  *(_OWORD *)(a1 + 1900) = v8;
  *(_OWORD *)(a1 + 1916) = v8;
  v9 = *(HWND *)(a3 + 24);
  if ( !v9 || (StockObject = (void *)SendMessageW(v9, 0x31u, 0, 0)) == 0 )
    StockObject = GetStockObject(17);
  MCHandleSetFont(a1, StockObject, 0);
  v11 = *(unsigned __int16 *)(a1 + 1822);
  LOWORD(v13) = *(_WORD *)(a1 + 1820);
  WORD3(v13) = *(_WORD *)(a1 + 1826);
  v12 = *(_DWORD *)(a1 + 1984) * *(_DWORD *)(a1 + 1988);
  WORD1(v13) = v11;
  if ( v11 <= v12 )
    WORD1(v13) = 1;
  MCUpdateStartEndDates(a1, &v13);
  *(_QWORD *)(a1 + 1976) = SetTimer(*(HWND *)a1, 2u, 0x1D4C0u, 0);
  MCInitColorArray(a1 + 1688);
  return 0;
}

```

## disassembly

```asm
0x180042bec  push    rbx
0x180042bee  push    rsi
0x180042bef  push    rdi
0x180042bf0  sub     rsp, 40h
0x180042bf4  mov     rax, cs:__security_cookie
0x180042bfb  xor     rax, rsp
0x180042bfe  mov     [rsp+58h+var_28], rax
0x180042c03  test    dword ptr [r8+30h], 0FE00h
0x180042c0b  xorps   xmm0, xmm0
0x180042c0e  movups  [rsp+58h+var_38], xmm0
0x180042c13  mov     rsi, r8
0x180042c16  mov     rbx, rcx
0x180042c19  jz      short loc_180042C24
0x180042c1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042c1f  jmp     loc_180042D99
0x180042c24  call    CIInitialize
0x180042c29  lea     rdx, [rbx+38h]
0x180042c2d  mov     rcx, rbx
0x180042c30  call    UpdateLocaleInfo
0x180042c35  mov     rax, [rsi+8]
0x180042c39  mov     edx, 2; cWidth
0x180042c3e  and     dword ptr [rbx+958h], 0FFFFFFFDh
0x180042c45  xor     ecx, ecx; iStyle
0x180042c47  mov     [rbx+660h], rax
0x180042c4e  mov     r8d, 0FFh; color
0x180042c54  mov     eax, [rbx+10h]
0x180042c57  shr     eax, 1Ah
0x180042c5a  not     eax
0x180042c5c  and     eax, 2
0x180042c5f  or      [rbx+958h], eax
0x180042c65  call    cs:__imp_CreatePen
0x180042c6b  mov     rcx, rbx
0x180042c6e  mov     [rbx+680h], rax
0x180042c75  call    MCReloadMenus
0x180042c7a  movups  xmm0, cs:c_stEpoch
0x180042c81  lea     rdi, [rbx+70Ch]
0x180042c88  mov     rcx, rdi; lpSystemTime
0x180042c8b  movdqu  xmmword ptr [rbx+6E8h], xmm0
0x180042c93  movups  xmm1, cs:c_stArmageddon
0x180042c9a  movdqu  xmmword ptr [rbx+6F8h], xmm1
0x180042ca2  call    cs:__imp_GetLocalTime
0x180042ca8  test    byte ptr [rbx+10h], 2
0x180042cac  movups  xmm0, xmmword ptr [rdi]
0x180042caf  movdqu  xmmword ptr [rbx+71Ch], xmm0
0x180042cb7  jz      short loc_180042CC1
0x180042cb9  movdqu  xmmword ptr [rbx+72Ch], xmm0
0x180042cc1  movdqu  xmmword ptr [rbx+78Ch], xmm0
0x180042cc9  mov     dword ptr [rbx+708h], 7
0x180042cd3  movdqu  xmmword ptr [rbx+79Ch], xmm0
0x180042cdb  movdqu  xmmword ptr [rbx+76Ch], xmm0
0x180042ce3  movdqu  xmmword ptr [rbx+77Ch], xmm0
0x180042ceb  mov     rcx, [rsi+18h]; hWnd
0x180042cef  test    rcx, rcx
0x180042cf2  jz      short loc_180042D09
0x180042cf4  xor     r9d, r9d; lParam
0x180042cf7  xor     r8d, r8d; wParam
0x180042cfa  lea     edx, [r9+31h]; Msg
0x180042cfe  call    cs:__imp_SendMessageW
0x180042d04  test    rax, rax
0x180042d07  jnz     short loc_180042D14
0x180042d09  mov     ecx, 11h; i
0x180042d0e  call    cs:__imp_GetStockObject
0x180042d14  xor     r8d, r8d
0x180042d17  mov     rdx, rax
0x180042d1a  mov     rcx, rbx
0x180042d1d  call    MCHandleSetFont
0x180042d22  movzx   eax, word ptr [rbx+71Ch]
0x180042d29  movzx   ecx, word ptr [rbx+71Eh]
0x180042d30  mov     word ptr [rsp+58h+var_38], ax
0x180042d35  movzx   eax, word ptr [rbx+722h]
0x180042d3c  mov     word ptr [rsp+58h+var_38+6], ax
0x180042d41  mov     eax, [rbx+7C4h]
0x180042d47  imul    eax, [rbx+7C0h]
0x180042d4e  mov     word ptr [rsp+58h+var_38+2], cx
0x180042d53  cmp     ecx, eax
0x180042d55  jg      short loc_180042D61
0x180042d57  mov     eax, 1
0x180042d5c  mov     word ptr [rsp+58h+var_38+2], ax
0x180042d61  lea     rdx, [rsp+58h+var_38]
0x180042d66  mov     rcx, rbx
0x180042d69  call    MCUpdateStartEndDates
0x180042d6e  mov     rcx, [rbx]; hWnd
0x180042d71  xor     r9d, r9d; lpTimerFunc
0x180042d74  mov     r8d, 1D4C0h; uElapse
0x180042d7a  lea     edx, [r9+2]; nIDEvent
0x180042d7e  call    cs:__imp_SetTimer
0x180042d84  lea     rcx, [rbx+698h]
0x180042d8b  mov     [rbx+7B8h], rax
0x180042d92  call    MCInitColorArray
0x180042d97  xor     eax, eax
0x180042d99  mov     rcx, [rsp+58h+var_28]
0x180042d9e  xor     rcx, rsp; StackCookie
0x180042da1  call    __security_check_cookie
0x180042da6  add     rsp, 40h
0x180042daa  pop     rdi
0x180042dab  pop     rsi
0x180042dac  pop     rbx
0x180042dad  retn
```

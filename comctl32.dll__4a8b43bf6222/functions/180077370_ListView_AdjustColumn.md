# ListView_AdjustColumn

- ea: `0x180077370`
- end: `0x180077568`
- name: `ListView_AdjustColumn`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18007793c`

## callees

- `0x1800115f0`
- `0x18001a5e0`
- `0x18005bde8`
- `0x180077370`

## import_xrefs

- `USER32!SendMessageW` at `0x1800773cb`
- `USER32!SendMessageW` at `0x1800773cb`
- `USER32!RedrawWindow` at `0x18007753e`
- `USER32!RedrawWindow` at `0x18007753e`
- `USER32!InvalidateRect` at `0x1800774af`
- `USER32!InvalidateRect` at `0x1800774af`
- `USER32!UpdateWindow` at `0x18007750b`
- `USER32!UpdateWindow` at `0x18007750b`
- `USER32!OffsetRect` at `0x1800774de`
- `USER32!OffsetRect` at `0x180077502`
- `USER32!OffsetRect` at `0x1800774de`
- `USER32!OffsetRect` at `0x180077502`
- `USER32!GetWindowRect` at `0x1800773e9`
- `USER32!GetWindowRect` at `0x1800773e9`

## pseudocode

```c
void __fastcall ListView_AdjustColumn(__int64 a1, int a2)
{
  int v2; // r14d
  int v5; // eax
  int v6; // edi
  int v7; // ecx
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // edx
  UINT v12; // r9d
  _QWORD v13[2]; // [rsp+20h] [rbp-29h] BYREF
  int v14; // [rsp+30h] [rbp-19h]
  int v15; // [rsp+34h] [rbp-15h]
  __int64 v16; // [rsp+38h] [rbp-11h]
  LPARAM *v17; // [rsp+40h] [rbp-9h]
  __int64 v18; // [rsp+48h] [rbp-1h]
  __int64 v19; // [rsp+50h] [rbp+7h]
  int v20; // [rsp+58h] [rbp+Fh]
  __int128 v21; // [rsp+5Ch] [rbp+13h]
  int v22; // [rsp+6Ch] [rbp+23h]
  LPARAM lParam[2]; // [rsp+70h] [rbp+27h] BYREF

  v2 = *(_DWORD *)(a1 + 468);
  *(_OWORD *)lParam = 0;
  if ( a2 != v2 )
  {
    v5 = SendMessageW(*(HWND *)(a1 + 440), 0x1207u, *(int *)(a1 + 464), (LPARAM)lParam);
    v6 = (v5 != 0 ? LODWORD(lParam[0]) : 0) - *(_DWORD *)(a1 + 456);
    GetWindowRect(*(HWND *)(a1 + 440), (LPRECT)lParam);
    HIDWORD(lParam[0]) = HIDWORD(lParam[1]) - HIDWORD(lParam[0]);
    lParam[1] = *(_QWORD *)(a1 + 164);
    LODWORD(lParam[0]) = v6;
    if ( *(_QWORD *)(a1 + 560) || *(_DWORD *)(a1 + 96) == -1 || *(_DWORD *)(a1 + 108) == -1 )
    {
      *(_DWORD *)(a1 + 452) = 0x7FFFFFFF;
      ListView_UpdateScrollBars(a1);
      v12 = 261;
      LODWORD(lParam[0]) = v6;
    }
    else
    {
      v13[1] = *(_QWORD *)a1;
      v15 = 0;
      v14 = a2 - v2;
      v22 = 0;
      v16 = 0;
      v18 = 0;
      v19 = 0;
      v7 = a2;
      v17 = lParam;
      v8 = *(_DWORD *)(a1 + 468);
      v13[0] = 80;
      if ( v8 < a2 )
        v7 = v8;
      v20 = 6;
      v21 = 0;
      LODWORD(lParam[0]) = v6 + v7;
      SmoothScrollWindow((__int64)v13);
      if ( a2 < *(_DWORD *)(a1 + 468) )
      {
        LODWORD(lParam[1]) = g_cxEdge + LODWORD(lParam[0]);
        InvalidateRect(*(HWND *)a1, (const RECT *)lParam, 1);
      }
      v9 = *(_DWORD *)(a1 + 460);
      v10 = v6 + a2;
      v11 = *(_DWORD *)(a1 + 456);
      *(_DWORD *)(a1 + 452) = 0x7FFFFFFF;
      LODWORD(lParam[0]) = v6;
      if ( v6 > v6 + a2 )
        v10 = v6;
      LODWORD(lParam[1]) = v10;
      OffsetRect((LPRECT)lParam, v11, v9);
      ListView_UpdateScrollBars(a1);
      OffsetRect((LPRECT)lParam, -*(_DWORD *)(a1 + 456), -*(_DWORD *)(a1 + 460));
      UpdateWindow(*(HWND *)a1);
      v12 = 257;
    }
    RedrawWindow(*(HWND *)a1, (const RECT *)lParam, 0, v12);
  }
}

```

## disassembly

```asm
0x180077370  mov     [rsp-8+arg_10], rbx
0x180077375  mov     [rsp-8+arg_18], rsi
0x18007737a  push    rbp
0x18007737b  push    rdi
0x18007737c  push    r14
0x18007737e  lea     rbp, [rsp-47h]
0x180077383  sub     rsp, 90h
0x18007738a  mov     rax, cs:__security_cookie
0x180077391  xor     rax, rsp
0x180077394  mov     [rbp+57h+var_20], rax
0x180077398  mov     r14d, [rcx+1D4h]
0x18007739f  xorps   xmm0, xmm0
0x1800773a2  mov     esi, edx
0x1800773a4  mov     rbx, rcx
0x1800773a7  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x1800773ab  cmp     edx, r14d
0x1800773ae  jz      loc_180077544
0x1800773b4  movsxd  r8, dword ptr [rcx+1D0h]; wParam
0x1800773bb  lea     r9, [rbp+57h+lParam]; lParam
0x1800773bf  mov     rcx, [rcx+1B8h]; hWnd
0x1800773c6  mov     edx, 1207h; Msg
0x1800773cb  call    cs:__imp_SendMessageW
0x1800773d1  mov     rcx, [rbx+1B8h]; hWnd
0x1800773d8  lea     rdx, [rbp+57h+lParam]; lpRect
0x1800773dc  neg     eax
0x1800773de  sbb     edi, edi
0x1800773e0  and     edi, dword ptr [rbp+57h+lParam]
0x1800773e3  sub     edi, [rbx+1C8h]
0x1800773e9  call    cs:__imp_GetWindowRect
0x1800773ef  mov     eax, dword ptr [rbp+57h+lParam+0Ch]
0x1800773f2  xor     ecx, ecx
0x1800773f4  sub     eax, dword ptr [rbp+57h+lParam+4]
0x1800773f7  mov     dword ptr [rbp+57h+lParam+4], eax
0x1800773fa  mov     eax, [rbx+0A4h]
0x180077400  mov     dword ptr [rbp+57h+lParam+8], eax
0x180077403  mov     eax, [rbx+0A8h]
0x180077409  mov     dword ptr [rbp+57h+lParam+0Ch], eax
0x18007740c  mov     dword ptr [rbp+57h+lParam], edi
0x18007740f  cmp     [rbx+230h], rcx
0x180077416  jnz     loc_180077519
0x18007741c  or      eax, 0FFFFFFFFh
0x18007741f  cmp     [rbx+60h], eax
0x180077422  jz      loc_180077519
0x180077428  cmp     [rbx+6Ch], eax
0x18007742b  jz      loc_180077519
0x180077431  mov     rax, [rbx]
0x180077434  xorps   xmm0, xmm0
0x180077437  mov     [rbp+57h+var_78], rax
0x18007743b  mov     eax, esi
0x18007743d  sub     eax, r14d
0x180077440  mov     [rbp+57h+var_6C], ecx
0x180077443  mov     [rbp+57h+var_70], eax
0x180077446  xor     eax, eax
0x180077448  mov     [rbp+57h+var_34], eax
0x18007744b  lea     rax, [rbp+57h+lParam]
0x18007744f  mov     [rbp+57h+var_68], rcx
0x180077453  mov     [rbp+57h+var_58], rcx
0x180077457  mov     [rbp+57h+var_50], rcx
0x18007745b  mov     ecx, esi
0x18007745d  mov     [rbp+57h+var_60], rax
0x180077461  mov     eax, [rbx+1D4h]
0x180077467  cmp     eax, esi
0x180077469  mov     [rbp+57h+var_80], 50h ; 'P'
0x180077471  cmovl   ecx, eax
0x180077474  mov     [rbp+57h+var_48], 6
0x18007747b  movups  [rbp+57h+var_44], xmm0
0x18007747f  lea     eax, [rdi+rcx]
0x180077482  lea     rcx, [rbp+57h+var_80]
0x180077486  mov     dword ptr [rbp+57h+lParam], eax
0x180077489  call    SmoothScrollWindow
0x18007748e  cmp     esi, [rbx+1D4h]
0x180077494  jge     short loc_1800774B5
0x180077496  mov     ecx, dword ptr [rbp+57h+lParam]
0x180077499  lea     rdx, [rbp+57h+lParam]; lpRect
0x18007749d  add     ecx, cs:g_cxEdge
0x1800774a3  mov     r8d, 1; bErase
0x1800774a9  mov     dword ptr [rbp+57h+lParam+8], ecx
0x1800774ac  mov     rcx, [rbx]; hWnd
0x1800774af  call    cs:__imp_InvalidateRect
0x1800774b5  mov     r8d, [rbx+1CCh]; dy
0x1800774bc  lea     eax, [rdi+rsi]
0x1800774bf  mov     edx, [rbx+1C8h]; dx
0x1800774c5  lea     rcx, [rbp+57h+lParam]; lprc
0x1800774c9  cmp     edi, eax
0x1800774cb  mov     dword ptr [rbx+1C4h], 7FFFFFFFh
0x1800774d5  mov     dword ptr [rbp+57h+lParam], edi
0x1800774d8  cmovg   eax, edi
0x1800774db  mov     dword ptr [rbp+57h+lParam+8], eax
0x1800774de  call    cs:__imp_OffsetRect
0x1800774e4  mov     rcx, rbx
0x1800774e7  call    ListView_UpdateScrollBars
0x1800774ec  mov     r8d, [rbx+1CCh]
0x1800774f3  lea     rcx, [rbp+57h+lParam]; lprc
0x1800774f7  mov     edx, [rbx+1C8h]
0x1800774fd  neg     r8d; dy
0x180077500  neg     edx; dx
0x180077502  call    cs:__imp_OffsetRect
0x180077508  mov     rcx, [rbx]; hWnd
0x18007750b  call    cs:__imp_UpdateWindow
0x180077511  mov     r9d, 101h
0x180077517  jmp     short loc_180077534
0x180077519  mov     rcx, rbx
0x18007751c  mov     dword ptr [rbx+1C4h], 7FFFFFFFh
0x180077526  call    ListView_UpdateScrollBars
0x18007752b  mov     r9d, 105h; flags
0x180077531  mov     dword ptr [rbp+57h+lParam], edi
0x180077534  mov     rcx, [rbx]; hWnd
0x180077537  lea     rdx, [rbp+57h+lParam]; lprcUpdate
0x18007753b  xor     r8d, r8d; hrgnUpdate
0x18007753e  call    cs:__imp_RedrawWindow
0x180077544  mov     rcx, [rbp+57h+var_20]
0x180077548  xor     rcx, rsp; StackCookie
0x18007754b  call    __security_check_cookie
0x180077550  lea     r11, [rsp+0A0h+var_10]
0x180077558  mov     rbx, [r11+30h]
0x18007755c  mov     rsi, [r11+38h]
0x180077560  mov     rsp, r11
0x180077563  pop     r14
0x180077565  pop     rdi
0x180077566  pop     rbp
0x180077567  retn
```

# Tab_OnLButtonDown

- ea: `0x180065944`
- end: `0x180065a70`
- name: `Tab_OnLButtonDown`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180066d40`

## callees

- `0x180063400`
- `0x180064868`
- `0x180065180`
- `0x180065390`
- `0x180065944`
- `0x180065d00`

## import_xrefs

- `USER32!SetCapture` at `0x180065a14`
- `USER32!SetCapture` at `0x180065a14`
- `USER32!SetFocus` at `0x1800659fb`
- `USER32!SetFocus` at `0x180065a51`
- `USER32!SetFocus` at `0x1800659fb`
- `USER32!SetFocus` at `0x180065a51`
- `USER32!UpdateWindow` at `0x180065a5a`
- `USER32!UpdateWindow` at `0x180065a5a`
- `USER32!GetAsyncKeyState` at `0x180065989`
- `USER32!GetAsyncKeyState` at `0x180065989`

## pseudocode

```c
void __fastcall Tab_OnLButtonDown(__int64 a1, __int64 a2, __int64 a3)
{
  bool v4; // cc
  int v5; // esi
  unsigned int v6; // edi
  HWND v7; // rcx
  _OWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  if ( *(char *)(a1 + 16) >= 0 )
    v4 = (int)a2 <= *(_DWORD *)(a1 + 116);
  else
    v4 = (int)a3 <= *(_DWORD *)(a1 + 116);
  if ( v4 )
  {
    v5 = -1;
    v6 = Tab_OnHitTest(a1, a2, a3, 0);
    if ( v6 != -1 )
    {
      if ( (*(_BYTE *)(a1 + 16) & 4) != 0 && GetAsyncKeyState(17) < 0 && (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
      {
        memset(v8, 0, sizeof(v8));
        LODWORD(v8[0]) = 16;
        DWORD2(v8[0]) = 1;
        v9 = 0;
        Tab_OnGetItem(a1, v6, v8);
        DWORD1(v8[0]) ^= 1u;
        Tab_OnSetItem(a1, v6, v8);
      }
      else
      {
        v5 = *(_DWORD *)(a1 + 96);
        if ( (*(_DWORD *)(a1 + 16) & 0x9000) == 0x1000 )
          SetFocus(*(HWND *)a1);
        if ( (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
        {
          v7 = *(HWND *)a1;
          *(_DWORD *)(a1 + 72) |= 6u;
          *(_DWORD *)(a1 + 100) = v6;
          SetCapture(v7);
          Tab_InvalidateItem(a1, v6, *(_DWORD *)(a1 + 16) & 8);
        }
        else
        {
          v5 = ChangeSel((_QWORD *)a1, v6, 1, 0);
        }
      }
    }
    if ( (*(_DWORD *)(a1 + 16) & 0x8000) == 0 && v5 == v6 )
    {
      SetFocus(*(HWND *)a1);
      UpdateWindow(*(HWND *)a1);
    }
  }
}

```

## disassembly

```asm
0x180065944  mov     [rsp+arg_0], rbx
0x180065949  mov     [rsp+arg_8], rsi
0x18006594e  push    rdi
0x18006594f  sub     rsp, 50h
0x180065953  test    byte ptr [rcx+10h], 80h
0x180065957  mov     rbx, rcx
0x18006595a  jz      short loc_180065962
0x18006595c  cmp     r8d, [rcx+74h]
0x180065960  jmp     short loc_180065965
0x180065962  cmp     edx, [rcx+74h]
0x180065965  jg      loc_180065A60
0x18006596b  xor     r9d, r9d
0x18006596e  or      esi, 0FFFFFFFFh
0x180065971  call    Tab_OnHitTest
0x180065976  mov     edi, eax
0x180065978  cmp     eax, esi
0x18006597a  jz      loc_180065A41
0x180065980  test    byte ptr [rbx+10h], 4
0x180065984  jz      short loc_1800659E6
0x180065986  lea     ecx, [rsi+12h]; vKey
0x180065989  call    cs:__imp_GetAsyncKeyState
0x18006598f  test    ax, ax
0x180065992  jns     short loc_1800659E6
0x180065994  test    dword ptr [rbx+10h], 100h
0x18006599b  jz      short loc_1800659E6
0x18006599d  xorps   xmm0, xmm0
0x1800659a0  lea     r8, [rsp+58h+var_38]
0x1800659a5  movups  [rsp+58h+var_38], xmm0
0x1800659aa  xor     eax, eax
0x1800659ac  mov     dword ptr [rsp+58h+var_38], 10h
0x1800659b4  mov     edx, edi
0x1800659b6  mov     dword ptr [rsp+58h+var_38+8], 1
0x1800659be  mov     rcx, rbx
0x1800659c1  mov     [rsp+58h+var_18], rax
0x1800659c6  movups  [rsp+58h+var_28], xmm0
0x1800659cb  call    Tab_OnGetItem
0x1800659d0  xor     dword ptr [rsp+58h+var_38+4], 1
0x1800659d5  lea     r8, [rsp+58h+var_38]
0x1800659da  mov     edx, edi
0x1800659dc  mov     rcx, rbx
0x1800659df  call    Tab_OnSetItem
0x1800659e4  jmp     short loc_180065A41
0x1800659e6  mov     eax, [rbx+10h]
0x1800659e9  mov     esi, [rbx+60h]
0x1800659ec  and     eax, 9000h
0x1800659f1  cmp     eax, 1000h
0x1800659f6  jnz     short loc_180065A01
0x1800659f8  mov     rcx, [rbx]; hWnd
0x1800659fb  call    cs:__imp_SetFocus
0x180065a01  test    dword ptr [rbx+10h], 100h
0x180065a08  jz      short loc_180065A2E
0x180065a0a  mov     rcx, [rbx]; hWnd
0x180065a0d  or      dword ptr [rbx+48h], 6
0x180065a11  mov     [rbx+64h], edi
0x180065a14  call    cs:__imp_SetCapture
0x180065a1a  mov     r8d, [rbx+10h]
0x180065a1e  mov     edx, edi
0x180065a20  and     r8d, 8
0x180065a24  mov     rcx, rbx
0x180065a27  call    Tab_InvalidateItem
0x180065a2c  jmp     short loc_180065A41
0x180065a2e  xor     r9d, r9d
0x180065a31  mov     edx, edi
0x180065a33  mov     rcx, rbx
0x180065a36  lea     r8d, [r9+1]
0x180065a3a  call    ChangeSel
0x180065a3f  mov     esi, eax
0x180065a41  test    dword ptr [rbx+10h], 8000h
0x180065a48  jnz     short loc_180065A60
0x180065a4a  cmp     esi, edi
0x180065a4c  jnz     short loc_180065A60
0x180065a4e  mov     rcx, [rbx]; hWnd
0x180065a51  call    cs:__imp_SetFocus
0x180065a57  mov     rcx, [rbx]; hWnd
0x180065a5a  call    cs:__imp_UpdateWindow
0x180065a60  mov     rbx, [rsp+58h+arg_0]
0x180065a65  mov     rsi, [rsp+58h+arg_8]
0x180065a6a  add     rsp, 50h
0x180065a6e  pop     rdi
0x180065a6f  retn
```

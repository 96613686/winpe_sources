# GetFileNamePreviewHook

- ea: `0x18000ed20`
- end: `0x18000ef91`
- name: `GetFileNamePreviewHook`
- size: `625`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800014b0`
- `0x18000ed20`
- `0x18000f0b8`
- `0x18000f25c`
- `0x18000f388`
- `0x180017010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000ef4a`
- `GDI32!DeleteObject` at `0x18000ef4a`
- `USER32!SendMessageW` at `0x18000edbb`
- `USER32!SendMessageW` at `0x18000ef67`
- `USER32!SendMessageW` at `0x18000edbb`
- `USER32!SendMessageW` at `0x18000ef67`
- `USER32!KillTimer` at `0x18000edd9`
- `USER32!KillTimer` at `0x18000ee7e`
- `USER32!KillTimer` at `0x18000eeab`
- `USER32!KillTimer` at `0x18000edd9`
- `USER32!KillTimer` at `0x18000ee7e`
- `USER32!KillTimer` at `0x18000eeab`
- `USER32!SendDlgItemMessageW` at `0x18000edfe`
- `USER32!SendDlgItemMessageW` at `0x18000ee1c`
- `USER32!SendDlgItemMessageW` at `0x18000edfe`
- `USER32!SendDlgItemMessageW` at `0x18000ee1c`
- `USER32!SetTimer` at `0x18000eebf`
- `USER32!SetTimer` at `0x18000eebf`
- `USER32!RemovePropW` at `0x18000ef3b`
- `USER32!RemovePropW` at `0x18000ef3b`
- `USER32!GetPropW` at `0x18000ed55`
- `USER32!GetPropW` at `0x18000eedc`
- `USER32!GetPropW` at `0x18000ed55`
- `USER32!GetPropW` at `0x18000eedc`

## pseudocode

```c
__int64 __fastcall GetFileNamePreviewHook(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  HWND *PropW; // rbx
  HWND v9; // rcx
  int v10; // eax
  HWND v12; // rcx
  HWND v13; // rcx
  _WORD v14[80]; // [rsp+30h] [rbp-E8h] BYREF

  PropW = (HWND *)GetPropW(hWnd, L"PreviewStuff");
  if ( Msg != 2 )
  {
    switch ( Msg )
    {
      case 0xFu:
        PreviewPaint(PropW);
        goto LABEL_26;
      case 0x110u:
        PreviewOpen(hWnd, lParam);
        PropW = (HWND *)GetPropW(hWnd, L"PreviewStuff");
        if ( ((_BYTE)PropW[4] & 0x20) != 0 )
          goto LABEL_26;
        break;
      case 0x111u:
        if ( (unsigned __int16)wParam != 1 && (unsigned __int16)wParam != 2 )
        {
          if ( (unsigned __int16)wParam == 1120 )
          {
            if ( WORD1(wParam) == 1 )
            {
              KillTimer(hWnd, 0x4D2u);
              SetTimer(hWnd, 0x4D2u, 0x3E8u, 0);
            }
            goto LABEL_26;
          }
          if ( (unsigned __int16)wParam != 1121 && (unsigned int)(unsigned __int16)wParam - 1136 > 1
            || WORD1(wParam) != 1 )
          {
            goto LABEL_26;
          }
        }
        KillTimer(hWnd, 0x4D2u);
        PreviewFile(PropW, 0);
        goto LABEL_26;
      case 0x113u:
        if ( wParam != 1234 )
          goto LABEL_26;
        KillTimer(hWnd, 0x4D2u);
        v14[0] = 0;
        v10 = SendDlgItemMessageW(hWnd, 1120, 0x188u, 0, 0);
        SendDlgItemMessageW(hWnd, 1120, 0x189u, v10, (LPARAM)v14);
        PreviewFile(PropW, v14);
        break;
      case 0x30Fu:
      case 0x311u:
        if ( PropW )
        {
          v9 = PropW[12];
          if ( v9 )
            SendMessageW(v9, Msg, wParam, lParam);
          goto LABEL_33;
        }
        return 0;
      default:
LABEL_26:
        if ( PropW )
          goto LABEL_33;
        return 0;
    }
    return 1;
  }
  if ( !PropW )
    return 0;
  PreviewFile(PropW, 0);
  RemovePropW(PropW[1], L"PreviewStuff");
  v12 = PropW[13];
  if ( v12 )
  {
    DeleteObject(v12);
    PropW[13] = 0;
  }
  v13 = PropW[12];
  if ( v13 )
  {
    SendMessageW(v13, 0x10u, 0, 0);
    PropW[12] = 0;
  }
LABEL_33:
  if ( ((_BYTE)PropW[4] & 0x20) == 0 )
    return 0;
  return ((__int64 (__fastcall *)(HWND, _QWORD, WPARAM, LPARAM))PropW[5])(hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x18000ed20  push    rbx
0x18000ed22  push    rbp
0x18000ed23  push    rsi
0x18000ed24  push    rdi
0x18000ed25  push    r14
0x18000ed27  push    r15
0x18000ed29  sub     rsp, 0E8h
0x18000ed30  mov     rax, cs:__security_cookie
0x18000ed37  xor     rax, rsp
0x18000ed3a  mov     [rsp+118h+var_48], rax
0x18000ed42  mov     r15d, edx
0x18000ed45  mov     r14, r9
0x18000ed48  lea     rdx, aPreviewstuff; "PreviewStuff"
0x18000ed4f  mov     rbp, r8
0x18000ed52  mov     rsi, rcx
0x18000ed55  call    cs:__imp_GetPropW
0x18000ed5b  mov     rbx, rax
0x18000ed5e  mov     eax, r15d
0x18000ed61  sub     eax, 2
0x18000ed64  jz      loc_18000EF1F
0x18000ed6a  sub     eax, 0Dh
0x18000ed6d  jz      loc_18000EEF0
0x18000ed73  sub     eax, 101h
0x18000ed78  jz      loc_18000EEC7
0x18000ed7e  sub     eax, 1
0x18000ed81  jz      loc_18000EE39
0x18000ed87  sub     eax, 2
0x18000ed8a  jz      short loc_18000EDC6
0x18000ed8c  sub     eax, 1FCh
0x18000ed91  jz      short loc_18000ED9C
0x18000ed93  cmp     eax, 2
0x18000ed96  jnz     loc_18000EEF8
0x18000ed9c  test    rbx, rbx
0x18000ed9f  jz      loc_18000EEFD
0x18000eda5  mov     rcx, [rbx+60h]; hWnd
0x18000eda9  test    rcx, rcx
0x18000edac  jz      loc_18000EF71
0x18000edb2  mov     r9, r14; lParam
0x18000edb5  mov     r8, rbp; wParam
0x18000edb8  mov     edx, r15d; Msg
0x18000edbb  call    cs:__imp_SendMessageW
0x18000edc1  jmp     loc_18000EF71
0x18000edc6  mov     edi, 4D2h
0x18000edcb  cmp     rbp, rdi
0x18000edce  jnz     loc_18000EEF8
0x18000edd4  mov     edx, edi; uIDEvent
0x18000edd6  mov     rcx, rsi; hWnd
0x18000edd9  call    cs:__imp_KillTimer
0x18000eddf  xor     edi, edi
0x18000ede1  xor     r9d, r9d; wParam
0x18000ede4  mov     [rsp+118h+var_E8], di
0x18000ede9  mov     r8d, 188h; Msg
0x18000edef  mov     [rsp+118h+lParam], rdi; lParam
0x18000edf4  mov     rcx, rsi; hDlg
0x18000edf7  mov     edi, 460h
0x18000edfc  mov     edx, edi; nIDDlgItem
0x18000edfe  call    cs:__imp_SendDlgItemMessageW
0x18000ee04  movsxd  r9, eax; wParam
0x18000ee07  mov     r8d, 189h; Msg
0x18000ee0d  lea     rax, [rsp+118h+var_E8]
0x18000ee12  mov     edx, edi; nIDDlgItem
0x18000ee14  mov     rcx, rsi; hDlg
0x18000ee17  mov     [rsp+118h+lParam], rax; lParam
0x18000ee1c  call    cs:__imp_SendDlgItemMessageW
0x18000ee22  lea     rdx, [rsp+118h+var_E8]
0x18000ee27  mov     rcx, rbx
0x18000ee2a  call    PreviewFile
0x18000ee2f  mov     eax, 1
0x18000ee34  jmp     loc_18000EEFF
0x18000ee39  movzx   ecx, bp
0x18000ee3c  sub     ecx, 1
0x18000ee3f  jz      short loc_18000EE76
0x18000ee41  sub     ecx, 1
0x18000ee44  jz      short loc_18000EE76
0x18000ee46  sub     ecx, 45Eh
0x18000ee4c  jz      short loc_18000EE90
0x18000ee4e  sub     ecx, 1
0x18000ee51  jz      short loc_18000EE61
0x18000ee53  sub     ecx, 0Fh
0x18000ee56  jz      short loc_18000EE61
0x18000ee58  cmp     ecx, 1
0x18000ee5b  jnz     loc_18000EEF8
0x18000ee61  mov     rax, rbp
0x18000ee64  mov     ecx, 1
0x18000ee69  shr     rax, 10h
0x18000ee6d  cmp     ax, cx
0x18000ee70  jnz     loc_18000EEF8
0x18000ee76  mov     edx, 4D2h; uIDEvent
0x18000ee7b  mov     rcx, rsi; hWnd
0x18000ee7e  call    cs:__imp_KillTimer
0x18000ee84  xor     edx, edx
0x18000ee86  mov     rcx, rbx
0x18000ee89  call    PreviewFile
0x18000ee8e  jmp     short loc_18000EEF8
0x18000ee90  mov     rax, rbp
0x18000ee93  mov     ecx, 1
0x18000ee98  shr     rax, 10h
0x18000ee9c  cmp     ax, cx
0x18000ee9f  jnz     short loc_18000EEF8
0x18000eea1  mov     edi, 4D2h
0x18000eea6  mov     rcx, rsi; hWnd
0x18000eea9  mov     edx, edi; uIDEvent
0x18000eeab  call    cs:__imp_KillTimer
0x18000eeb1  xor     r9d, r9d; lpTimerFunc
0x18000eeb4  mov     r8d, 3E8h; uElapse
0x18000eeba  mov     edx, edi; nIDEvent
0x18000eebc  mov     rcx, rsi; hWnd
0x18000eebf  call    cs:__imp_SetTimer
0x18000eec5  jmp     short loc_18000EEF8
0x18000eec7  mov     rdx, r14
0x18000eeca  mov     rcx, rsi; hWnd
0x18000eecd  call    PreviewOpen
0x18000eed2  lea     rdx, aPreviewstuff; "PreviewStuff"
0x18000eed9  mov     rcx, rsi; hWnd
0x18000eedc  call    cs:__imp_GetPropW
0x18000eee2  mov     rbx, rax
0x18000eee5  test    byte ptr [rax+20h], 20h
0x18000eee9  jnz     short loc_18000EEF8
0x18000eeeb  jmp     loc_18000EE2F
0x18000eef0  mov     rcx, rbx
0x18000eef3  call    PreviewPaint
0x18000eef8  test    rbx, rbx
0x18000eefb  jnz     short loc_18000EF71
0x18000eefd  xor     eax, eax
0x18000eeff  mov     rcx, [rsp+118h+var_48]
0x18000ef07  xor     rcx, rsp; StackCookie
0x18000ef0a  call    __security_check_cookie
0x18000ef0f  add     rsp, 0E8h
0x18000ef16  pop     r15
0x18000ef18  pop     r14
0x18000ef1a  pop     rdi
0x18000ef1b  pop     rsi
0x18000ef1c  pop     rbp
0x18000ef1d  pop     rbx
0x18000ef1e  retn
0x18000ef1f  xor     edi, edi
0x18000ef21  test    rbx, rbx
0x18000ef24  jz      short loc_18000EEFD
0x18000ef26  xor     edx, edx
0x18000ef28  mov     rcx, rbx
0x18000ef2b  call    PreviewFile
0x18000ef30  mov     rcx, [rbx+8]; hWnd
0x18000ef34  lea     rdx, aPreviewstuff; "PreviewStuff"
0x18000ef3b  call    cs:__imp_RemovePropW
0x18000ef41  mov     rcx, [rbx+68h]; ho
0x18000ef45  test    rcx, rcx
0x18000ef48  jz      short loc_18000EF54
0x18000ef4a  call    cs:__imp_DeleteObject
0x18000ef50  mov     [rbx+68h], rdi
0x18000ef54  mov     rcx, [rbx+60h]; hWnd
0x18000ef58  test    rcx, rcx
0x18000ef5b  jz      short loc_18000EF71
0x18000ef5d  xor     r9d, r9d; lParam
0x18000ef60  xor     r8d, r8d; wParam
0x18000ef63  lea     edx, [r9+10h]; Msg
0x18000ef67  call    cs:__imp_SendMessageW
0x18000ef6d  mov     [rbx+60h], rdi
0x18000ef71  test    byte ptr [rbx+20h], 20h
0x18000ef75  jz      short loc_18000EEFD
0x18000ef77  mov     rax, [rbx+28h]
0x18000ef7b  mov     r9, r14
0x18000ef7e  mov     r8, rbp
0x18000ef81  mov     edx, r15d
0x18000ef84  mov     rcx, rsi
0x18000ef87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef8c  jmp     loc_18000EEFF
```

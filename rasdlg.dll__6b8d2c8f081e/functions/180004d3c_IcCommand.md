# IcCommand

- ea: `0x180004d3c`
- end: `0x180004f41`
- name: `IcCommand`
- size: `517`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004f50`

## callees

- `0x180004d3c`

## import_xrefs

- `USER32!GetDlgItemInt` at `0x180004f00`
- `USER32!GetDlgItemInt` at `0x180004f00`
- `USER32!SendMessageW` at `0x180004dd8`
- `USER32!SendMessageW` at `0x180004e6c`
- `USER32!SendMessageW` at `0x180004e9d`
- `USER32!SendMessageW` at `0x180004ebc`
- `USER32!SendMessageW` at `0x180004ee3`
- `USER32!SendMessageW` at `0x180004dd8`
- `USER32!SendMessageW` at `0x180004e6c`
- `USER32!SendMessageW` at `0x180004e9d`
- `USER32!SendMessageW` at `0x180004ebc`
- `USER32!SendMessageW` at `0x180004ee3`
- `USER32!EndDialog` at `0x180004f2d`
- `USER32!EndDialog` at `0x180004f2d`
- `USER32!GetWindowLongPtrW` at `0x180004db5`
- `USER32!GetWindowLongPtrW` at `0x180004e54`
- `USER32!GetWindowLongPtrW` at `0x180004db5`
- `USER32!GetWindowLongPtrW` at `0x180004e54`
- `USER32!EnableWindow` at `0x180004de7`
- `USER32!EnableWindow` at `0x180004df3`
- `USER32!EnableWindow` at `0x180004dff`
- `USER32!EnableWindow` at `0x180004e0b`
- `USER32!EnableWindow` at `0x180004de7`
- `USER32!EnableWindow` at `0x180004df3`
- `USER32!EnableWindow` at `0x180004dff`
- `USER32!EnableWindow` at `0x180004e0b`
- `rtutils!TracePrintfExA` at `0x180004d77`
- `rtutils!TracePrintfExA` at `0x180004e26`
- `rtutils!TracePrintfExA` at `0x180004e46`
- `rtutils!TracePrintfExA` at `0x180004d77`
- `rtutils!TracePrintfExA` at `0x180004e26`
- `rtutils!TracePrintfExA` at `0x180004e46`

## string_xrefs

- `0x180004d64`: `IcCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall IcCommand(HWND hWnd, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  LONG_PTR v11; // rax
  HWND *v12; // rdi
  int v13; // ebx
  INT_PTR v14; // rdx
  HWND v15; // rcx
  LONG_PTR WindowLongPtrW; // rdi
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rax
  HWND v21; // rcx
  __int64 v22; // rbx
  UINT DlgItemInt; // eax
  BOOL Translated; // [rsp+70h] [rbp+18h] BYREF

  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "IcCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "OK pressed");
    WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
    v17 = SendMessageW(*(HWND *)(WindowLongPtrW + 16), 0x147u, 0, 0);
    if ( v17 >= 0 )
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)WindowLongPtrW + 8LL) + 132LL) = v17;
    v18 = *(_QWORD *)(*(_QWORD *)WindowLongPtrW + 8LL);
    *(_DWORD *)(v18 + 136) = SendMessageW(*(HWND *)(WindowLongPtrW + 24), 0xF0u, 0, 0);
    v19 = *(_QWORD *)(*(_QWORD *)WindowLongPtrW + 8LL);
    *(_DWORD *)(v19 + 128) = SendMessageW(*(HWND *)(WindowLongPtrW + 32), 0xF0u, 0, 0);
    v20 = *(_QWORD *)WindowLongPtrW;
    if ( **(_DWORD **)WindowLongPtrW )
    {
      v21 = *(HWND *)(WindowLongPtrW + 40);
      Translated = 0;
      v22 = *(_QWORD *)(v20 + 8);
      *(_DWORD *)(v22 + 140) = SendMessageW(v21, 0xF0u, 0, 0);
      DlgItemInt = GetDlgItemInt(*(HWND *)(WindowLongPtrW + 8), 1151, &Translated, 0);
      if ( Translated )
      {
        if ( DlgItemInt - 1 <= 0x3B9AC9FE )
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)WindowLongPtrW + 8LL) + 144LL) = DlgItemInt;
      }
    }
    v15 = *(HWND *)(WindowLongPtrW + 8);
    v14 = 1;
    goto LABEL_22;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v14 = 0;
    v15 = hWnd;
LABEL_22:
    EndDialog(v15, v14);
    return 1;
  }
  if ( v9 != 1147 )
    return 0;
  if ( !a2 )
  {
    v11 = GetWindowLongPtrW(hWnd, 16);
    v12 = (HWND *)v11;
    if ( **(_DWORD **)v11 )
    {
      v13 = SendMessageW(*(HWND *)(v11 + 32), 0xF0u, 0, 0);
      EnableWindow(v12[5], v13);
      EnableWindow(v12[6], v13);
      EnableWindow(v12[7], v13);
      EnableWindow(v12[8], v13);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004d3c  push    rbx
0x180004d3e  push    rbp
0x180004d3f  push    rsi
0x180004d40  push    rdi
0x180004d41  sub     rsp, 38h
0x180004d45  mov     rdi, rcx
0x180004d48  movzx   ebp, dx
0x180004d4b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180004d51  or      esi, 0FFFFFFFFh
0x180004d54  movzx   ebx, r8w
0x180004d58  mov     rax, r9
0x180004d5b  cmp     ecx, esi
0x180004d5d  jz      short loc_180004D83
0x180004d5f  mov     [rsp+58h+var_30], rax
0x180004d64  lea     r8, aIccommandNDIDC; "IcCommand(n=%d,i=%d,c=$%x)"
0x180004d6b  mov     r9d, ebp
0x180004d6e  mov     [rsp+58h+var_38], ebx
0x180004d72  mov     edx, 0Ch; dwFlags
0x180004d77  call    cs:__imp_TracePrintfExA
0x180004d7d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180004d83  sub     ebx, 1
0x180004d86  jz      loc_180004E36
0x180004d8c  sub     ebx, 1
0x180004d8f  jz      loc_180004E16
0x180004d95  cmp     ebx, 47Bh
0x180004d9b  jz      short loc_180004DA4
0x180004d9d  xor     eax, eax
0x180004d9f  jmp     loc_180004F38
0x180004da4  xor     esi, esi
0x180004da6  test    bp, bp
0x180004da9  jnz     loc_180004F33
0x180004daf  lea     edx, [rsi+10h]; nIndex
0x180004db2  mov     rcx, rdi; hWnd
0x180004db5  call    cs:__imp_GetWindowLongPtrW
0x180004dbb  mov     rdi, rax
0x180004dbe  mov     rcx, [rax]
0x180004dc1  cmp     [rcx], esi
0x180004dc3  jz      loc_180004F33
0x180004dc9  mov     rcx, [rax+20h]; hWnd
0x180004dcd  xor     r9d, r9d; lParam
0x180004dd0  xor     r8d, r8d; wParam
0x180004dd3  mov     edx, 0F0h; Msg
0x180004dd8  call    cs:__imp_SendMessageW
0x180004dde  mov     rcx, [rdi+28h]; hWnd
0x180004de2  mov     edx, eax; bEnable
0x180004de4  mov     rbx, rax
0x180004de7  call    cs:__imp_EnableWindow
0x180004ded  mov     rcx, [rdi+30h]; hWnd
0x180004df1  mov     edx, ebx; bEnable
0x180004df3  call    cs:__imp_EnableWindow
0x180004df9  mov     rcx, [rdi+38h]; hWnd
0x180004dfd  mov     edx, ebx; bEnable
0x180004dff  call    cs:__imp_EnableWindow
0x180004e05  mov     rcx, [rdi+40h]; hWnd
0x180004e09  mov     edx, ebx; bEnable
0x180004e0b  call    cs:__imp_EnableWindow
0x180004e11  jmp     loc_180004F33
0x180004e16  cmp     ecx, esi
0x180004e18  jz      short loc_180004E2C
0x180004e1a  lea     r8, aCancelPressed; "Cancel pressed"
0x180004e21  mov     edx, 0Ch; dwFlags
0x180004e26  call    cs:__imp_TracePrintfExA
0x180004e2c  xor     edx, edx
0x180004e2e  mov     rcx, rdi
0x180004e31  jmp     loc_180004F2D
0x180004e36  cmp     ecx, esi
0x180004e38  jz      short loc_180004E4C
0x180004e3a  lea     r8, aOkPressed; "OK pressed"
0x180004e41  mov     edx, 0Ch; dwFlags
0x180004e46  call    cs:__imp_TracePrintfExA
0x180004e4c  mov     edx, 10h; nIndex
0x180004e51  mov     rcx, rdi; hWnd
0x180004e54  call    cs:__imp_GetWindowLongPtrW
0x180004e5a  xor     r9d, r9d; lParam
0x180004e5d  xor     r8d, r8d; wParam
0x180004e60  mov     edx, 147h; Msg
0x180004e65  mov     rdi, rax
0x180004e68  mov     rcx, [rax+10h]; hWnd
0x180004e6c  call    cs:__imp_SendMessageW
0x180004e72  xor     esi, esi
0x180004e74  test    eax, eax
0x180004e76  js      short loc_180004E85
0x180004e78  mov     rcx, [rdi]
0x180004e7b  mov     rdx, [rcx+8]
0x180004e7f  mov     [rdx+84h], eax
0x180004e85  mov     rax, [rdi]
0x180004e88  mov     ebp, 0F0h
0x180004e8d  mov     rcx, [rdi+18h]; hWnd
0x180004e91  xor     r9d, r9d; lParam
0x180004e94  xor     r8d, r8d; wParam
0x180004e97  mov     edx, ebp; Msg
0x180004e99  mov     rbx, [rax+8]
0x180004e9d  call    cs:__imp_SendMessageW
0x180004ea3  mov     [rbx+88h], eax
0x180004ea9  xor     r9d, r9d; lParam
0x180004eac  mov     rax, [rdi]
0x180004eaf  xor     r8d, r8d; wParam
0x180004eb2  mov     rcx, [rdi+20h]; hWnd
0x180004eb6  mov     edx, ebp; Msg
0x180004eb8  mov     rbx, [rax+8]
0x180004ebc  call    cs:__imp_SendMessageW
0x180004ec2  mov     [rbx+80h], eax
0x180004ec8  mov     rax, [rdi]
0x180004ecb  cmp     [rax], esi
0x180004ecd  jz      short loc_180004F24
0x180004ecf  mov     rcx, [rdi+28h]; hWnd
0x180004ed3  xor     r9d, r9d; lParam
0x180004ed6  mov     [rsp+58h+Translated], esi
0x180004eda  xor     r8d, r8d; wParam
0x180004edd  mov     rbx, [rax+8]
0x180004ee1  mov     edx, ebp; Msg
0x180004ee3  call    cs:__imp_SendMessageW
0x180004ee9  mov     [rbx+8Ch], eax
0x180004eef  xor     r9d, r9d; bSigned
0x180004ef2  mov     rcx, [rdi+8]; hDlg
0x180004ef6  lea     r8, [rsp+58h+Translated]; lpTranslated
0x180004efb  mov     edx, 47Fh; nIDDlgItem
0x180004f00  call    cs:__imp_GetDlgItemInt
0x180004f06  cmp     [rsp+58h+Translated], esi
0x180004f0a  jz      short loc_180004F24
0x180004f0c  lea     ecx, [rax-1]
0x180004f0f  cmp     ecx, 3B9AC9FEh
0x180004f15  ja      short loc_180004F24
0x180004f17  mov     rcx, [rdi]
0x180004f1a  mov     rdx, [rcx+8]
0x180004f1e  mov     [rdx+90h], eax
0x180004f24  mov     rcx, [rdi+8]; hDlg
0x180004f28  mov     edx, 1; nResult
0x180004f2d  call    cs:__imp_EndDialog
0x180004f33  mov     eax, 1
0x180004f38  add     rsp, 38h
0x180004f3c  pop     rdi
0x180004f3d  pop     rsi
0x180004f3e  pop     rbp
0x180004f3f  pop     rbx
0x180004f40  retn
```

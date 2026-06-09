# DcCommand

- ea: `0x1800066b0`
- end: `0x1800067a5`
- name: `DcCommand`
- size: `245`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067b0`

## callees

- `0x1800066b0`
- `0x18003c108`

## import_xrefs

- `USER32!GetWindowTextW` at `0x180006757`
- `USER32!GetWindowTextW` at `0x180006757`
- `USER32!EndDialog` at `0x180006791`
- `USER32!EndDialog` at `0x180006791`
- `USER32!GetWindowLongPtrW` at `0x180006742`
- `USER32!GetWindowLongPtrW` at `0x180006742`
- `USER32!GetDlgItem` at `0x180006731`
- `USER32!GetDlgItem` at `0x180006731`
- `rtutils!TracePrintfExA` at `0x1800066e9`
- `rtutils!TracePrintfExA` at `0x180006723`
- `rtutils!TracePrintfExA` at `0x18000677f`
- `rtutils!TracePrintfExA` at `0x1800066e9`
- `rtutils!TracePrintfExA` at `0x180006723`
- `rtutils!TracePrintfExA` at `0x18000677f`

## string_xrefs

- `0x1800066d4`: `DcCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall DcCommand(HWND hDlg, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebx
  DWORD v6; // ecx
  int v7; // ebx
  HWND DlgItem; // rdi
  WCHAR *WindowLongPtrW; // rbx
  INT_PTR v11; // rdx

  v5 = a3;
  v6 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "DcCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
  }
  else
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "OK pressed");
    DlgItem = GetDlgItem(hDlg, 1065);
    WindowLongPtrW = (WCHAR *)GetWindowLongPtrW(hDlg, 16);
    GetWindowTextW(DlgItem, WindowLongPtrW, 129);
    if ( !(unsigned int)IsAllWhite(WindowLongPtrW) )
    {
      v11 = 1;
      goto LABEL_15;
    }
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Blank number cancel");
  }
  v11 = 0;
LABEL_15:
  EndDialog(hDlg, v11);
  return 1;
}

```

## disassembly

```asm
0x1800066b0  push    rbx
0x1800066b2  push    rbp
0x1800066b3  push    rsi
0x1800066b4  push    rdi
0x1800066b5  sub     rsp, 38h
0x1800066b9  mov     rsi, rcx
0x1800066bc  movzx   ebx, r8w
0x1800066c0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800066c6  or      ebp, 0FFFFFFFFh
0x1800066c9  mov     rax, r9
0x1800066cc  cmp     ecx, ebp
0x1800066ce  jz      short loc_1800066F5
0x1800066d0  movzx   r9d, dx
0x1800066d4  lea     r8, aDccommandNDIDC; "DcCommand(n=%d,i=%d,c=$%x)"
0x1800066db  mov     [rsp+58h+var_30], rax
0x1800066e0  mov     edx, 0Ch; dwFlags
0x1800066e5  mov     [rsp+58h+var_38], ebx
0x1800066e9  call    cs:__imp_TracePrintfExA
0x1800066ef  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800066f5  sub     ebx, 1
0x1800066f8  jz      short loc_180006713
0x1800066fa  cmp     ebx, 1
0x1800066fd  jz      short loc_180006706
0x1800066ff  xor     eax, eax
0x180006701  jmp     loc_18000679C
0x180006706  cmp     ecx, ebp
0x180006708  jz      short loc_180006785
0x18000670a  lea     r8, aCancelPressed; "Cancel pressed"
0x180006711  jmp     short loc_18000677A
0x180006713  cmp     ecx, ebp
0x180006715  jz      short loc_180006729
0x180006717  lea     r8, aOkPressed; "OK pressed"
0x18000671e  mov     edx, 0Ch; dwFlags
0x180006723  call    cs:__imp_TracePrintfExA
0x180006729  mov     edx, 429h; nIDDlgItem
0x18000672e  mov     rcx, rsi; hDlg
0x180006731  call    cs:__imp_GetDlgItem
0x180006737  mov     edx, 10h; nIndex
0x18000673c  mov     rcx, rsi; hWnd
0x18000673f  mov     rdi, rax
0x180006742  call    cs:__imp_GetWindowLongPtrW
0x180006748  mov     r8d, 81h; nMaxCount
0x18000674e  mov     rcx, rdi; hWnd
0x180006751  mov     rdx, rax; lpString
0x180006754  mov     rbx, rax
0x180006757  call    cs:__imp_GetWindowTextW
0x18000675d  mov     rcx, rbx
0x180006760  call    IsAllWhite
0x180006765  test    eax, eax
0x180006767  jz      short loc_180006789
0x180006769  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000676f  cmp     ecx, ebp
0x180006771  jz      short loc_180006785
0x180006773  lea     r8, aBlankNumberCan; "Blank number cancel"
0x18000677a  mov     edx, 0Ch; dwFlags
0x18000677f  call    cs:__imp_TracePrintfExA
0x180006785  xor     edx, edx
0x180006787  jmp     short loc_18000678E
0x180006789  mov     edx, 1; nResult
0x18000678e  mov     rcx, rsi; hDlg
0x180006791  call    cs:__imp_EndDialog
0x180006797  mov     eax, 1
0x18000679c  add     rsp, 38h
0x1800067a0  pop     rdi
0x1800067a1  pop     rsi
0x1800067a2  pop     rbp
0x1800067a3  pop     rbx
0x1800067a4  retn
```

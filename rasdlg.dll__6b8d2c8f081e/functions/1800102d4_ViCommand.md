# ViCommand

- ea: `0x1800102d4`
- end: `0x1800103a2`
- name: `ViCommand`
- size: `206`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800103b0`

## callees

- `0x1800102d4`

## import_xrefs

- `RASAPI32!WritePhonebookFile` at `0x18001036e`
- `RASAPI32!WritePhonebookFile` at `0x18001036e`
- `USER32!IsDlgButtonChecked` at `0x18001033f`
- `USER32!IsDlgButtonChecked` at `0x18001033f`
- `USER32!EndDialog` at `0x18001037f`
- `USER32!EndDialog` at `0x18001038e`
- `USER32!EndDialog` at `0x18001037f`
- `USER32!EndDialog` at `0x18001038e`
- `USER32!GetWindowLongPtrW` at `0x18001032e`
- `USER32!GetWindowLongPtrW` at `0x18001032e`
- `rtutils!TracePrintfExA` at `0x18001030d`
- `rtutils!TracePrintfExA` at `0x18001030d`

## string_xrefs

- `0x1800102f8`: `ViCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall ViCommand(HWND hDlg, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebp
  int v6; // ebx
  int v7; // ebx
  LONG_PTR WindowLongPtrW; // rsi

  v5 = a3;
  v6 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ViCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
  v7 = v6 - 2;
  if ( v7 )
  {
    if ( (unsigned int)(v7 - 4) < 2 )
    {
      WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
      if ( IsDlgButtonChecked(hDlg, 1579) )
      {
        *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 448) + 252LL) = 1;
        *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 448) + 532LL) = 1;
        WritePhonebookFile(*(_QWORD *)(WindowLongPtrW + 40), 0);
      }
      EndDialog(hDlg, v5 == 6);
      return 1;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    EndDialog(hDlg, 0);
    return 1;
  }
}

```

## disassembly

```asm
0x1800102d4  push    rbx
0x1800102d6  push    rbp
0x1800102d7  push    rsi
0x1800102d8  push    rdi
0x1800102d9  sub     rsp, 38h
0x1800102dd  mov     rdi, rcx
0x1800102e0  movzx   ebp, r8w
0x1800102e4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800102ea  mov     rax, r9
0x1800102ed  mov     ebx, ebp
0x1800102ef  cmp     ecx, 0FFFFFFFFh
0x1800102f2  jz      short loc_180010313
0x1800102f4  movzx   r9d, dx
0x1800102f8  lea     r8, aVicommandNDIDC; "ViCommand(n=%d,i=%d,c=$%x)"
0x1800102ff  mov     [rsp+58h+var_30], rax
0x180010304  mov     edx, 0Ch; dwFlags
0x180010309  mov     [rsp+58h+var_38], ebx
0x18001030d  call    cs:__imp_TracePrintfExA
0x180010313  sub     ebx, 2
0x180010316  jz      short loc_180010389
0x180010318  sub     ebx, 4
0x18001031b  jz      short loc_180010326
0x18001031d  cmp     ebx, 1
0x180010320  jz      short loc_180010326
0x180010322  xor     eax, eax
0x180010324  jmp     short loc_180010399
0x180010326  mov     edx, 10h; nIndex
0x18001032b  mov     rcx, rdi; hWnd
0x18001032e  call    cs:__imp_GetWindowLongPtrW
0x180010334  mov     edx, 62Bh; nIDButton
0x180010339  mov     rcx, rdi; hDlg
0x18001033c  mov     rsi, rax
0x18001033f  call    cs:__imp_IsDlgButtonChecked
0x180010345  mov     ebx, 1
0x18001034a  test    eax, eax
0x18001034c  jz      short loc_180010374
0x18001034e  mov     rcx, [rsi+1C0h]
0x180010355  xor     edx, edx
0x180010357  mov     [rcx+0FCh], ebx
0x18001035d  mov     rcx, [rsi+1C0h]
0x180010364  mov     [rcx+214h], ebx
0x18001036a  mov     rcx, [rsi+28h]
0x18001036e  call    cs:__imp_WritePhonebookFile
0x180010374  xor     edx, edx
0x180010376  mov     rcx, rdi; hDlg
0x180010379  cmp     ebp, 6
0x18001037c  setz    dl; nResult
0x18001037f  call    cs:__imp_EndDialog
0x180010385  mov     eax, ebx
0x180010387  jmp     short loc_180010399
0x180010389  xor     edx, edx; nResult
0x18001038b  mov     rcx, rdi; hDlg
0x18001038e  call    cs:__imp_EndDialog
0x180010394  mov     eax, 1
0x180010399  add     rsp, 38h
0x18001039d  pop     rdi
0x18001039e  pop     rsi
0x18001039f  pop     rbp
0x1800103a0  pop     rbx
0x1800103a1  retn
```

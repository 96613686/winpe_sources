# ItCommand

- ea: `0x1800299c8`
- end: `0x180029aa1`
- name: `ItCommand`
- size: `217`
- prototype: `__int64 __fastcall(HWND *, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029ab0`

## callees

- `0x1800299c8`
- `0x18004797c`

## import_xrefs

- `USER32!SendMessageW` at `0x180029a43`
- `USER32!SendMessageW` at `0x180029a43`
- `USER32!EndDialog` at `0x180029a86`
- `USER32!EndDialog` at `0x180029a86`
- `rtutils!TracePrintfExA` at `0x180029a09`
- `rtutils!TracePrintfExA` at `0x180029a5d`
- `rtutils!TracePrintfExA` at `0x180029a77`
- `rtutils!TracePrintfExA` at `0x180029a09`
- `rtutils!TracePrintfExA` at `0x180029a5d`
- `rtutils!TracePrintfExA` at `0x180029a77`

## string_xrefs

- `0x1800299f4`: `ItCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall ItCommand(HWND *a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebx
  DWORD v6; // ecx
  int v7; // ebx
  int v8; // ebx
  INT_PTR v10; // rdx

  v5 = a3;
  v6 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "ItCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v7 = v5 - 1;
  if ( !v7 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "OK pressed");
    v10 = 1;
    goto LABEL_14;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v10 = 0;
LABEL_14:
    EndDialog(a1[1], v10);
    return 1;
  }
  if ( v8 == 1159 )
  {
    Button_MakeDefault(a1[1], a1[3]);
    SendMessageW(a1[2], 0xB1u, 0xFFFFFFFF, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800299c8  mov     [rsp+arg_0], rbx
0x1800299cd  mov     [rsp+arg_8], rsi
0x1800299d2  push    rdi
0x1800299d3  sub     rsp, 30h
0x1800299d7  mov     rdi, rcx
0x1800299da  movzx   ebx, r8w
0x1800299de  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800299e4  mov     esi, 0FFFFFFFFh
0x1800299e9  mov     rax, r9
0x1800299ec  cmp     ecx, esi
0x1800299ee  jz      short loc_180029A15
0x1800299f0  movzx   r9d, dx
0x1800299f4  lea     r8, aItcommandNDIDC; "ItCommand(n=%d,i=%d,c=$%x)"
0x1800299fb  mov     [rsp+38h+var_10], rax
0x180029a00  mov     edx, 0Ch; dwFlags
0x180029a05  mov     [rsp+38h+var_18], ebx
0x180029a09  call    cs:__imp_TracePrintfExA
0x180029a0f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180029a15  sub     ebx, 1
0x180029a18  jz      short loc_180029A67
0x180029a1a  sub     ebx, 1
0x180029a1d  jz      short loc_180029A4D
0x180029a1f  cmp     ebx, 487h
0x180029a25  jnz     short loc_180029A49
0x180029a27  mov     rdx, [rdi+18h]; HWND
0x180029a2b  mov     rcx, [rdi+8]; hWnd
0x180029a2f  call    Button_MakeDefault
0x180029a34  mov     rcx, [rdi+10h]; hWnd
0x180029a38  xor     r9d, r9d; lParam
0x180029a3b  mov     r8, rsi; wParam
0x180029a3e  mov     edx, 0B1h; Msg
0x180029a43  call    cs:__imp_SendMessageW
0x180029a49  xor     eax, eax
0x180029a4b  jmp     short loc_180029A91
0x180029a4d  cmp     ecx, esi
0x180029a4f  jz      short loc_180029A63
0x180029a51  lea     r8, aCancelPressed; "Cancel pressed"
0x180029a58  mov     edx, 0Ch; dwFlags
0x180029a5d  call    cs:__imp_TracePrintfExA
0x180029a63  xor     edx, edx
0x180029a65  jmp     short loc_180029A82
0x180029a67  cmp     ecx, esi
0x180029a69  jz      short loc_180029A7D
0x180029a6b  lea     r8, aOkPressed; "OK pressed"
0x180029a72  mov     edx, 0Ch; dwFlags
0x180029a77  call    cs:__imp_TracePrintfExA
0x180029a7d  mov     edx, 1; nResult
0x180029a82  mov     rcx, [rdi+8]; hDlg
0x180029a86  call    cs:__imp_EndDialog
0x180029a8c  mov     eax, 1
0x180029a91  mov     rbx, [rsp+38h+arg_0]
0x180029a96  mov     rsi, [rsp+38h+arg_8]
0x180029a9b  add     rsp, 30h
0x180029a9f  pop     rdi
0x180029aa0  retn
```

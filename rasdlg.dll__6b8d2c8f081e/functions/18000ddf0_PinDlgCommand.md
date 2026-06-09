# PinDlgCommand

- ea: `0x18000ddf0`
- end: `0x18000de84`
- name: `PinDlgCommand`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e050`

## callees

- `0x18000ddf0`
- `0x18000e0c0`

## import_xrefs

- `USER32!EndDialog` at `0x18000de6e`
- `USER32!EndDialog` at `0x18000de6e`
- `rtutils!TracePrintfExA` at `0x18000de28`
- `rtutils!TracePrintfExA` at `0x18000de53`
- `rtutils!TracePrintfExA` at `0x18000de28`
- `rtutils!TracePrintfExA` at `0x18000de53`

## string_xrefs

- `0x18000de13`: `PinDlgCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall PinDlgCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebx
  DWORD v6; // ecx
  int v7; // ebx
  INT_PTR v9; // rdx

  v5 = a3;
  v6 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "PinDlgCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v9 = 0;
  }
  else
  {
    PinDlgSave(a1);
    v9 = 1;
  }
  EndDialog(*(HWND *)(a1 + 8), v9);
  return 1;
}

```

## disassembly

```asm
0x18000ddf0  mov     [rsp+arg_0], rbx
0x18000ddf5  push    rdi
0x18000ddf6  sub     rsp, 30h
0x18000ddfa  mov     rdi, rcx
0x18000ddfd  movzx   ebx, r8w
0x18000de01  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000de07  mov     rax, r9
0x18000de0a  cmp     ecx, 0FFFFFFFFh
0x18000de0d  jz      short loc_18000DE34
0x18000de0f  movzx   r9d, dx
0x18000de13  lea     r8, aPindlgcommandN; "PinDlgCommand(n=%d,i=%d,c=$%x)"
0x18000de1a  mov     [rsp+38h+var_10], rax
0x18000de1f  mov     edx, 0Ch; dwFlags
0x18000de24  mov     [rsp+38h+var_18], ebx
0x18000de28  call    cs:__imp_TracePrintfExA
0x18000de2e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000de34  sub     ebx, 1
0x18000de37  jz      short loc_18000DE5D
0x18000de39  cmp     ebx, 1
0x18000de3c  jz      short loc_18000DE42
0x18000de3e  xor     eax, eax
0x18000de40  jmp     short loc_18000DE79
0x18000de42  cmp     ecx, 0FFFFFFFFh
0x18000de45  jz      short loc_18000DE59
0x18000de47  lea     r8, aCancelPressed; "Cancel pressed"
0x18000de4e  mov     edx, 0Ch; dwFlags
0x18000de53  call    cs:__imp_TracePrintfExA
0x18000de59  xor     edx, edx
0x18000de5b  jmp     short loc_18000DE6A
0x18000de5d  mov     rcx, rdi
0x18000de60  call    PinDlgSave
0x18000de65  mov     edx, 1; nResult
0x18000de6a  mov     rcx, [rdi+8]; hDlg
0x18000de6e  call    cs:__imp_EndDialog
0x18000de74  mov     eax, 1
0x18000de79  mov     rbx, [rsp+38h+arg_0]
0x18000de7e  add     rsp, 30h
0x18000de82  pop     rdi
0x18000de83  retn
```

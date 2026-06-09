# ux::CLauncherMainTaskDialog::OnDialogConstructed(void)

- ea: `0x18000a62c`
- end: `0x18000a709`
- name: `?OnDialogConstructed@CLauncherMainTaskDialog@ux@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(HWND *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000b0c0`

## callees

- `0x180008ac8`
- `0x18000a62c`

## import_xrefs

- `USER32!SendMessageW` at `0x18000a67d`
- `USER32!SendMessageW` at `0x18000a696`
- `USER32!SendMessageW` at `0x18000a6b8`
- `USER32!SendMessageW` at `0x18000a6d1`
- `USER32!SendMessageW` at `0x18000a67d`
- `USER32!SendMessageW` at `0x18000a696`
- `USER32!SendMessageW` at `0x18000a6b8`
- `USER32!SendMessageW` at `0x18000a6d1`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::OnDialogConstructed(HWND *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  SendMessageW(this[21], 0x473u, 0x65u, 1);
  SendMessageW(this[21], 0x46Fu, 0x65u, 0);
  if ( *((_BYTE *)this + 181) )
  {
    SendMessageW(this[21], 0x470u, 0x66u, 0);
    SendMessageW(this[21], 0x470u, 0x67u, 0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
}

```

## disassembly

```asm
0x18000a62c  mov     [rsp+arg_0], rbx
0x18000a631  push    rsi
0x18000a632  sub     rsp, 20h
0x18000a636  mov     rbx, rcx
0x18000a639  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a640  lea     rsi, WPP_GLOBAL_Control
0x18000a647  cmp     rcx, rsi
0x18000a64a  jz      short loc_18000A667
0x18000a64c  test    byte ptr [rcx+1Ch], 8
0x18000a650  jz      short loc_18000A667
0x18000a652  mov     rcx, [rcx+10h]
0x18000a656  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a65d  mov     edx, 0Fh
0x18000a662  call    WPP_SF_
0x18000a667  mov     rcx, [rbx+0A8h]; hWnd
0x18000a66e  mov     r9d, 1; lParam
0x18000a674  mov     edx, 473h; Msg
0x18000a679  lea     r8d, [r9+64h]; wParam
0x18000a67d  call    cs:__imp_SendMessageW
0x18000a683  mov     rcx, [rbx+0A8h]; hWnd
0x18000a68a  xor     r9d, r9d; lParam
0x18000a68d  mov     edx, 46Fh; Msg
0x18000a692  lea     r8d, [r9+65h]; wParam
0x18000a696  call    cs:__imp_SendMessageW
0x18000a69c  cmp     byte ptr [rbx+0B5h], 0
0x18000a6a3  jz      short loc_18000A6D7
0x18000a6a5  mov     rcx, [rbx+0A8h]; hWnd
0x18000a6ac  xor     r9d, r9d; lParam
0x18000a6af  mov     edx, 470h; Msg
0x18000a6b4  lea     r8d, [r9+66h]; wParam
0x18000a6b8  call    cs:__imp_SendMessageW
0x18000a6be  mov     rcx, [rbx+0A8h]; hWnd
0x18000a6c5  xor     r9d, r9d; lParam
0x18000a6c8  mov     edx, 470h; Msg
0x18000a6cd  lea     r8d, [r9+67h]; wParam
0x18000a6d1  call    cs:__imp_SendMessageW
0x18000a6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6de  cmp     rcx, rsi
0x18000a6e1  jz      short loc_18000A6FE
0x18000a6e3  test    byte ptr [rcx+1Ch], 8
0x18000a6e7  jz      short loc_18000A6FE
0x18000a6e9  mov     rcx, [rcx+10h]
0x18000a6ed  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a6f4  mov     edx, 10h
0x18000a6f9  call    WPP_SF_
0x18000a6fe  mov     rbx, [rsp+28h+arg_0]
0x18000a703  add     rsp, 20h
0x18000a707  pop     rsi
0x18000a708  retn
```

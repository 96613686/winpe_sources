# ux::CLauncherMainTaskDialog::OnRadioButtonClicked(int)

- ea: `0x18000aa0c`
- end: `0x18000aad1`
- name: `?OnRadioButtonClicked@CLauncherMainTaskDialog@ux@@QEAAXH@Z`
- size: `197`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000b0c0`

## callees

- `0x180008ac8`
- `0x18000aa0c`

## import_xrefs

- `USER32!SendMessageW` at `0x18000aa8d`
- `USER32!SendMessageW` at `0x18000aa8d`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::OnRadioButtonClicked(ux::CLauncherMainTaskDialog *this, int a2)
{
  LPARAM v4; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  v4 = 0;
  *((_DWORD *)this + 44) = a2;
  if ( a2 == 102 )
  {
    if ( *((_BYTE *)this + 180) )
      goto LABEL_10;
LABEL_9:
    v4 = 1;
    goto LABEL_10;
  }
  if ( a2 == 103 && *((_BYTE *)this + 180) )
    goto LABEL_9;
LABEL_10:
  SendMessageW(*((HWND *)this + 21), 0x46Fu, 0x65u, v4);
  *((_DWORD *)this + 20) = 2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
}

```

## disassembly

```asm
0x18000aa0c  mov     [rsp+arg_0], rbx
0x18000aa11  mov     [rsp+arg_8], rsi
0x18000aa16  push    rdi
0x18000aa17  sub     rsp, 20h
0x18000aa1b  mov     edi, edx
0x18000aa1d  mov     rbx, rcx
0x18000aa20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa27  lea     rsi, WPP_GLOBAL_Control
0x18000aa2e  cmp     rcx, rsi
0x18000aa31  jz      short loc_18000AA4E
0x18000aa33  test    byte ptr [rcx+1Ch], 8
0x18000aa37  jz      short loc_18000AA4E
0x18000aa39  mov     rcx, [rcx+10h]
0x18000aa3d  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000aa44  mov     edx, 1Dh
0x18000aa49  call    WPP_SF_
0x18000aa4e  xor     r9d, r9d
0x18000aa51  mov     [rbx+0B0h], edi
0x18000aa57  cmp     edi, 66h ; 'f'
0x18000aa5a  jnz     short loc_18000AA67
0x18000aa5c  cmp     [rbx+0B4h], r9b
0x18000aa63  jz      short loc_18000AA75
0x18000aa65  jmp     short loc_18000AA7B
0x18000aa67  cmp     edi, 67h ; 'g'
0x18000aa6a  jnz     short loc_18000AA7B
0x18000aa6c  cmp     [rbx+0B4h], r9b
0x18000aa73  jz      short loc_18000AA7B
0x18000aa75  mov     r9d, 1; lParam
0x18000aa7b  mov     rcx, [rbx+0A8h]; hWnd
0x18000aa82  mov     edx, 46Fh; Msg
0x18000aa87  mov     r8d, 65h ; 'e'; wParam
0x18000aa8d  call    cs:__imp_SendMessageW
0x18000aa93  mov     dword ptr [rbx+50h], 2
0x18000aa9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaa1  cmp     rcx, rsi
0x18000aaa4  jz      short loc_18000AAC1
0x18000aaa6  test    byte ptr [rcx+1Ch], 8
0x18000aaaa  jz      short loc_18000AAC1
0x18000aaac  mov     rcx, [rcx+10h]
0x18000aab0  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000aab7  mov     edx, 1Eh
0x18000aabc  call    WPP_SF_
0x18000aac1  mov     rbx, [rsp+28h+arg_0]
0x18000aac6  mov     rsi, [rsp+28h+arg_8]
0x18000aacb  add     rsp, 20h
0x18000aacf  pop     rdi
0x18000aad0  retn
```

# ux::CLauncherMainTaskDialog::ShowErrorDialog(int,int)

- ea: `0x18000ae20`
- end: `0x18000aed1`
- name: `?ShowErrorDialog@CLauncherMainTaskDialog@ux@@AEBAXHH@Z`
- size: `177`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *this, __int64, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000a148`
- `0x18000a4e8`

## callees

- `0x180008ac8`
- `0x180008d9c`
- `0x180009360`
- `0x180009974`
- `0x18000ae20`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::ShowErrorDialog(
        ux::CLauncherMainTaskDialog *this,
        __int64 a2,
        unsigned __int16 a3)
{
  _BYTE v5[8]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v6[168]; // [rsp+38h] [rbp-B0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog((unsigned __int64)v5, 0xD0u, a3);
  WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal((__int64)v6, *((_QWORD *)this + 21));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)v5);
}

```

## disassembly

```asm
0x18000ae20  mov     [rsp+arg_0], rbx
0x18000ae25  mov     [rsp+arg_8], rsi
0x18000ae2a  push    rdi
0x18000ae2b  sub     rsp, 0E0h
0x18000ae32  mov     ebx, r8d
0x18000ae35  mov     rdi, rcx
0x18000ae38  lea     rsi, WPP_GLOBAL_Control
0x18000ae3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae46  cmp     rcx, rsi
0x18000ae49  jz      short loc_18000AE66
0x18000ae4b  test    byte ptr [rcx+1Ch], 8
0x18000ae4f  jz      short loc_18000AE66
0x18000ae51  mov     edx, 11h
0x18000ae56  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000ae5d  mov     rcx, [rcx+10h]
0x18000ae61  call    WPP_SF_
0x18000ae66  mov     r8d, ebx; int
0x18000ae69  mov     edx, 0D0h; int
0x18000ae6e  lea     rcx, [rsp+0E8h+var_B8]; this
0x18000ae73  call    ??0CLauncherErrorTaskDialog@ux@@QEAA@HH@Z; ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(int,int)
0x18000ae78  nop
0x18000ae79  mov     rdx, [rdi+0A8h]
0x18000ae80  lea     rcx, [rsp+0E8h+var_B0]
0x18000ae85  call    ?DoModal@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@QEAAJPEAUHWND__@@PEAH11@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(HWND__ *,int *,int *,int *)
0x18000ae8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae91  cmp     rcx, rsi
0x18000ae94  jz      short loc_18000AEB2
0x18000ae96  test    byte ptr [rcx+1Ch], 8
0x18000ae9a  jz      short loc_18000AEB2
0x18000ae9c  mov     edx, 12h
0x18000aea1  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000aea8  mov     rcx, [rcx+10h]
0x18000aeac  call    WPP_SF_
0x18000aeb1  nop
0x18000aeb2  lea     rcx, [rsp+0E8h+var_B8]; this
0x18000aeb7  call    ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
0x18000aebc  lea     r11, [rsp+0E8h+var_8]
0x18000aec4  mov     rbx, [r11+10h]
0x18000aec8  mov     rsi, [r11+18h]
0x18000aecc  mov     rsp, r11
0x18000aecf  pop     rdi
0x18000aed0  retn
```

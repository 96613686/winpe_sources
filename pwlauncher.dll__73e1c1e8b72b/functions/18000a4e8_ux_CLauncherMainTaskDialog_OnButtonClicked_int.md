# ux::CLauncherMainTaskDialog::OnButtonClicked(int)

- ea: `0x18000a4e8`
- end: `0x18000a624`
- name: `?OnButtonClicked@CLauncherMainTaskDialog@ux@@QEAA_NH@Z`
- size: `316`
- prototype: `char __fastcall(ux::CLauncherMainTaskDialog *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b0c0`

## callees

- `0x180005528`
- `0x180008ac8`
- `0x180009ce4`
- `0x18000a4e8`
- `0x18000ab94`
- `0x18000ae20`
- `0x18000b180`

## string_xrefs

- `0x18000a53a`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`
- `0x18000a5b6`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
char __fastcall ux::CLauncherMainTaskDialog::OnButtonClicked(ux::CLauncherMainTaskDialog *this, int a2)
{
  _QWORD *v4; // rcx
  char v5; // bl
  bool v6; // al
  int v7; // edx
  int v8; // esi
  __int64 v10; // [rsp+28h] [rbp-30h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      WPP_SF_sdD(
        v4[2],
        26,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        17,
        a2);
      v4 = WPP_GLOBAL_Control;
    }
  }
  v5 = 0;
  if ( a2 == 101 )
  {
    v5 = 1;
    v6 = (unsigned int)gp::CLauncherGroupPolicy::GetPolicy() - 2 <= 1;
    *((_BYTE *)this + 181) = v6;
    if ( v6 )
    {
      ux::CLauncherMainTaskDialog::ShowErrorDialog(this, v7, 209);
      v5 = 0;
    }
    else
    {
      v8 = *((_DWORD *)this + 44);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LODWORD(v10) = *((_DWORD *)this + 44);
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
          39,
          v10);
      }
      ux::CLauncherMainTaskDialog::EnableControls((HWND *)this, 0);
      ux::CLauncherMainTaskDialog::SetLauncherEnabled(this, v8 == 102);
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(v4[2], 28, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x18000a4e8  push    rbx
0x18000a4ea  push    rbp
0x18000a4eb  push    rsi
0x18000a4ec  push    rdi
0x18000a4ed  sub     rsp, 38h
0x18000a4f1  mov     esi, edx
0x18000a4f3  mov     rdi, rcx
0x18000a4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4fd  lea     rbp, WPP_GLOBAL_Control
0x18000a504  cmp     rcx, rbp
0x18000a507  jz      short loc_18000A565
0x18000a509  test    byte ptr [rcx+1Ch], 8
0x18000a50d  jz      short loc_18000A52B
0x18000a50f  mov     rcx, [rcx+10h]
0x18000a513  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a51a  mov     edx, 19h
0x18000a51f  call    WPP_SF_
0x18000a524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a52b  cmp     rcx, rbp
0x18000a52e  jz      short loc_18000A565
0x18000a530  test    byte ptr [rcx+1Ch], 4
0x18000a534  jz      short loc_18000A565
0x18000a536  mov     rcx, [rcx+10h]
0x18000a53a  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a541  mov     edx, 1Ah
0x18000a546  mov     dword ptr [rsp+58h+var_30], esi
0x18000a54a  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a551  mov     [rsp+58h+var_38], 111h
0x18000a559  call    WPP_SF_sdD
0x18000a55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a565  xor     bl, bl
0x18000a567  cmp     esi, 65h ; 'e'
0x18000a56a  jnz     loc_18000A5F9
0x18000a570  call    ?GetPolicy@CLauncherGroupPolicy@gp@@SA?AW4LauncherGroupPolicyState@2@XZ; gp::CLauncherGroupPolicy::GetPolicy(void)
0x18000a575  add     eax, 0FFFFFFFEh
0x18000a578  lea     ebx, [rsi-64h]
0x18000a57b  cmp     eax, ebx
0x18000a57d  setbe   al
0x18000a580  mov     [rdi+0B5h], al
0x18000a586  test    al, al
0x18000a588  jz      short loc_18000A59A
0x18000a58a  lea     r8d, [rsi+6Ch]; int
0x18000a58e  mov     rcx, rdi; this
0x18000a591  call    ?ShowErrorDialog@CLauncherMainTaskDialog@ux@@AEBAXHH@Z; ux::CLauncherMainTaskDialog::ShowErrorDialog(int,int)
0x18000a596  xor     bl, bl
0x18000a598  jmp     short loc_18000A5F2
0x18000a59a  mov     esi, [rdi+0B0h]
0x18000a5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5a7  cmp     rcx, rbp
0x18000a5aa  jz      short loc_18000A5DA
0x18000a5ac  test    byte ptr [rcx+1Ch], 4
0x18000a5b0  jz      short loc_18000A5DA
0x18000a5b2  mov     rcx, [rcx+10h]
0x18000a5b6  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a5bd  mov     edx, 1Bh
0x18000a5c2  mov     dword ptr [rsp+58h+var_30], esi
0x18000a5c6  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a5cd  mov     [rsp+58h+var_38], 127h
0x18000a5d5  call    WPP_SF_sdD
0x18000a5da  xor     edx, edx; bool
0x18000a5dc  mov     rcx, rdi; this
0x18000a5df  call    ?EnableControls@CLauncherMainTaskDialog@ux@@AEAAX_N@Z; ux::CLauncherMainTaskDialog::EnableControls(bool)
0x18000a5e4  cmp     esi, 66h ; 'f'
0x18000a5e7  mov     rcx, rdi; this
0x18000a5ea  setz    dl; bool
0x18000a5ed  call    ?SetLauncherEnabled@CLauncherMainTaskDialog@ux@@AEAAX_N@Z; ux::CLauncherMainTaskDialog::SetLauncherEnabled(bool)
0x18000a5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5f9  cmp     rcx, rbp
0x18000a5fc  jz      short loc_18000A619
0x18000a5fe  test    byte ptr [rcx+1Ch], 8
0x18000a602  jz      short loc_18000A619
0x18000a604  mov     rcx, [rcx+10h]
0x18000a608  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a60f  mov     edx, 1Ch
0x18000a614  call    WPP_SF_
0x18000a619  mov     al, bl
0x18000a61b  add     rsp, 38h
0x18000a61f  pop     rdi
0x18000a620  pop     rsi
0x18000a621  pop     rbp
0x18000a622  pop     rbx
0x18000a623  retn
```

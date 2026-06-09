# ux::CLauncherMainTaskDialog::HandleException(ATL::CAtlException const &)

- ea: `0x18000a148`
- end: `0x18000a277`
- name: `?HandleException@CLauncherMainTaskDialog@ux@@AEBA_NAEBVCAtlException@ATL@@@Z`
- size: `303`
- prototype: `char __fastcall(ux::CLauncherMainTaskDialog *this, const struct ATL::CAtlException *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001066e`

## callees

- `0x180005528`
- `0x180008ac8`
- `0x180008c40`
- `0x18000a148`
- `0x18000ae20`
- `0x18000aed8`

## string_xrefs

- `0x18000a199`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`
- `0x18000a21c`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
char __fastcall ux::CLauncherMainTaskDialog::HandleException(
        ux::CLauncherMainTaskDialog *this,
        const struct ATL::CAtlException *a2)
{
  _QWORD *v4; // rcx
  char v5; // bl
  __int64 v6; // rcx
  const char *v7; // rax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      WPP_SF_sdD(
        v4[2],
        22,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        228,
        *(_DWORD *)a2);
      v4 = WPP_GLOBAL_Control;
    }
  }
  v5 = 1;
  if ( *(_DWORD *)a2 == -2147220992 )
  {
    ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog(this);
  }
  else
  {
    if ( *(_DWORD *)a2 == -2147023673 )
    {
      v5 = 0;
      goto LABEL_13;
    }
    ux::CLauncherMainTaskDialog::ShowErrorDialog(this, (int)a2, 214);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      v6 = v4[2];
      v7 = "Yes";
      if ( !v5 )
        v7 = "No";
      WPP_SF_sds(
        v6,
        23,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        248,
        (__int64)v7);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_(v4[2], 24, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a148  push    rbx
0x18000a14a  push    rbp
0x18000a14b  push    rsi
0x18000a14c  push    rdi
0x18000a14d  sub     rsp, 38h
0x18000a151  mov     rdi, rdx
0x18000a154  mov     rsi, rcx
0x18000a157  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a15e  lea     rbp, WPP_GLOBAL_Control
0x18000a165  cmp     rcx, rbp
0x18000a168  jz      short loc_18000A1C8
0x18000a16a  test    byte ptr [rcx+1Ch], 8
0x18000a16e  jz      short loc_18000A18C
0x18000a170  mov     rcx, [rcx+10h]
0x18000a174  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a17b  mov     edx, 15h
0x18000a180  call    WPP_SF_
0x18000a185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a18c  cmp     rcx, rbp
0x18000a18f  jz      short loc_18000A1C8
0x18000a191  test    byte ptr [rcx+1Ch], 4
0x18000a195  jz      short loc_18000A1C8
0x18000a197  mov     eax, [rdi]
0x18000a199  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a1a0  mov     rcx, [rcx+10h]
0x18000a1a4  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a1ab  mov     dword ptr [rsp+58h+var_30], eax
0x18000a1af  mov     edx, 16h
0x18000a1b4  mov     [rsp+58h+var_38], 0E4h
0x18000a1bc  call    WPP_SF_sdD
0x18000a1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c8  cmp     dword ptr [rdi], 80040200h
0x18000a1ce  mov     bl, 1
0x18000a1d0  jz      short loc_18000A1EE
0x18000a1d2  cmp     dword ptr [rdi], 800704C7h
0x18000a1d8  jz      short loc_18000A1EA
0x18000a1da  mov     r8d, 0D6h; int
0x18000a1e0  mov     rcx, rsi; this
0x18000a1e3  call    ?ShowErrorDialog@CLauncherMainTaskDialog@ux@@AEBAXHH@Z; ux::CLauncherMainTaskDialog::ShowErrorDialog(int,int)
0x18000a1e8  jmp     short loc_18000A1F6
0x18000a1ea  xor     bl, bl
0x18000a1ec  jmp     short loc_18000A1FD
0x18000a1ee  mov     rcx, rsi; this
0x18000a1f1  call    ?ShowLauncherIncompatibleErrorDialog@CLauncherMainTaskDialog@ux@@AEBAXXZ; ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog(void)
0x18000a1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1fd  cmp     rcx, rbp
0x18000a200  jz      short loc_18000A26C
0x18000a202  test    byte ptr [rcx+1Ch], 4
0x18000a206  jz      short loc_18000A24C
0x18000a208  mov     rcx, [rcx+10h]
0x18000a20c  lea     rdx, aNo; "No"
0x18000a213  test    bl, bl
0x18000a215  lea     rax, aYes_0; "Yes"
0x18000a21c  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a223  cmovz   rax, rdx
0x18000a227  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a22e  mov     [rsp+58h+var_30], rax
0x18000a233  mov     edx, 17h
0x18000a238  mov     [rsp+58h+var_38], 0F8h
0x18000a240  call    WPP_SF_sds
0x18000a245  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a24c  cmp     rcx, rbp
0x18000a24f  jz      short loc_18000A26C
0x18000a251  test    byte ptr [rcx+1Ch], 8
0x18000a255  jz      short loc_18000A26C
0x18000a257  mov     rcx, [rcx+10h]
0x18000a25b  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a262  mov     edx, 18h
0x18000a267  call    WPP_SF_
0x18000a26c  mov     al, bl
0x18000a26e  add     rsp, 38h
0x18000a272  pop     rdi
0x18000a273  pop     rsi
0x18000a274  pop     rbp
0x18000a275  pop     rbx
0x18000a276  retn
```

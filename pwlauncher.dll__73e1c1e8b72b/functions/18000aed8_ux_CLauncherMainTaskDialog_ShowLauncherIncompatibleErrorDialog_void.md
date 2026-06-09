# ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog(void)

- ea: `0x18000aed8`
- end: `0x18000b044`
- name: `?ShowLauncherIncompatibleErrorDialog@CLauncherMainTaskDialog@ux@@AEBAXXZ`
- size: `364`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a148`

## callees

- `0x180008ac8`
- `0x180008d9c`
- `0x180009974`
- `0x18000aed8`
- `0x18000fdd6`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog(ux::CLauncherMainTaskDialog *this)
{
  _QWORD *v2; // rbx
  void **v3; // [rsp+30h] [rbp-79h] BYREF
  int v4; // [rsp+38h] [rbp-71h] BYREF
  __int64 v5; // [rsp+3Ch] [rbp-6Dh]
  void *v6; // [rsp+44h] [rbp-65h]
  unsigned int v7; // [rsp+4Ch] [rbp-5Dh]
  int v8; // [rsp+50h] [rbp-59h]
  __int64 v9; // [rsp+54h] [rbp-55h]
  __int64 v10; // [rsp+5Ch] [rbp-4Dh]
  __int64 v11; // [rsp+64h] [rbp-45h]
  __int64 v12; // [rsp+6Ch] [rbp-3Dh]
  __int64 v13; // [rsp+9Ch] [rbp-Dh]
  void *v14; // [rsp+C4h] [rbp+1Bh]
  void ***v15; // [rsp+CCh] [rbp+23h]
  __int64 v16; // [rsp+D8h] [rbp+2Fh]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  memset_0(&v4, 0, 0xA0u);
  v4 = 160;
  v6 = off_180019130;
  v16 = 0;
  v5 = 0;
  v14 = &WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback;
  v15 = &v3;
  v3 = &ux::CLauncherErrorTaskDialog::`vftable';
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_(v2[2], 37, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v9 = 202;
  v11 = 208;
  v12 = 214;
  v8 = 32;
  v7 = v7 & 0xFFFFFFFC | 1;
  v10 = 65534;
  v13 = 219;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(v2[2], 38, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal((__int64)&v4, *((_QWORD *)this + 21));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)&v3);
}

```

## disassembly

```asm
0x18000aed8  push    rbp
0x18000aeda  push    rbx
0x18000aedb  push    rdi
0x18000aedc  push    r12
0x18000aede  lea     rbp, [rsp-3Fh]
0x18000aee3  sub     rsp, 0E8h
0x18000aeea  mov     rdi, rcx
0x18000aeed  lea     r12, WPP_GLOBAL_Control
0x18000aef4  mov     rbx, cs:WPP_GLOBAL_Control
0x18000aefb  cmp     rbx, r12
0x18000aefe  jz      short loc_18000AF22
0x18000af00  test    byte ptr [rbx+1Ch], 8
0x18000af04  jz      short loc_18000AF22
0x18000af06  mov     edx, 13h
0x18000af0b  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000af12  mov     rcx, [rbx+10h]
0x18000af16  call    WPP_SF_
0x18000af1b  mov     rbx, cs:WPP_GLOBAL_Control
0x18000af22  xor     edx, edx; Val
0x18000af24  mov     r8d, 0A0h; Size
0x18000af2a  lea     rcx, [rbp+57h+var_C8]; void *
0x18000af2e  call    memset_0
0x18000af33  mov     [rbp+57h+var_C8], 0A0h
0x18000af3a  mov     rax, cs:off_180019130
0x18000af41  mov     [rbp+57h+var_BC], rax
0x18000af45  mov     [rbp+57h+var_28], 0
0x18000af4d  mov     [rbp+57h+var_C4], 0
0x18000af55  lea     rax, ?TaskDialogCallback@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@SAJPEAUHWND__@@I_K_J2@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000af5c  mov     [rbp+57h+var_3C], rax
0x18000af60  lea     rax, [rbp+57h+var_D0]
0x18000af64  mov     [rbp+57h+var_34], rax
0x18000af68  lea     rax, ??_7CLauncherErrorTaskDialog@ux@@6B@; const ux::CLauncherErrorTaskDialog::`vftable'
0x18000af6f  mov     [rbp+57h+var_D0], rax
0x18000af73  cmp     rbx, r12
0x18000af76  jz      short loc_18000AF9A
0x18000af78  test    byte ptr [rbx+1Ch], 8
0x18000af7c  jz      short loc_18000AF9A
0x18000af7e  mov     edx, 25h ; '%'
0x18000af83  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000af8a  mov     rcx, [rbx+10h]
0x18000af8e  call    WPP_SF_
0x18000af93  mov     rbx, cs:WPP_GLOBAL_Control
0x18000af9a  mov     [rbp+57h+var_AC], 0CAh
0x18000afa2  mov     [rbp+57h+var_9C], 0D0h
0x18000afaa  mov     [rbp+57h+var_94], 0D6h
0x18000afb2  mov     [rbp+57h+var_B0], 20h ; ' '
0x18000afb9  mov     eax, [rbp+57h+var_B4]
0x18000afbc  and     eax, 0FFFFFFFDh
0x18000afbf  or      eax, 1
0x18000afc2  mov     [rbp+57h+var_B4], eax
0x18000afc5  mov     [rbp+57h+var_A4], 0FFFEh
0x18000afcd  mov     [rbp+57h+var_64], 0DBh
0x18000afd5  cmp     rbx, r12
0x18000afd8  jz      short loc_18000AFF6
0x18000afda  test    byte ptr [rbx+1Ch], 8
0x18000afde  jz      short loc_18000AFF6
0x18000afe0  mov     edx, 26h ; '&'
0x18000afe5  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000afec  mov     rcx, [rbx+10h]
0x18000aff0  call    WPP_SF_
0x18000aff5  nop
0x18000aff6  mov     rdx, [rdi+0A8h]
0x18000affd  lea     rcx, [rbp+57h+var_C8]
0x18000b001  call    ?DoModal@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@QEAAJPEAUHWND__@@PEAH11@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(HWND__ *,int *,int *,int *)
0x18000b006  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b00d  cmp     rcx, r12
0x18000b010  jz      short loc_18000B02E
0x18000b012  test    byte ptr [rcx+1Ch], 8
0x18000b016  jz      short loc_18000B02E
0x18000b018  mov     edx, 14h
0x18000b01d  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000b024  mov     rcx, [rcx+10h]
0x18000b028  call    WPP_SF_
0x18000b02d  nop
0x18000b02e  lea     rcx, [rbp+57h+var_D0]; this
0x18000b032  call    ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
0x18000b037  add     rsp, 0E8h
0x18000b03e  pop     r12
0x18000b040  pop     rdi
0x18000b041  pop     rbx
0x18000b042  pop     rbp
0x18000b043  retn
```

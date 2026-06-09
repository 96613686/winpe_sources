# ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(int,int)

- ea: `0x180009360`
- end: `0x180009465`
- name: `??0CLauncherErrorTaskDialog@ux@@QEAA@HH@Z`
- size: `261`
- prototype: `unsigned __int64 __fastcall(unsigned __int64 this, unsigned __int16, unsigned __int16)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008e20`
- `0x18000ae20`
- `0x18001035e`

## callees

- `0x180008ac8`
- `0x180009360`
- `0x18000fdd6`

## pseudocode

```c
unsigned __int64 __fastcall ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(
        unsigned __int64 this,
        unsigned __int16 a2,
        unsigned __int16 a3)
{
  unsigned int v6; // eax

  memset_0((void *)(this + 12), 0, 0x9Cu);
  *(_DWORD *)(this + 8) = 160;
  *(_QWORD *)(this + 20) = off_180019130;
  *(_QWORD *)(this + 148) = &WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback;
  *(_QWORD *)(this + 168) = 0;
  *(_QWORD *)(this + 12) = 0;
  *(_QWORD *)(this + 156) = this & -(__int64)(this != -8);
  *(_QWORD *)this = &ux::CLauncherErrorTaskDialog::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  *(_QWORD *)(this + 52) = a2;
  *(_QWORD *)(this + 60) = a3;
  v6 = *(_DWORD *)(this + 28) & 0xFFFFFFFD;
  *(_QWORD *)(this + 36) = 202;
  *(_DWORD *)(this + 32) = 32;
  *(_DWORD *)(this + 28) = v6 | 1;
  *(_QWORD *)(this + 44) = 65534;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  return this;
}

```

## disassembly

```asm
0x180009360  push    rbx
0x180009362  push    rbp
0x180009363  push    rsi
0x180009364  push    rdi
0x180009365  sub     rsp, 28h
0x180009369  mov     esi, r8d
0x18000936c  mov     rdi, rcx
0x18000936f  mov     ebp, edx
0x180009371  add     rcx, 0Ch; void *
0x180009375  xor     edx, edx; Val
0x180009377  mov     r8d, 9Ch; Size
0x18000937d  call    memset_0
0x180009382  mov     dword ptr [rdi+8], 0A0h
0x180009389  mov     rax, cs:off_180019130
0x180009390  mov     [rdi+14h], rax
0x180009394  lea     rax, ?TaskDialogCallback@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@SAJPEAUHWND__@@I_K_J2@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000939b  mov     [rdi+94h], rax
0x1800093a2  lea     rax, [rdi+8]
0x1800093a6  neg     rax
0x1800093a9  mov     qword ptr [rdi+0A8h], 0
0x1800093b4  lea     rax, ??_7CLauncherErrorTaskDialog@ux@@6B@; const ux::CLauncherErrorTaskDialog::`vftable'
0x1800093bb  mov     qword ptr [rdi+0Ch], 0
0x1800093c3  sbb     rcx, rcx
0x1800093c6  and     rcx, rdi
0x1800093c9  mov     [rdi+9Ch], rcx
0x1800093d0  mov     [rdi], rax
0x1800093d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093da  lea     rbx, WPP_GLOBAL_Control
0x1800093e1  cmp     rcx, rbx
0x1800093e4  jz      short loc_180009401
0x1800093e6  test    byte ptr [rcx+1Ch], 8
0x1800093ea  jz      short loc_180009401
0x1800093ec  mov     rcx, [rcx+10h]
0x1800093f0  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x1800093f7  mov     edx, 23h ; '#'
0x1800093fc  call    WPP_SF_
0x180009401  movzx   eax, bp
0x180009404  mov     [rdi+34h], rax
0x180009408  movzx   eax, si
0x18000940b  mov     [rdi+3Ch], rax
0x18000940f  mov     eax, [rdi+1Ch]
0x180009412  and     eax, 0FFFFFFFDh
0x180009415  mov     qword ptr [rdi+24h], 0CAh
0x18000941d  or      eax, 1
0x180009420  mov     dword ptr [rdi+20h], 20h ; ' '
0x180009427  mov     [rdi+1Ch], eax
0x18000942a  mov     qword ptr [rdi+2Ch], 0FFFEh
0x180009432  mov     rcx, cs:WPP_GLOBAL_Control
0x180009439  cmp     rcx, rbx
0x18000943c  jz      short loc_180009459
0x18000943e  test    byte ptr [rcx+1Ch], 8
0x180009442  jz      short loc_180009459
0x180009444  mov     rcx, [rcx+10h]
0x180009448  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000944f  mov     edx, 24h ; '$'
0x180009454  call    WPP_SF_
0x180009459  mov     rax, rdi
0x18000945c  add     rsp, 28h
0x180009460  pop     rdi
0x180009461  pop     rsi
0x180009462  pop     rbp
0x180009463  pop     rbx
0x180009464  retn
```

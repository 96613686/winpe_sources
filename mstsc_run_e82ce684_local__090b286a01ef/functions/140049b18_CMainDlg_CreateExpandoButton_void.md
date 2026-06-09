# CMainDlg::CreateExpandoButton(void)

- ea: `0x140049b18`
- end: `0x140049f44`
- name: `?CreateExpandoButton@CMainDlg@@AEAAHXZ`
- size: `1068`
- prototype: `__int64 __fastcall(CMainDlg *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140049fa0`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x140049b18`
- `0x14004c2f4`
- `0x14004c9dc`
- `0x140097c30`
- `0x1400fcad0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!ShowWindow` at `0x140049ee7`
- `USER32!ShowWindow` at `0x140049ef5`
- `USER32!ShowWindow` at `0x140049ee7`
- `USER32!ShowWindow` at `0x140049ef5`
- `USER32!GetDlgItem` at `0x140049b6d`
- `USER32!GetDlgItem` at `0x140049bb1`
- `USER32!GetDlgItem` at `0x140049b6d`
- `USER32!GetDlgItem` at `0x140049bb1`
- `USER32!SendMessageW` at `0x140049bd2`
- `USER32!SendMessageW` at `0x140049be7`
- `USER32!SendMessageW` at `0x140049c0e`
- `USER32!SendMessageW` at `0x140049c22`
- `USER32!SendMessageW` at `0x140049c3d`
- `USER32!SendMessageW` at `0x140049c74`
- `USER32!SendMessageW` at `0x140049c8c`
- `USER32!SendMessageW` at `0x140049cc7`
- `USER32!SendMessageW` at `0x140049cdf`
- `USER32!SendMessageW` at `0x140049cf2`
- `USER32!SendMessageW` at `0x140049d43`
- `USER32!SendMessageW` at `0x140049bd2`
- `USER32!SendMessageW` at `0x140049be7`
- `USER32!SendMessageW` at `0x140049c0e`
- `USER32!SendMessageW` at `0x140049c22`
- `USER32!SendMessageW` at `0x140049c3d`
- `USER32!SendMessageW` at `0x140049c74`
- `USER32!SendMessageW` at `0x140049c8c`
- `USER32!SendMessageW` at `0x140049cc7`
- `USER32!SendMessageW` at `0x140049cdf`
- `USER32!SendMessageW` at `0x140049cf2`
- `USER32!SendMessageW` at `0x140049d43`
- `ole32!CoCreateInstance` at `0x140049d79`
- `ole32!CoCreateInstance` at `0x140049d79`

## string_xrefs

- `0x140049e64`: `Failed to set hide options accessible name`

## pseudocode

```c
__int64 __fastcall CMainDlg::CreateExpandoButton(CMainDlg *this)
{
  HWND v2; // rcx
  HWND *v3; // rbx
  HWND DlgItem; // r14
  int v5; // r15d
  int v6; // eax
  struct _IMAGELIST *ImageList32BitColors; // rax
  HWND v8; // rcx
  LRESULT v9; // rax
  HWND v10; // rcx
  bool v11; // zf
  unsigned int v12; // eax
  __int64 v13; // rax
  HWND v14; // rdx
  int v15; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v17; // edi
  unsigned int v18; // eax
  LPVOID v19; // rcx
  __int64 v21; // [rsp+28h] [rbp-D8h]
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v23[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __m256i lParam; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v28[256]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v29[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(v28, 0, sizeof(v28));
  v2 = (HWND)*((_QWORD *)this + 1);
  ppv = 0;
  v3 = (HWND *)((char *)this + 616);
  DlgItem = GetDlgItem(v2, 5014);
  v5 = -(*((_DWORD *)this + 24) != 0);
  if ( TSLoadString(*((HINSTANCE *)this + 4), 1102 - (*((_DWORD *)this + 24) != 0), v28, 256) )
    *v3 = GetDlgItem(*((HWND *)this + 1), 5017);
  if ( *v3 )
  {
    SendMessageW(*v3, 0x41Eu, 0x20u, 0);
    SendMessageW(*v3, 0x43Cu, 1u, 0);
    SendMessageW(*v3, 0x420u, 0, *((unsigned __int16 *)this + 316) | (*((unsigned __int16 *)this + 318) << 16));
    v6 = SendMessageW(*v3, 0x456u, 0, 0);
    SendMessageW(*v3, 0x457u, 0, v6 & 0xFFFFFFFFFFFF0000uLL);
    ImageList32BitColors = LoadImageList32BitColors(
                             *((HINSTANCE *)this + 4),
                             (const unsigned __int16 *)*((unsigned __int16 *)this + 320),
                             *((_DWORD *)this + 158));
    *((_QWORD *)this + 78) = ImageList32BitColors;
    if ( ImageList32BitColors )
    {
      SendMessageW(*v3, 0x430u, 0, (LPARAM)ImageList32BitColors);
      SendMessageW(*v3, 0x436u, 0, *((_QWORD *)this + 78));
      v8 = *v3;
      lParam.m256i_i64[0] = 0x139A00000000LL;
      lParam.m256i_i32[2] = 4100;
      memset((char *)&lParam.m256i_u64[1] + 4, 0, 20);
      SendMessageW(v8, 0x444u, 1u, (LPARAM)&lParam);
    }
    if ( DlgItem )
    {
      v9 = SendMessageW(DlgItem, 0x31u, 0, 0);
      SendMessageW(*v3, 0x30u, v9, 0);
    }
    v10 = *v3;
    v25 = v28;
    *(_QWORD *)&v23[1] = 3;
    v11 = *((_DWORD *)this + 24) == 0;
    v26 = 256;
    v23[0] = 48;
    v23[3] = !v11;
    v24 = 0;
    SendMessageW(v10, 0x440u, 0x139Au, (LPARAM)v23);
    CMainDlg::PositionExpandoButton(this, 0);
    CMainDlg::SetExpandoButtonBitmap(this);
    if ( CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &GUID_6e26e776_04f0_495d_80e4_3330352e3169, &ppv) >= 0 )
    {
      if ( TSLoadString(*((HINSTANCE *)this + 4), v5 + 1104, v29, 260) )
      {
        v13 = *(_QWORD *)ppv;
        v14 = *v3;
        *(GUID *)lParam.m256i_i8 = PROPID_ACC_NAME;
        v15 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64, _QWORD, __m256i *, unsigned __int16 *))(v13 + 56))(
                ppv,
                v14,
                4294967292LL,
                0,
                &lParam,
                v29);
        if ( v15 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v21) = v15;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_ff2496e086463c752882f855d2d17187_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"Failed to set hide options accessible name",
            v21);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v12);
      }
    }
    v17 = 1;
  }
  else
  {
    v17 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v18);
    }
    if ( *v3 )
      ShowWindow(*v3, 0);
    ShowWindow(DlgItem, 4);
  }
  v19 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return v17;
}

```

## disassembly

```asm
0x140049b18  mov     [rsp-8+arg_8], rbx
0x140049b1d  mov     [rsp-8+arg_10], rdi
0x140049b22  push    rbp
0x140049b23  push    r14
0x140049b25  push    r15
0x140049b27  lea     rbp, [rsp-3C0h]
0x140049b2f  sub     rsp, 4C0h
0x140049b36  mov     rax, cs:__security_cookie
0x140049b3d  xor     rax, rsp
0x140049b40  mov     [rbp+3D0h+var_20], rax
0x140049b47  mov     rdi, rcx
0x140049b4a  xor     edx, edx; Val
0x140049b4c  lea     rcx, [rbp+3D0h+var_430]; void *
0x140049b50  mov     r8d, 200h; Size
0x140049b56  call    memset_0
0x140049b5b  mov     rcx, [rdi+8]; hDlg
0x140049b5f  mov     edx, 1396h; nIDDlgItem
0x140049b64  mov     [rsp+4D0h+var_490], 0
0x140049b6d  call    cs:__imp_GetDlgItem
0x140049b73  mov     edx, [rdi+60h]
0x140049b76  lea     r8, [rbp+3D0h+var_430]; unsigned __int16 *
0x140049b7a  mov     ecx, edx
0x140049b7c  lea     rbx, [rdi+268h]
0x140049b83  neg     ecx
0x140049b85  mov     r9d, 100h; int
0x140049b8b  mov     rcx, [rdi+20h]; HINSTANCE
0x140049b8f  mov     r14, rax
0x140049b92  sbb     r15d, r15d
0x140049b95  neg     edx
0x140049b97  sbb     edx, edx
0x140049b99  add     edx, 44Eh; unsigned int
0x140049b9f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140049ba4  test    eax, eax
0x140049ba6  jz      short loc_140049BBA
0x140049ba8  mov     rcx, [rdi+8]; hDlg
0x140049bac  mov     edx, 1399h; nIDDlgItem
0x140049bb1  call    cs:__imp_GetDlgItem
0x140049bb7  mov     [rbx], rax
0x140049bba  mov     rcx, [rbx]; hWnd
0x140049bbd  test    rcx, rcx
0x140049bc0  jz      loc_140049E9A
0x140049bc6  xor     r9d, r9d; lParam
0x140049bc9  mov     edx, 41Eh; Msg
0x140049bce  lea     r8d, [r9+20h]; wParam
0x140049bd2  call    cs:__imp_SendMessageW
0x140049bd8  mov     rcx, [rbx]; hWnd
0x140049bdb  xor     r9d, r9d; lParam
0x140049bde  mov     edx, 43Ch; Msg
0x140049be3  lea     r8d, [r9+1]; wParam
0x140049be7  call    cs:__imp_SendMessageW
0x140049bed  movzx   ecx, word ptr [rdi+27Ch]
0x140049bf4  xor     r8d, r8d; wParam
0x140049bf7  movzx   eax, word ptr [rdi+278h]
0x140049bfe  mov     edx, 420h; Msg
0x140049c03  shl     ecx, 10h
0x140049c06  or      ecx, eax
0x140049c08  movsxd  r9, ecx; lParam
0x140049c0b  mov     rcx, [rbx]; hWnd
0x140049c0e  call    cs:__imp_SendMessageW
0x140049c14  mov     rcx, [rbx]; hWnd
0x140049c17  xor     r9d, r9d; lParam
0x140049c1a  xor     r8d, r8d; wParam
0x140049c1d  mov     edx, 456h; Msg
0x140049c22  call    cs:__imp_SendMessageW
0x140049c28  mov     rcx, [rbx]; hWnd
0x140049c2b  xor     r8d, r8d; wParam
0x140049c2e  movsxd  r9, eax
0x140049c31  mov     edx, 457h; Msg
0x140049c36  and     r9, 0FFFFFFFFFFFF0000h; lParam
0x140049c3d  call    cs:__imp_SendMessageW
0x140049c43  movzx   edx, word ptr [rdi+280h]; unsigned __int16 *
0x140049c4a  mov     r8d, [rdi+278h]; int
0x140049c51  mov     rcx, [rdi+20h]; HINSTANCE
0x140049c55  call    ?LoadImageList32BitColors@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGH@Z; LoadImageList32BitColors(HINSTANCE__ *,ushort const *,int)
0x140049c5a  mov     [rdi+270h], rax
0x140049c61  test    rax, rax
0x140049c64  jz      short loc_140049CCD
0x140049c66  mov     rcx, [rbx]; hWnd
0x140049c69  mov     r9, rax; lParam
0x140049c6c  xor     r8d, r8d; wParam
0x140049c6f  mov     edx, 430h; Msg
0x140049c74  call    cs:__imp_SendMessageW
0x140049c7a  mov     r9, [rdi+270h]; lParam
0x140049c81  xor     r8d, r8d; wParam
0x140049c84  mov     rcx, [rbx]; hWnd
0x140049c87  mov     edx, 436h; Msg
0x140049c8c  call    cs:__imp_SendMessageW
0x140049c92  mov     rcx, [rbx]; hWnd
0x140049c95  lea     r9, [rbp+3D0h+lParam]; lParam
0x140049c99  xor     eax, eax
0x140049c9b  mov     dword ptr [rbp+3D0h+lParam], 0
0x140049ca2  xorps   xmm0, xmm0
0x140049ca5  mov     dword ptr [rbp+3D0h+lParam+4], 139Ah
0x140049cac  movups  xmmword ptr [rbp+3D0h+lParam+0Dh], xmm0
0x140049cb0  mov     edx, 444h; Msg
0x140049cb5  mov     dword ptr [rbp+3D0h+lParam+8], 1004h
0x140049cbc  lea     r8d, [rax+1]; wParam
0x140049cc0  mov     byte ptr [rbp+3D0h+lParam+0Ch], 0
0x140049cc4  mov     [rbp+3D0h+var_434], eax
0x140049cc7  call    cs:__imp_SendMessageW
0x140049ccd  test    r14, r14
0x140049cd0  jz      short loc_140049CF8
0x140049cd2  xor     r9d, r9d; lParam
0x140049cd5  xor     r8d, r8d; wParam
0x140049cd8  mov     rcx, r14; hWnd
0x140049cdb  lea     edx, [r9+31h]; Msg
0x140049cdf  call    cs:__imp_SendMessageW
0x140049ce5  mov     rcx, [rbx]; hWnd
0x140049ce8  xor     r9d, r9d; lParam
0x140049ceb  mov     r8, rax; wParam
0x140049cee  lea     edx, [r9+30h]; Msg
0x140049cf2  call    cs:__imp_SendMessageW
0x140049cf8  mov     rcx, [rbx]; hWnd
0x140049cfb  lea     rax, [rbp+3D0h+var_430]
0x140049cff  mov     [rsp+4D0h+var_468], rax
0x140049d04  lea     r9, [rsp+4D0h+var_488]; lParam
0x140049d09  xor     eax, eax
0x140049d0b  mov     qword ptr [rsp+4D0h+var_488+4], 3
0x140049d14  cmp     [rdi+60h], eax
0x140049d17  xorps   xmm0, xmm0
0x140049d1a  mov     edx, 440h; Msg
0x140049d1f  mov     [rsp+4D0h+var_460], 100h
0x140049d28  setnz   al
0x140049d2b  mov     dword ptr [rsp+4D0h+var_488], 30h ; '0'
0x140049d33  mov     r8d, 139Ah; wParam
0x140049d39  mov     [rsp+4D0h+var_47C], eax
0x140049d3d  movdqu  [rsp+4D0h+var_478], xmm0
0x140049d43  call    cs:__imp_SendMessageW
0x140049d49  xor     edx, edx; int
0x140049d4b  mov     rcx, rdi; this
0x140049d4e  call    ?PositionExpandoButton@CMainDlg@@AEAAXH@Z; CMainDlg::PositionExpandoButton(int)
0x140049d53  mov     rcx, rdi; this
0x140049d56  call    ?SetExpandoButtonBitmap@CMainDlg@@AEAAXXZ; CMainDlg::SetExpandoButtonBitmap(void)
0x140049d5b  xor     edx, edx; pUnkOuter
0x140049d5d  lea     rax, [rsp+4D0h+var_490]
0x140049d62  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x140049d69  mov     [rsp+4D0h+ppv], rax; ppv
0x140049d6e  lea     rcx, CLSID_AccPropServices; rclsid
0x140049d75  lea     r8d, [rdx+15h]; dwClsContext
0x140049d79  call    cs:__imp_CoCreateInstance
0x140049d7f  test    eax, eax
0x140049d81  js      loc_140049E93
0x140049d87  mov     rcx, [rdi+20h]; HINSTANCE
0x140049d8b  lea     r8, [rbp+3D0h+var_230]; unsigned __int16 *
0x140049d92  mov     r9d, 104h; int
0x140049d98  lea     edx, [r15+450h]; unsigned int
0x140049d9f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140049da4  test    eax, eax
0x140049da6  jnz     short loc_140049DFC
0x140049da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140049daf  lea     rax, WPP_GLOBAL_Control
0x140049db6  cmp     rcx, rax
0x140049db9  jz      loc_140049E93
0x140049dbf  test    byte ptr [rcx+1Ch], 1
0x140049dc3  jz      loc_140049E93
0x140049dc9  cmp     byte ptr [rcx+19h], 2
0x140049dcd  jb      loc_140049E93
0x140049dd3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140049dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ddf  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140049de6  mov     edx, 1Ch
0x140049deb  mov     r9d, eax
0x140049dee  mov     rcx, [rcx+10h]
0x140049df2  call    WPP_SF_d
0x140049df7  jmp     loc_140049E93
0x140049dfc  mov     rcx, [rsp+4D0h+var_490]
0x140049e01  lea     rdx, [rbp+3D0h+var_230]
0x140049e08  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x140049e0f  mov     [rsp+4D0h+var_4A8], rdx
0x140049e14  xor     r9d, r9d
0x140049e17  lea     rdx, [rbp+3D0h+lParam]
0x140049e1b  mov     r8d, 0FFFFFFFCh
0x140049e21  mov     rax, [rcx]
0x140049e24  mov     [rsp+4D0h+ppv], rdx
0x140049e29  mov     rdx, [rbx]
0x140049e2c  movdqu  xmmword ptr [rbp+3D0h+lParam], xmm0
0x140049e31  mov     rax, [rax+38h]
0x140049e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049e3a  mov     ebx, eax
0x140049e3c  test    eax, eax
0x140049e3e  jns     short loc_140049E93
0x140049e40  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e47  lea     rax, WPP_GLOBAL_Control
0x140049e4e  cmp     rcx, rax
0x140049e51  jz      short loc_140049E93
0x140049e53  test    byte ptr [rcx+1Ch], 8
0x140049e57  jz      short loc_140049E93
0x140049e59  cmp     byte ptr [rcx+19h], 2
0x140049e5d  jb      short loc_140049E93
0x140049e5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140049e64  lea     rcx, aFailedToSetHid; "Failed to set hide options accessible n"...
0x140049e6b  mov     dword ptr [rsp+4D0h+var_4A8], ebx
0x140049e6f  mov     [rsp+4D0h+ppv], rcx
0x140049e74  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140049e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e82  mov     edx, 1Dh
0x140049e87  mov     r9d, eax
0x140049e8a  mov     rcx, [rcx+10h]
0x140049e8e  call    WPP_SF_DsD
0x140049e93  mov     edi, 1
0x140049e98  jmp     short loc_140049EFB
0x140049e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ea1  lea     rax, WPP_GLOBAL_Control
0x140049ea8  xor     edi, edi
0x140049eaa  cmp     rcx, rax
0x140049ead  jz      short loc_140049EDD
0x140049eaf  test    byte ptr [rcx+1Ch], 1
0x140049eb3  jz      short loc_140049EDD
0x140049eb5  cmp     byte ptr [rcx+19h], 2
0x140049eb9  jb      short loc_140049EDD
0x140049ebb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140049ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ec7  lea     edx, [rdi+1Eh]
0x140049eca  mov     r9d, eax
0x140049ecd  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140049ed4  mov     rcx, [rcx+10h]
0x140049ed8  call    WPP_SF_d
0x140049edd  mov     rcx, [rbx]; hWnd
0x140049ee0  test    rcx, rcx
0x140049ee3  jz      short loc_140049EED
0x140049ee5  xor     edx, edx; nCmdShow
0x140049ee7  call    cs:__imp_ShowWindow
0x140049eed  mov     edx, 4; nCmdShow
0x140049ef2  mov     rcx, r14; hWnd
0x140049ef5  call    cs:__imp_ShowWindow
0x140049efb  mov     rcx, [rsp+4D0h+var_490]
0x140049f00  test    rcx, rcx
0x140049f03  jz      short loc_140049F1A
0x140049f05  mov     [rsp+4D0h+var_490], 0
0x140049f0e  mov     rdx, [rcx]
0x140049f11  mov     rax, [rdx+10h]
0x140049f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049f1a  mov     eax, edi
0x140049f1c  mov     rcx, [rbp+3D0h+var_20]
0x140049f23  xor     rcx, rsp; StackCookie
0x140049f26  call    __security_check_cookie
0x140049f2b  lea     r11, [rsp+4D0h+var_10]
0x140049f33  mov     rbx, [r11+28h]
0x140049f37  mov     rdi, [r11+30h]
0x140049f3b  mov     rsp, r11
0x140049f3e  pop     r15
0x140049f40  pop     r14
0x140049f42  pop     rbp
0x140049f43  retn
```

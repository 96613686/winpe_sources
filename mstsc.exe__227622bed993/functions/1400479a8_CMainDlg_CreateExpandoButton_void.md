# CMainDlg::CreateExpandoButton(void)

- ea: `0x1400479a8`
- end: `0x140047dd4`
- name: `?CreateExpandoButton@CMainDlg@@AEAAHXZ`
- size: `1068`
- prototype: `__int64 __fastcall(CMainDlg *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140047e30`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400479a8`
- `0x14004a184`
- `0x14004a86c`
- `0x140095ac0`
- `0x1400fa960`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!ShowWindow` at `0x140047d77`
- `USER32!ShowWindow` at `0x140047d85`
- `USER32!ShowWindow` at `0x140047d77`
- `USER32!ShowWindow` at `0x140047d85`
- `USER32!GetDlgItem` at `0x1400479fd`
- `USER32!GetDlgItem` at `0x140047a41`
- `USER32!GetDlgItem` at `0x1400479fd`
- `USER32!GetDlgItem` at `0x140047a41`
- `USER32!SendMessageW` at `0x140047a62`
- `USER32!SendMessageW` at `0x140047a77`
- `USER32!SendMessageW` at `0x140047a9e`
- `USER32!SendMessageW` at `0x140047ab2`
- `USER32!SendMessageW` at `0x140047acd`
- `USER32!SendMessageW` at `0x140047b04`
- `USER32!SendMessageW` at `0x140047b1c`
- `USER32!SendMessageW` at `0x140047b57`
- `USER32!SendMessageW` at `0x140047b6f`
- `USER32!SendMessageW` at `0x140047b82`
- `USER32!SendMessageW` at `0x140047bd3`
- `USER32!SendMessageW` at `0x140047a62`
- `USER32!SendMessageW` at `0x140047a77`
- `USER32!SendMessageW` at `0x140047a9e`
- `USER32!SendMessageW` at `0x140047ab2`
- `USER32!SendMessageW` at `0x140047acd`
- `USER32!SendMessageW` at `0x140047b04`
- `USER32!SendMessageW` at `0x140047b1c`
- `USER32!SendMessageW` at `0x140047b57`
- `USER32!SendMessageW` at `0x140047b6f`
- `USER32!SendMessageW` at `0x140047b82`
- `USER32!SendMessageW` at `0x140047bd3`
- `ole32!CoCreateInstance` at `0x140047c09`
- `ole32!CoCreateInstance` at `0x140047c09`

## string_xrefs

- `0x140047cf4`: `Failed to set hide options accessible name`

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
0x1400479a8  mov     [rsp-8+arg_8], rbx
0x1400479ad  mov     [rsp-8+arg_10], rdi
0x1400479b2  push    rbp
0x1400479b3  push    r14
0x1400479b5  push    r15
0x1400479b7  lea     rbp, [rsp-3C0h]
0x1400479bf  sub     rsp, 4C0h
0x1400479c6  mov     rax, cs:__security_cookie
0x1400479cd  xor     rax, rsp
0x1400479d0  mov     [rbp+3D0h+var_20], rax
0x1400479d7  mov     rdi, rcx
0x1400479da  xor     edx, edx; Val
0x1400479dc  lea     rcx, [rbp+3D0h+var_430]; void *
0x1400479e0  mov     r8d, 200h; Size
0x1400479e6  call    memset_0
0x1400479eb  mov     rcx, [rdi+8]; hDlg
0x1400479ef  mov     edx, 1396h; nIDDlgItem
0x1400479f4  mov     [rsp+4D0h+var_490], 0
0x1400479fd  call    cs:__imp_GetDlgItem
0x140047a03  mov     edx, [rdi+60h]
0x140047a06  lea     r8, [rbp+3D0h+var_430]; unsigned __int16 *
0x140047a0a  mov     ecx, edx
0x140047a0c  lea     rbx, [rdi+268h]
0x140047a13  neg     ecx
0x140047a15  mov     r9d, 100h; int
0x140047a1b  mov     rcx, [rdi+20h]; HINSTANCE
0x140047a1f  mov     r14, rax
0x140047a22  sbb     r15d, r15d
0x140047a25  neg     edx
0x140047a27  sbb     edx, edx
0x140047a29  add     edx, 44Eh; unsigned int
0x140047a2f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140047a34  test    eax, eax
0x140047a36  jz      short loc_140047A4A
0x140047a38  mov     rcx, [rdi+8]; hDlg
0x140047a3c  mov     edx, 1399h; nIDDlgItem
0x140047a41  call    cs:__imp_GetDlgItem
0x140047a47  mov     [rbx], rax
0x140047a4a  mov     rcx, [rbx]; hWnd
0x140047a4d  test    rcx, rcx
0x140047a50  jz      loc_140047D2A
0x140047a56  xor     r9d, r9d; lParam
0x140047a59  mov     edx, 41Eh; Msg
0x140047a5e  lea     r8d, [r9+20h]; wParam
0x140047a62  call    cs:__imp_SendMessageW
0x140047a68  mov     rcx, [rbx]; hWnd
0x140047a6b  xor     r9d, r9d; lParam
0x140047a6e  mov     edx, 43Ch; Msg
0x140047a73  lea     r8d, [r9+1]; wParam
0x140047a77  call    cs:__imp_SendMessageW
0x140047a7d  movzx   ecx, word ptr [rdi+27Ch]
0x140047a84  xor     r8d, r8d; wParam
0x140047a87  movzx   eax, word ptr [rdi+278h]
0x140047a8e  mov     edx, 420h; Msg
0x140047a93  shl     ecx, 10h
0x140047a96  or      ecx, eax
0x140047a98  movsxd  r9, ecx; lParam
0x140047a9b  mov     rcx, [rbx]; hWnd
0x140047a9e  call    cs:__imp_SendMessageW
0x140047aa4  mov     rcx, [rbx]; hWnd
0x140047aa7  xor     r9d, r9d; lParam
0x140047aaa  xor     r8d, r8d; wParam
0x140047aad  mov     edx, 456h; Msg
0x140047ab2  call    cs:__imp_SendMessageW
0x140047ab8  mov     rcx, [rbx]; hWnd
0x140047abb  xor     r8d, r8d; wParam
0x140047abe  movsxd  r9, eax
0x140047ac1  mov     edx, 457h; Msg
0x140047ac6  and     r9, 0FFFFFFFFFFFF0000h; lParam
0x140047acd  call    cs:__imp_SendMessageW
0x140047ad3  movzx   edx, word ptr [rdi+280h]; unsigned __int16 *
0x140047ada  mov     r8d, [rdi+278h]; int
0x140047ae1  mov     rcx, [rdi+20h]; HINSTANCE
0x140047ae5  call    ?LoadImageList32BitColors@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGH@Z; LoadImageList32BitColors(HINSTANCE__ *,ushort const *,int)
0x140047aea  mov     [rdi+270h], rax
0x140047af1  test    rax, rax
0x140047af4  jz      short loc_140047B5D
0x140047af6  mov     rcx, [rbx]; hWnd
0x140047af9  mov     r9, rax; lParam
0x140047afc  xor     r8d, r8d; wParam
0x140047aff  mov     edx, 430h; Msg
0x140047b04  call    cs:__imp_SendMessageW
0x140047b0a  mov     r9, [rdi+270h]; lParam
0x140047b11  xor     r8d, r8d; wParam
0x140047b14  mov     rcx, [rbx]; hWnd
0x140047b17  mov     edx, 436h; Msg
0x140047b1c  call    cs:__imp_SendMessageW
0x140047b22  mov     rcx, [rbx]; hWnd
0x140047b25  lea     r9, [rbp+3D0h+lParam]; lParam
0x140047b29  xor     eax, eax
0x140047b2b  mov     dword ptr [rbp+3D0h+lParam], 0
0x140047b32  xorps   xmm0, xmm0
0x140047b35  mov     dword ptr [rbp+3D0h+lParam+4], 139Ah
0x140047b3c  movups  xmmword ptr [rbp+3D0h+lParam+0Dh], xmm0
0x140047b40  mov     edx, 444h; Msg
0x140047b45  mov     dword ptr [rbp+3D0h+lParam+8], 1004h
0x140047b4c  lea     r8d, [rax+1]; wParam
0x140047b50  mov     byte ptr [rbp+3D0h+lParam+0Ch], 0
0x140047b54  mov     [rbp+3D0h+var_434], eax
0x140047b57  call    cs:__imp_SendMessageW
0x140047b5d  test    r14, r14
0x140047b60  jz      short loc_140047B88
0x140047b62  xor     r9d, r9d; lParam
0x140047b65  xor     r8d, r8d; wParam
0x140047b68  mov     rcx, r14; hWnd
0x140047b6b  lea     edx, [r9+31h]; Msg
0x140047b6f  call    cs:__imp_SendMessageW
0x140047b75  mov     rcx, [rbx]; hWnd
0x140047b78  xor     r9d, r9d; lParam
0x140047b7b  mov     r8, rax; wParam
0x140047b7e  lea     edx, [r9+30h]; Msg
0x140047b82  call    cs:__imp_SendMessageW
0x140047b88  mov     rcx, [rbx]; hWnd
0x140047b8b  lea     rax, [rbp+3D0h+var_430]
0x140047b8f  mov     [rsp+4D0h+var_468], rax
0x140047b94  lea     r9, [rsp+4D0h+var_488]; lParam
0x140047b99  xor     eax, eax
0x140047b9b  mov     qword ptr [rsp+4D0h+var_488+4], 3
0x140047ba4  cmp     [rdi+60h], eax
0x140047ba7  xorps   xmm0, xmm0
0x140047baa  mov     edx, 440h; Msg
0x140047baf  mov     [rsp+4D0h+var_460], 100h
0x140047bb8  setnz   al
0x140047bbb  mov     dword ptr [rsp+4D0h+var_488], 30h ; '0'
0x140047bc3  mov     r8d, 139Ah; wParam
0x140047bc9  mov     [rsp+4D0h+var_47C], eax
0x140047bcd  movdqu  [rsp+4D0h+var_478], xmm0
0x140047bd3  call    cs:__imp_SendMessageW
0x140047bd9  xor     edx, edx; int
0x140047bdb  mov     rcx, rdi; this
0x140047bde  call    ?PositionExpandoButton@CMainDlg@@AEAAXH@Z; CMainDlg::PositionExpandoButton(int)
0x140047be3  mov     rcx, rdi; this
0x140047be6  call    ?SetExpandoButtonBitmap@CMainDlg@@AEAAXXZ; CMainDlg::SetExpandoButtonBitmap(void)
0x140047beb  xor     edx, edx; pUnkOuter
0x140047bed  lea     rax, [rsp+4D0h+var_490]
0x140047bf2  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x140047bf9  mov     [rsp+4D0h+ppv], rax; ppv
0x140047bfe  lea     rcx, CLSID_AccPropServices; rclsid
0x140047c05  lea     r8d, [rdx+15h]; dwClsContext
0x140047c09  call    cs:__imp_CoCreateInstance
0x140047c0f  test    eax, eax
0x140047c11  js      loc_140047D23
0x140047c17  mov     rcx, [rdi+20h]; HINSTANCE
0x140047c1b  lea     r8, [rbp+3D0h+var_230]; unsigned __int16 *
0x140047c22  mov     r9d, 104h; int
0x140047c28  lea     edx, [r15+450h]; unsigned int
0x140047c2f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140047c34  test    eax, eax
0x140047c36  jnz     short loc_140047C8C
0x140047c38  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c3f  lea     rax, WPP_GLOBAL_Control
0x140047c46  cmp     rcx, rax
0x140047c49  jz      loc_140047D23
0x140047c4f  test    byte ptr [rcx+1Ch], 1
0x140047c53  jz      loc_140047D23
0x140047c59  cmp     byte ptr [rcx+19h], 2
0x140047c5d  jb      loc_140047D23
0x140047c63  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047c68  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c6f  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140047c76  mov     edx, 1Ch
0x140047c7b  mov     r9d, eax
0x140047c7e  mov     rcx, [rcx+10h]
0x140047c82  call    WPP_SF_d
0x140047c87  jmp     loc_140047D23
0x140047c8c  mov     rcx, [rsp+4D0h+var_490]
0x140047c91  lea     rdx, [rbp+3D0h+var_230]
0x140047c98  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x140047c9f  mov     [rsp+4D0h+var_4A8], rdx
0x140047ca4  xor     r9d, r9d
0x140047ca7  lea     rdx, [rbp+3D0h+lParam]
0x140047cab  mov     r8d, 0FFFFFFFCh
0x140047cb1  mov     rax, [rcx]
0x140047cb4  mov     [rsp+4D0h+ppv], rdx
0x140047cb9  mov     rdx, [rbx]
0x140047cbc  movdqu  xmmword ptr [rbp+3D0h+lParam], xmm0
0x140047cc1  mov     rax, [rax+38h]
0x140047cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047cca  mov     ebx, eax
0x140047ccc  test    eax, eax
0x140047cce  jns     short loc_140047D23
0x140047cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140047cd7  lea     rax, WPP_GLOBAL_Control
0x140047cde  cmp     rcx, rax
0x140047ce1  jz      short loc_140047D23
0x140047ce3  test    byte ptr [rcx+1Ch], 8
0x140047ce7  jz      short loc_140047D23
0x140047ce9  cmp     byte ptr [rcx+19h], 2
0x140047ced  jb      short loc_140047D23
0x140047cef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047cf4  lea     rcx, aFailedToSetHid; "Failed to set hide options accessible n"...
0x140047cfb  mov     dword ptr [rsp+4D0h+var_4A8], ebx
0x140047cff  mov     [rsp+4D0h+ppv], rcx
0x140047d04  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140047d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d12  mov     edx, 1Dh
0x140047d17  mov     r9d, eax
0x140047d1a  mov     rcx, [rcx+10h]
0x140047d1e  call    WPP_SF_DsD
0x140047d23  mov     edi, 1
0x140047d28  jmp     short loc_140047D8B
0x140047d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d31  lea     rax, WPP_GLOBAL_Control
0x140047d38  xor     edi, edi
0x140047d3a  cmp     rcx, rax
0x140047d3d  jz      short loc_140047D6D
0x140047d3f  test    byte ptr [rcx+1Ch], 1
0x140047d43  jz      short loc_140047D6D
0x140047d45  cmp     byte ptr [rcx+19h], 2
0x140047d49  jb      short loc_140047D6D
0x140047d4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047d50  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d57  lea     edx, [rdi+1Eh]
0x140047d5a  mov     r9d, eax
0x140047d5d  lea     r8, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x140047d64  mov     rcx, [rcx+10h]
0x140047d68  call    WPP_SF_d
0x140047d6d  mov     rcx, [rbx]; hWnd
0x140047d70  test    rcx, rcx
0x140047d73  jz      short loc_140047D7D
0x140047d75  xor     edx, edx; nCmdShow
0x140047d77  call    cs:__imp_ShowWindow
0x140047d7d  mov     edx, 4; nCmdShow
0x140047d82  mov     rcx, r14; hWnd
0x140047d85  call    cs:__imp_ShowWindow
0x140047d8b  mov     rcx, [rsp+4D0h+var_490]
0x140047d90  test    rcx, rcx
0x140047d93  jz      short loc_140047DAA
0x140047d95  mov     [rsp+4D0h+var_490], 0
0x140047d9e  mov     rdx, [rcx]
0x140047da1  mov     rax, [rdx+10h]
0x140047da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047daa  mov     eax, edi
0x140047dac  mov     rcx, [rbp+3D0h+var_20]
0x140047db3  xor     rcx, rsp; StackCookie
0x140047db6  call    __security_check_cookie
0x140047dbb  lea     r11, [rsp+4D0h+var_10]
0x140047dc3  mov     rbx, [r11+28h]
0x140047dc7  mov     rdi, [r11+30h]
0x140047dcb  mov     rsp, r11
0x140047dce  pop     r15
0x140047dd0  pop     r14
0x140047dd2  pop     rbp
0x140047dd3  retn
```

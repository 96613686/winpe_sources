# CRedirectPromptDlg2View::PopulateConnectionInfo(void)

- ea: `0x1805009fc`
- end: `0x180500e99`
- name: `?PopulateConnectionInfo@CRedirectPromptDlg2View@@AEAAXXZ`
- size: `1181`
- prototype: `void __fastcall(CRedirectPromptDlg2View *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180500ea0`

## callees

- `0x180039ce4`
- `0x1800d1db0`
- `0x1800e9b1c`
- `0x1802498a0`
- `0x1804ffdf0`
- `0x1805005e8`
- `0x180500638`
- `0x1805009fc`
- `0x180502328`
- `0x1806495b4`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `USER32!GetWindowRect` at `0x180500b52`
- `USER32!GetWindowRect` at `0x180500b52`
- `USER32!ShowWindow` at `0x180500da9`
- `USER32!ShowWindow` at `0x180500db7`
- `USER32!ShowWindow` at `0x180500da9`
- `USER32!ShowWindow` at `0x180500db7`
- `USER32!MapWindowPoints` at `0x180500b68`
- `USER32!MapWindowPoints` at `0x180500b68`
- `USER32!SendMessageW` at `0x180500b26`
- `USER32!SendMessageW` at `0x180500d84`
- `USER32!SendMessageW` at `0x180500d9b`
- `USER32!SendMessageW` at `0x180500b26`
- `USER32!SendMessageW` at `0x180500d84`
- `USER32!SendMessageW` at `0x180500d9b`
- `USER32!GetDlgItem` at `0x180500b45`
- `USER32!GetDlgItem` at `0x180500b45`
- `USER32!MapDialogRect` at `0x180500b8b`
- `USER32!MapDialogRect` at `0x180500ba6`
- `USER32!MapDialogRect` at `0x180500bc1`
- `USER32!MapDialogRect` at `0x180500e08`
- `USER32!MapDialogRect` at `0x180500b8b`
- `USER32!MapDialogRect` at `0x180500ba6`
- `USER32!MapDialogRect` at `0x180500bc1`
- `USER32!MapDialogRect` at `0x180500e08`
- `OLE32!CoTaskMemFree` at `0x180500c49`
- `OLE32!CoTaskMemFree` at `0x180500c57`
- `OLE32!CoTaskMemFree` at `0x180500e58`
- `OLE32!CoTaskMemFree` at `0x180500e66`
- `OLE32!CoTaskMemFree` at `0x180500c49`
- `OLE32!CoTaskMemFree` at `0x180500c57`
- `OLE32!CoTaskMemFree` at `0x180500e58`
- `OLE32!CoTaskMemFree` at `0x180500e66`

## string_xrefs

- `0x180500d06`: `SysLink`

## pseudocode

```c
void __fastcall CRedirectPromptDlg2View::PopulateConnectionInfo(CRedirectPromptDlg2View *this)
{
  __int64 v2; // rcx
  signed int v3; // edi
  unsigned int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  HWND DlgItem; // rax
  LONG left; // r15d
  HWND v9; // rcx
  HWND v10; // rcx
  HWND v11; // rcx
  LONG top; // edi
  int v13; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v15; // esi
  LONG right; // r13d
  LONG bottom; // r12d
  HWND Window; // r15
  int v19; // eax
  const WCHAR *v20; // rcx
  HWND v21; // r14
  HWND v22; // rcx
  LONG v23; // eax
  int v24; // edi
  LONG v25; // [rsp+60h] [rbp-79h]
  unsigned int v26; // [rsp+64h] [rbp-75h] BYREF
  wchar_t *Str; // [rsp+68h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v29; // [rsp+78h] [rbp-61h] BYREF
  __int64 v30; // [rsp+80h] [rbp-59h] BYREF
  int i; // [rsp+88h] [rbp-51h]
  WPARAM wParam; // [rsp+90h] [rbp-49h]
  unsigned int *v33; // [rsp+98h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+A0h] [rbp-39h] BYREF
  struct tagRECT v35; // [rsp+B0h] [rbp-29h] BYREF
  struct tagRECT si128; // [rsp+C0h] [rbp-19h] BYREF
  struct tagRECT v37; // [rsp+D0h] [rbp-9h] BYREF

  v2 = *((_QWORD *)this + 9);
  Rect = 0;
  v30 = 0;
  v3 = v2 == 0 ? 0x80004005 : 0;
  v26 = 0;
  pv = 0;
  Str = 0;
  v33 = 0;
  v29 = 0;
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 32LL))(v2, &v30);
    if ( v3 >= 0 )
    {
      wParam = SendMessageW(*((HWND *)this + 1), 0x31u, 0, 0);
      CRedirectPromptDlg2View::UpdateWarningText(this);
      DlgItem = GetDlgItem(*((HWND *)this + 1), 16301);
      GetWindowRect(DlgItem, &Rect);
      MapWindowPoints(0, *((HWND *)this + 1), (LPPOINT)&Rect, 2u);
      left = Rect.left;
      v9 = (HWND)*((_QWORD *)this + 1);
      si128 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
      v25 = Rect.left;
      MapDialogRect(v9, &si128);
      v10 = (HWND)*((_QWORD *)this + 1);
      v37 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
      MapDialogRect(v10, &v37);
      v11 = (HWND)*((_QWORD *)this + 1);
      v35 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
      MapDialogRect(v11, &v35);
      top = Rect.top;
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 48LL))(v30, &v26);
      if ( v13 >= 0 )
      {
        v15 = 0;
        right = v37.right;
        bottom = si128.bottom;
        for ( i = left + v37.right; v15 < v26; ++v15 )
        {
          CoTaskMemFree(pv);
          pv = 0;
          CoTaskMemFree(Str);
          Str = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, LPVOID *, wchar_t **))(*(_QWORD *)v30 + 56LL))(
                 v30,
                 v15,
                 &pv,
                 &Str) >= 0 )
          {
            Window = (HWND)IsolationAwareCreateWindowExW(
                             0,
                             L"Static",
                             (LPCWSTR)pv,
                             0x40000000u,
                             left,
                             top,
                             right,
                             bottom,
                             *((HWND *)this + 1),
                             (HMENU)(2 * v15 + 16302),
                             *((HINSTANCE *)this + 4),
                             0);
            if ( Window )
            {
              v19 = ContainsLinkMarkup(Str);
              v20 = L"SysLink";
              if ( !v19 )
                v20 = L"Static";
              v21 = (HWND)IsolationAwareCreateWindowExW(
                            0,
                            v20,
                            Str,
                            v19 != 0 ? 1073807360 : 1073758208,
                            i,
                            top,
                            v35.right,
                            bottom,
                            *((HWND *)this + 1),
                            (HMENU)(2 * v15 + 16303),
                            *((HINSTANCE *)this + 4),
                            0);
              if ( v21 )
              {
                if ( wParam )
                {
                  SendMessageW(Window, 0x30u, wParam, 1);
                  SendMessageW(v21, 0x30u, wParam, 1);
                }
                ShowWindow(Window, 5);
                ShowWindow(v21, 5);
                top += bottom;
                *((_QWORD *)this + 11) = v21;
                *((_DWORD *)this + 20) = 16301;
              }
            }
            left = v25;
          }
        }
        if ( (unsigned int)GetDlgItemRect(*((HWND *)this + 1), 13498, &Rect) )
        {
          v23 = Rect.bottom;
        }
        else
        {
          v22 = (HWND)*((_QWORD *)this + 1);
          v35 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
          MapDialogRect(v22, &v35);
          v23 = v35.bottom;
          Rect.bottom = v35.bottom;
        }
        v24 = top - v23;
        if ( v24 > 0 && !*((_DWORD *)this + 34) )
        {
          GetControlsBelow(0x3FADu, &v33, &v29);
          CDlgBase::RepositionBottomControls(this, v24, v33, v29, 1);
        }
      }
      else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
             && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_eba7e521e3be33ba4b5ca1086e56447d_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Failed to get connection info row count from view model",
          v13);
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 18;
      v6 = "Failed to get connection info from view model";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 17;
    v6 = "ViewModel is null; cannot populate connection info";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_eba7e521e3be33ba4b5ca1086e56447d_Traceguids,
      v4,
      (__int64)v6,
      v3);
  }
  CoTaskMemFree(Str);
  Str = 0;
  CoTaskMemFree(pv);
  pv = 0;
  wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v30);
}

```

## disassembly

```asm
0x1805009fc  push    rbp
0x1805009fe  push    rbx
0x1805009ff  push    rsi
0x180500a00  push    rdi
0x180500a01  push    r12
0x180500a03  push    r13
0x180500a05  push    r14
0x180500a07  push    r15
0x180500a09  lea     rbp, [rsp-1Fh]
0x180500a0e  sub     rsp, 0F8h
0x180500a15  mov     rax, cs:__security_cookie
0x180500a1c  xor     rax, rsp
0x180500a1f  mov     [rbp+57h+var_50], rax
0x180500a23  mov     rbx, rcx
0x180500a26  xorps   xmm0, xmm0
0x180500a29  mov     rcx, [rcx+48h]
0x180500a2d  mov     rax, rcx
0x180500a30  neg     rax
0x180500a33  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180500a37  sbb     edi, edi
0x180500a39  xor     r14d, r14d
0x180500a3c  not     edi
0x180500a3e  mov     [rbp+57h+var_B0], r14
0x180500a42  and     edi, 80004005h
0x180500a48  mov     [rbp+57h+var_CC], r14d
0x180500a4c  mov     [rbp+57h+pv], r14
0x180500a50  mov     [rbp+57h+Str], r14
0x180500a54  mov     [rbp+57h+var_98], r14
0x180500a58  mov     [rbp+57h+var_B8], r14d
0x180500a5c  test    rcx, rcx
0x180500a5f  jnz     short loc_180500AC4
0x180500a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180500a68  lea     rax, WPP_GLOBAL_Control
0x180500a6f  cmp     rcx, rax
0x180500a72  jz      loc_180500E54
0x180500a78  test    byte ptr [rcx+1Ch], 8
0x180500a7c  jz      loc_180500E54
0x180500a82  cmp     byte ptr [rcx+19h], 2
0x180500a86  jb      loc_180500E54
0x180500a8c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180500a91  lea     edx, [r14+11h]
0x180500a95  lea     rcx, aViewmodelIsNul_1; "ViewModel is null; cannot populate conn"...
0x180500a9c  mov     [rsp+130h+var_108], edi
0x180500aa0  mov     qword ptr [rsp+130h+var_110], rcx
0x180500aa5  lea     r8, WPP_eba7e521e3be33ba4b5ca1086e56447d_Traceguids
0x180500aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180500ab3  mov     r9d, eax
0x180500ab6  mov     rcx, [rcx+10h]
0x180500aba  call    WPP_SF_DsD
0x180500abf  jmp     loc_180500E54
0x180500ac4  mov     rax, [rcx]
0x180500ac7  lea     rdx, [rbp+57h+var_B0]
0x180500acb  mov     rax, [rax+20h]
0x180500acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180500ad4  mov     edi, eax
0x180500ad6  test    eax, eax
0x180500ad8  jns     short loc_180500B18
0x180500ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180500ae1  lea     rax, WPP_GLOBAL_Control
0x180500ae8  cmp     rcx, rax
0x180500aeb  jz      loc_180500E54
0x180500af1  test    byte ptr [rcx+1Ch], 8
0x180500af5  jz      loc_180500E54
0x180500afb  cmp     byte ptr [rcx+19h], 2
0x180500aff  jb      loc_180500E54
0x180500b05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180500b0a  mov     edx, 12h
0x180500b0f  lea     rcx, aFailedToGetCon_16; "Failed to get connection info from view"...
0x180500b16  jmp     short loc_180500A9C
0x180500b18  mov     rcx, [rbx+8]; hWnd
0x180500b1c  xor     r9d, r9d; lParam
0x180500b1f  xor     r8d, r8d; wParam
0x180500b22  lea     edx, [r9+31h]; Msg
0x180500b26  call    cs:__imp_SendMessageW
0x180500b2c  lea     rdx, [rbp+57h+var_B0]
0x180500b30  mov     rcx, rbx; this
0x180500b33  mov     [rbp+57h+wParam], rax
0x180500b37  call    ?UpdateWarningText@CRedirectPromptDlg2View@@AEAAXAEAV?$com_ptr_t@UIRedirectPromptConnectionInfo@@Uerr_returncode_policy@wil@@@wil@@@Z; CRedirectPromptDlg2View::UpdateWarningText(wil::com_ptr_t<IRedirectPromptConnectionInfo,wil::err_returncode_policy> &)
0x180500b3c  mov     rcx, [rbx+8]; hDlg
0x180500b40  mov     edx, 3FADh; nIDDlgItem
0x180500b45  call    cs:__imp_GetDlgItem
0x180500b4b  mov     rcx, rax; hWnd
0x180500b4e  lea     rdx, [rbp+57h+Rect]; lpRect
0x180500b52  call    cs:__imp_GetWindowRect
0x180500b58  mov     rdx, [rbx+8]; hWndTo
0x180500b5c  lea     r8, [rbp+57h+Rect]; lpPoints
0x180500b60  mov     r9d, 2; cPoints
0x180500b66  xor     ecx, ecx; hWndFrom
0x180500b68  call    cs:__imp_MapWindowPoints
0x180500b6e  movdqa  xmm0, cs:__xmm@0000000d000000000000000000000000
0x180500b76  lea     rdx, [rbp+57h+var_70]; lpRect
0x180500b7a  mov     r15d, [rbp+57h+Rect.left]
0x180500b7e  mov     rcx, [rbx+8]; hDlg
0x180500b82  movdqu  xmmword ptr [rbp+57h+var_70.left], xmm0
0x180500b87  mov     [rbp+57h+var_D0], r15d
0x180500b8b  call    cs:__imp_MapDialogRect
0x180500b91  movdqa  xmm0, cs:__xmm@000000000000004b0000000000000000
0x180500b99  lea     rdx, [rbp+57h+var_60]; lpRect
0x180500b9d  mov     rcx, [rbx+8]; hDlg
0x180500ba1  movdqu  xmmword ptr [rbp+57h+var_60.left], xmm0
0x180500ba6  call    cs:__imp_MapDialogRect
0x180500bac  movdqa  xmm0, cs:__xmm@00000000000000ad0000000000000000
0x180500bb4  lea     rdx, [rbp+57h+var_80]; lpRect
0x180500bb8  mov     rcx, [rbx+8]; hDlg
0x180500bbc  movdqu  xmmword ptr [rbp+57h+var_80.left], xmm0
0x180500bc1  call    cs:__imp_MapDialogRect
0x180500bc7  mov     rcx, [rbp+57h+var_B0]
0x180500bcb  lea     rdx, [rbp+57h+var_CC]
0x180500bcf  mov     edi, [rbp+57h+Rect.top]
0x180500bd2  mov     rax, [rcx]
0x180500bd5  mov     rax, [rax+30h]
0x180500bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180500bde  mov     esi, eax
0x180500be0  test    eax, eax
0x180500be2  jns     short loc_180500C29
0x180500be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180500beb  lea     rax, WPP_GLOBAL_Control
0x180500bf2  cmp     rcx, rax
0x180500bf5  jz      loc_180500E54
0x180500bfb  test    byte ptr [rcx+1Ch], 8
0x180500bff  jz      loc_180500E54
0x180500c05  cmp     byte ptr [rcx+19h], 2
0x180500c09  jb      loc_180500E54
0x180500c0f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180500c14  mov     edx, 13h
0x180500c19  mov     [rsp+130h+var_108], esi
0x180500c1d  lea     rcx, aFailedToGetCon_1; "Failed to get connection info row count"...
0x180500c24  jmp     loc_180500AA0
0x180500c29  mov     esi, r14d
0x180500c2c  mov     r13d, [rbp+57h+var_60.right]
0x180500c30  mov     r12d, [rbp+57h+var_70.bottom]
0x180500c34  lea     eax, [r15+r13]
0x180500c38  mov     [rbp+57h+var_A8], eax
0x180500c3b  cmp     [rbp+57h+var_CC], r14d
0x180500c3f  jbe     loc_180500DDD
0x180500c45  mov     rcx, [rbp+57h+pv]; pv
0x180500c49  call    cs:__imp_CoTaskMemFree
0x180500c4f  mov     rcx, [rbp+57h+Str]; pv
0x180500c53  mov     [rbp+57h+pv], r14
0x180500c57  call    cs:__imp_CoTaskMemFree
0x180500c5d  mov     rcx, [rbp+57h+var_B0]
0x180500c61  lea     r9, [rbp+57h+Str]
0x180500c65  mov     [rbp+57h+Str], r14
0x180500c69  lea     r8, [rbp+57h+pv]
0x180500c6d  mov     edx, esi
0x180500c6f  mov     rax, [rcx]
0x180500c72  mov     rax, [rax+38h]
0x180500c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180500c7b  test    eax, eax
0x180500c7d  js      loc_180500DD2
0x180500c83  mov     rax, [rbx+20h]
0x180500c87  lea     r14d, [rsi+rsi]
0x180500c8b  mov     r8, [rbp+57h+pv]; lpWindowName
0x180500c8f  lea     ecx, [r14+3FAEh]
0x180500c96  mov     [rsp+130h+var_D8], 0; LPVOID
0x180500c9f  lea     rdx, ClassName; "Static"
0x180500ca6  mov     [rsp+130h+var_E0], rax; HINSTANCE
0x180500cab  mov     r9d, 40000000h; dwStyle
0x180500cb1  mov     rax, [rbx+8]
0x180500cb5  mov     [rsp+130h+var_E8], rcx; HMENU
0x180500cba  xor     ecx, ecx; dwExStyle
0x180500cbc  mov     [rsp+130h+var_F0], rax; HWND
0x180500cc1  mov     [rsp+130h+var_F8], r12d; int
0x180500cc6  mov     [rsp+130h+var_100], r13d; int
0x180500ccb  mov     [rsp+130h+var_108], edi; int
0x180500ccf  mov     [rsp+130h+var_110], r15d; int
0x180500cd4  call    IsolationAwareCreateWindowExW
0x180500cd9  mov     r15, rax
0x180500cdc  test    rax, rax
0x180500cdf  jz      loc_180500DCB
0x180500ce5  mov     rcx, [rbp+57h+Str]; Str
0x180500ce9  call    ?ContainsLinkMarkup@@YAHPEBG@Z; ContainsLinkMarkup(ushort const *)
0x180500cee  mov     r8, [rbp+57h+Str]; lpWindowName
0x180500cf2  lea     edx, [r14+3FAFh]
0x180500cf9  mov     ecx, eax
0x180500cfb  mov     [rsp+130h+var_D8], 0; LPVOID
0x180500d04  neg     ecx
0x180500d06  lea     rcx, aSyslink; "SysLink"
0x180500d0d  sbb     r9d, r9d
0x180500d10  and     r9d, 0C000h
0x180500d17  add     r9d, 40004000h; dwStyle
0x180500d1e  test    eax, eax
0x180500d20  lea     rax, ClassName; "Static"
0x180500d27  cmovz   rcx, rax
0x180500d2b  mov     rax, [rbx+20h]
0x180500d2f  mov     [rsp+130h+var_E0], rax; HINSTANCE
0x180500d34  mov     rax, [rbx+8]
0x180500d38  mov     [rsp+130h+var_E8], rdx; HMENU
0x180500d3d  mov     rdx, rcx; lpClassName
0x180500d40  mov     [rsp+130h+var_F0], rax; HWND
0x180500d45  xor     ecx, ecx; dwExStyle
0x180500d47  mov     eax, [rbp+57h+var_80.right]
0x180500d4a  mov     [rsp+130h+var_F8], r12d; int
0x180500d4f  mov     [rsp+130h+var_100], eax; int
0x180500d53  mov     eax, [rbp+57h+var_A8]
0x180500d56  mov     [rsp+130h+var_108], edi; int
0x180500d5a  mov     [rsp+130h+var_110], eax; int
0x180500d5e  call    IsolationAwareCreateWindowExW
0x180500d63  mov     r14, rax
0x180500d66  test    rax, rax
0x180500d69  jz      short loc_180500DCB
0x180500d6b  mov     rax, [rbp+57h+wParam]
0x180500d6f  test    rax, rax
0x180500d72  jz      short loc_180500DA1
0x180500d74  mov     r9d, 1; lParam
0x180500d7a  mov     r8, rax; wParam
0x180500d7d  mov     rcx, r15; hWnd
0x180500d80  lea     edx, [r9+2Fh]; Msg
0x180500d84  call    cs:__imp_SendMessageW
0x180500d8a  mov     r8, [rbp+57h+wParam]; wParam
0x180500d8e  mov     r9d, 1; lParam
0x180500d94  mov     rcx, r14; hWnd
0x180500d97  lea     edx, [r9+2Fh]; Msg
0x180500d9b  call    cs:__imp_SendMessageW
0x180500da1  mov     edx, 5; nCmdShow
0x180500da6  mov     rcx, r15; hWnd
0x180500da9  call    cs:__imp_ShowWindow
0x180500daf  mov     edx, 5; nCmdShow
0x180500db4  mov     rcx, r14; hWnd
0x180500db7  call    cs:__imp_ShowWindow
0x180500dbd  add     edi, r12d
0x180500dc0  mov     [rbx+58h], r14
0x180500dc4  mov     dword ptr [rbx+50h], 3FADh
0x180500dcb  mov     r15d, [rbp+57h+var_D0]
0x180500dcf  xor     r14d, r14d
0x180500dd2  inc     esi
0x180500dd4  cmp     esi, [rbp+57h+var_CC]
0x180500dd7  jb      loc_180500C45
0x180500ddd  mov     rcx, [rbx+8]; hWndTo
0x180500de1  lea     r8, [rbp+57h+Rect]; struct tagRECT *
0x180500de5  mov     edx, 34BAh; int
0x180500dea  call    ?GetDlgItemRect@@YAHPEAUHWND__@@HAEAUtagRECT@@@Z; GetDlgItemRect(HWND__ *,int,tagRECT &)
0x180500def  test    eax, eax
0x180500df1  jnz     short loc_180500E16
0x180500df3  movdqa  xmm0, cs:__xmm@00000062000000000000000000000000
0x180500dfb  lea     rdx, [rbp+57h+var_80]; lpRect
0x180500dff  mov     rcx, [rbx+8]; hDlg
0x180500e03  movdqu  xmmword ptr [rbp+57h+var_80.left], xmm0
0x180500e08  call    cs:__imp_MapDialogRect
0x180500e0e  mov     eax, [rbp+57h+var_80.bottom]
0x180500e11  mov     [rbp+57h+Rect.bottom], eax
0x180500e14  jmp     short loc_180500E19
0x180500e16  mov     eax, [rbp+57h+Rect.bottom]
0x180500e19  sub     edi, eax
0x180500e1b  test    edi, edi
0x180500e1d  jle     short loc_180500E54
0x180500e1f  cmp     [rbx+88h], r14d
0x180500e26  jnz     short loc_180500E54
0x180500e28  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x180500e2c  mov     ecx, 3FADh; unsigned int
0x180500e31  lea     rdx, [rbp+57h+var_98]; unsigned int **
0x180500e35  call    ?GetControlsBelow@@YAJIPEAPEAIPEAI@Z; GetControlsBelow(uint,uint * *,uint *)
0x180500e3a  mov     r9d, [rbp+57h+var_B8]; unsigned int
0x180500e3e  mov     edx, edi; int
0x180500e40  mov     r8, [rbp+57h+var_98]; unsigned int *
0x180500e44  mov     rcx, rbx; this
0x180500e47  mov     [rsp+130h+var_110], 1; int
0x180500e4f  call    ?RepositionBottomControls@CDlgBase@@IEAAXHPEAIIH@Z; CDlgBase::RepositionBottomControls(int,uint *,uint,int)
0x180500e54  mov     rcx, [rbp+57h+Str]; pv
0x180500e58  call    cs:__imp_CoTaskMemFree
0x180500e5e  mov     rcx, [rbp+57h+pv]; pv
0x180500e62  mov     [rbp+57h+Str], r14
0x180500e66  call    cs:__imp_CoTaskMemFree
0x180500e6c  lea     rcx, [rbp+57h+var_B0]; void *
0x180500e70  mov     [rbp+57h+pv], r14
0x180500e74  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180500e79  mov     rcx, [rbp+57h+var_50]
0x180500e7d  xor     rcx, rsp; StackCookie
0x180500e80  call    __security_check_cookie
0x180500e85  add     rsp, 0F8h
0x180500e8c  pop     r15
0x180500e8e  pop     r14
0x180500e90  pop     r13
0x180500e92  pop     r12
0x180500e94  pop     rdi
0x180500e95  pop     rsi
0x180500e96  pop     rbx
0x180500e97  pop     rbp
0x180500e98  retn
```

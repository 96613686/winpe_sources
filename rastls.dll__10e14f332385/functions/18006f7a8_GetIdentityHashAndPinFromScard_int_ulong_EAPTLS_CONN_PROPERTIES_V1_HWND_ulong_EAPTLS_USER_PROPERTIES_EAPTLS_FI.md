# GetIdentityHashAndPinFromScard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,ulong,_EAPTLS_USER_PROPERTIES * *,_EAPTLS_FILTER_PROP *,int,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x18006f7a8`
- end: `0x18006f973`
- name: `?GetIdentityHashAndPinFromScard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAU_EAPTLS_FILTER_PROP@@HPEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU5@@Z`
- size: `459`
- prototype: `unsigned int(int, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 *, HWND, unsigned int, struct _EAPTLS_USER_PROPERTIES **, struct _EAPTLS_FILTER_PROP *, int, const struct _CERT_CONTEXT **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800136f0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18006e6e0`
- `0x18006f550`
- `0x18006f7a8`
- `0x1800702c4`
- `0x18007042c`
- `0x1800718ac`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x18006f841`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x18006f841`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18006f89e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18006f92e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18006f89e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18006f92e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CreateDialogParamW` at `0x18006f820`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CreateDialogParamW` at `0x18006f820`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18006f84a`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18006f84a`

## pseudocode

```c
__int64 __fastcall GetIdentityHashAndPinFromScard(
        __int64 a1,
        unsigned int a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3,
        HWND a4,
        unsigned int a5,
        struct _EAPTLS_USER_PROPERTIES **a6,
        struct _CERT_CONTEXT *a7,
        int a8,
        struct _CERT_CONTEXT **a9,
        unsigned int *a10)
{
  HWND DialogParamW; // rax
  DWORD v14; // ecx
  int v15; // r8d
  HWND v16; // rbx
  const struct _CERT_CONTEXT **v17; // r15
  struct _EAPTLS_USER_PROPERTIES **v18; // r14
  unsigned int IdentityAndHashFromScard; // edi
  unsigned int v20; // ecx
  unsigned int v21; // eax
  struct _EAPTLS_CONTROL_BLOCK *v22; // rcx
  int dwInitParam; // [rsp+20h] [rbp-68h]
  unsigned int *v25; // [rsp+48h] [rbp-40h]
  int v26; // [rsp+90h] [rbp+8h] BYREF

  v26 = 0;
  a10 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_c4e812f99669349517681909258710e2_Traceguids);
  DialogParamW = CreateDialogParamW(g_hInstance, (LPCWSTR)0x68, a4, StatusDialogProc, 1);
  v16 = DialogParamW;
  if ( DialogParamW )
  {
    CenterWindow(DialogParamW, a4, v15);
    ShowWindow(v16, 5);
    UpdateWindow(v16);
  }
  v17 = (const struct _CERT_CONTEXT **)a9;
  v18 = a6;
  IdentityAndHashFromScard = GetIdentityAndHashFromScard(v14, a2, a3, a4, dwInitParam, a7, 0, a6, a9, v25);
  if ( !IdentityAndHashFromScard )
  {
    if ( v16 )
    {
      DestroyWindow(v16);
      v16 = 0;
    }
    if ( (WiFiCredRequireNgc(*v17, &v26, (unsigned __int64 *)&a10) || v26 != 1)
      && (unsigned int)IsCertNGC(*v17) != 1
      && (*((_BYTE *)*v18 + 12) & 4) == 0 )
    {
      v21 = InvokeSecurePinUI(v20, v18, a5, a4);
      IdentityAndHashFromScard = v21;
      if ( v21 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_16;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_c4e812f99669349517681909258710e2_Traceguids, v21);
      }
    }
  }
  v22 = WPP_GLOBAL_Control;
LABEL_16:
  if ( v16 )
  {
    DestroyWindow(v16);
    v22 = WPP_GLOBAL_Control;
  }
  if ( v22 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)v22 + 2), 59, &WPP_c4e812f99669349517681909258710e2_Traceguids, IdentityAndHashFromScard);
  return IdentityAndHashFromScard;
}

```

## disassembly

```asm
0x18006f7a8  mov     rax, rsp
0x18006f7ab  mov     [rax+10h], rbx
0x18006f7af  mov     [rax+18h], rbp
0x18006f7b3  mov     [rax+8], ecx
0x18006f7b6  push    rsi
0x18006f7b7  push    rdi
0x18006f7b8  push    r13
0x18006f7ba  push    r14
0x18006f7bc  push    r15
0x18006f7be  sub     rsp, 60h
0x18006f7c2  mov     rsi, r9
0x18006f7c5  mov     dword ptr [rax+8], 0
0x18006f7cc  mov     rdi, r8
0x18006f7cf  mov     qword ptr [rax+50h], 0
0x18006f7d7  mov     ebp, edx
0x18006f7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7e0  lea     r13, WPP_GLOBAL_Control
0x18006f7e7  cmp     rcx, r13
0x18006f7ea  jz      short loc_18006F801
0x18006f7ec  mov     rcx, [rcx+10h]
0x18006f7f0  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f7f7  mov     edx, 39h ; '9'
0x18006f7fc  call    WPP_SF_
0x18006f801  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006f808  lea     r9, ?StatusDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18006f80f  mov     r8, rsi; hWndParent
0x18006f812  mov     [rsp+88h+dwInitParam], 1; int
0x18006f81b  mov     edx, 68h ; 'h'; lpTemplateName
0x18006f820  call    cs:__imp_CreateDialogParamW
0x18006f826  mov     rbx, rax
0x18006f829  test    rax, rax
0x18006f82c  jz      short loc_18006F850
0x18006f82e  mov     rdx, rsi; HWND
0x18006f831  mov     rcx, rax; hWnd
0x18006f834  call    ?CenterWindow@@YAXPEAUHWND__@@0H@Z; CenterWindow(HWND__ *,HWND__ *,int)
0x18006f839  mov     edx, 5; nCmdShow
0x18006f83e  mov     rcx, rbx; hWnd
0x18006f841  call    cs:__imp_ShowWindow
0x18006f847  mov     rcx, rbx; hWnd
0x18006f84a  call    cs:__imp_UpdateWindow
0x18006f850  mov     rax, [rsp+88h+arg_30]
0x18006f858  mov     r9, rsi; HWND
0x18006f85b  mov     r15, [rsp+88h+arg_40]
0x18006f863  mov     r8, rdi; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18006f866  mov     r14, [rsp+88h+arg_28]
0x18006f86e  mov     edx, ebp; unsigned int
0x18006f870  mov     [rsp+88h+var_48], r15; struct _CERT_CONTEXT **
0x18006f875  mov     [rsp+88h+var_50], r14; struct _EAPTLS_USER_PROPERTIES **
0x18006f87a  mov     [rsp+88h+var_58], 0; int
0x18006f882  mov     [rsp+88h+var_60], rax; struct _EAPTLS_FILTER_PROP *
0x18006f887  call    ?GetIdentityAndHashFromScard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@HPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU5@@Z; GetIdentityAndHashFromScard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,int,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)
0x18006f88c  mov     edi, eax
0x18006f88e  test    eax, eax
0x18006f890  jnz     loc_18006F91F
0x18006f896  test    rbx, rbx
0x18006f899  jz      short loc_18006F8A6
0x18006f89b  mov     rcx, rbx; hWnd
0x18006f89e  call    cs:__imp_DestroyWindow
0x18006f8a4  xor     ebx, ebx
0x18006f8a6  mov     rcx, [r15]; struct _CERT_CONTEXT *
0x18006f8a9  lea     r8, [rsp+88h+arg_48]; unsigned __int64 *
0x18006f8b1  lea     rdx, [rsp+88h+arg_0]; int *
0x18006f8b9  call    ?WiFiCredRequireNgc@@YAKPEBU_CERT_CONTEXT@@PEAHPEA_K@Z; WiFiCredRequireNgc(_CERT_CONTEXT const *,int *,unsigned __int64 *)
0x18006f8be  test    eax, eax
0x18006f8c0  jnz     short loc_18006F8CC
0x18006f8c2  cmp     [rsp+88h+arg_0], 1
0x18006f8ca  jz      short loc_18006F91F
0x18006f8cc  mov     rcx, [r15]; pCertContext
0x18006f8cf  call    ?IsCertNGC@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertNGC(_CERT_CONTEXT const *)
0x18006f8d4  cmp     eax, 1
0x18006f8d7  jz      short loc_18006F91F
0x18006f8d9  mov     rax, [r14]
0x18006f8dc  test    byte ptr [rax+0Ch], 4
0x18006f8e0  jnz     short loc_18006F91F
0x18006f8e2  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x18006f8ea  mov     r9, rsi; HWND
0x18006f8ed  mov     rdx, r14; struct _EAPTLS_USER_PROPERTIES **
0x18006f8f0  call    ?InvokeSecurePinUI@@YAKKPEAPEAU_EAPTLS_USER_PROPERTIES@@KPEAUHWND__@@@Z; InvokeSecurePinUI(ulong,_EAPTLS_USER_PROPERTIES * *,ulong,HWND__ *)
0x18006f8f5  mov     edi, eax
0x18006f8f7  test    eax, eax
0x18006f8f9  jz      short loc_18006F91F
0x18006f8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f902  cmp     rcx, r13
0x18006f905  jz      short loc_18006F926
0x18006f907  mov     rcx, [rcx+10h]
0x18006f90b  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f912  mov     edx, 3Ah ; ':'
0x18006f917  mov     r9d, eax
0x18006f91a  call    WPP_SF_d
0x18006f91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f926  test    rbx, rbx
0x18006f929  jz      short loc_18006F93B
0x18006f92b  mov     rcx, rbx; hWnd
0x18006f92e  call    cs:__imp_DestroyWindow
0x18006f934  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f93b  cmp     rcx, r13
0x18006f93e  jz      short loc_18006F958
0x18006f940  mov     rcx, [rcx+10h]
0x18006f944  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f94b  mov     edx, 3Bh ; ';'
0x18006f950  mov     r9d, edi
0x18006f953  call    WPP_SF_d
0x18006f958  lea     r11, [rsp+88h+var_28]
0x18006f95d  mov     eax, edi
0x18006f95f  mov     rbx, [r11+38h]
0x18006f963  mov     rbp, [r11+40h]
0x18006f967  mov     rsp, r11
0x18006f96a  pop     r15
0x18006f96c  pop     r14
0x18006f96e  pop     r13
0x18006f970  pop     rdi
0x18006f971  pop     rsi
0x18006f972  retn
```

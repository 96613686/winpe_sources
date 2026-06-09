# CConfigAdvancedPage::OnInitDialog(HWND__ *,HWND__ * &)

- ea: `0x180014bc0`
- end: `0x180014d9d`
- name: `?OnInitDialog@CConfigAdvancedPage@@UEAAKPEAUHWND__@@AEAPEAU2@@Z`
- size: `477`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this, HWND hDlg, HWND *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000dd40`
- `0x1800146c8`
- `0x1800147f0`
- `0x180014bc0`

## import_xrefs

- `SHLWAPI!SHAutoComplete` at `0x180014c29`
- `SHLWAPI!SHAutoComplete` at `0x180014c29`
- `USER32!EnableWindow` at `0x180014c85`
- `USER32!EnableWindow` at `0x180014d82`
- `USER32!EnableWindow` at `0x180014c85`
- `USER32!EnableWindow` at `0x180014d82`
- `USER32!ShowWindow` at `0x180014c58`
- `USER32!ShowWindow` at `0x180014c6e`
- `USER32!ShowWindow` at `0x180014c9d`
- `USER32!ShowWindow` at `0x180014c58`
- `USER32!ShowWindow` at `0x180014c6e`
- `USER32!ShowWindow` at `0x180014c9d`
- `USER32!SetDlgItemTextW` at `0x180014c38`
- `USER32!SetDlgItemTextW` at `0x180014c38`
- `USER32!CheckDlgButton` at `0x180014cbd`
- `USER32!CheckDlgButton` at `0x180014cbd`
- `USER32!GetDlgItem` at `0x180014c1b`
- `USER32!GetDlgItem` at `0x180014c4d`
- `USER32!GetDlgItem` at `0x180014c63`
- `USER32!GetDlgItem` at `0x180014c7a`
- `USER32!GetDlgItem` at `0x180014c92`
- `USER32!GetDlgItem` at `0x180014d77`
- `USER32!GetDlgItem` at `0x180014c1b`
- `USER32!GetDlgItem` at `0x180014c4d`
- `USER32!GetDlgItem` at `0x180014c63`
- `USER32!GetDlgItem` at `0x180014c7a`
- `USER32!GetDlgItem` at `0x180014c92`
- `USER32!GetDlgItem` at `0x180014d77`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::OnInitDialog(WCHAR *this, HWND hDlg, HWND *a3)
{
  HWND DlgItem; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  HWND v9; // rax
  unsigned int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // rdi
  HWND v15; // rax
  int nIDDlgItem[4]; // [rsp+20h] [rbp-58h]
  __m128i si128; // [rsp+30h] [rbp-48h]
  int v18; // [rsp+40h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  SetLTREditDirection(hDlg, 4521);
  DlgItem = GetDlgItem(hDlg, 4521);
  SHAutoComplete(DlgItem, 1u);
  SetDlgItemTextW(hDlg, 4521, this + 20);
  if ( *((_DWORD *)this + 140) )
  {
    v9 = GetDlgItem(hDlg, 4538);
    ShowWindow(v9, 0);
  }
  else
  {
    v6 = GetDlgItem(hDlg, 4520);
    ShowWindow(v6, 0);
    v7 = GetDlgItem(hDlg, 4521);
    ShowWindow(v7, 0);
    v8 = GetDlgItem(hDlg, 4522);
    EnableWindow(v8, 0);
  }
  CheckDlgButton(hDlg, 4523, *(_DWORD *)(*((_QWORD *)this + 71) + 32LL) != 0);
  v10 = CConfigAdvancedPage::InitializeRetryControls((CConfigAdvancedPage *)this, hDlg);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v12 = 26;
LABEL_13:
    WPP_SF_d(v11[2], v12, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, v10);
    return v10;
  }
  v10 = CConfigAdvancedPage::InitializeDiscountRateControls((CConfigAdvancedPage *)this, hDlg);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v12 = 27;
    goto LABEL_13;
  }
  if ( !*((_DWORD *)this + 144) )
  {
    v14 = 0;
    *(__m128i *)nIDDlgItem = _mm_load_si128((const __m128i *)&_xmm);
    v18 = 4535;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v15 = GetDlgItem(hDlg, nIDDlgItem[v14]);
      EnableWindow(v15, 0);
      ++v14;
    }
    while ( v14 != 9 );
  }
  return 0;
}

```

## disassembly

```asm
0x180014bc0  push    rbx
0x180014bc2  push    rsi
0x180014bc3  push    rdi
0x180014bc4  push    r15
0x180014bc6  sub     rsp, 58h
0x180014bca  mov     rbx, rdx
0x180014bcd  mov     rdi, rcx
0x180014bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd7  lea     r15, WPP_GLOBAL_Control
0x180014bde  cmp     rcx, r15
0x180014be1  jz      short loc_180014C07
0x180014be3  test    dword ptr [rcx+1Ch], 100h
0x180014bea  jz      short loc_180014C07
0x180014bec  cmp     byte ptr [rcx+19h], 5
0x180014bf0  jb      short loc_180014C07
0x180014bf2  mov     rcx, [rcx+10h]
0x180014bf6  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014bfd  mov     edx, 18h
0x180014c02  call    WPP_SF_
0x180014c07  mov     esi, 11A9h
0x180014c0c  mov     rcx, rbx; hDlg
0x180014c0f  mov     edx, esi; nIDDlgItem
0x180014c11  call    SetLTREditDirection
0x180014c16  mov     edx, esi; nIDDlgItem
0x180014c18  mov     rcx, rbx; hDlg
0x180014c1b  call    cs:__imp_GetDlgItem
0x180014c21  mov     rcx, rax; hwndEdit
0x180014c24  mov     edx, 1; dwFlags
0x180014c29  call    cs:__imp_SHAutoComplete
0x180014c2f  lea     r8, [rdi+28h]; lpString
0x180014c33  mov     edx, esi; nIDDlgItem
0x180014c35  mov     rcx, rbx; hDlg
0x180014c38  call    cs:__imp_SetDlgItemTextW
0x180014c3e  cmp     dword ptr [rdi+230h], 0
0x180014c45  mov     rcx, rbx; hDlg
0x180014c48  jnz     short loc_180014C8D
0x180014c4a  lea     edx, [rsi-1]; nIDDlgItem
0x180014c4d  call    cs:__imp_GetDlgItem
0x180014c53  mov     rcx, rax; hWnd
0x180014c56  xor     edx, edx; nCmdShow
0x180014c58  call    cs:__imp_ShowWindow
0x180014c5e  mov     edx, esi; nIDDlgItem
0x180014c60  mov     rcx, rbx; hDlg
0x180014c63  call    cs:__imp_GetDlgItem
0x180014c69  mov     rcx, rax; hWnd
0x180014c6c  xor     edx, edx; nCmdShow
0x180014c6e  call    cs:__imp_ShowWindow
0x180014c74  lea     edx, [rsi+1]; nIDDlgItem
0x180014c77  mov     rcx, rbx; hDlg
0x180014c7a  call    cs:__imp_GetDlgItem
0x180014c80  mov     rcx, rax; hWnd
0x180014c83  xor     edx, edx; bEnable
0x180014c85  call    cs:__imp_EnableWindow
0x180014c8b  jmp     short loc_180014CA3
0x180014c8d  mov     edx, 11BAh; nIDDlgItem
0x180014c92  call    cs:__imp_GetDlgItem
0x180014c98  mov     rcx, rax; hWnd
0x180014c9b  xor     edx, edx; nCmdShow
0x180014c9d  call    cs:__imp_ShowWindow
0x180014ca3  mov     rax, [rdi+238h]
0x180014caa  xor     r8d, r8d
0x180014cad  mov     edx, 11ABh; nIDButton
0x180014cb2  mov     rcx, rbx; hDlg
0x180014cb5  cmp     [rax+20h], r8d
0x180014cb9  setnz   r8b; uCheck
0x180014cbd  call    cs:__imp_CheckDlgButton
0x180014cc3  mov     rdx, rbx; HWND
0x180014cc6  mov     rcx, rdi; this
0x180014cc9  call    ?InitializeRetryControls@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z; CConfigAdvancedPage::InitializeRetryControls(HWND__ *)
0x180014cce  mov     esi, eax
0x180014cd0  test    eax, eax
0x180014cd2  jz      short loc_180014D0E
0x180014cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cdb  cmp     rcx, r15
0x180014cde  jz      short loc_180014D07
0x180014ce0  test    dword ptr [rcx+1Ch], 100h
0x180014ce7  jz      short loc_180014D07
0x180014ce9  cmp     byte ptr [rcx+19h], 2
0x180014ced  jb      short loc_180014D07
0x180014cef  mov     edx, 1Ah
0x180014cf4  mov     rcx, [rcx+10h]
0x180014cf8  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014cff  mov     r9d, esi
0x180014d02  call    WPP_SF_d
0x180014d07  mov     eax, esi
0x180014d09  jmp     loc_180014D93
0x180014d0e  mov     rdx, rbx; HWND
0x180014d11  mov     rcx, rdi; this
0x180014d14  call    ?InitializeDiscountRateControls@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z; CConfigAdvancedPage::InitializeDiscountRateControls(HWND__ *)
0x180014d19  mov     esi, eax
0x180014d1b  test    eax, eax
0x180014d1d  jz      short loc_180014D41
0x180014d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d26  cmp     rcx, r15
0x180014d29  jz      short loc_180014D07
0x180014d2b  test    dword ptr [rcx+1Ch], 100h
0x180014d32  jz      short loc_180014D07
0x180014d34  cmp     byte ptr [rcx+19h], 2
0x180014d38  jb      short loc_180014D07
0x180014d3a  mov     edx, 1Bh
0x180014d3f  jmp     short loc_180014CF4
0x180014d41  cmp     dword ptr [rdi+240h], 0
0x180014d48  jnz     short loc_180014D91
0x180014d4a  movdqa  xmm0, cs:__xmm@000011ae000011ab000011aa000011a9
0x180014d52  xor     edi, edi
0x180014d54  movdqa  xmm1, cs:__xmm@000011b6000011b2000011b1000011af
0x180014d5c  movdqu  xmmword ptr [rsp+78h+nIDDlgItem], xmm0
0x180014d62  mov     [rsp+78h+var_38], 11B7h
0x180014d6a  movdqu  [rsp+78h+var_48], xmm1
0x180014d70  mov     edx, [rsp+rdi*4+78h+nIDDlgItem]; nIDDlgItem
0x180014d74  mov     rcx, rbx; hDlg
0x180014d77  call    cs:__imp_GetDlgItem
0x180014d7d  mov     rcx, rax; hWnd
0x180014d80  xor     edx, edx; bEnable
0x180014d82  call    cs:__imp_EnableWindow
0x180014d88  inc     rdi
0x180014d8b  cmp     rdi, 9
0x180014d8f  jnz     short loc_180014D70
0x180014d91  xor     eax, eax
0x180014d93  add     rsp, 58h
0x180014d97  pop     r15
0x180014d99  pop     rdi
0x180014d9a  pop     rsi
0x180014d9b  pop     rbx
0x180014d9c  retn
```

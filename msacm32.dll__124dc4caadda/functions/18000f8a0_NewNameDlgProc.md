# NewNameDlgProc

- ea: `0x18000f8a0`
- end: `0x18000fb4a`
- name: `NewNameDlgProc`
- size: `682`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180009270`
- `0x18000a250`
- `0x18000e300`
- `0x18000f8a0`
- `0x180010c10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fa07`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fae0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fa07`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000fae0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f9c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fa15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f9c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fa15`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x18000faf1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x18000faf1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18000fafe`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18000fafe`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000f952`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000f974`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000fa82`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000fa99`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000f952`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000f974`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000fa82`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000fa99`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000fab5`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000fab5`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18000fb1a`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18000fb1a`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18000fa6a`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18000fa6a`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18000f8e9`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18000f8e9`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowTextW` at `0x18000f98f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowTextW` at `0x18000f98f`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18000f95d`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18000fa8d`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18000f95d`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18000fa8d`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18000f93d`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18000f93d`

## pseudocode

```c
INT_PTR __fastcall NewNameDlgProc(HWND a1, int a2, int a3, HWND a4)
{
  _QWORD *PropW; // rax
  _QWORD *v9; // rsi
  int v10; // ebx
  int v11; // ebx
  BOOL v12; // ebx
  HWND v13; // rax
  unsigned __int16 *v14; // rbx
  HWND DlgItem; // rax
  const WCHAR *v16; // rbp
  __int64 v17; // rcx
  _QWORD *v18; // rbx
  BOOL i; // ecx
  int v20; // eax
  __int64 v21; // r10
  INT_PTR v22; // rdx
  unsigned __int16 *v23; // rbx
  HWND v24; // rax
  HWND v25; // rax
  __int16 v27; // [rsp+20h] [rbp-138h]
  char v28; // [rsp+28h] [rbp-130h]
  WCHAR Buffer[128]; // [rsp+30h] [rbp-128h] BYREF

  if ( (unsigned __int8)IsSendMessageWPresent() )
  {
    PropW = GetPropW(a1, L"MSACM Chooser Prop");
    v9 = PropW;
    v10 = a2 - 2;
    if ( !v10 )
    {
      if ( PropW )
        RemovePropW(a1, L"MSACM Chooser Prop");
      return 0;
    }
    v11 = v10 - 270;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        if ( (unsigned __int16)a3 == 1 )
        {
          v14 = (unsigned __int16 *)PropW[15];
          DlgItem = GetDlgItem(a1, 100);
          v16 = v14 + 1;
          GetWindowTextW(DlgItem, v14 + 1, ((unsigned __int64)*v14 - 2) >> 1);
          if ( (unsigned int)RemoveOutsideWhitespace(v17, v14) )
          {
            v18 = (_QWORD *)v9[17];
            for ( i = 0; v18 && !i; i = v20 == 0 )
            {
              v20 = lstrcmpW(v16, (LPCWSTR)(v18[2] + 2LL));
              v18 = (_QWORD *)*v18;
            }
            v21 = v9[33];
            if ( i )
            {
              ErrorResBox(a1, *(HINSTANCE *)(v21 + 88), 651, v28);
              return 1;
            }
            LoadStringW(*(HINSTANCE *)(v21 + 88), 0x97u, Buffer, 128);
            if ( lstrcmpW(v16, Buffer) )
            {
              v22 = 1;
LABEL_27:
              EndDialog(a1, v22);
              return 1;
            }
            v27 = 653;
          }
          else
          {
            v27 = 652;
          }
          ErrorResBox(a1, *(HINSTANCE *)(v9[33] + 88LL), v27, v28);
          return 1;
        }
        if ( (unsigned __int16)a3 != 2 )
        {
          if ( (unsigned __int16)a3 == 100 && HIWORD(a3) == 768 )
          {
            v12 = GetWindowTextLengthW(a4) != 0;
            v13 = GetDlgItem(a1, 1);
            EnableWindow(v13, v12);
          }
          return 0;
        }
LABEL_26:
        v22 = 0;
        goto LABEL_27;
      }
    }
    else
    {
      if ( PropW || !SetPropW(a1, L"MSACM Chooser Prop", a4) )
        goto LABEL_26;
      v23 = (unsigned __int16 *)*((_QWORD *)a4 + 15);
      v24 = GetDlgItem(a1, 1);
      EnableWindow(v24, 0);
      v25 = GetDlgItem(a1, 100);
      SendMessageW(v25, 0xC5u, ((unsigned __int64)*v23 - 2) >> 1, 0);
      LoadStringW(*(HINSTANCE *)(*((_QWORD *)a4 + 33) + 88LL), (*(_DWORD *)a4 != 1) + 608, Buffer, 128);
      SetDlgItemTextW(a1, 101, Buffer);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f8a0  mov     [rsp+arg_8], rbx
0x18000f8a5  mov     [rsp+arg_10], rbp
0x18000f8aa  push    rsi
0x18000f8ab  push    rdi
0x18000f8ac  push    r14
0x18000f8ae  sub     rsp, 140h
0x18000f8b5  mov     rax, cs:__security_cookie
0x18000f8bc  xor     rax, rsp
0x18000f8bf  mov     [rsp+158h+var_28], rax
0x18000f8c7  mov     r14, r9
0x18000f8ca  mov     rbp, r8
0x18000f8cd  mov     ebx, edx
0x18000f8cf  mov     rdi, rcx
0x18000f8d2  call    IsSendMessageWPresent
0x18000f8d7  test    al, al
0x18000f8d9  jz      loc_18000FB20
0x18000f8df  lea     rdx, gszInstProp; "MSACM Chooser Prop"
0x18000f8e6  mov     rcx, rdi; hWnd
0x18000f8e9  call    cs:__imp_GetPropW
0x18000f8ef  mov     rsi, rax
0x18000f8f2  sub     ebx, 2
0x18000f8f5  jz      loc_18000FB0B
0x18000f8fb  sub     ebx, 10Eh
0x18000f901  jz      loc_18000FA54
0x18000f907  cmp     ebx, 1
0x18000f90a  jnz     loc_18000FB20
0x18000f910  movzx   ecx, bp
0x18000f913  sub     ecx, ebx
0x18000f915  jz      short loc_18000F968
0x18000f917  sub     ecx, ebx
0x18000f919  jz      loc_18000FAF9
0x18000f91f  cmp     ecx, 62h ; 'b'
0x18000f922  jnz     loc_18000FB20
0x18000f928  shr     rbp, 10h
0x18000f92c  mov     eax, 300h
0x18000f931  cmp     bp, ax
0x18000f934  jnz     loc_18000FB20
0x18000f93a  mov     rcx, r14; hWnd
0x18000f93d  call    cs:__imp_GetWindowTextLengthW
0x18000f943  xor     ebx, ebx
0x18000f945  mov     edx, 1; nIDDlgItem
0x18000f94a  test    eax, eax
0x18000f94c  mov     rcx, rdi; hDlg
0x18000f94f  setnz   bl
0x18000f952  call    cs:__imp_GetDlgItem
0x18000f958  mov     rcx, rax; hWnd
0x18000f95b  mov     edx, ebx; bEnable
0x18000f95d  call    cs:__imp_EnableWindow
0x18000f963  jmp     loc_18000FB20
0x18000f968  mov     rbx, [rax+78h]
0x18000f96c  mov     edx, 64h ; 'd'; nIDDlgItem
0x18000f971  mov     rcx, rdi; hDlg
0x18000f974  call    cs:__imp_GetDlgItem
0x18000f97a  movzx   r8d, word ptr [rbx]
0x18000f97e  lea     rbp, [rbx+2]
0x18000f982  sub     r8, 2
0x18000f986  mov     rdx, rbp; lpString
0x18000f989  shr     r8, 1; nMaxCount
0x18000f98c  mov     rcx, rax; hWnd
0x18000f98f  call    cs:__imp_GetWindowTextW
0x18000f995  mov     rdx, rbx
0x18000f998  call    RemoveOutsideWhitespace
0x18000f99d  test    eax, eax
0x18000f99f  jnz     short loc_18000F9AD
0x18000f9a1  mov     [rsp+158h+var_138], 28Ch
0x18000f9a8  jmp     loc_18000FA30
0x18000f9ad  mov     rbx, [rsi+88h]
0x18000f9b4  xor     ecx, ecx
0x18000f9b6  jmp     short loc_18000F9D7
0x18000f9b8  test    ecx, ecx
0x18000f9ba  jnz     short loc_18000F9DC
0x18000f9bc  mov     rdx, [rbx+10h]
0x18000f9c0  mov     rcx, rbp; lpString1
0x18000f9c3  add     rdx, 2; lpString2
0x18000f9c7  call    cs:__imp_lstrcmpW
0x18000f9cd  mov     rbx, [rbx]
0x18000f9d0  xor     ecx, ecx
0x18000f9d2  test    eax, eax
0x18000f9d4  setz    cl
0x18000f9d7  test    rbx, rbx
0x18000f9da  jnz     short loc_18000F9B8
0x18000f9dc  mov     r10, [rsi+108h]
0x18000f9e3  test    ecx, ecx
0x18000f9e5  jz      short loc_18000F9F4
0x18000f9e7  mov     rdx, [r10+58h]
0x18000f9eb  mov     [rsp+158h+var_138], 28Bh
0x18000f9f2  jmp     short loc_18000FA3B
0x18000f9f4  mov     rcx, [r10+58h]; hInstance
0x18000f9f8  lea     r8, [rsp+158h+Buffer]; lpBuffer
0x18000f9fd  mov     r9d, 80h; cchBufferMax
0x18000fa03  lea     edx, [r9+17h]; uID
0x18000fa07  call    cs:__imp_LoadStringW
0x18000fa0d  lea     rdx, [rsp+158h+Buffer]; lpString2
0x18000fa12  mov     rcx, rbp; lpString1
0x18000fa15  call    cs:__imp_lstrcmpW
0x18000fa1b  test    eax, eax
0x18000fa1d  jz      short loc_18000FA29
0x18000fa1f  mov     edx, 1
0x18000fa24  jmp     loc_18000FAFB
0x18000fa29  mov     [rsp+158h+var_138], 28Dh; __int16
0x18000fa30  mov     rdx, [rsi+108h]
0x18000fa37  mov     rdx, [rdx+58h]; hInstance
0x18000fa3b  mov     r9d, 25Bh
0x18000fa41  mov     r8d, 30h ; '0'
0x18000fa47  mov     rcx, rdi; hWnd
0x18000fa4a  call    ErrorResBox
0x18000fa4f  jmp     loc_18000FB04
0x18000fa54  test    rsi, rsi
0x18000fa57  jnz     loc_18000FAF9
0x18000fa5d  mov     r8, r14; hData
0x18000fa60  lea     rdx, gszInstProp; "MSACM Chooser Prop"
0x18000fa67  mov     rcx, rdi; hWnd
0x18000fa6a  call    cs:__imp_SetPropW
0x18000fa70  test    eax, eax
0x18000fa72  jz      loc_18000FAF9
0x18000fa78  mov     rbx, [r14+78h]
0x18000fa7c  lea     edx, [rsi+1]; nIDDlgItem
0x18000fa7f  mov     rcx, rdi; hDlg
0x18000fa82  call    cs:__imp_GetDlgItem
0x18000fa88  mov     rcx, rax; hWnd
0x18000fa8b  xor     edx, edx; bEnable
0x18000fa8d  call    cs:__imp_EnableWindow
0x18000fa93  lea     edx, [rsi+64h]; nIDDlgItem
0x18000fa96  mov     rcx, rdi; hDlg
0x18000fa99  call    cs:__imp_GetDlgItem
0x18000fa9f  movzx   r8d, word ptr [rbx]
0x18000faa3  xor     r9d, r9d; lParam
0x18000faa6  sub     r8, 2
0x18000faaa  mov     edx, 0C5h; Msg
0x18000faaf  shr     r8, 1; wParam
0x18000fab2  mov     rcx, rax; hWnd
0x18000fab5  call    cs:__imp_SendMessageW
0x18000fabb  mov     rcx, [r14+108h]
0x18000fac2  lea     r8, [rsp+158h+Buffer]; lpBuffer
0x18000fac7  xor     edx, edx
0x18000fac9  mov     r9d, 80h; cchBufferMax
0x18000facf  cmp     dword ptr [r14], 1
0x18000fad3  mov     rcx, [rcx+58h]; hInstance
0x18000fad7  setnz   dl
0x18000fada  add     edx, 260h; uID
0x18000fae0  call    cs:__imp_LoadStringW
0x18000fae6  lea     r8, [rsp+158h+Buffer]; lpString
0x18000faeb  mov     rcx, rdi; hDlg
0x18000faee  lea     edx, [rsi+65h]; nIDDlgItem
0x18000faf1  call    cs:__imp_SetDlgItemTextW
0x18000faf7  jmp     short loc_18000FB20
0x18000faf9  xor     edx, edx; nResult
0x18000fafb  mov     rcx, rdi; hDlg
0x18000fafe  call    cs:__imp_EndDialog
0x18000fb04  mov     eax, 1
0x18000fb09  jmp     short loc_18000FB22
0x18000fb0b  test    rsi, rsi
0x18000fb0e  jz      short loc_18000FB20
0x18000fb10  lea     rdx, gszInstProp; "MSACM Chooser Prop"
0x18000fb17  mov     rcx, rdi; hWnd
0x18000fb1a  call    cs:__imp_RemovePropW
0x18000fb20  xor     eax, eax
0x18000fb22  mov     rcx, [rsp+158h+var_28]
0x18000fb2a  xor     rcx, rsp; StackCookie
0x18000fb2d  call    __security_check_cookie
0x18000fb32  lea     r11, [rsp+158h+var_18]
0x18000fb3a  mov     rbx, [r11+28h]
0x18000fb3e  mov     rbp, [r11+30h]
0x18000fb42  mov     rsp, r11
0x18000fb45  pop     r14
0x18000fb47  pop     rdi
0x18000fb48  pop     rsi
0x18000fb49  retn
```

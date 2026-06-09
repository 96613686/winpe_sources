# DrCommand

- ea: `0x18000b07c`
- end: `0x18000b495`
- name: `DrCommand`
- size: `1049`
- prototype: `__int64 __fastcall(HWND *, unsigned __int16, unsigned __int16, HWND)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000b510`

## callees

- `0x18000b004`
- `0x18000b07c`
- `0x18000b580`
- `0x18000b630`
- `0x18000c55c`
- `0x18000c588`
- `0x18000c624`
- `0x18000c700`
- `0x18000c7f0`
- `0x18000c9c8`
- `0x18000cbb0`
- `0x18002cd5c`
- `0x180040b44`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18000b19e`
- `msvcrt!wcspbrk` at `0x18000b19e`
- `USER32!GetWindowLongW` at `0x18000b1e2`
- `USER32!GetWindowLongW` at `0x18000b1e2`
- `USER32!PostMessageW` at `0x18000b3c9`
- `USER32!PostMessageW` at `0x18000b3c9`
- `USER32!GetWindowTextW` at `0x18000b18c`
- `USER32!GetWindowTextW` at `0x18000b18c`
- `USER32!IsDlgButtonChecked` at `0x18000b34f`
- `USER32!IsDlgButtonChecked` at `0x18000b34f`
- `USER32!SendMessageW` at `0x18000b244`
- `USER32!SendMessageW` at `0x18000b28b`
- `USER32!SendMessageW` at `0x18000b2a7`
- `USER32!SendMessageW` at `0x18000b2b2`
- `USER32!SendMessageW` at `0x18000b2c7`
- `USER32!SendMessageW` at `0x18000b244`
- `USER32!SendMessageW` at `0x18000b28b`
- `USER32!SendMessageW` at `0x18000b2a7`
- `USER32!SendMessageW` at `0x18000b2b2`
- `USER32!SendMessageW` at `0x18000b2c7`
- `USER32!EndDialog` at `0x18000b446`
- `USER32!EndDialog` at `0x18000b446`
- `USER32!SetWindowTextW` at `0x18000b1c4`
- `USER32!SetWindowTextW` at `0x18000b1c4`
- `USER32!GetDlgItem` at `0x18000b25b`
- `USER32!GetDlgItem` at `0x18000b25b`
- `USER32!EnableWindow` at `0x18000b1b3`
- `USER32!EnableWindow` at `0x18000b267`
- `USER32!EnableWindow` at `0x18000b1b3`
- `USER32!EnableWindow` at `0x18000b267`
- `rtutils!TracePrintfExA` at `0x18000b0d4`
- `rtutils!TracePrintfExA` at `0x18000b3b1`
- `rtutils!TracePrintfExA` at `0x18000b0d4`
- `rtutils!TracePrintfExA` at `0x18000b3b1`

## string_xrefs

- `0x18000b0c3`: `DrCommand(n=%d,i=%d,c=$%x)`
- `0x18000b3a7`: `DrCommand:GetCoCreateInstanceElevationHandle failed with error: hr=%#x`

## pseudocode

```c
__int64 __fastcall DrCommand(HWND *a1, unsigned __int16 a2, unsigned __int16 a3, HWND a4)
{
  unsigned int v8; // edi
  unsigned int v9; // edi
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi
  unsigned int v15; // edi
  wchar_t *v16; // rax
  HWND DlgItem; // rcx
  unsigned int v18; // eax
  HWND v19; // rcx
  unsigned int v20; // edi
  HWND v21; // rcx
  unsigned int v22; // esi
  _QWORD *v23; // rdi
  HWND v24; // rcx
  int InstanceElevationHandle; // eax
  HWND v26; // rcx
  __int64 v27; // rax
  INT_PTR v28; // rdx
  WCHAR String[264]; // [rsp+30h] [rbp-258h] BYREF

  v8 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DrCommand(n=%d,i=%d,c=$%x)", a2, a3, (_DWORD)a4);
  if ( v8 <= 0x579 )
  {
    if ( v8 == 1401 )
    {
      if ( a2 == 1 )
      {
        if ( (int)SendMessageW(a1[30], 0x147u, 0, 0) < 0 )
          return 1;
        DlgItem = GetDlgItem(a1[1], 1590);
        goto LABEL_28;
      }
LABEL_29:
      if ( a2 )
        return 1;
      v18 = SendMessageW(a4, 0xF0u, 0, 0);
      v19 = a1[6];
      v20 = v18;
      if ( v18 )
      {
        SendMessageW(v19, 0xF1u, 1u, 0);
      }
      else
      {
        SendMessageW(v19, 0xF1u, 0, 0);
        SendMessageW(a1[7], 0xF1u, 0, 0);
        v21 = a1[29];
        if ( v21 )
        {
          (*(void (__fastcall **)(HWND))(*(_QWORD *)v21 + 16LL))(v21);
          a1[29] = 0;
        }
      }
      DrEnableDisablePwControls(a1, v20);
      goto LABEL_21;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 7;
        if ( v11 )
        {
          v12 = v11 - 1092;
          if ( v12 )
          {
            v13 = v12 - 2;
            if ( !v13 )
            {
              if ( a2 != 512 )
              {
                if ( a2 == 256 && !(unsigned int)DrIsPasswordStyleEnabled(a1[3]) )
                {
                  DrClearFriendlyPassword(a1, 1);
                  return 1;
                }
                return 0;
              }
              GetWindowLongW(a1[2], -16);
              goto LABEL_21;
            }
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 3;
              if ( v15 )
              {
                if ( v15 == 1 )
                {
                  DrEditSelectedLocation(a1);
                  return 1;
                }
                return 0;
              }
              DrProperties(a1);
LABEL_21:
              DrPopulatePasswordField(a1, 0, 0, 0);
              return 1;
            }
            if ( a2 != 768 || ((_BYTE)(*a1)[2] & 2) == 0 )
              return 1;
            memset_0(String, 0, 0x202u);
            GetWindowTextW(a1[2], String, 257);
            v16 = wcspbrk(String, L"@\\");
            DlgItem = a1[4];
            if ( v16 )
            {
              EnableWindow(DlgItem, 0);
              SetWindowTextW(a1[4], &WideCharStr);
              return 1;
            }
LABEL_28:
            EnableWindow(DlgItem, 1);
            return 1;
          }
          goto LABEL_29;
        }
LABEL_53:
        if ( *a1 )
        {
          v27 = *(_QWORD *)*a1;
          if ( v27 )
          {
            if ( !*(_QWORD *)(v27 + 376) )
              HrRASDisplayHelp();
          }
        }
        return 1;
      }
      goto LABEL_57;
    }
LABEL_58:
    DrSave(a1);
    v28 = 1;
    goto LABEL_59;
  }
  switch ( v8 )
  {
    case 0x586u:
      if ( a2 == 1 )
      {
        DrLocationsSelChange(a1);
        return 1;
      }
      return 0;
    case 0x588u:
      if ( a2 == 1 )
      {
        DrNumbersSelChange(a1);
        return 1;
      }
      return 0;
    case 0x636u:
      goto LABEL_58;
    case 0x637u:
LABEL_57:
      v28 = 0;
LABEL_59:
      EndDialog(a1[1], v28);
      return 1;
    case 0x638u:
      goto LABEL_53;
  }
  if ( v8 - 1622 <= 1 )
  {
    v22 = 0;
    if ( !a2 && IsDlgButtonChecked(a1[1], v8) == 1 )
    {
      if ( !*(_DWORD *)(*(_QWORD *)*a1 + 360LL) )
      {
        v23 = a1 + 29;
        v24 = a1[29];
        if ( a3 == 1623 )
        {
          if ( !v24 )
          {
            InstanceElevationHandle = GetCoCreateInstanceElevationHandle(
                                        a1[1],
                                        (struct _GUID *)(a1 + 29),
                                        (const struct _GUID *)1);
            if ( InstanceElevationHandle < 0 )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "DrCommand:GetCoCreateInstanceElevationHandle failed with error: hr=%#x",
                  InstanceElevationHandle);
              v26 = a1[6];
              *v23 = 0;
              PostMessageW(v26, 0xF5u, 0, 0);
              return 1;
            }
          }
        }
        else if ( v24 )
        {
          (*(void (__fastcall **)(HWND))(*(_QWORD *)v24 + 16LL))(v24);
          *v23 = 0;
        }
      }
      DrPopulatePasswordField(a1, 0, 0, 0);
      LOBYTE(v22) = a3 == 1622;
      DrPopulateIdentificationFields(a1, v22);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b07c  push    rbx
0x18000b07e  push    rbp
0x18000b07f  push    rsi
0x18000b080  push    rdi
0x18000b081  push    r12
0x18000b083  push    r14
0x18000b085  push    r15
0x18000b087  sub     rsp, 250h
0x18000b08e  mov     rax, cs:__security_cookie
0x18000b095  xor     rax, rsp
0x18000b098  mov     [rsp+288h+var_48], rax
0x18000b0a0  mov     rbx, rcx
0x18000b0a3  movzx   r14d, r8w
0x18000b0a7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000b0ad  mov     r15, r9
0x18000b0b0  movzx   ebp, dx
0x18000b0b3  mov     edi, r14d
0x18000b0b6  cmp     ecx, 0FFFFFFFFh
0x18000b0b9  jz      short loc_18000B0DA
0x18000b0bb  mov     r9d, ebp
0x18000b0be  mov     [rsp+288h+var_260], r15
0x18000b0c3  lea     r8, aDrcommandNDIDC; "DrCommand(n=%d,i=%d,c=$%x)"
0x18000b0ca  mov     [rsp+288h+var_268], r14d
0x18000b0cf  mov     edx, 0Ch; dwFlags
0x18000b0d4  call    cs:__imp_TracePrintfExA
0x18000b0da  mov     eax, 579h
0x18000b0df  mov     r12d, 1
0x18000b0e5  cmp     edi, eax
0x18000b0e7  ja      loc_18000B2FB
0x18000b0ed  jz      loc_18000B22C
0x18000b0f3  sub     edi, r12d
0x18000b0f6  jz      loc_18000B437
0x18000b0fc  sub     edi, r12d
0x18000b0ff  jz      loc_18000B433
0x18000b105  sub     edi, 7
0x18000b108  jz      loc_18000B411
0x18000b10e  sub     edi, 444h
0x18000b114  jz      loc_18000B272
0x18000b11a  sub     edi, 2
0x18000b11d  jz      loc_18000B1CF
0x18000b123  sub     edi, r12d
0x18000b126  jz      short loc_18000B150
0x18000b128  sub     edi, 3
0x18000b12b  jz      short loc_18000B143
0x18000b12d  cmp     edi, r12d
0x18000b130  jnz     loc_18000B471
0x18000b136  mov     rcx, rbx
0x18000b139  call    DrEditSelectedLocation
0x18000b13e  jmp     loc_18000B45C
0x18000b143  mov     rcx, rbx
0x18000b146  call    DrProperties
0x18000b14b  jmp     loc_18000B1E8
0x18000b150  mov     eax, 300h
0x18000b155  cmp     ax, bp
0x18000b158  jnz     loc_18000B45C
0x18000b15e  mov     rax, [rbx]
0x18000b161  test    byte ptr [rax+8], 2
0x18000b165  jz      loc_18000B45C
0x18000b16b  xor     edx, edx; Val
0x18000b16d  lea     rcx, [rsp+288h+String]; void *
0x18000b172  mov     r8d, 202h; Size
0x18000b178  call    memset_0
0x18000b17d  mov     rcx, [rbx+10h]; hWnd
0x18000b181  lea     rdx, [rsp+288h+String]; lpString
0x18000b186  mov     r8d, 101h; nMaxCount
0x18000b18c  call    cs:__imp_GetWindowTextW
0x18000b192  lea     rdx, Control; "@\\"
0x18000b199  lea     rcx, [rsp+288h+String]; String
0x18000b19e  call    cs:__imp_wcspbrk
0x18000b1a4  mov     rcx, [rbx+20h]; hWnd
0x18000b1a8  test    rax, rax
0x18000b1ab  jz      loc_18000B264
0x18000b1b1  xor     edx, edx; bEnable
0x18000b1b3  call    cs:__imp_EnableWindow
0x18000b1b9  mov     rcx, [rbx+20h]; hWnd
0x18000b1bd  lea     rdx, WideCharStr; lpString
0x18000b1c4  call    cs:__imp_SetWindowTextW
0x18000b1ca  jmp     loc_18000B45C
0x18000b1cf  mov     eax, 200h
0x18000b1d4  cmp     bp, ax
0x18000b1d7  jnz     short loc_18000B1FD
0x18000b1d9  mov     rcx, [rbx+10h]; hWnd
0x18000b1dd  mov     edx, 0FFFFFFF0h; nIndex
0x18000b1e2  call    cs:__imp_GetWindowLongW
0x18000b1e8  xor     r9d, r9d
0x18000b1eb  xor     r8d, r8d
0x18000b1ee  xor     edx, edx
0x18000b1f0  mov     rcx, rbx
0x18000b1f3  call    DrPopulatePasswordField
0x18000b1f8  jmp     loc_18000B45C
0x18000b1fd  mov     eax, 100h
0x18000b202  cmp     bp, ax
0x18000b205  jnz     loc_18000B471
0x18000b20b  mov     rcx, [rbx+18h]
0x18000b20f  call    DrIsPasswordStyleEnabled
0x18000b214  test    eax, eax
0x18000b216  jnz     loc_18000B471
0x18000b21c  mov     edx, r12d
0x18000b21f  mov     rcx, rbx
0x18000b222  call    DrClearFriendlyPassword
0x18000b227  jmp     loc_18000B45C
0x18000b22c  cmp     bp, r12w
0x18000b230  jnz     short loc_18000B272
0x18000b232  mov     rcx, [rbx+0F0h]; hWnd
0x18000b239  xor     r9d, r9d; lParam
0x18000b23c  xor     r8d, r8d; wParam
0x18000b23f  mov     edx, 147h; Msg
0x18000b244  call    cs:__imp_SendMessageW
0x18000b24a  test    eax, eax
0x18000b24c  js      loc_18000B45C
0x18000b252  mov     rcx, [rbx+8]; hDlg
0x18000b256  mov     edx, 636h; nIDDlgItem
0x18000b25b  call    cs:__imp_GetDlgItem
0x18000b261  mov     rcx, rax; hWnd
0x18000b264  mov     edx, r12d; bEnable
0x18000b267  call    cs:__imp_EnableWindow
0x18000b26d  jmp     loc_18000B45C
0x18000b272  xor     esi, esi
0x18000b274  cmp     si, bp
0x18000b277  jnz     loc_18000B45C
0x18000b27d  xor     r9d, r9d; lParam
0x18000b280  xor     r8d, r8d; wParam
0x18000b283  mov     edx, 0F0h; Msg
0x18000b288  mov     rcx, r15; hWnd
0x18000b28b  call    cs:__imp_SendMessageW
0x18000b291  mov     rcx, [rbx+30h]; hWnd
0x18000b295  xor     r9d, r9d; lParam
0x18000b298  mov     rdi, rax
0x18000b29b  mov     edx, 0F1h; Msg
0x18000b2a0  test    eax, eax
0x18000b2a2  jz      short loc_18000B2AF
0x18000b2a4  mov     r8, r12; wParam
0x18000b2a7  call    cs:__imp_SendMessageW
0x18000b2ad  jmp     short loc_18000B2EC
0x18000b2af  xor     r8d, r8d; wParam
0x18000b2b2  call    cs:__imp_SendMessageW
0x18000b2b8  mov     rcx, [rbx+38h]; hWnd
0x18000b2bc  xor     r9d, r9d; lParam
0x18000b2bf  xor     r8d, r8d; wParam
0x18000b2c2  mov     edx, 0F1h; Msg
0x18000b2c7  call    cs:__imp_SendMessageW
0x18000b2cd  mov     rcx, [rbx+0E8h]
0x18000b2d4  test    rcx, rcx
0x18000b2d7  jz      short loc_18000B2EC
0x18000b2d9  mov     rax, [rcx]
0x18000b2dc  mov     rax, [rax+10h]
0x18000b2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e5  mov     [rbx+0E8h], rsi
0x18000b2ec  mov     edx, edi
0x18000b2ee  mov     rcx, rbx
0x18000b2f1  call    DrEnableDisablePwControls
0x18000b2f6  jmp     loc_18000B1E8
0x18000b2fb  mov     ecx, edi
0x18000b2fd  sub     ecx, 586h
0x18000b303  jz      loc_18000B461
0x18000b309  sub     ecx, 2
0x18000b30c  jz      loc_18000B44E
0x18000b312  sub     ecx, 0AEh
0x18000b318  jz      loc_18000B437
0x18000b31e  sub     ecx, r12d
0x18000b321  jz      loc_18000B433
0x18000b327  sub     ecx, r12d
0x18000b32a  jz      loc_18000B411
0x18000b330  sub     ecx, 1Eh
0x18000b333  jz      short loc_18000B33E
0x18000b335  cmp     ecx, r12d
0x18000b338  jnz     loc_18000B471
0x18000b33e  xor     esi, esi
0x18000b340  cmp     si, bp
0x18000b343  jnz     loc_18000B471
0x18000b349  mov     rcx, [rbx+8]; hDlg
0x18000b34d  mov     edx, edi; nIDButton
0x18000b34f  call    cs:__imp_IsDlgButtonChecked
0x18000b355  cmp     eax, r12d
0x18000b358  jnz     loc_18000B471
0x18000b35e  mov     rax, [rbx]
0x18000b361  mov     rcx, [rax]
0x18000b364  cmp     [rcx+168h], esi
0x18000b36a  jnz     short loc_18000B3E8
0x18000b36c  mov     eax, 657h
0x18000b371  lea     rdi, [rbx+0E8h]
0x18000b378  mov     rcx, [rdi]
0x18000b37b  cmp     ax, r14w
0x18000b37f  jnz     short loc_18000B3D4
0x18000b381  test    rcx, rcx
0x18000b384  jnz     short loc_18000B3E8
0x18000b386  mov     rcx, [rbx+8]; hwndOwner
0x18000b38a  mov     r8d, r12d
0x18000b38d  mov     rdx, rdi; void **
0x18000b390  call    GetCoCreateInstanceElevationHandle
0x18000b395  test    eax, eax
0x18000b397  jns     short loc_18000B3E8
0x18000b399  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000b39f  cmp     ecx, 0FFFFFFFFh
0x18000b3a2  jz      short loc_18000B3B7
0x18000b3a4  mov     r9d, eax
0x18000b3a7  lea     r8, aDrcommandGetco; "DrCommand:GetCoCreateInstanceElevationH"...
0x18000b3ae  lea     edx, [rsi+0Ch]; dwFlags
0x18000b3b1  call    cs:__imp_TracePrintfExA
0x18000b3b7  mov     rcx, [rbx+30h]; hWnd
0x18000b3bb  xor     r9d, r9d; lParam
0x18000b3be  xor     r8d, r8d; wParam
0x18000b3c1  mov     [rdi], rsi
0x18000b3c4  mov     edx, 0F5h; Msg
0x18000b3c9  call    cs:__imp_PostMessageW
0x18000b3cf  jmp     loc_18000B45C
0x18000b3d4  test    rcx, rcx
0x18000b3d7  jz      short loc_18000B3E8
0x18000b3d9  mov     rax, [rcx]
0x18000b3dc  mov     rax, [rax+10h]
0x18000b3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e5  mov     [rdi], rsi
0x18000b3e8  xor     r9d, r9d
0x18000b3eb  xor     r8d, r8d
0x18000b3ee  xor     edx, edx
0x18000b3f0  mov     rcx, rbx
0x18000b3f3  call    DrPopulatePasswordField
0x18000b3f8  mov     eax, 656h
0x18000b3fd  mov     rcx, rbx
0x18000b400  cmp     r14w, ax
0x18000b404  setz    sil
0x18000b408  mov     edx, esi
0x18000b40a  call    DrPopulateIdentificationFields
0x18000b40f  jmp     short loc_18000B45C
0x18000b411  mov     rax, [rbx]
0x18000b414  xor     esi, esi
0x18000b416  test    rax, rax
0x18000b419  jz      short loc_18000B45C
0x18000b41b  mov     rax, [rax]
0x18000b41e  test    rax, rax
0x18000b421  jz      short loc_18000B45C
0x18000b423  cmp     [rax+178h], rsi
0x18000b42a  jnz     short loc_18000B45C
0x18000b42c  call    HrRASDisplayHelp
0x18000b431  jmp     short loc_18000B45C
0x18000b433  xor     edx, edx
0x18000b435  jmp     short loc_18000B442
0x18000b437  mov     rcx, rbx
0x18000b43a  call    DrSave
0x18000b43f  mov     rdx, r12; nResult
0x18000b442  mov     rcx, [rbx+8]; hDlg
0x18000b446  call    cs:__imp_EndDialog
0x18000b44c  jmp     short loc_18000B45C
0x18000b44e  cmp     bp, r12w
0x18000b452  jnz     short loc_18000B471
0x18000b454  mov     rcx, rbx
0x18000b457  call    DrNumbersSelChange
0x18000b45c  mov     eax, r12d
0x18000b45f  jmp     short loc_18000B473
0x18000b461  cmp     bp, r12w
0x18000b465  jnz     short loc_18000B471
0x18000b467  mov     rcx, rbx
0x18000b46a  call    DrLocationsSelChange
0x18000b46f  jmp     short loc_18000B45C
0x18000b471  xor     eax, eax
0x18000b473  mov     rcx, [rsp+288h+var_48]
0x18000b47b  xor     rcx, rsp; StackCookie
0x18000b47e  call    __security_check_cookie
0x18000b483  add     rsp, 250h
0x18000b48a  pop     r15
0x18000b48c  pop     r14
0x18000b48e  pop     r12
0x18000b490  pop     rdi
0x18000b491  pop     rsi
0x18000b492  pop     rbp
0x18000b493  pop     rbx
0x18000b494  retn
```

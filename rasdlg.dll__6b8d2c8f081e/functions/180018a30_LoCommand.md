# LoCommand

- ea: `0x180018a30`
- end: `0x180018c57`
- name: `LoCommand`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018c60`

## callees

- `0x1800152a8`
- `0x180015498`
- `0x180015e1c`
- `0x180018a30`
- `0x180018fec`
- `0x180019164`
- `0x180019c7c`
- `0x180019fc8`
- `0x18001a5f8`
- `0x180023310`
- `0x180048048`

## import_xrefs

- `USER32!SendMessageW` at `0x180018b58`
- `USER32!SendMessageW` at `0x180018c1c`
- `USER32!SendMessageW` at `0x180018c3e`
- `USER32!SendMessageW` at `0x180018b58`
- `USER32!SendMessageW` at `0x180018c1c`
- `USER32!SendMessageW` at `0x180018c3e`
- `USER32!EnableWindow` at `0x180018b95`
- `USER32!EnableWindow` at `0x180018b95`
- `rtutils!TracePrintfExA` at `0x180018a6e`
- `rtutils!TracePrintfExA` at `0x180018a6e`

## string_xrefs

- `0x180018a5b`: `LoCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall LoCommand(HWND *a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  int v13; // eax
  __int64 v14; // rax
  _WORD *v15; // rcx
  int v16; // eax
  BOOL v17; // edi
  LRESULT ItemDataPtr; // rax
  __int64 v19; // rax
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  int v26; // eax
  __int64 v27; // rbx

  v7 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "LoCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
  if ( v7 > 0x5D4 )
  {
    v21 = v7 - 1495;
    if ( !v21 )
    {
      if ( a2 == 1 )
      {
        v26 = SendMessageW(a1[46], 0x147u, 0, 0);
        v27 = *((_QWORD *)*a1 + 109);
        *(_DWORD *)(v27 + 172) = SendMessageW(a1[46], 0x150u, v26, 0);
      }
      return 0;
    }
    v22 = v21 - 46;
    if ( v22 )
    {
      v23 = v22 - 3;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 53;
          if ( !v25 )
          {
            AdvancedVPNSettingsDlg(a1[1], (__int64)*a1);
            return 0;
          }
          if ( v25 != 204 || !*((_DWORD *)*a1 + 7) )
            return 0;
        }
      }
    }
    if ( a2 )
      return 0;
    LoRbToggle(a1, a3);
    return 1;
  }
  if ( v7 == 1492 )
  {
    LoUseWindowsPwEnable(a1);
    return 1;
  }
  v8 = v7 - 1034;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 137;
      if ( v10 )
      {
        v11 = v10 - 9;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 == 236 && a2 == 1 )
              LoVpnTypeSelChange(a1);
            return 0;
          }
          v13 = SuEditPbHandler(a1 + 166, a2);
        }
        else
        {
          v13 = SuBrowsePbHandler((__int64)(a1 + 166), a2);
        }
      }
      else
      {
        v13 = SuScriptsCbHandler(a1 + 166, a2);
      }
      if ( !v13 )
        return 0;
    }
    else
    {
      v14 = (__int64)*a1;
      if ( *((_DWORD *)*a1 + 7) && !*(_DWORD *)(v14 + 36) && (v15 = *(_WORD **)(v14 + 48)) != 0 && *v15 )
        LoEapPropertiesRemote((__int64)a1);
      else
        LoEapPropertiesLocal(a1);
    }
    return 1;
  }
  v16 = SendMessageW(a1[48], 0x147u, 0, 0);
  v17 = 0;
  if ( v16 >= 0 )
  {
    ItemDataPtr = ComboBox_GetItemDataPtr(a1[48], v16);
    if ( ItemDataPtr )
    {
      v19 = *(_QWORD *)(ItemDataPtr + 16);
      if ( v19 )
        v17 = *(_DWORD *)(v19 + 52) != 0;
    }
  }
  EnableWindow(a1[49], v17);
  return 1;
}

```

## disassembly

```asm
0x180018a30  push    rbx
0x180018a32  push    rbp
0x180018a33  push    rsi
0x180018a34  push    rdi
0x180018a35  push    r14
0x180018a37  sub     rsp, 30h
0x180018a3b  mov     rsi, rcx
0x180018a3e  movzx   r14d, r8w
0x180018a42  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018a48  mov     rax, r9
0x180018a4b  movzx   ebp, dx
0x180018a4e  mov     ebx, r14d
0x180018a51  cmp     ecx, 0FFFFFFFFh
0x180018a54  jz      short loc_180018A74
0x180018a56  mov     [rsp+58h+var_30], rax
0x180018a5b  lea     r8, aLocommandNDIDC; "LoCommand(n=%d,i=%d,c=$%x)"
0x180018a62  mov     r9d, ebp
0x180018a65  mov     [rsp+58h+var_38], ebx
0x180018a69  mov     edx, 0Ch; dwFlags
0x180018a6e  call    cs:__imp_TracePrintfExA
0x180018a74  mov     eax, 5D4h
0x180018a79  cmp     ebx, eax
0x180018a7b  ja      loc_180018BAC
0x180018a81  jz      loc_180018BA2
0x180018a87  sub     ebx, 40Ah
0x180018a8d  jz      loc_180018B46
0x180018a93  sub     ebx, 1
0x180018a96  jz      short loc_180018B0F
0x180018a98  sub     ebx, 89h
0x180018a9e  jz      short loc_180018AF3
0x180018aa0  sub     ebx, 9
0x180018aa3  jz      short loc_180018AE2
0x180018aa5  sub     ebx, 1
0x180018aa8  jz      short loc_180018AD1
0x180018aaa  cmp     ebx, 0ECh
0x180018ab0  jnz     loc_180018C4A
0x180018ab6  mov     ebx, 1
0x180018abb  cmp     bx, bp
0x180018abe  jnz     loc_180018C4A
0x180018ac4  mov     rcx, rsi
0x180018ac7  call    LoVpnTypeSelChange
0x180018acc  jmp     loc_180018C4A
0x180018ad1  lea     rcx, [rsi+530h]
0x180018ad8  movzx   edx, bp
0x180018adb  call    SuEditPbHandler
0x180018ae0  jmp     short loc_180018B02
0x180018ae2  lea     rcx, [rsi+530h]
0x180018ae9  movzx   edx, bp
0x180018aec  call    SuBrowsePbHandler
0x180018af1  jmp     short loc_180018B02
0x180018af3  lea     rcx, [rsi+530h]
0x180018afa  movzx   edx, bp
0x180018afd  call    SuScriptsCbHandler
0x180018b02  test    eax, eax
0x180018b04  jnz     loc_180018BEB
0x180018b0a  jmp     loc_180018C4A
0x180018b0f  mov     rax, [rsi]
0x180018b12  xor     edi, edi
0x180018b14  cmp     [rax+1Ch], edi
0x180018b17  jz      short loc_180018B39
0x180018b19  cmp     [rax+24h], edi
0x180018b1c  jnz     short loc_180018B39
0x180018b1e  mov     rcx, [rax+30h]
0x180018b22  test    rcx, rcx
0x180018b25  jz      short loc_180018B39
0x180018b27  cmp     [rcx], di
0x180018b2a  jz      short loc_180018B39
0x180018b2c  mov     rcx, rsi
0x180018b2f  call    LoEapPropertiesRemote
0x180018b34  jmp     loc_180018BEB
0x180018b39  mov     rcx, rsi
0x180018b3c  call    LoEapPropertiesLocal
0x180018b41  jmp     loc_180018BEB
0x180018b46  mov     rcx, [rsi+180h]; hWnd
0x180018b4d  xor     r9d, r9d; lParam
0x180018b50  xor     r8d, r8d; wParam
0x180018b53  mov     edx, 147h; Msg
0x180018b58  call    cs:__imp_SendMessageW
0x180018b5e  xor     edi, edi
0x180018b60  mov     ebx, 1
0x180018b65  test    eax, eax
0x180018b67  js      short loc_180018B8C
0x180018b69  mov     rcx, [rsi+180h]
0x180018b70  mov     edx, eax
0x180018b72  call    ComboBox_GetItemDataPtr
0x180018b77  test    rax, rax
0x180018b7a  jz      short loc_180018B8C
0x180018b7c  mov     rax, [rax+10h]
0x180018b80  test    rax, rax
0x180018b83  jz      short loc_180018B8C
0x180018b85  cmp     [rax+34h], edi
0x180018b88  jz      short loc_180018B8C
0x180018b8a  mov     edi, ebx
0x180018b8c  mov     rcx, [rsi+188h]; hWnd
0x180018b93  mov     edx, edi; bEnable
0x180018b95  call    cs:__imp_EnableWindow
0x180018b9b  mov     eax, ebx
0x180018b9d  jmp     loc_180018C4C
0x180018ba2  mov     rcx, rsi
0x180018ba5  call    LoUseWindowsPwEnable
0x180018baa  jmp     short loc_180018BEB
0x180018bac  sub     ebx, 5D7h
0x180018bb2  jz      short loc_180018C00
0x180018bb4  xor     edi, edi
0x180018bb6  sub     ebx, 2Eh ; '.'
0x180018bb9  jz      short loc_180018BDA
0x180018bbb  sub     ebx, 3
0x180018bbe  jz      short loc_180018BDA
0x180018bc0  sub     ebx, 1
0x180018bc3  jz      short loc_180018BDA
0x180018bc5  sub     ebx, 35h ; '5'
0x180018bc8  jz      short loc_180018BF2
0x180018bca  cmp     ebx, 0CCh
0x180018bd0  jnz     short loc_180018C4A
0x180018bd2  mov     rax, [rsi]
0x180018bd5  cmp     [rax+1Ch], edi
0x180018bd8  jz      short loc_180018C4A
0x180018bda  test    bp, bp
0x180018bdd  jnz     short loc_180018C4A
0x180018bdf  movzx   edx, r14w
0x180018be3  mov     rcx, rsi
0x180018be6  call    LoRbToggle
0x180018beb  mov     eax, 1
0x180018bf0  jmp     short loc_180018C4C
0x180018bf2  mov     rdx, [rsi]
0x180018bf5  mov     rcx, [rsi+8]; hWnd
0x180018bf9  call    AdvancedVPNSettingsDlg
0x180018bfe  jmp     short loc_180018C4A
0x180018c00  mov     ebx, 1
0x180018c05  cmp     bx, bp
0x180018c08  jnz     short loc_180018C4A
0x180018c0a  mov     rcx, [rsi+170h]; hWnd
0x180018c11  xor     r9d, r9d; lParam
0x180018c14  xor     r8d, r8d; wParam
0x180018c17  mov     edx, 147h; Msg
0x180018c1c  call    cs:__imp_SendMessageW
0x180018c22  mov     rcx, [rsi+170h]; hWnd
0x180018c29  xor     r9d, r9d; lParam
0x180018c2c  movsxd  r8, eax; wParam
0x180018c2f  mov     edx, 150h; Msg
0x180018c34  mov     rax, [rsi]
0x180018c37  mov     rbx, [rax+368h]
0x180018c3e  call    cs:__imp_SendMessageW
0x180018c44  mov     [rbx+0ACh], eax
0x180018c4a  xor     eax, eax
0x180018c4c  add     rsp, 30h
0x180018c50  pop     r14
0x180018c52  pop     rdi
0x180018c53  pop     rsi
0x180018c54  pop     rbp
0x180018c55  pop     rbx
0x180018c56  retn
```

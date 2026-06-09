# LeCommand

- ea: `0x1800106ec`
- end: `0x1800108d6`
- name: `LeCommand`
- size: `490`
- prototype: `__int64 __fastcall(HWND *, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010a70`

## callees

- `0x180010594`
- `0x1800106ec`
- `0x1800108dc`
- `0x180010b40`
- `0x180010c58`
- `0x180011100`
- `0x180011174`
- `0x1800112f8`
- `0x18001148c`
- `0x18003bea0`
- `0x18003c108`
- `0x18004797c`
- `0x180048364`

## import_xrefs

- `USER32!SendMessageW` at `0x18001086f`
- `USER32!SendMessageW` at `0x18001086f`
- `USER32!EndDialog` at `0x18001083b`
- `USER32!EndDialog` at `0x18001083b`
- `USER32!EnableWindow` at `0x1800107d6`
- `USER32!EnableWindow` at `0x1800107e2`
- `USER32!EnableWindow` at `0x1800107f2`
- `USER32!EnableWindow` at `0x1800107fe`
- `USER32!EnableWindow` at `0x1800107d6`
- `USER32!EnableWindow` at `0x1800107e2`
- `USER32!EnableWindow` at `0x1800107f2`
- `USER32!EnableWindow` at `0x1800107fe`
- `rtutils!TracePrintfExA` at `0x180010725`
- `rtutils!TracePrintfExA` at `0x18001082f`
- `rtutils!TracePrintfExA` at `0x180010725`
- `rtutils!TracePrintfExA` at `0x18001082f`

## string_xrefs

- `0x180010712`: `LeCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall LeCommand(HWND *a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // esi
  DWORD v6; // ecx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  WCHAR *Text; // rax
  BOOL v13; // edx
  WCHAR *v14; // rbx
  __int64 v15; // rax
  HWND v16; // rdx
  INT_PTR v17; // rdx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx

  v5 = a2;
  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "LeCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  if ( v7 > 0x5C2 )
  {
    v18 = v7 - 1475;
    if ( !v18 )
    {
      LeUp(a1);
      return 1;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      LeDown(a1);
      return 1;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      LeDelete(a1);
      return 1;
    }
    if ( v20 == 1 )
    {
      if ( v5 == 6 )
        Button_MakeDefault(a1[1], a1[9]);
      return 1;
    }
    return 0;
  }
  if ( v7 == 1474 )
  {
    if ( (_WORD)v5 == 1 )
    {
      LeEnableUpAndDownButtons(a1);
      if ( (int)SendMessageW(a1[11], 0x188u, 0, 0) >= 0 )
        LeItemTextFromListSelection(a1);
    }
    return 1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v17 = (int)LeSaveSettings(a1);
LABEL_25:
    EndDialog(a1[1], v17);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v17 = 0;
    goto LABEL_25;
  }
  v10 = v9 - 1468;
  if ( !v10 )
  {
    if ( (_WORD)v5 == 256 || (_WORD)v5 == 1024 )
    {
      Text = GetText(a1[10]);
      v13 = 0;
      v14 = Text;
      if ( !Text )
        goto LABEL_20;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      if ( v15 && !(unsigned int)IsAllWhite(v14) )
      {
        EnableWindow(a1[4], 1);
        EnableWindow(a1[5], 1);
        v16 = a1[4];
      }
      else
      {
LABEL_20:
        EnableWindow(a1[4], v13);
        EnableWindow(a1[5], 0);
        v16 = a1[9];
      }
      Button_MakeDefault(a1[1], v16);
      Free0(v14);
    }
    return 1;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    LeAdd(a1);
    return 1;
  }
  if ( v11 != 1 )
    return 0;
  LeReplace(a1);
  return 1;
}

```

## disassembly

```asm
0x1800106ec  push    rbx
0x1800106ee  push    rbp
0x1800106ef  push    rsi
0x1800106f0  push    rdi
0x1800106f1  sub     rsp, 38h
0x1800106f5  mov     rdi, rcx
0x1800106f8  movzx   esi, dx
0x1800106fb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180010701  mov     rax, r9
0x180010704  movzx   ebx, r8w
0x180010708  cmp     ecx, 0FFFFFFFFh
0x18001070b  jz      short loc_180010731
0x18001070d  mov     [rsp+58h+var_30], rax
0x180010712  lea     r8, aLecommandNDIDC; "LeCommand(n=%d,i=%d,c=$%x)"
0x180010719  mov     r9d, esi
0x18001071c  mov     [rsp+58h+var_38], ebx
0x180010720  mov     edx, 0Ch; dwFlags
0x180010725  call    cs:__imp_TracePrintfExA
0x18001072b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180010731  mov     eax, 5C2h
0x180010736  mov     ebp, 1
0x18001073b  cmp     ebx, eax
0x18001073d  ja      loc_180010883
0x180010743  jz      loc_180010853
0x180010749  sub     ebx, ebp
0x18001074b  jz      loc_180010846
0x180010751  sub     ebx, ebp
0x180010753  jz      loc_18001081E
0x180010759  sub     ebx, 5BCh
0x18001075f  jz      short loc_180010787
0x180010761  sub     ebx, ebp
0x180010763  jz      short loc_18001077A
0x180010765  cmp     ebx, ebp
0x180010767  jnz     loc_180010897
0x18001076d  mov     rcx, rdi
0x180010770  call    LeReplace
0x180010775  jmp     loc_1800108CB
0x18001077a  mov     rcx, rdi
0x18001077d  call    LeAdd
0x180010782  jmp     loc_1800108CB
0x180010787  mov     eax, 100h
0x18001078c  cmp     si, ax
0x18001078f  jz      short loc_18001079F
0x180010791  mov     eax, 400h
0x180010796  cmp     si, ax
0x180010799  jnz     loc_1800108CB
0x18001079f  mov     rcx, [rdi+50h]; hWnd
0x1800107a3  call    GetText
0x1800107a8  xor     edx, edx; bEnable
0x1800107aa  mov     rbx, rax
0x1800107ad  test    rax, rax
0x1800107b0  jz      short loc_1800107EE
0x1800107b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800107b6  inc     rax
0x1800107b9  cmp     [rbx+rax*2], dx
0x1800107bd  jnz     short loc_1800107B6
0x1800107bf  test    rax, rax
0x1800107c2  jz      short loc_1800107EE
0x1800107c4  mov     rcx, rbx
0x1800107c7  call    IsAllWhite
0x1800107cc  test    eax, eax
0x1800107ce  jnz     short loc_1800107EE
0x1800107d0  mov     rcx, [rdi+20h]; hWnd
0x1800107d4  mov     edx, ebp; bEnable
0x1800107d6  call    cs:__imp_EnableWindow
0x1800107dc  mov     rcx, [rdi+28h]; hWnd
0x1800107e0  mov     edx, ebp; bEnable
0x1800107e2  call    cs:__imp_EnableWindow
0x1800107e8  mov     rdx, [rdi+20h]
0x1800107ec  jmp     short loc_180010808
0x1800107ee  mov     rcx, [rdi+20h]; hWnd
0x1800107f2  call    cs:__imp_EnableWindow
0x1800107f8  mov     rcx, [rdi+28h]; hWnd
0x1800107fc  xor     edx, edx; bEnable
0x1800107fe  call    cs:__imp_EnableWindow
0x180010804  mov     rdx, [rdi+48h]; HWND
0x180010808  mov     rcx, [rdi+8]; hWnd
0x18001080c  call    Button_MakeDefault
0x180010811  mov     rcx, rbx
0x180010814  call    Free0
0x180010819  jmp     loc_1800108CB
0x18001081e  cmp     ecx, 0FFFFFFFFh
0x180010821  jz      short loc_180010835
0x180010823  lea     r8, aCancelPressed; "Cancel pressed"
0x18001082a  mov     edx, 0Ch; dwFlags
0x18001082f  call    cs:__imp_TracePrintfExA
0x180010835  xor     edx, edx; nResult
0x180010837  mov     rcx, [rdi+8]; hDlg
0x18001083b  call    cs:__imp_EndDialog
0x180010841  jmp     loc_1800108CB
0x180010846  mov     rcx, rdi
0x180010849  call    LeSaveSettings
0x18001084e  movsxd  rdx, eax
0x180010851  jmp     short loc_180010837
0x180010853  cmp     si, bp
0x180010856  jnz     short loc_1800108CB
0x180010858  mov     rcx, rdi
0x18001085b  call    LeEnableUpAndDownButtons
0x180010860  mov     rcx, [rdi+58h]; hWnd
0x180010864  xor     r9d, r9d; lParam
0x180010867  xor     r8d, r8d; wParam
0x18001086a  mov     edx, 188h; Msg
0x18001086f  call    cs:__imp_SendMessageW
0x180010875  test    eax, eax
0x180010877  js      short loc_1800108CB
0x180010879  mov     rcx, rdi
0x18001087c  call    LeItemTextFromListSelection
0x180010881  jmp     short loc_1800108CB
0x180010883  sub     ebx, 5C3h
0x180010889  jz      short loc_1800108C3
0x18001088b  sub     ebx, ebp
0x18001088d  jz      short loc_1800108B9
0x18001088f  sub     ebx, ebp
0x180010891  jz      short loc_1800108AF
0x180010893  cmp     ebx, ebp
0x180010895  jz      short loc_18001089B
0x180010897  xor     eax, eax
0x180010899  jmp     short loc_1800108CD
0x18001089b  cmp     esi, 6
0x18001089e  jnz     short loc_1800108CB
0x1800108a0  mov     rdx, [rdi+48h]; HWND
0x1800108a4  mov     rcx, [rdi+8]; hWnd
0x1800108a8  call    Button_MakeDefault
0x1800108ad  jmp     short loc_1800108CB
0x1800108af  mov     rcx, rdi
0x1800108b2  call    LeDelete
0x1800108b7  jmp     short loc_1800108CB
0x1800108b9  mov     rcx, rdi
0x1800108bc  call    LeDown
0x1800108c1  jmp     short loc_1800108CB
0x1800108c3  mov     rcx, rdi
0x1800108c6  call    LeUp
0x1800108cb  mov     eax, ebp
0x1800108cd  add     rsp, 38h
0x1800108d1  pop     rdi
0x1800108d2  pop     rsi
0x1800108d3  pop     rbp
0x1800108d4  pop     rbx
0x1800108d5  retn
```

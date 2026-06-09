# ElCommand

- ea: `0x18001d8f4`
- end: `0x18001db11`
- name: `ElCommand`
- size: `541`
- prototype: `__int64 __fastcall(HWND *lpParameter, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001db20`

## callees

- `0x18001d8f4`
- `0x18001dcd0`
- `0x18001e074`
- `0x180039580`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d9fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d9fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001da66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001da66`
- `USER32!SendMessageW` at `0x18001d997`
- `USER32!SendMessageW` at `0x18001d997`
- `USER32!EndDialog` at `0x18001dadf`
- `USER32!EndDialog` at `0x18001dadf`
- `USER32!SetWindowTextW` at `0x18001da8c`
- `USER32!SetWindowTextW` at `0x18001da8c`
- `rtutils!TracePrintfExA` at `0x18001d947`
- `rtutils!TracePrintfExA` at `0x18001daa5`
- `rtutils!TracePrintfExA` at `0x18001dac2`
- `rtutils!TracePrintfExA` at `0x18001d947`
- `rtutils!TracePrintfExA` at `0x18001daa5`
- `rtutils!TracePrintfExA` at `0x18001dac2`

## string_xrefs

- `0x18001d934`: `ElCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall ElCommand(HWND *lpParameter, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // edi
  DWORD v6; // ecx
  unsigned int v7; // ebx
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  struct tagOFNW v15; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR String[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v18[524]; // [rsp+2E4h] [rbp+1E4h] BYREF

  v5 = a3;
  v6 = g_dwTraceId;
  v7 = 0;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "ElCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v8 = v5 - 1;
  if ( !v8 )
  {
    ElSave(lpParameter);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
    {
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ElCancel");
    }
    if ( lpParameter && !lpParameter[68] )
      EndDialog(lpParameter[72], 0);
    return 1;
  }
  v10 = v9 - 1717;
  if ( !v10 )
    goto LABEL_11;
  v11 = v10 - 4;
  if ( !v11 )
    goto LABEL_11;
  v12 = v11 - 7;
  if ( !v12 )
  {
    *(&v15.lStructSize + 1) = 0;
    memset_0(&v15, 0, 0x94u);
    *(_DWORD *)String = 0;
    memset_0(v18, 0, 0x1FEu);
    if ( !LoadStringW(g_hinstDll, 0x6C9u, Buffer, 256) )
      Buffer[0] = 0;
    memset_0(&v15, 0, sizeof(v15));
    v15.hwndOwner = lpParameter[72];
    v15.lpstrFilter = L"HTML format Log files(*.htm)";
    v15.lpstrDefExt = L"htm";
    v15.lpstrFile = String;
    v15.lpstrTitle = Buffer;
    v15.lStructSize = 152;
    v15.nMaxFile = 257;
    v15.nMaxFileTitle = lstrlenW(Buffer);
    if ( GetSaveFileNameW(&v15) )
      SetWindowTextW(lpParameter[76], String);
    return 1;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_11:
    ElEnableRadioControls(lpParameter);
    return 1;
  }
  if ( v13 == 1 )
    *((_DWORD *)lpParameter + 141) = SendMessageW(lpParameter[80], 0xF0u, 0, 0);
  return v7;
}

```

## disassembly

```asm
0x18001d8f4  push    rbp
0x18001d8f6  push    rbx
0x18001d8f7  push    rsi
0x18001d8f8  push    rdi
0x18001d8f9  lea     rbp, [rsp-408h]
0x18001d901  sub     rsp, 508h
0x18001d908  mov     rax, cs:__security_cookie
0x18001d90f  xor     rax, rsp
0x18001d912  mov     [rbp+420h+var_30], rax
0x18001d919  mov     rsi, rcx
0x18001d91c  movzx   edi, r8w
0x18001d920  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d926  xor     ebx, ebx
0x18001d928  mov     rax, r9
0x18001d92b  cmp     ecx, 0FFFFFFFFh
0x18001d92e  jz      short loc_18001D953
0x18001d930  movzx   r9d, dx
0x18001d934  lea     r8, aElcommandNDIDC; "ElCommand(n=%d,i=%d,c=$%x)"
0x18001d93b  mov     [rsp+520h+var_4F8], rax
0x18001d940  lea     edx, [rbx+0Ch]; dwFlags
0x18001d943  mov     [rsp+520h+var_500], edi
0x18001d947  call    cs:__imp_TracePrintfExA
0x18001d94d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d953  sub     edi, 1
0x18001d956  jz      loc_18001DAE7
0x18001d95c  sub     edi, 1
0x18001d95f  jz      loc_18001DA94
0x18001d965  sub     edi, 6B5h
0x18001d96b  jz      short loc_18001D9A8
0x18001d96d  sub     edi, 4
0x18001d970  jz      short loc_18001D9A8
0x18001d972  sub     edi, 7
0x18001d975  jz      short loc_18001D9B5
0x18001d977  sub     edi, 1
0x18001d97a  jz      short loc_18001D9A8
0x18001d97c  cmp     edi, 1
0x18001d97f  jnz     loc_18001DAF4
0x18001d985  mov     rcx, [rsi+280h]; hWnd
0x18001d98c  xor     r9d, r9d; lParam
0x18001d98f  xor     r8d, r8d; wParam
0x18001d992  mov     edx, 0F0h; Msg
0x18001d997  call    cs:__imp_SendMessageW
0x18001d99d  mov     [rsi+234h], eax
0x18001d9a3  jmp     loc_18001DAF4
0x18001d9a8  mov     rcx, rsi
0x18001d9ab  call    ElEnableRadioControls
0x18001d9b0  jmp     loc_18001DAEF
0x18001d9b5  xor     eax, eax
0x18001d9b7  lea     rcx, [rsp+520h+var_4F0]; void *
0x18001d9bc  xor     edx, edx; Val
0x18001d9be  mov     dword ptr [rsp+520h+var_4F0+4], eax
0x18001d9c2  mov     r8d, 94h; Size
0x18001d9c8  call    memset_0
0x18001d9cd  xor     edx, edx; Val
0x18001d9cf  mov     dword ptr [rbp+420h+String], ebx
0x18001d9d5  mov     r8d, 1FEh; Size
0x18001d9db  lea     rcx, [rbp+420h+var_23C]; void *
0x18001d9e2  call    memset_0
0x18001d9e7  mov     rcx, cs:g_hinstDll; hInstance
0x18001d9ee  lea     r8, [rbp+420h+Buffer]; lpBuffer
0x18001d9f2  mov     r9d, 100h; cchBufferMax
0x18001d9f8  mov     edx, 6C9h; uID
0x18001d9fd  call    cs:__imp_LoadStringW
0x18001da03  test    eax, eax
0x18001da05  jnz     short loc_18001DA0B
0x18001da07  mov     [rbp+420h+Buffer], ax
0x18001da0b  mov     ebx, 98h
0x18001da10  lea     rcx, [rsp+520h+var_4F0]; void *
0x18001da15  mov     r8d, ebx; Size
0x18001da18  xor     edx, edx; Val
0x18001da1a  call    memset_0
0x18001da1f  mov     rax, [rsi+240h]
0x18001da26  lea     rcx, [rbp+420h+Buffer]; lpString
0x18001da2a  mov     [rsp+520h+var_4F0.hwndOwner], rax
0x18001da2f  lea     rax, aHtmlFormatLogF; "HTML format Log files(*.htm)"
0x18001da36  mov     [rsp+520h+var_4F0.lpstrFilter], rax
0x18001da3b  lea     rax, aHtm; "htm"
0x18001da42  mov     [rbp+420h+var_4F0.lpstrDefExt], rax
0x18001da46  lea     rax, [rbp+420h+String]
0x18001da4d  mov     [rsp+520h+var_4F0.lpstrFile], rax
0x18001da52  lea     rax, [rbp+420h+Buffer]
0x18001da56  mov     [rbp+420h+var_4F0.lpstrTitle], rax
0x18001da5a  mov     [rsp+520h+var_4F0.lStructSize], ebx
0x18001da5e  mov     [rsp+520h+var_4F0.nMaxFile], 101h
0x18001da66  call    cs:__imp_lstrlenW
0x18001da6c  lea     rcx, [rsp+520h+var_4F0]; LPOPENFILENAMEW
0x18001da71  mov     [rsp+520h+var_4F0.nMaxFileTitle], eax
0x18001da75  call    GetSaveFileNameW
0x18001da7a  test    eax, eax
0x18001da7c  jz      short loc_18001DAEF
0x18001da7e  mov     rcx, [rsi+260h]; hWnd
0x18001da85  lea     rdx, [rbp+420h+String]; lpString
0x18001da8c  call    cs:__imp_SetWindowTextW
0x18001da92  jmp     short loc_18001DAEF
0x18001da94  cmp     ecx, 0FFFFFFFFh
0x18001da97  jz      short loc_18001DAC8
0x18001da99  lea     r8, aCancelPressed; "Cancel pressed"
0x18001daa0  mov     edx, 0Ch; dwFlags
0x18001daa5  call    cs:__imp_TracePrintfExA
0x18001daab  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001dab1  cmp     ecx, 0FFFFFFFFh
0x18001dab4  jz      short loc_18001DAC8
0x18001dab6  lea     r8, aElcancel; "ElCancel"
0x18001dabd  mov     edx, 0Ch; dwFlags
0x18001dac2  call    cs:__imp_TracePrintfExA
0x18001dac8  test    rsi, rsi
0x18001dacb  jz      short loc_18001DAEF
0x18001dacd  cmp     [rsi+220h], rbx
0x18001dad4  jnz     short loc_18001DAEF
0x18001dad6  mov     rcx, [rsi+240h]; hDlg
0x18001dadd  xor     edx, edx; nResult
0x18001dadf  call    cs:__imp_EndDialog
0x18001dae5  jmp     short loc_18001DAEF
0x18001dae7  mov     rcx, rsi; lpParameter
0x18001daea  call    ElSave
0x18001daef  mov     ebx, 1
0x18001daf4  mov     eax, ebx
0x18001daf6  mov     rcx, [rbp+420h+var_30]
0x18001dafd  xor     rcx, rsp; StackCookie
0x18001db00  call    __security_check_cookie
0x18001db05  add     rsp, 508h
0x18001db0c  pop     rdi
0x18001db0d  pop     rsi
0x18001db0e  pop     rbx
0x18001db0f  pop     rbp
0x18001db10  retn
```

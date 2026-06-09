# L2tpCommand

- ea: `0x180023b84`
- end: `0x180023d14`
- name: `L2tpCommand`
- size: `400`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023d20`

## callees

- `0x180023b84`
- `0x180024558`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180023c80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180023c80`
- `USER32!GetWindowTextW` at `0x180023c6e`
- `USER32!GetWindowTextW` at `0x180023c6e`
- `USER32!SendMessageW` at `0x180023c0a`
- `USER32!SendMessageW` at `0x180023cc5`
- `USER32!SendMessageW` at `0x180023c0a`
- `USER32!SendMessageW` at `0x180023cc5`
- `USER32!SetWindowTextW` at `0x180023c98`
- `USER32!SetWindowTextW` at `0x180023c98`
- `USER32!EnableWindow` at `0x180023c19`
- `USER32!EnableWindow` at `0x180023c2d`
- `USER32!EnableWindow` at `0x180023cd4`
- `USER32!EnableWindow` at `0x180023ce0`
- `USER32!EnableWindow` at `0x180023cf1`
- `USER32!EnableWindow` at `0x180023c19`
- `USER32!EnableWindow` at `0x180023c2d`
- `USER32!EnableWindow` at `0x180023cd4`
- `USER32!EnableWindow` at `0x180023ce0`
- `USER32!EnableWindow` at `0x180023cf1`
- `rtutils!TracePrintfExA` at `0x180023bd1`
- `rtutils!TracePrintfExA` at `0x180023bd1`

## string_xrefs

- `0x180023bbe`: `L2tpCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall L2tpCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  HWND v10; // rcx
  BOOL v11; // edx
  HWND v12; // rcx
  int v14; // ebx
  WCHAR String[264]; // [rsp+30h] [rbp-238h] BYREF

  v6 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "L2tpCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
  if ( !a1 )
    return 0;
  v7 = v6 - 1604;
  if ( !v7 )
  {
    v14 = SendMessageW(*(HWND *)(a1 + 16), 0xF0u, 0, 0);
    EnableWindow(*(HWND *)(a1 + 24), v14);
    EnableWindow(*(HWND *)(a1 + 32), v14);
    v10 = *(HWND *)(a1 + 48);
    v11 = v14 == 0;
    goto LABEL_15;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 != 170 )
      return 0;
    v9 = SendMessageW(*(HWND *)(a1 + 40), 0xF0u, 0, 0);
    EnableWindow(*(HWND *)(a1 + 48), v9);
    EnableWindow(*(HWND *)(a1 + 24), v9 == 0);
    v10 = *(HWND *)(a1 + 32);
    v11 = v9 == 0;
LABEL_15:
    EnableWindow(v10, v11);
    return 0;
  }
  if ( a2 == 256 )
  {
    memset_0(String, 0, 0x202u);
    GetWindowTextW(*(HWND *)(a1 + 32), String, 257);
    if ( !lstrcmpW(String, L"****************") )
    {
      v12 = *(HWND *)(a1 + 32);
      *(_DWORD *)(a1 + 88) = 1;
      SetWindowTextW(v12, &WideCharStr);
    }
  }
  else if ( a2 == 512 )
  {
    RestoreAstericks(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x180023b84  push    rbx
0x180023b86  push    rsi
0x180023b87  push    rdi
0x180023b88  sub     rsp, 250h
0x180023b8f  mov     rax, cs:__security_cookie
0x180023b96  xor     rax, rsp
0x180023b99  mov     [rsp+268h+var_28], rax
0x180023ba1  mov     rsi, rcx
0x180023ba4  movzx   edi, dx
0x180023ba7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180023bad  mov     rax, r9
0x180023bb0  movzx   ebx, r8w
0x180023bb4  cmp     ecx, 0FFFFFFFFh
0x180023bb7  jz      short loc_180023BD7
0x180023bb9  mov     [rsp+268h+var_240], rax
0x180023bbe  lea     r8, aL2tpcommandNDI; "L2tpCommand(n=%d,i=%d,c=$%x)"
0x180023bc5  mov     r9d, edi
0x180023bc8  mov     [rsp+268h+var_248], ebx
0x180023bcc  mov     edx, 0Ch; dwFlags
0x180023bd1  call    cs:__imp_TracePrintfExA
0x180023bd7  test    rsi, rsi
0x180023bda  jz      loc_180023CF7
0x180023be0  sub     ebx, 644h
0x180023be6  jz      loc_180023CB6
0x180023bec  sub     ebx, 1
0x180023bef  jz      short loc_180023C3E
0x180023bf1  cmp     ebx, 0AAh
0x180023bf7  jnz     loc_180023CF7
0x180023bfd  mov     rcx, [rsi+28h]; hWnd
0x180023c01  lea     edx, [rbx+46h]; Msg
0x180023c04  xor     r9d, r9d; lParam
0x180023c07  xor     r8d, r8d; wParam
0x180023c0a  call    cs:__imp_SendMessageW
0x180023c10  mov     rcx, [rsi+30h]; hWnd
0x180023c14  mov     edx, eax; bEnable
0x180023c16  mov     rbx, rax
0x180023c19  call    cs:__imp_EnableWindow
0x180023c1f  mov     rcx, [rsi+18h]; hWnd
0x180023c23  xor     edi, edi
0x180023c25  test    ebx, ebx
0x180023c27  setz    dil
0x180023c2b  mov     edx, edi; bEnable
0x180023c2d  call    cs:__imp_EnableWindow
0x180023c33  mov     rcx, [rsi+20h]
0x180023c37  mov     edx, edi
0x180023c39  jmp     loc_180023CF1
0x180023c3e  mov     eax, 100h
0x180023c43  mov     ebx, 1
0x180023c48  cmp     di, ax
0x180023c4b  jnz     short loc_180023CA0
0x180023c4d  xor     edx, edx; Val
0x180023c4f  lea     rcx, [rsp+268h+String]; void *
0x180023c54  mov     r8d, 202h; Size
0x180023c5a  call    memset_0
0x180023c5f  mov     rcx, [rsi+20h]; hWnd
0x180023c63  lea     rdx, [rsp+268h+String]; lpString
0x180023c68  mov     r8d, 101h; nMaxCount
0x180023c6e  call    cs:__imp_GetWindowTextW
0x180023c74  lea     rdx, String2; "****************"
0x180023c7b  lea     rcx, [rsp+268h+String]; lpString1
0x180023c80  call    cs:__imp_lstrcmpW
0x180023c86  test    eax, eax
0x180023c88  jnz     short loc_180023CB2
0x180023c8a  mov     rcx, [rsi+20h]; hWnd
0x180023c8e  lea     rdx, WideCharStr; lpString
0x180023c95  mov     [rsi+58h], ebx
0x180023c98  call    cs:__imp_SetWindowTextW
0x180023c9e  jmp     short loc_180023CB2
0x180023ca0  mov     ecx, 200h
0x180023ca5  cmp     di, cx
0x180023ca8  jnz     short loc_180023CB2
0x180023caa  mov     rcx, rsi
0x180023cad  call    RestoreAstericks
0x180023cb2  mov     eax, ebx
0x180023cb4  jmp     short loc_180023CF9
0x180023cb6  mov     rcx, [rsi+10h]; hWnd
0x180023cba  xor     r9d, r9d; lParam
0x180023cbd  xor     r8d, r8d; wParam
0x180023cc0  mov     edx, 0F0h; Msg
0x180023cc5  call    cs:__imp_SendMessageW
0x180023ccb  mov     rcx, [rsi+18h]; hWnd
0x180023ccf  mov     edx, eax; bEnable
0x180023cd1  mov     rbx, rax
0x180023cd4  call    cs:__imp_EnableWindow
0x180023cda  mov     rcx, [rsi+20h]; hWnd
0x180023cde  mov     edx, ebx; bEnable
0x180023ce0  call    cs:__imp_EnableWindow
0x180023ce6  mov     rcx, [rsi+30h]; hWnd
0x180023cea  xor     edx, edx
0x180023cec  test    ebx, ebx
0x180023cee  setz    dl; bEnable
0x180023cf1  call    cs:__imp_EnableWindow
0x180023cf7  xor     eax, eax
0x180023cf9  mov     rcx, [rsp+268h+var_28]
0x180023d01  xor     rcx, rsp; StackCookie
0x180023d04  call    __security_check_cookie
0x180023d09  add     rsp, 250h
0x180023d10  pop     rdi
0x180023d11  pop     rsi
0x180023d12  pop     rbx
0x180023d13  retn
```

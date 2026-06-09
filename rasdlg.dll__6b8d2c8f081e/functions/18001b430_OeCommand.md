# OeCommand

- ea: `0x18001b430`
- end: `0x18001b5a6`
- name: `OeCommand`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b5b0`

## callees

- `0x18001b430`
- `0x18001ce58`
- `0x180039124`

## import_xrefs

- `USER32!SendMessageW` at `0x18001b4d1`
- `USER32!SendMessageW` at `0x18001b4fe`
- `USER32!SendMessageW` at `0x18001b528`
- `USER32!SendMessageW` at `0x18001b54a`
- `USER32!SendMessageW` at `0x18001b4d1`
- `USER32!SendMessageW` at `0x18001b4fe`
- `USER32!SendMessageW` at `0x18001b528`
- `USER32!SendMessageW` at `0x18001b54a`
- `USER32!EnableWindow` at `0x18001b559`
- `USER32!EnableWindow` at `0x18001b559`
- `rtutils!TracePrintfExA` at `0x18001b472`
- `rtutils!TracePrintfExA` at `0x18001b472`

## string_xrefs

- `0x18001b45a`: `OeCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall OeCommand(__int64 a1, HWND *a2, unsigned __int16 a3, unsigned __int16 a4, __int64 a5)
{
  __int64 v7; // rcx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  BOOL v19; // edx

  v7 = g_dwTraceId;
  v9 = a4;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "OeCommand(n=%d,i=%d,c=$%x)", a3, a4, a5);
  v10 = v9 - 1302;
  if ( !v10 )
  {
    RouterCallbackDlg(a2[4], (int)*a2);
    return 1;
  }
  v11 = v10 - 117;
  if ( !v11 )
  {
    SHFusionDialogBoxParam(v7, 502, a1, PpDlgProc);
    return 1;
  }
  v12 = v11 - 87;
  if ( !v12 )
  {
    if ( a3 )
      return 0;
    v19 = 1;
    goto LABEL_15;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    if ( a3 )
      return 0;
    SendMessageW(a2[37], 0x14Eu, 0, 0);
    v19 = 0;
LABEL_15:
    EnableWindow(a2[37], v19);
    return 1;
  }
  v14 = v13 - 47;
  if ( !v14 )
  {
    v18 = *((_QWORD *)*a2 + 109);
    *(_DWORD *)(v18 + 116) = SendMessageW(a2[31], 0xF0u, 0, 0);
    return 1;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v17 = *((_QWORD *)*a2 + 109);
    *(_DWORD *)(v17 + 120) = SendMessageW(a2[32], 0xF0u, 0, 0);
    return 1;
  }
  if ( v15 != 228 )
    return 0;
  v16 = *((_QWORD *)*a2 + 109);
  *(_DWORD *)(v16 + 128) = SendMessageW(a2[34], 0xF0u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18001b430  push    rbx
0x18001b432  push    rbp
0x18001b433  push    rsi
0x18001b434  push    rdi
0x18001b435  sub     rsp, 38h
0x18001b439  mov     rbp, rcx
0x18001b43c  movzx   esi, r8w
0x18001b440  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b446  mov     rdi, rdx
0x18001b449  movzx   ebx, r9w
0x18001b44d  cmp     ecx, 0FFFFFFFFh
0x18001b450  jz      short loc_18001B478
0x18001b452  mov     rax, [rsp+58h+arg_20]
0x18001b45a  lea     r8, aOecommandNDIDC; "OeCommand(n=%d,i=%d,c=$%x)"
0x18001b461  mov     [rsp+58h+var_30], rax
0x18001b466  mov     r9d, esi
0x18001b469  mov     edx, 0Ch; dwFlags
0x18001b46e  mov     dword ptr [rsp+58h+var_38], ebx
0x18001b472  call    cs:__imp_TracePrintfExA
0x18001b478  sub     ebx, 516h
0x18001b47e  jz      loc_18001B58C
0x18001b484  sub     ebx, 75h ; 'u'
0x18001b487  jz      loc_18001B571
0x18001b48d  sub     ebx, 57h ; 'W'
0x18001b490  jz      loc_18001B561
0x18001b496  sub     ebx, 1
0x18001b499  jz      loc_18001B533
0x18001b49f  sub     ebx, 2Fh ; '/'
0x18001b4a2  jz      short loc_18001B50C
0x18001b4a4  sub     ebx, 1
0x18001b4a7  jz      short loc_18001B4E2
0x18001b4a9  cmp     ebx, 0E4h
0x18001b4af  jnz     loc_18001B566
0x18001b4b5  mov     rax, [rdi]
0x18001b4b8  xor     r9d, r9d; lParam
0x18001b4bb  mov     rcx, [rdi+110h]; hWnd
0x18001b4c2  xor     r8d, r8d; wParam
0x18001b4c5  mov     edx, 0F0h; Msg
0x18001b4ca  mov     rbx, [rax+368h]
0x18001b4d1  call    cs:__imp_SendMessageW
0x18001b4d7  mov     [rbx+80h], eax
0x18001b4dd  jmp     loc_18001B598
0x18001b4e2  mov     rax, [rdi]
0x18001b4e5  xor     r9d, r9d; lParam
0x18001b4e8  mov     rcx, [rdi+100h]; hWnd
0x18001b4ef  xor     r8d, r8d; wParam
0x18001b4f2  mov     edx, 0F0h; Msg
0x18001b4f7  mov     rbx, [rax+368h]
0x18001b4fe  call    cs:__imp_SendMessageW
0x18001b504  mov     [rbx+78h], eax
0x18001b507  jmp     loc_18001B598
0x18001b50c  mov     rax, [rdi]
0x18001b50f  xor     r9d, r9d; lParam
0x18001b512  mov     rcx, [rdi+0F8h]; hWnd
0x18001b519  xor     r8d, r8d; wParam
0x18001b51c  mov     edx, 0F0h; Msg
0x18001b521  mov     rbx, [rax+368h]
0x18001b528  call    cs:__imp_SendMessageW
0x18001b52e  mov     [rbx+74h], eax
0x18001b531  jmp     short loc_18001B598
0x18001b533  test    si, si
0x18001b536  jnz     short loc_18001B566
0x18001b538  mov     rcx, [rdi+128h]; hWnd
0x18001b53f  xor     r9d, r9d; lParam
0x18001b542  xor     r8d, r8d; wParam
0x18001b545  mov     edx, 14Eh; Msg
0x18001b54a  call    cs:__imp_SendMessageW
0x18001b550  xor     edx, edx; bEnable
0x18001b552  mov     rcx, [rdi+128h]; hWnd
0x18001b559  call    cs:__imp_EnableWindow
0x18001b55f  jmp     short loc_18001B598
0x18001b561  test    si, si
0x18001b564  jz      short loc_18001B56A
0x18001b566  xor     eax, eax
0x18001b568  jmp     short loc_18001B59D
0x18001b56a  mov     edx, 1
0x18001b56f  jmp     short loc_18001B552
0x18001b571  lea     r9, PpDlgProc
0x18001b578  mov     [rsp+58h+var_38], rdi
0x18001b57d  mov     r8, rbp
0x18001b580  mov     edx, 1F6h
0x18001b585  call    SHFusionDialogBoxParam
0x18001b58a  jmp     short loc_18001B598
0x18001b58c  mov     rdx, [rdi]; int
0x18001b58f  mov     rcx, [rdi+20h]; hWnd
0x18001b593  call    RouterCallbackDlg
0x18001b598  mov     eax, 1
0x18001b59d  add     rsp, 38h
0x18001b5a1  pop     rdi
0x18001b5a2  pop     rsi
0x18001b5a3  pop     rbp
0x18001b5a4  pop     rbx
0x18001b5a5  retn
```

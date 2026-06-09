# ItRasApiComplete

- ea: `0x18002a128`
- end: `0x18002a319`
- name: `ItRasApiComplete`
- size: `497`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029ab0`

## callees

- `0x18002a128`
- `0x180048b6c`
- `0x18004d110`

## import_xrefs

- `RASAPI32!RasScriptReceive` at `0x18002a18b`
- `RASAPI32!RasScriptReceive` at `0x18002a18b`
- `USER32!SendMessageA` at `0x18002a29f`
- `USER32!SendMessageA` at `0x18002a30c`
- `USER32!SendMessageA` at `0x18002a29f`
- `USER32!SendMessageA` at `0x18002a30c`
- `USER32!SendMessageW` at `0x18002a288`
- `USER32!SendMessageW` at `0x18002a2b4`
- `USER32!SendMessageW` at `0x18002a2f5`
- `USER32!SendMessageW` at `0x18002a288`
- `USER32!SendMessageW` at `0x18002a2b4`
- `USER32!SendMessageW` at `0x18002a2f5`
- `USER32!EndDialog` at `0x18002a206`
- `USER32!EndDialog` at `0x18002a206`
- `rtutils!TracePrintfExA` at `0x18002a175`
- `rtutils!TracePrintfExA` at `0x18002a1aa`
- `rtutils!TracePrintfExA` at `0x18002a1d6`
- `rtutils!TracePrintfExA` at `0x18002a25b`
- `rtutils!TracePrintfExA` at `0x18002a175`
- `rtutils!TracePrintfExA` at `0x18002a1aa`
- `rtutils!TracePrintfExA` at `0x18002a1d6`
- `rtutils!TracePrintfExA` at `0x18002a25b`

## string_xrefs

- `0x18002a252`: `Read %d`

## pseudocode

```c
__int64 __fastcall ItRasApiComplete(__int64 a1)
{
  DWORD v2; // eax
  DWORD v3; // ecx
  DWORD v4; // edi
  unsigned int v6; // r14d
  LPARAM *v7; // rsi
  unsigned __int16 v8; // bp
  char v9; // cl
  HWND v10; // rcx
  int v11; // [rsp+20h] [rbp-488h]
  unsigned int v12[4]; // [rsp+40h] [rbp-468h] BYREF
  LPARAM lParam[130]; // [rsp+50h] [rbp-458h] BYREF

  v12[0] = 1024;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasScriptReceive");
  v2 = RasScriptReceive(*(_QWORD *)(a1 + 1088), a1 + 56, v12);
  v3 = g_dwTraceId;
  v4 = v2;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "RasScriptReceive=%d", v2);
    v3 = g_dwTraceId;
  }
  if ( v4 )
    goto LABEL_9;
  if ( v12[0] > 0x400 )
  {
    v4 = 24;
    if ( v3 != -1 )
      TracePrintfExA(v3, 0xCu, "RasScriptReceive=%d. Bad Length", 24);
LABEL_9:
    ErrorDlgUtil(*(HWND *)(a1 + 8), 0x14Du, v4, 0, v11, 0x169u, 0xFAu);
    EndDialog(*(HWND *)(a1 + 8), 0);
    return 1;
  }
  v6 = LOWORD(v12[0]);
  if ( LOWORD(v12[0]) )
  {
    v7 = lParam;
    if ( v3 != -1 )
      TracePrintfExA(v3, 0xCu, "Read %d", LOWORD(v12[0]));
    v8 = 0;
    do
    {
      v9 = *(_BYTE *)(v8 + a1 + 56);
      if ( v9 == 13 )
      {
        v10 = *(HWND *)(a1 + 16);
        *(_BYTE *)v7 = 0;
        SendMessageW(v10, 0xB1u, 0xFFFFFFFF, 0);
        SendMessageA(*(HWND *)(a1 + 16), 0xC2u, 0, (LPARAM)lParam);
        SendMessageW(*(HWND *)(a1 + 16), 0x7E7u, 0, 0);
        v7 = lParam;
      }
      else if ( (unsigned __int8)(v9 - 9) > 1u )
      {
        *(_BYTE *)v7 = v9;
        v7 = (LPARAM *)((char *)v7 + 1);
      }
      ++v8;
    }
    while ( v8 < v6 );
    *(_BYTE *)v7 = 0;
    if ( v7 != lParam )
    {
      SendMessageW(*(HWND *)(a1 + 16), 0xB1u, 0xFFFFFFFF, 0);
      SendMessageA(*(HWND *)(a1 + 16), 0xC2u, 0, (LPARAM)lParam);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002a128  push    rbx
0x18002a12a  push    rbp
0x18002a12b  push    rsi
0x18002a12c  push    rdi
0x18002a12d  push    r14
0x18002a12f  push    r15
0x18002a131  sub     rsp, 478h
0x18002a138  mov     rax, cs:__security_cookie
0x18002a13f  xor     rax, rsp
0x18002a142  mov     [rsp+4A8h+var_48], rax
0x18002a14a  mov     rbx, rcx
0x18002a14d  mov     r15d, 0FFFFFFFFh
0x18002a153  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002a159  mov     esi, 400h
0x18002a15e  mov     [rsp+4A8h+var_468], esi
0x18002a162  mov     ebp, 0Ch
0x18002a167  cmp     ecx, r15d
0x18002a16a  jz      short loc_18002A17B
0x18002a16c  lea     r8, aRasscriptrecei_1; "RasScriptReceive"
0x18002a173  mov     edx, ebp; dwFlags
0x18002a175  call    cs:__imp_TracePrintfExA
0x18002a17b  mov     rcx, [rbx+440h]
0x18002a182  lea     rdx, [rbx+38h]
0x18002a186  lea     r8, [rsp+4A8h+var_468]
0x18002a18b  call    cs:__imp_RasScriptReceive
0x18002a191  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002a197  mov     edi, eax
0x18002a199  cmp     ecx, r15d
0x18002a19c  jz      short loc_18002A1B6
0x18002a19e  mov     r9d, eax
0x18002a1a1  lea     r8, aRasscriptrecei; "RasScriptReceive=%d"
0x18002a1a8  mov     edx, ebp; dwFlags
0x18002a1aa  call    cs:__imp_TracePrintfExA
0x18002a1b0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002a1b6  test    edi, edi
0x18002a1b8  jnz     short loc_18002A1DC
0x18002a1ba  cmp     [rsp+4A8h+var_468], esi
0x18002a1be  jbe     short loc_18002A231
0x18002a1c0  mov     edi, 18h
0x18002a1c5  cmp     ecx, r15d
0x18002a1c8  jz      short loc_18002A1DC
0x18002a1ca  mov     r9d, edi
0x18002a1cd  lea     r8, aRasscriptrecei_0; "RasScriptReceive=%d. Bad Length"
0x18002a1d4  mov     edx, ebp; dwFlags
0x18002a1d6  call    cs:__imp_TracePrintfExA
0x18002a1dc  mov     rcx, [rbx+8]; hWnd
0x18002a1e0  xor     r9d, r9d
0x18002a1e3  mov     [rsp+4A8h+var_478], 0FAh; UINT
0x18002a1eb  mov     r8d, edi; dwMessageId
0x18002a1ee  mov     edx, 14Dh; uID
0x18002a1f3  mov     [rsp+4A8h+var_480], 169h; UINT
0x18002a1fb  call    ErrorDlgUtil
0x18002a200  mov     rcx, [rbx+8]; hDlg
0x18002a204  xor     edx, edx; nResult
0x18002a206  call    cs:__imp_EndDialog
0x18002a20c  mov     eax, 1
0x18002a211  mov     rcx, [rsp+4A8h+var_48]
0x18002a219  xor     rcx, rsp; StackCookie
0x18002a21c  call    __security_check_cookie
0x18002a221  add     rsp, 478h
0x18002a228  pop     r15
0x18002a22a  pop     r14
0x18002a22c  pop     rdi
0x18002a22d  pop     rsi
0x18002a22e  pop     rbp
0x18002a22f  pop     rbx
0x18002a230  retn
0x18002a231  movzx   r14d, word ptr [rsp+4A8h+var_468]
0x18002a237  mov     edi, 1
0x18002a23c  test    r14d, r14d
0x18002a23f  jz      loc_18002A312
0x18002a245  lea     rsi, [rsp+4A8h+lParam]
0x18002a24a  cmp     ecx, r15d
0x18002a24d  jz      short loc_18002A265
0x18002a24f  mov     r9d, r14d
0x18002a252  lea     r8, aReadD; "Read %d"
0x18002a259  mov     edx, ebp; dwFlags
0x18002a25b  call    cs:__imp_TracePrintfExA
0x18002a261  xor     ebp, ebp
0x18002a263  jmp     short loc_18002A26A
0x18002a265  xor     eax, eax
0x18002a267  movzx   ebp, ax
0x18002a26a  movzx   eax, bp
0x18002a26d  mov     cl, [rax+rbx+38h]
0x18002a271  cmp     cl, 0Dh
0x18002a274  jnz     short loc_18002A2C1
0x18002a276  mov     rcx, [rbx+10h]; hWnd
0x18002a27a  xor     r9d, r9d; lParam
0x18002a27d  mov     r8, r15; wParam
0x18002a280  mov     byte ptr [rsi], 0
0x18002a283  mov     edx, 0B1h; Msg
0x18002a288  call    cs:__imp_SendMessageW
0x18002a28e  mov     rcx, [rbx+10h]; hWnd
0x18002a292  lea     r9, [rsp+4A8h+lParam]; lParam
0x18002a297  xor     r8d, r8d; wParam
0x18002a29a  mov     edx, 0C2h; Msg
0x18002a29f  call    cs:__imp_SendMessageA
0x18002a2a5  mov     rcx, [rbx+10h]; hWnd
0x18002a2a9  xor     r9d, r9d; lParam
0x18002a2ac  xor     r8d, r8d; wParam
0x18002a2af  mov     edx, 7E7h; Msg
0x18002a2b4  call    cs:__imp_SendMessageW
0x18002a2ba  lea     rsi, [rsp+4A8h+lParam]
0x18002a2bf  jmp     short loc_18002A2CE
0x18002a2c1  lea     eax, [rcx-9]
0x18002a2c4  cmp     al, dil
0x18002a2c7  jbe     short loc_18002A2CE
0x18002a2c9  mov     [rsi], cl
0x18002a2cb  add     rsi, rdi
0x18002a2ce  add     bp, di
0x18002a2d1  movzx   eax, bp
0x18002a2d4  cmp     eax, r14d
0x18002a2d7  jb      short loc_18002A26A
0x18002a2d9  lea     rax, [rsp+4A8h+lParam]
0x18002a2de  mov     byte ptr [rsi], 0
0x18002a2e1  cmp     rsi, rax
0x18002a2e4  jz      short loc_18002A312
0x18002a2e6  mov     rcx, [rbx+10h]; hWnd
0x18002a2ea  xor     r9d, r9d; lParam
0x18002a2ed  mov     r8, r15; wParam
0x18002a2f0  mov     edx, 0B1h; Msg
0x18002a2f5  call    cs:__imp_SendMessageW
0x18002a2fb  mov     rcx, [rbx+10h]; hWnd
0x18002a2ff  lea     r9, [rsp+4A8h+lParam]; lParam
0x18002a304  xor     r8d, r8d; wParam
0x18002a307  mov     edx, 0C2h; Msg
0x18002a30c  call    cs:__imp_SendMessageA
0x18002a312  mov     eax, edi
0x18002a314  jmp     loc_18002A211
```

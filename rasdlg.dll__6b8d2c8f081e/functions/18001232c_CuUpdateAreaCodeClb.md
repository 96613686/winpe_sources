# CuUpdateAreaCodeClb

- ea: `0x18001232c`
- end: `0x180012426`
- name: `CuUpdateAreaCodeClb`
- size: `250`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011cec`
- `0x18001219c`

## callees

- `0x18001232c`
- `0x180047ebc`

## import_xrefs

- `USER32!SendMessageW` at `0x180012376`
- `USER32!SendMessageW` at `0x18001238c`
- `USER32!SendMessageW` at `0x1800123ab`
- `USER32!SendMessageW` at `0x1800123d6`
- `USER32!SendMessageW` at `0x1800123f0`
- `USER32!SendMessageW` at `0x180012407`
- `USER32!SendMessageW` at `0x180012376`
- `USER32!SendMessageW` at `0x18001238c`
- `USER32!SendMessageW` at `0x1800123ab`
- `USER32!SendMessageW` at `0x1800123d6`
- `USER32!SendMessageW` at `0x1800123f0`
- `USER32!SendMessageW` at `0x180012407`
- `rtutils!TracePrintfExA` at `0x180012355`
- `rtutils!TracePrintfExA` at `0x180012355`

## string_xrefs

- `0x180012349`: `CuUpdateAreaCodeClb`

## pseudocode

```c
void __fastcall CuUpdateAreaCodeClb(__int64 a1)
{
  __int64 i; // rdi
  _WORD *v3; // r9
  int v4; // eax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CuUpdateAreaCodeClb");
  if ( *(_QWORD *)(a1 + 104) )
  {
    SendMessageW(*(HWND *)(a1 + 24), 0x14Bu, 0, 0);
    SendMessageW(*(HWND *)(a1 + 24), 0x141u, 0xAu, 0);
    for ( i = **(_QWORD **)(a1 + 104); i; i = *(_QWORD *)(i + 8) )
      SendMessageW(*(HWND *)(a1 + 24), 0x143u, 0, *(_QWORD *)(i + 16));
    v3 = *(_WORD **)(a1 + 112);
    if ( v3 && *v3 )
    {
      v4 = SendMessageW(*(HWND *)(a1 + 24), 0x158u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v3);
      if ( v4 < 0 )
      {
        SendMessageW(*(HWND *)(a1 + 24), 0x14Au, 0, *(_QWORD *)(a1 + 112));
        v4 = 0;
      }
      SendMessageW(*(HWND *)(a1 + 24), 0x14Eu, (unsigned int)v4, 0);
    }
    ComboBox_AutoSizeDroppedWidth(*(HWND *)(a1 + 24));
  }
}

```

## disassembly

```asm
0x18001232c  mov     [rsp+arg_0], rbx
0x180012331  mov     [rsp+arg_8], rsi
0x180012336  push    rdi
0x180012337  sub     rsp, 20h
0x18001233b  mov     rbx, rcx
0x18001233e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012344  cmp     ecx, 0FFFFFFFFh
0x180012347  jz      short loc_18001235B
0x180012349  lea     r8, aCuupdateareaco; "CuUpdateAreaCodeClb"
0x180012350  mov     edx, 0Ch; dwFlags
0x180012355  call    cs:__imp_TracePrintfExA
0x18001235b  xor     esi, esi
0x18001235d  cmp     [rbx+68h], rsi
0x180012361  jz      loc_180012416
0x180012367  mov     rcx, [rbx+18h]; hWnd
0x18001236b  xor     r9d, r9d; lParam
0x18001236e  xor     r8d, r8d; wParam
0x180012371  mov     edx, 14Bh; Msg
0x180012376  call    cs:__imp_SendMessageW
0x18001237c  mov     rcx, [rbx+18h]; hWnd
0x180012380  lea     r8d, [rsi+0Ah]; wParam
0x180012384  xor     r9d, r9d; lParam
0x180012387  mov     edx, 141h; Msg
0x18001238c  call    cs:__imp_SendMessageW
0x180012392  mov     rax, [rbx+68h]
0x180012396  mov     rdi, [rax]
0x180012399  jmp     short loc_1800123B5
0x18001239b  mov     r9, [rdi+10h]; lParam
0x18001239f  xor     r8d, r8d; wParam
0x1800123a2  mov     rcx, [rbx+18h]; hWnd
0x1800123a6  mov     edx, 143h; Msg
0x1800123ab  call    cs:__imp_SendMessageW
0x1800123b1  mov     rdi, [rdi+8]
0x1800123b5  test    rdi, rdi
0x1800123b8  jnz     short loc_18001239B
0x1800123ba  mov     r9, [rbx+70h]; lParam
0x1800123be  test    r9, r9
0x1800123c1  jz      short loc_18001240D
0x1800123c3  cmp     [r9], si
0x1800123c7  jz      short loc_18001240D
0x1800123c9  mov     rcx, [rbx+18h]; hWnd
0x1800123cd  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800123d1  mov     edx, 158h; Msg
0x1800123d6  call    cs:__imp_SendMessageW
0x1800123dc  test    eax, eax
0x1800123de  jns     short loc_1800123F8
0x1800123e0  mov     r9, [rbx+70h]; lParam
0x1800123e4  xor     r8d, r8d; wParam
0x1800123e7  mov     rcx, [rbx+18h]; hWnd
0x1800123eb  mov     edx, 14Ah; Msg
0x1800123f0  call    cs:__imp_SendMessageW
0x1800123f6  mov     eax, esi
0x1800123f8  mov     rcx, [rbx+18h]; hWnd
0x1800123fc  xor     r9d, r9d; lParam
0x1800123ff  mov     r8d, eax; wParam
0x180012402  mov     edx, 14Eh; Msg
0x180012407  call    cs:__imp_SendMessageW
0x18001240d  mov     rcx, [rbx+18h]; hWnd
0x180012411  call    ComboBox_AutoSizeDroppedWidth
0x180012416  mov     rbx, [rsp+28h+arg_0]
0x18001241b  mov     rsi, [rsp+28h+arg_8]
0x180012420  add     rsp, 20h
0x180012424  pop     rdi
0x180012425  retn
```

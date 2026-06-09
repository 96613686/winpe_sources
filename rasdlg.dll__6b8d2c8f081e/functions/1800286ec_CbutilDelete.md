# CbutilDelete

- ea: `0x1800286ec`
- end: `0x1800287ba`
- name: `CbutilDelete`
- size: `206`
- prototype: `LRESULT __fastcall(HWND hWnd, HWND)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001615c`
- `0x180028210`

## callees

- `0x1800286ec`
- `0x180048f0c`
- `0x18004d0d2`

## import_xrefs

- `USER32!SendMessageW` at `0x180028787`
- `USER32!SendMessageW` at `0x18002879b`
- `USER32!SendMessageW` at `0x180028787`
- `USER32!SendMessageW` at `0x18002879b`
- `rtutils!TracePrintfExA` at `0x18002872d`
- `rtutils!TracePrintfExA` at `0x18002872d`

## string_xrefs

- `0x180028723`: `CbDelete`

## pseudocode

```c
LRESULT __fastcall CbutilDelete(HWND hWnd, HWND a2)
{
  LRESULT result; // rax
  va_list Arguments[9]; // [rsp+30h] [rbp-78h] BYREF
  int v6; // [rsp+78h] [rbp-30h]

  memset_0(Arguments, 0, 0x68u);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CbDelete");
  memset_0(Arguments, 0, 0x68u);
  v6 = 52;
  result = MsgDlgUtil(hWnd, 0xCCu, Arguments, g_hinstDll, 0x169u);
  if ( (_DWORD)result == 6 )
  {
    while ( 1 )
    {
      result = SendMessageW(a2, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
      if ( (int)result < 0 )
        break;
      SendMessageW(a2, 0x1008u, (unsigned int)result, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800286ec  mov     [rsp+arg_0], rbx
0x1800286f1  mov     [rsp+arg_8], rsi
0x1800286f6  push    rdi
0x1800286f7  sub     rsp, 0A0h
0x1800286fe  mov     rbx, rdx
0x180028701  mov     rdi, rcx
0x180028704  mov     esi, 68h ; 'h'
0x180028709  lea     rcx, [rsp+0A8h+Arguments]; void *
0x18002870e  mov     r8d, esi; Size
0x180028711  xor     edx, edx; Val
0x180028713  call    memset_0
0x180028718  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002871e  cmp     ecx, 0FFFFFFFFh
0x180028721  jz      short loc_180028733
0x180028723  lea     r8, aCbdelete; "CbDelete"
0x18002872a  lea     edx, [rsi-5Ch]; dwFlags
0x18002872d  call    cs:__imp_TracePrintfExA
0x180028733  mov     r8, rsi; Size
0x180028736  lea     rcx, [rsp+0A8h+Arguments]; void *
0x18002873b  xor     edx, edx; Val
0x18002873d  call    memset_0
0x180028742  mov     r9, cs:g_hinstDll; hInstance
0x180028749  lea     r8, [rsp+0A8h+Arguments]; Arguments
0x18002874e  mov     edx, 0CCh; uID
0x180028753  mov     [rsp+0A8h+var_30], 34h ; '4'
0x18002875b  mov     rcx, rdi; hWnd
0x18002875e  mov     [rsp+0A8h+var_88], 169h; UINT
0x180028766  call    MsgDlgUtil
0x18002876b  cmp     eax, 6
0x18002876e  jnz     short loc_1800287A5
0x180028770  lea     edi, [rax-4]
0x180028773  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028777  jmp     short loc_18002878D
0x180028779  mov     r8d, eax; wParam
0x18002877c  xor     r9d, r9d; lParam
0x18002877f  mov     edx, 1008h; Msg
0x180028784  mov     rcx, rbx; hWnd
0x180028787  call    cs:__imp_SendMessageW
0x18002878d  mov     r9, rdi; lParam
0x180028790  mov     r8, rsi; wParam
0x180028793  mov     edx, 100Ch; Msg
0x180028798  mov     rcx, rbx; hWnd
0x18002879b  call    cs:__imp_SendMessageW
0x1800287a1  test    eax, eax
0x1800287a3  jns     short loc_180028779
0x1800287a5  lea     r11, [rsp+0A8h+var_8]
0x1800287ad  mov     rbx, [r11+10h]
0x1800287b1  mov     rsi, [r11+18h]
0x1800287b5  mov     rsp, r11
0x1800287b8  pop     rdi
0x1800287b9  retn
```

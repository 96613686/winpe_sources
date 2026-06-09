# ComboEx_OnSetFont

- ea: `0x180038c54`
- end: `0x180038da5`
- name: `ComboEx_OnSetFont`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800371b0`
- `0x180038160`

## callees

- `0x1800115f0`
- `0x180018ab8`
- `0x180037b04`
- `0x180038c54`
- `0x18008ea60`

## import_xrefs

- `GDI32!DeleteObject` at `0x180038d81`
- `GDI32!DeleteObject` at `0x180038d81`
- `GDI32!CreateFontIndirectW` at `0x180038cd7`
- `GDI32!CreateFontIndirectW` at `0x180038cd7`
- `USER32!SystemParametersInfoW` at `0x180038ccc`
- `USER32!SystemParametersInfoW` at `0x180038ccc`
- `USER32!SendMessageW` at `0x180038c9d`
- `USER32!SendMessageW` at `0x180038d09`
- `USER32!SendMessageW` at `0x180038d23`
- `USER32!SendMessageW` at `0x180038d3b`
- `USER32!SendMessageW` at `0x180038d61`
- `USER32!SendMessageW` at `0x180038d73`
- `USER32!SendMessageW` at `0x180038c9d`
- `USER32!SendMessageW` at `0x180038d09`
- `USER32!SendMessageW` at `0x180038d23`
- `USER32!SendMessageW` at `0x180038d3b`
- `USER32!SendMessageW` at `0x180038d61`
- `USER32!SendMessageW` at `0x180038d73`

## pseudocode

```c
int __fastcall ComboEx_OnSetFont(__int64 a1, HFONT a2, int a3)
{
  void *v3; // rbp
  LPARAM v4; // r14
  HWND *v5; // rsi
  HFONT v8; // rax
  int CodePageForFont; // eax
  HWND v10; // rcx
  HWND v11; // rcx
  LPARAM v12; // rbx
  int result; // eax
  LOGFONTW pvParam; // [rsp+20h] [rbp-98h] BYREF

  v3 = 0;
  v4 = a3;
  v5 = (HWND *)(a1 + 56);
  if ( (*(_BYTE *)(a1 + 144) & 4) != 0 && *v5 )
    v3 = (void *)SendMessageW(*v5, 0x31u, 0, 0);
  if ( a2 )
  {
    *(_DWORD *)(a1 + 144) &= ~4u;
  }
  else
  {
    memset(&pvParam, 0, sizeof(pvParam));
    SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
    v8 = CreateFontIndirectW(&pvParam);
    *(_DWORD *)(a1 + 144) |= 4u;
    a2 = v8;
  }
  CodePageForFont = GetCodePageForFont(a2);
  v10 = *v5;
  *(_DWORD *)(a1 + 28) = CodePageForFont;
  SendMessageW(v10, 0x30u, (WPARAM)a2, v4);
  v11 = *(HWND *)(a1 + 64);
  if ( v11 )
  {
    SendMessageW(v11, 0x30u, (WPARAM)a2, v4);
    SendMessageW(*(HWND *)(a1 + 64), 0xD3u, 0xFFFFu, 0);
  }
  v12 = (int)ComboEx_ComputeItemHeight(a1, 0);
  SendMessageW(*(HWND *)a1, 0x153u, 0xFFFFFFFFFFFFFFFFuLL, v12);
  result = SendMessageW(*v5, 0x153u, 0, v12);
  if ( v3 )
    return DeleteObject(v3);
  return result;
}

```

## disassembly

```asm
0x180038c54  push    rbx
0x180038c56  push    rbp
0x180038c57  push    rsi
0x180038c58  push    rdi
0x180038c59  push    r14
0x180038c5b  sub     rsp, 90h
0x180038c62  mov     rax, cs:__security_cookie
0x180038c69  xor     rax, rsp
0x180038c6c  mov     [rsp+0B8h+var_38], rax
0x180038c74  xor     ebp, ebp
0x180038c76  movsxd  r14, r8d
0x180038c79  test    byte ptr [rcx+90h], 4
0x180038c80  lea     rsi, [rcx+38h]
0x180038c84  mov     rbx, rdx
0x180038c87  mov     rdi, rcx
0x180038c8a  jz      short loc_180038CA6
0x180038c8c  mov     rcx, [rsi]; hWnd
0x180038c8f  test    rcx, rcx
0x180038c92  jz      short loc_180038CA6
0x180038c94  xor     r9d, r9d; lParam
0x180038c97  lea     edx, [rbp+31h]; Msg
0x180038c9a  xor     r8d, r8d; wParam
0x180038c9d  call    cs:__imp_SendMessageW
0x180038ca3  mov     rbp, rax
0x180038ca6  test    rbx, rbx
0x180038ca9  jnz     short loc_180038CE9
0x180038cab  mov     ebx, 5Ch ; '\'
0x180038cb0  lea     rcx, [rsp+0B8h+pvParam]; void *
0x180038cb5  mov     r8d, ebx; Size
0x180038cb8  xor     edx, edx; Val
0x180038cba  call    memset
0x180038cbf  xor     r9d, r9d; fWinIni
0x180038cc2  lea     r8, [rsp+0B8h+pvParam]; pvParam
0x180038cc7  mov     edx, ebx; uiParam
0x180038cc9  lea     ecx, [rbx-3Dh]; uiAction
0x180038ccc  call    cs:__imp_SystemParametersInfoW
0x180038cd2  lea     rcx, [rsp+0B8h+pvParam]; lplf
0x180038cd7  call    cs:__imp_CreateFontIndirectW
0x180038cdd  or      dword ptr [rdi+90h], 4
0x180038ce4  mov     rbx, rax
0x180038ce7  jmp     short loc_180038CF0
0x180038ce9  and     dword ptr [rdi+90h], 0FFFFFFFBh
0x180038cf0  mov     rcx, rbx; h
0x180038cf3  call    GetCodePageForFont
0x180038cf8  mov     rcx, [rsi]; hWnd
0x180038cfb  mov     r9, r14; lParam
0x180038cfe  mov     r8, rbx; wParam
0x180038d01  mov     [rdi+1Ch], eax
0x180038d04  mov     edx, 30h ; '0'; Msg
0x180038d09  call    cs:__imp_SendMessageW
0x180038d0f  mov     rcx, [rdi+40h]; hWnd
0x180038d13  test    rcx, rcx
0x180038d16  jz      short loc_180038D41
0x180038d18  mov     r9, r14; lParam
0x180038d1b  mov     r8, rbx; wParam
0x180038d1e  mov     edx, 30h ; '0'; Msg
0x180038d23  call    cs:__imp_SendMessageW
0x180038d29  mov     rcx, [rdi+40h]; hWnd
0x180038d2d  xor     r9d, r9d; lParam
0x180038d30  mov     edx, 0D3h; Msg
0x180038d35  mov     r8d, 0FFFFh; wParam
0x180038d3b  call    cs:__imp_SendMessageW
0x180038d41  xor     edx, edx
0x180038d43  mov     rcx, rdi
0x180038d46  call    ComboEx_ComputeItemHeight
0x180038d4b  mov     rcx, [rdi]; hWnd
0x180038d4e  mov     r14d, 153h
0x180038d54  movsxd  rbx, eax
0x180038d57  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180038d5b  mov     r9, rbx; lParam
0x180038d5e  mov     edx, r14d; Msg
0x180038d61  call    cs:__imp_SendMessageW
0x180038d67  mov     rcx, [rsi]; hWnd
0x180038d6a  mov     r9, rbx; lParam
0x180038d6d  xor     r8d, r8d; wParam
0x180038d70  mov     edx, r14d; Msg
0x180038d73  call    cs:__imp_SendMessageW
0x180038d79  test    rbp, rbp
0x180038d7c  jz      short loc_180038D87
0x180038d7e  mov     rcx, rbp; ho
0x180038d81  call    cs:__imp_DeleteObject
0x180038d87  mov     rcx, [rsp+0B8h+var_38]
0x180038d8f  xor     rcx, rsp; StackCookie
0x180038d92  call    __security_check_cookie
0x180038d97  add     rsp, 90h
0x180038d9e  pop     r14
0x180038da0  pop     rdi
0x180038da1  pop     rsi
0x180038da2  pop     rbp
0x180038da3  pop     rbx
0x180038da4  retn
```

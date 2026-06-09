# ProxyWindow::DestroyProxyWindowImpl(void)

- ea: `0x18005ec9c`
- end: `0x18005ed07`
- name: `?DestroyProxyWindowImpl@ProxyWindow@@AEAAXXZ`
- size: `107`
- prototype: `void __fastcall(ProxyWindow *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18005ec60`
- `0x180061ab4`

## callees

- `0x18005ec9c`
- `0x1800a74d4`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18005ecc7`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18005ecc7`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18005ecd6`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18005ecd6`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18005ecec`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18005ecec`

## pseudocode

```c
void __fastcall ProxyWindow::DestroyProxyWindowImpl(ProxyWindow *this)
{
  HWND v2; // rcx

  if ( *((_QWORD *)this + 7) )
  {
    v2 = (HWND)*((_QWORD *)this + 8);
    if ( v2 && GetPropW(v2, L"__D3DProxyProp__") )
    {
      RemovePropW(*((HWND *)this + 8), L"__D3DProxyProp__");
      DwmUpdateProxyWindow(*((HWND *)this + 8), 0);
      *((_QWORD *)this + 8) = 0;
    }
    DestroyWindow(*((HWND *)this + 7));
  }
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x18005ec9c  push    rbx
0x18005ec9e  sub     rsp, 20h
0x18005eca2  cmp     qword ptr [rcx+38h], 0
0x18005eca7  mov     rbx, rcx
0x18005ecaa  jnz     short loc_18005ECBA
0x18005ecac  mov     qword ptr [rbx+38h], 0
0x18005ecb4  add     rsp, 20h
0x18005ecb8  pop     rbx
0x18005ecb9  retn
0x18005ecba  mov     rcx, [rcx+40h]; hWnd
0x18005ecbe  test    rcx, rcx
0x18005ecc1  jnz     short loc_18005ECCF
0x18005ecc3  mov     rcx, [rbx+38h]; hWnd
0x18005ecc7  call    cs:__imp_DestroyWindow
0x18005eccd  jmp     short loc_18005ECAC
0x18005eccf  lea     rdx, aD3dproxyprop; "__D3DProxyProp__"
0x18005ecd6  call    cs:__imp_GetPropW
0x18005ecdc  test    rax, rax
0x18005ecdf  jz      short loc_18005ECC3
0x18005ece1  mov     rcx, [rbx+40h]; hWnd
0x18005ece5  lea     rdx, aD3dproxyprop; "__D3DProxyProp__"
0x18005ecec  call    cs:__imp_RemovePropW
0x18005ecf2  mov     rcx, [rbx+40h]; HWND
0x18005ecf6  xor     edx, edx; HWND
0x18005ecf8  call    ?DwmUpdateProxyWindow@@YAXPEAUHWND__@@0@Z; DwmUpdateProxyWindow(HWND__ *,HWND__ *)
0x18005ecfd  mov     qword ptr [rbx+40h], 0
0x18005ed05  jmp     short loc_18005ECC3
```

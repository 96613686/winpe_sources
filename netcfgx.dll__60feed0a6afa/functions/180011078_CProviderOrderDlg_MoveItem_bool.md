# CProviderOrderDlg::MoveItem(bool)

- ea: `0x180011078`
- end: `0x18001126a`
- name: `?MoveItem@CProviderOrderDlg@@AEAAJ_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(CProviderOrderDlg *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800116b0`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x180011078`

## import_xrefs

- `USER32!SendMessageW` at `0x1800110cd`
- `USER32!SendMessageW` at `0x18001112c`
- `USER32!SendMessageW` at `0x180011150`
- `USER32!SendMessageW` at `0x180011167`
- `USER32!SendMessageW` at `0x18001117c`
- `USER32!SendMessageW` at `0x1800111a4`
- `USER32!SendMessageW` at `0x18001120d`
- `USER32!SendMessageW` at `0x180011224`
- `USER32!SendMessageW` at `0x18001123b`
- `USER32!SendMessageW` at `0x1800110cd`
- `USER32!SendMessageW` at `0x18001112c`
- `USER32!SendMessageW` at `0x180011150`
- `USER32!SendMessageW` at `0x180011167`
- `USER32!SendMessageW` at `0x18001117c`
- `USER32!SendMessageW` at `0x1800111a4`
- `USER32!SendMessageW` at `0x18001120d`
- `USER32!SendMessageW` at `0x180011224`
- `USER32!SendMessageW` at `0x18001123b`
- `USER32!GetDlgItem` at `0x1800110b1`
- `USER32!GetDlgItem` at `0x1800110b1`

## pseudocode

```c
__int64 __fastcall CProviderOrderDlg::MoveItem(HWND *this, char a2)
{
  HWND DlgItem; // rdi
  LRESULT v4; // rsi
  LRESULT v5; // rax
  __int64 v6; // rcx
  LRESULT v7; // rbx
  LPARAM lParam[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v10; // [rsp+30h] [rbp-D0h]
  __int128 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  LPARAM v13[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+80h] [rbp-80h]
  __int128 v15; // [rsp+90h] [rbp-70h]
  __int64 v16; // [rsp+A0h] [rbp-60h]
  char v17; // [rsp+C0h] [rbp-40h] BYREF

  DlgItem = GetDlgItem(this[1], 25011);
  v4 = SendMessageW(DlgItem, 0x110Au, 9u, 0);
  HIDWORD(lParam[0]) = 0;
  v12 = 0;
  *(_QWORD *)&v10 = 0;
  v11 = 0;
  memset_0(v13, 0, 0x60u);
  lParam[1] = v4;
  *((_QWORD *)&v10 + 1) = &v17;
  LODWORD(lParam[0]) = 39;
  LODWORD(v11) = 128;
  SendMessageW(DlgItem, 0x113Eu, 0, (LPARAM)lParam);
  *(_BYTE *)(v12 + 68) = 1;
  if ( a2 )
  {
    v5 = SendMessageW(DlgItem, 0x110Au, 2u, v4);
    if ( v5 )
      v5 = SendMessageW(DlgItem, 0x110Au, 2u, v5);
    v6 = -65535;
  }
  else
  {
    v5 = SendMessageW(DlgItem, 0x110Au, 1u, v4);
    v6 = -65534;
  }
  if ( !v5 )
    v5 = v6;
  v13[1] = v5;
  v13[0] = SendMessageW(DlgItem, 0x110Au, 3u, v4);
  v13[2] = lParam[0];
  v13[3] = lParam[1];
  v14 = v10;
  v15 = v11;
  v16 = v12;
  v7 = SendMessageW(DlgItem, 0x1132u, 0, (LPARAM)v13);
  SendMessageW(DlgItem, 0x1101u, 0, v4);
  SendMessageW(DlgItem, 0x110Bu, 9u, v7);
  return 0;
}

```

## disassembly

```asm
0x180011078  mov     [rsp-8+arg_8], rbx
0x18001107d  mov     [rsp-8+arg_10], rsi
0x180011082  push    rbp
0x180011083  push    rdi
0x180011084  push    r14
0x180011086  lea     rbp, [rsp-0E0h]
0x18001108e  sub     rsp, 1E0h
0x180011095  mov     rax, cs:__security_cookie
0x18001109c  xor     rax, rsp
0x18001109f  mov     [rbp+0F0h+var_20], rax
0x1800110a6  mov     rcx, [rcx+8]; hDlg
0x1800110aa  mov     bl, dl
0x1800110ac  mov     edx, 61B3h; nIDDlgItem
0x1800110b1  call    cs:__imp_GetDlgItem
0x1800110b7  xor     r9d, r9d; lParam
0x1800110ba  mov     r14d, 110Ah
0x1800110c0  mov     edx, r14d; Msg
0x1800110c3  mov     rcx, rax; hWnd
0x1800110c6  mov     rdi, rax
0x1800110c9  lea     r8d, [r9+9]; wParam
0x1800110cd  call    cs:__imp_SendMessageW
0x1800110d3  xorps   xmm0, xmm0
0x1800110d6  lea     rcx, [rsp+1F0h+var_190]; void *
0x1800110db  mov     rsi, rax
0x1800110de  xor     edx, edx; Val
0x1800110e0  xor     eax, eax
0x1800110e2  movups  xmmword ptr [rsp+1F0h+lParam], xmm0
0x1800110e7  mov     [rsp+1F0h+var_1A0], rax
0x1800110ec  movups  [rsp+1F0h+var_1C0], xmm0
0x1800110f1  lea     r8d, [rax+60h]; Size
0x1800110f5  movups  [rsp+1F0h+var_1B0], xmm0
0x1800110fa  call    memset_0
0x1800110ff  lea     rax, [rbp+0F0h+var_130]
0x180011103  mov     [rsp+1F0h+lParam+8], rsi
0x180011108  lea     r9, [rsp+1F0h+lParam]; lParam
0x18001110d  mov     qword ptr [rsp+1F0h+var_1C0+8], rax
0x180011112  xor     r8d, r8d; wParam
0x180011115  mov     dword ptr [rsp+1F0h+lParam], 27h ; '''
0x18001111d  lea     edx, [r14+34h]; Msg
0x180011121  mov     dword ptr [rsp+1F0h+var_1B0], 80h
0x180011129  mov     rcx, rdi; hWnd
0x18001112c  call    cs:__imp_SendMessageW
0x180011132  mov     rax, [rsp+1F0h+var_1A0]
0x180011137  mov     r9, rsi; lParam
0x18001113a  mov     edx, r14d; Msg
0x18001113d  mov     rcx, rdi; hWnd
0x180011140  mov     byte ptr [rax+44h], 1
0x180011144  test    bl, bl
0x180011146  jz      short loc_180011176
0x180011148  mov     ebx, 2
0x18001114d  mov     r8d, ebx; wParam
0x180011150  call    cs:__imp_SendMessageW
0x180011156  test    rax, rax
0x180011159  jz      short loc_18001116D
0x18001115b  mov     r9, rax; lParam
0x18001115e  mov     r8d, ebx; wParam
0x180011161  mov     edx, r14d; Msg
0x180011164  mov     rcx, rdi; hWnd
0x180011167  call    cs:__imp_SendMessageW
0x18001116d  mov     rcx, 0FFFFFFFFFFFF0001h
0x180011174  jmp     short loc_180011189
0x180011176  mov     r8d, 1; wParam
0x18001117c  call    cs:__imp_SendMessageW
0x180011182  mov     rcx, 0FFFFFFFFFFFF0002h
0x180011189  test    rax, rax
0x18001118c  mov     r9, rsi; lParam
0x18001118f  mov     r8d, 3; wParam
0x180011195  mov     edx, r14d; Msg
0x180011198  cmovz   rax, rcx
0x18001119c  mov     rcx, rdi; hWnd
0x18001119f  mov     [rsp+1F0h+var_188], rax
0x1800111a4  call    cs:__imp_SendMessageW
0x1800111aa  movsd   xmm0, qword ptr [rsp+1F0h+var_1B0+4]
0x1800111b0  lea     r9, [rsp+1F0h+var_190]; lParam
0x1800111b5  mov     [rsp+1F0h+var_190], rax
0x1800111ba  xor     r8d, r8d; wParam
0x1800111bd  mov     eax, dword ptr [rsp+1F0h+lParam]
0x1800111c1  mov     edx, 1132h; Msg
0x1800111c6  mov     dword ptr [rsp+1F0h+var_180], eax
0x1800111ca  mov     rcx, rdi; hWnd
0x1800111cd  mov     eax, dword ptr [rsp+1F0h+lParam+4]
0x1800111d1  mov     dword ptr [rsp+1F0h+var_180+4], eax
0x1800111d5  mov     rax, [rsp+1F0h+lParam+8]
0x1800111da  mov     [rsp+1F0h+var_178], rax
0x1800111df  mov     rax, qword ptr [rsp+1F0h+var_1C0]
0x1800111e4  mov     qword ptr [rbp+0F0h+var_170], rax
0x1800111e8  mov     rax, qword ptr [rsp+1F0h+var_1C0+8]
0x1800111ed  mov     qword ptr [rbp+0F0h+var_170+8], rax
0x1800111f1  mov     eax, dword ptr [rsp+1F0h+var_1B0]
0x1800111f5  mov     [rbp+0F0h+var_160], eax
0x1800111f8  mov     eax, dword ptr [rsp+1F0h+var_1B0+0Ch]
0x1800111fc  mov     [rbp+0F0h+var_154], eax
0x1800111ff  mov     rax, [rsp+1F0h+var_1A0]
0x180011204  mov     [rbp+0F0h+var_150], rax
0x180011208  movsd   [rbp+0F0h+var_15C], xmm0
0x18001120d  call    cs:__imp_SendMessageW
0x180011213  mov     r9, rsi; lParam
0x180011216  xor     r8d, r8d; wParam
0x180011219  mov     edx, 1101h; Msg
0x18001121e  mov     rcx, rdi; hWnd
0x180011221  mov     rbx, rax
0x180011224  call    cs:__imp_SendMessageW
0x18001122a  mov     r9, rbx; lParam
0x18001122d  mov     edx, 110Bh; Msg
0x180011232  mov     r8d, 9; wParam
0x180011238  mov     rcx, rdi; hWnd
0x18001123b  call    cs:__imp_SendMessageW
0x180011241  xor     eax, eax
0x180011243  mov     rcx, [rbp+0F0h+var_20]
0x18001124a  xor     rcx, rsp; StackCookie
0x18001124d  call    __security_check_cookie
0x180011252  lea     r11, [rsp+1F0h+var_10]
0x18001125a  mov     rbx, [r11+28h]
0x18001125e  mov     rsi, [r11+30h]
0x180011262  mov     rsp, r11
0x180011265  pop     r14
0x180011267  pop     rdi
0x180011268  pop     rbp
0x180011269  retn
```

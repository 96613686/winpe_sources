# CConfigureApps::SetListViewColumnWidths(int,int,int,int,int)

- ea: `0x18001af68`
- end: `0x18001b1ca`
- name: `?SetListViewColumnWidths@CConfigureApps@@AEAAXHHHHH@Z`
- size: `610`
- prototype: `void __fastcall(CConfigureApps *__hidden this, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a720`

## callees

- `0x180019128`
- `0x18001ae20`
- `0x18001af68`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x18001afcd`
- `USER32!SendMessageW` at `0x18001afff`
- `USER32!SendMessageW` at `0x18001b01c`
- `USER32!SendMessageW` at `0x18001b03e`
- `USER32!SendMessageW` at `0x18001b0ad`
- `USER32!SendMessageW` at `0x18001b14c`
- `USER32!SendMessageW` at `0x18001b180`
- `USER32!SendMessageW` at `0x18001afcd`
- `USER32!SendMessageW` at `0x18001afff`
- `USER32!SendMessageW` at `0x18001b01c`
- `USER32!SendMessageW` at `0x18001b03e`
- `USER32!SendMessageW` at `0x18001b0ad`
- `USER32!SendMessageW` at `0x18001b14c`
- `USER32!SendMessageW` at `0x18001b180`
- `USER32!DrawTextW` at `0x18001b0f9`
- `USER32!DrawTextW` at `0x18001b0f9`
- `GDI32!CreateCompatibleDC` at `0x18001afac`
- `GDI32!CreateCompatibleDC` at `0x18001afac`
- `GDI32!DeleteDC` at `0x18001b19a`
- `GDI32!DeleteDC` at `0x18001b19a`
- `GDI32!SelectObject` at `0x18001afd9`
- `GDI32!SelectObject` at `0x18001b0cf`
- `GDI32!SelectObject` at `0x18001b115`
- `GDI32!SelectObject` at `0x18001b191`
- `GDI32!SelectObject` at `0x18001afd9`
- `GDI32!SelectObject` at `0x18001b0cf`
- `GDI32!SelectObject` at `0x18001b115`
- `GDI32!SelectObject` at `0x18001b191`

## pseudocode

```c
void __fastcall CConfigureApps::SetListViewColumnWidths(HWND *this, __int64 a2, int a3, __int64 a4, int a5, int a6)
{
  int v7; // ebx
  HDC CompatibleDC; // rdi
  void *v9; // rax
  void *v10; // r13
  HWND v11; // rax
  HWND v12; // r15
  int v13; // r12d
  int v14; // esi
  int v15; // r13d
  int v16; // edx
  int v17; // ebx
  unsigned __int16 v18; // ax
  HGDIOBJ v19; // [rsp+38h] [rbp-C8h]
  HGDIOBJ h; // [rsp+48h] [rbp-B8h]
  HGDIOBJ v22; // [rsp+50h] [rbp-B0h]
  LPARAM lParam; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpchText; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+78h] [rbp-88h]
  struct tagRECT rc; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v27; // [rsp+C0h] [rbp-40h] BYREF

  v7 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    v9 = (void *)SendMessageW(this[7], 0x31u, 0, 0);
    v22 = SelectObject(CompatibleDC, v9);
    v10 = v22;
    if ( v22 )
    {
      v11 = (HWND)SendMessageW(this[7], 0x101Fu, 0, 0);
      v12 = v11;
      if ( v11 )
      {
        h = (HGDIOBJ)SendMessageW(v11, 0x31u, 0, 0);
        if ( h )
        {
          v13 = SendMessageW(v12, 0x1200u, 0, 0);
          if ( v13 > 0 )
          {
            GetHeaderPadding(this[7]);
            v14 = 0;
            v15 = 0;
            while ( v14 < v13 )
            {
              memset_0(&lParam, 0, 0x48u);
              lpchText = (LPCWSTR)&v27;
              LODWORD(lParam) = 2;
              v27 = 0;
              v25 = 512;
              if ( (unsigned int)SendMessageW(v12, 0x120Bu, v14, (LPARAM)&lParam) )
              {
                if ( *lpchText )
                {
                  v19 = SelectObject(CompatibleDC, h);
                  rc = 0;
                  if ( DrawTextW(CompatibleDC, lpchText, -1, &rc, 0x100520u) )
                    v7 = rc.right - rc.left;
                  SelectObject(CompatibleDC, v19);
                }
                if ( v14 )
                {
                  v17 = DirectUI::RelPixToPixel((DirectUI *)5, v16) + v7;
                  if ( v17 > a5 )
                    v17 = a5;
                  SendMessageW(this[7], 0x101Eu, v14, (unsigned __int16)v17);
                  v15 += v17;
                }
                v7 = 0;
              }
              ++v14;
            }
            v18 = a6 - v15;
            if ( a6 - v15 < a3 )
              v18 = a3;
            SendMessageW(this[7], 0x101Eu, 0, v18);
            v10 = v22;
          }
        }
      }
      SelectObject(CompatibleDC, v10);
    }
    DeleteDC(CompatibleDC);
  }
}

```

## disassembly

```asm
0x18001af68  mov     [rsp-8+arg_8], rbx
0x18001af6d  push    rbp
0x18001af6e  push    rsi
0x18001af6f  push    rdi
0x18001af70  push    r12
0x18001af72  push    r13
0x18001af74  push    r14
0x18001af76  push    r15
0x18001af78  lea     rbp, [rsp-3D0h]
0x18001af80  sub     rsp, 4D0h
0x18001af87  mov     rax, cs:__security_cookie
0x18001af8e  xor     rax, rsp
0x18001af91  mov     [rbp+400h+var_40], rax
0x18001af98  mov     r14, rcx
0x18001af9b  mov     [rsp+500h+var_4C0], r8d
0x18001afa0  xor     ebx, ebx
0x18001afa2  xor     ecx, ecx; hdc
0x18001afa4  mov     [rsp+500h+var_4CC], ebx
0x18001afa8  mov     [rsp+500h+var_4D0], ebx
0x18001afac  call    cs:__imp_CreateCompatibleDC
0x18001afb2  mov     rdi, rax
0x18001afb5  test    rax, rax
0x18001afb8  jz      loc_18001B1A0
0x18001afbe  mov     rcx, [r14+38h]; hWnd
0x18001afc2  lea     esi, [rbx+31h]
0x18001afc5  mov     edx, esi; Msg
0x18001afc7  xor     r9d, r9d; lParam
0x18001afca  xor     r8d, r8d; wParam
0x18001afcd  call    cs:__imp_SendMessageW
0x18001afd3  mov     rdx, rax; h
0x18001afd6  mov     rcx, rdi; hdc
0x18001afd9  call    cs:__imp_SelectObject
0x18001afdf  mov     [rsp+500h+var_4B0], rax
0x18001afe4  mov     r13, rax
0x18001afe7  test    rax, rax
0x18001afea  jz      loc_18001B197
0x18001aff0  mov     rcx, [r14+38h]; hWnd
0x18001aff4  xor     r9d, r9d; lParam
0x18001aff7  xor     r8d, r8d; wParam
0x18001affa  mov     edx, 101Fh; Msg
0x18001afff  call    cs:__imp_SendMessageW
0x18001b005  mov     r15, rax
0x18001b008  test    rax, rax
0x18001b00b  jz      loc_18001B18B
0x18001b011  xor     r9d, r9d; lParam
0x18001b014  xor     r8d, r8d; wParam
0x18001b017  mov     edx, esi; Msg
0x18001b019  mov     rcx, rax; hWnd
0x18001b01c  call    cs:__imp_SendMessageW
0x18001b022  mov     [rsp+500h+h], rax
0x18001b027  test    rax, rax
0x18001b02a  jz      loc_18001B18B
0x18001b030  xor     r9d, r9d; lParam
0x18001b033  xor     r8d, r8d; wParam
0x18001b036  mov     edx, 1200h; Msg
0x18001b03b  mov     rcx, r15; hWnd
0x18001b03e  call    cs:__imp_SendMessageW
0x18001b044  mov     r12, rax
0x18001b047  test    eax, eax
0x18001b049  jle     loc_18001B18B
0x18001b04f  mov     rcx, [r14+38h]; hWnd
0x18001b053  lea     r8, [rsp+500h+var_4D0]
0x18001b058  lea     rdx, [rsp+500h+var_4CC]
0x18001b05d  call    GetHeaderPadding
0x18001b062  mov     esi, ebx
0x18001b064  mov     r13d, ebx
0x18001b067  cmp     esi, r12d
0x18001b06a  jge     loc_18001B15E
0x18001b070  xor     edx, edx; Val
0x18001b072  lea     rcx, [rsp+500h+lParam]; void *
0x18001b077  lea     r8d, [rdx+48h]; Size
0x18001b07b  call    memset_0
0x18001b080  lea     rax, [rbp+400h+var_440]
0x18001b084  movsxd  r8, esi; wParam
0x18001b087  lea     r9, [rsp+500h+lParam]; lParam
0x18001b08c  mov     [rsp+500h+lpchText], rax
0x18001b091  mov     edx, 120Bh; Msg
0x18001b096  mov     dword ptr [rsp+500h+lParam], 2
0x18001b09e  mov     rcx, r15; hWnd
0x18001b0a1  mov     [rbp+400h+var_440], bx
0x18001b0a5  mov     [rsp+500h+var_488], 200h
0x18001b0ad  call    cs:__imp_SendMessageW
0x18001b0b3  test    eax, eax
0x18001b0b5  jz      loc_18001B157
0x18001b0bb  mov     rax, [rsp+500h+lpchText]
0x18001b0c0  xor     ecx, ecx
0x18001b0c2  cmp     [rax], cx
0x18001b0c5  jz      short loc_18001B11B
0x18001b0c7  mov     rdx, [rsp+500h+h]; h
0x18001b0cc  mov     rcx, rdi; hdc
0x18001b0cf  call    cs:__imp_SelectObject
0x18001b0d5  mov     rdx, [rsp+500h+lpchText]; lpchText
0x18001b0da  lea     r9, [rbp+400h+rc]; lprc
0x18001b0de  xorps   xmm0, xmm0
0x18001b0e1  mov     [rsp+500h+var_4C8], rax
0x18001b0e6  or      r8d, 0FFFFFFFFh; cchText
0x18001b0ea  mov     [rsp+500h+format], 100520h; format
0x18001b0f2  mov     rcx, rdi; hdc
0x18001b0f5  movups  xmmword ptr [rbp+400h+rc.left], xmm0
0x18001b0f9  call    cs:__imp_DrawTextW
0x18001b0ff  test    eax, eax
0x18001b101  jz      short loc_18001B10D
0x18001b103  mov     ebx, [rbp+400h+rc.right]
0x18001b106  sub     ebx, [rbp+400h+rc.left]
0x18001b109  add     ebx, [rsp+500h+var_4D0]
0x18001b10d  mov     rdx, [rsp+500h+var_4C8]; h
0x18001b112  mov     rcx, rdi; hdc
0x18001b115  call    cs:__imp_SelectObject
0x18001b11b  test    esi, esi
0x18001b11d  jz      short loc_18001B155
0x18001b11f  mov     ecx, 5; this
0x18001b124  call    ?RelPixToPixel@DirectUI@@YAHH@Z; DirectUI::RelPixToPixel(int)
0x18001b129  mov     rcx, [r14+38h]; hWnd
0x18001b12d  add     ebx, eax
0x18001b12f  add     ebx, [rsp+500h+var_4CC]
0x18001b133  mov     edx, 101Eh; Msg
0x18001b138  cmp     ebx, [rbp+400h+arg_20]
0x18001b13e  movsxd  r8, esi; wParam
0x18001b141  cmovg   ebx, [rbp+400h+arg_20]
0x18001b148  movzx   r9d, bx; lParam
0x18001b14c  call    cs:__imp_SendMessageW
0x18001b152  add     r13d, ebx
0x18001b155  xor     ebx, ebx
0x18001b157  inc     esi
0x18001b159  jmp     loc_18001B067
0x18001b15e  mov     eax, [rbp+400h+arg_28]
0x18001b164  mov     edx, 101Eh; Msg
0x18001b169  mov     rcx, [r14+38h]; hWnd
0x18001b16d  sub     eax, r13d
0x18001b170  cmp     eax, [rsp+500h+var_4C0]
0x18001b174  cmovl   eax, [rsp+500h+var_4C0]
0x18001b179  xor     r8d, r8d; wParam
0x18001b17c  movzx   r9d, ax; lParam
0x18001b180  call    cs:__imp_SendMessageW
0x18001b186  mov     r13, [rsp+500h+var_4B0]
0x18001b18b  mov     rdx, r13; h
0x18001b18e  mov     rcx, rdi; hdc
0x18001b191  call    cs:__imp_SelectObject
0x18001b197  mov     rcx, rdi; hdc
0x18001b19a  call    cs:__imp_DeleteDC
0x18001b1a0  mov     rcx, [rbp+400h+var_40]
0x18001b1a7  xor     rcx, rsp; StackCookie
0x18001b1aa  call    __security_check_cookie
0x18001b1af  mov     rbx, [rsp+500h+arg_8]
0x18001b1b7  add     rsp, 4D0h
0x18001b1be  pop     r15
0x18001b1c0  pop     r14
0x18001b1c2  pop     r13
0x18001b1c4  pop     r12
0x18001b1c6  pop     rdi
0x18001b1c7  pop     rsi
0x18001b1c8  pop     rbp
0x18001b1c9  retn
```

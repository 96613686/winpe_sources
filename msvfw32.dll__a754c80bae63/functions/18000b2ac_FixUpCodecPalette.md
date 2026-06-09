# FixUpCodecPalette

- ea: `0x18000b2ac`
- end: `0x18000b3d2`
- name: `FixUpCodecPalette`
- size: `294`
- prototype: `__int64 __fastcall(HIC hic)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5b8`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180003a60`
- `0x18000b2ac`

## import_xrefs

- `GDI32!GetSystemPaletteEntries` at `0x18000b347`
- `GDI32!GetSystemPaletteEntries` at `0x18000b347`
- `USER32!GetDC` at `0x18000b32e`
- `USER32!GetDC` at `0x18000b32e`
- `USER32!ReleaseDC` at `0x18000b352`
- `USER32!ReleaseDC` at `0x18000b352`

## pseudocode

```c
_BOOL8 __fastcall FixUpCodecPalette(HIC hic, __int64 a2)
{
  HDC DC; // rbx
  __int64 v5; // rdx
  int v6; // ecx
  _DWORD dw1[3]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+2Ch] [rbp-D4h]
  __int64 v10; // [rsp+34h] [rbp-CCh]
  int v11; // [rsp+3Ch] [rbp-C4h]
  __int64 v12; // [rsp+40h] [rbp-C0h]
  struct tagPALETTEENTRY pPalEntries[258]; // [rsp+48h] [rbp-B8h] BYREF

  memset_0(pPalEntries, 0, 0x400u);
  dw1[1] = *(_DWORD *)(a2 + 4);
  dw1[2] = *(_DWORD *)(a2 + 8);
  dw1[0] = 40;
  v9 = 524289;
  v10 = 0;
  v11 = 0;
  v12 = 256;
  DC = GetDC(0);
  GetSystemPaletteEntries(DC, 0, 0x100u, pPalEntries);
  ReleaseDC(0, DC);
  v5 = 0;
  do
  {
    if ( (unsigned int)(v5 - 8) > 0xEF )
      v6 = 0;
    else
      v6 = pPalEntries[v5].peBlue | (pPalEntries[v5].peRed << 16) | (pPalEntries[v5].peGreen << 8);
    pPalEntries[v5] = (struct tagPALETTEENTRY)v6;
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (int)v5 < 256 );
  return ICSendMessage(hic, 0x401Du, (DWORD_PTR)dw1, 0) == 0;
}

```

## disassembly

```asm
0x18000b2ac  mov     [rsp-8+arg_10], rbx
0x18000b2b1  push    rbp
0x18000b2b2  push    rdi
0x18000b2b3  push    r15
0x18000b2b5  lea     rbp, [rsp-360h]
0x18000b2bd  sub     rsp, 460h
0x18000b2c4  mov     rax, cs:__security_cookie
0x18000b2cb  xor     rax, rsp
0x18000b2ce  mov     [rbp+370h+var_20], rax
0x18000b2d5  mov     rbx, rdx
0x18000b2d8  mov     rdi, rcx
0x18000b2db  xor     edx, edx; Val
0x18000b2dd  lea     rcx, [rsp+470h+pPalEntries]; void *
0x18000b2e2  mov     r8d, 400h; Size
0x18000b2e8  call    memset_0
0x18000b2ed  mov     eax, [rbx+4]
0x18000b2f0  xor     ecx, ecx; hWnd
0x18000b2f2  mov     dword ptr [rsp+470h+dw1+4], eax
0x18000b2f6  mov     r15d, 1
0x18000b2fc  mov     eax, [rbx+8]
0x18000b2ff  mov     [rsp+470h+var_448], eax
0x18000b303  mov     dword ptr [rsp+470h+dw1], 28h ; '('
0x18000b30b  mov     [rsp+470h+var_444], 80001h
0x18000b314  mov     [rsp+470h+var_43C], 0
0x18000b31d  mov     [rsp+470h+var_434], 0
0x18000b325  mov     [rsp+470h+var_430], 100h
0x18000b32e  call    cs:__imp_GetDC
0x18000b334  lea     r9, [rsp+470h+pPalEntries]; pPalEntries
0x18000b339  xor     edx, edx; iStart
0x18000b33b  mov     rcx, rax; hdc
0x18000b33e  mov     r8d, 100h; cEntries
0x18000b344  mov     rbx, rax
0x18000b347  call    cs:__imp_GetSystemPaletteEntries
0x18000b34d  mov     rdx, rbx; hDC
0x18000b350  xor     ecx, ecx; hWnd
0x18000b352  call    cs:__imp_ReleaseDC
0x18000b358  xor     edx, edx
0x18000b35a  lea     eax, [rdx-8]
0x18000b35d  cmp     eax, 0EFh
0x18000b362  ja      short loc_18000B37F
0x18000b364  movzx   ecx, [rsp+rdx*4+470h+pPalEntries.peGreen]
0x18000b369  movzx   eax, [rsp+rdx*4+470h+pPalEntries.peRed]
0x18000b36e  shl     eax, 10h
0x18000b371  shl     ecx, 8
0x18000b374  or      ecx, eax
0x18000b376  movzx   eax, [rsp+rdx*4+470h+pPalEntries.peBlue]
0x18000b37b  or      ecx, eax
0x18000b37d  jmp     short loc_18000B381
0x18000b37f  xor     ecx, ecx
0x18000b381  mov     dword ptr [rsp+rdx*4+470h+pPalEntries.peRed], ecx
0x18000b385  add     edx, r15d
0x18000b388  cmp     edx, 100h
0x18000b38e  jl      short loc_18000B35A
0x18000b390  xor     r9d, r9d; dw2
0x18000b393  lea     r8, [rsp+470h+dw1]; dw1
0x18000b398  mov     edx, 401Dh; msg
0x18000b39d  mov     rcx, rdi; hic
0x18000b3a0  call    ICSendMessage
0x18000b3a5  xor     ecx, ecx
0x18000b3a7  test    rax, rax
0x18000b3aa  setz    cl
0x18000b3ad  mov     eax, ecx
0x18000b3af  mov     rcx, [rbp+370h+var_20]
0x18000b3b6  xor     rcx, rsp; StackCookie
0x18000b3b9  call    __security_check_cookie
0x18000b3be  mov     rbx, [rsp+470h+arg_10]
0x18000b3c6  add     rsp, 460h
0x18000b3cd  pop     r15
0x18000b3cf  pop     rdi
0x18000b3d0  pop     rbp
0x18000b3d1  retn
```

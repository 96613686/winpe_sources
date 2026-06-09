# CImagePalette::MakeIdentityPalette(tagPALETTEENTRY *,int,char *)

- ea: `0x180142b38`
- end: `0x180142d07`
- name: `?MakeIdentityPalette@CImagePalette@@SAJPEAUtagPALETTEENTRY@@HPEAD@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct tagPALETTEENTRY *, int, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180142d10`

## callees

- `0x1800388a0`
- `0x180142b38`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x180142b95`
- `KERNEL32!CompareStringA` at `0x180142b95`
- `GDI32!GetSystemPaletteEntries` at `0x180142c32`
- `GDI32!GetSystemPaletteEntries` at `0x180142c88`
- `GDI32!GetSystemPaletteEntries` at `0x180142c32`
- `GDI32!GetSystemPaletteEntries` at `0x180142c88`
- `GDI32!DeleteDC` at `0x180142bef`
- `GDI32!DeleteDC` at `0x180142cd5`
- `GDI32!DeleteDC` at `0x180142bef`
- `GDI32!DeleteDC` at `0x180142cd5`
- `GDI32!CreateDCA` at `0x180142bb8`
- `GDI32!CreateDCA` at `0x180142bb8`
- `GDI32!GetDeviceCaps` at `0x180142bdb`
- `GDI32!GetDeviceCaps` at `0x180142bdb`

## pseudocode

```c
__int64 __fastcall CImagePalette::MakeIdentityPalette(struct tagPALETTEENTRY *a1, int a2, char *a3)
{
  int v3; // ebx
  const CHAR *v7; // rdx
  const CHAR *v8; // rcx
  HDC DCA; // rax
  HDC v10; // rdi
  int v12; // r15d
  UINT SystemPaletteEntries; // eax
  __int64 i; // r8
  int v15; // esi
  UINT v16; // eax
  __int64 j; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  struct tagPALETTEENTRY pPalEntries[10]; // [rsp+30h] [rbp-58h] BYREF

  v3 = 10;
  if ( a2 < 10 )
    return 1;
  if ( !a3 || CompareStringA(0x7Fu, 1u, a3, -1, "DISPLAY", -1) == 2 )
  {
    v7 = 0;
    v8 = "DISPLAY";
  }
  else
  {
    v7 = a3;
    v8 = 0;
  }
  DCA = CreateDCA(v8, v7, 0, 0);
  v10 = DCA;
  if ( !DCA )
    return 2147942414LL;
  if ( GetDeviceCaps(DCA, 106) != 20 )
  {
    DeleteDC(v10);
    return 1;
  }
  v12 = 1;
  SystemPaletteEntries = GetSystemPaletteEntries(v10, 0, 0xAu, pPalEntries);
  for ( i = 0; (unsigned int)i < SystemPaletteEntries; i = (unsigned int)(i + 1) )
  {
    if ( pPalEntries[i].peRed != a1[i].peRed
      || pPalEntries[i].peGreen != a1[i].peGreen
      || pPalEntries[i].peBlue != a1[i].peBlue )
    {
      v12 = 0;
    }
  }
  v15 = 246;
  v16 = GetSystemPaletteEntries(v10, 0xF6u, 0xAu, pPalEntries);
  for ( j = 0; (unsigned int)j < v16; j = (unsigned int)(j + 1) )
  {
    v18 = (unsigned int)(j + 246);
    if ( (int)v18 < a2
      && (pPalEntries[j].peRed != a1[v18].peRed
       || pPalEntries[j].peGreen != a1[v18].peGreen
       || pPalEntries[j].peBlue != a1[v18].peBlue) )
    {
      v12 = 0;
    }
  }
  DeleteDC(v10);
  if ( !v12 )
    return 1;
  if ( a2 <= 246 )
    v15 = a2;
  while ( v3 < v15 )
  {
    v19 = (unsigned int)v3++;
    a1[v19].peFlags = 4;
  }
  return 0;
}

```

## disassembly

```asm
0x180142b38  mov     r11, rsp
0x180142b3b  mov     [r11+10h], rbx
0x180142b3f  mov     [r11+20h], rbp
0x180142b43  push    rsi
0x180142b44  push    rdi
0x180142b45  push    r12
0x180142b47  push    r14
0x180142b49  push    r15
0x180142b4b  sub     rsp, 60h
0x180142b4f  mov     rax, cs:__security_cookie
0x180142b56  xor     rax, rsp
0x180142b59  mov     [rsp+88h+var_30], rax
0x180142b5e  mov     ebx, 0Ah
0x180142b63  mov     rdi, r8
0x180142b66  mov     ebp, edx
0x180142b68  mov     r14, rcx
0x180142b6b  lea     r12d, [rbx-9]
0x180142b6f  cmp     edx, ebx
0x180142b71  jl      loc_180142BFB
0x180142b77  lea     rsi, pwszDriver; "DISPLAY"
0x180142b7e  test    r8, r8
0x180142b81  jz      short loc_180142BAD
0x180142b83  or      r9d, 0FFFFFFFFh; cchCount1
0x180142b87  lea     ecx, [rbx+75h]; Locale
0x180142b8a  mov     [r11-60h], r9d
0x180142b8e  mov     edx, r12d; dwCmpFlags
0x180142b91  mov     [r11-68h], rsi
0x180142b95  call    cs:__imp_CompareStringA
0x180142b9c  nop     dword ptr [rax+rax+00h]
0x180142ba1  cmp     eax, 2
0x180142ba4  jz      short loc_180142BAD
0x180142ba6  mov     rdx, rdi
0x180142ba9  xor     ecx, ecx
0x180142bab  jmp     short loc_180142BB2
0x180142bad  xor     edx, edx; pwszDevice
0x180142baf  mov     rcx, rsi; pwszDriver
0x180142bb2  xor     r9d, r9d; pdm
0x180142bb5  xor     r8d, r8d; pszPort
0x180142bb8  call    cs:__imp_CreateDCA
0x180142bbf  nop     dword ptr [rax+rax+00h]
0x180142bc4  mov     rdi, rax
0x180142bc7  test    rax, rax
0x180142bca  jnz     short loc_180142BD3
0x180142bcc  mov     eax, 8007000Eh
0x180142bd1  jmp     short loc_180142BFE
0x180142bd3  mov     edx, 6Ah ; 'j'; index
0x180142bd8  mov     rcx, rdi; hdc
0x180142bdb  call    cs:__imp_GetDeviceCaps
0x180142be2  nop     dword ptr [rax+rax+00h]
0x180142be7  mov     rcx, rdi; hdc
0x180142bea  cmp     eax, 14h
0x180142bed  jz      short loc_180142C25
0x180142bef  call    cs:__imp_DeleteDC
0x180142bf6  nop     dword ptr [rax+rax+00h]
0x180142bfb  mov     eax, r12d
0x180142bfe  mov     rcx, [rsp+88h+var_30]
0x180142c03  xor     rcx, rsp; StackCookie
0x180142c06  call    __security_check_cookie
0x180142c0b  lea     r11, [rsp+88h+var_28]
0x180142c10  mov     rbx, [r11+38h]
0x180142c14  mov     rbp, [r11+48h]
0x180142c18  mov     rsp, r11
0x180142c1b  pop     r15
0x180142c1d  pop     r14
0x180142c1f  pop     r12
0x180142c21  pop     rdi
0x180142c22  pop     rsi
0x180142c23  retn
0x180142c25  lea     r9, [rsp+88h+pPalEntries]; pPalEntries
0x180142c2a  mov     r8d, ebx; cEntries
0x180142c2d  xor     edx, edx; iStart
0x180142c2f  mov     r15d, r12d
0x180142c32  call    cs:__imp_GetSystemPaletteEntries
0x180142c39  nop     dword ptr [rax+rax+00h]
0x180142c3e  xor     r8d, r8d
0x180142c41  mov     r9d, eax
0x180142c44  test    eax, eax
0x180142c46  jz      short loc_180142C76
0x180142c48  mov     cl, [r14+r8*4]
0x180142c4c  cmp     [rsp+r8*4+88h+pPalEntries.peRed], cl
0x180142c51  jnz     short loc_180142C6B
0x180142c53  mov     cl, [r14+r8*4+1]
0x180142c58  cmp     [rsp+r8*4+88h+pPalEntries.peGreen], cl
0x180142c5d  jnz     short loc_180142C6B
0x180142c5f  mov     al, [r14+r8*4+2]
0x180142c64  cmp     [rsp+r8*4+88h+pPalEntries.peBlue], al
0x180142c69  jz      short loc_180142C6E
0x180142c6b  xor     r15d, r15d
0x180142c6e  add     r8d, r12d
0x180142c71  cmp     r8d, r9d
0x180142c74  jb      short loc_180142C48
0x180142c76  mov     esi, 0F6h
0x180142c7b  lea     r9, [rsp+88h+pPalEntries]; pPalEntries
0x180142c80  mov     edx, esi; iStart
0x180142c82  mov     r8d, ebx; cEntries
0x180142c85  mov     rcx, rdi; hdc
0x180142c88  call    cs:__imp_GetSystemPaletteEntries
0x180142c8f  nop     dword ptr [rax+rax+00h]
0x180142c94  xor     ecx, ecx
0x180142c96  mov     r10d, eax
0x180142c99  test    eax, eax
0x180142c9b  jz      short loc_180142CD2
0x180142c9d  lea     edx, [rcx+0F6h]
0x180142ca3  cmp     edx, ebp
0x180142ca5  jge     short loc_180142CCA
0x180142ca7  mov     al, [r14+rdx*4]
0x180142cab  cmp     [rsp+rcx*4+88h+pPalEntries.peRed], al
0x180142caf  jnz     short loc_180142CC7
0x180142cb1  mov     al, [r14+rdx*4+1]
0x180142cb6  cmp     [rsp+rcx*4+88h+pPalEntries.peGreen], al
0x180142cba  jnz     short loc_180142CC7
0x180142cbc  mov     al, [r14+rdx*4+2]
0x180142cc1  cmp     [rsp+rcx*4+88h+pPalEntries.peBlue], al
0x180142cc5  jz      short loc_180142CCA
0x180142cc7  xor     r15d, r15d
0x180142cca  add     ecx, r12d
0x180142ccd  cmp     ecx, r10d
0x180142cd0  jb      short loc_180142C9D
0x180142cd2  mov     rcx, rdi; hdc
0x180142cd5  call    cs:__imp_DeleteDC
0x180142cdc  nop     dword ptr [rax+rax+00h]
0x180142ce1  test    r15d, r15d
0x180142ce4  jz      loc_180142BFB
0x180142cea  cmp     ebp, esi
0x180142cec  cmovle  esi, ebp
0x180142cef  cmp     ebx, esi
0x180142cf1  jge     short loc_180142D00
0x180142cf3  mov     eax, ebx
0x180142cf5  add     ebx, r12d
0x180142cf8  mov     byte ptr [r14+rax*4+3], 4
0x180142cfe  jmp     short loc_180142CEF
0x180142d00  xor     eax, eax
0x180142d02  jmp     loc_180142BFE
```

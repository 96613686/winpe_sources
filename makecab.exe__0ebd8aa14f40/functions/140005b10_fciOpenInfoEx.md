# fciOpenInfoEx

- ea: `0x140005b10`
- end: `0x140005c46`
- name: `fciOpenInfoEx`
- size: `310`
- prototype: `__int64 __usercall@<rax>(LPSTR pszFile@<rcx>, int *err, void *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140005ae0`
- `0x140005c50`

## callees

- `0x1400058e0`
- `0x140005b10`
- `0x140005c80`
- `0x140006528`
- `0x140008620`
- `0x14000895c`

## string_xrefs

- `0x140005c1a`: `Could not open file: %1`

## pseudocode

```c
__int64 __fastcall fciOpenInfoEx(
        const CHAR *pszFile,
        _WORD *a2,
        _WORD *a3,
        _WORD *a4,
        int *err,
        __int64 *a6,
        unsigned int a7)
{
  __int64 v10; // rbp
  __int64 v11; // rbx
  _BYTE *i; // rcx
  __int64 result; // rax
  int v14; // [rsp+30h] [rbp-38h] BYREF
  __int16 v15; // [rsp+34h] [rbp-34h]

  v14 = 0;
  v10 = a6[1];
  v11 = *a6;
  v15 = 0;
  *err = 0;
  if ( !(unsigned int)GetFileTimeAndAttr(&v14, pszFile, a7, v10) || !(unsigned int)fnofpDiamond(&v14, v11, v10) )
    return -1;
  if ( *(_DWORD *)(v11 + 3144) )
  {
    for ( i = (_BYTE *)(v11 + 228); *i; ++i )
    {
      if ( *i > 0x7Fu )
      {
        v15 |= 0x80u;
        break;
      }
    }
  }
  *a2 = v14;
  *a3 = HIWORD(v14);
  *a4 = v15;
  *err = 0;
  if ( a7 )
    result = fciOpenUNC(pszFile, 0x8000, 0, err);
  else
    result = fciOpen(pszFile, 0x8000, 0, err);
  if ( result == -1 )
  {
    ErrSet(v10, "Could not open file: %1", "%s", pszFile);
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x140005b10  mov     r11, rsp
0x140005b13  mov     [r11+8], rbx
0x140005b17  mov     [r11+18h], rbp
0x140005b1b  mov     [r11+10h], rdx
0x140005b1f  push    rsi
0x140005b20  push    rdi
0x140005b21  push    r12
0x140005b23  push    r13
0x140005b25  push    r14
0x140005b27  sub     rsp, 40h
0x140005b2b  mov     r14, [rsp+68h+arg_28]
0x140005b33  xor     eax, eax
0x140005b35  mov     rsi, [rsp+68h+err]
0x140005b3d  mov     r12, r9
0x140005b40  mov     r13, r8
0x140005b43  mov     [rsp+68h+var_38], eax
0x140005b47  mov     r8d, [rsp+68h+arg_30]
0x140005b4f  mov     rdi, rcx
0x140005b52  mov     rbp, [r14+8]
0x140005b56  mov     rdx, rcx
0x140005b59  mov     rbx, [r14]
0x140005b5c  lea     rcx, [r11-38h]
0x140005b60  mov     r9, rbp
0x140005b63  mov     [rsp+68h+var_34], ax
0x140005b68  mov     [rsi], eax
0x140005b6a  call    GetFileTimeAndAttr
0x140005b6f  test    eax, eax
0x140005b71  jz      loc_140005C29
0x140005b77  mov     r8, rbp
0x140005b7a  lea     rcx, [rsp+68h+var_38]
0x140005b7f  mov     rdx, rbx
0x140005b82  call    fnofpDiamond
0x140005b87  test    eax, eax
0x140005b89  jz      loc_140005C29
0x140005b8f  cmp     dword ptr [rbx+0C48h], 0
0x140005b96  jz      short loc_140005BBA
0x140005b98  lea     rcx, [rbx+0E4h]
0x140005b9f  jmp     short loc_140005BA8
0x140005ba1  cmp     al, 7Fh
0x140005ba3  ja      short loc_140005BB0
0x140005ba5  inc     rcx
0x140005ba8  mov     al, [rcx]
0x140005baa  test    al, al
0x140005bac  jnz     short loc_140005BA1
0x140005bae  jmp     short loc_140005BBA
0x140005bb0  mov     eax, 80h
0x140005bb5  or      [rsp+68h+var_34], ax
0x140005bba  mov     rcx, [rsp+68h+arg_8]
0x140005bbf  xor     r8d, r8d; pmode
0x140005bc2  mov     r9, rsi; err
0x140005bc5  movzx   eax, word ptr [rsp+68h+var_38]
0x140005bca  mov     edx, 8000h; oflag
0x140005bcf  mov     [rsp+68h+pv], r14; pv
0x140005bd4  mov     [rcx], ax
0x140005bd7  mov     rcx, rdi; pszFile
0x140005bda  movzx   eax, word ptr [rsp+68h+var_38+2]
0x140005bdf  mov     [r13+0], ax
0x140005be4  movzx   eax, [rsp+68h+var_34]
0x140005be9  mov     [r12], ax
0x140005bee  mov     dword ptr [rsi], 0
0x140005bf4  cmp     [rsp+68h+arg_30], r8d
0x140005bfc  jz      short loc_140005C05
0x140005bfe  call    fciOpenUNC
0x140005c03  jmp     short loc_140005C0A
0x140005c05  call    fciOpen
0x140005c0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005c0e  jnz     short loc_140005C2D
0x140005c10  mov     r9, rdi
0x140005c13  lea     r8, aS_4; "%s"
0x140005c1a  lea     rdx, aCouldNotOpenFi; "Could not open file: %1"
0x140005c21  mov     rcx, rbp
0x140005c24  call    ErrSet
0x140005c29  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005c2d  lea     r11, [rsp+68h+var_28]
0x140005c32  mov     rbx, [r11+30h]
0x140005c36  mov     rbp, [r11+40h]
0x140005c3a  mov     rsp, r11
0x140005c3d  pop     r14
0x140005c3f  pop     r13
0x140005c41  pop     r12
0x140005c43  pop     rdi
0x140005c44  pop     rsi
0x140005c45  retn
```

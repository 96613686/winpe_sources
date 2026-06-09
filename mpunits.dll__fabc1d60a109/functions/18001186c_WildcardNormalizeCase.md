# WildcardNormalizeCase

- ea: `0x18001186c`
- end: `0x180011abc`
- name: `WildcardNormalizeCase`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180011db4`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18001186c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800119bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800119bb`

## string_xrefs

- `0x1800119ad`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall WildcardNormalizeCase(unsigned __int64 *a1)
{
  unsigned __int64 i; // r11
  unsigned __int64 j; // r9
  __int16 v4; // cx
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // r8
  __int16 v8; // r8
  unsigned int v9; // edi
  HMODULE ModuleHandleA; // rax
  __int16 v12; // ax
  __int16 v13; // dx
  __int16 v14; // cx

  for ( i = 0; i < *a1; ++i )
  {
    if ( LODWORD(a1[2 * i + 2]) == 2 )
    {
      v13 = a1[2 * i + 3];
      v14 = v13 + 32;
      if ( (unsigned __int16)(v13 - 65) > 0x19u )
        v14 = a1[2 * i + 3];
      LOWORD(a1[2 * i + 3]) = v14;
    }
    else if ( LODWORD(a1[2 * i + 2]) == 3 )
    {
      for ( j = a1[2 * i + 3]; j; j = *(_QWORD *)(j + 8) )
      {
        if ( *(_DWORD *)j )
        {
          if ( *(_DWORD *)j == 1 )
          {
            v4 = *(_WORD *)(j + 4) + 32;
            if ( (unsigned __int16)(*(_WORD *)(j + 4) - 65) > 0x19u )
              v4 = *(_WORD *)(j + 4);
            *(_WORD *)(j + 4) = v4;
          }
          continue;
        }
        v5 = *(_WORD *)(j + 4);
        v6 = *(_WORD *)(j + 6);
        if ( v5 < 0x61u || v5 > 0x7Au )
        {
          v7 = v5 - 65;
          if ( (unsigned __int16)(v5 - 65) > 0x19u
            && (unsigned __int16)(v6 - 97) > 0x19u
            && (unsigned __int16)(v6 - 65) > 0x19u
            && (v5 > 0x61u || v6 < 0x61u)
            && (v5 > 0x7Au || v6 < 0x7Au) )
          {
            if ( v5 <= 0x41u && v6 >= 0x41u || v5 <= 0x5Au && v6 >= 0x5Au )
            {
LABEL_30:
              v9 = *(unsigned __int16 *)(j + 4);
              ModuleHandleA = GetModuleHandleA("mpunits.dll");
              Intlstr_FormatString_FormatMessage(ModuleHandleA, 2092, v9);
              MI_ReportErrorDetails_ForCustomError(1, (int)L"MI", 0, 0);
              return 0xFFFFFFFFLL;
            }
            goto LABEL_41;
          }
        }
        else
        {
          v7 = v5 - 65;
        }
        if ( (unsigned __int16)(v5 - 97) > 0x19u && v7 > 0x19u
          || (unsigned __int16)(v6 - 97) > 0x19u && (unsigned __int16)(v6 - 65) > 0x19u )
        {
          goto LABEL_30;
        }
        if ( v7 > 0x19u )
          v8 = *(_WORD *)(j + 4);
        else
          v8 = v5 + 32;
        if ( (unsigned __int16)(v6 - 65) > 0x19u )
          v12 = *(_WORD *)(j + 6);
        else
          v12 = v6 + 32;
        if ( v5 == v8 )
        {
          if ( v6 != v12 )
            goto LABEL_30;
        }
        else if ( v6 == v12 )
        {
          goto LABEL_30;
        }
        if ( (unsigned __int16)(v5 - 65) <= 0x19u )
          v5 += 32;
LABEL_41:
        *(_WORD *)(j + 4) = v5;
        if ( (unsigned __int16)(v6 - 65) <= 0x19u )
          v6 += 32;
        *(_WORD *)(j + 6) = v6;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001186c  push    rbx
0x18001186e  push    rbp
0x18001186f  push    rdi
0x180011870  push    r12
0x180011872  push    r15
0x180011874  sub     rsp, 40h
0x180011878  xor     r11d, r11d
0x18001187b  mov     r10, rcx
0x18001187e  cmp     [rcx], r11
0x180011881  jbe     loc_180011AAE
0x180011887  lea     edi, [r11+41h]
0x18001188b  mov     bx, 19h
0x18001188f  lea     ebp, [rdi+20h]
0x180011892  lea     r15d, [r11+7Ah]
0x180011896  lea     r12d, [r11+5Ah]
0x18001189a  mov     r8, r11
0x18001189d  add     r8, r8
0x1800118a0  mov     ecx, [r10+r8*8+10h]
0x1800118a5  sub     ecx, 2
0x1800118a8  jz      loc_180011A86
0x1800118ae  cmp     ecx, 1
0x1800118b1  jnz     loc_180011AA2
0x1800118b7  mov     r9, [r10+r8*8+18h]
0x1800118bc  jmp     loc_180011A7B
0x1800118c1  mov     ecx, [r9]
0x1800118c4  test    ecx, ecx
0x1800118c6  jz      short loc_1800118F5
0x1800118c8  cmp     ecx, 1
0x1800118cb  jnz     loc_180011A77
0x1800118d1  movzx   eax, word ptr [r9+4]
0x1800118d6  movzx   ecx, word ptr [r9+4]
0x1800118db  sub     ax, di
0x1800118de  add     cx, 20h ; ' '
0x1800118e2  cmp     ax, bx
0x1800118e5  cmova   cx, [r9+4]
0x1800118eb  mov     [r9+4], cx
0x1800118f0  jmp     loc_180011A77
0x1800118f5  movzx   ecx, word ptr [r9+4]
0x1800118fa  movzx   edx, word ptr [r9+6]
0x1800118ff  cmp     bp, cx
0x180011902  ja      short loc_180011950
0x180011904  cmp     cx, r15w
0x180011908  ja      short loc_180011950
0x18001190a  movzx   r8d, cx
0x18001190e  sub     r8w, di
0x180011912  movzx   eax, cx
0x180011915  sub     ax, bp
0x180011918  cmp     ax, bx
0x18001191b  jbe     short loc_180011927
0x18001191d  cmp     r8w, bx
0x180011921  ja      loc_1800119A8
0x180011927  movzx   eax, dx
0x18001192a  sub     ax, bp
0x18001192d  cmp     ax, bx
0x180011930  jbe     short loc_18001193D
0x180011932  movzx   eax, dx
0x180011935  sub     ax, di
0x180011938  cmp     ax, bx
0x18001193b  ja      short loc_1800119A8
0x18001193d  cmp     r8w, bx
0x180011941  ja      loc_180011A1E
0x180011947  lea     r8d, [rcx+20h]
0x18001194b  jmp     loc_180011A22
0x180011950  movzx   r8d, cx
0x180011954  sub     r8w, di
0x180011958  cmp     r8w, bx
0x18001195c  jbe     short loc_180011912
0x18001195e  movzx   eax, dx
0x180011961  sub     ax, bp
0x180011964  cmp     ax, bx
0x180011967  jbe     short loc_180011912
0x180011969  movzx   eax, dx
0x18001196c  sub     ax, di
0x18001196f  cmp     ax, bx
0x180011972  jbe     short loc_180011912
0x180011974  cmp     cx, bp
0x180011977  ja      short loc_18001197E
0x180011979  cmp     bp, dx
0x18001197c  jbe     short loc_180011912
0x18001197e  cmp     cx, r15w
0x180011982  ja      short loc_18001198A
0x180011984  cmp     r15w, dx
0x180011988  jbe     short loc_180011912
0x18001198a  cmp     cx, di
0x18001198d  ja      short loc_180011994
0x18001198f  cmp     di, dx
0x180011992  jbe     short loc_1800119A8
0x180011994  cmp     cx, r12w
0x180011998  ja      loc_180011A5E
0x18001199e  cmp     r12w, dx
0x1800119a2  ja      loc_180011A5E
0x1800119a8  xorps   xmm0, xmm0
0x1800119ab  mov     edi, ecx
0x1800119ad  lea     rcx, ModuleName; "mpunits.dll"
0x1800119b4  mov     ebx, edx
0x1800119b6  movups  [rsp+68h+var_38], xmm0
0x1800119bb  call    cs:__imp_GetModuleHandleA
0x1800119c1  mov     r9d, ebx
0x1800119c4  mov     r8d, edi
0x1800119c7  mov     rcx, rax
0x1800119ca  mov     edx, 82Ch
0x1800119cf  call    _Intlstr_FormatString_FormatMessage
0x1800119d4  mov     qword ptr [rsp+68h+var_38], rax
0x1800119d9  lea     r9, [rsp+68h+var_38]
0x1800119de  mov     byte ptr [rsp+68h+var_38+8], 1
0x1800119e3  lea     rdx, aMi; "MI"
0x1800119ea  movaps  xmm0, [rsp+68h+var_38]
0x1800119ef  mov     r8d, 5
0x1800119f5  mov     [rsp+68h+var_40], 0; __int64
0x1800119fe  movdqa  [rsp+68h+var_38], xmm0
0x180011a04  mov     [rsp+68h+var_48], 0; __int64
0x180011a0d  lea     ecx, [r8-4]; int
0x180011a11  call    MI_ReportErrorDetails_ForCustomError
0x180011a16  or      eax, 0FFFFFFFFh
0x180011a19  jmp     loc_180011AB0
0x180011a1e  movzx   r8d, cx
0x180011a22  movzx   eax, dx
0x180011a25  sub     ax, di
0x180011a28  cmp     ax, bx
0x180011a2b  ja      short loc_180011A32
0x180011a2d  lea     eax, [rdx+20h]
0x180011a30  jmp     short loc_180011A35
0x180011a32  movzx   eax, dx
0x180011a35  cmp     cx, r8w
0x180011a39  jnz     short loc_180011A46
0x180011a3b  cmp     dx, ax
0x180011a3e  jnz     loc_1800119A8
0x180011a44  jmp     short loc_180011A4F
0x180011a46  cmp     dx, ax
0x180011a49  jz      loc_1800119A8
0x180011a4f  movzx   eax, cx
0x180011a52  sub     ax, di
0x180011a55  cmp     ax, bx
0x180011a58  ja      short loc_180011A5E
0x180011a5a  add     cx, 20h ; ' '
0x180011a5e  movzx   eax, dx
0x180011a61  mov     [r9+4], cx
0x180011a66  sub     ax, di
0x180011a69  cmp     ax, bx
0x180011a6c  ja      short loc_180011A72
0x180011a6e  add     dx, 20h ; ' '
0x180011a72  mov     [r9+6], dx
0x180011a77  mov     r9, [r9+8]
0x180011a7b  test    r9, r9
0x180011a7e  jnz     loc_1800118C1
0x180011a84  jmp     short loc_180011AA2
0x180011a86  movzx   edx, word ptr [r10+r8*8+18h]
0x180011a8c  movzx   eax, dx
0x180011a8f  sub     ax, di
0x180011a92  cmp     ax, bx
0x180011a95  lea     ecx, [rdx+20h]
0x180011a98  cmova   cx, dx
0x180011a9c  mov     [r10+r8*8+18h], cx
0x180011aa2  inc     r11
0x180011aa5  cmp     r11, [r10]
0x180011aa8  jb      loc_18001189A
0x180011aae  xor     eax, eax
0x180011ab0  add     rsp, 40h
0x180011ab4  pop     r15
0x180011ab6  pop     r12
0x180011ab8  pop     rdi
0x180011ab9  pop     rbp
0x180011aba  pop     rbx
0x180011abb  retn
```

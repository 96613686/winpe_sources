# WildcardParseCore

- ea: `0x180011ac4`
- end: `0x180011d42`
- name: `WildcardParseCore`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011db4`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18001143c`
- `0x1800114fc`
- `0x180011ac4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011c49`

## string_xrefs

- `0x180011c3d`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall WildcardParseCore(_QWORD *a1, _WORD *a2)
{
  _WORD *v2; // r15
  unsigned __int16 v4; // di
  char v5; // dl
  _QWORD *v6; // rbx
  unsigned __int16 v7; // r14
  unsigned __int16 v8; // r13
  char v9; // bp
  char v10; // cl
  char v11; // r12
  HMODULE ModuleHandleA; // rax
  char v14; // [rsp+90h] [rbp+8h]

  v2 = a2;
  *a1 = 0;
  v4 = *a2;
  if ( *(_DWORD *)a2 == 96 || !v4 )
    return 0;
  v5 = 0;
  v6 = a1 + 2;
  v14 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  do
  {
    if ( !v5 )
    {
      switch ( v4 )
      {
        case '*':
          if ( !v9 )
          {
            *(_DWORD *)v6 = 0;
LABEL_28:
            v6 += 2;
            ++*a1;
LABEL_29:
            v9 = 0;
            goto LABEL_30;
          }
          break;
        case '?':
          if ( !v9 )
          {
            *(_DWORD *)v6 = 1;
            goto LABEL_28;
          }
          break;
        case '[':
          if ( !v9 )
          {
            v5 = 1;
            *(_DWORD *)v6 = 3;
            v6[1] = 0;
            v10 = 1;
            ++*a1;
            v8 = 0;
            v14 = 1;
            v7 = 0;
            v11 = 0;
            goto LABEL_29;
          }
          break;
        default:
          if ( v4 == 96 && !v9 )
            goto LABEL_45;
          break;
      }
      *(_DWORD *)v6 = 2;
      *((_WORD *)v6 + 4) = v4;
      v6 += 2;
      ++*a1;
      goto LABEL_43;
    }
    if ( v4 == 93 )
    {
      if ( !v10 && !v9 )
      {
        if ( v7 && !WildcardBracketExpr_AddSpecificCharacter(v7, v6)
          || v8 && !WildcardBracketExpr_AddSpecificCharacter(v8, v6) )
        {
          return 0xFFFFFFFFLL;
        }
        v5 = 0;
        v6 += 2;
        v14 = 0;
        goto LABEL_24;
      }
    }
    else if ( v4 == 96 && !v9 )
    {
      goto LABEL_24;
    }
    if ( !v7 )
      goto LABEL_21;
    if ( !v11 )
    {
      if ( !WildcardBracketExpr_AddSpecificCharacter(v7, v6) )
        return 0xFFFFFFFFLL;
      v5 = v14;
LABEL_21:
      v7 = v8;
      v8 = v4;
      if ( v4 == 45 )
      {
        v11 = 1;
        if ( !v9 )
          goto LABEL_24;
      }
      goto LABEL_23;
    }
    if ( !WildcardBracketExpr_AddRange(v7, v4, v6) )
      return 0xFFFFFFFFLL;
    v5 = v14;
    v8 = 0;
    v7 = 0;
LABEL_23:
    v11 = 0;
LABEL_24:
    v10 = 0;
LABEL_43:
    if ( v4 != 96 || v9 )
      goto LABEL_29;
LABEL_45:
    v9 = 1;
LABEL_30:
    v4 = *++v2;
  }
  while ( *v2 );
  if ( v5 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_GetString_LoadString(ModuleHandleA, 2091);
    MI_ReportErrorDetails_ForCustomError(1, (int)L"MI", 0, 0);
    return 0xFFFFFFFFLL;
  }
  if ( v9 )
  {
    *(_DWORD *)v6 = 2;
    *((_WORD *)v6 + 4) = 96;
    ++*a1;
  }
  return 0;
}

```

## disassembly

```asm
0x180011ac4  push    rbx
0x180011ac6  push    rbp
0x180011ac7  push    rsi
0x180011ac8  push    rdi
0x180011ac9  push    r12
0x180011acb  push    r13
0x180011acd  push    r14
0x180011acf  push    r15
0x180011ad1  sub     rsp, 48h
0x180011ad5  xor     r8d, r8d
0x180011ad8  mov     r15, rdx
0x180011adb  mov     [rcx], r8
0x180011ade  mov     rsi, rcx
0x180011ae1  movzx   edi, word ptr [rdx]
0x180011ae4  lea     eax, [r8+60h]
0x180011ae8  cmp     di, ax
0x180011aeb  jnz     short loc_180011AF8
0x180011aed  cmp     [rdx+2], r8w
0x180011af2  jz      loc_180011D2F
0x180011af8  test    di, di
0x180011afb  jz      loc_180011D2F
0x180011b01  mov     dl, r8b
0x180011b04  lea     rbx, [rsi+10h]
0x180011b08  mov     [rsp+88h+arg_0], dl
0x180011b0f  mov     r14d, r8d
0x180011b12  mov     r13d, r8d
0x180011b15  mov     bpl, r8b
0x180011b18  mov     cl, r8b
0x180011b1b  mov     r12b, r8b
0x180011b1e  test    dl, dl
0x180011b20  jz      loc_180011C01
0x180011b26  cmp     di, 5Dh ; ']'
0x180011b2a  jnz     short loc_180011B81
0x180011b2c  test    cl, cl
0x180011b2e  jnz     short loc_180011B8B
0x180011b30  test    bpl, bpl
0x180011b33  jnz     short loc_180011B8B
0x180011b35  test    r14w, r14w
0x180011b39  jz      short loc_180011B53
0x180011b3b  mov     rdx, rbx
0x180011b3e  movzx   ecx, r14w
0x180011b42  call    WildcardBracketExpr_AddSpecificCharacter
0x180011b47  xor     r8d, r8d
0x180011b4a  test    rax, rax
0x180011b4d  jz      loc_180011C94
0x180011b53  test    r13w, r13w
0x180011b57  jz      short loc_180011B71
0x180011b59  mov     rdx, rbx
0x180011b5c  movzx   ecx, r13w
0x180011b60  call    WildcardBracketExpr_AddSpecificCharacter
0x180011b65  xor     r8d, r8d
0x180011b68  test    rax, rax
0x180011b6b  jz      loc_180011C94
0x180011b71  mov     dl, r8b
0x180011b74  add     rbx, 10h
0x180011b78  mov     [rsp+88h+arg_0], dl
0x180011b7f  jmp     short loc_180011BF4
0x180011b81  cmp     di, ax
0x180011b84  jnz     short loc_180011B8B
0x180011b86  test    bpl, bpl
0x180011b89  jz      short loc_180011BF4
0x180011b8b  test    r14w, r14w
0x180011b8f  jz      short loc_180011BDB
0x180011b91  movzx   ecx, r14w
0x180011b95  test    r12b, r12b
0x180011b98  jz      short loc_180011BC0
0x180011b9a  mov     r8, rbx
0x180011b9d  movzx   edx, di
0x180011ba0  call    WildcardBracketExpr_AddRange
0x180011ba5  xor     r8d, r8d
0x180011ba8  test    rax, rax
0x180011bab  jz      loc_180011C94
0x180011bb1  mov     dl, [rsp+88h+arg_0]
0x180011bb8  mov     r13d, r8d
0x180011bbb  mov     r14d, r8d
0x180011bbe  jmp     short loc_180011BF1
0x180011bc0  mov     rdx, rbx
0x180011bc3  call    WildcardBracketExpr_AddSpecificCharacter
0x180011bc8  xor     r8d, r8d
0x180011bcb  test    rax, rax
0x180011bce  jz      loc_180011C94
0x180011bd4  mov     dl, [rsp+88h+arg_0]
0x180011bdb  movzx   r14d, r13w
0x180011bdf  movzx   r13d, di
0x180011be3  cmp     di, 2Dh ; '-'
0x180011be7  jnz     short loc_180011BF1
0x180011be9  mov     r12b, 1
0x180011bec  test    bpl, bpl
0x180011bef  jz      short loc_180011BF4
0x180011bf1  mov     r12b, r8b
0x180011bf4  mov     cl, r8b
0x180011bf7  mov     eax, 60h ; '`'
0x180011bfc  jmp     loc_180011D03
0x180011c01  cmp     di, 2Ah ; '*'
0x180011c05  jnz     loc_180011C9C
0x180011c0b  test    bpl, bpl
0x180011c0e  jnz     loc_180011CF2
0x180011c14  mov     [rbx], r8d
0x180011c17  add     rbx, 10h
0x180011c1b  inc     qword ptr [rsi]
0x180011c1e  mov     bpl, r8b
0x180011c21  add     r15, 2
0x180011c25  movzx   edi, word ptr [r15]
0x180011c29  test    di, di
0x180011c2c  jnz     loc_180011B1E
0x180011c32  test    dl, dl
0x180011c34  jz      loc_180011D1D
0x180011c3a  xorps   xmm0, xmm0
0x180011c3d  lea     rcx, ModuleName; "mpunits.dll"
0x180011c44  movups  [rsp+88h+var_58], xmm0
0x180011c49  call    cs:__imp_GetModuleHandleA
0x180011c4f  mov     rcx, rax
0x180011c52  mov     edx, 82Bh
0x180011c57  call    _Intlstr_GetString_LoadString
0x180011c5c  mov     qword ptr [rsp+88h+var_58], rax
0x180011c61  lea     r9, [rsp+88h+var_58]
0x180011c66  xor     eax, eax
0x180011c68  lea     rdx, aMi; "MI"
0x180011c6f  mov     byte ptr [rsp+88h+var_58+8], al
0x180011c73  movaps  xmm0, [rsp+88h+var_58]
0x180011c78  mov     [rsp+88h+var_60], rax; __int64
0x180011c7d  lea     r8d, [rax+5]
0x180011c81  movdqa  [rsp+88h+var_58], xmm0
0x180011c87  lea     ecx, [rax+1]; int
0x180011c8a  mov     [rsp+88h+var_68], rax; __int64
0x180011c8f  call    MI_ReportErrorDetails_ForCustomError
0x180011c94  or      eax, 0FFFFFFFFh
0x180011c97  jmp     loc_180011D31
0x180011c9c  cmp     di, 3Fh ; '?'
0x180011ca0  jnz     short loc_180011CB2
0x180011ca2  test    bpl, bpl
0x180011ca5  jnz     short loc_180011CF2
0x180011ca7  mov     dword ptr [rbx], 1
0x180011cad  jmp     loc_180011C17
0x180011cb2  cmp     di, 5Bh ; '['
0x180011cb6  jnz     short loc_180011CE8
0x180011cb8  test    bpl, bpl
0x180011cbb  jnz     short loc_180011CF2
0x180011cbd  mov     dl, 1
0x180011cbf  mov     dword ptr [rbx], 3
0x180011cc5  mov     [rbx+8], r8
0x180011cc9  mov     cl, dl
0x180011ccb  inc     qword ptr [rsi]
0x180011cce  mov     r13d, r8d
0x180011cd1  mov     [rsp+88h+arg_0], dl
0x180011cd8  mov     r14d, r8d
0x180011cdb  mov     r12b, r8b
0x180011cde  mov     eax, 60h ; '`'
0x180011ce3  jmp     loc_180011C1E
0x180011ce8  cmp     di, ax
0x180011ceb  jnz     short loc_180011CF2
0x180011ced  test    bpl, bpl
0x180011cf0  jz      short loc_180011D15
0x180011cf2  mov     dword ptr [rbx], 2
0x180011cf8  mov     [rbx+8], di
0x180011cfc  add     rbx, 10h
0x180011d00  inc     qword ptr [rsi]
0x180011d03  cmp     di, ax
0x180011d06  jnz     loc_180011C1E
0x180011d0c  test    bpl, bpl
0x180011d0f  jnz     loc_180011C1E
0x180011d15  mov     bpl, 1
0x180011d18  jmp     loc_180011C21
0x180011d1d  test    bpl, bpl
0x180011d20  jz      short loc_180011D2F
0x180011d22  mov     dword ptr [rbx], 2
0x180011d28  mov     [rbx+8], ax
0x180011d2c  inc     qword ptr [rsi]
0x180011d2f  xor     eax, eax
0x180011d31  add     rsp, 48h
0x180011d35  pop     r15
0x180011d37  pop     r14
0x180011d39  pop     r13
0x180011d3b  pop     r12
0x180011d3d  pop     rdi
0x180011d3e  pop     rsi
0x180011d3f  pop     rbp
0x180011d40  pop     rbx
0x180011d41  retn
```

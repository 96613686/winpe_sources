# FindCmapSubtable

- ea: `0x18000db8c`
- end: `0x18000dd97`
- name: `FindCmapSubtable`
- size: `523`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e4c8`
- `0x18000e8f4`
- `0x18000f0f4`
- `0x1800143f0`

## callees

- `0x18000db8c`
- `0x180019e64`
- `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall FindCmapSubtable(__int64 a1, __int16 a2, __int16 a3, _WORD *a4)
{
  unsigned int v7; // r13d
  unsigned int v8; // ebx
  int v9; // edi
  int v10; // r15d
  __int16 i; // r12
  __int16 j; // r12
  _WORD v14[2]; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+34h] [rbp-Ch] BYREF
  __int64 v16; // [rsp+38h] [rbp-8h] BYREF

  v15 = 0;
  v16 = 0;
  v14[0] = 0;
  v7 = TTTableOffset(a1, (__int64)"cmap");
  if ( !v7 )
    return 0;
  if ( (unsigned __int16)ReadGeneric(a1, (__int64)&v15, 4u, (unsigned __int8 *)CMAP_HEADER_CONTROL, v7, v14) )
    return 0;
  v8 = v7 + v14[0];
  if ( v8 > *(_DWORD *)(a1 + 8) || SHIWORD(v15) > 1000 )
    return 0;
  v9 = 0;
  v10 = 0;
  if ( a2 == 3 && a3 == -1 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= SHIWORD(v15) )
        goto LABEL_31;
      if ( (unsigned __int16)ReadGeneric(a1, (__int64)&v16, 8u, (unsigned __int8 *)CMAP_TABLELOC_CONTROL, v8, v14) )
        return 0;
      if ( (_WORD)v16 == 3 )
      {
        if ( WORD1(v16) == 10 )
        {
          *a4 = 10;
LABEL_20:
          v10 = HIDWORD(v16);
          v9 = 1;
          goto LABEL_21;
        }
        if ( WORD1(v16) == 1 )
        {
          if ( !v9 || *a4 != 10 )
          {
            *a4 = 1;
            goto LABEL_20;
          }
        }
        else if ( !WORD1(v16) && !v9 )
        {
          *a4 = 0;
          goto LABEL_20;
        }
      }
LABEL_21:
      v8 += v14[0];
    }
  }
  for ( j = 0; j < SHIWORD(v15); ++j )
  {
    if ( v9 )
      return v10 + v7 < *(_DWORD *)(a1 + 8) ? v10 + v7 : 0;
    if ( (unsigned __int16)ReadGeneric(a1, (__int64)&v16, 8u, (unsigned __int8 *)CMAP_TABLELOC_CONTROL, v8, v14) )
      return 0;
    if ( (_WORD)v16 == a2 && (WORD1(v16) == a3 || a3 == -1) )
    {
      v9 = 1;
      v10 = HIDWORD(v16);
      *a4 = WORD1(v16);
    }
    v8 += v14[0];
  }
LABEL_31:
  if ( !v9 )
    return 0;
  return v10 + v7 < *(_DWORD *)(a1 + 8) ? v10 + v7 : 0;
}

```

## disassembly

```asm
0x18000db8c  mov     rax, rsp
0x18000db8f  mov     [rax+8], rbx
0x18000db93  mov     [rax+20h], r9
0x18000db97  mov     [rax+18h], r8w
0x18000db9c  mov     [rax+10h], dx
0x18000dba0  push    rbp
0x18000dba1  push    rsi
0x18000dba2  push    rdi
0x18000dba3  push    r12
0x18000dba5  push    r13
0x18000dba7  push    r14
0x18000dba9  push    r15
0x18000dbab  mov     rbp, rsp
0x18000dbae  sub     rsp, 40h
0x18000dbb2  movzx   r12d, dx
0x18000dbb6  mov     [rbp+var_C], 0
0x18000dbbd  xor     eax, eax
0x18000dbbf  mov     [rbp+var_8], 0
0x18000dbc7  lea     rdx, aCmap; "cmap"
0x18000dbce  mov     [rbp+var_10], ax
0x18000dbd2  movzx   esi, r8w
0x18000dbd6  mov     r14, rcx
0x18000dbd9  call    TTTableOffset
0x18000dbde  mov     r13d, eax
0x18000dbe1  test    eax, eax
0x18000dbe3  jz      loc_18000DD7D
0x18000dbe9  lea     rax, [rbp+var_10]
0x18000dbed  mov     r8d, 4
0x18000dbf3  mov     [rsp+40h+var_18], rax
0x18000dbf8  lea     r9, CMAP_HEADER_CONTROL
0x18000dbff  lea     rdx, [rbp+var_C]
0x18000dc03  mov     [rsp+40h+var_20], r13d
0x18000dc08  mov     rcx, r14
0x18000dc0b  call    ReadGeneric
0x18000dc10  xor     ecx, ecx
0x18000dc12  test    ax, ax
0x18000dc15  jnz     loc_18000DD7D
0x18000dc1b  movzx   ebx, [rbp+var_10]
0x18000dc1f  add     ebx, r13d
0x18000dc22  cmp     ebx, [r14+8]
0x18000dc26  ja      loc_18000DD7D
0x18000dc2c  mov     eax, 3E8h
0x18000dc31  cmp     word ptr [rbp+var_C+2], ax
0x18000dc35  jg      loc_18000DD7D
0x18000dc3b  mov     edi, ecx
0x18000dc3d  mov     r15d, ecx
0x18000dc40  mov     eax, 0FFFFh
0x18000dc45  cmp     r12w, 3
0x18000dc4a  jnz     loc_18000DCF5
0x18000dc50  cmp     si, ax
0x18000dc53  jnz     loc_18000DCF5
0x18000dc59  mov     r12d, ecx
0x18000dc5c  lea     esi, [rcx+1]
0x18000dc5f  cmp     r12w, word ptr [rbp+var_C+2]
0x18000dc64  jge     loc_18000DD6B
0x18000dc6a  lea     rax, [rbp+var_10]
0x18000dc6e  mov     r8d, 8
0x18000dc74  mov     [rsp+40h+var_18], rax
0x18000dc79  lea     r9, CMAP_TABLELOC_CONTROL
0x18000dc80  lea     rdx, [rbp+var_8]
0x18000dc84  mov     [rsp+40h+var_20], ebx
0x18000dc88  mov     rcx, r14
0x18000dc8b  call    ReadGeneric
0x18000dc90  xor     ecx, ecx
0x18000dc92  test    ax, ax
0x18000dc95  jnz     loc_18000DD7D
0x18000dc9b  cmp     word ptr [rbp+var_8], 3
0x18000dca0  jnz     short loc_18000DCE6
0x18000dca2  movzx   eax, word ptr [rbp+var_8+2]
0x18000dca6  lea     edx, [rcx+0Ah]
0x18000dca9  cmp     ax, dx
0x18000dcac  jnz     short loc_18000DCB7
0x18000dcae  mov     rax, [rbp+arg_18]
0x18000dcb2  mov     [rax], dx
0x18000dcb5  jmp     short loc_18000DCE0
0x18000dcb7  cmp     ax, si
0x18000dcba  jnz     short loc_18000DCCE
0x18000dcbc  mov     rax, [rbp+arg_18]
0x18000dcc0  test    edi, edi
0x18000dcc2  jz      short loc_18000DCC9
0x18000dcc4  cmp     [rax], dx
0x18000dcc7  jz      short loc_18000DCE6
0x18000dcc9  mov     [rax], si
0x18000dccc  jmp     short loc_18000DCE0
0x18000dcce  test    ax, ax
0x18000dcd1  jnz     short loc_18000DCE6
0x18000dcd3  test    edi, edi
0x18000dcd5  jnz     short loc_18000DCE6
0x18000dcd7  mov     eax, ecx
0x18000dcd9  mov     rcx, [rbp+arg_18]
0x18000dcdd  mov     [rcx], ax
0x18000dce0  mov     r15d, dword ptr [rbp+var_8+4]
0x18000dce4  mov     edi, esi
0x18000dce6  movzx   eax, [rbp+var_10]
0x18000dcea  add     r12w, si
0x18000dcee  add     ebx, eax
0x18000dcf0  jmp     loc_18000DC5F
0x18000dcf5  mov     r12d, ecx
0x18000dcf8  mov     esi, 1
0x18000dcfd  cmp     r12w, word ptr [rbp+var_C+2]
0x18000dd02  jge     short loc_18000DD6B
0x18000dd04  test    edi, edi
0x18000dd06  jnz     short loc_18000DD6F
0x18000dd08  lea     rax, [rbp+var_10]
0x18000dd0c  mov     rcx, r14
0x18000dd0f  mov     [rsp+40h+var_18], rax
0x18000dd14  lea     r8d, [rdi+8]
0x18000dd18  lea     r9, CMAP_TABLELOC_CONTROL
0x18000dd1f  mov     [rsp+40h+var_20], ebx
0x18000dd23  lea     rdx, [rbp+var_8]
0x18000dd27  call    ReadGeneric
0x18000dd2c  test    ax, ax
0x18000dd2f  jnz     short loc_18000DD7D
0x18000dd31  movzx   eax, [rbp+arg_8]
0x18000dd35  cmp     word ptr [rbp+var_8], ax
0x18000dd39  jnz     short loc_18000DD5F
0x18000dd3b  movzx   eax, word ptr [rbp+var_8+2]
0x18000dd3f  movzx   ecx, [rbp+arg_10]
0x18000dd43  cmp     ax, cx
0x18000dd46  jz      short loc_18000DD52
0x18000dd48  mov     edx, 0FFFFh
0x18000dd4d  cmp     cx, dx
0x18000dd50  jnz     short loc_18000DD5F
0x18000dd52  mov     rcx, [rbp+arg_18]
0x18000dd56  mov     edi, esi
0x18000dd58  mov     r15d, dword ptr [rbp+var_8+4]
0x18000dd5c  mov     [rcx], ax
0x18000dd5f  movzx   eax, [rbp+var_10]
0x18000dd63  add     r12w, si
0x18000dd67  add     ebx, eax
0x18000dd69  jmp     short loc_18000DCFD
0x18000dd6b  test    edi, edi
0x18000dd6d  jz      short loc_18000DD7D
0x18000dd6f  lea     ecx, [r15+r13]
0x18000dd73  cmp     ecx, [r14+8]
0x18000dd77  sbb     eax, eax
0x18000dd79  and     eax, ecx
0x18000dd7b  jmp     short loc_18000DD7F
0x18000dd7d  xor     eax, eax
0x18000dd7f  mov     rbx, [rsp+40h+arg_0]
0x18000dd87  add     rsp, 40h
0x18000dd8b  pop     r15
0x18000dd8d  pop     r14
0x18000dd8f  pop     r13
0x18000dd91  pop     r12
0x18000dd93  pop     rdi
0x18000dd94  pop     rsi
0x18000dd95  pop     rbp
0x18000dd96  retn
```

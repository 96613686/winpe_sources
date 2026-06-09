# TraceFilterEnginepEvaluateBinaryRuleEx

- ea: `0x14000dfb0`
- end: `0x14000e202`
- name: `TraceFilterEnginepEvaluateBinaryRuleEx`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000db60`

## callees

- `0x14000dfb0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000dfff`
- `ntoskrnl!RtlCompareMemory` at `0x14000e0ac`
- `ntoskrnl!RtlCompareMemory` at `0x14000e167`
- `ntoskrnl!RtlCompareMemory` at `0x14000dfff`
- `ntoskrnl!RtlCompareMemory` at `0x14000e0ac`
- `ntoskrnl!RtlCompareMemory` at `0x14000e167`

## pseudocode

```c
char __fastcall TraceFilterEnginepEvaluateBinaryRuleEx(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  SIZE_T v3; // rsi
  bool v4; // bl
  unsigned int v5; // r8d
  bool v8; // zf
  unsigned int v9; // ecx
  SIZE_T v10; // rsi
  SIZE_T v11; // rax
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned __int64 v14; // r12
  __int64 v15; // r13
  bool v16; // dl
  __int64 v17; // rbp
  unsigned __int16 v18; // r8
  int v19; // r15d
  bool v21; // al
  unsigned int v22; // ecx
  bool v23; // zf
  unsigned __int64 v24; // rcx
  SIZE_T v25; // rbp
  unsigned __int16 v26; // r15
  unsigned int v27; // eax
  bool v28; // cl
  unsigned __int16 v29; // r12
  char *i; // rsi
  unsigned int v31; // ecx
  int v32; // edx
  int v33; // ecx

  v3 = a3;
  v4 = 0;
  v5 = *(unsigned __int8 *)(a1 + 1);
  if ( v5 > 0x83 )
  {
    v8 = v5 == 132;
    v9 = v5 - 132;
LABEL_9:
    if ( !v8 )
    {
      v12 = v9 - 1;
      if ( !v12 )
      {
        v24 = *(unsigned __int16 *)(a1 + 2);
        v25 = v3;
        if ( v24 < v3 + 2 )
          return v4;
        v26 = *(_WORD *)(a1 + 4);
        v27 = v24 - 2;
        v28 = 0;
        if ( v27 / v26 == (_DWORD)v3 )
        {
          v29 = 0;
          for ( i = (char *)(a1 + 6); v29 < v26; ++v29 )
          {
            if ( v28 )
              break;
            v28 = RtlCompareMemory(i, a2, v25) == v25;
            i += v25;
          }
        }
        if ( *(_BYTE *)(a1 + 1) == 5 )
          return v28;
        return !v28;
      }
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          return 1;
        v14 = *(unsigned __int16 *)(a1 + 2);
        v15 = a1 + 4;
        v16 = 0;
        v17 = 0;
        do
        {
          if ( v17 + 2 >= v14 )
            break;
          v18 = (*(unsigned __int8 *)(v17 + v15) << 8) | *(unsigned __int8 *)((unsigned int)(v17 + 1) + v15);
          if ( !v18 || (unsigned int)v17 + (unsigned __int64)v18 + 2 > v14 )
            break;
          v19 = v18;
          if ( v18 == (_DWORD)v3 )
            v16 = RtlCompareMemory((const void *)(v15 + (unsigned int)(v17 + 2)), a2, v3) == v3;
          v17 = (unsigned int)(v19 + v17 + 2);
        }
        while ( !v16 );
        if ( *(_BYTE *)(a1 + 1) == 7 )
          return v16;
        return !v16;
      }
      if ( *(_WORD *)(a1 + 2) != 8 )
        return v4;
      v21 = 0;
      if ( (unsigned int)v3 > 4 )
        goto LABEL_34;
      switch ( (_DWORD)v3 )
      {
        case 4:
          v22 = *(_DWORD *)a2;
          break;
        case 2:
          v22 = *a2;
          break;
        case 1:
          v22 = *(unsigned __int8 *)a2;
          break;
        default:
LABEL_34:
          v23 = (_BYTE)v5 == 6;
LABEL_54:
          if ( v23 )
            return v21;
          return !v21;
      }
      if ( *(_DWORD *)(a1 + 4) <= v22 )
        v21 = v22 <= *(_DWORD *)(a1 + 8);
      goto LABEL_34;
    }
    v31 = *(unsigned __int16 *)(a1 + 2);
    if ( v31 != (_DWORD)v3 )
      return v4;
    v21 = 0;
    if ( (unsigned int)v3 <= 4 && v31 <= 4 )
    {
      switch ( (_DWORD)v3 )
      {
        case 4:
          v32 = *(_DWORD *)(a1 + 4);
          v33 = *(_DWORD *)a2;
LABEL_52:
          v21 = (v32 & v33) == v32;
          break;
        case 2:
          v32 = *(unsigned __int16 *)(a1 + 4);
          v33 = *a2;
          goto LABEL_52;
        case 1:
          v32 = *(unsigned __int8 *)(a1 + 4);
          v33 = *(unsigned __int8 *)a2;
          goto LABEL_52;
      }
    }
    v23 = (_BYTE)v5 == 4;
    goto LABEL_54;
  }
  if ( v5 != 131 && v5 != 3 )
  {
    v9 = v5 - 4;
    v8 = v5 == 4;
    goto LABEL_9;
  }
  if ( *(unsigned __int16 *)(a1 + 2) == (_DWORD)v3 )
  {
    v10 = *(unsigned __int16 *)(a1 + 2);
    v11 = RtlCompareMemory((const void *)(a1 + 4), a2, v10);
    v4 = v11 == v10;
    if ( *(_BYTE *)(a1 + 1) != 3 )
      return v11 != v10;
  }
  return v4;
}

```

## disassembly

```asm
0x14000dfb0  push    rbx
0x14000dfb2  push    rbp
0x14000dfb3  push    rsi
0x14000dfb4  push    rdi
0x14000dfb5  push    r12
0x14000dfb7  push    r13
0x14000dfb9  push    r14
0x14000dfbb  push    r15
0x14000dfbd  sub     rsp, 28h
0x14000dfc1  mov     esi, r8d
0x14000dfc4  xor     bl, bl
0x14000dfc6  movzx   r8d, byte ptr [rcx+1]
0x14000dfcb  mov     eax, 83h
0x14000dfd0  mov     r14, rdx
0x14000dfd3  mov     rdi, rcx
0x14000dfd6  cmp     r8d, eax
0x14000dfd9  ja      short loc_14000E026
0x14000dfdb  jz      short loc_14000DFEA
0x14000dfdd  mov     ecx, r8d
0x14000dfe0  sub     ecx, 3
0x14000dfe3  jz      short loc_14000DFEA
0x14000dfe5  sub     ecx, 1
0x14000dfe8  jmp     short loc_14000E02F
0x14000dfea  movzx   eax, word ptr [rdi+2]
0x14000dfee  cmp     eax, esi
0x14000dff0  jnz     loc_14000E1EE
0x14000dff6  lea     rcx, [rdi+4]; Source1
0x14000dffa  mov     r8d, eax; Length
0x14000dffd  mov     esi, eax
0x14000dfff  call    cs:__imp_RtlCompareMemory
0x14000e006  nop     dword ptr [rax+rax+00h]
0x14000e00b  cmp     rax, rsi
0x14000e00e  setz    bl
0x14000e011  cmp     byte ptr [rdi+1], 3
0x14000e015  jz      loc_14000E1EE
0x14000e01b  cmp     rax, rsi
0x14000e01e  setnz   bl
0x14000e021  jmp     loc_14000E1EE
0x14000e026  mov     ecx, r8d
0x14000e029  sub     ecx, 84h
0x14000e02f  jz      loc_14000E194
0x14000e035  sub     ecx, 1
0x14000e038  jz      loc_14000E121
0x14000e03e  sub     ecx, 1
0x14000e041  jz      loc_14000E0DC
0x14000e047  cmp     ecx, 1
0x14000e04a  jz      short loc_14000E056
0x14000e04c  mov     ebx, 1
0x14000e051  jmp     loc_14000E1EE
0x14000e056  movzx   r12d, word ptr [rdi+2]
0x14000e05b  lea     r13, [rdi+4]
0x14000e05f  xor     dl, dl
0x14000e061  xor     ebp, ebp
0x14000e063  lea     rax, [rbp+2]
0x14000e067  mov     r9d, ebp
0x14000e06a  cmp     rax, r12
0x14000e06d  jnb     short loc_14000E0C8
0x14000e06f  lea     eax, [rbp+1]
0x14000e072  movzx   r8d, byte ptr [rax+r13]
0x14000e077  movzx   eax, byte ptr [rbp+r13+0]
0x14000e07d  shl     ax, 8
0x14000e081  or      r8w, ax
0x14000e085  jz      short loc_14000E0C8
0x14000e087  movzx   ecx, r8w
0x14000e08b  add     rcx, 2
0x14000e08f  add     rcx, r9
0x14000e092  cmp     rcx, r12
0x14000e095  ja      short loc_14000E0C8
0x14000e097  movzx   r15d, r8w
0x14000e09b  cmp     r15d, esi
0x14000e09e  jnz     short loc_14000E0BE
0x14000e0a0  lea     ecx, [rbp+2]
0x14000e0a3  mov     r8, rsi; Length
0x14000e0a6  add     rcx, r13; Source1
0x14000e0a9  mov     rdx, r14; Source2
0x14000e0ac  call    cs:__imp_RtlCompareMemory
0x14000e0b3  nop     dword ptr [rax+rax+00h]
0x14000e0b8  cmp     rax, rsi
0x14000e0bb  setz    dl
0x14000e0be  add     ebp, 2
0x14000e0c1  add     ebp, r15d
0x14000e0c4  test    dl, dl
0x14000e0c6  jz      short loc_14000E063
0x14000e0c8  cmp     byte ptr [rdi+1], 7
0x14000e0cc  jnz     short loc_14000E0D5
0x14000e0ce  mov     bl, dl
0x14000e0d0  jmp     loc_14000E1EE
0x14000e0d5  test    dl, dl
0x14000e0d7  jmp     loc_14000E1EB
0x14000e0dc  cmp     word ptr [rdi+2], 8
0x14000e0e1  jnz     loc_14000E1EE
0x14000e0e7  xor     al, al
0x14000e0e9  cmp     esi, 4
0x14000e0ec  ja      short loc_14000E118
0x14000e0ee  mov     ebx, 1
0x14000e0f3  jnz     short loc_14000E0F9
0x14000e0f5  mov     ecx, [rdx]
0x14000e0f7  jmp     short loc_14000E10A
0x14000e0f9  cmp     esi, 2
0x14000e0fc  jnz     short loc_14000E103
0x14000e0fe  movzx   ecx, word ptr [rdx]
0x14000e101  jmp     short loc_14000E10A
0x14000e103  cmp     esi, ebx
0x14000e105  jnz     short loc_14000E118
0x14000e107  movzx   ecx, byte ptr [rdx]
0x14000e10a  cmp     [rdi+4], ecx
0x14000e10d  ja      short loc_14000E118
0x14000e10f  cmp     ecx, [rdi+8]
0x14000e112  movzx   eax, al
0x14000e115  cmovbe  eax, ebx
0x14000e118  cmp     r8b, 6
0x14000e11c  jmp     loc_14000E1E3
0x14000e121  movzx   ecx, word ptr [rdi+2]
0x14000e125  lea     rax, [rsi+2]
0x14000e129  mov     rbp, rsi
0x14000e12c  cmp     rcx, rax
0x14000e12f  jb      loc_14000E1EE
0x14000e135  movzx   r15d, word ptr [rdi+4]
0x14000e13a  lea     eax, [rcx-2]
0x14000e13d  xor     edx, edx
0x14000e13f  xor     cl, cl
0x14000e141  div     r15d
0x14000e144  cmp     eax, esi
0x14000e146  jnz     short loc_14000E186
0x14000e148  xor     r12d, r12d
0x14000e14b  lea     rsi, [rdi+6]
0x14000e14f  xor     eax, eax
0x14000e151  cmp     ax, r15w
0x14000e155  jnb     short loc_14000E186
0x14000e157  lea     ebx, [rax+1]
0x14000e15a  test    cl, cl
0x14000e15c  jnz     short loc_14000E186
0x14000e15e  mov     r8, rbp; Length
0x14000e161  mov     rdx, r14; Source2
0x14000e164  mov     rcx, rsi; Source1
0x14000e167  call    cs:__imp_RtlCompareMemory
0x14000e16e  nop     dword ptr [rax+rax+00h]
0x14000e173  cmp     rax, rbp
0x14000e176  setz    cl
0x14000e179  add     rsi, rbp
0x14000e17c  add     r12w, bx
0x14000e180  cmp     r12w, r15w
0x14000e184  jb      short loc_14000E15A
0x14000e186  cmp     byte ptr [rdi+1], 5
0x14000e18a  jnz     short loc_14000E190
0x14000e18c  mov     bl, cl
0x14000e18e  jmp     short loc_14000E1EE
0x14000e190  test    cl, cl
0x14000e192  jmp     short loc_14000E1EB
0x14000e194  movzx   ecx, word ptr [rdi+2]
0x14000e198  cmp     ecx, esi
0x14000e19a  jnz     short loc_14000E1EE
0x14000e19c  xor     al, al
0x14000e19e  cmp     esi, 4
0x14000e1a1  ja      short loc_14000E1DF
0x14000e1a3  cmp     ecx, 4
0x14000e1a6  ja      short loc_14000E1DF
0x14000e1a8  mov     ebx, 1
0x14000e1ad  cmp     esi, 4
0x14000e1b0  jnz     short loc_14000E1BA
0x14000e1b2  mov     edx, [rdi+4]
0x14000e1b5  mov     ecx, [r14]
0x14000e1b8  jmp     short loc_14000E1D5
0x14000e1ba  cmp     esi, 2
0x14000e1bd  jnz     short loc_14000E1C9
0x14000e1bf  movzx   edx, word ptr [rdi+4]
0x14000e1c3  movzx   ecx, word ptr [r14]
0x14000e1c7  jmp     short loc_14000E1D5
0x14000e1c9  cmp     esi, ebx
0x14000e1cb  jnz     short loc_14000E1DF
0x14000e1cd  movzx   edx, byte ptr [rdi+4]
0x14000e1d1  movzx   ecx, byte ptr [r14]
0x14000e1d5  and     ecx, edx
0x14000e1d7  movzx   eax, al
0x14000e1da  cmp     ecx, edx
0x14000e1dc  cmovz   eax, ebx
0x14000e1df  cmp     r8b, 4
0x14000e1e3  jnz     short loc_14000E1E9
0x14000e1e5  mov     bl, al
0x14000e1e7  jmp     short loc_14000E1EE
0x14000e1e9  test    al, al
0x14000e1eb  setz    bl
0x14000e1ee  mov     al, bl
0x14000e1f0  add     rsp, 28h
0x14000e1f4  pop     r15
0x14000e1f6  pop     r14
0x14000e1f8  pop     r13
0x14000e1fa  pop     r12
0x14000e1fc  pop     rdi
0x14000e1fd  pop     rsi
0x14000e1fe  pop     rbp
0x14000e1ff  pop     rbx
0x14000e200  retn
```

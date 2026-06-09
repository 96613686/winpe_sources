# bsdtar_getopt

- ea: `0x140003ad4`
- end: `0x140003ef9`
- name: `bsdtar_getopt`
- size: `1061`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001f9c`

## callees

- `0x140003ad4`
- `0x140007298`
- `0x1400076b9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003c4d`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003d18`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003da6`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003c4d`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003d18`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140003da6`

## pseudocode

```c
__int64 __fastcall bsdtar_getopt(__int64 a1)
{
  int v2; // eax
  unsigned __int8 ***v3; // rdi
  unsigned __int8 **v4; // rcx
  int v5; // edx
  unsigned __int8 *v6; // rax
  unsigned int v7; // ebp
  int v8; // eax
  unsigned __int8 **v9; // r9
  unsigned __int8 *v10; // rdx
  int v11; // r8d
  _DWORD *v12; // r14
  const char **v13; // rsi
  const char **v14; // r13
  const char *v15; // r12
  char *v16; // rax
  char *v17; // rax
  unsigned __int8 **v18; // rcx
  unsigned __int8 *v19; // rax
  char *v20; // rax
  char *v22; // rax
  unsigned __int8 *v23; // rcx
  unsigned __int8 **v24; // rax
  const char *v25; // rcx
  char *v26; // rax
  const char *v27; // r15
  __int64 v28; // rbp
  const char *v29; // rax
  char v30; // cl
  const char **v31; // r14
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned __int8 **v34; // rcx
  unsigned __int8 *v35; // rax
  _DWORD *v36; // [rsp+80h] [rbp+8h]

  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 128);
    v3 = (unsigned __int8 ***)(a1 + 152);
    *(_QWORD *)(a1 + 160) = 0;
    if ( v2 )
    {
      if ( v2 != 1 )
        goto LABEL_5;
    }
    else
    {
      ++*v3;
      --*(_DWORD *)(a1 + 148);
      v4 = *v3;
      v5 = *(_DWORD *)(a1 + 148);
      v6 = **v3;
      if ( !v6 )
        return 0xFFFFFFFFLL;
      if ( *v6 == 45 )
      {
        *(_DWORD *)(a1 + 128) = 2;
LABEL_5:
        v7 = 63;
        goto LABEL_6;
      }
      *(_DWORD *)(a1 + 128) = 1;
      *(_QWORD *)(a1 + 136) = *v4;
      *v3 = v4 + 1;
      *(_DWORD *)(a1 + 148) = v5 - 1;
    }
    v16 = *(char **)(a1 + 136);
    v7 = *v16;
    *(_QWORD *)(a1 + 136) = v16 + 1;
    if ( v7 )
    {
      v17 = strchr("aBb:C:cf:HhI:JjkLlmnOoPpqrSs:T:tUuvW:wX:xyZz", v7);
      if ( !v17 )
        return 63;
      if ( v17[1] == 58 )
      {
        v18 = *v3;
        v19 = **v3;
        *(_QWORD *)(a1 + 160) = v19;
        if ( !v19 )
        {
          lafe_warnc(0, "Option %c requires an argument", v7);
          return 63;
        }
        --*(_DWORD *)(a1 + 148);
        *v3 = v18 + 1;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 128) = 2;
    }
LABEL_6:
    v8 = *(_DWORD *)(a1 + 128);
    if ( v8 == 2 )
    {
      v9 = *v3;
      v10 = **v3;
      if ( !v10 || *v10 != 45 )
        return 0xFFFFFFFFLL;
      v11 = *v10 - 45;
      if ( *v10 == 45 )
      {
        v11 = v10[1] - 45;
        if ( v10[1] == 45 )
          v11 = v10[2];
      }
      v12 = (_DWORD *)(a1 + 148);
      --*(_DWORD *)(a1 + 148);
      *v3 = v9 + 1;
      if ( !v11 )
        return 0xFFFFFFFFLL;
      *(_QWORD *)(a1 + 136) = v10;
      v13 = 0;
      v36 = (_DWORD *)(a1 + 148);
      v14 = 0;
      v15 = "--";
      if ( v10[1] == 45 )
      {
        *(_DWORD *)(a1 + 128) = 4;
        *(_QWORD *)(a1 + 136) = v10 + 2;
        goto LABEL_40;
      }
      *(_DWORD *)(a1 + 128) = 3;
      *(_QWORD *)(a1 + 136) = v10 + 1;
    }
    else
    {
      v13 = 0;
      v12 = (_DWORD *)(a1 + 148);
      v14 = 0;
      v36 = (_DWORD *)(a1 + 148);
      v15 = "--";
      if ( v8 != 3 )
        goto LABEL_40;
    }
    v20 = *(char **)(a1 + 136);
    v7 = *v20;
    *(_QWORD *)(a1 + 136) = v20 + 1;
    if ( v7 )
      break;
    *(_DWORD *)(a1 + 128) = 2;
  }
  v22 = strchr("aBb:C:cf:HhI:JjkLlmnOoPpqrSs:T:tUuvW:wX:xyZz", v7);
  if ( !v22 )
    return 63;
  if ( v22[1] == 58 )
  {
    v23 = *(unsigned __int8 **)(a1 + 136);
    if ( !*v23 )
    {
      v24 = *v3;
      v23 = **v3;
      *(_QWORD *)(a1 + 136) = v23;
      if ( !v23 )
      {
        lafe_warnc(0, "Option -%c requires an argument", v7);
        return 63;
      }
      --*v12;
      *v3 = v24 + 1;
    }
    if ( v7 == 87 )
    {
      *(_DWORD *)(a1 + 128) = 4;
      v15 = "-W ";
    }
    else
    {
      *(_DWORD *)(a1 + 128) = 2;
      *(_QWORD *)(a1 + 160) = v23;
    }
  }
LABEL_40:
  if ( *(_DWORD *)(a1 + 128) != 4 )
    return v7;
  v25 = *(const char **)(a1 + 136);
  *(_DWORD *)(a1 + 128) = 2;
  v26 = strchr(v25, 61);
  v27 = *(const char **)(a1 + 136);
  if ( v26 )
  {
    v28 = v26 - v27;
    *(_QWORD *)(a1 + 160) = v26 + 1;
  }
  else
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
  }
  v29 = "absolute-paths";
  if ( !"absolute-paths" )
    goto LABEL_67;
  v30 = *v27;
  v31 = (const char **)&off_1400090B0;
  while ( *v29 != v30 )
  {
LABEL_53:
    v31 += 2;
    v29 = *v31;
    if ( !*v31 )
      goto LABEL_56;
  }
  if ( strncmp_0(v27, *v31, (unsigned int)v28) )
    goto LABEL_52;
  v14 = v13;
  v13 = v31;
  v32 = -1;
  do
    ++v32;
  while ( (*v31)[v32] );
  if ( v32 != v28 )
  {
LABEL_52:
    v30 = *v27;
    goto LABEL_53;
  }
  v14 = 0;
LABEL_56:
  if ( !v13 )
  {
LABEL_67:
    lafe_warnc(0, "Option %s%s is not supported", v15, *(_QWORD *)(a1 + 136));
    return 63;
  }
  if ( v14 )
  {
    lafe_warnc(0, "Ambiguous option %s%s (matches --%s and --%s)", v15, *(const char **)(a1 + 136), *v13, *v14);
    return 63;
  }
  v33 = *(_QWORD *)(a1 + 160);
  if ( !*((_DWORD *)v13 + 2) )
  {
    if ( !v33 )
      return *((unsigned int *)v13 + 3);
    lafe_warnc(0, "Option %s%s does not allow an argument", v15, *v13);
    return 63;
  }
  if ( !v33 )
  {
    v34 = *v3;
    v35 = **v3;
    *(_QWORD *)(a1 + 160) = v35;
    if ( !v35 )
    {
      lafe_warnc(0, "Option %s%s requires an argument", v15, *v13);
      return 63;
    }
    *v3 = v34 + 1;
    --*v36;
  }
  return *((unsigned int *)v13 + 3);
}

```

## disassembly

```asm
0x140003ad4  push    rbx
0x140003ad6  push    rbp
0x140003ad7  push    rsi
0x140003ad8  push    rdi
0x140003ad9  push    r12
0x140003adb  push    r13
0x140003add  push    r14
0x140003adf  push    r15
0x140003ae1  sub     rsp, 38h
0x140003ae5  mov     r10d, 2Dh ; '-'
0x140003aeb  mov     rbx, rcx
0x140003aee  lea     r15d, [r10+12h]
0x140003af2  mov     eax, [rbx+80h]
0x140003af8  lea     rdi, [rbx+98h]
0x140003aff  mov     qword ptr [rbx+0A0h], 0
0x140003b0a  test    eax, eax
0x140003b0c  jnz     loc_140003C14
0x140003b12  add     qword ptr [rdi], 8
0x140003b16  dec     dword ptr [rbx+94h]
0x140003b1c  mov     rcx, [rdi]
0x140003b1f  mov     edx, [rbx+94h]
0x140003b25  mov     rax, [rcx]
0x140003b28  test    rax, rax
0x140003b2b  jz      loc_140003D07
0x140003b31  cmp     [rax], r10b
0x140003b34  jnz     loc_140003BEE
0x140003b3a  mov     dword ptr [rbx+80h], 2
0x140003b44  mov     ebp, r15d
0x140003b47  mov     eax, [rbx+80h]
0x140003b4d  cmp     eax, 2
0x140003b50  jnz     loc_140003C8C
0x140003b56  mov     r9, [rdi]
0x140003b59  mov     rdx, [r9]
0x140003b5c  test    rdx, rdx
0x140003b5f  jz      loc_140003D07
0x140003b65  cmp     [rdx], r10b
0x140003b68  jnz     loc_140003D07
0x140003b6e  movzx   r8d, byte ptr [rdx]
0x140003b72  movzx   eax, r10b
0x140003b76  sub     r8d, eax
0x140003b79  jnz     short loc_140003B96
0x140003b7b  movzx   r8d, byte ptr [rdx+1]
0x140003b80  movzx   eax, r10b
0x140003b84  sub     r8d, eax
0x140003b87  jnz     short loc_140003B96
0x140003b89  movzx   r8d, byte ptr [rdx+2]
0x140003b8e  xor     eax, eax
0x140003b90  movzx   ecx, al
0x140003b93  sub     r8d, ecx
0x140003b96  lea     r14, [rbx+94h]
0x140003b9d  dec     dword ptr [r14]
0x140003ba0  lea     rax, [r9+8]
0x140003ba4  mov     [rdi], rax
0x140003ba7  test    r8d, r8d
0x140003baa  jz      loc_140003D07
0x140003bb0  lea     rax, [rdx+1]
0x140003bb4  mov     [rbx+88h], rdx
0x140003bbb  xor     esi, esi
0x140003bbd  mov     [rsp+78h+arg_0], r14
0x140003bc5  xor     r13d, r13d
0x140003bc8  lea     r12, asc_14000A8F0; "--"
0x140003bcf  cmp     [rax], r10b
0x140003bd2  jz      loc_140003CF0
0x140003bd8  mov     dword ptr [rbx+80h], 3
0x140003be2  mov     [rbx+88h], rax
0x140003be9  jmp     loc_140003CB0
0x140003bee  mov     dword ptr [rbx+80h], 1
0x140003bf8  mov     rax, [rcx]
0x140003bfb  mov     [rbx+88h], rax
0x140003c02  lea     rax, [rcx+8]
0x140003c06  mov     [rdi], rax
0x140003c09  lea     eax, [rdx-1]
0x140003c0c  mov     [rbx+94h], eax
0x140003c12  jmp     short loc_140003C1D
0x140003c14  cmp     eax, 1
0x140003c17  jnz     loc_140003B44
0x140003c1d  mov     rax, [rbx+88h]
0x140003c24  movsx   ebp, byte ptr [rax]
0x140003c27  inc     rax
0x140003c2a  mov     [rbx+88h], rax
0x140003c31  test    ebp, ebp
0x140003c33  jnz     short loc_140003C44
0x140003c35  mov     dword ptr [rbx+80h], 2
0x140003c3f  jmp     loc_140003B47
0x140003c44  mov     edx, ebp; Val
0x140003c46  lea     rcx, Str; "aBb:C:cf:HhI:JjkLlmnOoPpqrSs:T:tUuvW:wX"...
0x140003c4d  call    cs:__imp_strchr
0x140003c53  test    rax, rax
0x140003c56  jz      loc_140003CE8
0x140003c5c  cmp     byte ptr [rax+1], 3Ah ; ':'
0x140003c60  jnz     short loc_140003C81
0x140003c62  mov     rcx, [rdi]
0x140003c65  mov     rax, [rcx]
0x140003c68  mov     [rbx+0A0h], rax
0x140003c6f  test    rax, rax
0x140003c72  jz      short loc_140003CD7
0x140003c74  dec     dword ptr [rbx+94h]
0x140003c7a  lea     rax, [rcx+8]
0x140003c7e  mov     [rdi], rax
0x140003c81  mov     r10d, 2Dh ; '-'
0x140003c87  jmp     loc_140003B47
0x140003c8c  xor     esi, esi
0x140003c8e  lea     r14, [rbx+94h]
0x140003c95  xor     r13d, r13d
0x140003c98  mov     [rsp+78h+arg_0], r14
0x140003ca0  lea     r12, asc_14000A8F0; "--"
0x140003ca7  cmp     eax, 3
0x140003caa  jnz     loc_140003D83
0x140003cb0  mov     rax, [rbx+88h]
0x140003cb7  movsx   ebp, byte ptr [rax]
0x140003cba  inc     rax
0x140003cbd  mov     [rbx+88h], rax
0x140003cc4  test    ebp, ebp
0x140003cc6  jnz     short loc_140003D0F
0x140003cc8  mov     dword ptr [rbx+80h], 2
0x140003cd2  jmp     loc_140003AF2
0x140003cd7  lea     rdx, aOptionCRequire; "Option %c requires an argument"
0x140003cde  mov     r8d, ebp
0x140003ce1  xor     ecx, ecx
0x140003ce3  call    lafe_warnc
0x140003ce8  mov     eax, r15d
0x140003ceb  jmp     loc_140003EE8
0x140003cf0  lea     rax, [rdx+2]
0x140003cf4  mov     dword ptr [rbx+80h], 4
0x140003cfe  mov     [rbx+88h], rax
0x140003d05  jmp     short loc_140003D83
0x140003d07  or      eax, 0FFFFFFFFh
0x140003d0a  jmp     loc_140003EE8
0x140003d0f  mov     edx, ebp; Val
0x140003d11  lea     rcx, Str; "aBb:C:cf:HhI:JjkLlmnOoPpqrSs:T:tUuvW:wX"...
0x140003d18  call    cs:__imp_strchr
0x140003d1e  test    rax, rax
0x140003d21  jz      short loc_140003CE8
0x140003d23  cmp     byte ptr [rax+1], 3Ah ; ':'
0x140003d27  jnz     short loc_140003D83
0x140003d29  mov     rcx, [rbx+88h]
0x140003d30  cmp     byte ptr [rcx], 0
0x140003d33  jnz     short loc_140003D5A
0x140003d35  mov     rax, [rdi]
0x140003d38  mov     rcx, [rax]
0x140003d3b  mov     [rbx+88h], rcx
0x140003d42  test    rcx, rcx
0x140003d45  jnz     short loc_140003D50
0x140003d47  lea     rdx, aOptionCRequire_0; "Option -%c requires an argument"
0x140003d4e  jmp     short loc_140003CDE
0x140003d50  add     rax, 8
0x140003d54  dec     dword ptr [r14]
0x140003d57  mov     [rdi], rax
0x140003d5a  cmp     ebp, 57h ; 'W'
0x140003d5d  jnz     short loc_140003D72
0x140003d5f  mov     dword ptr [rbx+80h], 4
0x140003d69  lea     r12, aW; "-W "
0x140003d70  jmp     short loc_140003D83
0x140003d72  mov     dword ptr [rbx+80h], 2
0x140003d7c  mov     [rbx+0A0h], rcx
0x140003d83  cmp     dword ptr [rbx+80h], 4
0x140003d8a  jnz     loc_140003EE6
0x140003d90  mov     rcx, [rbx+88h]; Str
0x140003d97  mov     edx, 3Dh ; '='; Val
0x140003d9c  mov     dword ptr [rbx+80h], 2
0x140003da6  call    cs:__imp_strchr
0x140003dac  mov     r15, [rbx+88h]
0x140003db3  test    rax, rax
0x140003db6  jz      short loc_140003DCA
0x140003db8  mov     rbp, rax
0x140003dbb  sub     rbp, r15
0x140003dbe  inc     rax
0x140003dc1  mov     [rbx+0A0h], rax
0x140003dc8  jmp     short loc_140003DD8
0x140003dca  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140003dce  inc     rbp
0x140003dd1  cmp     byte ptr [r15+rbp], 0
0x140003dd6  jnz     short loc_140003DCE
0x140003dd8  mov     rax, cs:off_1400090B0; "absolute-paths"
0x140003ddf  test    rax, rax
0x140003de2  jz      loc_140003EC7
0x140003de8  mov     cl, [r15]
0x140003deb  lea     r14, off_1400090B0; "absolute-paths"
0x140003df2  cmp     [rax], cl
0x140003df4  jnz     short loc_140003E26
0x140003df6  mov     rdx, [r14]; Str2
0x140003df9  mov     r8d, ebp; MaxCount
0x140003dfc  mov     rcx, r15; Str1
0x140003dff  call    strncmp_0
0x140003e04  test    eax, eax
0x140003e06  jnz     short loc_140003E23
0x140003e08  mov     rcx, [r14]
0x140003e0b  mov     r13, rsi
0x140003e0e  mov     rsi, r14
0x140003e11  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003e15  inc     rax
0x140003e18  cmp     byte ptr [rcx+rax], 0
0x140003e1c  jnz     short loc_140003E15
0x140003e1e  cmp     rax, rbp
0x140003e21  jz      short loc_140003E34
0x140003e23  mov     cl, [r15]
0x140003e26  add     r14, 10h
0x140003e2a  mov     rax, [r14]
0x140003e2d  test    rax, rax
0x140003e30  jnz     short loc_140003DF2
0x140003e32  jmp     short loc_140003E37
0x140003e34  xor     r13d, r13d
0x140003e37  test    rsi, rsi
0x140003e3a  jz      loc_140003EC7
0x140003e40  test    r13, r13
0x140003e43  jz      short loc_140003E70
0x140003e45  mov     rax, [r13+0]
0x140003e49  lea     rdx, aAmbiguousOptio; "Ambiguous option %s%s (matches --%s and"...
0x140003e50  mov     r9, [rbx+88h]
0x140003e57  mov     r8, r12
0x140003e5a  mov     [rsp+78h+var_50], rax
0x140003e5f  xor     ecx, ecx
0x140003e61  mov     rax, [rsi]
0x140003e64  mov     [rsp+78h+var_58], rax
0x140003e69  call    lafe_warnc
0x140003e6e  jmp     short loc_140003EDF
0x140003e70  cmp     dword ptr [rsi+8], 0
0x140003e74  mov     rax, [rbx+0A0h]
0x140003e7b  jz      short loc_140003EB6
0x140003e7d  test    rax, rax
0x140003e80  jnz     short loc_140003EB1
0x140003e82  mov     rcx, [rdi]
0x140003e85  mov     rax, [rcx]
0x140003e88  mov     [rbx+0A0h], rax
0x140003e8f  test    rax, rax
0x140003e92  jnz     short loc_140003EA0
0x140003e94  mov     r9, [rsi]
0x140003e97  lea     rdx, aOptionSSRequir; "Option %s%s requires an argument"
0x140003e9e  jmp     short loc_140003ED5
0x140003ea0  lea     rax, [rcx+8]
0x140003ea4  mov     [rdi], rax
0x140003ea7  mov     rax, [rsp+78h+arg_0]
0x140003eaf  dec     dword ptr [rax]
0x140003eb1  mov     eax, [rsi+0Ch]
0x140003eb4  jmp     short loc_140003EE8
0x140003eb6  test    rax, rax
0x140003eb9  jz      short loc_140003EB1
0x140003ebb  mov     r9, [rsi]
0x140003ebe  lea     rdx, aOptionSSDoesNo; "Option %s%s does not allow an argument"
0x140003ec5  jmp     short loc_140003ED5
0x140003ec7  mov     r9, [rbx+88h]
0x140003ece  lea     rdx, aOptionSSIsNotS; "Option %s%s is not supported"
0x140003ed5  mov     r8, r12
0x140003ed8  xor     ecx, ecx
0x140003eda  call    lafe_warnc
0x140003edf  mov     eax, 3Fh ; '?'
0x140003ee4  jmp     short loc_140003EE8
0x140003ee6  mov     eax, ebp
0x140003ee8  add     rsp, 38h
0x140003eec  pop     r15
0x140003eee  pop     r14
0x140003ef0  pop     r13
0x140003ef2  pop     r12
0x140003ef4  pop     rdi
0x140003ef5  pop     rsi
0x140003ef6  pop     rbp
0x140003ef7  pop     rbx
0x140003ef8  retn
```

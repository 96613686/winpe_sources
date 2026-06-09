# CMSG_UpdateStream

- ea: `0x180002c34`
- end: `0x180002f6d`
- name: `CMSG_UpdateStream`
- size: `825`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002790`

## callees

- `0x180002280`
- `0x180002c34`
- `0x180002f74`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x18001f169`
- `0x180020010`

## string_xrefs

- `0x180002ebf`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`
- `0x180002f20`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`
- `0x180002f53`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_UpdateStream(__int64 a1, char *a2, unsigned int a3, int a4)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // r13d
  char *v7; // rbp
  __int64 v8; // r14
  char *v9; // r15
  __int64 v10; // rsi
  unsigned int v11; // r12d
  unsigned int v12; // r12d
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // eax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v23; // rax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-54h]
  char *v29; // [rsp+A8h] [rbp+10h]
  unsigned int v30; // [rsp+B0h] [rbp+18h]

  v30 = a3;
  v29 = a2;
  v4 = *(_QWORD *)(a1 + 72);
  v5 = 0;
  v26 = 0;
  v27 = 0;
  v6 = *(_DWORD *)(*(_QWORD *)(v4 + 112) + 60LL);
  if ( (*(_DWORD *)(v4 + 200) & 0x10000000) != 0 )
  {
    v5 = *(_DWORD *)(*(_QWORD *)(v4 + 160) + 48LL);
    v27 = v5;
  }
  v7 = *(char **)(v4 + 184);
  if ( v7 )
    goto LABEL_4;
  *(_DWORD *)(v4 + 196) = v5 + 2 * v6 * (0x1000 / v6 + 2);
  v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v4 + 24))(v5 + 2 * v6 * (0x1000 / v6 + 2), 0x1000 % v6);
  *(_QWORD *)(v4 + 184) = v23;
  v7 = (char *)v23;
  if ( v23 )
  {
    *(_DWORD *)(v4 + 200) |= 0x10u;
    a3 = v30;
    a2 = v29;
    *(_DWORD *)(v4 + 192) = 0;
LABEL_4:
    v8 = ((*(_DWORD *)(v4 + 196) - v6) >> 1) - v5;
    if ( *(_DWORD *)(v4 + 4) )
      v9 = &v7[v8];
    else
      v9 = &v7[((*(_DWORD *)(v4 + 196) - v6) >> 1) - v5 + (unsigned __int64)v5];
    while ( 1 )
    {
      v10 = *(unsigned int *)(v4 + 192);
      v11 = a3;
      if ( (int)v8 - (int)v10 <= a3 )
        v11 = v8 - v10;
      if ( v11 )
      {
        memcpy_0(&v7[v10], a2, v11);
        *(_DWORD *)(v4 + 192) += v11;
        v29 += v11;
        LODWORD(v10) = *(_DWORD *)(v4 + 192);
        a3 = v30 - v11;
        v5 = v27;
        v30 -= v11;
      }
      if ( a4 && !a3 )
        break;
      LODWORD(v10) = v10 - (unsigned int)v10 % v6;
      if ( a3 < v5 + v6 )
      {
        if ( (unsigned int)v10 <= v6 )
          goto LABEL_25;
        LODWORD(v10) = v10 - v6;
      }
      v12 = 0;
      if ( (unsigned int)v10 > v6 )
        goto LABEL_16;
LABEL_25:
      if ( !a3 )
        return 0;
      a2 = v29;
    }
    v12 = 1;
LABEL_16:
    v13 = v8 + v6;
    v14 = v4 + 88;
    if ( *(_DWORD *)(v4 + 4) )
      v15 = CNG_Encrypt(v14, v7, (unsigned int)v10, v9, v5 + v13, &v26, v12);
    else
      v15 = CNG_Decrypt(v14, v7, (unsigned int)v10, v9, v13, &v26, v12);
    v18 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          v17,
          (unsigned int)"Status",
          v15,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
          193);
      return v18;
    }
    v19 = *(_DWORD *)(v4 + 192);
    if ( v19 > (unsigned int)v10 )
      memmove_0(v7, &v7[(unsigned int)v10], v19 - (unsigned int)v10);
    *(_DWORD *)(v4 + 192) -= v10;
    *(_QWORD *)(v4 + 40) += (unsigned int)v10;
    v20 = *(_QWORD *)(a1 + 24);
    if ( *(_DWORD *)(a1 + 32) )
      v21 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD, unsigned int))(a1 + 16))(
              v20,
              v9,
              v26,
              *(_QWORD *)(a1 + 136),
              v12);
    else
      v21 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(a1 + 16))(v20, v9, v26, v12);
    v18 = v21;
    if ( v21 )
    {
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c", 482);
      return v18;
    }
    a3 = v30;
    v5 = v27;
    goto LABEL_25;
  }
  v18 = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      v25,
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      102);
  return v18;
}

```

## disassembly

```asm
0x180002c34  mov     rax, rsp
0x180002c37  mov     [rax+20h], r9d
0x180002c3b  mov     [rax+18h], r8d
0x180002c3f  mov     [rax+10h], rdx
0x180002c43  mov     [rax+8], rcx
0x180002c47  push    rbx
0x180002c48  push    rbp
0x180002c49  push    rsi
0x180002c4a  push    rdi
0x180002c4b  push    r12
0x180002c4d  push    r13
0x180002c4f  push    r14
0x180002c51  push    r15
0x180002c53  sub     rsp, 58h
0x180002c57  mov     rdi, [rcx+48h]
0x180002c5b  xor     ebx, ebx
0x180002c5d  mov     dword ptr [rax-58h], 0
0x180002c64  mov     [rsp+98h+var_54], ebx
0x180002c68  test    dword ptr [rdi+0C8h], 10000000h
0x180002c72  mov     rax, [rdi+70h]
0x180002c76  mov     r13d, [rax+3Ch]
0x180002c7a  jz      short loc_180002C8A
0x180002c7c  mov     rax, [rdi+0A0h]
0x180002c83  mov     ebx, [rax+30h]
0x180002c86  mov     [rsp+98h+var_54], ebx
0x180002c8a  mov     rbp, [rdi+0B8h]
0x180002c91  test    rbp, rbp
0x180002c94  jz      loc_180002E19
0x180002c9a  mov     r14d, [rdi+0C4h]
0x180002ca1  sub     r14d, r13d
0x180002ca4  shr     r14d, 1
0x180002ca7  sub     r14d, ebx
0x180002caa  cmp     dword ptr [rdi+4], 0
0x180002cae  mov     eax, r14d
0x180002cb1  jz      loc_180002EE4
0x180002cb7  lea     r15, [r14+rbp]
0x180002cbb  mov     esi, [rdi+0C0h]
0x180002cc1  mov     eax, r14d
0x180002cc4  sub     eax, esi
0x180002cc6  mov     r12d, r8d
0x180002cc9  cmp     eax, r8d
0x180002ccc  cmovbe  r12d, eax
0x180002cd0  test    r12d, r12d
0x180002cd3  jz      short loc_180002D10
0x180002cd5  lea     rcx, [rsi+rbp]; void *
0x180002cd9  mov     r8d, r12d; Size
0x180002cdc  mov     ebx, r12d
0x180002cdf  call    memcpy_0
0x180002ce4  mov     r8d, [rsp+98h+arg_10]
0x180002cec  add     [rdi+0C0h], r12d
0x180002cf3  add     [rsp+98h+arg_8], rbx
0x180002cfb  mov     esi, [rdi+0C0h]
0x180002d01  sub     r8d, r12d
0x180002d04  mov     ebx, [rsp+98h+var_54]
0x180002d08  mov     [rsp+98h+arg_10], r8d
0x180002d10  cmp     [rsp+98h+arg_18], 0
0x180002d18  jnz     short loc_180002D3D
0x180002d1a  xor     edx, edx
0x180002d1c  mov     eax, esi
0x180002d1e  div     r13d
0x180002d21  lea     eax, [rbx+r13]
0x180002d25  sub     esi, edx
0x180002d27  cmp     r8d, eax
0x180002d2a  jb      loc_180002E77
0x180002d30  xor     r12d, r12d
0x180002d33  cmp     esi, r13d
0x180002d36  ja      short loc_180002D46
0x180002d38  jmp     loc_180002DDB
0x180002d3d  test    r8d, r8d
0x180002d40  jnz     short loc_180002D1A
0x180002d42  lea     r12d, [r8+1]
0x180002d46  cmp     dword ptr [rdi+4], 0
0x180002d4a  lea     rdx, [rsp+98h+var_58]
0x180002d4f  mov     [rsp+98h+var_68], r12d
0x180002d54  lea     eax, [r14+r13]
0x180002d58  mov     [rsp+98h+var_70], rdx
0x180002d5d  lea     rcx, [rdi+58h]
0x180002d61  mov     rdx, rbp
0x180002d64  mov     r9, r15
0x180002d67  mov     r8d, esi
0x180002d6a  jz      loc_180002E88
0x180002d70  add     eax, ebx
0x180002d72  mov     [rsp+98h+var_78], eax
0x180002d76  call    CNG_Encrypt
0x180002d7b  mov     ebx, eax
0x180002d7d  test    eax, eax
0x180002d7f  jnz     loc_180002E96
0x180002d85  mov     eax, [rdi+0C0h]
0x180002d8b  cmp     eax, esi
0x180002d8d  ja      loc_180002F36
0x180002d93  sub     [rdi+0C0h], esi
0x180002d99  mov     rdx, r15
0x180002d9c  mov     eax, esi
0x180002d9e  add     [rdi+28h], rax
0x180002da2  mov     rax, [rsp+98h+arg_0]
0x180002daa  mov     r8d, [rsp+98h+var_58]
0x180002daf  cmp     dword ptr [rax+20h], 0
0x180002db3  mov     rcx, [rax+18h]
0x180002db7  jnz     short loc_180002E02
0x180002db9  mov     rax, [rax+10h]
0x180002dbd  mov     r9d, r12d
0x180002dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc5  mov     ebx, eax
0x180002dc7  test    eax, eax
0x180002dc9  jnz     loc_180002F4D
0x180002dcf  mov     r8d, [rsp+98h+arg_10]
0x180002dd7  mov     ebx, [rsp+98h+var_54]
0x180002ddb  test    r8d, r8d
0x180002dde  jz      short loc_180002DED
0x180002de0  mov     rdx, [rsp+98h+arg_8]
0x180002de8  jmp     loc_180002CBB
0x180002ded  xor     ebx, ebx
0x180002def  mov     eax, ebx
0x180002df1  add     rsp, 58h
0x180002df5  pop     r15
0x180002df7  pop     r14
0x180002df9  pop     r13
0x180002dfb  pop     r12
0x180002dfd  pop     rdi
0x180002dfe  pop     rsi
0x180002dff  pop     rbp
0x180002e00  pop     rbx
0x180002e01  retn
0x180002e02  mov     r9, [rax+88h]
0x180002e09  mov     rax, [rax+10h]
0x180002e0d  mov     [rsp+98h+var_78], r12d
0x180002e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e17  jmp     short loc_180002DC5
0x180002e19  xor     edx, edx
0x180002e1b  mov     eax, 1000h
0x180002e20  div     r13d
0x180002e23  add     eax, 2
0x180002e26  imul    eax, r13d
0x180002e2a  lea     eax, [rbx+rax*2]
0x180002e2d  mov     [rdi+0C4h], eax
0x180002e33  mov     ecx, eax
0x180002e35  mov     rax, [rdi+18h]
0x180002e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3e  mov     [rdi+0B8h], rax
0x180002e45  mov     rbp, rax
0x180002e48  test    rax, rax
0x180002e4b  jz      loc_180002EF2
0x180002e51  or      dword ptr [rdi+0C8h], 10h
0x180002e58  mov     r8d, [rsp+98h+arg_10]
0x180002e60  mov     rdx, [rsp+98h+arg_8]
0x180002e68  mov     dword ptr [rdi+0C0h], 0
0x180002e72  jmp     loc_180002C9A
0x180002e77  cmp     esi, r13d
0x180002e7a  jbe     loc_180002DDB
0x180002e80  sub     esi, r13d
0x180002e83  jmp     loc_180002D30
0x180002e88  mov     [rsp+98h+var_78], eax
0x180002e8c  call    CNG_Decrypt
0x180002e91  jmp     loc_180002D7B
0x180002e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e9d  lea     rax, WPP_GLOBAL_Control
0x180002ea4  cmp     rcx, rax
0x180002ea7  jz      loc_180002DEF
0x180002ead  test    byte ptr [rcx+1Ch], 1
0x180002eb1  jz      loc_180002DEF
0x180002eb7  mov     [rsp+98h+var_68], 1C1h
0x180002ebf  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ec6  mov     [rsp+98h+var_70], rax
0x180002ecb  mov     [rsp+98h+var_78], ebx
0x180002ecf  mov     rcx, [rcx+10h]
0x180002ed3  lea     r9, aStatus; "Status"
0x180002eda  call    WPP_SF_sDsd
0x180002edf  jmp     loc_180002DEF
0x180002ee4  mov     r15d, ebx
0x180002ee7  add     r15, rax
0x180002eea  add     r15, rbp
0x180002eed  jmp     loc_180002CBB
0x180002ef2  mov     ebx, 8009000Eh
0x180002ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002efe  lea     rax, WPP_GLOBAL_Control
0x180002f05  cmp     rcx, rax
0x180002f08  jz      loc_180002DEF
0x180002f0e  test    byte ptr [rcx+1Ch], 1
0x180002f12  jz      loc_180002DEF
0x180002f18  mov     [rsp+98h+var_68], 166h
0x180002f20  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002f27  mov     [rsp+98h+var_70], rax
0x180002f2c  mov     [rsp+98h+var_78], 8009000Eh
0x180002f34  jmp     short loc_180002ECF
0x180002f36  sub     eax, esi
0x180002f38  mov     edx, esi
0x180002f3a  mov     r8d, eax; Size
0x180002f3d  add     rdx, rbp; Src
0x180002f40  mov     rcx, rbp; void *
0x180002f43  call    memmove_0
0x180002f48  jmp     loc_180002D93
0x180002f4d  mov     r9d, 1E2h
0x180002f53  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002f5a  lea     rdx, aStatus; "Status"
0x180002f61  mov     ecx, ebx
0x180002f63  call    DebugTraceError
0x180002f68  jmp     loc_180002DEF
```

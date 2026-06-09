# bVerifyMsftTable(sfnt_mappingTable *,ulong *,ulong *,_CMAPINFO *,ushort,ulong *,uint,uint,sfnt_char2IndexDirectory *)

- ea: `0x140046b40`
- end: `0x140046d37`
- name: `?bVerifyMsftTable@@YAHPEAUsfnt_mappingTable@@PEAK1PEAU_CMAPINFO@@G1IIPEAUsfnt_char2IndexDirectory@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(struct sfnt_mappingTable *, unsigned int *, unsigned int *, struct _CMAPINFO *, unsigned __int16, unsigned int *, unsigned int, unsigned int, struct sfnt_char2IndexDirectory *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009224`

## callees

- `0x140046b40`
- `0x140046d40`

## pseudocode

```c
__int64 __fastcall bVerifyMsftTable(
        struct sfnt_mappingTable *a1,
        unsigned int *a2,
        unsigned int *a3,
        struct _CMAPINFO *a4,
        unsigned __int16 a5,
        unsigned int *a6,
        unsigned int a7,
        unsigned int a8,
        struct sfnt_char2IndexDirectory *a9)
{
  __int16 v13; // cx
  __int16 v14; // ax
  unsigned __int16 *v15; // rdi
  unsigned __int16 v16; // cx
  __int64 v17; // rdx
  unsigned __int16 v18; // bp
  unsigned __int16 *v19; // rsi
  unsigned __int16 *v20; // r10
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // ecx
  int v24; // r11d
  int v25; // r9d
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // r8

  if ( !(unsigned int)IsValidFormat4TableSize(a1, a9, a8, a7) )
    return 0;
  v13 = *((_BYTE *)a1 + 7) >> 1;
  v14 = *((unsigned __int8 *)a1 + 6);
  v15 = (unsigned __int16 *)((char *)a1 + 14);
  v16 = (v14 << 7) | v13;
  v17 = v16;
  if ( v15[v16 - 1] != 0xFFFF )
    return 0;
  *a2 = 3;
  v18 = 0;
  v19 = &v15[v16];
  v20 = v19 + 1;
  v21 = *((unsigned __int8 *)v19 + 2) << 8;
  v22 = v21 | *((unsigned __int8 *)v19 + 3);
  *a6 = v22;
  if ( a5 == 1 )
  {
    v23 = 61440;
    if ( v21 != 61440 )
      v23 = 0;
  }
  else if ( !v21 || v21 == 57344 )
  {
    v23 = 0;
  }
  else
  {
    v23 = 61440;
    if ( v21 != 61440 )
      v23 = v22 - 32;
  }
  *a3 = v23;
  if ( v19[v17] == 0xFFFF && (unsigned __int16)v17 > 1u )
  {
    LOWORD(v17) = v17 - 1;
    --v19;
  }
  v24 = (unsigned __int16)v17;
  v25 = 0;
  *((_DWORD *)a4 + 1) = (unsigned __int16)v17;
  *(_DWORD *)a4 = 0;
  *((_DWORD *)a4 + 3) = 0;
  while ( v15 < v19 )
  {
    v26 = _byteswap_ushort(*v20);
    v27 = _byteswap_ushort(*v15);
    if ( v27 < v26 || v18 > v26 || !v26 && v27 == 0xFFFF )
      return 0;
    v25 += v27 - v26 + 1;
    *((_DWORD *)a4 + 3) = v25;
    if ( v18 < 0xB7u && v26 > 0xB7u )
      *(_DWORD *)a4 |= 2u;
    if ( v27 >= 0x2219u && v26 <= 0x2219u )
      *(_DWORD *)a4 |= 1u;
    ++v20;
    v18 = v27;
    ++v15;
  }
  if ( (*(_BYTE *)a4 & 3) == 3 )
  {
    *((_DWORD *)a4 + 1) = v24 + 1;
    *((_DWORD *)a4 + 3) = v25 + 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140046b40  push    rbx
0x140046b42  push    rbp
0x140046b43  push    rsi
0x140046b44  push    rdi
0x140046b45  push    r12
0x140046b47  push    r13
0x140046b49  push    r14
0x140046b4b  push    r15
0x140046b4d  sub     rsp, 28h
0x140046b51  mov     rbx, r9
0x140046b54  mov     r14, r8
0x140046b57  mov     r9d, [rsp+68h+arg_30]; unsigned int
0x140046b5f  mov     rsi, rdx
0x140046b62  mov     r8d, [rsp+68h+arg_38]; unsigned int
0x140046b6a  mov     rdi, rcx
0x140046b6d  mov     rdx, [rsp+68h+arg_40]; struct sfnt_char2IndexDirectory *
0x140046b75  call    ?IsValidFormat4TableSize@@YAHPEAUsfnt_mappingTable@@PEAUsfnt_char2IndexDirectory@@II@Z; IsValidFormat4TableSize(sfnt_mappingTable *,sfnt_char2IndexDirectory *,uint,uint)
0x140046b7a  xor     r15d, r15d
0x140046b7d  test    eax, eax
0x140046b7f  jz      loc_140046D06
0x140046b85  mov     al, [rdi+7]
0x140046b88  mov     r11d, 0FFFFh
0x140046b8e  shr     al, 1
0x140046b90  movzx   ecx, al
0x140046b93  movzx   eax, byte ptr [rdi+6]
0x140046b97  add     rdi, 0Eh
0x140046b9b  shl     ax, 7
0x140046b9f  or      cx, ax
0x140046ba2  movzx   edx, cx
0x140046ba5  cmp     [rdi+rdx*2-2], r11w
0x140046bab  jnz     loc_140046D06
0x140046bb1  mov     rax, [rsp+68h+arg_28]
0x140046bb9  lea     r12d, [r15+1]
0x140046bbd  mov     dword ptr [rsi], 3
0x140046bc3  mov     ebp, r15d
0x140046bc6  lea     rsi, [rdi+rdx*2]
0x140046bca  lea     r10, [rsi+2]
0x140046bce  movzx   r8d, byte ptr [r10]
0x140046bd2  movzx   r9d, byte ptr [r10+1]
0x140046bd7  shl     r8d, 8
0x140046bdb  or      r9d, r8d
0x140046bde  mov     [rax], r9d
0x140046be1  cmp     [rsp+68h+arg_20], r12w
0x140046bea  jnz     loc_140046D0A
0x140046bf0  mov     ecx, 0F000h
0x140046bf5  cmp     r8d, ecx
0x140046bf8  cmovnz  ecx, r15d
0x140046bfc  mov     [r14], ecx
0x140046bff  cmp     [r10+rdx*2-2], r11w
0x140046c05  jz      loc_140046CD0
0x140046c0b  movzx   r11d, dx
0x140046c0f  mov     r9d, r15d
0x140046c12  mov     [rbx+4], r11d
0x140046c16  mov     r13d, 0B7h
0x140046c1c  mov     [rbx], r15d
0x140046c1f  mov     r14d, 2219h
0x140046c25  mov     [rbx+0Ch], r15d
0x140046c29  cmp     rdi, rsi
0x140046c2c  jnb     loc_140046CB2
0x140046c32  movzx   eax, byte ptr [r10+1]
0x140046c37  movzx   edx, byte ptr [r10]
0x140046c3b  movzx   r8d, byte ptr [rdi]
0x140046c3f  shl     dx, 8
0x140046c43  or      dx, ax
0x140046c46  shl     r8w, 8
0x140046c4b  movzx   eax, byte ptr [rdi+1]
0x140046c4f  or      r8w, ax
0x140046c53  cmp     r8w, dx
0x140046c57  jb      loc_140046D06
0x140046c5d  cmp     bp, dx
0x140046c60  ja      loc_140046D06
0x140046c66  test    dx, dx
0x140046c69  jz      loc_140046CF7
0x140046c6f  inc     r9d
0x140046c72  movzx   ecx, r8w
0x140046c76  movzx   eax, dx
0x140046c79  sub     ecx, eax
0x140046c7b  add     r9d, ecx
0x140046c7e  mov     [rbx+0Ch], r9d
0x140046c82  cmp     r13w, bp
0x140046c86  ja      short loc_140046CA7
0x140046c88  cmp     r14w, r8w
0x140046c8c  jbe     short loc_140046C9C
0x140046c8e  add     r10, 2
0x140046c92  movzx   ebp, r8w
0x140046c96  add     rdi, 2
0x140046c9a  jmp     short loc_140046C29
0x140046c9c  cmp     r14w, dx
0x140046ca0  jb      short loc_140046C8E
0x140046ca2  or      [rbx], r12d
0x140046ca5  jmp     short loc_140046C8E
0x140046ca7  cmp     r13w, dx
0x140046cab  jnb     short loc_140046C88
0x140046cad  or      dword ptr [rbx], 2
0x140046cb0  jmp     short loc_140046C88
0x140046cb2  mov     ecx, [rbx]
0x140046cb4  and     ecx, 3
0x140046cb7  cmp     cl, 3
0x140046cba  jz      short loc_140046CE7
0x140046cbc  mov     eax, r12d
0x140046cbf  add     rsp, 28h
0x140046cc3  pop     r15
0x140046cc5  pop     r14
0x140046cc7  pop     r13
0x140046cc9  pop     r12
0x140046ccb  pop     rdi
0x140046ccc  pop     rsi
0x140046ccd  pop     rbp
0x140046cce  pop     rbx
0x140046ccf  retn
0x140046cd0  cmp     dx, r12w
0x140046cd4  jbe     loc_140046C0B
0x140046cda  sub     dx, r12w
0x140046cde  add     rsi, 0FFFFFFFFFFFFFFFEh
0x140046ce2  jmp     loc_140046C0B
0x140046ce7  lea     ecx, [r11+1]
0x140046ceb  mov     [rbx+4], ecx
0x140046cee  lea     ecx, [r9+1]
0x140046cf2  mov     [rbx+0Ch], ecx
0x140046cf5  jmp     short loc_140046CBC
0x140046cf7  mov     eax, 0FFFFh
0x140046cfc  cmp     r8w, ax
0x140046d00  jnz     loc_140046C6F
0x140046d06  xor     eax, eax
0x140046d08  jmp     short loc_140046CBF
0x140046d0a  test    r8d, r8d
0x140046d0d  jz      short loc_140046D2F
0x140046d0f  cmp     r8d, 0E000h
0x140046d16  jz      short loc_140046D2F
0x140046d18  mov     ecx, 0F000h
0x140046d1d  cmp     r8d, ecx
0x140046d20  jz      loc_140046BFC
0x140046d26  lea     ecx, [r9-20h]
0x140046d2a  jmp     loc_140046BFC
0x140046d2f  mov     ecx, r15d
0x140046d32  jmp     loc_140046BFC
```

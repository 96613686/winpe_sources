# I_UrlCacheGetUrlFileName

- ea: `0x180003f00`
- end: `0x18000416d`
- name: `I_UrlCacheGetUrlFileName`
- size: `621`
- prototype: `__int64 __fastcall(UCHAR *, _WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004c90`
- `0x180007dc0`

## callees

- `0x180003f00`
- `0x18000e2f0`
- `0x18000fb38`
- `0x18000fb7c`
- `0x18000fbc4`

## pseudocode

```c
__int64 __fastcall I_UrlCacheGetUrlFileName(UCHAR *a1, _WORD *a2)
{
  __int64 v4; // r8
  BCRYPT_HASH_HANDLE *v5; // r8
  int v6; // r9d
  __int16 v7; // ax
  unsigned int v8; // ecx
  unsigned int v9; // edx
  __int16 v10; // ax
  __int16 v11; // ax
  unsigned int v12; // edx
  unsigned int v13; // ecx
  __int16 v14; // ax
  unsigned int v15; // edx
  __int16 v16; // ax
  __int16 v17; // ax
  unsigned int v18; // edx
  unsigned int v19; // ecx
  __int16 v20; // ax
  unsigned int v21; // edx
  __int16 v22; // ax
  __int16 v23; // ax
  unsigned int v24; // edx
  unsigned int v25; // ecx
  __int16 v26; // ax
  unsigned int v27; // edx
  __int16 v28; // ax
  __int16 v29; // ax
  unsigned int v30; // edx
  unsigned int v31; // ecx
  __int16 v32; // ax
  unsigned int v33; // edx
  __int16 v34; // ax
  __int16 v35; // ax
  unsigned int v36; // edx
  unsigned int v37; // ecx
  __int16 v38; // ax
  unsigned int v39; // edx
  __int16 v40; // ax
  __int16 v41; // ax
  unsigned int v42; // edx
  __int16 v43; // ax
  unsigned int v44; // ecx
  unsigned int v45; // edx
  __int16 v46; // ax
  __int16 v47; // ax
  unsigned int v48; // edx
  unsigned int v49; // ecx
  __int16 v50; // ax
  unsigned int v51; // edx
  __int16 v52; // ax
  __int64 result; // rax
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v55; // [rsp+30h] [rbp-18h]

  *(_OWORD *)phHash = 0;
  v55 = 0;
  CngRsa32Compat_MD5Init(phHash);
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a1[2 * v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  CngRsa32Compat_MD5Update(phHash, a1, 2 * v4);
  CngRsa32Compat_MD5Final((__int64)phHash);
  v5 = &phHash[1];
  v6 = 2;
  do
  {
    v7 = 48;
    v8 = *(unsigned __int8 *)v5 >> 4;
    if ( v8 > 9 )
      v7 = 55;
    v9 = *(_BYTE *)v5 & 0xF;
    *a2 = v8 + v7;
    v10 = 48;
    if ( v9 > 9 )
      v10 = 55;
    v11 = v9 + v10;
    v12 = *((unsigned __int8 *)v5 + 1);
    a2[1] = v11;
    v13 = v12 >> 4;
    v14 = 48;
    if ( v12 >> 4 > 9 )
      v14 = 55;
    v15 = v12 & 0xF;
    a2[2] = v13 + v14;
    v16 = 48;
    if ( v15 > 9 )
      v16 = 55;
    v17 = v15 + v16;
    v18 = *((unsigned __int8 *)v5 + 2);
    a2[3] = v17;
    v19 = v18 >> 4;
    v20 = 48;
    if ( v18 >> 4 > 9 )
      v20 = 55;
    v21 = v18 & 0xF;
    a2[4] = v19 + v20;
    v22 = 48;
    if ( v21 > 9 )
      v22 = 55;
    v23 = v21 + v22;
    v24 = *((unsigned __int8 *)v5 + 3);
    a2[5] = v23;
    v25 = v24 >> 4;
    v26 = 48;
    if ( v24 >> 4 > 9 )
      v26 = 55;
    v27 = v24 & 0xF;
    a2[6] = v25 + v26;
    v28 = 48;
    if ( v27 > 9 )
      v28 = 55;
    v29 = v27 + v28;
    v30 = *((unsigned __int8 *)v5 + 4);
    a2[7] = v29;
    v31 = v30 >> 4;
    v32 = 48;
    if ( v30 >> 4 > 9 )
      v32 = 55;
    v33 = v30 & 0xF;
    a2[8] = v31 + v32;
    v34 = 48;
    if ( v33 > 9 )
      v34 = 55;
    v35 = v33 + v34;
    v36 = *((unsigned __int8 *)v5 + 5);
    a2[9] = v35;
    v37 = v36 >> 4;
    v38 = 48;
    if ( v36 >> 4 > 9 )
      v38 = 55;
    v39 = v36 & 0xF;
    a2[10] = v37 + v38;
    v40 = 48;
    if ( v39 > 9 )
      v40 = 55;
    a2 += 16;
    v41 = v39 + v40;
    v42 = *((unsigned __int8 *)v5 + 6);
    *(a2 - 5) = v41;
    ++v5;
    v43 = 48;
    v44 = v42 >> 4;
    if ( v42 >> 4 > 9 )
      v43 = 55;
    v45 = v42 & 0xF;
    *(a2 - 4) = v44 + v43;
    v46 = 48;
    if ( v45 > 9 )
      v46 = 55;
    v47 = v45 + v46;
    v48 = *((unsigned __int8 *)v5 - 1);
    *(a2 - 3) = v47;
    v49 = v48 >> 4;
    v50 = 48;
    if ( v48 >> 4 > 9 )
      v50 = 55;
    v51 = v48 & 0xF;
    *(a2 - 2) = v49 + v50;
    v52 = 48;
    if ( v51 > 9 )
      v52 = 55;
    *(a2 - 1) = v51 + v52;
    --v6;
  }
  while ( v6 );
  result = 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180003f00  mov     [rsp+arg_10], rbx
0x180003f05  push    rdi
0x180003f06  sub     rsp, 40h
0x180003f0a  mov     rax, cs:__security_cookie
0x180003f11  xor     rax, rsp
0x180003f14  mov     [rsp+48h+var_10], rax
0x180003f19  mov     rdi, rcx
0x180003f1c  xorps   xmm0, xmm0
0x180003f1f  xor     eax, eax
0x180003f21  lea     rcx, [rsp+48h+phHash]; phHash
0x180003f26  movups  xmmword ptr [rsp+48h+phHash], xmm0
0x180003f2b  mov     [rsp+48h+var_18], rax
0x180003f30  mov     rbx, rdx
0x180003f33  call    CngRsa32Compat_MD5Init
0x180003f38  test    rdi, rdi
0x180003f3b  jz      loc_180004165
0x180003f41  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180003f48  nop     dword ptr [rax+rax+00000000h]
0x180003f50  inc     r8
0x180003f53  cmp     word ptr [rdi+r8*2], 0
0x180003f59  jnz     short loc_180003F50
0x180003f5b  add     r8d, r8d
0x180003f5e  lea     rcx, [rsp+48h+phHash]
0x180003f63  mov     rdx, rdi
0x180003f66  call    CngRsa32Compat_MD5Update
0x180003f6b  lea     rcx, [rsp+48h+phHash]
0x180003f70  call    CngRsa32Compat_MD5Final
0x180003f75  lea     r8, [rsp+48h+phHash+8]
0x180003f7a  mov     r9d, 2
0x180003f80  mov     r10d, 37h ; '7'
0x180003f86  nop     word ptr [rax+rax+00000000h]
0x180003f90  movzx   edx, byte ptr [r8]
0x180003f94  mov     eax, 30h ; '0'
0x180003f99  mov     ecx, edx
0x180003f9b  shr     ecx, 4
0x180003f9e  cmp     ecx, 9
0x180003fa1  cmova   ax, r10w
0x180003fa6  and     edx, 0Fh
0x180003fa9  add     ax, cx
0x180003fac  mov     [rbx], ax
0x180003faf  cmp     edx, 9
0x180003fb2  mov     eax, 30h ; '0'
0x180003fb7  cmova   ax, r10w
0x180003fbc  add     ax, dx
0x180003fbf  movzx   edx, byte ptr [r8+1]
0x180003fc4  mov     [rbx+2], ax
0x180003fc8  mov     ecx, edx
0x180003fca  shr     ecx, 4
0x180003fcd  mov     eax, 30h ; '0'
0x180003fd2  cmp     ecx, 9
0x180003fd5  cmova   ax, r10w
0x180003fda  and     edx, 0Fh
0x180003fdd  add     ax, cx
0x180003fe0  mov     [rbx+4], ax
0x180003fe4  cmp     edx, 9
0x180003fe7  mov     eax, 30h ; '0'
0x180003fec  cmova   ax, r10w
0x180003ff1  add     ax, dx
0x180003ff4  movzx   edx, byte ptr [r8+2]
0x180003ff9  mov     [rbx+6], ax
0x180003ffd  mov     ecx, edx
0x180003fff  shr     ecx, 4
0x180004002  mov     eax, 30h ; '0'
0x180004007  cmp     ecx, 9
0x18000400a  cmova   ax, r10w
0x18000400f  and     edx, 0Fh
0x180004012  add     ax, cx
0x180004015  mov     [rbx+8], ax
0x180004019  cmp     edx, 9
0x18000401c  mov     eax, 30h ; '0'
0x180004021  cmova   ax, r10w
0x180004026  add     ax, dx
0x180004029  movzx   edx, byte ptr [r8+3]
0x18000402e  mov     [rbx+0Ah], ax
0x180004032  mov     ecx, edx
0x180004034  shr     ecx, 4
0x180004037  mov     eax, 30h ; '0'
0x18000403c  cmp     ecx, 9
0x18000403f  cmova   ax, r10w
0x180004044  and     edx, 0Fh
0x180004047  add     ax, cx
0x18000404a  mov     [rbx+0Ch], ax
0x18000404e  cmp     edx, 9
0x180004051  mov     eax, 30h ; '0'
0x180004056  cmova   ax, r10w
0x18000405b  add     ax, dx
0x18000405e  movzx   edx, byte ptr [r8+4]
0x180004063  mov     [rbx+0Eh], ax
0x180004067  mov     ecx, edx
0x180004069  shr     ecx, 4
0x18000406c  mov     eax, 30h ; '0'
0x180004071  cmp     ecx, 9
0x180004074  cmova   ax, r10w
0x180004079  and     edx, 0Fh
0x18000407c  add     ax, cx
0x18000407f  mov     [rbx+10h], ax
0x180004083  cmp     edx, 9
0x180004086  mov     eax, 30h ; '0'
0x18000408b  cmova   ax, r10w
0x180004090  add     ax, dx
0x180004093  movzx   edx, byte ptr [r8+5]
0x180004098  mov     [rbx+12h], ax
0x18000409c  mov     ecx, edx
0x18000409e  shr     ecx, 4
0x1800040a1  mov     eax, 30h ; '0'
0x1800040a6  cmp     ecx, 9
0x1800040a9  cmova   ax, r10w
0x1800040ae  and     edx, 0Fh
0x1800040b1  add     ax, cx
0x1800040b4  mov     [rbx+14h], ax
0x1800040b8  cmp     edx, 9
0x1800040bb  mov     eax, 30h ; '0'
0x1800040c0  cmova   ax, r10w
0x1800040c5  lea     rbx, [rbx+20h]
0x1800040c9  add     ax, dx
0x1800040cc  movzx   edx, byte ptr [r8+6]
0x1800040d1  mov     [rbx-0Ah], ax
0x1800040d5  lea     r8, [r8+8]
0x1800040d9  mov     ecx, edx
0x1800040db  mov     eax, 30h ; '0'
0x1800040e0  shr     ecx, 4
0x1800040e3  cmp     ecx, 9
0x1800040e6  cmova   ax, r10w
0x1800040eb  and     edx, 0Fh
0x1800040ee  add     ax, cx
0x1800040f1  mov     [rbx-8], ax
0x1800040f5  cmp     edx, 9
0x1800040f8  mov     eax, 30h ; '0'
0x1800040fd  cmova   ax, r10w
0x180004102  add     ax, dx
0x180004105  movzx   edx, byte ptr [r8-1]
0x18000410a  mov     [rbx-6], ax
0x18000410e  mov     ecx, edx
0x180004110  shr     ecx, 4
0x180004113  mov     eax, 30h ; '0'
0x180004118  cmp     ecx, 9
0x18000411b  cmova   ax, r10w
0x180004120  and     edx, 0Fh
0x180004123  add     ax, cx
0x180004126  mov     [rbx-4], ax
0x18000412a  cmp     edx, 9
0x18000412d  mov     eax, 30h ; '0'
0x180004132  cmova   ax, r10w
0x180004137  add     ax, dx
0x18000413a  mov     [rbx-2], ax
0x18000413e  add     r9d, 0FFFFFFFFh
0x180004142  jnz     loc_180003F90
0x180004148  xor     eax, eax
0x18000414a  mov     [rbx], ax
0x18000414d  mov     rcx, [rsp+48h+var_10]
0x180004152  xor     rcx, rsp; StackCookie
0x180004155  call    __security_check_cookie
0x18000415a  mov     rbx, [rsp+48h+arg_10]
0x18000415f  add     rsp, 40h
0x180004163  pop     rdi
0x180004164  retn
0x180004165  xor     r8d, r8d
0x180004168  jmp     loc_180003F5B
```

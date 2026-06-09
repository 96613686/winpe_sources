# I_UrlCacheGetUrlFileName

- ea: `0x180002810`
- end: `0x180002a7d`
- name: `I_UrlCacheGetUrlFileName`
- size: `621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800015bc`
- `0x180002460`
- `0x180003e7c`
- `0x18001ff84`

## callees

- `0x180002810`
- `0x18001fa58`
- `0x18001fa9c`
- `0x18001fae4`
- `0x1800265b0`

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
0x180002810  mov     [rsp+arg_10], rbx
0x180002815  push    rdi
0x180002816  sub     rsp, 40h
0x18000281a  mov     rax, cs:__security_cookie
0x180002821  xor     rax, rsp
0x180002824  mov     [rsp+48h+var_10], rax
0x180002829  mov     rdi, rcx
0x18000282c  xorps   xmm0, xmm0
0x18000282f  xor     eax, eax
0x180002831  lea     rcx, [rsp+48h+phHash]; phHash
0x180002836  movups  xmmword ptr [rsp+48h+phHash], xmm0
0x18000283b  mov     [rsp+48h+var_18], rax
0x180002840  mov     rbx, rdx
0x180002843  call    CngRsa32Compat_MD5Init
0x180002848  test    rdi, rdi
0x18000284b  jz      loc_180002A75
0x180002851  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180002858  nop     dword ptr [rax+rax+00000000h]
0x180002860  inc     r8
0x180002863  cmp     word ptr [rdi+r8*2], 0
0x180002869  jnz     short loc_180002860
0x18000286b  add     r8d, r8d
0x18000286e  lea     rcx, [rsp+48h+phHash]
0x180002873  mov     rdx, rdi
0x180002876  call    CngRsa32Compat_MD5Update
0x18000287b  lea     rcx, [rsp+48h+phHash]
0x180002880  call    CngRsa32Compat_MD5Final
0x180002885  lea     r8, [rsp+48h+phHash+8]
0x18000288a  mov     r9d, 2
0x180002890  mov     r10d, 37h ; '7'
0x180002896  nop     word ptr [rax+rax+00000000h]
0x1800028a0  movzx   edx, byte ptr [r8]
0x1800028a4  mov     eax, 30h ; '0'
0x1800028a9  mov     ecx, edx
0x1800028ab  shr     ecx, 4
0x1800028ae  cmp     ecx, 9
0x1800028b1  cmova   ax, r10w
0x1800028b6  and     edx, 0Fh
0x1800028b9  add     ax, cx
0x1800028bc  mov     [rbx], ax
0x1800028bf  cmp     edx, 9
0x1800028c2  mov     eax, 30h ; '0'
0x1800028c7  cmova   ax, r10w
0x1800028cc  add     ax, dx
0x1800028cf  movzx   edx, byte ptr [r8+1]
0x1800028d4  mov     [rbx+2], ax
0x1800028d8  mov     ecx, edx
0x1800028da  shr     ecx, 4
0x1800028dd  mov     eax, 30h ; '0'
0x1800028e2  cmp     ecx, 9
0x1800028e5  cmova   ax, r10w
0x1800028ea  and     edx, 0Fh
0x1800028ed  add     ax, cx
0x1800028f0  mov     [rbx+4], ax
0x1800028f4  cmp     edx, 9
0x1800028f7  mov     eax, 30h ; '0'
0x1800028fc  cmova   ax, r10w
0x180002901  add     ax, dx
0x180002904  movzx   edx, byte ptr [r8+2]
0x180002909  mov     [rbx+6], ax
0x18000290d  mov     ecx, edx
0x18000290f  shr     ecx, 4
0x180002912  mov     eax, 30h ; '0'
0x180002917  cmp     ecx, 9
0x18000291a  cmova   ax, r10w
0x18000291f  and     edx, 0Fh
0x180002922  add     ax, cx
0x180002925  mov     [rbx+8], ax
0x180002929  cmp     edx, 9
0x18000292c  mov     eax, 30h ; '0'
0x180002931  cmova   ax, r10w
0x180002936  add     ax, dx
0x180002939  movzx   edx, byte ptr [r8+3]
0x18000293e  mov     [rbx+0Ah], ax
0x180002942  mov     ecx, edx
0x180002944  shr     ecx, 4
0x180002947  mov     eax, 30h ; '0'
0x18000294c  cmp     ecx, 9
0x18000294f  cmova   ax, r10w
0x180002954  and     edx, 0Fh
0x180002957  add     ax, cx
0x18000295a  mov     [rbx+0Ch], ax
0x18000295e  cmp     edx, 9
0x180002961  mov     eax, 30h ; '0'
0x180002966  cmova   ax, r10w
0x18000296b  add     ax, dx
0x18000296e  movzx   edx, byte ptr [r8+4]
0x180002973  mov     [rbx+0Eh], ax
0x180002977  mov     ecx, edx
0x180002979  shr     ecx, 4
0x18000297c  mov     eax, 30h ; '0'
0x180002981  cmp     ecx, 9
0x180002984  cmova   ax, r10w
0x180002989  and     edx, 0Fh
0x18000298c  add     ax, cx
0x18000298f  mov     [rbx+10h], ax
0x180002993  cmp     edx, 9
0x180002996  mov     eax, 30h ; '0'
0x18000299b  cmova   ax, r10w
0x1800029a0  add     ax, dx
0x1800029a3  movzx   edx, byte ptr [r8+5]
0x1800029a8  mov     [rbx+12h], ax
0x1800029ac  mov     ecx, edx
0x1800029ae  shr     ecx, 4
0x1800029b1  mov     eax, 30h ; '0'
0x1800029b6  cmp     ecx, 9
0x1800029b9  cmova   ax, r10w
0x1800029be  and     edx, 0Fh
0x1800029c1  add     ax, cx
0x1800029c4  mov     [rbx+14h], ax
0x1800029c8  cmp     edx, 9
0x1800029cb  mov     eax, 30h ; '0'
0x1800029d0  cmova   ax, r10w
0x1800029d5  lea     rbx, [rbx+20h]
0x1800029d9  add     ax, dx
0x1800029dc  movzx   edx, byte ptr [r8+6]
0x1800029e1  mov     [rbx-0Ah], ax
0x1800029e5  lea     r8, [r8+8]
0x1800029e9  mov     ecx, edx
0x1800029eb  mov     eax, 30h ; '0'
0x1800029f0  shr     ecx, 4
0x1800029f3  cmp     ecx, 9
0x1800029f6  cmova   ax, r10w
0x1800029fb  and     edx, 0Fh
0x1800029fe  add     ax, cx
0x180002a01  mov     [rbx-8], ax
0x180002a05  cmp     edx, 9
0x180002a08  mov     eax, 30h ; '0'
0x180002a0d  cmova   ax, r10w
0x180002a12  add     ax, dx
0x180002a15  movzx   edx, byte ptr [r8-1]
0x180002a1a  mov     [rbx-6], ax
0x180002a1e  mov     ecx, edx
0x180002a20  shr     ecx, 4
0x180002a23  mov     eax, 30h ; '0'
0x180002a28  cmp     ecx, 9
0x180002a2b  cmova   ax, r10w
0x180002a30  and     edx, 0Fh
0x180002a33  add     ax, cx
0x180002a36  mov     [rbx-4], ax
0x180002a3a  cmp     edx, 9
0x180002a3d  mov     eax, 30h ; '0'
0x180002a42  cmova   ax, r10w
0x180002a47  add     ax, dx
0x180002a4a  mov     [rbx-2], ax
0x180002a4e  add     r9d, 0FFFFFFFFh
0x180002a52  jnz     loc_1800028A0
0x180002a58  xor     eax, eax
0x180002a5a  mov     [rbx], ax
0x180002a5d  mov     rcx, [rsp+48h+var_10]
0x180002a62  xor     rcx, rsp; StackCookie
0x180002a65  call    __security_check_cookie
0x180002a6a  mov     rbx, [rsp+48h+arg_10]
0x180002a6f  add     rsp, 40h
0x180002a73  pop     rdi
0x180002a74  retn
0x180002a75  xor     r8d, r8d
0x180002a78  jmp     loc_18000286B
```

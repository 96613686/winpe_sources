# Int_FwValidateAddresses

- ea: `0x18000f520`
- end: `0x18000fbac`
- name: `Int_FwValidateAddresses`
- size: `1676`
- prototype: `__int64 __fastcall(__int64, int, int, _DWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d490`
- `0x1800150e0`
- `0x18002e7c0`
- `0x18002eff8`

## callees

- `0x18000ccd4`
- `0x18000f520`
- `0x180010ec8`
- `0x180012bb0`
- `0x180017d1c`
- `0x18002d8d4`
- `0x18002edd0`
- `0x18002f668`

## pseudocode

```c
__int64 __fastcall Int_FwValidateAddresses(__int64 a1, int a2, int a3, _DWORD *a4)
{
  _QWORD *v8; // r10
  unsigned int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rsi
  __int64 v14; // rsi
  unsigned int m; // ebx
  __int64 i; // rbp
  unsigned int v18; // r9d
  int v19; // ebx
  unsigned int v20; // eax
  bool v21; // sf
  __int64 v22; // r11
  __int64 j; // r10
  unsigned int v24; // esi
  __int64 v25; // r14
  __int64 k; // rbx
  unsigned int v27; // ebp
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned __int8 near **v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rax

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 258, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = *(_DWORD *)a1;
  if ( a2 )
  {
    if ( v9 < 0x800 && *(_DWORD *)(a1 + 4) < 0x800u )
      goto LABEL_14;
    *a4 = 1048647;
    v10 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v12 = 259;
LABEL_11:
    WPP_SF_d(v11[2], v12, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    return v10;
  }
  if ( a3 )
  {
    if ( !v9 && !*(_DWORD *)(a1 + 4) )
      goto LABEL_14;
    *a4 = 1048647;
    v10 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v12 = 260;
    goto LABEL_11;
  }
  if ( v9 >= 0x800 || *(_DWORD *)(a1 + 4) >= 0x800u )
  {
    *a4 = 1048647;
    v10 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v12 = 261;
    goto LABEL_11;
  }
LABEL_14:
  v13 = (_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( !*v13 )
    {
LABEL_16:
      *a4 = 1048640;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 262;
      goto LABEL_11;
    }
  }
  else if ( *v13 )
  {
    goto LABEL_16;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
  {
    v19 = *(_DWORD *)(8 * i + *v13 + 4);
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_(v8[2], 257, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( !v19 )
      goto LABEL_53;
    v20 = 0;
    if ( v19 >= 0 )
      goto LABEL_53;
    do
    {
      if ( v20 >= 0x20 )
        break;
      ++v20;
      v21 = (v19 & 0x40000000) != 0;
      v19 *= 2;
    }
    while ( v21 );
    if ( v19 )
    {
LABEL_53:
      v10 = 87;
      *a4 = 1048645;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 263;
      goto LABEL_11;
    }
    if ( a2 && (unsigned int)Int_FwIPV4SubnetContainsMulticast((struct _tag_FW_IPV4_SUBNET *)(8 * i + *v13)) )
    {
      *a4 = 1048652;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 264;
      goto LABEL_11;
    }
  }
  v18 = *(_DWORD *)(a1 + 40);
  if ( v18 )
  {
    v22 = *(_QWORD *)(a1 + 48);
    if ( !v22 )
    {
LABEL_32:
      *a4 = 1048641;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 265;
      goto LABEL_11;
    }
  }
  else
  {
    if ( *(_QWORD *)(a1 + 48) )
      goto LABEL_32;
    v22 = *(_QWORD *)(a1 + 48);
  }
  for ( j = 0; (unsigned int)j < v18; j = (unsigned int)(j + 1) )
  {
    v28 = v22 + 20 * j;
    v29 = *(_QWORD *)v28 - (_QWORD)g_IPV6_LOOPBACK_ADDRESS;
    if ( !v29 )
      v29 = *(_QWORD *)(v28 + 8) - qword_18003C240;
    if ( !v29 )
    {
      *a4 = 1048650;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 266;
      goto LABEL_11;
    }
    if ( (unsigned int)(*(_DWORD *)(v28 + 16) - 1) > 0x7F )
    {
      *a4 = 1048646;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 267;
      goto LABEL_11;
    }
    if ( a2 && (unsigned int)Int_FwIPV6SubnetContainsMulticast((struct _tag_FW_IPV6_SUBNET *)v28) )
    {
      *a4 = 1048650;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v12 = 268;
      goto LABEL_11;
    }
  }
  v24 = *(_DWORD *)(a1 + 24);
  if ( v24 )
  {
    v25 = *(_QWORD *)(a1 + 32);
    if ( v25 )
      goto LABEL_57;
LABEL_77:
    *a4 = 1048642;
    v10 = 87;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v12 = 269;
    goto LABEL_11;
  }
  if ( *(_QWORD *)(a1 + 32) )
    goto LABEL_77;
  v25 = *(_QWORD *)(a1 + 32);
LABEL_57:
  for ( k = 0; (unsigned int)k < v24; k = (unsigned int)(k + 1) )
  {
    if ( *(_DWORD *)(v25 + 8 * k) > *(_DWORD *)(v25 + 8 * k + 4) )
    {
      *a4 = 1048644;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 270;
        goto LABEL_11;
      }
      return v10;
    }
    if ( a2 && (unsigned int)Int_FwIPV4RangeContainsMulticast() )
    {
      *a4 = 1048652;
      v10 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 271;
        goto LABEL_11;
      }
      return v10;
    }
  }
  v27 = *(_DWORD *)(a1 + 56);
  if ( v27 )
  {
    v14 = *(_QWORD *)(a1 + 64);
    if ( v14 )
      goto LABEL_24;
  }
  else if ( !*(_QWORD *)(a1 + 64) )
  {
    v14 = *(_QWORD *)(a1 + 64);
LABEL_24:
    for ( m = 0; ; ++m )
    {
      v10 = 0;
      if ( m >= v27 )
        break;
      v30 = (unsigned __int8 near **)(v14 + 32LL * m);
      v31 = *v30 - g_IPV6_LOOPBACK_ADDRESS;
      if ( *v30 == g_IPV6_LOOPBACK_ADDRESS )
        v31 = (__int64)&v30[1][-qword_18003C240];
      if ( !v31 )
      {
        *a4 = 1048650;
        v10 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 273;
          goto LABEL_11;
        }
        return v10;
      }
      v32 = v30[2] - g_IPV6_LOOPBACK_ADDRESS;
      if ( !v32 )
        v32 = (__int64)&v30[3][-qword_18003C240];
      if ( !v32 )
      {
        *a4 = 1048650;
        v10 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 274;
          goto LABEL_11;
        }
        return v10;
      }
      if ( memcmp_0((const void *)(v14 + 32LL * m), v30 + 2, 0x10u) > 0 )
      {
        *a4 = 1048644;
        v10 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 275;
          goto LABEL_11;
        }
        return v10;
      }
      if ( a2 && (unsigned int)Int_FwIPV6RangeContainsMulticast(v14 + 32LL * m) )
      {
        *a4 = 1048650;
        v10 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 276;
          goto LABEL_11;
        }
        return v10;
      }
    }
    return v10;
  }
  *a4 = 1048643;
  v10 = 87;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 272;
    goto LABEL_11;
  }
  return v10;
}

```

## disassembly

```asm
0x18000f520  push    rbx
0x18000f522  push    rdi
0x18000f523  push    r12
0x18000f525  push    r13
0x18000f527  push    r15
0x18000f529  sub     rsp, 20h
0x18000f52d  mov     r12, r9
0x18000f530  mov     ebx, r8d
0x18000f533  mov     r15d, edx
0x18000f536  mov     rdi, rcx
0x18000f539  mov     r10, cs:WPP_GLOBAL_Control
0x18000f540  lea     r13, WPP_GLOBAL_Control
0x18000f547  cmp     r10, r13
0x18000f54a  jz      short loc_18000F557
0x18000f54c  test    byte ptr [r10+1Ch], 8
0x18000f551  jnz     loc_18000F99F
0x18000f557  mov     eax, [rdi]
0x18000f559  mov     [rsp+48h+arg_0], rbp
0x18000f55e  mov     [rsp+48h+arg_8], rsi
0x18000f563  mov     [rsp+48h+arg_10], r14
0x18000f568  test    r15d, r15d
0x18000f56b  jnz     loc_18000F618
0x18000f571  test    ebx, ebx
0x18000f573  jnz     short loc_18000F5C9
0x18000f575  cmp     eax, 800h
0x18000f57a  jnb     short loc_18000F585
0x18000f57c  cmp     dword ptr [rdi+4], 800h
0x18000f583  jb      short loc_18000F5DA
0x18000f585  mov     dword ptr [r12], 100047h
0x18000f58d  mov     edi, 57h ; 'W'
0x18000f592  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f599  cmp     rcx, r13
0x18000f59c  jz      loc_18000F665
0x18000f5a2  test    byte ptr [rcx+1Ch], 1
0x18000f5a6  jz      loc_18000F665
0x18000f5ac  mov     edx, 105h
0x18000f5b1  mov     rcx, [rcx+10h]
0x18000f5b5  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000f5bc  mov     r9d, edi
0x18000f5bf  call    WPP_SF_d
0x18000f5c4  jmp     loc_18000F665
0x18000f5c9  test    eax, eax
0x18000f5cb  jnz     loc_18000F9C0
0x18000f5d1  cmp     [rdi+4], eax
0x18000f5d4  jnz     loc_18000F9C0
0x18000f5da  cmp     dword ptr [rdi+8], 0
0x18000f5de  lea     rsi, [rdi+10h]
0x18000f5e2  jnz     loc_18000F683
0x18000f5e8  cmp     qword ptr [rsi], 0
0x18000f5ec  jz      loc_18000F68D
0x18000f5f2  mov     dword ptr [r12], 100040h
0x18000f5fa  mov     edi, 57h ; 'W'
0x18000f5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f606  cmp     rcx, r13
0x18000f609  jz      short loc_18000F665
0x18000f60b  test    byte ptr [rcx+1Ch], 1
0x18000f60f  jz      short loc_18000F665
0x18000f611  mov     edx, 106h
0x18000f616  jmp     short loc_18000F5B1
0x18000f618  cmp     eax, 800h
0x18000f61d  jb      loc_18000F6D6
0x18000f623  mov     dword ptr [r12], 100047h
0x18000f62b  mov     edi, 57h ; 'W'
0x18000f630  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f637  cmp     rcx, r13
0x18000f63a  jz      short loc_18000F665
0x18000f63c  test    byte ptr [rcx+1Ch], 1
0x18000f640  jz      short loc_18000F665
0x18000f642  mov     edx, 103h
0x18000f647  jmp     loc_18000F5B1
0x18000f64c  mov     rsi, [rdi+40h]
0x18000f650  test    rsi, rsi
0x18000f653  jz      loc_18000FAD8
0x18000f659  xor     ebx, ebx
0x18000f65b  xor     edi, edi
0x18000f65d  cmp     ebx, ebp
0x18000f65f  jb      loc_18000F812
0x18000f665  mov     r14, [rsp+48h+arg_10]
0x18000f66a  mov     eax, edi
0x18000f66c  mov     rsi, [rsp+48h+arg_8]
0x18000f671  mov     rbp, [rsp+48h+arg_0]
0x18000f676  add     rsp, 20h
0x18000f67a  pop     r15
0x18000f67c  pop     r13
0x18000f67e  pop     r12
0x18000f680  pop     rdi
0x18000f681  pop     rbx
0x18000f682  retn
0x18000f683  cmp     qword ptr [rsi], 0
0x18000f687  jz      loc_18000F5F2
0x18000f68d  xor     ebp, ebp
0x18000f68f  nop
0x18000f690  cmp     ebp, [rdi+8]
0x18000f693  jb      short loc_18000F6E8
0x18000f695  mov     r9d, [rdi+28h]
0x18000f699  test    r9d, r9d
0x18000f69c  jnz     loc_18000F731
0x18000f6a2  cmp     qword ptr [rdi+30h], 0
0x18000f6a7  jz      loc_18000F9F1
0x18000f6ad  mov     dword ptr [r12], 100041h
0x18000f6b5  mov     edi, 57h ; 'W'
0x18000f6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6c1  cmp     rcx, r13
0x18000f6c4  jz      short loc_18000F665
0x18000f6c6  test    byte ptr [rcx+1Ch], 1
0x18000f6ca  jz      short loc_18000F665
0x18000f6cc  mov     edx, 109h
0x18000f6d1  jmp     loc_18000F5B1
0x18000f6d6  cmp     dword ptr [rdi+4], 800h
0x18000f6dd  jb      loc_18000F5DA
0x18000f6e3  jmp     loc_18000F623
0x18000f6e8  mov     rax, [rsi]
0x18000f6eb  lea     r14, ds:0[rbp*8]
0x18000f6f3  mov     ebx, [r14+rax+4]
0x18000f6f8  cmp     r10, r13
0x18000f6fb  jz      short loc_18000F708
0x18000f6fd  test    byte ptr [r10+1Ch], 8
0x18000f702  jnz     loc_18000F8B7
0x18000f708  test    ebx, ebx
0x18000f70a  jz      short loc_18000F762
0x18000f70c  xor     eax, eax
0x18000f70e  test    ebx, ebx
0x18000f710  jns     short loc_18000F762
0x18000f712  cmp     eax, 20h ; ' '
0x18000f715  jnb     short loc_18000F71D
0x18000f717  inc     eax
0x18000f719  add     ebx, ebx
0x18000f71b  js      short loc_18000F712
0x18000f71d  test    ebx, ebx
0x18000f71f  jnz     short loc_18000F762
0x18000f721  test    r15d, r15d
0x18000f724  jnz     loc_18000F909
0x18000f72a  inc     ebp
0x18000f72c  jmp     loc_18000F690
0x18000f731  mov     r11, [rdi+30h]
0x18000f735  test    r11, r11
0x18000f738  jz      loc_18000F6AD
0x18000f73e  xor     r10d, r10d
0x18000f741  cmp     r10d, r9d
0x18000f744  jb      loc_18000F7CA
0x18000f74a  mov     esi, [rdi+18h]
0x18000f74d  test    esi, esi
0x18000f74f  jnz     short loc_18000F794
0x18000f751  cmp     qword ptr [rdi+20h], 0
0x18000f756  jnz     loc_18000F886
0x18000f75c  mov     r14, [rdi+20h]
0x18000f760  jmp     short loc_18000F7A1
0x18000f762  mov     eax, 100045h
0x18000f767  mov     edi, 57h ; 'W'
0x18000f76c  mov     [r12], eax
0x18000f770  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f777  cmp     rcx, r13
0x18000f77a  jz      loc_18000F665
0x18000f780  test    byte ptr [rcx+1Ch], 1
0x18000f784  jz      loc_18000F665
0x18000f78a  mov     edx, 107h
0x18000f78f  jmp     loc_18000F5B1
0x18000f794  mov     r14, [rdi+20h]
0x18000f798  test    r14, r14
0x18000f79b  jz      loc_18000F886
0x18000f7a1  xor     ebx, ebx
0x18000f7a3  cmp     ebx, esi
0x18000f7a5  jb      loc_18000F97E
0x18000f7ab  mov     ebp, [rdi+38h]
0x18000f7ae  test    ebp, ebp
0x18000f7b0  jnz     loc_18000F64C
0x18000f7b6  cmp     qword ptr [rdi+40h], 0
0x18000f7bb  jnz     loc_18000FAD8
0x18000f7c1  mov     rsi, [rdi+40h]
0x18000f7c5  jmp     loc_18000F659
0x18000f7ca  lea     rcx, [r10+r10*4]
0x18000f7ce  mov     rax, [r11+rcx*4]
0x18000f7d2  lea     rcx, [r11+rcx*4]; struct _tag_FW_IPV6_SUBNET *
0x18000f7d6  sub     rax, cs:?g_IPV6_LOOPBACK_ADDRESS@@3PAEA; uchar near * g_IPV6_LOOPBACK_ADDRESS
0x18000f7dd  jnz     short loc_18000F7EA
0x18000f7df  mov     rax, [rcx+8]
0x18000f7e3  sub     rax, cs:qword_18003C240
0x18000f7ea  test    rax, rax
0x18000f7ed  jz      loc_18000F8D8
0x18000f7f3  mov     eax, [rcx+10h]
0x18000f7f6  dec     eax
0x18000f7f8  cmp     eax, 7Fh
0x18000f7fb  ja      loc_18000FA38
0x18000f801  test    r15d, r15d
0x18000f804  jnz     loc_18000F9FA
0x18000f80a  inc     r10d
0x18000f80d  jmp     loc_18000F741
0x18000f812  mov     edi, ebx
0x18000f814  shl     rdi, 5
0x18000f818  add     rdi, rsi
0x18000f81b  mov     rax, [rdi]
0x18000f81e  sub     rax, cs:?g_IPV6_LOOPBACK_ADDRESS@@3PAEA; uchar near * g_IPV6_LOOPBACK_ADDRESS
0x18000f825  jnz     short loc_18000F832
0x18000f827  mov     rax, [rdi+8]
0x18000f82b  sub     rax, cs:qword_18003C240
0x18000f832  test    rax, rax
0x18000f835  jz      loc_18000F94D
0x18000f83b  mov     rax, [rdi+10h]
0x18000f83f  lea     rdx, [rdi+10h]; Buf2
0x18000f843  sub     rax, cs:?g_IPV6_LOOPBACK_ADDRESS@@3PAEA; uchar near * g_IPV6_LOOPBACK_ADDRESS
0x18000f84a  jnz     short loc_18000F857
0x18000f84c  mov     rax, [rdx+8]
0x18000f850  sub     rax, cs:qword_18003C240
0x18000f857  test    rax, rax
0x18000f85a  jz      loc_18000FB7B
0x18000f860  mov     r8d, 10h; Size
0x18000f866  mov     rcx, rdi; Buf1
0x18000f869  call    memcmp_0
0x18000f86e  test    eax, eax
0x18000f870  jg      loc_18000FB4A
0x18000f876  test    r15d, r15d
0x18000f879  jnz     loc_18000FB09
0x18000f87f  inc     ebx
0x18000f881  jmp     loc_18000F65B
0x18000f886  mov     dword ptr [r12], 100042h
0x18000f88e  mov     edi, 57h ; 'W'
0x18000f893  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f89a  cmp     rcx, r13
0x18000f89d  jz      loc_18000F665
0x18000f8a3  test    byte ptr [rcx+1Ch], 1
0x18000f8a7  jz      loc_18000F665
0x18000f8ad  mov     edx, 10Dh
0x18000f8b2  jmp     loc_18000F5B1
0x18000f8b7  mov     rcx, [r10+10h]
0x18000f8bb  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000f8c2  mov     edx, 101h
0x18000f8c7  call    WPP_SF_
0x18000f8cc  mov     r10, cs:WPP_GLOBAL_Control
0x18000f8d3  jmp     loc_18000F708
0x18000f8d8  mov     dword ptr [r12], 10004Ah
0x18000f8e0  mov     edi, 57h ; 'W'
0x18000f8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8ec  cmp     rcx, r13
0x18000f8ef  jz      loc_18000F665
0x18000f8f5  test    byte ptr [rcx+1Ch], 1
0x18000f8f9  jz      loc_18000F665
0x18000f8ff  mov     edx, 10Ah
0x18000f904  jmp     loc_18000F5B1
0x18000f909  mov     rcx, [rsi]
0x18000f90c  add     rcx, r14; struct _tag_FW_IPV4_SUBNET *
0x18000f90f  call    ?Int_FwIPV4SubnetContainsMulticast@@YAHPEAU_tag_FW_IPV4_SUBNET@@@Z; Int_FwIPV4SubnetContainsMulticast(_tag_FW_IPV4_SUBNET *)
0x18000f914  test    eax, eax
0x18000f916  jz      loc_18000F72A
0x18000f91c  mov     dword ptr [r12], 10004Ch
0x18000f924  mov     edi, 57h ; 'W'
0x18000f929  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f930  cmp     rcx, r13
0x18000f933  jz      loc_18000F665
0x18000f939  test    byte ptr [rcx+1Ch], 1
0x18000f93d  jz      loc_18000F665
0x18000f943  mov     edx, 108h
0x18000f948  jmp     loc_18000F5B1
0x18000f94d  mov     dword ptr [r12], 10004Ah
0x18000f955  mov     edi, 57h ; 'W'
0x18000f95a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f961  cmp     rcx, r13
0x18000f964  jz      loc_18000F665
0x18000f96a  test    byte ptr [rcx+1Ch], 1
0x18000f96e  jz      loc_18000F665
0x18000f974  mov     edx, 111h
0x18000f979  jmp     loc_18000F5B1
0x18000f97e  mov     eax, [r14+rbx*8+4]
0x18000f983  lea     rcx, [r14+rbx*8]
0x18000f987  cmp     [rcx], eax
0x18000f989  ja      loc_18000FAA7
0x18000f98f  test    r15d, r15d
0x18000f992  jnz     loc_18000FA69
0x18000f998  inc     ebx
0x18000f99a  jmp     loc_18000F7A3
0x18000f99f  mov     rcx, [r10+10h]
0x18000f9a3  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000f9aa  mov     edx, 102h
0x18000f9af  call    WPP_SF_
0x18000f9b4  mov     r10, cs:WPP_GLOBAL_Control
0x18000f9bb  jmp     loc_18000F557
0x18000f9c0  mov     dword ptr [r12], 100047h
0x18000f9c8  mov     edi, 57h ; 'W'
0x18000f9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9d4  cmp     rcx, r13
0x18000f9d7  jz      loc_18000F665
0x18000f9dd  test    byte ptr [rcx+1Ch], 1
0x18000f9e1  jz      loc_18000F665
0x18000f9e7  mov     edx, 104h
0x18000f9ec  jmp     loc_18000F5B1
0x18000f9f1  mov     r11, [rdi+30h]
0x18000f9f5  jmp     loc_18000F73E
0x18000f9fa  call    ?Int_FwIPV6SubnetContainsMulticast@@YAHPEAU_tag_FW_IPV6_SUBNET@@@Z; Int_FwIPV6SubnetContainsMulticast(_tag_FW_IPV6_SUBNET *)
0x18000f9ff  test    eax, eax
0x18000fa01  jz      loc_18000F80A
0x18000fa07  mov     dword ptr [r12], 10004Ah
0x18000fa0f  mov     edi, 57h ; 'W'
0x18000fa14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa1b  cmp     rcx, r13
0x18000fa1e  jz      loc_18000F665
0x18000fa24  test    byte ptr [rcx+1Ch], 1
0x18000fa28  jz      loc_18000F665
0x18000fa2e  mov     edx, 10Ch
0x18000fa33  jmp     loc_18000F5B1
0x18000fa38  mov     dword ptr [r12], 100046h
0x18000fa40  mov     edi, 57h ; 'W'
  ... truncated ...
```

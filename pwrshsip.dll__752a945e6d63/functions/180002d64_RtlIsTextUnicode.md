# RtlIsTextUnicode

- ea: `0x180002d64`
- end: `0x1800032e1`
- name: `RtlIsTextUnicode`
- size: `1405`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ab0`

## callees

- `0x180002d64`

## pseudocode

```c
bool __fastcall RtlIsTextUnicode(__int64 a1, unsigned int a2, int *a3)
{
  unsigned int v3; // r9d
  unsigned int v4; // eax
  unsigned int v5; // edx
  int *v6; // r11
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // edi
  unsigned int v11; // ebp
  unsigned int v12; // r14d
  unsigned int v13; // r13d
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  unsigned int v16; // r10d
  int v17; // esi
  int v18; // r11d
  int v19; // r15d
  int v20; // r9d
  __int64 v21; // r8
  unsigned int v22; // r10d
  unsigned int v23; // r8d
  unsigned int v24; // r10d
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // ebp
  unsigned int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  int v32; // r14d
  unsigned int v33; // r10d
  unsigned int v34; // edi
  unsigned int v35; // eax
  __int16 v36; // dx
  unsigned int v37; // eax
  unsigned __int64 v38; // rax
  int v39; // ecx
  int v40; // edx
  int v41; // ecx
  int v42; // r8d
  int v43; // eax
  int v44; // ecx
  int v46; // [rsp+0h] [rbp-98h]
  int v47; // [rsp+4h] [rbp-94h]
  int v48; // [rsp+8h] [rbp-90h]
  int v49; // [rsp+Ch] [rbp-8Ch]
  int v50; // [rsp+10h] [rbp-88h]
  int v51; // [rsp+14h] [rbp-84h]
  int v52; // [rsp+18h] [rbp-80h]
  int v53; // [rsp+1Ch] [rbp-7Ch]
  int v54; // [rsp+20h] [rbp-78h]
  int v55; // [rsp+24h] [rbp-74h]
  int v56; // [rsp+28h] [rbp-70h]
  unsigned int v57; // [rsp+2Ch] [rbp-6Ch]
  unsigned int v58; // [rsp+30h] [rbp-68h]
  unsigned int v59; // [rsp+34h] [rbp-64h]
  unsigned int v60; // [rsp+40h] [rbp-58h]
  int v61; // [rsp+A0h] [rbp+8h]
  int v64; // [rsp+B8h] [rbp+20h]

  v3 = a2;
  v60 = a2 >> 1;
  v5 = a2 >> 1;
  v4 = v5;
  v6 = a3;
  if ( v5 > 0x100 )
    v5 = 256;
  v8 = 0;
  if ( v3 < 2 || v3 == 2 && *(_WORD *)a1 && !*(_BYTE *)(a1 + 1) )
  {
    if ( v6 )
      *v6 = 5;
    return 0;
  }
  v49 = 0;
  v9 = 0;
  v61 = 0;
  v10 = 0;
  v48 = 0;
  v11 = 0;
  v47 = 0;
  v12 = 0;
  v64 = 0;
  v13 = 0;
  v46 = 0;
  v14 = 0;
  v56 = 0;
  v15 = 0;
  v55 = 0;
  v52 = 0;
  v50 = 0;
  v51 = 0;
  v53 = 0;
  v54 = 0;
  v58 = 0;
  v57 = 0;
  if ( v3 > 2 && v4 <= 0x100 && (v3 & 1) == 0 )
  {
    if ( (*(_WORD *)(a1 + 2LL * (v5 - 1)) & 0xFF00) == 0 )
      --v5;
    v9 = 0;
    v8 = 0;
  }
  v59 = 0;
  v16 = 0;
  v17 = 3;
  if ( v5 )
  {
    v18 = 0;
    v19 = 0;
    v20 = 0;
    do
    {
      v21 = v16;
      v22 = *(unsigned __int16 *)(a1 + 2LL * v16);
      if ( v22 > 0xD00 )
      {
        if ( v22 == 0x2000 )
        {
          ++v51;
        }
        else if ( v22 != 8232 && v22 != 8233 )
        {
          if ( v22 == 12288 )
          {
            ++v46;
          }
          else if ( v22 != 65279 )
          {
            if ( v22 == 65534 )
            {
              ++v55;
            }
            else if ( v22 == 0xFFFF )
            {
              ++v56;
            }
          }
        }
      }
      else if ( v22 == 3328 )
      {
        v61 = v9 + 1;
      }
      else if ( v22 )
      {
        switch ( v22 )
        {
          case 9u:
            ++v20;
            break;
          case 0xAu:
            ++v19;
            break;
          case 0xDu:
            ++v18;
            break;
          case 0x20u:
            ++v64;
            break;
          case 0x900u:
            ++v50;
            break;
          case 0xA00u:
            ++v52;
            break;
          case 0xA0Du:
            ++v54;
            break;
        }
      }
      else
      {
        ++v53;
      }
      v23 = *(unsigned __int8 *)(a1 + 2 * v21);
      v24 = v22 >> 8;
      if ( (_BYTE)v23 == 13 && v11 == 10 || (_BYTE)v23 == 10 && v11 == 13 )
        ++v15;
      v25 = v24;
      v10 += ((_BYTE)v23 == 0) + (v24 == 0);
      v26 = v11;
      if ( v11 >= v24 )
      {
        v25 = v11;
        v26 = v24;
      }
      v27 = v58;
      v12 += v25 - v26;
      v58 = v23;
      v28 = v27;
      v29 = v23;
      if ( v27 >= v23 )
      {
        v29 = v27;
        v28 = v23;
      }
      v30 = v29 - v28;
      v11 = v24;
      v9 = v61;
      v13 += v30;
      v31 = v24;
      v16 = v59 + 1;
      v59 = v16;
    }
    while ( v16 < v5 );
    v47 = v20;
    v3 = a2;
    v48 = v19;
    v14 = 0;
    v49 = v18;
    v6 = a3;
    v57 = v12;
    if ( v23 == 13 && v31 == 10 || v23 == 10 && v11 == 13 )
      ++v15;
    v8 = 0;
  }
  v32 = v10 - 1;
  if ( v11 )
    v32 = v10;
  v33 = 512;
  v34 = v15 + 1;
  if ( v11 != 26 )
    v34 = v15;
  if ( v3 <= 0x200 )
    v33 = v3;
  if ( NlsMbCodePageTag )
  {
    if ( v33 )
    {
      do
      {
        v35 = v14 + 1;
        v36 = *((_WORD *)&NlsLeadByteInfoTable + *(unsigned __int8 *)(v8 + a1));
        if ( !v36 )
          v35 = v14;
        v14 = v35;
        v37 = v8 + 1;
        if ( !v36 )
          v37 = v8;
        v8 = v37 + 1;
      }
      while ( v37 + 1 < v33 );
    }
    v8 = 0;
  }
  if ( v13 >= 0x7F )
  {
    if ( !v57 )
      goto LABEL_82;
    v8 = 0;
  }
  else if ( !v57 )
  {
    v8 = 1;
    goto LABEL_82;
  }
  if ( !v13 )
    v8 = 16;
LABEL_82:
  if ( NlsMbCodePageTag && v14 && v6 && (*v6 & 0x400) != 0 )
  {
    if ( v60 <= 0x100 )
      v38 = (unsigned __int64)v3 >> 2;
    else
      LODWORD(v38) = 128;
    if ( v14 >= ((int)v38 - 1) / 3u )
      v17 = (v14 < 2 * ((int)v38 - 1) / 3u) + 1;
    v8 |= 0x400u;
  }
  v39 = v8 | 2;
  if ( v17 * v57 >= v13 )
    v39 = v8;
  v40 = v39 | 0x20;
  if ( v17 * v13 >= v57 )
    v40 = v39;
  v41 = v40 | 4;
  if ( !(v49 + v48 + v47 + v46 + v64) )
    v41 = v40;
  v42 = v41 | 0x40;
  if ( !(v61 + v52 + v51 + v50) )
    v42 = v41;
  if ( v56 + v55 + v54 + v53 || v34 && v34 >= v33 / 0x28 )
    v42 |= 0x100u;
  v43 = v42 | 0x200;
  if ( (v3 & 1) == 0 )
    v43 = v42;
  v44 = v43 | 0x1000;
  if ( !v32 )
    v44 = v43;
  if ( *(_WORD *)a1 == 0xFEFF )
  {
    v44 |= 8u;
  }
  else if ( *(_WORD *)a1 == 0xFFFE )
  {
    v44 |= 0x80u;
  }
  if ( v6 )
  {
    v44 &= *v6;
    *v6 = v44;
  }
  return (v44 & 0xB08) == 8 || (v44 & 0xF0) == 0 && (v44 & 0xF00) == 0 && (v44 & 0xF00F) != 0;
}

```

## disassembly

```asm
0x180002d64  mov     [rsp+arg_10], r8
0x180002d69  mov     [rsp+arg_8], edx
0x180002d6d  push    rbx
0x180002d6e  push    rbp
0x180002d6f  push    rsi
0x180002d70  push    rdi
0x180002d71  push    r12
0x180002d73  push    r13
0x180002d75  push    r14
0x180002d77  push    r15
0x180002d79  sub     rsp, 58h
0x180002d7d  mov     eax, edx
0x180002d7f  mov     r9d, edx
0x180002d82  shr     eax, 1
0x180002d84  mov     r10d, 100h
0x180002d8a  cmp     eax, r10d
0x180002d8d  mov     qword ptr [rsp+98h+var_58], rax
0x180002d92  mov     edx, eax
0x180002d94  mov     r11, r8
0x180002d97  cmova   edx, r10d
0x180002d9b  mov     r12, rcx
0x180002d9e  xor     r8d, r8d
0x180002da1  cmp     r9d, 2
0x180002da5  jb      loc_1800032C2
0x180002dab  jnz     short loc_180002DBD
0x180002dad  cmp     [rcx], r8w
0x180002db1  jz      short loc_180002DBD
0x180002db3  cmp     [rcx+1], r8b
0x180002db7  jz      loc_1800032C2
0x180002dbd  mov     [rsp+98h+var_8C], r8d
0x180002dc2  mov     ecx, r8d
0x180002dc5  mov     [rsp+98h+arg_0], ecx
0x180002dcc  mov     edi, r8d
0x180002dcf  mov     [rsp+98h+var_90], r8d
0x180002dd4  mov     ebp, r8d
0x180002dd7  mov     [rsp+98h+var_94], r8d
0x180002ddc  mov     r14d, r8d
0x180002ddf  mov     [rsp+98h+arg_18], r8d
0x180002de7  mov     r13d, r8d
0x180002dea  mov     [rsp+98h+var_98], r8d
0x180002dee  mov     r15d, r8d
0x180002df1  mov     [rsp+98h+var_70], r8d
0x180002df6  mov     ebx, r8d
0x180002df9  mov     [rsp+98h+var_74], r8d
0x180002dfe  mov     [rsp+98h+var_80], r8d
0x180002e03  mov     [rsp+98h+var_88], r8d
0x180002e08  mov     [rsp+98h+var_84], r8d
0x180002e0d  mov     [rsp+98h+var_7C], r8d
0x180002e12  mov     [rsp+98h+var_78], r8d
0x180002e17  mov     [rsp+98h+var_68], r8d
0x180002e1c  mov     [rsp+98h+var_6C], r8d
0x180002e21  mov     [rsp+98h+var_60], r8d
0x180002e26  cmp     r9d, 2
0x180002e2a  jbe     short loc_180002E4D
0x180002e2c  cmp     eax, r10d
0x180002e2f  ja      short loc_180002E4D
0x180002e31  test    r9b, 1
0x180002e35  jnz     short loc_180002E4D
0x180002e37  lea     ecx, [rdx-1]
0x180002e3a  mov     r8d, 0FF00h
0x180002e40  test    [r12+rcx*2], r8w
0x180002e45  cmovz   edx, ecx
0x180002e48  mov     ecx, ebx
0x180002e4a  xor     r8d, r8d
0x180002e4d  mov     [rsp+98h+var_64], r8d
0x180002e52  mov     r10d, r8d
0x180002e55  mov     esi, 3
0x180002e5a  test    edx, edx
0x180002e5c  jz      loc_1800030E7
0x180002e62  mov     r11d, ebx
0x180002e65  mov     r15d, ebx
0x180002e68  mov     r9d, ebx
0x180002e6b  mov     r8d, r10d
0x180002e6e  movzx   r10d, word ptr [r12+r8*2]
0x180002e73  cmp     r10d, 0D00h
0x180002e7a  ja      short loc_180002EED
0x180002e7c  jz      short loc_180002EE2
0x180002e7e  mov     ecx, r10d
0x180002e81  test    r10d, r10d
0x180002e84  jz      short loc_180002EDC
0x180002e86  sub     ecx, 9
0x180002e89  jz      short loc_180002ED7
0x180002e8b  sub     ecx, 1
0x180002e8e  jz      short loc_180002ED2
0x180002e90  sub     ecx, esi
0x180002e92  jz      short loc_180002ECD
0x180002e94  sub     ecx, 13h
0x180002e97  jz      short loc_180002EC4
0x180002e99  sub     ecx, 8E0h
0x180002e9f  jz      short loc_180002EBE
0x180002ea1  sub     ecx, 100h
0x180002ea7  jz      short loc_180002EB8
0x180002ea9  cmp     ecx, 0Dh
0x180002eac  jnz     loc_180002F34
0x180002eb2  inc     [rsp+98h+var_78]
0x180002eb6  jmp     short loc_180002F34
0x180002eb8  inc     [rsp+98h+var_80]
0x180002ebc  jmp     short loc_180002F34
0x180002ebe  inc     [rsp+98h+var_88]
0x180002ec2  jmp     short loc_180002F34
0x180002ec4  inc     [rsp+98h+arg_18]
0x180002ecb  jmp     short loc_180002F34
0x180002ecd  inc     r11d
0x180002ed0  jmp     short loc_180002F34
0x180002ed2  inc     r15d
0x180002ed5  jmp     short loc_180002F34
0x180002ed7  inc     r9d
0x180002eda  jmp     short loc_180002F34
0x180002edc  inc     [rsp+98h+var_7C]
0x180002ee0  jmp     short loc_180002F34
0x180002ee2  inc     ecx
0x180002ee4  mov     [rsp+98h+arg_0], ecx
0x180002eeb  jmp     short loc_180002F34
0x180002eed  mov     ecx, r10d
0x180002ef0  sub     ecx, 2000h
0x180002ef6  jz      short loc_180002F30
0x180002ef8  sub     ecx, 28h ; '('
0x180002efb  jz      short loc_180002F34
0x180002efd  sub     ecx, 1
0x180002f00  jz      short loc_180002F34
0x180002f02  sub     ecx, 0FD7h
0x180002f08  jz      short loc_180002F2B
0x180002f0a  sub     ecx, 0CEFFh
0x180002f10  jz      short loc_180002F34
0x180002f12  sub     ecx, 0FFh
0x180002f18  jz      short loc_180002F25
0x180002f1a  cmp     ecx, 1
0x180002f1d  jnz     short loc_180002F34
0x180002f1f  inc     [rsp+98h+var_70]
0x180002f23  jmp     short loc_180002F34
0x180002f25  inc     [rsp+98h+var_74]
0x180002f29  jmp     short loc_180002F34
0x180002f2b  inc     [rsp+98h+var_98]
0x180002f2e  jmp     short loc_180002F34
0x180002f30  inc     [rsp+98h+var_84]
0x180002f34  movzx   r8d, byte ptr [r12+r8*2]
0x180002f39  shr     r10d, 8
0x180002f3d  cmp     r8b, 0Dh
0x180002f41  jnz     short loc_180002F48
0x180002f43  cmp     ebp, 0Ah
0x180002f46  jz      short loc_180002F53
0x180002f48  cmp     r8b, 0Ah
0x180002f4c  jnz     short loc_180002F55
0x180002f4e  cmp     ebp, 0Dh
0x180002f51  jnz     short loc_180002F55
0x180002f53  inc     ebx
0x180002f55  xor     ecx, ecx
0x180002f57  test    r8b, r8b
0x180002f5a  setz    cl
0x180002f5d  xor     eax, eax
0x180002f5f  test    r10d, r10d
0x180002f62  setz    al
0x180002f65  add     edi, eax
0x180002f67  mov     eax, r10d
0x180002f6a  add     edi, ecx
0x180002f6c  mov     ecx, ebp
0x180002f6e  cmp     ebp, r10d
0x180002f71  cmovnb  eax, ebp
0x180002f74  cmovnb  ecx, r10d
0x180002f78  mov     ebp, [rsp+98h+var_68]
0x180002f7c  sub     eax, ecx
0x180002f7e  add     r14d, eax
0x180002f81  mov     [rsp+98h+var_68], r8d
0x180002f86  cmp     ebp, r8d
0x180002f89  mov     ecx, ebp
0x180002f8b  mov     eax, r8d
0x180002f8e  cmovnb  eax, ebp
0x180002f91  cmovnb  ecx, r8d
0x180002f95  sub     eax, ecx
0x180002f97  mov     ebp, r10d
0x180002f9a  mov     ecx, [rsp+98h+arg_0]
0x180002fa1  add     r13d, eax
0x180002fa4  mov     eax, r10d
0x180002fa7  mov     r10d, [rsp+98h+var_64]
0x180002fac  inc     r10d
0x180002faf  mov     [rsp+98h+var_64], r10d
0x180002fb4  cmp     r10d, edx
0x180002fb7  jb      loc_180002E6B
0x180002fbd  mov     [rsp+98h+var_94], r9d
0x180002fc2  mov     r9d, [rsp+98h+arg_8]
0x180002fca  mov     [rsp+98h+var_90], r15d
0x180002fcf  mov     r15d, [rsp+98h+var_60]
0x180002fd4  mov     [rsp+98h+var_8C], r11d
0x180002fd9  mov     r11, [rsp+98h+arg_10]
0x180002fe1  mov     [rsp+98h+var_6C], r14d
0x180002fe6  cmp     r8d, 0Dh
0x180002fea  jnz     short loc_180003065
0x180002fec  mov     ecx, [rsp+98h+var_8C]
0x180002ff0  mov     [rsp+98h+var_8C], ecx
0x180002ff4  mov     ecx, [rsp+98h+var_90]
0x180002ff8  mov     [rsp+98h+var_90], ecx
0x180002ffc  mov     ecx, [rsp+98h+var_94]
0x180003000  mov     [rsp+98h+var_94], ecx
0x180003004  mov     ecx, [rsp+98h+arg_18]
0x18000300b  mov     [rsp+98h+arg_18], ecx
0x180003012  mov     ecx, [rsp+98h+var_98]
0x180003015  mov     [rsp+98h+var_98], ecx
0x180003018  mov     ecx, [rsp+98h+var_70]
0x18000301c  mov     [rsp+98h+var_70], ecx
0x180003020  mov     ecx, [rsp+98h+var_74]
0x180003024  mov     [rsp+98h+var_74], ecx
0x180003028  mov     ecx, [rsp+98h+arg_0]
0x18000302f  mov     [rsp+98h+arg_0], ecx
0x180003036  mov     ecx, [rsp+98h+var_80]
0x18000303a  mov     [rsp+98h+var_80], ecx
0x18000303e  mov     ecx, [rsp+98h+var_88]
0x180003042  mov     [rsp+98h+var_88], ecx
0x180003046  mov     ecx, [rsp+98h+var_84]
0x18000304a  mov     [rsp+98h+var_84], ecx
0x18000304e  mov     ecx, [rsp+98h+var_7C]
0x180003052  mov     [rsp+98h+var_7C], ecx
0x180003056  mov     ecx, [rsp+98h+var_78]
0x18000305a  mov     [rsp+98h+var_78], ecx
0x18000305e  cmp     eax, 0Ah
0x180003061  jz      short loc_1800030E2
0x180003063  jmp     short loc_1800030D7
0x180003065  mov     ecx, [rsp+98h+var_90]
0x180003069  mov     eax, [rsp+98h+var_8C]
0x18000306d  mov     [rsp+98h+var_90], ecx
0x180003071  mov     ecx, [rsp+98h+var_94]
0x180003075  mov     [rsp+98h+var_94], ecx
0x180003079  mov     ecx, [rsp+98h+arg_18]
0x180003080  mov     [rsp+98h+arg_18], ecx
0x180003087  mov     ecx, [rsp+98h+var_98]
0x18000308a  mov     [rsp+98h+var_98], ecx
0x18000308d  mov     ecx, [rsp+98h+var_70]
0x180003091  mov     [rsp+98h+var_70], ecx
0x180003095  mov     ecx, [rsp+98h+var_74]
0x180003099  mov     [rsp+98h+var_74], ecx
0x18000309d  mov     ecx, [rsp+98h+arg_0]
0x1800030a4  mov     [rsp+98h+arg_0], ecx
0x1800030ab  mov     ecx, [rsp+98h+var_80]
0x1800030af  mov     [rsp+98h+var_80], ecx
0x1800030b3  mov     ecx, [rsp+98h+var_88]
0x1800030b7  mov     [rsp+98h+var_88], ecx
0x1800030bb  mov     ecx, [rsp+98h+var_84]
0x1800030bf  mov     [rsp+98h+var_84], ecx
0x1800030c3  mov     ecx, [rsp+98h+var_7C]
0x1800030c7  mov     [rsp+98h+var_7C], ecx
0x1800030cb  mov     ecx, [rsp+98h+var_78]
0x1800030cf  mov     [rsp+98h+var_78], ecx
0x1800030d3  mov     [rsp+98h+var_8C], eax
0x1800030d7  cmp     r8d, 0Ah
0x1800030db  jnz     short loc_1800030E4
0x1800030dd  cmp     ebp, 0Dh
0x1800030e0  jnz     short loc_1800030E4
0x1800030e2  inc     ebx
0x1800030e4  xor     r8d, r8d
0x1800030e7  test    ebp, ebp
0x1800030e9  lea     r14d, [rdi-1]
0x1800030ed  mov     eax, 200h
0x1800030f2  cmovnz  r14d, edi
0x1800030f6  mov     r10d, eax
0x1800030f9  cmp     ebp, 1Ah
0x1800030fc  lea     edi, [rbx+1]
0x1800030ff  cmovnz  edi, ebx
0x180003102  mov     bl, cs:?NlsMbCodePageTag@@3EA; uchar NlsMbCodePageTag
0x180003108  cmp     r9d, eax
0x18000310b  cmovbe  r10d, r9d
0x18000310f  test    bl, bl
0x180003111  jz      short loc_18000314F
0x180003113  xor     ebp, ebp
0x180003115  test    r10d, r10d
0x180003118  jz      short loc_18000314C
0x18000311a  mov     eax, r8d
0x18000311d  lea     rdx, ?NlsLeadByteInfoTable@@3PAGA; ushort near * NlsLeadByteInfoTable
0x180003124  movzx   ecx, byte ptr [rax+r12]
0x180003129  lea     eax, [r15+1]
0x18000312d  movzx   edx, word ptr [rdx+rcx*2]
0x180003131  test    dx, dx
0x180003134  cmovz   eax, r15d
0x180003138  mov     r15d, eax
0x18000313b  lea     eax, [r8+1]
0x18000313f  cmovz   eax, r8d
0x180003143  lea     r8d, [rax+1]
0x180003147  cmp     r8d, r10d
0x18000314a  jb      short loc_18000311A
0x18000314c  xor     r8d, r8d
0x18000314f  mov     ebp, [rsp+98h+var_6C]
0x180003153  cmp     r13d, 7Fh
0x180003157  jnb     short loc_180003163
0x180003159  test    ebp, ebp
0x18000315b  jnz     short loc_18000316A
0x18000315d  lea     r8d, [rbp+1]
0x180003161  jmp     short loc_180003176
0x180003163  test    ebp, ebp
0x180003165  jz      short loc_180003176
0x180003167  xor     r8d, r8d
0x18000316a  test    r13d, r13d
0x18000316d  mov     eax, 10h
0x180003172  cmovz   r8d, eax
0x180003176  test    bl, bl
0x180003178  jz      short loc_1800031CF
0x18000317a  test    r15d, r15d
0x18000317d  jz      short loc_1800031CF
0x18000317f  test    r11, r11
0x180003182  jz      short loc_1800031CF
0x180003184  test    dword ptr [r11], 400h
0x18000318b  jz      short loc_1800031CF
0x18000318d  cmp     [rsp+98h+var_58], 100h
  ... truncated ...
```

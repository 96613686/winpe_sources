# DevAuthHostGetRequest

- ea: `0x180001e04`
- end: `0x1800020db`
- name: `DevAuthHostGetRequest`
- size: `727`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800015f0`

## callees

- `0x180001e04`
- `0x180002348`
- `0x1800026e8`
- `0x1800027dc`
- `0x180002888`
- `0x180002b38`
- `0x1800036a0`
- `0x1800037ac`
- `0x1800067e0`

## import_xrefs

- `cng!BCryptHashData` at `0x180002093`
- `cng!BCryptHashData` at `0x180002093`

## pseudocode

```c
__int64 __fastcall DevAuthHostGetRequest(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  ULONG v4; // ebp
  unsigned int v8; // ecx
  __int64 v9; // rsi
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  int HostStrictPairingCert; // eax
  __int64 v18; // r9
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  size_t Size; // [rsp+30h] [rbp-78h]
  ULONG cbInput; // [rsp+40h] [rbp-68h] BYREF
  UCHAR v25[32]; // [rsp+48h] [rbp-60h] BYREF

  v4 = 0;
  cbInput = 0;
  if ( *(_BYTE *)a1 == 1 && !*(_DWORD *)(a1 + 8) )
  {
    v8 = *(unsigned __int8 *)(a1 + 1);
    v9 = a2 + 5;
    v10 = 0;
    if ( v8 <= 6 )
    {
      if ( v8 == 6 )
      {
        *(_BYTE *)a2 = 65;
        *(_WORD *)(a2 + 1) = 1536;
        if ( (unsigned int)DevAuthGetRunningHash(*(_QWORD *)(a1 + 1224), v25)
          && DevAuthSignHash(c_pbHostPrivateKey, 0x21Bu, v25, v18, (PUCHAR)(v9 + 4)) )
        {
          *(_DWORD *)v9 = 65798;
          v4 = 260;
          goto LABEL_24;
        }
LABEL_25:
        if ( !v10 )
          goto LABEL_44;
        goto LABEL_38;
      }
      v11 = v8 - 1;
      if ( !v11 )
      {
        *(_BYTE *)a2 = 65;
        *(_WORD *)(a2 + 1) = 256;
        if ( !(unsigned int)DevAuthGenerateRandomNumber((void *)(a1 + 16), 0x20u) )
          goto LABEL_25;
        *(_DWORD *)v9 = 671088897;
        v4 = 44;
        *(_OWORD *)(v9 + 4) = *(_OWORD *)(a1 + 16);
        *(_OWORD *)(v9 + 20) = *(_OWORD *)(a1 + 32);
        *(_DWORD *)(v9 + 36) = _byteswap_ulong(*(_DWORD *)(a1 + 12));
        *(_DWORD *)(v9 + 40) = -374375611;
        goto LABEL_24;
      }
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( (_DWORD)v14 )
          {
            if ( (_DWORD)v14 != 1 )
              goto LABEL_44;
            *(_BYTE *)a2 = 65;
            *(_WORD *)(a2 + 1) = 1280;
            v15 = GenerateHostKeyExchange(a1, a2 + 5, a3, &cbInput);
            v4 = cbInput;
            LOBYTE(v10) = v15 != 0;
            goto LABEL_25;
          }
          *(_BYTE *)a2 = 65;
          *(_WORD *)(a2 + 1) = 1024;
          v16 = a2 + 9;
          if ( (*(_BYTE *)(a1 + 80) & 4) != 0 )
            HostStrictPairingCert = DevAuthGetHostStrictPairingCert(a1 + 126, *(unsigned int *)(a1 + 1152), a3, v9 + 4);
          else
            HostStrictPairingCert = DevAuthGetHostGenericCert(v14, v16);
          if ( HostStrictPairingCert )
          {
            *(_DWORD *)v9 = 1073873156;
            v4 = 580;
LABEL_24:
            v10 = 1;
            goto LABEL_25;
          }
          goto LABEL_25;
        }
        *(_DWORD *)(a2 + 1) = 67371776;
      }
      else
      {
        *(_DWORD *)(a2 + 1) = 1409286656;
      }
LABEL_17:
      *(_BYTE *)a2 = 66;
      v10 = 1;
      goto LABEL_43;
    }
    v19 = v8 - 7;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        *(_DWORD *)(a2 + 1) = 1140852736;
        goto LABEL_17;
      }
      v21 = v20 - 3;
      if ( v21 )
      {
        if ( v21 != 1 )
          goto LABEL_44;
        *(_WORD *)(a2 + 1) = 3072;
        goto LABEL_17;
      }
      *(_BYTE *)a2 = 65;
      v4 = 4;
      *(_WORD *)(a2 + 1) = 2816;
      *(_DWORD *)v9 = 267;
    }
    else
    {
      *(_BYTE *)a2 = 65;
      *(_WORD *)(a2 + 1) = 1792;
      if ( !(unsigned int)DevAuthGetRunningHash(*(_QWORD *)(a1 + 1224), v25) )
        goto LABEL_44;
      LODWORD(Size) = 32;
      if ( !(unsigned int)DevAuthPesudoRandomFunction(
                            (int)"Host Finished",
                            (int)a1 + 1168,
                            48,
                            (int)v25,
                            32,
                            (void *)(v9 + 4),
                            Size) )
        goto LABEL_44;
      *(_DWORD *)v9 = 536871175;
      v4 = 36;
    }
    v10 = 1;
LABEL_38:
    if ( *(_BYTE *)a2 == 65 )
      *(_WORD *)(a2 + 3) = ((_WORD)v4 << 8) | BYTE1(v4);
    if ( v4 )
    {
      if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(*(_QWORD *)(a1 + 1224) + 8LL), (PUCHAR)v9, v4, 0) < 0 )
        v10 = 0;
    }
LABEL_43:
    *(_DWORD *)(a1 + 8) = 1;
    *a4 = v4 + 5;
    if ( v10 )
      return v10;
LABEL_44:
    *(_BYTE *)a1 = 3;
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180001e04  push    rbx
0x180001e06  push    rbp
0x180001e07  push    rsi
0x180001e08  push    rdi
0x180001e09  push    r12
0x180001e0b  push    r14
0x180001e0d  push    r15
0x180001e0f  sub     rsp, 70h
0x180001e13  mov     rax, cs:__security_cookie
0x180001e1a  xor     rax, rsp
0x180001e1d  mov     [rsp+0A8h+var_40], rax
0x180001e22  xor     ebp, ebp
0x180001e24  mov     r15, r9
0x180001e27  mov     rdi, rdx
0x180001e2a  mov     [rsp+0A8h+cbInput], ebp
0x180001e2e  mov     r14, rcx
0x180001e31  lea     r12d, [rbp+1]
0x180001e35  cmp     [rcx], r12b
0x180001e38  jnz     loc_1800020BC
0x180001e3e  cmp     [rcx+8], ebp
0x180001e41  jnz     loc_1800020BC
0x180001e47  movzx   ecx, byte ptr [rcx+1]
0x180001e4b  lea     rsi, [rdx+5]
0x180001e4f  xor     ebx, ebx
0x180001e51  cmp     ecx, 6
0x180001e54  ja      loc_180001FB3
0x180001e5a  jz      loc_180001F57
0x180001e60  sub     ecx, r12d
0x180001e63  jz      loc_180001F0D
0x180001e69  sub     ecx, r12d
0x180001e6c  jz      loc_180001F04
0x180001e72  sub     ecx, r12d
0x180001e75  jz      short loc_180001EF2
0x180001e77  sub     ecx, r12d
0x180001e7a  jz      short loc_180001EAC
0x180001e7c  cmp     ecx, r12d
0x180001e7f  jnz     loc_1800020B4
0x180001e85  mov     byte ptr [rdx], 41h ; 'A'
0x180001e88  lea     r9, [rsp+0A8h+cbInput]
0x180001e8d  mov     word ptr [rdx+1], 500h
0x180001e93  mov     rcx, r14
0x180001e96  mov     rdx, rsi
0x180001e99  call    _GenerateHostKeyExchange
0x180001e9e  mov     ebp, [rsp+0A8h+cbInput]
0x180001ea2  test    eax, eax
0x180001ea4  setnz   bl
0x180001ea7  jmp     loc_180001FA6
0x180001eac  mov     byte ptr [rdx], 41h ; 'A'
0x180001eaf  mov     word ptr [rdx+1], 400h
0x180001eb5  lea     rdx, [rsi+4]
0x180001eb9  test    byte ptr [r14+50h], 4
0x180001ebe  jz      short loc_180001EEB
0x180001ec0  mov     r9, rdx
0x180001ec3  lea     rcx, [r14+7Eh]
0x180001ec7  mov     edx, [r14+480h]
0x180001ece  call    DevAuthGetHostStrictPairingCert
0x180001ed3  test    eax, eax
0x180001ed5  jz      loc_180001FA6
0x180001edb  mov     dword ptr [rsi], 40020104h
0x180001ee1  mov     ebp, 244h
0x180001ee6  jmp     loc_180001FA3
0x180001eeb  call    DevAuthGetHostGenericCert
0x180001ef0  jmp     short loc_180001ED3
0x180001ef2  mov     dword ptr [rdx+1], 4040300h
0x180001ef9  mov     byte ptr [rdx], 42h ; 'B'
0x180001efc  mov     ebx, r12d
0x180001eff  jmp     loc_1800020A6
0x180001f04  mov     dword ptr [rdx+1], 54000200h
0x180001f0b  jmp     short loc_180001EF9
0x180001f0d  mov     byte ptr [rdx], 41h ; 'A'
0x180001f10  lea     rcx, [r14+10h]; void *
0x180001f14  mov     word ptr [rdx+1], 100h
0x180001f1a  mov     edx, 20h ; ' '; Size
0x180001f1f  call    DevAuthGenerateRandomNumber
0x180001f24  test    eax, eax
0x180001f26  jz      short loc_180001FA6
0x180001f28  mov     dword ptr [rsi], 28000101h
0x180001f2e  mov     ebp, 2Ch ; ','
0x180001f33  movups  xmm0, xmmword ptr [r14+10h]
0x180001f38  movups  xmmword ptr [rsi+4], xmm0
0x180001f3c  movups  xmm1, xmmword ptr [r14+20h]
0x180001f41  movups  xmmword ptr [rsi+14h], xmm1
0x180001f45  mov     eax, [r14+0Ch]
0x180001f49  bswap   eax
0x180001f4b  mov     [rsi+24h], eax
0x180001f4e  mov     dword ptr [rsi+28h], 0E9AF7B45h
0x180001f55  jmp     short loc_180001FA3
0x180001f57  mov     byte ptr [rdx], 41h ; 'A'
0x180001f5a  mov     word ptr [rdx+1], 600h
0x180001f60  lea     rdx, [rsp+0A8h+var_60]
0x180001f65  mov     rcx, [r14+4C8h]
0x180001f6c  call    DevAuthGetRunningHash
0x180001f71  test    eax, eax
0x180001f73  jz      short loc_180001FA6
0x180001f75  lea     rax, [rsi+4]
0x180001f79  mov     edx, 21Bh; cbInput
0x180001f7e  lea     r8, [rsp+0A8h+var_60]; PUCHAR
0x180001f83  mov     [rsp+0A8h+pbOutput], rax; pbOutput
0x180001f88  lea     rcx, c_pbHostPrivateKey; "RSA2"
0x180001f8f  call    DevAuthSignHash
0x180001f94  test    eax, eax
0x180001f96  jz      short loc_180001FA6
0x180001f98  mov     dword ptr [rsi], 10106h
0x180001f9e  mov     ebp, 104h
0x180001fa3  mov     ebx, r12d
0x180001fa6  test    ebx, ebx
0x180001fa8  jz      loc_1800020B4
0x180001fae  jmp     loc_180002063
0x180001fb3  sub     ecx, 7
0x180001fb6  jz      short loc_180001FF8
0x180001fb8  sub     ecx, r12d
0x180001fbb  jz      short loc_180001FEC
0x180001fbd  sub     ecx, 3
0x180001fc0  jz      short loc_180001FD6
0x180001fc2  cmp     ecx, r12d
0x180001fc5  jnz     loc_1800020B4
0x180001fcb  mov     word ptr [rdx+1], 0C00h
0x180001fd1  jmp     loc_180001EF9
0x180001fd6  mov     byte ptr [rdx], 41h ; 'A'
0x180001fd9  mov     ebp, 4
0x180001fde  mov     word ptr [rdx+1], 0B00h
0x180001fe4  mov     dword ptr [rsi], 10Bh
0x180001fea  jmp     short loc_180002060
0x180001fec  mov     dword ptr [rdx+1], 44000800h
0x180001ff3  jmp     loc_180001EF9
0x180001ff8  mov     byte ptr [rdx], 41h ; 'A'
0x180001ffb  mov     word ptr [rdx+1], 700h
0x180002001  lea     rdx, [rsp+0A8h+var_60]
0x180002006  mov     rcx, [r14+4C8h]
0x18000200d  call    DevAuthGetRunningHash
0x180002012  test    eax, eax
0x180002014  jz      loc_1800020B4
0x18000201a  lea     rax, [rsi+4]
0x18000201e  mov     dword ptr [rsp+0A8h+Size], 20h ; ' '; Size
0x180002026  mov     [rsp+0A8h+var_80], rax; void *
0x18000202b  lea     rdx, [r14+490h]; int
0x180002032  lea     r9, [rsp+0A8h+var_60]; int
0x180002037  mov     dword ptr [rsp+0A8h+pbOutput], 20h ; ' '; int
0x18000203f  mov     r8d, 30h ; '0'; int
0x180002045  lea     rcx, aHostFinished; "Host Finished"
0x18000204c  call    DevAuthPesudoRandomFunction
0x180002051  test    eax, eax
0x180002053  jz      short loc_1800020B4
0x180002055  mov     dword ptr [rsi], 20000107h
0x18000205b  mov     ebp, 24h ; '$'
0x180002060  mov     ebx, r12d
0x180002063  cmp     byte ptr [rdi], 41h ; 'A'
0x180002066  jnz     short loc_18000207B
0x180002068  movzx   eax, bp
0x18000206b  mov     ecx, eax
0x18000206d  shl     ax, 8
0x180002071  shr     ecx, 8
0x180002074  or      cx, ax
0x180002077  mov     [rdi+3], cx
0x18000207b  test    ebp, ebp
0x18000207d  jz      short loc_1800020A6
0x18000207f  mov     rcx, [r14+4C8h]
0x180002086  xor     r9d, r9d; dwFlags
0x180002089  mov     r8d, ebp; cbInput
0x18000208c  mov     rdx, rsi; pbInput
0x18000208f  mov     rcx, [rcx+8]; hHash
0x180002093  call    cs:__imp_BCryptHashData
0x18000209a  nop     dword ptr [rax+rax+00h]
0x18000209f  xor     ecx, ecx
0x1800020a1  test    eax, eax
0x1800020a3  cmovs   ebx, ecx
0x1800020a6  mov     [r14+8], r12d
0x1800020aa  lea     ecx, [rbp+5]
0x1800020ad  mov     [r15], ecx
0x1800020b0  test    ebx, ebx
0x1800020b2  jnz     short loc_1800020B8
0x1800020b4  mov     byte ptr [r14], 3
0x1800020b8  mov     eax, ebx
0x1800020ba  jmp     short loc_1800020BE
0x1800020bc  xor     eax, eax
0x1800020be  mov     rcx, [rsp+0A8h+var_40]
0x1800020c3  xor     rcx, rsp; StackCookie
0x1800020c6  call    __security_check_cookie
0x1800020cb  add     rsp, 70h
0x1800020cf  pop     r15
0x1800020d1  pop     r14
0x1800020d3  pop     r12
0x1800020d5  pop     rdi
0x1800020d6  pop     rsi
0x1800020d7  pop     rbp
0x1800020d8  pop     rbx
0x1800020d9  retn
```

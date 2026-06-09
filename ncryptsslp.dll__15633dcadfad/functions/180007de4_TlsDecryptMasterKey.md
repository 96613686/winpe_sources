# TlsDecryptMasterKey

- ea: `0x180007de4`
- end: `0x18000819f`
- name: `TlsDecryptMasterKey`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011f10`

## callees

- `0x180005cb0`
- `0x180007de4`
- `0x1800081a8`
- `0x18000b594`
- `0x18000b654`
- `0x180020248`
- `0x180020bc4`
- `0x180020c08`
- `0x180024ef0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180007f5d`
- `bcrypt!BCryptGenRandom` at `0x180007f5d`
- `ncrypt!NCryptDecrypt` at `0x180007f9f`
- `ncrypt!NCryptDecrypt` at `0x180007f9f`

## string_xrefs

- `0x180007f00`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800080c8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsDecryptMasterKey(
        __int64 a1,
        NCRYPT_KEY_HANDLE a2,
        __int64 a3,
        __int64 a4,
        BYTE *pbInput,
        DWORD dwFlags,
        DWORD cbInput)
{
  __int64 v8; // r14
  __int64 v10; // rdx
  int v12; // eax
  int v13; // edx
  unsigned int v14; // ebx
  BYTE *v15; // rax
  int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // r12d
  _QWORD *v21; // rcx
  unsigned int v22; // ebx
  int v23; // esi
  DWORD v24; // ebx
  unsigned int v25; // esi
  __int64 i; // rcx
  int v27; // eax
  int v28; // edx
  __int64 v29; // r9
  int pbOutput; // [rsp+20h] [rbp-E0h]
  DWORD pcbResult; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  int v33; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+6Ch] [rbp-94h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v36; // [rsp+78h] [rbp-88h] BYREF
  _OWORD *v37; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v38; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v39[3]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v40; // [rsp+9Ch] [rbp-64h] BYREF
  __int16 v41; // [rsp+9Dh] [rbp-63h]
  char v42; // [rsp+9Fh] [rbp-61h]
  __int128 v43; // [rsp+A0h] [rbp-60h]
  UCHAR v44[28]; // [rsp+B0h] [rbp-50h] BYREF
  UCHAR pbBuffer[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v46; // [rsp+E0h] [rbp-20h]
  __int128 v47; // [rsp+F0h] [rbp-10h]

  v37 = 0;
  v33 = 0;
  v41 = 0;
  v42 = 0;
  v8 = 48;
  v36 = 0;
  v32 = 0;
  v10 = *(unsigned int *)(a3 + 8);
  v34 = 0;
  memset(v44, 0, sizeof(v44));
  v38 = 0;
  v35 = 0;
  v39[0] = 60;
  v39[1] = 1936944183;
  v39[2] = v10;
  v40 = 0;
  v43 = 0;
  pcbResult = 48;
  *(_OWORD *)pbBuffer = 0;
  v46 = 0;
  v47 = 0;
  v12 = TlsParseParameterList(a4, v10, &v37, &v33, &v36, &v32, &v38, &v35, 0, 0, &v34);
  v14 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        v12,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        209);
    goto LABEL_5;
  }
  v17 = BCryptGenRandom(0, pbBuffer, 0x30u, 2u);
  v14 = v17;
  if ( v17 < 0 )
  {
    v29 = 1505;
    goto LABEL_30;
  }
  v18 = NCryptDecrypt(a2, pbInput, cbInput, 0, &v40, 0x30u, &pcbResult, dwFlags);
  v20 = v18;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v19, v18);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
    {
      pbOutput = 48;
      WPP_SF_DD(v21[2], 24, v19, pcbResult);
      v21 = WPP_GLOBAL_Control;
    }
  }
  v22 = (unsigned __int8)v41 | (v40 << 8);
  v23 = v34;
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
  {
    pbOutput = v34;
    WPP_SF_DD(v21[2], 25, v19, v22);
    v21 = WPP_GLOBAL_Control;
  }
  v24 = v20 | (pcbResult - 48) | ((v22 - v23) >> 31);
  v25 = -((v24 | -v24) >> 31);
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
    WPP_SF_D(v21[2], 26, v19, v25);
  for ( i = 0; i != 48; ++i )
    *(&v40 + i) ^= (unsigned __int8)v25 & (pbBuffer[i] ^ *(&v40 + i));
  if ( *(_DWORD *)(a3 + 8) < 0x301u )
  {
    v17 = Ssl3ComputeMasterKey(a1, &v40, 0x30u, a3 + 28, pbOutput, v37, v33, v36, v32);
    v14 = v17;
    if ( v17 >= 0 )
      goto LABEL_25;
    v29 = 1598;
LABEL_30:
    DebugTraceError((unsigned int)v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v29);
    goto LABEL_5;
  }
  v27 = Tls1ComputeMasterKey(48, a3, (__int64)v39, (int)v37, v33, (__int64)v36, v32, v38, v35);
  v14 = v27;
  if ( v27 >= 0 )
  {
LABEL_25:
    v14 = 0;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      v27,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      44);
LABEL_5:
  v15 = &v40;
  do
  {
    *v15++ = 0;
    --v8;
  }
  while ( v8 );
  return v14;
}

```

## disassembly

```asm
0x180007de4  push    rbp
0x180007de6  push    rbx
0x180007de7  push    rsi
0x180007de8  push    rdi
0x180007de9  push    r12
0x180007deb  push    r13
0x180007ded  push    r14
0x180007def  push    r15
0x180007df1  lea     rbp, [rsp-18h]
0x180007df6  sub     rsp, 118h
0x180007dfd  mov     rax, cs:__security_cookie
0x180007e04  xor     rax, rsp
0x180007e07  mov     [rbp+50h+var_50], rax
0x180007e0b  mov     rsi, [rbp+50h+pbInput]
0x180007e12  xor     r12d, r12d
0x180007e15  mov     r13, rcx
0x180007e18  mov     [rbp+50h+var_D0], r12
0x180007e1c  xor     ecx, ecx
0x180007e1e  mov     [rsp+150h+var_E8], r12d
0x180007e23  mov     [rbp+50h+var_B3], cx
0x180007e27  xorps   xmm0, xmm0
0x180007e2a  mov     [rbp+50h+var_B1], cl
0x180007e2d  lea     r14d, [r12+30h]
0x180007e32  mov     rax, r9
0x180007e35  mov     [rsp+150h+var_D8], r12
0x180007e3a  lea     rcx, [rsp+150h+var_E4]
0x180007e3f  mov     [rsp+150h+var_EC], r12d
0x180007e44  mov     [rsp+150h+var_100], rcx
0x180007e49  lea     r9, [rsp+150h+var_E8]
0x180007e4e  mov     [rsp+150h+var_108], r12
0x180007e53  lea     rcx, [rsp+150h+var_E0]
0x180007e58  mov     [rsp+150h+var_110], r12
0x180007e5d  mov     rdi, rdx
0x180007e60  mov     edx, [r8+8]
0x180007e64  mov     r15, r8
0x180007e67  mov     qword ptr [rsp+150h+dwFlags], rcx
0x180007e6c  lea     r8, [rbp+50h+var_D0]
0x180007e70  lea     rcx, [rbp+50h+var_C8]
0x180007e74  mov     [rsp+150h+var_E4], r12d
0x180007e79  mov     [rsp+150h+pcbResult], rcx
0x180007e7e  lea     rcx, [rsp+150h+var_EC]
0x180007e83  mov     qword ptr [rsp+150h+cbOutput], rcx
0x180007e88  lea     rcx, [rsp+150h+var_D8]
0x180007e8d  mov     [rsp+150h+pbOutput], rcx
0x180007e92  mov     rcx, rax
0x180007e95  movups  xmmword ptr [rbp+50h+var_A0], xmm0
0x180007e99  mov     [rbp+50h+var_C8], r12
0x180007e9d  mov     [rsp+150h+var_E0], r12d
0x180007ea2  mov     [rbp+50h+var_C0], 3Ch ; '<'
0x180007ea9  mov     [rbp+50h+var_BC], 73736C37h
0x180007eb0  mov     [rbp+50h+var_B8], edx
0x180007eb3  mov     [rbp+50h+var_B4], r12b
0x180007eb7  movups  [rbp+50h+var_B0], xmm0
0x180007ebb  mov     [rsp+150h+var_F0], r14d
0x180007ec0  movups  xmmword ptr [rbp+50h+var_A0+0Ch], xmm0
0x180007ec4  movups  xmmword ptr [rbp+50h+pbBuffer], xmm0
0x180007ec8  movups  [rbp+50h+var_70], xmm0
0x180007ecc  movups  [rbp+50h+var_60], xmm0
0x180007ed0  call    TlsParseParameterList
0x180007ed5  mov     ebx, eax
0x180007ed7  test    eax, eax
0x180007ed9  jns     short loc_180007F4E
0x180007edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ee2  lea     rdi, WPP_GLOBAL_Control
0x180007ee9  cmp     rcx, rdi
0x180007eec  jz      short loc_180007F1C
0x180007eee  test    byte ptr [rcx+1Ch], 1
0x180007ef2  jz      short loc_180007F1C
0x180007ef4  mov     dword ptr [rsp+150h+pcbResult], 5D1h
0x180007efc  mov     rcx, [rcx+10h]
0x180007f00  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f07  mov     qword ptr [rsp+150h+cbOutput], r8
0x180007f0c  lea     r9, aStatus; "Status"
0x180007f13  mov     dword ptr [rsp+150h+pbOutput], eax
0x180007f17  call    WPP_SF_sDsd
0x180007f1c  lea     rax, [rbp+50h+var_B4]
0x180007f20  mov     [rax], r12b
0x180007f23  inc     rax
0x180007f26  sub     r14, 1
0x180007f2a  jnz     short loc_180007F20
0x180007f2c  mov     eax, ebx
0x180007f2e  mov     rcx, [rbp+50h+var_50]
0x180007f32  xor     rcx, rsp; StackCookie
0x180007f35  call    __security_check_cookie
0x180007f3a  add     rsp, 118h
0x180007f41  pop     r15
0x180007f43  pop     r14
0x180007f45  pop     r13
0x180007f47  pop     r12
0x180007f49  pop     rdi
0x180007f4a  pop     rsi
0x180007f4b  pop     rbx
0x180007f4c  pop     rbp
0x180007f4d  retn
0x180007f4e  mov     r9d, 2; dwFlags
0x180007f54  lea     rdx, [rbp+50h+pbBuffer]; pbBuffer
0x180007f58  mov     r8d, r14d; cbBuffer
0x180007f5b  xor     ecx, ecx; hAlgorithm
0x180007f5d  call    cs:__imp_BCryptGenRandom
0x180007f63  mov     ebx, eax
0x180007f65  test    eax, eax
0x180007f67  js      loc_1800080BA
0x180007f6d  mov     eax, [rbp+50h+arg_28]
0x180007f73  xor     r9d, r9d; pPaddingInfo
0x180007f76  mov     r8d, [rbp+50h+cbInput]; cbInput
0x180007f7d  mov     rdx, rsi; pbInput
0x180007f80  mov     [rsp+150h+dwFlags], eax; dwFlags
0x180007f84  mov     rcx, rdi; hKey
0x180007f87  lea     rax, [rsp+150h+var_F0]
0x180007f8c  mov     [rsp+150h+pcbResult], rax; pcbResult
0x180007f91  lea     rax, [rbp+50h+var_B4]
0x180007f95  mov     [rsp+150h+cbOutput], r14d; cbOutput
0x180007f9a  mov     [rsp+150h+pbOutput], rax; pbOutput
0x180007f9f  call    cs:__imp_NCryptDecrypt
0x180007fa5  mov     r12d, eax
0x180007fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007faf  lea     rdi, WPP_GLOBAL_Control
0x180007fb6  cmp     rcx, rdi
0x180007fb9  jz      short loc_180007FD4
0x180007fbb  test    byte ptr [rcx+1Ch], 8
0x180007fbf  jnz     loc_1800080E2
0x180007fc5  cmp     rcx, rdi
0x180007fc8  jz      short loc_180007FD4
0x180007fca  test    byte ptr [rcx+1Ch], 8
0x180007fce  jnz     loc_1800080FF
0x180007fd4  movzx   ebx, [rbp+50h+var_B4]
0x180007fd8  movzx   eax, byte ptr [rbp+50h+var_B3]
0x180007fdc  shl     ebx, 8
0x180007fdf  or      ebx, eax
0x180007fe1  mov     esi, [rsp+150h+var_E4]
0x180007fe5  cmp     rcx, rdi
0x180007fe8  jz      short loc_180007FF4
0x180007fea  test    byte ptr [rcx+1Ch], 8
0x180007fee  jnz     loc_180008123
0x180007ff4  mov     eax, [rsp+150h+var_F0]
0x180007ff8  sub     ebx, esi
0x180007ffa  shr     ebx, 1Fh
0x180007ffd  add     eax, 0FFFFFFD0h
0x180008000  or      ebx, eax
0x180008002  or      ebx, r12d
0x180008005  mov     esi, ebx
0x180008007  neg     esi
0x180008009  or      esi, ebx
0x18000800b  shr     esi, 1Fh
0x18000800e  neg     esi
0x180008010  cmp     rcx, rdi
0x180008013  jz      short loc_18000801F
0x180008015  test    byte ptr [rcx+1Ch], 8
0x180008019  jnz     loc_180008144
0x18000801f  xor     r12d, r12d
0x180008022  mov     ecx, r12d
0x180008025  mov     al, [rbp+rcx+50h+var_B4]
0x180008029  xor     al, [rbp+rcx+50h+pbBuffer]
0x18000802d  and     al, sil
0x180008030  xor     [rbp+rcx+50h+var_B4], al
0x180008034  inc     rcx
0x180008037  cmp     rcx, r14
0x18000803a  jnz     short loc_180008025
0x18000803c  cmp     dword ptr [r15+8], 301h
0x180008044  jb      loc_18000815A
0x18000804a  mov     eax, [rsp+150h+var_E0]
0x18000804e  lea     r8, [rbp+50h+var_C0]
0x180008052  mov     r9, [rbp+50h+var_D0]
0x180008056  mov     rdx, r15
0x180008059  mov     dword ptr [rsp+150h+var_110], eax
0x18000805d  mov     rax, [rbp+50h+var_C8]
0x180008061  mov     qword ptr [rsp+150h+dwFlags], rax
0x180008066  mov     eax, [rsp+150h+var_EC]
0x18000806a  mov     dword ptr [rsp+150h+pcbResult], eax
0x18000806e  mov     rax, [rsp+150h+var_D8]
0x180008073  mov     qword ptr [rsp+150h+cbOutput], rax
0x180008078  mov     eax, [rsp+150h+var_E8]
0x18000807c  mov     dword ptr [rsp+150h+pbOutput], eax
0x180008080  call    Tls1ComputeMasterKey
0x180008085  mov     ebx, eax
0x180008087  test    eax, eax
0x180008089  js      short loc_180008093
0x18000808b  mov     ebx, r12d
0x18000808e  jmp     loc_180007F1C
0x180008093  mov     rcx, cs:WPP_GLOBAL_Control
0x18000809a  cmp     rcx, rdi
0x18000809d  jz      loc_180007F1C
0x1800080a3  test    byte ptr [rcx+1Ch], 1
0x1800080a7  jz      loc_180007F1C
0x1800080ad  mov     dword ptr [rsp+150h+pcbResult], 62Ch
0x1800080b5  jmp     loc_180007EFC
0x1800080ba  mov     r9d, 5E1h
0x1800080c0  jmp     short loc_1800080C8
0x1800080c2  mov     r9d, 63Eh
0x1800080c8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800080cf  mov     ecx, eax
0x1800080d1  lea     rdx, aStatus; "Status"
0x1800080d8  call    DebugTraceError
0x1800080dd  jmp     loc_180007F1C
0x1800080e2  mov     rcx, [rcx+10h]
0x1800080e6  mov     edx, 17h
0x1800080eb  mov     r9d, r12d
0x1800080ee  call    WPP_SF_D
0x1800080f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080fa  jmp     loc_180007FC5
0x1800080ff  mov     r9d, [rsp+150h+var_F0]
0x180008104  mov     edx, 18h
0x180008109  mov     rcx, [rcx+10h]
0x18000810d  mov     dword ptr [rsp+150h+pbOutput], r14d
0x180008112  call    WPP_SF_DD
0x180008117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000811e  jmp     loc_180007FD4
0x180008123  mov     rcx, [rcx+10h]
0x180008127  mov     edx, 19h
0x18000812c  mov     r9d, ebx
0x18000812f  mov     dword ptr [rsp+150h+pbOutput], esi
0x180008133  call    WPP_SF_DD
0x180008138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000813f  jmp     loc_180007FF4
0x180008144  mov     rcx, [rcx+10h]
0x180008148  mov     edx, 1Ah
0x18000814d  mov     r9d, esi
0x180008150  call    WPP_SF_D
0x180008155  jmp     loc_18000801F
0x18000815a  mov     eax, [rsp+150h+var_EC]
0x18000815e  lea     r9, [r15+1Ch]
0x180008162  mov     dword ptr [rsp+150h+var_110], eax
0x180008166  lea     rdx, [rbp+50h+var_B4]
0x18000816a  mov     rax, [rsp+150h+var_D8]
0x18000816f  mov     r8d, r14d
0x180008172  mov     qword ptr [rsp+150h+dwFlags], rax
0x180008177  mov     rcx, r13
0x18000817a  mov     eax, [rsp+150h+var_E8]
0x18000817e  mov     dword ptr [rsp+150h+pcbResult], eax
0x180008182  mov     rax, [rbp+50h+var_D0]
0x180008186  mov     qword ptr [rsp+150h+cbOutput], rax
0x18000818b  call    Ssl3ComputeMasterKey
0x180008190  mov     ebx, eax
0x180008192  test    eax, eax
0x180008194  jns     loc_18000808B
0x18000819a  jmp     loc_1800080C2
```

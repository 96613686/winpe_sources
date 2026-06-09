# WSTVerifySignature

- ea: `0x14002bc00`
- end: `0x14002bf14`
- name: `WSTVerifySignature`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029870`

## callees

- `0x140007008`
- `0x140010160`
- `0x140010240`
- `0x1400261e0`
- `0x14002bc00`
- `0x14002bf1c`

## string_xrefs

- `0x14002bcc9`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002bcff`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002bca1`: `Can't have readonly & readonly_w_checksum\n`
- `0x14002bd71`: `Failed to verify signature token: %#x\n`

## pseudocode

```c
__int64 __fastcall WSTVerifySignature(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // r11
  unsigned int v8; // r10d
  __int64 v9; // rdi
  unsigned int *v10; // rdx
  unsigned int i; // r8d
  int v12; // eax
  int v13; // ebx
  int v14; // r8d
  int v15; // eax
  int v16; // eax
  unsigned int j; // esi
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int8 *v20; // rsi
  int v21; // eax
  char v22; // r8
  __int64 k; // rdx
  unsigned __int8 v24; // cl
  char v25; // al
  __int64 v27; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-61h] BYREF
  int v29; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v30; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int8 *v31; // [rsp+68h] [rbp-51h] BYREF
  __int64 v32; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v33[64]; // [rsp+80h] [rbp-39h] BYREF

  v4 = a3;
  v30 = 0;
  v27 = 0;
  v31 = 0;
  v28 = 0;
  v8 = *(_DWORD *)(a2 + 4);
  v9 = 0;
  v10 = 0;
  v29 = 0;
  v32 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v12 = *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL * i + 4);
    if ( v12 < 0 && (v12 & 0x10000000) != 0 )
    {
      v13 = -2146893048;
      if ( !KsecInfoLevel )
        return (unsigned int)v13;
      KsecDebugOut(1, "Can't have readonly & readonly_w_checksum\n");
      goto LABEL_44;
    }
    if ( (v12 & 0xFFFFFFF) == 2 )
      v10 = (unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL * i);
  }
  if ( v10 )
  {
    v14 = *(_DWORD *)(a1 + 108);
    if ( (v14 & 0x1000C) != 0 )
    {
      v15 = WSTVerifySignatureToken(a1, v10, 0, v4, &v31, &v29, (int *)&v28, 0, &v32);
      v13 = v15;
      if ( v15 >= 0 )
      {
        v16 = CDLocateCheckSum(v28, &v30);
        v13 = v16;
        if ( v16 >= 0 )
        {
          v9 = v30;
          v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v30 + 48))(
                  *(_QWORD *)(a1 + 80),
                  *(unsigned int *)(a1 + 72),
                  (*(_DWORD *)(a1 + 104) & 4) != 0 ? 25 : 23,
                  &v27);
          if ( v13 >= 0 )
          {
            for ( j = 0; j < *(_DWORD *)(a2 + 4); ++j )
            {
              v18 = *(_QWORD *)(a2 + 8);
              if ( (*(_DWORD *)(v18 + 16LL * j + 4) & 0xFFFFFFF) != 2 && *(int *)(v18 + 16LL * j + 4) >= 0 )
              {
                v19 = *(unsigned int *)(v18 + 16LL * j);
                if ( (_DWORD)v19 )
                {
                  v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(v9 + 24))(
                          v27,
                          v19,
                          *(_QWORD *)(v18 + 16LL * j + 8));
                  if ( v13 < 0 )
                    goto LABEL_44;
                }
              }
            }
            v20 = v31;
            v13 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 *))(v9 + 24))(v27, 16, v31 - 2);
            if ( v13 >= 0 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v9 + 32))(v27, v33);
              if ( v13 >= 0 )
              {
                v21 = (*(__int64 (__fastcall **)(__int64 *))(v9 + 40))(&v27);
                v27 = 0;
                v13 = v21;
                if ( v21 < 0 )
                  return (unsigned int)v13;
                v22 = 0;
                for ( k = 0; k != 12; ++k )
                {
                  v24 = v20[k + 14];
                  v25 = v33[k];
                  v22 |= v25 ^ v24;
                }
                if ( v22 )
                {
                  if ( KsecInfoLevel )
                    KsecDebugOut(1, "SpVerifySignature bad checksum\n");
                  v13 = -2146893041;
                }
                else if ( a4 )
                {
                  *a4 = v29;
                }
              }
            }
          }
        }
        else
        {
          if ( KsecInfoLevel )
            KsecDebugOut(1, "Failed to load MD5 checksum: %#x\n", v16);
          v9 = v30;
        }
      }
      else if ( KsecInfoLevel )
      {
        KsecDebugOut(1, "Failed to verify signature token: %#x\n", v15);
      }
    }
    else
    {
      if ( KsecInfoLevel )
        KsecDebugOut(
          1,
          "no signing %#x, %s, line %d\n",
          v14,
          "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
          824);
      v13 = -1073741637;
    }
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(
        1,
        "No signature buffer found. %s, line %d\n",
        "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        813);
    v13 = -1073741811;
  }
LABEL_44:
  if ( v27 && v9 )
    (*(void (__fastcall **)(__int64 *))(v9 + 40))(&v27);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002bc00  push    rbp
0x14002bc02  push    rbx
0x14002bc03  push    rsi
0x14002bc04  push    rdi
0x14002bc05  push    r12
0x14002bc07  push    r13
0x14002bc09  push    r14
0x14002bc0b  push    r15
0x14002bc0d  lea     rbp, [rsp-1Fh]
0x14002bc12  sub     rsp, 0D8h
0x14002bc19  mov     rax, cs:__security_cookie
0x14002bc20  xor     rax, rsp
0x14002bc23  mov     [rbp+57h+var_50], rax
0x14002bc27  xor     r12d, r12d
0x14002bc2a  mov     r11d, r8d
0x14002bc2d  mov     r14, rdx
0x14002bc30  mov     [rbp+57h+var_B0], r12
0x14002bc34  mov     r15, r9
0x14002bc37  mov     [rbp+57h+var_C0], r12
0x14002bc3b  mov     rsi, rcx
0x14002bc3e  mov     [rbp+57h+var_A8], r12
0x14002bc42  lea     r13d, [r12+1]
0x14002bc47  mov     [rbp+57h+var_B8], r12d
0x14002bc4b  mov     r10d, [r14+4]
0x14002bc4f  mov     edi, r12d
0x14002bc52  mov     edx, r12d
0x14002bc55  mov     [rbp+57h+var_B4], r12d
0x14002bc59  mov     [rbp+57h+var_A0], r12
0x14002bc5d  mov     r8d, r12d
0x14002bc60  cmp     r8d, r10d
0x14002bc63  jnb     short loc_14002BCB5
0x14002bc65  mov     r9d, r8d
0x14002bc68  shl     r9, 4
0x14002bc6c  add     r9, [r14+8]
0x14002bc70  mov     eax, [r9+4]
0x14002bc74  test    eax, eax
0x14002bc76  jns     short loc_14002BC7E
0x14002bc78  bt      eax, 1Ch
0x14002bc7c  jb      short loc_14002BC8F
0x14002bc7e  and     eax, 0FFFFFFFh
0x14002bc83  cmp     eax, 2
0x14002bc86  cmovz   rdx, r9
0x14002bc8a  add     r8d, r13d
0x14002bc8d  jmp     short loc_14002BC60
0x14002bc8f  cmp     cs:KsecInfoLevel, r12d
0x14002bc96  mov     ebx, 80090308h
0x14002bc9b  jz      loc_14002BEF1
0x14002bca1  lea     rdx, aCanTHaveReadon; "Can't have readonly & readonly_w_checks"...
0x14002bca8  mov     ecx, r13d
0x14002bcab  call    KsecDebugOut
0x14002bcb0  jmp     loc_14002BED9
0x14002bcb5  test    rdx, rdx
0x14002bcb8  jnz     short loc_14002BCE9
0x14002bcba  cmp     cs:KsecInfoLevel, r12d
0x14002bcc1  jz      short loc_14002BCDF
0x14002bcc3  mov     r9d, 32Dh
0x14002bcc9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x14002bcd0  lea     rdx, aNoSignatureBuf; "No signature buffer found. %s, line %d"...
0x14002bcd7  mov     ecx, r13d
0x14002bcda  call    KsecDebugOut
0x14002bcdf  mov     ebx, 0C000000Dh
0x14002bce4  jmp     loc_14002BED9
0x14002bce9  mov     r8d, [rcx+6Ch]
0x14002bced  test    r8d, 1000Ch
0x14002bcf4  jnz     short loc_14002BD27
0x14002bcf6  cmp     cs:KsecInfoLevel, r12d
0x14002bcfd  jz      short loc_14002BD1D
0x14002bcff  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x14002bd06  mov     dword ptr [rsp+110h+var_F0], 338h
0x14002bd0e  lea     rdx, aNoSigningXSLin; "no signing %#x, %s, line %d\n"
0x14002bd15  mov     ecx, r13d
0x14002bd18  call    KsecDebugOut
0x14002bd1d  mov     ebx, 0C00000BBh
0x14002bd22  jmp     loc_14002BED9
0x14002bd27  lea     rax, [rbp+57h+var_A0]
0x14002bd2b  mov     r9, r11
0x14002bd2e  mov     [rsp+110h+var_D0], rax
0x14002bd33  xor     r8d, r8d
0x14002bd36  mov     [rsp+110h+var_D8], r12
0x14002bd3b  lea     rax, [rbp+57h+var_B8]
0x14002bd3f  mov     [rsp+110h+var_E0], rax
0x14002bd44  lea     rax, [rbp+57h+var_B4]
0x14002bd48  mov     [rsp+110h+var_E8], rax
0x14002bd4d  lea     rax, [rbp+57h+var_A8]
0x14002bd51  mov     [rsp+110h+var_F0], rax
0x14002bd56  call    WSTVerifySignatureToken
0x14002bd5b  mov     ebx, eax
0x14002bd5d  test    eax, eax
0x14002bd5f  jns     short loc_14002BD85
0x14002bd61  cmp     cs:KsecInfoLevel, r12d
0x14002bd68  jz      loc_14002BED9
0x14002bd6e  mov     r8d, eax
0x14002bd71  lea     rdx, aFailedToVerify; "Failed to verify signature token: %#x\n"
0x14002bd78  mov     ecx, r13d
0x14002bd7b  call    KsecDebugOut
0x14002bd80  jmp     loc_14002BED9
0x14002bd85  mov     ecx, [rbp+57h+var_B8]
0x14002bd88  lea     rdx, [rbp+57h+var_B0]
0x14002bd8c  call    CDLocateCheckSum
0x14002bd91  mov     ebx, eax
0x14002bd93  test    eax, eax
0x14002bd95  jns     short loc_14002BDBB
0x14002bd97  cmp     cs:KsecInfoLevel, r12d
0x14002bd9e  jz      short loc_14002BDB2
0x14002bda0  mov     r8d, eax
0x14002bda3  lea     rdx, aFailedToLoadMd; "Failed to load MD5 checksum: %#x\n"
0x14002bdaa  mov     ecx, r13d
0x14002bdad  call    KsecDebugOut
0x14002bdb2  mov     rdi, [rbp+57h+var_B0]
0x14002bdb6  jmp     loc_14002BED9
0x14002bdbb  mov     eax, [rsi+68h]
0x14002bdbe  lea     r9, [rbp+57h+var_C0]
0x14002bdc2  mov     rdi, [rbp+57h+var_B0]
0x14002bdc6  and     al, 4
0x14002bdc8  mov     edx, [rsi+48h]
0x14002bdcb  neg     al
0x14002bdcd  mov     rcx, [rsi+50h]
0x14002bdd1  sbb     r8d, r8d
0x14002bdd4  mov     rax, [rdi+30h]
0x14002bdd8  and     r8d, 2
0x14002bddc  add     r8d, 17h
0x14002bde0  call    _guard_dispatch_icall
0x14002bde5  mov     ebx, eax
0x14002bde7  test    eax, eax
0x14002bde9  js      loc_14002BED9
0x14002bdef  mov     esi, r12d
0x14002bdf2  cmp     esi, [r14+4]
0x14002bdf6  jnb     short loc_14002BE40
0x14002bdf8  mov     rcx, [r14+8]
0x14002bdfc  mov     r8d, esi
0x14002bdff  add     r8, r8
0x14002be02  mov     edx, [rcx+r8*8+4]
0x14002be07  mov     eax, edx
0x14002be09  and     eax, 0FFFFFFFh
0x14002be0e  cmp     eax, 2
0x14002be11  jz      short loc_14002BE3B
0x14002be13  test    edx, edx
0x14002be15  js      short loc_14002BE3B
0x14002be17  mov     edx, [rcx+r8*8]
0x14002be1b  test    edx, edx
0x14002be1d  jz      short loc_14002BE3B
0x14002be1f  mov     r8, [rcx+r8*8+8]
0x14002be24  mov     rcx, [rbp+57h+var_C0]
0x14002be28  mov     rax, [rdi+18h]
0x14002be2c  call    _guard_dispatch_icall
0x14002be31  mov     ebx, eax
0x14002be33  test    eax, eax
0x14002be35  js      loc_14002BED9
0x14002be3b  add     esi, r13d
0x14002be3e  jmp     short loc_14002BDF2
0x14002be40  mov     rsi, [rbp+57h+var_A8]
0x14002be44  mov     edx, 10h
0x14002be49  mov     rax, [rdi+18h]
0x14002be4d  mov     rcx, [rbp+57h+var_C0]
0x14002be51  lea     r8, [rsi-2]
0x14002be55  call    _guard_dispatch_icall
0x14002be5a  mov     ebx, eax
0x14002be5c  test    eax, eax
0x14002be5e  js      short loc_14002BED9
0x14002be60  mov     rax, [rdi+20h]
0x14002be64  lea     rdx, [rbp+57h+var_90]
0x14002be68  mov     rcx, [rbp+57h+var_C0]
0x14002be6c  call    _guard_dispatch_icall
0x14002be71  mov     ebx, eax
0x14002be73  test    eax, eax
0x14002be75  js      short loc_14002BED9
0x14002be77  mov     rax, [rdi+28h]
0x14002be7b  lea     rcx, [rbp+57h+var_C0]
0x14002be7f  call    _guard_dispatch_icall
0x14002be84  mov     [rbp+57h+var_C0], r12
0x14002be88  mov     ebx, eax
0x14002be8a  test    eax, eax
0x14002be8c  js      short loc_14002BEF1
0x14002be8e  mov     r8b, r12b
0x14002be91  mov     rdx, r12
0x14002be94  mov     cl, [rdx+rsi+0Eh]
0x14002be98  mov     al, [rbp+rdx+57h+var_90]
0x14002be9c  add     rdx, r13
0x14002be9f  xor     cl, al
0x14002bea1  or      r8b, cl
0x14002bea4  cmp     rdx, 0Ch
0x14002bea8  jnz     short loc_14002BE94
0x14002beaa  test    r8b, r8b
0x14002bead  jnz     short loc_14002BEBC
0x14002beaf  test    r15, r15
0x14002beb2  jz      short loc_14002BED9
0x14002beb4  mov     eax, [rbp+57h+var_B4]
0x14002beb7  mov     [r15], eax
0x14002beba  jmp     short loc_14002BED9
0x14002bebc  cmp     cs:KsecInfoLevel, r12d
0x14002bec3  jz      short loc_14002BED4
0x14002bec5  lea     rdx, aSpverifysignat; "SpVerifySignature bad checksum\n"
0x14002becc  mov     ecx, r13d
0x14002becf  call    KsecDebugOut
0x14002bed4  mov     ebx, 8009030Fh
0x14002bed9  cmp     [rbp+57h+var_C0], r12
0x14002bedd  jz      short loc_14002BEF1
0x14002bedf  test    rdi, rdi
0x14002bee2  jz      short loc_14002BEF1
0x14002bee4  mov     rax, [rdi+28h]
0x14002bee8  lea     rcx, [rbp+57h+var_C0]
0x14002beec  call    _guard_dispatch_icall
0x14002bef1  mov     eax, ebx
0x14002bef3  mov     rcx, [rbp+57h+var_50]
0x14002bef7  xor     rcx, rsp; StackCookie
0x14002befa  call    __security_check_cookie
0x14002beff  add     rsp, 0D8h
0x14002bf06  pop     r15
0x14002bf08  pop     r14
0x14002bf0a  pop     r13
0x14002bf0c  pop     r12
0x14002bf0e  pop     rdi
0x14002bf0f  pop     rsi
0x14002bf10  pop     rbx
0x14002bf11  pop     rbp
0x14002bf12  retn
```

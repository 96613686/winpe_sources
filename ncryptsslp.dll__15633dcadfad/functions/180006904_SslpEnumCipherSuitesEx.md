# SslpEnumCipherSuitesEx

- ea: `0x180006904`
- end: `0x180006b53`
- name: `SslpEnumCipherSuitesEx`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012b30`

## callees

- `0x180003ef0`
- `0x180006904`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x180010280`
- `0x180012c68`
- `0x180023cf8`
- `0x180025660`

## string_xrefs

- `0x180006a67`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x180006aa0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x180006ae0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`
- `0x180006b07`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`

## pseudocode

```c
__int64 __fastcall SslpEnumCipherSuitesEx(__int64 a1, int a2, __int64 *a3, _QWORD *a4)
{
  _DWORD *v4; // rbx
  _DWORD *v8; // rax
  int v9; // esi
  int v10; // ecx
  int v11; // r9d
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  _OWORD *v17; // rdx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  unsigned int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rcx

  v4 = (_DWORD *)*a4;
  if ( !*a4 )
  {
    v8 = (_DWORD *)SafeAllocaAllocateFromHeap(181840);
    v4 = v8;
    if ( v8 )
    {
      v9 = 1;
      memset(v8, 0, 0x2C650u);
      v12 = BuildCipherList(v10, a2, (int)v4 + 40, v11, (__int64)(v4 + 9));
      v13 = v12;
      if ( v12 < 0 )
      {
        DebugTraceError((unsigned int)v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", 1114);
LABEL_27:
        MSCryptFree(v4);
        return v13;
      }
      goto LABEL_4;
    }
    v22 = 1095;
    v13 = -2146893810;
    v23 = 2148073486LL;
LABEL_18:
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", v22);
    return v13;
  }
  if ( !MSCryptLookupMemoryBuffer(a1, *a4) )
  {
    v22 = 1128;
    goto LABEL_17;
  }
  v21 = v4[9];
  if ( v21 > 0xE1 || (v9 = 0, v4[8] > v21) )
  {
    v22 = 1136;
LABEL_17:
    v23 = 2148073511LL;
    v13 = -2146893785;
    goto LABEL_18;
  }
LABEL_4:
  if ( v4[8] == v4[9] )
  {
    v13 = -2146893782;
    DebugTraceError(2148073514LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", 1150);
  }
  else
  {
    v14 = SafeAllocaAllocateFromHeap(808);
    v15 = v14;
    if ( v14 )
    {
      v16 = 6;
      v17 = (_OWORD *)v14;
      v18 = &v4[202 * v4[8] + 10];
      do
      {
        *v17 = *v18;
        v17[1] = v18[1];
        v17[2] = v18[2];
        v17[3] = v18[3];
        v17[4] = v18[4];
        v17[5] = v18[5];
        v17[6] = v18[6];
        v19 = v18[7];
        v18 += 8;
        v17[7] = v19;
        v17 += 8;
        --v16;
      }
      while ( v16 );
      *v17 = *v18;
      v17[1] = v18[1];
      *((_QWORD *)v17 + 4) = *((_QWORD *)v18 + 4);
      ++v4[8];
      *a3 = v15;
      if ( v9 )
      {
        *((_QWORD *)v4 + 1) = v4;
        MSCryptAddMemoryBuffer(0, v4, v15, 128);
        *a4 = v4;
        v4 = 0;
      }
      v13 = 0;
    }
    else
    {
      v13 = -2146893810;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c",
          140);
    }
  }
  if ( v9 && v4 )
    goto LABEL_27;
  return v13;
}

```

## disassembly

```asm
0x180006904  push    rbx
0x180006906  push    rsi
0x180006907  push    rdi
0x180006908  push    r14
0x18000690a  push    r15
0x18000690c  sub     rsp, 40h
0x180006910  mov     rbx, [r9]
0x180006913  mov     r14, r9
0x180006916  mov     r15, r8
0x180006919  mov     rdi, rdx
0x18000691c  test    rbx, rbx
0x18000691f  jnz     loc_180006A34
0x180006925  mov     ecx, 2C650h
0x18000692a  call    SafeAllocaAllocateFromHeap
0x18000692f  mov     rbx, rax
0x180006932  test    rax, rax
0x180006935  jz      loc_180006AC9
0x18000693b  xor     edx, edx; Val
0x18000693d  mov     r8d, 2C650h; Size
0x180006943  mov     rcx, rax; void *
0x180006946  mov     esi, 1
0x18000694b  call    memset
0x180006950  lea     rax, [rbx+24h]
0x180006954  mov     rdx, rdi
0x180006957  lea     r8, [rbx+28h]
0x18000695b  mov     [rsp+68h+var_48], rax
0x180006960  call    BuildCipherList
0x180006965  mov     edi, eax
0x180006967  test    eax, eax
0x180006969  js      loc_180006ADA
0x18000696f  mov     eax, [rbx+24h]
0x180006972  cmp     [rbx+20h], eax
0x180006975  jz      loc_180006B02
0x18000697b  mov     ecx, 328h
0x180006980  call    SafeAllocaAllocateFromHeap
0x180006985  mov     r8, rax
0x180006988  test    rax, rax
0x18000698b  jz      loc_180006A7C
0x180006991  mov     eax, [rbx+20h]
0x180006994  mov     ecx, 6
0x180006999  imul    rax, 328h
0x1800069a0  mov     rdx, r8
0x1800069a3  lea     r9d, [rcx+7Ah]
0x1800069a7  add     rax, 28h ; '('
0x1800069ab  add     rax, rbx
0x1800069ae  movups  xmm0, xmmword ptr [rax]
0x1800069b1  movups  xmmword ptr [rdx], xmm0
0x1800069b4  movups  xmm1, xmmword ptr [rax+10h]
0x1800069b8  movups  xmmword ptr [rdx+10h], xmm1
0x1800069bc  movups  xmm0, xmmword ptr [rax+20h]
0x1800069c0  movups  xmmword ptr [rdx+20h], xmm0
0x1800069c4  movups  xmm1, xmmword ptr [rax+30h]
0x1800069c8  movups  xmmword ptr [rdx+30h], xmm1
0x1800069cc  movups  xmm0, xmmword ptr [rax+40h]
0x1800069d0  movups  xmmword ptr [rdx+40h], xmm0
0x1800069d4  movups  xmm1, xmmword ptr [rax+50h]
0x1800069d8  movups  xmmword ptr [rdx+50h], xmm1
0x1800069dc  movups  xmm0, xmmword ptr [rax+60h]
0x1800069e0  movups  xmmword ptr [rdx+60h], xmm0
0x1800069e4  movups  xmm1, xmmword ptr [rax+70h]
0x1800069e8  add     rax, r9
0x1800069eb  movups  xmmword ptr [rdx+70h], xmm1
0x1800069ef  add     rdx, r9
0x1800069f2  sub     rcx, 1
0x1800069f6  jnz     short loc_1800069AE
0x1800069f8  movups  xmm0, xmmword ptr [rax]
0x1800069fb  movups  xmmword ptr [rdx], xmm0
0x1800069fe  movups  xmm1, xmmword ptr [rax+10h]
0x180006a02  movups  xmmword ptr [rdx+10h], xmm1
0x180006a06  mov     rax, [rax+20h]
0x180006a0a  mov     [rdx+20h], rax
0x180006a0e  inc     dword ptr [rbx+20h]
0x180006a11  mov     [r15], r8
0x180006a14  test    esi, esi
0x180006a16  jnz     loc_180006B27
0x180006a1c  xor     edi, edi
0x180006a1e  test    esi, esi
0x180006a20  jnz     loc_180006B3D
0x180006a26  mov     eax, edi
0x180006a28  add     rsp, 40h
0x180006a2c  pop     r15
0x180006a2e  pop     r14
0x180006a30  pop     rdi
0x180006a31  pop     rsi
0x180006a32  pop     rbx
0x180006a33  retn
0x180006a34  mov     rdx, rbx
0x180006a37  call    MSCryptLookupMemoryBuffer
0x180006a3c  test    rax, rax
0x180006a3f  jz      loc_180006AF7
0x180006a45  mov     eax, [rbx+24h]
0x180006a48  cmp     eax, 0E1h
0x180006a4d  ja      short loc_180006A5A
0x180006a4f  xor     esi, esi
0x180006a51  cmp     [rbx+20h], eax
0x180006a54  jbe     loc_18000696F
0x180006a5a  mov     r9d, 470h
0x180006a60  mov     ecx, 80090027h
0x180006a65  mov     edi, ecx
0x180006a67  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006a6e  lea     rdx, aStatus; "Status"
0x180006a75  call    DebugTraceError
0x180006a7a  jmp     short loc_180006A26
0x180006a7c  mov     eax, 8009000Eh
0x180006a81  mov     edi, eax
0x180006a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a8a  lea     rdx, WPP_GLOBAL_Control
0x180006a91  cmp     rcx, rdx
0x180006a94  jz      short loc_180006A1E
0x180006a96  test    byte ptr [rcx+1Ch], 1
0x180006a9a  jz      short loc_180006A1E
0x180006a9c  mov     rcx, [rcx+10h]
0x180006aa0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006aa7  mov     [rsp+68h+var_38], 48Ch
0x180006aaf  lea     r9, aStatus; "Status"
0x180006ab6  mov     [rsp+68h+var_40], r8
0x180006abb  mov     dword ptr [rsp+68h+var_48], eax
0x180006abf  call    WPP_SF_sDsd
0x180006ac4  jmp     loc_180006A1E
0x180006ac9  mov     eax, 8009000Eh
0x180006ace  mov     r9d, 447h
0x180006ad4  mov     edi, eax
0x180006ad6  mov     ecx, eax
0x180006ad8  jmp     short loc_180006A67
0x180006ada  mov     r9d, 45Ah
0x180006ae0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006ae7  lea     rdx, aStatus; "Status"
0x180006aee  mov     ecx, eax
0x180006af0  call    DebugTraceError
0x180006af5  jmp     short loc_180006B46
0x180006af7  mov     r9d, 468h
0x180006afd  jmp     loc_180006A60
0x180006b02  mov     edi, 8009002Ah
0x180006b07  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006b0e  mov     ecx, edi
0x180006b10  lea     rdx, aStatus; "Status"
0x180006b17  mov     r9d, 47Eh
0x180006b1d  call    DebugTraceError
0x180006b22  jmp     loc_180006A1E
0x180006b27  mov     rdx, rbx
0x180006b2a  mov     [rbx+8], rbx
0x180006b2e  call    MSCryptAddMemoryBuffer
0x180006b33  mov     [r14], rbx
0x180006b36  xor     ebx, ebx
0x180006b38  jmp     loc_180006A1C
0x180006b3d  test    rbx, rbx
0x180006b40  jz      loc_180006A26
0x180006b46  mov     rcx, rbx
0x180006b49  call    MSCryptFree
0x180006b4e  jmp     loc_180006A26
```

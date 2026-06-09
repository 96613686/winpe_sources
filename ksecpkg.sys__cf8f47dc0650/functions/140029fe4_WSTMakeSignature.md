# WSTMakeSignature

- ea: `0x140029fe4`
- end: `0x14002a2de`
- name: `WSTMakeSignature`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400290b0`

## callees

- `0x140007008`
- `0x140010160`
- `0x140010240`
- `0x1400261e0`
- `0x140029f74`
- `0x140029fe4`
- `0x14002a2e4`
- `0x14002c874`

## string_xrefs

- `0x14002a0ac`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002a0e2`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002a084`: `Can't have readonly & readonly_w_checksum\n`

## pseudocode

```c
__int64 __fastcall WSTMakeSignature(__int64 a1, int a2, __int64 a3, char a4)
{
  unsigned int v5; // r9d
  __int64 v9; // rdi
  __int64 v10; // rsi
  unsigned int i; // edx
  int v12; // eax
  int v13; // ebx
  int v14; // r8d
  int v15; // edx
  int v16; // r9d
  int v17; // eax
  unsigned int v18; // ecx
  int v19; // eax
  unsigned int v20; // ecx
  unsigned int j; // esi
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rsi
  int v25; // eax
  __int64 v27; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v30; // [rsp+60h] [rbp-59h] BYREF
  __int64 v31; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v33; // [rsp+80h] [rbp-39h] BYREF
  int v34; // [rsp+88h] [rbp-31h]

  v5 = *(_DWORD *)(a3 + 4);
  v30 = 0;
  v27 = 0;
  v31 = 0;
  v9 = 0;
  v28 = 0;
  v10 = 0;
  v29 = 0;
  v32[0] = 0;
  for ( i = 0; i < v5; ++i )
  {
    v12 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * i + 4);
    if ( v12 < 0 && (v12 & 0x10000000) != 0 )
    {
      v13 = -2146893048;
      if ( !KsecInfoLevel )
        return (unsigned int)v13;
      KsecDebugOut(1, "Can't have readonly & readonly_w_checksum\n");
      goto LABEL_39;
    }
    if ( (v12 & 0xFFFFFFF) == 2 )
      v10 = *(_QWORD *)(a3 + 8) + 16LL * i;
  }
  if ( !v10 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(
        1,
        "No signature buffer found. %s, line %d\n",
        "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        584);
    v13 = -1073741811;
    goto LABEL_39;
  }
  v14 = *(_DWORD *)(a1 + 108);
  if ( (v14 & 0x1000C) == 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(
        1,
        "no signing context attributes %#x, %s, line %d\n",
        v14,
        "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        595);
    v13 = -1073741637;
    goto LABEL_39;
  }
  v13 = WSTGetChecksumAndEncryptionType(a1, 0, a2, (unsigned int)&v28, (__int64)&v29);
  if ( v13 < 0 )
    return (unsigned int)v13;
  v13 = WSTMakeSignatureToken(a1, a2, v10, v16, v15, a4, v15, (__int64)&v31, (__int64)v32);
  if ( v13 < 0 )
    goto LABEL_39;
  v17 = CDLocateCheckSum(v28, &v30);
  v13 = v17;
  if ( v17 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to load %d checksum: 0x%x.\n", v18, (unsigned int)v17);
LABEL_23:
    v9 = v30;
    goto LABEL_39;
  }
  v19 = CDLocateCSystem(v29, v32);
  v13 = v19;
  if ( v19 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to load %d crypt system: %#x\n", v20, (unsigned int)v19);
    goto LABEL_23;
  }
  v9 = v30;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v30 + 48))(
          *(_QWORD *)(a1 + 80),
          *(unsigned int *)(a1 + 72),
          (*(_DWORD *)(a1 + 104) & 2) != 0 ? 25 : 23,
          &v27);
  if ( v13 >= 0 )
  {
    for ( j = 0; j < *(_DWORD *)(a3 + 4); ++j )
    {
      v22 = *(_QWORD *)(a3 + 8);
      if ( (*(_DWORD *)(v22 + 16LL * j + 4) & 0xFFFFFFF) != 2 && *(int *)(v22 + 16LL * j + 4) >= 0 )
      {
        v23 = *(unsigned int *)(v22 + 16LL * j);
        if ( (_DWORD)v23 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(v9 + 24))(
                  v27,
                  v23,
                  *(_QWORD *)(v22 + 16LL * j + 8));
          if ( v13 < 0 )
            goto LABEL_39;
        }
      }
    }
    v24 = v31;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v9 + 24))(v27, 16, v31 - 2);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v9 + 32))(v27, &v33);
      if ( v13 >= 0 )
      {
        v25 = (*(__int64 (__fastcall **)(__int64 *))(v9 + 40))(&v27);
        v27 = 0;
        v13 = v25;
        if ( v25 < 0 )
          return (unsigned int)v13;
        *(_QWORD *)(v24 + 14) = v33;
        *(_DWORD *)(v24 + 22) = v34;
      }
    }
  }
LABEL_39:
  if ( v27 && v9 )
    (*(void (__fastcall **)(__int64 *))(v9 + 40))(&v27);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140029fe4  push    rbp
0x140029fe6  push    rbx
0x140029fe7  push    rsi
0x140029fe8  push    rdi
0x140029fe9  push    r12
0x140029feb  push    r13
0x140029fed  push    r14
0x140029fef  push    r15
0x140029ff1  lea     rbp, [rsp-1Fh]
0x140029ff6  sub     rsp, 0D8h
0x140029ffd  mov     rax, cs:__security_cookie
0x14002a004  xor     rax, rsp
0x14002a007  mov     [rbp+57h+var_50], rax
0x14002a00b  xor     r10d, r10d
0x14002a00e  mov     r13d, r9d
0x14002a011  mov     r9d, [r8+4]
0x14002a015  mov     r12d, edx
0x14002a018  mov     r15, r8
0x14002a01b  mov     [rbp+57h+var_B0], r10
0x14002a01f  mov     r14, rcx
0x14002a022  mov     [rbp+57h+var_C0], r10
0x14002a026  lea     r11d, [r10+1]
0x14002a02a  mov     [rbp+57h+var_A8], r10
0x14002a02e  mov     edi, r10d
0x14002a031  mov     [rbp+57h+var_B8], r10d
0x14002a035  mov     esi, r10d
0x14002a038  mov     [rbp+57h+var_B4], r10d
0x14002a03c  mov     [rbp+57h+var_A0], r10
0x14002a040  mov     edx, r10d
0x14002a043  cmp     edx, r9d
0x14002a046  jnb     short loc_14002A098
0x14002a048  mov     r8d, edx
0x14002a04b  shl     r8, 4
0x14002a04f  add     r8, [r15+8]
0x14002a053  mov     eax, [r8+4]
0x14002a057  test    eax, eax
0x14002a059  jns     short loc_14002A061
0x14002a05b  bt      eax, 1Ch
0x14002a05f  jb      short loc_14002A072
0x14002a061  and     eax, 0FFFFFFFh
0x14002a066  cmp     eax, 2
0x14002a069  cmovz   rsi, r8
0x14002a06d  add     edx, r11d
0x14002a070  jmp     short loc_14002A043
0x14002a072  cmp     cs:KsecInfoLevel, r10d
0x14002a079  mov     ebx, 80090308h
0x14002a07e  jz      loc_14002A2BB
0x14002a084  lea     rdx, aCanTHaveReadon; "Can't have readonly & readonly_w_checks"...
0x14002a08b  mov     ecx, r11d
0x14002a08e  call    KsecDebugOut
0x14002a093  jmp     loc_14002A2A2
0x14002a098  test    rsi, rsi
0x14002a09b  jnz     short loc_14002A0CC
0x14002a09d  cmp     cs:KsecInfoLevel, r10d
0x14002a0a4  jz      short loc_14002A0C2
0x14002a0a6  mov     r9d, 248h
0x14002a0ac  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x14002a0b3  lea     rdx, aNoSignatureBuf; "No signature buffer found. %s, line %d"...
0x14002a0ba  mov     ecx, r11d
0x14002a0bd  call    KsecDebugOut
0x14002a0c2  mov     ebx, 0C000000Dh
0x14002a0c7  jmp     loc_14002A2A2
0x14002a0cc  mov     r8d, [rcx+6Ch]
0x14002a0d0  test    r8d, 1000Ch
0x14002a0d7  jnz     short loc_14002A10A
0x14002a0d9  cmp     cs:KsecInfoLevel, r10d
0x14002a0e0  jz      short loc_14002A100
0x14002a0e2  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x14002a0e9  mov     dword ptr [rsp+110h+var_F0], 253h
0x14002a0f1  lea     rdx, aNoSigningConte; "no signing context attributes %#x, %s, "...
0x14002a0f8  mov     ecx, r11d
0x14002a0fb  call    KsecDebugOut
0x14002a100  mov     ebx, 0C00000BBh
0x14002a105  jmp     loc_14002A2A2
0x14002a10a  lea     rax, [rbp+57h+var_B4]
0x14002a10e  mov     r8d, r12d
0x14002a111  lea     r9, [rbp+57h+var_B8]
0x14002a115  mov     [rsp+110h+var_F0], rax
0x14002a11a  xor     edx, edx
0x14002a11c  call    WSTGetChecksumAndEncryptionType
0x14002a121  mov     ebx, eax
0x14002a123  test    eax, eax
0x14002a125  js      loc_14002A2BB
0x14002a12b  lea     rcx, [rbp+57h+var_A0]
0x14002a12f  mov     r8, rsi
0x14002a132  mov     [rsp+110h+var_D0], rcx
0x14002a137  lea     rcx, [rbp+57h+var_A8]
0x14002a13b  mov     [rsp+110h+var_D8], rcx
0x14002a140  mov     rcx, r14
0x14002a143  mov     [rsp+110h+var_E0], edx
0x14002a147  mov     [rsp+110h+var_E8], r13
0x14002a14c  mov     byte ptr [rsp+110h+var_F0], dl
0x14002a150  mov     edx, r12d
0x14002a153  call    WSTMakeSignatureToken
0x14002a158  mov     ebx, eax
0x14002a15a  test    eax, eax
0x14002a15c  js      loc_14002A2A2
0x14002a162  mov     ecx, [rbp+57h+var_B8]
0x14002a165  lea     rdx, [rbp+57h+var_B0]
0x14002a169  call    CDLocateCheckSum
0x14002a16e  mov     ebx, eax
0x14002a170  test    eax, eax
0x14002a172  jns     short loc_14002A19C
0x14002a174  cmp     cs:KsecInfoLevel, edi
0x14002a17a  jz      short loc_14002A193
0x14002a17c  lea     rdx, aFailedToLoadDC_1; "Failed to load %d checksum: 0x%x.\n"
0x14002a183  mov     r8d, ecx
0x14002a186  mov     r9d, eax
0x14002a189  mov     ecx, 1
0x14002a18e  call    KsecDebugOut
0x14002a193  mov     rdi, [rbp+57h+var_B0]
0x14002a197  jmp     loc_14002A2A2
0x14002a19c  mov     ecx, [rbp+57h+var_B4]
0x14002a19f  lea     rdx, [rbp+57h+var_A0]
0x14002a1a3  call    CDLocateCSystem
0x14002a1a8  mov     ebx, eax
0x14002a1aa  test    eax, eax
0x14002a1ac  jns     short loc_14002A1BF
0x14002a1ae  cmp     cs:KsecInfoLevel, edi
0x14002a1b4  jz      short loc_14002A193
0x14002a1b6  lea     rdx, aFailedToLoadDC_0; "Failed to load %d crypt system: %#x\n"
0x14002a1bd  jmp     short loc_14002A183
0x14002a1bf  mov     eax, [r14+68h]
0x14002a1c3  lea     r9, [rbp+57h+var_C0]
0x14002a1c7  mov     rdi, [rbp+57h+var_B0]
0x14002a1cb  and     al, 2
0x14002a1cd  mov     edx, [r14+48h]
0x14002a1d1  neg     al
0x14002a1d3  mov     rcx, [r14+50h]
0x14002a1d7  sbb     r8d, r8d
0x14002a1da  mov     rax, [rdi+30h]
0x14002a1de  and     r8d, 2
0x14002a1e2  add     r8d, 17h
0x14002a1e6  call    _guard_dispatch_icall
0x14002a1eb  mov     ebx, eax
0x14002a1ed  test    eax, eax
0x14002a1ef  js      loc_14002A2A2
0x14002a1f5  xor     esi, esi
0x14002a1f7  cmp     esi, [r15+4]
0x14002a1fb  jnb     short loc_14002A240
0x14002a1fd  mov     rcx, [r15+8]
0x14002a201  mov     r8d, esi
0x14002a204  add     r8, r8
0x14002a207  mov     edx, [rcx+r8*8+4]
0x14002a20c  mov     eax, edx
0x14002a20e  and     eax, 0FFFFFFFh
0x14002a213  cmp     eax, 2
0x14002a216  jz      short loc_14002A23C
0x14002a218  test    edx, edx
0x14002a21a  js      short loc_14002A23C
0x14002a21c  mov     edx, [rcx+r8*8]
0x14002a220  test    edx, edx
0x14002a222  jz      short loc_14002A23C
0x14002a224  mov     r8, [rcx+r8*8+8]
0x14002a229  mov     rcx, [rbp+57h+var_C0]
0x14002a22d  mov     rax, [rdi+18h]
0x14002a231  call    _guard_dispatch_icall
0x14002a236  mov     ebx, eax
0x14002a238  test    eax, eax
0x14002a23a  js      short loc_14002A2A2
0x14002a23c  inc     esi
0x14002a23e  jmp     short loc_14002A1F7
0x14002a240  mov     rsi, [rbp+57h+var_A8]
0x14002a244  mov     edx, 10h
0x14002a249  mov     rax, [rdi+18h]
0x14002a24d  mov     rcx, [rbp+57h+var_C0]
0x14002a251  lea     r8, [rsi-2]
0x14002a255  call    _guard_dispatch_icall
0x14002a25a  mov     ebx, eax
0x14002a25c  test    eax, eax
0x14002a25e  js      short loc_14002A2A2
0x14002a260  mov     rax, [rdi+20h]
0x14002a264  lea     rdx, [rbp+57h+var_90]
0x14002a268  mov     rcx, [rbp+57h+var_C0]
0x14002a26c  call    _guard_dispatch_icall
0x14002a271  mov     ebx, eax
0x14002a273  test    eax, eax
0x14002a275  js      short loc_14002A2A2
0x14002a277  mov     rax, [rdi+28h]
0x14002a27b  lea     rcx, [rbp+57h+var_C0]
0x14002a27f  call    _guard_dispatch_icall
0x14002a284  mov     [rbp+57h+var_C0], 0
0x14002a28c  mov     ebx, eax
0x14002a28e  test    eax, eax
0x14002a290  js      short loc_14002A2BB
0x14002a292  movsd   xmm0, [rbp+57h+var_90]
0x14002a297  movsd   qword ptr [rsi+0Eh], xmm0
0x14002a29c  mov     eax, [rbp+57h+var_88]
0x14002a29f  mov     [rsi+16h], eax
0x14002a2a2  cmp     [rbp+57h+var_C0], 0
0x14002a2a7  jz      short loc_14002A2BB
0x14002a2a9  test    rdi, rdi
0x14002a2ac  jz      short loc_14002A2BB
0x14002a2ae  mov     rax, [rdi+28h]
0x14002a2b2  lea     rcx, [rbp+57h+var_C0]
0x14002a2b6  call    _guard_dispatch_icall
0x14002a2bb  mov     eax, ebx
0x14002a2bd  mov     rcx, [rbp+57h+var_50]
0x14002a2c1  xor     rcx, rsp; StackCookie
0x14002a2c4  call    __security_check_cookie
0x14002a2c9  add     rsp, 0D8h
0x14002a2d0  pop     r15
0x14002a2d2  pop     r14
0x14002a2d4  pop     r13
0x14002a2d6  pop     r12
0x14002a2d8  pop     rdi
0x14002a2d9  pop     rsi
0x14002a2da  pop     rbx
0x14002a2db  pop     rbp
0x14002a2dc  retn
```

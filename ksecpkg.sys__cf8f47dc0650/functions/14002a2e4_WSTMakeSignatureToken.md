# WSTMakeSignatureToken

- ea: `0x14002a2e4`
- end: `0x14002a469`
- name: `WSTMakeSignatureToken`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140029fe4`
- `0x14002a4d8`

## callees

- `0x140007008`
- `0x14002a2e4`

## string_xrefs

- `0x14002a35b`: `WSTMakeSignatureToken CFX buffer too small %d, expected %d!\n`

## pseudocode

```c
__int64 __fastcall WSTMakeSignatureToken(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        char a6,
        int a7,
        _QWORD *a8,
        __int64 *a9)
{
  __int16 v10; // r11
  int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // r8d
  int v15; // esi
  __int64 v16; // rcx
  _BYTE *v17; // rbx
  int v18; // eax
  char *v19; // rdx
  __int64 v20; // rcx
  bool v21; // zf
  __int64 v22; // rcx
  _QWORD *v23; // rcx

  v10 = a7;
  if ( a5 && (v12 = a7 + 58, a2 != -2147483647) || (v12 = 26, a2 != -2147483647) || a5 )
  {
    v14 = *(_DWORD *)a3;
    v15 = v12 + 2;
    if ( v14 >= v12 + 2 )
    {
      v16 = *(_QWORD *)(a3 + 8);
      v13 = 0;
      v17 = (_BYTE *)(v16 + 2);
      *(_BYTE *)v16 = (a5 != 0) + 4;
      *(_BYTE *)(v16 + 1) = 4;
      *(_BYTE *)(v16 + 2) = 0;
      if ( a5 )
      {
        *(_BYTE *)(v16 + 3) = -1;
        *(_BYTE *)(v16 + 4) = HIBYTE(v10);
        *(_BYTE *)(v16 + 5) = v10;
        *(_WORD *)(v16 + 6) = 0;
      }
      else
      {
        *(_DWORD *)(v16 + 3) = -1;
        *(_BYTE *)(v16 + 7) = -1;
      }
      if ( (*(_DWORD *)(a1 + 104) & 4) != 0 )
        *v17 |= 1u;
      v18 = *(_DWORD *)(a1 + 108);
      if ( (v18 & 0x400) != 0 || (v19 = (char *)(a1 + 88), (v18 & 0x1000C) == 0x10000) )
        v19 = &a6;
      v20 = HIDWORD(*(_QWORD *)v19);
      v17[9] = v20;
      v17[6] = BYTE3(v20);
      v17[7] = BYTE2(v20);
      v17[8] = BYTE1(v20);
      v17[10] = v19[3];
      v17[11] = v19[2];
      v17[12] = v19[1];
      v17[13] = *v19;
      ++*(_QWORD *)v19;
      v21 = KsecInfoLevel == 0;
      v22 = *(_QWORD *)(v17 + 6);
      *a9 = v22;
      if ( !v21 )
        KsecDebugOut(16, "Making signature buffer (encrypt = %d) with nonce 0x%I64x\n", a5, v22);
      v23 = a8;
      *(_DWORD *)a3 = v15;
      *v23 = v17;
    }
    else
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "WSTMakeSignatureToken CFX buffer too small %d, expected %d!\n", v14, v15);
      return (unsigned int)-1073741789;
    }
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "KERB_WRAP_NO_ENCRYPT flag passed to MakeSignature!\n");
    return (unsigned int)-1073741811;
  }
  return v13;
}

```

## disassembly

```asm
0x14002a2e4  push    rbx
0x14002a2e6  push    rsi
0x14002a2e7  push    rdi
0x14002a2e8  push    r14
0x14002a2ea  sub     rsp, 28h
0x14002a2ee  movzx   r9d, [rsp+48h+arg_20]
0x14002a2f4  mov     r10, rcx
0x14002a2f7  mov     r11d, [rsp+48h+arg_30]
0x14002a2ff  mov     r14, r8
0x14002a302  mov     ecx, 80000001h
0x14002a307  test    r9b, r9b
0x14002a30a  jz      short loc_14002A314
0x14002a30c  lea     rax, [r11+3Ah]
0x14002a310  cmp     edx, ecx
0x14002a312  jnz     short loc_14002A344
0x14002a314  mov     eax, 1Ah
0x14002a319  cmp     edx, ecx
0x14002a31b  jnz     short loc_14002A344
0x14002a31d  test    r9b, r9b
0x14002a320  jnz     short loc_14002A344
0x14002a322  cmp     cs:KsecInfoLevel, 0
0x14002a329  jz      short loc_14002A33A
0x14002a32b  lea     rdx, aKerbWrapNoEncr; "KERB_WRAP_NO_ENCRYPT flag passed to Mak"...
0x14002a332  lea     ecx, [rax-19h]
0x14002a335  call    KsecDebugOut
0x14002a33a  mov     edi, 0C000000Dh
0x14002a33f  jmp     loc_14002A45C
0x14002a344  mov     r8d, [r8]
0x14002a347  lea     esi, [rax+2]
0x14002a34a  cmp     r8d, esi
0x14002a34d  jnb     short loc_14002A376
0x14002a34f  cmp     cs:KsecInfoLevel, 0
0x14002a356  jz      short loc_14002A36C
0x14002a358  mov     r9d, esi
0x14002a35b  lea     rdx, aWstmakesignatu; "WSTMakeSignatureToken CFX buffer too sm"...
0x14002a362  mov     ecx, 1
0x14002a367  call    KsecDebugOut
0x14002a36c  mov     edi, 0C0000023h
0x14002a371  jmp     loc_14002A45C
0x14002a376  mov     rcx, [r14+8]
0x14002a37a  xor     edi, edi
0x14002a37c  test    r9b, r9b
0x14002a37f  setnz   al
0x14002a382  add     al, 4
0x14002a384  lea     rbx, [rcx+2]
0x14002a388  mov     [rcx], al
0x14002a38a  mov     byte ptr [rcx+1], 4
0x14002a38e  mov     [rbx], dil
0x14002a391  test    r9b, r9b
0x14002a394  jz      short loc_14002A3AF
0x14002a396  mov     byte ptr [rbx+1], 0FFh
0x14002a39a  mov     eax, r11d
0x14002a39d  shr     eax, 8
0x14002a3a0  mov     [rbx+2], al
0x14002a3a3  xor     eax, eax
0x14002a3a5  mov     [rbx+3], r11b
0x14002a3a9  mov     [rbx+4], ax
0x14002a3ad  jmp     short loc_14002A3BA
0x14002a3af  mov     dword ptr [rbx+1], 0FFFFFFFFh
0x14002a3b6  mov     byte ptr [rbx+5], 0FFh
0x14002a3ba  mov     eax, [r10+68h]
0x14002a3be  test    al, 4
0x14002a3c0  jz      short loc_14002A3C5
0x14002a3c2  or      byte ptr [rbx], 1
0x14002a3c5  mov     eax, [r10+6Ch]
0x14002a3c9  bt      eax, 0Ah
0x14002a3cd  jb      short loc_14002A3DF
0x14002a3cf  and     eax, 1000Ch
0x14002a3d4  lea     rdx, [r10+58h]
0x14002a3d8  cmp     eax, 10000h
0x14002a3dd  jnz     short loc_14002A3E4
0x14002a3df  lea     rdx, [rsp+48h+arg_28]
0x14002a3e4  mov     rcx, [rdx]
0x14002a3e7  shr     rcx, 20h
0x14002a3eb  mov     [rbx+9], cl
0x14002a3ee  mov     eax, ecx
0x14002a3f0  shr     eax, 18h
0x14002a3f3  mov     [rbx+6], al
0x14002a3f6  mov     eax, ecx
0x14002a3f8  shr     eax, 10h
0x14002a3fb  mov     [rbx+7], al
0x14002a3fe  mov     eax, ecx
0x14002a400  shr     eax, 8
0x14002a403  mov     [rbx+8], al
0x14002a406  mov     al, [rdx+3]
0x14002a409  mov     [rbx+0Ah], al
0x14002a40c  mov     al, [rdx+2]
0x14002a40f  mov     [rbx+0Bh], al
0x14002a412  mov     al, [rdx+1]
0x14002a415  mov     [rbx+0Ch], al
0x14002a418  mov     al, [rdx]
0x14002a41a  mov     [rbx+0Dh], al
0x14002a41d  inc     qword ptr [rdx]
0x14002a420  cmp     cs:KsecInfoLevel, edi
0x14002a426  mov     rax, [rsp+48h+arg_40]
0x14002a42e  mov     rcx, [rbx+6]
0x14002a432  mov     [rax], rcx
0x14002a435  jz      short loc_14002A44E
0x14002a437  mov     r8d, r9d
0x14002a43a  lea     rdx, aMakingSignatur; "Making signature buffer (encrypt = %d) "...
0x14002a441  mov     r9, rcx
0x14002a444  mov     ecx, 10h
0x14002a449  call    KsecDebugOut
0x14002a44e  mov     rcx, [rsp+48h+arg_38]
0x14002a456  mov     [r14], esi
0x14002a459  mov     [rcx], rbx
0x14002a45c  mov     eax, edi
0x14002a45e  add     rsp, 28h
0x14002a462  pop     r14
0x14002a464  pop     rdi
0x14002a465  pop     rsi
0x14002a466  pop     rbx
0x14002a467  retn
```

# HsmpBitmapIsReparseBufferSupported

- ea: `0x14006a13c`
- end: `0x14006a789`
- name: `HsmpBitmapIsReparseBufferSupported`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140069920`

## callees

- `0x140003c50`
- `0x14000d908`
- `0x14000d95c`
- `0x14000db8c`
- `0x14001880c`
- `0x14001e280`
- `0x14006a13c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14006a205`
- `ntoskrnl!RtlComputeCrc32` at `0x14006a205`

## pseudocode

```c
__int64 __fastcall HsmpBitmapIsReparseBufferSupported(__int64 a1, unsigned int a2)
{
  unsigned __int8 v4; // r13
  unsigned __int8 v5; // r12
  unsigned int v6; // edi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  UCHAR *v9; // rdi
  unsigned int v10; // r14d
  unsigned __int64 v11; // rcx
  __int64 v12; // r8
  unsigned __int64 v13; // rbx
  unsigned int i; // r11d
  unsigned int v15; // eax
  unsigned __int64 v16; // r9
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned __int16 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // edx
  __int64 v23; // rax
  unsigned __int16 v24; // r8
  unsigned __int64 v25; // r9
  unsigned int v26; // eax
  int v27; // ebx
  unsigned int v28; // r8d
  __int64 v29; // rax
  unsigned __int16 v30; // r9
  unsigned __int64 v31; // rdx
  unsigned int v32; // eax
  unsigned __int8 v34; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 v35; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int8 v36; // [rsp+88h] [rbp+20h] BYREF

  v36 = 0;
  v35 = 0;
  v4 = 0;
  v5 = 0;
  if ( !a1 )
  {
    v6 = -1073688830;
    HsmDbgBreakOnStatus(3221278466LL);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 159;
LABEL_6:
      WPP_SF_d(v7->AttachedDevice, v8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids, 3221278466LL);
      return v6;
    }
    return v6;
  }
  v34 = 0;
  if ( a2 < 0x18 )
  {
    v10 = 0;
    goto LABEL_106;
  }
  if ( *(_DWORD *)a1 != 1884451906 )
  {
    v10 = 1;
    goto LABEL_106;
  }
  v9 = (UCHAR *)(a1 + 8);
  if ( (*(_BYTE *)(a1 + 12) & 2) != 0 )
  {
    v10 = 2;
    if ( *(_DWORD *)(a1 + 4) != RtlComputeCrc32(0, v9, a2 - 8) )
    {
LABEL_106:
      HsmDbgBreakOnCorruption();
      v6 = -1073688830;
      HsmDbgBreakOnStatus(3221278466LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          160,
          WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
          v10,
          -1073688830);
      }
      return v6;
    }
  }
  v11 = *(unsigned int *)v9;
  if ( a2 < (unsigned int)v11 )
  {
    v10 = 3;
    goto LABEL_106;
  }
  v12 = *(unsigned __int16 *)(a1 + 14);
  if ( !(_WORD)v12 )
  {
    v10 = 4;
    goto LABEL_106;
  }
  v13 = 8 * v12 + 16;
  if ( v13 >= v11 )
  {
    v10 = 5;
    goto LABEL_106;
  }
  v10 = 0x10000;
  for ( i = 0; ; ++i )
  {
    v15 = *(unsigned __int16 *)(a1 + 14);
    if ( (unsigned __int16)v12 >= 5u )
      v15 = 5;
    if ( i >= v15 )
      break;
    if ( *(_WORD *)(a1 + 8LL * i + 16) >= 0x12u )
      goto LABEL_106;
    v16 = *(unsigned int *)(a1 + 8LL * i + 20);
    if ( (_DWORD)v16 )
    {
      if ( v16 < v13 )
        goto LABEL_106;
    }
    if ( (unsigned int)v16 > (unsigned int)v11 )
      goto LABEL_106;
    v17 = *(unsigned __int16 *)(a1 + 8LL * i + 18);
    if ( v17 > (unsigned int)v11 )
      goto LABEL_106;
    v18 = v16 + v17;
    if ( v18 < (unsigned int)v16 || v18 > (unsigned int)v11 )
      goto LABEL_106;
    ++v10;
  }
  v10 = 0x20000;
  if ( (unsigned int)v11 < 0x18 )
    goto LABEL_106;
  v19 = *(_WORD *)(a1 + 16);
  if ( v19 >= 0x12u )
    goto LABEL_106;
  v20 = *(unsigned int *)(a1 + 20);
  if ( (_DWORD)v20 )
  {
    if ( v20 < v13 || (unsigned int)v20 > (unsigned int)v11 )
      goto LABEL_106;
  }
  v21 = *(unsigned __int16 *)(a1 + 18);
  if ( v21 > (unsigned int)v11
    || v21 + (unsigned int)v20 < (unsigned int)v20
    || v21 + (unsigned int)v20 > (unsigned int)v11
    || v19 != 7
    || (_WORD)v21 != 1 )
  {
    goto LABEL_106;
  }
  memmove(&v34, (const void *)(a1 + v20), *(unsigned __int16 *)(a1 + 18));
  if ( v34 > 1u )
  {
    v10 = 131073;
    goto LABEL_106;
  }
  v22 = *(_DWORD *)(a1 + 8);
  v6 = -1073741275;
  if ( v22 >= 0x18
    && (v23 = *(unsigned __int16 *)(a1 + 14), (unsigned __int16)v23 > 2u)
    && v22 >= 0x28
    && (v24 = *(_WORD *)(a1 + 32), v24 < 0x12u)
    && ((v25 = *(unsigned int *)(a1 + 36), !(_DWORD)v25) || v25 >= 8 * v23 + 16 && (unsigned int)v25 <= v22)
    && (v26 = *(unsigned __int16 *)(a1 + 34), v26 <= v22)
    && v26 + (unsigned int)v25 >= (unsigned int)v25
    && v26 + (unsigned int)v25 <= v22
    && v24 == 7
    && (_WORD)v26 == 1 )
  {
    memmove(&v35, (const void *)(a1 + v25), *(unsigned __int16 *)(a1 + 34));
    v5 = v35;
    v27 = 0;
  }
  else
  {
    v27 = -1073741275;
  }
  HsmDbgBreakOnStatus((unsigned int)v27);
  if ( v27 >= 0 )
  {
    if ( v5 )
    {
      if ( *(_WORD *)(a1 + 14) < 4u )
      {
        HsmDbgBreakOnCorruption();
        v6 = -1073688830;
        HsmDbgBreakOnStatus(3221278466LL);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v8 = 162;
          goto LABEL_6;
        }
        return v6;
      }
      if ( !*(_DWORD *)(a1 + 52) )
      {
        HsmDbgBreakOnCorruption();
        v6 = -1073688830;
        HsmDbgBreakOnStatus(3221278466LL);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v8 = 163;
          goto LABEL_6;
        }
        return v6;
      }
      if ( *(_WORD *)(a1 + 50) > 0x1000u )
      {
        HsmDbgBreakOnCorruption();
        v6 = -1073688830;
        HsmDbgBreakOnStatus(3221278466LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDd(
            WPP_GLOBAL_Control->AttachedDevice,
            164,
            WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
            *(unsigned __int16 *)(a1 + 50),
            4096,
            -1073688830);
        }
        return v6;
      }
    }
    if ( v5 <= 1u )
    {
      v28 = *(_DWORD *)(a1 + 8);
      if ( v28 >= 0x18 )
      {
        v29 = *(unsigned __int16 *)(a1 + 14);
        if ( (unsigned __int16)v29 > 1u && v28 >= 0x20 )
        {
          v30 = *(_WORD *)(a1 + 24);
          if ( v30 < 0x12u )
          {
            v31 = *(unsigned int *)(a1 + 28);
            if ( !(_DWORD)v31 || v31 >= 8 * v29 + 16 && (unsigned int)v31 <= v28 )
            {
              v32 = *(unsigned __int16 *)(a1 + 26);
              if ( v32 <= v28
                && v32 + (unsigned int)v31 >= (unsigned int)v31
                && v32 + (unsigned int)v31 <= v28
                && v30 == 7
                && (_WORD)v32 == 1 )
              {
                memmove(&v36, (const void *)(a1 + v31), *(unsigned __int16 *)(a1 + 26));
                v4 = v36;
                v6 = 0;
              }
            }
          }
        }
      }
      HsmDbgBreakOnStatus(v6);
      if ( (v6 & 0x80000000) == 0 )
      {
        if ( (unsigned __int8)(v4 - 1) > 0x13u )
        {
          HsmDbgBreakOnCorruption();
          v6 = -1073688830;
          HsmDbgBreakOnStatus(3221278466LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              167,
              WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
              v4,
              -1073688830);
          }
        }
      }
      else
      {
        HsmDbgBreakOnCorruption();
        v6 = -1073688830;
        HsmDbgBreakOnStatus(3221278466LL);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v8 = 166;
          goto LABEL_6;
        }
      }
    }
    else
    {
      HsmDbgBreakOnCorruption();
      v6 = -1073688830;
      HsmDbgBreakOnStatus(3221278466LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          165,
          WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
          v5,
          1,
          -1073688830);
      }
    }
    return v6;
  }
  HsmDbgBreakOnCorruption();
  v6 = -1073688830;
  HsmDbgBreakOnStatus(3221278466LL);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = 161;
    goto LABEL_6;
  }
  return v6;
}

```

## disassembly

```asm
0x14006a13c  mov     rax, rsp
0x14006a13f  mov     [rax+10h], rbx
0x14006a143  push    rbp
0x14006a144  push    rsi
0x14006a145  push    rdi
0x14006a146  push    r12
0x14006a148  push    r13
0x14006a14a  push    r14
0x14006a14c  push    r15
0x14006a14e  sub     rsp, 30h
0x14006a152  xor     r10d, r10d
0x14006a155  mov     ebx, edx
0x14006a157  mov     [rax+20h], r10b
0x14006a15b  mov     rsi, rcx
0x14006a15e  mov     [rax+18h], r10b
0x14006a162  mov     r13b, r10b
0x14006a165  mov     r12b, r10b
0x14006a168  test    rcx, rcx
0x14006a16b  jnz     short loc_14006A1CC
0x14006a16d  mov     ebx, 0C000CF02h
0x14006a172  mov     ecx, ebx
0x14006a174  mov     edi, ebx
0x14006a176  call    HsmDbgBreakOnStatus
0x14006a17b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a182  lea     rax, WPP_GLOBAL_Control
0x14006a189  cmp     rcx, rax
0x14006a18c  jz      loc_14006A771
0x14006a192  mov     eax, [rcx+2Ch]
0x14006a195  lea     ebp, [rsi+1]
0x14006a198  test    bpl, al
0x14006a19b  jz      loc_14006A771
0x14006a1a1  lea     r15d, [rsi+2]
0x14006a1a5  cmp     [rcx+29h], r15b
0x14006a1a9  jb      loc_14006A771
0x14006a1af  mov     edx, 9Fh
0x14006a1b4  mov     rcx, [rcx+18h]
0x14006a1b8  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a1bf  mov     r9d, ebx
0x14006a1c2  call    WPP_SF_d
0x14006a1c7  jmp     loc_14006A771
0x14006a1cc  mov     [rsp+68h+arg_0], r10b
0x14006a1d1  mov     ebp, 1
0x14006a1d6  lea     r15d, [rbp+1]
0x14006a1da  cmp     ebx, 18h
0x14006a1dd  jb      loc_14006A71E
0x14006a1e3  cmp     dword ptr [rcx], 70527442h
0x14006a1e9  jnz     loc_14006A719
0x14006a1ef  lea     rdi, [rcx+8]
0x14006a1f3  test    [rcx+0Ch], r15b
0x14006a1f7  jz      short loc_14006A21D
0x14006a1f9  lea     r8d, [rdx-8]; Length
0x14006a1fd  xor     ecx, ecx; InitialCrc
0x14006a1ff  mov     rdx, rdi; Buffer
0x14006a202  mov     r14d, r15d
0x14006a205  call    cs:__imp_RtlComputeCrc32
0x14006a20c  nop     dword ptr [rax+rax+00h]
0x14006a211  cmp     [rsi+4], eax
0x14006a214  jnz     loc_14006A721
0x14006a21a  xor     r10d, r10d
0x14006a21d  mov     ecx, [rdi]
0x14006a21f  cmp     ebx, ecx
0x14006a221  jb      loc_14006A711
0x14006a227  movzx   r8d, word ptr [rsi+0Eh]
0x14006a22c  test    r8w, r8w
0x14006a230  jz      loc_14006A709
0x14006a236  lea     rbx, ds:10h[r8*8]
0x14006a23e  cmp     rbx, rcx
0x14006a241  jnb     loc_14006A701
0x14006a247  mov     r14d, 10000h
0x14006a24d  mov     r11d, r10d
0x14006a250  mov     edx, 5
0x14006a255  mov     eax, r8d
0x14006a258  cmp     r8w, dx
0x14006a25c  jb      short loc_14006A260
0x14006a25e  mov     eax, edx
0x14006a260  cmp     r11d, eax
0x14006a263  jnb     short loc_14006A2BB
0x14006a265  mov     r10d, r11d
0x14006a268  cmp     word ptr [rsi+r10*8+10h], 12h
0x14006a26f  jnb     loc_14006A721
0x14006a275  mov     r9d, [rsi+r10*8+14h]
0x14006a27a  test    r9d, r9d
0x14006a27d  jz      short loc_14006A288
0x14006a27f  cmp     r9, rbx
0x14006a282  jb      loc_14006A721
0x14006a288  cmp     r9d, ecx
0x14006a28b  ja      loc_14006A721
0x14006a291  movzx   eax, word ptr [rsi+r10*8+12h]
0x14006a297  cmp     eax, ecx
0x14006a299  ja      loc_14006A721
0x14006a29f  add     eax, r9d
0x14006a2a2  cmp     eax, r9d
0x14006a2a5  jb      loc_14006A721
0x14006a2ab  cmp     eax, ecx
0x14006a2ad  ja      loc_14006A721
0x14006a2b3  add     r14d, ebp
0x14006a2b6  add     r11d, ebp
0x14006a2b9  jmp     short loc_14006A255
0x14006a2bb  mov     r14d, 20000h
0x14006a2c1  cmp     ecx, 18h
0x14006a2c4  jb      loc_14006A721
0x14006a2ca  xor     r10d, r10d
0x14006a2cd  cmp     r10w, r8w
0x14006a2d1  jnb     loc_14006A721
0x14006a2d7  movzx   r9d, word ptr [rsi+10h]
0x14006a2dc  cmp     r9w, 12h
0x14006a2e1  jnb     loc_14006A721
0x14006a2e7  mov     edx, [rsi+14h]
0x14006a2ea  test    edx, edx
0x14006a2ec  jz      short loc_14006A2FF
0x14006a2ee  cmp     rdx, rbx
0x14006a2f1  jb      loc_14006A721
0x14006a2f7  cmp     edx, ecx
0x14006a2f9  ja      loc_14006A721
0x14006a2ff  movzx   eax, word ptr [rsi+12h]
0x14006a303  cmp     eax, ecx
0x14006a305  ja      loc_14006A721
0x14006a30b  lea     r8d, [rax+rdx]
0x14006a30f  cmp     r8d, edx
0x14006a312  jb      loc_14006A721
0x14006a318  cmp     r8d, ecx
0x14006a31b  ja      loc_14006A721
0x14006a321  cmp     r9w, 7
0x14006a326  jnz     loc_14006A721
0x14006a32c  cmp     ax, bp
0x14006a32f  jnz     loc_14006A721
0x14006a335  mov     r8d, eax; Size
0x14006a338  lea     rcx, [rsp+68h+arg_0]; void *
0x14006a33d  add     rdx, rsi; Src
0x14006a340  call    memmove
0x14006a345  cmp     [rsp+68h+arg_0], bpl
0x14006a34a  ja      loc_14006A6F9
0x14006a350  mov     edx, [rsi+8]
0x14006a353  mov     edi, 0C0000225h
0x14006a358  cmp     edx, 18h
0x14006a35b  jb      short loc_14006A3D4
0x14006a35d  movzx   eax, word ptr [rsi+0Eh]
0x14006a361  cmp     r15w, ax
0x14006a365  jnb     short loc_14006A3D4
0x14006a367  cmp     edx, 28h ; '('
0x14006a36a  jb      short loc_14006A3D4
0x14006a36c  movzx   r8d, word ptr [rsi+20h]
0x14006a371  cmp     r8w, 12h
0x14006a376  jnb     short loc_14006A3D4
0x14006a378  mov     r9d, [rsi+24h]
0x14006a37c  test    r9d, r9d
0x14006a37f  jz      short loc_14006A393
0x14006a381  lea     rcx, ds:10h[rax*8]
0x14006a389  cmp     r9, rcx
0x14006a38c  jb      short loc_14006A3D4
0x14006a38e  cmp     r9d, edx
0x14006a391  ja      short loc_14006A3D4
0x14006a393  movzx   eax, word ptr [rsi+22h]
0x14006a397  cmp     eax, edx
0x14006a399  ja      short loc_14006A3D4
0x14006a39b  lea     ecx, [rax+r9]
0x14006a39f  cmp     ecx, r9d
0x14006a3a2  jb      short loc_14006A3D4
0x14006a3a4  cmp     ecx, edx
0x14006a3a6  ja      short loc_14006A3D4
0x14006a3a8  cmp     r8w, 7
0x14006a3ad  jnz     short loc_14006A3D4
0x14006a3af  cmp     ax, bp
0x14006a3b2  jnz     short loc_14006A3D4
0x14006a3b4  mov     r8d, eax; Size
0x14006a3b7  lea     rdx, [rsi+r9]; Src
0x14006a3bb  lea     rcx, [rsp+68h+arg_10]; void *
0x14006a3c3  call    memmove
0x14006a3c8  mov     r12b, [rsp+68h+arg_10]
0x14006a3d0  xor     ebx, ebx
0x14006a3d2  jmp     short loc_14006A3D6
0x14006a3d4  mov     ebx, edi
0x14006a3d6  mov     ecx, ebx
0x14006a3d8  call    HsmDbgBreakOnStatus
0x14006a3dd  test    ebx, ebx
0x14006a3df  jns     short loc_14006A42B
0x14006a3e1  call    HsmDbgBreakOnCorruption
0x14006a3e6  mov     ebx, 0C000CF02h
0x14006a3eb  mov     ecx, ebx
0x14006a3ed  mov     edi, ebx
0x14006a3ef  call    HsmDbgBreakOnStatus
0x14006a3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a3fb  lea     rax, WPP_GLOBAL_Control
0x14006a402  cmp     rcx, rax
0x14006a405  jz      loc_14006A771
0x14006a40b  mov     eax, [rcx+2Ch]
0x14006a40e  test    bpl, al
0x14006a411  jz      loc_14006A771
0x14006a417  cmp     [rcx+29h], r15b
0x14006a41b  jb      loc_14006A771
0x14006a421  mov     edx, 0A1h
0x14006a426  jmp     loc_14006A1B4
0x14006a42b  test    r12b, r12b
0x14006a42e  jz      loc_14006A550
0x14006a434  mov     r14d, 4
0x14006a43a  cmp     [rsi+0Eh], r14w
0x14006a43f  jnb     short loc_14006A48B
0x14006a441  call    HsmDbgBreakOnCorruption
0x14006a446  mov     ebx, 0C000CF02h
0x14006a44b  mov     ecx, ebx
0x14006a44d  mov     edi, ebx
0x14006a44f  call    HsmDbgBreakOnStatus
0x14006a454  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a45b  lea     rax, WPP_GLOBAL_Control
0x14006a462  cmp     rcx, rax
0x14006a465  jz      loc_14006A771
0x14006a46b  mov     eax, [rcx+2Ch]
0x14006a46e  test    bpl, al
0x14006a471  jz      loc_14006A771
0x14006a477  cmp     [rcx+29h], r15b
0x14006a47b  jb      loc_14006A771
0x14006a481  mov     edx, 0A2h
0x14006a486  jmp     loc_14006A1B4
0x14006a48b  cmp     dword ptr [rsi+34h], 0
0x14006a48f  jnz     short loc_14006A4DB
0x14006a491  call    HsmDbgBreakOnCorruption
0x14006a496  mov     ebx, 0C000CF02h
0x14006a49b  mov     ecx, ebx
0x14006a49d  mov     edi, ebx
0x14006a49f  call    HsmDbgBreakOnStatus
0x14006a4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4ab  lea     rax, WPP_GLOBAL_Control
0x14006a4b2  cmp     rcx, rax
0x14006a4b5  jz      loc_14006A771
0x14006a4bb  mov     eax, [rcx+2Ch]
0x14006a4be  test    bpl, al
0x14006a4c1  jz      loc_14006A771
0x14006a4c7  cmp     [rcx+29h], r15b
0x14006a4cb  jb      loc_14006A771
0x14006a4d1  mov     edx, 0A3h
0x14006a4d6  jmp     loc_14006A1B4
0x14006a4db  mov     r14d, 1000h
0x14006a4e1  cmp     [rsi+32h], r14w
0x14006a4e6  jbe     short loc_14006A550
0x14006a4e8  call    HsmDbgBreakOnCorruption
0x14006a4ed  mov     ebx, 0C000CF02h
0x14006a4f2  mov     ecx, ebx
0x14006a4f4  mov     edi, ebx
0x14006a4f6  call    HsmDbgBreakOnStatus
0x14006a4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a502  lea     rax, WPP_GLOBAL_Control
0x14006a509  cmp     rcx, rax
0x14006a50c  jz      loc_14006A771
0x14006a512  mov     eax, [rcx+2Ch]
0x14006a515  test    bpl, al
0x14006a518  jz      loc_14006A771
0x14006a51e  cmp     [rcx+29h], r15b
0x14006a522  jb      loc_14006A771
0x14006a528  movzx   r9d, word ptr [rsi+32h]
0x14006a52d  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a534  mov     rcx, [rcx+18h]
0x14006a538  mov     edx, 0A4h
0x14006a53d  mov     [rsp+68h+var_40], ebx
0x14006a541  mov     [rsp+68h+var_48], r14d
0x14006a546  call    WPP_SF_DDd
0x14006a54b  jmp     loc_14006A771
0x14006a550  cmp     r12b, bpl
0x14006a553  jbe     short loc_14006A5BB
0x14006a555  call    HsmDbgBreakOnCorruption
0x14006a55a  mov     ebx, 0C000CF02h
0x14006a55f  mov     ecx, ebx
0x14006a561  mov     edi, ebx
0x14006a563  call    HsmDbgBreakOnStatus
0x14006a568  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a56f  lea     rax, WPP_GLOBAL_Control
0x14006a576  cmp     rcx, rax
0x14006a579  jz      loc_14006A771
0x14006a57f  mov     eax, [rcx+2Ch]
0x14006a582  test    bpl, al
0x14006a585  jz      loc_14006A771
0x14006a58b  cmp     [rcx+29h], r15b
0x14006a58f  jb      loc_14006A771
0x14006a595  mov     rcx, [rcx+18h]
0x14006a599  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a5a0  movzx   r9d, r12b
0x14006a5a4  mov     edx, 0A5h
0x14006a5a9  mov     [rsp+68h+var_40], ebx
0x14006a5ad  mov     [rsp+68h+var_48], ebp
0x14006a5b1  call    WPP_SF_DDd
0x14006a5b6  jmp     loc_14006A771
0x14006a5bb  mov     r8d, [rsi+8]
0x14006a5bf  cmp     r8d, 18h
0x14006a5c3  jb      short loc_14006A637
0x14006a5c5  movzx   eax, word ptr [rsi+0Eh]
0x14006a5c9  cmp     bp, ax
0x14006a5cc  jnb     short loc_14006A637
0x14006a5ce  cmp     r8d, 20h ; ' '
0x14006a5d2  jb      short loc_14006A637
0x14006a5d4  movzx   r9d, word ptr [rsi+18h]
0x14006a5d9  cmp     r9w, 12h
0x14006a5de  jnb     short loc_14006A637
0x14006a5e0  mov     edx, [rsi+1Ch]
0x14006a5e3  test    edx, edx
0x14006a5e5  jz      short loc_14006A5F9
0x14006a5e7  lea     rcx, ds:10h[rax*8]
0x14006a5ef  cmp     rdx, rcx
0x14006a5f2  jb      short loc_14006A637
0x14006a5f4  cmp     edx, r8d
0x14006a5f7  ja      short loc_14006A637
0x14006a5f9  movzx   eax, word ptr [rsi+1Ah]
  ... truncated ...
```

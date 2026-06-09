# HsmpBitmapIsReparseBufferSupported

- ea: `0x14006a25c`
- end: `0x14006a8a9`
- name: `HsmpBitmapIsReparseBufferSupported`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140069a40`

## callees

- `0x140003c50`
- `0x14000d908`
- `0x14000d95c`
- `0x14000db8c`
- `0x14001888c`
- `0x14001e300`
- `0x14006a25c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14006a325`
- `ntoskrnl!RtlComputeCrc32` at `0x14006a325`

## pseudocode

```c
__int64 __fastcall HsmpBitmapIsReparseBufferSupported(__int64 a1, unsigned int a2)
{
  char v4; // r13
  unsigned __int8 v5; // r12
  unsigned int v6; // edi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  UCHAR *v9; // rdi
  unsigned __int64 v10; // rcx
  __int64 v11; // r8
  unsigned __int64 v12; // rbx
  int v13; // r14d
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
  char v36; // [rsp+88h] [rbp+20h] BYREF

  v36 = 0;
  v35 = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 )
  {
    v34 = 0;
    if ( a2 < 0x18 )
      goto LABEL_100;
    if ( *(_DWORD *)a1 != 1884451906 )
      goto LABEL_100;
    v9 = (UCHAR *)(a1 + 8);
    if ( (*(_BYTE *)(a1 + 12) & 2) != 0 && *(_DWORD *)(a1 + 4) != RtlComputeCrc32(0, v9, a2 - 8) )
      goto LABEL_100;
    v10 = *(unsigned int *)v9;
    if ( a2 < (unsigned int)v10 )
      goto LABEL_100;
    v11 = *(unsigned __int16 *)(a1 + 14);
    if ( !(_WORD)v11 )
      goto LABEL_100;
    v12 = 8 * v11 + 16;
    if ( v12 >= v10 )
      goto LABEL_100;
    v13 = 0x10000;
    for ( i = 0; ; ++i )
    {
      v15 = *(unsigned __int16 *)(a1 + 14);
      if ( (unsigned __int16)v11 >= 5u )
        v15 = 5;
      if ( i >= v15 )
        break;
      if ( *(_WORD *)(a1 + 8LL * i + 16) >= 0x12u )
        goto LABEL_100;
      v16 = *(unsigned int *)(a1 + 8LL * i + 20);
      if ( (_DWORD)v16 )
      {
        if ( v16 < v12 )
          goto LABEL_100;
      }
      if ( (unsigned int)v16 > (unsigned int)v10 )
        goto LABEL_100;
      v17 = *(unsigned __int16 *)(a1 + 8LL * i + 18);
      if ( v17 > (unsigned int)v10 )
        goto LABEL_100;
      v18 = v16 + v17;
      if ( v18 < (unsigned int)v16 || v18 > (unsigned int)v10 )
        goto LABEL_100;
      ++v13;
    }
    if ( (unsigned int)v10 < 0x18
      || (v19 = *(_WORD *)(a1 + 16), v19 >= 0x12u)
      || (v20 = *(unsigned int *)(a1 + 20), (_DWORD)v20) && (v20 < v12 || (unsigned int)v20 > (unsigned int)v10)
      || (v21 = *(unsigned __int16 *)(a1 + 18), v21 > (unsigned int)v10)
      || v21 + (unsigned int)v20 < (unsigned int)v20
      || v21 + (unsigned int)v20 > (unsigned int)v10
      || v19 != 7
      || (_WORD)v21 != 1
      || (memmove(&v34, (const void *)(a1 + v20), *(unsigned __int16 *)(a1 + 18)), v34 > 1u) )
    {
LABEL_100:
      HsmDbgBreakOnCorruption();
      v6 = -1073688830;
      HsmDbgBreakOnStatus(-1073688830);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids);
      }
      return v6;
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
    HsmDbgBreakOnStatus(v27);
    if ( v27 >= 0 )
    {
      if ( v5 )
      {
        if ( *(_WORD *)(a1 + 14) < 4u )
        {
          HsmDbgBreakOnCorruption();
          v6 = -1073688830;
          HsmDbgBreakOnStatus(-1073688830);
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
          HsmDbgBreakOnStatus(-1073688830);
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
          HsmDbgBreakOnStatus(-1073688830);
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
            HsmDbgBreakOnStatus(-1073688830);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids);
            }
          }
        }
        else
        {
          HsmDbgBreakOnCorruption();
          v6 = -1073688830;
          HsmDbgBreakOnStatus(-1073688830);
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
        HsmDbgBreakOnStatus(-1073688830);
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
    HsmDbgBreakOnStatus(-1073688830);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 161;
      goto LABEL_6;
    }
  }
  else
  {
    v6 = -1073688830;
    HsmDbgBreakOnStatus(-1073688830);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 159;
LABEL_6:
      WPP_SF_d(v7->AttachedDevice, v8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids, 3221278466LL);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14006a25c  mov     rax, rsp
0x14006a25f  mov     [rax+10h], rbx
0x14006a263  push    rbp
0x14006a264  push    rsi
0x14006a265  push    rdi
0x14006a266  push    r12
0x14006a268  push    r13
0x14006a26a  push    r14
0x14006a26c  push    r15
0x14006a26e  sub     rsp, 30h
0x14006a272  xor     r10d, r10d
0x14006a275  mov     ebx, edx
0x14006a277  mov     [rax+20h], r10b
0x14006a27b  mov     rsi, rcx
0x14006a27e  mov     [rax+18h], r10b
0x14006a282  mov     r13b, r10b
0x14006a285  mov     r12b, r10b
0x14006a288  test    rcx, rcx
0x14006a28b  jnz     short loc_14006A2EC
0x14006a28d  mov     ebx, 0C000CF02h
0x14006a292  mov     ecx, ebx
0x14006a294  mov     edi, ebx
0x14006a296  call    HsmDbgBreakOnStatus
0x14006a29b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a2a2  lea     rax, WPP_GLOBAL_Control
0x14006a2a9  cmp     rcx, rax
0x14006a2ac  jz      loc_14006A891
0x14006a2b2  mov     eax, [rcx+2Ch]
0x14006a2b5  lea     ebp, [rsi+1]
0x14006a2b8  test    bpl, al
0x14006a2bb  jz      loc_14006A891
0x14006a2c1  lea     r15d, [rsi+2]
0x14006a2c5  cmp     [rcx+29h], r15b
0x14006a2c9  jb      loc_14006A891
0x14006a2cf  mov     edx, 9Fh
0x14006a2d4  mov     rcx, [rcx+18h]
0x14006a2d8  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a2df  mov     r9d, ebx
0x14006a2e2  call    WPP_SF_d
0x14006a2e7  jmp     loc_14006A891
0x14006a2ec  mov     [rsp+68h+arg_0], r10b
0x14006a2f1  mov     ebp, 1
0x14006a2f6  lea     r15d, [rbp+1]
0x14006a2fa  cmp     ebx, 18h
0x14006a2fd  jb      loc_14006A83E
0x14006a303  cmp     dword ptr [rcx], 70527442h
0x14006a309  jnz     loc_14006A839
0x14006a30f  lea     rdi, [rcx+8]
0x14006a313  test    [rcx+0Ch], r15b
0x14006a317  jz      short loc_14006A33D
0x14006a319  lea     r8d, [rdx-8]; Length
0x14006a31d  xor     ecx, ecx; InitialCrc
0x14006a31f  mov     rdx, rdi; Buffer
0x14006a322  mov     r14d, r15d
0x14006a325  call    cs:__imp_RtlComputeCrc32
0x14006a32c  nop     dword ptr [rax+rax+00h]
0x14006a331  cmp     [rsi+4], eax
0x14006a334  jnz     loc_14006A841
0x14006a33a  xor     r10d, r10d
0x14006a33d  mov     ecx, [rdi]
0x14006a33f  cmp     ebx, ecx
0x14006a341  jb      loc_14006A831
0x14006a347  movzx   r8d, word ptr [rsi+0Eh]
0x14006a34c  test    r8w, r8w
0x14006a350  jz      loc_14006A829
0x14006a356  lea     rbx, ds:10h[r8*8]
0x14006a35e  cmp     rbx, rcx
0x14006a361  jnb     loc_14006A821
0x14006a367  mov     r14d, 10000h
0x14006a36d  mov     r11d, r10d
0x14006a370  mov     edx, 5
0x14006a375  mov     eax, r8d
0x14006a378  cmp     r8w, dx
0x14006a37c  jb      short loc_14006A380
0x14006a37e  mov     eax, edx
0x14006a380  cmp     r11d, eax
0x14006a383  jnb     short loc_14006A3DB
0x14006a385  mov     r10d, r11d
0x14006a388  cmp     word ptr [rsi+r10*8+10h], 12h
0x14006a38f  jnb     loc_14006A841
0x14006a395  mov     r9d, [rsi+r10*8+14h]
0x14006a39a  test    r9d, r9d
0x14006a39d  jz      short loc_14006A3A8
0x14006a39f  cmp     r9, rbx
0x14006a3a2  jb      loc_14006A841
0x14006a3a8  cmp     r9d, ecx
0x14006a3ab  ja      loc_14006A841
0x14006a3b1  movzx   eax, word ptr [rsi+r10*8+12h]
0x14006a3b7  cmp     eax, ecx
0x14006a3b9  ja      loc_14006A841
0x14006a3bf  add     eax, r9d
0x14006a3c2  cmp     eax, r9d
0x14006a3c5  jb      loc_14006A841
0x14006a3cb  cmp     eax, ecx
0x14006a3cd  ja      loc_14006A841
0x14006a3d3  add     r14d, ebp
0x14006a3d6  add     r11d, ebp
0x14006a3d9  jmp     short loc_14006A375
0x14006a3db  mov     r14d, 20000h
0x14006a3e1  cmp     ecx, 18h
0x14006a3e4  jb      loc_14006A841
0x14006a3ea  xor     r10d, r10d
0x14006a3ed  cmp     r10w, r8w
0x14006a3f1  jnb     loc_14006A841
0x14006a3f7  movzx   r9d, word ptr [rsi+10h]
0x14006a3fc  cmp     r9w, 12h
0x14006a401  jnb     loc_14006A841
0x14006a407  mov     edx, [rsi+14h]
0x14006a40a  test    edx, edx
0x14006a40c  jz      short loc_14006A41F
0x14006a40e  cmp     rdx, rbx
0x14006a411  jb      loc_14006A841
0x14006a417  cmp     edx, ecx
0x14006a419  ja      loc_14006A841
0x14006a41f  movzx   eax, word ptr [rsi+12h]
0x14006a423  cmp     eax, ecx
0x14006a425  ja      loc_14006A841
0x14006a42b  lea     r8d, [rax+rdx]
0x14006a42f  cmp     r8d, edx
0x14006a432  jb      loc_14006A841
0x14006a438  cmp     r8d, ecx
0x14006a43b  ja      loc_14006A841
0x14006a441  cmp     r9w, 7
0x14006a446  jnz     loc_14006A841
0x14006a44c  cmp     ax, bp
0x14006a44f  jnz     loc_14006A841
0x14006a455  mov     r8d, eax; Size
0x14006a458  lea     rcx, [rsp+68h+arg_0]; void *
0x14006a45d  add     rdx, rsi; Src
0x14006a460  call    memmove
0x14006a465  cmp     [rsp+68h+arg_0], bpl
0x14006a46a  ja      loc_14006A819
0x14006a470  mov     edx, [rsi+8]
0x14006a473  mov     edi, 0C0000225h
0x14006a478  cmp     edx, 18h
0x14006a47b  jb      short loc_14006A4F4
0x14006a47d  movzx   eax, word ptr [rsi+0Eh]
0x14006a481  cmp     r15w, ax
0x14006a485  jnb     short loc_14006A4F4
0x14006a487  cmp     edx, 28h ; '('
0x14006a48a  jb      short loc_14006A4F4
0x14006a48c  movzx   r8d, word ptr [rsi+20h]
0x14006a491  cmp     r8w, 12h
0x14006a496  jnb     short loc_14006A4F4
0x14006a498  mov     r9d, [rsi+24h]
0x14006a49c  test    r9d, r9d
0x14006a49f  jz      short loc_14006A4B3
0x14006a4a1  lea     rcx, ds:10h[rax*8]
0x14006a4a9  cmp     r9, rcx
0x14006a4ac  jb      short loc_14006A4F4
0x14006a4ae  cmp     r9d, edx
0x14006a4b1  ja      short loc_14006A4F4
0x14006a4b3  movzx   eax, word ptr [rsi+22h]
0x14006a4b7  cmp     eax, edx
0x14006a4b9  ja      short loc_14006A4F4
0x14006a4bb  lea     ecx, [rax+r9]
0x14006a4bf  cmp     ecx, r9d
0x14006a4c2  jb      short loc_14006A4F4
0x14006a4c4  cmp     ecx, edx
0x14006a4c6  ja      short loc_14006A4F4
0x14006a4c8  cmp     r8w, 7
0x14006a4cd  jnz     short loc_14006A4F4
0x14006a4cf  cmp     ax, bp
0x14006a4d2  jnz     short loc_14006A4F4
0x14006a4d4  mov     r8d, eax; Size
0x14006a4d7  lea     rdx, [rsi+r9]; Src
0x14006a4db  lea     rcx, [rsp+68h+arg_10]; void *
0x14006a4e3  call    memmove
0x14006a4e8  mov     r12b, [rsp+68h+arg_10]
0x14006a4f0  xor     ebx, ebx
0x14006a4f2  jmp     short loc_14006A4F6
0x14006a4f4  mov     ebx, edi
0x14006a4f6  mov     ecx, ebx
0x14006a4f8  call    HsmDbgBreakOnStatus
0x14006a4fd  test    ebx, ebx
0x14006a4ff  jns     short loc_14006A54B
0x14006a501  call    HsmDbgBreakOnCorruption
0x14006a506  mov     ebx, 0C000CF02h
0x14006a50b  mov     ecx, ebx
0x14006a50d  mov     edi, ebx
0x14006a50f  call    HsmDbgBreakOnStatus
0x14006a514  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a51b  lea     rax, WPP_GLOBAL_Control
0x14006a522  cmp     rcx, rax
0x14006a525  jz      loc_14006A891
0x14006a52b  mov     eax, [rcx+2Ch]
0x14006a52e  test    bpl, al
0x14006a531  jz      loc_14006A891
0x14006a537  cmp     [rcx+29h], r15b
0x14006a53b  jb      loc_14006A891
0x14006a541  mov     edx, 0A1h
0x14006a546  jmp     loc_14006A2D4
0x14006a54b  test    r12b, r12b
0x14006a54e  jz      loc_14006A670
0x14006a554  mov     r14d, 4
0x14006a55a  cmp     [rsi+0Eh], r14w
0x14006a55f  jnb     short loc_14006A5AB
0x14006a561  call    HsmDbgBreakOnCorruption
0x14006a566  mov     ebx, 0C000CF02h
0x14006a56b  mov     ecx, ebx
0x14006a56d  mov     edi, ebx
0x14006a56f  call    HsmDbgBreakOnStatus
0x14006a574  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a57b  lea     rax, WPP_GLOBAL_Control
0x14006a582  cmp     rcx, rax
0x14006a585  jz      loc_14006A891
0x14006a58b  mov     eax, [rcx+2Ch]
0x14006a58e  test    bpl, al
0x14006a591  jz      loc_14006A891
0x14006a597  cmp     [rcx+29h], r15b
0x14006a59b  jb      loc_14006A891
0x14006a5a1  mov     edx, 0A2h
0x14006a5a6  jmp     loc_14006A2D4
0x14006a5ab  cmp     dword ptr [rsi+34h], 0
0x14006a5af  jnz     short loc_14006A5FB
0x14006a5b1  call    HsmDbgBreakOnCorruption
0x14006a5b6  mov     ebx, 0C000CF02h
0x14006a5bb  mov     ecx, ebx
0x14006a5bd  mov     edi, ebx
0x14006a5bf  call    HsmDbgBreakOnStatus
0x14006a5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a5cb  lea     rax, WPP_GLOBAL_Control
0x14006a5d2  cmp     rcx, rax
0x14006a5d5  jz      loc_14006A891
0x14006a5db  mov     eax, [rcx+2Ch]
0x14006a5de  test    bpl, al
0x14006a5e1  jz      loc_14006A891
0x14006a5e7  cmp     [rcx+29h], r15b
0x14006a5eb  jb      loc_14006A891
0x14006a5f1  mov     edx, 0A3h
0x14006a5f6  jmp     loc_14006A2D4
0x14006a5fb  mov     r14d, 1000h
0x14006a601  cmp     [rsi+32h], r14w
0x14006a606  jbe     short loc_14006A670
0x14006a608  call    HsmDbgBreakOnCorruption
0x14006a60d  mov     ebx, 0C000CF02h
0x14006a612  mov     ecx, ebx
0x14006a614  mov     edi, ebx
0x14006a616  call    HsmDbgBreakOnStatus
0x14006a61b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a622  lea     rax, WPP_GLOBAL_Control
0x14006a629  cmp     rcx, rax
0x14006a62c  jz      loc_14006A891
0x14006a632  mov     eax, [rcx+2Ch]
0x14006a635  test    bpl, al
0x14006a638  jz      loc_14006A891
0x14006a63e  cmp     [rcx+29h], r15b
0x14006a642  jb      loc_14006A891
0x14006a648  movzx   r9d, word ptr [rsi+32h]
0x14006a64d  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a654  mov     rcx, [rcx+18h]
0x14006a658  mov     edx, 0A4h
0x14006a65d  mov     [rsp+68h+var_40], ebx
0x14006a661  mov     [rsp+68h+var_48], r14d
0x14006a666  call    WPP_SF_DDd
0x14006a66b  jmp     loc_14006A891
0x14006a670  cmp     r12b, bpl
0x14006a673  jbe     short loc_14006A6DB
0x14006a675  call    HsmDbgBreakOnCorruption
0x14006a67a  mov     ebx, 0C000CF02h
0x14006a67f  mov     ecx, ebx
0x14006a681  mov     edi, ebx
0x14006a683  call    HsmDbgBreakOnStatus
0x14006a688  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a68f  lea     rax, WPP_GLOBAL_Control
0x14006a696  cmp     rcx, rax
0x14006a699  jz      loc_14006A891
0x14006a69f  mov     eax, [rcx+2Ch]
0x14006a6a2  test    bpl, al
0x14006a6a5  jz      loc_14006A891
0x14006a6ab  cmp     [rcx+29h], r15b
0x14006a6af  jb      loc_14006A891
0x14006a6b5  mov     rcx, [rcx+18h]
0x14006a6b9  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006a6c0  movzx   r9d, r12b
0x14006a6c4  mov     edx, 0A5h
0x14006a6c9  mov     [rsp+68h+var_40], ebx
0x14006a6cd  mov     [rsp+68h+var_48], ebp
0x14006a6d1  call    WPP_SF_DDd
0x14006a6d6  jmp     loc_14006A891
0x14006a6db  mov     r8d, [rsi+8]
0x14006a6df  cmp     r8d, 18h
0x14006a6e3  jb      short loc_14006A757
0x14006a6e5  movzx   eax, word ptr [rsi+0Eh]
0x14006a6e9  cmp     bp, ax
0x14006a6ec  jnb     short loc_14006A757
0x14006a6ee  cmp     r8d, 20h ; ' '
0x14006a6f2  jb      short loc_14006A757
0x14006a6f4  movzx   r9d, word ptr [rsi+18h]
0x14006a6f9  cmp     r9w, 12h
0x14006a6fe  jnb     short loc_14006A757
0x14006a700  mov     edx, [rsi+1Ch]
0x14006a703  test    edx, edx
0x14006a705  jz      short loc_14006A719
0x14006a707  lea     rcx, ds:10h[rax*8]
0x14006a70f  cmp     rdx, rcx
0x14006a712  jb      short loc_14006A757
0x14006a714  cmp     edx, r8d
0x14006a717  ja      short loc_14006A757
0x14006a719  movzx   eax, word ptr [rsi+1Ah]
  ... truncated ...
```

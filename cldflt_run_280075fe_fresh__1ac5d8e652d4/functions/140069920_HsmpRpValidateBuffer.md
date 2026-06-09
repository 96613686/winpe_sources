# HsmpRpValidateBuffer

- ea: `0x140069920`
- end: `0x14006a133`
- name: `HsmpRpValidateBuffer`
- size: `2067`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140059648`
- `0x140067d04`

## callees

- `0x140003c50`
- `0x14000d908`
- `0x14000d95c`
- `0x14000db8c`
- `0x140069920`
- `0x14006a13c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14006998c`
- `ntoskrnl!RtlComputeCrc32` at `0x14006998c`

## pseudocode

```c
__int64 __fastcall HsmpRpValidateBuffer(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  int v3; // ebp
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // r15d
  unsigned __int64 v8; // r8
  __int64 v9; // r10
  unsigned __int64 v10; // r11
  __int64 i; // r9
  unsigned int v12; // eax
  unsigned __int64 v13; // rax
  unsigned int v14; // ecx
  unsigned int IsReparseBufferSupported; // edi
  unsigned __int16 v17; // dx
  unsigned __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rbp
  unsigned int v21; // r14d
  int v22; // edi
  unsigned int v23; // eax
  unsigned int v24; // edx
  __int64 v25; // rax
  unsigned __int16 v26; // r9
  unsigned __int64 v27; // r8
  unsigned int v28; // eax
  int v29; // edi
  unsigned int v30; // r8d
  __int64 v31; // rax
  unsigned __int16 v32; // r9
  unsigned __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // edi
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  unsigned int v39; // edx
  __int64 v40; // rax
  unsigned __int16 v41; // r9
  unsigned __int64 v42; // r8
  unsigned int v43; // eax
  unsigned int v44; // edx
  __int64 v45; // rax
  unsigned __int16 v46; // r9
  unsigned __int64 v47; // r8
  unsigned int v48; // eax
  unsigned int v49; // edx
  __int64 v50; // rax
  unsigned __int16 v51; // r9
  unsigned __int64 v52; // r8

  v2 = a2 - 4;
  LOBYTE(v3) = 0;
  if ( a2 <= 4 )
    v2 = 0;
  v5 = *(_DWORD *)a1 & 0xF;
  if ( v5 )
  {
    if ( v5 <= 1 )
    {
      if ( v2 < 0x18 )
      {
        v7 = 0;
        goto LABEL_21;
      }
      v6 = a1 + 4;
      if ( *(_DWORD *)(a1 + 4) != 1884448070 )
      {
        v7 = 1;
        goto LABEL_21;
      }
      if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
      {
        v7 = 2;
        if ( *(_DWORD *)(a1 + 8) != RtlComputeCrc32(0, (PUCHAR)(a1 + 12), v2 - 8) )
        {
LABEL_21:
          HsmDbgBreakOnCorruption();
          IsReparseBufferSupported = -1073688830;
          HsmDbgBreakOnStatus(3221278466LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
              v7,
              -1073688830);
          }
          return IsReparseBufferSupported;
        }
      }
      v8 = *(unsigned int *)(v6 + 8);
      if ( v2 < (unsigned int)v8 )
      {
        v7 = 3;
        goto LABEL_21;
      }
      v9 = *(unsigned __int16 *)(v6 + 14);
      if ( !(_WORD)v9 )
      {
        v7 = 4;
        goto LABEL_21;
      }
      v10 = 8 * v9 + 16;
      if ( v10 >= v8 )
      {
        v7 = 5;
        goto LABEL_21;
      }
      v7 = 0x10000;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v12 = *(unsigned __int16 *)(v6 + 14);
        if ( (unsigned int)v9 >= 0xA )
          v12 = 10;
        if ( (unsigned int)i >= v12 )
          break;
        if ( *(_WORD *)(v6 + 8 * i + 16) >= 0x12u )
          goto LABEL_21;
        v13 = *(unsigned int *)(v6 + 8 * i + 20);
        if ( (_DWORD)v13 )
        {
          if ( v13 < v10 )
            goto LABEL_21;
        }
        if ( (unsigned int)v13 > (unsigned int)v8 )
          goto LABEL_21;
        v14 = *(unsigned __int16 *)(v6 + 8 * i + 18);
        if ( v14 > (unsigned int)v8
          || v14 + (unsigned int)v13 > (unsigned int)v8
          || v14 + (unsigned int)v13 < (unsigned int)v13 )
        {
          goto LABEL_21;
        }
        ++v7;
      }
      v7 = 0x20000;
      if ( (unsigned int)v8 < 0x18 )
        goto LABEL_21;
      v17 = *(_WORD *)(v6 + 16);
      if ( v17 >= 0x12u )
        goto LABEL_21;
      v18 = *(unsigned int *)(v6 + 20);
      if ( (_DWORD)v18 )
      {
        if ( v18 < v10 || (unsigned int)v18 > (unsigned int)v8 )
          goto LABEL_21;
      }
      v19 = *(unsigned __int16 *)(v6 + 18);
      if ( v19 > (unsigned int)v8
        || v19 + (unsigned int)v18 > (unsigned int)v8
        || v19 + (unsigned int)v18 < (unsigned int)v18
        || v17 != 7
        || v19 != 1 )
      {
        goto LABEL_21;
      }
      if ( *(_BYTE *)(v18 + v6) > 1u )
      {
        v7 = 131073;
        goto LABEL_21;
      }
      v39 = *(_DWORD *)(v6 + 8);
      v40 = *(unsigned __int16 *)(v6 + 14);
      if ( (unsigned __int16)v40 > 1u
        && (unsigned int)v8 >= 0x20
        && (v41 = *(_WORD *)(v6 + 24), v41 < 0x12u)
        && ((v42 = *(unsigned int *)(v6 + 28), !(_DWORD)v42) || v42 >= 8 * v40 + 16 && (unsigned int)v42 <= v39)
        && (v43 = *(unsigned __int16 *)(v6 + 26), v43 <= v39)
        && v43 + (unsigned int)v42 <= v39
        && v43 + (unsigned int)v42 >= (unsigned int)v42
        && v41 == 10
        && v43 == 4 )
      {
        v3 = *(_DWORD *)(v42 + v6);
        IsReparseBufferSupported = 0;
      }
      else
      {
        IsReparseBufferSupported = -1073741275;
      }
      HsmDbgBreakOnStatus(IsReparseBufferSupported);
      if ( (IsReparseBufferSupported & 0x80000000) != 0 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return IsReparseBufferSupported;
        }
        v37 = 24;
        v38 = IsReparseBufferSupported;
        goto LABEL_115;
      }
      if ( (v3 & 0x10) != 0 )
        return IsReparseBufferSupported;
      v44 = *(_DWORD *)(v6 + 8);
      if ( v44 < 0x18 )
      {
        IsReparseBufferSupported = -1073741275;
        HsmDbgBreakOnStatus(3221226021LL);
      }
      else
      {
        v45 = *(unsigned __int16 *)(v6 + 14);
        if ( (unsigned __int16)v45 > 2u
          && v44 >= 0x28
          && (v46 = *(_WORD *)(v6 + 32), v46 < 0x12u)
          && ((v47 = *(unsigned int *)(v6 + 36), !(_DWORD)v47) || v47 >= 8 * v45 + 16 && (unsigned int)v47 <= v44)
          && (v48 = *(unsigned __int16 *)(v6 + 34), v48 <= v44)
          && v48 + (unsigned int)v47 <= v44
          && v48 + (unsigned int)v47 >= (unsigned int)v47
          && v46 == 6
          && v48 == 8 )
        {
          IsReparseBufferSupported = 0;
        }
        else
        {
          IsReparseBufferSupported = -1073741275;
        }
        HsmDbgBreakOnStatus(IsReparseBufferSupported);
        if ( (IsReparseBufferSupported & 0x80000000) == 0 )
        {
          v49 = *(_DWORD *)(v6 + 8);
          v20 = 0;
          v21 = 0;
          if ( v49 < 0x18 )
          {
            HsmDbgBreakOnStatus(3221226021LL);
          }
          else
          {
            v50 = *(unsigned __int16 *)(v6 + 14);
            if ( (unsigned __int16)v50 <= 4u
              || v49 < 0x38
              || (v51 = *(_WORD *)(v6 + 48), v51 >= 0x12u)
              || (v52 = *(unsigned int *)(v6 + 52), (_DWORD)v52) && (v52 < 8 * v50 + 16 || (unsigned int)v52 > v49)
              || (v23 = *(unsigned __int16 *)(v6 + 50), v23 > v49)
              || v23 + (unsigned int)v52 > v49
              || v51 != 17
              || v23 + (unsigned int)v52 < (unsigned int)v52 )
            {
              v22 = -1073741275;
            }
            else
            {
              if ( (_DWORD)v52 && (_WORD)v23 )
                v20 = v6 + v52;
              v21 = *(unsigned __int16 *)(v6 + 50);
              v22 = 0;
            }
            if ( v22 < 0 )
              v21 = 0;
            HsmDbgBreakOnStatus((unsigned int)v22);
            if ( v22 >= 0 )
            {
              IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v20, v21);
              HsmDbgBreakOnStatus(IsReparseBufferSupported);
              if ( (IsReparseBufferSupported & 0x80000000) != 0 )
              {
                v36 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  return IsReparseBufferSupported;
                }
                v37 = 26;
                goto LABEL_114;
              }
            }
          }
          v24 = *(_DWORD *)(v6 + 8);
          if ( v24 < 0x18 )
          {
            HsmDbgBreakOnStatus(3221226021LL);
          }
          else
          {
            v25 = *(unsigned __int16 *)(v6 + 14);
            if ( (unsigned __int16)v25 <= 5u
              || v24 < 0x40
              || (v26 = *(_WORD *)(v6 + 56), v26 >= 0x12u)
              || (v27 = *(unsigned int *)(v6 + 60), (_DWORD)v27) && (v27 < 8 * v25 + 16 || (unsigned int)v27 > v24)
              || (v28 = *(unsigned __int16 *)(v6 + 58), v28 > v24)
              || v28 + (unsigned int)v27 > v24
              || v26 != 17
              || v28 + (unsigned int)v27 < (unsigned int)v27 )
            {
              v29 = -1073741275;
            }
            else
            {
              if ( (_DWORD)v27 && (_WORD)v28 )
                v20 = v6 + v27;
              else
                v20 = 0;
              v29 = 0;
              v21 = *(unsigned __int16 *)(v6 + 58);
            }
            HsmDbgBreakOnStatus((unsigned int)v29);
            if ( v29 >= 0 )
            {
              IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v20, v21);
              HsmDbgBreakOnStatus(IsReparseBufferSupported);
              if ( (IsReparseBufferSupported & 0x80000000) != 0 )
              {
                v36 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  return IsReparseBufferSupported;
                }
                v37 = 27;
                goto LABEL_114;
              }
            }
          }
          v30 = *(_DWORD *)(v6 + 8);
          if ( v30 < 0x18 )
          {
            HsmDbgBreakOnStatus(3221226021LL);
            return 0;
          }
          v31 = *(unsigned __int16 *)(v6 + 14);
          if ( (unsigned __int16)v31 <= 6u
            || v30 < 0x48
            || (v32 = *(_WORD *)(v6 + 64), v32 >= 0x12u)
            || (v33 = *(unsigned int *)(v6 + 68), (_DWORD)v33) && (v33 < 8 * v31 + 16 || (unsigned int)v33 > v30)
            || (v34 = *(unsigned __int16 *)(v6 + 66), v34 > v30)
            || v34 + (unsigned int)v33 > v30
            || v32 != 17
            || v34 + (unsigned int)v33 < (unsigned int)v33 )
          {
            v35 = -1073741275;
          }
          else
          {
            if ( (_DWORD)v33 && (_WORD)v34 )
              v20 = v6 + v33;
            else
              v20 = 0;
            v35 = 0;
            v21 = *(unsigned __int16 *)(v6 + 66);
          }
          HsmDbgBreakOnStatus((unsigned int)v35);
          if ( v35 < 0 )
            return 0;
          IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v20, v21);
          HsmDbgBreakOnStatus(IsReparseBufferSupported);
          if ( (IsReparseBufferSupported & 0x80000000) == 0 )
            return IsReparseBufferSupported;
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return IsReparseBufferSupported;
          }
          v37 = 28;
          goto LABEL_114;
        }
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return IsReparseBufferSupported;
      }
      v37 = 25;
LABEL_114:
      v38 = IsReparseBufferSupported;
LABEL_115:
      WPP_SF_d(v36->AttachedDevice, v37, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, v38);
      return IsReparseBufferSupported;
    }
    IsReparseBufferSupported = -1073741735;
    HsmDbgBreakOnStatus(3221225561LL);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return IsReparseBufferSupported;
    }
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      *(_DWORD *)a1 & 0xF,
      -1073741735);
    return 3221225561LL;
  }
  else
  {
    HsmDbgBreakOnCorruption();
    IsReparseBufferSupported = -1073741736;
    HsmDbgBreakOnStatus(3221225560LL);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return IsReparseBufferSupported;
    }
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      *(_DWORD *)a1 & 0xF,
      -1073741736);
    return 3221225560LL;
  }
}

```

## disassembly

```asm
0x140069920  mov     [rsp+arg_18], rbx
0x140069925  push    rbp
0x140069926  push    rsi
0x140069927  push    rdi
0x140069928  sub     rsp, 30h
0x14006992c  xor     eax, eax
0x14006992e  lea     edi, [rdx-4]
0x140069931  xor     ebp, ebp
0x140069933  mov     rbx, rcx
0x140069936  cmp     edx, 4
0x140069939  cmovbe  edi, eax
0x14006993c  mov     eax, [rcx]
0x14006993e  and     eax, 0Fh
0x140069941  cmp     eax, 1
0x140069944  jb      loc_140069B25
0x14006994a  ja      loc_140069B92
0x140069950  mov     [rsp+48h+arg_0], r14
0x140069955  mov     [rsp+48h+arg_10], r15
0x14006995a  cmp     edi, 18h
0x14006995d  jb      loc_14006A12B
0x140069963  add     rbx, 4
0x140069967  cmp     dword ptr [rbx], 70526546h
0x14006996d  jnz     loc_14006A120
0x140069973  mov     r14d, 2
0x140069979  test    [rbx+0Ch], r14b
0x14006997d  jz      short loc_14006999D
0x14006997f  lea     r8d, [rdi-8]; Length
0x140069983  xor     ecx, ecx; InitialCrc
0x140069985  lea     rdx, [rbx+8]; Buffer
0x140069989  mov     r15d, r14d
0x14006998c  call    cs:__imp_RtlComputeCrc32
0x140069993  nop     dword ptr [rax+rax+00h]
0x140069998  cmp     [rbx+4], eax
0x14006999b  jnz     short loc_140069A16
0x14006999d  mov     r8d, [rbx+8]
0x1400699a1  cmp     edi, r8d
0x1400699a4  jb      loc_14006A115
0x1400699aa  movzx   r10d, word ptr [rbx+0Eh]
0x1400699af  test    r10w, r10w
0x1400699b3  jz      loc_14006A10A
0x1400699b9  lea     r11, ds:10h[r10*8]
0x1400699c1  cmp     r11, r8
0x1400699c4  jnb     loc_14006A0FF
0x1400699ca  mov     r15d, 10000h
0x1400699d0  xor     r9d, r9d
0x1400699d3  mov     eax, r10d
0x1400699d6  cmp     r10d, 0Ah
0x1400699da  jb      short loc_1400699E1
0x1400699dc  mov     eax, 0Ah
0x1400699e1  cmp     r9d, eax
0x1400699e4  jnb     loc_140069A6E
0x1400699ea  cmp     word ptr [rbx+r9*8+10h], 12h
0x1400699f1  jnb     short loc_140069A16
0x1400699f3  mov     eax, [rbx+r9*8+14h]
0x1400699f8  lea     rdx, [rbx+r9*8]
0x1400699fc  test    eax, eax
0x1400699fe  jnz     short loc_140069A58
0x140069a00  cmp     eax, r8d
0x140069a03  ja      short loc_140069A16
0x140069a05  movzx   ecx, word ptr [rdx+12h]
0x140069a09  cmp     ecx, r8d
0x140069a0c  ja      short loc_140069A16
0x140069a0e  lea     edx, [rcx+rax]
0x140069a11  cmp     edx, r8d
0x140069a14  jbe     short loc_140069A5F
0x140069a16  call    HsmDbgBreakOnCorruption
0x140069a1b  mov     edi, 0C000CF02h
0x140069a20  mov     ecx, edi
0x140069a22  call    HsmDbgBreakOnStatus
0x140069a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140069a2e  lea     rax, WPP_GLOBAL_Control
0x140069a35  cmp     rcx, rax
0x140069a38  jnz     loc_140069AEF
0x140069a3e  mov     r14, [rsp+48h+arg_0]
0x140069a43  mov     r15, [rsp+48h+arg_10]
0x140069a48  mov     eax, edi
0x140069a4a  mov     rbx, [rsp+48h+arg_18]
0x140069a4f  add     rsp, 30h
0x140069a53  pop     rdi
0x140069a54  pop     rsi
0x140069a55  pop     rbp
0x140069a56  retn
0x140069a58  cmp     rax, r11
0x140069a5b  jnb     short loc_140069A00
0x140069a5d  jmp     short loc_140069A16
0x140069a5f  cmp     edx, eax
0x140069a61  jb      short loc_140069A16
0x140069a63  inc     r15d
0x140069a66  inc     r9d
0x140069a69  jmp     loc_1400699D3
0x140069a6e  mov     r15d, 20000h
0x140069a74  cmp     r8d, 18h
0x140069a78  jb      short loc_140069A16
0x140069a7a  xor     eax, eax
0x140069a7c  cmp     ax, r10w
0x140069a80  jnb     short loc_140069A16
0x140069a82  movzx   edx, word ptr [rbx+10h]
0x140069a86  cmp     dx, 12h
0x140069a8a  jnb     short loc_140069A16
0x140069a8c  mov     ecx, [rbx+14h]
0x140069a8f  test    ecx, ecx
0x140069a91  jz      short loc_140069AA5
0x140069a93  cmp     rcx, r11
0x140069a96  jb      loc_140069A16
0x140069a9c  cmp     ecx, r8d
0x140069a9f  ja      loc_140069A16
0x140069aa5  movzx   eax, word ptr [rbx+12h]
0x140069aa9  cmp     eax, r8d
0x140069aac  ja      loc_140069A16
0x140069ab2  lea     r9d, [rax+rcx]
0x140069ab6  cmp     r9d, r8d
0x140069ab9  ja      loc_140069A16
0x140069abf  cmp     r9d, ecx
0x140069ac2  jb      loc_140069A16
0x140069ac8  cmp     dx, 7
0x140069acc  jnz     loc_140069A16
0x140069ad2  cmp     eax, 1
0x140069ad5  jnz     loc_140069A16
0x140069adb  cmp     [rcx+rbx], al
0x140069ade  jbe     loc_140069EB5
0x140069ae4  mov     r15d, 20001h
0x140069aea  jmp     loc_140069A16
0x140069aef  mov     eax, [rcx+2Ch]
0x140069af2  test    al, 1
0x140069af4  jz      loc_140069A3E
0x140069afa  cmp     byte ptr [rcx+29h], 2
0x140069afe  jb      loc_140069A3E
0x140069b04  mov     rcx, [rcx+18h]
0x140069b08  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069b0f  mov     edx, 17h
0x140069b14  mov     [rsp+48h+var_28], edi
0x140069b18  mov     r9d, r15d
0x140069b1b  call    WPP_SF_Dd
0x140069b20  jmp     loc_140069A3E
0x140069b25  call    HsmDbgBreakOnCorruption
0x140069b2a  mov     edi, 0C0000058h
0x140069b2f  mov     ecx, edi
0x140069b31  call    HsmDbgBreakOnStatus
0x140069b36  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b3d  lea     rax, WPP_GLOBAL_Control
0x140069b44  cmp     rcx, rax
0x140069b47  jz      loc_140069A48
0x140069b4d  mov     eax, [rcx+2Ch]
0x140069b50  test    al, 1
0x140069b52  jz      loc_140069A48
0x140069b58  cmp     byte ptr [rcx+29h], 2
0x140069b5c  jb      loc_140069A48
0x140069b62  mov     r9d, [rbx]
0x140069b65  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069b6c  mov     rcx, [rcx+18h]
0x140069b70  and     r9d, 0Fh
0x140069b74  mov     edx, 15h
0x140069b79  mov     [rsp+48h+var_28], edi
0x140069b7d  call    WPP_SF_Dd
0x140069b82  mov     eax, edi
0x140069b84  mov     rbx, [rsp+48h+arg_18]
0x140069b89  add     rsp, 30h
0x140069b8d  pop     rdi
0x140069b8e  pop     rsi
0x140069b8f  pop     rbp
0x140069b90  retn
0x140069b92  mov     edi, 0C0000059h
0x140069b97  mov     ecx, edi
0x140069b99  call    HsmDbgBreakOnStatus
0x140069b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140069ba5  lea     rax, WPP_GLOBAL_Control
0x140069bac  cmp     rcx, rax
0x140069baf  jz      loc_140069A48
0x140069bb5  mov     eax, [rcx+2Ch]
0x140069bb8  test    al, 1
0x140069bba  jz      loc_140069A48
0x140069bc0  cmp     byte ptr [rcx+29h], 2
0x140069bc4  jb      loc_140069A48
0x140069bca  mov     r9d, [rbx]
0x140069bcd  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069bd4  mov     rcx, [rcx+18h]
0x140069bd8  and     r9d, 0Fh
0x140069bdc  mov     edx, 16h
0x140069be1  mov     [rsp+48h+var_28], edi
0x140069be5  call    WPP_SF_Dd
0x140069bea  mov     rbx, [rsp+48h+arg_18]
0x140069bef  mov     eax, edi
0x140069bf1  add     rsp, 30h
0x140069bf5  pop     rdi
0x140069bf6  pop     rsi
0x140069bf7  pop     rbp
0x140069bf8  retn
0x140069bfa  cmp     ecx, r8d
0x140069bfd  jb      short loc_140069C3A
0x140069bff  test    r8d, r8d
0x140069c02  jz      short loc_140069C0D
0x140069c04  test    ax, ax
0x140069c07  jz      short loc_140069C0D
0x140069c09  lea     rbp, [rbx+r8]
0x140069c0d  mov     r14d, eax
0x140069c10  xor     edi, edi
0x140069c12  jmp     short loc_140069C3C
0x140069c14  lea     rcx, ds:10h[rax*8]
0x140069c1c  cmp     r8, rcx
0x140069c1f  jb      short loc_140069C3A
0x140069c21  cmp     r8d, edx
0x140069c24  ja      short loc_140069C3A
0x140069c26  movzx   eax, word ptr [rbx+32h]
0x140069c2a  cmp     eax, edx
0x140069c2c  ja      short loc_140069C3A
0x140069c2e  lea     ecx, [rax+r8]
0x140069c32  cmp     ecx, edx
0x140069c34  jbe     loc_140069D48
0x140069c3a  mov     edi, esi
0x140069c3c  xor     eax, eax
0x140069c3e  mov     ecx, edi
0x140069c40  test    edi, edi
0x140069c42  cmovs   r14d, eax
0x140069c46  call    HsmDbgBreakOnStatus
0x140069c4b  test    edi, edi
0x140069c4d  jns     loc_14006A0DA
0x140069c53  cmp     edi, esi
0x140069c55  jnz     loc_140069E05
0x140069c5b  mov     edx, [rbx+8]
0x140069c5e  cmp     edx, 18h
0x140069c61  jb      loc_14006A0F3
0x140069c67  movzx   eax, word ptr [rbx+0Eh]
0x140069c6b  mov     r15d, 5
0x140069c71  cmp     r15w, ax
0x140069c75  jnb     short loc_140069CB7
0x140069c77  cmp     edx, 40h ; '@'
0x140069c7a  jb      short loc_140069CB7
0x140069c7c  movzx   r9d, word ptr [rbx+38h]
0x140069c81  cmp     r9w, 12h
0x140069c86  jnb     short loc_140069CB7
0x140069c88  mov     r8d, [rbx+3Ch]
0x140069c8c  test    r8d, r8d
0x140069c8f  jz      short loc_140069CA3
0x140069c91  lea     rcx, ds:10h[rax*8]
0x140069c99  cmp     r8, rcx
0x140069c9c  jb      short loc_140069CB7
0x140069c9e  cmp     r8d, edx
0x140069ca1  ja      short loc_140069CB7
0x140069ca3  movzx   eax, word ptr [rbx+3Ah]
0x140069ca7  cmp     eax, edx
0x140069ca9  ja      short loc_140069CB7
0x140069cab  lea     ecx, [rax+r8]
0x140069caf  cmp     ecx, edx
0x140069cb1  jbe     loc_140069D58
0x140069cb7  mov     edi, esi
0x140069cb9  mov     ecx, edi
0x140069cbb  call    HsmDbgBreakOnStatus
0x140069cc0  test    edi, edi
0x140069cc2  jns     loc_140069DB6
0x140069cc8  cmp     edi, esi
0x140069cca  jnz     loc_140069DCA
0x140069cd0  mov     r8d, [rbx+8]
0x140069cd4  cmp     r8d, 18h
0x140069cd8  jb      loc_140069EA7
0x140069cde  movzx   eax, word ptr [rbx+0Eh]
0x140069ce2  mov     ecx, 6
0x140069ce7  cmp     cx, ax
0x140069cea  jnb     short loc_140069D28
0x140069cec  cmp     r8d, 48h ; 'H'
0x140069cf0  jb      short loc_140069D28
0x140069cf2  movzx   r9d, word ptr [rbx+40h]
0x140069cf7  cmp     r9w, 12h
0x140069cfc  jnb     short loc_140069D28
0x140069cfe  mov     edx, [rbx+44h]
0x140069d01  test    edx, edx
0x140069d03  jz      short loc_140069D17
0x140069d05  lea     rcx, ds:10h[rax*8]
0x140069d0d  cmp     rdx, rcx
0x140069d10  jb      short loc_140069D28
0x140069d12  cmp     edx, r8d
0x140069d15  ja      short loc_140069D28
0x140069d17  movzx   eax, word ptr [rbx+42h]
0x140069d1b  cmp     eax, r8d
0x140069d1e  ja      short loc_140069D28
0x140069d20  lea     ecx, [rax+rdx]
0x140069d23  cmp     ecx, r8d
0x140069d26  jbe     short loc_140069D8C
0x140069d28  mov     edi, esi
0x140069d2a  mov     ecx, edi
0x140069d2c  call    HsmDbgBreakOnStatus
0x140069d31  test    edi, edi
0x140069d33  jns     loc_140069E89
0x140069d39  cmp     edi, esi
0x140069d3b  jnz     loc_140069E40
0x140069d41  xor     edi, edi
0x140069d43  jmp     loc_140069A3E
0x140069d48  cmp     r9w, 11h
0x140069d4d  jz      loc_140069BFA
0x140069d53  jmp     loc_140069C3A
0x140069d58  cmp     r9w, 11h
0x140069d5d  jnz     loc_140069CB7
0x140069d63  cmp     ecx, r8d
0x140069d66  jb      loc_140069CB7
0x140069d6c  test    r8d, r8d
0x140069d6f  jz      loc_14006A06C
0x140069d75  test    ax, ax
0x140069d78  jz      loc_14006A06C
0x140069d7e  lea     rbp, [rbx+r8]
0x140069d82  xor     edi, edi
0x140069d84  mov     r14d, eax
  ... truncated ...
```

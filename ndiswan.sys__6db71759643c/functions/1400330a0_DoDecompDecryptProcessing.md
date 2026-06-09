# DoDecompDecryptProcessing

- ea: `0x1400330a0`
- end: `0x140033c29`
- name: `DoDecompDecryptProcessing`
- size: `2953`
- prototype: `__int64 __fastcall(PVOID)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140032cd0`

## callees

- `0x140008bf4`
- `0x140008f90`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x140010580`
- `0x1400105d4`
- `0x140016400`
- `0x14002dd7c`
- `0x1400330a0`
- `0x140033c30`
- `0x140033db4`
- `0x140033df0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003362a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003362a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033647`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033bc2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033647`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c18`
- `ntoskrnl!ExAllocatePool2` at `0x140033607`
- `ntoskrnl!ExAllocatePool2` at `0x140033607`
- `cng!BCryptDestroyKey` at `0x140033a8e`
- `cng!BCryptDestroyKey` at `0x140033ad2`
- `cng!BCryptDestroyKey` at `0x140033a8e`
- `cng!BCryptDestroyKey` at `0x140033ad2`
- `cng!BCryptGenerateSymmetricKey` at `0x140033329`
- `cng!BCryptGenerateSymmetricKey` at `0x1400333ee`
- `cng!BCryptGenerateSymmetricKey` at `0x140033329`
- `cng!BCryptGenerateSymmetricKey` at `0x1400333ee`
- `cng!BCryptEncrypt` at `0x140033389`
- `cng!BCryptEncrypt` at `0x140033445`
- `cng!BCryptEncrypt` at `0x140033389`
- `cng!BCryptEncrypt` at `0x140033445`

## pseudocode

```c
char __fastcall DoDecompDecryptProcessing(char *a1, PUCHAR *a2, ULONG *a3)
{
  ULONG v3; // r9d
  PUCHAR v5; // rcx
  ULONG *v6; // r12
  PUCHAR *v7; // r13
  int v8; // r14d
  int v9; // edi
  __int16 v10; // r9
  int v11; // esi
  __int64 v12; // r8
  __int64 v13; // rdx
  BCRYPT_KEY_HANDLE *v14; // r9
  __int64 v15; // rax
  UCHAR *pbSecret; // r10
  ULONG v17; // ecx
  __int64 v18; // r8
  char v19; // al
  unsigned __int16 v20; // cx
  __int16 v21; // dx
  __int64 v22; // rdx
  BCRYPT_KEY_HANDLE *v23; // rax
  BCRYPT_KEY_HANDLE *v24; // rax
  BCRYPT_KEY_HANDLE v25; // rcx
  int v27; // r9d
  ULONG v28; // edx
  unsigned int v29; // r8d
  __int64 v30; // rax
  unsigned __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int64 v33; // rcx
  __int64 Pool2; // rdi
  __int64 v35; // rsi
  KSPIN_LOCK *v36; // rcx
  int v37; // r9d
  unsigned __int64 v38; // rdx
  unsigned int i; // r8d
  BCRYPT_KEY_HANDLE *v40; // rcx
  int v41; // r12d
  BCRYPT_KEY_HANDLE *v42; // r12
  _WORD *v43; // r13
  unsigned int v44; // esi
  __int8 v45; // al
  __m128i v46; // xmm0
  size_t v47; // r8
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rax
  int v50; // eax
  __int16 v51; // cx
  ULONG cbOutput; // [rsp+50h] [rbp-98h] BYREF
  int v53; // [rsp+54h] [rbp-94h]
  BCRYPT_KEY_HANDLE *phKey; // [rsp+58h] [rbp-90h]
  unsigned int v55; // [rsp+60h] [rbp-88h]
  PUCHAR pbOutput; // [rsp+68h] [rbp-80h] BYREF
  __int64 v57; // [rsp+70h] [rbp-78h]
  __m128i v58; // [rsp+80h] [rbp-68h] BYREF
  int v59; // [rsp+90h] [rbp-58h]
  int v60; // [rsp+94h] [rbp-54h]
  unsigned int v61; // [rsp+98h] [rbp-50h]
  char v62; // [rsp+F0h] [rbp+8h]
  int v63; // [rsp+F0h] [rbp+8h]
  ULONG *pcbResult; // [rsp+100h] [rbp+18h] BYREF
  ULONG cbInput; // [rsp+108h] [rbp+20h]

  pcbResult = a3;
  v3 = *a3;
  v5 = *a2;
  v6 = a3;
  v7 = a2;
  pbOutput = *a2;
  cbOutput = v3;
  v8 = *((_DWORD *)a1 + 64);
  if ( (v8 & 6) == 0 )
    return 0;
  v9 = _byteswap_ushort(*(_WORD *)v5);
  pbOutput = v5 + 2;
  v59 = v9;
  cbOutput = v3 - 2;
  if ( (int)(v3 - 2) <= 0 )
    goto LABEL_57;
  v10 = *((_WORD *)a1 + 662);
  v11 = v8 & 0x800;
  v61 = (unsigned __int16)v9;
  v60 = v11;
  v12 = v9 & 0xFFF;
  v13 = 0;
  v55 = 0;
  if ( (v8 & 0x800) != 0 )
  {
    if ( (v9 & 0xFFF) == (v10 & 0xFFF) )
    {
      v53 = 1;
    }
    else
    {
      v37 = v10 & 0xFFF;
      if ( (_DWORD)v12 == v37 || (((v9 & 0xFFF) - (_WORD)v37) & 0x800) != 0 )
      {
        if ( ((v37 - v12) & 0xFFF) > glMaxOutOfOrderDepth )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 76, v12, a1, v9 & 0xFFF, v37);
          }
          return 0;
        }
        v53 = 2;
      }
      else
      {
        v53 = 3;
        v13 = ((v9 & 0xFFF) - (_WORD)v37) & 0xFFF;
        v55 = ((v9 & 0xFFF) - (_WORD)v37) & 0xFFF;
      }
    }
  }
  else
  {
    v27 = v10 & 0xFFF;
    if ( (_DWORD)v12 != v27 && (((v9 & 0xFFF) - (_WORD)v27) & 0x800) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_59:
        if ( *((_DWORD *)a1 + 16) )
        {
          Pool2 = ExAllocatePool2(64, 132, 1129210199);
          if ( Pool2 )
          {
            v35 = *((_QWORD *)a1 + 6);
            KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v35 + 736));
            v36 = (KSPIN_LOCK *)(v35 + 736);
            if ( *(_DWORD *)(v35 + 20) == 2 )
            {
              ++*(_DWORD *)(v35 + 28);
              KeReleaseSpinLockFromDpcLevel(v36);
              *(_QWORD *)(Pool2 + 8) = *((_QWORD *)a1 + 4);
              *(_DWORD *)(Pool2 + 16) = 43953;
              *(_DWORD *)(Pool2 + 20) = 6;
              *(_WORD *)(Pool2 + 24) = -640;
              *(_BYTE *)(Pool2 + 26) = 14;
              *(_BYTE *)(Pool2 + 27) = a1[1332];
              ++*((_DWORD *)a1 + 333);
              *(_WORD *)(Pool2 + 28) = 1024;
              BuildIoPacket(*((PVOID *)a1 + 6), a1);
            }
            else
            {
              KeReleaseSpinLockFromDpcLevel(v36);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
              }
            }
            ExFreePoolWithTag((PVOID)Pool2, 0);
          }
        }
        return 0;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 75, v12, a1, v9 & 0xFFF, v27);
LABEL_57:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          78,
          WPP_52604c4400d53a16edd48a543f00e082_Traceguids,
          v9 & 0xFFF,
          *((_WORD *)a1 + 662) & 0xFFF);
      }
      if ( (v8 & 0x800) != 0 )
        return 0;
      goto LABEL_59;
    }
    v53 = 0;
  }
  v14 = (BCRYPT_KEY_HANDLE *)*((_QWORD *)a1 + 161);
  v15 = *((_QWORD *)a1 + 144);
  pbSecret = (UCHAR *)(a1 + 1260);
  v17 = *((_DWORD *)a1 + 319);
  phKey = v14;
  v57 = v15;
  v58.m128i_i64[0] = (__int64)&WPP_GLOBAL_Control;
  cbInput = v17;
  v62 = 0;
  if ( (v9 & 0x8000u) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v58.m128i_i64[0] )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_52604c4400d53a16edd48a543f00e082_Traceguids, v9 & 0xFFF);
        v14 = phKey;
        pbSecret = (UCHAR *)(a1 + 1260);
        v17 = cbInput;
        v13 = v55;
      }
      v15 = v57;
    }
    v62 = 1;
    if ( (v8 & 4) != 0 && (v8 & 0x800) == 0 )
    {
      CngRsa32Compat_rc4_key_Ex(v14, v17, pbSecret);
      v14 = phKey;
      pbSecret = (UCHAR *)(a1 + 1260);
      v17 = cbInput;
      v13 = v55;
      v15 = v57;
    }
    if ( (v8 & 2) != 0 )
    {
      initrecvcontext(v15, v13, v12);
      v14 = phKey;
      pbSecret = (UCHAR *)(a1 + 1260);
      v17 = cbInput;
      v13 = v55;
    }
  }
  v18 = 4096;
  if ( (v8 & 0x800) == 0 || v53 == 1 )
  {
    v19 = v62;
    goto LABEL_15;
  }
  if ( v53 == 2 )
  {
    if ( (v9 & 0x1000) != 0 )
    {
      if ( (v8 & 4) != 0 )
      {
        v38 = *((_QWORD *)a1 + 163);
        for ( i = 0; i < glCachedKeyCount; ++i )
        {
          if ( v38 <= *((_QWORD *)a1 + 162) )
          {
            v38 = *((_QWORD *)a1 + 164);
          }
          else
          {
            v38 += -2LL - v17;
            v17 = cbInput;
          }
          pcbResult = (ULONG *)v38;
          if ( *(_WORD *)v38 == (v9 & 0xFFF) )
          {
            CngRsa32Compat_rc4_key_Ex(v14, v17, (PUCHAR)(v38 + 2));
            v40 = phKey;
            *(_WORD *)pcbResult = -1;
            CngRsa32Compat_rc4(v40, cbOutput, pbOutput);
            goto LABEL_39;
          }
        }
      }
      return 0;
    }
    goto LABEL_39;
  }
  v19 = 1;
  if ( (v8 & 4) == 0
    || (v41 = *((unsigned __int16 *)a1 + 662), LOWORD(v41) = v41 & 0xFFF, v63 = v41, v6 = pcbResult, !(_DWORD)v13) )
  {
LABEL_15:
    v20 = v9 & 0xFFF;
    if ( !v19 )
      goto LABEL_19;
    goto LABEL_16;
  }
  v42 = phKey;
  v43 = a1 + 1260;
  v44 = v55;
  v53 = v8 & 0x80;
  while ( 1 )
  {
    if ( (v8 & 0x40) != 0 )
    {
      v45 = a1[1267];
      v58 = 0;
      v58.m128i_i8[4] = v45;
      v58.m128i_i32[0] = *(_DWORD *)(a1 + 1263);
      v46 = _mm_add_epi8(_mm_load_si128(&v58), (__m128i)_xmm);
      *(_WORD *)(a1 + 1263) = _mm_cvtsi128_si32(v46);
      *(_WORD *)(a1 + 1265) = _mm_extract_epi16(v46, 1);
      a1[1267] = _mm_extract_epi16(v46, 2);
    }
    else
    {
      GetNewKeyFromSHA(a1 + 1240, v13, v18);
      v17 = cbInput;
    }
    CngRsa32Compat_rc4_key_Ex(v42, v17, (PUCHAR)a1 + 1260);
    CngRsa32Compat_rc4(v42, cbInput, a1 + 1260);
    if ( v53 )
    {
      *v43 = 9937;
      a1[1262] = -98;
    }
    else if ( (v8 & 0x1000) != 0 )
    {
      *(_BYTE *)v43 = -47;
    }
    if ( (int)--v44 < glCachedKeyCount )
    {
      v47 = cbInput;
      **((_WORD **)a1 + 163) = v63;
      memmove((void *)(*((_QWORD *)a1 + 163) + 2LL), a1 + 1260, v47);
      v48 = *((_QWORD *)a1 + 163);
      if ( v48 >= *((_QWORD *)a1 + 164) )
        v49 = *((_QWORD *)a1 + 162);
      else
        v49 = v48 + cbInput + 2LL;
      *((_QWORD *)a1 + 163) = v49;
    }
    CngRsa32Compat_rc4_key_Ex(v42, cbInput, (PUCHAR)a1 + 1260);
    HIWORD(v50) = HIWORD(v63);
    if ( (unsigned __int16)v63 >= 0xFFFu )
    {
      v63 = 0;
    }
    else
    {
      LOWORD(v50) = v63 + 1;
      v63 = v50;
    }
    if ( !v44 )
      break;
    v17 = cbInput;
  }
  LOWORD(v9) = v59;
  pbSecret = (UCHAR *)(a1 + 1260);
  v11 = v60;
  v6 = pcbResult;
  v7 = a2;
  v20 = v59 & 0xFFF;
  v14 = phKey;
LABEL_16:
  v21 = *((_WORD *)a1 + 662);
  if ( (unsigned __int16)(v21 & 0xFFF) > v20 )
    v21 += 4096;
  *((_WORD *)a1 + 662) = v21 ^ (v9 ^ v21) & 0xFFF;
LABEL_19:
  v22 = *((unsigned __int16 *)a1 + 662);
  if ( v20 != (v22 & 0xFFF) )
    goto LABEL_57;
  LOWORD(v22) = v22 + 1;
  *((_WORD *)a1 + 662) = v22;
  if ( (v9 & 0x1000) != 0 )
  {
    if ( (v8 & 4) == 0 )
      return 0;
    if ( v11 || (unsigned __int16)v22 - *((unsigned __int16 *)a1 + 664) >= 256 )
    {
      *((_WORD *)a1 + 664) = v22 & 0xFF00;
      if ( (v22 & 0xF000) == 0xF000 )
      {
        v51 = v22 & 0xF00;
        LOWORD(v22) = v22 & 0xFFF;
        *((_WORD *)a1 + 664) = v51;
        *((_WORD *)a1 + 662) = v22;
      }
      if ( (v8 & 0x40) != 0 )
      {
        ++pbSecret[3];
        pbSecret[4] += 3;
        pbSecret[5] += 13;
        pbSecret[6] += 57;
        pbSecret[7] += 19;
      }
      else
      {
        GetNewKeyFromSHA(a1 + 1240, v22, 61440);
        v14 = phKey;
        pbSecret = (UCHAR *)(a1 + 1260);
      }
      if ( !v14 )
        __fastfail(7u);
      if ( *v14 )
      {
        BCryptDestroyKey(*v14);
        v23 = phKey;
        pbSecret = (UCHAR *)(a1 + 1260);
        *phKey = 0;
      }
      else
      {
        v23 = phKey;
      }
      if ( BCryptGenerateSymmetricKey(ghAlgRC4, v23, 0, 0, pbSecret, cbInput, 0) < 0 )
        __fastfail(7u);
      LODWORD(pcbResult) = 0;
      if ( BCryptEncrypt(
             *phKey,
             (PUCHAR)a1 + 1260,
             cbInput,
             0,
             0,
             0,
             (PUCHAR)a1 + 1260,
             cbInput,
             (ULONG *)&pcbResult,
             0) < 0 )
        __fastfail(7u);
      if ( (v8 & 0x80u) != 0 )
      {
        *((_WORD *)a1 + 630) = 9937;
        a1[1262] = -98;
      }
      else if ( (v8 & 0x1000) != 0 )
      {
        a1[1260] = -47;
      }
      v24 = phKey;
      if ( *phKey )
      {
        BCryptDestroyKey(*phKey);
        v24 = phKey;
        *phKey = 0;
      }
      if ( BCryptGenerateSymmetricKey(ghAlgRC4, v24, 0, 0, (PUCHAR)a1 + 1260, cbInput, 0) < 0 )
        __fastfail(7u);
    }
    v25 = *phKey;
    LODWORD(pcbResult) = 0;
    if ( BCryptEncrypt(v25, pbOutput, cbOutput, 0, 0, 0, pbOutput, cbOutput, (ULONG *)&pcbResult, 0) < 0 )
      __fastfail(7u);
  }
LABEL_39:
  if ( (v9 & 0x2000) == 0 )
  {
LABEL_40:
    *v7 = pbOutput;
    *v6 = cbOutput;
    return 1;
  }
  if ( (v8 & 2) != 0 )
  {
    v28 = cbOutput;
    v29 = v61 >> 8;
    v30 = v57;
    v31 = (int)cbOutput + *((unsigned int *)a1 + 416) + ((unsigned __int64)*((unsigned int *)a1 + 437) << 32);
    *((_DWORD *)a1 + 416) += cbOutput;
    *((_DWORD *)a1 + 437) = HIDWORD(v31);
    if ( (unsigned int)decompress((_DWORD)pbOutput, v28, v29 & 0x40, (unsigned int)&pbOutput, (__int64)&cbOutput, v30) )
    {
      if ( (int)cbOutput > 0 && (int)cbOutput <= glMRRU )
      {
        v32 = *((unsigned int *)a1 + 414);
        v33 = (int)cbOutput + v32 + ((unsigned __int64)*((unsigned int *)a1 + 435) << 32);
        *((_DWORD *)a1 + 414) = cbOutput + v32;
        *((_DWORD *)a1 + 435) = HIDWORD(v33);
        goto LABEL_40;
      }
      if ( !v11 )
        --*((_WORD *)a1 + 662);
    }
    else if ( !v11 )
    {
      --*((_WORD *)a1 + 662);
    }
    goto LABEL_57;
  }
  return 0;
}

```

## disassembly

```asm
0x1400330a0  mov     [rsp+arg_10], r8
0x1400330a5  mov     [rsp+arg_8], rdx
0x1400330aa  push    rbx
0x1400330ab  push    rbp
0x1400330ac  push    rsi
0x1400330ad  push    rdi
0x1400330ae  push    r12
0x1400330b0  push    r13
0x1400330b2  push    r14
0x1400330b4  push    r15
0x1400330b6  sub     rsp, 0A8h
0x1400330bd  mov     r9d, [r8]
0x1400330c0  mov     rbx, rcx
0x1400330c3  mov     rcx, [rdx]
0x1400330c6  mov     r12, r8
0x1400330c9  mov     r13, rdx
0x1400330cc  mov     [rsp+0E8h+pbOutput], rcx
0x1400330d1  mov     [rsp+0E8h+var_98], r9d
0x1400330d6  mov     r14d, [rbx+100h]
0x1400330dd  test    r14b, 6
0x1400330e1  jz      loc_1400334C8
0x1400330e7  movzx   eax, byte ptr [rcx]
0x1400330ea  mov     ebp, 0FFFh
0x1400330ef  movzx   edi, byte ptr [rcx+1]
0x1400330f3  shl     ax, 8
0x1400330f7  or      di, ax
0x1400330fa  lea     rax, [rcx+2]
0x1400330fe  mov     [rsp+0E8h+pbOutput], rax
0x140033103  lea     eax, [r9-2]
0x140033107  mov     [rsp+0E8h+var_58], edi
0x14003310e  mov     [rsp+0E8h+var_98], eax
0x140033112  test    eax, eax
0x140033114  jle     loc_1400335CB
0x14003311a  movzx   r9d, word ptr [rbx+52Ch]
0x140033122  xor     r15d, r15d
0x140033125  movzx   eax, di
0x140033128  mov     esi, r14d
0x14003312b  and     esi, 800h
0x140033131  mov     [rsp+0E8h+var_50], eax
0x140033138  mov     r8d, eax
0x14003313b  mov     [rsp+0E8h+var_54], esi
0x140033142  and     r8d, ebp
0x140033145  mov     edx, r15d
0x140033148  mov     [rsp+0E8h+var_88], edx
0x14003314c  test    esi, esi
0x14003314e  jz      loc_140033488
0x140033154  movzx   ecx, di
0x140033157  movzx   eax, r9w
0x14003315b  and     cx, bp
0x14003315e  and     ax, bp
0x140033161  cmp     cx, ax
0x140033164  jnz     loc_1400336F8
0x14003316a  mov     [rsp+0E8h+var_94], 1
0x140033172  mov     r9, [rbx+508h]
0x140033179  lea     r11, WPP_GLOBAL_Control
0x140033180  mov     rax, [rbx+480h]
0x140033187  lea     r10, [rbx+4ECh]
0x14003318e  mov     ecx, [rbx+4FCh]
0x140033194  mov     [rsp+0E8h+phKey], r9
0x140033199  mov     [rsp+0E8h+var_78], rax
0x14003319e  mov     qword ptr [rsp+0E8h+var_68], r11
0x1400331a6  mov     [rsp+0E8h+cbInput], ecx
0x1400331ad  mov     byte ptr [rsp+0E8h+arg_0], r15b
0x1400331b5  test    di, di
0x1400331b8  jns     short loc_14003321A
0x1400331ba  mov     r11, cs:WPP_GLOBAL_Control
0x1400331c1  cmp     r11, qword ptr [rsp+0E8h+var_68]
0x1400331c9  jz      short loc_1400331DC
0x1400331cb  mov     eax, [r11+2Ch]
0x1400331cf  test    al, 10h
0x1400331d1  jnz     loc_14003373F
0x1400331d7  mov     rax, [rsp+0E8h+var_78]
0x1400331dc  mov     byte ptr [rsp+0E8h+arg_0], 1
0x1400331e4  test    r14b, 4
0x1400331e8  jnz     loc_14003377E
0x1400331ee  test    r14b, 2
0x1400331f2  jz      short loc_140033213
0x1400331f4  mov     rcx, rax
0x1400331f7  call    initrecvcontext
0x1400331fc  mov     r9, [rsp+0E8h+phKey]
0x140033201  lea     r10, [rbx+4ECh]
0x140033208  mov     ecx, [rsp+0E8h+cbInput]
0x14003320f  mov     edx, [rsp+0E8h+var_88]
0x140033213  lea     r11, WPP_GLOBAL_Control
0x14003321a  mov     r8d, 1000h
0x140033220  test    esi, esi
0x140033222  jnz     loc_1400334A1
0x140033228  movzx   eax, byte ptr [rsp+0E8h+arg_0]
0x140033230  movzx   ecx, di
0x140033233  and     cx, bp
0x140033236  test    al, al
0x140033238  jz      short loc_140033263
0x14003323a  movzx   edx, word ptr [rbx+52Ch]
0x140033241  movzx   eax, dx
0x140033244  and     ax, bp
0x140033247  cmp     ax, cx
0x14003324a  ja      loc_140033A60
0x140033250  movzx   eax, dx
0x140033253  xor     ax, di
0x140033256  and     ax, bp
0x140033259  xor     ax, dx
0x14003325c  mov     [rbx+52Ch], ax
0x140033263  movzx   edx, word ptr [rbx+52Ch]
0x14003326a  movzx   eax, dx
0x14003326d  and     ax, bp
0x140033270  cmp     cx, ax
0x140033273  jnz     loc_1400335D2
0x140033279  inc     dx
0x14003327c  mov     [rbx+52Ch], dx
0x140033283  test    r8w, di
0x140033287  jz      loc_140033459
0x14003328d  test    r14b, 4
0x140033291  jz      loc_1400334C8
0x140033297  test    esi, esi
0x140033299  jz      loc_14003357C
0x14003329f  mov     eax, 0FF00h
0x1400332a4  mov     r8d, 0F000h
0x1400332aa  movzx   ecx, dx
0x1400332ad  and     cx, ax
0x1400332b0  movzx   eax, cx
0x1400332b3  mov     [rbx+530h], cx
0x1400332ba  and     ax, r8w
0x1400332be  cmp     ax, r8w
0x1400332c2  jz      loc_140033A69
0x1400332c8  test    r14b, 40h
0x1400332cc  jnz     loc_1400335AE
0x1400332d2  lea     rcx, [rbx+4D8h]
0x1400332d9  call    GetNewKeyFromSHA
0x1400332de  mov     r9, [rsp+0E8h+phKey]
0x1400332e3  lea     r10, [rbx+4ECh]
0x1400332ea  test    r9, r9
0x1400332ed  jz      loc_140033A82
0x1400332f3  mov     rcx, [r9]; hKey
0x1400332f6  test    rcx, rcx
0x1400332f9  jnz     loc_140033A8E
0x1400332ff  mov     rax, [rsp+0E8h+phKey]
0x140033304  mov     ecx, [rsp+0E8h+cbInput]
0x14003330b  xor     r9d, r9d; cbKeyObject
0x14003330e  mov     [rsp+0E8h+dwFlags], r15d; dwFlags
0x140033313  xor     r8d, r8d; pbKeyObject
0x140033316  mov     [rsp+0E8h+cbSecret], ecx; cbSecret
0x14003331a  mov     rdx, rax; phKey
0x14003331d  mov     rcx, cs:ghAlgRC4; hAlgorithm
0x140033324  mov     [rsp+0E8h+pbSecret], r10; pbSecret
0x140033329  call    cs:__imp_BCryptGenerateSymmetricKey
0x140033330  nop     dword ptr [rax+rax+00h]
0x140033335  test    eax, eax
0x140033337  js      loc_140033AAE
0x14003333d  mov     ecx, [rsp+0E8h+cbInput]
0x140033344  lea     rax, [rsp+0E8h+arg_10]
0x14003334c  mov     [rsp+0E8h+var_A0], r15d; dwFlags
0x140033351  mov     r8d, ecx; cbInput
0x140033354  mov     [rsp+0E8h+pcbResult], rax; pcbResult
0x140033359  xor     r9d, r9d; pPaddingInfo
0x14003335c  mov     [rsp+0E8h+cbOutput], ecx; cbOutput
0x140033360  lea     rax, [rbx+4ECh]
0x140033367  mov     qword ptr [rsp+0E8h+dwFlags], rax; pbOutput
0x14003336c  mov     rdx, rax; pbInput
0x14003336f  mov     rax, [rsp+0E8h+phKey]
0x140033374  mov     [rsp+0E8h+cbSecret], r15d; cbIV
0x140033379  mov     dword ptr [rsp+0E8h+arg_10], r15d
0x140033381  mov     [rsp+0E8h+pbSecret], r15; pbIV
0x140033386  mov     rcx, [rax]; hKey
0x140033389  call    cs:__imp_BCryptEncrypt
0x140033390  nop     dword ptr [rax+rax+00h]
0x140033395  test    eax, eax
0x140033397  js      loc_140033ABA
0x14003339d  test    r14b, r14b
0x1400333a0  js      loc_140033599
0x1400333a6  bt      r14d, 0Ch
0x1400333ab  jb      loc_140033AC6
0x1400333b1  mov     rax, [rsp+0E8h+phKey]
0x1400333b6  mov     rcx, [rax]; hKey
0x1400333b9  test    rcx, rcx
0x1400333bc  jnz     loc_140033AD2
0x1400333c2  mov     ecx, [rsp+0E8h+cbInput]
0x1400333c9  xor     r9d, r9d; cbKeyObject
0x1400333cc  mov     [rsp+0E8h+dwFlags], r15d; dwFlags
0x1400333d1  xor     r8d, r8d; pbKeyObject
0x1400333d4  mov     [rsp+0E8h+cbSecret], ecx; cbSecret
0x1400333d8  mov     rdx, rax; phKey
0x1400333db  lea     rcx, [rbx+4ECh]
0x1400333e2  mov     [rsp+0E8h+pbSecret], rcx; pbSecret
0x1400333e7  mov     rcx, cs:ghAlgRC4; hAlgorithm
0x1400333ee  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400333f5  nop     dword ptr [rax+rax+00h]
0x1400333fa  test    eax, eax
0x1400333fc  js      loc_140033AEB
0x140033402  mov     rdx, [rsp+0E8h+pbOutput]; pbInput
0x140033407  lea     rax, [rsp+0E8h+arg_10]
0x14003340f  mov     r8d, [rsp+0E8h+var_98]; cbInput
0x140033414  xor     r9d, r9d; pPaddingInfo
0x140033417  mov     [rsp+0E8h+var_A0], r15d; dwFlags
0x14003341c  mov     [rsp+0E8h+pcbResult], rax; pcbResult
0x140033421  mov     rax, [rsp+0E8h+phKey]
0x140033426  mov     [rsp+0E8h+cbOutput], r8d; cbOutput
0x14003342b  mov     qword ptr [rsp+0E8h+dwFlags], rdx; pbOutput
0x140033430  mov     [rsp+0E8h+cbSecret], r15d; cbIV
0x140033435  mov     rcx, [rax]; hKey
0x140033438  mov     dword ptr [rsp+0E8h+arg_10], r15d
0x140033440  mov     [rsp+0E8h+pbSecret], r15; pbIV
0x140033445  call    cs:__imp_BCryptEncrypt
0x14003344c  nop     dword ptr [rax+rax+00h]
0x140033451  test    eax, eax
0x140033453  js      loc_140033AF7
0x140033459  bt      di, 0Dh
0x14003345e  jb      short loc_1400334CC
0x140033460  mov     rax, [rsp+0E8h+pbOutput]
0x140033465  mov     [r13+0], rax
0x140033469  mov     eax, [rsp+0E8h+var_98]
0x14003346d  mov     [r12], eax
0x140033471  mov     al, 1
0x140033473  add     rsp, 0A8h
0x14003347a  pop     r15
0x14003347c  pop     r14
0x14003347e  pop     r13
0x140033480  pop     r12
0x140033482  pop     rdi
0x140033483  pop     rsi
0x140033484  pop     rbp
0x140033485  pop     rbx
0x140033486  retn
0x140033488  and     r9d, ebp
0x14003348b  mov     eax, r8d
0x14003348e  sub     eax, r9d
0x140033491  jnz     loc_1400336A2
0x140033497  mov     [rsp+0E8h+var_94], r15d
0x14003349c  jmp     loc_140033172
0x1400334a1  mov     eax, [rsp+0E8h+var_94]
0x1400334a5  cmp     eax, 1
0x1400334a8  jz      loc_140033228
0x1400334ae  cmp     eax, 2
0x1400334b1  jnz     loc_14003383E
0x1400334b7  bt      di, 0Ch
0x1400334bc  jnb     short loc_140033459
0x1400334be  test    r14b, 4
0x1400334c2  jnz     loc_1400337B4
0x1400334c8  xor     al, al
0x1400334ca  jmp     short loc_140033473
0x1400334cc  test    r14b, 2
0x1400334d0  jz      short loc_1400334C8
0x1400334d2  mov     eax, [rbx+680h]
0x1400334d8  lea     r9, [rsp+0E8h+pbOutput]
0x1400334dd  mov     ecx, [rbx+6D4h]
0x1400334e3  movsxd  rdx, [rsp+0E8h+var_98]
0x1400334e8  mov     r8d, [rsp+0E8h+var_50]
0x1400334f0  shl     rcx, 20h
0x1400334f4  add     rcx, rax
0x1400334f7  shr     r8d, 8
0x1400334fb  mov     rax, [rsp+0E8h+var_78]
0x140033500  add     rcx, rdx
0x140033503  mov     [rbx+680h], ecx
0x140033509  and     r8d, 40h
0x14003350d  shr     rcx, 20h
0x140033511  mov     qword ptr [rsp+0E8h+cbSecret], rax
0x140033516  lea     rax, [rsp+0E8h+var_98]
0x14003351b  mov     [rbx+6D4h], ecx
0x140033521  mov     rcx, [rsp+0E8h+pbOutput]
0x140033526  mov     [rsp+0E8h+pbSecret], rax
0x14003352b  call    decompress
0x140033530  test    eax, eax
0x140033532  jz      loc_140033B03
0x140033538  movsxd  rdx, [rsp+0E8h+var_98]
0x14003353d  test    edx, edx
0x14003353f  jle     loc_140033B1E
0x140033545  cmp     edx, cs:glMRRU
0x14003354b  jg      loc_140033B1E
0x140033551  mov     ecx, [rbx+6CCh]
0x140033557  mov     eax, [rbx+678h]
0x14003355d  shl     rcx, 20h
0x140033561  add     rcx, rax
0x140033564  add     rcx, rdx
0x140033567  mov     [rbx+678h], ecx
0x14003356d  shr     rcx, 20h
0x140033571  mov     [rbx+6CCh], ecx
0x140033577  jmp     loc_140033460
0x14003357c  movzx   eax, word ptr [rbx+530h]
0x140033583  movzx   ecx, dx
0x140033586  sub     ecx, eax
0x140033588  cmp     ecx, 100h
0x14003358e  jl      loc_140033402
0x140033594  jmp     loc_14003329F
0x140033599  mov     word ptr [rbx+4ECh], 26D1h
0x1400335a2  mov     byte ptr [rbx+4EEh], 9Eh
0x1400335a9  jmp     loc_1400333B1
0x1400335ae  inc     byte ptr [r10+3]
0x1400335b2  add     byte ptr [r10+4], 3
0x1400335b7  add     byte ptr [r10+5], 0Dh
0x1400335bc  add     byte ptr [r10+6], 39h ; '9'
0x1400335c1  add     byte ptr [r10+7], 13h
0x1400335c6  jmp     loc_1400332EA
0x1400335cb  lea     r11, WPP_GLOBAL_Control
0x1400335d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335d9  cmp     rcx, r11
0x1400335dc  jnz     loc_140033B7E
0x1400335e2  bt      r14d, 0Bh
0x1400335e7  jb      loc_1400334C8
0x1400335ed  cmp     dword ptr [rbx+40h], 0
0x1400335f1  jz      loc_1400334C8
0x1400335f7  mov     edx, 84h
  ... truncated ...
```

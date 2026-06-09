# Smb2BatchedWrite

- ea: `0x140050b90`
- end: `0x140051397`
- name: `Smb2BatchedWrite`
- size: `2055`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001cc00`

## callees

- `0x140029764`
- `0x140029944`
- `0x14002997c`
- `0x1400299f0`
- `0x140029a78`
- `0x1400372c0`
- `0x140050b90`
- `0x1400513a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400511b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051288`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400511b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051288`
- `ntoskrnl!IoFreeMdl` at `0x14005119a`
- `ntoskrnl!IoFreeMdl` at `0x14005126f`
- `ntoskrnl!IoFreeMdl` at `0x14005119a`
- `ntoskrnl!IoFreeMdl` at `0x14005126f`
- `ntoskrnl!MmMdlPageContentsState` at `0x140051085`
- `ntoskrnl!MmMdlPageContentsState` at `0x14005109b`
- `ntoskrnl!MmMdlPageContentsState` at `0x140051085`
- `ntoskrnl!MmMdlPageContentsState` at `0x14005109b`
- `ntoskrnl!ExAllocatePool2` at `0x140050ff6`
- `ntoskrnl!ExAllocatePool2` at `0x140050ff6`
- `ntoskrnl!IoAllocateMdl` at `0x140050fd5`
- `ntoskrnl!IoAllocateMdl` at `0x140050fd5`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140050c2b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140050c2b`

## pseudocode

```c
__int64 __fastcall Smb2BatchedWrite(__int64 a1)
{
  int v1; // r15d
  volatile signed __int32 *v2; // rsi
  __int64 v3; // r12
  __int64 v4; // r13
  __int64 result; // rax
  __int64 v7; // r9
  unsigned int *v8; // rbx
  __int64 *v9; // rdi
  unsigned int v10; // r14d
  __int64 v11; // r8
  unsigned int i; // esi
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // r11d
  __int64 v19; // rbx
  __m128i v20; // xmm9
  __m128i v21; // xmm10
  __int64 v22; // xmm11_8
  __int64 v23; // r13
  unsigned int v24; // r12d
  __m128i v25; // xmm7
  __m128i v26; // xmm6
  ULONG v27; // edi
  __int64 v28; // xmm8_8
  unsigned int v29; // r15d
  __int64 v30; // r9
  int v31; // r11d
  int v32; // r11d
  __int64 v33; // r8
  PMDL Mdl; // rdi
  _QWORD *Pool2; // rax
  _QWORD *v36; // rsi
  int v37; // r13d
  int v38; // r14d
  __int64 j; // r15
  __int64 v40; // r12
  __int64 v41; // rbx
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // r8
  char *v45; // r9
  size_t v46; // rbx
  volatile signed __int32 *v47; // r15
  volatile signed __int32 v48; // eax
  unsigned int v49; // r14d
  volatile signed __int32 v50; // ebx
  __int64 v51; // rcx
  char v52; // r10
  __int64 v53; // [rsp+28h] [rbp-D8h]
  unsigned int v54; // [rsp+28h] [rbp-D8h]
  __int64 v55; // [rsp+50h] [rbp-B0h]
  unsigned int v56; // [rsp+58h] [rbp-A8h]
  unsigned int v57; // [rsp+58h] [rbp-A8h]
  struct _MDL *v58; // [rsp+60h] [rbp-A0h]
  __m128i v59; // [rsp+68h] [rbp-98h] BYREF
  __m128i v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  __m128i v62; // [rsp+90h] [rbp-70h] BYREF
  __m128i v63; // [rsp+A0h] [rbp-60h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  __m128i v66; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+E0h] [rbp-20h]
  int v69; // [rsp+1A0h] [rbp+A0h]
  unsigned int v70; // [rsp+1A8h] [rbp+A8h]
  unsigned int v71; // [rsp+1B0h] [rbp+B0h]
  char v72; // [rsp+1B8h] [rbp+B8h]

  v69 = a1;
  v1 = *(_DWORD *)(a1 + 540);
  v2 = *(volatile signed __int32 **)(a1 + 544);
  v3 = *(_QWORD *)(a1 + 40);
  v4 = *(_QWORD *)(a1 + 552);
  v56 = *(_DWORD *)(a1 + 572);
  v70 = *(_DWORD *)(a1 + 512);
  v64 = 0;
  v55 = (__int64)v2;
  v62 = 0;
  v63 = 0;
  v72 = *(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 428);
  *(_QWORD *)(a1 + 184) = 0;
  if ( !v2 )
    __int2c();
  if ( *(_DWORD *)v4 != 1 )
    return 3221225560LL;
  v7 = *(unsigned int *)(v4 + 4);
  if ( (v7 & 0xFFFFFFF0) != 0 )
    return 3221225659LL;
  if ( v1 == 1344075 && *(_BYTE *)(v3 + 64) )
    return 3221225506LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a0d11c23c33e3a5bacf27bfb28bbdaa8_Traceguids, v7);
  }
  v8 = (unsigned int *)(v4 + 16);
  if ( v1 == 1344075 )
    v9 = *(__int64 **)(v4 + 32);
  else
    v9 = *(__int64 **)(v3 + 8);
  v10 = 0;
  if ( v4 != -16 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v9 )
          __int2c();
        v11 = v8[3];
        if ( *((_DWORD *)v9 + 10) != (_DWORD)v11 )
          __int2c();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          LODWORD(v53) = *v8;
          WPP_SF_DqDDDD(WPP_GLOBAL_Control->AttachedDevice, 13, v11, v10, v9, v53, v8[1], v8[2], v8[3]);
        }
        for ( i = 0; i < v8[2]; ++i )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_DDiDD(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              2LL * i,
              v10,
              i,
              *(_QWORD *)&v8[4 * i + 6],
              v8[4 * i + 8],
              v8[4 * i + 9]);
          }
        }
        v13 = *v8;
        if ( (_DWORD)v13 )
          v8 = (unsigned int *)((char *)v8 + v13);
        else
          v8 = 0;
        if ( v1 == 1344075 )
          break;
        v9 = (__int64 *)*v9;
        ++v10;
        if ( !v8 )
          goto LABEL_41;
      }
      if ( !v8 )
        break;
      v9 = (__int64 *)*((_QWORD *)v8 + 2);
      ++v10;
    }
    v9 = 0;
LABEL_41:
    v2 = (volatile signed __int32 *)v55;
  }
  if ( v9 )
    __int2c();
  v14 = 16LL * v70;
  if ( v14 > 0xFFFFFFFF )
    return 3221225621LL;
  if ( v56 && v56 < (int)v14 + 8 )
    return 3221225507LL;
  LOBYTE(v7) = v1 == 1344075;
  *v2 = v70 + 1;
  Smb2BatchedWriteIteratorInitialize(&v62, v4, v3, v7);
  while ( 2 )
  {
    v19 = v63.m128i_i64[0];
    if ( !v63.m128i_i64[0] )
      __int2c();
    v20 = v62;
    v21 = v63;
    v22 = v64;
    v23 = _mm_srli_si128(v62, 8).m128i_u64[0];
    v24 = _mm_cvtsi128_si32(_mm_srli_si128(v63, 12));
    v25 = v62;
    v26 = v63;
    v68 = v64;
    v59 = v62;
    v27 = *(_DWORD *)(v23 + 12);
    v28 = v64;
    v65 = v23;
    v57 = v24;
    v60 = v63;
    v66 = v62;
    v67 = v63;
    if ( !v27 )
    {
      v50 = 0;
      v49 = _mm_cvtsi128_si32(_mm_srli_si128(v63, 12));
      goto LABEL_95;
    }
    v71 = v18;
    v29 = v18;
    LOBYTE(v17) = 0;
    if ( !(unsigned __int8)Smb2BatchedWriteIteratorNext(&v66, v15, v16, v17) )
    {
LABEL_88:
      v47 = (volatile signed __int32 *)v55;
      v36 = 0;
      Mdl = 0;
      v49 = _mm_cvtsi128_si32(_mm_srli_si128(v26, 12));
      v48 = Smb2BatchedWriteExecute(v69, v19, v24, v23, v55, v31 + v49 - v24, 0, 0);
      goto LABEL_89;
    }
    while ( 1 )
    {
      v32 = *(_DWORD *)(v66.m128i_i64[1] + 12);
      if ( !v32 || v72 )
        break;
      v33 = v60.m128i_i64[0];
      if ( v60.m128i_i64[0] != v67.m128i_i64[0] )
      {
        LOBYTE(v30) = 1;
LABEL_61:
        if ( ((*(_DWORD *)(v60.m128i_i64[0] + 44)
             + *(_DWORD *)(v59.m128i_i64[1] + 8)
             + *(_DWORD *)(v59.m128i_i64[1] + 12))
            & 0xFFF) != 0
          || ((*(_DWORD *)(v66.m128i_i64[1] + 8) + *(_DWORD *)(v67.m128i_i64[0] + 44)) & 0xFFF) != 0 )
        {
          goto LABEL_67;
        }
        goto LABEL_63;
      }
      v30 = (unsigned __int8)v30;
      if ( *(_DWORD *)(v59.m128i_i64[1] + 8) + *(_DWORD *)(v59.m128i_i64[1] + 12) != *(_DWORD *)(v66.m128i_i64[1] + 8) )
        v30 = 1;
      if ( (_BYTE)v30 )
        goto LABEL_61;
LABEL_63:
      v25 = v66;
      v27 += v32;
      v26 = v67;
      ++v29;
      v28 = v68;
      v71 = v29;
      v59 = v66;
      v60 = v67;
      if ( !(unsigned __int8)Smb2BatchedWriteIteratorNext(&v66, v66.m128i_i64[1], v33, v30) )
        goto LABEL_66;
    }
    v31 = 1;
LABEL_66:
    if ( !(_BYTE)v30 )
      goto LABEL_88;
LABEL_67:
    Mdl = IoAllocateMdl((PVOID)(*(_QWORD *)(v19 + 32) + *(unsigned int *)(v19 + 44)), v27, 0, 0, 0);
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16LL * v29, 2000844882);
    v36 = Pool2;
    if ( !Mdl )
    {
      if ( Pool2 )
      {
        ExFreePoolWithTag(Pool2, 0x77427852u);
        v36 = 0;
      }
      goto LABEL_87;
    }
    if ( !Pool2 )
    {
      IoFreeMdl(Mdl);
      Mdl = 0;
LABEL_87:
      v47 = (volatile signed __int32 *)v55;
      v25 = v20;
      v26 = v21;
      v28 = v22;
      v48 = Smb2BatchedWriteExecute(v69, v19, v24, v23, v55, 1, 0, 0);
      v49 = _mm_cvtsi128_si32(_mm_srli_si128(v21, 12));
      goto LABEL_89;
    }
    v61 = v22;
    v58 = Mdl + 1;
    v37 = 0;
    v38 = 0;
    Mdl->MdlFlags |= 0x4010u;
    v25 = v20;
    v26 = v21;
    v28 = v22;
    v59 = v20;
    v60 = v21;
    if ( v29 )
    {
      for ( j = 0; ; ++j )
      {
        v40 = v59.m128i_i64[1];
        v41 = v60.m128i_i64[0];
        v42 = 2 * j;
        v36[v42] = *(_QWORD *)v59.m128i_i64[1];
        LODWORD(v36[v42 + 1]) = v37;
        HIDWORD(v36[v42 + 1]) = *(_DWORD *)(v40 + 12);
        if ( (unsigned int)MmMdlPageContentsState(v41, 2) != 1 )
          MmMdlPageContentsState(Mdl, 0);
        v43 = (unsigned int)(*(_DWORD *)(v41 + 44) + *(_DWORD *)(v40 + 8));
        v44 = ((v43 & 0xFFF) + *(unsigned int *)(v40 + 12) + 4095LL) >> 12;
        v45 = (char *)(v41 + 8 * ((v43 >> 12) + 6));
        if ( (v43 & 0xFFF) != 0 && v38 )
        {
          v45 += 8;
          v44 = (unsigned int)(v44 - 1);
        }
        if ( (_DWORD)v44 )
        {
          v46 = 8LL * (unsigned int)v44;
          memmove(v58, v45, v46);
          v58 = (struct _MDL *)((char *)v58 + v46);
        }
        if ( ++v38 >= v71 )
          break;
        v37 += *(_DWORD *)(v40 + 12);
        if ( !(unsigned __int8)Smb2BatchedWriteIteratorNext(&v59, v43, v44, v45) )
          __int2c();
      }
      v28 = v61;
      v26 = v60;
      v29 = v71;
      v25 = v59;
      v24 = v57;
    }
    v54 = v29;
    v47 = (volatile signed __int32 *)v55;
    v48 = Smb2BatchedWriteExecute(v69, (_DWORD)Mdl, v24, (_DWORD)v36, v55, v54, 1, 1);
    v23 = v65;
    v49 = _mm_cvtsi128_si32(_mm_srli_si128(v26, 12));
LABEL_89:
    v50 = v48;
    if ( v48 != 259 )
    {
      if ( Mdl )
        IoFreeMdl(Mdl);
      if ( v36 )
        ExFreePoolWithTag(v36, 0x77427852u);
      v2 = (volatile signed __int32 *)v55;
LABEL_95:
      if ( v24 <= v49 )
      {
        while ( 1 )
        {
          v51 = 2LL * v24;
          v2[2 * v51 + 2] = v50;
          v2[2 * v51 + 3] = *(_DWORD *)(v23 + 12);
          *(_QWORD *)&v2[2 * v51 + 4] = *(_QWORD *)v23;
          if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
            return 0;
          if ( !(unsigned __int8)Smb2BatchedWriteIteratorNext(&v62, v15, v16, v17) )
            break;
          v24 = v63.m128i_u32[3];
          if ( v63.m128i_i32[3] > v49 )
            break;
          v23 = v62.m128i_i64[1];
        }
      }
      v47 = (volatile signed __int32 *)v55;
    }
    v64 = v28;
    v62 = v25;
    v63 = v26;
    if ( (unsigned __int8)Smb2BatchedWriteIteratorNext(&v62, v15, v16, v17) )
    {
      v2 = (volatile signed __int32 *)v55;
      continue;
    }
    break;
  }
  if ( _InterlockedExchangeAdd(v47, 0xFFFFFFFF) == 1 )
    return 0;
  result = 0;
  if ( v52 )
    return 259;
  return result;
}

```

## disassembly

```asm
0x140050b90  mov     rax, rsp
0x140050b93  mov     [rax+8], rcx
0x140050b97  push    rbp
0x140050b98  push    rbx
0x140050b99  push    rsi
0x140050b9a  push    rdi
0x140050b9b  push    r12
0x140050b9d  push    r13
0x140050b9f  push    r14
0x140050ba1  push    r15
0x140050ba3  lea     rbp, [rsp-58h]
0x140050ba8  sub     rsp, 158h
0x140050baf  mov     r15d, [rcx+21Ch]
0x140050bb6  xorps   xmm0, xmm0
0x140050bb9  mov     rsi, [rcx+220h]
0x140050bc0  mov     edi, 14824Bh
0x140050bc5  mov     r12, [rcx+28h]
0x140050bc9  cmp     r15d, edi
0x140050bcc  mov     r13, [rcx+228h]
0x140050bd3  mov     rbx, rcx
0x140050bd6  movaps  xmmword ptr [rax-58h], xmm6
0x140050bda  setz    byte ptr [rbp+90h+arg_10]
0x140050be1  movaps  xmmword ptr [rax-68h], xmm7
0x140050be5  movaps  xmmword ptr [rax-78h], xmm8
0x140050bea  movaps  xmmword ptr [rax-88h], xmm9
0x140050bf2  movaps  xmmword ptr [rax-98h], xmm10
0x140050bfa  movaps  xmmword ptr [rax-0A8h], xmm11
0x140050c02  mov     eax, [rcx+23Ch]
0x140050c08  mov     [rsp+190h+var_138], eax
0x140050c0c  mov     eax, [rcx+200h]
0x140050c12  mov     [rbp+90h+arg_8], eax
0x140050c18  xor     eax, eax
0x140050c1a  mov     [rbp+90h+var_E0], rax
0x140050c1e  mov     [rsp+190h+var_140], rsi
0x140050c23  movups  [rbp+90h+var_100], xmm0
0x140050c27  movups  [rbp+90h+var_F0], xmm0
0x140050c2b  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140050c32  nop     dword ptr [rax+rax+00h]
0x140050c37  mov     al, [rax+1ACh]
0x140050c3d  mov     [rbp+90h+arg_18], al
0x140050c43  mov     qword ptr [rbx+0B8h], 0
0x140050c4e  test    rsi, rsi
0x140050c51  jnz     short loc_140050C55
0x140050c53  int     2Ch; Windows NT - assertion failure
0x140050c55  mov     r11d, 1
0x140050c5b  cmp     [r13+0], r11d
0x140050c5f  jz      short loc_140050C6B
0x140050c61  mov     eax, 0C0000058h
0x140050c66  jmp     loc_140051360
0x140050c6b  mov     r9d, [r13+4]
0x140050c6f  test    r9d, 0FFFFFFF0h
0x140050c76  jz      short loc_140050C82
0x140050c78  mov     eax, 0C00000BBh
0x140050c7d  jmp     loc_140051360
0x140050c82  cmp     r15d, edi
0x140050c85  jnz     short loc_140050C99
0x140050c87  cmp     byte ptr [r12+40h], 0
0x140050c8d  jz      short loc_140050C99
0x140050c8f  mov     eax, 0C0000022h
0x140050c94  jmp     loc_140051360
0x140050c99  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050ca0  lea     rax, WPP_GLOBAL_Control
0x140050ca7  cmp     rcx, rax
0x140050caa  jz      short loc_140050CDB
0x140050cac  mov     eax, [rcx+2Ch]
0x140050caf  test    al, 2
0x140050cb1  jz      short loc_140050CD4
0x140050cb3  cmp     byte ptr [rcx+29h], 4
0x140050cb7  jb      short loc_140050CD4
0x140050cb9  mov     rcx, [rcx+18h]
0x140050cbd  lea     r8, WPP_a0d11c23c33e3a5bacf27bfb28bbdaa8_Traceguids
0x140050cc4  mov     edx, 0Ch
0x140050cc9  call    WPP_SF_d
0x140050cce  mov     r11d, 1
0x140050cd4  lea     rax, WPP_GLOBAL_Control
0x140050cdb  lea     rbx, [r13+10h]
0x140050cdf  cmp     r15d, edi
0x140050ce2  jz      short loc_140050CEB
0x140050ce4  mov     rdi, [r12+8]
0x140050ce9  jmp     short loc_140050CEF
0x140050ceb  mov     rdi, [rbx+10h]
0x140050cef  xor     r14d, r14d
0x140050cf2  test    rbx, rbx
0x140050cf5  jz      loc_140050E0F
0x140050cfb  test    rdi, rdi
0x140050cfe  jnz     short loc_140050D02
0x140050d00  int     2Ch; Windows NT - assertion failure
0x140050d02  mov     r8d, [rbx+0Ch]
0x140050d06  cmp     [rdi+28h], r8d
0x140050d0a  jz      short loc_140050D0E
0x140050d0c  int     2Ch; Windows NT - assertion failure
0x140050d0e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050d15  cmp     rcx, rax
0x140050d18  jz      short loc_140050D5D
0x140050d1a  mov     eax, [rcx+2Ch]
0x140050d1d  test    al, 2
0x140050d1f  jz      short loc_140050D56
0x140050d21  cmp     byte ptr [rcx+29h], 4
0x140050d25  jb      short loc_140050D56
0x140050d27  mov     eax, [rbx+8]
0x140050d2a  mov     edx, 0Dh
0x140050d2f  mov     rcx, [rcx+18h]
0x140050d33  mov     r9d, r14d
0x140050d36  mov     [rsp+190h+var_150], r8d
0x140050d3b  mov     [rsp+190h+var_158], eax
0x140050d3f  mov     eax, [rbx+4]
0x140050d42  mov     [rsp+190h+var_160], eax
0x140050d46  mov     eax, [rbx]
0x140050d48  mov     dword ptr [rsp+190h+var_168], eax
0x140050d4c  mov     [rsp+190h+Irp], rdi
0x140050d51  call    WPP_SF_DqDDDD
0x140050d56  lea     rax, WPP_GLOBAL_Control
0x140050d5d  xor     esi, esi
0x140050d5f  lea     r11d, [rsi+1]
0x140050d63  cmp     [rbx+8], esi
0x140050d66  jbe     short loc_140050DCD
0x140050d68  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050d6f  cmp     rcx, rax
0x140050d72  jz      short loc_140050DC5
0x140050d74  mov     eax, [rcx+2Ch]
0x140050d77  test    al, 2
0x140050d79  jz      short loc_140050DBE
0x140050d7b  cmp     byte ptr [rcx+29h], 4
0x140050d7f  jb      short loc_140050DBE
0x140050d81  mov     rcx, [rcx+18h]
0x140050d85  mov     edx, 0Eh
0x140050d8a  mov     r8d, esi
0x140050d8d  mov     r9d, r14d
0x140050d90  add     r8, r8
0x140050d93  mov     eax, [rbx+r8*8+24h]
0x140050d98  mov     [rsp+190h+var_158], eax
0x140050d9c  mov     eax, [rbx+r8*8+20h]
0x140050da1  mov     [rsp+190h+var_160], eax
0x140050da5  mov     rax, [rbx+r8*8+18h]
0x140050daa  mov     [rsp+190h+var_168], rax
0x140050daf  mov     dword ptr [rsp+190h+Irp], esi
0x140050db3  call    WPP_SF_DDiDD
0x140050db8  mov     r11d, 1
0x140050dbe  lea     rax, WPP_GLOBAL_Control
0x140050dc5  add     esi, r11d
0x140050dc8  cmp     esi, [rbx+8]
0x140050dcb  jb      short loc_140050D68
0x140050dcd  mov     eax, [rbx]
0x140050dcf  test    eax, eax
0x140050dd1  jz      short loc_140050DD8
0x140050dd3  add     rbx, rax
0x140050dd6  jmp     short loc_140050DDA
0x140050dd8  xor     ebx, ebx
0x140050dda  cmp     r15d, 14824Bh
0x140050de1  jz      short loc_140050DF0
0x140050de3  mov     rdi, [rdi]
0x140050de6  add     r14d, r11d
0x140050de9  test    rbx, rbx
0x140050dec  jz      short loc_140050E0A
0x140050dee  jmp     short loc_140050DFC
0x140050df0  test    rbx, rbx
0x140050df3  jz      short loc_140050E08
0x140050df5  mov     rdi, [rbx+10h]
0x140050df9  add     r14d, r11d
0x140050dfc  lea     rax, WPP_GLOBAL_Control
0x140050e03  jmp     loc_140050CFB
0x140050e08  xor     edi, edi
0x140050e0a  mov     rsi, [rsp+190h+var_140]
0x140050e0f  test    rdi, rdi
0x140050e12  jz      short loc_140050E16
0x140050e14  int     2Ch; Windows NT - assertion failure
0x140050e16  mov     edx, [rbp+90h+arg_8]
0x140050e1c  mov     ecx, 0FFFFFFFFh
0x140050e21  mov     eax, edx
0x140050e23  shl     rax, 4
0x140050e27  cmp     rax, rcx
0x140050e2a  ja      loc_14005135B
0x140050e30  mov     ecx, [rsp+190h+var_138]
0x140050e34  test    ecx, ecx
0x140050e36  jz      short loc_140050E49
0x140050e38  add     eax, 8
0x140050e3b  cmp     ecx, eax
0x140050e3d  jnb     short loc_140050E49
0x140050e3f  mov     eax, 0C0000023h
0x140050e44  jmp     loc_140051360
0x140050e49  mov     r9b, byte ptr [rbp+90h+arg_10]
0x140050e50  lea     eax, [rdx+1]
0x140050e53  xor     r10b, r10b
0x140050e56  mov     [rsi], eax
0x140050e58  mov     rdx, r13
0x140050e5b  mov     byte ptr [rbp+90h+arg_8], r10b
0x140050e62  mov     r8, r12
0x140050e65  lea     rcx, [rbp+90h+var_100]
0x140050e69  call    Smb2BatchedWriteIteratorInitialize
0x140050e6e  mov     rbx, qword ptr [rbp+90h+var_F0]
0x140050e72  test    rbx, rbx
0x140050e75  jnz     short loc_140050E79
0x140050e77  int     2Ch; Windows NT - assertion failure
0x140050e79  movups  xmm9, [rbp+90h+var_100]
0x140050e7e  movups  xmm10, [rbp+90h+var_F0]
0x140050e83  movsd   xmm11, [rbp+90h+var_E0]
0x140050e89  movdqa  xmm0, xmm9
0x140050e8e  psrldq  xmm0, 8
0x140050e93  movdqa  xmm1, xmm10
0x140050e98  movq    r13, xmm0
0x140050e9d  psrldq  xmm1, 0Ch
0x140050ea2  movd    r12d, xmm1
0x140050ea7  movups  xmm7, xmm9
0x140050eab  movups  xmm6, xmm10
0x140050eaf  movsd   [rbp+90h+var_B0], xmm11
0x140050eb5  movups  [rsp+190h+var_128], xmm7
0x140050eba  mov     edi, [r13+0Ch]
0x140050ebe  movaps  xmm8, xmm11
0x140050ec2  mov     [rbp+90h+var_D8], r13
0x140050ec6  mov     [rsp+190h+var_138], r12d
0x140050ecb  movups  [rsp+190h+var_118], xmm6
0x140050ed0  movups  [rbp+90h+var_D0], xmm9
0x140050ed5  movups  [rbp+90h+var_C0], xmm10
0x140050eda  test    edi, edi
0x140050edc  jz      loc_1400512FA
0x140050ee2  lea     rcx, [rbp+90h+var_D0]
0x140050ee6  mov     [rbp+90h+arg_10], r11d
0x140050eed  mov     r15d, r11d
0x140050ef0  xor     r9b, r9b
0x140050ef3  call    Smb2BatchedWriteIteratorNext
0x140050ef8  test    al, al
0x140050efa  jz      loc_140051212
0x140050f00  mov     rdx, qword ptr [rbp+90h+var_D0+8]
0x140050f04  mov     r11d, [rdx+0Ch]
0x140050f08  test    r11d, r11d
0x140050f0b  jz      loc_140050FAE
0x140050f11  cmp     [rbp+90h+arg_18], 0
0x140050f18  jnz     loc_140050FAE
0x140050f1e  mov     r8, qword ptr [rsp+190h+var_118]
0x140050f23  mov     r10, qword ptr [rbp+90h+var_C0]
0x140050f27  mov     rcx, qword ptr [rsp+190h+var_128+8]
0x140050f2c  cmp     r8, r10
0x140050f2f  jnz     short loc_140050F4E
0x140050f31  mov     eax, [rcx+0Ch]
0x140050f34  add     eax, [rcx+8]
0x140050f37  cmp     eax, [rdx+8]
0x140050f3a  mov     eax, 1
0x140050f3f  movzx   r9d, r9b
0x140050f43  cmovnz  r9d, eax
0x140050f47  test    r9b, r9b
0x140050f4a  jz      short loc_140050F70
0x140050f4c  jmp     short loc_140050F51
0x140050f4e  mov     r9b, 1
0x140050f51  mov     eax, [rcx+0Ch]
0x140050f54  add     eax, [rcx+8]
0x140050f57  add     eax, [r8+2Ch]
0x140050f5b  test    eax, 0FFFh
0x140050f60  jnz     short loc_140050FBD
0x140050f62  mov     eax, [r10+2Ch]
0x140050f66  add     eax, [rdx+8]
0x140050f69  test    eax, 0FFFh
0x140050f6e  jnz     short loc_140050FBD
0x140050f70  movups  xmm7, [rbp+90h+var_D0]
0x140050f74  add     edi, r11d
0x140050f77  mov     r11d, 1
0x140050f7d  movups  xmm6, [rbp+90h+var_C0]
0x140050f81  lea     rcx, [rbp+90h+var_D0]
0x140050f85  add     r15d, r11d
0x140050f88  movsd   xmm8, [rbp+90h+var_B0]
0x140050f8e  mov     [rbp+90h+arg_10], r15d
0x140050f95  movups  [rsp+190h+var_128], xmm7
0x140050f9a  movups  [rsp+190h+var_118], xmm6
0x140050f9f  call    Smb2BatchedWriteIteratorNext
0x140050fa4  test    al, al
0x140050fa6  jnz     loc_140050F00
0x140050fac  jmp     short loc_140050FB4
0x140050fae  mov     r11d, 1
0x140050fb4  test    r9b, r9b
0x140050fb7  jz      loc_140051212
0x140050fbd  mov     ecx, [rbx+2Ch]
0x140050fc0  xor     r9d, r9d; ChargeQuota
0x140050fc3  add     rcx, [rbx+20h]; VirtualAddress
0x140050fc7  xor     r8d, r8d; SecondaryBuffer
0x140050fca  mov     edx, edi; Length
0x140050fcc  mov     [rsp+190h+Irp], 0; Irp
0x140050fd5  call    cs:__imp_IoAllocateMdl
0x140050fdc  nop     dword ptr [rax+rax+00h]
0x140050fe1  mov     edx, r15d
0x140050fe4  mov     ecx, 40h ; '@'
0x140050fe9  shl     rdx, 4
0x140050fed  mov     r8d, 77427852h
0x140050ff3  mov     rdi, rax
0x140050ff6  call    cs:__imp_ExAllocatePool2
0x140050ffd  nop     dword ptr [rax+rax+00h]
0x140051002  mov     rsi, rax
0x140051005  test    rdi, rdi
0x140051008  jz      loc_1400511AA
0x14005100e  test    rax, rax
0x140051011  jz      loc_140051197
0x140051017  lea     rax, [rdi+30h]
0x14005101b  movsd   [rbp+90h+var_108], xmm11
0x140051021  mov     [rsp+190h+var_130], rax
0x140051026  xor     r13d, r13d
0x140051029  mov     eax, 4010h
0x14005102e  xor     r14d, r14d
0x140051031  or      [rdi+0Ah], ax
0x140051035  movups  xmm7, xmm9
0x140051039  movups  xmm6, xmm10
0x14005103d  movaps  xmm8, xmm11
0x140051041  movups  [rsp+190h+var_128], xmm7
  ... truncated ...
```

# CStmt::BuildParamList(CExtByteBuffer *,int)

- ea: `0x18007e650`
- end: `0x18007ef56`
- name: `?BuildParamList@CStmt@@AEAAHPEAVCExtByteBuffer@@H@Z`
- size: `2310`
- prototype: `int(CStmt *__hidden this, struct CExtByteBuffer *, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180025520`
- `0x180079680`
- `0x18007fc20`
- `0x180083c90`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180009de0`
- `0x18007e650`
- `0x1800dfb80`
- `0x180134658`
- `0x180134738`
- `0x1801a65e1`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x18007e7f7`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x18007e834`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x18007e7f7`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x18007e834`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eaa0`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eafb`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eba5`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007ec31`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eaa0`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eafb`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007eba5`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18007ec31`

## string_xrefs

- `0x18007ed5b`: ` READONLY`

## pseudocode

```c
__int64 __fastcall CStmt::BuildParamList(CStmt *this, struct CExtByteBuffer *a2, int a3)
{
  int v3; // esi
  CStmt *v5; // rbx
  _QWORD *v6; // rcx
  __int64 v7; // r13
  unsigned __int64 v8; // r15
  int v9; // r10d
  wchar_t *v10; // r14
  int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // r8
  _QWORD *v14; // rax
  _QWORD *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // rsi
  unsigned __int64 *v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  int v25; // eax
  int v26; // ebx
  unsigned __int16 v27; // cx
  __int16 v28; // ax
  __int16 v29; // cx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  wchar_t v38; // ax
  wchar_t *v39; // rax
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v46; // r8
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // r8
  unsigned int v52; // ebx
  __int64 v53; // rdx
  __int64 v55; // [rsp+30h] [rbp-D0h]
  __int64 v57; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v59; // [rsp+50h] [rbp-B0h]
  _QWORD *v60; // [rsp+58h] [rbp-A8h]
  _QWORD v61[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Src[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v63; // [rsp+74h] [rbp-8Ch] BYREF
  wchar_t Buffer[389]; // [rsp+76h] [rbp-8Ah] BYREF

  v3 = a3;
  v5 = this;
  memset_0(Src, 0, 0x306u);
  v6 = (_QWORD *)*((_QWORD *)v5 + 15);
  v7 = *((_QWORD *)v5 + 74);
  v8 = 1;
  v61[0] = 0;
  v9 = 0;
  v60 = v6;
  v10 = 0;
  v11 = 0;
  v59 = v6[176];
  if ( !v59 )
    return 0;
  v12 = 64;
  v57 = 64;
  v13 = 40;
  v55 = 40;
  v14 = (_QWORD *)(v7 + 88);
  v15 = (_QWORD *)(v7 + 88);
  while ( 1 )
  {
    if ( v7 )
    {
      if ( v3 )
      {
        v15 = v14;
        if ( (*(_BYTE *)(v7 + 128) & 0x18) != 0 )
        {
          v15 = (_QWORD *)(v7 + 88);
          v16 = v13 + *(_QWORD *)(v7 + 88) - 40LL;
          if ( (*(_BYTE *)(v16 + 24) & 1) != 0 )
          {
            while ( (*(_BYTE *)(*(_QWORD *)v16 + 64LL) & 1) == 0 )
            {
              v16 = *(_QWORD *)(v16 + 16);
              if ( !v16 )
              {
                v17 = 0;
                goto LABEL_11;
              }
            }
          }
          v17 = *(_QWORD *)v16;
LABEL_11:
          if ( (*(_BYTE *)(v17 + 56) & 4) != 0 )
          {
            v18 = *(_DWORD *)(*(_QWORD *)(v17 + 24)
                            + *(_QWORD *)(v7 + 32) * (*((_QWORD *)v5 + 75) - 1LL)
                            + *(_QWORD *)(v7 + 8));
            if ( v18 == 13 || v18 == 3 && *(_WORD *)(v17 + 84) <= 1u )
              goto LABEL_106;
            v13 = v55;
          }
        }
      }
      v19 = *(_QWORD *)(*v15 + v13 - 32);
    }
    else
    {
      v20 = (unsigned __int64 *)v6[178];
      if ( !v20 || v8 > *v20 || (v19 = *(_QWORD *)(v20[3] + 8 * v8 - 8)) == 0 )
      {
        v21 = v6[179];
        if ( v21 )
          v19 = v21 + v12 - 64;
        else
          v19 = 0;
      }
    }
    if ( v9 )
    {
      wmemcpy(Src, L",@P", 3);
      _itow_s(v8, Buffer, 0x180u, 10);
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      v23 = v22 + 3;
    }
    else
    {
      *(_DWORD *)Src = 5242944;
      _itow_s(v8, &v63, 0x181u, 10);
      v24 = -1;
      do
        ++v24;
      while ( Buffer[v24 - 1] );
      v23 = v24 + 2;
    }
    Src[v23] = 32;
    v61[0] = v23 + 1;
    v25 = CExtByteBuffer::WriteIntoExtBuffer(a2, Src, 2 * (v23 + 1));
    v11 = v25;
    if ( v25 < 0 )
      break;
    v26 = *(_DWORD *)(v19 + 44);
    if ( v26 != 25 && v26 != 30 )
    {
      v27 = *(_DWORD *)(v19 + 44);
      if ( (unsigned __int16)v26 == 16 )
      {
        v28 = 16;
        v29 = 23;
LABEL_37:
        if ( *(_QWORD *)(v19 + 16) == 4 )
          v28 = v29;
        v27 = v28;
      }
      else if ( (unsigned __int16)v26 == 17 )
      {
        v28 = 17;
        v29 = 24;
        goto LABEL_37;
      }
      if ( v27 < 0x23u )
      {
        v10 = (wchar_t *)(&g_SqlServerTypes)[v27];
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 )
          v11 = bidTraceHR(`GetSSTypeString'::`2'::_bidSrcFile2A[0], 157705, 2147614731LL);
        else
          v11 = -2147352565;
        if ( v11 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v30 = (unsigned int)v11;
            v31 = 841737;
            goto LABEL_116;
          }
          goto LABEL_117;
        }
      }
      v32 = -1;
      do
        ++v32;
      while ( v10[v32] );
      v61[0] = v32;
      goto LABEL_69;
    }
    v33 = *(_QWORD *)(v19 + 56);
    if ( v33 )
    {
      v34 = 2;
      if ( v26 == 25 )
        v34 = 0;
      v35 = CParamProps::Get3PartName(v33, Src, 387, v61, v34);
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_58;
      v35 = bidTraceHR(off_1802603D0[0], 858121, 2147749409LL);
    }
    if ( v35 < 0 )
    {
LABEL_58:
      v36 = 387;
      v37 = Src;
      do
      {
        if ( v36 == -2147483259 )
          break;
        v38 = *(wchar_t *)((char *)v37 + (char *)L"Dummy.UDTOrTVP" - (char *)Src);
        if ( !v38 )
          break;
        *v37++ = v38;
        --v36;
      }
      while ( v36 );
      v39 = v37 - 1;
      v11 = -2147024774;
      if ( v36 )
      {
        v39 = v37;
        v11 = 0;
      }
      *v39 = 0;
      if ( !v36 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v30 = (unsigned int)v11;
          v31 = 866313;
LABEL_116:
          _mm_lfence();
          bidTraceHR(off_1802603D0[0], v31, v30);
        }
LABEL_117:
        v52 = 40157;
        goto LABEL_129;
      }
      v40 = -1;
      do
        ++v40;
      while ( Src[v40] );
      v61[0] = v40;
    }
    v10 = Src;
LABEL_69:
    _mm_lfence();
    v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, v10, 2LL * v61[0]);
    v11 = v41;
    if ( v41 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_117;
      v31 = 875529;
LABEL_115:
      v30 = (unsigned int)v41;
      goto LABEL_116;
    }
    switch ( v26 )
    {
      case 1:
      case 2:
      case 4:
      case 5:
      case 7:
      case 8:
        _mm_lfence();
        Src[0] = 40;
        v47 = *(_QWORD *)(v19 + 32);
        if ( !v47 )
          LODWORD(v47) = 1;
        _ltow_s(v47, &Src[1], 0x182u, 10);
        v48 = -1;
        do
          ++v48;
        while ( Src[v48] );
        Src[v48] = 41;
        v61[0] = v48 + 1;
        v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, Src, 2 * (v48 + 1));
        v11 = v41;
        if ( v41 >= 0 )
          goto LABEL_103;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        v31 = 922633;
        goto LABEL_115;
      case 15:
        _mm_lfence();
        Src[0] = 40;
        _ltow_s(*(unsigned __int8 *)(v19 + 40), &Src[1], 0x182u, 10);
        v42 = -1;
        do
          ++v42;
        while ( Src[v42] );
        v61[0] = v42;
        v43 = v42;
        if ( *(_BYTE *)(v19 + 41) )
        {
          Src[v42] = 44;
          v61[0] = v42 + 1;
          _ltow_s(*(unsigned __int8 *)(v19 + 41), &Src[v42 + 1], 387 - (v42 + 1), 10);
          v44 = -1;
          while ( Src[v61[0] + 1 + v44++] != 0 )
            ;
          v42 = v44 + v61[0];
          v43 = v44 + v61[0];
        }
        v46 = v42 + 1;
        v61[0] = v46;
        Src[v43] = 41;
        v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, Src, 2 * v46);
        v11 = v41;
        if ( v41 >= 0 )
          goto LABEL_103;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        v31 = 901129;
        goto LABEL_115;
      case 29:
        v50 = *(_QWORD *)(v19 + 56);
        if ( !v50 )
          goto LABEL_103;
        v11 = CParamProps::Get3PartName(v50, Src, 387, v61, 1);
        if ( v11 < 0 )
        {
          v52 = 40732;
          goto LABEL_129;
        }
        if ( !v61[0] )
          goto LABEL_103;
        _mm_lfence();
        v41 = CExtByteBuffer::WriteWCharToExtBuffer(a2, 0x28u);
        v11 = v41;
        if ( v41 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          v31 = 958473;
          goto LABEL_115;
        }
        _mm_lfence();
        v51 = -1;
        do
          ++v51;
        while ( Src[v51] );
        v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, Src, 2 * v51);
        v11 = v41;
        if ( v41 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          v31 = 961545;
          goto LABEL_115;
        }
        _mm_lfence();
        v41 = CExtByteBuffer::WriteWCharToExtBuffer(a2, 0x29u);
        v11 = v41;
        if ( v41 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          v31 = 963593;
          goto LABEL_115;
        }
LABEL_103:
        if ( (*(_BYTE *)(v19 + 8) & 2) != 0 )
        {
          _mm_lfence();
          v25 = CExtByteBuffer::WriteIntoExtBuffer(a2, L" OUTPUT", 0xEu);
          v11 = v25;
          if ( v25 < 0 )
          {
            v52 = 40157;
            if ( (bidGblFlags & 2) != 0 )
            {
              v53 = 977929;
              goto LABEL_128;
            }
            goto LABEL_129;
          }
        }
        v3 = a3;
        v15 = (_QWORD *)(v7 + 88);
        v9 = 1;
        v5 = this;
        break;
      case 30:
        _mm_lfence();
        v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, L" READONLY", 0x12u);
        v11 = v41;
        if ( v41 >= 0 )
          goto LABEL_103;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        v31 = 970761;
        goto LABEL_115;
      case 32:
      case 33:
      case 34:
        _mm_lfence();
        Src[0] = 40;
        _ltow_s(*(unsigned __int8 *)(v19 + 41), &Src[1], 0x182u, 10);
        v49 = -1;
        do
          ++v49;
        while ( Src[v49] );
        Src[v49] = 41;
        v61[0] = v49 + 1;
        v41 = CExtByteBuffer::WriteIntoExtBuffer(a2, Src, 2 * (v49 + 1));
        v11 = v41;
        if ( v41 >= 0 )
          goto LABEL_103;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        v31 = 939017;
        goto LABEL_115;
      default:
        goto LABEL_103;
    }
LABEL_106:
    ++v8;
    v13 = v55 + 40;
    v12 = v57 + 64;
    v55 += 40;
    v57 += 64;
    if ( v8 > v59 )
    {
      if ( v11 < 0 )
        goto LABEL_117;
      return 0;
    }
    v6 = v60;
    v14 = (_QWORD *)(v7 + 88);
  }
  v52 = 40157;
  if ( (bidGblFlags & 2) != 0 )
  {
    v53 = 833545;
LABEL_128:
    _mm_lfence();
    bidTraceHR(off_1802603D0[0], v53, (unsigned int)v25);
  }
LABEL_129:
  _mm_lfence();
  if ( (bidGblFlags & 2) != 0 )
  {
    _mm_lfence();
    v11 = bidTraceHR(off_1802603D0[0], 989193, (unsigned int)v11);
  }
  CErrorData::PostStandardError((CStmt *)((char *)this + 136), v52, v11, 0);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18007e650  mov     [rsp-8+arg_10], rbx
0x18007e655  push    rbp
0x18007e656  push    rsi
0x18007e657  push    rdi
0x18007e658  push    r12
0x18007e65a  push    r13
0x18007e65c  push    r14
0x18007e65e  push    r15
0x18007e660  lea     rbp, [rsp-290h]
0x18007e668  sub     rsp, 390h
0x18007e66f  mov     rax, cs:__security_cookie
0x18007e676  xor     rax, rsp
0x18007e679  mov     [rbp+2C0h+var_40], rax
0x18007e680  mov     esi, r8d
0x18007e683  mov     [rsp+3C0h+var_388], r8d
0x18007e688  mov     r12, rdx
0x18007e68b  mov     [rsp+3C0h+var_378], rcx
0x18007e690  mov     rbx, rcx
0x18007e693  xor     edx, edx; Val
0x18007e695  mov     r8d, 306h; Size
0x18007e69b  lea     rcx, [rsp+3C0h+Src]; void *
0x18007e6a0  call    memset_0
0x18007e6a5  mov     rcx, [rbx+78h]
0x18007e6a9  xor     r11d, r11d
0x18007e6ac  mov     r13, [rbx+250h]
0x18007e6b3  mov     r15d, 1
0x18007e6b9  mov     [rsp+3C0h+var_360], r11
0x18007e6be  mov     r10d, r11d
0x18007e6c1  mov     [rsp+3C0h+var_368], rcx
0x18007e6c6  mov     r14d, r11d
0x18007e6c9  mov     rax, [rcx+580h]
0x18007e6d0  mov     edi, r11d
0x18007e6d3  mov     [rsp+3C0h+var_370], rax
0x18007e6d8  cmp     rax, r15
0x18007e6db  jb      loc_18007EE5B
0x18007e6e1  mov     eax, 40h ; '@'
0x18007e6e6  mov     edx, eax
0x18007e6e8  mov     [rsp+3C0h+var_380], rax
0x18007e6ed  mov     eax, 28h ; '('
0x18007e6f2  mov     r8d, eax
0x18007e6f5  mov     [rsp+3C0h+var_390], rax
0x18007e6fa  lea     rax, [r13+58h]
0x18007e6fe  mov     r9, rax
0x18007e701  test    r13, r13
0x18007e704  jz      loc_18007E795
0x18007e70a  test    esi, esi
0x18007e70c  jz      short loc_18007E78B
0x18007e70e  test    byte ptr [r13+80h], 18h
0x18007e716  mov     r9, rax
0x18007e719  jz      short loc_18007E78B
0x18007e71b  mov     rcx, [r13+58h]
0x18007e71f  lea     r9, [r13+58h]
0x18007e723  add     rcx, 0FFFFFFFFFFFFFFD8h
0x18007e727  add     rcx, r8
0x18007e72a  test    byte ptr [rcx+18h], 1
0x18007e72e  jz      short loc_18007E747
0x18007e730  mov     rax, [rcx]
0x18007e733  test    byte ptr [rax+40h], 1
0x18007e737  jnz     short loc_18007E747
0x18007e739  mov     rcx, [rcx+10h]
0x18007e73d  test    rcx, rcx
0x18007e740  jnz     short loc_18007E730
0x18007e742  mov     rdx, r11
0x18007e745  jmp     short loc_18007E74A
0x18007e747  mov     rdx, [rcx]
0x18007e74a  test    byte ptr [rdx+38h], 4
0x18007e74e  jz      short loc_18007E78B
0x18007e750  mov     rcx, [rbx+258h]
0x18007e757  mov     rax, [r13+8]
0x18007e75b  dec     rcx
0x18007e75e  imul    rcx, [r13+20h]
0x18007e763  add     rcx, [rdx+18h]
0x18007e767  mov     r8d, [rcx+rax]
0x18007e76b  cmp     r8d, 0Dh
0x18007e76f  jz      loc_18007EDB4
0x18007e775  cmp     r8d, 3
0x18007e779  jnz     short loc_18007E786
0x18007e77b  cmp     word ptr [rdx+54h], 1
0x18007e780  jbe     loc_18007EDB4
0x18007e786  mov     r8, [rsp+3C0h+var_390]
0x18007e78b  mov     rax, [r9]
0x18007e78e  mov     rsi, [rax+r8-20h]
0x18007e793  jmp     short loc_18007E7CC
0x18007e795  mov     rax, [rcx+590h]
0x18007e79c  test    rax, rax
0x18007e79f  jz      short loc_18007E7B4
0x18007e7a1  cmp     r15, [rax]
0x18007e7a4  ja      short loc_18007E7B4
0x18007e7a6  mov     rax, [rax+18h]
0x18007e7aa  mov     rsi, [rax+r15*8-8]
0x18007e7af  test    rsi, rsi
0x18007e7b2  jnz     short loc_18007E7CC
0x18007e7b4  mov     rax, [rcx+598h]
0x18007e7bb  test    rax, rax
0x18007e7be  jz      short loc_18007E7C9
0x18007e7c0  lea     rsi, [rdx-40h]
0x18007e7c4  add     rsi, rax
0x18007e7c7  jmp     short loc_18007E7CC
0x18007e7c9  mov     rsi, r11
0x18007e7cc  mov     r9d, 0Ah; Radix
0x18007e7d2  mov     ecx, r15d; Value
0x18007e7d5  test    r10d, r10d
0x18007e7d8  jz      short loc_18007E821
0x18007e7da  mov     eax, 50h ; 'P'
0x18007e7df  mov     dword ptr [rsp+3C0h+Src], 40002Ch
0x18007e7e7  mov     r8d, 180h; BufferCount
0x18007e7ed  mov     [rsp+3C0h+var_34C], ax
0x18007e7f2  lea     rdx, [rsp+3C0h+Buffer]; Buffer
0x18007e7f7  call    cs:__imp__itow_s
0x18007e7fd  lea     rax, [rsp+3C0h+Buffer]
0x18007e802  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007e809  nop     dword ptr [rax+00000000h]
0x18007e810  inc     r8
0x18007e813  cmp     word ptr [rax+r8*2], 0
0x18007e819  jnz     short loc_18007E810
0x18007e81b  add     r8, 3
0x18007e81f  jmp     short loc_18007E85F
0x18007e821  mov     r8d, 181h; BufferCount
0x18007e827  mov     dword ptr [rsp+3C0h+Src], 500040h
0x18007e82f  lea     rdx, [rsp+3C0h+var_34C]; Buffer
0x18007e834  call    cs:__imp__itow_s
0x18007e83a  lea     rax, [rsp+3C0h+var_34C]
0x18007e83f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007e846  nop     word ptr [rax+rax+00000000h]
0x18007e850  inc     r8
0x18007e853  cmp     word ptr [rax+r8*2], 0
0x18007e859  jnz     short loc_18007E850
0x18007e85b  add     r8, 2
0x18007e85f  mov     eax, 20h ; ' '
0x18007e864  lea     rdx, [rsp+3C0h+Src]; Src
0x18007e869  mov     [rsp+r8*2+3C0h+Src], ax
0x18007e86f  mov     rcx, r12; this
0x18007e872  inc     r8
0x18007e875  mov     [rsp+3C0h+var_360], r8
0x18007e87a  add     r8, r8; Size
0x18007e87d  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18007e882  mov     edi, eax
0x18007e884  test    eax, eax
0x18007e886  js      loc_18007EEAE
0x18007e88c  mov     ebx, [rsi+2Ch]
0x18007e88f  cmp     ebx, 19h
0x18007e892  jz      loc_18007E955
0x18007e898  cmp     ebx, 1Eh
0x18007e89b  jz      loc_18007E955
0x18007e8a1  mov     r8, [rsi+10h]
0x18007e8a5  movzx   ecx, bx
0x18007e8a8  mov     edx, ecx
0x18007e8aa  sub     edx, 10h
0x18007e8ad  jz      short loc_18007E8C0
0x18007e8af  cmp     edx, 1
0x18007e8b2  jnz     short loc_18007E8D5
0x18007e8b4  mov     eax, 11h
0x18007e8b9  mov     ecx, 18h
0x18007e8be  jmp     short loc_18007E8CA
0x18007e8c0  mov     eax, 10h
0x18007e8c5  mov     ecx, 17h
0x18007e8ca  cmp     r8, 4
0x18007e8ce  cmovz   ax, cx
0x18007e8d2  movzx   ecx, ax
0x18007e8d5  cmp     cx, 23h ; '#'
0x18007e8d9  jb      short loc_18007E922
0x18007e8db  test    byte ptr cs:_bidGblFlags, 2
0x18007e8e2  jz      short loc_18007E8FF
0x18007e8e4  mov     rcx, cs:?_bidSrcFile2A@?1??GetSSTypeString@@YAJG_JPEAPEB_W@Z@4REBDEB; char const * const `GetSSTypeString(ushort,__int64,wchar_t const * *)'::`2'::_bidSrcFile2A
0x18007e8eb  mov     edx, 26809h
0x18007e8f0  mov     r8d, 8002000Bh
0x18007e8f6  call    _bidTraceHR
0x18007e8fb  mov     edi, eax
0x18007e8fd  jmp     short loc_18007E904
0x18007e8ff  mov     edi, 8002000Bh
0x18007e904  test    edi, edi
0x18007e906  jns     short loc_18007E934
0x18007e908  test    byte ptr cs:_bidGblFlags, 2
0x18007e90f  jz      loc_18007EE34
0x18007e915  mov     r8d, edi
0x18007e918  mov     edx, 0CD809h
0x18007e91d  jmp     loc_18007EE25
0x18007e922  movzx   eax, cx
0x18007e925  lea     rcx, cs:180000000h
0x18007e92c  mov     r14, rva ?g_SqlServerTypes@@3PAPEB_WA[rcx+rax*8]; wchar_t const * near * g_SqlServerTypes ...
0x18007e934  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007e93b  nop     dword ptr [rax+rax+00h]
0x18007e940  inc     rax
0x18007e943  cmp     word ptr [r14+rax*2], 0
0x18007e949  jnz     short loc_18007E940
0x18007e94b  mov     [rsp+3C0h+var_360], rax
0x18007e950  jmp     loc_18007EA35
0x18007e955  mov     rcx, [rsi+38h]
0x18007e959  test    rcx, rcx
0x18007e95c  jz      short loc_18007E98B
0x18007e95e  cmp     ebx, 19h
0x18007e961  lea     r9, [rsp+3C0h+var_360]
0x18007e966  mov     eax, 2
0x18007e96b  lea     rdx, [rsp+3C0h+Src]
0x18007e970  mov     r14d, 0
0x18007e976  mov     r8d, 183h
0x18007e97c  cmovz   eax, r14d
0x18007e980  mov     [rsp+3C0h+var_3A0], eax
0x18007e984  call    ?Get3PartName@CParamProps@@QEAAJPEA_W_KPEA_KW4ETypeFor3PartName@@@Z; CParamProps::Get3PartName(wchar_t *,unsigned __int64,unsigned __int64 *,ETypeFor3PartName)
0x18007e989  jmp     short loc_18007E9AE
0x18007e98b  test    byte ptr cs:_bidGblFlags, 2
0x18007e992  jz      short loc_18007E9B8
0x18007e994  mov     rcx, cs:off_1802603D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18007e99b  mov     edx, 0D1809h
0x18007e9a0  mov     r8d, 80040E21h
0x18007e9a6  call    _bidTraceHR
0x18007e9ab  xor     r14d, r14d
0x18007e9ae  test    eax, eax
0x18007e9b0  jns     loc_18007EA30
0x18007e9b6  jmp     short loc_18007E9BB
0x18007e9b8  xor     r14d, r14d
0x18007e9bb  lea     r8, aDummyUdtortvp; "Dummy.UDTOrTVP"
0x18007e9c2  mov     edx, 183h
0x18007e9c7  lea     rax, [rsp+3C0h+Src]
0x18007e9cc  sub     r8, rax
0x18007e9cf  lea     rcx, [rsp+3C0h+Src]
0x18007e9d4  lea     rax, [rdx+7FFFFE7Bh]
0x18007e9db  test    rax, rax
0x18007e9de  jz      short loc_18007E9F7
0x18007e9e0  movzx   eax, word ptr [r8+rcx]
0x18007e9e5  test    ax, ax
0x18007e9e8  jz      short loc_18007E9F7
0x18007e9ea  mov     [rcx], ax
0x18007e9ed  add     rcx, 2
0x18007e9f1  sub     rdx, 1
0x18007e9f5  jnz     short loc_18007E9D4
0x18007e9f7  test    rdx, rdx
0x18007e9fa  lea     rax, [rcx-2]
0x18007e9fe  mov     edi, 8007007Ah
0x18007ea03  cmovnz  rax, rcx
0x18007ea07  cmovnz  edi, r14d
0x18007ea0b  mov     [rax], r14w
0x18007ea0f  jz      loc_18007EE98
0x18007ea15  lea     rcx, [rsp+3C0h+Src]
0x18007ea1a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007ea21  inc     rax
0x18007ea24  cmp     word ptr [rcx+rax*2], 0
0x18007ea29  jnz     short loc_18007EA21
0x18007ea2b  mov     [rsp+3C0h+var_360], rax
0x18007ea30  lea     r14, [rsp+3C0h+Src]
0x18007ea35  lfence
0x18007ea38  mov     r8, [rsp+3C0h+var_360]
0x18007ea3d  mov     rdx, r14; Src
0x18007ea40  add     r8, r8; Size
0x18007ea43  mov     rcx, r12; this
0x18007ea46  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18007ea4b  mov     edi, eax
0x18007ea4d  test    eax, eax
0x18007ea4f  js      loc_18007EE88
0x18007ea55  lea     eax, [rbx-1]; switch 34 cases
0x18007ea58  cmp     eax, 21h
0x18007ea5b  ja      def_18007EA7C; jumptable 000000018007EA7C default case, cases 3,6,9-14,16-28,31
0x18007ea61  lea     rdx, cs:180000000h
0x18007ea68  cdqe
0x18007ea6a  movzx   eax, ds:(byte_18007EF34 - 180000000h)[rdx+rax]
0x18007ea72  mov     ecx, ds:(jpt_18007EA7C - 180000000h)[rdx+rax*4]
0x18007ea79  add     rcx, rdx
0x18007ea7c  jmp     rcx; switch jump
0x18007ea7e  lfence; jumptable 000000018007EA7C case 15
0x18007ea81  mov     eax, 28h ; '('
0x18007ea86  lea     rdx, [rsp+3C0h+Src+2]; Buffer
0x18007ea8b  mov     [rsp+3C0h+Src], ax
0x18007ea90  mov     r9d, 0Ah; Radix
0x18007ea96  movzx   ecx, byte ptr [rsi+28h]; Value
0x18007ea9a  mov     r8d, 182h; BufferCount
0x18007eaa0  call    cs:__imp__ltow_s
0x18007eaa6  lea     rax, [rsp+3C0h+Src]
0x18007eaab  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007eab2  inc     r8
0x18007eab5  cmp     word ptr [rax+r8*2], 0
0x18007eabb  jnz     short loc_18007EAB2
0x18007eabd  mov     [rsp+3C0h+var_360], r8
0x18007eac2  mov     rax, r8
0x18007eac5  cmp     byte ptr [rsi+29h], 0
0x18007eac9  jz      short loc_18007EB33
0x18007eacb  mov     eax, 2Ch ; ','
0x18007ead0  lea     rdx, [rsp+3C0h+Src]
0x18007ead5  mov     [rsp+r8*2+3C0h+Src], ax
0x18007eadb  mov     r9d, 0Ah; Radix
0x18007eae1  lea     rax, [r8+1]
0x18007eae5  mov     r8d, 183h
0x18007eaeb  mov     [rsp+3C0h+var_360], rax
0x18007eaf0  lea     rdx, [rdx+rax*2]; Buffer
0x18007eaf4  movzx   ecx, byte ptr [rsi+29h]; Value
0x18007eaf8  sub     r8, rax; BufferCount
0x18007eafb  call    cs:__imp__ltow_s
0x18007eb01  mov     rdx, [rsp+3C0h+var_360]
0x18007eb06  lea     rcx, [rsp+3C0h+Src]
0x18007eb0b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007eb12  lea     rcx, [rcx+rdx*2]
0x18007eb16  nop     word ptr [rax+rax+00000000h]
0x18007eb20  cmp     word ptr [rcx+rax*2+2], 0
0x18007eb26  lea     rax, [rax+1]
0x18007eb2a  jnz     short loc_18007EB20
0x18007eb2c  lea     r8, [rax+rdx]
0x18007eb30  mov     rax, r8
0x18007eb33  inc     r8
0x18007eb36  lea     rdx, [rsp+3C0h+Src]; Src
0x18007eb3b  mov     ecx, 29h ; ')'
0x18007eb40  mov     [rsp+3C0h+var_360], r8
  ... truncated ...
```

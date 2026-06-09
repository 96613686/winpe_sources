# CxPlatDataPathSocketReceive

- ea: `0x14003a300`
- end: `0x14003aa59`
- name: `CxPlatDataPathSocketReceive`
- size: `1881`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1400290b4`
- `0x140039110`
- `0x14003a300`
- `0x14003aa60`
- `0x14003ade0`
- `0x14003c710`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003cb00`
- `0x14003ead8`
- `0x14004a32c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003a5d0`
- `ntoskrnl!_snprintf_s` at `0x14003a66f`
- `ntoskrnl!_snprintf_s` at `0x14003a8ff`
- `ntoskrnl!_snprintf_s` at `0x14003a9dd`
- `ntoskrnl!_snprintf_s` at `0x14003a5d0`
- `ntoskrnl!_snprintf_s` at `0x14003a66f`
- `ntoskrnl!_snprintf_s` at `0x14003a8ff`
- `ntoskrnl!_snprintf_s` at `0x14003a9dd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003a95e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003a95e`
- `ntoskrnl!ExQueryDepthSList` at `0x14003a92a`
- `ntoskrnl!ExQueryDepthSList` at `0x14003a92a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003a362`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003a362`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003aa23`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003aa23`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathSocketReceive(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 *v3; // r14
  char *v5; // r9
  char v7; // r10
  __int64 v8; // r15
  char v9; // dl
  __int64 v10; // r11
  unsigned __int16 v11; // bx
  __int64 v12; // rsi
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  __int128 v16; // xmm0
  bool v17; // zf
  int v18; // eax
  struct _MDL *v19; // r12
  unsigned int v20; // r13d
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // edx
  int v25; // ecx
  __int64 v26; // r8
  unsigned __int16 v27; // cx
  __int64 v28; // rax
  char v29; // cl
  __int64 *v30; // rbx
  __int16 v31; // dx
  __int16 v32; // ax
  __int16 v33; // ax
  __int64 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rcx
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+38h] [rbp-C8h]
  char v40; // [rsp+50h] [rbp-B0h]
  int v41; // [rsp+54h] [rbp-ACh]
  int v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+5Ch] [rbp-A4h]
  unsigned int v44; // [rsp+60h] [rbp-A0h]
  char *v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  __int64 *v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h] BYREF
  PEX_RUNDOWN_REF RunRef; // [rsp+88h] [rbp-78h]
  _BYTE v50[24]; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+A8h] [rbp-58h]
  __int128 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+C8h] [rbp-38h]
  char DstBuf[128]; // [rsp+D0h] [rbp-30h] BYREF

  v3 = a3;
  if ( !a3 )
    return 0;
  v44 = HIDWORD(KeGetPcr()[1].LockArray) % CxPlatProcessorCount;
  RunRef = (PEX_RUNDOWN_REF)(a1 + 424 + 8LL * v44);
  if ( !ExAcquireRundownProtection(RunRef) )
    return 3221225635LL;
  v48 = 0;
  v47 = &v48;
  v7 = 1;
  do
  {
    if ( !v3[1] || !v3[3] )
    {
      if ( (byte_14005C48E & 0x20) == 0 )
        goto LABEL_51;
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Dropping datagram with empty mdl.", a1);
      goto LABEL_89;
    }
    v46 = 0;
    memset(v50, 0, sizeof(v50));
    v51 = 0;
    v8 = 0;
    v52 = 0;
    v53 = 0;
    v9 = 0;
    v54 = 0;
    LOBYTE(v5) = 0;
    v10 = *((unsigned int *)v3 + 10);
    v11 = 0;
    v12 = v3[4];
    v13 = v12;
    v40 = 0;
    if ( (unsigned int)v10 < 0x10 )
      v13 = 0;
    LOBYTE(v41) = 0;
    LOBYTE(v43) = 0;
    if ( !v13 )
      goto LABEL_87;
    while ( 1 )
    {
      v14 = *(_DWORD *)(v13 + 8);
      if ( v14 != 41 )
        break;
      v15 = *(_DWORD *)(v13 + 12);
      switch ( v15 )
      {
        case 19:
          *(_WORD *)v50 = 23;
          v16 = *(_OWORD *)(v13 + 16);
          *(_WORD *)&v50[2] = *(_WORD *)(a1 + 2);
          *(_OWORD *)&v50[8] = v16;
          CxPlatConvertFromMappedV6(v50, v50, v13, v5);
          v51 = *(_DWORD *)(v13 + 32);
LABEL_13:
          v9 = v7;
          goto LABEL_42;
        case 75:
          v17 = *(_BYTE *)(v13 + 24) == (unsigned __int8)v7;
          goto LABEL_16;
        case 39:
        case 50:
          goto LABEL_25;
      }
      if ( v15 != 21 )
        goto LABEL_42;
      v43 = *(_DWORD *)(v13 + 16);
LABEL_28:
      v7 = 1;
LABEL_42:
      v13 += (*(_QWORD *)v13 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( v13 + 16 > (unsigned __int64)(v12 + v10) || !v13 )
        goto LABEL_18;
    }
    if ( v14 )
    {
      if ( v14 == 17 && *(_DWORD *)(v13 + 12) == 3 )
      {
        v11 = *(_WORD *)(v13 + 16);
        v40 = v7;
      }
      goto LABEL_42;
    }
    v18 = *(_DWORD *)(v13 + 12);
    if ( v18 == 19 )
    {
      *(_WORD *)v50 = 2;
      *(_DWORD *)&v50[4] = *(_DWORD *)(v13 + 16);
      *(_WORD *)&v50[2] = *(_WORD *)(a1 + 2);
      v51 = *(_DWORD *)(v13 + 20);
      goto LABEL_13;
    }
    if ( v18 != 75 )
    {
      if ( v18 != 3 )
      {
        if ( v18 == 50 )
        {
          v41 = *(_DWORD *)(v13 + 16);
        }
        else if ( v18 == 4 )
        {
          v43 = *(_DWORD *)(v13 + 16);
        }
        goto LABEL_42;
      }
LABEL_25:
      v41 = *(_DWORD *)(v13 + 16);
      goto LABEL_28;
    }
    v17 = *(_BYTE *)(v13 + 24) == 3;
LABEL_16:
    if ( !v17 )
      goto LABEL_42;
    LOBYTE(v5) = v7;
LABEL_18:
    if ( v9 || (_BYTE)v5 )
    {
      CxPlatConvertFromMappedV6(v3[6], &v52, v13, v5);
      if ( (_BYTE)v5 )
      {
        if ( (*(_BYTE *)(a1 + 80) & 2) == 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)(a1 + 56) + 8LL))(
            a1,
            *(_QWORD *)(a1 + 64),
            &v52);
          goto LABEL_90;
        }
        goto LABEL_51;
      }
      v19 = (struct _MDL *)v3[1];
      v20 = *((_DWORD *)v3 + 4);
      v21 = v3[3];
      v45 = 0;
      if ( !v11 )
      {
        if ( v21 > 0xFFFF )
        {
          if ( (byte_14005C48E & 0x20) == 0 )
            goto LABEL_51;
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "[%p] Dropping datagram with too many bytes (%llu).",
            (const void *)a1,
            v21);
LABEL_49:
          McTemplateU0s_EtwWriteTransfer(v22, QuicLogWarning, DstBuf);
          goto LABEL_50;
        }
        v11 = v3[3];
      }
      if ( (unsigned __int8)CxPlatMdlMapChain(v19) )
      {
        if ( (byte_14005C48E & 2) != 0 )
          McTemplateU0pqhubr3ubr5_EtwWriteTransfer(v25, v24, a1, v21, v11, v38, (__int64)v50, v39, (__int64)&v52);
        if ( v21 )
        {
          v5 = 0;
          v26 = 0;
          while ( 1 )
          {
            v27 = v21;
            if ( v11 <= v21 )
              v27 = v11;
            v42 = v27;
            if ( v27 > v19->ByteCount - v20 )
              break;
            if ( !v8 )
            {
              LOBYTE(v26) = v40;
              v28 = CxPlatSocketAllocRxIoBlock(
                      *(_QWORD *)(a1 + 56),
                      v44 % *(_DWORD *)(*(_QWORD *)(a1 + 56) + 128LL),
                      v26,
                      v5);
              v8 = v28;
              if ( !v28 )
              {
                if ( (byte_14005C48E & 0x20) == 0 )
                  goto LABEL_50;
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Couldn't allocate receive context.", a1);
                goto LABEL_49;
              }
              v29 = *(_BYTE *)(v28 + 120) & 0xFE | (v21 > 0x1000);
              *(_BYTE *)(v28 + 120) = v29;
              v45 = (char *)CxPlatPoolAlloc(*(_QWORD *)v28 + 96 * ((v29 & 1) + 5LL));
              *(_QWORD *)(v8 + 8) = v45;
              v5 = v45;
              if ( !v45 )
              {
                if ( (byte_14005C48E & 0x20) != 0 )
                {
                  _snprintf_s(
                    DstBuf,
                    0x80u,
                    0xFFFFFFFFFFFFFFFFuLL,
                    "[%p] Couldn't allocate receive buffers.",
                    (const void *)a1);
                  McTemplateU0s_EtwWriteTransfer(v35, QuicLogWarning, DstBuf);
                }
                v36 = *(_QWORD *)(v8 - 16);
                ++*(_DWORD *)(v36 + 28);
                if ( ExQueryDepthSList((PSLIST_HEADER)v36) < *(_WORD *)(v36 + 16) )
                {
                  ExpInterlockedPushEntrySList((PSLIST_HEADER)v36, (PSLIST_ENTRY)(v8 - 16));
                }
                else
                {
                  ++*(_DWORD *)(v36 + 32);
                  (*(void (__fastcall **)(__int64, __int64))(v36 + 56))(v8 - 16, v36);
                }
                v7 = 1;
                goto LABEL_51;
              }
              *(_DWORD *)(v8 + 16) = 0;
              v26 = v8 + 128;
              *(_QWORD *)(v8 + 24) = 688LL * (v44 % *(_DWORD *)(*(_QWORD *)(a1 + 56) + 128LL))
                                   + *(_QWORD *)(a1 + 56)
                                   + 144LL;
              v46 = v8 + 128;
              *(_OWORD *)(v8 + 60) = *(_OWORD *)v50;
              *(_QWORD *)(v8 + 76) = *(_QWORD *)&v50[16];
              *(_DWORD *)(v8 + 84) = v51;
              *(_OWORD *)(v8 + 32) = v52;
              *(_QWORD *)(v8 + 48) = v53;
              *(_DWORD *)(v8 + 56) = v54;
            }
            v30 = (__int64 *)(v26 + 8);
            *(_QWORD *)v26 = v8;
            *(_QWORD *)(v26 + 8) = 0;
            v31 = v44 % *(_DWORD *)(*(_QWORD *)(a1 + 56) + 128LL);
            *(_BYTE *)(v26 + 36) = v41;
            *(_BYTE *)(v26 + 37) = v43;
            v32 = *(_WORD *)(v26 + 38);
            *(_WORD *)(v26 + 34) = v31;
            *(_QWORD *)(v26 + 24) = v5;
            *(_WORD *)(v26 + 38) = v32 & 0xFFFC | 1;
            memmove(v5, (char *)v19->MappedSystemVa + v20, (unsigned __int16)v42);
            *(_WORD *)(v46 + 32) = v42;
            v5 = &v45[(unsigned __int16)v42];
            v33 = *(_WORD *)(v46 + 38) & 0xFFF7;
            *(_QWORD *)(v46 + 16) = v8 + 24;
            v45 = v5;
            *(_WORD *)(v46 + 38) = v33 | 4;
            v7 = 1;
            *(_WORD *)(v8 + 100) = *(_WORD *)(v8 + 100) & 0x8000 | 1;
            v34 = v47;
            v47 = v30;
            *v34 = (__int64)v30;
            if ( ++*(_DWORD *)(v8 + 16) == 64 )
            {
              if ( (byte_14005C48E & 0x20) == 0 )
                goto LABEL_51;
              _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Exceeded URO preallocation capacity.", a1);
              goto LABEL_49;
            }
            v11 = v42;
            v20 += v42;
            if ( v20 != v19->ByteCount || (v19 = v19->Next, v20 = 0, v19) )
            {
              v26 = *(unsigned int *)(*(_QWORD *)(a1 + 56) + 124LL) + v46;
              v46 = v26;
              v21 -= (unsigned __int16)v42;
              if ( v21 )
                continue;
            }
            goto LABEL_51;
          }
          if ( (byte_14005C48E & 0x20) == 0 )
            goto LABEL_50;
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Dropping datagram with fragmented MDL.", a1);
          goto LABEL_49;
        }
      }
      else if ( (byte_14005C48E & 0x20) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Failed to map MDL chain", a1);
        goto LABEL_49;
      }
LABEL_50:
      v7 = 1;
      goto LABEL_51;
    }
LABEL_87:
    if ( (byte_14005C48E & 0x20) == 0 )
      goto LABEL_51;
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%p] Dropping datagram missing IP_PKTINFO/IP_RECVERR.", a1);
LABEL_89:
    McTemplateU0s_EtwWriteTransfer(v37, QuicLogWarning, DstBuf);
LABEL_90:
    v7 = 1;
LABEL_51:
    v3 = (__int64 *)*v3;
  }
  while ( v3 );
  if ( v48 )
  {
    v23 = *(_QWORD *)(a1 + 64);
    if ( (*(_BYTE *)(a1 + 80) & 2) != 0 )
      CxPlatPcpRecvCallback(4, v23);
    else
      (**(void (__fastcall ***)(__int64, __int64))(a1 + 56))(a1, v23);
  }
  ExReleaseRundownProtection(RunRef);
  return 0;
}

```

## disassembly

```asm
0x14003a300  mov     [rsp-8+arg_8], rbx
0x14003a305  push    rbp
0x14003a306  push    rsi
0x14003a307  push    rdi
0x14003a308  push    r12
0x14003a30a  push    r13
0x14003a30c  push    r14
0x14003a30e  push    r15
0x14003a310  lea     rbp, [rsp-60h]
0x14003a315  sub     rsp, 160h
0x14003a31c  mov     rax, cs:__security_cookie
0x14003a323  xor     rax, rsp
0x14003a326  mov     [rbp+90h+var_40], rax
0x14003a32a  xor     r13d, r13d
0x14003a32d  mov     r14, r8
0x14003a330  mov     rdi, rcx
0x14003a333  test    r8, r8
0x14003a336  jz      loc_14003AA2F
0x14003a33c  mov     eax, gs:1A4h
0x14003a344  xor     edx, edx
0x14003a346  div     cs:CxPlatProcessorCount
0x14003a34c  add     rcx, 1A8h
0x14003a353  mov     [rsp+190h+var_130], edx
0x14003a357  lea     rax, [rcx+rdx*8]
0x14003a35b  mov     rcx, rax; RunRef
0x14003a35e  mov     [rbp+90h+RunRef], rax
0x14003a362  call    cs:__imp_ExAcquireRundownProtection
0x14003a369  nop     dword ptr [rax+rax+00h]
0x14003a36e  test    al, al
0x14003a370  jnz     short loc_14003A37C
0x14003a372  mov     eax, 0C00000A3h
0x14003a377  jmp     loc_14003AA31
0x14003a37c  lea     rcx, [rbp+90h+var_110]
0x14003a380  mov     [rbp+90h+var_110], r13
0x14003a384  mov     [rsp+190h+var_118], rcx
0x14003a389  mov     ecx, 4
0x14003a38e  lea     r10d, [rcx-3]
0x14003a392  lea     r12d, [rcx-2]
0x14003a396  cmp     [r14+8], r13
0x14003a39a  jz      loc_14003AA04
0x14003a3a0  cmp     [r14+18h], r13
0x14003a3a4  jz      loc_14003AA04
0x14003a3aa  xor     eax, eax
0x14003a3ac  mov     [rsp+190h+var_120], r13
0x14003a3b1  xorps   xmm0, xmm0
0x14003a3b4  mov     [rbp+90h+var_F0], rax
0x14003a3b8  movups  [rbp+90h+var_100], xmm0
0x14003a3bc  mov     [rbp+90h+var_E8], eax
0x14003a3bf  mov     r15, r13
0x14003a3c2  movups  [rbp+90h+var_E0], xmm0
0x14003a3c6  mov     [rbp+90h+var_D0], rax
0x14003a3ca  mov     dl, r13b
0x14003a3cd  mov     [rbp+90h+var_C8], eax
0x14003a3d0  mov     r9b, r13b
0x14003a3d3  mov     r11d, [r14+28h]
0x14003a3d7  movzx   ebx, r13w
0x14003a3db  mov     rsi, [r14+20h]
0x14003a3df  cmp     r11d, 10h
0x14003a3e3  mov     r8, rsi
0x14003a3e6  mov     [rsp+190h+var_140], r13b
0x14003a3eb  cmovb   r8, r13
0x14003a3ef  mov     [rsp+190h+var_13C], r13d
0x14003a3f4  mov     [rsp+190h+var_134], r13d
0x14003a3f9  test    r8, r8
0x14003a3fc  jz      loc_14003A9B7
0x14003a402  mov     eax, [r8+8]
0x14003a406  cmp     eax, 29h ; ')'
0x14003a409  jnz     loc_14003A4DA
0x14003a40f  mov     eax, [r8+0Ch]
0x14003a413  cmp     eax, 13h
0x14003a416  jnz     short loc_14003A44F
0x14003a418  mov     eax, 17h
0x14003a41d  lea     rdx, [rbp+90h+var_100]
0x14003a421  mov     word ptr [rbp+90h+var_100], ax
0x14003a425  lea     rcx, [rbp+90h+var_100]
0x14003a429  movups  xmm0, xmmword ptr [r8+10h]
0x14003a42e  movzx   eax, word ptr [rdi+2]
0x14003a432  mov     word ptr [rbp+90h+var_100+2], ax
0x14003a436  movdqu  [rbp+90h+var_100+8], xmm0
0x14003a43b  call    CxPlatConvertFromMappedV6
0x14003a440  mov     ecx, [r8+20h]
0x14003a444  mov     [rbp+90h+var_E8], ecx
0x14003a447  mov     dl, r10b
0x14003a44a  jmp     loc_14003A54E
0x14003a44f  cmp     eax, 4Bh ; 'K'
0x14003a452  jnz     short loc_14003A4AB
0x14003a454  cmp     [r8+18h], r10b
0x14003a458  jnz     loc_14003A54E
0x14003a45e  mov     r9b, r10b
0x14003a461  test    dl, dl
0x14003a463  jnz     short loc_14003A46E
0x14003a465  test    r9b, r9b
0x14003a468  jz      loc_14003A9B7
0x14003a46e  mov     rcx, [r14+30h]
0x14003a472  lea     rdx, [rbp+90h+var_E0]
0x14003a476  call    CxPlatConvertFromMappedV6
0x14003a47b  test    r9b, r9b
0x14003a47e  jz      loc_14003A580
0x14003a484  test    [rdi+50h], r12b
0x14003a488  jnz     loc_14003A5FB
0x14003a48e  mov     rax, [rdi+38h]
0x14003a492  lea     r8, [rbp+90h+var_E0]
0x14003a496  mov     rdx, [rdi+40h]
0x14003a49a  mov     rcx, rdi
0x14003a49d  mov     rax, [rax+8]
0x14003a4a1  call    _guard_dispatch_icall
0x14003a4a6  jmp     loc_14003A9F9
0x14003a4ab  cmp     eax, 27h ; '''
0x14003a4ae  jz      short loc_14003A4B5
0x14003a4b0  cmp     eax, 32h ; '2'
0x14003a4b3  jnz     short loc_14003A4C0
0x14003a4b5  mov     r10d, [r8+10h]
0x14003a4b9  mov     [rsp+190h+var_13C], r10d
0x14003a4be  jmp     short loc_14003A4D2
0x14003a4c0  cmp     eax, 15h
0x14003a4c3  jnz     loc_14003A54E
0x14003a4c9  mov     r10d, [r8+10h]
0x14003a4cd  mov     [rsp+190h+var_134], r10d
0x14003a4d2  mov     r10d, 1
0x14003a4d8  jmp     short loc_14003A54E
0x14003a4da  test    eax, eax
0x14003a4dc  jnz     short loc_14003A538
0x14003a4de  mov     eax, [r8+0Ch]
0x14003a4e2  cmp     eax, 13h
0x14003a4e5  jnz     short loc_14003A507
0x14003a4e7  mov     word ptr [rbp+90h+var_100], r12w
0x14003a4ec  mov     eax, [r8+10h]
0x14003a4f0  mov     dword ptr [rbp+90h+var_100+4], eax
0x14003a4f3  movzx   eax, word ptr [rdi+2]
0x14003a4f7  mov     word ptr [rbp+90h+var_100+2], ax
0x14003a4fb  mov     eax, [r8+14h]
0x14003a4ff  mov     [rbp+90h+var_E8], eax
0x14003a502  jmp     loc_14003A447
0x14003a507  cmp     eax, 4Bh ; 'K'
0x14003a50a  jnz     short loc_14003A516
0x14003a50c  cmp     byte ptr [r8+18h], 3
0x14003a511  jmp     loc_14003A458
0x14003a516  cmp     eax, 3
0x14003a519  jz      short loc_14003A4B5
0x14003a51b  cmp     eax, 32h ; '2'
0x14003a51e  jnz     short loc_14003A52A
0x14003a520  mov     eax, [r8+10h]
0x14003a524  mov     [rsp+190h+var_13C], eax
0x14003a528  jmp     short loc_14003A54E
0x14003a52a  cmp     eax, ecx
0x14003a52c  jnz     short loc_14003A54E
0x14003a52e  mov     eax, [r8+10h]
0x14003a532  mov     [rsp+190h+var_134], eax
0x14003a536  jmp     short loc_14003A54E
0x14003a538  cmp     eax, 11h
0x14003a53b  jnz     short loc_14003A54E
0x14003a53d  cmp     dword ptr [r8+0Ch], 3
0x14003a542  jnz     short loc_14003A54E
0x14003a544  movzx   ebx, word ptr [r8+10h]
0x14003a549  mov     [rsp+190h+var_140], r10b
0x14003a54e  mov     rax, [r8]
0x14003a551  lea     rcx, [rsi+r11]
0x14003a555  add     rax, 7
0x14003a559  and     rax, 0FFFFFFFFFFFFFFF8h
0x14003a55d  add     r8, rax
0x14003a560  lea     rax, [r8+10h]
0x14003a564  cmp     rax, rcx
0x14003a567  ja      loc_14003A461
0x14003a56d  test    r8, r8
0x14003a570  jz      loc_14003A461
0x14003a576  mov     ecx, 4
0x14003a57b  jmp     loc_14003A402
0x14003a580  mov     r12, [r14+8]
0x14003a584  xor     eax, eax
0x14003a586  mov     r13d, [r14+10h]
0x14003a58a  mov     rsi, [r14+18h]
0x14003a58e  mov     [rsp+190h+var_128], rax
0x14003a593  test    bx, bx
0x14003a596  jnz     loc_14003A63E
0x14003a59c  cmp     rsi, 0FFFFh
0x14003a5a3  jbe     loc_14003A63B
0x14003a5a9  test    cs:byte_14005C48E, 20h
0x14003a5b0  jz      short loc_14003A5F2
0x14003a5b2  mov     [rsp+190h+var_168], rsi
0x14003a5b7  lea     r9, aPDroppingDatag; "[%p] Dropping datagram with too many by"...
0x14003a5be  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003a5c2  mov     [rsp+190h+var_170], rdi
0x14003a5c7  mov     edx, 80h; SizeInBytes
0x14003a5cc  lea     rcx, [rbp+90h+DstBuf]; DstBuf
0x14003a5d0  call    cs:__imp__snprintf_s
0x14003a5d7  nop     dword ptr [rax+rax+00h]
0x14003a5dc  lea     r8, [rbp+90h+DstBuf]
0x14003a5e0  lea     rdx, QuicLogWarning
0x14003a5e7  call    McTemplateU0s_EtwWriteTransfer
0x14003a5ec  mov     r10d, 1
0x14003a5f2  xor     r13d, r13d
0x14003a5f5  mov     r12d, 2
0x14003a5fb  mov     r14, [r14]
0x14003a5fe  mov     ecx, 4
0x14003a603  test    r14, r14
0x14003a606  jnz     loc_14003A396
0x14003a60c  mov     r8, [rbp+90h+var_110]
0x14003a610  test    r8, r8
0x14003a613  jz      loc_14003AA1F
0x14003a619  mov     rdx, [rdi+40h]
0x14003a61d  test    [rdi+50h], r12b
0x14003a621  jnz     loc_14003AA1A
0x14003a627  mov     rax, [rdi+38h]
0x14003a62b  mov     rcx, rdi
0x14003a62e  mov     rax, [rax]
0x14003a631  call    _guard_dispatch_icall
0x14003a636  jmp     loc_14003AA1F
0x14003a63b  movzx   ebx, si
0x14003a63e  mov     rcx, r12; MemoryDescriptorList
0x14003a641  call    CxPlatMdlMapChain
0x14003a646  xor     r10d, r10d
0x14003a649  test    al, al
0x14003a64b  jnz     short loc_14003A680
0x14003a64d  test    cs:byte_14005C48E, 20h
0x14003a654  jz      short loc_14003A5EC
0x14003a656  lea     r9, aPFailedToMapMd; "[%p] Failed to map MDL chain"
0x14003a65d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003a661  mov     [rsp+190h+var_170], rdi
0x14003a666  mov     edx, 80h; SizeInBytes
0x14003a66b  lea     rcx, [rbp+90h+DstBuf]; DstBuf
0x14003a66f  call    cs:__imp__snprintf_s
0x14003a676  nop     dword ptr [rax+rax+00h]
0x14003a67b  jmp     loc_14003A5DC
0x14003a680  test    cs:byte_14005C48E, 2
0x14003a687  jz      short loc_14003A6AE
0x14003a689  lea     rax, [rbp+90h+var_E0]
0x14003a68d  mov     r9d, esi
0x14003a690  mov     [rsp+190h+var_150], rax
0x14003a695  mov     r8, rdi
0x14003a698  lea     rax, [rbp+90h+var_100]
0x14003a69c  mov     [rsp+190h+var_160], rax
0x14003a6a1  mov     word ptr [rsp+190h+var_170], bx
0x14003a6a6  call    McTemplateU0pqhubr3ubr5_EtwWriteTransfer
0x14003a6ab  xor     r10d, r10d
0x14003a6ae  test    rsi, rsi
0x14003a6b1  jz      loc_14003A5EC
0x14003a6b7  mov     r9, [rsp+190h+var_128]
0x14003a6bc  mov     r8, r15
0x14003a6bf  movzx   eax, bx
0x14003a6c2  movzx   ecx, si
0x14003a6c5  cmp     rax, rsi
0x14003a6c8  mov     eax, [r12+28h]
0x14003a6cd  cmovbe  cx, bx
0x14003a6d1  sub     eax, r13d
0x14003a6d4  movzx   ebx, cx
0x14003a6d7  mov     [rsp+190h+var_138], ebx
0x14003a6db  cmp     ebx, eax
0x14003a6dd  ja      loc_14003A99E
0x14003a6e3  test    r15, r15
0x14003a6e6  jnz     loc_14003A7C8
0x14003a6ec  mov     rcx, [rdi+38h]
0x14003a6f0  xor     edx, edx
0x14003a6f2  mov     ebx, [rsp+190h+var_130]
0x14003a6f6  mov     eax, ebx
0x14003a6f8  mov     r8b, [rsp+190h+var_140]
0x14003a6fd  div     dword ptr [rcx+80h]
0x14003a703  call    CxPlatSocketAllocRxIoBlock
0x14003a708  mov     r15, rax
0x14003a70b  test    rax, rax
0x14003a70e  jz      loc_14003A96C
0x14003a714  mov     cl, [rax+78h]
0x14003a717  cmp     rsi, 1000h
0x14003a71e  setnbe  dl
0x14003a721  and     cl, 0FEh
0x14003a724  or      dl, cl
0x14003a726  movzx   ecx, dl
0x14003a729  mov     [rax+78h], cl
0x14003a72c  and     rcx, 1
0x14003a730  add     rcx, 5
0x14003a734  lea     rcx, [rcx+rcx*2]
0x14003a738  shl     rcx, 5
0x14003a73c  add     rcx, [rax]
0x14003a73f  call    CxPlatPoolAlloc
0x14003a744  xor     r10d, r10d
0x14003a747  mov     [rsp+190h+var_128], rax
0x14003a74c  mov     [r15+8], rax
0x14003a750  mov     r9, rax
0x14003a753  test    rax, rax
0x14003a756  jz      loc_14003A8DD
0x14003a75c  mov     [r15+10h], r10d
0x14003a760  xor     edx, edx
0x14003a762  mov     r8, [rdi+38h]
0x14003a766  mov     eax, ebx
0x14003a768  div     dword ptr [r8+80h]
0x14003a76f  mov     ecx, edx
0x14003a771  imul    rdx, rcx, 2B0h
0x14003a778  lea     rcx, [r8+90h]
0x14003a77f  add     rcx, rdx
0x14003a782  lea     r8, [r15+80h]
0x14003a789  mov     [r15+18h], rcx
0x14003a78d  movups  xmm0, [rbp+90h+var_100]
0x14003a791  mov     [rsp+190h+var_120], r8
0x14003a796  movups  xmmword ptr [r15+3Ch], xmm0
0x14003a79b  movsd   xmm1, [rbp+90h+var_F0]
0x14003a7a0  movsd   qword ptr [r15+4Ch], xmm1
0x14003a7a6  mov     eax, [rbp+90h+var_E8]
0x14003a7a9  mov     [r15+54h], eax
0x14003a7ad  movups  xmm0, [rbp+90h+var_E0]
0x14003a7b1  movups  xmmword ptr [r15+20h], xmm0
0x14003a7b6  movsd   xmm1, [rbp+90h+var_D0]
  ... truncated ...
```

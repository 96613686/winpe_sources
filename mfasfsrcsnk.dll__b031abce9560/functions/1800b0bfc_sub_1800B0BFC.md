# sub_1800B0BFC

- ea: `0x1800b0bfc`
- end: `0x1800b137c`
- name: `sub_1800B0BFC`
- size: `1920`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800b4e8c`
- `0x1800b570c`
- `0x1800bcee4`
- `0x1800bec70`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x180024594`
- `0x18003c314`
- `0x18003d2e0`
- `0x18003d2f8`
- `0x18003d740`
- `0x18003e15c`
- `0x18004f390`
- `0x18007fdd0`
- `0x1800b0bfc`
- `0x1800b84c4`
- `0x1800c6094`
- `0x1800c6354`
- `0x18013e2e0`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0d33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0dda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0f31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ff3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b10bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b110e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1287`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0d33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0dda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0f31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ff3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b10bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b110e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1287`

## string_xrefs

- `0x1800b0c31`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b0d8b`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b0e32`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b0f89`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b104b`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b1166`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b11b6`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`
- `0x1800b12df`: `CASFBytewiseMediaSource::ConfigureByteStreamBuffering`

## pseudocode

```c
__int64 __fastcall sub_1800B0BFC(__int64 a1, int a2, int a3)
{
  int v6; // ebx
  _WORD *v7; // r15
  __int64 (__fastcall ***v8)(_QWORD, __int64 *, __int64 *); // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // esi
  unsigned int i; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(); // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 (__fastcall ***v21)(); // rcx
  int v22; // esi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // xmm0_4
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 (__fastcall ***v32)(); // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 (__fastcall ***v36)(); // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 (__fastcall ***v41)(); // rcx
  __int64 v42; // rax
  __int64 (__fastcall ***v43)(); // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 (__fastcall ***v50)(); // rcx
  __int64 v51; // rax
  __int64 v52; // rax
  _BYTE v54[4]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v55; // [rsp+64h] [rbp-25h] BYREF
  __int64 v56; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v57[8]; // [rsp+70h] [rbp-19h] BYREF

  sub_18000A580(v54, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 5876);
  v6 = 0;
  v56 = 0;
  v55 = 0;
  v7 = 0;
  memset(v57, 0, sizeof(v57));
  v8 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 1200);
  if ( !v8 )
    goto LABEL_109;
  v9 = (**v8)(v8, qword_18014EE20, &v56);
  v6 = v9;
  if ( v9 == -2147467262 )
  {
    v6 = 0;
    goto LABEL_109;
  }
  if ( !*(_QWORD *)(a1 + 1312) )
  {
    if ( v9 >= 0 )
      goto LABEL_109;
    goto LABEL_107;
  }
  v11 = 0;
  if ( a3 )
  {
    v12 = *(_QWORD *)(a1 + 1024);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 200);
      for ( i = 0; i < v13; ++i )
      {
        v15 = sub_18003C314(a1, i);
        if ( v15 )
        {
          v16 = *(_QWORD *)(v15 + 1232) - *(_QWORD *)"vids";
          if ( !v16 )
            v16 = *(_QWORD *)(v15 + 1240) - 0x719B3800AA000080LL;
          if ( !v16 )
          {
            v11 = 80000000;
            break;
          }
        }
      }
    }
  }
  if ( !a2 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 32LL))(v56, 0);
    if ( v6 < 0 )
    {
      v17 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v18 = MFGetCallStackTracingWeakReference(0, v10);
        qword_180169350 = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v17 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = sub_180001870(v17);
        if ( *(_DWORD *)(v19 + 1996) != v6 )
          sub_18007FDD0(v19, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 5941, (unsigned int)v6);
      }
      if ( !byte_1801692C8 )
        goto LABEL_107;
      v20 = 520;
      goto LABEL_57;
    }
  }
  if ( !*(_QWORD *)(a1 + 1016) )
  {
    v21 = (__int64 (__fastcall ***)())qword_180169350;
    v22 = -2147467262;
    v6 = -2147467262;
    if ( !qword_180169350 )
    {
      v23 = MFGetCallStackTracingWeakReference(0, v10);
      qword_180169350 = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v21 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v21 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v24 = sub_180001870(v21);
      if ( *(_DWORD *)(v24 + 1996) != -2147467262 )
        sub_18007FDD0(v24, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 5953, 2147500034LL);
    }
    if ( !byte_1801692C8 )
      goto LABEL_107;
    v25 = 521;
    goto LABEL_38;
  }
  v26 = sub_1800C6094();
  v27 = *(_DWORD *)(a1 + 900);
  v57[0] = v26;
  v57[6] = *(_QWORD *)(a1 + 1296);
  v28 = 10000LL * *(unsigned int *)(a1 + 976);
  LODWORD(v57[7]) = v27;
  v29 = -1;
  v57[5] = v11;
  v57[4] = v28;
  if ( *(_QWORD *)(a1 + 1272) )
    v29 = *(_QWORD *)(a1 + 1272);
  v57[1] = v29;
  if ( (unsigned int)sub_180024594(a1, 0, 0, &v55) == -2147024774 )
  {
    if ( v55 <= 2 || (((_BYTE)v55 - 2) & 7) != 0 )
    {
      v43 = (__int64 (__fastcall ***)())qword_180169350;
      v22 = -2147418113;
      v6 = -2147418113;
      if ( !qword_180169350 )
      {
        v44 = MFGetCallStackTracingWeakReference(0, v55);
        qword_180169350 = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v43 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = sub_180001870(v43);
        if ( *(_DWORD *)(v45 + 1996) != -2147418113 )
          sub_18007FDD0(v45, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 6016, 2147549183LL);
      }
      if ( !byte_1801692C8 )
        goto LABEL_107;
      v25 = 522;
LABEL_38:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v25, &stru_180156148, a1, v22);
LABEL_107:
      if ( v56 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 32LL))(v56, 0);
      goto LABEL_109;
    }
    if ( (v55 & 0xFFFFFFF8) <= 0x320 )
    {
      v30 = sub_18003D2F8(v55);
      v7 = (_WORD *)v30;
      if ( !v30 )
      {
        v32 = (__int64 (__fastcall ***)())qword_180169350;
        v6 = -2147024882;
        if ( !qword_180169350 )
        {
          v33 = MFGetCallStackTracingWeakReference(0, v31);
          qword_180169350 = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v32 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = sub_180001870(v32);
          if ( *(_DWORD *)(v34 + 1996) != -2147024882 )
            sub_18007FDD0(v34, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 6030, 2147942414LL);
        }
        if ( !byte_1801692C8 )
          goto LABEL_107;
        v20 = 523;
        goto LABEL_57;
      }
      if ( (int)sub_180024594(a1, v30, v55, &v55) >= 0 )
      {
        if ( *v7 )
        {
          v36 = (__int64 (__fastcall ***)())qword_180169350;
          v22 = -2147418113;
          v6 = -2147418113;
          if ( !qword_180169350 )
          {
            v37 = MFGetCallStackTracingWeakReference(0, v35);
            qword_180169350 = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v36 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = sub_180001870(v36);
            if ( *(_DWORD *)(v38 + 1996) != -2147418113 )
              sub_18007FDD0(v38, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 6047, 2147549183LL);
          }
          if ( !byte_1801692C8 )
            goto LABEL_107;
          v25 = 524;
          goto LABEL_38;
        }
        LODWORD(v57[3]) = ((unsigned __int64)v55 - 2) >> 3;
        v57[2] = v7 + 1;
      }
    }
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v56 + 24LL))(v56, v57);
  if ( v6 < 0 )
  {
    v41 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v42 = MFGetCallStackTracingWeakReference(0, v39);
      qword_180169350 = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v41 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v46 = sub_180001870(v41);
      if ( *(_DWORD *)(v46 + 1996) != v6 )
        sub_18007FDD0(v46, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 6062, (unsigned int)v6);
    }
    if ( !byte_1801692C8 )
      goto LABEL_107;
    v20 = 525;
    goto LABEL_57;
  }
  *(_DWORD *)(a1 + 980) = sub_1800B84C4(v40, v57);
  if ( (unsigned __int8)byte_1801692CB >= 4u )
    sub_1800C6354(
      *((_QWORD *)RequestContext + 17),
      v47,
      v48,
      a1,
      v57[0],
      v57[1],
      v57[6],
      v57[4],
      *(float *)&v57[7],
      v57[3],
      v57[5]);
  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 32LL))(v56, 1);
    if ( v6 < 0 )
    {
      v50 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v51 = MFGetCallStackTracingWeakReference(0, v49);
        qword_180169350 = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v50 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = sub_180001870(v50);
        if ( *(_DWORD *)(v52 + 1996) != v6 )
          sub_18007FDD0(v52, "CASFBytewiseMediaSource::ConfigureByteStreamBuffering", 6084, (unsigned int)v6);
      }
      if ( !byte_1801692C8 )
        goto LABEL_107;
      v20 = 527;
LABEL_57:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v20, &stru_180156148, a1, v6);
      goto LABEL_107;
    }
  }
LABEL_109:
  j__o_free(v7);
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  sub_180005880(v54);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b0bfc  mov     [rsp-8+arg_8], rbx
0x1800b0c01  mov     [rsp-8+arg_10], rsi
0x1800b0c06  push    rbp
0x1800b0c07  push    rdi
0x1800b0c08  push    r12
0x1800b0c0a  push    r14
0x1800b0c0c  push    r15
0x1800b0c0e  lea     rbp, [rsp-37h]
0x1800b0c13  sub     rsp, 0C0h
0x1800b0c1a  mov     rax, cs:__security_cookie
0x1800b0c21  xor     rax, rsp
0x1800b0c24  mov     [rbp+57h+var_30], rax
0x1800b0c28  mov     esi, r8d
0x1800b0c2b  mov     r12d, edx
0x1800b0c2e  mov     rdi, rcx
0x1800b0c31  lea     rdx, aCasfbytewiseme_32; "CASFBytewiseMediaSource::ConfigureByteS"...
0x1800b0c38  mov     r8d, 16F4h
0x1800b0c3e  lea     rcx, [rbp+57h+var_80]
0x1800b0c42  call    sub_18000A580
0x1800b0c47  xor     ebx, ebx
0x1800b0c49  lea     rcx, [rbp+57h+var_70]; void *
0x1800b0c4d  xor     edx, edx; Val
0x1800b0c4f  mov     [rbp+57h+var_78], rbx
0x1800b0c53  mov     [rbp+57h+var_7C], ebx
0x1800b0c56  xor     r15d, r15d
0x1800b0c59  lea     r8d, [rbx+40h]; Size
0x1800b0c5d  call    memset
0x1800b0c62  mov     rcx, [rdi+4B0h]
0x1800b0c69  test    rcx, rcx
0x1800b0c6c  jz      loc_1800B1323
0x1800b0c72  mov     rax, [rcx]
0x1800b0c75  lea     r8, [rbp+57h+var_78]
0x1800b0c79  lea     rdx, qword_18014EE20
0x1800b0c80  mov     rax, [rax]
0x1800b0c83  call    cs:__guard_dispatch_icall_fptr
0x1800b0c89  mov     ebx, eax
0x1800b0c8b  cmp     eax, 80004002h
0x1800b0c90  jnz     short loc_1800B0C99
0x1800b0c92  xor     ebx, ebx
0x1800b0c94  jmp     loc_1800B1323
0x1800b0c99  cmp     [rdi+520h], r15
0x1800b0ca0  jz      loc_1800B1307
0x1800b0ca6  xor     r14d, r14d
0x1800b0ca9  test    esi, esi
0x1800b0cab  jz      short loc_1800B0D01
0x1800b0cad  mov     rax, [rdi+400h]
0x1800b0cb4  test    rax, rax
0x1800b0cb7  jz      short loc_1800B0D01
0x1800b0cb9  mov     esi, [rax+0C8h]
0x1800b0cbf  xor     ebx, ebx
0x1800b0cc1  cmp     ebx, esi
0x1800b0cc3  jnb     short loc_1800B0D01
0x1800b0cc5  mov     edx, ebx
0x1800b0cc7  mov     rcx, rdi
0x1800b0cca  call    sub_18003C314
0x1800b0ccf  test    rax, rax
0x1800b0cd2  jz      short loc_1800B0CF7
0x1800b0cd4  mov     rcx, [rax+4D0h]
0x1800b0cdb  sub     rcx, qword ptr cs:aVids; "vids"
0x1800b0ce2  jnz     short loc_1800B0CF2
0x1800b0ce4  mov     rcx, [rax+4D8h]
0x1800b0ceb  sub     rcx, cs:qword_18014E7C8
0x1800b0cf2  test    rcx, rcx
0x1800b0cf5  jz      short loc_1800B0CFB
0x1800b0cf7  inc     ebx
0x1800b0cf9  jmp     short loc_1800B0CC1
0x1800b0cfb  mov     r14d, 4C4B400h
0x1800b0d01  test    r12d, r12d
0x1800b0d04  jnz     loc_1800B0DB7
0x1800b0d0a  mov     rcx, [rbp+57h+var_78]
0x1800b0d0e  xor     edx, edx
0x1800b0d10  mov     rax, [rcx]
0x1800b0d13  mov     rax, [rax+20h]
0x1800b0d17  call    cs:__guard_dispatch_icall_fptr
0x1800b0d1d  mov     ebx, eax
0x1800b0d1f  test    eax, eax
0x1800b0d21  jns     loc_1800B0DB7
0x1800b0d27  mov     rcx, cs:qword_180169350
0x1800b0d2e  test    rcx, rcx
0x1800b0d31  jnz     short loc_1800B0D75
0x1800b0d33  call    cs:MFGetCallStackTracingWeakReference
0x1800b0d39  mov     cs:qword_180169350, rax
0x1800b0d40  mov     rcx, rax
0x1800b0d43  test    rax, rax
0x1800b0d46  jz      short loc_1800B0D67
0x1800b0d48  mov     rax, [rax]
0x1800b0d4b  mov     edx, 7F0h
0x1800b0d50  mov     rax, [rax+8]
0x1800b0d54  call    cs:__guard_dispatch_icall_fptr
0x1800b0d5a  test    eax, eax
0x1800b0d5c  jz      short loc_1800B0D67
0x1800b0d5e  mov     rcx, cs:qword_180169350
0x1800b0d65  jmp     short loc_1800B0D75
0x1800b0d67  lea     rcx, off_1801683B0
0x1800b0d6e  mov     cs:qword_180169350, rcx
0x1800b0d75  cmp     [rcx+8], r15b
0x1800b0d79  jz      short loc_1800B0DA0
0x1800b0d7b  call    sub_180001870
0x1800b0d80  cmp     [rax+7CCh], ebx
0x1800b0d86  jz      short loc_1800B0DA0
0x1800b0d88  mov     r9d, ebx
0x1800b0d8b  lea     rdx, aCasfbytewiseme_32; "CASFBytewiseMediaSource::ConfigureByteS"...
0x1800b0d92  mov     r8d, 1735h
0x1800b0d98  mov     rcx, rax
0x1800b0d9b  call    sub_18007FDD0
0x1800b0da0  cmp     cs:byte_1801692C8, 1
0x1800b0da7  jb      loc_1800B130B
0x1800b0dad  mov     edx, 208h
0x1800b0db2  jmp     loc_1800B0FB0
0x1800b0db7  mov     rcx, [rdi+3F8h]
0x1800b0dbe  test    rcx, rcx
0x1800b0dc1  jnz     loc_1800B0E7C
0x1800b0dc7  mov     rcx, cs:qword_180169350
0x1800b0dce  mov     esi, 80004002h
0x1800b0dd3  mov     ebx, esi
0x1800b0dd5  test    rcx, rcx
0x1800b0dd8  jnz     short loc_1800B0E1C
0x1800b0dda  call    cs:MFGetCallStackTracingWeakReference
0x1800b0de0  mov     cs:qword_180169350, rax
0x1800b0de7  mov     rcx, rax
0x1800b0dea  test    rax, rax
0x1800b0ded  jz      short loc_1800B0E0E
0x1800b0def  mov     rax, [rax]
0x1800b0df2  mov     edx, 7F0h
0x1800b0df7  mov     rax, [rax+8]
0x1800b0dfb  call    cs:__guard_dispatch_icall_fptr
0x1800b0e01  test    eax, eax
0x1800b0e03  jz      short loc_1800B0E0E
0x1800b0e05  mov     rcx, cs:qword_180169350
0x1800b0e0c  jmp     short loc_1800B0E1C
0x1800b0e0e  lea     rcx, off_1801683B0
0x1800b0e15  mov     cs:qword_180169350, rcx
0x1800b0e1c  cmp     [rcx+8], r15b
0x1800b0e20  jz      short loc_1800B0E47
0x1800b0e22  call    sub_180001870
0x1800b0e27  cmp     [rax+7CCh], esi
0x1800b0e2d  jz      short loc_1800B0E47
0x1800b0e2f  mov     r9d, esi
0x1800b0e32  lea     rdx, aCasfbytewiseme_32; "CASFBytewiseMediaSource::ConfigureByteS"...
0x1800b0e39  mov     r8d, 1741h
0x1800b0e3f  mov     rcx, rax
0x1800b0e42  call    sub_18007FDD0
0x1800b0e47  cmp     cs:byte_1801692C8, 1
0x1800b0e4e  jb      loc_1800B130B
0x1800b0e54  mov     edx, 209h
0x1800b0e59  mov     dword ptr [rsp+0E0h+var_C0], esi
0x1800b0e5d  mov     rcx, cs:RequestContext
0x1800b0e64  lea     r8, stru_180156148
0x1800b0e6b  mov     r9, rdi
0x1800b0e6e  mov     rcx, [rcx+10h]
0x1800b0e72  call    sub_18004F390
0x1800b0e77  jmp     loc_1800B130B
0x1800b0e7c  call    sub_1800C6094
0x1800b0e81  movss   xmm0, dword ptr [rdi+384h]
0x1800b0e89  lea     r9, [rbp+57h+var_7C]
0x1800b0e8d  mov     [rbp+57h+var_70], rax
0x1800b0e91  mov     rax, [rdi+510h]
0x1800b0e98  mov     [rbp+57h+var_40], rax
0x1800b0e9c  mov     eax, [rdi+3D0h]
0x1800b0ea2  imul    rcx, rax, 2710h
0x1800b0ea9  movss   [rbp+57h+var_38], xmm0
0x1800b0eae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b0eb2  mov     [rbp+57h+var_48], r14
0x1800b0eb6  mov     [rbp+57h+var_50], rcx
0x1800b0eba  mov     rcx, [rdi+4F8h]
0x1800b0ec1  test    rcx, rcx
0x1800b0ec4  cmovnz  rax, rcx
0x1800b0ec8  xor     r8d, r8d
0x1800b0ecb  xor     edx, edx
0x1800b0ecd  mov     [rbp+57h+var_68], rax
0x1800b0ed1  mov     rcx, rdi
0x1800b0ed4  call    sub_180024594
0x1800b0ed9  cmp     eax, 8007007Ah
0x1800b0ede  jnz     loc_1800B108D
0x1800b0ee4  mov     edx, [rbp+57h+var_7C]
0x1800b0ee7  cmp     edx, 2
0x1800b0eea  jbe     loc_1800B10FB
0x1800b0ef0  lea     eax, [rdx+0FEh]
0x1800b0ef6  mov     ecx, edx
0x1800b0ef8  test    al, 7
0x1800b0efa  jnz     loc_1800B10FB
0x1800b0f00  and     edx, 0FFFFFFF8h
0x1800b0f03  cmp     edx, 320h
0x1800b0f09  ja      loc_1800B108D
0x1800b0f0f  call    sub_18003D2F8
0x1800b0f14  mov     r15, rax
0x1800b0f17  test    rax, rax
0x1800b0f1a  jnz     loc_1800B0FB9
0x1800b0f20  mov     rcx, cs:qword_180169350
0x1800b0f27  mov     ebx, 8007000Eh
0x1800b0f2c  test    rcx, rcx
0x1800b0f2f  jnz     short loc_1800B0F73
0x1800b0f31  call    cs:MFGetCallStackTracingWeakReference
0x1800b0f37  mov     cs:qword_180169350, rax
0x1800b0f3e  mov     rcx, rax
0x1800b0f41  test    rax, rax
0x1800b0f44  jz      short loc_1800B0F65
0x1800b0f46  mov     rax, [rax]
0x1800b0f49  mov     edx, 7F0h
0x1800b0f4e  mov     rax, [rax+8]
0x1800b0f52  call    cs:__guard_dispatch_icall_fptr
0x1800b0f58  test    eax, eax
0x1800b0f5a  jz      short loc_1800B0F65
0x1800b0f5c  mov     rcx, cs:qword_180169350
0x1800b0f63  jmp     short loc_1800B0F73
0x1800b0f65  lea     rcx, off_1801683B0
0x1800b0f6c  mov     cs:qword_180169350, rcx
0x1800b0f73  cmp     byte ptr [rcx+8], 0
0x1800b0f77  jz      short loc_1800B0F9E
0x1800b0f79  call    sub_180001870
0x1800b0f7e  cmp     [rax+7CCh], ebx
0x1800b0f84  jz      short loc_1800B0F9E
0x1800b0f86  mov     r9d, ebx
0x1800b0f89  lea     rdx, aCasfbytewiseme_32; "CASFBytewiseMediaSource::ConfigureByteS"...
0x1800b0f90  mov     r8d, 178Eh
0x1800b0f96  mov     rcx, rax
0x1800b0f99  call    sub_18007FDD0
0x1800b0f9e  cmp     cs:byte_1801692C8, 1
0x1800b0fa5  jb      loc_1800B130B
0x1800b0fab  mov     edx, 20Bh
0x1800b0fb0  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800b0fb4  jmp     loc_1800B0E5D
0x1800b0fb9  mov     r8d, [rbp+57h+var_7C]
0x1800b0fbd  lea     r9, [rbp+57h+var_7C]
0x1800b0fc1  mov     rdx, r15
0x1800b0fc4  mov     rcx, rdi
0x1800b0fc7  call    sub_180024594
0x1800b0fcc  test    eax, eax
0x1800b0fce  js      loc_1800B108D
0x1800b0fd4  xor     eax, eax
0x1800b0fd6  cmp     ax, [r15]
0x1800b0fda  jz      loc_1800B1077
0x1800b0fe0  mov     rcx, cs:qword_180169350
0x1800b0fe7  mov     esi, 8000FFFFh
0x1800b0fec  mov     ebx, esi
0x1800b0fee  test    rcx, rcx
0x1800b0ff1  jnz     short loc_1800B1035
0x1800b0ff3  call    cs:MFGetCallStackTracingWeakReference
0x1800b0ff9  mov     cs:qword_180169350, rax
0x1800b1000  mov     rcx, rax
0x1800b1003  test    rax, rax
0x1800b1006  jz      short loc_1800B1027
0x1800b1008  mov     rax, [rax]
0x1800b100b  mov     edx, 7F0h
0x1800b1010  mov     rax, [rax+8]
0x1800b1014  call    cs:__guard_dispatch_icall_fptr
0x1800b101a  test    eax, eax
0x1800b101c  jz      short loc_1800B1027
0x1800b101e  mov     rcx, cs:qword_180169350
0x1800b1025  jmp     short loc_1800B1035
0x1800b1027  lea     rcx, off_1801683B0
0x1800b102e  mov     cs:qword_180169350, rcx
0x1800b1035  cmp     byte ptr [rcx+8], 0
0x1800b1039  jz      short loc_1800B1060
0x1800b103b  call    sub_180001870
0x1800b1040  cmp     [rax+7CCh], esi
0x1800b1046  jz      short loc_1800B1060
0x1800b1048  mov     r9d, esi
0x1800b104b  lea     rdx, aCasfbytewiseme_32; "CASFBytewiseMediaSource::ConfigureByteS"...
0x1800b1052  mov     r8d, 179Fh
0x1800b1058  mov     rcx, rax
0x1800b105b  call    sub_18007FDD0
0x1800b1060  cmp     cs:byte_1801692C8, 1
0x1800b1067  jb      loc_1800B130B
0x1800b106d  mov     edx, 20Ch
0x1800b1072  jmp     loc_1800B0E59
0x1800b1077  mov     eax, [rbp+57h+var_7C]
0x1800b107a  sub     rax, 2
0x1800b107e  shr     rax, 3
0x1800b1082  mov     [rbp+57h+var_58], eax
0x1800b1085  lea     rax, [r15+2]
0x1800b1089  mov     [rbp+57h+var_60], rax
0x1800b108d  mov     rcx, [rbp+57h+var_78]
0x1800b1091  lea     rdx, [rbp+57h+var_70]
0x1800b1095  mov     rax, [rcx]
0x1800b1098  mov     rax, [rax+18h]
0x1800b109c  call    cs:__guard_dispatch_icall_fptr
0x1800b10a2  mov     ebx, eax
0x1800b10a4  test    eax, eax
0x1800b10a6  jns     loc_1800B11E2
0x1800b10ac  mov     rcx, cs:qword_180169350
0x1800b10b3  test    rcx, rcx
0x1800b10b6  jnz     loc_1800B11A0
0x1800b10bc  call    cs:MFGetCallStackTracingWeakReference
0x1800b10c2  mov     cs:qword_180169350, rax
0x1800b10c9  mov     rcx, rax
0x1800b10cc  test    rax, rax
0x1800b10cf  jz      loc_1800B1192
0x1800b10d5  mov     rax, [rax]
0x1800b10d8  mov     edx, 7F0h
0x1800b10dd  mov     rax, [rax+8]
0x1800b10e1  call    cs:__guard_dispatch_icall_fptr
0x1800b10e7  test    eax, eax
0x1800b10e9  jz      loc_1800B1192
0x1800b10ef  mov     rcx, cs:qword_180169350
0x1800b10f6  jmp     loc_1800B11A0
0x1800b10fb  mov     rcx, cs:qword_180169350
0x1800b1102  mov     esi, 8000FFFFh
0x1800b1107  mov     ebx, esi
0x1800b1109  test    rcx, rcx
  ... truncated ...
```

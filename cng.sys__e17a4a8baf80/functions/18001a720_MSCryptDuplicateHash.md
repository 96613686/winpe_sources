# MSCryptDuplicateHash

- ea: `0x18001a720`
- end: `0x18001b681`
- name: `MSCryptDuplicateHash`
- size: `3937`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800017a0`
- `0x1800019f0`
- `0x180001c40`
- `0x180001e80`
- `0x180002220`
- `0x18001155c`
- `0x1800123d0`
- `0x18001a648`
- `0x18001a720`
- `0x18001bfe0`
- `0x180024da0`
- `0x1800442a8`
- `0x180052084`
- `0x18006eb24`
- `0x180086880`
- `0x18009ac90`
- `0x18009f5e0`
- `0x18009f700`
- `0x1800a45c0`

## string_xrefs

- `0x18001b622`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18001b65c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptDuplicateHash(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // r9
  unsigned int *v8; // rax
  unsigned int v9; // r9d
  unsigned int *v10; // rdi
  size_t v11; // rax
  int v12; // ebx
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx

  if ( a5 )
  {
    v7 = 3090;
    goto LABEL_68;
  }
  v8 = (unsigned int *)validateMSCryptHash(a1, a2);
  v10 = v8;
  if ( !v8 )
  {
    v7 = 3099;
    goto LABEL_68;
  }
  if ( !a2 || !a3 || v8[9] )
  {
    v7 = 3108;
LABEL_68:
    v12 = -1073741811;
    v17 = 3221225485LL;
LABEL_69:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v7);
    return (unsigned int)v12;
  }
  v11 = *v8;
  if ( v9 >= (unsigned int)v11 )
  {
    memmove((void *)a3, v10, v11);
    switch ( v10[2] )
    {
      case 0x20001u:
      case 0x20003u:
      case 0x20004u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        goto LABEL_63;
      case 0x20002u:
      case 0x20005u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
        goto LABEL_63;
      case 0x20006u:
      case 0x20007u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
        *(_OWORD *)(a3 + 256) = *((_OWORD *)v10 + 16);
        *(_OWORD *)(a3 + 272) = *((_OWORD *)v10 + 17);
        *(_OWORD *)(a3 + 288) = *((_OWORD *)v10 + 18);
        *(_OWORD *)(a3 + 304) = *((_OWORD *)v10 + 19);
        *(_OWORD *)(a3 + 320) = *((_OWORD *)v10 + 20);
        *(_OWORD *)(a3 + 336) = *((_OWORD *)v10 + 21);
        goto LABEL_63;
      case 0x20008u:
        SymCryptGcmExpandKey(a3 + 128, *((_QWORD *)v10 + 272), v10 + 674, *((_QWORD *)v10 + 336));
        if ( v10[29] )
        {
          *(_OWORD *)(a3 + 2736) = *((_OWORD *)v10 + 171);
          *(_OWORD *)(a3 + 2752) = *((_OWORD *)v10 + 172);
          *(_OWORD *)(a3 + 2768) = *((_OWORD *)v10 + 173);
          *(_OWORD *)(a3 + 2784) = *((_OWORD *)v10 + 174);
          *(_OWORD *)(a3 + 2800) = *((_OWORD *)v10 + 175);
          *(_OWORD *)(a3 + 2816) = *((_OWORD *)v10 + 176);
          *(_OWORD *)(a3 + 2832) = *((_OWORD *)v10 + 177);
          if ( a3 != -128 )
            *(_QWORD *)(a3 + 2736) = a3 + 128;
        }
        goto LABEL_63;
      case 0x20009u:
      case 0x2000Bu:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        SymCryptHmacSha1StateCopy(v10 + 52, a3 + 128, a3 + 208);
        goto LABEL_63;
      case 0x2000Au:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        SymCryptHmacMd5StateCopy(v10 + 44, a3 + 128, a3 + 176);
        goto LABEL_63;
      case 0x2000Cu:
      case 0x2000Du:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
        *(_OWORD *)(a3 + 256) = *((_OWORD *)v10 + 16);
        SymCryptHmacSha512StateCopy(v10 + 68, a3 + 128, a3 + 272);
        goto LABEL_63;
      case 0x2000Eu:
        SymCryptAesKeyCopy(v10 + 32, a3 + 128);
        *(_OWORD *)(v14 + 496) = *(_OWORD *)(v15 + 496);
        *(_OWORD *)(v14 + 512) = *(_OWORD *)(v15 + 512);
        *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
        *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
        *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
        *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
        if ( !v14 )
          v14 = *((_QWORD *)v10 + 89);
        *(_QWORD *)(a3 + 712) = v14;
        goto LABEL_63;
      case 0x2000Fu:
        SymCryptSha3_256StateCopy(v10 + 32, (void *)(a3 + 128));
        goto LABEL_63;
      case 0x20010u:
        SymCryptSha3_384StateCopy(v10 + 32, (void *)(a3 + 128));
        goto LABEL_63;
      case 0x20011u:
        SymCryptSha3_512StateCopy(v10 + 32, (void *)(a3 + 128));
        goto LABEL_63;
      case 0x20012u:
      case 0x20013u:
      case 0x20014u:
        SymCryptHmacKeyCopy(v10 + 32, a3 + 128);
        SymCryptHmacStateCopy(v10 + 160, a3 + 128, a3 + 640);
        goto LABEL_63;
      case 0x20015u:
        if ( v10[70] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 528) = *((_OWORD *)v10 + 33);
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v10 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v10 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v10 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v10 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v10 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v10 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v10 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v10 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v10 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v10 + 47);
        }
        if ( v10[70] )
        {
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v10 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v10 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v10 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v10 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v10 + 22);
          *(_OWORD *)(a3 + 368) = *((_OWORD *)v10 + 23);
          *(_OWORD *)(a3 + 384) = *((_OWORD *)v10 + 24);
          *(_OWORD *)(a3 + 400) = *((_OWORD *)v10 + 25);
          *(_OWORD *)(a3 + 416) = *((_OWORD *)v10 + 26);
          *(_OWORD *)(a3 + 432) = *((_OWORD *)v10 + 27);
          *(_OWORD *)(a3 + 448) = *((_OWORD *)v10 + 28);
          *(_OWORD *)(a3 + 464) = *((_OWORD *)v10 + 29);
          *(_OWORD *)(a3 + 480) = *((_OWORD *)v10 + 30);
          *(_OWORD *)(a3 + 496) = *((_OWORD *)v10 + 31);
          *(_OWORD *)(a3 + 512) = *((_OWORD *)v10 + 32);
        }
        *(_QWORD *)(a3 + 184) = 0;
        *(_DWORD *)(a3 + 192) = 0;
        *(_QWORD *)(a3 + 264) = 0;
        *(_DWORD *)(a3 + 272) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 120, *((_QWORD *)v10 + 23), v10[48]);
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3335;
          goto LABEL_33;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v10 + 33), v10[68]);
        if ( v12 >= 0 )
          goto LABEL_63;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3343;
        goto LABEL_36;
      case 0x20016u:
        if ( v10[70] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 528) = *((_OWORD *)v10 + 33);
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v10 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v10 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v10 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v10 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v10 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v10 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v10 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v10 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v10 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v10 + 47);
        }
        if ( v10[70] )
        {
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v10 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v10 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v10 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v10 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v10 + 22);
          *(_OWORD *)(a3 + 368) = *((_OWORD *)v10 + 23);
          *(_OWORD *)(a3 + 384) = *((_OWORD *)v10 + 24);
          *(_OWORD *)(a3 + 400) = *((_OWORD *)v10 + 25);
          *(_OWORD *)(a3 + 416) = *((_OWORD *)v10 + 26);
          *(_OWORD *)(a3 + 432) = *((_OWORD *)v10 + 27);
          *(_OWORD *)(a3 + 448) = *((_OWORD *)v10 + 28);
          *(_OWORD *)(a3 + 464) = *((_OWORD *)v10 + 29);
          *(_OWORD *)(a3 + 480) = *((_OWORD *)v10 + 30);
          *(_OWORD *)(a3 + 496) = *((_OWORD *)v10 + 31);
          *(_OWORD *)(a3 + 512) = *((_OWORD *)v10 + 32);
        }
        *(_QWORD *)(a3 + 184) = 0;
        *(_DWORD *)(a3 + 192) = 0;
        *(_QWORD *)(a3 + 264) = 0;
        *(_DWORD *)(a3 + 272) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 120, *((_QWORD *)v10 + 23), v10[48]);
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3374;
          goto LABEL_33;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v10 + 33), v10[68]);
        if ( v12 >= 0 )
          goto LABEL_63;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3382;
LABEL_36:
        v17 = (unsigned int)v12;
        goto LABEL_69;
      case 0x20017u:
        if ( v10[132] )
        {
          *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
          *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
          *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
          *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
          *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
          *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
          *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
          *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
          *(_OWORD *)(a3 + 256) = *((_OWORD *)v10 + 16);
          *(_OWORD *)(a3 + 272) = *((_OWORD *)v10 + 17);
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v10 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v10 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v10 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v10 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v10 + 22);
        }
        if ( v10[132] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v10 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v10 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v10 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v10 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v10 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v10 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v10 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v10 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v10 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v10 + 47);
          *(_OWORD *)(a3 + 768) = *((_OWORD *)v10 + 48);
        }
        *(_QWORD *)(a3 + 432) = 0;
        *(_DWORD *)(a3 + 440) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 368, *((_QWORD *)v10 + 54), v10[110]);
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3409;
          goto LABEL_33;
        }
        *(_QWORD *)(a3 + 512) = 0;
        *(_DWORD *)(a3 + 520) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 448, *((_QWORD *)v10 + 64), v10[130]);
        v12 = v16;
        if ( v16 >= 0 )
          goto LABEL_63;
        v7 = 3417;
        goto LABEL_33;
      case 0x20018u:
        if ( v10[132] )
        {
          *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
          *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
          *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
          *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
          *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
          *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
          *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
          *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
          *(_OWORD *)(a3 + 256) = *((_OWORD *)v10 + 16);
          *(_OWORD *)(a3 + 272) = *((_OWORD *)v10 + 17);
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v10 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v10 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v10 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v10 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v10 + 22);
        }
        if ( v10[132] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v10 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v10 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v10 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v10 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v10 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v10 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v10 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v10 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v10 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v10 + 47);
          *(_OWORD *)(a3 + 768) = *((_OWORD *)v10 + 48);
        }
        *(_QWORD *)(a3 + 432) = 0;
        *(_DWORD *)(a3 + 440) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 368, *((_QWORD *)v10 + 54), v10[110]);
        v12 = v16;
        if ( v16 >= 0 )
        {
          *(_QWORD *)(a3 + 512) = 0;
          *(_DWORD *)(a3 + 520) = 0;
          v16 = MSCryptCustomBufferUpdate(a3 + 448, *((_QWORD *)v10 + 64), v10[130]);
          v12 = v16;
          if ( v16 >= 0 )
          {
LABEL_63:
            *a2 = a3;
            return 0;
          }
          v7 = 3452;
        }
        else
        {
          v7 = 3444;
        }
LABEL_33:
        v17 = (unsigned int)v16;
        goto LABEL_69;
      case 0x20019u:
        SymCryptShake128StateCopy(v10 + 32, (void *)(a3 + 128));
        goto LABEL_63;
      case 0x2001Au:
        SymCryptShake256StateCopy(v10 + 32, (void *)(a3 + 128));
        goto LABEL_63;
      default:
        v12 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v13,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            155);
        return (unsigned int)v12;
    }
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x18001a720  push    rbx
0x18001a722  push    rbp
0x18001a723  push    rsi
0x18001a724  push    rdi
0x18001a725  push    r12
0x18001a727  push    r14
0x18001a729  push    r15
0x18001a72b  sub     rsp, 40h
0x18001a72f  xor     r12d, r12d
0x18001a732  mov     rsi, r8
0x18001a735  mov     r15, rdx
0x18001a738  cmp     [rsp+78h+arg_20], r12d
0x18001a740  jz      short loc_18001A74D
0x18001a742  mov     r9d, 0C12h
0x18001a748  jmp     loc_18001B652
0x18001a74d  call    validateMSCryptHash
0x18001a752  mov     rdi, rax
0x18001a755  test    rax, rax
0x18001a758  jnz     short loc_18001A765
0x18001a75a  mov     r9d, 0C1Bh
0x18001a760  jmp     loc_18001B652
0x18001a765  test    r15, r15
0x18001a768  jz      loc_18001B64C
0x18001a76e  test    rsi, rsi
0x18001a771  jz      loc_18001B64C
0x18001a777  cmp     [rax+24h], r12d
0x18001a77b  jnz     loc_18001B64C
0x18001a781  mov     eax, [rax]
0x18001a783  cmp     r9d, eax
0x18001a786  jnb     short loc_18001A792
0x18001a788  mov     ebx, 0C0000023h
0x18001a78d  jmp     loc_18001B66F
0x18001a792  mov     r8, rax; Size
0x18001a795  mov     rdx, rdi; Src
0x18001a798  mov     rcx, rsi; void *
0x18001a79b  call    memmove
0x18001a7a0  mov     eax, [rdi+8]
0x18001a7a3  add     eax, 0FFFDFFFFh; switch 26 cases
0x18001a7a8  cmp     eax, 19h
0x18001a7ab  ja      def_18001A7C2; jumptable 000000018001A7C2 default case
0x18001a7b1  lea     rcx, cs:180000000h
0x18001a7b8  mov     eax, ds:(jpt_18001A7C2 - 180000000h)[rcx+rax*4]
0x18001a7bf  add     rax, rcx
0x18001a7c2  jmp     rax; switch jump
0x18001a7c8  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 cases 131073,131075,131076
0x18001a7cf  movaps  xmmword ptr [rsi+80h], xmm0
0x18001a7d6  movaps  xmm1, xmmword ptr [rdi+90h]
0x18001a7dd  movaps  xmmword ptr [rsi+90h], xmm1
0x18001a7e4  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18001a7eb  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18001a7f2  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18001a7f9  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18001a800  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18001a807  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18001a80e  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18001a815  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18001a81c  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18001a823  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18001a82a  jmp     loc_18001B5F7
0x18001a82f  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 cases 131074,131077
0x18001a836  movaps  xmmword ptr [rsi+80h], xmm0
0x18001a83d  movaps  xmm1, xmmword ptr [rdi+90h]
0x18001a844  movaps  xmmword ptr [rsi+90h], xmm1
0x18001a84b  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18001a852  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18001a859  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18001a860  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18001a867  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18001a86e  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18001a875  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18001a87c  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18001a883  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18001a88a  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18001a891  movaps  xmm1, xmmword ptr [rdi+0F0h]
0x18001a898  movaps  xmmword ptr [rsi+0F0h], xmm1
0x18001a89f  jmp     loc_18001B5F7
0x18001a8a4  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 cases 131078,131079
0x18001a8ab  movups  xmmword ptr [rsi+80h], xmm0
0x18001a8b2  movups  xmm1, xmmword ptr [rdi+90h]
0x18001a8b9  movups  xmmword ptr [rsi+90h], xmm1
0x18001a8c0  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18001a8c7  movups  xmmword ptr [rsi+0A0h], xmm0
0x18001a8ce  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18001a8d5  movups  xmmword ptr [rsi+0B0h], xmm1
0x18001a8dc  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18001a8e3  movups  xmmword ptr [rsi+0C0h], xmm0
0x18001a8ea  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18001a8f1  movups  xmmword ptr [rsi+0D0h], xmm1
0x18001a8f8  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18001a8ff  movups  xmmword ptr [rsi+0E0h], xmm0
0x18001a906  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18001a90d  movups  xmmword ptr [rsi+0F0h], xmm1
0x18001a914  movups  xmm0, xmmword ptr [rdi+100h]
0x18001a91b  movups  xmmword ptr [rsi+100h], xmm0
0x18001a922  movups  xmm1, xmmword ptr [rdi+110h]
0x18001a929  movups  xmmword ptr [rsi+110h], xmm1
0x18001a930  movups  xmm0, xmmword ptr [rdi+120h]
0x18001a937  movups  xmmword ptr [rsi+120h], xmm0
0x18001a93e  movups  xmm1, xmmword ptr [rdi+130h]
0x18001a945  movups  xmmword ptr [rsi+130h], xmm1
0x18001a94c  movups  xmm0, xmmword ptr [rdi+140h]
0x18001a953  movups  xmmword ptr [rsi+140h], xmm0
0x18001a95a  movups  xmm1, xmmword ptr [rdi+150h]
0x18001a961  movups  xmmword ptr [rsi+150h], xmm1
0x18001a968  jmp     loc_18001B5F7
0x18001a96d  mov     r9, [rdi+0A80h]; jumptable 000000018001A7C2 case 131080
0x18001a974  lea     rbx, [rsi+80h]
0x18001a97b  mov     rdx, [rdi+880h]
0x18001a982  lea     r8, [rdi+0A88h]
0x18001a989  mov     rcx, rbx
0x18001a98c  call    SymCryptGcmExpandKey
0x18001a991  cmp     [rdi+74h], r12d
0x18001a995  jz      loc_18001B5F7
0x18001a99b  movaps  xmm0, xmmword ptr [rdi+0AB0h]
0x18001a9a2  movaps  xmmword ptr [rsi+0AB0h], xmm0
0x18001a9a9  movaps  xmm1, xmmword ptr [rdi+0AC0h]
0x18001a9b0  movaps  xmmword ptr [rsi+0AC0h], xmm1
0x18001a9b7  movaps  xmm0, xmmword ptr [rdi+0AD0h]
0x18001a9be  movaps  xmmword ptr [rsi+0AD0h], xmm0
0x18001a9c5  movaps  xmm1, xmmword ptr [rdi+0AE0h]
0x18001a9cc  movaps  xmmword ptr [rsi+0AE0h], xmm1
0x18001a9d3  movaps  xmm0, xmmword ptr [rdi+0AF0h]
0x18001a9da  movaps  xmmword ptr [rsi+0AF0h], xmm0
0x18001a9e1  movaps  xmm1, xmmword ptr [rdi+0B00h]
0x18001a9e8  movaps  xmmword ptr [rsi+0B00h], xmm1
0x18001a9ef  movaps  xmm0, xmmword ptr [rdi+0B10h]
0x18001a9f6  movaps  xmmword ptr [rsi+0B10h], xmm0
0x18001a9fd  test    rbx, rbx
0x18001aa00  jz      loc_18001B5F7
0x18001aa06  mov     [rsi+0AB0h], rbx
0x18001aa0d  jmp     loc_18001B5F7
0x18001aa12  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 case 131081
0x18001aa19  lea     rdx, [rsi+80h]
0x18001aa20  movaps  xmmword ptr [rdx], xmm0
0x18001aa23  lea     r8, [rsi+0D0h]
0x18001aa2a  movaps  xmm1, xmmword ptr [rdi+90h]
0x18001aa31  lea     rcx, [rdi+0D0h]
0x18001aa38  movaps  xmmword ptr [rdx+10h], xmm1
0x18001aa3c  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18001aa43  movaps  xmmword ptr [rdx+20h], xmm0
0x18001aa47  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18001aa4e  movaps  xmmword ptr [rdx+30h], xmm1
0x18001aa52  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18001aa59  movaps  xmmword ptr [rdx+40h], xmm0
0x18001aa5d  call    SymCryptHmacSha1StateCopy
0x18001aa62  jmp     loc_18001B5F7
0x18001aa67  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 case 131082
0x18001aa6e  lea     rdx, [rsi+80h]
0x18001aa75  movaps  xmmword ptr [rdx], xmm0
0x18001aa78  lea     r8, [rsi+0B0h]
0x18001aa7f  movaps  xmm1, xmmword ptr [rdi+90h]
0x18001aa86  lea     rcx, [rdi+0B0h]
0x18001aa8d  movaps  xmmword ptr [rdx+10h], xmm1
0x18001aa91  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18001aa98  movaps  xmmword ptr [rdx+20h], xmm0
0x18001aa9c  call    SymCryptHmacMd5StateCopy
0x18001aaa1  jmp     loc_18001B5F7
0x18001aaa6  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 case 131083
0x18001aaad  lea     rdx, [rsi+80h]
0x18001aab4  movaps  xmmword ptr [rdx], xmm0
0x18001aab7  lea     r8, [rsi+0D0h]
0x18001aabe  movaps  xmm1, xmmword ptr [rdi+90h]
0x18001aac5  lea     rcx, [rdi+0D0h]
0x18001aacc  movaps  xmmword ptr [rdx+10h], xmm1
0x18001aad0  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18001aad7  movaps  xmmword ptr [rdx+20h], xmm0
0x18001aadb  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18001aae2  movaps  xmmword ptr [rdx+30h], xmm1
0x18001aae6  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18001aaed  movaps  xmmword ptr [rdx+40h], xmm0
0x18001aaf1  call    SymCryptHmacSha1StateCopy
0x18001aaf6  jmp     loc_18001B5F7
0x18001aafb  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 case 131084
0x18001ab02  lea     rdx, [rsi+80h]
0x18001ab09  lea     r8, [rsi+110h]
0x18001ab10  movups  xmmword ptr [rdx], xmm0
0x18001ab13  lea     rcx, [rdi+110h]
0x18001ab1a  movups  xmm1, xmmword ptr [rdi+90h]
0x18001ab21  movups  xmmword ptr [rdx+10h], xmm1
0x18001ab25  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18001ab2c  movups  xmmword ptr [rdx+20h], xmm0
0x18001ab30  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18001ab37  movups  xmmword ptr [rdx+30h], xmm1
0x18001ab3b  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18001ab42  movups  xmmword ptr [rdx+40h], xmm0
0x18001ab46  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18001ab4d  movups  xmmword ptr [rdx+50h], xmm1
0x18001ab51  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18001ab58  movups  xmmword ptr [rdx+60h], xmm0
0x18001ab5c  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18001ab63  movups  xmmword ptr [rdx+70h], xmm1
0x18001ab67  movups  xmm0, xmmword ptr [rdi+100h]
0x18001ab6e  movups  xmmword ptr [rdx+80h], xmm0
0x18001ab75  call    SymCryptHmacSha512StateCopy
0x18001ab7a  jmp     loc_18001B5F7
0x18001ab7f  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018001A7C2 case 131085
0x18001ab86  lea     rdx, [rsi+80h]
0x18001ab8d  lea     r8, [rsi+110h]
0x18001ab94  movups  xmmword ptr [rdx], xmm0
0x18001ab97  lea     rcx, [rdi+110h]
0x18001ab9e  movups  xmm1, xmmword ptr [rdi+90h]
0x18001aba5  movups  xmmword ptr [rdx+10h], xmm1
0x18001aba9  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18001abb0  movups  xmmword ptr [rdx+20h], xmm0
0x18001abb4  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18001abbb  movups  xmmword ptr [rdx+30h], xmm1
0x18001abbf  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18001abc6  movups  xmmword ptr [rdx+40h], xmm0
0x18001abca  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18001abd1  movups  xmmword ptr [rdx+50h], xmm1
0x18001abd5  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18001abdc  movups  xmmword ptr [rdx+60h], xmm0
0x18001abe0  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18001abe7  movups  xmmword ptr [rdx+70h], xmm1
0x18001abeb  movups  xmm0, xmmword ptr [rdi+100h]
0x18001abf2  movups  xmmword ptr [rdx+80h], xmm0
0x18001abf9  call    SymCryptHmacSha512StateCopy
0x18001abfe  jmp     loc_18001B5F7
0x18001ac03  lea     rdx, [rsi+80h]; jumptable 000000018001A7C2 case 131086
0x18001ac0a  lea     rcx, [rdi+80h]
0x18001ac11  call    SymCryptAesKeyCopy
0x18001ac16  movups  xmm2, xmmword ptr [rcx+1F0h]
0x18001ac1d  movdqu  xmmword ptr [rdx+1F0h], xmm2
0x18001ac25  movups  xmm3, xmmword ptr [rcx+200h]
0x18001ac2c  movdqu  xmmword ptr [rdx+200h], xmm3
0x18001ac34  movaps  xmm0, xmmword ptr [rdi+2A0h]
0x18001ac3b  movaps  xmmword ptr [rsi+2A0h], xmm0
0x18001ac42  movaps  xmm1, xmmword ptr [rdi+2B0h]
0x18001ac49  movaps  xmmword ptr [rsi+2B0h], xmm1
0x18001ac50  movaps  xmm0, xmmword ptr [rdi+2C0h]
0x18001ac57  movaps  xmmword ptr [rsi+2C0h], xmm0
0x18001ac5e  movaps  xmm1, xmmword ptr [rdi+2D0h]
0x18001ac65  movaps  xmmword ptr [rsi+2D0h], xmm1
0x18001ac6c  test    rdx, rdx
0x18001ac6f  jnz     short loc_18001AC78
0x18001ac71  mov     rdx, [rdi+2C8h]
0x18001ac78  mov     [rsi+2C8h], rdx
0x18001ac7f  jmp     loc_18001B5F7
0x18001ac84  lea     rdx, [rsi+80h]; jumptable 000000018001A7C2 case 131087
0x18001ac8b  lea     rcx, [rdi+80h]; Src
0x18001ac92  call    SymCryptSha3_256StateCopy
0x18001ac97  jmp     loc_18001B5F7
0x18001ac9c  lea     rdx, [rsi+80h]; jumptable 000000018001A7C2 case 131088
0x18001aca3  lea     rcx, [rdi+80h]; Src
0x18001acaa  call    SymCryptSha3_384StateCopy
0x18001acaf  jmp     loc_18001B5F7
0x18001acb4  lea     rdx, [rsi+80h]; jumptable 000000018001A7C2 case 131089
0x18001acbb  lea     rcx, [rdi+80h]; Src
0x18001acc2  call    SymCryptSha3_512StateCopy
0x18001acc7  jmp     loc_18001B5F7
0x18001accc  lea     rbx, [rsi+80h]; jumptable 000000018001A7C2 cases 131090-131092
0x18001acd3  mov     rdx, rbx
0x18001acd6  lea     rcx, [rdi+80h]
0x18001acdd  call    SymCryptHmacKeyCopy
0x18001ace2  lea     r8, [rsi+280h]
0x18001ace9  mov     rdx, rbx
0x18001acec  lea     rcx, [rdi+280h]
0x18001acf3  call    SymCryptHmacStateCopy
0x18001acf8  jmp     loc_18001B5F7
0x18001acfd  mov     eax, [rdi+118h]; jumptable 000000018001A7C2 case 131093
0x18001ad03  sub     eax, 2
0x18001ad06  cmp     eax, 1
0x18001ad09  ja      loc_18001ADE1
0x18001ad0f  movups  xmm0, xmmword ptr [rdi+210h]
0x18001ad16  movups  xmmword ptr [rsi+210h], xmm0
0x18001ad1d  movups  xmm1, xmmword ptr [rdi+220h]
0x18001ad24  movups  xmmword ptr [rsi+220h], xmm1
0x18001ad2b  movups  xmm0, xmmword ptr [rdi+230h]
0x18001ad32  movups  xmmword ptr [rsi+230h], xmm0
0x18001ad39  movups  xmm1, xmmword ptr [rdi+240h]
0x18001ad40  movups  xmmword ptr [rsi+240h], xmm1
0x18001ad47  movups  xmm0, xmmword ptr [rdi+250h]
0x18001ad4e  movups  xmmword ptr [rsi+250h], xmm0
0x18001ad55  movups  xmm1, xmmword ptr [rdi+260h]
0x18001ad5c  movups  xmmword ptr [rsi+260h], xmm1
0x18001ad63  movups  xmm0, xmmword ptr [rdi+270h]
0x18001ad6a  movups  xmmword ptr [rsi+270h], xmm0
0x18001ad71  movups  xmm1, xmmword ptr [rdi+280h]
0x18001ad78  movups  xmmword ptr [rsi+280h], xmm1
0x18001ad7f  movups  xmm0, xmmword ptr [rdi+290h]
0x18001ad86  movups  xmmword ptr [rsi+290h], xmm0
0x18001ad8d  movups  xmm1, xmmword ptr [rdi+2A0h]
0x18001ad94  movups  xmmword ptr [rsi+2A0h], xmm1
0x18001ad9b  movups  xmm0, xmmword ptr [rdi+2B0h]
0x18001ada2  movups  xmmword ptr [rsi+2B0h], xmm0
0x18001ada9  movups  xmm1, xmmword ptr [rdi+2C0h]
0x18001adb0  movups  xmmword ptr [rsi+2C0h], xmm1
0x18001adb7  movups  xmm0, xmmword ptr [rdi+2D0h]
0x18001adbe  movups  xmmword ptr [rsi+2D0h], xmm0
0x18001adc5  movups  xmm1, xmmword ptr [rdi+2E0h]
0x18001adcc  movups  xmmword ptr [rsi+2E0h], xmm1
0x18001add3  movups  xmm0, xmmword ptr [rdi+2F0h]
0x18001adda  movups  xmmword ptr [rsi+2F0h], xmm0
0x18001ade1  cmp     [rdi+118h], r12d
0x18001ade8  jz      loc_18001AEC0
0x18001adee  movups  xmm0, xmmword ptr [rdi+120h]
0x18001adf5  movups  xmmword ptr [rsi+120h], xmm0
0x18001adfc  movups  xmm1, xmmword ptr [rdi+130h]
0x18001ae03  movups  xmmword ptr [rsi+130h], xmm1
0x18001ae0a  movups  xmm0, xmmword ptr [rdi+140h]
  ... truncated ...
```

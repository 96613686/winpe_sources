# MSCryptDuplicateHash

- ea: `0x180010600`
- end: `0x1800115c7`
- name: `MSCryptDuplicateHash`
- size: `4039`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180010528`
- `0x180010600`
- `0x180011f00`
- `0x18001ac70`
- `0x18003a218`
- `0x180047f94`
- `0x180064984`
- `0x18007c680`
- `0x1800926b0`
- `0x180097330`
- `0x180097450`
- `0x18009da40`

## string_xrefs

- `0x180011568`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800115a2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptDuplicateHash(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // r9
  const void **v8; // rax
  unsigned int v9; // r9d
  const void **v10; // rdi
  size_t v11; // rax
  int v12; // ebx
  int v13; // edx
  _OWORD *v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx

  if ( a5 )
  {
    v7 = 3090;
    goto LABEL_64;
  }
  v8 = (const void **)validateMSCryptHash(a1, a2);
  v10 = v8;
  if ( !v8 )
  {
    v7 = 3099;
    goto LABEL_64;
  }
  if ( !a2 || !a3 || *((_DWORD *)v8 + 9) )
  {
    v7 = 3108;
LABEL_64:
    v12 = -1073741811;
    v17 = 3221225485LL;
LABEL_65:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v7);
    return (unsigned int)v12;
  }
  v11 = *(unsigned int *)v8;
  if ( v9 >= (unsigned int)v11 )
  {
    memmove((void *)a3, v10, v11);
    switch ( *((_DWORD *)v10 + 2) )
    {
      case 0x20001:
      case 0x20003:
      case 0x20004:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        goto LABEL_59;
      case 0x20002:
      case 0x20005:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
        goto LABEL_59;
      case 0x20006:
      case 0x20007:
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
        goto LABEL_59;
      case 0x20008:
        SymCryptGcmExpandKey(a3 + 128, v10[272], v10 + 337, v10[336]);
        if ( *((_DWORD *)v10 + 29) )
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
        goto LABEL_59;
      case 0x20009:
      case 0x2000B:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        SymCryptHmacSha1StateCopy(v10 + 26, a3 + 128, a3 + 208);
        goto LABEL_59;
      case 0x2000A:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        SymCryptHmacMd5StateCopy(v10 + 22, a3 + 128, a3 + 176);
        goto LABEL_59;
      case 0x2000C:
      case 0x2000D:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v10 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v10 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v10 + 15);
        *(_OWORD *)(a3 + 256) = *((_OWORD *)v10 + 16);
        SymCryptHmacSha512StateCopy(v10 + 34, a3 + 128, a3 + 272);
        goto LABEL_59;
      case 0x2000E:
        SymCryptAesKeyCopy(v10 + 16, a3 + 128);
        v14[31] = *(_OWORD *)(v15 + 496);
        v14[32] = *(_OWORD *)(v15 + 512);
        *(_OWORD *)(a3 + 672) = *((_OWORD *)v10 + 42);
        *(_OWORD *)(a3 + 688) = *((_OWORD *)v10 + 43);
        *(_OWORD *)(a3 + 704) = *((_OWORD *)v10 + 44);
        *(_OWORD *)(a3 + 720) = *((_OWORD *)v10 + 45);
        if ( !v14 )
          v14 = v10[89];
        *(_QWORD *)(a3 + 712) = v14;
        goto LABEL_59;
      case 0x2000F:
      case 0x20010:
      case 0x20011:
      case 0x20019:
      case 0x2001A:
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
        goto LABEL_59;
      case 0x20012:
      case 0x20013:
      case 0x20014:
        SymCryptHmacKeyCopy(v10 + 16, a3 + 128);
        SymCryptHmacStateCopy(v10 + 80, a3 + 128, a3 + 640);
        goto LABEL_59;
      case 0x20015:
        if ( (unsigned int)(*((_DWORD *)v10 + 70) - 2) <= 1 )
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
        if ( *((_DWORD *)v10 + 70) )
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
        v16 = MSCryptCustomBufferUpdate(a3 + 120, v10[23], *((_DWORD *)v10 + 48));
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3335;
          goto LABEL_30;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, v10[33], *((_DWORD *)v10 + 68));
        if ( v12 >= 0 )
          goto LABEL_59;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3343;
        goto LABEL_33;
      case 0x20016:
        if ( (unsigned int)(*((_DWORD *)v10 + 70) - 2) <= 1 )
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
        if ( *((_DWORD *)v10 + 70) )
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
        v16 = MSCryptCustomBufferUpdate(a3 + 120, v10[23], *((_DWORD *)v10 + 48));
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3374;
          goto LABEL_30;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, v10[33], *((_DWORD *)v10 + 68));
        if ( v12 >= 0 )
          goto LABEL_59;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3382;
LABEL_33:
        v17 = (unsigned int)v12;
        goto LABEL_65;
      case 0x20017:
        if ( *((_DWORD *)v10 + 132) )
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
        if ( (unsigned int)(*((_DWORD *)v10 + 132) - 2) <= 1 )
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
        v16 = MSCryptCustomBufferUpdate(a3 + 368, v10[54], *((_DWORD *)v10 + 110));
        v12 = v16;
        if ( v16 < 0 )
        {
          v7 = 3409;
          goto LABEL_30;
        }
        *(_QWORD *)(a3 + 512) = 0;
        *(_DWORD *)(a3 + 520) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 448, v10[64], *((_DWORD *)v10 + 130));
        v12 = v16;
        if ( v16 >= 0 )
          goto LABEL_59;
        v7 = 3417;
        goto LABEL_30;
      case 0x20018:
        if ( *((_DWORD *)v10 + 132) )
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
        if ( (unsigned int)(*((_DWORD *)v10 + 132) - 2) <= 1 )
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
        v16 = MSCryptCustomBufferUpdate(a3 + 368, v10[54], *((_DWORD *)v10 + 110));
        v12 = v16;
        if ( v16 >= 0 )
        {
          *(_QWORD *)(a3 + 512) = 0;
          *(_DWORD *)(a3 + 520) = 0;
          v16 = MSCryptCustomBufferUpdate(a3 + 448, v10[64], *((_DWORD *)v10 + 130));
          v12 = v16;
          if ( v16 >= 0 )
          {
LABEL_59:
            *a2 = a3;
            return 0;
          }
          v7 = 3452;
        }
        else
        {
          v7 = 3444;
        }
LABEL_30:
        v17 = (unsigned int)v16;
        goto LABEL_65;
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
0x180010600  push    rbx
0x180010602  push    rbp
0x180010603  push    rsi
0x180010604  push    rdi
0x180010605  push    r12
0x180010607  push    r14
0x180010609  push    r15
0x18001060b  sub     rsp, 40h
0x18001060f  xor     r12d, r12d
0x180010612  mov     rsi, r8
0x180010615  mov     r15, rdx
0x180010618  cmp     [rsp+78h+arg_20], r12d
0x180010620  jz      short loc_18001062D
0x180010622  mov     r9d, 0C12h
0x180010628  jmp     loc_180011598
0x18001062d  call    validateMSCryptHash
0x180010632  mov     rdi, rax
0x180010635  test    rax, rax
0x180010638  jnz     short loc_180010645
0x18001063a  mov     r9d, 0C1Bh
0x180010640  jmp     loc_180011598
0x180010645  test    r15, r15
0x180010648  jz      loc_180011592
0x18001064e  test    rsi, rsi
0x180010651  jz      loc_180011592
0x180010657  cmp     [rax+24h], r12d
0x18001065b  jnz     loc_180011592
0x180010661  mov     eax, [rax]
0x180010663  cmp     r9d, eax
0x180010666  jnb     short loc_180010672
0x180010668  mov     ebx, 0C0000023h
0x18001066d  jmp     loc_1800115B5
0x180010672  mov     r8, rax; Size
0x180010675  mov     rdx, rdi; Src
0x180010678  mov     rcx, rsi; void *
0x18001067b  call    memmove
0x180010680  mov     eax, [rdi+8]
0x180010683  add     eax, 0FFFDFFFFh; switch 26 cases
0x180010688  cmp     eax, 19h
0x18001068b  ja      def_1800106A2; jumptable 00000001800106A2 default case
0x180010691  lea     rcx, cs:180000000h
0x180010698  mov     eax, ds:(jpt_1800106A2 - 180000000h)[rcx+rax*4]
0x18001069f  add     rax, rcx
0x1800106a2  jmp     rax; switch jump
0x1800106a8  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 cases 131073,131075,131076
0x1800106af  movaps  xmmword ptr [rsi+80h], xmm0
0x1800106b6  movaps  xmm1, xmmword ptr [rdi+90h]
0x1800106bd  movaps  xmmword ptr [rsi+90h], xmm1
0x1800106c4  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x1800106cb  movaps  xmmword ptr [rsi+0A0h], xmm0
0x1800106d2  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x1800106d9  movaps  xmmword ptr [rsi+0B0h], xmm1
0x1800106e0  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x1800106e7  movaps  xmmword ptr [rsi+0C0h], xmm0
0x1800106ee  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x1800106f5  movaps  xmmword ptr [rsi+0D0h], xmm1
0x1800106fc  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x180010703  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18001070a  jmp     loc_18001153D
0x18001070f  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 cases 131074,131077
0x180010716  movaps  xmmword ptr [rsi+80h], xmm0
0x18001071d  movaps  xmm1, xmmword ptr [rdi+90h]
0x180010724  movaps  xmmword ptr [rsi+90h], xmm1
0x18001072b  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x180010732  movaps  xmmword ptr [rsi+0A0h], xmm0
0x180010739  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x180010740  movaps  xmmword ptr [rsi+0B0h], xmm1
0x180010747  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18001074e  movaps  xmmword ptr [rsi+0C0h], xmm0
0x180010755  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18001075c  movaps  xmmword ptr [rsi+0D0h], xmm1
0x180010763  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18001076a  movaps  xmmword ptr [rsi+0E0h], xmm0
0x180010771  movaps  xmm1, xmmword ptr [rdi+0F0h]
0x180010778  movaps  xmmword ptr [rsi+0F0h], xmm1
0x18001077f  jmp     loc_18001153D
0x180010784  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 cases 131078,131079
0x18001078b  movups  xmmword ptr [rsi+80h], xmm0
0x180010792  movups  xmm1, xmmword ptr [rdi+90h]
0x180010799  movups  xmmword ptr [rsi+90h], xmm1
0x1800107a0  movups  xmm0, xmmword ptr [rdi+0A0h]
0x1800107a7  movups  xmmword ptr [rsi+0A0h], xmm0
0x1800107ae  movups  xmm1, xmmword ptr [rdi+0B0h]
0x1800107b5  movups  xmmword ptr [rsi+0B0h], xmm1
0x1800107bc  movups  xmm0, xmmword ptr [rdi+0C0h]
0x1800107c3  movups  xmmword ptr [rsi+0C0h], xmm0
0x1800107ca  movups  xmm1, xmmword ptr [rdi+0D0h]
0x1800107d1  movups  xmmword ptr [rsi+0D0h], xmm1
0x1800107d8  movups  xmm0, xmmword ptr [rdi+0E0h]
0x1800107df  movups  xmmword ptr [rsi+0E0h], xmm0
0x1800107e6  movups  xmm1, xmmword ptr [rdi+0F0h]
0x1800107ed  movups  xmmword ptr [rsi+0F0h], xmm1
0x1800107f4  movups  xmm0, xmmword ptr [rdi+100h]
0x1800107fb  movups  xmmword ptr [rsi+100h], xmm0
0x180010802  movups  xmm1, xmmword ptr [rdi+110h]
0x180010809  movups  xmmword ptr [rsi+110h], xmm1
0x180010810  movups  xmm0, xmmword ptr [rdi+120h]
0x180010817  movups  xmmword ptr [rsi+120h], xmm0
0x18001081e  movups  xmm1, xmmword ptr [rdi+130h]
0x180010825  movups  xmmword ptr [rsi+130h], xmm1
0x18001082c  movups  xmm0, xmmword ptr [rdi+140h]
0x180010833  movups  xmmword ptr [rsi+140h], xmm0
0x18001083a  movups  xmm1, xmmword ptr [rdi+150h]
0x180010841  movups  xmmword ptr [rsi+150h], xmm1
0x180010848  jmp     loc_18001153D
0x18001084d  mov     r9, [rdi+0A80h]; jumptable 00000001800106A2 case 131080
0x180010854  lea     rbx, [rsi+80h]
0x18001085b  mov     rdx, [rdi+880h]
0x180010862  lea     r8, [rdi+0A88h]
0x180010869  mov     rcx, rbx
0x18001086c  call    SymCryptGcmExpandKey
0x180010871  cmp     [rdi+74h], r12d
0x180010875  jz      loc_18001153D
0x18001087b  movaps  xmm0, xmmword ptr [rdi+0AB0h]
0x180010882  movaps  xmmword ptr [rsi+0AB0h], xmm0
0x180010889  movaps  xmm1, xmmword ptr [rdi+0AC0h]
0x180010890  movaps  xmmword ptr [rsi+0AC0h], xmm1
0x180010897  movaps  xmm0, xmmword ptr [rdi+0AD0h]
0x18001089e  movaps  xmmword ptr [rsi+0AD0h], xmm0
0x1800108a5  movaps  xmm1, xmmword ptr [rdi+0AE0h]
0x1800108ac  movaps  xmmword ptr [rsi+0AE0h], xmm1
0x1800108b3  movaps  xmm0, xmmword ptr [rdi+0AF0h]
0x1800108ba  movaps  xmmword ptr [rsi+0AF0h], xmm0
0x1800108c1  movaps  xmm1, xmmword ptr [rdi+0B00h]
0x1800108c8  movaps  xmmword ptr [rsi+0B00h], xmm1
0x1800108cf  movaps  xmm0, xmmword ptr [rdi+0B10h]
0x1800108d6  movaps  xmmword ptr [rsi+0B10h], xmm0
0x1800108dd  test    rbx, rbx
0x1800108e0  jz      loc_18001153D
0x1800108e6  mov     [rsi+0AB0h], rbx
0x1800108ed  jmp     loc_18001153D
0x1800108f2  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 case 131081
0x1800108f9  lea     rdx, [rsi+80h]
0x180010900  movaps  xmmword ptr [rdx], xmm0
0x180010903  lea     r8, [rsi+0D0h]
0x18001090a  movaps  xmm1, xmmword ptr [rdi+90h]
0x180010911  lea     rcx, [rdi+0D0h]
0x180010918  movaps  xmmword ptr [rdx+10h], xmm1
0x18001091c  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x180010923  movaps  xmmword ptr [rdx+20h], xmm0
0x180010927  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18001092e  movaps  xmmword ptr [rdx+30h], xmm1
0x180010932  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x180010939  movaps  xmmword ptr [rdx+40h], xmm0
0x18001093d  call    SymCryptHmacSha1StateCopy
0x180010942  jmp     loc_18001153D
0x180010947  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 case 131082
0x18001094e  lea     rdx, [rsi+80h]
0x180010955  movaps  xmmword ptr [rdx], xmm0
0x180010958  lea     r8, [rsi+0B0h]
0x18001095f  movaps  xmm1, xmmword ptr [rdi+90h]
0x180010966  lea     rcx, [rdi+0B0h]
0x18001096d  movaps  xmmword ptr [rdx+10h], xmm1
0x180010971  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x180010978  movaps  xmmword ptr [rdx+20h], xmm0
0x18001097c  call    SymCryptHmacMd5StateCopy
0x180010981  jmp     loc_18001153D
0x180010986  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 case 131083
0x18001098d  lea     rdx, [rsi+80h]
0x180010994  movaps  xmmword ptr [rdx], xmm0
0x180010997  lea     r8, [rsi+0D0h]
0x18001099e  movaps  xmm1, xmmword ptr [rdi+90h]
0x1800109a5  lea     rcx, [rdi+0D0h]
0x1800109ac  movaps  xmmword ptr [rdx+10h], xmm1
0x1800109b0  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x1800109b7  movaps  xmmword ptr [rdx+20h], xmm0
0x1800109bb  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x1800109c2  movaps  xmmword ptr [rdx+30h], xmm1
0x1800109c6  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x1800109cd  movaps  xmmword ptr [rdx+40h], xmm0
0x1800109d1  call    SymCryptHmacSha1StateCopy
0x1800109d6  jmp     loc_18001153D
0x1800109db  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 case 131084
0x1800109e2  lea     rdx, [rsi+80h]
0x1800109e9  lea     r8, [rsi+110h]
0x1800109f0  movups  xmmword ptr [rdx], xmm0
0x1800109f3  lea     rcx, [rdi+110h]
0x1800109fa  movups  xmm1, xmmword ptr [rdi+90h]
0x180010a01  movups  xmmword ptr [rdx+10h], xmm1
0x180010a05  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180010a0c  movups  xmmword ptr [rdx+20h], xmm0
0x180010a10  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180010a17  movups  xmmword ptr [rdx+30h], xmm1
0x180010a1b  movups  xmm0, xmmword ptr [rdi+0C0h]
0x180010a22  movups  xmmword ptr [rdx+40h], xmm0
0x180010a26  movups  xmm1, xmmword ptr [rdi+0D0h]
0x180010a2d  movups  xmmword ptr [rdx+50h], xmm1
0x180010a31  movups  xmm0, xmmword ptr [rdi+0E0h]
0x180010a38  movups  xmmword ptr [rdx+60h], xmm0
0x180010a3c  movups  xmm1, xmmword ptr [rdi+0F0h]
0x180010a43  movups  xmmword ptr [rdx+70h], xmm1
0x180010a47  movups  xmm0, xmmword ptr [rdi+100h]
0x180010a4e  movups  xmmword ptr [rdx+80h], xmm0
0x180010a55  call    SymCryptHmacSha512StateCopy
0x180010a5a  jmp     loc_18001153D
0x180010a5f  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 00000001800106A2 case 131085
0x180010a66  lea     rdx, [rsi+80h]
0x180010a6d  lea     r8, [rsi+110h]
0x180010a74  movups  xmmword ptr [rdx], xmm0
0x180010a77  lea     rcx, [rdi+110h]
0x180010a7e  movups  xmm1, xmmword ptr [rdi+90h]
0x180010a85  movups  xmmword ptr [rdx+10h], xmm1
0x180010a89  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180010a90  movups  xmmword ptr [rdx+20h], xmm0
0x180010a94  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180010a9b  movups  xmmword ptr [rdx+30h], xmm1
0x180010a9f  movups  xmm0, xmmword ptr [rdi+0C0h]
0x180010aa6  movups  xmmword ptr [rdx+40h], xmm0
0x180010aaa  movups  xmm1, xmmword ptr [rdi+0D0h]
0x180010ab1  movups  xmmword ptr [rdx+50h], xmm1
0x180010ab5  movups  xmm0, xmmword ptr [rdi+0E0h]
0x180010abc  movups  xmmword ptr [rdx+60h], xmm0
0x180010ac0  movups  xmm1, xmmword ptr [rdi+0F0h]
0x180010ac7  movups  xmmword ptr [rdx+70h], xmm1
0x180010acb  movups  xmm0, xmmword ptr [rdi+100h]
0x180010ad2  movups  xmmword ptr [rdx+80h], xmm0
0x180010ad9  call    SymCryptHmacSha512StateCopy
0x180010ade  jmp     loc_18001153D
0x180010ae3  lea     rdx, [rsi+80h]; jumptable 00000001800106A2 case 131086
0x180010aea  lea     rcx, [rdi+80h]
0x180010af1  call    SymCryptAesKeyCopy
0x180010af6  movups  xmm2, xmmword ptr [rcx+1F0h]
0x180010afd  movdqu  xmmword ptr [rdx+1F0h], xmm2
0x180010b05  movups  xmm3, xmmword ptr [rcx+200h]
0x180010b0c  movdqu  xmmword ptr [rdx+200h], xmm3
0x180010b14  movaps  xmm0, xmmword ptr [rdi+2A0h]
0x180010b1b  movaps  xmmword ptr [rsi+2A0h], xmm0
0x180010b22  movaps  xmm1, xmmword ptr [rdi+2B0h]
0x180010b29  movaps  xmmword ptr [rsi+2B0h], xmm1
0x180010b30  movaps  xmm0, xmmword ptr [rdi+2C0h]
0x180010b37  movaps  xmmword ptr [rsi+2C0h], xmm0
0x180010b3e  movaps  xmm1, xmmword ptr [rdi+2D0h]
0x180010b45  movaps  xmmword ptr [rsi+2D0h], xmm1
0x180010b4c  test    rdx, rdx
0x180010b4f  jnz     short loc_180010B58
0x180010b51  mov     rdx, [rdi+2C8h]
0x180010b58  mov     [rsi+2C8h], rdx
0x180010b5f  jmp     loc_18001153D
0x180010b64  lea     rbx, [rsi+80h]; jumptable 00000001800106A2 cases 131090-131092
0x180010b6b  mov     rdx, rbx
0x180010b6e  lea     rcx, [rdi+80h]
0x180010b75  call    SymCryptHmacKeyCopy
0x180010b7a  lea     r8, [rsi+280h]
0x180010b81  mov     rdx, rbx
0x180010b84  lea     rcx, [rdi+280h]
0x180010b8b  call    SymCryptHmacStateCopy
0x180010b90  jmp     loc_18001153D
0x180010b95  mov     eax, [rdi+118h]; jumptable 00000001800106A2 case 131093
0x180010b9b  sub     eax, 2
0x180010b9e  cmp     eax, 1
0x180010ba1  ja      loc_180010C79
0x180010ba7  movups  xmm0, xmmword ptr [rdi+210h]
0x180010bae  movups  xmmword ptr [rsi+210h], xmm0
0x180010bb5  movups  xmm1, xmmword ptr [rdi+220h]
0x180010bbc  movups  xmmword ptr [rsi+220h], xmm1
0x180010bc3  movups  xmm0, xmmword ptr [rdi+230h]
0x180010bca  movups  xmmword ptr [rsi+230h], xmm0
0x180010bd1  movups  xmm1, xmmword ptr [rdi+240h]
0x180010bd8  movups  xmmword ptr [rsi+240h], xmm1
0x180010bdf  movups  xmm0, xmmword ptr [rdi+250h]
0x180010be6  movups  xmmword ptr [rsi+250h], xmm0
0x180010bed  movups  xmm1, xmmword ptr [rdi+260h]
0x180010bf4  movups  xmmword ptr [rsi+260h], xmm1
0x180010bfb  movups  xmm0, xmmword ptr [rdi+270h]
0x180010c02  movups  xmmword ptr [rsi+270h], xmm0
0x180010c09  movups  xmm1, xmmword ptr [rdi+280h]
0x180010c10  movups  xmmword ptr [rsi+280h], xmm1
0x180010c17  movups  xmm0, xmmword ptr [rdi+290h]
0x180010c1e  movups  xmmword ptr [rsi+290h], xmm0
0x180010c25  movups  xmm1, xmmword ptr [rdi+2A0h]
0x180010c2c  movups  xmmword ptr [rsi+2A0h], xmm1
0x180010c33  movups  xmm0, xmmword ptr [rdi+2B0h]
0x180010c3a  movups  xmmword ptr [rsi+2B0h], xmm0
0x180010c41  movups  xmm1, xmmword ptr [rdi+2C0h]
0x180010c48  movups  xmmword ptr [rsi+2C0h], xmm1
0x180010c4f  movups  xmm0, xmmword ptr [rdi+2D0h]
0x180010c56  movups  xmmword ptr [rsi+2D0h], xmm0
0x180010c5d  movups  xmm1, xmmword ptr [rdi+2E0h]
0x180010c64  movups  xmmword ptr [rsi+2E0h], xmm1
0x180010c6b  movups  xmm0, xmmword ptr [rdi+2F0h]
0x180010c72  movups  xmmword ptr [rsi+2F0h], xmm0
0x180010c79  cmp     [rdi+118h], r12d
0x180010c80  jz      loc_180010D58
0x180010c86  movups  xmm0, xmmword ptr [rdi+120h]
0x180010c8d  movups  xmmword ptr [rsi+120h], xmm0
0x180010c94  movups  xmm1, xmmword ptr [rdi+130h]
0x180010c9b  movups  xmmword ptr [rsi+130h], xmm1
0x180010ca2  movups  xmm0, xmmword ptr [rdi+140h]
0x180010ca9  movups  xmmword ptr [rsi+140h], xmm0
0x180010cb0  movups  xmm1, xmmword ptr [rdi+150h]
0x180010cb7  movups  xmmword ptr [rsi+150h], xmm1
0x180010cbe  movups  xmm0, xmmword ptr [rdi+160h]
0x180010cc5  movups  xmmword ptr [rsi+160h], xmm0
0x180010ccc  movups  xmm1, xmmword ptr [rdi+170h]
0x180010cd3  movups  xmmword ptr [rsi+170h], xmm1
0x180010cda  movups  xmm0, xmmword ptr [rdi+180h]
0x180010ce1  movups  xmmword ptr [rsi+180h], xmm0
0x180010ce8  movups  xmm1, xmmword ptr [rdi+190h]
0x180010cef  movups  xmmword ptr [rsi+190h], xmm1
0x180010cf6  movups  xmm0, xmmword ptr [rdi+1A0h]
  ... truncated ...
```

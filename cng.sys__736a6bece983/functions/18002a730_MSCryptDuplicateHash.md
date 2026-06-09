# MSCryptDuplicateHash

- ea: `0x18002a730`
- end: `0x18002b6f7`
- name: `MSCryptDuplicateHash`
- size: `4039`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180017d20`
- `0x18002a658`
- `0x18002a730`
- `0x18002bb40`
- `0x18003ad18`
- `0x180048a24`
- `0x180065304`
- `0x18007d670`
- `0x180094110`
- `0x180098d90`
- `0x180098eb0`
- `0x18009f780`

## string_xrefs

- `0x18002b698`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18002b6d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
    goto LABEL_64;
  }
  v8 = (unsigned int *)validateMSCryptHash(a1, a2);
  v10 = v8;
  if ( !v8 )
  {
    v7 = 3099;
    goto LABEL_64;
  }
  if ( !a2 || !a3 || v8[9] )
  {
    v7 = 3108;
LABEL_64:
    v12 = -1073741811;
    v17 = 3221225485LL;
LABEL_65:
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
        goto LABEL_59;
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
        goto LABEL_59;
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
        goto LABEL_59;
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
        goto LABEL_59;
      case 0x20009u:
      case 0x2000Bu:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v10 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v10 + 12);
        SymCryptHmacSha1StateCopy(v10 + 52, a3 + 128, a3 + 208);
        goto LABEL_59;
      case 0x2000Au:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v10 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v10 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v10 + 10);
        SymCryptHmacMd5StateCopy(v10 + 44, a3 + 128, a3 + 176);
        goto LABEL_59;
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
        goto LABEL_59;
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
        goto LABEL_59;
      case 0x2000Fu:
      case 0x20010u:
      case 0x20011u:
      case 0x20019u:
      case 0x2001Au:
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
      case 0x20012u:
      case 0x20013u:
      case 0x20014u:
        SymCryptHmacKeyCopy(v10 + 32, a3 + 128);
        SymCryptHmacStateCopy(v10 + 160, a3 + 128, a3 + 640);
        goto LABEL_59;
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
          goto LABEL_30;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v10 + 33), v10[68]);
        if ( v12 >= 0 )
          goto LABEL_59;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3343;
        goto LABEL_33;
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
          goto LABEL_30;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v10 + 33), v10[68]);
        if ( v12 >= 0 )
          goto LABEL_59;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3382;
LABEL_33:
        v17 = (unsigned int)v12;
        goto LABEL_65;
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
          goto LABEL_30;
        }
        *(_QWORD *)(a3 + 512) = 0;
        *(_DWORD *)(a3 + 520) = 0;
        v16 = MSCryptCustomBufferUpdate(a3 + 448, *((_QWORD *)v10 + 64), v10[130]);
        v12 = v16;
        if ( v16 >= 0 )
          goto LABEL_59;
        v7 = 3417;
        goto LABEL_30;
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
0x18002a730  push    rbx
0x18002a732  push    rbp
0x18002a733  push    rsi
0x18002a734  push    rdi
0x18002a735  push    r12
0x18002a737  push    r14
0x18002a739  push    r15
0x18002a73b  sub     rsp, 40h
0x18002a73f  xor     r12d, r12d
0x18002a742  mov     rsi, r8
0x18002a745  mov     r15, rdx
0x18002a748  cmp     [rsp+78h+arg_20], r12d
0x18002a750  jz      short loc_18002A75D
0x18002a752  mov     r9d, 0C12h
0x18002a758  jmp     loc_18002B6C8
0x18002a75d  call    validateMSCryptHash
0x18002a762  mov     rdi, rax
0x18002a765  test    rax, rax
0x18002a768  jnz     short loc_18002A775
0x18002a76a  mov     r9d, 0C1Bh
0x18002a770  jmp     loc_18002B6C8
0x18002a775  test    r15, r15
0x18002a778  jz      loc_18002B6C2
0x18002a77e  test    rsi, rsi
0x18002a781  jz      loc_18002B6C2
0x18002a787  cmp     [rax+24h], r12d
0x18002a78b  jnz     loc_18002B6C2
0x18002a791  mov     eax, [rax]
0x18002a793  cmp     r9d, eax
0x18002a796  jnb     short loc_18002A7A2
0x18002a798  mov     ebx, 0C0000023h
0x18002a79d  jmp     loc_18002B6E5
0x18002a7a2  mov     r8, rax; Size
0x18002a7a5  mov     rdx, rdi; Src
0x18002a7a8  mov     rcx, rsi; void *
0x18002a7ab  call    memmove
0x18002a7b0  mov     eax, [rdi+8]
0x18002a7b3  add     eax, 0FFFDFFFFh; switch 26 cases
0x18002a7b8  cmp     eax, 19h
0x18002a7bb  ja      def_18002A7D2; jumptable 000000018002A7D2 default case
0x18002a7c1  lea     rcx, cs:180000000h
0x18002a7c8  mov     eax, ds:(jpt_18002A7D2 - 180000000h)[rcx+rax*4]
0x18002a7cf  add     rax, rcx
0x18002a7d2  jmp     rax; switch jump
0x18002a7d8  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 cases 131073,131075,131076
0x18002a7df  movaps  xmmword ptr [rsi+80h], xmm0
0x18002a7e6  movaps  xmm1, xmmword ptr [rdi+90h]
0x18002a7ed  movaps  xmmword ptr [rsi+90h], xmm1
0x18002a7f4  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18002a7fb  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18002a802  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18002a809  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18002a810  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18002a817  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18002a81e  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18002a825  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18002a82c  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18002a833  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18002a83a  jmp     loc_18002B66D
0x18002a83f  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 cases 131074,131077
0x18002a846  movaps  xmmword ptr [rsi+80h], xmm0
0x18002a84d  movaps  xmm1, xmmword ptr [rdi+90h]
0x18002a854  movaps  xmmword ptr [rsi+90h], xmm1
0x18002a85b  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18002a862  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18002a869  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18002a870  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18002a877  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18002a87e  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18002a885  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18002a88c  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18002a893  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18002a89a  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18002a8a1  movaps  xmm1, xmmword ptr [rdi+0F0h]
0x18002a8a8  movaps  xmmword ptr [rsi+0F0h], xmm1
0x18002a8af  jmp     loc_18002B66D
0x18002a8b4  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 cases 131078,131079
0x18002a8bb  movups  xmmword ptr [rsi+80h], xmm0
0x18002a8c2  movups  xmm1, xmmword ptr [rdi+90h]
0x18002a8c9  movups  xmmword ptr [rsi+90h], xmm1
0x18002a8d0  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18002a8d7  movups  xmmword ptr [rsi+0A0h], xmm0
0x18002a8de  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18002a8e5  movups  xmmword ptr [rsi+0B0h], xmm1
0x18002a8ec  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18002a8f3  movups  xmmword ptr [rsi+0C0h], xmm0
0x18002a8fa  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18002a901  movups  xmmword ptr [rsi+0D0h], xmm1
0x18002a908  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18002a90f  movups  xmmword ptr [rsi+0E0h], xmm0
0x18002a916  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18002a91d  movups  xmmword ptr [rsi+0F0h], xmm1
0x18002a924  movups  xmm0, xmmword ptr [rdi+100h]
0x18002a92b  movups  xmmword ptr [rsi+100h], xmm0
0x18002a932  movups  xmm1, xmmword ptr [rdi+110h]
0x18002a939  movups  xmmword ptr [rsi+110h], xmm1
0x18002a940  movups  xmm0, xmmword ptr [rdi+120h]
0x18002a947  movups  xmmword ptr [rsi+120h], xmm0
0x18002a94e  movups  xmm1, xmmword ptr [rdi+130h]
0x18002a955  movups  xmmword ptr [rsi+130h], xmm1
0x18002a95c  movups  xmm0, xmmword ptr [rdi+140h]
0x18002a963  movups  xmmword ptr [rsi+140h], xmm0
0x18002a96a  movups  xmm1, xmmword ptr [rdi+150h]
0x18002a971  movups  xmmword ptr [rsi+150h], xmm1
0x18002a978  jmp     loc_18002B66D
0x18002a97d  mov     r9, [rdi+0A80h]; jumptable 000000018002A7D2 case 131080
0x18002a984  lea     rbx, [rsi+80h]
0x18002a98b  mov     rdx, [rdi+880h]
0x18002a992  lea     r8, [rdi+0A88h]
0x18002a999  mov     rcx, rbx
0x18002a99c  call    SymCryptGcmExpandKey
0x18002a9a1  cmp     [rdi+74h], r12d
0x18002a9a5  jz      loc_18002B66D
0x18002a9ab  movaps  xmm0, xmmword ptr [rdi+0AB0h]
0x18002a9b2  movaps  xmmword ptr [rsi+0AB0h], xmm0
0x18002a9b9  movaps  xmm1, xmmword ptr [rdi+0AC0h]
0x18002a9c0  movaps  xmmword ptr [rsi+0AC0h], xmm1
0x18002a9c7  movaps  xmm0, xmmword ptr [rdi+0AD0h]
0x18002a9ce  movaps  xmmword ptr [rsi+0AD0h], xmm0
0x18002a9d5  movaps  xmm1, xmmword ptr [rdi+0AE0h]
0x18002a9dc  movaps  xmmword ptr [rsi+0AE0h], xmm1
0x18002a9e3  movaps  xmm0, xmmword ptr [rdi+0AF0h]
0x18002a9ea  movaps  xmmword ptr [rsi+0AF0h], xmm0
0x18002a9f1  movaps  xmm1, xmmword ptr [rdi+0B00h]
0x18002a9f8  movaps  xmmword ptr [rsi+0B00h], xmm1
0x18002a9ff  movaps  xmm0, xmmword ptr [rdi+0B10h]
0x18002aa06  movaps  xmmword ptr [rsi+0B10h], xmm0
0x18002aa0d  test    rbx, rbx
0x18002aa10  jz      loc_18002B66D
0x18002aa16  mov     [rsi+0AB0h], rbx
0x18002aa1d  jmp     loc_18002B66D
0x18002aa22  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 case 131081
0x18002aa29  lea     rdx, [rsi+80h]
0x18002aa30  movaps  xmmword ptr [rdx], xmm0
0x18002aa33  lea     r8, [rsi+0D0h]
0x18002aa3a  movaps  xmm1, xmmword ptr [rdi+90h]
0x18002aa41  lea     rcx, [rdi+0D0h]
0x18002aa48  movaps  xmmword ptr [rdx+10h], xmm1
0x18002aa4c  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18002aa53  movaps  xmmword ptr [rdx+20h], xmm0
0x18002aa57  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18002aa5e  movaps  xmmword ptr [rdx+30h], xmm1
0x18002aa62  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18002aa69  movaps  xmmword ptr [rdx+40h], xmm0
0x18002aa6d  call    SymCryptHmacSha1StateCopy
0x18002aa72  jmp     loc_18002B66D
0x18002aa77  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 case 131082
0x18002aa7e  lea     rdx, [rsi+80h]
0x18002aa85  movaps  xmmword ptr [rdx], xmm0
0x18002aa88  lea     r8, [rsi+0B0h]
0x18002aa8f  movaps  xmm1, xmmword ptr [rdi+90h]
0x18002aa96  lea     rcx, [rdi+0B0h]
0x18002aa9d  movaps  xmmword ptr [rdx+10h], xmm1
0x18002aaa1  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18002aaa8  movaps  xmmword ptr [rdx+20h], xmm0
0x18002aaac  call    SymCryptHmacMd5StateCopy
0x18002aab1  jmp     loc_18002B66D
0x18002aab6  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 case 131083
0x18002aabd  lea     rdx, [rsi+80h]
0x18002aac4  movaps  xmmword ptr [rdx], xmm0
0x18002aac7  lea     r8, [rsi+0D0h]
0x18002aace  movaps  xmm1, xmmword ptr [rdi+90h]
0x18002aad5  lea     rcx, [rdi+0D0h]
0x18002aadc  movaps  xmmword ptr [rdx+10h], xmm1
0x18002aae0  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18002aae7  movaps  xmmword ptr [rdx+20h], xmm0
0x18002aaeb  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18002aaf2  movaps  xmmword ptr [rdx+30h], xmm1
0x18002aaf6  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18002aafd  movaps  xmmword ptr [rdx+40h], xmm0
0x18002ab01  call    SymCryptHmacSha1StateCopy
0x18002ab06  jmp     loc_18002B66D
0x18002ab0b  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 case 131084
0x18002ab12  lea     rdx, [rsi+80h]
0x18002ab19  lea     r8, [rsi+110h]
0x18002ab20  movups  xmmword ptr [rdx], xmm0
0x18002ab23  lea     rcx, [rdi+110h]
0x18002ab2a  movups  xmm1, xmmword ptr [rdi+90h]
0x18002ab31  movups  xmmword ptr [rdx+10h], xmm1
0x18002ab35  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18002ab3c  movups  xmmword ptr [rdx+20h], xmm0
0x18002ab40  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18002ab47  movups  xmmword ptr [rdx+30h], xmm1
0x18002ab4b  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18002ab52  movups  xmmword ptr [rdx+40h], xmm0
0x18002ab56  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18002ab5d  movups  xmmword ptr [rdx+50h], xmm1
0x18002ab61  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18002ab68  movups  xmmword ptr [rdx+60h], xmm0
0x18002ab6c  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18002ab73  movups  xmmword ptr [rdx+70h], xmm1
0x18002ab77  movups  xmm0, xmmword ptr [rdi+100h]
0x18002ab7e  movups  xmmword ptr [rdx+80h], xmm0
0x18002ab85  call    SymCryptHmacSha512StateCopy
0x18002ab8a  jmp     loc_18002B66D
0x18002ab8f  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018002A7D2 case 131085
0x18002ab96  lea     rdx, [rsi+80h]
0x18002ab9d  lea     r8, [rsi+110h]
0x18002aba4  movups  xmmword ptr [rdx], xmm0
0x18002aba7  lea     rcx, [rdi+110h]
0x18002abae  movups  xmm1, xmmword ptr [rdi+90h]
0x18002abb5  movups  xmmword ptr [rdx+10h], xmm1
0x18002abb9  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18002abc0  movups  xmmword ptr [rdx+20h], xmm0
0x18002abc4  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18002abcb  movups  xmmword ptr [rdx+30h], xmm1
0x18002abcf  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18002abd6  movups  xmmword ptr [rdx+40h], xmm0
0x18002abda  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18002abe1  movups  xmmword ptr [rdx+50h], xmm1
0x18002abe5  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18002abec  movups  xmmword ptr [rdx+60h], xmm0
0x18002abf0  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18002abf7  movups  xmmword ptr [rdx+70h], xmm1
0x18002abfb  movups  xmm0, xmmword ptr [rdi+100h]
0x18002ac02  movups  xmmword ptr [rdx+80h], xmm0
0x18002ac09  call    SymCryptHmacSha512StateCopy
0x18002ac0e  jmp     loc_18002B66D
0x18002ac13  lea     rdx, [rsi+80h]; jumptable 000000018002A7D2 case 131086
0x18002ac1a  lea     rcx, [rdi+80h]
0x18002ac21  call    SymCryptAesKeyCopy
0x18002ac26  movups  xmm2, xmmword ptr [rcx+1F0h]
0x18002ac2d  movdqu  xmmword ptr [rdx+1F0h], xmm2
0x18002ac35  movups  xmm3, xmmword ptr [rcx+200h]
0x18002ac3c  movdqu  xmmword ptr [rdx+200h], xmm3
0x18002ac44  movaps  xmm0, xmmword ptr [rdi+2A0h]
0x18002ac4b  movaps  xmmword ptr [rsi+2A0h], xmm0
0x18002ac52  movaps  xmm1, xmmword ptr [rdi+2B0h]
0x18002ac59  movaps  xmmword ptr [rsi+2B0h], xmm1
0x18002ac60  movaps  xmm0, xmmword ptr [rdi+2C0h]
0x18002ac67  movaps  xmmword ptr [rsi+2C0h], xmm0
0x18002ac6e  movaps  xmm1, xmmword ptr [rdi+2D0h]
0x18002ac75  movaps  xmmword ptr [rsi+2D0h], xmm1
0x18002ac7c  test    rdx, rdx
0x18002ac7f  jnz     short loc_18002AC88
0x18002ac81  mov     rdx, [rdi+2C8h]
0x18002ac88  mov     [rsi+2C8h], rdx
0x18002ac8f  jmp     loc_18002B66D
0x18002ac94  lea     rbx, [rsi+80h]; jumptable 000000018002A7D2 cases 131090-131092
0x18002ac9b  mov     rdx, rbx
0x18002ac9e  lea     rcx, [rdi+80h]
0x18002aca5  call    SymCryptHmacKeyCopy
0x18002acaa  lea     r8, [rsi+280h]
0x18002acb1  mov     rdx, rbx
0x18002acb4  lea     rcx, [rdi+280h]
0x18002acbb  call    SymCryptHmacStateCopy
0x18002acc0  jmp     loc_18002B66D
0x18002acc5  mov     eax, [rdi+118h]; jumptable 000000018002A7D2 case 131093
0x18002accb  sub     eax, 2
0x18002acce  cmp     eax, 1
0x18002acd1  ja      loc_18002ADA9
0x18002acd7  movups  xmm0, xmmword ptr [rdi+210h]
0x18002acde  movups  xmmword ptr [rsi+210h], xmm0
0x18002ace5  movups  xmm1, xmmword ptr [rdi+220h]
0x18002acec  movups  xmmword ptr [rsi+220h], xmm1
0x18002acf3  movups  xmm0, xmmword ptr [rdi+230h]
0x18002acfa  movups  xmmword ptr [rsi+230h], xmm0
0x18002ad01  movups  xmm1, xmmword ptr [rdi+240h]
0x18002ad08  movups  xmmword ptr [rsi+240h], xmm1
0x18002ad0f  movups  xmm0, xmmword ptr [rdi+250h]
0x18002ad16  movups  xmmword ptr [rsi+250h], xmm0
0x18002ad1d  movups  xmm1, xmmword ptr [rdi+260h]
0x18002ad24  movups  xmmword ptr [rsi+260h], xmm1
0x18002ad2b  movups  xmm0, xmmword ptr [rdi+270h]
0x18002ad32  movups  xmmword ptr [rsi+270h], xmm0
0x18002ad39  movups  xmm1, xmmword ptr [rdi+280h]
0x18002ad40  movups  xmmword ptr [rsi+280h], xmm1
0x18002ad47  movups  xmm0, xmmword ptr [rdi+290h]
0x18002ad4e  movups  xmmword ptr [rsi+290h], xmm0
0x18002ad55  movups  xmm1, xmmword ptr [rdi+2A0h]
0x18002ad5c  movups  xmmword ptr [rsi+2A0h], xmm1
0x18002ad63  movups  xmm0, xmmword ptr [rdi+2B0h]
0x18002ad6a  movups  xmmword ptr [rsi+2B0h], xmm0
0x18002ad71  movups  xmm1, xmmword ptr [rdi+2C0h]
0x18002ad78  movups  xmmword ptr [rsi+2C0h], xmm1
0x18002ad7f  movups  xmm0, xmmword ptr [rdi+2D0h]
0x18002ad86  movups  xmmword ptr [rsi+2D0h], xmm0
0x18002ad8d  movups  xmm1, xmmword ptr [rdi+2E0h]
0x18002ad94  movups  xmmword ptr [rsi+2E0h], xmm1
0x18002ad9b  movups  xmm0, xmmword ptr [rdi+2F0h]
0x18002ada2  movups  xmmword ptr [rsi+2F0h], xmm0
0x18002ada9  cmp     [rdi+118h], r12d
0x18002adb0  jz      loc_18002AE88
0x18002adb6  movups  xmm0, xmmword ptr [rdi+120h]
0x18002adbd  movups  xmmword ptr [rsi+120h], xmm0
0x18002adc4  movups  xmm1, xmmword ptr [rdi+130h]
0x18002adcb  movups  xmmword ptr [rsi+130h], xmm1
0x18002add2  movups  xmm0, xmmword ptr [rdi+140h]
0x18002add9  movups  xmmword ptr [rsi+140h], xmm0
0x18002ade0  movups  xmm1, xmmword ptr [rdi+150h]
0x18002ade7  movups  xmmword ptr [rsi+150h], xmm1
0x18002adee  movups  xmm0, xmmword ptr [rdi+160h]
0x18002adf5  movups  xmmword ptr [rsi+160h], xmm0
0x18002adfc  movups  xmm1, xmmword ptr [rdi+170h]
0x18002ae03  movups  xmmword ptr [rsi+170h], xmm1
0x18002ae0a  movups  xmm0, xmmword ptr [rdi+180h]
0x18002ae11  movups  xmmword ptr [rsi+180h], xmm0
0x18002ae18  movups  xmm1, xmmword ptr [rdi+190h]
0x18002ae1f  movups  xmmword ptr [rsi+190h], xmm1
0x18002ae26  movups  xmm0, xmmword ptr [rdi+1A0h]
  ... truncated ...
```

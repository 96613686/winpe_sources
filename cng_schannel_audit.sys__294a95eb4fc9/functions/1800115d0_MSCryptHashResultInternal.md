# MSCryptHashResultInternal

- ea: `0x1800115d0`
- end: `0x180011ab0`
- name: `MSCryptHashResultInternal`
- size: `1248`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x180011ac0`
- `0x18003b970`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800115d0`
- `0x180012b30`
- `0x180018100`
- `0x180018450`
- `0x18002daa0`
- `0x18002dc10`
- `0x18003140c`
- `0x180031dd0`
- `0x180031ec0`
- `0x180034e80`
- `0x18003c480`
- `0x18003cf30`
- `0x1800403b0`
- `0x180064860`
- `0x1800648b0`
- `0x1800872e0`
- `0x180092228`
- `0x18009234c`
- `0x1800925f0`
- `0x180092620`
- `0x180092f20`
- `0x180092fa8`
- `0x180093640`
- `0x180096b8c`
- `0x1800972f8`
- `0x180097380`

## string_xrefs

- `0x1800116d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180011a8d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashResultInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  unsigned int v7; // esi
  int v8; // ebx
  bool v9; // r14
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx

  v4 = (unsigned int)a3;
  v7 = 0;
  v8 = 1;
  v9 = (a4 & 1) == 0;
  switch ( *(_DWORD *)(a1 + 8) )
  {
    case 0x20001:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2399;
        goto LABEL_4;
      }
      SymCryptMd5Result(a1 + 128);
      return v7;
    case 0x20002:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v10 = 2416;
        goto LABEL_4;
      }
      SymCryptSha1Result(a1 + 128, a2);
      return v7;
    case 0x20003:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2433;
        goto LABEL_4;
      }
      SymCryptMd2Result(a1 + 128);
      return v7;
    case 0x20004:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2450;
        goto LABEL_4;
      }
      SymCryptMd4Result(a1 + 128);
      return v7;
    case 0x20005:
      if ( *(_DWORD *)(a1 + 12) == 32 )
      {
        SymCryptSha256Result(a1 + 128);
      }
      else
      {
        v7 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            163);
      }
      return v7;
    case 0x20006:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2484;
        goto LABEL_4;
      }
      SymCryptSha384Result(a1 + 128);
      return v7;
    case 0x20007:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2501;
        goto LABEL_4;
      }
      SymCryptSha512Result(a1 + 128);
      return v7;
    case 0x20008:
      if ( !*(_DWORD *)(a1 + 116) )
      {
        v7 = -1073740758;
        v10 = 2518;
        v11 = 3221226538LL;
        goto LABEL_85;
      }
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2525;
        goto LABEL_4;
      }
      SymCryptGcmEncryptFinal(a1 + 2736, a2, 16);
      *(_DWORD *)(a1 + 116) = 0;
      return v7;
    case 0x20009:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v10 = 2548;
        goto LABEL_4;
      }
      SymCryptHmacSha1Result(a1 + 208);
      SymCryptHmacSha1Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000A:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2566;
        goto LABEL_4;
      }
      SymCryptHmacMd5Result(a1 + 176);
      SymCryptHmacMd5Init(a1 + 176, a1 + 128);
      return v7;
    case 0x2000B:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v10 = 2584;
        goto LABEL_4;
      }
      SymCryptHmacSha256Result(a1 + 208);
      SymCryptHmacSha256Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000C:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2602;
        goto LABEL_4;
      }
      SymCryptHmacSha384Result(a1 + 272);
      SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      return v7;
    case 0x2000D:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2620;
        goto LABEL_4;
      }
      SymCryptHmacSha512Result(a1 + 272);
      SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      return v7;
    case 0x2000E:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2638;
        goto LABEL_4;
      }
      SymCryptAesCmacResult(a1 + 672);
      *(_QWORD *)(a1 + 704) = 0;
      *(_QWORD *)(a1 + 672) = 0;
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 712) = a1 + 128;
      return v7;
    case 0x2000F:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v10 = 2656;
        goto LABEL_4;
      }
      a3 = 32;
      goto LABEL_52;
    case 0x20010:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2673;
        goto LABEL_4;
      }
      a3 = 48;
      goto LABEL_52;
    case 0x20011:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2690;
        goto LABEL_4;
      }
      a3 = 64;
LABEL_52:
      LOBYTE(a4) = 1;
LABEL_53:
      SymCryptKeccakExtract(a1 + 128, a2, a3, a4);
      break;
    case 0x20012:
      if ( *(_DWORD *)(a1 + 12) == 32 )
        goto LABEL_62;
      v10 = 2707;
      goto LABEL_4;
    case 0x20013:
      if ( *(_DWORD *)(a1 + 12) == 48 )
        goto LABEL_62;
      v10 = 2725;
      goto LABEL_4;
    case 0x20014:
      if ( *(_DWORD *)(a1 + 12) == 64 )
      {
LABEL_62:
        SymCryptHmacResult(a1 + 640);
        SymCryptHmacInit(a1 + 640, a1 + 128);
      }
      else
      {
        v10 = 2743;
LABEL_4:
        v7 = -1073741816;
        v11 = 3221225480LL;
LABEL_85:
        DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v10);
      }
      break;
    case 0x20015:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      goto LABEL_69;
    case 0x20016:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
LABEL_69:
      LOBYTE(a4) = v9;
      SymCryptCShake256Extract(a1 + 528, a2, v4, a4);
      *(_DWORD *)(a1 + 280) = 2 * !v9 + 1;
      return v7;
    case 0x20017:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v12 = a1 + 544;
      v13 = v4;
      v14 = a2;
      if ( v9 )
        goto LABEL_76;
      goto LABEL_77;
    case 0x20018:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v12 = a1 + 544;
      v13 = v4;
      v14 = a2;
      if ( v9 )
      {
LABEL_76:
        SymCryptKmac128ResultEx(v12, v14, v13);
      }
      else
      {
LABEL_77:
        SymCryptKmac256Extract(v12, a2, v4);
        v8 = 3;
      }
      *(_DWORD *)(a1 + 528) = v8;
      return v7;
    case 0x20019:
    case 0x2001A:
      a3 = (unsigned int)a3;
      LOBYTE(a4) = (a4 & 1) == 0;
      goto LABEL_53;
    default:
      v7 = -1073741637;
      v10 = 2886;
      v11 = 3221225659LL;
      goto LABEL_85;
  }
  return v7;
}

```

## disassembly

```asm
0x1800115d0  push    rbx
0x1800115d2  push    rbp
0x1800115d3  push    rsi
0x1800115d4  push    rdi
0x1800115d5  push    r14
0x1800115d7  push    r15
0x1800115d9  sub     rsp, 48h
0x1800115dd  mov     eax, [rcx+8]
0x1800115e0  mov     r14d, r9d
0x1800115e3  add     eax, 0FFFDFFFFh; switch 26 cases
0x1800115e8  mov     r15d, r8d
0x1800115eb  mov     rbp, rdx
0x1800115ee  mov     rdi, rcx
0x1800115f1  cmp     eax, 19h
0x1800115f4  ja      def_180011616; jumptable 0000000180011616 default case
0x1800115fa  xor     esi, esi
0x1800115fc  lea     rcx, cs:180000000h
0x180011603  mov     eax, ds:(jpt_180011616 - 180000000h)[rcx+rax*4]
0x18001160a  not     r14b
0x18001160d  lea     ebx, [rsi+1]
0x180011610  and     r14b, bl
0x180011613  add     rax, rcx
0x180011616  jmp     rax; switch jump
0x18001161c  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180011616 case 131073
0x180011620  jz      short loc_180011637
0x180011622  mov     r9d, 95Fh
0x180011628  mov     esi, 0C0000008h
0x18001162d  mov     ecx, 0C0000008h
0x180011632  jmp     loc_180011A8D
0x180011637  lea     rcx, [rdi+80h]
0x18001163e  call    SymCryptMd5Result
0x180011643  jmp     loc_180011AA0
0x180011648  cmp     dword ptr [rdi+0Ch], 14h; jumptable 0000000180011616 case 131074
0x18001164c  jz      short loc_180011656
0x18001164e  mov     r9d, 970h
0x180011654  jmp     short loc_180011628
0x180011656  lea     rcx, [rdi+80h]
0x18001165d  call    SymCryptSha1Result
0x180011662  jmp     loc_180011AA0
0x180011667  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180011616 case 131075
0x18001166b  jz      short loc_180011675
0x18001166d  mov     r9d, 981h
0x180011673  jmp     short loc_180011628
0x180011675  lea     rcx, [rdi+80h]
0x18001167c  call    SymCryptMd2Result
0x180011681  jmp     loc_180011AA0
0x180011686  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180011616 case 131076
0x18001168a  jz      short loc_180011694
0x18001168c  mov     r9d, 992h
0x180011692  jmp     short loc_180011628
0x180011694  lea     rcx, [rdi+80h]
0x18001169b  call    SymCryptMd4Result
0x1800116a0  jmp     loc_180011AA0
0x1800116a5  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180011616 case 131077
0x1800116a9  jz      short loc_180011703
0x1800116ab  mov     esi, 0C0000008h
0x1800116b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116b7  lea     rax, WPP_GLOBAL_Control
0x1800116be  cmp     rcx, rax
0x1800116c1  jz      loc_180011AA0
0x1800116c7  mov     eax, [rcx+2Ch]
0x1800116ca  test    bl, al
0x1800116cc  jz      loc_180011AA0
0x1800116d2  mov     rcx, [rcx+18h]
0x1800116d6  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800116dd  mov     [rsp+78h+var_48], 9A3h
0x1800116e5  lea     r9, aStatus; "Status"
0x1800116ec  mov     [rsp+78h+var_50], r8
0x1800116f1  mov     [rsp+78h+var_58], 0C0000008h
0x1800116f9  call    WPP_SF_sDsd
0x1800116fe  jmp     loc_180011AA0
0x180011703  lea     rcx, [rdi+80h]
0x18001170a  call    SymCryptSha256Result
0x18001170f  jmp     loc_180011AA0
0x180011714  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180011616 case 131078
0x180011718  jz      short loc_180011725
0x18001171a  mov     r9d, 9B4h
0x180011720  jmp     loc_180011628
0x180011725  lea     rcx, [rdi+80h]
0x18001172c  call    SymCryptSha384Result
0x180011731  jmp     loc_180011AA0
0x180011736  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180011616 case 131079
0x18001173a  jz      short loc_180011747
0x18001173c  mov     r9d, 9C5h
0x180011742  jmp     loc_180011628
0x180011747  lea     rcx, [rdi+80h]
0x18001174e  call    SymCryptSha512Result
0x180011753  jmp     loc_180011AA0
0x180011758  cmp     [rdi+74h], esi; jumptable 0000000180011616 case 131080
0x18001175b  jnz     short loc_180011772
0x18001175d  mov     esi, 0C000042Ah
0x180011762  mov     r9d, 9D6h
0x180011768  mov     ecx, 0C000042Ah
0x18001176d  jmp     loc_180011A8D
0x180011772  cmp     dword ptr [rdi+0Ch], 10h
0x180011776  jz      short loc_180011783
0x180011778  mov     r9d, 9DDh
0x18001177e  jmp     loc_180011628
0x180011783  lea     rcx, [rdi+0AB0h]
0x18001178a  mov     r8d, 10h
0x180011790  call    SymCryptGcmEncryptFinal
0x180011795  mov     [rdi+74h], esi
0x180011798  jmp     loc_180011AA0
0x18001179d  cmp     dword ptr [rdi+0Ch], 14h; jumptable 0000000180011616 case 131081
0x1800117a1  jz      short loc_1800117AE
0x1800117a3  mov     r9d, 9F4h
0x1800117a9  jmp     loc_180011628
0x1800117ae  lea     rbx, [rdi+0D0h]
0x1800117b5  mov     rcx, rbx
0x1800117b8  call    SymCryptHmacSha1Result
0x1800117bd  lea     rdx, [rdi+80h]
0x1800117c4  mov     rcx, rbx
0x1800117c7  call    SymCryptHmacSha1Init
0x1800117cc  jmp     loc_180011AA0
0x1800117d1  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180011616 case 131082
0x1800117d5  jz      short loc_1800117E2
0x1800117d7  mov     r9d, 0A06h
0x1800117dd  jmp     loc_180011628
0x1800117e2  lea     rbx, [rdi+0B0h]
0x1800117e9  mov     rcx, rbx
0x1800117ec  call    SymCryptHmacMd5Result
0x1800117f1  lea     rdx, [rdi+80h]
0x1800117f8  mov     rcx, rbx
0x1800117fb  call    SymCryptHmacMd5Init
0x180011800  jmp     loc_180011AA0
0x180011805  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180011616 case 131083
0x180011809  jz      short loc_180011816
0x18001180b  mov     r9d, 0A18h
0x180011811  jmp     loc_180011628
0x180011816  lea     rbx, [rdi+0D0h]
0x18001181d  mov     rcx, rbx
0x180011820  call    SymCryptHmacSha256Result
0x180011825  lea     rdx, [rdi+80h]
0x18001182c  mov     rcx, rbx
0x18001182f  call    SymCryptHmacSha256Init
0x180011834  jmp     loc_180011AA0
0x180011839  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180011616 case 131084
0x18001183d  jz      short loc_18001184A
0x18001183f  mov     r9d, 0A2Ah
0x180011845  jmp     loc_180011628
0x18001184a  lea     rbx, [rdi+110h]
0x180011851  mov     rcx, rbx
0x180011854  call    SymCryptHmacSha384Result
0x180011859  lea     rdx, [rdi+80h]
0x180011860  mov     rcx, rbx
0x180011863  call    SymCryptHmacSha512Init
0x180011868  jmp     loc_180011AA0
0x18001186d  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180011616 case 131085
0x180011871  jz      short loc_18001187E
0x180011873  mov     r9d, 0A3Ch
0x180011879  jmp     loc_180011628
0x18001187e  lea     rbx, [rdi+110h]
0x180011885  mov     rcx, rbx
0x180011888  call    SymCryptHmacSha512Result
0x18001188d  lea     rdx, [rdi+80h]
0x180011894  mov     rcx, rbx
0x180011897  call    SymCryptHmacSha512Init
0x18001189c  jmp     loc_180011AA0
0x1800118a1  cmp     dword ptr [rdi+0Ch], 10h; jumptable 0000000180011616 case 131086
0x1800118a5  jz      short loc_1800118B2
0x1800118a7  mov     r9d, 0A4Eh
0x1800118ad  jmp     loc_180011628
0x1800118b2  lea     rbx, [rdi+2A0h]
0x1800118b9  mov     rcx, rbx
0x1800118bc  call    SymCryptAesCmacResult
0x1800118c1  mov     [rbx+20h], rsi
0x1800118c5  lea     rax, [rdi+80h]
0x1800118cc  mov     [rbx], rsi
0x1800118cf  mov     [rbx+8], rsi
0x1800118d3  mov     [rbx+28h], rax
0x1800118d7  jmp     loc_180011AA0
0x1800118dc  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180011616 case 131087
0x1800118e0  jz      short loc_1800118ED
0x1800118e2  mov     r9d, 0A60h
0x1800118e8  jmp     loc_180011628
0x1800118ed  mov     r8d, 20h ; ' '
0x1800118f3  mov     r9b, bl
0x1800118f6  lea     rcx, [rdi+80h]
0x1800118fd  call    SymCryptKeccakExtract
0x180011902  jmp     loc_180011AA0
0x180011907  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180011616 case 131088
0x18001190b  jz      short loc_180011918
0x18001190d  mov     r9d, 0A71h
0x180011913  jmp     loc_180011628
0x180011918  mov     r8d, 30h ; '0'
0x18001191e  jmp     short loc_1800118F3
0x180011920  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180011616 case 131089
0x180011924  jz      short loc_180011931
0x180011926  mov     r9d, 0A82h
0x18001192c  jmp     loc_180011628
0x180011931  mov     r8d, 40h ; '@'
0x180011937  jmp     short loc_1800118F3
0x180011939  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 0000000180011616 case 131090
0x18001193d  jz      short loc_18001194A
0x18001193f  mov     r9d, 0A93h
0x180011945  jmp     loc_180011628
0x18001194a  lea     rbx, [rdi+280h]
0x180011951  mov     rcx, rbx
0x180011954  call    SymCryptHmacResult
0x180011959  lea     rdx, [rdi+80h]
0x180011960  mov     rcx, rbx
0x180011963  call    SymCryptHmacInit
0x180011968  jmp     loc_180011AA0
0x18001196d  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 0000000180011616 case 131091
0x180011971  jz      short loc_18001194A
0x180011973  mov     r9d, 0AA5h
0x180011979  jmp     loc_180011628
0x18001197e  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 0000000180011616 case 131092
0x180011982  jz      short loc_18001194A
0x180011984  mov     r9d, 0AB7h
0x18001198a  jmp     loc_180011628
0x18001198f  cmp     [rdi+118h], ebx; jumptable 0000000180011616 case 131093
0x180011995  ja      short loc_1800119A4
0x180011997  xor     r8d, r8d
0x18001199a  xor     edx, edx
0x18001199c  mov     rcx, rdi
0x18001199f  call    MSCryptHashDataInternal
0x1800119a4  mov     r8, r15
0x1800119a7  lea     rcx, [rdi+210h]
0x1800119ae  mov     r9b, r14b
0x1800119b1  mov     rdx, rbp
0x1800119b4  call    SymCryptCShake256Extract
0x1800119b9  movzx   eax, r14b
0x1800119bd  xor     eax, ebx
0x1800119bf  lea     eax, ds:1[rax*2]
0x1800119c6  mov     [rdi+118h], eax
0x1800119cc  jmp     loc_180011AA0
0x1800119d1  cmp     [rdi+118h], ebx; jumptable 0000000180011616 case 131094
0x1800119d7  ja      short loc_1800119E6
0x1800119d9  xor     r8d, r8d
0x1800119dc  xor     edx, edx
0x1800119de  mov     rcx, rdi
0x1800119e1  call    MSCryptHashDataInternal
0x1800119e6  mov     r8, r15
0x1800119e9  lea     rcx, [rdi+210h]
0x1800119f0  mov     r9b, r14b
0x1800119f3  mov     rdx, rbp
0x1800119f6  call    SymCryptCShake256Extract
0x1800119fb  jmp     short loc_1800119B9
0x1800119fd  cmp     [rdi+210h], ebx; jumptable 0000000180011616 case 131095
0x180011a03  ja      short loc_180011A12
0x180011a05  xor     r8d, r8d
0x180011a08  xor     edx, edx
0x180011a0a  mov     rcx, rdi
0x180011a0d  call    MSCryptHashDataInternal
0x180011a12  lea     rcx, [rdi+220h]
0x180011a19  mov     r8, r15
0x180011a1c  mov     rdx, rbp
0x180011a1f  test    r14b, r14b
0x180011a22  jz      short loc_180011A2B
0x180011a24  call    SymCryptKmac128ResultEx
0x180011a29  jmp     short loc_180011A35
0x180011a2b  call    SymCryptKmac256Extract
0x180011a30  mov     ebx, 3
0x180011a35  mov     [rdi+210h], ebx
0x180011a3b  jmp     short loc_180011AA0
0x180011a3d  cmp     [rdi+210h], ebx; jumptable 0000000180011616 case 131096
0x180011a43  ja      short loc_180011A52
0x180011a45  xor     r8d, r8d
0x180011a48  xor     edx, edx
0x180011a4a  mov     rcx, rdi
0x180011a4d  call    MSCryptHashDataInternal
0x180011a52  lea     rcx, [rdi+220h]
0x180011a59  mov     r8, r15
0x180011a5c  mov     rdx, rbp
0x180011a5f  test    r14b, r14b
0x180011a62  jz      short loc_180011A6B
0x180011a64  call    SymCryptKmac128ResultEx
0x180011a69  jmp     short loc_180011A35
0x180011a6b  call    SymCryptKmac256Extract
0x180011a70  jmp     short loc_180011A30
0x180011a72  mov     r8, r15; jumptable 0000000180011616 cases 131097,131098
0x180011a75  mov     r9b, r14b
0x180011a78  jmp     loc_1800118F6
0x180011a7d  mov     esi, 0C00000BBh; jumptable 0000000180011616 default case
0x180011a82  mov     r9d, 0B46h
0x180011a88  mov     ecx, 0C00000BBh
0x180011a8d  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011a94  lea     rdx, aStatus; "Status"
0x180011a9b  call    DebugTraceError
0x180011aa0  mov     eax, esi
0x180011aa2  add     rsp, 48h
0x180011aa6  pop     r15
0x180011aa8  pop     r14
0x180011aaa  pop     rdi
0x180011aab  pop     rsi
0x180011aac  pop     rbp
0x180011aad  pop     rbx
0x180011aae  retn
```

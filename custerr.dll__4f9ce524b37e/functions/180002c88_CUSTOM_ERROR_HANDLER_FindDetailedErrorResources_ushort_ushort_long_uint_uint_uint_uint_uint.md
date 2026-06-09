# CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(ushort,ushort,long,uint *,uint *,uint *,uint *,uint *)

- ea: `0x180002c88`
- end: `0x180003774`
- name: `?FindDetailedErrorResources@CUSTOM_ERROR_HANDLER@@AEAAJGGJPEAI0000@Z`
- size: `2796`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, unsigned __int16, unsigned __int16, int, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000377c`
- `0x18000518c`

## callees

- `0x180002c88`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(
        CUSTOM_ERROR_HANDLER *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  int v9; // eax
  int v10; // ecx
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  unsigned int *v14; // r10
  unsigned int *v15; // r11
  unsigned int *v16; // rbx
  unsigned int *v17; // rdi
  unsigned int *v18; // rsi

  if ( a2 <= 0x1AFu )
  {
    if ( a2 == 431 )
    {
      v9 = 12392;
      v10 = 12391;
      v11 = 12390;
      v12 = 12389;
      v13 = 12388;
    }
    else
    {
      switch ( a2 )
      {
        case 0x190u:
          v9 = 12668;
          v10 = 12667;
          v11 = 12666;
          v12 = 12665;
          v13 = 12664;
          goto LABEL_158;
        case 0x191u:
          switch ( a3 )
          {
            case 1u:
              v9 = 12212;
              v10 = 12211;
              v11 = 12210;
              v12 = 12209;
              v13 = 12208;
              goto LABEL_158;
            case 2u:
              v9 = 12218;
              v10 = 12217;
              v11 = 12216;
              v12 = 12215;
              v13 = 12214;
              goto LABEL_158;
            case 3u:
              v9 = 12224;
              v10 = 12223;
              v11 = 12222;
              v12 = 12221;
              v13 = 12220;
              goto LABEL_158;
            case 4u:
              v9 = 12230;
              v10 = 12229;
              v11 = 12228;
              v12 = 12227;
              v13 = 12226;
              goto LABEL_158;
          }
          v14 = a9;
          v15 = a8;
          v16 = a7;
          v17 = a6;
          v18 = a5;
          if ( a3 == 5 )
          {
            v9 = 12236;
            v10 = 12235;
            v11 = 12234;
            v12 = 12233;
            v13 = 12232;
          }
          else
          {
            v9 = 12206;
            v10 = 12205;
            v11 = 12204;
            v12 = 12203;
            v13 = 12202;
          }
          goto LABEL_159;
        case 0x193u:
          if ( a3 <= 0xAu )
          {
            switch ( a3 )
            {
              case 0xAu:
                v9 = 12518;
                v10 = 12517;
                v11 = 12516;
                v12 = 12515;
                v13 = 12514;
                goto LABEL_158;
              case 1u:
                v9 = 12248;
                v10 = 12247;
                v11 = 12246;
                v12 = 12245;
                v13 = 12244;
                goto LABEL_158;
              case 2u:
                v9 = 12254;
                v10 = 12253;
                v11 = 12252;
                v12 = 12251;
                v13 = 12250;
                goto LABEL_158;
              case 3u:
                v9 = 12260;
                v10 = 12259;
                v11 = 12258;
                v12 = 12257;
                v13 = 12256;
                goto LABEL_158;
              case 4u:
                v9 = 12266;
                v10 = 12265;
                v11 = 12264;
                v12 = 12263;
                v13 = 12262;
                goto LABEL_158;
              case 5u:
                v9 = 12272;
                v10 = 12271;
                v11 = 12270;
                v12 = 12269;
                v13 = 12268;
                goto LABEL_158;
              case 6u:
                v9 = 12278;
                v10 = 12277;
                v11 = 12276;
                v12 = 12275;
                v13 = 12274;
                goto LABEL_158;
              case 7u:
                v9 = 12284;
                v10 = 12283;
                v11 = 12282;
                v12 = 12281;
                v13 = 12280;
                goto LABEL_158;
              case 8u:
                v9 = 12290;
                v10 = 12289;
                v11 = 12288;
                v12 = 12287;
                v13 = 12286;
                goto LABEL_158;
            }
            goto LABEL_42;
          }
          switch ( a3 )
          {
            case 0xCu:
              v9 = 12296;
              v10 = 12295;
              v11 = 12294;
              v12 = 12293;
              v13 = 12292;
              break;
            case 0xDu:
              v9 = 12302;
              v10 = 12301;
              v11 = 12300;
              v12 = 12299;
              v13 = 12298;
              break;
            case 0xEu:
              v9 = 12308;
              v10 = 12307;
              v11 = 12306;
              v12 = 12305;
              v13 = 12304;
              break;
            case 0x10u:
              v9 = 12314;
              v10 = 12313;
              v11 = 12312;
              v12 = 12311;
              v13 = 12310;
              break;
            case 0x11u:
              v9 = 12320;
              v10 = 12319;
              v11 = 12318;
              v12 = 12317;
              v13 = 12316;
              break;
            case 0x12u:
              v9 = 12326;
              v10 = 12325;
              v11 = 12324;
              v12 = 12323;
              v13 = 12322;
              break;
            case 0x13u:
              v9 = 12332;
              v10 = 12331;
              v11 = 12330;
              v12 = 12329;
              v13 = 12328;
              break;
            default:
LABEL_42:
              v9 = 12242;
              v10 = 12241;
              v11 = 12240;
              v12 = 12239;
              v13 = 12238;
              goto LABEL_158;
          }
          goto LABEL_158;
        case 0x194u:
          if ( a3 <= 0xCu )
          {
            switch ( a3 )
            {
              case 0xCu:
                v9 = 12404;
                v10 = 12403;
                v11 = 12402;
                v12 = 12401;
                v13 = 12400;
                goto LABEL_158;
              case 2u:
                v9 = 12344;
                v10 = 12343;
                v11 = 12342;
                v12 = 12341;
                v13 = 12340;
                goto LABEL_158;
              case 3u:
                v9 = 12350;
                v10 = 12349;
                v11 = 12348;
                v12 = 12347;
                v13 = 12346;
                goto LABEL_158;
              case 4u:
                v9 = 12356;
                v10 = 12355;
                v11 = 12354;
                v12 = 12353;
                v13 = 12352;
                goto LABEL_158;
              case 5u:
                v9 = 12362;
                v10 = 12361;
                v11 = 12360;
                v12 = 12359;
                v13 = 12358;
                goto LABEL_158;
              case 6u:
                v9 = 12368;
                v10 = 12367;
                v11 = 12366;
                v12 = 12365;
                v13 = 12364;
                goto LABEL_158;
              case 7u:
                v9 = 12374;
                v10 = 12373;
                v11 = 12372;
                v12 = 12371;
                v13 = 12370;
                goto LABEL_158;
              case 8u:
                v9 = 12380;
                v10 = 12379;
                v11 = 12378;
                v12 = 12377;
                v13 = 12376;
                goto LABEL_158;
              case 9u:
                v9 = 12386;
                v10 = 12385;
                v11 = 12384;
                v12 = 12383;
                v13 = 12382;
                goto LABEL_158;
              case 0xBu:
                v9 = 12398;
                v10 = 12397;
                v11 = 12396;
                v12 = 12395;
                v13 = 12394;
                goto LABEL_158;
            }
            goto LABEL_79;
          }
          switch ( a3 )
          {
            case 0xEu:
              v9 = 12416;
              v10 = 12415;
              v11 = 12414;
              v12 = 12413;
              v13 = 12412;
              break;
            case 0xFu:
              v9 = 12422;
              v10 = 12421;
              v11 = 12420;
              v12 = 12419;
              v13 = 12418;
              break;
            case 0x10u:
              v9 = 12626;
              v10 = 12625;
              v11 = 12624;
              v12 = 12623;
              v13 = 12622;
              break;
            case 0x11u:
              v9 = 12632;
              v10 = 12631;
              v11 = 12630;
              v12 = 12629;
              v13 = 12628;
              break;
            case 0x14u:
              v9 = 12686;
              v10 = 12685;
              v11 = 12684;
              v12 = 12683;
              v13 = 12682;
              break;
            case 0x15u:
              v9 = 12692;
              v10 = 12691;
              v11 = 12690;
              v12 = 12689;
              v13 = 12688;
              break;
            case 0x16u:
              v9 = 12698;
              v10 = 12697;
              v11 = 12696;
              v12 = 12695;
              v13 = 12694;
              break;
            case 0x17u:
              v9 = 12704;
              v10 = 12703;
              v11 = 12702;
              v12 = 12701;
              v13 = 12700;
              break;
            default:
LABEL_79:
              v9 = 12338;
              v10 = 12337;
              v11 = 12336;
              v12 = 12335;
              v13 = 12334;
              goto LABEL_158;
          }
          break;
        case 0x195u:
          v9 = 12428;
          v10 = 12427;
          v11 = 12426;
          v12 = 12425;
          v13 = 12424;
          goto LABEL_158;
        case 0x196u:
          v9 = 12434;
          v10 = 12433;
          v11 = 12432;
          v12 = 12431;
          v13 = 12430;
          goto LABEL_158;
        case 0x197u:
          v9 = 12524;
          v10 = 12523;
          v11 = 12522;
          v12 = 12521;
          v13 = 12520;
          goto LABEL_158;
        case 0x198u:
          v9 = 12530;
          v10 = 12529;
          v11 = 12528;
          v12 = 12527;
          v13 = 12526;
          goto LABEL_158;
        case 0x199u:
          v9 = 12536;
          v10 = 12535;
          v11 = 12534;
          v12 = 12533;
          v13 = 12532;
          goto LABEL_158;
        case 0x19Au:
          v9 = 12542;
          v10 = 12541;
          v11 = 12540;
          v12 = 12539;
          v13 = 12538;
          goto LABEL_158;
        case 0x19Bu:
          v9 = 12548;
          v10 = 12547;
          v11 = 12546;
          v12 = 12545;
          v13 = 12544;
          goto LABEL_158;
        case 0x19Cu:
          v9 = 12440;
          v10 = 12439;
          v11 = 12438;
          v12 = 12437;
          v13 = 12436;
          goto LABEL_158;
        case 0x19Du:
          if ( a3 == 1 )
          {
            v9 = 12410;
            v10 = 12409;
            v11 = 12408;
            v12 = 12407;
            v13 = 12406;
          }
          else
          {
            v9 = 12608;
            v10 = 12607;
            v11 = 12606;
            v12 = 12605;
            v13 = 12604;
          }
          goto LABEL_158;
        case 0x19Eu:
          v9 = 12554;
          v10 = 12553;
          v11 = 12552;
          v12 = 12551;
          v13 = 12550;
          goto LABEL_158;
        case 0x19Fu:
          v9 = 12560;
          v10 = 12559;
          v11 = 12558;
          v12 = 12557;
          v13 = 12556;
          goto LABEL_158;
        case 0x1A0u:
          v9 = 12566;
          v10 = 12565;
          v11 = 12564;
          v12 = 12563;
          v13 = 12562;
          goto LABEL_158;
        case 0x1A1u:
          v9 = 12572;
          v10 = 12571;
          v11 = 12570;
          v12 = 12569;
          v13 = 12568;
          goto LABEL_158;
        default:
          goto LABEL_110;
      }
    }
    goto LABEL_158;
  }
  if ( a2 == 500 )
  {
    if ( a3 > 0x13u )
    {
      switch ( a3 )
      {
        case 0x15u:
          v9 = 12638;
          v10 = 12637;
          v11 = 12636;
          v12 = 12635;
          v13 = 12634;
          goto LABEL_158;
        case 0x16u:
          v9 = 12644;
          v10 = 12643;
          v11 = 12642;
          v12 = 12641;
          v13 = 12640;
          goto LABEL_158;
        case 0x17u:
          v9 = 12650;
          v10 = 12649;
          v11 = 12648;
          v12 = 12647;
          v13 = 12646;
          goto LABEL_158;
        case 0x18u:
          v9 = 12656;
          v10 = 12655;
          v11 = 12654;
          v12 = 12653;
          v13 = 12652;
          goto LABEL_158;
        case 0x64u:
          v9 = 12488;
          v10 = 12487;
          v11 = 12486;
          v12 = 12485;
          v13 = 12484;
          goto LABEL_158;
      }
    }
    else
    {
      switch ( a3 )
      {
        case 0x13u:
          v9 = 12482;
          v10 = 12481;
          v11 = 12480;
          v12 = 12479;
          v13 = 12478;
          goto LABEL_158;
        case 0xBu:
          v9 = 12452;
          v10 = 12451;
          v11 = 12450;
          v12 = 12449;
          v13 = 12448;
          goto LABEL_158;
        case 0xCu:
          v9 = 12458;
          v10 = 12457;
          v11 = 12456;
          v12 = 12455;
          v13 = 12454;
          goto LABEL_158;
        case 0xDu:
          v9 = 12464;
          v10 = 12463;
          v11 = 12462;
          v12 = 12461;
          v13 = 12460;
          goto LABEL_158;
        case 0xFu:
          v9 = 12470;
          v10 = 12469;
          v11 = 12468;
          v12 = 12467;
          v13 = 12466;
          goto LABEL_158;
        case 0x10u:
          v9 = 12476;
          v10 = 12475;
          v11 = 12474;
          v12 = 12473;
          v13 = 12472;
          goto LABEL_158;
      }
    }
    switch ( a4 )
    {
      case -2147024894:
        v9 = 12620;
        v10 = 12619;
        v11 = 12618;
        v12 = 12617;
        v13 = 12616;
        goto LABEL_158;
      case -2147024883:
        v9 = 12614;
        v10 = 12613;
        v11 = 12612;
        v12 = 12611;
        v13 = 12610;
        goto LABEL_158;
      case -2147024770:
        v9 = 12596;
        v10 = 12595;
        v11 = 12594;
        v12 = 12593;
        v13 = 12592;
        goto LABEL_158;
    }
    v14 = a9;
    v15 = a8;
    v16 = a7;
    v17 = a6;
    v18 = a5;
    if ( a4 == -2147024769 )
    {
      v9 = 12602;
      v10 = 12601;
      v11 = 12600;
      v12 = 12599;
      v13 = 12598;
    }
    else
    {
      v9 = 12446;
      v10 = 12445;
      v11 = 12444;
      v12 = 12443;
      v13 = 12442;
    }
  }
  else
  {
    if ( a2 == 501 )
    {
      v9 = 12494;
      v10 = 12493;
      v11 = 12492;
      v12 = 12491;
      v13 = 12490;
      goto LABEL_158;
    }
    if ( a2 != 502 )
    {
      if ( a2 != 503 )
      {
        if ( a2 == 504 )
        {
          v9 = 12584;
          v10 = 12583;
          v11 = 12582;
          v12 = 12581;
          v13 = 12580;
        }
        else if ( a2 == 505 )
        {
          v9 = 12590;
          v10 = 12589;
          v11 = 12588;
          v12 = 12587;
          v13 = 12586;
        }
        else
        {
LABEL_110:
          v9 = 12200;
          v10 = 12199;
          v11 = 12198;
          v12 = 12197;
          v13 = 12196;
        }
        goto LABEL_158;
      }
      if ( a3 == 2 )
      {
        v9 = 12662;
        v10 = 12661;
        v11 = 12660;
        v12 = 12659;
        v13 = 12658;
      }
      else
      {
        if ( a3 != 3 )
        {
          v14 = a9;
          v15 = a8;
          v16 = a7;
          v17 = a6;
          v18 = a5;
          if ( a3 == 4 )
          {
            v9 = 12680;
            v10 = 12679;
            v11 = 12678;
            v12 = 12677;
            v13 = 12676;
          }
          else
          {
            v9 = 12578;
            v10 = 12577;
            v11 = 12576;
            v12 = 12575;
            v13 = 12574;
          }
          goto LABEL_159;
        }
        v9 = 12674;
        v10 = 12673;
        v11 = 12672;
        v12 = 12671;
        v13 = 12670;
      }
LABEL_158:
      v18 = a5;
      v17 = a6;
      v16 = a7;
      v15 = a8;
      v14 = a9;
      goto LABEL_159;
    }
    if ( a3 == 1 )
    {
      v9 = 12506;
      v10 = 12505;
      v11 = 12504;
      v12 = 12503;
      v13 = 12502;
      goto LABEL_158;
    }
    v14 = a9;
    v15 = a8;
    v16 = a7;
    v17 = a6;
    v18 = a5;
    if ( a3 == 2 )
    {
      v9 = 12512;
      v10 = 12511;
      v11 = 12510;
      v12 = 12509;
      v13 = 12508;
    }
    else
    {
      v9 = 12500;
      v10 = 12499;
      v11 = 12498;
      v12 = 12497;
      v13 = 12496;
    }
  }
LABEL_159:
  *v18 = v13;
  *v17 = v12;
  *v16 = v11;
  *v15 = v10;
  *v14 = v9;
  return 0;
}

```

## disassembly

```asm
0x180002c88  push    rbp
0x180002c8a  push    rbx
0x180002c8b  push    rsi
0x180002c8c  push    rdi
0x180002c8d  mov     rbp, rsp
0x180002c90  movzx   ecx, dx
0x180002c93  mov     eax, 1AFh
0x180002c98  cmp     ecx, eax
0x180002c9a  ja      loc_180003381
0x180002ca0  jz      loc_180003369
0x180002ca6  add     ecx, 0FFFFFE70h; switch 18 cases
0x180002cac  cmp     ecx, 11h
0x180002caf  ja      def_180002CC9; jumptable 0000000180002CC9 default case, case 402
0x180002cb5  movsxd  rax, ecx
0x180002cb8  lea     rdx, cs:180000000h
0x180002cbf  mov     ecx, ds:(jpt_180002CC9 - 180000000h)[rdx+rax*4]
0x180002cc6  add     rcx, rdx
0x180002cc9  jmp     rcx; switch jump
0x180002ccb  mov     eax, 317Ch; jumptable 0000000180002CC9 case 400
0x180002cd0  lea     ecx, [rax-1]
0x180002cd3  lea     edx, [rax-2]
0x180002cd6  lea     r8d, [rax-3]
0x180002cda  lea     r9d, [rax-4]
0x180002cde  jmp     loc_180003701
0x180002ce3  movzx   ecx, r8w; jumptable 0000000180002CC9 case 401
0x180002ce7  sub     ecx, 1
0x180002cea  jz      loc_180002D94
0x180002cf0  sub     ecx, 1
0x180002cf3  jz      loc_180002D7C
0x180002cf9  sub     ecx, 1
0x180002cfc  jz      short loc_180002D64
0x180002cfe  sub     ecx, 1
0x180002d01  jz      short loc_180002D4C
0x180002d03  mov     r10, [rbp+arg_40]
0x180002d07  mov     r11, [rbp+arg_38]
0x180002d0b  mov     rbx, [rbp+arg_30]
0x180002d0f  mov     rdi, [rbp+arg_28]
0x180002d13  mov     rsi, [rbp+arg_20]
0x180002d17  cmp     ecx, 1
0x180002d1a  jz      short loc_180002D34
0x180002d1c  mov     eax, 2FAEh
0x180002d21  lea     ecx, [rax-1]
0x180002d24  lea     edx, [rax-2]
0x180002d27  lea     r8d, [rax-3]
0x180002d2b  lea     r9d, [rax-4]
0x180002d2f  jmp     loc_180003715
0x180002d34  mov     eax, 2FCCh
0x180002d39  lea     ecx, [rax-1]
0x180002d3c  lea     edx, [rax-2]
0x180002d3f  lea     r8d, [rax-3]
0x180002d43  lea     r9d, [rax-4]
0x180002d47  jmp     loc_180003715
0x180002d4c  mov     eax, 2FC6h
0x180002d51  lea     ecx, [rax-1]
0x180002d54  lea     edx, [rax-2]
0x180002d57  lea     r8d, [rax-3]
0x180002d5b  lea     r9d, [rax-4]
0x180002d5f  jmp     loc_180003701
0x180002d64  mov     eax, 2FC0h
0x180002d69  lea     ecx, [rax-1]
0x180002d6c  lea     edx, [rax-2]
0x180002d6f  lea     r8d, [rax-3]
0x180002d73  lea     r9d, [rax-4]
0x180002d77  jmp     loc_180003701
0x180002d7c  mov     eax, 2FBAh
0x180002d81  lea     ecx, [rax-1]
0x180002d84  lea     edx, [rax-2]
0x180002d87  lea     r8d, [rax-3]
0x180002d8b  lea     r9d, [rax-4]
0x180002d8f  jmp     loc_180003701
0x180002d94  mov     eax, 2FB4h
0x180002d99  lea     ecx, [rax-1]
0x180002d9c  lea     edx, [rax-2]
0x180002d9f  lea     r8d, [rax-3]
0x180002da3  lea     r9d, [rax-4]
0x180002da7  jmp     loc_180003701
0x180002dac  movzx   ecx, r8w; jumptable 0000000180002CC9 case 403
0x180002db0  cmp     ecx, 0Ah
0x180002db3  ja      loc_180002ECF
0x180002db9  jz      loc_180002EB7
0x180002dbf  sub     ecx, 1
0x180002dc2  jz      loc_180002E9F
0x180002dc8  sub     ecx, 1
0x180002dcb  jz      loc_180002E87
0x180002dd1  sub     ecx, 1
0x180002dd4  jz      loc_180002E6F
0x180002dda  sub     ecx, 1
0x180002ddd  jz      short loc_180002E57
0x180002ddf  sub     ecx, 1
0x180002de2  jz      short loc_180002E3F
0x180002de4  sub     ecx, 1
0x180002de7  jz      short loc_180002E27
0x180002de9  sub     ecx, 1
0x180002dec  jz      short loc_180002E0F
0x180002dee  cmp     ecx, 1
0x180002df1  jnz     loc_180002EFE
0x180002df7  mov     eax, 3002h
0x180002dfc  lea     ecx, [rax-1]
0x180002dff  lea     edx, [rax-2]
0x180002e02  lea     r8d, [rax-3]
0x180002e06  lea     r9d, [rax-4]
0x180002e0a  jmp     loc_180003701
0x180002e0f  mov     eax, 2FFCh
0x180002e14  lea     ecx, [rax-1]
0x180002e17  lea     edx, [rax-2]
0x180002e1a  lea     r8d, [rax-3]
0x180002e1e  lea     r9d, [rax-4]
0x180002e22  jmp     loc_180003701
0x180002e27  mov     eax, 2FF6h
0x180002e2c  lea     ecx, [rax-1]
0x180002e2f  lea     edx, [rax-2]
0x180002e32  lea     r8d, [rax-3]
0x180002e36  lea     r9d, [rax-4]
0x180002e3a  jmp     loc_180003701
0x180002e3f  mov     eax, 2FF0h
0x180002e44  lea     ecx, [rax-1]
0x180002e47  lea     edx, [rax-2]
0x180002e4a  lea     r8d, [rax-3]
0x180002e4e  lea     r9d, [rax-4]
0x180002e52  jmp     loc_180003701
0x180002e57  mov     eax, 2FEAh
0x180002e5c  lea     ecx, [rax-1]
0x180002e5f  lea     edx, [rax-2]
0x180002e62  lea     r8d, [rax-3]
0x180002e66  lea     r9d, [rax-4]
0x180002e6a  jmp     loc_180003701
0x180002e6f  mov     eax, 2FE4h
0x180002e74  lea     ecx, [rax-1]
0x180002e77  lea     edx, [rax-2]
0x180002e7a  lea     r8d, [rax-3]
0x180002e7e  lea     r9d, [rax-4]
0x180002e82  jmp     loc_180003701
0x180002e87  mov     eax, 2FDEh
0x180002e8c  lea     ecx, [rax-1]
0x180002e8f  lea     edx, [rax-2]
0x180002e92  lea     r8d, [rax-3]
0x180002e96  lea     r9d, [rax-4]
0x180002e9a  jmp     loc_180003701
0x180002e9f  mov     eax, 2FD8h
0x180002ea4  lea     ecx, [rax-1]
0x180002ea7  lea     edx, [rax-2]
0x180002eaa  lea     r8d, [rax-3]
0x180002eae  lea     r9d, [rax-4]
0x180002eb2  jmp     loc_180003701
0x180002eb7  mov     eax, 30E6h
0x180002ebc  lea     ecx, [rax-1]
0x180002ebf  lea     edx, [rax-2]
0x180002ec2  lea     r8d, [rax-3]
0x180002ec6  lea     r9d, [rax-4]
0x180002eca  jmp     loc_180003701
0x180002ecf  sub     ecx, 0Ch
0x180002ed2  jz      loc_180002FA6
0x180002ed8  sub     ecx, 1
0x180002edb  jz      loc_180002F8E
0x180002ee1  sub     ecx, 1
0x180002ee4  jz      loc_180002F76
0x180002eea  sub     ecx, 2
0x180002eed  jz      short loc_180002F5E
0x180002eef  sub     ecx, 1
0x180002ef2  jz      short loc_180002F46
0x180002ef4  sub     ecx, 1
0x180002ef7  jz      short loc_180002F2E
0x180002ef9  cmp     ecx, 1
0x180002efc  jz      short loc_180002F16
0x180002efe  mov     eax, 2FD2h
0x180002f03  lea     ecx, [rax-1]
0x180002f06  lea     edx, [rax-2]
0x180002f09  lea     r8d, [rax-3]
0x180002f0d  lea     r9d, [rax-4]
0x180002f11  jmp     loc_180003701
0x180002f16  mov     eax, 302Ch
0x180002f1b  lea     ecx, [rax-1]
0x180002f1e  lea     edx, [rax-2]
0x180002f21  lea     r8d, [rax-3]
0x180002f25  lea     r9d, [rax-4]
0x180002f29  jmp     loc_180003701
0x180002f2e  mov     eax, 3026h
0x180002f33  lea     ecx, [rax-1]
0x180002f36  lea     edx, [rax-2]
0x180002f39  lea     r8d, [rax-3]
0x180002f3d  lea     r9d, [rax-4]
0x180002f41  jmp     loc_180003701
0x180002f46  mov     eax, 3020h
0x180002f4b  lea     ecx, [rax-1]
0x180002f4e  lea     edx, [rax-2]
0x180002f51  lea     r8d, [rax-3]
0x180002f55  lea     r9d, [rax-4]
0x180002f59  jmp     loc_180003701
0x180002f5e  mov     eax, 301Ah
0x180002f63  lea     ecx, [rax-1]
0x180002f66  lea     edx, [rax-2]
0x180002f69  lea     r8d, [rax-3]
0x180002f6d  lea     r9d, [rax-4]
0x180002f71  jmp     loc_180003701
0x180002f76  mov     eax, 3014h
0x180002f7b  lea     ecx, [rax-1]
0x180002f7e  lea     edx, [rax-2]
0x180002f81  lea     r8d, [rax-3]
0x180002f85  lea     r9d, [rax-4]
0x180002f89  jmp     loc_180003701
0x180002f8e  mov     eax, 300Eh
0x180002f93  lea     ecx, [rax-1]
0x180002f96  lea     edx, [rax-2]
0x180002f99  lea     r8d, [rax-3]
0x180002f9d  lea     r9d, [rax-4]
0x180002fa1  jmp     loc_180003701
0x180002fa6  mov     eax, 3008h
0x180002fab  lea     ecx, [rax-1]
0x180002fae  lea     edx, [rax-2]
0x180002fb1  lea     r8d, [rax-3]
0x180002fb5  lea     r9d, [rax-4]
0x180002fb9  jmp     loc_180003701
0x180002fbe  movzx   ecx, r8w; jumptable 0000000180002CC9 case 404
0x180002fc2  cmp     ecx, 0Ch
0x180002fc5  ja      loc_180003102
0x180002fcb  jz      loc_1800030EA
0x180002fd1  sub     ecx, 2
0x180002fd4  jz      loc_1800030D2
0x180002fda  sub     ecx, 1
0x180002fdd  jz      loc_1800030BA
0x180002fe3  sub     ecx, 1
0x180002fe6  jz      loc_1800030A2
0x180002fec  sub     ecx, 1
0x180002fef  jz      loc_18000308A
0x180002ff5  sub     ecx, 1
0x180002ff8  jz      short loc_180003072
0x180002ffa  sub     ecx, 1
0x180002ffd  jz      short loc_18000305A
0x180002fff  sub     ecx, 1
0x180003002  jz      short loc_180003042
0x180003004  sub     ecx, 1
0x180003007  jz      short loc_18000302A
0x180003009  cmp     ecx, 2
0x18000300c  jnz     loc_18000313A
0x180003012  mov     eax, 306Eh
0x180003017  lea     ecx, [rax-1]
0x18000301a  lea     edx, [rax-2]
0x18000301d  lea     r8d, [rax-3]
0x180003021  lea     r9d, [rax-4]
0x180003025  jmp     loc_180003701
0x18000302a  mov     eax, 3062h
0x18000302f  lea     ecx, [rax-1]
0x180003032  lea     edx, [rax-2]
0x180003035  lea     r8d, [rax-3]
0x180003039  lea     r9d, [rax-4]
0x18000303d  jmp     loc_180003701
0x180003042  mov     eax, 305Ch
0x180003047  lea     ecx, [rax-1]
0x18000304a  lea     edx, [rax-2]
0x18000304d  lea     r8d, [rax-3]
0x180003051  lea     r9d, [rax-4]
0x180003055  jmp     loc_180003701
0x18000305a  mov     eax, 3056h
0x18000305f  lea     ecx, [rax-1]
0x180003062  lea     edx, [rax-2]
0x180003065  lea     r8d, [rax-3]
0x180003069  lea     r9d, [rax-4]
0x18000306d  jmp     loc_180003701
0x180003072  mov     eax, 3050h
0x180003077  lea     ecx, [rax-1]
0x18000307a  lea     edx, [rax-2]
0x18000307d  lea     r8d, [rax-3]
0x180003081  lea     r9d, [rax-4]
0x180003085  jmp     loc_180003701
0x18000308a  mov     eax, 304Ah
0x18000308f  lea     ecx, [rax-1]
0x180003092  lea     edx, [rax-2]
0x180003095  lea     r8d, [rax-3]
0x180003099  lea     r9d, [rax-4]
0x18000309d  jmp     loc_180003701
0x1800030a2  mov     eax, 3044h
0x1800030a7  lea     ecx, [rax-1]
0x1800030aa  lea     edx, [rax-2]
0x1800030ad  lea     r8d, [rax-3]
0x1800030b1  lea     r9d, [rax-4]
0x1800030b5  jmp     loc_180003701
0x1800030ba  mov     eax, 303Eh
0x1800030bf  lea     ecx, [rax-1]
0x1800030c2  lea     edx, [rax-2]
0x1800030c5  lea     r8d, [rax-3]
0x1800030c9  lea     r9d, [rax-4]
0x1800030cd  jmp     loc_180003701
0x1800030d2  mov     eax, 3038h
0x1800030d7  lea     ecx, [rax-1]
0x1800030da  lea     edx, [rax-2]
0x1800030dd  lea     r8d, [rax-3]
0x1800030e1  lea     r9d, [rax-4]
0x1800030e5  jmp     loc_180003701
0x1800030ea  mov     eax, 3074h
0x1800030ef  lea     ecx, [rax-1]
0x1800030f2  lea     edx, [rax-2]
0x1800030f5  lea     r8d, [rax-3]
0x1800030f9  lea     r9d, [rax-4]
0x1800030fd  jmp     loc_180003701
0x180003102  sub     ecx, 0Eh
0x180003105  jz      loc_1800031FA
0x18000310b  sub     ecx, 1
0x18000310e  jz      loc_1800031E2
0x180003114  sub     ecx, 1
0x180003117  jz      loc_1800031CA
  ... truncated ...
```

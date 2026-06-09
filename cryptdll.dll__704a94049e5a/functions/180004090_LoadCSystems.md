# LoadCSystems

- ea: `0x180004090`
- end: `0x180004675`
- name: `LoadCSystems`
- size: `1509`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005658`

## callees

- `0x180004090`

## pseudocode

```c
__int64 LoadCSystems()
{
  __int64 v0; // rax
  unsigned int v1; // ecx
  __int128 v2; // xmm1
  unsigned __int64 v3; // rax
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  unsigned int v10; // ecx
  __int128 v11; // xmm1
  __int64 v12; // rax
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  unsigned int v19; // ecx
  __int64 v20; // rax
  unsigned int v21; // ecx
  __int128 v22; // xmm1
  __int64 v23; // rax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  unsigned int v30; // ecx
  __int128 v31; // xmm1
  __int64 v32; // rax
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  unsigned int v39; // ecx
  __int64 v40; // rax
  unsigned int v41; // ecx
  __int64 v42; // rax
  unsigned int v43; // ecx
  __int64 v44; // rax
  unsigned int v45; // ecx
  __int128 v46; // xmm1
  __int64 v47; // rax
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  unsigned int v54; // ecx
  __int128 v55; // xmm1
  __int64 v56; // rax
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  unsigned int v63; // ecx
  __int128 v64; // xmm1
  __int64 v65; // rax
  __int128 v66; // xmm0
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  unsigned int v72; // ecx
  __int128 v73; // xmm1
  __int64 v74; // rax
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm0
  __int128 v80; // xmm1
  int v81; // ecx
  __int128 v82; // xmm1
  __int64 v83; // rax
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm0
  __int128 v89; // xmm1

  v0 = (unsigned int)cCSystems;
  v1 = cCSystems + 1;
  if ( (unsigned int)(cCSystems + 1) < 0x18 )
  {
    v2 = xmmword_18000E090;
    v3 = (unsigned __int64)(unsigned int)cCSystems << 7;
    *(_OWORD *)((char *)CSystems + v3) = csAESk256;
    v4 = *(_OWORD *)&off_18000E0A0;
    *(_OWORD *)((char *)&CSystems[2] + v3) = v2;
    v5 = *(_OWORD *)&off_18000E0B0;
    *(_OWORD *)((char *)&CSystems[4] + v3) = v4;
    v6 = *(_OWORD *)off_18000E0C0;
    *(_OWORD *)((char *)&CSystems[6] + v3) = v5;
    v7 = *(_OWORD *)off_18000E0D0;
    *(_OWORD *)((char *)&CSystems[8] + v3) = v6;
    v8 = xmmword_18000E0E0;
    *(_OWORD *)((char *)&CSystems[10] + v3) = v7;
    v9 = *(_OWORD *)&off_18000E0F0;
    *(_OWORD *)((char *)&CSystems[12] + v3) = v8;
    *(_OWORD *)((char *)&CSystems[14] + v3) = v9;
    v0 = v1;
    cCSystems = v1;
  }
  v10 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v11 = xmmword_18000E110;
    v12 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v12) = csAESk128;
    v13 = *(_OWORD *)&off_18000E120;
    *(_OWORD *)((char *)&CSystems[2] + v12) = v11;
    v14 = *(_OWORD *)&off_18000E130;
    *(_OWORD *)((char *)&CSystems[4] + v12) = v13;
    v15 = *(_OWORD *)off_18000E140;
    *(_OWORD *)((char *)&CSystems[6] + v12) = v14;
    v16 = *(_OWORD *)off_18000E150;
    *(_OWORD *)((char *)&CSystems[8] + v12) = v15;
    v17 = xmmword_18000E160;
    *(_OWORD *)((char *)&CSystems[10] + v12) = v16;
    v18 = *(_OWORD *)&off_18000E170;
    *(_OWORD *)((char *)&CSystems[12] + v12) = v17;
    *(_OWORD *)((char *)&CSystems[14] + v12) = v18;
    v0 = v10;
    cCSystems = v10;
  }
  v19 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v20 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v20) = csRC4_HMAC;
    *(_OWORD *)((char *)&CSystems[2] + v20) = xmmword_18000A2F0;
    *(_OWORD *)((char *)&CSystems[4] + v20) = *(_OWORD *)&off_18000A300;
    *(_OWORD *)((char *)&CSystems[6] + v20) = *(_OWORD *)off_18000A310;
    *(_OWORD *)((char *)&CSystems[8] + v20) = *(_OWORD *)off_18000A320;
    *(_OWORD *)((char *)&CSystems[10] + v20) = *(_OWORD *)&off_18000A330;
    *(_OWORD *)((char *)&CSystems[12] + v20) = xmmword_18000A340;
    *(_OWORD *)((char *)&CSystems[14] + v20) = *(_OWORD *)&off_18000A350;
    v0 = v19;
    cCSystems = v19;
  }
  v21 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v22 = xmmword_18000E390;
    v23 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v23) = csRC4_HMAC_OLD;
    v24 = *(_OWORD *)&off_18000E3A0;
    *(_OWORD *)((char *)&CSystems[2] + v23) = v22;
    v25 = *(_OWORD *)&off_18000E3B0;
    *(_OWORD *)((char *)&CSystems[4] + v23) = v24;
    v26 = *(_OWORD *)off_18000E3C0;
    *(_OWORD *)((char *)&CSystems[6] + v23) = v25;
    v27 = *(_OWORD *)&off_18000E3D0;
    *(_OWORD *)((char *)&CSystems[8] + v23) = v26;
    v28 = xmmword_18000E3E0;
    *(_OWORD *)((char *)&CSystems[10] + v23) = v27;
    v29 = xmmword_18000E3F0;
    *(_OWORD *)((char *)&CSystems[12] + v23) = v28;
    *(_OWORD *)((char *)&CSystems[14] + v23) = v29;
    v0 = v21;
    cCSystems = v21;
  }
  v30 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v31 = xmmword_18000E410;
    v32 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v32) = csRC4_MD4;
    v33 = *(_OWORD *)&off_18000E420;
    *(_OWORD *)((char *)&CSystems[2] + v32) = v31;
    v34 = *(_OWORD *)&off_18000E430;
    *(_OWORD *)((char *)&CSystems[4] + v32) = v33;
    v35 = *(_OWORD *)off_18000E440;
    *(_OWORD *)((char *)&CSystems[6] + v32) = v34;
    v36 = *(_OWORD *)&off_18000E450;
    *(_OWORD *)((char *)&CSystems[8] + v32) = v35;
    v37 = xmmword_18000E460;
    *(_OWORD *)((char *)&CSystems[10] + v32) = v36;
    v38 = xmmword_18000E470;
    *(_OWORD *)((char *)&CSystems[12] + v32) = v37;
    *(_OWORD *)((char *)&CSystems[14] + v32) = v38;
    v0 = v30;
    cCSystems = v30;
  }
  v39 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v40 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v40) = csRC4_PLAIN;
    *(_OWORD *)((char *)&CSystems[2] + v40) = xmmword_18000A270;
    *(_OWORD *)((char *)&CSystems[4] + v40) = *(_OWORD *)&off_18000A280;
    *(_OWORD *)((char *)&CSystems[6] + v40) = *(_OWORD *)off_18000A290;
    *(_OWORD *)((char *)&CSystems[8] + v40) = *(_OWORD *)off_18000A2A0;
    *(_OWORD *)((char *)&CSystems[10] + v40) = *(_OWORD *)&off_18000A2B0;
    *(_OWORD *)((char *)&CSystems[12] + v40) = xmmword_18000A2C0;
    *(_OWORD *)((char *)&CSystems[14] + v40) = xmmword_18000A2D0;
    v0 = v39;
    cCSystems = v39;
  }
  v41 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v42 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v42) = csRC4_PLAIN_EXP;
    *(_OWORD *)((char *)&CSystems[2] + v42) = xmmword_18000A3F0;
    *(_OWORD *)((char *)&CSystems[4] + v42) = *(_OWORD *)&off_18000A400;
    *(_OWORD *)((char *)&CSystems[6] + v42) = *(_OWORD *)off_18000A410;
    *(_OWORD *)((char *)&CSystems[8] + v42) = *(_OWORD *)off_18000A420;
    *(_OWORD *)((char *)&CSystems[10] + v42) = *(_OWORD *)&off_18000A430;
    *(_OWORD *)((char *)&CSystems[12] + v42) = xmmword_18000A440;
    *(_OWORD *)((char *)&CSystems[14] + v42) = xmmword_18000A450;
    v0 = v41;
    cCSystems = v41;
  }
  v43 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v44 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v44) = csRC4_HMAC_EXP;
    *(_OWORD *)((char *)&CSystems[2] + v44) = xmmword_18000A370;
    *(_OWORD *)((char *)&CSystems[4] + v44) = *(_OWORD *)&off_18000A380;
    *(_OWORD *)((char *)&CSystems[6] + v44) = *(_OWORD *)off_18000A390;
    *(_OWORD *)((char *)&CSystems[8] + v44) = *(_OWORD *)off_18000A3A0;
    *(_OWORD *)((char *)&CSystems[10] + v44) = *(_OWORD *)&off_18000A3B0;
    *(_OWORD *)((char *)&CSystems[12] + v44) = xmmword_18000A3C0;
    *(_OWORD *)((char *)&CSystems[14] + v44) = *(_OWORD *)&off_18000A3D0;
    v0 = v43;
    cCSystems = v43;
  }
  v45 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v46 = xmmword_18000E290;
    v47 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v47) = csRC4_HMAC_OLD_EXP;
    v48 = *(_OWORD *)&off_18000E2A0;
    *(_OWORD *)((char *)&CSystems[2] + v47) = v46;
    v49 = *(_OWORD *)&off_18000E2B0;
    *(_OWORD *)((char *)&CSystems[4] + v47) = v48;
    v50 = *(_OWORD *)off_18000E2C0;
    *(_OWORD *)((char *)&CSystems[6] + v47) = v49;
    v51 = *(_OWORD *)&off_18000E2D0;
    *(_OWORD *)((char *)&CSystems[8] + v47) = v50;
    v52 = xmmword_18000E2E0;
    *(_OWORD *)((char *)&CSystems[10] + v47) = v51;
    v53 = xmmword_18000E2F0;
    *(_OWORD *)((char *)&CSystems[12] + v47) = v52;
    *(_OWORD *)((char *)&CSystems[14] + v47) = v53;
    v0 = v45;
    cCSystems = v45;
  }
  v54 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v55 = xmmword_18000E210;
    v56 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v56) = csRC4_PLAIN_OLD;
    v57 = *(_OWORD *)&off_18000E220;
    *(_OWORD *)((char *)&CSystems[2] + v56) = v55;
    v58 = *(_OWORD *)&off_18000E230;
    *(_OWORD *)((char *)&CSystems[4] + v56) = v57;
    v59 = *(_OWORD *)off_18000E240;
    *(_OWORD *)((char *)&CSystems[6] + v56) = v58;
    v60 = *(_OWORD *)&off_18000E250;
    *(_OWORD *)((char *)&CSystems[8] + v56) = v59;
    v61 = xmmword_18000E260;
    *(_OWORD *)((char *)&CSystems[10] + v56) = v60;
    v62 = xmmword_18000E270;
    *(_OWORD *)((char *)&CSystems[12] + v56) = v61;
    *(_OWORD *)((char *)&CSystems[14] + v56) = v62;
    v0 = v54;
    cCSystems = v54;
  }
  v63 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v64 = xmmword_18000E310;
    v65 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v65) = csRC4_PLAIN_OLD_EXP;
    v66 = *(_OWORD *)&off_18000E320;
    *(_OWORD *)((char *)&CSystems[2] + v65) = v64;
    v67 = *(_OWORD *)&off_18000E330;
    *(_OWORD *)((char *)&CSystems[4] + v65) = v66;
    v68 = *(_OWORD *)off_18000E340;
    *(_OWORD *)((char *)&CSystems[6] + v65) = v67;
    v69 = *(_OWORD *)&off_18000E350;
    *(_OWORD *)((char *)&CSystems[8] + v65) = v68;
    v70 = xmmword_18000E360;
    *(_OWORD *)((char *)&CSystems[10] + v65) = v69;
    v71 = xmmword_18000E370;
    *(_OWORD *)((char *)&CSystems[12] + v65) = v70;
    *(_OWORD *)((char *)&CSystems[14] + v65) = v71;
    v0 = v63;
    cCSystems = v63;
  }
  v72 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v73 = xmmword_18000E010;
    v74 = v0 << 7;
    *(_OWORD *)((char *)CSystems + v74) = csAESk256Plain;
    v75 = *(_OWORD *)&off_18000E020;
    *(_OWORD *)((char *)&CSystems[2] + v74) = v73;
    v76 = xmmword_18000E030;
    *(_OWORD *)((char *)&CSystems[4] + v74) = v75;
    v77 = *(_OWORD *)off_18000E040;
    *(_OWORD *)((char *)&CSystems[6] + v74) = v76;
    v78 = *(_OWORD *)off_18000E050;
    *(_OWORD *)((char *)&CSystems[8] + v74) = v77;
    v79 = *(_OWORD *)&off_18000E060;
    *(_OWORD *)((char *)&CSystems[10] + v74) = v78;
    v80 = xmmword_18000E070;
    *(_OWORD *)((char *)&CSystems[12] + v74) = v79;
    *(_OWORD *)((char *)&CSystems[14] + v74) = v80;
    v0 = v72;
    cCSystems = v72;
  }
  v81 = v0 + 1;
  if ( (unsigned int)(v0 + 1) < 0x18 )
  {
    v82 = xmmword_18000E190;
    v83 = v0 << 7;
    cCSystems = v81;
    *(_OWORD *)((char *)CSystems + v83) = csAESk128Plain;
    v84 = *(_OWORD *)&off_18000E1A0;
    *(_OWORD *)((char *)&CSystems[2] + v83) = v82;
    v85 = xmmword_18000E1B0;
    *(_OWORD *)((char *)&CSystems[4] + v83) = v84;
    v86 = *(_OWORD *)off_18000E1C0;
    *(_OWORD *)((char *)&CSystems[6] + v83) = v85;
    v87 = *(_OWORD *)off_18000E1D0;
    *(_OWORD *)((char *)&CSystems[8] + v83) = v86;
    v88 = *(_OWORD *)&off_18000E1E0;
    *(_OWORD *)((char *)&CSystems[10] + v83) = v87;
    v89 = xmmword_18000E1F0;
    *(_OWORD *)((char *)&CSystems[12] + v83) = v88;
    *(_OWORD *)((char *)&CSystems[14] + v83) = v89;
  }
  return 0;
}

```

## disassembly

```asm
0x180004090  mov     eax, cs:cCSystems
0x180004096  lea     rdx, CSystems
0x18000409d  lea     ecx, [rax+1]
0x1800040a0  cmp     ecx, 18h
0x1800040a3  jnb     short loc_180004110
0x1800040a5  movaps  xmm0, cs:csAESk256
0x1800040ac  movaps  xmm1, cs:xmmword_18000E090
0x1800040b3  shl     rax, 7
0x1800040b7  movups  xmmword ptr [rax+rdx], xmm0
0x1800040bb  movaps  xmm0, xmmword ptr cs:off_18000E0A0; "Kerberos AES256-CTS-HMAC-SHA1-96"
0x1800040c2  movups  xmmword ptr [rax+rdx+10h], xmm1
0x1800040c7  movaps  xmm1, xmmword ptr cs:off_18000E0B0
0x1800040ce  movups  xmmword ptr [rax+rdx+20h], xmm0
0x1800040d3  movaps  xmm0, xmmword ptr cs:off_18000E0C0
0x1800040da  movups  xmmword ptr [rax+rdx+30h], xmm1
0x1800040df  movaps  xmm1, xmmword ptr cs:off_18000E0D0
0x1800040e6  movups  xmmword ptr [rax+rdx+40h], xmm0
0x1800040eb  movaps  xmm0, cs:xmmword_18000E0E0
0x1800040f2  movups  xmmword ptr [rax+rdx+50h], xmm1
0x1800040f7  movaps  xmm1, xmmword ptr cs:off_18000E0F0
0x1800040fe  movups  xmmword ptr [rax+rdx+60h], xmm0
0x180004103  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004108  mov     eax, ecx
0x18000410a  mov     cs:cCSystems, eax
0x180004110  lea     ecx, [rax+1]
0x180004113  cmp     ecx, 18h
0x180004116  jnb     short loc_180004183
0x180004118  movaps  xmm0, cs:csAESk128
0x18000411f  movaps  xmm1, cs:xmmword_18000E110
0x180004126  shl     rax, 7
0x18000412a  movups  xmmword ptr [rax+rdx], xmm0
0x18000412e  movaps  xmm0, xmmword ptr cs:off_18000E120; "Kerberos AES128-CTS-HMAC-SHA1-96"
0x180004135  movups  xmmword ptr [rax+rdx+10h], xmm1
0x18000413a  movaps  xmm1, xmmword ptr cs:off_18000E130
0x180004141  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004146  movaps  xmm0, xmmword ptr cs:off_18000E140
0x18000414d  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004152  movaps  xmm1, xmmword ptr cs:off_18000E150
0x180004159  movups  xmmword ptr [rax+rdx+40h], xmm0
0x18000415e  movaps  xmm0, cs:xmmword_18000E160
0x180004165  movups  xmmword ptr [rax+rdx+50h], xmm1
0x18000416a  movaps  xmm1, xmmword ptr cs:off_18000E170
0x180004171  movups  xmmword ptr [rax+rdx+60h], xmm0
0x180004176  movups  xmmword ptr [rax+rdx+70h], xmm1
0x18000417b  mov     eax, ecx
0x18000417d  mov     cs:cCSystems, eax
0x180004183  lea     ecx, [rax+1]
0x180004186  cmp     ecx, 18h
0x180004189  jnb     short loc_1800041F6
0x18000418b  movaps  xmm0, cs:csRC4_HMAC
0x180004192  movaps  xmm1, cs:xmmword_18000A2F0
0x180004199  shl     rax, 7
0x18000419d  movups  xmmword ptr [rax+rdx], xmm0
0x1800041a1  movaps  xmm0, xmmword ptr cs:off_18000A300; "RSADSI RC4-HMAC"
0x1800041a8  movups  xmmword ptr [rax+rdx+10h], xmm1
0x1800041ad  movaps  xmm1, xmmword ptr cs:off_18000A310
0x1800041b4  movups  xmmword ptr [rax+rdx+20h], xmm0
0x1800041b9  movaps  xmm0, xmmword ptr cs:off_18000A320
0x1800041c0  movups  xmmword ptr [rax+rdx+30h], xmm1
0x1800041c5  movaps  xmm1, xmmword ptr cs:off_18000A330
0x1800041cc  movups  xmmword ptr [rax+rdx+40h], xmm0
0x1800041d1  movaps  xmm0, cs:xmmword_18000A340
0x1800041d8  movups  xmmword ptr [rax+rdx+50h], xmm1
0x1800041dd  movaps  xmm1, xmmword ptr cs:off_18000A350
0x1800041e4  movups  xmmword ptr [rax+rdx+60h], xmm0
0x1800041e9  movups  xmmword ptr [rax+rdx+70h], xmm1
0x1800041ee  mov     eax, ecx
0x1800041f0  mov     cs:cCSystems, eax
0x1800041f6  lea     ecx, [rax+1]
0x1800041f9  cmp     ecx, 18h
0x1800041fc  jnb     short loc_180004269
0x1800041fe  movaps  xmm0, cs:csRC4_HMAC_OLD
0x180004205  movaps  xmm1, cs:xmmword_18000E390
0x18000420c  shl     rax, 7
0x180004210  movups  xmmword ptr [rax+rdx], xmm0
0x180004214  movaps  xmm0, xmmword ptr cs:off_18000E3A0; "RSADSI RC4-HMAC"
0x18000421b  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004220  movaps  xmm1, xmmword ptr cs:off_18000E3B0
0x180004227  movups  xmmword ptr [rax+rdx+20h], xmm0
0x18000422c  movaps  xmm0, xmmword ptr cs:off_18000E3C0
0x180004233  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004238  movaps  xmm1, xmmword ptr cs:off_18000E3D0
0x18000423f  movups  xmmword ptr [rax+rdx+40h], xmm0
0x180004244  movaps  xmm0, cs:xmmword_18000E3E0
0x18000424b  movups  xmmword ptr [rax+rdx+50h], xmm1
0x180004250  movaps  xmm1, cs:xmmword_18000E3F0
0x180004257  movups  xmmword ptr [rax+rdx+60h], xmm0
0x18000425c  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004261  mov     eax, ecx
0x180004263  mov     cs:cCSystems, eax
0x180004269  lea     ecx, [rax+1]
0x18000426c  cmp     ecx, 18h
0x18000426f  jnb     short loc_1800042DC
0x180004271  movaps  xmm0, cs:csRC4_MD4
0x180004278  movaps  xmm1, cs:xmmword_18000E410
0x18000427f  shl     rax, 7
0x180004283  movups  xmmword ptr [rax+rdx], xmm0
0x180004287  movaps  xmm0, xmmword ptr cs:off_18000E420; "RSADSI RC4-MD4"
0x18000428e  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004293  movaps  xmm1, xmmword ptr cs:off_18000E430
0x18000429a  movups  xmmword ptr [rax+rdx+20h], xmm0
0x18000429f  movaps  xmm0, xmmword ptr cs:off_18000E440
0x1800042a6  movups  xmmword ptr [rax+rdx+30h], xmm1
0x1800042ab  movaps  xmm1, xmmword ptr cs:off_18000E450
0x1800042b2  movups  xmmword ptr [rax+rdx+40h], xmm0
0x1800042b7  movaps  xmm0, cs:xmmword_18000E460
0x1800042be  movups  xmmword ptr [rax+rdx+50h], xmm1
0x1800042c3  movaps  xmm1, cs:xmmword_18000E470
0x1800042ca  movups  xmmword ptr [rax+rdx+60h], xmm0
0x1800042cf  movups  xmmword ptr [rax+rdx+70h], xmm1
0x1800042d4  mov     eax, ecx
0x1800042d6  mov     cs:cCSystems, eax
0x1800042dc  lea     ecx, [rax+1]
0x1800042df  cmp     ecx, 18h
0x1800042e2  jnb     short loc_18000434F
0x1800042e4  movaps  xmm0, cs:csRC4_PLAIN
0x1800042eb  movaps  xmm1, cs:xmmword_18000A270
0x1800042f2  shl     rax, 7
0x1800042f6  movups  xmmword ptr [rax+rdx], xmm0
0x1800042fa  movaps  xmm0, xmmword ptr cs:off_18000A280; "RSADSI RC4"
0x180004301  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004306  movaps  xmm1, xmmword ptr cs:off_18000A290
0x18000430d  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004312  movaps  xmm0, xmmword ptr cs:off_18000A2A0
0x180004319  movups  xmmword ptr [rax+rdx+30h], xmm1
0x18000431e  movaps  xmm1, xmmword ptr cs:off_18000A2B0
0x180004325  movups  xmmword ptr [rax+rdx+40h], xmm0
0x18000432a  movaps  xmm0, cs:xmmword_18000A2C0
0x180004331  movups  xmmword ptr [rax+rdx+50h], xmm1
0x180004336  movaps  xmm1, cs:xmmword_18000A2D0
0x18000433d  movups  xmmword ptr [rax+rdx+60h], xmm0
0x180004342  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004347  mov     eax, ecx
0x180004349  mov     cs:cCSystems, eax
0x18000434f  lea     ecx, [rax+1]
0x180004352  cmp     ecx, 18h
0x180004355  jnb     short loc_1800043C2
0x180004357  movaps  xmm0, cs:csRC4_PLAIN_EXP
0x18000435e  movaps  xmm1, cs:xmmword_18000A3F0
0x180004365  shl     rax, 7
0x180004369  movups  xmmword ptr [rax+rdx], xmm0
0x18000436d  movaps  xmm0, xmmword ptr cs:off_18000A400; "RSADSI RC4-EXP"
0x180004374  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004379  movaps  xmm1, xmmword ptr cs:off_18000A410
0x180004380  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004385  movaps  xmm0, xmmword ptr cs:off_18000A420
0x18000438c  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004391  movaps  xmm1, xmmword ptr cs:off_18000A430
0x180004398  movups  xmmword ptr [rax+rdx+40h], xmm0
0x18000439d  movaps  xmm0, cs:xmmword_18000A440
0x1800043a4  movups  xmmword ptr [rax+rdx+50h], xmm1
0x1800043a9  movaps  xmm1, cs:xmmword_18000A450
0x1800043b0  movups  xmmword ptr [rax+rdx+60h], xmm0
0x1800043b5  movups  xmmword ptr [rax+rdx+70h], xmm1
0x1800043ba  mov     eax, ecx
0x1800043bc  mov     cs:cCSystems, eax
0x1800043c2  lea     ecx, [rax+1]
0x1800043c5  cmp     ecx, 18h
0x1800043c8  jnb     short loc_180004435
0x1800043ca  movaps  xmm0, cs:csRC4_HMAC_EXP
0x1800043d1  movaps  xmm1, cs:xmmword_18000A370
0x1800043d8  shl     rax, 7
0x1800043dc  movups  xmmword ptr [rax+rdx], xmm0
0x1800043e0  movaps  xmm0, xmmword ptr cs:off_18000A380; "RSADSI RC4-HMAC"
0x1800043e7  movups  xmmword ptr [rax+rdx+10h], xmm1
0x1800043ec  movaps  xmm1, xmmword ptr cs:off_18000A390
0x1800043f3  movups  xmmword ptr [rax+rdx+20h], xmm0
0x1800043f8  movaps  xmm0, xmmword ptr cs:off_18000A3A0
0x1800043ff  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004404  movaps  xmm1, xmmword ptr cs:off_18000A3B0
0x18000440b  movups  xmmword ptr [rax+rdx+40h], xmm0
0x180004410  movaps  xmm0, cs:xmmword_18000A3C0
0x180004417  movups  xmmword ptr [rax+rdx+50h], xmm1
0x18000441c  movaps  xmm1, xmmword ptr cs:off_18000A3D0
0x180004423  movups  xmmword ptr [rax+rdx+60h], xmm0
0x180004428  movups  xmmword ptr [rax+rdx+70h], xmm1
0x18000442d  mov     eax, ecx
0x18000442f  mov     cs:cCSystems, eax
0x180004435  lea     ecx, [rax+1]
0x180004438  cmp     ecx, 18h
0x18000443b  jnb     short loc_1800044A8
0x18000443d  movaps  xmm0, cs:csRC4_HMAC_OLD_EXP
0x180004444  movaps  xmm1, cs:xmmword_18000E290
0x18000444b  shl     rax, 7
0x18000444f  movups  xmmword ptr [rax+rdx], xmm0
0x180004453  movaps  xmm0, xmmword ptr cs:off_18000E2A0; "RSADSI RC4-HMAC"
0x18000445a  movups  xmmword ptr [rax+rdx+10h], xmm1
0x18000445f  movaps  xmm1, xmmword ptr cs:off_18000E2B0
0x180004466  movups  xmmword ptr [rax+rdx+20h], xmm0
0x18000446b  movaps  xmm0, xmmword ptr cs:off_18000E2C0
0x180004472  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004477  movaps  xmm1, xmmword ptr cs:off_18000E2D0
0x18000447e  movups  xmmword ptr [rax+rdx+40h], xmm0
0x180004483  movaps  xmm0, cs:xmmword_18000E2E0
0x18000448a  movups  xmmword ptr [rax+rdx+50h], xmm1
0x18000448f  movaps  xmm1, cs:xmmword_18000E2F0
0x180004496  movups  xmmword ptr [rax+rdx+60h], xmm0
0x18000449b  movups  xmmword ptr [rax+rdx+70h], xmm1
0x1800044a0  mov     eax, ecx
0x1800044a2  mov     cs:cCSystems, eax
0x1800044a8  lea     ecx, [rax+1]
0x1800044ab  cmp     ecx, 18h
0x1800044ae  jnb     short loc_18000451B
0x1800044b0  movaps  xmm0, cs:csRC4_PLAIN_OLD
0x1800044b7  movaps  xmm1, cs:xmmword_18000E210
0x1800044be  shl     rax, 7
0x1800044c2  movups  xmmword ptr [rax+rdx], xmm0
0x1800044c6  movaps  xmm0, xmmword ptr cs:off_18000E220; "RSADSI RC4"
0x1800044cd  movups  xmmword ptr [rax+rdx+10h], xmm1
0x1800044d2  movaps  xmm1, xmmword ptr cs:off_18000E230
0x1800044d9  movups  xmmword ptr [rax+rdx+20h], xmm0
0x1800044de  movaps  xmm0, xmmword ptr cs:off_18000E240
0x1800044e5  movups  xmmword ptr [rax+rdx+30h], xmm1
0x1800044ea  movaps  xmm1, xmmword ptr cs:off_18000E250
0x1800044f1  movups  xmmword ptr [rax+rdx+40h], xmm0
0x1800044f6  movaps  xmm0, cs:xmmword_18000E260
0x1800044fd  movups  xmmword ptr [rax+rdx+50h], xmm1
0x180004502  movaps  xmm1, cs:xmmword_18000E270
0x180004509  movups  xmmword ptr [rax+rdx+60h], xmm0
0x18000450e  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004513  mov     eax, ecx
0x180004515  mov     cs:cCSystems, eax
0x18000451b  lea     ecx, [rax+1]
0x18000451e  cmp     ecx, 18h
0x180004521  jnb     short loc_18000458E
0x180004523  movaps  xmm0, cs:csRC4_PLAIN_OLD_EXP
0x18000452a  movaps  xmm1, cs:xmmword_18000E310
0x180004531  shl     rax, 7
0x180004535  movups  xmmword ptr [rax+rdx], xmm0
0x180004539  movaps  xmm0, xmmword ptr cs:off_18000E320; "RSADSI RC4-EXP"
0x180004540  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004545  movaps  xmm1, xmmword ptr cs:off_18000E330
0x18000454c  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004551  movaps  xmm0, xmmword ptr cs:off_18000E340
0x180004558  movups  xmmword ptr [rax+rdx+30h], xmm1
0x18000455d  movaps  xmm1, xmmword ptr cs:off_18000E350
0x180004564  movups  xmmword ptr [rax+rdx+40h], xmm0
0x180004569  movaps  xmm0, cs:xmmword_18000E360
0x180004570  movups  xmmword ptr [rax+rdx+50h], xmm1
0x180004575  movaps  xmm1, cs:xmmword_18000E370
0x18000457c  movups  xmmword ptr [rax+rdx+60h], xmm0
0x180004581  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004586  mov     eax, ecx
0x180004588  mov     cs:cCSystems, eax
0x18000458e  lea     ecx, [rax+1]
0x180004591  cmp     ecx, 18h
0x180004594  jnb     short loc_180004601
0x180004596  movaps  xmm0, cs:csAESk256Plain
0x18000459d  movaps  xmm1, cs:xmmword_18000E010
0x1800045a4  shl     rax, 7
0x1800045a8  movups  xmmword ptr [rax+rdx], xmm0
0x1800045ac  movaps  xmm0, xmmword ptr cs:off_18000E020; "Kerberos AES256-CTS-HMAC-SHA1-96-PLAIN"
0x1800045b3  movups  xmmword ptr [rax+rdx+10h], xmm1
0x1800045b8  movaps  xmm1, cs:xmmword_18000E030
0x1800045bf  movups  xmmword ptr [rax+rdx+20h], xmm0
0x1800045c4  movaps  xmm0, xmmword ptr cs:off_18000E040
0x1800045cb  movups  xmmword ptr [rax+rdx+30h], xmm1
0x1800045d0  movaps  xmm1, xmmword ptr cs:off_18000E050
0x1800045d7  movups  xmmword ptr [rax+rdx+40h], xmm0
0x1800045dc  movaps  xmm0, xmmword ptr cs:off_18000E060
0x1800045e3  movups  xmmword ptr [rax+rdx+50h], xmm1
0x1800045e8  movaps  xmm1, cs:xmmword_18000E070
0x1800045ef  movups  xmmword ptr [rax+rdx+60h], xmm0
0x1800045f4  movups  xmmword ptr [rax+rdx+70h], xmm1
0x1800045f9  mov     eax, ecx
0x1800045fb  mov     cs:cCSystems, eax
0x180004601  lea     ecx, [rax+1]
0x180004604  cmp     ecx, 18h
0x180004607  jnb     short loc_180004672
0x180004609  movaps  xmm0, cs:csAESk128Plain
0x180004610  movaps  xmm1, cs:xmmword_18000E190
0x180004617  shl     rax, 7
0x18000461b  mov     cs:cCSystems, ecx
0x180004621  movups  xmmword ptr [rax+rdx], xmm0
0x180004625  movaps  xmm0, xmmword ptr cs:off_18000E1A0; "Kerberos AES128-CTS-HMAC-SHA1-96-PLAIN"
0x18000462c  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004631  movaps  xmm1, cs:xmmword_18000E1B0
0x180004638  movups  xmmword ptr [rax+rdx+20h], xmm0
0x18000463d  movaps  xmm0, xmmword ptr cs:off_18000E1C0
0x180004644  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004649  movaps  xmm1, xmmword ptr cs:off_18000E1D0
0x180004650  movups  xmmword ptr [rax+rdx+40h], xmm0
0x180004655  movaps  xmm0, xmmword ptr cs:off_18000E1E0
0x18000465c  movups  xmmword ptr [rax+rdx+50h], xmm1
0x180004661  movaps  xmm1, cs:xmmword_18000E1F0
0x180004668  movups  xmmword ptr [rax+rdx+60h], xmm0
0x18000466d  movups  xmmword ptr [rax+rdx+70h], xmm1
0x180004672  xor     eax, eax
0x180004674  retn
```

# CompileFragments(x,x,x,x,x,x,x)

- ea: `0x1000646f`
- end: `0x1000683b`
- name: `_CompileFragments@28`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10006841`

## callees

- `0x100055d1`
- `0x1000646f`

## pseudocode

```c
int __fastcall CompileFragments(int a1, __int16 a2, __int16 a3, __int16 a4, int a5, int a6, int a7)
{
  int v8; // ecx
  int v9; // edx
  int v10; // eax
  int result; // eax
  int v12; // [esp-4h] [ebp-10h]

  v8 = 0;
  *(_WORD *)(a1 + 18) = a2 >> 1;
  v9 = (unsigned __int16)(a2 >> 1) * (a3 >> 1);
  *(_DWORD *)a1 = a1 + 2868;
  v10 = v9 + a1 + 2868;
  *(_DWORD *)(a1 + 4) = v10;
  *(_DWORD *)(a1 + 8) = v9 + v10;
  *(_WORD *)(a1 + 16) = a4;
  *(_DWORD *)(a1 + 12) = a5;
  switch ( a6 )
  {
    case 0:
      v12 = 4;
      *(_DWORD *)(a1 + 48) = a7 + 8;
      goto LABEL_11;
    case 1:
      v12 = 5;
      goto LABEL_11;
    case 2:
      v12 = 6;
      goto LABEL_11;
    case 3:
      v12 = 7;
      goto LABEL_11;
    case 4:
      v12 = 8;
LABEL_11:
      v8 = v12;
      break;
  }
  *(_WORD *)(a1 + 20) = 0;
  *(_DWORD *)(a1 + 1844) = 0;
  *(_DWORD *)(a1 + 1848) = 1;
  *(_DWORD *)(a1 + 1852) = 2;
  *(_DWORD *)(a1 + 1856) = v8;
  *(_DWORD *)(a1 + 1860) = 9;
  *(_DWORD *)(a1 + 1864) = 10;
  *(_DWORD *)(a1 + 1868) = 12;
  *(_DWORD *)(a1 + 1876) = v8;
  *(_DWORD *)(a1 + 1880) = 9;
  *(_DWORD *)(a1 + 1884) = 10;
  *(_DWORD *)(a1 + 1888) = 13;
  *(_DWORD *)(a1 + 1872) += 49157;
  *(_DWORD *)(a1 + 1892) = v8;
  *(_DWORD *)(a1 + 1896) = 9;
  *(_DWORD *)(a1 + 1900) = 11;
  *(_DWORD *)(a1 + 1904) = 14;
  *(_DWORD *)(a1 + 1908) = 15;
  *(_DWORD *)(a1 + 1912) = 49143;
  *(_DWORD *)(a1 + 1916) = 3;
  CopyFragments(2, 17);
  *(_DWORD *)(a1 + 1988) = 16;
  CopyFragments(2, 17);
  *(_DWORD *)(a1 + 1992) = 49170;
  *(_DWORD *)(a1 + 2064) = 17;
  *(_DWORD *)(a1 + 2068) = 20;
  *(_DWORD *)(a1 + 2072) = 22;
  *(_DWORD *)(a1 + 2076) = 24;
  *(_DWORD *)(a1 + 2080) = 49149;
  *(_DWORD *)(a1 + 2084) = 25;
  *(_DWORD *)(a1 + 2088) = 18;
  *(_DWORD *)(a1 + 2092) = 20;
  *(_DWORD *)(a1 + 2096) = 23;
  *(_DWORD *)(a1 + 2100) = 24;
  *(_DWORD *)(a1 + 2104) = 49149;
  *(_DWORD *)(a1 + 2108) = 26;
  *(_DWORD *)(a1 + 2112) = 19;
  *(_DWORD *)(a1 + 2116) = 20;
  *(_DWORD *)(a1 + 2120) = 23;
  *(_DWORD *)(a1 + 2124) = 24;
  *(_DWORD *)(a1 + 2128) = 49149;
  *(_DWORD *)(a1 + 2132) = 27;
  *(_DWORD *)(a1 + 2136) = 28;
  *(_DWORD *)(a1 + 2140) = 49097;
  *(_DWORD *)(a1 + 2144) = 29;
  *(_DWORD *)(a1 + 2148) = 30;
  *(_DWORD *)(a1 + 2152) = 32;
  *(_DWORD *)(a1 + 2160) = 33;
  *(_DWORD *)(a1 + 2156) = 49154;
  *(_DWORD *)(a1 + 2164) = 34;
  *(_DWORD *)(a1 + 2168) = 35;
  *(_DWORD *)(a1 + 2172) = 49149;
  *(_DWORD *)(a1 + 2176) = 31;
  CopyFragments(76, 8);
  *(_DWORD *)(a1 + 2212) = 16;
  CopyFragments(76, 8);
  *(_DWORD *)(a1 + 2216) = 49161;
  *(_DWORD *)(a1 + 2252) = 36;
  *(_DWORD *)(a1 + 2256) = 28;
  *(_DWORD *)(a1 + 2260) = 49132;
  *(_DWORD *)(a1 + 2264) = 37;
  *(_WORD *)(a1 + 22) = 106;
  *(_DWORD *)(a1 + 2268) = 0;
  *(_DWORD *)(a1 + 2272) = 38;
  *(_DWORD *)(a1 + 2276) = 39;
  *(_DWORD *)(a1 + 2280) = 41;
  *(_DWORD *)(a1 + 2288) = 42;
  *(_DWORD *)(a1 + 2284) = 49154;
  *(_DWORD *)(a1 + 2292) = 43;
  *(_DWORD *)(a1 + 2296) = 15;
  *(_DWORD *)(a1 + 2300) = 49149;
  *(_DWORD *)(a1 + 2304) = 40;
  CopyFragments(108, 8);
  *(_DWORD *)(a1 + 2340) = 16;
  CopyFragments(108, 8);
  *(_DWORD *)(a1 + 2344) = 49161;
  *(_DWORD *)(a1 + 2380) = 44;
  *(_DWORD *)(a1 + 2384) = 49133;
  *(_DWORD *)(a1 + 2388) = 45;
  *(_DWORD *)(a1 + 2392) = 46;
  *(_DWORD *)(a1 + 2396) = 48;
  *(_DWORD *)(a1 + 2404) = 49;
  *(_DWORD *)(a1 + 2400) = 49154;
  *(_DWORD *)(a1 + 2408) = 50;
  *(_DWORD *)(a1 + 2412) = 15;
  *(_DWORD *)(a1 + 2416) = 49149;
  *(_DWORD *)(a1 + 2420) = 47;
  CopyFragments(137, 8);
  *(_DWORD *)(a1 + 2456) = 16;
  CopyFragments(137, 8);
  *(_DWORD *)(a1 + 2460) = 49161;
  *(_DWORD *)(a1 + 2496) = 51;
  result = 1;
  *(_DWORD *)(a1 + 2500) = 49133;
  *(_DWORD *)(a1 + 2504) = 37;
  return result;
}

```

## disassembly

```asm
0x1000646f  mov     edi, edi
0x10006471  push    ebp
0x10006472  mov     ebp, esp
0x10006474  push    ebx
0x10006475  push    esi
0x10006476  mov     ax, dx
0x10006479  movsx   edx, [ebp+arg_0]
0x1000647d  sar     ax, 1
0x10006480  push    edi
0x10006481  mov     edi, ecx
0x10006483  sar     edx, 1
0x10006485  xor     ecx, ecx
0x10006487  mov     [edi+12h], ax
0x1000648b  lea     esi, [edi+0B34h]
0x10006491  movzx   eax, ax
0x10006494  imul    edx, eax
0x10006497  mov     [edi], esi
0x10006499  lea     eax, [edx+esi]
0x1000649c  mov     [edi+4], eax
0x1000649f  lea     esi, [edi+734h]
0x100064a5  add     eax, edx
0x100064a7  mov     [edi+8], eax
0x100064aa  mov     ax, [ebp+arg_4]
0x100064ae  mov     [edi+10h], ax
0x100064b2  mov     eax, [ebp+arg_8]
0x100064b5  mov     [edi+0Ch], eax
0x100064b8  mov     eax, [ebp+arg_C]
0x100064bb  sub     eax, ecx
0x100064bd  jz      short loc_100064E3
0x100064bf  sub     eax, 1
0x100064c2  jz      short loc_100064DF
0x100064c4  sub     eax, 1
0x100064c7  jz      short loc_100064DB
0x100064c9  sub     eax, 1
0x100064cc  jz      short loc_100064D7
0x100064ce  sub     eax, 1
0x100064d1  jnz     short loc_100064EF
0x100064d3  push    8
0x100064d5  jmp     short loc_100064EE
0x100064d7  push    7
0x100064d9  jmp     short loc_100064EE
0x100064db  push    6
0x100064dd  jmp     short loc_100064EE
0x100064df  push    5
0x100064e1  jmp     short loc_100064EE
0x100064e3  mov     eax, [ebp+arg_10]
0x100064e6  add     eax, 8
0x100064e9  push    4
0x100064eb  mov     [edi+30h], eax
0x100064ee  pop     ecx
0x100064ef  push    9
0x100064f1  pop     edx
0x100064f2  xor     eax, eax
0x100064f4  mov     [edi+14h], ax
0x100064f8  mov     [esi], eax
0x100064fa  mov     dword ptr [esi+4], 1
0x10006501  mov     dword ptr [esi+8], 2
0x10006508  mov     [esi+0Ch], ecx
0x1000650b  mov     [esi+10h], edx
0x1000650e  push    0Ah
0x10006510  pop     eax
0x10006511  mov     [esi+14h], eax
0x10006514  mov     dword ptr [esi+18h], 0Ch
0x1000651b  mov     [esi+20h], ecx
0x1000651e  mov     [esi+24h], edx
0x10006521  mov     [esi+28h], eax
0x10006524  mov     dword ptr [esi+2Ch], 0Dh
0x1000652b  add     dword ptr [esi+1Ch], 0C005h
0x10006532  push    11h
0x10006534  mov     [esi+30h], ecx
0x10006537  mov     ecx, esi
0x10006539  pop     ebx
0x1000653a  mov     [esi+34h], edx
0x1000653d  push    ebx
0x1000653e  mov     dword ptr [esi+38h], 0Bh
0x10006545  push    2
0x10006547  mov     dword ptr [esi+3Ch], 0Eh
0x1000654e  mov     dword ptr [esi+40h], 0Fh
0x10006555  push    13h
0x10006557  mov     dword ptr [esi+44h], 0BFF7h
0x1000655e  pop     edx
0x1000655f  mov     dword ptr [esi+48h], 3
0x10006566  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x1000656b  push    ebx
0x1000656c  push    2
0x1000656e  push    26h ; '&'
0x10006570  pop     edx
0x10006571  mov     ecx, esi
0x10006573  mov     dword ptr [esi+90h], 10h
0x1000657d  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x10006582  mov     dword ptr [esi+94h], 0C012h
0x1000658c  mov     [esi+0DCh], ebx
0x10006592  mov     ebx, 0BFFDh
0x10006597  push    14h
0x10006599  pop     edx
0x1000659a  mov     [esi+0E0h], edx
0x100065a0  mov     dword ptr [esi+0E4h], 16h
0x100065aa  push    18h
0x100065ac  pop     ecx
0x100065ad  mov     [esi+0E8h], ecx
0x100065b3  mov     [esi+0ECh], ebx
0x100065b9  mov     dword ptr [esi+0F0h], 19h
0x100065c3  mov     dword ptr [esi+0F4h], 12h
0x100065cd  mov     [esi+0F8h], edx
0x100065d3  push    17h
0x100065d5  pop     eax
0x100065d6  mov     [esi+0FCh], eax
0x100065dc  mov     [esi+100h], ecx
0x100065e2  mov     [esi+104h], ebx
0x100065e8  mov     dword ptr [esi+108h], 1Ah
0x100065f2  mov     dword ptr [esi+10Ch], 13h
0x100065fc  mov     [esi+110h], edx
0x10006602  mov     [esi+114h], eax
0x10006608  mov     [esi+118h], ecx
0x1000660e  mov     [esi+11Ch], ebx
0x10006614  mov     dword ptr [esi+120h], 1Bh
0x1000661e  push    1Ch
0x10006620  pop     ebx
0x10006621  mov     [esi+124h], ebx
0x10006627  mov     dword ptr [esi+128h], 0BFC9h
0x10006631  mov     dword ptr [esi+12Ch], 1Dh
0x1000663b  mov     dword ptr [esi+130h], 1Eh
0x10006645  mov     dword ptr [esi+134h], 20h ; ' '
0x1000664f  mov     dword ptr [esi+13Ch], 21h ; '!'
0x10006659  mov     dword ptr [esi+138h], 0C002h
0x10006663  mov     dword ptr [esi+140h], 22h ; '"'
0x1000666d  mov     dword ptr [esi+144h], 23h ; '#'
0x10006677  push    8
0x10006679  mov     dword ptr [esi+148h], 0BFFDh
0x10006683  mov     dword ptr [esi+14Ch], 1Fh
0x1000668d  push    4Ch ; 'L'
0x1000668f  push    54h ; 'T'
0x10006691  pop     edx
0x10006692  mov     ecx, esi
0x10006694  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x10006699  push    8
0x1000669b  push    4Ch ; 'L'
0x1000669d  push    5Eh ; '^'
0x1000669f  pop     edx
0x100066a0  mov     ecx, esi
0x100066a2  mov     dword ptr [esi+170h], 10h
0x100066ac  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x100066b1  mov     dword ptr [esi+174h], 0C009h
0x100066bb  mov     ecx, esi
0x100066bd  mov     dword ptr [esi+198h], 24h ; '$'
0x100066c7  mov     [esi+19Ch], ebx
0x100066cd  mov     dword ptr [esi+1A0h], 0BFECh
0x100066d7  mov     dword ptr [esi+1A4h], 25h ; '%'
0x100066e1  push    6Ah ; 'j'
0x100066e3  pop     eax
0x100066e4  mov     [edi+16h], ax
0x100066e8  mov     edi, 0C002h
0x100066ed  mov     dword ptr [esi+1A8h], 0
0x100066f7  mov     dword ptr [esi+1ACh], 26h ; '&'
0x10006701  mov     dword ptr [esi+1B0h], 27h ; '''
0x1000670b  mov     dword ptr [esi+1B4h], 29h ; ')'
0x10006715  mov     dword ptr [esi+1BCh], 2Ah ; '*'
0x1000671f  push    8
0x10006721  mov     [esi+1B8h], edi
0x10006727  push    6Ch ; 'l'
0x10006729  mov     dword ptr [esi+1C0h], 2Bh ; '+'
0x10006733  mov     dword ptr [esi+1C4h], 0Fh
0x1000673d  push    74h ; 't'
0x1000673f  mov     dword ptr [esi+1C8h], 0BFFDh
0x10006749  pop     edx
0x1000674a  mov     dword ptr [esi+1CCh], 28h ; '('
0x10006754  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x10006759  push    8
0x1000675b  push    6Ch ; 'l'
0x1000675d  push    7Eh ; '~'
0x1000675f  pop     edx
0x10006760  mov     ecx, esi
0x10006762  mov     dword ptr [esi+1F0h], 10h
0x1000676c  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x10006771  mov     dword ptr [esi+1F4h], 0C009h
0x1000677b  lea     ebx, [edi-15h]
0x1000677e  mov     dword ptr [esi+218h], 2Ch ; ','
0x10006788  mov     ecx, esi
0x1000678a  mov     [esi+21Ch], ebx
0x10006790  mov     dword ptr [esi+220h], 2Dh ; '-'
0x1000679a  mov     dword ptr [esi+224h], 2Eh ; '.'
0x100067a4  mov     dword ptr [esi+228h], 30h ; '0'
0x100067ae  mov     dword ptr [esi+230h], 31h ; '1'
0x100067b8  mov     [esi+22Ch], edi
0x100067be  mov     edi, 89h
0x100067c3  mov     dword ptr [esi+234h], 32h ; '2'
0x100067cd  mov     dword ptr [esi+238h], 0Fh
0x100067d7  push    8
0x100067d9  mov     dword ptr [esi+23Ch], 0BFFDh
0x100067e3  lea     edx, [edi+8]
0x100067e6  push    edi
0x100067e7  mov     dword ptr [esi+240h], 2Fh ; '/'
0x100067f1  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x100067f6  push    8
0x100067f8  push    edi
0x100067f9  lea     edx, [edi+12h]
0x100067fc  mov     dword ptr [esi+264h], 10h
0x10006806  mov     ecx, esi
0x10006808  call    _CopyFragments@16; CopyFragments(x,x,x,x)
0x1000680d  mov     dword ptr [esi+268h], 0C009h
0x10006817  xor     eax, eax
0x10006819  mov     dword ptr [esi+28Ch], 33h ; '3'
0x10006823  inc     eax
0x10006824  mov     [esi+290h], ebx
0x1000682a  pop     edi
0x1000682b  mov     dword ptr [esi+294h], 25h ; '%'
0x10006835  pop     esi
0x10006836  pop     ebx
0x10006837  pop     ebp
0x10006838  retn    14h
```

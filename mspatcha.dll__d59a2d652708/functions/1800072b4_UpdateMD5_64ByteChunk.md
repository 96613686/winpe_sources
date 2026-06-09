# UpdateMD5_64ByteChunk

- ea: `0x1800072b4`
- end: `0x180007b46`
- name: `UpdateMD5_64ByteChunk`
- size: `2194`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180007090`

## pseudocode

```c
__int64 __fastcall UpdateMD5_64ByteChunk(_DWORD *a1, _DWORD *a2)
{
  int v2; // r11d
  _DWORD *v3; // rsi
  int v4; // r10d
  int v5; // r9d
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  int v10; // edx
  int v11; // r15d
  int v12; // r12d
  int v13; // r14d
  int v14; // r8d
  int v15; // r9d
  int v16; // r10d
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  int v20; // edi
  int v21; // r13d
  int v22; // ebp
  int v23; // ebx
  int v24; // r11d
  int v25; // r10d
  int v26; // r9d
  int v27; // r8d
  int v28; // edx
  int v29; // r10d
  int v30; // r9d
  int v31; // r8d
  int v32; // edx
  int v33; // r10d
  int v34; // r9d
  int v35; // r8d
  int v36; // r11d
  int v37; // r10d
  int v38; // ebx
  int v39; // edx
  int v40; // r8d
  int v41; // r9d
  int v42; // r10d
  int v43; // edx
  int v44; // r8d
  int v45; // r9d
  int v46; // r10d
  int v47; // edx
  int v48; // r8d
  int v49; // r9d
  int v50; // r10d
  int v51; // r11d
  int v52; // r8d
  int v53; // r9d
  int v54; // edx
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  int v58; // edx
  int v59; // r10d
  int v60; // ecx
  int v61; // r9d
  int v62; // edx
  int v63; // r8d
  int v64; // r10d
  int v65; // ecx
  int v66; // edx
  int v67; // r8d
  int v68; // r9d
  int v69; // ecx
  int v70; // r10d
  int v71; // r8d
  int v72; // edx
  int v73; // ecx
  __int64 result; // rax
  int v75; // [rsp+0h] [rbp-68h]
  int v76; // [rsp+4h] [rbp-64h]
  int v77; // [rsp+8h] [rbp-60h]
  int v78; // [rsp+Ch] [rbp-5Ch]
  int v79; // [rsp+10h] [rbp-58h]
  int v80; // [rsp+14h] [rbp-54h]
  int v81; // [rsp+18h] [rbp-50h]
  int v83; // [rsp+78h] [rbp+10h]
  int v84; // [rsp+80h] [rbp+18h]
  int v85; // [rsp+88h] [rbp+20h]

  v2 = a1[1];
  v3 = a2;
  v4 = a1[2];
  v5 = a1[3];
  v83 = *a2;
  v6 = v2 + __ROL4__(*a2 + (v2 & v4 | v5 & ~v2) + *a1 - 680876936, 7);
  v85 = v3[1];
  v80 = v3[2];
  v7 = v6 + __ROL4__(v85 + (v2 & v6 | v4 & ~v6) + v5 - 389564586, 12);
  v84 = v3[3];
  v8 = v7 + __ROL4__(v80 + (v6 & v7 | v2 & ~v7) + v4 + 606105819, 17);
  v9 = v8 + __ROL4__(v84 + (v7 & v8 | v6 & ~v8) + v2 - 1044525330, 22);
  v76 = v3[4];
  v10 = v9 + __ROL4__(v6 + (v8 & v9 | v7 & ~v9) + v76 - 176418897, 7);
  v81 = v3[5];
  v11 = v3[7];
  v12 = v3[10];
  v13 = v3[12];
  v14 = v10 + __ROL4__(v7 + (v9 & v10 | v8 & ~v10) + v81 + 1200080426, 12);
  v75 = v3[6];
  v15 = v14 + __ROL4__(v8 + (v10 & v14 | v9 & ~v14) + v75 - 1473231341, 17);
  v79 = v3[8];
  v16 = v15 + __ROL4__(v9 + (v14 & v15 | v10 & ~v15) + v11 - 45705983, 22);
  v17 = v16 + __ROL4__(v10 + (v15 & v16 | v14 & ~v16) + v79 + 1770035416, 7);
  v78 = v3[9];
  v18 = v17 + __ROL4__(v14 + (v16 & v17 | v15 & ~v17) + v78 - 1958414417, 12);
  v77 = v3[11];
  v19 = v18 + __ROL4__(v15 + (v17 & v18 | v16 & ~v18) + v12 - 42063, 17);
  v20 = v19 + __ROL4__(v16 + (v18 & v19 | v17 & ~v19) + v77 - 1990404162, 22);
  v21 = v3[13];
  v22 = v3[14];
  LODWORD(v3) = v3[15];
  v23 = v20 + __ROL4__(v17 + (v19 & v20 | v18 & ~v20) + v13 + 1804603682, 7);
  v24 = v23 + __ROL4__(v18 + (v20 & v23 | v19 & ~v23) + v21 - 40341101, 12);
  v25 = v24 + __ROL4__(v19 + (v24 & v23 | ~v24 & v20) + v22 - 1502002290, 17);
  v26 = v25 + __ROL4__(v20 + (v24 & v25 | ~v25 & v23) + (_DWORD)v3 + 1236535329, 22);
  v27 = v26 + __ROL4__(v85 - 165796510 + v23 + (v24 & v26 | v25 & ~v24), 5);
  v28 = v27 + __ROL4__(v24 + v75 + (v25 & v27 | v26 & ~v25) - 1069501632, 9);
  v29 = v28 + __ROL4__(v77 + (v26 & v28 | v27 & ~v26) + 643717713 + v25, 14);
  v30 = v29 + __ROL4__(v83 + (v27 & v29 | v28 & ~v27) - 373897302 + v26, 20);
  v31 = v30 + __ROL4__(v81 + (v28 & v30 | v29 & ~v28) - 701558691 + v27, 5);
  v32 = v31 + __ROL4__(v12 + (v29 & v31 | v30 & ~v29) + 38016083 + v28, 9);
  v33 = v32 + __ROL4__((_DWORD)v3 + (v30 & v32 | v31 & ~v30) - 660478335 + v29, 14);
  v34 = v33 + __ROL4__(v76 + (v31 & v33 | v32 & ~v31) - 405537848 + v30, 20);
  v35 = v34 + __ROL4__(v78 + (v32 & v34 | v33 & ~v32) + 568446438 + v31, 5);
  v36 = v35 + __ROL4__(v32 + v22 + (v33 & v35 | v34 & ~v33) - 1019803690, 9);
  v37 = v36 + __ROL4__(v84 + (v34 & v36 | v35 & ~v34) - 187363961 + v33, 14);
  v38 = v37 + __ROL4__(v34 + v79 + (v35 & v37 | v36 & ~v35) + 1163531501, 20);
  v39 = v38 + __ROL4__(v21 + (v36 & v38 | v37 & ~v36) + v35 - 1444681467, 5);
  v40 = v39 + __ROL4__(v36 + v80 + (v37 & v39 | v38 & ~v37) - 51403784, 9);
  v41 = v40 + __ROL4__(v11 + (v38 & v40 | v39 & ~v38) + v37 + 1735328473, 14);
  v42 = v41 + __ROL4__(v13 + (v39 & v41 | v40 & ~v39) + v38 - 1926607734, 20);
  v43 = v42 + __ROL4__(v81 + (v40 ^ v41 ^ v42) - 378558 + v39, 4);
  v44 = v43 + __ROL4__(v79 + (v41 ^ v42 ^ v43) - 2022574463 + v40, 11);
  v45 = v44 + __ROL4__(v77 + (v42 ^ v43 ^ v44) + 1839030562 + v41, 16);
  v46 = v45 + __ROL4__(v22 + (v43 ^ v44 ^ v45) - 35309556 + v42, 23);
  v47 = v46 + __ROL4__(v85 + (v46 ^ v44 ^ v45) - 1530992060 + v43, 4);
  v48 = v47 + __ROL4__(v76 + (v45 ^ v46 ^ v47) + 1272893353 + v44, 11);
  v49 = v48 + __ROL4__(v11 + (v46 ^ v47 ^ v48) - 155497632 + v45, 16);
  v50 = v49 + __ROL4__(v12 + (v47 ^ v48 ^ v49) - 1094730640 + v46, 23);
  v51 = v50 + __ROL4__(v21 + (v50 ^ v48 ^ v49) + v47 + 681279174, 4);
  v52 = v51 + __ROL4__(v83 + (v49 ^ v50 ^ v51) - 358537222 + v48, 11);
  v53 = v52 + __ROL4__(v84 + (v50 ^ v51 ^ v52) - 722521979 + v49, 16);
  v54 = v53 + __ROL4__(v50 + v75 + (v51 ^ v52 ^ v53) + 76029189, 23);
  v55 = v54 + __ROL4__(v51 - 640364487 + v78 + (v54 ^ v52 ^ v53), 4);
  v56 = v55 + __ROL4__(v13 + (v53 ^ v54 ^ v55) - 421815835 + v52, 11);
  v57 = v56 + __ROL4__((_DWORD)v3 + (v54 ^ v55 ^ v56) + 530742520 + v53, 16);
  v58 = v57 + __ROL4__(v80 + (v55 ^ v56 ^ v57) - 995338651 + v54, 23);
  v59 = v58 + __ROL4__(v55 + (v57 ^ (v58 | ~v56)) + v83 - 198630844, 6);
  v60 = v59 + __ROL4__(v11 + (v58 ^ (v59 | ~v57)) + v56 + 1126891415, 10);
  v61 = v60 + __ROL4__(v22 + (v59 ^ (v60 | ~v58)) - 1416354905 + v57, 15);
  v62 = v61 + __ROL4__(v81 + (v60 ^ (v61 | ~v59)) - 57434055 + v58, 21);
  v63 = v62 + __ROL4__(v13 + (v61 ^ (v62 | ~v60)) + v59 + 1700485571, 6);
  v64 = v63 + __ROL4__(v60 + (v62 ^ (v63 | ~v61)) + v84 - 1894986606, 10);
  v65 = v64 + __ROL4__(v12 + (v63 ^ (v64 | ~v62)) + v61 - 1051523, 15);
  v66 = v65 + __ROL4__(v62 + (v64 ^ (v65 | ~v63)) + v85 - 2054922799, 21);
  v67 = v66 + __ROL4__(v63 + (v65 ^ (v66 | ~v64)) + v79 + 1873313359, 6);
  v68 = v67 + __ROL4__((_DWORD)v3 + (v66 ^ (v67 | ~v65)) + v64 - 30611744, 10);
  v69 = v68 + __ROL4__(v65 + (v67 ^ (v68 | ~v66)) + v75 - 1560198380, 15);
  v70 = v69 + __ROL4__(v66 + (v68 ^ (v69 | ~v67)) + v21 + 1309151649, 21);
  v71 = v70 + __ROL4__(v67 + (v69 ^ (v70 | ~v68)) + v76 - 145523070, 6);
  v72 = v71 + __ROL4__(v68 + (v70 ^ (v71 | ~v69)) + v77 - 1120210379, 10);
  v73 = v72 + __ROL4__(v69 + (v71 ^ (v72 | ~v70)) + v80 + 718787259, 15);
  *a1 += v71;
  a1[2] += v73;
  result = (unsigned int)(v73 + __ROL4__(v70 + (v72 ^ (v73 | ~v71)) + v78 - 343485551, 21));
  a1[1] += result;
  a1[3] += v72;
  return result;
}

```

## disassembly

```asm
0x1800072b4  mov     [rsp+arg_0], rcx
0x1800072b9  push    rbx
0x1800072ba  push    rbp
0x1800072bb  push    rsi
0x1800072bc  push    rdi
0x1800072bd  push    r12
0x1800072bf  push    r13
0x1800072c1  push    r14
0x1800072c3  push    r15
0x1800072c5  sub     rsp, 28h
0x1800072c9  mov     r11d, [rcx+4]
0x1800072cd  mov     rsi, rdx
0x1800072d0  mov     r10d, [rcx+8]
0x1800072d4  mov     r8d, r11d
0x1800072d7  mov     r9d, [rcx+0Ch]
0x1800072db  not     r8d
0x1800072de  mov     edx, [rcx]
0x1800072e0  and     r8d, r9d
0x1800072e3  mov     ecx, [rsi]
0x1800072e5  add     edx, 0D76AA478h
0x1800072eb  mov     [rsp+68h+arg_8], ecx
0x1800072ef  mov     eax, r10d
0x1800072f2  and     eax, r11d
0x1800072f5  or      r8d, eax
0x1800072f8  add     r8d, ecx
0x1800072fb  add     edx, r8d
0x1800072fe  mov     r8d, [rsi+4]
0x180007302  rol     edx, 7
0x180007305  add     edx, r11d
0x180007308  mov     [rsp+68h+arg_18], r8d
0x180007310  mov     ecx, edx
0x180007312  mov     eax, edx
0x180007314  not     ecx
0x180007316  and     eax, r11d
0x180007319  and     ecx, r10d
0x18000731c  or      ecx, eax
0x18000731e  add     ecx, r8d
0x180007321  lea     r8d, [r9-173848AAh]
0x180007328  mov     r9d, [rsi+8]
0x18000732c  add     r8d, ecx
0x18000732f  mov     [rsp+68h+var_54], r9d
0x180007334  rol     r8d, 0Ch
0x180007338  add     r8d, edx
0x18000733b  mov     ecx, r8d
0x18000733e  mov     eax, r8d
0x180007341  not     ecx
0x180007343  and     eax, edx
0x180007345  and     ecx, r11d
0x180007348  or      ecx, eax
0x18000734a  add     ecx, r9d
0x18000734d  lea     r9d, [r10+242070DBh]
0x180007354  mov     r10d, [rsi+0Ch]
0x180007358  add     r9d, ecx
0x18000735b  mov     [rsp+68h+arg_10], r10d
0x180007363  rol     r9d, 11h
0x180007367  add     r9d, r8d
0x18000736a  mov     ecx, r9d
0x18000736d  mov     eax, r9d
0x180007370  not     ecx
0x180007372  and     eax, r8d
0x180007375  and     ecx, edx
0x180007377  or      ecx, eax
0x180007379  add     ecx, r10d
0x18000737c  lea     r10d, [r11-3E423112h]
0x180007383  mov     r11d, [rsi+10h]
0x180007387  add     r10d, ecx
0x18000738a  rol     r10d, 16h
0x18000738e  add     r10d, r9d
0x180007391  mov     [rsp+68h+var_64], r11d
0x180007396  mov     ecx, r10d
0x180007399  mov     eax, r10d
0x18000739c  not     ecx
0x18000739e  and     eax, r9d
0x1800073a1  and     ecx, r8d
0x1800073a4  or      ecx, eax
0x1800073a6  add     ecx, edx
0x1800073a8  lea     edx, [r11-0A83F051h]
0x1800073af  mov     r11d, [rsi+14h]
0x1800073b3  add     edx, ecx
0x1800073b5  rol     edx, 7
0x1800073b8  add     edx, r10d
0x1800073bb  mov     [rsp+68h+var_50], r11d
0x1800073c0  mov     ecx, edx
0x1800073c2  mov     eax, edx
0x1800073c4  not     ecx
0x1800073c6  and     eax, r10d
0x1800073c9  and     ecx, r9d
0x1800073cc  or      ecx, eax
0x1800073ce  add     ecx, r8d
0x1800073d1  lea     r8d, [r11+4787C62Ah]
0x1800073d8  add     r8d, ecx
0x1800073db  mov     r11d, [rsi+18h]
0x1800073df  mov     r15d, [rsi+1Ch]
0x1800073e3  mov     r12d, [rsi+28h]
0x1800073e7  mov     r14d, [rsi+30h]
0x1800073eb  rol     r8d, 0Ch
0x1800073ef  add     r8d, edx
0x1800073f2  mov     [rsp+68h+var_68], r11d
0x1800073f6  mov     ecx, r8d
0x1800073f9  mov     eax, r8d
0x1800073fc  not     ecx
0x1800073fe  and     eax, edx
0x180007400  and     ecx, r10d
0x180007403  or      ecx, eax
0x180007405  add     ecx, r9d
0x180007408  lea     r9d, [r11-57CFB9EDh]
0x18000740f  mov     r11d, [rsi+20h]
0x180007413  add     r9d, ecx
0x180007416  rol     r9d, 11h
0x18000741a  add     r9d, r8d
0x18000741d  mov     [rsp+68h+var_58], r11d
0x180007422  mov     ecx, r9d
0x180007425  mov     eax, r9d
0x180007428  not     ecx
0x18000742a  and     eax, r8d
0x18000742d  and     ecx, edx
0x18000742f  or      ecx, eax
0x180007431  add     ecx, r10d
0x180007434  lea     r10d, [r15-2B96AFFh]
0x18000743b  add     r10d, ecx
0x18000743e  rol     r10d, 16h
0x180007442  add     r10d, r9d
0x180007445  mov     ecx, r10d
0x180007448  mov     eax, r10d
0x18000744b  not     ecx
0x18000744d  and     eax, r9d
0x180007450  and     ecx, r8d
0x180007453  or      ecx, eax
0x180007455  add     ecx, edx
0x180007457  lea     edx, [r11+698098D8h]
0x18000745e  mov     r11d, [rsi+24h]
0x180007462  add     edx, ecx
0x180007464  rol     edx, 7
0x180007467  add     edx, r10d
0x18000746a  mov     [rsp+68h+var_5C], r11d
0x18000746f  mov     ecx, edx
0x180007471  mov     eax, edx
0x180007473  not     ecx
0x180007475  and     eax, r10d
0x180007478  and     ecx, r9d
0x18000747b  or      ecx, eax
0x18000747d  add     ecx, r8d
0x180007480  lea     r8d, [r11-74BB0851h]
0x180007487  mov     r11d, [rsi+2Ch]
0x18000748b  add     r8d, ecx
0x18000748e  rol     r8d, 0Ch
0x180007492  add     r8d, edx
0x180007495  mov     [rsp+68h+var_60], r11d
0x18000749a  mov     ecx, r8d
0x18000749d  mov     eax, r8d
0x1800074a0  not     ecx
0x1800074a2  lea     edi, [r11-76A32842h]
0x1800074a9  and     ecx, r10d
0x1800074ac  and     eax, edx
0x1800074ae  or      ecx, eax
0x1800074b0  add     ecx, r9d
0x1800074b3  lea     r9d, [r12-0A44Fh]
0x1800074bb  add     r9d, ecx
0x1800074be  rol     r9d, 11h
0x1800074c2  add     r9d, r8d
0x1800074c5  mov     ecx, r9d
0x1800074c8  mov     eax, r9d
0x1800074cb  not     ecx
0x1800074cd  and     eax, r8d
0x1800074d0  and     ecx, edx
0x1800074d2  or      ecx, eax
0x1800074d4  add     ecx, r10d
0x1800074d7  add     edi, ecx
0x1800074d9  rol     edi, 16h
0x1800074dc  add     edi, r9d
0x1800074df  mov     ecx, edi
0x1800074e1  not     ecx
0x1800074e3  mov     r13d, [rsi+34h]
0x1800074e7  lea     ebx, [r14+6B901122h]
0x1800074ee  mov     ebp, [rsi+38h]
0x1800074f1  and     ecx, r8d
0x1800074f4  mov     esi, [rsi+3Ch]
0x1800074f7  mov     eax, edi
0x1800074f9  and     eax, r9d
0x1800074fc  or      ecx, eax
0x1800074fe  lea     r11d, [r13-2678E6Dh]
0x180007505  add     ecx, edx
0x180007507  lea     r10d, [rbp-5986BC72h]
0x18000750e  add     ebx, ecx
0x180007510  rol     ebx, 7
0x180007513  add     ebx, edi
0x180007515  mov     ecx, ebx
0x180007517  mov     eax, ebx
0x180007519  not     ecx
0x18000751b  and     eax, edi
0x18000751d  and     ecx, r9d
0x180007520  or      ecx, eax
0x180007522  mov     eax, ebx
0x180007524  add     ecx, r8d
0x180007527  add     r11d, ecx
0x18000752a  mov     ecx, edi
0x18000752c  rol     r11d, 0Ch
0x180007530  add     r11d, ebx
0x180007533  and     eax, r11d
0x180007536  mov     r8d, r11d
0x180007539  not     r8d
0x18000753c  and     ecx, r8d
0x18000753f  or      ecx, eax
0x180007541  add     ecx, r9d
0x180007544  lea     r9d, [rsi+49B40821h]
0x18000754b  add     r10d, ecx
0x18000754e  mov     ecx, ebx
0x180007550  rol     r10d, 11h
0x180007554  add     r10d, r11d
0x180007557  and     r8d, r10d
0x18000755a  mov     edx, r10d
0x18000755d  not     edx
0x18000755f  mov     eax, r10d
0x180007562  and     ecx, edx
0x180007564  and     eax, r11d
0x180007567  or      ecx, eax
0x180007569  add     ecx, edi
0x18000756b  mov     edi, [rsp+68h+arg_18]
0x180007572  add     r9d, ecx
0x180007575  add     edi, 0F61E2562h
0x18000757b  rol     r9d, 16h
0x18000757f  add     r9d, r10d
0x180007582  and     edx, r9d
0x180007585  mov     eax, r9d
0x180007588  and     eax, r11d
0x18000758b  mov     ecx, r9d
0x18000758e  or      r8d, eax
0x180007591  not     ecx
0x180007593  add     r8d, ebx
0x180007596  add     r8d, edi
0x180007599  rol     r8d, 5
0x18000759d  add     r8d, r9d
0x1800075a0  and     ecx, r8d
0x1800075a3  mov     eax, r8d
0x1800075a6  and     eax, r10d
0x1800075a9  or      edx, eax
0x1800075ab  add     edx, 0C040B340h
0x1800075b1  add     edx, [rsp+68h+var_68]
0x1800075b4  add     edx, r11d
0x1800075b7  rol     edx, 9
0x1800075ba  add     edx, r8d
0x1800075bd  mov     eax, edx
0x1800075bf  and     eax, r9d
0x1800075c2  or      ecx, eax
0x1800075c4  add     ecx, 265E5A51h
0x1800075ca  add     ecx, [rsp+68h+var_60]
0x1800075ce  add     r10d, ecx
0x1800075d1  mov     ecx, r8d
0x1800075d4  rol     r10d, 0Eh
0x1800075d8  not     ecx
0x1800075da  add     r10d, edx
0x1800075dd  and     ecx, edx
0x1800075df  mov     eax, r10d
0x1800075e2  mov     edi, [rsp+68h+var_50]
0x1800075e6  and     eax, r8d
0x1800075e9  or      ecx, eax
0x1800075eb  add     ecx, 0E9B6C7AAh
0x1800075f1  add     ecx, [rsp+68h+arg_8]
0x1800075f5  add     r9d, ecx
0x1800075f8  mov     ecx, edx
0x1800075fa  not     ecx
0x1800075fc  rol     r9d, 14h
0x180007600  and     ecx, r10d
0x180007603  add     r9d, r10d
0x180007606  mov     eax, r9d
0x180007609  and     eax, edx
0x18000760b  or      ecx, eax
0x18000760d  add     ecx, 0D62F105Dh
0x180007613  add     ecx, edi
0x180007615  add     r8d, ecx
0x180007618  mov     ecx, r10d
0x18000761b  not     ecx
0x18000761d  rol     r8d, 5
0x180007621  and     ecx, r9d
0x180007624  add     r8d, r9d
0x180007627  mov     eax, r8d
0x18000762a  and     eax, r10d
0x18000762d  or      ecx, eax
0x18000762f  add     ecx, 2441453h
0x180007635  add     ecx, r12d
0x180007638  add     edx, ecx
0x18000763a  mov     ecx, r9d
0x18000763d  not     ecx
0x18000763f  rol     edx, 9
0x180007642  and     ecx, r8d
0x180007645  add     edx, r8d
0x180007648  mov     eax, edx
0x18000764a  and     eax, r9d
0x18000764d  or      ecx, eax
0x18000764f  add     ecx, 0D8A1E681h
0x180007655  add     ecx, esi
0x180007657  add     r10d, ecx
0x18000765a  mov     ecx, r8d
0x18000765d  not     ecx
0x18000765f  rol     r10d, 0Eh
0x180007663  and     ecx, edx
0x180007665  add     r10d, edx
0x180007668  mov     eax, r10d
0x18000766b  mov     r11d, r10d
0x18000766e  and     eax, r8d
  ... truncated ...
```

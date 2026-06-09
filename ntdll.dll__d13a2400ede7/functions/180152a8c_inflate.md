# inflate

- ea: `0x180152a8c`
- end: `0x1801539c5`
- name: `inflate`
- size: `3897`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180150a58`

## callees

- `0x180152a8c`
- `0x180153b18`
- `0x180153b58`
- `0x1801554cc`
- `0x180155854`
- `0x180155cdc`
- `0x180164280`

## string_xrefs

- `0x180152d56`: `unknown compression method`

## pseudocode

```c
__int64 __fastcall inflate(unsigned __int8 **a1)
{
  unsigned __int8 **v2; // rcx
  unsigned __int8 *v3; // rdi
  __int64 v4; // r9
  __int64 v5; // rdx
  unsigned __int8 *v6; // r10
  unsigned int v7; // r12d
  unsigned __int8 *v8; // r13
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  _DWORD *v11; // r15
  _DWORD *v12; // r8
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  __int64 result; // rax
  unsigned __int32 v18; // ebp
  int v19; // eax
  char v20; // al
  unsigned int v21; // ebp
  const char *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // ecx
  int v25; // eax
  const char *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // r15d
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  char v33; // cl
  unsigned int v34; // ebp
  char v35; // dl
  unsigned int v36; // ecx
  int v37; // eax
  unsigned int v38; // edx
  __int64 v39; // rdx
  __int16 v40; // cx
  const char *v41; // rax
  unsigned int v42; // ebx
  __int64 v43; // r11
  unsigned int v44; // edx
  int v45; // r10d
  unsigned int v46; // edx
  __int16 v47; // r8
  int v48; // edx
  int v49; // eax
  unsigned int v50; // ebp
  unsigned int v51; // ebp
  int v52; // r8d
  int v53; // r8d
  int v54; // eax
  unsigned int v55; // eax
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  __int64 v60; // r11
  int v61; // edx
  unsigned int v62; // eax
  int v63; // r8d
  unsigned int v64; // r10d
  unsigned int v65; // edx
  int v66; // eax
  __int64 v67; // r11
  int v68; // edx
  unsigned int v69; // eax
  int v70; // r8d
  unsigned int v71; // r10d
  unsigned int v72; // edx
  int v73; // eax
  __int64 v74; // rcx
  unsigned int v75; // ecx
  unsigned int v76; // eax
  unsigned int v77; // r8d
  __int64 v78; // rcx
  unsigned int v79; // eax
  unsigned int v80; // edx
  unsigned __int8 *v81; // rcx
  unsigned __int8 v82; // al
  int v83; // ecx
  int v84; // edx
  int v85; // eax
  unsigned int v86; // r15d
  int v87; // ecx
  int v88; // ecx
  bool v89; // zf
  unsigned int v90; // ebx
  int v91; // eax
  int v92; // edx
  int v93; // eax
  __int16 v94; // [rsp+32h] [rbp-46h]
  unsigned int v95; // [rsp+34h] [rbp-44h]
  unsigned __int8 *v96; // [rsp+38h] [rbp-40h]
  unsigned int v97; // [rsp+88h] [rbp+10h]
  unsigned int v98; // [rsp+90h] [rbp+18h]
  unsigned int v99; // [rsp+98h] [rbp+20h]

  if ( (unsigned int)inflateStateCheck() || !v2[2] || !*v2 && *((_DWORD *)v2 + 2) )
    return 4294967294LL;
  v3 = v2[5];
  if ( *((_DWORD *)v3 + 2) == 16191 )
    *((_DWORD *)v3 + 2) = 16192;
  v4 = *((unsigned int *)v2 + 6);
  v5 = (unsigned int)v4;
  v6 = v2[2];
  v7 = *((_DWORD *)v2 + 2);
  v8 = *v2;
  v9 = *((_DWORD *)v3 + 18);
  v10 = *((_DWORD *)v3 + 19);
  v97 = *((_DWORD *)v2 + 6);
  v96 = v6;
  v99 = v97;
  v95 = v7;
  v98 = 0;
LABEL_8:
  v11 = v3 + 112;
LABEL_9:
  v12 = v3 + 116;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v13 = *((_DWORD *)v3 + 2);
        if ( v13 > 16199 )
          break;
        if ( v13 == 16199 )
        {
LABEL_131:
          *((_DWORD *)v3 + 2) = 16200;
LABEL_132:
          if ( v7 < 6 || (unsigned int)v4 < 0x102 )
          {
            v60 = *((_QWORD *)v3 + 12);
            v61 = (1 << *v11) - 1;
            *((_DWORD *)v3 + 2265) = 0;
            while ( 1 )
            {
              v62 = *(_DWORD *)(v60 + 4LL * (v9 & v61));
              v63 = BYTE1(v62);
              if ( BYTE1(v62) <= v10 )
                break;
              if ( !v7 )
                goto LABEL_227;
              --v7;
              v9 += *v8++ << v10;
              v10 += 8;
            }
            if ( (_BYTE)v62 && (v62 & 0xF0) == 0 )
            {
              v4 = (unsigned int)(1 << (BYTE1(v62) + v62));
              v64 = HIWORD(v62);
              while ( 1 )
              {
                v62 = *(_DWORD *)(v60 + 4LL * (v64 + ((v9 & ((_DWORD)v4 - 1)) >> v63)));
                if ( v63 + (unsigned int)BYTE1(v62) <= v10 )
                  break;
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              *((_DWORD *)v3 + 2265) = v63;
              v9 >>= v63;
              v10 -= v63;
            }
            *((_DWORD *)v3 + 2265) += BYTE1(v62);
            v10 -= BYTE1(v62);
            v9 >>= SBYTE1(v62);
            *((_DWORD *)v3 + 20) = HIWORD(v62);
            if ( !(_BYTE)v62 )
            {
              *((_DWORD *)v3 + 2) = 16205;
              goto LABEL_54;
            }
            if ( (v62 & 0x20) != 0 )
            {
              *((_DWORD *)v3 + 2265) = -1;
              *((_DWORD *)v3 + 2) = 16191;
              goto LABEL_54;
            }
            if ( (v62 & 0x40) != 0 )
            {
              v41 = "invalid literal/length code";
              goto LABEL_93;
            }
            v12 = v3 + 116;
            *((_DWORD *)v3 + 2) = 16201;
            *((_DWORD *)v3 + 22) = v62 & 0xF;
LABEL_162:
            v65 = *((_DWORD *)v3 + 22);
            if ( v65 )
            {
              while ( v10 < v65 )
              {
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v10 -= v65;
              v66 = v9 & ((1 << v65) - 1);
              v9 >>= v65;
              *((_DWORD *)v3 + 20) += v66;
              *((_DWORD *)v3 + 2265) += v65;
            }
            *((_DWORD *)v3 + 2266) = *((_DWORD *)v3 + 20);
            *((_DWORD *)v3 + 2) = 16202;
LABEL_168:
            v67 = *((_QWORD *)v3 + 13);
            v68 = (1 << *v12) - 1;
            while ( 1 )
            {
              v69 = *(_DWORD *)(v67 + 4LL * (v9 & v68));
              v70 = BYTE1(v69);
              if ( BYTE1(v69) <= v10 )
                break;
              if ( !v7 )
                goto LABEL_227;
              --v7;
              v9 += *v8++ << v10;
              v10 += 8;
            }
            if ( (v69 & 0xF0) == 0 )
            {
              v4 = (unsigned int)(1 << (BYTE1(v69) + v69));
              v71 = HIWORD(v69);
              while ( 1 )
              {
                v69 = *(_DWORD *)(v67 + 4LL * (v71 + ((v9 & ((_DWORD)v4 - 1)) >> v70)));
                if ( v70 + (unsigned int)BYTE1(v69) <= v10 )
                  break;
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v10 -= v70;
              v9 >>= v70;
              *((_DWORD *)v3 + 2265) += v70;
            }
            *((_DWORD *)v3 + 2265) += BYTE1(v69);
            v10 -= BYTE1(v69);
            v9 >>= SBYTE1(v69);
            if ( (v69 & 0x40) != 0 )
            {
              v41 = "invalid distance code";
              goto LABEL_93;
            }
            v4 = v99;
            v12 = v3 + 116;
            v6 = v96;
            *((_DWORD *)v3 + 21) = HIWORD(v69);
            *((_DWORD *)v3 + 2) = 16203;
            *((_DWORD *)v3 + 22) = v69 & 0xF;
LABEL_181:
            v72 = *((_DWORD *)v3 + 22);
            if ( v72 )
            {
              while ( v10 < v72 )
              {
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v10 -= v72;
              v73 = v9 & ((1 << v72) - 1);
              v9 >>= v72;
              *((_DWORD *)v3 + 21) += v73;
              *((_DWORD *)v3 + 2265) += v72;
            }
            v5 = v97;
            *((_DWORD *)v3 + 2) = 16204;
            goto LABEL_187;
          }
          a1[2] = v6;
          *((_DWORD *)a1 + 6) = v4;
          *a1 = v8;
          *((_DWORD *)a1 + 2) = v7;
          *((_DWORD *)v3 + 18) = v9;
          *((_DWORD *)v3 + 19) = v10;
          inflate_fast(a1, v5, v12);
          v12 = v3 + 116;
          v6 = a1[2];
          v4 = *((unsigned int *)a1 + 6);
          v8 = *a1;
          v7 = *((_DWORD *)a1 + 2);
          v9 = *((_DWORD *)v3 + 18);
          v10 = *((_DWORD *)v3 + 19);
          v5 = v97;
          v96 = v6;
          v99 = *((_DWORD *)a1 + 6);
          if ( *((_DWORD *)v3 + 2) == 16191 )
          {
            *((_DWORD *)v3 + 2265) = -1;
            goto LABEL_9;
          }
        }
        else if ( v13 > 16193 )
        {
          v29 = v13 - 16194;
          if ( !v29 )
            goto LABEL_63;
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( !v31 )
            {
              while ( v10 < 0xE )
              {
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v33 = v9;
              v10 -= 14;
              v34 = v9 >> 5;
              v35 = v34;
              v36 = (v33 & 0x1F) + 257;
              v34 >>= 5;
              *((_DWORD *)v3 + 31) = v36;
              v37 = v34 & 0xF;
              v9 = v34 >> 4;
              v38 = (v35 & 0x1F) + 1;
              *((_DWORD *)v3 + 32) = v38;
              *((_DWORD *)v3 + 30) = v37 + 4;
              if ( v36 > 0x11E || v38 > 0x1E )
              {
                v22 = "too many length or distance symbols";
                goto LABEL_46;
              }
              *((_DWORD *)v3 + 33) = 0;
              *((_DWORD *)v3 + 2) = 16197;
LABEL_84:
              while ( 1 )
              {
                v39 = *((unsigned int *)v3 + 33);
                if ( (unsigned int)v39 >= *((_DWORD *)v3 + 30) )
                  break;
                while ( v10 < 3 )
                {
                  if ( !v7 )
                    goto LABEL_227;
                  --v7;
                  v9 += *v8++ << v10;
                  v10 += 8;
                }
                v40 = v9 & 7;
                v9 >>= 3;
                *(_WORD *)&v3[2 * *((unsigned __int16 *)qword_180192070 + v39) + 144] = v40;
                ++*((_DWORD *)v3 + 33);
                v10 -= 3;
              }
              while ( (unsigned int)v39 < 0x13 )
              {
                *(_WORD *)&v3[2 * *((unsigned __int16 *)qword_180192070 + v39) + 144] = 0;
                v39 = (unsigned int)(*((_DWORD *)v3 + 33) + 1);
                *((_DWORD *)v3 + 33) = v39;
              }
              *v11 = 7;
              *((_QWORD *)v3 + 12) = v3 + 1360;
              *((_QWORD *)v3 + 17) = v3 + 1360;
              v98 = inflate_table(0, (int)v3 + 144, 19, (int)v3 + 136, (__int64)v11, (__int64)(v3 + 784));
              if ( !v98 )
              {
                *((_DWORD *)v3 + 33) = 0;
                *((_DWORD *)v3 + 2) = 16198;
                goto LABEL_95;
              }
              v41 = "invalid code lengths set";
LABEL_93:
              a1[4] = (unsigned __int8 *)v41;
              *((_DWORD *)v3 + 2) = 16209;
              goto LABEL_54;
            }
            v32 = v31 - 1;
            if ( !v32 )
              goto LABEL_84;
            if ( v32 != 1 )
              return 4294967294LL;
LABEL_95:
            while ( 1 )
            {
              v42 = *((_DWORD *)v3 + 32) + *((_DWORD *)v3 + 31);
              v43 = *((unsigned int *)v3 + 33);
              if ( (unsigned int)v43 >= v42 )
                break;
              v4 = *((_QWORD *)v3 + 12);
              while ( 1 )
              {
                v44 = *(_DWORD *)(v4 + 4LL * (v9 & ((1 << *v11) - 1)));
                v45 = BYTE1(v44);
                v94 = HIWORD(v44);
                if ( BYTE1(v44) <= v10 )
                  break;
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v46 = HIWORD(v44);
              if ( (unsigned __int16)v46 >= 0x10u )
              {
                if ( (_WORD)v46 == 16 )
                {
                  while ( v10 < v45 + 2 )
                  {
                    if ( !v7 )
                      goto LABEL_227;
                    --v7;
                    v9 += *v8++ << v10;
                    v10 += 8;
                  }
                  v10 -= v45;
                  v9 >>= v45;
                  if ( !(_DWORD)v43 )
                  {
LABEL_121:
                    a1[4] = "invalid bit length repeat";
                    *((_DWORD *)v3 + 2) = 16209;
                    break;
                  }
                  v47 = *(_WORD *)&v3[2 * (unsigned int)(v43 - 1) + 144];
                  v48 = (v9 & 3) + 3;
                  v9 >>= 2;
                  v10 -= 2;
                }
                else
                {
                  v4 = 0;
                  if ( v94 == 17 )
                  {
                    while ( v10 < v45 + 3 )
                    {
                      if ( !v7 )
                        goto LABEL_227;
                      --v7;
                      v9 += *v8++ << v10;
                      v10 += 8;
                    }
                    v49 = -3;
                    v50 = v9 >> v45;
                    v48 = (v50 & 7) + 3;
                    v9 = v50 >> 3;
                  }
                  else
                  {
                    while ( v10 < v45 + 7 )
                    {
                      if ( !v7 )
                        goto LABEL_227;
                      --v7;
                      v9 += *v8++ << v10;
                      v10 += 8;
                    }
                    v49 = -7;
                    v51 = v9 >> v45;
                    v48 = (v51 & 0x7F) + 11;
                    v9 = v51 >> 7;
                  }
                  v47 = 0;
                  v10 += v49 - v45;
                }
                if ( (int)v43 + v48 > v42 )
                  goto LABEL_121;
                do
                {
                  *(_WORD *)&v3[2 * (*((_DWORD *)v3 + 33))++ + 144] = v47;
                  --v48;
                }
                while ( v48 );
              }
              else
              {
                *(_WORD *)&v3[2 * v43 + 144] = v46;
                v9 >>= v45;
                v10 -= v45;
                ++*((_DWORD *)v3 + 33);
              }
            }
            v12 = v3 + 116;
            v5 = v97;
            v4 = v99;
            v6 = v96;
            if ( *((_DWORD *)v3 + 2) != 16209 )
            {
              if ( *((_WORD *)v3 + 328) )
              {
                v52 = *((_DWORD *)v3 + 31);
                *v11 = 10;
                *((_QWORD *)v3 + 17) = v3 + 1360;
                *((_QWORD *)v3 + 12) = v3 + 1360;
                v98 = inflate_table(1, (int)v3 + 144, v52, (int)v3 + 136, (__int64)(v3 + 112), (__int64)(v3 + 784));
                if ( v98 )
                {
                  v4 = v99;
                  v6 = v96;
                  a1[4] = "invalid literal/lengths set";
                  *((_DWORD *)v3 + 2) = 16209;
                  goto LABEL_71;
                }
                v53 = *((_DWORD *)v3 + 32);
                *((_QWORD *)v3 + 13) = *((_QWORD *)v3 + 17);
                v54 = *((_DWORD *)v3 + 31) + 72;
                *((_DWORD *)v3 + 29) = 9;
                v55 = inflate_table(2, (int)v3 + 2 * v54, v53, (int)v3 + 136, (__int64)(v3 + 116), (__int64)(v3 + 784));
                v5 = v97;
                v11 = v3 + 112;
                v4 = v99;
                v6 = v96;
                v98 = v55;
                if ( !v55 )
                  goto LABEL_131;
                a1[4] = "invalid distances set";
                *((_DWORD *)v3 + 2) = 16209;
              }
              else
              {
                a1[4] = "invalid code -- missing end-of-block";
                *((_DWORD *)v3 + 2) = 16209;
              }
              goto LABEL_9;
            }
          }
          else
          {
LABEL_64:
            v27 = *((_DWORD *)v3 + 20);
            if ( v27 )
            {
              v28 = v7;
              if ( v27 <= v7 )
                v28 = *((_DWORD *)v3 + 20);
              if ( v28 > (unsigned int)v4 )
                v28 = v4;
              if ( !v28 )
              {
LABEL_227:
                v86 = v98;
                goto LABEL_228;
              }
              memmove(v6, v8, v28);
              v7 -= v28;
              v4 = v99 - v28;
              v6 = &v96[v28];
              v99 -= v28;
              v8 += v28;
              v96 = v6;
              *((_DWORD *)v3 + 20) -= v28;
LABEL_71:
              v5 = v97;
              goto LABEL_8;
            }
            *((_DWORD *)v3 + 2) = 16191;
          }
        }
        else
        {
          if ( v13 == 16193 )
          {
            v9 >>= v10 & 7;
            for ( v10 -= v10 & 7; v10 < 0x20; v10 += 8 )
            {
              if ( !v7 )
                goto LABEL_227;
              --v7;
              v9 += *v8++ << v10;
            }
            if ( (unsigned __int16)v9 != ~v9 >> 16 )
            {
              v26 = "invalid stored block lengths";
              goto LABEL_217;
            }
            *((_DWORD *)v3 + 20) = (unsigned __int16)v9;
            v9 = 0;
            v10 = 0;
LABEL_63:
            *((_DWORD *)v3 + 2) = 16195;
            goto LABEL_64;
          }
          v14 = v13 - 16180;
          if ( v14 )
          {
            v15 = v14 - 9;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( (unsigned int)(v16 - 1) >= 2 )
                  return 4294967294LL;
                goto LABEL_25;
              }
            }
            else
            {
              while ( v10 < 0x20 )
              {
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v18 = _byteswap_ulong(v9);
              *((_DWORD *)v3 + 8) = v18;
              v10 = 0;
              *((_DWORD *)a1 + 19) = v18;
              v9 = 0;
              *((_DWORD *)v3 + 2) = 16190;
            }
            if ( !*((_DWORD *)v3 + 5) )
            {
              a1[2] = v6;
              result = 2;
              *((_DWORD *)a1 + 6) = v4;
              *a1 = v8;
              *((_DWORD *)a1 + 2) = v7;
              *((_DWORD *)v3 + 18) = v9;
              *((_DWORD *)v3 + 19) = v10;
              return result;
            }
            v19 = adler32_z(0, 0);
            v5 = v97;
            v12 = v3 + 116;
            v4 = v99;
            v6 = v96;
            *((_DWORD *)v3 + 8) = v19;
            *((_DWORD *)a1 + 19) = v19;
            *((_DWORD *)v3 + 2) = 16191;
LABEL_25:
            if ( *((_DWORD *)v3 + 3) )
            {
              *((_DWORD *)v3 + 2) = 16206;
              v9 >>= v10 & 7;
              v10 -= v10 & 7;
            }
            else
            {
              while ( v10 < 3 )
              {
                if ( !v7 )
                  goto LABEL_227;
                --v7;
                v9 += *v8++ << v10;
                v10 += 8;
              }
              v20 = v9;
              v21 = v9 >> 1;
              *((_DWORD *)v3 + 3) = v20 & 1;
              if ( (v21 & 3) != 0 )
              {
                switch ( v21 & 3 )
                {
                  case 1u:
                    *v11 = 9;
                    *((_QWORD *)v3 + 12) = "`\a";
                    *((_QWORD *)v3 + 13) = qword_1801920A0;
                    *v12 = 5;
                    *((_DWORD *)v3 + 2) = 16199;
                    break;
                  case 2u:
                    *((_DWORD *)v3 + 2) = 16196;
                    break;
                  case 3u:
                    a1[4] = "invalid block type";
                    *((_DWORD *)v3 + 2) = 16209;
                    break;
                }
              }
              else
              {
                *((_DWORD *)v3 + 2) = 16193;
              }
              v9 = v21 >> 2;
              v10 -= 3;
            }
          }
          else if ( *((_DWORD *)v3 + 4) )
          {
            while ( v10 < 0x10 )
            {
              if ( !v7 )
                goto LABEL_227;
              --v7;
              v9 += *v8++ << v10;
              v10 += 8;
            }
            if ( (v9 >> 8) + ((unsigned __int8)v9 << 8) != 31 * (((v9 >> 8) + ((unsigned __int8)v9 << 8)) / 0x1F) )
            {
              v22 = "incorrect header check";
              goto LABEL_46;
            }
            if ( (v9 & 0xF) != 8 )
            {
              v22 = "unknown compression method";
              goto LABEL_46;
            }
            v23 = *((_DWORD *)v3 + 12);
            v9 >>= 4;
            v24 = (v9 & 0xF) + 8;
            if ( !v23 )
            {
              *((_DWORD *)v3 + 12) = v24;
              v23 = (v9 & 0xF) + 8;
            }
            if ( v24 <= 0xF && v24 <= v23 )
            {
              *((_DWORD *)v3 + 6) = 0;
              *((_DWORD *)v3 + 7) = 1 << v24;
              v25 = adler32_z(0, 0);
              v10 = 0;
              *((_DWORD *)v3 + 8) = v25;
              *((_DWORD *)a1 + 19) = v25;
              *((_DWORD *)v3 + 2) = ~BYTE1(v9) & 2 | 0x3F3D;
              v9 = 0;
LABEL_54:
              v5 = v97;
              v4 = v99;
              v6 = v96;
              goto LABEL_9;
            }
            v10 -= 4;
            v22 = "invalid window size";
LABEL_46:
            v5 = v97;
            a1[4] = (unsigned __int8 *)v22;
            *((_DWORD *)v3 + 2) = 16209;
          }
          else
          {
            *((_DWORD *)v3 + 2) = 16192;
          }
        }
      }
      if ( v13 > 16205 )
        break;
      if ( v13 == 16205 )
      {
        if ( !(_DWORD)v4 )
          goto LABEL_227;
        *v6++ = v3[80];
        v4 = (unsigned int)(v4 - 1);
        v96 = v6;
        v99 = v4;
        *((_DWORD *)v3 + 2) = 16200;
      }
      else
      {
        v56 = v13 - 16200;
        if ( !v56 )
          goto LABEL_132;
        v57 = v56 - 1;
        if ( !v57 )
          goto LABEL_162;
        v58 = v57 - 1;
        if ( !v58 )
          goto LABEL_168;
        v59 = v58 - 1;
        if ( !v59 )
          goto LABEL_181;
        if ( v59 != 1 )
          return 4294967294LL;
LABEL_187:
        if ( !(_DWORD)v4 )
          goto LABEL_227;
        v74 = *((unsigned int *)v3 + 21);
        if ( (unsigned int)v74 <= (int)v5 - (int)v4 )
        {
          v81 = &v6[-v74];
          v79 = *((_DWORD *)v3 + 20);
          v80 = v79;
        }
        else
        {
          v75 = v74 - (v5 - v4);
          if ( v75 > *((_DWORD *)v3 + 14) && *((_DWORD *)v3 + 2264) )
          {
            v26 = "invalid distance too far back";
            goto LABEL_217;
          }
          v76 = *((_DWORD *)v3 + 15);
          if ( v75 > v76 )
          {
            v75 -= v76;
            v76 = *((_DWORD *)v3 + 13);
          }
          v77 = v75;
          v78 = v76 - v75;
          v79 = *((_DWORD *)v3 + 20);
          v80 = v79;
          v81 = (unsigned __int8 *)(*((_QWORD *)v3 + 8) + v78);
          if ( v77 <= v79 )
            v80 = v77;
        }
        if ( v80 > (unsigned int)v4 )
          v80 = v4;
        v4 = (unsigned int)v4 - v80;
        v99 = v4;
        *((_DWORD *)v3 + 20) = v79 - v80;
        do
        {
          v82 = *v81++;
          *v6++ = v82;
          --v80;
        }
        while ( v80 );
        v12 = v3 + 116;
        v5 = v97;
        v96 = v6;
        if ( !*((_DWORD *)v3 + 20) )
        {
          *((_DWORD *)v3 + 2) = 16200;
          goto LABEL_9;
        }
      }
    }
    v83 = v13 - 16206;
    if ( v83 )
    {
      v87 = v83 - 2;
      if ( !v87 )
        goto LABEL_221;
      v88 = v87 - 1;
      if ( !v88 )
      {
        v86 = -3;
        goto LABEL_228;
      }
      if ( v88 == 1 )
        return 4294967292LL;
      return 4294967294LL;
    }
    if ( !*((_DWORD *)v3 + 4) )
      goto LABEL_220;
    while ( v10 < 0x20 )
    {
      if ( !v7 )
        goto LABEL_227;
      --v7;
      v9 += *v8++ << v10;
      v10 += 8;
    }
    v84 = v5 - v4;
    *((_DWORD *)a1 + 7) += v84;
    *((_DWORD *)v3 + 9) += v84;
    if ( (v3[16] & 4) != 0 && v84 )
    {
      v85 = adler32_z(*((unsigned int *)v3 + 8), &v6[-v84]);
      v4 = v99;
      v12 = v3 + 116;
      v6 = v96;
      *((_DWORD *)v3 + 8) = v85;
      *((_DWORD *)a1 + 19) = v85;
    }
    v5 = (unsigned int)v4;
    v97 = v4;
    if ( (v3[16] & 4) == 0 || _byteswap_ulong(v9) == *((_DWORD *)v3 + 8) )
      break;
    v26 = "incorrect data check";
LABEL_217:
    a1[4] = (unsigned __int8 *)v26;
    *((_DWORD *)v3 + 2) = 16209;
  }
  v9 = 0;
  v10 = 0;
LABEL_220:
  *((_DWORD *)v3 + 2) = 16208;
LABEL_221:
  v86 = 1;
LABEL_228:
  a1[2] = v96;
  *((_DWORD *)a1 + 6) = v99;
  *a1 = v8;
  *((_DWORD *)a1 + 2) = v7;
  v89 = *((_DWORD *)v3 + 13) == 0;
  *((_DWORD *)v3 + 18) = v9;
  *((_DWORD *)v3 + 19) = v10;
  if ( (!v89 || v97 != *((_DWORD *)a1 + 6) && *((int *)v3 + 2) <= 16205)
    && (unsigned int)updatewindow(a1, a1[2], v97 - *((_DWORD *)a1 + 6), v4) )
  {
    *((_DWORD *)v3 + 2) = 16210;
    return 4294967292LL;
  }
  v90 = v97 - *((_DWORD *)a1 + 6);
  *((_DWORD *)a1 + 7) += v90;
  *((_DWORD *)a1 + 3) += v95 - *((_DWORD *)a1 + 2);
  *((_DWORD *)v3 + 9) += v90;
  if ( (v3[16] & 4) != 0 && v90 )
  {
    v91 = adler32_z(*((unsigned int *)v3 + 8), &a1[2][-v90]);
    *((_DWORD *)v3 + 8) = v91;
    *((_DWORD *)a1 + 19) = v91;
  }
  v92 = 128;
  if ( *((_DWORD *)v3 + 2) != 16191 )
    v92 = 0;
  if ( *((_DWORD *)v3 + 2) == 16199 || (v93 = 0, *((_DWORD *)v3 + 2) == 16194) )
    v93 = 256;
  *((_DWORD *)a1 + 18) = v92 + *((_DWORD *)v3 + 19) + v93 + (*((_DWORD *)v3 + 3) != 0 ? 0x40 : 0);
  if ( !v86 )
    return (unsigned int)-5;
  return v86;
}

```

## disassembly

```asm
0x180152a8c  mov     [rsp+arg_0], rbx
0x180152a91  mov     [rsp+arg_8], edx
0x180152a95  push    rbp
0x180152a96  push    rsi
0x180152a97  push    rdi
0x180152a98  push    r12
0x180152a9a  push    r13
0x180152a9c  push    r14
0x180152a9e  push    r15
0x180152aa0  sub     rsp, 40h
0x180152aa4  mov     rsi, rcx
0x180152aa7  call    inflateStateCheck
0x180152aac  xor     ebx, ebx
0x180152aae  test    eax, eax
0x180152ab0  jnz     loc_180152B78
0x180152ab6  cmp     [rcx+10h], rbx
0x180152aba  jz      loc_180152B78
0x180152ac0  cmp     [rcx], rbx
0x180152ac3  jnz     short loc_180152ACE
0x180152ac5  cmp     [rcx+8], ebx
0x180152ac8  jnz     loc_180152B78
0x180152ace  mov     rdi, [rcx+28h]
0x180152ad2  cmp     dword ptr [rdi+8], 3F3Fh
0x180152ad9  jnz     short loc_180152AE2
0x180152adb  mov     dword ptr [rdi+8], 3F40h
0x180152ae2  mov     r9d, [rcx+18h]
0x180152ae6  mov     edx, r9d
0x180152ae9  mov     r10, [rcx+10h]
0x180152aed  mov     r12d, [rcx+8]
0x180152af1  mov     r13, [rcx]
0x180152af4  mov     ebp, [rdi+48h]
0x180152af7  mov     r14d, [rdi+4Ch]
0x180152afb  mov     [rsp+78h+arg_8], edx
0x180152b02  mov     [rsp+78h+var_40], r10
0x180152b07  mov     [rsp+78h+arg_18], r9d
0x180152b0f  mov     [rsp+78h+var_44], r12d
0x180152b14  mov     [rsp+78h+arg_10], ebx
0x180152b1b  lea     r15, [rdi+70h]
0x180152b1f  mov     r11d, 7
0x180152b25  lea     r8, [rdi+74h]
0x180152b29  mov     ecx, [rdi+8]
0x180152b2c  cmp     ecx, 3F47h
0x180152b32  jg      loc_1801533D0
0x180152b38  jz      loc_180153344
0x180152b3e  cmp     ecx, 3F41h
0x180152b44  jg      loc_180152EA6
0x180152b4a  jz      loc_180152DDD
0x180152b50  sub     ecx, 3F34h
0x180152b56  jz      loc_180152CD1
0x180152b5c  sub     ecx, 9
0x180152b5f  jz      short loc_180152B96
0x180152b61  sub     ecx, 1
0x180152b64  jz      short loc_180152BD1
0x180152b66  sub     ecx, 1
0x180152b69  jz      loc_180152C11
0x180152b6f  cmp     ecx, 1
0x180152b72  jz      loc_180152C11
0x180152b78  mov     eax, 0FFFFFFFEh
0x180152b7d  mov     rbx, [rsp+78h+arg_0]
0x180152b85  add     rsp, 40h
0x180152b89  pop     r15
0x180152b8b  pop     r14
0x180152b8d  pop     r13
0x180152b8f  pop     r12
0x180152b91  pop     rdi
0x180152b92  pop     rsi
0x180152b93  pop     rbp
0x180152b94  retn
0x180152b96  cmp     r14d, 20h ; ' '
0x180152b9a  jnb     short loc_180152BBD
0x180152b9c  test    r12d, r12d
0x180152b9f  jz      loc_1801538D9
0x180152ba5  movzx   eax, byte ptr [r13+0]
0x180152baa  mov     ecx, r14d
0x180152bad  shl     eax, cl
0x180152baf  dec     r12d
0x180152bb2  add     ebp, eax
0x180152bb4  inc     r13
0x180152bb7  add     r14d, 8
0x180152bbb  jmp     short loc_180152B96
0x180152bbd  bswap   ebp
0x180152bbf  mov     [rdi+20h], ebp
0x180152bc2  mov     r14d, ebx
0x180152bc5  mov     [rsi+4Ch], ebp
0x180152bc8  mov     ebp, ebx
0x180152bca  mov     dword ptr [rdi+8], 3F3Eh
0x180152bd1  cmp     [rdi+14h], ebx
0x180152bd4  jz      loc_18015387E
0x180152bda  xor     r8d, r8d
0x180152bdd  xor     edx, edx
0x180152bdf  xor     ecx, ecx
0x180152be1  call    adler32_z
0x180152be6  mov     edx, [rsp+78h+arg_8]
0x180152bed  lea     r8, [rdi+74h]
0x180152bf1  mov     r9d, [rsp+78h+arg_18]
0x180152bf9  mov     r11d, 7
0x180152bff  mov     r10, [rsp+78h+var_40]
0x180152c04  mov     [rdi+20h], eax
0x180152c07  mov     [rsi+4Ch], eax
0x180152c0a  mov     dword ptr [rdi+8], 3F3Fh
0x180152c11  cmp     [rdi+0Ch], ebx
0x180152c14  jz      short loc_180152C2D
0x180152c16  mov     ecx, r14d
0x180152c19  mov     dword ptr [rdi+8], 3F4Eh
0x180152c20  and     ecx, r11d
0x180152c23  shr     ebp, cl
0x180152c25  sub     r14d, ecx
0x180152c28  jmp     loc_180152B29
0x180152c2d  cmp     r14d, 3
0x180152c31  jnb     short loc_180152C54
0x180152c33  test    r12d, r12d
0x180152c36  jz      loc_1801538D9
0x180152c3c  movzx   eax, byte ptr [r13+0]
0x180152c41  mov     ecx, r14d
0x180152c44  shl     eax, cl
0x180152c46  dec     r12d
0x180152c49  add     ebp, eax
0x180152c4b  inc     r13
0x180152c4e  add     r14d, 8
0x180152c52  jmp     short loc_180152C2D
0x180152c54  mov     eax, ebp
0x180152c56  shr     ebp, 1
0x180152c58  and     eax, 1
0x180152c5b  mov     [rdi+0Ch], eax
0x180152c5e  mov     eax, ebp
0x180152c60  and     eax, 3
0x180152c63  jz      short loc_180152CBE
0x180152c65  sub     eax, 1
0x180152c68  jz      short loc_180152C91
0x180152c6a  sub     eax, 1
0x180152c6d  jz      short loc_180152C88
0x180152c6f  cmp     eax, 1
0x180152c72  jnz     short loc_180152CC5
0x180152c74  lea     rax, aInvalidBlockTy; "invalid block type"
0x180152c7b  mov     [rsi+20h], rax
0x180152c7f  mov     dword ptr [rdi+8], 3F51h
0x180152c86  jmp     short loc_180152CC5
0x180152c88  mov     dword ptr [rdi+8], 3F44h
0x180152c8f  jmp     short loc_180152CC5
0x180152c91  lea     rax, asc_180191870; "`\a"
0x180152c98  mov     dword ptr [r15], 9
0x180152c9f  mov     [rdi+60h], rax
0x180152ca3  lea     rax, qword_1801920A0
0x180152caa  mov     [rdi+68h], rax
0x180152cae  mov     dword ptr [r8], 5
0x180152cb5  mov     dword ptr [rdi+8], 3F47h
0x180152cbc  jmp     short loc_180152CC5
0x180152cbe  mov     dword ptr [rdi+8], 3F41h
0x180152cc5  shr     ebp, 2
0x180152cc8  add     r14d, 0FFFFFFFDh
0x180152ccc  jmp     loc_180152B29
0x180152cd1  cmp     [rdi+10h], ebx
0x180152cd4  jnz     short loc_180152CE2
0x180152cd6  mov     dword ptr [rdi+8], 3F40h
0x180152cdd  jmp     loc_180152B29
0x180152ce2  cmp     r14d, 10h
0x180152ce6  jnb     short loc_180152D09
0x180152ce8  test    r12d, r12d
0x180152ceb  jz      loc_1801538D9
0x180152cf1  movzx   eax, byte ptr [r13+0]
0x180152cf6  mov     ecx, r14d
0x180152cf9  shl     eax, cl
0x180152cfb  dec     r12d
0x180152cfe  add     ebp, eax
0x180152d00  inc     r13
0x180152d03  add     r14d, 8
0x180152d07  jmp     short loc_180152CE2
0x180152d09  movzx   ecx, bpl
0x180152d0d  mov     eax, ebp
0x180152d0f  shr     eax, 8
0x180152d12  shl     ecx, 8
0x180152d15  add     ecx, eax
0x180152d17  mov     eax, 8421085h
0x180152d1c  mul     ecx
0x180152d1e  mov     eax, ecx
0x180152d20  sub     eax, edx
0x180152d22  shr     eax, 1
0x180152d24  add     eax, edx
0x180152d26  shr     eax, 4
0x180152d29  imul    eax, 1Fh
0x180152d2c  cmp     ecx, eax
0x180152d2e  jz      short loc_180152D4E
0x180152d30  lea     rax, aIncorrectHeade; "incorrect header check"
0x180152d37  mov     edx, [rsp+78h+arg_8]
0x180152d3e  mov     [rsi+20h], rax
0x180152d42  mov     dword ptr [rdi+8], 3F51h
0x180152d49  jmp     loc_180152B29
0x180152d4e  mov     eax, ebp
0x180152d50  and     al, 0Fh
0x180152d52  cmp     al, 8
0x180152d54  jz      short loc_180152D5F
0x180152d56  lea     rax, aUnknownCompres; "unknown compression method"
0x180152d5d  jmp     short loc_180152D37
0x180152d5f  mov     eax, [rdi+30h]
0x180152d62  shr     ebp, 4
0x180152d65  mov     ecx, ebp
0x180152d67  and     ecx, 0Fh
0x180152d6a  add     ecx, 8
0x180152d6d  test    eax, eax
0x180152d6f  jnz     short loc_180152D76
0x180152d71  mov     [rdi+30h], ecx
0x180152d74  mov     eax, ecx
0x180152d76  cmp     ecx, 0Fh
0x180152d79  ja      short loc_180152DCD
0x180152d7b  cmp     ecx, eax
0x180152d7d  ja      short loc_180152DCD
0x180152d7f  mov     eax, 1
0x180152d84  mov     [rdi+18h], ebx
0x180152d87  shl     eax, cl
0x180152d89  xor     r8d, r8d
0x180152d8c  xor     ecx, ecx
0x180152d8e  mov     [rdi+1Ch], eax
0x180152d91  xor     edx, edx
0x180152d93  call    adler32_z
0x180152d98  shr     ebp, 8
0x180152d9b  mov     r14d, ebx
0x180152d9e  not     ebp
0x180152da0  mov     [rdi+20h], eax
0x180152da3  and     ebp, 2
0x180152da6  mov     [rsi+4Ch], eax
0x180152da9  or      ebp, 3F3Dh
0x180152daf  mov     [rdi+8], ebp
0x180152db2  mov     ebp, ebx
0x180152db4  mov     edx, [rsp+78h+arg_8]
0x180152dbb  mov     r9d, [rsp+78h+arg_18]
0x180152dc3  mov     r10, [rsp+78h+var_40]
0x180152dc8  jmp     loc_180152B1F
0x180152dcd  add     r14d, 0FFFFFFFCh
0x180152dd1  lea     rax, aInvalidWindowS; "invalid window size"
0x180152dd8  jmp     loc_180152D37
0x180152ddd  mov     ecx, r14d
0x180152de0  and     ecx, r11d
0x180152de3  shr     ebp, cl
0x180152de5  sub     r14d, ecx
0x180152de8  cmp     r14d, 20h ; ' '
0x180152dec  jnb     short loc_180152E0F
0x180152dee  test    r12d, r12d
0x180152df1  jz      loc_1801538D9
0x180152df7  movzx   eax, byte ptr [r13+0]
0x180152dfc  mov     ecx, r14d
0x180152dff  shl     eax, cl
0x180152e01  dec     r12d
0x180152e04  add     ebp, eax
0x180152e06  inc     r13
0x180152e09  add     r14d, 8
0x180152e0d  jmp     short loc_180152DE8
0x180152e0f  mov     eax, ebp
0x180152e11  movzx   ecx, bp
0x180152e14  not     eax
0x180152e16  shr     eax, 10h
0x180152e19  cmp     ecx, eax
0x180152e1b  jz      short loc_180152E29
0x180152e1d  lea     rax, aInvalidStoredB; "invalid stored block lengths"
0x180152e24  jmp     loc_18015386E
0x180152e29  mov     [rdi+50h], ecx
0x180152e2c  mov     ebp, ebx
0x180152e2e  mov     r14d, ebx
0x180152e31  mov     dword ptr [rdi+8], 3F43h
0x180152e38  mov     eax, [rdi+50h]
0x180152e3b  test    eax, eax
0x180152e3d  jz      loc_180153338
0x180152e43  cmp     eax, r12d
0x180152e46  mov     r15d, r12d
0x180152e49  cmovbe  r15d, eax
0x180152e4d  cmp     r15d, r9d
0x180152e50  cmova   r15d, r9d
0x180152e54  test    r15d, r15d
0x180152e57  jz      loc_1801538D9
0x180152e5d  mov     r8d, r15d; Size
0x180152e60  mov     rdx, r13; Src
0x180152e63  mov     rcx, r10; void *
0x180152e66  mov     ebx, r15d
0x180152e69  call    memmove
0x180152e6e  mov     r9d, [rsp+78h+arg_18]
0x180152e76  sub     r12d, r15d
0x180152e79  mov     r10, [rsp+78h+var_40]
0x180152e7e  sub     r9d, r15d
0x180152e81  add     r10, rbx
0x180152e84  mov     [rsp+78h+arg_18], r9d
0x180152e8c  add     r13, rbx
0x180152e8f  mov     [rsp+78h+var_40], r10
0x180152e94  sub     [rdi+50h], r15d
0x180152e98  mov     edx, [rsp+78h+arg_8]
0x180152e9f  xor     ebx, ebx
0x180152ea1  jmp     loc_180152B1B
0x180152ea6  sub     ecx, 3F42h
0x180152eac  jz      short loc_180152E31
0x180152eae  sub     ecx, 1
0x180152eb1  jz      short loc_180152E38
0x180152eb3  sub     ecx, 1
0x180152eb6  jz      short loc_180152ECF
0x180152eb8  sub     ecx, 1
0x180152ebb  jz      loc_180152F4B
0x180152ec1  cmp     ecx, 1
0x180152ec4  jnz     loc_180152B78
0x180152eca  jmp     loc_180153031
0x180152ecf  cmp     r14d, 0Eh
0x180152ed3  jnb     short loc_180152EF6
0x180152ed5  test    r12d, r12d
0x180152ed8  jz      loc_1801538D9
  ... truncated ...
```

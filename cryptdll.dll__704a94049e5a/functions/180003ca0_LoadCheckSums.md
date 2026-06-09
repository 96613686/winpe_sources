# LoadCheckSums

- ea: `0x180003ca0`
- end: `0x180004081`
- name: `LoadCheckSums`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005658`

## callees

- `0x180003ca0`

## pseudocode

```c
__int64 LoadCheckSums()
{
  unsigned __int64 v0; // rax
  unsigned int v1; // ecx
  unsigned __int64 v2; // rax
  unsigned int v3; // ecx
  unsigned __int64 v4; // rax
  unsigned int v5; // ecx
  unsigned __int64 v6; // rax
  unsigned int v7; // ecx
  unsigned __int64 v8; // rax
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  unsigned int v11; // ecx
  unsigned __int64 v12; // rax
  unsigned int v13; // ecx
  unsigned __int64 v14; // rax
  unsigned int v15; // ecx
  unsigned __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned __int64 v20; // rax
  unsigned int v21; // ecx
  unsigned __int64 v22; // rax
  unsigned int v23; // ecx
  unsigned __int64 v24; // rax
  unsigned int v25; // ecx
  unsigned __int64 v26; // rax

  if ( (unsigned int)cCheckSums < 0x18 )
  {
    v0 = (unsigned __int64)(unsigned int)cCheckSums++ << 6;
    v1 = cCheckSums;
    *(_OWORD *)((char *)CheckSumFns + v0) = csfMD5_HMAC;
    *(_OWORD *)((char *)&CheckSumFns[2] + v0) = *(_OWORD *)off_18000A070;
    *(_OWORD *)((char *)&CheckSumFns[4] + v0) = *(_OWORD *)&off_18000A080;
    *(_OWORD *)((char *)&CheckSumFns[6] + v0) = *(_OWORD *)&off_18000A090;
    if ( v1 < 0x18 )
    {
      v2 = (unsigned __int64)v1 << 6;
      v3 = v1 + 1;
      cCheckSums = v3;
      *(_OWORD *)((char *)CheckSumFns + v2) = csfHMAC_MD5;
      *(_OWORD *)((char *)&CheckSumFns[2] + v2) = *(_OWORD *)off_18000A0B0;
      *(_OWORD *)((char *)&CheckSumFns[4] + v2) = *(_OWORD *)&off_18000A0C0;
      *(_OWORD *)((char *)&CheckSumFns[6] + v2) = *(_OWORD *)&off_18000A0D0;
      if ( v3 < 0x18 )
      {
        v4 = (unsigned __int64)v3 << 6;
        v5 = v3 + 1;
        cCheckSums = v5;
        *(_OWORD *)((char *)CheckSumFns + v4) = csfMD4;
        *(_OWORD *)((char *)&CheckSumFns[2] + v4) = *(_OWORD *)&off_18000A030;
        *(_OWORD *)((char *)&CheckSumFns[4] + v4) = *(_OWORD *)off_18000A040;
        *(_OWORD *)((char *)&CheckSumFns[6] + v4) = *(_OWORD *)&off_18000A050;
        if ( v5 < 0x18 )
        {
          v6 = (unsigned __int64)v5 << 6;
          v7 = v5 + 1;
          cCheckSums = v7;
          *(_OWORD *)((char *)CheckSumFns + v6) = csfMD5;
          *(_OWORD *)((char *)&CheckSumFns[2] + v6) = *(_OWORD *)off_18000A0F0;
          *(_OWORD *)((char *)&CheckSumFns[4] + v6) = *(_OWORD *)off_18000A100;
          *(_OWORD *)((char *)&CheckSumFns[6] + v6) = *(_OWORD *)&off_18000A110;
          if ( v7 < 0x18 )
          {
            v8 = (unsigned __int64)v7 << 6;
            v9 = v7 + 1;
            cCheckSums = v9;
            *(_OWORD *)((char *)CheckSumFns + v8) = csfKERB_CRC32;
            *(_OWORD *)((char *)&CheckSumFns[2] + v8) = *(_OWORD *)off_18000A470;
            *(_OWORD *)((char *)&CheckSumFns[4] + v8) = *(_OWORD *)off_18000A480;
            *(_OWORD *)((char *)&CheckSumFns[6] + v8) = *(_OWORD *)&off_18000A490;
            if ( v9 < 0x18 )
            {
              v10 = (unsigned __int64)v9 << 6;
              v11 = v9 + 1;
              cCheckSums = v11;
              *(_OWORD *)((char *)CheckSumFns + v10) = csfCRC32;
              *(_OWORD *)((char *)&CheckSumFns[2] + v10) = *(_OWORD *)off_18000A4B0;
              *(_OWORD *)((char *)&CheckSumFns[4] + v10) = *(_OWORD *)off_18000A4C0;
              *(_OWORD *)((char *)&CheckSumFns[6] + v10) = *(_OWORD *)&off_18000A4D0;
              if ( v11 < 0x18 )
              {
                v12 = (unsigned __int64)v11 << 6;
                v13 = v11 + 1;
                cCheckSums = v13;
                *(_OWORD *)((char *)CheckSumFns + v12) = csfHMAC_SHA_96_AES128;
                *(_OWORD *)((char *)&CheckSumFns[2] + v12) = *(_OWORD *)off_18000A1F0;
                *(_OWORD *)((char *)&CheckSumFns[4] + v12) = *(_OWORD *)off_18000A200;
                *(_OWORD *)((char *)&CheckSumFns[6] + v12) = *(_OWORD *)&off_18000A210;
                if ( v13 < 0x18 )
                {
                  v14 = (unsigned __int64)v13 << 6;
                  v15 = v13 + 1;
                  cCheckSums = v15;
                  *(_OWORD *)((char *)CheckSumFns + v14) = csfHMAC_SHA_96_AES256;
                  *(_OWORD *)((char *)&CheckSumFns[2] + v14) = *(_OWORD *)off_18000A1B0;
                  *(_OWORD *)((char *)&CheckSumFns[4] + v14) = *(_OWORD *)off_18000A1C0;
                  *(_OWORD *)((char *)&CheckSumFns[6] + v14) = *(_OWORD *)&off_18000A1D0;
                  if ( v15 < 0x18 )
                  {
                    v16 = (unsigned __int64)v15 << 6;
                    v17 = v15 + 1;
                    cCheckSums = v17;
                    *(_OWORD *)((char *)CheckSumFns + v16) = csfHMAC_SHA_96_AES128_Ki;
                    *(_OWORD *)((char *)&CheckSumFns[2] + v16) = *(_OWORD *)off_18000A170;
                    *(_OWORD *)((char *)&CheckSumFns[4] + v16) = *(_OWORD *)off_18000A180;
                    *(_OWORD *)((char *)&CheckSumFns[6] + v16) = *(_OWORD *)&off_18000A190;
                    if ( v17 < 0x18 )
                    {
                      v18 = (unsigned __int64)v17 << 6;
                      v19 = v17 + 1;
                      cCheckSums = v19;
                      *(_OWORD *)((char *)CheckSumFns + v18) = csfHMAC_SHA_96_AES256_Ki;
                      *(_OWORD *)((char *)&CheckSumFns[2] + v18) = *(_OWORD *)off_18000A230;
                      *(_OWORD *)((char *)&CheckSumFns[4] + v18) = *(_OWORD *)off_18000A240;
                      *(_OWORD *)((char *)&CheckSumFns[6] + v18) = *(_OWORD *)&off_18000A250;
                      if ( v19 < 0x18 )
                      {
                        v20 = (unsigned __int64)v19 << 6;
                        v21 = v19 + 1;
                        cCheckSums = v21;
                        *(_OWORD *)((char *)CheckSumFns + v20) = csfSHA;
                        *(_OWORD *)((char *)&CheckSumFns[2] + v20) = *(_OWORD *)&off_18000A4F0;
                        *(_OWORD *)((char *)&CheckSumFns[4] + v20) = *(_OWORD *)off_18000A500;
                        *(_OWORD *)((char *)&CheckSumFns[6] + v20) = *(_OWORD *)&off_18000A510;
                        if ( v21 < 0x18 )
                        {
                          v22 = (unsigned __int64)v21 << 6;
                          v23 = v21 + 1;
                          cCheckSums = v23;
                          *(_OWORD *)((char *)CheckSumFns + v22) = csfSHA256;
                          *(_OWORD *)((char *)&CheckSumFns[2] + v22) = *(_OWORD *)off_18000A570;
                          *(_OWORD *)((char *)&CheckSumFns[4] + v22) = *(_OWORD *)off_18000A580;
                          *(_OWORD *)((char *)&CheckSumFns[6] + v22) = *(_OWORD *)&off_18000A590;
                          if ( v23 < 0x18 )
                          {
                            v24 = (unsigned __int64)v23 << 6;
                            v25 = v23 + 1;
                            cCheckSums = v25;
                            *(_OWORD *)((char *)CheckSumFns + v24) = csfSHA384;
                            *(_OWORD *)((char *)&CheckSumFns[2] + v24) = *(_OWORD *)off_18000A530;
                            *(_OWORD *)((char *)&CheckSumFns[4] + v24) = *(_OWORD *)off_18000A540;
                            *(_OWORD *)((char *)&CheckSumFns[6] + v24) = *(_OWORD *)&off_18000A550;
                            if ( v25 < 0x18 )
                            {
                              v26 = (unsigned __int64)v25 << 6;
                              *(_OWORD *)((char *)CheckSumFns + v26) = csfSHA512;
                              *(_OWORD *)((char *)&CheckSumFns[2] + v26) = *(_OWORD *)off_18000A130;
                              *(_OWORD *)((char *)&CheckSumFns[4] + v26) = *(_OWORD *)off_18000A140;
                              *(_OWORD *)((char *)&CheckSumFns[6] + v26) = *(_OWORD *)&off_18000A150;
                              cCheckSums = v25 + 1;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003ca0  mov     ecx, cs:cCheckSums
0x180003ca6  cmp     ecx, 18h
0x180003ca9  jnb     loc_18000407E
0x180003caf  movaps  xmm0, cs:csfMD5_HMAC
0x180003cb6  lea     rdx, CheckSumFns
0x180003cbd  movaps  xmm1, xmmword ptr cs:off_18000A070
0x180003cc4  mov     eax, ecx
0x180003cc6  shl     rax, 6
0x180003cca  inc     ecx
0x180003ccc  mov     cs:cCheckSums, ecx
0x180003cd2  movups  xmmword ptr [rax+rdx], xmm0
0x180003cd6  movaps  xmm0, xmmword ptr cs:off_18000A080
0x180003cdd  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003ce2  movaps  xmm1, xmmword ptr cs:off_18000A090
0x180003ce9  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003cee  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003cf3  cmp     ecx, 18h
0x180003cf6  jnb     loc_18000407E
0x180003cfc  movaps  xmm0, cs:csfHMAC_MD5
0x180003d03  movaps  xmm1, xmmword ptr cs:off_18000A0B0
0x180003d0a  mov     eax, ecx
0x180003d0c  shl     rax, 6
0x180003d10  inc     ecx
0x180003d12  mov     cs:cCheckSums, ecx
0x180003d18  movups  xmmword ptr [rax+rdx], xmm0
0x180003d1c  movaps  xmm0, xmmword ptr cs:off_18000A0C0
0x180003d23  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003d28  movaps  xmm1, xmmword ptr cs:off_18000A0D0
0x180003d2f  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003d34  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003d39  cmp     ecx, 18h
0x180003d3c  jnb     loc_18000407E
0x180003d42  movaps  xmm0, cs:csfMD4
0x180003d49  movaps  xmm1, xmmword ptr cs:off_18000A030
0x180003d50  mov     eax, ecx
0x180003d52  shl     rax, 6
0x180003d56  inc     ecx
0x180003d58  mov     cs:cCheckSums, ecx
0x180003d5e  movups  xmmword ptr [rax+rdx], xmm0
0x180003d62  movaps  xmm0, xmmword ptr cs:off_18000A040
0x180003d69  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003d6e  movaps  xmm1, xmmword ptr cs:off_18000A050
0x180003d75  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003d7a  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003d7f  cmp     ecx, 18h
0x180003d82  jnb     loc_18000407E
0x180003d88  movaps  xmm0, cs:csfMD5
0x180003d8f  movaps  xmm1, xmmword ptr cs:off_18000A0F0
0x180003d96  mov     eax, ecx
0x180003d98  shl     rax, 6
0x180003d9c  inc     ecx
0x180003d9e  mov     cs:cCheckSums, ecx
0x180003da4  movups  xmmword ptr [rax+rdx], xmm0
0x180003da8  movaps  xmm0, xmmword ptr cs:off_18000A100
0x180003daf  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003db4  movaps  xmm1, xmmword ptr cs:off_18000A110
0x180003dbb  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003dc0  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003dc5  cmp     ecx, 18h
0x180003dc8  jnb     loc_18000407E
0x180003dce  movaps  xmm0, cs:csfKERB_CRC32
0x180003dd5  movaps  xmm1, xmmword ptr cs:off_18000A470
0x180003ddc  mov     eax, ecx
0x180003dde  shl     rax, 6
0x180003de2  inc     ecx
0x180003de4  mov     cs:cCheckSums, ecx
0x180003dea  movups  xmmword ptr [rax+rdx], xmm0
0x180003dee  movaps  xmm0, xmmword ptr cs:off_18000A480
0x180003df5  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003dfa  movaps  xmm1, xmmword ptr cs:off_18000A490
0x180003e01  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003e06  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003e0b  cmp     ecx, 18h
0x180003e0e  jnb     loc_18000407E
0x180003e14  movaps  xmm0, cs:csfCRC32
0x180003e1b  movaps  xmm1, xmmword ptr cs:off_18000A4B0
0x180003e22  mov     eax, ecx
0x180003e24  shl     rax, 6
0x180003e28  inc     ecx
0x180003e2a  mov     cs:cCheckSums, ecx
0x180003e30  movups  xmmword ptr [rax+rdx], xmm0
0x180003e34  movaps  xmm0, xmmword ptr cs:off_18000A4C0
0x180003e3b  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003e40  movaps  xmm1, xmmword ptr cs:off_18000A4D0
0x180003e47  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003e4c  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003e51  cmp     ecx, 18h
0x180003e54  jnb     loc_18000407E
0x180003e5a  movaps  xmm0, cs:csfHMAC_SHA_96_AES128
0x180003e61  movaps  xmm1, xmmword ptr cs:off_18000A1F0
0x180003e68  mov     eax, ecx
0x180003e6a  shl     rax, 6
0x180003e6e  inc     ecx
0x180003e70  mov     cs:cCheckSums, ecx
0x180003e76  movups  xmmword ptr [rax+rdx], xmm0
0x180003e7a  movaps  xmm0, xmmword ptr cs:off_18000A200
0x180003e81  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003e86  movaps  xmm1, xmmword ptr cs:off_18000A210
0x180003e8d  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003e92  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003e97  cmp     ecx, 18h
0x180003e9a  jnb     loc_18000407E
0x180003ea0  movaps  xmm0, cs:csfHMAC_SHA_96_AES256
0x180003ea7  movaps  xmm1, xmmword ptr cs:off_18000A1B0
0x180003eae  mov     eax, ecx
0x180003eb0  shl     rax, 6
0x180003eb4  inc     ecx
0x180003eb6  mov     cs:cCheckSums, ecx
0x180003ebc  movups  xmmword ptr [rax+rdx], xmm0
0x180003ec0  movaps  xmm0, xmmword ptr cs:off_18000A1C0
0x180003ec7  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003ecc  movaps  xmm1, xmmword ptr cs:off_18000A1D0
0x180003ed3  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003ed8  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003edd  cmp     ecx, 18h
0x180003ee0  jnb     loc_18000407E
0x180003ee6  movaps  xmm0, cs:csfHMAC_SHA_96_AES128_Ki
0x180003eed  movaps  xmm1, xmmword ptr cs:off_18000A170
0x180003ef4  mov     eax, ecx
0x180003ef6  shl     rax, 6
0x180003efa  inc     ecx
0x180003efc  mov     cs:cCheckSums, ecx
0x180003f02  movups  xmmword ptr [rax+rdx], xmm0
0x180003f06  movaps  xmm0, xmmword ptr cs:off_18000A180
0x180003f0d  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003f12  movaps  xmm1, xmmword ptr cs:off_18000A190
0x180003f19  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003f1e  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003f23  cmp     ecx, 18h
0x180003f26  jnb     loc_18000407E
0x180003f2c  movaps  xmm0, cs:csfHMAC_SHA_96_AES256_Ki
0x180003f33  movaps  xmm1, xmmword ptr cs:off_18000A230
0x180003f3a  mov     eax, ecx
0x180003f3c  shl     rax, 6
0x180003f40  inc     ecx
0x180003f42  mov     cs:cCheckSums, ecx
0x180003f48  movups  xmmword ptr [rax+rdx], xmm0
0x180003f4c  movaps  xmm0, xmmword ptr cs:off_18000A240
0x180003f53  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003f58  movaps  xmm1, xmmword ptr cs:off_18000A250
0x180003f5f  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003f64  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003f69  cmp     ecx, 18h
0x180003f6c  jnb     loc_18000407E
0x180003f72  movaps  xmm0, cs:csfSHA
0x180003f79  movaps  xmm1, xmmword ptr cs:off_18000A4F0
0x180003f80  mov     eax, ecx
0x180003f82  shl     rax, 6
0x180003f86  inc     ecx
0x180003f88  mov     cs:cCheckSums, ecx
0x180003f8e  movups  xmmword ptr [rax+rdx], xmm0
0x180003f92  movaps  xmm0, xmmword ptr cs:off_18000A500
0x180003f99  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003f9e  movaps  xmm1, xmmword ptr cs:off_18000A510
0x180003fa5  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003faa  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003faf  cmp     ecx, 18h
0x180003fb2  jnb     loc_18000407E
0x180003fb8  movaps  xmm0, cs:csfSHA256
0x180003fbf  movaps  xmm1, xmmword ptr cs:off_18000A570
0x180003fc6  mov     eax, ecx
0x180003fc8  shl     rax, 6
0x180003fcc  inc     ecx
0x180003fce  mov     cs:cCheckSums, ecx
0x180003fd4  movups  xmmword ptr [rax+rdx], xmm0
0x180003fd8  movaps  xmm0, xmmword ptr cs:off_18000A580
0x180003fdf  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180003fe4  movaps  xmm1, xmmword ptr cs:off_18000A590
0x180003feb  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180003ff0  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180003ff5  cmp     ecx, 18h
0x180003ff8  jnb     loc_18000407E
0x180003ffe  movaps  xmm0, cs:csfSHA384
0x180004005  movaps  xmm1, xmmword ptr cs:off_18000A530
0x18000400c  mov     eax, ecx
0x18000400e  shl     rax, 6
0x180004012  inc     ecx
0x180004014  mov     cs:cCheckSums, ecx
0x18000401a  movups  xmmword ptr [rax+rdx], xmm0
0x18000401e  movaps  xmm0, xmmword ptr cs:off_18000A540
0x180004025  movups  xmmword ptr [rax+rdx+10h], xmm1
0x18000402a  movaps  xmm1, xmmword ptr cs:off_18000A550
0x180004031  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004036  movups  xmmword ptr [rax+rdx+30h], xmm1
0x18000403b  cmp     ecx, 18h
0x18000403e  jnb     short loc_18000407E
0x180004040  movaps  xmm0, cs:csfSHA512
0x180004047  movaps  xmm1, xmmword ptr cs:off_18000A130
0x18000404e  mov     eax, ecx
0x180004050  shl     rax, 6
0x180004054  movups  xmmword ptr [rax+rdx], xmm0
0x180004058  movaps  xmm0, xmmword ptr cs:off_18000A140
0x18000405f  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180004064  movaps  xmm1, xmmword ptr cs:off_18000A150
0x18000406b  movups  xmmword ptr [rax+rdx+20h], xmm0
0x180004070  movups  xmmword ptr [rax+rdx+30h], xmm1
0x180004075  lea     eax, [rcx+1]
0x180004078  mov     cs:cCheckSums, eax
0x18000407e  xor     eax, eax
0x180004080  retn
```

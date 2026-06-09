# RtlConvertNtFilePathToWin32FilePath

- ea: `0x180005b30`
- end: `0x180005fb2`
- name: `RtlConvertNtFilePathToWin32FilePath`
- size: `1154`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800056f0`

## callees

- `0x180005b30`
- `0x180008220`
- `0x180009dc0`
- `0x18000a8e0`

## string_xrefs

- `0x180005b5b`: `onecore\base\lstring\path.cpp`
- `0x180005baa`: `onecore\base\lstring\path.cpp`
- `0x180005ece`: `onecore\base\lstring\path.cpp`
- `0x180005b7c`: `Not-null check failed: PathIn`
- `0x180005bcb`: `Not-null check failed: PathOut`
- `0x180005b70`: `RtlConvertNtFilePathToWin32FilePath`
- `0x180005bbf`: `RtlConvertNtFilePathToWin32FilePath`
- `0x180005ee9`: `RtlConvertNtFilePathToWin32FilePath`

## pseudocode

```c
__int64 __fastcall RtlConvertNtFilePathToWin32FilePath(const __m128i *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  const char *v6; // rax
  __int64 result; // rax
  unsigned __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rbx
  bool v13; // zf
  const char **v14; // r8
  const char *v15; // rax
  __m128i v16; // xmm2
  unsigned __int64 v17; // rcx
  __int64 v18; // xmm1_8
  __m128i v19; // xmm0
  unsigned __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-E0h]
  const char *v22; // [rsp+30h] [rbp-D0h] BYREF
  const char *v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h]
  const char *v25; // [rsp+48h] [rbp-B8h]
  _DWORD v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v27[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v28[2]; // [rsp+78h] [rbp-88h]
  _QWORD v29[49]; // [rsp+88h] [rbp-78h]
  __int128 v30; // [rsp+210h] [rbp+110h] BYREF
  __int64 v31; // [rsp+220h] [rbp+120h]
  __m128i v32; // [rsp+228h] [rbp+128h]
  unsigned __int64 v33; // [rsp+238h] [rbp+138h]
  __int64 v34; // [rsp+240h] [rbp+140h]
  __int64 v35; // [rsp+248h] [rbp+148h]
  const WCHAR *v36; // [rsp+250h] [rbp+150h]

  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v24 = 456;
    v22 = "onecore\\base\\lstring\\path.cpp";
    v23 = "RtlConvertNtFilePathToWin32FilePath";
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v25 = v6;
    RtlReportErrorOrigination(a1, a2, 3221225485LL, a4);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v24 = 457;
    v22 = "onecore\\base\\lstring\\path.cpp";
    v23 = "RtlConvertNtFilePathToWin32FilePath";
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v8 = -1;
  v9 = 2147352624;
  do
    ++v8;
  while ( *(_WORD *)(2 * v8 + 0x7FFE0030) );
  if ( v8 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v10 = 2 * v8;
    v27[2] = L"\\??\\UNC\\";
    v29[0] = L"\\\\";
    v29[3] = L"\\??\\HardDisk";
    v29[24] = L"\\\\";
    v29[6] = L"\\\\?\\HardDisk";
    v11 = v10 - 2;
    v27[0] = 16;
    v29[9] = L"\\??\\Volume";
    v27[1] = 18;
    v29[12] = L"\\\\?\\Volume";
    v12 = 0;
    v28[0] = 4;
    v29[15] = L"\\??\\";
    v29[21] = L"\\DosDevices\\UNC\\";
    v29[27] = L"\\DosDevices\\";
    v29[33] = L"\\SystemRoot";
    v28[1] = 6;
    v29[1] = 24;
    v29[2] = 26;
    v13 = *(_WORD *)(2 * (v10 >> 1) + 0x7FFE002E) == 92;
    v29[39] = L"\\Device\\HarddiskVolume";
    v29[42] = L"\\\\?\\HarddiskVolume";
    if ( !v13 )
      v11 = v10;
    v29[4] = 24;
    v29[45] = L"\\Device\\Mup";
    v29[48] = L"\\\\?\\UNC";
    v29[5] = 26;
    v29[7] = 20;
    v29[8] = 22;
    v29[10] = 20;
    v29[11] = 22;
    v29[13] = 8;
    v29[14] = 10;
    v29[16] = 0;
    v29[17] = 2;
    v29[18] = &LocaleName;
    v29[19] = 32;
    v29[20] = 34;
    v29[22] = 4;
    v29[23] = 6;
    v29[25] = 24;
    v29[26] = 26;
    v29[28] = 0;
    v29[29] = 2;
    v29[30] = &LocaleName;
    v29[31] = 22;
    v29[32] = 24;
    v29[34] = v11;
    v29[35] = v10 + 2;
    v29[36] = 2147352624;
    v29[37] = 44;
    v29[38] = 46;
    v29[40] = 36;
    v29[41] = 38;
    v29[43] = 22;
    v29[44] = 24;
    v29[46] = 14;
    v29[47] = 16;
    while ( 1 )
    {
      v14 = (const char **)&v27[6 * v12];
      v15 = *v14;
      if ( (unsigned __int64)*v14 <= a1->m128i_i64[0] )
      {
        v22 = (const char *)v27[6 * v12];
        v23 = v15;
        v24 = a1[1].m128i_i64[0];
        v26[0] = 0;
        result = RtlCompareEncodedLBlobs((unsigned int)&v22, v10, (_DWORD)v14, v9, v21, (__int64)v26);
        if ( (int)result < 0 )
          return result;
        if ( !v26[0] )
          break;
      }
      if ( (unsigned __int64)++v12 >= 9 )
      {
        if ( v12 == 9 )
        {
          v24 = 507;
          v22 = "onecore\\base\\lstring\\path.cpp";
          v25 = 0;
          v23 = "RtlConvertNtFilePathToWin32FilePath";
          RtlReportErrorOrigination(v11, v10, 3221225529LL, v9);
          return 3221225529LL;
        }
        break;
      }
    }
    v16 = _mm_loadu_si128(a1);
    v34 = 2;
    v35 = 2;
    v36 = &LocaleName;
    v17 = v27[6 * v12];
    v18 = v29[6 * v12];
    v30 = *(_OWORD *)&v28[6 * v12];
    v19 = (__m128i)v17;
    v20 = a1[1].m128i_i64[0] + v17;
    v31 = v18;
    v32 = _mm_sub_epi64(v16, _mm_unpacklo_epi64(v19, v19));
    v33 = v20;
    result = RtlConcatenateLUnicodeStrings(v20, v10, &v30, a2);
    if ( (int)result >= 0 )
    {
      if ( *a2 > 2u )
        *a2 -= 2LL;
      return 0;
    }
  }
  else
  {
    v24 = 393;
    v22 = "onecore\\base\\lstring\\lunicode_string.cpp";
    v23 = "RtlInitLUnicodeStringFromNullTerminatedString";
    v25 = "cch <= (((((SIZE_T)~((SIZE_T)0)) - (((SIZE_T)~((SIZE_T)0)) % sizeof(WCHAR))) / sizeof(WCHAR)) - 1)";
    RtlReportErrorOrigination(a1, v8, 3221226539LL, 2147352624);
    return 3221226539LL;
  }
  return result;
}

```

## disassembly

```asm
0x180005b30  push    rbp
0x180005b32  push    rsi
0x180005b33  push    rdi
0x180005b34  push    r14
0x180005b36  lea     rbp, [rsp-168h]
0x180005b3e  sub     rsp, 268h
0x180005b45  xor     r14d, r14d
0x180005b48  mov     rsi, rdx
0x180005b4b  mov     rdi, rcx
0x180005b4e  test    rdx, rdx
0x180005b51  jz      short loc_180005B56
0x180005b53  mov     [rdx], r14
0x180005b56  test    rdi, rdi
0x180005b59  jnz     short loc_180005BA5
0x180005b5b  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180005b62  mov     [rsp+280h+var_240], 1C8h
0x180005b6b  mov     [rsp+280h+var_250], rax
0x180005b70  lea     rax, aRtlconvertntfi; "RtlConvertNtFilePathToWin32FilePath"
0x180005b77  mov     [rsp+280h+var_248], rax
0x180005b7c  lea     rax, aNotNullCheckFa_1; "Not-null check failed: PathIn"
0x180005b83  mov     r8d, 0C000000Dh
0x180005b89  mov     [rsp+280h+var_238], rax
0x180005b8e  call    RtlReportErrorOrigination
0x180005b93  mov     eax, 0C000000Dh
0x180005b98  add     rsp, 268h
0x180005b9f  pop     r14
0x180005ba1  pop     rdi
0x180005ba2  pop     rsi
0x180005ba3  pop     rbp
0x180005ba4  retn
0x180005ba5  test    rsi, rsi
0x180005ba8  jnz     short loc_180005BD4
0x180005baa  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180005bb1  mov     [rsp+280h+var_240], 1C9h
0x180005bba  mov     [rsp+280h+var_250], rax
0x180005bbf  lea     rax, aRtlconvertntfi; "RtlConvertNtFilePathToWin32FilePath"
0x180005bc6  mov     [rsp+280h+var_248], rax
0x180005bcb  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x180005bd2  jmp     short loc_180005B83
0x180005bd4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180005bdb  mov     r9d, 7FFE0030h
0x180005be1  inc     rdx
0x180005be4  cmp     [r9+rdx*2], r14w
0x180005be9  jnz     short loc_180005BE1
0x180005beb  mov     rax, 7FFFFFFFFFFFFFFEh
0x180005bf5  cmp     rdx, rax
0x180005bf8  jbe     short loc_180005C44
0x180005bfa  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lunicode_string"...
0x180005c01  mov     [rsp+280h+var_240], 189h
0x180005c0a  mov     [rsp+280h+var_250], rax
0x180005c0f  mov     r8d, 0C000042Bh
0x180005c15  lea     rax, aRtlinitlunicod; "RtlInitLUnicodeStringFromNullTerminated"...
0x180005c1c  mov     [rsp+280h+var_248], rax
0x180005c21  lea     rax, aCchSizeTSizeT0; "cch <= (((((SIZE_T)~((SIZE_T)0)) - (((S"...
0x180005c28  mov     [rsp+280h+var_238], rax
0x180005c2d  call    RtlReportErrorOrigination
0x180005c32  mov     eax, 0C000042Bh
0x180005c37  add     rsp, 268h
0x180005c3e  pop     r14
0x180005c40  pop     rdi
0x180005c41  pop     rsi
0x180005c42  pop     rbp
0x180005c43  retn
0x180005c44  add     rdx, rdx
0x180005c47  mov     [rsp+280h+arg_10], rbx
0x180005c4f  lea     rax, aUnc; "\\??\\UNC\\"
0x180005c56  mov     [rsp+280h+var_20], r15
0x180005c5e  mov     [rsp+280h+var_210], rax
0x180005c63  lea     rcx, asc_1800291C4; "\\\\"
0x180005c6a  lea     rax, aHarddisk; "\\??\\HardDisk"
0x180005c71  mov     [rbp+180h+var_1F8], rcx
0x180005c75  mov     [rbp+180h+var_1E0], rax
0x180005c79  lea     r15, LocaleName
0x180005c80  lea     rax, aHarddisk_0; "\\\\?\\HardDisk"
0x180005c87  mov     [rbp+180h+var_138], rcx
0x180005c8b  mov     [rbp+180h+var_1C8], rax
0x180005c8f  lea     rcx, [rdx-2]
0x180005c93  lea     rax, aVolume; "\\??\\Volume"
0x180005c9a  mov     [rsp+280h+var_220], 10h
0x180005ca3  mov     [rbp+180h+var_1B0], rax
0x180005ca7  lea     r8, [rdx+2]
0x180005cab  lea     rax, aVolume_0; "\\\\?\\Volume"
0x180005cb2  mov     [rsp+280h+var_218], 12h
0x180005cbb  mov     [rbp+180h+var_198], rax
0x180005cbf  mov     rbx, r14
0x180005cc2  lea     rax, String2; "\\??\\"
0x180005cc9  mov     qword ptr [rsp+280h+var_208], 4
0x180005cd2  mov     [rbp+180h+var_180], rax
0x180005cd6  lea     rax, aDosdevicesUnc; "\\DosDevices\\UNC\\"
0x180005cdd  mov     [rbp+180h+var_150], rax
0x180005ce1  lea     rax, aDosdevices; "\\DosDevices\\"
0x180005ce8  mov     [rbp+180h+var_120], rax
0x180005cec  lea     rax, aSystemroot; "\\SystemRoot"
0x180005cf3  mov     [rbp+180h+var_F0], rax
0x180005cfa  mov     rax, rdx
0x180005cfd  shr     rax, 1
0x180005d00  mov     qword ptr [rbp+180h+var_208+8], 6
0x180005d08  mov     [rbp+180h+var_1F0], 18h
0x180005d10  mov     [rbp+180h+var_1E8], 1Ah
0x180005d18  cmp     word ptr [rax+rax+7FFE002Eh], 5Ch ; '\'
0x180005d21  lea     rax, aDeviceHarddisk; "\\Device\\HarddiskVolume"
0x180005d28  mov     [rbp+180h+var_C0], rax
0x180005d2f  lea     rax, aHarddiskvolume; "\\\\?\\HarddiskVolume"
0x180005d36  mov     [rbp+180h+var_A8], rax
0x180005d3d  cmovnz  rcx, rdx
0x180005d41  lea     rax, aDeviceMup; "\\Device\\Mup"
0x180005d48  mov     [rbp+180h+var_1D8], 18h
0x180005d50  mov     [rbp+180h+var_90], rax
0x180005d57  lea     rax, aUnc_0; "\\\\?\\UNC"
0x180005d5e  mov     [rbp+180h+var_78], rax
0x180005d65  mov     [rbp+180h+var_1D0], 1Ah
0x180005d6d  mov     [rbp+180h+var_1C0], 14h
0x180005d75  mov     [rbp+180h+var_1B8], 16h
0x180005d7d  mov     [rbp+180h+var_1A8], 14h
0x180005d85  mov     [rbp+180h+var_1A0], 16h
0x180005d8d  mov     [rbp+180h+var_190], 8
0x180005d95  mov     [rbp+180h+var_188], 0Ah
0x180005d9d  mov     [rbp+180h+var_178], r14
0x180005da1  mov     [rbp+180h+var_170], 2
0x180005da9  mov     [rbp+180h+var_168], r15
0x180005dad  mov     [rbp+180h+var_160], 20h ; ' '
0x180005db5  mov     [rbp+180h+var_158], 22h ; '"'
0x180005dbd  mov     [rbp+180h+var_148], 4
0x180005dc5  mov     [rbp+180h+var_140], 6
0x180005dcd  mov     [rbp+180h+var_130], 18h
0x180005dd5  mov     [rbp+180h+var_128], 1Ah
0x180005ddd  mov     [rbp+180h+var_118], r14
0x180005de1  mov     [rbp+180h+var_110], 2
0x180005de9  mov     [rbp+180h+var_108], r15
0x180005ded  mov     [rbp+180h+var_100], 16h
0x180005df8  mov     [rbp+180h+var_F8], 18h
0x180005e03  mov     [rbp+180h+var_E8], rcx
0x180005e0a  mov     [rbp+180h+var_E0], r8
0x180005e11  mov     [rbp+180h+var_D8], r9
0x180005e18  mov     [rbp+180h+var_D0], 2Ch ; ','
0x180005e23  mov     [rbp+180h+var_C8], 2Eh ; '.'
0x180005e2e  mov     [rbp+180h+var_B8], 24h ; '$'
0x180005e39  mov     [rbp+180h+var_B0], 26h ; '&'
0x180005e44  mov     [rbp+180h+var_A0], 16h
0x180005e4f  mov     [rbp+180h+var_98], 18h
0x180005e5a  mov     [rbp+180h+var_88], 0Eh
0x180005e65  mov     [rbp+180h+var_80], 10h
0x180005e70  lea     rax, [rbx+rbx*2]
0x180005e74  shl     rax, 4
0x180005e78  lea     r8, [rsp+280h+var_220]
0x180005e7d  add     r8, rax
0x180005e80  mov     rax, [r8]
0x180005e83  cmp     rax, [rdi]
0x180005e86  ja      short loc_180005EC3
0x180005e88  mov     [rsp+280h+var_250], rax
0x180005e8d  lea     rcx, [rsp+280h+var_250]
0x180005e92  mov     [rsp+280h+var_248], rax
0x180005e97  mov     rax, [rdi+10h]
0x180005e9b  mov     [rsp+280h+var_240], rax
0x180005ea0  lea     rax, [rsp+280h+var_230]
0x180005ea5  mov     [rsp+280h+var_258], rax
0x180005eaa  mov     [rsp+280h+var_230], r14d
0x180005eaf  call    RtlCompareEncodedLBlobs
0x180005eb4  test    eax, eax
0x180005eb6  js      loc_180005F95
0x180005ebc  cmp     [rsp+280h+var_230], r14d
0x180005ec1  jz      short loc_180005F09
0x180005ec3  inc     rbx
0x180005ec6  cmp     rbx, 9
0x180005eca  jb      short loc_180005E70
0x180005ecc  jnz     short loc_180005F09
0x180005ece  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180005ed5  mov     [rsp+280h+var_240], 1FBh
0x180005ede  mov     [rsp+280h+var_250], rax
0x180005ee3  mov     r8d, 0C0000039h
0x180005ee9  lea     rax, aRtlconvertntfi; "RtlConvertNtFilePathToWin32FilePath"
0x180005ef0  mov     [rsp+280h+var_238], r14
0x180005ef5  mov     [rsp+280h+var_248], rax
0x180005efa  call    RtlReportErrorOrigination
0x180005eff  mov     eax, 0C0000039h
0x180005f04  jmp     loc_180005F95
0x180005f09  movdqu  xmm2, xmmword ptr [rdi]
0x180005f0d  lea     rax, [rbx+rbx*2]
0x180005f11  mov     [rbp+180h+var_40], 2
0x180005f1c  add     rax, rax
0x180005f1f  mov     [rbp+180h+var_38], 2
0x180005f2a  mov     r9, rsi
0x180005f2d  mov     [rbp+180h+var_30], r15
0x180005f34  lea     r8, [rbp+180h+var_70]
0x180005f3b  mov     rcx, [rsp+rax*8+280h+var_220]
0x180005f40  movups  xmm0, [rsp+rax*8+280h+var_208]
0x180005f45  movsd   xmm1, [rbp+rax*8+180h+var_1F8]
0x180005f4b  movaps  [rbp+180h+var_70], xmm0
0x180005f52  movq    xmm0, rcx
0x180005f57  add     rcx, [rdi+10h]
0x180005f5b  punpcklqdq xmm0, xmm0
0x180005f5f  psubq   xmm2, xmm0
0x180005f63  movsd   [rbp+180h+var_60], xmm1
0x180005f6b  movdqu  [rbp+180h+var_58], xmm2
0x180005f73  mov     [rbp+180h+var_48], rcx
0x180005f7a  call    RtlConcatenateLUnicodeStrings
0x180005f7f  test    eax, eax
0x180005f81  js      short loc_180005F95
0x180005f83  mov     rax, [rsi]
0x180005f86  cmp     rax, 2
0x180005f8a  jbe     short loc_180005F93
0x180005f8c  add     rax, 0FFFFFFFFFFFFFFFEh
0x180005f90  mov     [rsi], rax
0x180005f93  xor     eax, eax
0x180005f95  mov     rbx, [rsp+280h+arg_10]
0x180005f9d  mov     r15, [rsp+280h+var_20]
0x180005fa5  add     rsp, 268h
0x180005fac  pop     r14
0x180005fae  pop     rdi
0x180005faf  pop     rsi
0x180005fb0  pop     rbp
0x180005fb1  retn
```

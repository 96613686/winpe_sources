# FvepCheckMetadataLogicalCopies

- ea: `0x1400b1110`
- end: `0x1400b1671`
- name: `FvepCheckMetadataLogicalCopies`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400a7e30`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000bc68`
- `0x14000cc08`
- `0x14000cd30`
- `0x1400b1110`
- `0x1400b1c60`
- `0x1400b4c90`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b12f0`
- `ntoskrnl!RtlCompareMemory` at `0x1400b12f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b1277`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b161c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b1277`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b161c`

## pseudocode

```c
__int64 __fastcall FvepCheckMetadataLogicalCopies(__int64 *a1, const void *a2, _DWORD *a3, __int64 a4)
{
  __int64 *v4; // r15
  unsigned __int64 v5; // rcx
  void *v6; // rbx
  unsigned __int64 v7; // rdx
  int v8; // ebp
  __int64 v9; // r11
  unsigned int v10; // edi
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r10
  bool v14; // zf
  char v16; // r12
  char v17; // r13
  __int64 v18; // rsi
  int InformationAndValidationFromLogicalCopy; // r15d
  SIZE_T v20; // rbx
  __int64 v21; // r8
  int v22; // r8d
  unsigned int v24; // [rsp+20h] [rbp-B8h]
  int v25; // [rsp+28h] [rbp-B0h]
  unsigned int v26; // [rsp+60h] [rbp-78h]
  __int64 v27; // [rsp+68h] [rbp-70h]
  void *Source1; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int64 v29; // [rsp+78h] [rbp-60h]
  __int64 v30[11]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v34; // [rsp+F8h] [rbp+20h]

  v34 = a4;
  v4 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 438, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
    a4 = v34;
  }
  v5 = *((unsigned int *)v4 + 327);
  v6 = 0;
  v7 = v4[131];
  v8 = 0;
  v9 = 0;
  Source1 = 0;
  v27 = 0;
  v30[0] = 0;
  v26 = v5;
  v29 = v7;
  do
  {
    v10 = *(_DWORD *)(a4 + 24 * v9 + 8);
    v11 = *(_QWORD *)(a4 + 24 * v9);
    if ( v10 )
    {
      if ( (((_DWORD)v5 - 1) & (unsigned int)v5) != 0 || !(_DWORD)v5 )
      {
        if ( v10 % (unsigned int)v5 )
          v10 = v5 + v10 - v10 % (unsigned int)v5;
        v7 = v29;
      }
      else
      {
        v10 = ~(v5 - 1) & (v5 + v10 - 1);
      }
    }
    else
    {
      v10 = 0x10000;
    }
    v12 = v10 + v11;
    if ( v12 < v11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = -1073741675;
        v24 = v10;
        WPP_SF_iiL(WPP_GLOBAL_Control->AttachedDevice, 439, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v11);
        v9 = v27;
      }
      if ( v8 >= 0 )
        v8 = -1071579105;
    }
    else
    {
      if ( v11 && v12 <= v7 )
      {
        v13 = v5 - 1;
        if ( (v5 & (v5 - 1)) != 0 || !v5 )
          v14 = v11 % v5 == 0;
        else
          v14 = (v13 & v11) == 0;
        if ( v14 && ((v5 & (v5 - 1)) != 0 || !v5 ? v12 % v5 == 0 : (v13 & v12) == 0) )
        {
          v16 = 0;
          v17 = 0;
          v18 = 0;
          if ( !*((_DWORD *)v4 + 346) )
            goto LABEL_72;
          while ( 1 )
          {
            if ( v6 )
            {
              ExFreePoolWithTag(v6, 0x30455646u);
              Source1 = 0;
              v30[0] = 0;
            }
            InformationAndValidationFromLogicalCopy = FvepReadInformationAndValidationFromLogicalCopy(
                                                        (_DWORD)v4,
                                                        v11,
                                                        v10,
                                                        v18,
                                                        v24,
                                                        v25,
                                                        (__int64)&Source1,
                                                        (__int64)v30);
            if ( InformationAndValidationFromLogicalCopy < 0 )
            {
              if ( InformationAndValidationFromLogicalCopy == -1071579134 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_iDDd(WPP_GLOBAL_Control->AttachedDevice, 443, 3223388162LL, v11, v10, v18, -1071579134);
                }
                v16 = 1;
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 2;
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_iDDd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    444,
                    3223388162LL,
                    v11,
                    v10,
                    v18,
                    InformationAndValidationFromLogicalCopy);
                }
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 0;
              }
              if ( v8 >= 0 )
                v8 = InformationAndValidationFromLogicalCopy;
            }
            else
            {
              v20 = *(unsigned int *)(v34 + 24 * v27 + 8);
              if ( RtlCompareMemory(Source1, a2, v20) == v20 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v25 = v18;
                  v24 = v10;
                  WPP_SF_iDD(WPP_GLOBAL_Control->AttachedDevice, 441, v21, v11);
                }
                v9 = v27;
                v17 = 1;
                v4 = a1;
                *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 1;
                v18 = (unsigned int)(v18 + 1);
                goto LABEL_56;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_iDD(WPP_GLOBAL_Control->AttachedDevice, 442, v21, v11);
              }
              v16 = 1;
              *(_DWORD *)(*(_QWORD *)(v34 + 24 * v27 + 16) + 4 * v18) = 2;
            }
            v18 = (unsigned int)(v18 + 1);
            v22 = InformationAndValidationFromLogicalCopy;
            v4 = a1;
            v25 = v18;
            FveLogEventWithMetadataInfo(
              *a1,
              (const EVENT_DESCRIPTOR *)FVE_METADATA_LOGICAL_COPY_MATCH_FAIL,
              v22,
              v11,
              v10);
            v9 = v27;
LABEL_56:
            v6 = Source1;
            if ( (unsigned int)v18 >= *((_DWORD *)v4 + 346) )
            {
              if ( v17 && v16 )
                *a3 |= 0x10000u;
              goto LABEL_72;
            }
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = 0;
        v24 = v10 + v11;
        WPP_SF_iiL(WPP_GLOBAL_Control->AttachedDevice, 440, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v11);
        v9 = v27;
      }
      if ( v8 >= 0 )
        v8 = -1071579105;
    }
LABEL_72:
    v5 = v26;
    ++v9;
    a4 = v34;
    v7 = v29;
    v27 = v9;
  }
  while ( v9 != 3 );
  if ( v6 )
    ExFreePoolWithTag(v6, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 445, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b1110  mov     rax, rsp
0x1400b1113  mov     [rax+20h], r9
0x1400b1117  mov     [rax+18h], r8
0x1400b111b  mov     [rax+10h], rdx
0x1400b111f  mov     [rax+8], rcx
0x1400b1123  push    rbx
0x1400b1124  push    rbp
0x1400b1125  push    rsi
0x1400b1126  push    rdi
0x1400b1127  push    r12
0x1400b1129  push    r13
0x1400b112b  push    r14
0x1400b112d  push    r15
0x1400b112f  sub     rsp, 98h
0x1400b1136  mov     r15, rcx
0x1400b1139  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1140  lea     rsi, WPP_GLOBAL_Control
0x1400b1147  cmp     rcx, rsi
0x1400b114a  jz      short loc_1400B1176
0x1400b114c  mov     eax, [rcx+2Ch]
0x1400b114f  test    al, 4
0x1400b1151  jz      short loc_1400B1176
0x1400b1153  cmp     byte ptr [rcx+29h], 5
0x1400b1157  jb      short loc_1400B1176
0x1400b1159  mov     rcx, [rcx+18h]
0x1400b115d  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b1164  mov     edx, 1B6h
0x1400b1169  call    WPP_SF_
0x1400b116e  mov     r9, [rsp+0D8h+arg_18]
0x1400b1176  mov     ecx, [r15+51Ch]
0x1400b117d  xor     ebx, ebx
0x1400b117f  mov     rdx, [r15+418h]
0x1400b1186  xor     ebp, ebp
0x1400b1188  xor     r11d, r11d
0x1400b118b  mov     [rsp+0D8h+Source1], rbx
0x1400b1190  mov     [rsp+0D8h+var_70], r11
0x1400b1195  mov     r12d, 0C021001Fh
0x1400b119b  mov     [rsp+0D8h+var_58], rbx
0x1400b11a3  mov     [rsp+0D8h+var_78], ecx
0x1400b11a7  mov     [rsp+0D8h+var_60], rdx
0x1400b11ac  lea     rax, [r11+r11*2]
0x1400b11b0  mov     edi, [r9+rax*8+8]
0x1400b11b5  mov     r14, [r9+rax*8]
0x1400b11b9  test    edi, edi
0x1400b11bb  jnz     short loc_1400B11C4
0x1400b11bd  mov     edi, 10000h
0x1400b11c2  jmp     short loc_1400B11EC
0x1400b11c4  lea     eax, [rcx-1]
0x1400b11c7  test    ecx, eax
0x1400b11c9  jnz     short loc_1400B11D9
0x1400b11cb  test    ecx, ecx
0x1400b11cd  jz      short loc_1400B11D9
0x1400b11cf  dec     edi
0x1400b11d1  not     eax
0x1400b11d3  add     edi, ecx
0x1400b11d5  and     edi, eax
0x1400b11d7  jmp     short loc_1400B11EC
0x1400b11d9  xor     edx, edx
0x1400b11db  mov     eax, edi
0x1400b11dd  div     ecx
0x1400b11df  test    edx, edx
0x1400b11e1  jz      short loc_1400B11E7
0x1400b11e3  sub     edi, edx
0x1400b11e5  add     edi, ecx
0x1400b11e7  mov     rdx, [rsp+0D8h+var_60]
0x1400b11ec  mov     r9d, edi
0x1400b11ef  lea     r8, [r9+r14]
0x1400b11f3  cmp     r8, r14
0x1400b11f6  jb      loc_1400B1594
0x1400b11fc  test    r14, r14
0x1400b11ff  jz      loc_1400B1548
0x1400b1205  cmp     r8, rdx
0x1400b1208  ja      loc_1400B1548
0x1400b120e  lea     r10, [rcx-1]
0x1400b1212  mov     r9, r10
0x1400b1215  and     r9, rcx
0x1400b1218  jnz     short loc_1400B1224
0x1400b121a  test    rcx, rcx
0x1400b121d  jz      short loc_1400B1224
0x1400b121f  test    r14, r10
0x1400b1222  jmp     short loc_1400B122F
0x1400b1224  xor     edx, edx
0x1400b1226  mov     rax, r14
0x1400b1229  div     rcx
0x1400b122c  test    rdx, rdx
0x1400b122f  jnz     loc_1400B1548
0x1400b1235  test    r9, r9
0x1400b1238  jnz     short loc_1400B1244
0x1400b123a  test    rcx, rcx
0x1400b123d  jz      short loc_1400B1244
0x1400b123f  test    r8, r10
0x1400b1242  jmp     short loc_1400B124F
0x1400b1244  xor     edx, edx
0x1400b1246  mov     rax, r8
0x1400b1249  div     rcx
0x1400b124c  test    rdx, rdx
0x1400b124f  jnz     loc_1400B1548
0x1400b1255  xor     r12b, r12b
0x1400b1258  xor     r13b, r13b
0x1400b125b  xor     esi, esi
0x1400b125d  cmp     [r15+568h], esi
0x1400b1264  jbe     loc_1400B15DF
0x1400b126a  test    rbx, rbx
0x1400b126d  jz      short loc_1400B1298
0x1400b126f  mov     edx, 30455646h; Tag
0x1400b1274  mov     rcx, rbx; P
0x1400b1277  call    cs:__imp_ExFreePoolWithTag
0x1400b127e  nop     dword ptr [rax+rax+00h]
0x1400b1283  mov     [rsp+0D8h+Source1], 0
0x1400b128c  mov     [rsp+0D8h+var_58], 0
0x1400b1298  lea     rax, [rsp+0D8h+var_58]
0x1400b12a0  mov     r9d, esi
0x1400b12a3  mov     [rsp+0D8h+var_A0], rax
0x1400b12a8  mov     r8d, edi
0x1400b12ab  lea     rax, [rsp+0D8h+Source1]
0x1400b12b0  mov     rdx, r14
0x1400b12b3  mov     rcx, r15
0x1400b12b6  mov     [rsp+0D8h+var_A8], rax
0x1400b12bb  call    FvepReadInformationAndValidationFromLogicalCopy
0x1400b12c0  mov     r15d, eax
0x1400b12c3  test    eax, eax
0x1400b12c5  js      loc_1400B13CC
0x1400b12cb  mov     rdx, [rsp+0D8h+var_70]
0x1400b12d0  mov     rcx, [rsp+0D8h+arg_18]
0x1400b12d8  lea     rax, [rdx+rdx*2]
0x1400b12dc  mov     rdx, [rsp+0D8h+Source2]; Source2
0x1400b12e4  mov     ebx, [rcx+rax*8+8]
0x1400b12e8  mov     rcx, [rsp+0D8h+Source1]; Source1
0x1400b12ed  mov     r8d, ebx; Length
0x1400b12f0  call    cs:__imp_RtlCompareMemory
0x1400b12f7  nop     dword ptr [rax+rax+00h]
0x1400b12fc  cmp     rax, rbx
0x1400b12ff  jnz     short loc_1400B1369
0x1400b1301  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1308  lea     rax, WPP_GLOBAL_Control
0x1400b130f  cmp     rcx, rax
0x1400b1312  jz      short loc_1400B133A
0x1400b1314  mov     eax, [rcx+2Ch]
0x1400b1317  test    al, 4
0x1400b1319  jz      short loc_1400B133A
0x1400b131b  cmp     byte ptr [rcx+29h], 4
0x1400b131f  jb      short loc_1400B133A
0x1400b1321  mov     rcx, [rcx+18h]
0x1400b1325  mov     edx, 1B9h
0x1400b132a  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b132e  mov     r9, r14
0x1400b1331  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b1335  call    WPP_SF_iDD
0x1400b133a  mov     r11, [rsp+0D8h+var_70]
0x1400b133f  mov     r13b, 1
0x1400b1342  mov     rdx, [rsp+0D8h+arg_18]
0x1400b134a  mov     r15, [rsp+0D8h+arg_0]
0x1400b1352  lea     rax, [r11+r11*2]
0x1400b1356  mov     rax, [rdx+rax*8+10h]
0x1400b135b  mov     dword ptr [rax+rsi*4], 1
0x1400b1362  inc     esi
0x1400b1364  jmp     loc_1400B1505
0x1400b1369  mov     ebx, 4CA7h
0x1400b136e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1375  lea     rax, WPP_GLOBAL_Control
0x1400b137c  cmp     rcx, rax
0x1400b137f  jz      short loc_1400B13A7
0x1400b1381  mov     eax, [rcx+2Ch]
0x1400b1384  test    al, 4
0x1400b1386  jz      short loc_1400B13A7
0x1400b1388  cmp     byte ptr [rcx+29h], 2
0x1400b138c  jb      short loc_1400B13A7
0x1400b138e  mov     rcx, [rcx+18h]
0x1400b1392  mov     edx, 1BAh
0x1400b1397  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b139b  mov     r9, r14
0x1400b139e  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b13a2  call    WPP_SF_iDD
0x1400b13a7  mov     r8, [rsp+0D8h+var_70]
0x1400b13ac  mov     r12b, 1
0x1400b13af  mov     rdx, [rsp+0D8h+arg_18]
0x1400b13b7  lea     rax, [r8+r8*2]
0x1400b13bb  mov     rax, [rdx+rax*8+10h]
0x1400b13c0  mov     dword ptr [rax+rsi*4], 2
0x1400b13c7  jmp     loc_1400B14A2
0x1400b13cc  mov     r8d, 0C0210002h
0x1400b13d2  cmp     r15d, r8d
0x1400b13d5  jnz     short loc_1400B143C
0x1400b13d7  mov     ebx, 4CB9h
0x1400b13dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b13e3  lea     rax, WPP_GLOBAL_Control
0x1400b13ea  cmp     rcx, rax
0x1400b13ed  jz      short loc_1400B141A
0x1400b13ef  mov     eax, [rcx+2Ch]
0x1400b13f2  test    al, 4
0x1400b13f4  jz      short loc_1400B141A
0x1400b13f6  cmp     byte ptr [rcx+29h], 2
0x1400b13fa  jb      short loc_1400B141A
0x1400b13fc  mov     rcx, [rcx+18h]
0x1400b1400  mov     edx, 1BBh
0x1400b1405  mov     dword ptr [rsp+0D8h+var_A8], r8d
0x1400b140a  mov     r9, r14
0x1400b140d  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b1411  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b1415  call    WPP_SF_iDDd
0x1400b141a  mov     r8, [rsp+0D8h+var_70]
0x1400b141f  mov     r12b, 1
0x1400b1422  mov     rdx, [rsp+0D8h+arg_18]
0x1400b142a  lea     rax, [r8+r8*2]
0x1400b142e  mov     rax, [rdx+rax*8+10h]
0x1400b1433  mov     dword ptr [rax+rsi*4], 2
0x1400b143a  jmp     short loc_1400B149C
0x1400b143c  mov     ebx, 4CC8h
0x1400b1441  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1448  lea     rax, WPP_GLOBAL_Control
0x1400b144f  cmp     rcx, rax
0x1400b1452  jz      short loc_1400B147F
0x1400b1454  mov     eax, [rcx+2Ch]
0x1400b1457  test    al, 4
0x1400b1459  jz      short loc_1400B147F
0x1400b145b  cmp     byte ptr [rcx+29h], 2
0x1400b145f  jb      short loc_1400B147F
0x1400b1461  mov     rcx, [rcx+18h]
0x1400b1465  mov     edx, 1BCh
0x1400b146a  mov     dword ptr [rsp+0D8h+var_A8], r15d
0x1400b146f  mov     r9, r14
0x1400b1472  mov     dword ptr [rsp+0D8h+var_B0], esi
0x1400b1476  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1400b147a  call    WPP_SF_iDDd
0x1400b147f  mov     r8, [rsp+0D8h+var_70]
0x1400b1484  mov     rdx, [rsp+0D8h+arg_18]
0x1400b148c  lea     rax, [r8+r8*2]
0x1400b1490  mov     rax, [rdx+rax*8+10h]
0x1400b1495  mov     dword ptr [rax+rsi*4], 0
0x1400b149c  test    ebp, ebp
0x1400b149e  cmovns  ebp, r15d
0x1400b14a2  mov     r8, [rsp+0D8h+arg_0]
0x1400b14aa  inc     esi
0x1400b14ac  mov     [rsp+0D8h+var_88], 0
0x1400b14b1  mov     r9, r14
0x1400b14b4  mov     [rsp+0D8h+var_90], 0
0x1400b14b9  mov     eax, ebx
0x1400b14bb  mov     ecx, [r8+568h]
0x1400b14c2  mov     [rsp+0D8h+var_98], rax
0x1400b14c7  mov     rax, [r8+558h]
0x1400b14ce  mov     r8d, r15d
0x1400b14d1  mov     r15, [rsp+0D8h+arg_0]
0x1400b14d9  mov     [rsp+0D8h+var_A0], rax
0x1400b14de  mov     [rsp+0D8h+var_A8], rcx
0x1400b14e3  mov     edx, esi
0x1400b14e5  mov     rcx, [r15]
0x1400b14e8  mov     [rsp+0D8h+var_B0], rdx
0x1400b14ed  lea     rdx, FVE_METADATA_LOGICAL_COPY_MATCH_FAIL
0x1400b14f4  mov     eax, edi
0x1400b14f6  mov     [rsp+0D8h+var_B8], rax
0x1400b14fb  call    FveLogEventWithMetadataInfo
0x1400b1500  mov     r11, [rsp+0D8h+var_70]
0x1400b1505  mov     rbx, [rsp+0D8h+Source1]
0x1400b150a  cmp     esi, [r15+568h]
0x1400b1511  jb      loc_1400B126A
0x1400b1517  test    r13b, r13b
0x1400b151a  jz      loc_1400B15DF
0x1400b1520  test    r12b, r12b
0x1400b1523  lea     rsi, WPP_GLOBAL_Control
0x1400b152a  mov     r12d, 0C021001Fh
0x1400b1530  jz      loc_1400B15EC
0x1400b1536  mov     r8, [rsp+0D8h+arg_10]
0x1400b153e  bts     dword ptr [r8], 10h
0x1400b1543  jmp     loc_1400B15EC
0x1400b1548  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b154f  cmp     rcx, rsi
0x1400b1552  jz      short loc_1400B158B
0x1400b1554  mov     eax, [rcx+2Ch]
0x1400b1557  test    al, 4
0x1400b1559  jz      short loc_1400B158B
0x1400b155b  cmp     byte ptr [rcx+29h], 2
0x1400b155f  jb      short loc_1400B158B
0x1400b1561  mov     rcx, [rcx+18h]
0x1400b1565  mov     edx, 1B8h
0x1400b156a  mov     dword ptr [rsp+0D8h+var_B0], 0
0x1400b1572  mov     r9, r14
0x1400b1575  mov     [rsp+0D8h+var_B8], r8
0x1400b157a  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b1581  call    WPP_SF_iiL
0x1400b1586  mov     r11, [rsp+0D8h+var_70]
0x1400b158b  test    ebp, ebp
0x1400b158d  js      short loc_1400B15EC
0x1400b158f  mov     ebp, r12d
0x1400b1592  jmp     short loc_1400B15EC
0x1400b1594  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b159b  cmp     rcx, rsi
0x1400b159e  jz      short loc_1400B15D7
0x1400b15a0  mov     eax, [rcx+2Ch]
0x1400b15a3  test    al, 4
0x1400b15a5  jz      short loc_1400B15D7
0x1400b15a7  cmp     byte ptr [rcx+29h], 2
0x1400b15ab  jb      short loc_1400B15D7
0x1400b15ad  mov     rcx, [rcx+18h]
0x1400b15b1  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b15b8  mov     dword ptr [rsp+0D8h+var_B0], 0C0000095h
0x1400b15c0  mov     edx, 1B7h
0x1400b15c5  mov     [rsp+0D8h+var_B8], r9
0x1400b15ca  mov     r9, r14
0x1400b15cd  call    WPP_SF_iiL
0x1400b15d2  mov     r11, [rsp+0D8h+var_70]
  ... truncated ...
```

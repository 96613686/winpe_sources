# biCompressionFromSubtype

- ea: `0x18000e5b8`
- end: `0x18000e810`
- name: `biCompressionFromSubtype`
- size: `600`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800040b0`
- `0x180006e88`
- `0x18000d350`
- `0x18000e160`

## callees

- `0x18000e5b8`

## pseudocode

```c
__int64 __fastcall biCompressionFromSubtype(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax

  v1 = *a1 - *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1 )
    v1 = a1[1] - *(_QWORD *)MEDIASUBTYPE_IYUV.Data4;
  if ( !v1 )
    return *(unsigned int *)a1;
  v2 = *a1 - MEDIASUBTYPE_I420;
  if ( *a1 == (_QWORD)MEDIASUBTYPE_I420 )
    v2 = a1[1] - *((_QWORD *)&MEDIASUBTYPE_I420 + 1);
  if ( !v2 )
    return *(unsigned int *)a1;
  v3 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YV12.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YV12.Data1 )
    v3 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YV12.Data4;
  if ( !v3 )
    return *(unsigned int *)a1;
  v4 = *a1 - *(_QWORD *)&MEDIASUBTYPE_NV12.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_NV12.Data1 )
    v4 = a1[1] - *(_QWORD *)MEDIASUBTYPE_NV12.Data4;
  if ( !v4 )
    return *(unsigned int *)a1;
  v5 = *a1 - *(_QWORD *)&MEDIASUBTYPE_NV11.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_NV11.Data1 )
    v5 = a1[1] - *(_QWORD *)MEDIASUBTYPE_NV11.Data4;
  if ( !v5 )
    return *(unsigned int *)a1;
  v6 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 )
    v6 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YUY2.Data4;
  if ( !v6 )
    return *(unsigned int *)a1;
  v7 = *a1 - *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1 )
    v7 = a1[1] - *(_QWORD *)MEDIASUBTYPE_UYVY.Data4;
  if ( !v7 )
    return *(unsigned int *)a1;
  v8 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1 )
    v8 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YVYU.Data4;
  if ( !v8 )
    return *(unsigned int *)a1;
  v9 = *a1 - MEDIASUBTYPE_V216;
  if ( *a1 == (_QWORD)MEDIASUBTYPE_V216 )
    v9 = a1[1] - *((_QWORD *)&MEDIASUBTYPE_V216 + 1);
  if ( !v9 )
    return *(unsigned int *)a1;
  v10 = *a1 - MEDIASUBTYPE_V410;
  if ( *a1 == (_QWORD)MEDIASUBTYPE_V410 )
    v10 = a1[1] - *((_QWORD *)&MEDIASUBTYPE_V410 + 1);
  if ( !v10 )
    return *(unsigned int *)a1;
  v11 = *a1 - *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1 )
    v11 = a1[1] - *(_QWORD *)MEDIASUBTYPE_AYUV.Data4;
  if ( !v11 )
    return *(unsigned int *)a1;
  v12 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1 )
    v12 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YVU9.Data4;
  if ( !v12 )
    return *(unsigned int *)a1;
  v13 = *a1 - MEDIASUBTYPE_v210;
  if ( *a1 == MEDIASUBTYPE_v210 )
    v13 = a1[1] - 0x719B3800AA000080LL;
  if ( !v13 )
    return *(unsigned int *)a1;
  v14 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1 )
    v14 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB32.Data4;
  if ( !v14 )
    return 0;
  v15 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1 )
    v15 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB24.Data4;
  if ( !v15 )
    return 0;
  v16 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 )
    v16 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB565.Data4;
  if ( !v16 )
    return 3;
  v18 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1 )
    v18 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB555.Data4;
  if ( !v18 )
    return 0;
  v19 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 )
    v19 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB8.Data4;
  if ( !v19 )
    return 0;
  v20 = *a1 - *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1 )
    v20 = a1[1] - *(_QWORD *)MEDIASUBTYPE_ARGB32.Data4;
  if ( !v20 )
    return 0;
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x18000e5b8  mov     rax, [rcx]
0x18000e5bb  sub     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data1
0x18000e5c2  jnz     short loc_18000E5CF
0x18000e5c4  mov     rax, [rcx+8]
0x18000e5c8  sub     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data4
0x18000e5cf  test    rax, rax
0x18000e5d2  jz      loc_18000E80D
0x18000e5d8  mov     rax, [rcx]
0x18000e5db  sub     rax, qword ptr cs:MEDIASUBTYPE_I420
0x18000e5e2  jnz     short loc_18000E5EF
0x18000e5e4  mov     rax, [rcx+8]
0x18000e5e8  sub     rax, qword ptr cs:MEDIASUBTYPE_I420+8
0x18000e5ef  test    rax, rax
0x18000e5f2  jz      loc_18000E80D
0x18000e5f8  mov     rax, [rcx]
0x18000e5fb  sub     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data1
0x18000e602  jnz     short loc_18000E60F
0x18000e604  mov     rax, [rcx+8]
0x18000e608  sub     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data4
0x18000e60f  test    rax, rax
0x18000e612  jz      loc_18000E80D
0x18000e618  mov     rax, [rcx]
0x18000e61b  sub     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data1
0x18000e622  jnz     short loc_18000E62F
0x18000e624  mov     rax, [rcx+8]
0x18000e628  sub     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data4
0x18000e62f  test    rax, rax
0x18000e632  jz      loc_18000E80D
0x18000e638  mov     rax, [rcx]
0x18000e63b  sub     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data1
0x18000e642  jnz     short loc_18000E64F
0x18000e644  mov     rax, [rcx+8]
0x18000e648  sub     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data4
0x18000e64f  test    rax, rax
0x18000e652  jz      loc_18000E80D
0x18000e658  mov     rax, [rcx]
0x18000e65b  sub     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x18000e662  jnz     short loc_18000E66F
0x18000e664  mov     rax, [rcx+8]
0x18000e668  sub     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x18000e66f  test    rax, rax
0x18000e672  jz      loc_18000E80D
0x18000e678  mov     rax, [rcx]
0x18000e67b  sub     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x18000e682  jnz     short loc_18000E68F
0x18000e684  mov     rax, [rcx+8]
0x18000e688  sub     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x18000e68f  test    rax, rax
0x18000e692  jz      loc_18000E80D
0x18000e698  mov     rax, [rcx]
0x18000e69b  sub     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data1
0x18000e6a2  jnz     short loc_18000E6AF
0x18000e6a4  mov     rax, [rcx+8]
0x18000e6a8  sub     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data4
0x18000e6af  test    rax, rax
0x18000e6b2  jz      loc_18000E80D
0x18000e6b8  mov     rax, [rcx]
0x18000e6bb  sub     rax, qword ptr cs:MEDIASUBTYPE_V216
0x18000e6c2  jnz     short loc_18000E6CF
0x18000e6c4  mov     rax, [rcx+8]
0x18000e6c8  sub     rax, qword ptr cs:MEDIASUBTYPE_V216+8
0x18000e6cf  test    rax, rax
0x18000e6d2  jz      loc_18000E80D
0x18000e6d8  mov     rax, [rcx]
0x18000e6db  sub     rax, qword ptr cs:MEDIASUBTYPE_V410
0x18000e6e2  jnz     short loc_18000E6EF
0x18000e6e4  mov     rax, [rcx+8]
0x18000e6e8  sub     rax, qword ptr cs:MEDIASUBTYPE_V410+8
0x18000e6ef  test    rax, rax
0x18000e6f2  jz      loc_18000E80D
0x18000e6f8  mov     rax, [rcx]
0x18000e6fb  sub     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x18000e702  jnz     short loc_18000E70F
0x18000e704  mov     rax, [rcx+8]
0x18000e708  sub     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data4
0x18000e70f  test    rax, rax
0x18000e712  jz      loc_18000E80D
0x18000e718  mov     rax, [rcx]
0x18000e71b  sub     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data1
0x18000e722  jnz     short loc_18000E72F
0x18000e724  mov     rax, [rcx+8]
0x18000e728  sub     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data4
0x18000e72f  test    rax, rax
0x18000e732  jz      loc_18000E80D
0x18000e738  mov     rax, [rcx]
0x18000e73b  sub     rax, cs:MEDIASUBTYPE_v210
0x18000e742  jnz     short loc_18000E74F
0x18000e744  mov     rax, [rcx+8]
0x18000e748  sub     rax, cs:qword_18002F888
0x18000e74f  test    rax, rax
0x18000e752  jz      loc_18000E80D
0x18000e758  mov     rax, [rcx]
0x18000e75b  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data1
0x18000e762  jnz     short loc_18000E76F
0x18000e764  mov     rax, [rcx+8]
0x18000e768  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data4
0x18000e76f  test    rax, rax
0x18000e772  jz      loc_18000E80A
0x18000e778  mov     rax, [rcx]
0x18000e77b  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data1
0x18000e782  jnz     short loc_18000E78F
0x18000e784  mov     rax, [rcx+8]
0x18000e788  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data4
0x18000e78f  test    rax, rax
0x18000e792  jz      short loc_18000E80A
0x18000e794  mov     rax, [rcx]
0x18000e797  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x18000e79e  jnz     short loc_18000E7AB
0x18000e7a0  mov     rax, [rcx+8]
0x18000e7a4  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x18000e7ab  test    rax, rax
0x18000e7ae  jnz     short loc_18000E7B6
0x18000e7b0  mov     eax, 3
0x18000e7b5  retn
0x18000e7b6  mov     rax, [rcx]
0x18000e7b9  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data1
0x18000e7c0  jnz     short loc_18000E7CD
0x18000e7c2  mov     rax, [rcx+8]
0x18000e7c6  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data4
0x18000e7cd  test    rax, rax
0x18000e7d0  jz      short loc_18000E80A
0x18000e7d2  mov     rax, [rcx]
0x18000e7d5  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x18000e7dc  jnz     short loc_18000E7E9
0x18000e7de  mov     rax, [rcx+8]
0x18000e7e2  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x18000e7e9  test    rax, rax
0x18000e7ec  jz      short loc_18000E80A
0x18000e7ee  mov     rax, [rcx]
0x18000e7f1  sub     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x18000e7f8  jnz     short loc_18000E805
0x18000e7fa  mov     rax, [rcx+8]
0x18000e7fe  sub     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data4
0x18000e805  test    rax, rax
0x18000e808  jnz     short loc_18000E80D
0x18000e80a  xor     eax, eax
0x18000e80c  retn
0x18000e80d  mov     eax, [rcx]
0x18000e80f  retn
```

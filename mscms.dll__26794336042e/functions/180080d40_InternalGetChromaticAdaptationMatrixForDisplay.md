# InternalGetChromaticAdaptationMatrixForDisplay

- ea: `0x180080d40`
- end: `0x18008117e`
- name: `InternalGetChromaticAdaptationMatrixForDisplay`
- size: `1086`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180026990`
- `0x1800280a8`
- `0x1800281a0`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18007fbe4`
- `0x180080864`
- `0x180080a64`
- `0x180080d40`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180080e2b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180080e2b`

## pseudocode

```c
__int64 __fastcall InternalGetChromaticAdaptationMatrixForDisplay(unsigned __int64 a1, UINT32 a2, __int64 a3)
{
  unsigned __int64 v4; // rsi
  DWORD v6; // ebx
  const char *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int DeviceInfo; // eax
  float v13; // xmm4_4
  float v14; // xmm1_4
  float v15; // xmm0_4
  float v16; // xmm0_4
  float v17; // xmm4_4
  float v18; // xmm9_4
  float v19; // xmm10_4
  float v20; // xmm11_4
  float v21; // xmm7_4
  float v22; // xmm8_4
  float v23; // xmm6_4
  __int64 result; // rax
  int v25; // xmm4_4
  int v26; // xmm0_4
  int v27; // xmm0_4
  const char *v28; // [rsp+30h] [rbp-D8h]
  float v29; // [rsp+38h] [rbp-D0h] BYREF
  float v30; // [rsp+3Ch] [rbp-CCh] BYREF
  float v31; // [rsp+40h] [rbp-C8h] BYREF
  float v32; // [rsp+44h] [rbp-C4h] BYREF
  float v33; // [rsp+48h] [rbp-C0h] BYREF
  float v34; // [rsp+4Ch] [rbp-BCh] BYREF
  float v35[3]; // [rsp+50h] [rbp-B8h] BYREF
  float v36; // [rsp+5Ch] [rbp-ACh]
  int v37; // [rsp+60h] [rbp-A8h]
  int v38; // [rsp+64h] [rbp-A4h]
  float v39; // [rsp+68h] [rbp-A0h]
  float v40; // [rsp+6Ch] [rbp-9Ch]
  float v41; // [rsp+70h] [rbp-98h]
  float v42[4]; // [rsp+78h] [rbp-90h] BYREF
  float v43; // [rsp+88h] [rbp-80h] BYREF
  float v44; // [rsp+8Ch] [rbp-7Ch]
  float v45; // [rsp+90h] [rbp-78h]
  float v46[12]; // [rsp+98h] [rbp-70h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v48[1964]; // [rsp+DCh] [rbp-2Ch] BYREF
  unsigned int v49; // [rsp+888h] [rbp+780h] BYREF
  unsigned int v50; // [rsp+890h] [rbp+788h] BYREF
  unsigned int v51; // [rsp+898h] [rbp+790h] BYREF
  unsigned int v52[14]; // [rsp+8A0h] [rbp+798h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+970h] [rbp+868h]

  v4 = HIDWORD(a1);
  v6 = a1;
  if ( !a1 )
  {
    v7 = "Invalid adapter LUID in InternalGetChromaticAdaptationMatrixForDisplay\n";
    v8 = 2147942487LL;
    v9 = 249;
LABEL_21:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
      (const char *)v8,
      (int)v7,
      v28);
    return 0;
  }
  if ( a2 >= 0x10 )
  {
    v7 = "Invalid source Id in InternalGetChromaticAdaptationMatrixForDisplay\n";
    v8 = 2147942487LL;
    v9 = 255;
    goto LABEL_21;
  }
  if ( a3 )
  {
    v10 = 0;
    v11 = 0;
    do
    {
      ++v10;
      *(_QWORD *)(a3 + v11 + 4) = 0;
      *(_DWORD *)(a3 + v11) = 0;
      v11 += 12;
    }
    while ( v10 != 3 );
    memset_0(v48, 0, 0x7F4u);
    requestPacket.type = -2;
    requestPacket.size = 2056;
    requestPacket.adapterId.LowPart = v6;
    requestPacket.adapterId.HighPart = v4;
    requestPacket.id = a2;
    DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
    if ( DeviceInfo )
    {
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
        (const char *)DeviceInfo,
        (unsigned int)"Failed to get display info in InternalGetChromaticAdaptationMatrixForDisplay\n",
        v28);
    }
    else if ( v52[8] )
    {
      v29 = 0.0;
      v30 = 0.0;
      if ( ConvertUintToXY(&v29, &v30, v52) )
      {
        v14 = v30;
        v15 = v29 / v30;
        v42[1] = 1.0;
        v32 = 0.0;
        v31 = 0.0;
        v33 = 0.0;
        v30 = 0.0;
        v34 = 0.0;
        v42[0] = v15;
        v16 = 1.0 - v29;
        v29 = 0.0;
        v42[2] = fmaxf((float)(v16 - v14) / v14, v13);
        if ( ConvertUintToXY(&v29, &v32, &v49) && ConvertUintToXY(&v31, &v33, &v50) && ConvertUintToXY(&v30, &v34, &v51) )
        {
          v18 = v29 / v32;
          v36 = 1.0;
          v37 = 1065353216;
          v38 = 1065353216;
          v35[0] = v29 / v32;
          v19 = v31 / v33;
          v20 = v30 / v34;
          v21 = fmaxf((float)((float)(1.0 - v29) - v32) / v32, v17);
          v35[1] = v31 / v33;
          v22 = fmaxf((float)((float)(1.0 - v31) - v33) / v33, v17);
          v35[2] = v30 / v34;
          v23 = fmaxf((float)((float)(1.0 - v30) - v34) / v34, v17);
          v39 = v21;
          v40 = v22;
          v41 = v23;
          if ( InvertMatrix((float (*const)[3])v46, (const float (*const)[3])v35) )
          {
            MatrixMultiply(&v43, (const float (*const)[3])v46, v42);
            v35[1] = v19 * v44;
            v35[2] = v20 * v45;
            v40 = v22 * v44;
            v41 = v23 * v45;
            v35[0] = v18 * v43;
            v36 = v43;
            v37 = LODWORD(v44);
            v38 = LODWORD(v45);
            v39 = v21 * v43;
            MatrixMultiply(
              (float (*const)[3])a3,
              (const float (*const)[3])qword_18008FE50,
              (const float (*const)[3])v35);
            result = 1;
            v25 = *(_DWORD *)(a3 + 4);
            *(_DWORD *)(a3 + 4) = *(_DWORD *)(a3 + 12);
            *(_DWORD *)(a3 + 12) = v25;
            v26 = *(_DWORD *)(a3 + 8);
            *(_DWORD *)(a3 + 8) = *(_DWORD *)(a3 + 24);
            *(_DWORD *)(a3 + 24) = v26;
            v27 = *(_DWORD *)(a3 + 20);
            *(_DWORD *)(a3 + 20) = *(_DWORD *)(a3 + 28);
            *(_DWORD *)(a3 + 28) = v27;
            return result;
          }
          v7 = "Failed to invert the color primary XYZ matrix in InternalGetChromaticAdaptationMatrixForDisplay\n";
          v9 = 353;
        }
        else
        {
          v7 = "Invalid color primary value in InternalGetChromaticAdaptationMatrixForDisplay\n";
          v9 = 324;
        }
      }
      else
      {
        v7 = "Invalid white point value in InternalGetChromaticAdaptationMatrixForDisplay\n";
        v9 = 299;
      }
      v8 = 2147500037LL;
      goto LABEL_21;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180080d40  mov     rax, rsp
0x180080d43  push    rbp
0x180080d44  push    rbx
0x180080d45  push    rsi
0x180080d46  push    rdi
0x180080d47  push    r14
0x180080d49  lea     rbp, [rax-868h]
0x180080d50  sub     rsp, 940h
0x180080d57  movaps  xmmword ptr [rax-38h], xmm6
0x180080d5b  movaps  xmmword ptr [rax-48h], xmm7
0x180080d5f  movaps  xmmword ptr [rax-58h], xmm8
0x180080d64  movaps  xmmword ptr [rax-68h], xmm9
0x180080d69  movaps  xmmword ptr [rax-78h], xmm10
0x180080d6e  movaps  xmmword ptr [rax-88h], xmm11
0x180080d76  mov     rax, cs:__security_cookie
0x180080d7d  xor     rax, rsp
0x180080d80  mov     [rbp+860h+var_90], rax
0x180080d87  mov     rsi, rcx
0x180080d8a  mov     rdi, r8
0x180080d8d  shr     rsi, 20h
0x180080d91  mov     r14d, edx
0x180080d94  mov     rbx, rcx
0x180080d97  test    ecx, ecx
0x180080d99  jnz     short loc_180080DB6
0x180080d9b  test    esi, esi
0x180080d9d  jnz     short loc_180080DB6
0x180080d9f  lea     rax, aInvalidAdapter; "Invalid adapter LUID in InternalGetChro"...
0x180080da6  mov     r9d, 80070057h
0x180080dac  mov     edx, 0F9h
0x180080db1  jmp     loc_180081125
0x180080db6  cmp     r14d, 10h
0x180080dba  jb      short loc_180080DD3
0x180080dbc  lea     rax, aInvalidSourceI; "Invalid source Id in InternalGetChromat"...
0x180080dc3  mov     r9d, 80070057h
0x180080dc9  mov     edx, 0FFh
0x180080dce  jmp     loc_180081125
0x180080dd3  test    rdi, rdi
0x180080dd6  jz      loc_18008113D
0x180080ddc  xor     ecx, ecx
0x180080dde  xor     eax, eax
0x180080de0  inc     rcx
0x180080de3  mov     qword ptr [r8+rax+4], 0
0x180080dec  mov     dword ptr [r8+rax], 0
0x180080df4  lea     rax, [rax+0Ch]
0x180080df8  cmp     rcx, 3
0x180080dfc  jnz     short loc_180080DE0
0x180080dfe  xor     edx, edx; Val
0x180080e00  lea     rcx, [rbp+860h+var_88C]; void *
0x180080e04  mov     r8d, 7F4h; Size
0x180080e0a  call    memset_0
0x180080e0f  lea     rcx, [rbp+860h+requestPacket]; requestPacket
0x180080e13  mov     [rbp+860h+requestPacket.type], 0FFFFFFFEh
0x180080e1a  mov     [rbp+860h+requestPacket.size], 808h
0x180080e21  mov     [rbp+860h+requestPacket.adapterId.LowPart], ebx
0x180080e24  mov     [rbp+860h+requestPacket.adapterId.HighPart], esi
0x180080e27  mov     [rbp+860h+requestPacket.id], r14d
0x180080e2b  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180080e31  test    eax, eax
0x180080e33  jz      short loc_180080E61
0x180080e35  mov     rcx, [rbp+868h]; this
0x180080e3c  lea     rdx, aFailedToGetDis; "Failed to get display info in InternalG"...
0x180080e43  mov     qword ptr [rsp+960h+var_940], rdx; unsigned int
0x180080e48  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\color\\color"...
0x180080e4f  mov     edx, 119h; void *
0x180080e54  mov     r9d, eax; char *
0x180080e57  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180080e5c  jmp     loc_18008113D
0x180080e61  cmp     [rbp+860h+var_A8], 0
0x180080e68  jz      loc_18008113D
0x180080e6e  lea     r8, [rbp+860h+var_C8]; unsigned int *
0x180080e75  mov     [rsp+960h+var_930], 0
0x180080e7d  lea     rdx, [rsp+960h+var_92C]; float *
0x180080e82  mov     [rsp+960h+var_92C], 0
0x180080e8a  lea     rcx, [rsp+960h+var_930]; float *
0x180080e8f  xorps   xmm4, xmm4
0x180080e92  call    ?ConvertUintToXY@@YA_NAEAM0QEAI@Z; ConvertUintToXY(float &,float &,uint * const)
0x180080e97  test    al, al
0x180080e99  jnz     short loc_180080EAC
0x180080e9b  lea     rax, aInvalidWhitePo; "Invalid white point value in InternalGe"...
0x180080ea2  mov     edx, 12Bh
0x180080ea7  jmp     loc_18008111F
0x180080eac  movss   xmm1, [rsp+960h+var_92C]
0x180080eb2  lea     r8, [rbp+860h+var_E0]; unsigned int *
0x180080eb9  movss   xmm0, [rsp+960h+var_930]
0x180080ebf  lea     rdx, [rsp+960h+var_924]; float *
0x180080ec4  movss   xmm6, cs:__real@3f800000
0x180080ecc  lea     rcx, [rsp+960h+var_930]; float *
0x180080ed1  divss   xmm0, xmm1
0x180080ed5  mov     [rsp+960h+var_8EC], 3F800000h
0x180080edd  mov     [rsp+960h+var_924], 0
0x180080ee5  mov     [rsp+960h+var_928], 0
0x180080eed  mov     [rsp+960h+var_920], 0
0x180080ef5  mov     [rsp+960h+var_92C], 0
0x180080efd  mov     [rsp+960h+var_91C], 0
0x180080f05  movss   [rsp+960h+var_8F0], xmm0
0x180080f0b  movaps  xmm0, xmm6
0x180080f0e  subss   xmm0, [rsp+960h+var_930]
0x180080f14  mov     [rsp+960h+var_930], 0
0x180080f1c  subss   xmm0, xmm1
0x180080f20  divss   xmm0, xmm1
0x180080f24  maxss   xmm0, xmm4
0x180080f28  movss   [rsp+960h+var_8E8], xmm0
0x180080f2e  call    ?ConvertUintToXY@@YA_NAEAM0QEAI@Z; ConvertUintToXY(float &,float &,uint * const)
0x180080f33  test    al, al
0x180080f35  jz      loc_180081113
0x180080f3b  lea     r8, [rbp+860h+var_D8]; unsigned int *
0x180080f42  lea     rdx, [rsp+960h+var_920]; float *
0x180080f47  lea     rcx, [rsp+960h+var_928]; float *
0x180080f4c  call    ?ConvertUintToXY@@YA_NAEAM0QEAI@Z; ConvertUintToXY(float &,float &,uint * const)
0x180080f51  test    al, al
0x180080f53  jz      loc_180081113
0x180080f59  lea     r8, [rbp+860h+var_D0]; unsigned int *
0x180080f60  lea     rdx, [rsp+960h+var_91C]; float *
0x180080f65  lea     rcx, [rsp+960h+var_92C]; float *
0x180080f6a  call    ?ConvertUintToXY@@YA_NAEAM0QEAI@Z; ConvertUintToXY(float &,float &,uint * const)
0x180080f6f  test    al, al
0x180080f71  jz      loc_180081113
0x180080f77  movss   xmm0, [rsp+960h+var_924]
0x180080f7d  lea     rdx, [rsp+960h+var_918]; float (*)[3]
0x180080f82  movss   xmm1, [rsp+960h+var_920]
0x180080f88  lea     rcx, [rbp+860h+var_8D0]; float (*)[3]
0x180080f8c  movss   xmm2, [rsp+960h+var_91C]
0x180080f92  movaps  xmm7, xmm6
0x180080f95  subss   xmm7, [rsp+960h+var_930]
0x180080f9b  movss   xmm9, [rsp+960h+var_930]
0x180080fa2  movaps  xmm8, xmm6
0x180080fa6  subss   xmm8, [rsp+960h+var_928]
0x180080fad  subss   xmm6, [rsp+960h+var_92C]
0x180080fb3  movss   xmm10, [rsp+960h+var_928]
0x180080fba  movss   xmm11, [rsp+960h+var_92C]
0x180080fc1  subss   xmm7, xmm0
0x180080fc5  divss   xmm9, xmm0
0x180080fca  mov     [rsp+960h+var_90C], 3F800000h
0x180080fd2  mov     [rsp+960h+var_908], 3F800000h
0x180080fda  mov     [rsp+960h+var_904], 3F800000h
0x180080fe2  subss   xmm8, xmm1
0x180080fe7  subss   xmm6, xmm2
0x180080feb  movss   [rsp+960h+var_918], xmm9
0x180080ff2  divss   xmm7, xmm0
0x180080ff6  divss   xmm8, xmm1
0x180080ffb  divss   xmm6, xmm2
0x180080fff  divss   xmm10, xmm1
0x180081004  divss   xmm11, xmm2
0x180081009  maxss   xmm7, xmm4
0x18008100d  movss   [rsp+960h+var_918+4], xmm10
0x180081014  maxss   xmm8, xmm4
0x180081019  movss   [rsp+960h+var_918+8], xmm11
0x180081020  maxss   xmm6, xmm4
0x180081024  movss   [rsp+960h+var_900], xmm7
0x18008102a  movss   [rsp+960h+var_8FC], xmm8
0x180081031  movss   [rsp+960h+var_8F8], xmm6
0x180081037  call    ?InvertMatrix@@YA_NQEAY02MQEAY02$$CBM@Z; InvertMatrix(float (* const)[3],float const (* const)[3])
0x18008103c  test    al, al
0x18008103e  jnz     short loc_180081051
0x180081040  lea     rax, aFailedToInvert; "Failed to invert the color primary XYZ "...
0x180081047  mov     edx, 161h
0x18008104c  jmp     loc_18008111F
0x180081051  lea     r8, [rsp+960h+var_8F0]; float *
0x180081056  lea     rdx, [rbp+860h+var_8D0]; float (*)[3]
0x18008105a  lea     rcx, [rbp+860h+var_8E0]; float *
0x18008105e  call    ?MatrixMultiply@@YAXQEAMQEAY02$$CBMQEBM@Z; MatrixMultiply(float * const,float const (* const)[3],float const * const)
0x180081063  movss   xmm1, [rbp+860h+var_8DC]
0x180081068  lea     r8, [rsp+960h+var_918]; float (*)[3]
0x18008106d  movss   xmm0, [rbp+860h+var_8D8]
0x180081072  lea     rdx, qword_18008FE50; float (*)[3]
0x180081079  movss   xmm4, [rbp+860h+var_8E0]
0x18008107e  mov     rcx, rdi; float (*)[3]
0x180081081  mulss   xmm10, xmm1
0x180081086  mulss   xmm11, xmm0
0x18008108b  mulss   xmm8, xmm1
0x180081090  mulss   xmm6, xmm0
0x180081094  mulss   xmm9, xmm4
0x180081099  mulss   xmm7, xmm4
0x18008109d  movss   [rsp+960h+var_918+4], xmm10
0x1800810a4  movss   [rsp+960h+var_918+8], xmm11
0x1800810ab  movss   [rsp+960h+var_8FC], xmm8
0x1800810b2  movss   [rsp+960h+var_8F8], xmm6
0x1800810b8  movss   [rsp+960h+var_918], xmm9
0x1800810bf  movss   [rsp+960h+var_90C], xmm4
0x1800810c5  movss   [rsp+960h+var_908], xmm1
0x1800810cb  movss   [rsp+960h+var_904], xmm0
0x1800810d1  movss   [rsp+960h+var_900], xmm7
0x1800810d7  call    ?MatrixMultiply@@YAXQEAY02MQEAY02$$CBM1@Z; MatrixMultiply(float (* const)[3],float const (* const)[3],float const (* const)[3])
0x1800810dc  mov     ecx, [rdi+0Ch]
0x1800810df  mov     eax, 1
0x1800810e4  movss   xmm4, dword ptr [rdi+4]
0x1800810e9  mov     [rdi+4], ecx
0x1800810ec  movss   dword ptr [rdi+0Ch], xmm4
0x1800810f1  movss   xmm0, dword ptr [rdi+8]
0x1800810f6  mov     ecx, [rdi+18h]
0x1800810f9  mov     [rdi+8], ecx
0x1800810fc  movss   dword ptr [rdi+18h], xmm0
0x180081101  movss   xmm0, dword ptr [rdi+14h]
0x180081106  mov     ecx, [rdi+1Ch]
0x180081109  mov     [rdi+14h], ecx
0x18008110c  movss   dword ptr [rdi+1Ch], xmm0
0x180081111  jmp     short loc_18008113F
0x180081113  lea     rax, aInvalidColorPr; "Invalid color primary value in Internal"...
0x18008111a  mov     edx, 144h; void *
0x18008111f  mov     r9d, 80004005h; char *
0x180081125  mov     rcx, [rbp+868h]; this
0x18008112c  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\color\\color"...
0x180081133  mov     qword ptr [rsp+960h+var_940], rax; int
0x180081138  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008113d  xor     eax, eax
0x18008113f  mov     rcx, [rbp+860h+var_90]
0x180081146  xor     rcx, rsp; StackCookie
0x180081149  call    __security_check_cookie
0x18008114e  lea     r11, [rsp+960h+var_20]
0x180081156  movaps  xmm6, xmmword ptr [r11-10h]
0x18008115b  movaps  xmm7, xmmword ptr [r11-20h]
0x180081160  movaps  xmm8, xmmword ptr [r11-30h]
0x180081165  movaps  xmm9, xmmword ptr [r11-40h]
0x18008116a  movaps  xmm10, xmmword ptr [r11-50h]
0x18008116f  movaps  xmm11, xmmword ptr [r11-60h]
0x180081174  mov     rsp, r11
0x180081177  pop     r14
0x180081179  pop     rdi
0x18008117a  pop     rsi
0x18008117b  pop     rbx
0x18008117c  pop     rbp
0x18008117d  retn
```

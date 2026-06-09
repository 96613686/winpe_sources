# ApplyAdvancedColorCalibration(HMONITOR__ *,AdvancedColorCalibrationData *)

- ea: `0x1800258c0`
- end: `0x18002607e`
- name: `?ApplyAdvancedColorCalibration@@YAJPEAUHMONITOR__@@PEAUAdvancedColorCalibrationData@@@Z`
- size: `1982`
- prototype: `__int64 __fastcall(HMONITOR hMonitor, struct AdvancedColorCalibrationData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180047f20`

## callees

- `0x18001582c`
- `0x180015e7c`
- `0x180016660`
- `0x180016f50`
- `0x1800258c0`
- `0x18002e5f0`
- `0x18002e614`
- `0x18002e670`
- `0x18002eab4`
- `0x18002f2f4`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025a38`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025aa8`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025b18`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025a38`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025aa8`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x180025b18`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025ff6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002600b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002600b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800259f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800259f2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800259b1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800259b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ApplyAdvancedColorCalibration(HMONITOR hMonitor, struct AdvancedColorCalibrationData *a2)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // r14
  _QWORD *v5; // r13
  _DWORD *v6; // rsi
  HRESULT v8; // ebx
  LONG DeviceInfo; // eax
  bool v10; // sf
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // r12d
  __int64 v14; // rbx
  __int64 v15; // rcx
  unsigned int v16; // r12d
  __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned int v19; // r12d
  __int64 v20; // rbx
  __m64 *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // r15d
  __int64 v25; // r12
  double v26; // xmm0_8
  double v27; // xmm0_8
  unsigned int v28; // r10d
  __m128i si128; // xmm4
  __int64 v30; // r11
  __m128 v31; // xmm5
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rax
  __m128 v36; // xmm3
  __m128 v37; // xmm2
  __m128 v38; // xmm1
  unsigned __int32 v39; // xmm0_4
  __int64 v40; // rax
  __int64 v41; // r9
  __m128 v42; // xmm3
  __int64 v43; // r8
  __m128 v44; // xmm2
  __m128 v45; // xmm1
  __int64 v46; // rdx
  __int64 v47; // rax
  unsigned __int32 v48; // xmm0_4
  __int64 v50; // [rsp+38h] [rbp-D0h]
  __int64 v51; // [rsp+38h] [rbp-D0h]
  __int64 v52; // [rsp+38h] [rbp-D0h]
  _QWORD *v53; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v56; // [rsp+68h] [rbp-A0h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+78h] [rbp-90h] BYREF
  char v58[144]; // [rsp+8Ch] [rbp-7Ch] BYREF
  WCHAR sourceString[134]; // [rsp+11Ch] [rbp+14h] BYREF
  struct DISPLAYCONFIG_PATH_INFO UserData; // [rsp+228h] [rbp+120h] BYREF
  _OWORD v61[6]; // [rsp+278h] [rbp+170h] BYREF

  memset(&UserData, 0, sizeof(UserData));
  v3 = 0;
  v4 = 0;
  string = 0;
  v5 = 0;
  v6 = 0;
  v56 = (unsigned __int16 *)operator new[](0x208u);
  v8 = InternalTranslateHMonitorToICMName(hMonitor, v56);
  if ( v8 >= 0 )
  {
    v8 = InternalTranslateICMNameToPath(v56, &UserData);
    if ( v8 >= 0 )
    {
      memset_0(v58, 0, 0x190u);
      requestPacket.adapterId = UserData.targetInfo.adapterId;
      requestPacket.id = UserData.targetInfo.id;
      requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
      requestPacket.size = 420;
      DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
      v10 = DeviceInfo < 0;
      if ( DeviceInfo > 0 )
        v10 = 1;
      if ( v10 )
      {
LABEL_6:
        v8 = -2147024809;
        goto LABEL_43;
      }
      v11 = -1;
      do
        ++v11;
      while ( sourceString[v11] );
      v8 = WindowsCreateString(sourceString, v11, &string);
      if ( v8 >= 0 )
      {
        if ( a2 )
        {
          v12 = *((_QWORD *)a2 + 2);
          v50 = v12;
          if ( v12 )
          {
            v13 = *((_DWORD *)a2 + 2);
            if ( v13 >= 2 )
            {
              v14 = 0;
              while ( _finite(*(float *)(v12 + 4 * v14)) )
              {
                v12 = v50;
                v14 = (unsigned int)(v14 + 1);
                if ( (unsigned int)v14 >= v13 )
                {
                  v53 = operator new(0x18u);
                  v3 = v53;
                  *v53 = &UniformPointListCurve::`vftable';
                  v3[1] = v50;
                  *((_DWORD *)v3 + 4) = v13;
                  v15 = *((_QWORD *)a2 + 3);
                  v51 = v15;
                  if ( v15 )
                  {
                    v16 = *((_DWORD *)a2 + 2);
                    if ( v16 >= 2 )
                    {
                      v17 = 0;
                      while ( _finite(*(float *)(v15 + 4 * v17)) )
                      {
                        v15 = v51;
                        v17 = (unsigned int)(v17 + 1);
                        if ( (unsigned int)v17 >= v16 )
                        {
                          v53 = operator new(0x18u);
                          v4 = v53;
                          *v53 = &UniformPointListCurve::`vftable';
                          v4[1] = v51;
                          *((_DWORD *)v4 + 4) = v16;
                          v18 = *((_QWORD *)a2 + 4);
                          v52 = v18;
                          if ( v18 )
                          {
                            v19 = *((_DWORD *)a2 + 2);
                            if ( v19 >= 2 )
                            {
                              v20 = 0;
                              while ( _finite(*(float *)(v18 + 4 * v20)) )
                              {
                                v18 = v52;
                                v20 = (unsigned int)(v20 + 1);
                                if ( (unsigned int)v20 >= v19 )
                                {
                                  v5 = operator new(0x18u);
                                  v53 = v5;
                                  *v5 = &UniformPointListCurve::`vftable';
                                  v5[1] = v52;
                                  *((_DWORD *)v5 + 4) = v19;
                                  goto LABEL_27;
                                }
                              }
                            }
                          }
                          goto LABEL_6;
                        }
                      }
                    }
                  }
                  goto LABEL_6;
                }
              }
            }
          }
          goto LABEL_6;
        }
LABEL_27:
        memset(v61, 0, sizeof(v61));
        v6 = operator new(0xC000u);
        *v6 = 0;
        memset_0(v6 + 1, 0, 0xBFFCu);
        if ( a2 )
        {
          v21 = *(__m64 **)a2;
          if ( (unsigned __int64)v61 > *(_QWORD *)a2 + 44LL || (__m64 *)((char *)&v61[5] + 8) < v21 )
          {
            v61[0] = _mm_cvtps_pd((__m64)v21->m64_u64);
            v61[1] = _mm_cvtps_pd(v21[1]);
            v61[2] = _mm_cvtps_pd(v21[2]);
            v61[3] = _mm_cvtps_pd(v21[3]);
            v61[4] = _mm_cvtps_pd(v21[4]);
            v61[5] = _mm_cvtps_pd(v21[5]);
          }
          else
          {
            v22 = 0;
            do
            {
              *((double *)v61 + v22) = v21->m64_f32[v22];
              *((double *)v61 + (unsigned int)(v22 + 1)) = v21->m64_f32[(unsigned int)(v22 + 1)];
              *((double *)v61 + (unsigned int)(v22 + 2)) = v21->m64_f32[(unsigned int)(v22 + 2)];
              v23 = (unsigned int)(v22 + 3);
              v22 = (unsigned int)(v22 + 4);
              *((double *)v61 + v23) = v21->m64_f32[v23];
            }
            while ( (unsigned int)v22 < 9 );
            for ( ; (unsigned int)v22 < 0xC; v22 = (unsigned int)(v22 + 1) )
              *((double *)v61 + v22) = v21->m64_f32[v22];
          }
          v24 = 0;
          v25 = 0;
          do
          {
            v26 = (*(double (__fastcall **)(_QWORD *))*v3)(v3);
            v6[3 * v25] = LODWORD(v26);
            v27 = (*(double (__fastcall **)(_QWORD *))*v4)(v4);
            v6[3 * v25 + 1] = LODWORD(v27);
            ++v24;
            *(float *)&v6[3 * v25++ + 2] = (*(float (__fastcall **)(_QWORD *))*v5)(v5);
          }
          while ( v24 < 0x1000 );
        }
        else
        {
          v28 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v30 = 0;
          v31 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
          *(double *)v61 = DOUBLE_1_0;
          *((double *)&v61[2] + 1) = DOUBLE_1_0;
          *(double *)&v61[5] = DOUBLE_1_0;
          do
          {
            v32 = 3LL * (v28 + 1);
            v33 = 3 * v30;
            v34 = 3LL * (v28 + 2);
            v35 = 3LL * (v28 + 3);
            v30 += 8;
            v36 = _mm_div_ps(_mm_cvtepi32_ps(_mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v28), 0), si128)), v31);
            v6[v33] = v36.m128_i32[0];
            v37 = _mm_shuffle_ps(v36, v36, 229);
            v6[v33 + 1] = v36.m128_i32[0];
            v38 = _mm_unpackhi_ps(v37, v37);
            v6[v33 + 2] = v36.m128_i32[0];
            v39 = _mm_unpackhi_ps(v38, v38).m128_u32[0];
            v6[v35] = v39;
            v6[v35 + 1] = v39;
            v6[v35 + 2] = v39;
            v40 = v28 + 4;
            v41 = 3 * v40;
            v6[v32] = v37.m128_i32[0];
            v6[v32 + 1] = v37.m128_i32[0];
            v42 = _mm_div_ps(_mm_cvtepi32_ps(_mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v40), 0), si128)), v31);
            v6[v32 + 2] = v37.m128_i32[0];
            v43 = 3LL * (v28 + 5);
            v6[v34] = v38.m128_i32[0];
            v6[v34 + 1] = v38.m128_i32[0];
            v44 = _mm_shuffle_ps(v42, v42, 229);
            v6[v34 + 2] = v38.m128_i32[0];
            v45 = _mm_unpackhi_ps(v44, v44);
            v46 = 3LL * (v28 + 6);
            v6[v41] = v42.m128_i32[0];
            v47 = 3LL * (v28 + 7);
            v6[v43] = v44.m128_i32[0];
            v6[v46] = v45.m128_i32[0];
            v48 = _mm_unpackhi_ps(v45, v45).m128_u32[0];
            v28 += 8;
            v6[v47] = v48;
            v6[v47 + 1] = v48;
            v6[v47 + 2] = v48;
            v6[v41 + 1] = v42.m128_i32[0];
            v6[v43 + 1] = v44.m128_i32[0];
            v6[v46 + 1] = v45.m128_i32[0];
            v6[v41 + 2] = v42.m128_i32[0];
            v6[v43 + 2] = v44.m128_i32[0];
            v6[v46 + 2] = v45.m128_i32[0];
          }
          while ( v28 < 0x1000 );
        }
        EventDescriptor_8 = (EVENT_DESCRIPTOR)xmmword_18008C718;
        v8 = ModernColorSetMatrix(string, (struct _GUID *)&EventDescriptor_8, (double (*)[12])v61);
        if ( v8 >= 0 )
        {
          EventDescriptor_8 = (EVENT_DESCRIPTOR)xmmword_18008C718;
          v8 = ModernColorSetLut(string, (struct _GUID *)&EventDescriptor_8, (struct FloatTriple (*)[4096])v6);
        }
      }
    }
  }
LABEL_43:
  if ( (unsigned int)dword_18009E048 > 5 && (qword_18009E058 & 1) != 0 && (qword_18009E060 & 1) == qword_18009E060 )
  {
    LODWORD(v53) = v8;
    *(_QWORD *)&UserData.targetInfo.modeInfoIdx = &v53;
    UserData.sourceInfo.adapterId = (LUID)off_18009E050;
    *(_QWORD *)&UserData.targetInfo.rotation = 4;
    *(_QWORD *)&EventDescriptor_8.Id = 0x50B000000LL;
    EventDescriptor_8.Keyword = 1;
    UserData.sourceInfo.id = *(unsigned __int16 *)off_18009E050;
    *(_QWORD *)&UserData.sourceInfo.statusFlags = &byte_1800920B7;
    UserData.sourceInfo.modeInfoIdx = 2;
    *(_QWORD *)&UserData.targetInfo.adapterId.HighPart = 0x10000002ELL;
    EventWriteTransfer(qword_18009E068, &EventDescriptor_8, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)&UserData);
  }
  operator delete(v56);
  WindowsDeleteString(string);
  operator delete(0);
  operator delete(0);
  operator delete(v3);
  operator delete(v4);
  operator delete(v5);
  operator delete(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800258c0  mov     r11, rsp
0x1800258c3  push    rbp
0x1800258c4  push    rbx
0x1800258c5  push    rsi
0x1800258c6  push    rdi
0x1800258c7  push    r13
0x1800258c9  push    r14
0x1800258cb  lea     rbp, [r11-238h]
0x1800258d2  sub     rsp, 308h
0x1800258d9  mov     rax, cs:__security_cookie
0x1800258e0  xor     rax, rsp
0x1800258e3  mov     [rbp+230h+var_60], rax
0x1800258ea  xorps   xmm0, xmm0
0x1800258ed  mov     [r11+18h], r12
0x1800258f1  mov     rbx, rcx
0x1800258f4  mov     [r11-38h], r15
0x1800258f8  xor     ecx, ecx
0x1800258fa  xor     eax, eax
0x1800258fc  mov     dword ptr [rbp+230h+var_110.Ptr], ecx
0x180025902  mov     edi, ecx
0x180025904  mov     r14d, ecx
0x180025907  mov     [rsp+330h+string], rcx
0x18002590c  mov     r13d, ecx
0x18002590f  mov     [rbp+230h+var_CC], eax
0x180025915  mov     esi, ecx
0x180025917  mov     r15, rdx
0x18002591a  mov     ecx, 208h; unsigned __int64
0x18002591f  movups  xmmword ptr [rbp+230h+var_110.Ptr+4], xmm0
0x180025926  movups  [rbp+230h+var_FC], xmm0
0x18002592d  movups  [rbp+230h+var_EC], xmm0
0x180025934  movups  [rbp+230h+var_DC], xmm0
0x18002593b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025940  mov     rdx, rax; unsigned __int16 *
0x180025943  mov     [rsp+330h+var_2D0], rax
0x180025948  mov     rcx, rbx; hMonitor
0x18002594b  mov     r12, rax
0x18002594e  call    ?InternalTranslateHMonitorToICMName@@YAJPEAUHMONITOR__@@PEAG@Z; InternalTranslateHMonitorToICMName(HMONITOR__ *,ushort *)
0x180025953  mov     ebx, eax
0x180025955  test    eax, eax
0x180025957  js      loc_180025EFA
0x18002595d  lea     rdx, [rbp+230h+var_110]; struct DISPLAYCONFIG_PATH_INFO *
0x180025964  mov     rcx, r12; unsigned __int16 *
0x180025967  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x18002596c  mov     ebx, eax
0x18002596e  test    eax, eax
0x180025970  js      loc_180025EFA
0x180025976  xor     edx, edx; Val
0x180025978  lea     rcx, [rbp+230h+var_2AC]; void *
0x18002597c  mov     r8d, 190h; Size
0x180025982  call    memset_0
0x180025987  mov     rax, qword ptr [rbp+230h+var_FC]
0x18002598e  lea     rcx, [rsp+330h+requestPacket]; requestPacket
0x180025993  mov     qword ptr [rsp+330h+requestPacket.adapterId.LowPart], rax
0x180025998  mov     eax, dword ptr [rbp+230h+var_FC+8]
0x18002599e  mov     [rbp+230h+requestPacket.id], eax
0x1800259a1  mov     [rsp+330h+requestPacket.type], 2
0x1800259a9  mov     [rsp+330h+requestPacket.size], 1A4h
0x1800259b1  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800259b7  test    eax, eax
0x1800259b9  jle     short loc_1800259C5
0x1800259bb  movzx   eax, ax
0x1800259be  or      eax, 80070000h
0x1800259c3  test    eax, eax
0x1800259c5  jns     short loc_1800259D1
0x1800259c7  mov     ebx, 80070057h
0x1800259cc  jmp     loc_180025EFA
0x1800259d1  lea     rax, [rbp+230h+sourceString]
0x1800259d5  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800259dc  nop     dword ptr [rax+00h]
0x1800259e0  inc     rdx; length
0x1800259e3  cmp     [rax+rdx*2], si
0x1800259e7  jnz     short loc_1800259E0
0x1800259e9  lea     r8, [rsp+330h+string]; string
0x1800259ee  lea     rcx, [rbp+230h+sourceString]; sourceString
0x1800259f2  call    cs:__imp_WindowsCreateString
0x1800259f8  mov     ebx, eax
0x1800259fa  test    eax, eax
0x1800259fc  js      loc_180025EFA
0x180025a02  test    r15, r15
0x180025a05  jz      loc_180025B5C
0x180025a0b  mov     rcx, [r15+10h]
0x180025a0f  mov     [rsp+330h+var_300], rcx
0x180025a14  test    rcx, rcx
0x180025a17  jz      short loc_1800259C7
0x180025a19  mov     r12d, [r15+8]
0x180025a1d  cmp     r12d, 2
0x180025a21  jb      short loc_1800259C7
0x180025a23  xor     ebx, ebx
0x180025a25  nop     word ptr [rax+rax+00000000h]
0x180025a30  movss   xmm0, dword ptr [rcx+rbx*4]
0x180025a35  cvtps2pd xmm0, xmm0; X
0x180025a38  call    cs:__imp__finite
0x180025a3e  test    eax, eax
0x180025a40  jz      short loc_1800259C7
0x180025a42  mov     rcx, [rsp+330h+var_300]
0x180025a47  inc     ebx
0x180025a49  cmp     ebx, r12d
0x180025a4c  jb      short loc_180025A30
0x180025a4e  mov     ecx, 18h; Size
0x180025a53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025a58  mov     [rsp+330h+var_2F8], rax
0x180025a5d  mov     rdi, rax
0x180025a60  lea     rax, ??_7UniformPointListCurve@@6B@; const UniformPointListCurve::`vftable'
0x180025a67  mov     [rdi], rax
0x180025a6a  mov     rax, [rsp+330h+var_300]
0x180025a6f  mov     [rdi+8], rax
0x180025a73  mov     [rdi+10h], r12d
0x180025a77  mov     rcx, [r15+18h]
0x180025a7b  mov     [rsp+330h+var_300], rcx
0x180025a80  test    rcx, rcx
0x180025a83  jz      loc_1800259C7
0x180025a89  mov     r12d, [r15+8]
0x180025a8d  cmp     r12d, 2
0x180025a91  jb      loc_1800259C7
0x180025a97  xor     ebx, ebx
0x180025a99  nop     dword ptr [rax+00000000h]
0x180025aa0  movss   xmm0, dword ptr [rcx+rbx*4]
0x180025aa5  cvtps2pd xmm0, xmm0; X
0x180025aa8  call    cs:__imp__finite
0x180025aae  test    eax, eax
0x180025ab0  jz      loc_1800259C7
0x180025ab6  mov     rcx, [rsp+330h+var_300]
0x180025abb  inc     ebx
0x180025abd  cmp     ebx, r12d
0x180025ac0  jb      short loc_180025AA0
0x180025ac2  mov     ecx, 18h; Size
0x180025ac7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025acc  mov     [rsp+330h+var_2F8], rax
0x180025ad1  mov     r14, rax
0x180025ad4  lea     rax, ??_7UniformPointListCurve@@6B@; const UniformPointListCurve::`vftable'
0x180025adb  mov     [r14], rax
0x180025ade  mov     rax, [rsp+330h+var_300]
0x180025ae3  mov     [r14+8], rax
0x180025ae7  mov     [r14+10h], r12d
0x180025aeb  mov     rcx, [r15+20h]
0x180025aef  mov     [rsp+330h+var_300], rcx
0x180025af4  test    rcx, rcx
0x180025af7  jz      loc_1800259C7
0x180025afd  mov     r12d, [r15+8]
0x180025b01  cmp     r12d, 2
0x180025b05  jb      loc_1800259C7
0x180025b0b  xor     ebx, ebx
0x180025b0d  nop     dword ptr [rax]
0x180025b10  movss   xmm0, dword ptr [rcx+rbx*4]
0x180025b15  cvtps2pd xmm0, xmm0; X
0x180025b18  call    cs:__imp__finite
0x180025b1e  test    eax, eax
0x180025b20  jz      loc_1800259C7
0x180025b26  mov     rcx, [rsp+330h+var_300]
0x180025b2b  inc     ebx
0x180025b2d  cmp     ebx, r12d
0x180025b30  jb      short loc_180025B10
0x180025b32  mov     ecx, 18h; Size
0x180025b37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025b3c  mov     r13, rax
0x180025b3f  mov     [rsp+330h+var_2F8], rax
0x180025b44  lea     rax, ??_7UniformPointListCurve@@6B@; const UniformPointListCurve::`vftable'
0x180025b4b  mov     [r13+0], rax
0x180025b4f  mov     rax, [rsp+330h+var_300]
0x180025b54  mov     [r13+8], rax
0x180025b58  mov     [r13+10h], r12d
0x180025b5c  xorps   xmm0, xmm0
0x180025b5f  mov     ecx, 0C000h; Size
0x180025b64  movups  xmmword ptr [rbp+230h+var_C0], xmm0
0x180025b6b  movups  xmmword ptr [rbp+230h+var_C0+10h], xmm0
0x180025b72  movups  xmmword ptr [rbp+230h+var_C0+20h], xmm0
0x180025b79  movups  xmmword ptr [rbp+230h+var_C0+30h], xmm0
0x180025b80  movups  xmmword ptr [rbp+230h+var_C0+40h], xmm0
0x180025b87  movups  xmmword ptr [rbp+230h+var_C0+50h], xmm0
0x180025b8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025b93  xor     edx, edx; Val
0x180025b95  mov     r8d, 0BFFCh; Size
0x180025b9b  mov     rsi, rax
0x180025b9e  lea     rcx, [rax+4]; void *
0x180025ba2  mov     dword ptr [rax], 0
0x180025ba8  call    memset_0
0x180025bad  test    r15, r15
0x180025bb0  jz      loc_180025D3E
0x180025bb6  mov     r8, [r15]
0x180025bb9  lea     rcx, [rbp+230h+var_C0]
0x180025bc0  movaps  [rsp+330h+var_48+8], xmm6
0x180025bc8  movaps  [rsp+330h+var_58+8], xmm7
0x180025bd0  lea     rax, [r8+2Ch]
0x180025bd4  cmp     rcx, rax
0x180025bd7  ja      loc_180025C69
0x180025bdd  lea     rax, [rbp+230h+var_C0+58h]
0x180025be4  cmp     rax, r8
0x180025be7  jb      loc_180025C69
0x180025bed  xor     edx, edx
0x180025bef  nop
0x180025bf0  movss   xmm0, dword ptr [r8+rdx*4]
0x180025bf6  lea     eax, [rdx+1]
0x180025bf9  cvtps2pd xmm0, xmm0
0x180025bfc  movsd   [rbp+rdx*8+230h+var_C0], xmm0
0x180025c05  movss   xmm0, dword ptr [r8+rax*4]
0x180025c0b  cvtps2pd xmm0, xmm0
0x180025c0e  movsd   [rbp+rax*8+230h+var_C0], xmm0
0x180025c17  lea     eax, [rdx+2]
0x180025c1a  movss   xmm0, dword ptr [r8+rax*4]
0x180025c20  cvtps2pd xmm0, xmm0
0x180025c23  movsd   [rbp+rax*8+230h+var_C0], xmm0
0x180025c2c  lea     eax, [rdx+3]
0x180025c2f  movss   xmm0, dword ptr [r8+rax*4]
0x180025c35  add     edx, 4
0x180025c38  cvtps2pd xmm0, xmm0
0x180025c3b  movsd   [rbp+rax*8+230h+var_C0], xmm0
0x180025c44  cmp     edx, 9
0x180025c47  jb      short loc_180025BF0
0x180025c49  cmp     edx, 0Ch
0x180025c4c  jnb     short loc_180025CB0
0x180025c4e  movss   xmm0, dword ptr [r8+rdx*4]
0x180025c54  cvtps2pd xmm0, xmm0
0x180025c57  movsd   [rbp+rdx*8+230h+var_C0], xmm0
0x180025c60  inc     edx
0x180025c62  cmp     edx, 0Ch
0x180025c65  jb      short loc_180025C4E
0x180025c67  jmp     short loc_180025CB0
0x180025c69  cvtps2pd xmm0, qword ptr [r8]
0x180025c6d  movups  xmmword ptr [rbp+230h+var_C0], xmm0
0x180025c74  cvtps2pd xmm0, qword ptr [r8+8]
0x180025c79  movups  xmmword ptr [rbp+230h+var_C0+10h], xmm0
0x180025c80  cvtps2pd xmm0, qword ptr [r8+10h]
0x180025c85  movups  xmmword ptr [rbp+230h+var_C0+20h], xmm0
0x180025c8c  cvtps2pd xmm0, qword ptr [r8+18h]
0x180025c91  movups  xmmword ptr [rbp+230h+var_C0+30h], xmm0
0x180025c98  cvtps2pd xmm0, qword ptr [r8+20h]
0x180025c9d  movups  xmmword ptr [rbp+230h+var_C0+40h], xmm0
0x180025ca4  cvtps2pd xmm0, qword ptr [r8+28h]
0x180025ca9  movups  xmmword ptr [rbp+230h+var_C0+50h], xmm0
0x180025cb0  movss   xmm7, cs:__real@457ff000
0x180025cb8  xor     r15d, r15d
0x180025cbb  xor     r12d, r12d
0x180025cbe  xchg    ax, ax
0x180025cc0  xorps   xmm6, xmm6
0x180025cc3  mov     eax, r15d
0x180025cc6  mov     rcx, rdi
0x180025cc9  lea     rbx, [r12+r12*2]
0x180025ccd  cvtsi2ss xmm6, rax
0x180025cd2  mov     rax, [rdi]
0x180025cd5  mov     rax, [rax]
0x180025cd8  divss   xmm6, xmm7
0x180025cdc  movaps  xmm1, xmm6
0x180025cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce4  movss   dword ptr [rsi+rbx*4], xmm0
0x180025ce9  movaps  xmm1, xmm6
0x180025cec  mov     rax, [r14]
0x180025cef  mov     rcx, r14
0x180025cf2  mov     rax, [rax]
0x180025cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cfa  movss   dword ptr [rsi+rbx*4+4], xmm0
0x180025d00  movaps  xmm1, xmm6
0x180025d03  mov     rax, [r13+0]
0x180025d07  mov     rcx, r13
0x180025d0a  mov     rax, [rax]
0x180025d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d12  inc     r15d
0x180025d15  movss   dword ptr [rsi+rbx*4+8], xmm0
0x180025d1b  lea     r12, [r12+1]
0x180025d20  cmp     r15d, 1000h
0x180025d27  jb      short loc_180025CC0
0x180025d29  movaps  xmm7, [rsp+330h+var_58+8]
0x180025d31  movaps  xmm6, [rsp+330h+var_48+8]
0x180025d39  jmp     loc_180025EB2
0x180025d3e  movsd   xmm0, cs:__real@3ff0000000000000
0x180025d46  xor     r10d, r10d
0x180025d49  movdqa  xmm4, cs:__xmm@00000003000000020000000100000000
0x180025d51  xor     r11d, r11d
0x180025d54  movdqa  xmm5, cs:__xmm@457ff000457ff000457ff000457ff000
0x180025d5c  movsd   [rbp+230h+var_C0], xmm0
0x180025d64  movsd   [rbp+230h+var_C0+28h], xmm0
0x180025d6c  movsd   [rbp+230h+var_C0+50h], xmm0
0x180025d74  nop     dword ptr [rax+00h]
0x180025d78  nop     dword ptr [rax+rax+00000000h]
0x180025d80  lea     eax, [r10+1]
0x180025d84  movd    xmm0, r10d
0x180025d89  lea     r8, [rax+rax*2]
0x180025d8d  pshufd  xmm0, xmm0, 0
0x180025d92  paddd   xmm0, xmm4
0x180025d96  lea     r9, [r11+r11*2]
0x180025d9a  cvtdq2ps xmm3, xmm0
0x180025d9d  lea     eax, [r10+2]
0x180025da1  lea     rdx, [rax+rax*2]
0x180025da5  lea     eax, [r10+3]
0x180025da9  lea     rax, [rax+rax*2]
0x180025dad  lea     r11, [r11+8]
0x180025db1  divps   xmm3, xmm5
0x180025db4  movss   dword ptr [rsi+r9*4], xmm3
0x180025dba  movaps  xmm2, xmm3
0x180025dbd  shufps  xmm2, xmm3, 0E5h
0x180025dc1  movss   dword ptr [rsi+r9*4+4], xmm3
0x180025dc8  movaps  xmm1, xmm2
0x180025dcb  unpckhps xmm1, xmm2
0x180025dce  movss   dword ptr [rsi+r9*4+8], xmm3
0x180025dd5  movaps  xmm0, xmm1
0x180025dd8  unpckhps xmm0, xmm1
0x180025ddb  movss   dword ptr [rsi+rax*4], xmm0
0x180025de0  movss   dword ptr [rsi+rax*4+4], xmm0
0x180025de6  movss   dword ptr [rsi+rax*4+8], xmm0
0x180025dec  lea     eax, [r10+4]
0x180025df0  movd    xmm0, eax
  ... truncated ...
```

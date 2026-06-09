# KpsGPRead(void)

- ea: `0x18001a1e0`
- end: `0x18001a861`
- name: `?KpsGPRead@@YAKXZ`
- size: `1665`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019ad0`
- `0x180019dcc`

## callees

- `0x180019a20`
- `0x18001a1e0`
- `0x18001aa80`
- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18003012c`
- `0x180031040`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001a73f`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a73f`
- `ntdll!RtlEnterCriticalSection` at `0x18001a6a9`
- `ntdll!RtlEnterCriticalSection` at `0x18001a6a9`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18001a5c9`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18001a5c9`

## pseudocode

```c
__int64 KpsGPRead(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  int v9; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+3Ch] [rbp-CCh] BYREF
  int v11; // [rsp+40h] [rbp-C8h] BYREF
  int v12; // [rsp+44h] [rbp-C4h] BYREF
  int v13; // [rsp+48h] [rbp-C0h] BYREF
  int v14; // [rsp+4Ch] [rbp-BCh] BYREF
  int v15; // [rsp+50h] [rbp-B8h] BYREF
  int v16; // [rsp+54h] [rbp-B4h] BYREF
  int v17; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+5Ch] [rbp-ACh] BYREF
  int v19; // [rsp+60h] [rbp-A8h] BYREF
  int v20; // [rsp+64h] [rbp-A4h] BYREF
  int v21; // [rsp+68h] [rbp-A0h] BYREF
  int v22; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v23; // [rsp+70h] [rbp-98h] BYREF
  int v24; // [rsp+74h] [rbp-94h] BYREF
  int v25; // [rsp+78h] [rbp-90h] BYREF
  int v26; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v27; // [rsp+80h] [rbp-88h] BYREF
  int v28; // [rsp+84h] [rbp-84h] BYREF
  unsigned int v29; // [rsp+88h] [rbp-80h] BYREF
  void *lpMem[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int *v32; // [rsp+B0h] [rbp-58h]
  __int64 v33; // [rsp+B8h] [rbp-50h]
  __int64 (__usercall *v34)@<rax>(wchar_t *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, void *); // [rsp+C8h] [rbp-40h] BYREF
  int v35; // [rsp+D0h] [rbp-38h]
  const wchar_t *v36; // [rsp+D8h] [rbp-30h]
  void **v37; // [rsp+E0h] [rbp-28h]
  int v38; // [rsp+E8h] [rbp-20h]
  int *v39; // [rsp+F0h] [rbp-18h]
  int v40; // [rsp+F8h] [rbp-10h]
  __int64 v41; // [rsp+100h] [rbp-8h]
  int v42; // [rsp+108h] [rbp+0h]
  const wchar_t *v43; // [rsp+110h] [rbp+8h]
  int *v44; // [rsp+118h] [rbp+10h]
  int v45; // [rsp+120h] [rbp+18h]
  int *v46; // [rsp+128h] [rbp+20h]
  int v47; // [rsp+130h] [rbp+28h]
  __int64 v48; // [rsp+138h] [rbp+30h]
  int v49; // [rsp+140h] [rbp+38h]
  const wchar_t *v50; // [rsp+148h] [rbp+40h]
  int *v51; // [rsp+150h] [rbp+48h]
  int v52; // [rsp+158h] [rbp+50h]
  int *v53; // [rsp+160h] [rbp+58h]
  int v54; // [rsp+168h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+68h]
  int v56; // [rsp+178h] [rbp+70h]
  const wchar_t *v57; // [rsp+180h] [rbp+78h]
  int *v58; // [rsp+188h] [rbp+80h]
  int v59; // [rsp+190h] [rbp+88h]
  int *v60; // [rsp+198h] [rbp+90h]
  int v61; // [rsp+1A0h] [rbp+98h]
  __int64 v62; // [rsp+1A8h] [rbp+A0h]
  int v63; // [rsp+1B0h] [rbp+A8h]
  const wchar_t *v64; // [rsp+1B8h] [rbp+B0h]
  int *v65; // [rsp+1C0h] [rbp+B8h]
  int v66; // [rsp+1C8h] [rbp+C0h]
  int *v67; // [rsp+1D0h] [rbp+C8h]
  int v68; // [rsp+1D8h] [rbp+D0h]
  __int64 v69; // [rsp+1E0h] [rbp+D8h]
  int v70; // [rsp+1E8h] [rbp+E0h]
  const wchar_t *v71; // [rsp+1F0h] [rbp+E8h]
  unsigned int *v72; // [rsp+1F8h] [rbp+F0h]
  int v73; // [rsp+200h] [rbp+F8h]
  int *v74; // [rsp+208h] [rbp+100h]
  int v75; // [rsp+210h] [rbp+108h]
  __int64 v76; // [rsp+218h] [rbp+110h]
  int v77; // [rsp+220h] [rbp+118h]
  const wchar_t *v78; // [rsp+228h] [rbp+120h]
  int *v79; // [rsp+230h] [rbp+128h]
  int v80; // [rsp+238h] [rbp+130h]
  int *v81; // [rsp+240h] [rbp+138h]
  int v82; // [rsp+248h] [rbp+140h]
  __int64 v83; // [rsp+250h] [rbp+148h]
  int v84; // [rsp+258h] [rbp+150h]
  const wchar_t *v85; // [rsp+260h] [rbp+158h]
  int *v86; // [rsp+268h] [rbp+160h]
  int v87; // [rsp+270h] [rbp+168h]
  int *v88; // [rsp+278h] [rbp+170h]
  int v89; // [rsp+280h] [rbp+178h]
  __int64 v90; // [rsp+288h] [rbp+180h]
  int v91; // [rsp+290h] [rbp+188h]
  const wchar_t *v92; // [rsp+298h] [rbp+190h]
  int *v93; // [rsp+2A0h] [rbp+198h]
  int v94; // [rsp+2A8h] [rbp+1A0h]
  int *v95; // [rsp+2B0h] [rbp+1A8h]
  int v96; // [rsp+2B8h] [rbp+1B0h]
  __int64 v97; // [rsp+2C0h] [rbp+1B8h]
  int v98; // [rsp+2C8h] [rbp+1C0h]
  const wchar_t *v99; // [rsp+2D0h] [rbp+1C8h]
  int *v100; // [rsp+2D8h] [rbp+1D0h]
  int v101; // [rsp+2E0h] [rbp+1D8h]
  int *v102; // [rsp+2E8h] [rbp+1E0h]
  int v103; // [rsp+2F0h] [rbp+1E8h]
  __int64 v104; // [rsp+2F8h] [rbp+1F0h]
  int v105; // [rsp+300h] [rbp+1F8h]
  const wchar_t *v106; // [rsp+308h] [rbp+200h]
  int *v107; // [rsp+310h] [rbp+208h]
  int v108; // [rsp+318h] [rbp+210h]
  int *v109; // [rsp+320h] [rbp+218h]
  int v110; // [rsp+328h] [rbp+220h]
  __int64 v111; // [rsp+330h] [rbp+228h]
  int v112; // [rsp+338h] [rbp+230h]
  const wchar_t *v113; // [rsp+340h] [rbp+238h]
  unsigned int *v114; // [rsp+348h] [rbp+240h]
  int v115; // [rsp+350h] [rbp+248h]
  unsigned int *v116; // [rsp+358h] [rbp+250h]
  int v117; // [rsp+360h] [rbp+258h]
  __int128 v118; // [rsp+368h] [rbp+260h]
  __int128 v119; // [rsp+378h] [rbp+270h]
  __int128 v120; // [rsp+388h] [rbp+280h]
  __int64 v121; // [rsp+398h] [rbp+290h]

  v25 = 0x10000;
  v11 = 0;
  v26 = -1;
  v27 = -1;
  v12 = 0;
  v19 = 1;
  v20 = 1;
  v13 = 0;
  v34 = KpsGPQuery;
  v21 = 10;
  v36 = L"HttpsUrlGroup";
  v37 = lpMem;
  v39 = &dword_18003492C;
  v43 = L"HttpsClientAuth";
  v44 = &v11;
  v46 = &v19;
  v50 = L"DisallowUnprotectedPasswordAuth";
  v51 = &v12;
  v53 = &v20;
  v57 = L"MaximumPasswordPreauthFailure";
  v58 = &v13;
  v60 = &v21;
  v64 = L"PasswordPreauthFailureLockout";
  v65 = &v9;
  v67 = &v22;
  *(_OWORD *)lpMem = 0;
  v9 = 0;
  v31 = 0;
  v22 = 10;
  v10 = 0;
  v23 = 1;
  v14 = 0;
  v24 = 10;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v28 = 10000;
  v35 = 16;
  v38 = 7;
  v40 = 0;
  v41 = 0;
  v42 = 32;
  v45 = 4;
  v47 = 4;
  v48 = 0;
  v49 = 32;
  v52 = 4;
  v54 = 4;
  v55 = 0;
  v56 = 32;
  v59 = 4;
  v61 = 4;
  v62 = 0;
  v63 = 32;
  v66 = 4;
  v68 = 4;
  v69 = 0;
  v71 = L"RetryKdcConnection";
  v72 = &v10;
  v74 = &v23;
  v78 = L"RediscoverKdcTimeout";
  v79 = &v14;
  v81 = &v24;
  v85 = L"MaximumPayloadSize";
  v86 = &v15;
  v88 = &v25;
  v92 = L"MaximumBandwidth";
  v93 = &v16;
  v95 = &v26;
  v99 = L"MaximumConnections";
  v100 = &v17;
  v102 = &v27;
  v106 = L"SocketTimeout";
  v107 = &v18;
  v109 = &v28;
  v113 = L"KpsInfoLevel";
  v114 = &KpsInfoLevel;
  v116 = &KpsInfoLevel;
  v121 = 0;
  v70 = 32;
  v73 = 4;
  v75 = 4;
  v76 = 0;
  v77 = 32;
  v80 = 4;
  v82 = 4;
  v83 = 0;
  v84 = 32;
  v87 = 4;
  v89 = 4;
  v90 = 0;
  v91 = 32;
  v94 = 4;
  v96 = 4;
  v97 = 0;
  v98 = 32;
  v101 = 4;
  v103 = 4;
  v104 = 0;
  v105 = 32;
  v108 = 4;
  v110 = 4;
  v111 = 0;
  v112 = 32;
  v115 = 4;
  v117 = 4;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
  v0 = RtlQueryRegistryValuesEx(0x40000000, hKey, &v34, 0, 0);
  v1 = v0;
  if ( v0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 32;
LABEL_8:
      WPP_SF_D(v2[2], v3, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v0);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  v0 = KpsParseUrlPrefixList((struct _UNICODE_STRING *)lpMem, (struct _KPS_URL_PREFIX_LIST *)&v31);
  v1 = v0;
  if ( !v0 )
  {
    if ( !v9 )
    {
      v9 = 10;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_18;
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, 10);
    }
    v4 = WPP_GLOBAL_Control;
LABEL_18:
    if ( v10 > 0xA )
    {
      v10 = 1;
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        WPP_SF_D(v4[2], 35, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, 1);
    }
    RtlEnterCriticalSection(&stru_18003A958);
    KpsFreeUrlPrefixList((struct _KPS_URL_PREFIX_LIST *)&xmmword_18003A998);
    dword_18003A9A8 = v11;
    dword_18003A9AC = v12;
    dword_18003A9B0 = v13;
    dword_18003A9B4 = v9;
    dword_18003A9B8 = v10;
    dword_18003A9BC = v14;
    dword_18003A9C0 = v15;
    dword_18003A9C4 = v16;
    dword_18003A9C8 = v17;
    dword_18003A9CC = v18;
    xmmword_18003A998 = v31;
    v31 = 0;
    RtlLeaveCriticalSection(&stru_18003A958);
    goto LABEL_23;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = 33;
    goto LABEL_8;
  }
LABEL_23:
  KpsFreeUrlPrefixList((struct _KPS_URL_PREFIX_LIST *)&v31);
  KpsFreeMem(lpMem[1]);
  if ( v1 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
    {
      v29 = v1;
      v32 = &v29;
      v33 = 4;
      McGenEventWrite_EventWriteTransfer(v5, GPReadFailure, v6, 2, &v31);
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v1);
LABEL_34:
        v7 = WPP_GLOBAL_Control;
        goto LABEL_35;
      }
      goto LABEL_35;
    }
  }
  else
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
      McGenEventWrite_EventWriteTransfer(v5, GPReadSuccess, v6, 1, &v31);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
        goto LABEL_34;
      }
LABEL_35:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
        WPP_SF_D(v7[2], 38, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001a1e0  mov     rax, rsp
0x18001a1e3  mov     [rax+8], rbx
0x18001a1e7  mov     [rax+10h], rsi
0x18001a1eb  mov     [rax+18h], rdi
0x18001a1ef  push    rbp
0x18001a1f0  push    r12
0x18001a1f2  push    r13
0x18001a1f4  push    r14
0x18001a1f6  push    r15
0x18001a1f8  lea     rbp, [rax-2D8h]
0x18001a1ff  sub     rsp, 3B0h
0x18001a206  mov     rax, cs:__security_cookie
0x18001a20d  xor     rax, rsp
0x18001a210  mov     [rbp+2D0h+var_30], rax
0x18001a217  xor     r15d, r15d
0x18001a21a  mov     [rsp+3D0h+var_360], 10000h
0x18001a222  or      eax, 0FFFFFFFFh
0x18001a225  mov     [rsp+3D0h+var_398], r15d
0x18001a22a  mov     [rsp+3D0h+var_35C], eax
0x18001a22e  xorps   xmm0, xmm0
0x18001a231  mov     [rsp+3D0h+var_358], eax
0x18001a235  xorps   xmm1, xmm1
0x18001a238  lea     esi, [r15+1]
0x18001a23c  mov     [rsp+3D0h+var_394], r15d
0x18001a241  lea     ecx, [rsi+3]
0x18001a244  mov     [rsp+3D0h+var_378], esi
0x18001a248  lea     r12d, [r15+20h]
0x18001a24c  mov     [rsp+3D0h+var_374], esi
0x18001a250  lea     rax, ?KpsGPQuery@@YAJPEAGKPEAXK11@Z; KpsGPQuery(ushort *,ulong,void *,ulong,void *,void *)
0x18001a257  mov     [rsp+3D0h+var_390], r15d
0x18001a25c  mov     [rbp+2D0h+var_310], rax
0x18001a260  lea     r13d, [r15+0Ah]
0x18001a264  lea     rax, aHttpsurlgroup; "HttpsUrlGroup"
0x18001a26b  mov     [rsp+3D0h+var_370], r13d
0x18001a270  mov     [rbp+2D0h+var_300], rax
0x18001a274  lea     rax, [rbp+2D0h+lpMem]
0x18001a278  mov     [rbp+2D0h+var_2F8], rax
0x18001a27c  lea     rax, dword_18003492C
0x18001a283  mov     [rbp+2D0h+var_2E8], rax
0x18001a287  lea     rax, aHttpsclientaut; "HttpsClientAuth"
0x18001a28e  mov     [rbp+2D0h+var_2C8], rax
0x18001a292  lea     rax, [rsp+3D0h+var_398]
0x18001a297  mov     [rbp+2D0h+var_2C0], rax
0x18001a29b  lea     rax, [rsp+3D0h+var_378]
0x18001a2a0  mov     [rbp+2D0h+var_2B0], rax
0x18001a2a4  lea     rax, aDisallowunprot; "DisallowUnprotectedPasswordAuth"
0x18001a2ab  mov     [rbp+2D0h+var_290], rax
0x18001a2af  lea     rax, [rsp+3D0h+var_394]
0x18001a2b4  mov     [rbp+2D0h+var_288], rax
0x18001a2b8  lea     rax, [rsp+3D0h+var_374]
0x18001a2bd  mov     [rbp+2D0h+var_278], rax
0x18001a2c1  lea     rax, aMaximumpasswor; "MaximumPasswordPreauthFailure"
0x18001a2c8  mov     [rbp+2D0h+var_258], rax
0x18001a2cc  lea     rax, [rsp+3D0h+var_390]
0x18001a2d1  mov     [rbp+2D0h+var_250], rax
0x18001a2d8  lea     rax, [rsp+3D0h+var_370]
0x18001a2dd  mov     [rbp+2D0h+var_240], rax
0x18001a2e4  lea     rax, aPasswordpreaut; "PasswordPreauthFailureLockout"
0x18001a2eb  mov     [rbp+2D0h+var_220], rax
0x18001a2f2  lea     rax, [rsp+3D0h+var_3A0]
0x18001a2f7  mov     [rbp+2D0h+var_218], rax
0x18001a2fe  lea     rax, [rsp+3D0h+var_36C]
0x18001a303  mov     [rbp+2D0h+var_208], rax
0x18001a30a  movups  xmmword ptr [rbp+2D0h+lpMem], xmm0
0x18001a30e  mov     [rsp+3D0h+var_3A0], r15d
0x18001a313  movups  [rbp+2D0h+var_338], xmm1
0x18001a317  mov     [rsp+3D0h+var_36C], r13d
0x18001a31c  mov     [rsp+3D0h+var_39C], r15d
0x18001a321  mov     [rsp+3D0h+var_368], esi
0x18001a325  mov     [rsp+3D0h+var_38C], r15d
0x18001a32a  mov     [rsp+3D0h+var_364], r13d
0x18001a32f  mov     [rsp+3D0h+var_388], r15d
0x18001a334  mov     [rsp+3D0h+var_384], r15d
0x18001a339  mov     [rsp+3D0h+var_380], r15d
0x18001a33e  mov     [rsp+3D0h+var_37C], r15d
0x18001a343  mov     [rsp+3D0h+var_354], 2710h
0x18001a34b  mov     [rbp+2D0h+var_308], 10h
0x18001a352  mov     [rbp+2D0h+var_2F0], 7
0x18001a359  mov     [rbp+2D0h+var_2E0], r15d
0x18001a35d  mov     [rbp+2D0h+var_2D8], r15
0x18001a361  mov     [rbp+2D0h+var_2D0], r12d
0x18001a365  mov     [rbp+2D0h+var_2B8], ecx
0x18001a368  mov     [rbp+2D0h+var_2A8], ecx
0x18001a36b  mov     [rbp+2D0h+var_2A0], r15
0x18001a36f  mov     [rbp+2D0h+var_298], r12d
0x18001a373  mov     [rbp+2D0h+var_280], ecx
0x18001a376  mov     [rbp+2D0h+var_270], ecx
0x18001a379  mov     [rbp+2D0h+var_268], r15
0x18001a37d  mov     [rbp+2D0h+var_260], r12d
0x18001a381  mov     [rbp+2D0h+var_248], ecx
0x18001a387  mov     [rbp+2D0h+var_238], ecx
0x18001a38d  mov     [rbp+2D0h+var_230], r15
0x18001a394  mov     [rbp+2D0h+var_228], r12d
0x18001a39b  mov     [rbp+2D0h+var_210], ecx
0x18001a3a1  mov     [rbp+2D0h+var_200], ecx
0x18001a3a7  lea     rax, aRetrykdcconnec; "RetryKdcConnection"
0x18001a3ae  mov     [rbp+2D0h+var_1F8], r15
0x18001a3b5  mov     [rbp+2D0h+var_1E8], rax
0x18001a3bc  lea     rax, [rsp+3D0h+var_39C]
0x18001a3c1  mov     [rbp+2D0h+var_1E0], rax
0x18001a3c8  lea     rax, [rsp+3D0h+var_368]
0x18001a3cd  mov     [rbp+2D0h+var_1D0], rax
0x18001a3d4  lea     rax, aRediscoverkdct; "RediscoverKdcTimeout"
0x18001a3db  mov     [rbp+2D0h+var_1B0], rax
0x18001a3e2  lea     rax, [rsp+3D0h+var_38C]
0x18001a3e7  mov     [rbp+2D0h+var_1A8], rax
0x18001a3ee  lea     rax, [rsp+3D0h+var_364]
0x18001a3f3  mov     [rbp+2D0h+var_198], rax
0x18001a3fa  lea     rax, aMaximumpayload; "MaximumPayloadSize"
0x18001a401  mov     [rbp+2D0h+var_178], rax
0x18001a408  lea     rax, [rsp+3D0h+var_388]
0x18001a40d  mov     [rbp+2D0h+var_170], rax
0x18001a414  lea     rax, [rsp+3D0h+var_360]
0x18001a419  mov     [rbp+2D0h+var_160], rax
0x18001a420  lea     rax, aMaximumbandwid; "MaximumBandwidth"
0x18001a427  mov     [rbp+2D0h+var_140], rax
0x18001a42e  lea     rax, [rsp+3D0h+var_384]
0x18001a433  mov     [rbp+2D0h+var_138], rax
0x18001a43a  lea     rax, [rsp+3D0h+var_35C]
0x18001a43f  mov     [rbp+2D0h+var_128], rax
0x18001a446  lea     rax, aMaximumconnect; "MaximumConnections"
0x18001a44d  mov     [rbp+2D0h+var_108], rax
0x18001a454  lea     rax, [rsp+3D0h+var_380]
0x18001a459  mov     [rbp+2D0h+var_100], rax
0x18001a460  lea     rax, [rsp+3D0h+var_358]
0x18001a465  mov     [rbp+2D0h+var_F0], rax
0x18001a46c  lea     rax, aSockettimeout; "SocketTimeout"
0x18001a473  mov     [rbp+2D0h+var_D0], rax
0x18001a47a  lea     rax, [rsp+3D0h+var_37C]
0x18001a47f  mov     [rbp+2D0h+var_C8], rax
0x18001a486  lea     rax, [rsp+3D0h+var_354]
0x18001a48b  mov     [rbp+2D0h+var_B8], rax
0x18001a492  lea     rax, aKpsinfolevel; "KpsInfoLevel"
0x18001a499  mov     [rbp+2D0h+var_98], rax
0x18001a4a0  lea     rax, ?KpsInfoLevel@@3KA; ulong KpsInfoLevel
0x18001a4a7  mov     [rbp+2D0h+var_90], rax
0x18001a4ae  mov     [rbp+2D0h+var_80], rax
0x18001a4b5  xor     eax, eax
0x18001a4b7  mov     [rbp+2D0h+var_40], rax
0x18001a4be  mov     [rbp+2D0h+var_1F0], r12d
0x18001a4c5  mov     [rbp+2D0h+var_1D8], ecx
0x18001a4cb  mov     [rbp+2D0h+var_1C8], ecx
0x18001a4d1  mov     [rbp+2D0h+var_1C0], r15
0x18001a4d8  mov     [rbp+2D0h+var_1B8], r12d
0x18001a4df  mov     [rbp+2D0h+var_1A0], ecx
0x18001a4e5  mov     [rbp+2D0h+var_190], ecx
0x18001a4eb  mov     [rbp+2D0h+var_188], r15
0x18001a4f2  mov     [rbp+2D0h+var_180], r12d
0x18001a4f9  mov     [rbp+2D0h+var_168], ecx
0x18001a4ff  mov     [rbp+2D0h+var_158], ecx
0x18001a505  mov     [rbp+2D0h+var_150], r15
0x18001a50c  mov     [rbp+2D0h+var_148], r12d
0x18001a513  mov     [rbp+2D0h+var_130], ecx
0x18001a519  mov     [rbp+2D0h+var_120], ecx
0x18001a51f  mov     [rbp+2D0h+var_118], r15
0x18001a526  mov     [rbp+2D0h+var_110], r12d
0x18001a52d  mov     [rbp+2D0h+var_F8], ecx
0x18001a533  mov     [rbp+2D0h+var_E8], ecx
0x18001a539  mov     [rbp+2D0h+var_E0], r15
0x18001a540  mov     [rbp+2D0h+var_D8], r12d
0x18001a547  mov     [rbp+2D0h+var_C0], ecx
0x18001a54d  mov     [rbp+2D0h+var_B0], ecx
0x18001a553  mov     [rbp+2D0h+var_A8], r15
0x18001a55a  mov     [rbp+2D0h+var_A0], r12d
0x18001a561  mov     [rbp+2D0h+var_88], ecx
0x18001a567  mov     [rbp+2D0h+var_78], ecx
0x18001a56d  movups  [rbp+2D0h+var_70], xmm0
0x18001a574  movups  [rbp+2D0h+var_60], xmm0
0x18001a57b  movups  [rbp+2D0h+var_50], xmm0
0x18001a582  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a589  lea     r14, WPP_GLOBAL_Control
0x18001a590  lea     rdi, WPP_55dedb296c8337923463e18711d485b4_Traceguids
0x18001a597  cmp     rcx, r14
0x18001a59a  jz      short loc_18001A5B1
0x18001a59c  test    [rcx+1Ch], r12b
0x18001a5a0  jz      short loc_18001A5B1
0x18001a5a2  mov     rcx, [rcx+10h]
0x18001a5a6  lea     edx, [rsi+1Eh]
0x18001a5a9  mov     r8, rdi
0x18001a5ac  call    WPP_SF_
0x18001a5b1  mov     rdx, cs:hKey
0x18001a5b8  lea     r8, [rbp+2D0h+var_310]
0x18001a5bc  xor     r9d, r9d
0x18001a5bf  mov     [rsp+3D0h+var_3B0], r15
0x18001a5c4  mov     ecx, 40000000h
0x18001a5c9  call    cs:__imp_RtlQueryRegistryValuesEx
0x18001a5d0  nop     dword ptr [rax+rax+00h]
0x18001a5d5  mov     ebx, eax
0x18001a5d7  test    eax, eax
0x18001a5d9  jz      short loc_18001A60C
0x18001a5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5e2  cmp     rcx, r14
0x18001a5e5  jz      loc_18001A74B
0x18001a5eb  test    [rcx+1Ch], sil
0x18001a5ef  jz      loc_18001A74B
0x18001a5f5  mov     edx, r12d
0x18001a5f8  mov     rcx, [rcx+10h]
0x18001a5fc  mov     r9d, eax
0x18001a5ff  mov     r8, rdi
0x18001a602  call    WPP_SF_D
0x18001a607  jmp     loc_18001A74B
0x18001a60c  lea     rdx, [rbp+2D0h+var_338]; struct _KPS_URL_PREFIX_LIST *
0x18001a610  lea     rcx, [rbp+2D0h+lpMem]; struct _UNICODE_STRING *
0x18001a614  call    ?KpsParseUrlPrefixList@@YAKPEAU_UNICODE_STRING@@PEAU_KPS_URL_PREFIX_LIST@@@Z; KpsParseUrlPrefixList(_UNICODE_STRING *,_KPS_URL_PREFIX_LIST *)
0x18001a619  mov     ebx, eax
0x18001a61b  test    eax, eax
0x18001a61d  jz      short loc_18001A640
0x18001a61f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a626  cmp     rcx, r14
0x18001a629  jz      loc_18001A74B
0x18001a62f  test    [rcx+1Ch], sil
0x18001a633  jz      loc_18001A74B
0x18001a639  mov     edx, 21h ; '!'
0x18001a63e  jmp     short loc_18001A5F8
0x18001a640  cmp     [rsp+3D0h+var_3A0], esi
0x18001a644  jnb     short loc_18001A671
0x18001a646  mov     [rsp+3D0h+var_3A0], r13d
0x18001a64b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a652  cmp     rcx, r14
0x18001a655  jz      short loc_18001A678
0x18001a657  test    byte ptr [rcx+1Ch], 2
0x18001a65b  jz      short loc_18001A678
0x18001a65d  mov     rcx, [rcx+10h]
0x18001a661  mov     edx, 22h ; '"'
0x18001a666  mov     r9d, r13d
0x18001a669  mov     r8, rdi
0x18001a66c  call    WPP_SF_D
0x18001a671  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a678  cmp     [rsp+3D0h+var_39C], r13d
0x18001a67d  jbe     short loc_18001A6A2
0x18001a67f  mov     [rsp+3D0h+var_39C], esi
0x18001a683  cmp     rcx, r14
0x18001a686  jz      short loc_18001A6A2
0x18001a688  test    byte ptr [rcx+1Ch], 2
0x18001a68c  jz      short loc_18001A6A2
0x18001a68e  mov     rcx, [rcx+10h]
0x18001a692  mov     edx, 23h ; '#'
0x18001a697  mov     r9d, esi
0x18001a69a  mov     r8, rdi
0x18001a69d  call    WPP_SF_D
0x18001a6a2  lea     rcx, stru_18003A958; CriticalSection
0x18001a6a9  call    cs:__imp_RtlEnterCriticalSection
0x18001a6b0  nop     dword ptr [rax+rax+00h]
0x18001a6b5  lea     rcx, xmmword_18003A998; struct _KPS_URL_PREFIX_LIST *
0x18001a6bc  call    ?KpsFreeUrlPrefixList@@YAXPEAU_KPS_URL_PREFIX_LIST@@@Z; KpsFreeUrlPrefixList(_KPS_URL_PREFIX_LIST *)
0x18001a6c1  mov     eax, [rsp+3D0h+var_398]
0x18001a6c5  lea     rcx, stru_18003A958; CriticalSection
0x18001a6cc  movups  xmm0, [rbp+2D0h+var_338]
0x18001a6d0  mov     cs:dword_18003A9A8, eax
0x18001a6d6  mov     eax, [rsp+3D0h+var_394]
0x18001a6da  xorps   xmm1, xmm1
0x18001a6dd  mov     cs:dword_18003A9AC, eax
0x18001a6e3  mov     eax, [rsp+3D0h+var_390]
0x18001a6e7  mov     cs:dword_18003A9B0, eax
0x18001a6ed  mov     eax, [rsp+3D0h+var_3A0]
0x18001a6f1  mov     cs:dword_18003A9B4, eax
0x18001a6f7  mov     eax, [rsp+3D0h+var_39C]
0x18001a6fb  mov     cs:dword_18003A9B8, eax
0x18001a701  mov     eax, [rsp+3D0h+var_38C]
0x18001a705  mov     cs:dword_18003A9BC, eax
0x18001a70b  mov     eax, [rsp+3D0h+var_388]
0x18001a70f  mov     cs:dword_18003A9C0, eax
0x18001a715  mov     eax, [rsp+3D0h+var_384]
0x18001a719  mov     cs:dword_18003A9C4, eax
0x18001a71f  mov     eax, [rsp+3D0h+var_380]
0x18001a723  mov     cs:dword_18003A9C8, eax
0x18001a729  mov     eax, [rsp+3D0h+var_37C]
0x18001a72d  mov     cs:dword_18003A9CC, eax
0x18001a733  movdqu  cs:xmmword_18003A998, xmm0
0x18001a73b  movups  [rbp+2D0h+var_338], xmm1
0x18001a73f  call    cs:__imp_RtlLeaveCriticalSection
0x18001a746  nop     dword ptr [rax+rax+00h]
0x18001a74b  lea     rcx, [rbp+2D0h+var_338]; struct _KPS_URL_PREFIX_LIST *
0x18001a74f  call    ?KpsFreeUrlPrefixList@@YAXPEAU_KPS_URL_PREFIX_LIST@@@Z; KpsFreeUrlPrefixList(_KPS_URL_PREFIX_LIST *)
0x18001a754  mov     rcx, [rbp+2D0h+lpMem+8]; lpMem
0x18001a758  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18001a75d  test    ebx, ebx
0x18001a75f  jz      short loc_18001A7C4
0x18001a761  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, sil
0x18001a768  jz      short loc_18001A798
0x18001a76a  lea     rax, [rbp+2D0h+var_350]
0x18001a76e  mov     [rbp+2D0h+var_350], ebx
0x18001a771  mov     [rbp+2D0h+var_328], rax
0x18001a775  lea     rdx, GPReadFailure
0x18001a77c  lea     rax, [rbp+2D0h+var_338]
0x18001a780  mov     [rbp+2D0h+var_320], 4
0x18001a788  mov     r9d, 2
0x18001a78e  mov     [rsp+3D0h+var_3B0], rax
0x18001a793  call    McGenEventWrite_EventWriteTransfer
0x18001a798  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a79f  cmp     rcx, r14
0x18001a7a2  jz      loc_18001A82E
0x18001a7a8  test    byte ptr [rcx+1Ch], 10h
0x18001a7ac  jz      short loc_18001A80F
0x18001a7ae  mov     rcx, [rcx+10h]
0x18001a7b2  mov     edx, 24h ; '$'
0x18001a7b7  mov     r9d, ebx
0x18001a7ba  mov     r8, rdi
0x18001a7bd  call    WPP_SF_D
0x18001a7c2  jmp     short loc_18001A808
  ... truncated ...
```

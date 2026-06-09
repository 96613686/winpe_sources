# Dhcpv6QueryLeaseInfo

- ea: `0x180001010`
- end: `0x1800016e5`
- name: `Dhcpv6QueryLeaseInfo`
- size: `1749`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001d30`
- `0x180001e70`
- `0x180001ff0`
- `0x1800025e0`
- `0x180002650`
- `0x180002680`
- `0x180003a90`
- `0x1800042fe`
- `0x1800072fc`
- `0x180007891`
- `0x1800081c0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000791e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000791e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001123`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001189`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800011b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001123`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180001189`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800011b8`

## pseudocode

```c
__int64 __fastcall Dhcpv6QueryLeaseInfo(void *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _OWORD *v5; // rsi
  unsigned int LeaseInfov6; // edi
  int v7; // ecx
  LPWSTR CommandLineW; // rax
  int v9; // ecx
  LPWSTR v10; // rax
  int v11; // ecx
  int v12; // r8d
  char v13; // dl
  unsigned int v14; // r8d
  __int64 v15; // rcx
  _OWORD *v16; // rax
  void *v17; // rax
  void *v18; // rax
  SIZE_T v19; // rcx
  void *v20; // rax
  unsigned __int16 v21; // di
  LPVOID v22; // rax
  unsigned __int16 i; // r12
  __int64 v24; // rdi
  _BYTE *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  size_t v28; // r13
  char *v29; // rcx
  int v30; // ecx
  int v31; // eax
  bool v32; // zf
  int v34; // [rsp+40h] [rbp-228h] BYREF
  unsigned __int16 v35; // [rsp+48h] [rbp-220h]
  unsigned int v36; // [rsp+50h] [rbp-218h]
  void *Src[2]; // [rsp+58h] [rbp-210h] BYREF
  void *v38[2]; // [rsp+68h] [rbp-200h] BYREF
  NET_LUID v39; // [rsp+78h] [rbp-1F0h] BYREF
  _BYTE v40[3]; // [rsp+80h] [rbp-1E8h] BYREF
  char v41; // [rsp+83h] [rbp-1E5h]
  int v42; // [rsp+84h] [rbp-1E4h]
  int v43; // [rsp+88h] [rbp-1E0h]
  int v44; // [rsp+A0h] [rbp-1C8h]
  void **v45; // [rsp+A8h] [rbp-1C0h] BYREF
  unsigned int v46; // [rsp+B0h] [rbp-1B8h]
  void *v47[3]; // [rsp+B8h] [rbp-1B0h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-198h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-188h]
  __int128 v50; // [rsp+F0h] [rbp-178h]
  _OWORD v51[4]; // [rsp+100h] [rbp-168h]
  __int128 v52; // [rsp+140h] [rbp-128h]
  __m256i v53; // [rsp+150h] [rbp-118h]
  __int128 v54; // [rsp+170h] [rbp-F8h]
  _BYTE v55[24]; // [rsp+180h] [rbp-E8h]
  _DWORD v56[20]; // [rsp+1A0h] [rbp-C8h] BYREF
  __int16 v57; // [rsp+1F0h] [rbp-78h]
  char v58; // [rsp+1F4h] [rbp-74h]
  __int32 v59; // [rsp+1F8h] [rbp-70h]
  __int128 v60; // [rsp+1FCh] [rbp-6Ch]
  __int64 v61; // [rsp+20Ch] [rbp-5Ch]
  unsigned int v62; // [rsp+214h] [rbp-54h]
  unsigned int v63; // [rsp+218h] [rbp-50h]
  char v64; // [rsp+21Ch] [rbp-4Ch]
  __int128 v65; // [rsp+21Dh] [rbp-4Bh]

  v47[1] = a1;
  v47[2] = a2;
  memset_0(v56, 0, 0x90u);
  memset_0(&v48, 0, 0xC8u);
  *(_OWORD *)v38 = 0;
  *(_OWORD *)Src = 0;
  memset_0(v40, 0, 0x40u);
  v5 = 0;
  v39.Value = 0;
  v34 = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(v4, 51, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    LeaseInfov6 = 87;
    goto LABEL_54;
  }
  LeaseInfov6 = Dhcpv6AdapterNameToIfId((const WCHAR *)a1, &v39);
  if ( !LeaseInfov6 )
  {
    if ( !a2 )
    {
      LeaseInfov6 = 87;
      goto LABEL_54;
    }
    if ( *a2 )
    {
      LeaseInfov6 = 87;
      goto LABEL_54;
    }
    if ( (xmmword_18000F160 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_SS(
        v9,
        52,
        (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
        (_DWORD)a1,
        (__int64)CommandLineW);
    }
    LeaseInfov6 = RpcCliQueryLeaseInfov6(
                    v7,
                    (unsigned int)&v39,
                    (unsigned int)v56,
                    (unsigned int)v38,
                    (__int64)Src,
                    (__int64)v40,
                    (__int64)&v34);
    v36 = LeaseInfov6;
    if ( (xmmword_18000F160 & 0x10) != 0 )
    {
      v10 = GetCommandLineW();
      WPP_SF_DSS(v11, 53, v12, LeaseInfov6, (__int64)a1, (__int64)v10);
    }
    if ( !LeaseInfov6 )
    {
      BYTE8(v52) = v58;
      v13 = v64;
      v55[0] = v64;
      LODWORD(v48) = v56[0];
      *(_OWORD *)&v55[1] = v65;
      if ( v58 )
      {
        DWORD2(v48) = v56[1];
        *(_QWORD *)&v49 = v56[2];
        *((_QWORD *)&v49 + 1) = v56[3];
        LOWORD(v52) = v57;
        v14 = 0;
        if ( v57 )
        {
          do
          {
            v15 = 40LL * v14;
            *(__m128i *)((char *)v51 + v15 + 8) = _mm_unpacklo_epi32(
                                                    _mm_loadl_epi64((const __m128i *)&v56[8 * v14 + 10]),
                                                    (__m128i)0LL);
            *(_DWORD *)((char *)v51 + v15) = v56[8 * v14 + 8];
            *(_DWORD *)((char *)v51 + v15 + 4) = v56[8 * v14 + 9];
            *(_OWORD *)((char *)&v51[-1] + v15) = *(_OWORD *)&v56[8 * v14++ + 4];
          }
          while ( v14 < (unsigned __int16)v52 );
          v13 = v55[0];
        }
      }
      if ( v13 )
      {
        v53.m256i_i32[0] = v59;
        *((_QWORD *)&v54 + 1) = v63;
        *(_QWORD *)&v54 = v62;
        v53.m256i_i64[3] = v61;
        *(_OWORD *)&v53.m256i_u64[1] = v60;
      }
      v16 = DhcpAlloc(0x130u);
      v5 = v16;
      if ( !v16 )
      {
LABEL_24:
        LeaseInfov6 = 8;
        goto LABEL_54;
      }
      *v16 = v48;
      v16[1] = v49;
      v16[2] = v50;
      v16[3] = v51[0];
      v16[4] = v51[1];
      v16[5] = v51[2];
      v16[6] = v51[3];
      v16[7] = v52;
      *((__m256i *)v16 + 4) = v53;
      v16[10] = v54;
      v16[11] = *(_OWORD *)v55;
      *((_QWORD *)v16 + 24) = *(_QWORD *)&v55[16];
      if ( LOWORD(Src[0]) )
      {
        *((_WORD *)v16 + 104) = Src[0];
        v17 = DhcpAlloc(LOWORD(Src[0]));
        *((_QWORD *)v5 + 25) = v17;
        if ( !v17 )
        {
          LeaseInfov6 = 8;
          goto LABEL_54;
        }
        memcpy_0(v17, Src[1], LOWORD(Src[0]));
      }
      if ( LOWORD(v38[0]) )
      {
        *((_WORD *)v5 + 112) = v38[0];
        v18 = DhcpAlloc(LOWORD(v38[0]));
        *((_QWORD *)v5 + 27) = v18;
        if ( !v18 )
        {
          LeaseInfov6 = 8;
          goto LABEL_54;
        }
        memcpy_0(v18, v38[1], LOWORD(v38[0]));
      }
      *((_DWORD *)v5 + 60) = v43;
      *((_DWORD *)v5 + 59) = v42;
      if ( v41 )
      {
        v19 = 16 * v46;
        if ( (unsigned int)v19 < v46 )
        {
          LeaseInfov6 = 87;
          goto LABEL_54;
        }
        v20 = DhcpAlloc(v19);
        *((_QWORD *)v5 + 36) = v20;
        if ( !v20 )
        {
          LeaseInfov6 = 8;
          goto LABEL_54;
        }
        memcpy_0(v20, v47[0], 16LL * v46);
        *((_DWORD *)v5 + 70) = v46;
        *((_BYTE *)v5 + 235) = v41;
      }
      if ( v40[2] )
      {
        v21 = v44;
        v35 = v44;
        v22 = DhcpAlloc(8LL * (unsigned __int16)v44);
        *((_QWORD *)v5 + 34) = v22;
        if ( !v22 )
        {
          LeaseInfov6 = 8;
          goto LABEL_54;
        }
        for ( i = 0; i < v21; ++i )
        {
          v24 = i;
          v25 = v45[v24];
          if ( !v25 )
            goto LABEL_49;
          v26 = 256;
          do
          {
            if ( !*v25 )
              break;
            ++v25;
            --v26;
          }
          while ( v26 );
          v27 = 256 - v26;
          if ( !v26 )
LABEL_49:
            v27 = 0;
          v28 = v27 + 1;
          *(_QWORD *)(v24 * 8 + *((_QWORD *)v5 + 34)) = DhcpAlloc(v27 + 1);
          v29 = *(char **)(v24 * 8 + *((_QWORD *)v5 + 34));
          if ( !v29 )
            goto LABEL_24;
          StringCchCopyA(v29, v28, (STRSAFE_LPCSTR)v45[v24]);
          v21 = v35;
        }
        *((_DWORD *)v5 + 66) = v21;
        *((_BYTE *)v5 + 234) = 1;
      }
      *((_DWORD *)v5 + 74) = v34;
      *a2 = v5;
      v5 = 0;
      LeaseInfov6 = 0;
    }
  }
LABEL_54:
  Dhcpv6FreeLeaseInfo(v5);
  if ( v41 )
    DhcpMidlUserFree(v47);
  v31 = v44;
  if ( v44 )
  {
    do
    {
      DhcpMidlUserFree(&v45[v31]);
      v32 = v44 == 1;
      v31 = --v44;
    }
    while ( !v32 );
    DhcpMidlUserFree((void **)&v45);
  }
  if ( LOWORD(Src[0]) )
    DhcpMidlUserFree(&Src[1]);
  if ( LOWORD(v38[0]) )
    DhcpMidlUserFree(&v38[1]);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v30, 54, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, LeaseInfov6);
  return LeaseInfov6;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_10], rbx
0x180001015  mov     [rsp+arg_18], rsi
0x18000101a  push    rdi
0x18000101b  push    r12
0x18000101d  push    r13
0x18000101f  push    r14
0x180001021  push    r15
0x180001023  sub     rsp, 240h
0x18000102a  mov     rax, cs:__security_cookie
0x180001031  xor     rax, rsp
0x180001034  mov     [rsp+268h+var_38], rax
0x18000103c  mov     rbx, rdx
0x18000103f  mov     r14, rcx
0x180001042  mov     [rsp+268h+var_1A8], rcx
0x18000104a  mov     [rsp+268h+var_1A0], rdx
0x180001052  xor     edx, edx; Val
0x180001054  mov     r8d, 90h; Size
0x18000105a  lea     rcx, [rsp+268h+var_C8]; void *
0x180001062  call    memset_0
0x180001067  xor     edx, edx; Val
0x180001069  mov     r8d, 0C8h; Size
0x18000106f  lea     rcx, [rsp+268h+var_198]; void *
0x180001077  call    memset_0
0x18000107c  xorps   xmm0, xmm0
0x18000107f  movups  xmmword ptr [rsp+268h+var_200], xmm0
0x180001084  xorps   xmm1, xmm1
0x180001087  movups  xmmword ptr [rsp+268h+Src], xmm1
0x18000108c  xor     edx, edx; Val
0x18000108e  mov     r8d, 40h ; '@'; Size
0x180001094  lea     rcx, [rsp+268h+var_1E8]; void *
0x18000109c  call    memset_0
0x1800010a1  xor     r15d, r15d
0x1800010a4  mov     esi, r15d
0x1800010a7  mov     [rsp+268h+var_1F0], r15
0x1800010ac  mov     [rsp+268h+var_228], r15d
0x1800010b1  test    byte ptr cs:xmmword_18000F160, 10h
0x1800010b8  jz      short loc_1800010CE
0x1800010ba  mov     edx, 33h ; '3'
0x1800010bf  mov     r9, r14
0x1800010c2  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800010c9  call    WPP_SF_S
0x1800010ce  test    rbx, rbx
0x1800010d1  jz      short loc_1800010D6
0x1800010d3  mov     [rbx], r15
0x1800010d6  test    r14, r14
0x1800010d9  jnz     short loc_1800010E5
0x1800010db  mov     edi, 57h ; 'W'
0x1800010e0  jmp     loc_180001614
0x1800010e5  lea     rdx, [rsp+268h+var_1F0]
0x1800010ea  mov     rcx, r14
0x1800010ed  call    Dhcpv6AdapterNameToIfId
0x1800010f2  mov     edi, eax
0x1800010f4  test    eax, eax
0x1800010f6  jnz     loc_180001614
0x1800010fc  test    rbx, rbx
0x1800010ff  jnz     short loc_18000110B
0x180001101  mov     edi, 57h ; 'W'
0x180001106  jmp     loc_180001614
0x18000110b  cmp     [rbx], r15
0x18000110e  jz      short loc_18000111A
0x180001110  mov     edi, 57h ; 'W'
0x180001115  jmp     loc_180001614
0x18000111a  test    byte ptr cs:xmmword_18000F160, 10h
0x180001121  jz      short loc_180001143
0x180001123  call    cs:__imp_GetCommandLineW
0x180001129  mov     edx, 34h ; '4'
0x18000112e  mov     [rsp+268h+var_248], rax
0x180001133  mov     r9, r14
0x180001136  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000113d  call    WPP_SF_SS
0x180001142  nop
0x180001143  lea     rax, [rsp+268h+var_228]
0x180001148  mov     [rsp+268h+var_238], rax
0x18000114d  lea     rax, [rsp+268h+var_1E8]
0x180001155  mov     [rsp+268h+var_240], rax
0x18000115a  lea     rax, [rsp+268h+Src]
0x18000115f  mov     [rsp+268h+var_248], rax
0x180001164  lea     r9, [rsp+268h+var_200]
0x180001169  lea     r8, [rsp+268h+var_C8]
0x180001171  lea     rdx, [rsp+268h+var_1F0]
0x180001176  call    RpcCliQueryLeaseInfov6
0x18000117b  mov     edi, eax
0x18000117d  mov     [rsp+268h+var_218], eax
0x180001181  jmp     short loc_1800011AF
0x180001183  mov     edi, eax
0x180001185  mov     [rsp+268h+var_218], eax
0x180001189  call    cs:__imp_GetCommandLineW
0x18000118f  mov     rdx, rax
0x180001192  mov     ecx, edi
0x180001194  call    TraceRpcException
0x180001199  xor     r15d, r15d
0x18000119c  mov     esi, r15d
0x18000119f  mov     r14, [rsp+268h+var_1A8]
0x1800011a7  mov     rbx, [rsp+268h+var_1A0]
0x1800011af  test    byte ptr cs:xmmword_18000F160, 10h
0x1800011b6  jz      short loc_1800011D5
0x1800011b8  call    cs:__imp_GetCommandLineW
0x1800011be  mov     edx, 35h ; '5'
0x1800011c3  mov     [rsp+268h+var_240], rax
0x1800011c8  mov     [rsp+268h+var_248], r14
0x1800011cd  mov     r9d, edi
0x1800011d0  call    WPP_SF_DSS
0x1800011d5  test    edi, edi
0x1800011d7  jnz     loc_180001614
0x1800011dd  movzx   ecx, [rsp+268h+var_74]
0x1800011e5  mov     byte ptr [rsp+268h+var_128+8], cl
0x1800011ec  movzx   edx, [rsp+268h+var_4C]
0x1800011f4  mov     byte ptr [rsp+268h+var_E8], dl
0x1800011fb  mov     eax, [rsp+268h+var_C8]
0x180001202  mov     dword ptr [rsp+268h+var_198], eax
0x180001209  movups  xmm0, [rsp+268h+var_4B]
0x180001211  movups  [rsp+268h+var_E8+1], xmm0
0x180001219  test    cl, cl
0x18000121b  jz      loc_1800012D9
0x180001221  mov     eax, [rsp+268h+var_C4]
0x180001228  mov     dword ptr [rsp+268h+var_198+8], eax
0x18000122f  mov     eax, [rsp+268h+var_C0]
0x180001236  mov     qword ptr [rsp+268h+var_188], rax
0x18000123e  mov     eax, [rsp+268h+var_BC]
0x180001245  mov     qword ptr [rsp+268h+var_188+8], rax
0x18000124d  movzx   eax, [rsp+268h+var_78]
0x180001255  mov     word ptr [rsp+268h+var_128], ax
0x18000125d  mov     r8d, r15d
0x180001260  cmp     r15w, ax
0x180001264  jnb     short loc_1800012D9
0x180001266  mov     eax, r8d
0x180001269  mov     edx, r8d
0x18000126c  shl     rdx, 5
0x180001270  lea     rax, [rax+rax*4]
0x180001274  lea     rcx, ds:0[rax*8]
0x18000127c  movq    xmm1, [rsp+rdx+268h+var_A0]
0x180001285  xorps   xmm0, xmm0
0x180001288  punpckldq xmm1, xmm0
0x18000128c  movdqu  [rsp+rcx+268h+var_168+8], xmm1
0x180001295  mov     eax, [rsp+rdx+268h+var_A8]
0x18000129c  mov     dword ptr [rsp+rcx+268h+var_168], eax
0x1800012a3  mov     eax, [rsp+rdx+268h+var_A4]
0x1800012aa  mov     dword ptr [rsp+rcx+268h+var_168+4], eax
0x1800012b1  movups  xmm0, [rsp+rdx+268h+var_B8]
0x1800012b9  movups  [rsp+rcx+268h+var_178], xmm0
0x1800012c1  inc     r8d
0x1800012c4  movzx   eax, word ptr [rsp+268h+var_128]
0x1800012cc  cmp     r8d, eax
0x1800012cf  jb      short loc_180001266
0x1800012d1  movzx   edx, byte ptr [rsp+268h+var_E8]
0x1800012d9  test    dl, dl
0x1800012db  jz      short loc_180001335
0x1800012dd  mov     eax, [rsp+268h+var_70]
0x1800012e4  mov     dword ptr [rsp+268h+var_118], eax
0x1800012eb  mov     eax, [rsp+268h+var_50]
0x1800012f2  mov     qword ptr [rsp+268h+var_F8+8], rax
0x1800012fa  mov     eax, [rsp+268h+var_54]
0x180001301  mov     qword ptr [rsp+268h+var_F8], rax
0x180001309  mov     eax, [rsp+268h+var_5C]
0x180001310  mov     [rsp+268h+var_100], eax
0x180001317  mov     eax, [rsp+268h+var_58]
0x18000131e  mov     [rsp+268h+var_FC], eax
0x180001325  movups  xmm0, [rsp+268h+var_6C]
0x18000132d  movups  [rsp+268h+var_118+8], xmm0
0x180001335  mov     ecx, 130h
0x18000133a  call    DhcpAlloc
0x18000133f  mov     rsi, rax
0x180001342  test    rax, rax
0x180001345  jnz     short loc_180001351
0x180001347  mov     edi, 8
0x18000134c  jmp     loc_180001614
0x180001351  movaps  xmm0, [rsp+268h+var_198]
0x180001359  movups  xmmword ptr [rax], xmm0
0x18000135c  movaps  xmm1, [rsp+268h+var_188]
0x180001364  movups  xmmword ptr [rax+10h], xmm1
0x180001368  movaps  xmm0, [rsp+268h+var_178]
0x180001370  movups  xmmword ptr [rax+20h], xmm0
0x180001374  movaps  xmm1, [rsp+268h+var_168]
0x18000137c  movups  xmmword ptr [rax+30h], xmm1
0x180001380  movaps  xmm0, [rsp+268h+var_158]
0x180001388  movups  xmmword ptr [rax+40h], xmm0
0x18000138c  movaps  xmm1, [rsp+268h+var_148]
0x180001394  movups  xmmword ptr [rax+50h], xmm1
0x180001398  movaps  xmm0, [rsp+268h+var_138]
0x1800013a0  movups  xmmword ptr [rax+60h], xmm0
0x1800013a4  movaps  xmm1, [rsp+268h+var_128]
0x1800013ac  movups  xmmword ptr [rax+70h], xmm1
0x1800013b0  movaps  xmm0, [rsp+268h+var_118]
0x1800013b8  movups  xmmword ptr [rax+80h], xmm0
0x1800013bf  movaps  xmm1, xmmword ptr [rsp+160h]
0x1800013c7  movups  xmmword ptr [rax+90h], xmm1
0x1800013ce  movaps  xmm0, [rsp+268h+var_F8]
0x1800013d6  movups  xmmword ptr [rax+0A0h], xmm0
0x1800013dd  movaps  xmm1, [rsp+268h+var_E8]
0x1800013e5  movups  xmmword ptr [rax+0B0h], xmm1
0x1800013ec  mov     rax, [rsp+268h+var_D8]
0x1800013f4  mov     [rsi+0C0h], rax
0x1800013fb  movzx   eax, word ptr [rsp+268h+Src]
0x180001400  test    ax, ax
0x180001403  jz      short loc_18000143F
0x180001405  mov     [rsi+0D0h], ax
0x18000140c  movzx   ecx, word ptr [rsp+268h+Src]
0x180001411  call    DhcpAlloc
0x180001416  mov     [rsi+0C8h], rax
0x18000141d  test    rax, rax
0x180001420  jnz     short loc_18000142C
0x180001422  mov     edi, 8
0x180001427  jmp     loc_180001614
0x18000142c  movzx   r8d, word ptr [rsp+268h+Src]; Size
0x180001432  mov     rdx, [rsp+268h+Src+8]; Src
0x180001437  mov     rcx, rax; void *
0x18000143a  call    memcpy_0
0x18000143f  movzx   eax, word ptr [rsp+268h+var_200]
0x180001444  test    ax, ax
0x180001447  jz      short loc_180001483
0x180001449  mov     [rsi+0E0h], ax
0x180001450  movzx   ecx, word ptr [rsp+268h+var_200]
0x180001455  call    DhcpAlloc
0x18000145a  mov     [rsi+0D8h], rax
0x180001461  test    rax, rax
0x180001464  jnz     short loc_180001470
0x180001466  mov     edi, 8
0x18000146b  jmp     loc_180001614
0x180001470  movzx   r8d, word ptr [rsp+268h+var_200]; Size
0x180001476  mov     rdx, [rsp+268h+var_200+8]; Src
0x18000147b  mov     rcx, rax; void *
0x18000147e  call    memcpy_0
0x180001483  mov     eax, [rsp+268h+var_1E0]
0x18000148a  mov     [rsi+0F0h], eax
0x180001490  mov     eax, [rsp+268h+var_1E4]
0x180001497  mov     [rsi+0ECh], eax
0x18000149d  cmp     [rsp+268h+var_1E5], 0
0x1800014a5  jz      short loc_180001516
0x1800014a7  mov     ecx, [rsp+268h+var_1B8]
0x1800014ae  shl     ecx, 4
0x1800014b1  cmp     ecx, [rsp+268h+var_1B8]
0x1800014b8  jnb     short loc_1800014C4
0x1800014ba  mov     edi, 57h ; 'W'
0x1800014bf  jmp     loc_180001614
0x1800014c4  call    DhcpAlloc
0x1800014c9  mov     [rsi+120h], rax
0x1800014d0  test    rax, rax
0x1800014d3  jnz     short loc_1800014DF
0x1800014d5  mov     edi, 8
0x1800014da  jmp     loc_180001614
0x1800014df  mov     r8d, [rsp+268h+var_1B8]
0x1800014e7  shl     r8, 4; Size
0x1800014eb  mov     rdx, [rsp+268h+var_1B0]; Src
0x1800014f3  mov     rcx, rax; void *
0x1800014f6  call    memcpy_0
0x1800014fb  mov     eax, [rsp+268h+var_1B8]
0x180001502  mov     [rsi+118h], eax
0x180001508  movzx   eax, [rsp+268h+var_1E5]
0x180001510  mov     [rsi+0EBh], al
0x180001516  cmp     [rsp+268h+var_1E6], 0
0x18000151e  jz      loc_180001601
0x180001524  movzx   edi, word ptr [rsp+268h+var_1C8]
0x18000152c  mov     [rsp+268h+var_220], di
0x180001531  mov     ecx, edi
0x180001533  shl     rcx, 3
0x180001537  call    DhcpAlloc
0x18000153c  mov     [rsi+110h], rax
0x180001543  test    rax, rax
0x180001546  jnz     short loc_180001552
0x180001548  mov     edi, 8
0x18000154d  jmp     loc_180001614
0x180001552  movzx   r12d, r15w
0x180001556  cmp     r12w, di
0x18000155a  jnb     loc_1800015F1
0x180001560  movzx   eax, r12w
0x180001564  lea     rdi, ds:0[rax*8]
0x18000156c  mov     rax, [rsp+268h+var_1C0]
0x180001574  mov     rcx, [rdi+rax]
0x180001578  test    rcx, rcx
0x18000157b  jz      short loc_1800015A1
0x18000157d  mov     eax, 100h
0x180001582  cmp     byte ptr [rcx], 0
0x180001585  jz      short loc_180001590
0x180001587  inc     rcx
0x18000158a  sub     rax, 1
0x18000158e  jnz     short loc_180001582
0x180001590  mov     ecx, 100h
0x180001595  sub     rcx, rax
0x180001598  test    rax, rax
0x18000159b  cmovz   rcx, r15
0x18000159f  jnz     short loc_1800015A4
0x1800015a1  mov     rcx, r15
0x1800015a4  lea     r13, [rcx+1]
0x1800015a8  mov     rcx, r13
0x1800015ab  call    DhcpAlloc
0x1800015b0  mov     rcx, [rsi+110h]
0x1800015b7  mov     [rdi+rcx], rax
0x1800015bb  mov     rax, [rsi+110h]
0x1800015c2  mov     rcx, [rdi+rax]; pszDest
0x1800015c6  test    rcx, rcx
0x1800015c9  jz      loc_180001347
0x1800015cf  mov     r8, [rsp+268h+var_1C0]
0x1800015d7  mov     r8, [rdi+r8]; pszSrc
0x1800015db  mov     rdx, r13; cchDest
0x1800015de  call    StringCchCopyA
0x1800015e3  inc     r12w
0x1800015e7  movzx   edi, [rsp+268h+var_220]
0x1800015ec  jmp     loc_180001556
0x1800015f1  movzx   eax, di
0x1800015f4  mov     [rsi+108h], eax
  ... truncated ...
```

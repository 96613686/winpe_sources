# myOpenCertStores(ulong,ulong *,void * * *,ushort const * * *)

- ea: `0x180018d44`
- end: `0x180019122`
- name: `?myOpenCertStores@@YAJKPEAKPEAPEAPEAXPEAPEAPEBG@Z`
- size: `990`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, void ***, const unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018310`

## callees

- `0x180015c0c`
- `0x180017e6c`
- `0x180018d44`
- `0x18001a8a4`
- `0x18001caf0`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018db9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019061`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019061`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190e4`
- `CRYPT32!CertOpenStore` at `0x180018e7a`
- `CRYPT32!CertOpenStore` at `0x180018ef3`
- `CRYPT32!CertOpenStore` at `0x180018e7a`
- `CRYPT32!CertOpenStore` at `0x180018ef3`
- `CRYPT32!CertSetStoreProperty` at `0x18001903d`
- `CRYPT32!CertSetStoreProperty` at `0x18001903d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018f96`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800190d0`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018f96`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800190d0`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018e9c`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018f15`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018fd4`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180019058`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018e9c`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018f15`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018fd4`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180019058`

## pseudocode

```c
__int64 __fastcall myOpenCertStores(int a1, unsigned int *a2, void ***a3, const unsigned __int16 ***a4)
{
  unsigned __int16 *v5; // r15
  void **v6; // r12
  int v7; // edx
  const unsigned __int16 **v8; // r14
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  unsigned int v11; // esi
  int v12; // ecx
  int v13; // edx
  struct _STOREMAP near **v14; // rdi
  int v15; // r13d
  HCERTSTORE v16; // rax
  unsigned int v17; // r15d
  __int64 v18; // rcx
  HCERTSTORE v19; // rax
  unsigned int v20; // r15d
  __int64 v21; // rcx
  unsigned int v22; // r15d
  int v23; // eax
  unsigned int v24; // ecx
  HINSTANCE v25; // rcx
  void *v26; // r13
  unsigned int v27; // r15d
  unsigned __int16 *ResourceStringNoCache; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // ecx
  int v35; // [rsp+30h] [rbp-30h]
  int v36; // [rsp+34h] [rbp-2Ch]
  __int128 pvData; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-10h] BYREF
  BSTR v40; // [rsp+58h] [rbp-8h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = 0;
  bstrString = 0;
  v40 = 0;
  hMem = 0;
  *(_QWORD *)&pvData = 0;
  *a4 = 0;
  v6 = (void **)LocalAlloc(0, 0x78u);
  if ( !v6 )
  {
    v7 = -2147024882;
    v8 = 0;
    v9 = -2147024882;
    v10 = 19399067;
LABEL_55:
    CSPrintErrorLineFile(v10, v7);
    goto LABEL_56;
  }
  v8 = (const unsigned __int16 **)LocalAlloc(0, 0x78u);
  if ( !v8 )
  {
    v7 = -2147024882;
    v10 = 19923355;
    v9 = -2147024882;
    goto LABEL_55;
  }
  v9 = 0;
  if ( (a1 & 0x7001F) == 0 )
    goto LABEL_52;
  if ( (a1 & 0x1C8FFE0) != 0 )
  {
    v9 = -2147024809;
    v10 = 20840859;
LABEL_54:
    v7 = v9;
    goto LABEL_55;
  }
  v11 = 0;
  v12 = a1 | 0x70000;
  v13 = a1 & 0x10000000;
  v35 = a1 & 0x10000000;
  if ( (a1 & 0x70000) != 0 )
    v12 = a1;
  v14 = &s_aStoreMap;
  v15 = v12 | 1;
  if ( (v12 & 0x1F) != 0 )
    v15 = v12;
  v36 = v15;
  while ( v14[1] )
  {
    if ( (v15 & *(_DWORD *)v14) == 0 )
      goto LABEL_37;
    if ( (v15 & 0x10000) != 0 )
    {
      v16 = CertOpenStore((LPCSTR)0xA, 1u, 0, v13 != 0 ? 164354 : 163842, v14[1]);
      if ( v16 )
      {
        v13 = v35;
        v18 = v11++;
        v6[v18] = v16;
        v8[v18] = (const unsigned __int16 *)v14[3];
      }
      else
      {
        v17 = myHLastError();
        CSPrintErrorLineFileData((const unsigned __int16 *)v14[1], 0x15A019Bu, v17);
        v13 = v35;
        if ( !v9 )
          v9 = v17;
      }
    }
    if ( (v15 & 0x20000) != 0 )
    {
      v19 = CertOpenStore((LPCSTR)0xA, 1u, 0, v13 != 0 ? 98818 : 98306, v14[1]);
      if ( v19 )
      {
        v21 = v11++;
        v6[v21] = v19;
        v8[v21] = (const unsigned __int16 *)v14[2];
      }
      else
      {
        v20 = myHLastError();
        CSPrintErrorLineFileData((const unsigned __int16 *)v14[1], 0x177019Bu, v20);
        if ( !v9 )
          v9 = v20;
      }
    }
    if ( (v15 & 0x40000) == 0 || !v14[5] )
      goto LABEL_35;
    if ( *(_DWORD *)v14 == 2 )
    {
      v22 = 1008;
    }
    else
    {
      v22 = 0;
      if ( *(_DWORD *)v14 == 4 )
        v22 = 1007;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    v23 = FormatDSStoreName(&bstrString, &v40, (const unsigned __int16 *)v14[5], (unsigned __int16 **)&hMem);
    if ( v23 )
    {
      CSPrintErrorLineFile(0x1A9019Bu, v23);
LABEL_35:
      v13 = v35;
LABEL_36:
      v5 = (unsigned __int16 *)pvData;
      goto LABEL_37;
    }
    v26 = myUrlCertOpenStore(v24, (const unsigned __int16 *)hMem);
    if ( !v26 )
    {
      v27 = myHLastError();
      CSPrintErrorLineFileData((const unsigned __int16 *)hMem, 0x1B4019Bu, v27);
      v15 = v36;
      v13 = v35;
      if ( !v9 )
        v9 = v27;
      goto LABEL_36;
    }
    ResourceStringNoCache = myLoadResourceStringNoCache(v25, v22);
    *(_QWORD *)&pvData = ResourceStringNoCache;
    v5 = ResourceStringNoCache;
    if ( ResourceStringNoCache )
    {
      v29 = -1;
      pvData = 0;
      do
        ++v29;
      while ( ResourceStringNoCache[v29] );
      v30 = 2 * v29 + 2;
      if ( v30 > 0x10000 )
      {
        v9 = -2147024362;
        v10 = 29753755;
        goto LABEL_54;
      }
      LODWORD(pvData) = v30;
      *((_QWORD *)&pvData + 1) = ResourceStringNoCache;
      if ( !CertSetStoreProperty(v26, 0x1000u, 0, &pvData) )
      {
        v31 = myHLastError();
        CSPrintErrorLineFileData((const unsigned __int16 *)hMem, 0x1D2019Bu, v31);
      }
      LocalFree(v5);
      v5 = 0;
      *(_QWORD *)&pvData = 0;
    }
    v13 = v35;
    v32 = v11++;
    v6[v32] = v26;
    v15 = v36;
    v8[v32] = (const unsigned __int16 *)v14[4];
LABEL_37:
    v14 += 6;
  }
  if ( !v11 )
  {
LABEL_52:
    v10 = 32440731;
    if ( !v9 )
      v9 = -2147024894;
    goto LABEL_54;
  }
  v9 = 0;
  *a2 = v11;
  *a3 = v6;
  v6 = 0;
  *a4 = v8;
  v8 = 0;
LABEL_56:
  SysFreeString(bstrString);
  SysFreeString(v40);
  LocalFree(hMem);
  LocalFree(v5);
  myCloseCertStores(v33, v6, v8);
  return v9;
}

```

## disassembly

```asm
0x180018d44  mov     rax, rsp
0x180018d47  mov     [rax+8], rbx
0x180018d4b  mov     [rax+20h], r9
0x180018d4f  mov     [rax+18h], r8
0x180018d53  mov     [rax+10h], rdx
0x180018d57  push    rbp
0x180018d58  push    rsi
0x180018d59  push    rdi
0x180018d5a  push    r12
0x180018d5c  push    r13
0x180018d5e  push    r14
0x180018d60  push    r15
0x180018d62  mov     rbp, rsp
0x180018d65  sub     rsp, 60h
0x180018d69  xor     r13d, r13d
0x180018d6c  mov     edi, ecx
0x180018d6e  mov     [rdx], r13d
0x180018d71  xor     ecx, ecx; uFlags
0x180018d73  mov     [r8], r13
0x180018d76  mov     r15d, r13d
0x180018d79  mov     [rbp+bstrString], r13
0x180018d7d  lea     ebx, [r13+78h]
0x180018d81  mov     [rbp+var_8], r13
0x180018d85  mov     edx, ebx; uBytes
0x180018d87  mov     [rbp+hMem], r13
0x180018d8b  mov     qword ptr [rbp+pvData], r13
0x180018d8f  mov     [r9], r13
0x180018d92  call    cs:__imp_LocalAlloc
0x180018d98  mov     r12, rax
0x180018d9b  test    rax, rax
0x180018d9e  jnz     short loc_180018DB4
0x180018da0  mov     edx, 8007000Eh
0x180018da5  mov     r14d, r13d
0x180018da8  mov     ebx, edx
0x180018daa  mov     ecx, 128019Bh
0x180018daf  jmp     loc_1800190D0
0x180018db4  mov     rdx, rbx; uBytes
0x180018db7  xor     ecx, ecx; uFlags
0x180018db9  call    cs:__imp_LocalAlloc
0x180018dbf  mov     r14, rax
0x180018dc2  test    rax, rax
0x180018dc5  jnz     short loc_180018DD8
0x180018dc7  mov     edx, 8007000Eh
0x180018dcc  mov     ecx, 130019Bh
0x180018dd1  mov     ebx, edx
0x180018dd3  jmp     loc_1800190D0
0x180018dd8  mov     ebx, r13d
0x180018ddb  test    edi, 7001Fh
0x180018de1  jz      loc_1800190BF
0x180018de7  test    edi, 1C8FFE0h
0x180018ded  jz      short loc_180018DFE
0x180018def  mov     ebx, 80070057h
0x180018df4  mov     ecx, 13E019Bh
0x180018df9  jmp     loc_1800190CE
0x180018dfe  mov     r8d, 70000h
0x180018e04  mov     esi, r13d
0x180018e07  mov     edx, edi
0x180018e09  mov     ecx, edi
0x180018e0b  or      ecx, r8d
0x180018e0e  and     edx, 10000000h
0x180018e14  test    r8d, edi
0x180018e17  mov     [rbp+var_30], edx
0x180018e1a  cmovnz  ecx, edi
0x180018e1d  xor     r8d, r8d
0x180018e20  mov     r13d, ecx
0x180018e23  lea     rdi, ?s_aStoreMap@@3PAU_STOREMAP@@A; _STOREMAP near * s_aStoreMap
0x180018e2a  or      r13d, 1
0x180018e2e  test    cl, 1Fh
0x180018e31  cmovnz  r13d, ecx
0x180018e35  mov     [rbp+var_2C], r13d
0x180018e39  mov     rcx, [rdi+8]
0x180018e3d  test    rcx, rcx
0x180018e40  jz      loc_180019099
0x180018e46  test    [rdi], r13d
0x180018e49  jz      loc_180018FA6
0x180018e4f  bt      r13d, 10h
0x180018e54  jnb     short loc_180018EC4
0x180018e56  mov     eax, edx
0x180018e58  mov     [rsp+60h+pvPara], rcx; pvPara
0x180018e5d  neg     eax
0x180018e5f  sbb     r9d, r9d
0x180018e62  xor     r8d, r8d; hCryptProv
0x180018e65  and     r9d, 200h
0x180018e6c  add     r9d, 28002h; dwFlags
0x180018e73  lea     edx, [r8+1]; dwEncodingType
0x180018e77  lea     ecx, [rdx+9]; lpszStoreProvider
0x180018e7a  call    cs:__imp_CertOpenStore
0x180018e80  xor     r8d, r8d
0x180018e83  test    rax, rax
0x180018e86  jnz     short loc_180018EB1
0x180018e88  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018e8d  mov     rcx, [rdi+8]
0x180018e91  mov     r8d, eax
0x180018e94  mov     edx, 15A019Bh
0x180018e99  mov     r15d, eax
0x180018e9c  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018ea2  mov     edx, [rbp+var_30]
0x180018ea5  xor     r8d, r8d
0x180018ea8  test    ebx, ebx
0x180018eaa  jnz     short loc_180018EC4
0x180018eac  mov     ebx, r15d
0x180018eaf  jmp     short loc_180018EC4
0x180018eb1  mov     edx, [rbp+var_30]
0x180018eb4  mov     ecx, esi
0x180018eb6  inc     esi
0x180018eb8  mov     [r12+rcx*8], rax
0x180018ebc  mov     rax, [rdi+18h]
0x180018ec0  mov     [r14+rcx*8], rax
0x180018ec4  bt      r13d, 11h
0x180018ec9  jnb     short loc_180018F37
0x180018ecb  mov     eax, edx
0x180018ecd  neg     eax
0x180018ecf  mov     rax, [rdi+8]
0x180018ed3  sbb     r9d, r9d
0x180018ed6  mov     [rsp+60h+pvPara], rax; pvPara
0x180018edb  xor     r8d, r8d; hCryptProv
0x180018ede  and     r9d, 200h
0x180018ee5  add     r9d, 18002h; dwFlags
0x180018eec  lea     edx, [r8+1]; dwEncodingType
0x180018ef0  lea     ecx, [rdx+9]; lpszStoreProvider
0x180018ef3  call    cs:__imp_CertOpenStore
0x180018ef9  xor     r8d, r8d
0x180018efc  test    rax, rax
0x180018eff  jnz     short loc_180018F27
0x180018f01  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018f06  mov     rcx, [rdi+8]
0x180018f0a  mov     r8d, eax
0x180018f0d  mov     edx, 177019Bh
0x180018f12  mov     r15d, eax
0x180018f15  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018f1b  xor     r8d, r8d
0x180018f1e  test    ebx, ebx
0x180018f20  jnz     short loc_180018F37
0x180018f22  mov     ebx, r15d
0x180018f25  jmp     short loc_180018F37
0x180018f27  mov     ecx, esi
0x180018f29  inc     esi
0x180018f2b  mov     [r12+rcx*8], rax
0x180018f2f  mov     rax, [rdi+10h]
0x180018f33  mov     [r14+rcx*8], rax
0x180018f37  bt      r13d, 12h
0x180018f3c  jnb     short loc_180018F9F
0x180018f3e  cmp     [rdi+28h], r8
0x180018f42  jz      short loc_180018F9F
0x180018f44  cmp     dword ptr [rdi], 2
0x180018f47  jz      short loc_180018F59
0x180018f49  cmp     dword ptr [rdi], 4
0x180018f4c  mov     r15d, r8d
0x180018f4f  jnz     short loc_180018F5F
0x180018f51  mov     r15d, 3EFh
0x180018f57  jmp     short loc_180018F5F
0x180018f59  mov     r15d, 3F0h
0x180018f5f  mov     rcx, [rbp+hMem]; hMem
0x180018f63  test    rcx, rcx
0x180018f66  jz      short loc_180018F76
0x180018f68  call    cs:__imp_LocalFree
0x180018f6e  mov     [rbp+hMem], 0
0x180018f76  mov     r8, [rdi+28h]; unsigned __int16 *
0x180018f7a  lea     r9, [rbp+hMem]; unsigned __int16 **
0x180018f7e  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x180018f82  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x180018f86  call    ?FormatDSStoreName@@YAJPEAPEAG0PEBG0@Z; FormatDSStoreName(ushort * *,ushort * *,ushort const *,ushort * *)
0x180018f8b  test    eax, eax
0x180018f8d  jz      short loc_180018FAF
0x180018f8f  mov     edx, eax
0x180018f91  mov     ecx, 1A9019Bh
0x180018f96  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180018f9c  xor     r8d, r8d
0x180018f9f  mov     edx, [rbp+var_30]
0x180018fa2  mov     r15, qword ptr [rbp+pvData]
0x180018fa6  add     rdi, 30h ; '0'
0x180018faa  jmp     loc_180018E39
0x180018faf  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x180018fb3  call    ?myUrlCertOpenStore@@YAPEAXKPEBG@Z; myUrlCertOpenStore(ulong,ushort const *)
0x180018fb8  mov     r13, rax
0x180018fbb  test    rax, rax
0x180018fbe  jnz     short loc_180018FED
0x180018fc0  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018fc5  mov     rcx, [rbp+hMem]
0x180018fc9  mov     r8d, eax
0x180018fcc  mov     edx, 1B4019Bh
0x180018fd1  mov     r15d, eax
0x180018fd4  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018fda  mov     r13d, [rbp+var_2C]
0x180018fde  xor     r8d, r8d
0x180018fe1  mov     edx, [rbp+var_30]
0x180018fe4  test    ebx, ebx
0x180018fe6  jnz     short loc_180018FA2
0x180018fe8  mov     ebx, r15d
0x180018feb  jmp     short loc_180018FA2
0x180018fed  mov     edx, r15d; unsigned int
0x180018ff0  call    ?myLoadResourceStringNoCache@@YAPEAGPEAUHINSTANCE__@@K@Z; myLoadResourceStringNoCache(HINSTANCE__ *,ulong)
0x180018ff5  xor     r8d, r8d; dwFlags
0x180018ff8  mov     qword ptr [rbp+pvData], rax
0x180018ffc  mov     r15, rax
0x180018fff  test    rax, rax
0x180019002  jz      short loc_180019071
0x180019004  xorps   xmm0, xmm0
0x180019007  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001900b  movups  [rbp+pvData], xmm0
0x18001900f  inc     rcx
0x180019012  cmp     [rax+rcx*2], r8w
0x180019017  jnz     short loc_18001900F
0x180019019  lea     rcx, ds:2[rcx*2]
0x180019021  cmp     rcx, 10000h
0x180019028  ja      short loc_18001908D
0x18001902a  mov     dword ptr [rbp+pvData], ecx
0x18001902d  lea     r9, [rbp+pvData]; pvData
0x180019031  mov     rcx, r13; hCertStore
0x180019034  mov     qword ptr [rbp+pvData+8], r15
0x180019038  mov     edx, 1000h; dwPropId
0x18001903d  call    cs:__imp_CertSetStoreProperty
0x180019043  test    eax, eax
0x180019045  jnz     short loc_18001905E
0x180019047  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001904c  mov     rcx, [rbp+hMem]
0x180019050  mov     r8d, eax
0x180019053  mov     edx, 1D2019Bh
0x180019058  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001905e  mov     rcx, r15; hMem
0x180019061  call    cs:__imp_LocalFree
0x180019067  xor     r8d, r8d
0x18001906a  mov     r15d, r8d
0x18001906d  mov     qword ptr [rbp+pvData], r8
0x180019071  mov     edx, [rbp+var_30]
0x180019074  mov     ecx, esi
0x180019076  inc     esi
0x180019078  mov     [r12+rcx*8], r13
0x18001907c  mov     rax, [rdi+20h]
0x180019080  mov     r13d, [rbp+var_2C]
0x180019084  mov     [r14+rcx*8], rax
0x180019088  jmp     loc_180018FA6
0x18001908d  mov     ebx, 80070216h
0x180019092  mov     ecx, 1C6019Bh
0x180019097  jmp     short loc_1800190CE
0x180019099  xor     r13d, r13d
0x18001909c  test    esi, esi
0x18001909e  jz      short loc_1800190BF
0x1800190a0  mov     rax, [rbp+arg_8]
0x1800190a4  mov     ebx, r13d
0x1800190a7  mov     [rax], esi
0x1800190a9  mov     rax, [rbp+arg_10]
0x1800190ad  mov     [rax], r12
0x1800190b0  mov     r12d, r13d
0x1800190b3  mov     rax, [rbp+arg_18]
0x1800190b7  mov     [rax], r14
0x1800190ba  mov     r14d, r13d
0x1800190bd  jmp     short loc_1800190D6
0x1800190bf  test    ebx, ebx
0x1800190c1  mov     eax, 80070002h
0x1800190c6  mov     ecx, 1EF019Bh
0x1800190cb  cmovz   ebx, eax
0x1800190ce  mov     edx, ebx
0x1800190d0  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800190d6  mov     rcx, [rbp+bstrString]; bstrString
0x1800190da  call    cs:__imp_SysFreeString
0x1800190e0  mov     rcx, [rbp+var_8]; bstrString
0x1800190e4  call    cs:__imp_SysFreeString
0x1800190ea  mov     rcx, [rbp+hMem]; hMem
0x1800190ee  call    cs:__imp_LocalFree
0x1800190f4  mov     rcx, r15; hMem
0x1800190f7  call    cs:__imp_LocalFree
0x1800190fd  mov     r8, r14; unsigned __int16 **
0x180019100  mov     rdx, r12; void **
0x180019103  call    ?myCloseCertStores@@YAXKPEAPEAXPEAPEBG@Z; myCloseCertStores(ulong,void * *,ushort const * *)
0x180019108  mov     eax, ebx
0x18001910a  mov     rbx, [rsp+60h+arg_0]
0x180019112  add     rsp, 60h
0x180019116  pop     r15
0x180019118  pop     r14
0x18001911a  pop     r13
0x18001911c  pop     r12
0x18001911e  pop     rdi
0x18001911f  pop     rsi
0x180019120  pop     rbp
0x180019121  retn
```

# TlmiLogHydrationAborted

- ea: `0x180019ed8`
- end: `0x18001a302`
- name: `TlmiLogHydrationAborted`
- size: `1066`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012c28`

## callees

- `0x180001078`
- `0x180001aa0`
- `0x180019ed8`
- `0x18001ae98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2c4`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019f68`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019f68`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f3e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f3e`
- `AEPIC!PicFreeFileInfo` at `0x18001a2da`
- `AEPIC!PicFreeFileInfo` at `0x18001a2da`
- `AEPIC!PicRetrieveFileInfo` at `0x180019f8d`
- `AEPIC!PicRetrieveFileInfo` at `0x180019f8d`

## pseudocode

```c
void __fastcall TlmiLogHydrationAborted(__int64 a1)
{
  HANDLE v2; // rax
  void *v3; // rdi
  int v4; // ecx
  __int64 v5; // rax
  const WCHAR *v6; // r8
  __int64 v7; // rdx
  int v8; // edx
  const WCHAR *v9; // rdx
  __int64 v10; // r8
  int v11; // r8d
  const WCHAR *v12; // rdx
  __int64 v13; // r8
  int v14; // r8d
  const WCHAR *v15; // rdx
  __int64 v16; // r8
  int v17; // r8d
  const WCHAR *v18; // rdx
  __int64 v19; // r8
  int v20; // r8d
  const WCHAR *v21; // rdx
  __int64 v22; // r8
  int v23; // r8d
  const WCHAR *v24; // rdx
  __int64 v25; // r8
  int v26; // r8d
  const WCHAR *v27; // rdx
  __int64 v28; // r8
  int v29; // r8d
  const WCHAR *v30; // rdx
  __int64 v31; // r8
  int v32; // r8d
  const WCHAR *v33; // rdx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh] BYREF
  const WCHAR **v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  _DWORD *v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  WCHAR *v46; // [rsp+A0h] [rbp-60h]
  _DWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v48; // [rsp+B0h] [rbp-50h]
  int v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+BCh] [rbp-44h]
  const WCHAR *v51; // [rsp+C0h] [rbp-40h]
  int v52; // [rsp+C8h] [rbp-38h]
  int v53; // [rsp+CCh] [rbp-34h]
  const WCHAR *v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+DCh] [rbp-24h]
  const WCHAR *v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  int v59; // [rsp+ECh] [rbp-14h]
  const WCHAR *v60; // [rsp+F0h] [rbp-10h]
  int v61; // [rsp+F8h] [rbp-8h]
  int v62; // [rsp+FCh] [rbp-4h]
  const WCHAR *v63; // [rsp+100h] [rbp+0h]
  int v64; // [rsp+108h] [rbp+8h]
  int v65; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v66; // [rsp+110h] [rbp+10h]
  int v67; // [rsp+118h] [rbp+18h]
  int v68; // [rsp+11Ch] [rbp+1Ch]
  const WCHAR *v69; // [rsp+120h] [rbp+20h]
  int v70; // [rsp+128h] [rbp+28h]
  int v71; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v72; // [rsp+130h] [rbp+30h]
  int v73; // [rsp+138h] [rbp+38h]
  int v74; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v75; // [rsp+140h] [rbp+40h]
  int v76; // [rsp+148h] [rbp+48h]
  int v77; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v78; // [rsp+150h] [rbp+50h]
  __int64 v79; // [rsp+158h] [rbp+58h]
  __int64 *v80; // [rsp+160h] [rbp+60h]
  __int64 v81; // [rsp+168h] [rbp+68h]
  int *v82; // [rsp+170h] [rbp+70h]
  __int64 v83; // [rsp+178h] [rbp+78h]
  __int64 *v84; // [rsp+180h] [rbp+80h]
  __int64 v85; // [rsp+188h] [rbp+88h]
  WCHAR ExeName[264]; // [rsp+190h] [rbp+90h] BYREF

  dwSize = 261;
  v36 = 0;
  if ( byte_18002A930 && !NtCurrentPeb()->Ldr->ShutdownInProgress )
  {
    v2 = OpenProcess(0x1000u, 0, *(_DWORD *)(a1 + 16));
    v3 = v2;
    if ( v2 )
    {
      if ( QueryFullProcessImageNameW(v2, 1u, ExeName, &dwSize) )
      {
        if ( (int)PicRetrieveFileInfo(ExeName, 256, &v36) >= 0 )
        {
          TlmiRemoveUsername(ExeName);
          if ( (unsigned int)dword_18002A1A0 > 5
            && (qword_18002A1B0 & 0x400000000000LL) != 0
            && (qword_18002A1B8 & 0x400000000000LL) == qword_18002A1B8 )
          {
            v4 = 2;
            v37 = *(int *)(a1 + 20);
            v42 = &v37;
            v44 = v47;
            v46 = ExeName;
            v43 = 8;
            v47[0] = 2 * (unsigned __int16)dwSize;
            v5 = -1;
            v45 = 2;
            v47[1] = 0;
            v6 = v36[9];
            if ( v6 )
            {
              v7 = -1;
              do
                ++v7;
              while ( v6[v7] );
              v8 = 2 * v7 + 2;
            }
            else
            {
              v6 = &SourceString;
              v8 = 2;
            }
            v48 = v6;
            v49 = v8;
            v50 = 0;
            v9 = v36[4];
            if ( v9 )
            {
              v10 = -1;
              do
                ++v10;
              while ( v9[v10] );
              v11 = 2 * v10 + 2;
            }
            else
            {
              v9 = &SourceString;
              v11 = 2;
            }
            v51 = v9;
            v52 = v11;
            v53 = 0;
            v12 = v36[7];
            if ( v12 )
            {
              v13 = -1;
              do
                ++v13;
              while ( v12[v13] );
              v14 = 2 * v13 + 2;
            }
            else
            {
              v12 = &SourceString;
              v14 = 2;
            }
            v54 = v12;
            v55 = v14;
            v56 = 0;
            v15 = v36[2];
            if ( v15 )
            {
              v16 = -1;
              do
                ++v16;
              while ( v15[v16] );
              v17 = 2 * v16 + 2;
            }
            else
            {
              v15 = &SourceString;
              v17 = 2;
            }
            v57 = v15;
            v58 = v17;
            v59 = 0;
            v18 = *v36;
            if ( *v36 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
              v20 = 2 * v19 + 2;
            }
            else
            {
              v18 = &SourceString;
              v20 = 2;
            }
            v60 = v18;
            v61 = v20;
            v62 = 0;
            v21 = v36[3];
            if ( v21 )
            {
              v22 = -1;
              do
                ++v22;
              while ( v21[v22] );
              v23 = 2 * v22 + 2;
            }
            else
            {
              v21 = &SourceString;
              v23 = 2;
            }
            v63 = v21;
            v64 = v23;
            v65 = 0;
            v24 = v36[6];
            if ( v24 )
            {
              v25 = -1;
              do
                ++v25;
              while ( v24[v25] );
              v26 = 2 * v25 + 2;
            }
            else
            {
              v24 = &SourceString;
              v26 = 2;
            }
            v66 = v24;
            v67 = v26;
            v68 = 0;
            v27 = v36[8];
            if ( v27 )
            {
              v28 = -1;
              do
                ++v28;
              while ( v27[v28] );
              v29 = 2 * v28 + 2;
            }
            else
            {
              v27 = &SourceString;
              v29 = 2;
            }
            v69 = v27;
            v70 = v29;
            v71 = 0;
            v30 = v36[1];
            if ( v30 )
            {
              v31 = -1;
              do
                ++v31;
              while ( v30[v31] );
              v32 = 2 * v31 + 2;
            }
            else
            {
              v30 = &SourceString;
              v32 = 2;
            }
            v72 = v30;
            v73 = v32;
            v74 = 0;
            v33 = v36[5];
            if ( v33 )
            {
              do
                ++v5;
              while ( v33[v5] );
              v4 = 2 * v5 + 2;
            }
            else
            {
              v33 = &SourceString;
            }
            v38 = (unsigned int)dword_18002AB78;
            v75 = v33;
            v78 = &v38;
            v39 = qword_18002AB70;
            v80 = &v39;
            v35 = dword_18002AB7C;
            v82 = &v35;
            v84 = &v40;
            v76 = v4;
            v77 = 0;
            v79 = 8;
            v81 = 8;
            v83 = 4;
            v40 = 0x1000000;
            v85 = 8;
            tlgWriteTransfer_EventWriteTransfer(
              (__int64)&dword_18002A1A0,
              (unsigned __int8 *)byte_18002398F,
              0,
              0,
              0x13u,
              &v41);
          }
        }
      }
      CloseHandle(v3);
    }
    if ( v36 )
      PicFreeFileInfo();
  }
}

```

## disassembly

```asm
0x180019ed8  push    rbp
0x180019eda  push    rbx
0x180019edb  push    rsi
0x180019edc  push    rdi
0x180019edd  lea     rbp, [rsp-2B8h]
0x180019ee5  sub     rsp, 3B8h
0x180019eec  mov     rax, cs:__security_cookie
0x180019ef3  xor     rax, rsp
0x180019ef6  mov     [rbp+2D0h+var_30], rax
0x180019efd  xor     esi, esi
0x180019eff  mov     [rsp+3D0h+dwSize], 105h
0x180019f07  cmp     cs:byte_18002A930, sil
0x180019f0e  mov     rbx, rcx
0x180019f11  mov     [rsp+3D0h+var_398], rsi
0x180019f16  jz      loc_18001A2E6
0x180019f1c  mov     rax, gs:60h
0x180019f25  mov     rdx, [rax+18h]
0x180019f29  cmp     [rdx+48h], sil
0x180019f2d  jnz     loc_18001A2E6
0x180019f33  mov     r8d, [rcx+10h]; dwProcessId
0x180019f37  xor     edx, edx; bInheritHandle
0x180019f39  mov     ecx, 1000h; dwDesiredAccess
0x180019f3e  call    cs:__imp_OpenProcess
0x180019f45  nop     dword ptr [rax+rax+00h]
0x180019f4a  mov     rdi, rax
0x180019f4d  test    rax, rax
0x180019f50  jz      loc_18001A2D0
0x180019f56  lea     r9, [rsp+3D0h+dwSize]; lpdwSize
0x180019f5b  mov     rcx, rax; hProcess
0x180019f5e  lea     r8, [rbp+2D0h+ExeName]; lpExeName
0x180019f65  lea     edx, [rsi+1]; dwFlags
0x180019f68  call    cs:__imp_QueryFullProcessImageNameW
0x180019f6f  nop     dword ptr [rax+rax+00h]
0x180019f74  test    eax, eax
0x180019f76  jz      loc_18001A2C1
0x180019f7c  lea     r8, [rsp+3D0h+var_398]
0x180019f81  mov     edx, 100h
0x180019f86  lea     rcx, [rbp+2D0h+ExeName]
0x180019f8d  call    cs:__imp_PicRetrieveFileInfo
0x180019f94  nop     dword ptr [rax+rax+00h]
0x180019f99  test    eax, eax
0x180019f9b  js      loc_18001A2C1
0x180019fa1  movzx   edx, word ptr [rsp+3D0h+dwSize]
0x180019fa6  lea     rcx, [rbp+2D0h+ExeName]
0x180019fad  add     dx, dx
0x180019fb0  call    TlmiRemoveUsername
0x180019fb5  mov     eax, cs:dword_18002A1A0
0x180019fbb  cmp     eax, 5
0x180019fbe  jbe     loc_18001A2C1
0x180019fc4  mov     rcx, cs:qword_18002A1B8
0x180019fcb  mov     rdx, 400000000000h
0x180019fd5  mov     rax, cs:qword_18002A1B0
0x180019fdc  test    rdx, rax
0x180019fdf  jz      loc_18001A2C1
0x180019fe5  mov     rax, rcx
0x180019fe8  and     rax, rdx
0x180019feb  cmp     rax, rcx
0x180019fee  jnz     loc_18001A2C1
0x180019ff4  movsxd  rax, dword ptr [rbx+14h]
0x180019ff8  lea     ecx, [rsi+2]
0x180019ffb  mov     r9, [rsp+3D0h+var_398]
0x18001a000  lea     r10, SourceString
0x18001a007  mov     [rsp+3D0h+var_390], rax
0x18001a00c  lea     rax, [rsp+3D0h+var_390]
0x18001a011  mov     [rbp+2D0h+var_350], rax
0x18001a015  lea     rax, [rbp+2D0h+var_328]
0x18001a019  mov     [rbp+2D0h+var_340], rax
0x18001a01d  lea     rax, [rbp+2D0h+ExeName]
0x18001a024  mov     [rbp+2D0h+var_330], rax
0x18001a028  movzx   eax, word ptr [rsp+3D0h+dwSize]
0x18001a02d  add     eax, eax
0x18001a02f  mov     [rbp+2D0h+var_348], 8
0x18001a037  mov     [rbp+2D0h+var_328], eax
0x18001a03a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a03e  mov     [rbp+2D0h+var_338], rcx
0x18001a042  mov     [rbp+2D0h+var_324], esi
0x18001a045  mov     r8, [r9+48h]
0x18001a049  test    r8, r8
0x18001a04c  jz      short loc_18001A064
0x18001a04e  mov     rdx, rax
0x18001a051  inc     rdx
0x18001a054  cmp     [r8+rdx*2], si
0x18001a059  jnz     short loc_18001A051
0x18001a05b  lea     edx, ds:2[rdx*2]
0x18001a062  jmp     short loc_18001A069
0x18001a064  mov     r8, r10
0x18001a067  mov     edx, ecx
0x18001a069  mov     [rbp+2D0h+var_320], r8
0x18001a06d  mov     [rbp+2D0h+var_318], edx
0x18001a070  mov     [rbp+2D0h+var_314], esi
0x18001a073  mov     rdx, [r9+20h]
0x18001a077  test    rdx, rdx
0x18001a07a  jz      short loc_18001A093
0x18001a07c  mov     r8, rax
0x18001a07f  inc     r8
0x18001a082  cmp     [rdx+r8*2], si
0x18001a087  jnz     short loc_18001A07F
0x18001a089  lea     r8d, ds:2[r8*2]
0x18001a091  jmp     short loc_18001A099
0x18001a093  mov     rdx, r10
0x18001a096  mov     r8d, ecx
0x18001a099  mov     [rbp+2D0h+var_310], rdx
0x18001a09d  mov     [rbp+2D0h+var_308], r8d
0x18001a0a1  mov     [rbp+2D0h+var_304], esi
0x18001a0a4  mov     rdx, [r9+38h]
0x18001a0a8  test    rdx, rdx
0x18001a0ab  jz      short loc_18001A0C4
0x18001a0ad  mov     r8, rax
0x18001a0b0  inc     r8
0x18001a0b3  cmp     [rdx+r8*2], si
0x18001a0b8  jnz     short loc_18001A0B0
0x18001a0ba  lea     r8d, ds:2[r8*2]
0x18001a0c2  jmp     short loc_18001A0CA
0x18001a0c4  mov     rdx, r10
0x18001a0c7  mov     r8d, ecx
0x18001a0ca  mov     [rbp+2D0h+var_300], rdx
0x18001a0ce  mov     [rbp+2D0h+var_2F8], r8d
0x18001a0d2  mov     [rbp+2D0h+var_2F4], esi
0x18001a0d5  mov     rdx, [r9+10h]
0x18001a0d9  test    rdx, rdx
0x18001a0dc  jz      short loc_18001A0F5
0x18001a0de  mov     r8, rax
0x18001a0e1  inc     r8
0x18001a0e4  cmp     [rdx+r8*2], si
0x18001a0e9  jnz     short loc_18001A0E1
0x18001a0eb  lea     r8d, ds:2[r8*2]
0x18001a0f3  jmp     short loc_18001A0FB
0x18001a0f5  mov     rdx, r10
0x18001a0f8  mov     r8d, ecx
0x18001a0fb  mov     [rbp+2D0h+var_2F0], rdx
0x18001a0ff  mov     [rbp+2D0h+var_2E8], r8d
0x18001a103  mov     [rbp+2D0h+var_2E4], esi
0x18001a106  mov     rdx, [r9]
0x18001a109  test    rdx, rdx
0x18001a10c  jz      short loc_18001A125
0x18001a10e  mov     r8, rax
0x18001a111  inc     r8
0x18001a114  cmp     [rdx+r8*2], si
0x18001a119  jnz     short loc_18001A111
0x18001a11b  lea     r8d, ds:2[r8*2]
0x18001a123  jmp     short loc_18001A12B
0x18001a125  mov     rdx, r10
0x18001a128  mov     r8d, ecx
0x18001a12b  mov     [rbp+2D0h+var_2E0], rdx
0x18001a12f  mov     [rbp+2D0h+var_2D8], r8d
0x18001a133  mov     [rbp+2D0h+var_2D4], esi
0x18001a136  mov     rdx, [r9+18h]
0x18001a13a  test    rdx, rdx
0x18001a13d  jz      short loc_18001A156
0x18001a13f  mov     r8, rax
0x18001a142  inc     r8
0x18001a145  cmp     [rdx+r8*2], si
0x18001a14a  jnz     short loc_18001A142
0x18001a14c  lea     r8d, ds:2[r8*2]
0x18001a154  jmp     short loc_18001A15C
0x18001a156  mov     rdx, r10
0x18001a159  mov     r8d, ecx
0x18001a15c  mov     [rbp+2D0h+var_2D0], rdx
0x18001a160  mov     [rbp+2D0h+var_2C8], r8d
0x18001a164  mov     [rbp+2D0h+var_2C4], esi
0x18001a167  mov     rdx, [r9+30h]
0x18001a16b  test    rdx, rdx
0x18001a16e  jz      short loc_18001A187
0x18001a170  mov     r8, rax
0x18001a173  inc     r8
0x18001a176  cmp     [rdx+r8*2], si
0x18001a17b  jnz     short loc_18001A173
0x18001a17d  lea     r8d, ds:2[r8*2]
0x18001a185  jmp     short loc_18001A18D
0x18001a187  mov     rdx, r10
0x18001a18a  mov     r8d, ecx
0x18001a18d  mov     [rbp+2D0h+var_2C0], rdx
0x18001a191  mov     [rbp+2D0h+var_2B8], r8d
0x18001a195  mov     [rbp+2D0h+var_2B4], esi
0x18001a198  mov     rdx, [r9+40h]
0x18001a19c  test    rdx, rdx
0x18001a19f  jz      short loc_18001A1B8
0x18001a1a1  mov     r8, rax
0x18001a1a4  inc     r8
0x18001a1a7  cmp     [rdx+r8*2], si
0x18001a1ac  jnz     short loc_18001A1A4
0x18001a1ae  lea     r8d, ds:2[r8*2]
0x18001a1b6  jmp     short loc_18001A1BE
0x18001a1b8  mov     rdx, r10
0x18001a1bb  mov     r8d, ecx
0x18001a1be  mov     [rbp+2D0h+var_2B0], rdx
0x18001a1c2  mov     [rbp+2D0h+var_2A8], r8d
0x18001a1c6  mov     [rbp+2D0h+var_2A4], esi
0x18001a1c9  mov     rdx, [r9+8]
0x18001a1cd  test    rdx, rdx
0x18001a1d0  jz      short loc_18001A1E9
0x18001a1d2  mov     r8, rax
0x18001a1d5  inc     r8
0x18001a1d8  cmp     [rdx+r8*2], si
0x18001a1dd  jnz     short loc_18001A1D5
0x18001a1df  lea     r8d, ds:2[r8*2]
0x18001a1e7  jmp     short loc_18001A1EF
0x18001a1e9  mov     rdx, r10
0x18001a1ec  mov     r8d, ecx
0x18001a1ef  mov     [rbp+2D0h+var_2A0], rdx
0x18001a1f3  mov     [rbp+2D0h+var_298], r8d
0x18001a1f7  mov     [rbp+2D0h+var_294], esi
0x18001a1fa  mov     rdx, [r9+28h]
0x18001a1fe  test    rdx, rdx
0x18001a201  jz      short loc_18001A215
0x18001a203  inc     rax
0x18001a206  cmp     [rdx+rax*2], si
0x18001a20a  jnz     short loc_18001A203
0x18001a20c  lea     ecx, ds:2[rax*2]
0x18001a213  jmp     short loc_18001A218
0x18001a215  mov     rdx, r10
0x18001a218  mov     eax, cs:dword_18002AB78
0x18001a21e  xor     r9d, r9d
0x18001a221  mov     [rsp+3D0h+var_388], rax
0x18001a226  xor     r8d, r8d
0x18001a229  lea     rax, [rsp+3D0h+var_388]
0x18001a22e  mov     [rbp+2D0h+var_290], rdx
0x18001a232  mov     [rbp+2D0h+var_280], rax
0x18001a236  lea     rdx, byte_18002398F
0x18001a23d  mov     rax, cs:qword_18002AB70
0x18001a244  mov     [rsp+3D0h+var_380], rax
0x18001a249  lea     rax, [rsp+3D0h+var_380]
0x18001a24e  mov     [rbp+2D0h+var_270], rax
0x18001a252  mov     eax, cs:dword_18002AB7C
0x18001a258  mov     [rsp+3D0h+var_39C], eax
0x18001a25c  lea     rax, [rsp+3D0h+var_39C]
0x18001a261  mov     [rbp+2D0h+var_260], rax
0x18001a265  lea     rax, [rsp+3D0h+var_378]
0x18001a26a  mov     [rbp+2D0h+var_250], rax
0x18001a271  lea     rax, [rsp+3D0h+var_370]
0x18001a276  mov     [rbp+2D0h+var_288], ecx
0x18001a279  lea     rcx, dword_18002A1A0
0x18001a280  mov     [rsp+3D0h+var_3A8], rax
0x18001a285  mov     [rsp+3D0h+var_3B0], 13h
0x18001a28d  mov     [rbp+2D0h+var_284], esi
0x18001a290  mov     [rbp+2D0h+var_278], 8
0x18001a298  mov     [rbp+2D0h+var_268], 8
0x18001a2a0  mov     [rbp+2D0h+var_258], 4
0x18001a2a8  mov     [rsp+3D0h+var_378], 1000000h
0x18001a2b1  mov     [rbp+2D0h+var_248], 8
0x18001a2bc  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a2c1  mov     rcx, rdi; hObject
0x18001a2c4  call    cs:__imp_CloseHandle
0x18001a2cb  nop     dword ptr [rax+rax+00h]
0x18001a2d0  mov     rcx, [rsp+3D0h+var_398]
0x18001a2d5  test    rcx, rcx
0x18001a2d8  jz      short loc_18001A2E6
0x18001a2da  call    cs:__imp_PicFreeFileInfo
0x18001a2e1  nop     dword ptr [rax+rax+00h]
0x18001a2e6  mov     rcx, [rbp+2D0h+var_30]
0x18001a2ed  xor     rcx, rsp; StackCookie
0x18001a2f0  call    __security_check_cookie
0x18001a2f5  add     rsp, 3B8h
0x18001a2fc  pop     rdi
0x18001a2fd  pop     rsi
0x18001a2fe  pop     rbx
0x18001a2ff  pop     rbp
0x18001a300  retn
```

# MwcUpdateLSP

- ea: `0x180033a4c`
- end: `0x180034091`
- name: `MwcUpdateLSP`
- size: `1605`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180034098`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x180033a4c`
- `0x180038104`
- `0x18003a9bc`
- `0x18003ab10`
- `0x18003aec4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003405a`
- `ntdll!RtlFreeHeap` at `0x18003405a`
- `WS2_32!WSCUpdateProviderEx` at `0x180033ed1`
- `WS2_32!WSCUpdateProviderEx` at `0x180033ed1`
- `WS2_32!WPUGetProviderPathEx` at `0x180033af9`
- `WS2_32!WPUGetProviderPathEx` at `0x180033bbf`
- `WS2_32!WPUGetProviderPathEx` at `0x180033af9`
- `WS2_32!WPUGetProviderPathEx` at `0x180033bbf`

## string_xrefs

- `0x180033b61`: `Failed to allocate space for provider path`
- `0x180033bf2`: `Failed to get provider path`
- `0x180033f8d`: `Failed to update LSP`

## pseudocode

```c
char __fastcall MwcUpdateLSP(char a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  _BYTE *v5; // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  _BYTE *v12; // rax
  int v13; // eax
  int v14; // eax
  PVOID v15; // r8
  __int64 v16; // rdx
  unsigned int i; // r9d
  __int64 v18; // rsi
  __int64 v19; // rax
  unsigned int v20; // r8d
  unsigned int v21; // r13d
  unsigned int v22; // ebx
  __int64 v23; // r15
  __int64 v24; // r10
  __int64 v25; // rax
  __int64 v26; // r11
  _OWORD *v27; // rdx
  _OWORD *v28; // rcx
  _OWORD *v29; // rax
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  int v44; // eax
  _OWORD *v45; // rcx
  __int64 v46; // r10
  _OWORD *v47; // rax
  __int128 v48; // xmm1
  _OWORD *v49; // rax
  __int64 v50; // rdx
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  int v64; // eax
  int v65; // eax
  unsigned int v66; // r13d
  char *v67; // r14
  char *v68; // r9
  _QWORD *v70; // [rsp+28h] [rbp-E8h]
  unsigned int v71; // [rsp+90h] [rbp-80h] BYREF
  char v72; // [rsp+94h] [rbp-7Ch]
  int v73; // [rsp+98h] [rbp-78h] BYREF
  unsigned int v74; // [rsp+9Ch] [rbp-74h]
  _QWORD v75[2]; // [rsp+A0h] [rbp-70h] BYREF
  PVOID P; // [rsp+B0h] [rbp-60h]
  _DWORD v77[2]; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v78; // [rsp+C0h] [rbp-50h]
  _DWORD v79[2]; // [rsp+C8h] [rbp-48h] BYREF
  __int64 v80; // [rsp+D0h] [rbp-40h]
  _BYTE v81[640]; // [rsp+E0h] [rbp-30h] BYREF
  _BYTE v82[528]; // [rsp+360h] [rbp+250h] BYREF

  v5 = v82;
  v74 = a4;
  v75[0] = a3;
  v72 = a1;
  v9 = *(_DWORD *)(a5 + 4) - 2;
  v71 = 0;
  v73 = 261;
  P = v82;
  if ( (v9 & 0xFFFFFFFD) != 0 || !a1 )
  {
    v10 = WPUGetProviderPathEx(a2, v82, &v73, &v71, a5);
  }
  else
  {
    v77[0] = *(_DWORD *)a5;
    v78 = *(_QWORD *)(a5 + 8);
    v77[1] = 4;
    v10 = WPUGetProviderPathEx(a2, v82, &v73, &v71, v77);
  }
  if ( !v10 )
    goto LABEL_21;
  v11 = v71;
  if ( v71 != 10014 )
    goto LABEL_17;
  P = (PVOID)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 2LL * v73);
  v5 = P;
  if ( !P )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 62, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    LOBYTE(v12) = LogError(8, L"Failed to allocate space for provider path");
    return (char)v12;
  }
  v13 = *(_DWORD *)(a5 + 4) - 2;
  v71 = 0;
  if ( (v13 & 0xFFFFFFFD) != 0 || !a1 )
  {
    v14 = WPUGetProviderPathEx(a2, P, &v73, &v71, a5);
  }
  else
  {
    v79[0] = *(_DWORD *)a5;
    v80 = *(_QWORD *)(a5 + 8);
    v79[1] = 4;
    v14 = WPUGetProviderPathEx(a2, P, &v73, &v71, v79);
  }
  if ( !v14 )
  {
LABEL_21:
    v16 = v75[0];
    for ( i = 0; i < a4; ++i )
    {
      v18 = v75[0] + 628LL * i;
      v19 = *(_QWORD *)a2 - *(_QWORD *)(v18 + 20);
      if ( *(_QWORD *)a2 == *(_QWORD *)(v18 + 20) )
        v19 = *(_QWORD *)(a2 + 8) - *(_QWORD *)(v18 + 28);
      v20 = i + 1;
      if ( !v19 )
      {
        v21 = i + 1;
        if ( v20 < a4 )
        {
          v22 = v74;
          v23 = v20;
          do
          {
            v24 = 628 * v23;
            v25 = *(_QWORD *)a2 - *(_QWORD *)(628 * v23 + v16 + 20);
            if ( *(_QWORD *)a2 == *(_QWORD *)(628 * v23 + v16 + 20) )
              v25 = *(_QWORD *)(a2 + 8) - *(_QWORD *)(v24 + v16 + 28);
            if ( !v25 )
            {
              if ( v21 != v20 )
              {
                v26 = 4;
                v27 = (_OWORD *)(628LL * v21 + v16);
                v28 = v81;
                v29 = v27;
                do
                {
                  v30 = *v29;
                  v31 = v29[1];
                  v29 += 8;
                  *v28 = v30;
                  v32 = *(v29 - 6);
                  v28[1] = v31;
                  v33 = *(v29 - 5);
                  v28[2] = v32;
                  v34 = *(v29 - 4);
                  v28[3] = v33;
                  v35 = *(v29 - 3);
                  v28[4] = v34;
                  v36 = *(v29 - 2);
                  v28[5] = v35;
                  v37 = *(v29 - 1);
                  v28[6] = v36;
                  v28[7] = v37;
                  v28 += 8;
                  --v26;
                }
                while ( v26 );
                v38 = v29[1];
                *v28 = *v29;
                v39 = v29[2];
                v28[1] = v38;
                v40 = v29[3];
                v28[2] = v39;
                v41 = v29[4];
                v28[3] = v40;
                v42 = v29[5];
                v28[4] = v41;
                v43 = v29[6];
                v44 = *((_DWORD *)v29 + 28);
                v28[5] = v42;
                v28[6] = v43;
                *((_DWORD *)v28 + 28) = v44;
                v45 = (_OWORD *)(v24 + v75[0]);
                v46 = 4;
                v47 = v45;
                do
                {
                  *v27 = *v47;
                  v27[1] = v47[1];
                  v27[2] = v47[2];
                  v27[3] = v47[3];
                  v27[4] = v47[4];
                  v27[5] = v47[5];
                  v27[6] = v47[6];
                  v48 = v47[7];
                  v47 += 8;
                  v27[7] = v48;
                  v27 += 8;
                  --v46;
                }
                while ( v46 );
                *v27 = *v47;
                v27[1] = v47[1];
                v27[2] = v47[2];
                v27[3] = v47[3];
                v27[4] = v47[4];
                v27[5] = v47[5];
                v27[6] = v47[6];
                *((_DWORD *)v27 + 28) = *((_DWORD *)v47 + 28);
                v49 = v81;
                v50 = 4;
                do
                {
                  v51 = v49[1];
                  *v45 = *v49;
                  v52 = v49[2];
                  v45[1] = v51;
                  v53 = v49[3];
                  v45[2] = v52;
                  v54 = v49[4];
                  v45[3] = v53;
                  v55 = v49[5];
                  v45[4] = v54;
                  v56 = v49[6];
                  v45[5] = v55;
                  v57 = v49[7];
                  v49 += 8;
                  v45[6] = v56;
                  v45[7] = v57;
                  v45 += 8;
                  --v50;
                }
                while ( v50 );
                v16 = v75[0];
                v58 = v49[1];
                *v45 = *v49;
                v59 = v49[2];
                v45[1] = v58;
                v60 = v49[3];
                v45[2] = v59;
                v61 = v49[4];
                v45[3] = v60;
                v62 = v49[5];
                v45[4] = v61;
                v63 = v49[6];
                v64 = *((_DWORD *)v49 + 28);
                v45[5] = v62;
                v45[6] = v63;
                *((_DWORD *)v45 + 28) = v64;
              }
              ++v21;
            }
            ++v20;
            ++v23;
          }
          while ( v20 < v22 );
          v5 = P;
        }
        v65 = *(_DWORD *)(a5 + 4) - 2;
        v71 = 0;
        if ( (v65 & 0xFFFFFFFD) != 0 || !a1 )
        {
          v70 = (_QWORD *)a5;
        }
        else
        {
          LODWORD(v75[0]) = *(_DWORD *)a5;
          v75[1] = *(_QWORD *)(a5 + 8);
          v70 = v75;
          HIDWORD(v75[0]) = 4;
        }
        v66 = v21 - i;
        if ( (unsigned int)WSCUpdateProviderEx(a2, v5, v18, v66, &v71, v70) )
        {
          LogError(v71, L"Failed to update LSP");
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            v68 = " [32]";
            if ( !v72 )
              v68 = byte_180055A0D;
            WPP_SF_sLDDDDDDDDDDLL(
              *(unsigned __int8 *)(a2 + 15),
              *(unsigned __int8 *)(a2 + 14),
              *(unsigned __int8 *)(a2 + 13),
              (_DWORD)v68,
              *(_DWORD *)a2,
              *(_WORD *)(a2 + 4),
              *(_WORD *)(a2 + 6),
              *(_BYTE *)(a2 + 8),
              *(_BYTE *)(a2 + 9),
              *(_BYTE *)(a2 + 10),
              *(_BYTE *)(a2 + 11),
              *(_BYTE *)(a2 + 12),
              *(_BYTE *)(a2 + 13),
              *(_BYTE *)(a2 + 14),
              *(_BYTE *)(a2 + 15),
              v66,
              v71);
          }
        }
        else if ( (xmmword_180063D60 & 2) != 0 )
        {
          v67 = " [32]";
          if ( !v72 )
            v67 = byte_180055A0D;
          WPP_SF_sLDDDDDDDDDDL(
            *(unsigned __int8 *)(a2 + 14),
            *(unsigned __int8 *)(a2 + 13),
            *(unsigned __int8 *)(a2 + 12),
            (_DWORD)v67,
            *(_DWORD *)a2,
            *(_WORD *)(a2 + 4),
            *(_WORD *)(a2 + 6),
            *(_BYTE *)(a2 + 8),
            *(_BYTE *)(a2 + 9),
            *(_BYTE *)(a2 + 10),
            *(_BYTE *)(a2 + 11),
            *(_BYTE *)(a2 + 12),
            *(_BYTE *)(a2 + 13),
            *(_BYTE *)(a2 + 14),
            *(_BYTE *)(a2 + 15),
            v66);
        }
        break;
      }
    }
    v15 = P;
    v12 = v82;
    if ( P != v82 )
      goto LABEL_57;
    return (char)v12;
  }
  v11 = v71;
LABEL_17:
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_l(v11, 63, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (unsigned int)v11);
    v11 = v71;
  }
  LogError(v11, L"Failed to get provider path");
  v12 = v82;
  if ( v5 != v82 )
  {
    v15 = v5;
LABEL_57:
    LOBYTE(v12) = RtlFreeHeap(SockPrivateHeap, 0, v15);
  }
  return (char)v12;
}

```

## disassembly

```asm
0x180033a4c  mov     [rsp-8+arg_0], rbx
0x180033a51  push    rbp
0x180033a52  push    rsi
0x180033a53  push    rdi
0x180033a54  push    r12
0x180033a56  push    r13
0x180033a58  push    r14
0x180033a5a  push    r15
0x180033a5c  lea     rbp, [rsp-470h]
0x180033a64  sub     rsp, 580h
0x180033a6b  mov     rax, cs:__security_cookie
0x180033a72  xor     rax, rsp
0x180033a75  mov     [rbp+4A0h+var_40], rax
0x180033a7c  mov     rdi, [rbp+4A0h+arg_20]
0x180033a83  lea     rbx, [rbp+4A0h+var_250]
0x180033a8a  mov     esi, 0FFFFFFFDh
0x180033a8f  mov     [rbp+4A0h+var_514], r9d
0x180033a93  mov     r15d, r9d
0x180033a96  mov     [rbp+4A0h+var_510], r8
0x180033a9a  mov     r12, rdx
0x180033a9d  mov     [rbp+4A0h+var_51C], cl
0x180033aa0  mov     eax, [rdi+4]
0x180033aa3  mov     r14b, cl
0x180033aa6  sub     eax, 2
0x180033aa9  mov     [rbp+4A0h+var_520], 0
0x180033ab0  mov     [rbp+4A0h+var_518], 105h
0x180033ab7  mov     [rbp+4A0h+P], rbx
0x180033abb  test    esi, eax
0x180033abd  jnz     short loc_180033AE2
0x180033abf  test    cl, cl
0x180033ac1  jz      short loc_180033AE2
0x180033ac3  mov     eax, [rdi]
0x180033ac5  mov     [rbp+4A0h+var_4F8], eax
0x180033ac8  mov     rax, [rdi+8]
0x180033acc  mov     [rbp+4A0h+var_4F0], rax
0x180033ad0  lea     rax, [rbp+4A0h+var_4F8]
0x180033ad4  mov     [rsp+5B0h+var_590], rax
0x180033ad9  mov     [rbp+4A0h+var_4F4], 4
0x180033ae0  jmp     short loc_180033AE7
0x180033ae2  mov     [rsp+5B0h+var_590], rdi
0x180033ae7  lea     r9, [rbp+4A0h+var_520]
0x180033aeb  mov     rcx, r12
0x180033aee  lea     r8, [rbp+4A0h+var_518]
0x180033af2  lea     rdx, [rbp+4A0h+var_250]
0x180033af9  call    cs:__imp_WPUGetProviderPathEx
0x180033b00  nop     dword ptr [rax+rax+00h]
0x180033b05  test    eax, eax
0x180033b07  jz      loc_180033C16
0x180033b0d  mov     ecx, [rbp+4A0h+var_520]
0x180033b10  cmp     ecx, 271Eh
0x180033b16  jnz     loc_180033BD2
0x180033b1c  movsxd  r8, [rbp+4A0h+var_518]
0x180033b20  xor     edx, edx
0x180033b22  mov     rcx, cs:SockPrivateHeap
0x180033b29  add     r8, r8
0x180033b2c  mov     rax, cs:SockAllocateHeapRoutine
0x180033b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b38  mov     [rbp+4A0h+P], rax
0x180033b3c  mov     rbx, rax
0x180033b3f  test    rax, rax
0x180033b42  jnz     short loc_180033B77
0x180033b44  test    byte ptr cs:xmmword_180063D60, 2
0x180033b4b  jz      short loc_180033B61
0x180033b4d  lea     edx, [rax+3Eh]
0x180033b50  mov     ecx, 401h
0x180033b55  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180033b5c  call    WPP_SF_
0x180033b61  lea     rdx, aFailedToAlloca_7; "Failed to allocate space for provider p"...
0x180033b68  mov     ecx, 8
0x180033b6d  call    LogError
0x180033b72  jmp     loc_180034066
0x180033b77  mov     eax, [rdi+4]
0x180033b7a  sub     eax, 2
0x180033b7d  mov     [rbp+4A0h+var_520], 0
0x180033b84  test    esi, eax
0x180033b86  jnz     short loc_180033BAC
0x180033b88  test    r14b, r14b
0x180033b8b  jz      short loc_180033BAC
0x180033b8d  mov     eax, [rdi]
0x180033b8f  mov     [rbp+4A0h+var_4E8], eax
0x180033b92  mov     rax, [rdi+8]
0x180033b96  mov     [rbp+4A0h+var_4E0], rax
0x180033b9a  lea     rax, [rbp+4A0h+var_4E8]
0x180033b9e  mov     [rsp+5B0h+var_590], rax
0x180033ba3  mov     [rbp+4A0h+var_4E4], 4
0x180033baa  jmp     short loc_180033BB1
0x180033bac  mov     [rsp+5B0h+var_590], rdi
0x180033bb1  lea     r9, [rbp+4A0h+var_520]
0x180033bb5  mov     rdx, rbx
0x180033bb8  lea     r8, [rbp+4A0h+var_518]
0x180033bbc  mov     rcx, r12
0x180033bbf  call    cs:__imp_WPUGetProviderPathEx
0x180033bc6  nop     dword ptr [rax+rax+00h]
0x180033bcb  test    eax, eax
0x180033bcd  jz      short loc_180033C16
0x180033bcf  mov     ecx, [rbp+4A0h+var_520]
0x180033bd2  test    byte ptr cs:xmmword_180063D60, 2
0x180033bd9  jz      short loc_180033BF2
0x180033bdb  mov     edx, 3Fh ; '?'
0x180033be0  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180033be7  mov     r9d, ecx
0x180033bea  call    WPP_SF_l
0x180033bef  mov     ecx, [rbp+4A0h+var_520]
0x180033bf2  lea     rdx, aFailedToGetPro; "Failed to get provider path"
0x180033bf9  call    LogError
0x180033bfe  lea     rax, [rbp+4A0h+var_250]
0x180033c05  cmp     rbx, rax
0x180033c08  jz      loc_180034066
0x180033c0e  mov     r8, rbx
0x180033c11  jmp     loc_180034051
0x180033c16  mov     rdx, [rbp+4A0h+var_510]
0x180033c1a  xor     r9d, r9d
0x180033c1d  cmp     r9d, r15d
0x180033c20  jnb     loc_180034041
0x180033c26  mov     eax, r9d
0x180033c29  imul    rsi, rax, 274h
0x180033c30  mov     rax, [r12]
0x180033c34  add     rsi, rdx
0x180033c37  sub     rax, [rsi+14h]
0x180033c3b  jnz     short loc_180033C46
0x180033c3d  mov     rax, [r12+8]
0x180033c42  sub     rax, [rsi+1Ch]
0x180033c46  lea     r8d, [r9+1]
0x180033c4a  test    rax, rax
0x180033c4d  jz      short loc_180033C54
0x180033c4f  mov     r9d, r8d
0x180033c52  jmp     short loc_180033C1D
0x180033c54  mov     r13d, r8d
0x180033c57  cmp     r8d, r15d
0x180033c5a  jnb     loc_180033E7C
0x180033c60  mov     ebx, [rbp+4A0h+var_514]
0x180033c63  mov     r15d, r8d
0x180033c66  mov     rax, [r12]
0x180033c6a  imul    r10, r15, 274h
0x180033c71  sub     rax, [r10+rdx+14h]
0x180033c76  jnz     short loc_180033C82
0x180033c78  mov     rax, [r12+8]
0x180033c7d  sub     rax, [r10+rdx+1Ch]
0x180033c82  test    rax, rax
0x180033c85  jnz     loc_180033E69
0x180033c8b  cmp     r13d, r8d
0x180033c8e  jz      loc_180033E66
0x180033c94  mov     eax, r13d
0x180033c97  mov     r11d, 4
0x180033c9d  imul    rcx, rax, 274h
0x180033ca4  add     rdx, rcx
0x180033ca7  lea     rcx, [rbp+4A0h+var_4D0]
0x180033cab  mov     rax, rdx
0x180033cae  movups  xmm0, xmmword ptr [rax]
0x180033cb1  movups  xmm1, xmmword ptr [rax+10h]
0x180033cb5  lea     rax, [rax+80h]
0x180033cbc  movups  xmmword ptr [rcx], xmm0
0x180033cbf  movups  xmm0, xmmword ptr [rax-60h]
0x180033cc3  movups  xmmword ptr [rcx+10h], xmm1
0x180033cc7  movups  xmm1, xmmword ptr [rax-50h]
0x180033ccb  movups  xmmword ptr [rcx+20h], xmm0
0x180033ccf  movups  xmm0, xmmword ptr [rax-40h]
0x180033cd3  movups  xmmword ptr [rcx+30h], xmm1
0x180033cd7  movups  xmm1, xmmword ptr [rax-30h]
0x180033cdb  movups  xmmword ptr [rcx+40h], xmm0
0x180033cdf  movups  xmm0, xmmword ptr [rax-20h]
0x180033ce3  movups  xmmword ptr [rcx+50h], xmm1
0x180033ce7  movups  xmm1, xmmword ptr [rax-10h]
0x180033ceb  movups  xmmword ptr [rcx+60h], xmm0
0x180033cef  movups  xmmword ptr [rcx+70h], xmm1
0x180033cf3  lea     rcx, [rcx+80h]
0x180033cfa  sub     r11, 1
0x180033cfe  jnz     short loc_180033CAE
0x180033d00  movups  xmm0, xmmword ptr [rax]
0x180033d03  movups  xmm1, xmmword ptr [rax+10h]
0x180033d07  movups  xmmword ptr [rcx], xmm0
0x180033d0a  movups  xmm0, xmmword ptr [rax+20h]
0x180033d0e  movups  xmmword ptr [rcx+10h], xmm1
0x180033d12  movups  xmm1, xmmword ptr [rax+30h]
0x180033d16  movups  xmmword ptr [rcx+20h], xmm0
0x180033d1a  movups  xmm0, xmmword ptr [rax+40h]
0x180033d1e  movups  xmmword ptr [rcx+30h], xmm1
0x180033d22  movups  xmm1, xmmword ptr [rax+50h]
0x180033d26  movups  xmmword ptr [rcx+40h], xmm0
0x180033d2a  movups  xmm0, xmmword ptr [rax+60h]
0x180033d2e  mov     eax, [rax+70h]
0x180033d31  movups  xmmword ptr [rcx+50h], xmm1
0x180033d35  movups  xmmword ptr [rcx+60h], xmm0
0x180033d39  mov     [rcx+70h], eax
0x180033d3c  mov     rcx, [rbp+4A0h+var_510]
0x180033d40  add     rcx, r10
0x180033d43  lea     r10d, [r11+4]
0x180033d47  lea     r11d, [r10+7Ch]
0x180033d4b  mov     rax, rcx
0x180033d4e  movups  xmm0, xmmword ptr [rax]
0x180033d51  movups  xmmword ptr [rdx], xmm0
0x180033d54  movups  xmm1, xmmword ptr [rax+10h]
0x180033d58  movups  xmmword ptr [rdx+10h], xmm1
0x180033d5c  movups  xmm0, xmmword ptr [rax+20h]
0x180033d60  movups  xmmword ptr [rdx+20h], xmm0
0x180033d64  movups  xmm1, xmmword ptr [rax+30h]
0x180033d68  movups  xmmword ptr [rdx+30h], xmm1
0x180033d6c  movups  xmm0, xmmword ptr [rax+40h]
0x180033d70  movups  xmmword ptr [rdx+40h], xmm0
0x180033d74  movups  xmm1, xmmword ptr [rax+50h]
0x180033d78  movups  xmmword ptr [rdx+50h], xmm1
0x180033d7c  movups  xmm0, xmmword ptr [rax+60h]
0x180033d80  movups  xmmword ptr [rdx+60h], xmm0
0x180033d84  movups  xmm1, xmmword ptr [rax+70h]
0x180033d88  add     rax, r11
0x180033d8b  movups  xmmword ptr [rdx+70h], xmm1
0x180033d8f  add     rdx, r11
0x180033d92  sub     r10, 1
0x180033d96  jnz     short loc_180033D4E
0x180033d98  movups  xmm0, xmmword ptr [rax]
0x180033d9b  movups  xmmword ptr [rdx], xmm0
0x180033d9e  movups  xmm1, xmmword ptr [rax+10h]
0x180033da2  movups  xmmword ptr [rdx+10h], xmm1
0x180033da6  movups  xmm0, xmmword ptr [rax+20h]
0x180033daa  movups  xmmword ptr [rdx+20h], xmm0
0x180033dae  movups  xmm1, xmmword ptr [rax+30h]
0x180033db2  movups  xmmword ptr [rdx+30h], xmm1
0x180033db6  movups  xmm0, xmmword ptr [rax+40h]
0x180033dba  movups  xmmword ptr [rdx+40h], xmm0
0x180033dbe  movups  xmm1, xmmword ptr [rax+50h]
0x180033dc2  movups  xmmword ptr [rdx+50h], xmm1
0x180033dc6  movups  xmm0, xmmword ptr [rax+60h]
0x180033dca  movups  xmmword ptr [rdx+60h], xmm0
0x180033dce  mov     eax, [rax+70h]
0x180033dd1  mov     [rdx+70h], eax
0x180033dd4  lea     rax, [rbp+4A0h+var_4D0]
0x180033dd8  lea     edx, [r10+4]
0x180033ddc  movups  xmm0, xmmword ptr [rax]
0x180033ddf  movups  xmm1, xmmword ptr [rax+10h]
0x180033de3  movups  xmmword ptr [rcx], xmm0
0x180033de6  movups  xmm0, xmmword ptr [rax+20h]
0x180033dea  movups  xmmword ptr [rcx+10h], xmm1
0x180033dee  movups  xmm1, xmmword ptr [rax+30h]
0x180033df2  movups  xmmword ptr [rcx+20h], xmm0
0x180033df6  movups  xmm0, xmmword ptr [rax+40h]
0x180033dfa  movups  xmmword ptr [rcx+30h], xmm1
0x180033dfe  movups  xmm1, xmmword ptr [rax+50h]
0x180033e02  movups  xmmword ptr [rcx+40h], xmm0
0x180033e06  movups  xmm0, xmmword ptr [rax+60h]
0x180033e0a  movups  xmmword ptr [rcx+50h], xmm1
0x180033e0e  movups  xmm1, xmmword ptr [rax+70h]
0x180033e12  add     rax, r11
0x180033e15  movups  xmmword ptr [rcx+60h], xmm0
0x180033e19  movups  xmmword ptr [rcx+70h], xmm1
0x180033e1d  add     rcx, r11
0x180033e20  sub     rdx, 1
0x180033e24  jnz     short loc_180033DDC
0x180033e26  movups  xmm0, xmmword ptr [rax]
0x180033e29  mov     rdx, [rbp+4A0h+var_510]
0x180033e2d  movups  xmm1, xmmword ptr [rax+10h]
0x180033e31  movups  xmmword ptr [rcx], xmm0
0x180033e34  movups  xmm0, xmmword ptr [rax+20h]
0x180033e38  movups  xmmword ptr [rcx+10h], xmm1
0x180033e3c  movups  xmm1, xmmword ptr [rax+30h]
0x180033e40  movups  xmmword ptr [rcx+20h], xmm0
0x180033e44  movups  xmm0, xmmword ptr [rax+40h]
0x180033e48  movups  xmmword ptr [rcx+30h], xmm1
0x180033e4c  movups  xmm1, xmmword ptr [rax+50h]
0x180033e50  movups  xmmword ptr [rcx+40h], xmm0
0x180033e54  movups  xmm0, xmmword ptr [rax+60h]
0x180033e58  mov     eax, [rax+70h]
0x180033e5b  movups  xmmword ptr [rcx+50h], xmm1
0x180033e5f  movups  xmmword ptr [rcx+60h], xmm0
0x180033e63  mov     [rcx+70h], eax
0x180033e66  inc     r13d
0x180033e69  inc     r8d
0x180033e6c  inc     r15
0x180033e6f  cmp     r8d, ebx
0x180033e72  jb      loc_180033C66
0x180033e78  mov     rbx, [rbp+4A0h+P]
0x180033e7c  mov     eax, [rdi+4]
0x180033e7f  sub     eax, 2
0x180033e82  mov     [rbp+4A0h+var_520], 0
0x180033e89  test    eax, 0FFFFFFFDh
0x180033e8e  jnz     short loc_180033EB4
0x180033e90  test    r14b, r14b
0x180033e93  jz      short loc_180033EB4
0x180033e95  mov     eax, [rdi]
0x180033e97  mov     dword ptr [rbp+4A0h+var_510], eax
0x180033e9a  mov     rax, [rdi+8]
0x180033e9e  mov     [rbp+4A0h+var_508], rax
0x180033ea2  lea     rax, [rbp+4A0h+var_510]
0x180033ea6  mov     [rsp+5B0h+var_588], rax
0x180033eab  mov     dword ptr [rbp+4A0h+var_510+4], 4
0x180033eb2  jmp     short loc_180033EB9
0x180033eb4  mov     [rsp+5B0h+var_588], rdi
0x180033eb9  sub     r13d, r9d
0x180033ebc  lea     rax, [rbp+4A0h+var_520]
0x180033ec0  mov     r9d, r13d
0x180033ec3  mov     [rsp+5B0h+var_590], rax
0x180033ec8  mov     r8, rsi
0x180033ecb  mov     rdx, rbx
0x180033ece  mov     rcx, r12
0x180033ed1  call    cs:__imp_WSCUpdateProviderEx
0x180033ed8  nop     dword ptr [rax+rax+00h]
0x180033edd  test    eax, eax
0x180033edf  jnz     loc_180033F8A
0x180033ee5  test    byte ptr cs:xmmword_180063D60, 2
0x180033eec  jz      loc_180034041
0x180033ef2  movzx   eax, byte ptr [r12+0Fh]
  ... truncated ...
```

# DhcpRenewIpAddressLeaseEx

- ea: `0x18000a4d0`
- end: `0x18000a944`
- name: `DhcpRenewIpAddressLeaseEx`
- size: `1140`
- prototype: `__int64 __fastcall(int, int, int, int, void *Source, rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000a410`

## callees

- `0x180002760`
- `0x1800048c0`
- `0x180005162`
- `0x1800058e4`
- `0x18000a4d0`
- `0x18000d5c8`
- `0x18000f4ec`
- `0x180010154`
- `0x1800110f8`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a6b6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a7f1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a82f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a6b6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a7f1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a82f`

## pseudocode

```c
__int64 __fastcall DhcpRenewIpAddressLeaseEx(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *Source,
        rsize_t SourceSize)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  const void *v11; // r8
  unsigned int v12; // eax
  _DWORD *v13; // r13
  __int64 *v14; // r14
  __int64 *v15; // r12
  _DWORD *v16; // rdi
  LPWSTR CommandLineW; // rax
  _OWORD *v18; // rdx
  int *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  int *v22; // rdx
  int *v23; // rax
  LPWSTR v24; // rax
  int v25; // ecx
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int128 v31; // [rsp+50h] [rbp-3F8h] BYREF
  __int128 v32; // [rsp+60h] [rbp-3E8h]
  __int128 v33; // [rsp+70h] [rbp-3D8h]
  __int64 v34; // [rsp+80h] [rbp-3C8h]
  __int64 v35; // [rsp+88h] [rbp-3C0h]
  __int64 v36; // [rsp+90h] [rbp-3B8h]
  __int64 v37; // [rsp+98h] [rbp-3B0h]
  __int64 v38; // [rsp+A0h] [rbp-3A8h]
  _DWORD *v39; // [rsp+A8h] [rbp-3A0h]
  _DWORD *v40; // [rsp+B0h] [rbp-398h]
  _DWORD *v41; // [rsp+B8h] [rbp-390h]
  _QWORD *v42; // [rsp+C0h] [rbp-388h]
  _DWORD *v43; // [rsp+C8h] [rbp-380h]
  _BYTE v44[272]; // [rsp+D0h] [rbp-378h] BYREF
  int v45; // [rsp+1E0h] [rbp-268h] BYREF
  _BYTE Destination[268]; // [rsp+1E4h] [rbp-264h] BYREF
  unsigned int v47; // [rsp+2F0h] [rbp-158h] BYREF
  char v48; // [rsp+2F4h] [rbp-154h] BYREF
  _BYTE v49[267]; // [rsp+2F5h] [rbp-153h] BYREF

  v34 = a4;
  v35 = a3;
  memset_0(Destination, 0, 0x100u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  memset_0(&v48, 0, 0x100u);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 228, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v8 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 229, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    if ( (Source == 0) != ((_DWORD)SourceSize == 0) || !a2 )
      goto LABEL_5;
    v45 = SourceSize;
    if ( Source )
    {
      v9 = memcpy_s(Destination, 0xFFu, Source, (unsigned int)SourceSize);
      v8 = Win32FromErrno(v9);
      if ( v8 )
        goto LABEL_30;
    }
    v10 = *(_DWORD *)(a2 + 8);
    if ( !v10 || (v11 = *(const void **)a2) == 0 )
    {
LABEL_5:
      v8 = 87;
      goto LABEL_30;
    }
    DWORD2(v31) = *(_DWORD *)(a2 + 8);
    v47 = v10;
    v12 = memcpy_s(v49, 0xFEu, v11, v10);
    v8 = Win32FromErrno(v12);
    if ( !v8 )
    {
      v13 = (_DWORD *)(a2 + 24);
      v36 = a2 + 24;
      DWORD2(v32) = *(_DWORD *)(a2 + 24);
      v40 = (_DWORD *)(a2 + 16);
      LODWORD(v32) = *(_DWORD *)(a2 + 16);
      v41 = (_DWORD *)(a2 + 28);
      HIDWORD(v32) = *(_DWORD *)(a2 + 28);
      v14 = (__int64 *)(a2 + 56);
      v37 = a2 + 56;
      HIDWORD(v33) = *(_DWORD *)(a2 + 56);
      v42 = (_QWORD *)(a2 + 32);
      LODWORD(v33) = *(_DWORD *)(a2 + 32);
      v43 = (_DWORD *)(a2 + 20);
      DWORD1(v32) = *(_DWORD *)(a2 + 20);
      v15 = (__int64 *)(a2 + 40);
      v38 = a2 + 40;
      DWORD1(v33) = *(_DWORD *)(a2 + 40);
      v16 = (_DWORD *)(a2 + 48);
      v39 = v16;
      DWORD2(v33) = *v16;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_DS(1028, 231, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
      v18 = v44;
      v19 = &v45;
      v20 = 2;
      v21 = 2;
      do
      {
        *v18 = *(_OWORD *)v19;
        v18[1] = *((_OWORD *)v19 + 1);
        v18[2] = *((_OWORD *)v19 + 2);
        v18[3] = *((_OWORD *)v19 + 3);
        v18[4] = *((_OWORD *)v19 + 4);
        v18[5] = *((_OWORD *)v19 + 5);
        v18[6] = *((_OWORD *)v19 + 6);
        v18[7] = *((_OWORD *)v19 + 7);
        v18 += 8;
        v19 += 32;
        --v21;
      }
      while ( v21 );
      *(_DWORD *)v18 = *v19;
      v22 = &v45;
      v23 = (int *)&v47;
      do
      {
        *(_OWORD *)v22 = *(_OWORD *)v23;
        *((_OWORD *)v22 + 1) = *((_OWORD *)v23 + 1);
        *((_OWORD *)v22 + 2) = *((_OWORD *)v23 + 2);
        *((_OWORD *)v22 + 3) = *((_OWORD *)v23 + 3);
        *((_OWORD *)v22 + 4) = *((_OWORD *)v23 + 4);
        *((_OWORD *)v22 + 5) = *((_OWORD *)v23 + 5);
        *((_OWORD *)v22 + 6) = *((_OWORD *)v23 + 6);
        *((_OWORD *)v22 + 7) = *((_OWORD *)v23 + 7);
        v22 += 32;
        v23 += 32;
        --v20;
      }
      while ( v20 );
      *v22 = *v23;
      v8 = RpcCliRenewIpAddressLeaseEx(
             0,
             a1,
             (unsigned int)&v31,
             (unsigned int)&v45,
             v35,
             v34,
             (__int64)v44,
             SourceSize);
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v24 = GetCommandLineW();
        WPP_SF_DDS(v25, 232, v26, v8, a1, (__int64)v24);
      }
      if ( !v8 )
      {
        *v40 = v32;
        *v41 = HIDWORD(v32);
        *v42 = (unsigned int)v33;
        *v43 = DWORD1(v32);
        *v13 = DWORD2(v32);
        v27 = 0x7FFFFFFFFFFFFFFFLL;
        v28 = 0x7FFFFFFFFFFFFFFFLL;
        if ( DWORD1(v33) != -1 )
          v28 = DWORD1(v33);
        *v15 = v28;
        v29 = 0x7FFFFFFFFFFFFFFFLL;
        if ( DWORD2(v33) != -1 )
          v29 = DWORD2(v33);
        *(_QWORD *)v16 = v29;
        if ( HIDWORD(v33) != -1 )
          v27 = HIDWORD(v33);
        *v14 = v27;
      }
    }
  }
LABEL_30:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 233, WPP_e15037783097355a5233924022d92169_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000a4d0  push    rbx
0x18000a4d2  push    rsi
0x18000a4d3  push    rdi
0x18000a4d4  push    r12
0x18000a4d6  push    r13
0x18000a4d8  push    r14
0x18000a4da  push    r15
0x18000a4dc  sub     rsp, 410h
0x18000a4e3  mov     rax, cs:__security_cookie
0x18000a4ea  xor     rax, rsp
0x18000a4ed  mov     [rsp+448h+var_48], rax
0x18000a4f5  mov     [rsp+448h+var_3C8], r9
0x18000a4fd  mov     [rsp+448h+var_3C0], r8
0x18000a505  mov     rdi, rdx
0x18000a508  mov     r15d, ecx
0x18000a50b  mov     [rsp+448h+var_400], ecx
0x18000a50f  mov     rbx, [rsp+448h+Source]
0x18000a517  mov     esi, 100h
0x18000a51c  mov     r8d, esi; Size
0x18000a51f  xor     edx, edx; Val
0x18000a521  lea     rcx, [rsp+448h+Destination]; void *
0x18000a529  call    memset_0
0x18000a52e  xorps   xmm0, xmm0
0x18000a531  movups  [rsp+448h+var_3F8], xmm0
0x18000a536  movups  [rsp+448h+var_3E8], xmm0
0x18000a53b  movups  [rsp+448h+var_3D8], xmm0
0x18000a540  mov     r8d, esi; Size
0x18000a543  xor     edx, edx; Val
0x18000a545  lea     rcx, [rsp+448h+var_154]; void *
0x18000a54d  call    memset_0
0x18000a552  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a559  jz      short loc_18000A56F
0x18000a55b  lea     edx, [rsi-1Ch]
0x18000a55e  mov     ecx, 404h
0x18000a563  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a56a  call    WPP_SF_
0x18000a56f  call    DhcpIsFSEGuestSystem
0x18000a574  test    eax, eax
0x18000a576  jnz     loc_18000A8D4
0x18000a57c  xor     ecx, ecx
0x18000a57e  test    rbx, rbx
0x18000a581  setz    cl
0x18000a584  mov     esi, dword ptr [rsp+448h+SourceSize]
0x18000a58b  test    esi, esi
0x18000a58d  setz    al
0x18000a590  cmp     ecx, eax
0x18000a592  jz      short loc_18000A59E
0x18000a594  mov     ebx, 57h ; 'W'
0x18000a599  jmp     loc_18000A8FD
0x18000a59e  test    rdi, rdi
0x18000a5a1  jz      short loc_18000A594
0x18000a5a3  mov     [rsp+448h+var_268], esi
0x18000a5aa  test    rbx, rbx
0x18000a5ad  jz      short loc_18000A5D8
0x18000a5af  mov     r9, rsi; SourceSize
0x18000a5b2  mov     r8, rbx; Source
0x18000a5b5  mov     edx, 0FFh; DestinationSize
0x18000a5ba  lea     rcx, [rsp+448h+Destination]; Destination
0x18000a5c2  call    memcpy_s
0x18000a5c7  mov     ecx, eax
0x18000a5c9  call    Win32FromErrno
0x18000a5ce  mov     ebx, eax
0x18000a5d0  test    eax, eax
0x18000a5d2  jnz     loc_18000A8FD
0x18000a5d8  mov     eax, [rdi+8]
0x18000a5db  test    eax, eax
0x18000a5dd  jz      short loc_18000A594
0x18000a5df  mov     r8, [rdi]; Source
0x18000a5e2  test    r8, r8
0x18000a5e5  jz      short loc_18000A594
0x18000a5e7  mov     dword ptr [rsp+448h+var_3F8+8], eax
0x18000a5eb  mov     [rsp+448h+var_158], eax
0x18000a5f2  mov     r9d, eax; SourceSize
0x18000a5f5  mov     edx, 0FEh; DestinationSize
0x18000a5fa  lea     rcx, [rsp+448h+var_153]; Destination
0x18000a602  call    memcpy_s
0x18000a607  mov     ecx, eax
0x18000a609  call    Win32FromErrno
0x18000a60e  mov     ebx, eax
0x18000a610  test    eax, eax
0x18000a612  jnz     loc_18000A8FD
0x18000a618  lea     r13, [rdi+18h]
0x18000a61c  mov     [rsp+448h+var_3B8], r13
0x18000a624  mov     eax, [r13+0]
0x18000a628  mov     dword ptr [rsp+448h+var_3E8+8], eax
0x18000a62c  lea     rax, [rdi+10h]
0x18000a630  mov     [rsp+448h+var_398], rax
0x18000a638  mov     eax, [rax]
0x18000a63a  mov     dword ptr [rsp+448h+var_3E8], eax
0x18000a63e  lea     rax, [rdi+1Ch]
0x18000a642  mov     [rsp+448h+var_390], rax
0x18000a64a  mov     eax, [rax]
0x18000a64c  mov     dword ptr [rsp+448h+var_3E8+0Ch], eax
0x18000a650  lea     r14, [rdi+38h]
0x18000a654  mov     [rsp+448h+var_3B0], r14
0x18000a65c  mov     eax, [r14]
0x18000a65f  mov     dword ptr [rsp+448h+var_3D8+0Ch], eax
0x18000a663  lea     rax, [rdi+20h]
0x18000a667  mov     [rsp+448h+var_388], rax
0x18000a66f  mov     eax, [rax]
0x18000a671  mov     dword ptr [rsp+448h+var_3D8], eax
0x18000a675  lea     rax, [rdi+14h]
0x18000a679  mov     [rsp+448h+var_380], rax
0x18000a681  mov     eax, [rax]
0x18000a683  mov     dword ptr [rsp+448h+var_3E8+4], eax
0x18000a687  lea     r12, [rdi+28h]
0x18000a68b  mov     [rsp+448h+var_3A8], r12
0x18000a693  mov     eax, [r12]
0x18000a697  mov     dword ptr [rsp+448h+var_3D8+4], eax
0x18000a69b  add     rdi, 30h ; '0'
0x18000a69f  mov     [rsp+448h+var_3A0], rdi
0x18000a6a7  mov     eax, [rdi]
0x18000a6a9  mov     dword ptr [rsp+448h+var_3D8+8], eax
0x18000a6ad  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a6b4  jz      short loc_18000A6DB
0x18000a6b6  call    cs:__imp_GetCommandLineW
0x18000a6bc  mov     edx, 0E7h
0x18000a6c1  mov     ecx, 404h
0x18000a6c6  mov     [rsp+448h+var_428], rax
0x18000a6cb  mov     r9d, r15d
0x18000a6ce  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a6d5  call    WPP_SF_DS
0x18000a6da  nop
0x18000a6db  lea     rdx, [rsp+448h+var_378]
0x18000a6e3  lea     rax, [rsp+448h+var_268]
0x18000a6eb  mov     ecx, 2
0x18000a6f0  mov     r8d, ecx
0x18000a6f3  lea     r9d, [rcx+7Eh]
0x18000a6f7  movups  xmm0, xmmword ptr [rax]
0x18000a6fa  movups  xmmword ptr [rdx], xmm0
0x18000a6fd  movups  xmm1, xmmword ptr [rax+10h]
0x18000a701  movups  xmmword ptr [rdx+10h], xmm1
0x18000a705  movups  xmm0, xmmword ptr [rax+20h]
0x18000a709  movups  xmmword ptr [rdx+20h], xmm0
0x18000a70d  movups  xmm1, xmmword ptr [rax+30h]
0x18000a711  movups  xmmword ptr [rdx+30h], xmm1
0x18000a715  movups  xmm0, xmmword ptr [rax+40h]
0x18000a719  movups  xmmword ptr [rdx+40h], xmm0
0x18000a71d  movups  xmm1, xmmword ptr [rax+50h]
0x18000a721  movups  xmmword ptr [rdx+50h], xmm1
0x18000a725  movups  xmm0, xmmword ptr [rax+60h]
0x18000a729  movups  xmmword ptr [rdx+60h], xmm0
0x18000a72d  movups  xmm1, xmmword ptr [rax+70h]
0x18000a731  movups  xmmword ptr [rdx+70h], xmm1
0x18000a735  add     rdx, r9
0x18000a738  add     rax, r9
0x18000a73b  sub     r8, 1
0x18000a73f  jnz     short loc_18000A6F7
0x18000a741  mov     eax, [rax]
0x18000a743  mov     [rdx], eax
0x18000a745  lea     rdx, [rsp+448h+var_268]
0x18000a74d  lea     rax, [rsp+448h+var_158]
0x18000a755  movups  xmm0, xmmword ptr [rax]
0x18000a758  movups  xmmword ptr [rdx], xmm0
0x18000a75b  movups  xmm1, xmmword ptr [rax+10h]
0x18000a75f  movups  xmmword ptr [rdx+10h], xmm1
0x18000a763  movups  xmm0, xmmword ptr [rax+20h]
0x18000a767  movups  xmmword ptr [rdx+20h], xmm0
0x18000a76b  movups  xmm1, xmmword ptr [rax+30h]
0x18000a76f  movups  xmmword ptr [rdx+30h], xmm1
0x18000a773  movups  xmm0, xmmword ptr [rax+40h]
0x18000a777  movups  xmmword ptr [rdx+40h], xmm0
0x18000a77b  movups  xmm1, xmmword ptr [rax+50h]
0x18000a77f  movups  xmmword ptr [rdx+50h], xmm1
0x18000a783  movups  xmm0, xmmword ptr [rax+60h]
0x18000a787  movups  xmmword ptr [rdx+60h], xmm0
0x18000a78b  movups  xmm1, xmmword ptr [rax+70h]
0x18000a78f  movups  xmmword ptr [rdx+70h], xmm1
0x18000a793  add     rdx, r9
0x18000a796  add     rax, r9
0x18000a799  sub     rcx, 1
0x18000a79d  jnz     short loc_18000A755
0x18000a79f  mov     eax, [rax]
0x18000a7a1  mov     [rdx], eax
0x18000a7a3  mov     [rsp+448h+var_410], esi
0x18000a7a7  lea     rax, [rsp+448h+var_378]
0x18000a7af  mov     [rsp+448h+var_418], rax
0x18000a7b4  mov     rax, [rsp+448h+var_3C8]
0x18000a7bc  mov     [rsp+448h+var_420], rax
0x18000a7c1  mov     rax, [rsp+448h+var_3C0]
0x18000a7c9  mov     [rsp+448h+var_428], rax
0x18000a7ce  lea     r9, [rsp+448h+var_268]
0x18000a7d6  lea     r8, [rsp+448h+var_3F8]
0x18000a7db  mov     edx, r15d
0x18000a7de  call    RpcCliRenewIpAddressLeaseEx
0x18000a7e3  mov     ebx, eax
0x18000a7e5  mov     [rsp+448h+var_408], eax
0x18000a7e9  jmp     short loc_18000A826
0x18000a7eb  mov     ebx, eax
0x18000a7ed  mov     [rsp+448h+var_408], eax
0x18000a7f1  call    cs:__imp_GetCommandLineW
0x18000a7f7  mov     rdx, rax
0x18000a7fa  mov     ecx, ebx
0x18000a7fc  call    TraceRpcException
0x18000a801  mov     r15d, [rsp+448h+var_400]
0x18000a806  mov     r13, [rsp+448h+var_3B8]
0x18000a80e  mov     r14, [rsp+448h+var_3B0]
0x18000a816  mov     r12, [rsp+448h+var_3A8]
0x18000a81e  mov     rdi, [rsp+448h+var_3A0]
0x18000a826  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a82d  jz      short loc_18000A84C
0x18000a82f  call    cs:__imp_GetCommandLineW
0x18000a835  mov     edx, 0E8h
0x18000a83a  mov     [rsp+448h+var_420], rax
0x18000a83f  mov     dword ptr [rsp+448h+var_428], r15d
0x18000a844  mov     r9d, ebx
0x18000a847  call    WPP_SF_DDS
0x18000a84c  test    ebx, ebx
0x18000a84e  jnz     loc_18000A8FD
0x18000a854  mov     eax, dword ptr [rsp+448h+var_3E8]
0x18000a858  mov     rcx, [rsp+448h+var_398]
0x18000a860  mov     [rcx], eax
0x18000a862  mov     eax, dword ptr [rsp+448h+var_3E8+0Ch]
0x18000a866  mov     rcx, [rsp+448h+var_390]
0x18000a86e  mov     [rcx], eax
0x18000a870  mov     eax, dword ptr [rsp+448h+var_3D8]
0x18000a874  mov     rcx, [rsp+448h+var_388]
0x18000a87c  mov     [rcx], rax
0x18000a87f  mov     eax, dword ptr [rsp+448h+var_3E8+4]
0x18000a883  mov     rcx, [rsp+448h+var_380]
0x18000a88b  mov     [rcx], eax
0x18000a88d  mov     eax, dword ptr [rsp+448h+var_3E8+8]
0x18000a891  mov     [r13+0], eax
0x18000a895  or      edx, 0FFFFFFFFh
0x18000a898  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a8a2  cmp     dword ptr [rsp+448h+var_3D8+4], edx
0x18000a8a6  mov     rcx, rax
0x18000a8a9  jz      short loc_18000A8AF
0x18000a8ab  mov     ecx, dword ptr [rsp+448h+var_3D8+4]
0x18000a8af  mov     [r12], rcx
0x18000a8b3  cmp     dword ptr [rsp+448h+var_3D8+8], edx
0x18000a8b7  mov     rcx, rax
0x18000a8ba  jz      short loc_18000A8C0
0x18000a8bc  mov     ecx, dword ptr [rsp+448h+var_3D8+8]
0x18000a8c0  mov     [rdi], rcx
0x18000a8c3  cmp     dword ptr [rsp+448h+var_3D8+0Ch], edx
0x18000a8c7  jnz     short loc_18000A8CE
0x18000a8c9  mov     [r14], rax
0x18000a8cc  jmp     short loc_18000A8FD
0x18000a8ce  mov     eax, dword ptr [rsp+448h+var_3D8+0Ch]
0x18000a8d2  jmp     short loc_18000A8C9
0x18000a8d4  mov     ebx, 32h ; '2'
0x18000a8d9  lea     ecx, [rbx-30h]
0x18000a8dc  test    byte ptr cs:xmmword_18001E1E0, cl
0x18000a8e2  jz      short loc_18000A8FD
0x18000a8e4  mov     edx, 0E5h
0x18000a8e9  mov     ecx, 401h
0x18000a8ee  mov     r9d, ebx
0x18000a8f1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a8f8  call    WPP_SF_d
0x18000a8fd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a904  jz      short loc_18000A91F
0x18000a906  mov     edx, 0E9h
0x18000a90b  mov     ecx, 404h
0x18000a910  mov     r9d, ebx
0x18000a913  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a91a  call    WPP_SF_d
0x18000a91f  mov     eax, ebx
0x18000a921  mov     rcx, [rsp+448h+var_48]
0x18000a929  xor     rcx, rsp; StackCookie
0x18000a92c  call    __security_check_cookie
0x18000a931  add     rsp, 410h
0x18000a938  pop     r15
0x18000a93a  pop     r14
0x18000a93c  pop     r13
0x18000a93e  pop     r12
0x18000a940  pop     rdi
0x18000a941  pop     rsi
0x18000a942  pop     rbx
0x18000a943  retn
0x180010d30  push    rbp
0x180010d32  sub     rsp, 40h
0x180010d36  mov     rbp, rdx
0x180010d39  mov     rcx, [rcx]
0x180010d3c  mov     ecx, [rcx]; ExceptionCode
0x180010d3e  call    cs:__imp_I_RpcExceptionFilter
0x180010d44  nop
0x180010d45  add     rsp, 40h
0x180010d49  pop     rbp
0x180010d4a  retn
```

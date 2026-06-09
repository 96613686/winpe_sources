# DhcpReleaseIpAddressLeaseEx

- ea: `0x180009d40`
- end: `0x18000a177`
- name: `DhcpReleaseIpAddressLeaseEx`
- size: `1079`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009c90`

## callees

- `0x180002760`
- `0x1800048c0`
- `0x180005162`
- `0x1800057c0`
- `0x180009d40`
- `0x18000d5c8`
- `0x18000f4ec`
- `0x180010154`
- `0x1800110f8`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180009f09`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a02a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a062`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180009f09`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a02a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a062`

## pseudocode

```c
__int64 __fastcall DhcpReleaseIpAddressLeaseEx(int a1, __int64 a2, const void *a3, unsigned int a4)
{
  rsize_t v4; // rsi
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
  __int128 v31; // [rsp+40h] [rbp-3E8h] BYREF
  __int128 v32; // [rsp+50h] [rbp-3D8h]
  __int128 v33; // [rsp+60h] [rbp-3C8h]
  __int64 v34; // [rsp+70h] [rbp-3B8h]
  __int64 v35; // [rsp+78h] [rbp-3B0h]
  __int64 v36; // [rsp+80h] [rbp-3A8h]
  _DWORD *v37; // [rsp+88h] [rbp-3A0h]
  _DWORD *v38; // [rsp+90h] [rbp-398h]
  _DWORD *v39; // [rsp+98h] [rbp-390h]
  _QWORD *v40; // [rsp+A0h] [rbp-388h]
  _DWORD *v41; // [rsp+A8h] [rbp-380h]
  _BYTE v42[272]; // [rsp+B0h] [rbp-378h] BYREF
  int v43; // [rsp+1C0h] [rbp-268h] BYREF
  _BYTE Destination[268]; // [rsp+1C4h] [rbp-264h] BYREF
  unsigned int v45; // [rsp+2D0h] [rbp-158h] BYREF
  char v46; // [rsp+2D4h] [rbp-154h] BYREF
  _BYTE v47[267]; // [rsp+2D5h] [rbp-153h] BYREF

  v4 = a4;
  memset_0(Destination, 0, 0x100u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  memset_0(&v46, 0, 0x100u);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 237, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v8 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 238, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    if ( (a3 == 0) != ((_DWORD)v4 == 0) || !a2 )
      goto LABEL_5;
    v43 = v4;
    if ( a3 )
    {
      v9 = memcpy_s(Destination, 0xFFu, a3, v4);
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
    v45 = v10;
    v12 = memcpy_s(v47, 0xFEu, v11, v10);
    v8 = Win32FromErrno(v12);
    if ( !v8 )
    {
      v13 = (_DWORD *)(a2 + 24);
      v34 = a2 + 24;
      DWORD2(v32) = *(_DWORD *)(a2 + 24);
      v38 = (_DWORD *)(a2 + 16);
      LODWORD(v32) = *(_DWORD *)(a2 + 16);
      v39 = (_DWORD *)(a2 + 28);
      HIDWORD(v32) = *(_DWORD *)(a2 + 28);
      v14 = (__int64 *)(a2 + 56);
      v35 = a2 + 56;
      HIDWORD(v33) = *(_DWORD *)(a2 + 56);
      v40 = (_QWORD *)(a2 + 32);
      LODWORD(v33) = *(_DWORD *)(a2 + 32);
      v41 = (_DWORD *)(a2 + 20);
      DWORD1(v32) = *(_DWORD *)(a2 + 20);
      v15 = (__int64 *)(a2 + 40);
      v36 = a2 + 40;
      DWORD1(v33) = *(_DWORD *)(a2 + 40);
      v16 = (_DWORD *)(a2 + 48);
      v37 = v16;
      DWORD2(v33) = *v16;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_DS(1028, 239, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
      v18 = v42;
      v19 = &v43;
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
      v22 = &v43;
      v23 = (int *)&v45;
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
      v8 = RpcCliReleaseIpAddressLeaseEx(0, a1, (unsigned int)&v31, (unsigned int)&v43, (__int64)v42, v4);
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v24 = GetCommandLineW();
        WPP_SF_DDS(v25, 240, v26, v8, a1, (__int64)v24);
      }
      if ( !v8 )
      {
        *v38 = v32;
        *v39 = HIDWORD(v32);
        *v40 = (unsigned int)v33;
        *v41 = DWORD1(v32);
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
    WPP_SF_d(1028, 241, WPP_e15037783097355a5233924022d92169_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180009d40  push    rbx
0x180009d42  push    rsi
0x180009d43  push    rdi
0x180009d44  push    r12
0x180009d46  push    r13
0x180009d48  push    r14
0x180009d4a  push    r15
0x180009d4c  sub     rsp, 3F0h
0x180009d53  mov     rax, cs:__security_cookie
0x180009d5a  xor     rax, rsp
0x180009d5d  mov     [rsp+428h+var_48], rax
0x180009d65  mov     esi, r9d
0x180009d68  mov     rbx, r8
0x180009d6b  mov     rdi, rdx
0x180009d6e  mov     r15d, ecx
0x180009d71  mov     [rsp+428h+var_3F0], ecx
0x180009d75  mov     r14d, 100h
0x180009d7b  mov     r8d, r14d; Size
0x180009d7e  xor     edx, edx; Val
0x180009d80  lea     rcx, [rsp+428h+Destination]; void *
0x180009d88  call    memset_0
0x180009d8d  xorps   xmm0, xmm0
0x180009d90  movups  [rsp+428h+var_3E8], xmm0
0x180009d95  movups  [rsp+428h+var_3D8], xmm0
0x180009d9a  movups  [rsp+428h+var_3C8], xmm0
0x180009d9f  mov     r8d, r14d; Size
0x180009da2  xor     edx, edx; Val
0x180009da4  lea     rcx, [rsp+428h+var_154]; void *
0x180009dac  call    memset_0
0x180009db1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180009db8  jz      short loc_180009DCF
0x180009dba  lea     edx, [r14-13h]
0x180009dbe  mov     ecx, 404h
0x180009dc3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009dca  call    WPP_SF_
0x180009dcf  call    DhcpIsFSEGuestSystem
0x180009dd4  test    eax, eax
0x180009dd6  jnz     loc_18000A107
0x180009ddc  xor     ecx, ecx
0x180009dde  test    esi, esi
0x180009de0  setz    cl
0x180009de3  test    rbx, rbx
0x180009de6  setz    al
0x180009de9  cmp     eax, ecx
0x180009deb  jz      short loc_180009DF7
0x180009ded  mov     ebx, 57h ; 'W'
0x180009df2  jmp     loc_18000A130
0x180009df7  test    rdi, rdi
0x180009dfa  jz      short loc_180009DED
0x180009dfc  mov     [rsp+428h+var_268], esi
0x180009e03  test    rbx, rbx
0x180009e06  jz      short loc_180009E31
0x180009e08  mov     r9, rsi; SourceSize
0x180009e0b  mov     r8, rbx; Source
0x180009e0e  mov     edx, 0FFh; DestinationSize
0x180009e13  lea     rcx, [rsp+428h+Destination]; Destination
0x180009e1b  call    memcpy_s
0x180009e20  mov     ecx, eax
0x180009e22  call    Win32FromErrno
0x180009e27  mov     ebx, eax
0x180009e29  test    eax, eax
0x180009e2b  jnz     loc_18000A130
0x180009e31  mov     eax, [rdi+8]
0x180009e34  test    eax, eax
0x180009e36  jz      short loc_180009DED
0x180009e38  mov     r8, [rdi]; Source
0x180009e3b  test    r8, r8
0x180009e3e  jz      short loc_180009DED
0x180009e40  mov     dword ptr [rsp+428h+var_3E8+8], eax
0x180009e44  mov     [rsp+428h+var_158], eax
0x180009e4b  mov     r9d, eax; SourceSize
0x180009e4e  mov     edx, 0FEh; DestinationSize
0x180009e53  lea     rcx, [rsp+428h+var_153]; Destination
0x180009e5b  call    memcpy_s
0x180009e60  mov     ecx, eax
0x180009e62  call    Win32FromErrno
0x180009e67  mov     ebx, eax
0x180009e69  test    eax, eax
0x180009e6b  jnz     loc_18000A130
0x180009e71  lea     r13, [rdi+18h]
0x180009e75  mov     [rsp+428h+var_3B8], r13
0x180009e7a  mov     eax, [r13+0]
0x180009e7e  mov     dword ptr [rsp+428h+var_3D8+8], eax
0x180009e82  lea     rax, [rdi+10h]
0x180009e86  mov     [rsp+428h+var_398], rax
0x180009e8e  mov     eax, [rax]
0x180009e90  mov     dword ptr [rsp+428h+var_3D8], eax
0x180009e94  lea     rax, [rdi+1Ch]
0x180009e98  mov     [rsp+428h+var_390], rax
0x180009ea0  mov     eax, [rax]
0x180009ea2  mov     dword ptr [rsp+428h+var_3D8+0Ch], eax
0x180009ea6  lea     r14, [rdi+38h]
0x180009eaa  mov     [rsp+428h+var_3B0], r14
0x180009eaf  mov     eax, [r14]
0x180009eb2  mov     dword ptr [rsp+428h+var_3C8+0Ch], eax
0x180009eb6  lea     rax, [rdi+20h]
0x180009eba  mov     [rsp+428h+var_388], rax
0x180009ec2  mov     eax, [rax]
0x180009ec4  mov     dword ptr [rsp+428h+var_3C8], eax
0x180009ec8  lea     rax, [rdi+14h]
0x180009ecc  mov     [rsp+428h+var_380], rax
0x180009ed4  mov     eax, [rax]
0x180009ed6  mov     dword ptr [rsp+428h+var_3D8+4], eax
0x180009eda  lea     r12, [rdi+28h]
0x180009ede  mov     [rsp+428h+var_3A8], r12
0x180009ee6  mov     eax, [r12]
0x180009eea  mov     dword ptr [rsp+428h+var_3C8+4], eax
0x180009eee  add     rdi, 30h ; '0'
0x180009ef2  mov     [rsp+428h+var_3A0], rdi
0x180009efa  mov     eax, [rdi]
0x180009efc  mov     dword ptr [rsp+428h+var_3C8+8], eax
0x180009f00  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180009f07  jz      short loc_180009F2E
0x180009f09  call    cs:__imp_GetCommandLineW
0x180009f0f  mov     edx, 0EFh
0x180009f14  mov     ecx, 404h
0x180009f19  mov     [rsp+428h+var_408], rax
0x180009f1e  mov     r9d, r15d
0x180009f21  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009f28  call    WPP_SF_DS
0x180009f2d  nop
0x180009f2e  lea     rdx, [rsp+428h+var_378]
0x180009f36  lea     rax, [rsp+428h+var_268]
0x180009f3e  mov     ecx, 2
0x180009f43  mov     r8d, ecx
0x180009f46  lea     r9d, [rcx+7Eh]
0x180009f4a  movups  xmm0, xmmword ptr [rax]
0x180009f4d  movups  xmmword ptr [rdx], xmm0
0x180009f50  movups  xmm1, xmmword ptr [rax+10h]
0x180009f54  movups  xmmword ptr [rdx+10h], xmm1
0x180009f58  movups  xmm0, xmmword ptr [rax+20h]
0x180009f5c  movups  xmmword ptr [rdx+20h], xmm0
0x180009f60  movups  xmm1, xmmword ptr [rax+30h]
0x180009f64  movups  xmmword ptr [rdx+30h], xmm1
0x180009f68  movups  xmm0, xmmword ptr [rax+40h]
0x180009f6c  movups  xmmword ptr [rdx+40h], xmm0
0x180009f70  movups  xmm1, xmmword ptr [rax+50h]
0x180009f74  movups  xmmword ptr [rdx+50h], xmm1
0x180009f78  movups  xmm0, xmmword ptr [rax+60h]
0x180009f7c  movups  xmmword ptr [rdx+60h], xmm0
0x180009f80  movups  xmm1, xmmword ptr [rax+70h]
0x180009f84  movups  xmmword ptr [rdx+70h], xmm1
0x180009f88  add     rdx, r9
0x180009f8b  add     rax, r9
0x180009f8e  sub     r8, 1
0x180009f92  jnz     short loc_180009F4A
0x180009f94  mov     eax, [rax]
0x180009f96  mov     [rdx], eax
0x180009f98  lea     rdx, [rsp+428h+var_268]
0x180009fa0  lea     rax, [rsp+428h+var_158]
0x180009fa8  movups  xmm0, xmmword ptr [rax]
0x180009fab  movups  xmmword ptr [rdx], xmm0
0x180009fae  movups  xmm1, xmmword ptr [rax+10h]
0x180009fb2  movups  xmmword ptr [rdx+10h], xmm1
0x180009fb6  movups  xmm0, xmmword ptr [rax+20h]
0x180009fba  movups  xmmword ptr [rdx+20h], xmm0
0x180009fbe  movups  xmm1, xmmword ptr [rax+30h]
0x180009fc2  movups  xmmword ptr [rdx+30h], xmm1
0x180009fc6  movups  xmm0, xmmword ptr [rax+40h]
0x180009fca  movups  xmmword ptr [rdx+40h], xmm0
0x180009fce  movups  xmm1, xmmword ptr [rax+50h]
0x180009fd2  movups  xmmword ptr [rdx+50h], xmm1
0x180009fd6  movups  xmm0, xmmword ptr [rax+60h]
0x180009fda  movups  xmmword ptr [rdx+60h], xmm0
0x180009fde  movups  xmm1, xmmword ptr [rax+70h]
0x180009fe2  movups  xmmword ptr [rdx+70h], xmm1
0x180009fe6  add     rdx, r9
0x180009fe9  add     rax, r9
0x180009fec  sub     rcx, 1
0x180009ff0  jnz     short loc_180009FA8
0x180009ff2  mov     eax, [rax]
0x180009ff4  mov     [rdx], eax
0x180009ff6  mov     dword ptr [rsp+428h+var_400], esi
0x180009ffa  lea     rax, [rsp+428h+var_378]
0x18000a002  mov     [rsp+428h+var_408], rax
0x18000a007  lea     r9, [rsp+428h+var_268]
0x18000a00f  lea     r8, [rsp+428h+var_3E8]
0x18000a014  mov     edx, r15d
0x18000a017  call    RpcCliReleaseIpAddressLeaseEx
0x18000a01c  mov     ebx, eax
0x18000a01e  mov     [rsp+428h+var_3F8], eax
0x18000a022  jmp     short loc_18000A059
0x18000a024  mov     ebx, eax
0x18000a026  mov     [rsp+428h+var_3F8], eax
0x18000a02a  call    cs:__imp_GetCommandLineW
0x18000a030  mov     rdx, rax
0x18000a033  mov     ecx, ebx
0x18000a035  call    TraceRpcException
0x18000a03a  mov     r15d, [rsp+428h+var_3F0]
0x18000a03f  mov     r13, [rsp+428h+var_3B8]
0x18000a044  mov     r14, [rsp+428h+var_3B0]
0x18000a049  mov     r12, [rsp+428h+var_3A8]
0x18000a051  mov     rdi, [rsp+428h+var_3A0]
0x18000a059  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a060  jz      short loc_18000A07F
0x18000a062  call    cs:__imp_GetCommandLineW
0x18000a068  mov     edx, 0F0h
0x18000a06d  mov     [rsp+428h+var_400], rax
0x18000a072  mov     dword ptr [rsp+428h+var_408], r15d
0x18000a077  mov     r9d, ebx
0x18000a07a  call    WPP_SF_DDS
0x18000a07f  test    ebx, ebx
0x18000a081  jnz     loc_18000A130
0x18000a087  mov     eax, dword ptr [rsp+428h+var_3D8]
0x18000a08b  mov     rcx, [rsp+428h+var_398]
0x18000a093  mov     [rcx], eax
0x18000a095  mov     eax, dword ptr [rsp+428h+var_3D8+0Ch]
0x18000a099  mov     rcx, [rsp+428h+var_390]
0x18000a0a1  mov     [rcx], eax
0x18000a0a3  mov     eax, dword ptr [rsp+428h+var_3C8]
0x18000a0a7  mov     rcx, [rsp+428h+var_388]
0x18000a0af  mov     [rcx], rax
0x18000a0b2  mov     eax, dword ptr [rsp+428h+var_3D8+4]
0x18000a0b6  mov     rcx, [rsp+428h+var_380]
0x18000a0be  mov     [rcx], eax
0x18000a0c0  mov     eax, dword ptr [rsp+428h+var_3D8+8]
0x18000a0c4  mov     [r13+0], eax
0x18000a0c8  or      edx, 0FFFFFFFFh
0x18000a0cb  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a0d5  cmp     dword ptr [rsp+428h+var_3C8+4], edx
0x18000a0d9  mov     rcx, rax
0x18000a0dc  jz      short loc_18000A0E2
0x18000a0de  mov     ecx, dword ptr [rsp+428h+var_3C8+4]
0x18000a0e2  mov     [r12], rcx
0x18000a0e6  cmp     dword ptr [rsp+428h+var_3C8+8], edx
0x18000a0ea  mov     rcx, rax
0x18000a0ed  jz      short loc_18000A0F3
0x18000a0ef  mov     ecx, dword ptr [rsp+428h+var_3C8+8]
0x18000a0f3  mov     [rdi], rcx
0x18000a0f6  cmp     dword ptr [rsp+428h+var_3C8+0Ch], edx
0x18000a0fa  jnz     short loc_18000A101
0x18000a0fc  mov     [r14], rax
0x18000a0ff  jmp     short loc_18000A130
0x18000a101  mov     eax, dword ptr [rsp+428h+var_3C8+0Ch]
0x18000a105  jmp     short loc_18000A0FC
0x18000a107  mov     ebx, 32h ; '2'
0x18000a10c  lea     ecx, [rbx-30h]
0x18000a10f  test    byte ptr cs:xmmword_18001E1E0, cl
0x18000a115  jz      short loc_18000A130
0x18000a117  mov     edx, 0EEh
0x18000a11c  mov     ecx, 401h
0x18000a121  mov     r9d, ebx
0x18000a124  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a12b  call    WPP_SF_d
0x18000a130  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a137  jz      short loc_18000A152
0x18000a139  mov     edx, 0F1h
0x18000a13e  mov     ecx, 404h
0x18000a143  mov     r9d, ebx
0x18000a146  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a14d  call    WPP_SF_d
0x18000a152  mov     eax, ebx
0x18000a154  mov     rcx, [rsp+428h+var_48]
0x18000a15c  xor     rcx, rsp; StackCookie
0x18000a15f  call    __security_check_cookie
0x18000a164  add     rsp, 3F0h
0x18000a16b  pop     r15
0x18000a16d  pop     r14
0x18000a16f  pop     r13
0x18000a171  pop     r12
0x18000a173  pop     rdi
0x18000a174  pop     rsi
0x18000a175  pop     rbx
0x18000a176  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```

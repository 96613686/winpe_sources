# EapProcessEaphostSendPacket

- ea: `0x180006bd0`
- end: `0x180007497`
- name: `EapProcessEaphostSendPacket`
- size: `2247`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800067e0`

## callees

- `0x1800053e0`
- `0x180005440`
- `0x180006bd0`
- `0x1800074a0`
- `0x180007f60`
- `0x180010ae0`
- `0x180014030`
- `0x180018a90`
- `0x18001d208`
- `0x180020250`
- `0x180020aea`
- `0x1800214f0`
- `0x180025740`
- `0x180027dec`
- `0x180028054`
- `0x18002f705`
- `0x180030010`

## import_xrefs

- `eappprxy!EapHostPeerGetSendPacket` at `0x180006cac`
- `eappprxy!EapHostPeerGetSendPacket` at `0x180006cac`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800071d5`
- `eappprxy!EapHostPeerFreeEapError` at `0x1800071d5`
- `MobileNetworking!ReleaseWriteLock` at `0x180007341`
- `MobileNetworking!ReleaseWriteLock` at `0x180007341`
- `MobileNetworking!AcquireWriteLock` at `0x1800073b1`
- `MobileNetworking!AcquireWriteLock` at `0x1800073b1`
- `MobileNetworking!AllocateMemory` at `0x180007043`
- `MobileNetworking!AllocateMemory` at `0x180007043`
- `MobileNetworking!FreeMemory` at `0x180007122`
- `MobileNetworking!FreeMemory` at `0x180007122`

## pseudocode

```c
__int64 __fastcall EapProcessEaphostSendPacket(EAP_SESSIONID *a1)
{
  __int64 v1; // rax
  unsigned int v3; // r13d
  _QWORD *v4; // rcx
  DWORD SendPacket; // ebx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  EAP_ERROR *v8; // rsi
  unsigned int v9; // r14d
  int v10; // eax
  size_t v11; // rsi
  int v12; // ecx
  int v13; // r8d
  _QWORD *v14; // rbx
  char v15; // r15
  unsigned int v16; // r14d
  int v17; // r12d
  __int64 EapPacketTypeDescription; // rax
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdi
  BYTE *v23; // r15
  unsigned int v24; // r12d
  _QWORD *v25; // rcx
  EAP_ERROR *v26; // rdi
  _BYTE *v28; // rcx
  _BYTE *v29; // r13
  _QWORD *v30; // rcx
  unsigned int v31; // r12d
  __int64 v32; // rbx
  __int64 v33; // r15
  _QWORD *v34; // rcx
  __int64 v35; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE *v36; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-A8h]
  __int64 v39; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE *v40; // [rsp+70h] [rbp-98h] BYREF
  DWORD pcbSendPacket[2]; // [rsp+78h] [rbp-90h] BYREF
  BYTE *ppSendPacket; // [rsp+80h] [rbp-88h] BYREF
  EAP_ERROR *ppEapError; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v44[16]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE **v45; // [rsp+A8h] [rbp-60h]
  __int64 v46; // [rsp+B0h] [rbp-58h]
  unsigned int *v47; // [rsp+B8h] [rbp-50h]
  __int64 v48; // [rsp+C0h] [rbp-48h]
  __int64 *v49; // [rsp+C8h] [rbp-40h]
  __int64 v50; // [rsp+D0h] [rbp-38h]
  __int64 *v51; // [rsp+D8h] [rbp-30h]
  __int64 v52; // [rsp+E0h] [rbp-28h]
  _BYTE **v53; // [rsp+E8h] [rbp-20h]
  __int64 v54; // [rsp+F0h] [rbp-18h]
  _BYTE v55[256]; // [rsp+F8h] [rbp-10h] BYREF

  v1 = *(_QWORD *)a1;
  v37 = 9;
  v3 = *(_DWORD *)(v1 + 20);
  ppSendPacket = 0;
  pcbSendPacket[0] = 0;
  ppEapError = 0;
  LOBYTE(v35) = 0;
  LODWORD(v36) = 0;
  v38 = v3;
  memset_0(v55, 0, sizeof(v55));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 194, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 0x10) != 0 )
      WPP_SF_d(v4[7], 195, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3);
  }
  SendPacket = EapHostPeerGetSendPacket(a1[2], pcbSendPacket, &ppSendPacket, &ppEapError);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 196, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = ppEapError;
  v9 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v7[7], 172, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( SendPacket )
  {
    v10 = EapProcessEaphostFailure(a1, SendPacket, v6, v8);
    if ( !v10 )
    {
LABEL_18:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_69;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 173, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9, v10);
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 174, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, 0);
    v7 = WPP_GLOBAL_Control;
  }
  if ( SendPacket )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
    {
      WPP_SF_dD(v7[7], 197, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3, SendPacket);
LABEL_68:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_69;
    }
    goto LABEL_69;
  }
  v11 = LOWORD(pcbSendPacket[0]);
  if ( (unsigned int)ParseEapPacket(
                       v3,
                       LOWORD(pcbSendPacket[0]),
                       (_DWORD)ppSendPacket,
                       (unsigned int)&v35,
                       (__int64)&v37,
                       (__int64)&v36) )
    goto LABEL_41;
  v14 = WPP_GLOBAL_Control;
  v15 = v35;
  v16 = v37;
  v17 = (int)v36;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
  {
    EapPacketTypeDescription = GetEapPacketTypeDescription(v37);
    WPP_SF_ddSdd(
      v14[7],
      198,
      (unsigned int)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids,
      v3,
      v11,
      EapPacketTypeDescription,
      v15,
      v17);
    v14 = WPP_GLOBAL_Control;
  }
  if ( (byte_18003DF41 & 0x40) != 0 )
  {
    LODWORD(v40) = v17;
    v45 = &v36;
    LOBYTE(v35) = v15;
    v47 = &v37;
    LODWORD(v39) = v16;
    v49 = &v39;
    v51 = &v35;
    v53 = &v40;
    LOWORD(v37) = v11;
    LODWORD(v36) = v3;
    v46 = 4;
    v48 = 2;
    v50 = 4;
    v52 = 1;
    v54 = 4;
    McGenEventWrite_EtwEventWriteTransfer(v12, (unsigned int)"@", v13, 6, (__int64)v44);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v16 == 6 && (unsigned int)v11 > 5 )
  {
    v19 = 255;
    if ( v11 - 5 <= 0xFF )
      v19 = v11 - 5;
    memcpy_0(v55, ppSendPacket + 5, v19);
    v55[255] = 0;
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 68) & 0x20) != 0 )
    {
      WPP_SF_ds(v14[7], 199, (unsigned int)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3, (__int64)v55);
      v14 = WPP_GLOBAL_Control;
    }
    if ( (byte_18003DF41 & 0x40) != 0 )
    {
      McTemplateU0qs_EtwEventWriteTransfer(v21, v20, v3, v55);
LABEL_41:
      v14 = WPP_GLOBAL_Control;
    }
  }
  v22 = *(_QWORD *)a1;
  v23 = ppSendPacket;
  v36 = 0;
  v24 = *(_DWORD *)(v22 + 20);
  LODWORD(v39) = v24;
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v14[7], 31, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  v40 = 0;
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 17) & 0x800) != 0 )
    WPP_SF_(v14[7], 25, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
  v36 = 0;
  SendPacket = AllocateMemory((unsigned __int16)(v11 + 4), &v40, "AllocateEapolPacket", 333);
  if ( !SendPacket )
  {
    *v40 = 1;
    v36 = v40;
    goto LABEL_53;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_58:
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 68) & 1) != 0 )
      WPP_SF_dd(v25[7], 32, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v24, SendPacket);
    goto LABEL_61;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v24, SendPacket);
LABEL_53:
    v25 = WPP_GLOBAL_Control;
  }
  if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v25[7], 27, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, SendPacket);
    v25 = WPP_GLOBAL_Control;
  }
  if ( SendPacket )
    goto LABEL_58;
  v36[1] = 0;
  v28 = v36;
  v36[2] = BYTE1(v11);
  v28[3] = v11;
  memcpy_0(v36 + 4, v23, v11);
  v29 = v36;
  LODWORD(v40) = *(_DWORD *)(v22 + 20);
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
    v30 = WPP_GLOBAL_Control;
  }
  v31 = *(_DWORD *)(v22 + 20);
  v32 = *(_QWORD *)(v22 + 192);
  v33 = *(_QWORD *)(v22 + 2368);
  if ( v30 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v30 + 17) & 0x800) != 0 )
    {
      WPP_SF_(v30[7], 52, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v30 = WPP_GLOBAL_Control;
    }
    if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 68) & 0x20) != 0 )
      WPP_SF_dd(v30[7], 53, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v31, (unsigned __int16)(v11 + 4));
  }
  ReleaseWriteLock(v22, v22 + 2896, "MSMSendOneXPacket", 537);
  SendPacket = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *))(v22 + 2288))(
                 v32,
                 v33,
                 (unsigned __int16)(v11 + 4),
                 v29);
  if ( SendPacket
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v31, SendPacket);
  }
  AcquireWriteLock(v22, v22 + 2896, "MSMSendOneXPacket", 548);
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, SendPacket);
    v34 = WPP_GLOBAL_Control;
  }
  if ( !SendPacket )
    goto LABEL_100;
  ++*(_DWORD *)(v22 + 164);
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        29,
        WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids,
        (unsigned int)v40,
        SendPacket);
      v34 = WPP_GLOBAL_Control;
    }
LABEL_100:
    if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(v34[7], 30, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, SendPacket);
      v34 = WPP_GLOBAL_Control;
    }
  }
  if ( SendPacket && v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 68) & 1) != 0 )
    WPP_SF_dd(v34[7], 33, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, (unsigned int)v39, SendPacket);
  v3 = v38;
LABEL_61:
  FreeMemory(&v36, "SendEapPacket", 399);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, SendPacket);
    v7 = WPP_GLOBAL_Control;
  }
  if ( SendPacket && v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
  {
    WPP_SF_dd(v7[7], 200, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3, SendPacket);
    goto LABEL_68;
  }
LABEL_69:
  v26 = ppEapError;
  if ( !ppEapError )
  {
LABEL_76:
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
      WPP_SF_D(v7[7], 201, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, SendPacket);
    return SendPacket;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 0x10) != 0 )
    WPP_SF_d(v7[7], 11, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3);
  EapHostPeerFreeEapError(v26);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3);
      v7 = WPP_GLOBAL_Control;
    }
    goto LABEL_76;
  }
  return SendPacket;
}

```

## disassembly

```asm
0x180006bd0  mov     r11, rsp
0x180006bd3  push    rbp
0x180006bd4  push    rbx
0x180006bd5  push    rdi
0x180006bd6  push    r12
0x180006bd8  push    r13
0x180006bda  lea     rbp, [r11-128h]
0x180006be1  sub     rsp, 200h
0x180006be8  mov     rax, cs:__security_cookie
0x180006bef  xor     rax, rsp
0x180006bf2  mov     [rbp+120h+var_30], rax
0x180006bf9  mov     rax, [rcx]
0x180006bfc  mov     rdi, rcx
0x180006bff  mov     [r11+10h], rsi
0x180006c03  lea     rcx, [rbp+120h+var_130]; void *
0x180006c07  xor     edx, edx; Val
0x180006c09  mov     [r11+18h], r14
0x180006c0d  mov     r8d, 100h; Size
0x180006c13  mov     [rsp+220h+var_1D0], 9
0x180006c1b  mov     r13d, [rax+14h]
0x180006c1f  xor     eax, eax
0x180006c21  mov     [rsp+220h+ppSendPacket], rax
0x180006c26  mov     [rsp+220h+pcbSendPacket], eax
0x180006c2a  mov     [rbp+120h+ppEapError], rax
0x180006c2e  mov     byte ptr [rsp+220h+var_1E0], al
0x180006c32  mov     dword ptr [rsp+220h+var_1D8], eax
0x180006c36  mov     [rsp+220h+var_1C8], r13d
0x180006c3b  call    memset_0
0x180006c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c47  lea     r12, WPP_GLOBAL_Control
0x180006c4e  cmp     rcx, r12
0x180006c51  jz      short loc_180006C9B
0x180006c53  test    dword ptr [rcx+44h], 800h
0x180006c5a  jz      short loc_180006C78
0x180006c5c  mov     rcx, [rcx+38h]
0x180006c60  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006c67  mov     edx, 0C2h
0x180006c6c  call    WPP_SF_
0x180006c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c78  cmp     rcx, r12
0x180006c7b  jz      short loc_180006C9B
0x180006c7d  test    byte ptr [rcx+44h], 10h
0x180006c81  jz      short loc_180006C9B
0x180006c83  mov     rcx, [rcx+38h]
0x180006c87  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006c8e  mov     edx, 0C3h
0x180006c93  mov     r9d, r13d
0x180006c96  call    WPP_SF_d
0x180006c9b  mov     ecx, [rdi+8]; sessionHandle
0x180006c9e  lea     r9, [rbp+120h+ppEapError]; ppEapError
0x180006ca2  lea     r8, [rsp+220h+ppSendPacket]; ppSendPacket
0x180006ca7  lea     rdx, [rsp+220h+pcbSendPacket]; pcbSendPacket
0x180006cac  call    cs:__imp_EapHostPeerGetSendPacket
0x180006cb2  mov     ebx, eax
0x180006cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cbb  cmp     rcx, r12
0x180006cbe  jz      short loc_180006CE5
0x180006cc0  test    byte ptr [rcx+44h], 10h
0x180006cc4  jz      short loc_180006CE5
0x180006cc6  mov     rcx, [rcx+38h]
0x180006cca  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006cd1  mov     edx, 0C4h
0x180006cd6  mov     r9d, r13d
0x180006cd9  call    WPP_SF_d
0x180006cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ce5  mov     rax, [rdi]
0x180006ce8  mov     rsi, [rbp+120h+ppEapError]
0x180006cec  mov     r14d, [rax+14h]
0x180006cf0  cmp     rcx, r12
0x180006cf3  jz      short loc_180006D1A
0x180006cf5  test    dword ptr [rcx+44h], 800h
0x180006cfc  jz      short loc_180006D1A
0x180006cfe  mov     rcx, [rcx+38h]
0x180006d02  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006d09  mov     edx, 0ACh
0x180006d0e  call    WPP_SF_
0x180006d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d1a  test    ebx, ebx
0x180006d1c  jz      short loc_180006D68
0x180006d1e  mov     r9, rsi
0x180006d21  mov     edx, ebx
0x180006d23  mov     rcx, rdi
0x180006d26  call    EapProcessEaphostFailure
0x180006d2b  test    eax, eax
0x180006d2d  jz      short loc_180006D61
0x180006d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d36  cmp     rcx, r12
0x180006d39  jz      loc_180007196
0x180006d3f  test    byte ptr [rcx+44h], 1
0x180006d43  jz      short loc_180006D68
0x180006d45  mov     rcx, [rcx+38h]
0x180006d49  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006d50  mov     edx, 0ADh
0x180006d55  mov     dword ptr [rsp+220h+var_200], eax
0x180006d59  mov     r9d, r14d
0x180006d5c  call    WPP_SF_dd
0x180006d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d68  cmp     rcx, r12
0x180006d6b  jz      short loc_180006D95
0x180006d6d  test    dword ptr [rcx+44h], 800h
0x180006d74  jz      short loc_180006D95
0x180006d76  mov     rcx, [rcx+38h]
0x180006d7a  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006d81  mov     edx, 0AEh
0x180006d86  xor     r9d, r9d
0x180006d89  call    WPP_SF_D
0x180006d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d95  test    ebx, ebx
0x180006d97  jz      short loc_180006DCD
0x180006d99  cmp     rcx, r12
0x180006d9c  jz      loc_180007196
0x180006da2  test    byte ptr [rcx+44h], 1
0x180006da6  jz      loc_180007196
0x180006dac  mov     rcx, [rcx+38h]
0x180006db0  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006db7  mov     edx, 0C5h
0x180006dbc  mov     dword ptr [rsp+220h+var_200], ebx
0x180006dc0  mov     r9d, r13d
0x180006dc3  call    WPP_SF_dD
0x180006dc8  jmp     loc_18000718F
0x180006dcd  movzx   esi, word ptr [rsp+220h+pcbSendPacket]
0x180006dd2  lea     rax, [rsp+220h+var_1D8]
0x180006dd7  mov     r8, [rsp+220h+ppSendPacket]
0x180006ddc  lea     r9, [rsp+220h+var_1E0]
0x180006de1  mov     qword ptr [rsp+220h+var_1F8], rax
0x180006de6  movzx   edx, si
0x180006de9  lea     rax, [rsp+220h+var_1D0]
0x180006dee  mov     [rsp+220h+arg_18], r15
0x180006df6  mov     ecx, r13d
0x180006df9  mov     [rsp+220h+var_200], rax
0x180006dfe  call    ParseEapPacket
0x180006e03  test    eax, eax
0x180006e05  jnz     loc_180006F99
0x180006e0b  mov     rbx, cs:WPP_GLOBAL_Control
0x180006e12  lea     rax, WPP_GLOBAL_Control
0x180006e19  movzx   r15d, byte ptr [rsp+220h+var_1E0]
0x180006e1f  mov     r14d, [rsp+220h+var_1D0]
0x180006e24  mov     r12d, dword ptr [rsp+220h+var_1D8]
0x180006e29  cmp     rbx, rax
0x180006e2c  jz      short loc_180006E6E
0x180006e2e  test    byte ptr [rbx+44h], 20h
0x180006e32  jz      short loc_180006E6E
0x180006e34  mov     ecx, r14d
0x180006e37  call    GetEapPacketTypeDescription
0x180006e3c  mov     rcx, [rbx+38h]
0x180006e40  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006e47  mov     dword ptr [rsp+220h+var_1E8], r12d
0x180006e4c  mov     edx, 0C6h
0x180006e51  mov     [rsp+220h+var_1F0], r15d
0x180006e56  mov     r9d, r13d
0x180006e59  mov     qword ptr [rsp+220h+var_1F8], rax
0x180006e5e  mov     dword ptr [rsp+220h+var_200], esi
0x180006e62  call    WPP_SF_ddSdd
0x180006e67  mov     rbx, cs:WPP_GLOBAL_Control
0x180006e6e  test    cs:byte_18003DF41, 40h
0x180006e75  jz      loc_180006F0B
0x180006e7b  lea     rax, [rsp+220h+var_1D8]
0x180006e80  mov     dword ptr [rsp+220h+var_1B8], r12d
0x180006e85  mov     [rbp+120h+var_180], rax
0x180006e89  lea     rdx, SendingEAPPacket; "@"
0x180006e90  lea     rax, [rsp+220h+var_1D0]
0x180006e95  mov     byte ptr [rsp+220h+var_1E0], r15b
0x180006e9a  mov     [rbp+120h+var_170], rax
0x180006e9e  mov     r9d, 6
0x180006ea4  lea     rax, [rsp+220h+var_1C0]
0x180006ea9  mov     dword ptr [rsp+220h+var_1C0], r14d
0x180006eae  mov     [rbp+120h+var_160], rax
0x180006eb2  lea     rax, [rsp+220h+var_1E0]
0x180006eb7  mov     [rbp+120h+var_150], rax
0x180006ebb  lea     rax, [rsp+220h+var_1B8]
0x180006ec0  mov     [rbp+120h+var_140], rax
0x180006ec4  lea     rax, [rbp+120h+var_190]
0x180006ec8  mov     [rsp+220h+var_200], rax
0x180006ecd  mov     word ptr [rsp+220h+var_1D0], si
0x180006ed2  mov     dword ptr [rsp+220h+var_1D8], r13d
0x180006ed7  mov     [rbp+120h+var_178], 4
0x180006edf  mov     [rbp+120h+var_168], 2
0x180006ee7  mov     [rbp+120h+var_158], 4
0x180006eef  mov     [rbp+120h+var_148], 1
0x180006ef7  mov     [rbp+120h+var_138], 4
0x180006eff  call    McGenEventWrite_EtwEventWriteTransfer
0x180006f04  mov     rbx, cs:WPP_GLOBAL_Control
0x180006f0b  cmp     r14d, 6
0x180006f0f  jnz     loc_180006FA0
0x180006f15  cmp     esi, 5
0x180006f18  jbe     loc_180006FA0
0x180006f1e  lea     rcx, [rsi-5]
0x180006f22  mov     eax, 0FFh
0x180006f27  cmp     rcx, rax
0x180006f2a  ja      short loc_180006F2E
0x180006f2c  mov     eax, ecx
0x180006f2e  mov     rdx, [rsp+220h+ppSendPacket]
0x180006f33  lea     rcx, [rbp+120h+var_130]; void *
0x180006f37  add     rdx, 5; Src
0x180006f3b  mov     r8d, eax; Size
0x180006f3e  call    memcpy_0
0x180006f43  mov     [rbp+120h+var_31], 0
0x180006f4a  lea     r15, WPP_GLOBAL_Control
0x180006f51  cmp     rbx, r15
0x180006f54  jz      short loc_180006F84
0x180006f56  test    byte ptr [rbx+44h], 20h
0x180006f5a  jz      short loc_180006F84
0x180006f5c  mov     rcx, [rbx+38h]
0x180006f60  lea     rax, [rbp+120h+var_130]
0x180006f64  mov     edx, 0C7h
0x180006f69  mov     [rsp+220h+var_200], rax
0x180006f6e  mov     r9d, r13d
0x180006f71  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180006f78  call    WPP_SF_ds
0x180006f7d  mov     rbx, cs:WPP_GLOBAL_Control
0x180006f84  test    cs:byte_18003DF41, 40h
0x180006f8b  jz      short loc_180006FA0
0x180006f8d  lea     r9, [rbp+120h+var_130]
0x180006f91  mov     r8d, r13d
0x180006f94  call    McTemplateU0qs_EtwEventWriteTransfer
0x180006f99  mov     rbx, cs:WPP_GLOBAL_Control
0x180006fa0  mov     rdi, [rdi]
0x180006fa3  mov     r15, [rsp+220h+ppSendPacket]
0x180006fa8  mov     [rsp+220h+var_1D8], 0
0x180006fb1  mov     r12d, [rdi+14h]
0x180006fb5  mov     dword ptr [rsp+220h+var_1C0], r12d
0x180006fba  lea     rax, WPP_GLOBAL_Control
0x180006fc1  cmp     rbx, rax
0x180006fc4  jz      short loc_180006FEB
0x180006fc6  test    dword ptr [rbx+44h], 800h
0x180006fcd  jz      short loc_180006FEB
0x180006fcf  mov     rcx, [rbx+38h]
0x180006fd3  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180006fda  mov     edx, 1Fh
0x180006fdf  call    WPP_SF_
0x180006fe4  mov     rbx, cs:WPP_GLOBAL_Control
0x180006feb  lea     eax, [rsi+4]
0x180006fee  mov     [rsp+220h+var_1B8], 0
0x180006ff7  movzx   r14d, ax
0x180006ffb  lea     rax, WPP_GLOBAL_Control
0x180007002  cmp     rbx, rax
0x180007005  jz      short loc_180007025
0x180007007  test    dword ptr [rbx+44h], 800h
0x18000700e  jz      short loc_180007025
0x180007010  mov     rcx, [rbx+38h]
0x180007014  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x18000701b  mov     edx, 19h
0x180007020  call    WPP_SF_
0x180007025  mov     r9d, 14Dh
0x18000702b  mov     [rsp+220h+var_1D8], 0
0x180007034  lea     r8, aAllocateeapolp; "AllocateEapolPacket"
0x18000703b  mov     ecx, r14d
0x18000703e  lea     rdx, [rsp+220h+var_1B8]
0x180007043  call    cs:__imp_AllocateMemory
0x180007049  mov     ebx, eax
0x18000704b  test    eax, eax
0x18000704d  jz      short loc_180007086
0x18000704f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007056  lea     rax, WPP_GLOBAL_Control
0x18000705d  cmp     rcx, rax
0x180007060  jz      short loc_1800070DB
0x180007062  test    byte ptr [rcx+44h], 1
0x180007066  jz      short loc_1800070A6
0x180007068  mov     rcx, [rcx+38h]
0x18000706c  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180007073  mov     edx, 1Ah
0x180007078  mov     dword ptr [rsp+220h+var_200], ebx
0x18000707c  mov     r9d, r12d
0x18000707f  call    WPP_SF_dd
0x180007084  jmp     short loc_180007098
0x180007086  mov     rax, [rsp+220h+var_1B8]
0x18000708b  mov     byte ptr [rax], 1
0x18000708e  mov     rax, [rsp+220h+var_1B8]
0x180007093  mov     [rsp+220h+var_1D8], rax
0x180007098  mov     rcx, cs:WPP_GLOBAL_Control
0x18000709f  lea     rax, WPP_GLOBAL_Control
0x1800070a6  cmp     rcx, rax
0x1800070a9  jz      short loc_1800070D3
0x1800070ab  test    dword ptr [rcx+44h], 800h
0x1800070b2  jz      short loc_1800070D3
0x1800070b4  mov     rcx, [rcx+38h]
0x1800070b8  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x1800070bf  mov     edx, 1Bh
0x1800070c4  mov     r9d, ebx
0x1800070c7  call    WPP_SF_D
0x1800070cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d3  test    ebx, ebx
0x1800070d5  jz      loc_180007252
0x1800070db  lea     rdi, WPP_GLOBAL_Control
0x1800070e2  cmp     rcx, rdi
0x1800070e5  jz      short loc_180007109
0x1800070e7  test    byte ptr [rcx+44h], 1
0x1800070eb  jz      short loc_180007109
0x1800070ed  mov     rcx, [rcx+38h]
0x1800070f1  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x1800070f8  mov     edx, 20h ; ' '
0x1800070fd  mov     dword ptr [rsp+220h+var_200], ebx
0x180007101  mov     r9d, r12d
0x180007104  call    WPP_SF_dd
0x180007109  lea     r12, WPP_GLOBAL_Control
0x180007110  mov     r8d, 18Fh
0x180007116  lea     rdx, aSendeappacket; "SendEapPacket"
0x18000711d  lea     rcx, [rsp+220h+var_1D8]
0x180007122  call    cs:__imp_FreeMemory
0x180007128  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```

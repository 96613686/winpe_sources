# SendEapolStart

- ea: `0x180016a40`
- end: `0x180016e6f`
- name: `SendEapolStart`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180022630`

## callees

- `0x180004f40`
- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180016a40`
- `0x1800214f0`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180016c7b`
- `MobileNetworking!ReleaseWriteLock` at `0x180016c7b`
- `MobileNetworking!AcquireWriteLock` at `0x180016cf3`
- `MobileNetworking!AcquireWriteLock` at `0x180016cf3`
- `MobileNetworking!AllocateMemory` at `0x180016ae4`
- `MobileNetworking!AllocateMemory` at `0x180016ae4`
- `MobileNetworking!FreeMemory` at `0x180016e1d`
- `MobileNetworking!FreeMemory` at `0x180016e1d`

## pseudocode

```c
__int64 __fastcall SendEapolStart(__int64 a1)
{
  unsigned int v1; // edi
  unsigned int v3; // r13d
  _QWORD *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _BYTE *v9; // r14
  unsigned int v10; // r12d
  _QWORD *v11; // rcx
  unsigned int v12; // r15d
  __int64 v13; // rdi
  __int64 v14; // rbp
  void *v15; // rcx
  _BYTE *v17; // [rsp+70h] [rbp+8h] BYREF
  _BYTE *v18; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_DWORD *)(a1 + 2272);
  v3 = *(_DWORD *)(a1 + 20);
  v17 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v18 = 0;
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_(v4[7], 25, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
  v17 = 0;
  v5 = AllocateMemory(v1, &v18, "AllocateEapolPacket", 333);
  v6 = v5;
  if ( !v5 )
  {
    *v18 = 1;
    v17 = v18;
    goto LABEL_12;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_53;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v3, v5);
LABEL_12:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 27, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
    {
      v8 = 36;
LABEL_20:
      WPP_SF_dd(v7[7], v8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v3, v6);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  v17[1] = 1;
  *((_WORD *)v17 + 1) = 0;
  v9 = v17;
  v10 = *(_DWORD *)(a1 + 20);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v12 = *(_DWORD *)(a1 + 20);
  v13 = *(_QWORD *)(a1 + 192);
  v14 = *(_QWORD *)(a1 + 2368);
  if ( v11 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    {
      WPP_SF_(v11[7], 52, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 0x20) != 0 )
      WPP_SF_dd(v11[7], 53, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v12, 5);
  }
  ReleaseWriteLock(a1, a1 + 2896, "MSMSendOneXPacket", 537);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(a1 + 2288))(v13, v14, 5, v9);
  if ( v6 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v12, v6);
  AcquireWriteLock(a1, a1 + 2896, "MSMSendOneXPacket", 548);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    ++*(_DWORD *)(a1 + 164);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_44;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v10, v6);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 30, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_44:
  if ( v6 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
    {
      v8 = 37;
      goto LABEL_20;
    }
  }
  else
  {
    ++*(_DWORD *)(a1 + 160);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v3);
    if ( (byte_18003DF41 & 0x40) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v15, EAPOLStartSent, v3);
  }
LABEL_53:
  FreeMemory(&v17, "SendEapolStart", 433);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180016a40  mov     rax, rsp
0x180016a43  push    rdi
0x180016a44  sub     rsp, 60h
0x180016a48  mov     edi, [rcx+8E0h]
0x180016a4e  mov     [rax+18h], rbx
0x180016a52  mov     rbx, rcx
0x180016a55  mov     [rax-10h], rbp
0x180016a59  xor     ebp, ebp
0x180016a5b  mov     [rax-18h], rsi
0x180016a5f  mov     [rax-28h], r13
0x180016a63  mov     r13d, [rcx+14h]
0x180016a67  mov     [rax+8], rbp
0x180016a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a72  lea     rsi, WPP_GLOBAL_Control
0x180016a79  cmp     rcx, rsi
0x180016a7c  jz      short loc_180016AA3
0x180016a7e  test    dword ptr [rcx+44h], 800h
0x180016a85  jz      short loc_180016AA3
0x180016a87  mov     rcx, [rcx+38h]
0x180016a8b  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016a92  mov     edx, 23h ; '#'
0x180016a97  call    WPP_SF_
0x180016a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aa3  mov     [rsp+68h+arg_8], rbp
0x180016aa8  cmp     rcx, rsi
0x180016aab  jz      short loc_180016ACB
0x180016aad  test    dword ptr [rcx+44h], 800h
0x180016ab4  jz      short loc_180016ACB
0x180016ab6  mov     rcx, [rcx+38h]
0x180016aba  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016ac1  mov     edx, 19h
0x180016ac6  call    WPP_SF_
0x180016acb  mov     r9d, 14Dh
0x180016ad1  mov     [rsp+68h+arg_0], rbp
0x180016ad6  lea     r8, aAllocateeapolp; "AllocateEapolPacket"
0x180016add  mov     ecx, edi
0x180016adf  lea     rdx, [rsp+68h+arg_8]
0x180016ae4  call    cs:__imp_AllocateMemory
0x180016aea  mov     edi, eax
0x180016aec  test    eax, eax
0x180016aee  jz      short loc_180016B24
0x180016af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180016af7  cmp     rcx, rsi
0x180016afa  jz      loc_180016E0B
0x180016b00  test    byte ptr [rcx+44h], 1
0x180016b04  jz      short loc_180016B3D
0x180016b06  mov     rcx, [rcx+38h]
0x180016b0a  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016b11  mov     edx, 1Ah
0x180016b16  mov     [rsp+68h+var_48], eax
0x180016b1a  mov     r9d, r13d
0x180016b1d  call    WPP_SF_dd
0x180016b22  jmp     short loc_180016B36
0x180016b24  mov     rax, [rsp+68h+arg_8]
0x180016b29  mov     byte ptr [rax], 1
0x180016b2c  mov     rax, [rsp+68h+arg_8]
0x180016b31  mov     [rsp+68h+arg_0], rax
0x180016b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b3d  cmp     rcx, rsi
0x180016b40  jz      short loc_180016B6A
0x180016b42  test    dword ptr [rcx+44h], 800h
0x180016b49  jz      short loc_180016B6A
0x180016b4b  mov     rcx, [rcx+38h]
0x180016b4f  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016b56  mov     edx, 1Bh
0x180016b5b  mov     r9d, edi
0x180016b5e  call    WPP_SF_D
0x180016b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b6a  test    edi, edi
0x180016b6c  jz      short loc_180016BA2
0x180016b6e  cmp     rcx, rsi
0x180016b71  jz      loc_180016E0B
0x180016b77  test    byte ptr [rcx+44h], 1
0x180016b7b  jz      loc_180016E0B
0x180016b81  mov     edx, 24h ; '$'
0x180016b86  mov     rcx, [rcx+38h]
0x180016b8a  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016b91  mov     r9d, r13d
0x180016b94  mov     [rsp+68h+var_48], edi
0x180016b98  call    WPP_SF_dd
0x180016b9d  jmp     loc_180016E0B
0x180016ba2  mov     rax, [rsp+68h+arg_0]
0x180016ba7  mov     [rsp+68h+var_20], r12
0x180016bac  mov     [rsp+68h+var_30], r14
0x180016bb1  mov     [rsp+68h+var_38], r15
0x180016bb6  mov     byte ptr [rax+1], 1
0x180016bba  mov     rax, [rsp+68h+arg_0]
0x180016bbf  mov     [rax+2], bp
0x180016bc3  mov     r14, [rsp+68h+arg_0]
0x180016bc8  mov     r12d, [rbx+14h]
0x180016bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bd3  cmp     rcx, rsi
0x180016bd6  jz      short loc_180016BFD
0x180016bd8  test    dword ptr [rcx+44h], 800h
0x180016bdf  jz      short loc_180016BFD
0x180016be1  mov     rcx, [rcx+38h]
0x180016be5  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016bec  mov     edx, 1Ch
0x180016bf1  call    WPP_SF_
0x180016bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bfd  mov     r15d, [rbx+14h]
0x180016c01  mov     rdi, [rbx+0C0h]
0x180016c08  mov     rbp, [rbx+940h]
0x180016c0f  cmp     rcx, rsi
0x180016c12  jz      short loc_180016C64
0x180016c14  test    dword ptr [rcx+44h], 800h
0x180016c1b  jz      short loc_180016C39
0x180016c1d  mov     rcx, [rcx+38h]
0x180016c21  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180016c28  mov     edx, 34h ; '4'
0x180016c2d  call    WPP_SF_
0x180016c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c39  cmp     rcx, rsi
0x180016c3c  jz      short loc_180016C64
0x180016c3e  test    byte ptr [rcx+44h], 20h
0x180016c42  jz      short loc_180016C64
0x180016c44  mov     rcx, [rcx+38h]
0x180016c48  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180016c4f  mov     edx, 35h ; '5'
0x180016c54  mov     [rsp+68h+var_48], 5
0x180016c5c  mov     r9d, r15d
0x180016c5f  call    WPP_SF_dd
0x180016c64  mov     r9d, 219h
0x180016c6a  lea     r8, aMsmsendonexpac; "MSMSendOneXPacket"
0x180016c71  lea     rdx, [rbx+0B50h]
0x180016c78  mov     rcx, rbx
0x180016c7b  call    cs:__imp_ReleaseWriteLock
0x180016c81  mov     rax, [rbx+8F0h]
0x180016c88  mov     r9, r14
0x180016c8b  mov     r8d, 5
0x180016c91  mov     rdx, rbp
0x180016c94  mov     rcx, rdi
0x180016c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c9c  mov     r14, [rsp+68h+var_30]
0x180016ca1  mov     edi, eax
0x180016ca3  test    eax, eax
0x180016ca5  jz      short loc_180016CDC
0x180016ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cae  lea     rax, WPP_GLOBAL_Control
0x180016cb5  cmp     rcx, rax
0x180016cb8  jz      short loc_180016CDC
0x180016cba  test    byte ptr [rcx+44h], 1
0x180016cbe  jz      short loc_180016CDC
0x180016cc0  mov     rcx, [rcx+38h]
0x180016cc4  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180016ccb  mov     edx, 36h ; '6'
0x180016cd0  mov     [rsp+68h+var_48], edi
0x180016cd4  mov     r9d, r15d
0x180016cd7  call    WPP_SF_dd
0x180016cdc  mov     r9d, 224h
0x180016ce2  lea     r8, aMsmsendonexpac; "MSMSendOneXPacket"
0x180016ce9  lea     rdx, [rbx+0B50h]
0x180016cf0  mov     rcx, rbx
0x180016cf3  call    cs:__imp_AcquireWriteLock
0x180016cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d00  lea     rsi, WPP_GLOBAL_Control
0x180016d07  mov     r15, [rsp+68h+var_38]
0x180016d0c  cmp     rcx, rsi
0x180016d0f  jz      short loc_180016D39
0x180016d11  test    dword ptr [rcx+44h], 800h
0x180016d18  jz      short loc_180016D39
0x180016d1a  mov     rcx, [rcx+38h]
0x180016d1e  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180016d25  mov     edx, 37h ; '7'
0x180016d2a  mov     r9d, edi
0x180016d2d  call    WPP_SF_D
0x180016d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d39  test    edi, edi
0x180016d3b  jz      short loc_180016D78
0x180016d3d  inc     dword ptr [rbx+0A4h]
0x180016d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d4a  cmp     rcx, rsi
0x180016d4d  jz      short loc_180016DA5
0x180016d4f  test    byte ptr [rcx+44h], 1
0x180016d53  jz      short loc_180016D78
0x180016d55  mov     rcx, [rcx+38h]
0x180016d59  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016d60  mov     edx, 1Dh
0x180016d65  mov     [rsp+68h+var_48], edi
0x180016d69  mov     r9d, r12d
0x180016d6c  call    WPP_SF_dd
0x180016d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d78  cmp     rcx, rsi
0x180016d7b  jz      short loc_180016DA5
0x180016d7d  test    dword ptr [rcx+44h], 800h
0x180016d84  jz      short loc_180016DA5
0x180016d86  mov     rcx, [rcx+38h]
0x180016d8a  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016d91  mov     edx, 1Eh
0x180016d96  mov     r9d, edi
0x180016d99  call    WPP_SF_D
0x180016d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016da5  mov     r12, [rsp+68h+var_20]
0x180016daa  test    edi, edi
0x180016dac  jz      short loc_180016DC3
0x180016dae  cmp     rcx, rsi
0x180016db1  jz      short loc_180016E0B
0x180016db3  test    byte ptr [rcx+44h], 1
0x180016db7  jz      short loc_180016E0B
0x180016db9  mov     edx, 25h ; '%'
0x180016dbe  jmp     loc_180016B86
0x180016dc3  inc     dword ptr [rbx+0A0h]
0x180016dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dd0  cmp     rcx, rsi
0x180016dd3  jz      short loc_180016DF3
0x180016dd5  test    byte ptr [rcx+44h], 20h
0x180016dd9  jz      short loc_180016DF3
0x180016ddb  mov     rcx, [rcx+38h]
0x180016ddf  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016de6  mov     edx, 26h ; '&'
0x180016deb  mov     r9d, r13d
0x180016dee  call    WPP_SF_d
0x180016df3  test    cs:byte_18003DF41, 40h
0x180016dfa  jz      short loc_180016E0B
0x180016dfc  mov     r8d, r13d
0x180016dff  lea     rdx, EAPOLStartSent
0x180016e06  call    McTemplateU0q_EtwEventWriteTransfer
0x180016e0b  mov     r8d, 1B1h
0x180016e11  lea     rdx, aSendeapolstart; "SendEapolStart"
0x180016e18  lea     rcx, [rsp+68h+arg_0]
0x180016e1d  call    cs:__imp_FreeMemory
0x180016e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e2a  mov     r13, [rsp+68h+var_28]
0x180016e2f  cmp     rcx, rsi
0x180016e32  mov     rsi, [rsp+68h+var_18]
0x180016e37  mov     rbp, [rsp+68h+var_10]
0x180016e3c  mov     rbx, [rsp+68h+arg_10]
0x180016e44  jz      short loc_180016E67
0x180016e46  test    dword ptr [rcx+44h], 800h
0x180016e4d  jz      short loc_180016E67
0x180016e4f  mov     rcx, [rcx+38h]
0x180016e53  lea     r8, WPP_f14bb58de79333a80cb19c03949f5f0d_Traceguids
0x180016e5a  mov     edx, 27h ; '''
0x180016e5f  mov     r9d, edi
0x180016e62  call    WPP_SF_D
0x180016e67  mov     eax, edi
0x180016e69  add     rsp, 60h
0x180016e6d  pop     rdi
0x180016e6e  retn
```

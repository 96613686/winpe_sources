# MSMUIRequest

- ea: `0x1800288c4`
- end: `0x180028b0b`
- name: `MSMUIRequest`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180022c30`
- `0x180024c40`
- `0x180027494`

## callees

- `0x180004710`
- `0x180005440`
- `0x180007f60`
- `0x1800214f0`
- `0x1800288c4`
- `0x180028c4c`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002899e`
- `MobileNetworking!ReleaseWriteLock` at `0x18002899e`
- `MobileNetworking!AcquireWriteLock` at `0x180028a6e`
- `MobileNetworking!AcquireWriteLock` at `0x180028a6e`

## pseudocode

```c
__int64 __fastcall MSMUIRequest(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // ebx
  unsigned int v6; // r14d
  __int64 v7; // r13
  unsigned int v8; // r15d
  unsigned int v9; // edi
  char *v11; // rcx
  unsigned int v12; // esi
  void *v13; // rcx
  __int64 v15; // [rsp+90h] [rbp+8h]

  v5 = *(_DWORD *)(a1 + 20);
  v6 = a3;
  v7 = *(_QWORD *)(a1 + 192);
  v8 = a2;
  v9 = a4[1];
  v15 = *(_QWORD *)(a1 + 2368);
  v11 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 2336) )
  {
    if ( v11 != (char *)&WPP_GLOBAL_Control && v11[68] < 0 )
      WPP_SF_dddd(*((_QWORD *)v11 + 7), a2, a3, v5, v9, v8, v6);
    if ( (byte_18003DF41 & 0x20) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v11, SendingMSMUIRequest, v5, v9);
    ReleaseWriteLock(a1, a1 + 2896, "MSMUIRequest", 100);
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _DWORD *))(a1 + 2336))(
            v7,
            v15,
            v8,
            v6,
            *a4,
            a4);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5, v12);
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5, v9);
      if ( (byte_18003DF41 & 8) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(v13, MSMUIRequestSent, v5, v9);
    }
    AcquireWriteLock(a1, a1 + 2896, "MSMUIRequest", 130);
    goto LABEL_25;
  }
  v12 = 1459;
  if ( (Microsoft_Windows_OneXEnableBits & 0x40) != 0 )
  {
    McTemplateU0qq_EtwEventWriteTransfer(v11, CannotSendUIRequest, v5, v9);
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( v11 != (char *)&WPP_GLOBAL_Control )
  {
    if ( (v11[68] & 1) == 0 )
    {
LABEL_26:
      if ( v11 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
        WPP_SF_D(*((_QWORD *)v11 + 7), 19, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v12);
      return v12;
    }
    WPP_SF_dd(*((_QWORD *)v11 + 7), 17, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5, v9);
LABEL_25:
    v11 = (char *)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  return v12;
}

```

## disassembly

```asm
0x1800288c4  push    rbx
0x1800288c6  push    rbp
0x1800288c7  push    rsi
0x1800288c8  push    rdi
0x1800288c9  push    r12
0x1800288cb  push    r13
0x1800288cd  push    r14
0x1800288cf  push    r15
0x1800288d1  sub     rsp, 48h
0x1800288d5  mov     rax, [rcx+940h]
0x1800288dc  mov     rsi, r9
0x1800288df  mov     ebx, [rcx+14h]
0x1800288e2  mov     r14d, r8d
0x1800288e5  mov     r13, [rcx+0C0h]
0x1800288ec  mov     r15d, edx
0x1800288ef  mov     edi, [r9+4]
0x1800288f3  mov     rbp, rcx
0x1800288f6  mov     [rsp+88h+arg_0], rax
0x1800288fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180028905  lea     r12, WPP_GLOBAL_Control
0x18002890c  cmp     rcx, r12
0x18002890f  jz      short loc_180028936
0x180028911  test    dword ptr [rcx+44h], 800h
0x180028918  jz      short loc_180028936
0x18002891a  mov     rcx, [rcx+38h]
0x18002891e  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028925  mov     edx, 0Eh
0x18002892a  call    WPP_SF_
0x18002892f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028936  cmp     qword ptr [rbp+920h], 0
0x18002893e  jz      loc_180028A7D
0x180028944  cmp     rcx, r12
0x180028947  jz      short loc_180028969
0x180028949  test    byte ptr [rcx+44h], 80h
0x18002894d  jz      short loc_180028969
0x18002894f  mov     rcx, [rcx+38h]
0x180028953  mov     r9d, ebx
0x180028956  mov     [rsp+88h+var_58], r14d
0x18002895b  mov     dword ptr [rsp+88h+var_60], r15d
0x180028960  mov     [rsp+88h+var_68], edi
0x180028964  call    WPP_SF_dddd
0x180028969  test    cs:byte_18003DF41, 20h
0x180028970  jz      short loc_180028984
0x180028972  mov     r9d, edi
0x180028975  lea     rdx, SendingMSMUIRequest
0x18002897c  mov     r8d, ebx
0x18002897f  call    McTemplateU0qq_EtwEventWriteTransfer
0x180028984  lea     r12, [rbp+0B50h]
0x18002898b  mov     r9d, 64h ; 'd'
0x180028991  mov     rdx, r12
0x180028994  lea     r8, aMsmuirequest; "MSMUIRequest"
0x18002899b  mov     rcx, rbp
0x18002899e  call    cs:__imp_ReleaseWriteLock
0x1800289a4  mov     r8d, [rsi]
0x1800289a7  mov     r9d, r14d
0x1800289aa  mov     rdx, [rsp+88h+arg_0]
0x1800289b2  mov     rcx, r13
0x1800289b5  mov     rax, [rbp+920h]
0x1800289bc  mov     [rsp+88h+var_60], rsi
0x1800289c1  mov     [rsp+88h+var_68], r8d
0x1800289c6  mov     r8d, r15d
0x1800289c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289ce  mov     esi, eax
0x1800289d0  test    eax, eax
0x1800289d2  jz      short loc_180028A0B
0x1800289d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289db  lea     rax, WPP_GLOBAL_Control
0x1800289e2  cmp     rcx, rax
0x1800289e5  jz      short loc_180028A5B
0x1800289e7  test    byte ptr [rcx+44h], 1
0x1800289eb  jz      short loc_180028A5B
0x1800289ed  mov     rcx, [rcx+38h]
0x1800289f1  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800289f8  mov     edx, 10h
0x1800289fd  mov     [rsp+88h+var_68], esi
0x180028a01  mov     r9d, ebx
0x180028a04  call    WPP_SF_dd
0x180028a09  jmp     short loc_180028A5B
0x180028a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a12  lea     rax, WPP_GLOBAL_Control
0x180028a19  cmp     rcx, rax
0x180028a1c  jz      short loc_180028A40
0x180028a1e  test    byte ptr [rcx+44h], 4
0x180028a22  jz      short loc_180028A40
0x180028a24  mov     rcx, [rcx+38h]
0x180028a28  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028a2f  mov     edx, 12h
0x180028a34  mov     [rsp+88h+var_68], edi
0x180028a38  mov     r9d, ebx
0x180028a3b  call    WPP_SF_dd
0x180028a40  test    cs:byte_18003DF41, 8
0x180028a47  jz      short loc_180028A5B
0x180028a49  mov     r9d, edi
0x180028a4c  lea     rdx, MSMUIRequestSent
0x180028a53  mov     r8d, ebx
0x180028a56  call    McTemplateU0qq_EtwEventWriteTransfer
0x180028a5b  mov     r9d, 82h
0x180028a61  lea     r8, aMsmuirequest; "MSMUIRequest"
0x180028a68  mov     rdx, r12
0x180028a6b  mov     rcx, rbp
0x180028a6e  call    cs:__imp_AcquireWriteLock
0x180028a74  lea     r12, WPP_GLOBAL_Control
0x180028a7b  jmp     short loc_180028ACB
0x180028a7d  test    cs:Microsoft_Windows_OneXEnableBits, 40h
0x180028a84  mov     esi, 5B3h
0x180028a89  jz      short loc_180028AA4
0x180028a8b  mov     r9d, edi
0x180028a8e  lea     rdx, CannotSendUIRequest
0x180028a95  mov     r8d, ebx
0x180028a98  call    McTemplateU0qq_EtwEventWriteTransfer
0x180028a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028aa4  cmp     rcx, r12
0x180028aa7  jz      short loc_180028AF8
0x180028aa9  test    byte ptr [rcx+44h], 1
0x180028aad  jz      short loc_180028AD2
0x180028aaf  mov     rcx, [rcx+38h]
0x180028ab3  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028aba  mov     edx, 11h
0x180028abf  mov     [rsp+88h+var_68], edi
0x180028ac3  mov     r9d, ebx
0x180028ac6  call    WPP_SF_dd
0x180028acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ad2  cmp     rcx, r12
0x180028ad5  jz      short loc_180028AF8
0x180028ad7  test    dword ptr [rcx+44h], 800h
0x180028ade  jz      short loc_180028AF8
0x180028ae0  mov     rcx, [rcx+38h]
0x180028ae4  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028aeb  mov     edx, 13h
0x180028af0  mov     r9d, esi
0x180028af3  call    WPP_SF_D
0x180028af8  mov     eax, esi
0x180028afa  add     rsp, 48h
0x180028afe  pop     r15
0x180028b00  pop     r14
0x180028b02  pop     r13
0x180028b04  pop     r12
0x180028b06  pop     rdi
0x180028b07  pop     rsi
0x180028b08  pop     rbp
0x180028b09  pop     rbx
0x180028b0a  retn
```

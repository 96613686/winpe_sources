# MRxSmbIsValidDirectory

- ea: `0x140029ff0`
- end: `0x14002a42a`
- name: `MRxSmbIsValidDirectory`
- size: `1082`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x14000b6f0`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000e708`
- `0x140029ff0`
- `0x140046120`
- `0x140046a50`
- `0x14004d7f0`
- `0x14004dd50`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002a21f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002a21f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002a13d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002a13d`

## pseudocode

```c
__int64 __fastcall MRxSmbIsValidDirectory(__int64 a1, _WORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbp
  __int64 v7; // rbx
  __int64 v8; // rdi
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rcx
  int OrdinaryExchange; // edi
  char v12; // bl
  int v13; // eax
  int v14; // ebx
  unsigned __int16 *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  _DWORD *v20; // rbx
  PDEVICE_OBJECT v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-68h]
  __int64 v24; // [rsp+28h] [rbp-60h]
  __int128 v25; // [rsp+30h] [rbp-58h] BYREF
  __int64 v26; // [rsp+40h] [rbp-48h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF
  PVOID pContext; // [rsp+A0h] [rbp+18h] BYREF

  v25 = 0;
  pContext = 0;
  v26 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 656) + 40LL);
  v7 = *(_QWORD *)(v6 + 96);
  v8 = *(_QWORD *)(v6 + 88);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
  if ( (Microsoft_Windows_SMBClientEnableBits & 2) != 0 )
  {
    LODWORD(v23) = 0;
    LOBYTE(a4) = -76;
    McTemplateK0uq_EtwWriteTransfer(v9, a2, a1 + 412, a4);
  }
  v10 = *(_QWORD *)(a1 + 672);
  if ( (*(_DWORD *)(v10 + 12) & 8) != 0 && !*(_BYTE *)(*(_QWORD *)(v6 + 96) + 381LL) )
  {
    OrdinaryExchange = -1073741311;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        78,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        a1,
        -1073741311);
    v12 = 109;
    goto LABEL_56;
  }
  v13 = *(_DWORD *)(v10 + 8);
  if ( v13 == 3 )
  {
    OrdinaryExchange = -1073741311;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        79,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        a1,
        -1073741311);
    v12 = 117;
    goto LABEL_56;
  }
  if ( ((v13 - 2) & 0xFFFFFFFD) != 0 )
    goto LABEL_30;
  if ( (*(_DWORD *)(v7 + 136) & 0x10) != 0 && !*(_BYTE *)(MRxSmbGetConfigurationBlock() + 229)
    || (*(_DWORD *)(v7 + 136) & 4) != 0 )
  {
    OrdinaryExchange = -1073741311;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        80,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        a1,
        -1073741311);
    v12 = -126;
    goto LABEL_56;
  }
  if ( (*(_BYTE *)(v8 + 672) & 8) != 0 )
  {
LABEL_30:
    v14 = 0;
    while ( 1 )
    {
      v15 = *(unsigned __int16 **)(a1 + 680);
      v16 = *(_QWORD *)(v6 + 96);
      Interval.QuadPart = 0;
      OrdinaryExchange = SmbCeSetupAlternateSPNForSession(v16, v15);
      Interval.QuadPart = -10000000 * v14;
      KeDelayExecutionThread(0, 0, &Interval);
      if ( OrdinaryExchange != -1069481983 )
        break;
      if ( ++v14 > 10 )
      {
        OrdinaryExchange = -1073741311;
LABEL_36:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            82,
            WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
            a1,
            OrdinaryExchange);
        }
        v12 = -85;
        goto LABEL_56;
      }
    }
    if ( OrdinaryExchange != -1073740964 && OrdinaryExchange < 0 )
      goto LABEL_36;
    v17 = *(_QWORD *)(a1 + 672);
    if ( ((*(_DWORD *)(v17 + 8) - 2) & 0xFFFFFFFD) == 0 )
      *(_DWORD *)(v17 + 20) = 2;
    v18 = *(_QWORD *)(a1 + 672);
    if ( (*(_DWORD *)(v18 + 12) & 8) != 0 )
      *(_DWORD *)(v18 + 24) |= 8u;
    if ( (*(_BYTE *)(a1 + 750) & 8) != 0 )
    {
      OrdinaryExchange = -1073741637;
      v12 = -62;
    }
    else if ( *a2 )
    {
      SmbCeReconnect(*(PVOID *)(*(_QWORD *)(a1 + 656) + 40LL));
      OrdinaryExchange = v19;
      if ( v19 )
      {
        v12 = -46;
      }
      else
      {
        OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                             a1,
                             *(_QWORD *)(a1 + 656),
                             12,
                             (__int64)MRxSmbCoreCheckPath,
                             v23,
                             (__int64 *)&pContext);
        if ( OrdinaryExchange )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
          }
          v12 = -32;
        }
        else
        {
          v20 = pContext;
          *((_QWORD *)pContext + 108) = a2;
          v20[18] |= 0x10u;
          *((_BYTE *)v20 + 1009) = -1;
          *((_QWORD *)v20 + 15) = &v25;
          MRxSmbSetInitialSMB(v20 + 222);
          OrdinaryExchange = SmbCeInitiateExchange(v20);
          SmbPseFinalizeOrdinaryExchange(v20);
          v12 = -19;
        }
      }
    }
    else
    {
      OrdinaryExchange = 0;
      v12 = 0;
    }
  }
  else
  {
    OrdinaryExchange = -1073741311;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        81,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        a1,
        -1073741311);
    v12 = -118;
  }
LABEL_56:
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      84,
      WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
      (unsigned int)OrdinaryExchange);
  if ( OrdinaryExchange < 0 && (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
  {
    LODWORD(v24) = 0;
    McTemplateK0qqq_EtwWriteTransfer(
      (_DWORD)v21,
      (unsigned int)CreateFileError,
      a1 + 412,
      OrdinaryExchange,
      v12,
      v24,
      v25,
      v26);
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 2) != 0 )
  {
    LOBYTE(a4) = -75;
    McTemplateK0uq_EtwWriteTransfer(v21, a2, a1 + 412, a4);
  }
  return (unsigned int)OrdinaryExchange;
}

```

## disassembly

```asm
0x140029ff0  mov     r11, rsp
0x140029ff3  mov     [r11+10h], rbx
0x140029ff7  push    rbp
0x140029ff8  push    rsi
0x140029ff9  push    rdi
0x140029ffa  push    r12
0x140029ffc  push    r13
0x140029ffe  push    r14
0x14002a000  push    r15
0x14002a002  sub     rsp, 50h
0x14002a006  xor     r15d, r15d
0x14002a009  xorps   xmm0, xmm0
0x14002a00c  movups  [rsp+88h+var_58], xmm0
0x14002a011  xor     eax, eax
0x14002a013  mov     [r11+18h], r15
0x14002a017  mov     [r11-48h], rax
0x14002a01b  mov     r14, rdx
0x14002a01e  mov     rax, [rcx+290h]
0x14002a025  mov     rsi, rcx
0x14002a028  mov     rbp, [rax+28h]
0x14002a02c  mov     rbx, [rbp+60h]
0x14002a030  mov     rdi, [rbp+58h]
0x14002a034  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a03b  lea     r12, WPP_GLOBAL_Control
0x14002a042  lea     r13, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002a049  cmp     rcx, r12
0x14002a04c  jz      short loc_14002A067
0x14002a04e  test    dword ptr [rcx+2Ch], 400h
0x14002a055  jz      short loc_14002A067
0x14002a057  mov     rcx, [rcx+18h]
0x14002a05b  lea     edx, [r15+4Dh]
0x14002a05f  mov     r8, r13
0x14002a062  call    WPP_SF_
0x14002a067  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 2
0x14002a06e  jz      short loc_14002A084
0x14002a070  lea     r8, [rsi+19Ch]
0x14002a077  mov     dword ptr [rsp+88h+var_68], r15d
0x14002a07c  mov     r9b, 0B4h
0x14002a07f  call    McTemplateK0uq_EtwWriteTransfer
0x14002a084  mov     rcx, [rsi+2A0h]
0x14002a08b  mov     eax, [rcx+0Ch]
0x14002a08e  test    al, 8
0x14002a090  jz      short loc_14002A0DF
0x14002a092  mov     rax, [rbp+60h]
0x14002a096  cmp     [rax+17Dh], r15b
0x14002a09d  jnz     short loc_14002A0DF
0x14002a09f  mov     edi, 0C0000201h
0x14002a0a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a0ab  cmp     rcx, r12
0x14002a0ae  jz      short loc_14002A0D5
0x14002a0b0  test    dword ptr [rcx+2Ch], 100h
0x14002a0b7  jz      short loc_14002A0D5
0x14002a0b9  mov     rcx, [rcx+18h]
0x14002a0bd  mov     edx, 4Eh ; 'N'
0x14002a0c2  mov     r9, rsi
0x14002a0c5  mov     dword ptr [rsp+88h+var_68], 0C0000201h
0x14002a0cd  mov     r8, r13
0x14002a0d0  call    WPP_SF_qD
0x14002a0d5  mov     ebx, 10100E6Dh
0x14002a0da  jmp     loc_14002A39E
0x14002a0df  mov     eax, [rcx+8]
0x14002a0e2  cmp     eax, 3
0x14002a0e5  jnz     short loc_14002A125
0x14002a0e7  mov     edi, 0C0000201h
0x14002a0ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a0f3  cmp     rcx, r12
0x14002a0f6  jz      short loc_14002A11B
0x14002a0f8  test    dword ptr [rcx+2Ch], 100h
0x14002a0ff  jz      short loc_14002A11B
0x14002a101  mov     rcx, [rcx+18h]
0x14002a105  lea     edx, [rax+4Ch]
0x14002a108  mov     r9, rsi
0x14002a10b  mov     dword ptr [rsp+88h+var_68], 0C0000201h
0x14002a113  mov     r8, r13
0x14002a116  call    WPP_SF_qD
0x14002a11b  mov     ebx, 10100E75h
0x14002a120  jmp     loc_14002A39E
0x14002a125  add     eax, 0FFFFFFFEh
0x14002a128  test    eax, 0FFFFFFFDh
0x14002a12d  jnz     loc_14002A1E5
0x14002a133  mov     eax, [rbx+88h]
0x14002a139  test    al, 10h
0x14002a13b  jz      short loc_14002A152
0x14002a13d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002a144  nop     dword ptr [rax+rax+00h]
0x14002a149  cmp     [rax+0E5h], r15b
0x14002a150  jz      short loc_14002A15C
0x14002a152  mov     eax, [rbx+88h]
0x14002a158  test    al, 4
0x14002a15a  jz      short loc_14002A19C
0x14002a15c  mov     edi, 0C0000201h
0x14002a161  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a168  cmp     rcx, r12
0x14002a16b  jz      short loc_14002A192
0x14002a16d  test    dword ptr [rcx+2Ch], 100h
0x14002a174  jz      short loc_14002A192
0x14002a176  mov     rcx, [rcx+18h]
0x14002a17a  mov     edx, 50h ; 'P'
0x14002a17f  mov     r9, rsi
0x14002a182  mov     dword ptr [rsp+88h+var_68], 0C0000201h
0x14002a18a  mov     r8, r13
0x14002a18d  call    WPP_SF_qD
0x14002a192  mov     ebx, 10100E82h
0x14002a197  jmp     loc_14002A39E
0x14002a19c  test    byte ptr [rdi+2A0h], 8
0x14002a1a3  jnz     short loc_14002A1E5
0x14002a1a5  mov     edi, 0C0000201h
0x14002a1aa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a1b1  cmp     rcx, r12
0x14002a1b4  jz      short loc_14002A1DB
0x14002a1b6  test    dword ptr [rcx+2Ch], 100h
0x14002a1bd  jz      short loc_14002A1DB
0x14002a1bf  mov     rcx, [rcx+18h]
0x14002a1c3  mov     edx, 51h ; 'Q'
0x14002a1c8  mov     r9, rsi
0x14002a1cb  mov     dword ptr [rsp+88h+var_68], 0C0000201h
0x14002a1d3  mov     r8, r13
0x14002a1d6  call    WPP_SF_qD
0x14002a1db  mov     ebx, 10100E8Ah
0x14002a1e0  jmp     loc_14002A39E
0x14002a1e5  mov     ebx, r15d
0x14002a1e8  mov     rdx, [rsi+2A8h]
0x14002a1ef  mov     rcx, [rbp+60h]
0x14002a1f3  mov     qword ptr [rsp+88h+Interval], r15
0x14002a1fb  call    SmbCeSetupAlternateSPNForSession
0x14002a200  mov     edi, eax
0x14002a202  lea     r8, [rsp+88h+Interval]; Interval
0x14002a20a  imul    eax, ebx, 0FF676980h
0x14002a210  xor     edx, edx; Alertable
0x14002a212  movsxd  rcx, eax
0x14002a215  mov     qword ptr [rsp+88h+Interval], rcx
0x14002a21d  xor     ecx, ecx; WaitMode
0x14002a21f  call    cs:__imp_KeDelayExecutionThread
0x14002a226  nop     dword ptr [rax+rax+00h]
0x14002a22b  cmp     edi, 0C0410001h
0x14002a231  jnz     short loc_14002A241
0x14002a233  inc     ebx
0x14002a235  cmp     ebx, 0Ah
0x14002a238  jle     short loc_14002A1E8
0x14002a23a  mov     edi, 0C0000201h
0x14002a23f  jmp     short loc_14002A24D
0x14002a241  cmp     edi, 0C000035Ch
0x14002a247  jz      short loc_14002A284
0x14002a249  test    edi, edi
0x14002a24b  jns     short loc_14002A284
0x14002a24d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a254  cmp     rcx, r12
0x14002a257  jz      short loc_14002A27A
0x14002a259  test    dword ptr [rcx+2Ch], 100h
0x14002a260  jz      short loc_14002A27A
0x14002a262  mov     rcx, [rcx+18h]
0x14002a266  mov     edx, 52h ; 'R'
0x14002a26b  mov     r9, rsi
0x14002a26e  mov     dword ptr [rsp+88h+var_68], edi
0x14002a272  mov     r8, r13
0x14002a275  call    WPP_SF_qD
0x14002a27a  mov     ebx, 10100EABh
0x14002a27f  jmp     loc_14002A39E
0x14002a284  mov     rcx, [rsi+2A0h]
0x14002a28b  mov     eax, [rcx+8]
0x14002a28e  sub     eax, 2
0x14002a291  test    eax, 0FFFFFFFDh
0x14002a296  jnz     short loc_14002A29F
0x14002a298  mov     dword ptr [rcx+14h], 2
0x14002a29f  mov     rcx, [rsi+2A0h]
0x14002a2a6  mov     eax, [rcx+0Ch]
0x14002a2a9  test    al, 8
0x14002a2ab  jz      short loc_14002A2B1
0x14002a2ad  or      dword ptr [rcx+18h], 8
0x14002a2b1  test    byte ptr [rsi+2EEh], 8
0x14002a2b8  jz      short loc_14002A2C9
0x14002a2ba  mov     edi, 0C00000BBh
0x14002a2bf  mov     ebx, 10100EC2h
0x14002a2c4  jmp     loc_14002A39E
0x14002a2c9  cmp     [r14], r15w
0x14002a2cd  jnz     short loc_14002A2DC
0x14002a2cf  mov     edi, r15d
0x14002a2d2  mov     ebx, 10100000h
0x14002a2d7  jmp     loc_14002A39E
0x14002a2dc  mov     rcx, [rsi+290h]
0x14002a2e3  mov     rcx, [rcx+28h]; Context
0x14002a2e7  call    SmbCeReconnect
0x14002a2ec  mov     edi, eax
0x14002a2ee  test    eax, eax
0x14002a2f0  jz      short loc_14002A2FC
0x14002a2f2  mov     ebx, 10100ED2h
0x14002a2f7  jmp     loc_14002A39E
0x14002a2fc  mov     rdx, [rsi+290h]
0x14002a303  lea     rax, [rsp+88h+pContext]
0x14002a30b  lea     r9, MRxSmbCoreCheckPath
0x14002a312  mov     [rsp+88h+var_60], rax
0x14002a317  mov     r8d, 0Ch
0x14002a31d  mov     rcx, rsi
0x14002a320  call    __SmbPseCreateOrdinaryExchange
0x14002a325  mov     edi, eax
0x14002a327  test    eax, eax
0x14002a329  jz      short loc_14002A358
0x14002a32b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a332  cmp     rcx, r12
0x14002a335  jz      short loc_14002A351
0x14002a337  test    dword ptr [rcx+2Ch], 400h
0x14002a33e  jz      short loc_14002A351
0x14002a340  mov     rcx, [rcx+18h]
0x14002a344  mov     edx, 53h ; 'S'
0x14002a349  mov     r8, r13
0x14002a34c  call    WPP_SF_
0x14002a351  mov     ebx, 10100EE0h
0x14002a356  jmp     short loc_14002A39E
0x14002a358  mov     rbx, [rsp+88h+pContext]
0x14002a360  lea     rax, [rsp+88h+var_58]
0x14002a365  mov     [rbx+360h], r14
0x14002a36c  lea     rcx, [rbx+378h]
0x14002a373  or      dword ptr [rbx+48h], 10h
0x14002a377  mov     byte ptr [rbx+3F1h], 0FFh
0x14002a37e  mov     [rbx+78h], rax
0x14002a382  call    MRxSmbSetInitialSMB
0x14002a387  mov     rcx, rbx
0x14002a38a  call    SmbCeInitiateExchange
0x14002a38f  mov     rcx, rbx; pContext
0x14002a392  mov     edi, eax
0x14002a394  call    SmbPseFinalizeOrdinaryExchange
0x14002a399  mov     ebx, 10100EEDh
0x14002a39e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a3a5  cmp     rcx, r12
0x14002a3a8  jz      short loc_14002A3C7
0x14002a3aa  test    dword ptr [rcx+2Ch], 400h
0x14002a3b1  jz      short loc_14002A3C7
0x14002a3b3  mov     rcx, [rcx+18h]
0x14002a3b7  mov     edx, 54h ; 'T'
0x14002a3bc  mov     r9d, edi
0x14002a3bf  mov     r8, r13
0x14002a3c2  call    WPP_SF_d
0x14002a3c7  test    edi, edi
0x14002a3c9  jns     short loc_14002A3F3
0x14002a3cb  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14002a3d2  jz      short loc_14002A3F3
0x14002a3d4  lea     r8, [rsi+19Ch]
0x14002a3db  mov     dword ptr [rsp+88h+var_60], r15d
0x14002a3e0  mov     r9d, edi
0x14002a3e3  mov     dword ptr [rsp+88h+var_68], ebx
0x14002a3e7  lea     rdx, CreateFileError
0x14002a3ee  call    McTemplateK0qqq_EtwWriteTransfer
0x14002a3f3  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 2
0x14002a3fa  jz      short loc_14002A40F
0x14002a3fc  lea     r8, [rsi+19Ch]
0x14002a403  mov     dword ptr [rsp+88h+var_68], edi
0x14002a407  mov     r9b, 0B5h
0x14002a40a  call    McTemplateK0uq_EtwWriteTransfer
0x14002a40f  mov     rbx, [rsp+88h+arg_8]
0x14002a417  mov     eax, edi
0x14002a419  add     rsp, 50h
0x14002a41d  pop     r15
0x14002a41f  pop     r14
0x14002a421  pop     r13
0x14002a423  pop     r12
0x14002a425  pop     rdi
0x14002a426  pop     rsi
0x14002a427  pop     rbp
0x14002a428  retn
```

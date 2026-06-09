# DhcpInitRebootState

- ea: `0x18002fedc`
- end: `0x1800303ca`
- name: `DhcpInitRebootState`
- size: `1262`
- prototype: `__int64 __fastcall(__int64, int, int, __int64 (__fastcall **)(__int64, __int64, int), __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032f50`

## callees

- `0x1800032b8`
- `0x1800057f0`
- `0x180008e6c`
- `0x180009108`
- `0x1800094f0`
- `0x18000b650`
- `0x18001098c`
- `0x180010cc4`
- `0x180012ef0`
- `0x180014bd8`
- `0x18001556c`
- `0x18001a2e4`
- `0x18001bb80`
- `0x18001d826`
- `0x18001f8e0`
- `0x1800205e4`
- `0x1800221a8`
- `0x18002f670`
- `0x18002fedc`
- `0x18003214c`
- `0x180033480`
- `0x1800355dc`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d4c0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030221`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030221`

## pseudocode

```c
__int64 __fastcall DhcpInitRebootState(
        __int64 a1,
        int a2,
        int a3,
        __int64 (__fastcall **a4)(__int64, __int64, int),
        __int64 a5)
{
  int v8; // esi
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  int v17; // edx
  unsigned int v18; // eax
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v23[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C8h] BYREF
  _OWORD v25[13]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+150h] [rbp+48h] BYREF
  int v27; // [rsp+160h] [rbp+58h] BYREF

  LODWORD(v26) = a2;
  v23[0] = 0;
  memset_0(v25, 0, 0xC8u);
  lpSubKey = 0;
  v27 = 0;
  LODWORD(v26) = 0;
  v8 = IsDhcpAddressPlumbedInStack(a1);
  v9 = DhcpSetContextForcedBroadcastFlag(a1);
  if ( v9 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_6;
    WPP_SF_D(1025, 221, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v9);
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_S(1025, 222, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 56));
LABEL_6:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 223, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v10, InitRebootState, *(_QWORD *)(a1 + 56));
  TraceLogErrorv4(a1, 0, 107);
  *a4 = ReRenewParameters;
  v11 = RenewLease(a1, (int)v23, 1, a3, (__int64)&v26, v25);
  v12 = v11;
  if ( v8 )
    *(_DWORD *)(a1 + 776) = 1;
  if ( DhcpGlobalIsShuttingDown )
  {
    v12 = 65;
    goto LABEL_14;
  }
  if ( !v11 )
  {
    SetEventNotification(8, *(_QWORD *)(a1 + 56));
    if ( *(_DWORD *)&DhcpGlobalUseNetworkHint )
    {
      GetNetworkHint(*(_QWORD *)(a1 + 24), &lpSubKey, &v27, 0);
      if ( lpSubKey )
        RegDeleteKeyExW(*(HKEY *)(a1 + 728), lpSubKey, 0, 0);
    }
    goto LABEL_43;
  }
  v13 = v11 - 65;
  if ( !v13 )
  {
LABEL_14:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 224, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, 65);
    goto LABEL_60;
  }
  v14 = v13 - 1158;
  if ( !v14 )
  {
    if ( v8 )
      *(_DWORD *)(a1 + 776) = 0;
    if ( g_fVelocityDhcpOption108RenewFix )
      v17 = *(_QWORD *)(a1 + 2160) != 0 ? 25 : 8;
    else
      v17 = 8;
    DhcpSetEventInRenewState(a1, v17, (_DWORD)a4, a5, 1223);
    goto LABEL_60;
  }
  v15 = v14 - 6;
  if ( !v15 || v15 == 4093 )
  {
    DhcpSetEventInRenewState(a1, 14, (_DWORD)a4, a5, v12);
    DhcpUninitializeInterface(a1, 0);
    *(_DWORD *)(a1 + 132) = 0;
    *(_DWORD *)(a1 + 1928) = 1;
LABEL_49:
    if ( v12 != 121 )
      goto LABEL_60;
    goto LABEL_50;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 225, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v12);
  if ( *(_DWORD *)(a1 + 564) || (unsigned int)RefreshNotNeeded(a1) == 1 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 226, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
    memset_0(v25, 0, 0xC8u);
    DhcpCopyExistingStackParams(a1, v25);
    if ( (_DWORD)v26 )
      SetExpiryTimeForNonReceivedOptions(a1, v16, 1);
LABEL_43:
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_q(1028, 228, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 24));
    v18 = ApplyDhcpConfigurationToNIC(a1, (__int64)v25, v8 == 0);
    v12 = v18;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_dJ(1028, 229, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v18, *(_QWORD *)(a1 + 24));
    if ( !v12 )
    {
      DhcpSetEventInRenewState(a1, 9, (_DWORD)a4, a5, 0);
LABEL_58:
      DhcpSetDADPending(a1);
      if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(
          v21,
          DadRegistered,
          *(unsigned int *)(a1 + 48),
          *(unsigned int *)(a1 + 120));
      goto LABEL_60;
    }
    DhcpSetEventInRenewState(a1, 11, (_DWORD)a4, a5, v12);
    goto LABEL_49;
  }
  if ( (xmmword_1800616A0 & 8) != 0 )
    WPP_SF_(1027, 227, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
  DhcpSetEventInRenewState(a1, 11, (_DWORD)a4, a5, v12);
  DhcpUninitializeInterface(a1, 0);
  v12 = 121;
LABEL_50:
  if ( !(unsigned int)DhcpApplyFallback(a1) )
  {
    if ( (byte_1800619C9 & 1) != 0 )
    {
      McTemplateU0jqq_EtwEventWriteTransfer(
        v19,
        (unsigned int)SelfPerftrackDHCPFallbackAddress,
        a1 + 32,
        *(_DWORD *)(a1 + 48),
        0);
      if ( (byte_1800619C9 & 1) != 0 )
        McTemplateU0jqq_EtwEventWriteTransfer(
          v20,
          (unsigned int)PerftrackWlanDHCPFallbackAddress,
          a1 + 32,
          *(_DWORD *)(a1 + 48),
          0);
    }
    DhcpSetEventInRenewState(a1, 12, (_DWORD)a4, a5, 121);
    goto LABEL_58;
  }
  if ( (byte_1800619C9 & 1) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(v19, PerftrackRequestNoResponse, a1 + 32, *(unsigned int *)(a1 + 48));
LABEL_60:
  DhcpPunycodeFree(&lpSubKey);
  DhcpCleanParsedOptions((char *)v25);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 230, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002fedc  mov     rax, rsp
0x18002fedf  mov     [rax+8], rbx
0x18002fee3  mov     [rax+18h], rsi
0x18002fee7  mov     [rax+10h], edx
0x18002feea  push    rbp
0x18002feeb  push    rdi
0x18002feec  push    r12
0x18002feee  push    r13
0x18002fef0  push    r15
0x18002fef2  lea     rbp, [rax-38h]
0x18002fef6  sub     rsp, 110h
0x18002fefd  mov     edi, r8d
0x18002ff00  mov     rbx, rcx
0x18002ff03  xor     r12d, r12d
0x18002ff06  lea     rcx, [rsp+130h+var_F0]; void *
0x18002ff0b  mov     r8d, 0C8h; Size
0x18002ff11  mov     [rsp+130h+var_100], r12d
0x18002ff16  xor     edx, edx; Val
0x18002ff18  mov     r15, r9
0x18002ff1b  call    memset_0
0x18002ff20  mov     rcx, rbx
0x18002ff23  mov     [rsp+130h+lpSubKey], r12
0x18002ff28  mov     [rbp+30h+arg_18], r12d
0x18002ff2c  mov     dword ptr [rbp+30h+arg_8], r12d
0x18002ff30  call    IsDhcpAddressPlumbedInStack
0x18002ff35  mov     rcx, rbx
0x18002ff38  mov     esi, eax
0x18002ff3a  call    DhcpSetContextForcedBroadcastFlag
0x18002ff3f  test    eax, eax
0x18002ff41  jz      short loc_18002FF65
0x18002ff43  test    byte ptr cs:xmmword_1800616A0, 2
0x18002ff4a  jz      short loc_18002FF88
0x18002ff4c  mov     edx, 0DDh
0x18002ff51  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002ff58  mov     ecx, 401h
0x18002ff5d  mov     r9d, eax
0x18002ff60  call    WPP_SF_D
0x18002ff65  test    byte ptr cs:xmmword_1800616A0, 2
0x18002ff6c  jz      short loc_18002FF88
0x18002ff6e  mov     r9, [rbx+38h]
0x18002ff72  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002ff79  mov     edx, 0DEh
0x18002ff7e  mov     ecx, 401h
0x18002ff83  call    WPP_SF_S
0x18002ff88  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002ff8f  jz      short loc_18002FFAB
0x18002ff91  mov     r9, [rbx+18h]
0x18002ff95  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002ff9c  mov     edx, 0DFh
0x18002ffa1  mov     ecx, 404h
0x18002ffa6  call    WPP_SF_q
0x18002ffab  mov     r13d, 1
0x18002ffb1  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x18002ffb8  jz      short loc_18002FFCA
0x18002ffba  mov     r8, [rbx+38h]
0x18002ffbe  lea     rdx, InitRebootState
0x18002ffc5  call    McTemplateU0z_EtwEventWriteTransfer
0x18002ffca  xor     edx, edx
0x18002ffcc  mov     rcx, rbx
0x18002ffcf  lea     r8d, [rdx+6Bh]
0x18002ffd3  call    TraceLogErrorv4
0x18002ffd8  lea     rax, ReRenewParameters
0x18002ffdf  mov     r9d, edi; int
0x18002ffe2  mov     [r15], rax
0x18002ffe5  lea     rdx, [rsp+130h+var_100]; int
0x18002ffea  lea     rax, [rsp+130h+var_F0]
0x18002ffef  mov     r8d, r13d; int
0x18002fff2  mov     [rsp+130h+var_108], rax; void *
0x18002fff7  mov     rcx, rbx; int
0x18002fffa  lea     rax, [rbp+30h+arg_8]
0x18002fffe  mov     [rsp+130h+var_110], rax; __int64
0x180030003  call    RenewLease
0x180030008  mov     edi, eax
0x18003000a  test    esi, esi
0x18003000c  jz      short loc_180030015
0x18003000e  mov     [rbx+308h], r13d
0x180030015  cmp     cs:DhcpGlobalIsShuttingDown, r12d
0x18003001c  jz      short loc_180030051
0x18003001e  mov     edi, 41h ; 'A'
0x180030023  test    byte ptr cs:xmmword_1800616A0, 2
0x18003002a  jz      loc_180030376
0x180030030  mov     edx, 0E0h
0x180030035  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18003003c  mov     ecx, 401h
0x180030041  mov     r9d, 41h ; 'A'
0x180030047  call    WPP_SF_D
0x18003004c  jmp     loc_180030376
0x180030051  test    edi, edi
0x180030053  jz      loc_1800301DE
0x180030059  sub     eax, 41h ; 'A'
0x18003005c  jz      short loc_180030023
0x18003005e  sub     eax, 486h
0x180030063  jz      loc_180030195
0x180030069  sub     eax, 6
0x18003006c  jz      loc_180030158
0x180030072  cmp     eax, 0FFDh
0x180030077  jz      loc_180030158
0x18003007d  test    byte ptr cs:xmmword_1800616A0, 2
0x180030084  jz      short loc_18003009F
0x180030086  mov     edx, 0E1h
0x18003008b  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x180030092  mov     ecx, 401h
0x180030097  mov     r9d, edi
0x18003009a  call    WPP_SF_D
0x18003009f  cmp     [rbx+234h], r12d
0x1800300a6  jnz     short loc_180030100
0x1800300a8  mov     rcx, rbx
0x1800300ab  call    RefreshNotNeeded
0x1800300b0  cmp     eax, r13d
0x1800300b3  jz      short loc_180030100
0x1800300b5  test    byte ptr cs:xmmword_1800616A0, 8
0x1800300bc  jz      short loc_1800300D4
0x1800300be  mov     edx, 0E3h
0x1800300c3  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x1800300ca  mov     ecx, 403h
0x1800300cf  call    WPP_SF_
0x1800300d4  mov     r9, [rbp+30h+arg_20]
0x1800300d8  mov     r8, r15
0x1800300db  mov     edx, 0Bh
0x1800300e0  mov     dword ptr [rsp+130h+var_110], edi
0x1800300e4  mov     rcx, rbx
0x1800300e7  call    DhcpSetEventInRenewState
0x1800300ec  xor     edx, edx
0x1800300ee  mov     rcx, rbx
0x1800300f1  call    DhcpUninitializeInterface
0x1800300f6  mov     edi, 79h ; 'y'
0x1800300fb  jmp     loc_1800302B6
0x180030100  test    byte ptr cs:xmmword_1800616A0, 10h
0x180030107  jz      short loc_18003011F
0x180030109  mov     edx, 0E2h
0x18003010e  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x180030115  mov     ecx, 404h
0x18003011a  call    WPP_SF_
0x18003011f  xor     edx, edx; Val
0x180030121  lea     rcx, [rsp+130h+var_F0]; void *
0x180030126  mov     r8d, 0C8h; Size
0x18003012c  call    memset_0
0x180030131  lea     rdx, [rsp+130h+var_F0]
0x180030136  mov     rcx, rbx
0x180030139  call    DhcpCopyExistingStackParams
0x18003013e  cmp     dword ptr [rbp+30h+arg_8], r12d
0x180030142  jz      loc_180030227
0x180030148  mov     r8d, r13d
0x18003014b  mov     rcx, rbx
0x18003014e  call    SetExpiryTimeForNonReceivedOptions
0x180030153  jmp     loc_180030227
0x180030158  mov     r9, [rbp+30h+arg_20]
0x18003015c  mov     r8, r15
0x18003015f  mov     edx, 0Eh
0x180030164  mov     dword ptr [rsp+130h+var_110], edi
0x180030168  mov     rcx, rbx
0x18003016b  call    DhcpSetEventInRenewState
0x180030170  xor     edx, edx
0x180030172  mov     rcx, rbx
0x180030175  call    DhcpUninitializeInterface
0x18003017a  mov     [rbx+84h], r12d
0x180030181  mov     [rbx+788h], r13d
0x180030188  test    edi, edi
0x18003018a  jz      loc_180030227
0x180030190  jmp     loc_1800302AD
0x180030195  test    esi, esi
0x180030197  jz      short loc_1800301A0
0x180030199  mov     [rbx+308h], r12d
0x1800301a0  cmp     cs:g_fVelocityDhcpOption108RenewFix, r12d
0x1800301a7  jz      short loc_1800301BD
0x1800301a9  mov     rax, [rbx+870h]
0x1800301b0  neg     rax
0x1800301b3  sbb     edx, edx
0x1800301b5  and     edx, 11h
0x1800301b8  add     edx, 8
0x1800301bb  jmp     short loc_1800301C2
0x1800301bd  mov     edx, 8
0x1800301c2  mov     r9, [rbp+30h+arg_20]
0x1800301c6  mov     r8, r15
0x1800301c9  mov     rcx, rbx
0x1800301cc  mov     dword ptr [rsp+130h+var_110], 4C7h
0x1800301d4  call    DhcpSetEventInRenewState
0x1800301d9  jmp     loc_180030376
0x1800301de  mov     rdx, [rbx+38h]
0x1800301e2  mov     ecx, 8
0x1800301e7  call    SetEventNotification
0x1800301ec  cmp     cs:DhcpGlobalUseNetworkHint, r12d
0x1800301f3  jz      short loc_180030227
0x1800301f5  mov     rcx, [rbx+18h]
0x1800301f9  lea     r8, [rbp+30h+arg_18]
0x1800301fd  xor     r9d, r9d
0x180030200  lea     rdx, [rsp+130h+lpSubKey]
0x180030205  call    GetNetworkHint
0x18003020a  mov     rdx, [rsp+130h+lpSubKey]; lpSubKey
0x18003020f  test    rdx, rdx
0x180030212  jz      short loc_180030227
0x180030214  mov     rcx, [rbx+2D8h]; hKey
0x18003021b  xor     r9d, r9d; Reserved
0x18003021e  xor     r8d, r8d; samDesired
0x180030221  call    cs:__imp_RegDeleteKeyExW
0x180030227  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003022e  jz      short loc_18003024A
0x180030230  mov     r9, [rbx+18h]
0x180030234  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18003023b  mov     edx, 0E4h
0x180030240  mov     ecx, 404h
0x180030245  call    WPP_SF_q
0x18003024a  test    esi, esi
0x18003024c  lea     rdx, [rsp+130h+var_F0]
0x180030251  mov     r8d, r12d
0x180030254  mov     rcx, rbx
0x180030257  setz    r8b
0x18003025b  call    ApplyDhcpConfigurationToNIC
0x180030260  mov     edi, eax
0x180030262  test    byte ptr cs:xmmword_1800616A0, 10h
0x180030269  jz      short loc_18003028D
0x18003026b  mov     r8, [rbx+18h]
0x18003026f  mov     edx, 0E5h
0x180030274  mov     [rsp+130h+var_110], r8
0x180030279  mov     ecx, 404h
0x18003027e  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x180030285  mov     r9d, eax
0x180030288  call    WPP_SF_dJ
0x18003028d  mov     r9, [rbp+30h+arg_20]
0x180030291  mov     r8, r15
0x180030294  mov     rcx, rbx
0x180030297  test    edi, edi
0x180030299  jz      loc_180030342
0x18003029f  mov     edx, 0Bh
0x1800302a4  mov     dword ptr [rsp+130h+var_110], edi
0x1800302a8  call    DhcpSetEventInRenewState
0x1800302ad  cmp     edi, 79h ; 'y'
0x1800302b0  jnz     loc_180030376
0x1800302b6  mov     rcx, rbx
0x1800302b9  call    DhcpApplyFallback
0x1800302be  test    eax, eax
0x1800302c0  jnz     short loc_180030323
0x1800302c2  mov     al, cs:byte_1800619C9
0x1800302c8  test    r13b, al
0x1800302cb  jz      short loc_18003030A
0x1800302cd  mov     r9d, [rbx+30h]
0x1800302d1  lea     r8, [rbx+20h]
0x1800302d5  lea     rdx, SelfPerftrackDHCPFallbackAddress
0x1800302dc  mov     dword ptr [rsp+130h+var_110], r12d
0x1800302e1  call    McTemplateU0jqq_EtwEventWriteTransfer
0x1800302e6  mov     al, cs:byte_1800619C9
0x1800302ec  test    r13b, al
0x1800302ef  jz      short loc_18003030A
0x1800302f1  mov     r9d, [rbx+30h]
0x1800302f5  lea     r8, [rbx+20h]
0x1800302f9  lea     rdx, PerftrackWlanDHCPFallbackAddress
0x180030300  mov     dword ptr [rsp+130h+var_110], r12d
0x180030305  call    McTemplateU0jqq_EtwEventWriteTransfer
0x18003030a  mov     r9, [rbp+30h+arg_20]
0x18003030e  mov     r8, r15
0x180030311  mov     dword ptr [rsp+130h+var_110], 79h ; 'y'
0x180030319  mov     edx, 0Ch
0x18003031e  mov     rcx, rbx
0x180030321  jmp     short loc_18003034C
0x180030323  test    cs:byte_1800619C9, r13b
0x18003032a  jz      short loc_180030376
0x18003032c  mov     r9d, [rbx+30h]
0x180030330  lea     r8, [rbx+20h]
0x180030334  lea     rdx, PerftrackRequestNoResponse
0x18003033b  call    McTemplateU0jq_EtwEventWriteTransfer
0x180030340  jmp     short loc_180030376
0x180030342  mov     dword ptr [rsp+130h+var_110], r12d
0x180030347  mov     edx, 9
0x18003034c  call    DhcpSetEventInRenewState
0x180030351  mov     rcx, rbx
0x180030354  call    DhcpSetDADPending
0x180030359  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x180030360  jz      short loc_180030376
0x180030362  mov     r9d, [rbx+78h]
0x180030366  lea     rdx, DadRegistered
0x18003036d  mov     r8d, [rbx+30h]
0x180030371  call    McTemplateU0qq_EtwEventWriteTransfer
0x180030376  lea     rcx, [rsp+130h+lpSubKey]
0x18003037b  call    DhcpPunycodeFree
0x180030380  lea     rcx, [rsp+130h+var_F0]; void *
0x180030385  call    DhcpCleanParsedOptions
0x18003038a  test    byte ptr cs:xmmword_1800616A0, 10h
0x180030391  jz      short loc_1800303AC
0x180030393  mov     edx, 0E6h
0x180030398  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18003039f  mov     ecx, 404h
0x1800303a4  mov     r9d, edi
0x1800303a7  call    WPP_SF_D
0x1800303ac  lea     r11, [rsp+130h+var_20]
0x1800303b4  mov     eax, edi
0x1800303b6  mov     rbx, [r11+30h]
0x1800303ba  mov     rsi, [r11+40h]
0x1800303be  mov     rsp, r11
0x1800303c1  pop     r15
0x1800303c3  pop     r13
0x1800303c5  pop     r12
0x1800303c7  pop     rdi
0x1800303c8  pop     rbp
0x1800303c9  retn
```

# CreateDhcpv6Release

- ea: `0x18001fc58`
- end: `0x1800200d2`
- name: `CreateDhcpv6Release`
- size: `1146`
- prototype: `__int64 __fastcall(__int64, __int16 *, int *, int, void *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800216a4`
- `0x1800218e0`

## callees

- `0x180001d8c`
- `0x180002cac`
- `0x180002f80`
- `0x180004b30`
- `0x18000e1ec`
- `0x18000ed3c`
- `0x180017ffc`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001fc58`
- `0x180030920`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Release(__int64 a1, __int16 *a2, int *a3, int a4, void *a5, void *a6)
{
  __int64 v10; // rbx
  unsigned int appended; // ebx
  __int16 v12; // ax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r9
  _QWORD *v18; // r14
  void *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  void *v22; // rcx
  __int64 v23; // rdx
  u_short v24; // r9
  int v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v29; // [rsp+80h] [rbp-80h] BYREF
  int Src; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v31; // [rsp+88h] [rbp-78h] BYREF
  int *v32; // [rsp+90h] [rbp-70h]
  _BYTE v33[208]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[208]; // [rsp+170h] [rbp+70h] BYREF
  _WORD v35[2048]; // [rsp+240h] [rbp+140h] BYREF

  v32 = a3;
  v27 = 0;
  v31 = 0;
  Src = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v10 = a1 + 668;
      if ( a1 != -668 )
      {
        if ( a3 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_S(1028, 79, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
          if ( a4 && !a5 )
          {
            appended = 87;
            goto LABEL_37;
          }
          memset_0(v33, 0, 0xC8u);
          memset_0(v34, 0, 0xC8u);
          v12 = *a2;
          *(_BYTE *)v10 = 8;
          *(_WORD *)(v10 + 1) = v12;
          *(_BYTE *)(v10 + 3) = *((_BYTE *)a2 + 2);
          v28 = v10 + 4;
          v26 = 4;
          v29 = 0;
          appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v26, &v28, a1 + 4763);
          if ( appended )
            goto LABEL_37;
          AddToArray(v33, v13, &v27, 8);
          appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v26, &v28, a1 + 4763);
          if ( appended )
            goto LABEL_37;
          AddToArray(v33, v14, &v27, 1);
          if ( !a4 )
            a6 = (void *)(a1 + 480);
          appended = Dhcpv6AppendOption(a6, 0x10u, 2u, &v26, &v28, a1 + 4763);
          if ( appended )
            goto LABEL_37;
          AddToArray(v33, v15, &v27, 2);
          if ( a4 )
          {
            appended = Dhcpv6AppendOption(a5, 0x30u, 0x19u, &v26, &v28, a1 + 4763);
            if ( appended )
              goto LABEL_37;
            v17 = 25;
          }
          else
          {
            v18 = *(_QWORD **)(a1 + 104);
            while ( v18 != (_QWORD *)(a1 + 104) )
            {
              v19 = v18;
              v18 = (_QWORD *)*v18;
              appended = Dhcpv6AppendOption(v19, 0xA8u, 3u, &v26, &v28, a1 + 4763);
              if ( appended )
                goto LABEL_37;
            }
            v17 = 3;
          }
          AddToArray(v33, v16, &v27, v17);
          if ( *(_DWORD *)(a1 + 9032) )
            goto LABEL_28;
          appended = Dhcpv6AppendDefaultVendorClassOption(&v26, (u_short **)&v28, a1 + 4763);
          if ( appended )
            goto LABEL_37;
          AddToArray(v33, v20, &v27, 16);
          v22 = *(void **)(a1 + 656);
          if ( !v22 )
          {
LABEL_28:
            appended = Dhcpv6AppendSendOptions(
                         a1,
                         (_QWORD **)(a1 + 616),
                         *(_QWORD *)(a1 + 656),
                         *(_DWORD *)(a1 + 664),
                         &v28,
                         &v26,
                         a1 + 4763,
                         (__int64)v33,
                         &v27,
                         (__int64)v34,
                         &v31,
                         v35,
                         &v29);
            if ( !appended
              && (*(_DWORD *)(a1 + 9032)
               || (unsigned int)IsPresentInArray(v33, 0)
               || !v29
               || v28 + (unsigned __int64)v29 > a1 + 4763
               || (appended = Dhcpv6AppendOption(v35, v29, v24, &v26, &v28, a1 + 4763)) == 0) )
            {
              *v32 = v26;
              return appended;
            }
            goto LABEL_37;
          }
          appended = Dhcpv6AppendUserClassOption(v22, *(unsigned __int8 *)(a1 + 664), v21, &v26, &v28, a1 + 4763);
          if ( !appended )
          {
            AddToArray(v33, v23, &v27, 15);
            goto LABEL_28;
          }
LABEL_37:
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_SD(
              1025,
              80,
              (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
              *(_QWORD *)(a1 + 56),
              appended);
          goto LABEL_39;
        }
      }
    }
  }
  appended = 87;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    WPP_SF_D(1025, 78, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
    goto LABEL_37;
  }
LABEL_39:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
  TraceLogErrorv6(a1, appended, 46);
  return appended;
}

```

## disassembly

```asm
0x18001fc58  mov     [rsp-8+arg_8], rbx
0x18001fc5d  push    rbp
0x18001fc5e  push    rsi
0x18001fc5f  push    rdi
0x18001fc60  push    r12
0x18001fc62  push    r13
0x18001fc64  push    r14
0x18001fc66  push    r15
0x18001fc68  lea     rbp, [rsp-1150h]
0x18001fc70  mov     eax, 1250h
0x18001fc75  call    _alloca_probe
0x18001fc7a  sub     rsp, rax
0x18001fc7d  mov     rax, cs:__security_cookie
0x18001fc84  xor     rax, rsp
0x18001fc87  mov     [rbp+1180h+var_40], rax
0x18001fc8e  mov     r13, [rbp+1180h+arg_20]
0x18001fc95  xor     esi, esi
0x18001fc97  mov     r12, [rbp+1180h+arg_28]
0x18001fc9e  mov     rax, r8
0x18001fca1  mov     [rbp+1180h+var_11F0], rax
0x18001fca5  mov     r14d, r9d
0x18001fca8  mov     [rsp+1280h+var_120C], esi
0x18001fcac  mov     r15, rdx
0x18001fcaf  mov     [rbp+1180h+var_11F8], esi
0x18001fcb2  mov     rdi, rcx
0x18001fcb5  mov     [rbp+1180h+Src], esi
0x18001fcb8  test    rcx, rcx
0x18001fcbb  jz      loc_18002002D
0x18001fcc1  test    rdx, rdx
0x18001fcc4  jz      loc_18002002D
0x18001fcca  lea     rbx, [rcx+29Ch]
0x18001fcd1  test    rbx, rbx
0x18001fcd4  jz      loc_18002002D
0x18001fcda  test    rax, rax
0x18001fcdd  jz      loc_18002002D
0x18001fce3  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001fcea  jz      short loc_18001FD04
0x18001fcec  mov     r9, [rdi+38h]
0x18001fcf0  lea     edx, [rsi+4Fh]
0x18001fcf3  mov     ecx, 404h
0x18001fcf8  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001fcff  call    WPP_SF_S
0x18001fd04  test    r14d, r14d
0x18001fd07  jz      short loc_18001FD17
0x18001fd09  test    r13, r13
0x18001fd0c  jnz     short loc_18001FD17
0x18001fd0e  lea     ebx, [r13+57h]
0x18001fd12  jmp     loc_180020052
0x18001fd17  mov     esi, 0C8h
0x18001fd1c  lea     rcx, [rbp+1180h+var_11E0]; void *
0x18001fd20  mov     r8d, esi; Size
0x18001fd23  xor     edx, edx; Val
0x18001fd25  call    memset_0
0x18001fd2a  mov     r8d, esi; Size
0x18001fd2d  lea     rcx, [rbp+1180h+var_1110]; void *
0x18001fd31  xor     edx, edx; Val
0x18001fd33  call    memset_0
0x18001fd38  movzx   eax, word ptr [r15]
0x18001fd3c  lea     rsi, [rdi+129Bh]
0x18001fd43  mov     ecx, 4
0x18001fd48  mov     byte ptr [rbx], 8
0x18001fd4b  mov     [rbx+1], ax
0x18001fd4f  lea     r9, [rsp+1280h+var_1210]
0x18001fd54  mov     al, [r15+2]
0x18001fd58  mov     edx, ecx
0x18001fd5a  mov     [rbx+3], al
0x18001fd5d  lea     rax, [rbx+4]
0x18001fd61  mov     [rsp+1280h+var_1208], rax
0x18001fd66  lea     r8d, [rcx+4]
0x18001fd6a  lea     rax, [rsp+1280h+var_1208]
0x18001fd6f  mov     [rsp+1280h+var_1210], ecx
0x18001fd73  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fd78  lea     rcx, [rbp+1180h+Src]; Src
0x18001fd7c  mov     [rsp+1280h+var_1260], rax; __int64
0x18001fd81  mov     [rbp+1180h+var_1200], 0
0x18001fd88  call    Dhcpv6AppendOption
0x18001fd8d  mov     ebx, eax
0x18001fd8f  test    eax, eax
0x18001fd91  jnz     loc_180020052
0x18001fd97  lea     r9d, [rax+8]
0x18001fd9b  lea     r8, [rsp+1280h+var_120C]
0x18001fda0  lea     rcx, [rbp+1180h+var_11E0]
0x18001fda4  call    AddToArray
0x18001fda9  lea     rax, [rsp+1280h+var_1208]
0x18001fdae  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fdb3  lea     r15d, [rbx+1]
0x18001fdb7  mov     [rsp+1280h+var_1260], rax; __int64
0x18001fdbc  mov     r8d, r15d
0x18001fdbf  lea     edx, [rbx+10h]
0x18001fdc2  lea     rcx, [rdi+1C8h]; Src
0x18001fdc9  lea     r9, [rsp+1280h+var_1210]
0x18001fdce  call    Dhcpv6AppendOption
0x18001fdd3  mov     ebx, eax
0x18001fdd5  test    eax, eax
0x18001fdd7  jnz     loc_180020052
0x18001fddd  mov     r9d, r15d
0x18001fde0  lea     r8, [rsp+1280h+var_120C]
0x18001fde5  lea     rcx, [rbp+1180h+var_11E0]
0x18001fde9  call    AddToArray
0x18001fdee  test    r14d, r14d
0x18001fdf1  jnz     short loc_18001FDFA
0x18001fdf3  lea     r12, [rdi+1E0h]
0x18001fdfa  mov     r15d, 2
0x18001fe00  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fe05  lea     rax, [rsp+1280h+var_1208]
0x18001fe0a  mov     r8d, r15d
0x18001fe0d  lea     r9, [rsp+1280h+var_1210]
0x18001fe12  mov     [rsp+1280h+var_1260], rax; __int64
0x18001fe17  mov     rcx, r12; Src
0x18001fe1a  lea     edx, [r15+0Eh]
0x18001fe1e  call    Dhcpv6AppendOption
0x18001fe23  mov     ebx, eax
0x18001fe25  test    eax, eax
0x18001fe27  jnz     loc_180020052
0x18001fe2d  mov     r9d, r15d
0x18001fe30  lea     r8, [rsp+1280h+var_120C]
0x18001fe35  lea     rcx, [rbp+1180h+var_11E0]
0x18001fe39  call    AddToArray
0x18001fe3e  test    r14d, r14d
0x18001fe41  jz      short loc_18001FE78
0x18001fe43  lea     rax, [rsp+1280h+var_1208]
0x18001fe48  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fe4d  lea     r14d, [r15+17h]
0x18001fe51  mov     [rsp+1280h+var_1260], rax; __int64
0x18001fe56  mov     r8d, r14d
0x18001fe59  lea     edx, [rbx+30h]
0x18001fe5c  lea     r9, [rsp+1280h+var_1210]
0x18001fe61  mov     rcx, r13; Src
0x18001fe64  call    Dhcpv6AppendOption
0x18001fe69  mov     ebx, eax
0x18001fe6b  test    eax, eax
0x18001fe6d  jnz     loc_180020052
0x18001fe73  mov     r9d, r14d
0x18001fe76  jmp     short loc_18001FEBF
0x18001fe78  lea     r15, [rdi+68h]
0x18001fe7c  mov     r12d, 3
0x18001fe82  mov     r14, [r15]
0x18001fe85  cmp     r14, r15
0x18001fe88  jz      short loc_18001FEBC
0x18001fe8a  lea     rax, [rsp+1280h+var_1208]
0x18001fe8f  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fe94  mov     rcx, r14; Src
0x18001fe97  mov     [rsp+1280h+var_1260], rax; __int64
0x18001fe9c  mov     r14, [r14]
0x18001fe9f  lea     r9, [rsp+1280h+var_1210]
0x18001fea4  mov     r8d, r12d
0x18001fea7  mov     edx, 0A8h
0x18001feac  call    Dhcpv6AppendOption
0x18001feb1  mov     ebx, eax
0x18001feb3  test    eax, eax
0x18001feb5  jz      short loc_18001FE85
0x18001feb7  jmp     loc_180020052
0x18001febc  mov     r9d, r12d
0x18001febf  lea     r8, [rsp+1280h+var_120C]
0x18001fec4  lea     rcx, [rbp+1180h+var_11E0]
0x18001fec8  call    AddToArray
0x18001fecd  cmp     dword ptr [rdi+2348h], 0
0x18001fed4  jnz     short loc_18001FF4C
0x18001fed6  mov     r8, rsi
0x18001fed9  lea     rdx, [rsp+1280h+var_1208]
0x18001fede  lea     rcx, [rsp+1280h+var_1210]
0x18001fee3  call    Dhcpv6AppendDefaultVendorClassOption
0x18001fee8  mov     ebx, eax
0x18001feea  test    eax, eax
0x18001feec  jnz     loc_180020052
0x18001fef2  lea     r9d, [rax+10h]
0x18001fef6  lea     r8, [rsp+1280h+var_120C]
0x18001fefb  lea     rcx, [rbp+1180h+var_11E0]
0x18001feff  call    AddToArray
0x18001ff04  mov     rcx, [rdi+290h]; Src
0x18001ff0b  test    rcx, rcx
0x18001ff0e  jz      short loc_18001FF4C
0x18001ff10  movzx   edx, byte ptr [rdi+298h]
0x18001ff17  lea     rax, [rsp+1280h+var_1208]
0x18001ff1c  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001ff21  lea     r9, [rsp+1280h+var_1210]
0x18001ff26  mov     [rsp+1280h+var_1260], rax; __int64
0x18001ff2b  call    Dhcpv6AppendUserClassOption
0x18001ff30  mov     ebx, eax
0x18001ff32  test    eax, eax
0x18001ff34  jnz     loc_180020052
0x18001ff3a  lea     r9d, [rax+0Fh]
0x18001ff3e  lea     r8, [rsp+1280h+var_120C]
0x18001ff43  lea     rcx, [rbp+1180h+var_11E0]
0x18001ff47  call    AddToArray
0x18001ff4c  mov     r9d, [rdi+298h]
0x18001ff53  lea     rax, [rbp+1180h+var_1200]
0x18001ff57  mov     r8, [rdi+290h]
0x18001ff5e  lea     rdx, [rdi+268h]
0x18001ff65  mov     [rsp+1280h+var_1220], rax
0x18001ff6a  mov     rcx, rdi
0x18001ff6d  lea     rax, [rbp+1180h+var_1040]
0x18001ff74  mov     [rsp+1280h+var_1228], rax
0x18001ff79  lea     rax, [rbp+1180h+var_11F8]
0x18001ff7d  mov     [rsp+1280h+var_1230], rax
0x18001ff82  lea     rax, [rbp+1180h+var_1110]
0x18001ff86  mov     [rsp+1280h+var_1238], rax
0x18001ff8b  lea     rax, [rsp+1280h+var_120C]
0x18001ff90  mov     [rsp+1280h+var_1240], rax
0x18001ff95  lea     rax, [rbp+1180h+var_11E0]
0x18001ff99  mov     [rsp+1280h+var_1248], rax
0x18001ff9e  lea     rax, [rsp+1280h+var_1210]
0x18001ffa3  mov     [rsp+1280h+var_1250], rsi
0x18001ffa8  mov     [rsp+1280h+var_1258], rax
0x18001ffad  lea     rax, [rsp+1280h+var_1208]
0x18001ffb2  mov     [rsp+1280h+var_1260], rax
0x18001ffb7  call    Dhcpv6AppendSendOptions
0x18001ffbc  mov     ebx, eax
0x18001ffbe  test    eax, eax
0x18001ffc0  jnz     loc_180020052
0x18001ffc6  cmp     [rdi+2348h], eax
0x18001ffcc  jnz     short loc_18002001D
0x18001ffce  xor     edx, edx
0x18001ffd0  lea     r9d, [rax+11h]
0x18001ffd4  lea     rcx, [rbp+1180h+var_11E0]
0x18001ffd8  call    IsPresentInArray
0x18001ffdd  test    eax, eax
0x18001ffdf  jnz     short loc_18002001D
0x18001ffe1  mov     edx, [rbp+1180h+var_1200]
0x18001ffe4  test    edx, edx
0x18001ffe6  jz      short loc_18002001D
0x18001ffe8  mov     eax, edx
0x18001ffea  add     rax, [rsp+1280h+var_1208]
0x18001ffef  cmp     rax, rsi
0x18001fff2  ja      short loc_18002001D
0x18001fff4  mov     r8d, r9d
0x18001fff7  mov     [rsp+1280h+var_1258], rsi; __int64
0x18001fffc  lea     rax, [rsp+1280h+var_1208]
0x180020001  lea     r9, [rsp+1280h+var_1210]
0x180020006  mov     [rsp+1280h+var_1260], rax; __int64
0x18002000b  lea     rcx, [rbp+1180h+var_1040]; Src
0x180020012  call    Dhcpv6AppendOption
0x180020017  mov     ebx, eax
0x180020019  test    eax, eax
0x18002001b  jnz     short loc_180020052
0x18002001d  mov     rcx, [rbp+1180h+var_11F0]
0x180020021  mov     eax, [rsp+1280h+var_1210]
0x180020025  mov     [rcx], eax
0x180020027  test    ebx, ebx
0x180020029  jz      short loc_1800200A5
0x18002002b  jmp     short loc_180020052
0x18002002d  mov     ebx, 57h ; 'W'
0x180020032  test    byte ptr cs:xmmword_1800423E0, 2
0x180020039  jz      short loc_180020079
0x18002003b  lea     edx, [rbx-9]
0x18002003e  mov     ecx, 401h
0x180020043  mov     r9d, ebx
0x180020046  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18002004d  call    WPP_SF_D
0x180020052  test    byte ptr cs:xmmword_1800423E0, 2
0x180020059  jz      short loc_180020079
0x18002005b  mov     r9, [rdi+38h]
0x18002005f  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180020066  mov     edx, 50h ; 'P'
0x18002006b  mov     dword ptr [rsp+1280h+var_1260], ebx
0x18002006f  mov     ecx, 401h
0x180020074  call    WPP_SF_SD
0x180020079  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180020080  jz      short loc_180020095
0x180020082  mov     r8d, [rdi+30h]
0x180020086  lea     rdx, ErrorCreatingPacket
0x18002008d  mov     r9d, ebx
0x180020090  call    McTemplateU0qq_EtwEventWriteTransfer
0x180020095  mov     r8d, 2Eh ; '.'
0x18002009b  mov     edx, ebx
0x18002009d  mov     rcx, rdi
0x1800200a0  call    TraceLogErrorv6
0x1800200a5  mov     eax, ebx
0x1800200a7  mov     rcx, [rbp+1180h+var_40]
0x1800200ae  xor     rcx, rsp; StackCookie
0x1800200b1  call    __security_check_cookie
0x1800200b6  mov     rbx, [rsp+1280h+arg_8]
0x1800200be  add     rsp, 1250h
0x1800200c5  pop     r15
0x1800200c7  pop     r14
0x1800200c9  pop     r13
0x1800200cb  pop     r12
0x1800200cd  pop     rdi
0x1800200ce  pop     rsi
0x1800200cf  pop     rbp
0x1800200d0  retn
```

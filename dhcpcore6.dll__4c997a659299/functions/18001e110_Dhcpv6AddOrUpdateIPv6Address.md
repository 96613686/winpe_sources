# Dhcpv6AddOrUpdateIPv6Address

- ea: `0x18001e110`
- end: `0x18001e5b7`
- name: `Dhcpv6AddOrUpdateIPv6Address`
- size: `1191`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001225c`

## callees

- `0x180001bb8`
- `0x180004a8c`
- `0x180004c3c`
- `0x18000dee0`
- `0x180018580`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001e110`
- `0x180031a8c`
- `0x180031b48`
- `0x180031bb8`
- `0x180031c54`
- `0x1800338c0`
- `0x180034b44`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e391`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e391`

## pseudocode

```c
__int64 __fastcall Dhcpv6AddOrUpdateIPv6Address(_QWORD *a1, unsigned int a2, __int128 *a3, __int64 a4, int a5, int a6)
{
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  __int128 v13; // xmm0
  int v14; // eax
  int v15; // r12d
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int AllParameters; // ebx
  __int128 v21; // xmm0
  __int64 v22; // rcx
  bool v23; // zf
  unsigned int v24; // eax
  __int128 v25; // xmm0
  __int64 v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v33[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v34; // [rsp+D4h] [rbp-2Ch]
  __int128 v35; // [rsp+DCh] [rbp-24h]

  v29 = 0;
  memset_0(v33, 0, 0x140u);
  v12 = (unsigned int)g_fVelocityDhcpnsiv6StyleUpdate;
  v30 = 0;
  memset(v31, 0, 28);
  memset(v32, 0, 24);
  if ( g_fVelocityDhcpnsiv6StyleUpdate && (xmmword_1800423E0 & 0x10) != 0 )
  {
    v28 = a6;
    WPP_SF_qDqdDD(g_fVelocityDhcpnsiv6StyleUpdate, v9, v10, (_DWORD)a1, a2, (char)a3);
    v12 = (unsigned int)g_fVelocityDhcpnsiv6StyleUpdate;
  }
  v13 = *a3;
  *(_QWORD *)&v32[0] = *a1;
  v14 = -1;
  DWORD1(v31[1]) = -1;
  v15 = -1;
  WORD4(v31[1]) = -1;
  if ( a5 != -1 )
    v15 = a5;
  LOWORD(v31[1]) = 128;
  LODWORD(v31[0]) = v15;
  *(_OWORD *)((char *)v32 + 8) = v13;
  if ( a6 != -1 )
    v14 = a6;
  DWORD1(v31[0]) = v14;
  *((_QWORD *)&v31[0] + 1) = 0x300000003LL;
  if ( !(_DWORD)v12 && (xmmword_1800423E0 & 0x10) != 0 )
  {
    v27 = *a1;
    WPP_SF_dDJ(v12, 31);
  }
  v16 = SetAllParameters(v12, (unsigned int)&v29, v10, v11, (__int64)v32, v27, (__int64)v31, 28, v28, 2);
  AllParameters = v16;
  if ( !g_fVelocityDhcpnsiv6StyleUpdate && (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 32, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v16);
  if ( AllParameters == 5010 )
  {
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 8) != 0 )
      McTemplateU0b16q_EtwEventWriteTransfer(v18, V6AddressAlreadyExists, a3, a2);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF__IPV6_JD(v18, v17, v19, a3, *a1, 5010);
  }
  if ( !g_fVelocityDhcpnsiv6StyleUpdate )
  {
    if ( AllParameters )
      goto LABEL_50;
    do
    {
LABEL_31:
      Sleep(0x1F4u);
      *(_QWORD *)&v32[0] = *a1;
      if ( g_fVelocityDhcpnsiv6StyleUpdate )
      {
        AllParameters = GetAllParameters(
                          v22,
                          (unsigned int)&NPI_MS_IPV6_MODULEID,
                          10,
                          (unsigned int)v32,
                          24,
                          0,
                          0,
                          (__int64)&v30,
                          8,
                          0,
                          0);
        v23 = AllParameters == 0;
      }
      else
      {
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_dDJ(v22, 34);
        v24 = GetAllParameters(
                v22,
                (unsigned int)&NPI_MS_IPV6_MODULEID,
                10,
                (unsigned int)v32,
                24,
                0,
                0,
                (__int64)&v30,
                8,
                0,
                0);
        AllParameters = v24;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_D(1028, 35, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v24);
        v23 = AllParameters == 0;
      }
      if ( !v23 )
        goto LABEL_21;
    }
    while ( HIDWORD(v30) == 1 );
    if ( g_fVelocityDhcpnsiv6StyleUpdate )
    {
      v18 = (unsigned int)(HIDWORD(v30) - 2);
      if ( HIDWORD(v30) != 2 )
      {
        v18 = (unsigned int)(HIDWORD(v30) - 3);
        if ( (unsigned int)v18 < 2 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF__IPV6_(1028, 36, v19, a3);
        }
        else
        {
          AllParameters = 31;
        }
        goto LABEL_21;
      }
    }
    else
    {
      v18 = (unsigned int)(HIDWORD(v30) - 2);
      if ( HIDWORD(v30) != 2 )
      {
        v18 = (unsigned int)(HIDWORD(v30) - 3);
        if ( (unsigned int)v18 >= 2 )
        {
          AllParameters = 31;
          goto LABEL_50;
        }
        goto LABEL_56;
      }
    }
    AllParameters = 4100;
    goto LABEL_21;
  }
  if ( !AllParameters )
    goto LABEL_31;
LABEL_21:
  if ( g_fVelocityDhcpnsiv6StyleUpdate )
  {
    if ( AllParameters )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF__IPV6_D(v18, 37, v19, a3, AllParameters);
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
        McTemplateU0b16q_EtwEventWriteTransfer(v18, ErrorAddingIpv6Address, a3, AllParameters);
      InitializeTraceElementFromContext(v33, 0, AllParameters, 19);
      v21 = *a3;
      v34 = 23;
      v35 = v21;
      TraceLogEx(v33);
    }
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 38, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, AllParameters);
    return AllParameters;
  }
LABEL_56:
  if ( !AllParameters )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF__IPV6_(1028, 40, v19, a3);
    return AllParameters;
  }
LABEL_50:
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF__IPV6_D(v18, 39, v19, a3, AllParameters);
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0b16q_EtwEventWriteTransfer(v18, ErrorAddingIpv6Address, a3, AllParameters);
  InitializeTraceElementFromContext(v33, 0, AllParameters, 19);
  v25 = *a3;
  v34 = 23;
  v35 = v25;
  TraceLogEx(v33);
  return AllParameters;
}

```

## disassembly

```asm
0x18001e110  mov     [rsp-8+arg_18], rbx
0x18001e115  push    rbp
0x18001e116  push    rsi
0x18001e117  push    rdi
0x18001e118  push    r12
0x18001e11a  push    r13
0x18001e11c  push    r14
0x18001e11e  push    r15
0x18001e120  lea     rbp, [rsp-110h]
0x18001e128  sub     rsp, 210h
0x18001e12f  mov     rax, cs:__security_cookie
0x18001e136  xor     rax, rsp
0x18001e139  mov     [rbp+140h+var_40], rax
0x18001e140  mov     rdi, r8
0x18001e143  mov     r15d, edx
0x18001e146  mov     r14, rcx
0x18001e149  xor     r13d, r13d
0x18001e14c  xor     edx, edx; Val
0x18001e14e  mov     [rsp+240h+var_1D0], r13d
0x18001e153  mov     r8d, 140h; Size
0x18001e159  lea     rcx, [rbp+140h+var_180]; void *
0x18001e15d  call    memset_0
0x18001e162  mov     ecx, cs:g_fVelocityDhcpnsiv6StyleUpdate
0x18001e168  xor     eax, eax
0x18001e16a  mov     ebx, [rbp+140h+arg_28]
0x18001e170  xorps   xmm1, xmm1
0x18001e173  mov     esi, [rbp+140h+arg_20]
0x18001e179  xorps   xmm0, xmm0
0x18001e17c  mov     [rbp+140h+var_190], rax
0x18001e180  mov     [rsp+240h+var_1C8], r13
0x18001e185  movups  [rbp+140h+var_1C0], xmm1
0x18001e189  movups  [rbp+140h+var_1C0+0Ch], xmm1
0x18001e18d  movups  [rbp+140h+var_1A0], xmm0
0x18001e191  test    ecx, ecx
0x18001e193  jz      short loc_18001E1BE
0x18001e195  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001e19c  jz      short loc_18001E1BE
0x18001e19e  mov     [rsp+240h+var_200], ebx
0x18001e1a2  mov     r9, r14
0x18001e1a5  mov     dword ptr [rsp+240h+var_208], esi
0x18001e1a9  mov     [rsp+240h+var_218], rdi
0x18001e1ae  mov     dword ptr [rsp+240h+var_220], r15d
0x18001e1b3  call    WPP_SF_qDqdDD
0x18001e1b8  mov     ecx, cs:g_fVelocityDhcpnsiv6StyleUpdate
0x18001e1be  mov     rax, [r14]
0x18001e1c1  movups  xmm0, xmmword ptr [rdi]
0x18001e1c4  mov     qword ptr [rbp+140h+var_1A0], rax
0x18001e1c8  or      eax, 0FFFFFFFFh
0x18001e1cb  cmp     esi, eax
0x18001e1cd  mov     [rbp+140h+var_1AC], eax
0x18001e1d0  mov     r12d, eax
0x18001e1d3  mov     [rbp+140h+var_1A8], 0FFFFh
0x18001e1d9  cmovnz  r12d, esi
0x18001e1dd  mov     [rbp+140h+var_1B0], 80h
0x18001e1e3  cmp     ebx, eax
0x18001e1e5  mov     dword ptr [rbp+140h+var_1C0], r12d
0x18001e1e9  movdqu  [rbp+140h+var_1A0+8], xmm0
0x18001e1ee  cmovnz  eax, ebx
0x18001e1f1  mov     dword ptr [rbp+140h+var_1C0+4], eax
0x18001e1f4  mov     eax, 3
0x18001e1f9  mov     dword ptr [rbp+140h+var_1C0+8], eax
0x18001e1fc  mov     dword ptr [rbp+140h+var_1C0+0Ch], eax
0x18001e1ff  test    ecx, ecx
0x18001e201  jnz     short loc_18001E226
0x18001e203  mov     sil, 10h
0x18001e206  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e20d  jz      short loc_18001E229
0x18001e20f  lea     edx, [rax+1Ch]
0x18001e212  mov     rax, [r14]
0x18001e215  mov     [rsp+240h+var_218], rax
0x18001e21a  mov     dword ptr [rsp+240h+var_220], r12d
0x18001e21f  call    WPP_SF_dDJ
0x18001e224  jmp     short loc_18001E229
0x18001e226  mov     sil, 10h
0x18001e229  mov     dword ptr [rsp+240h+var_1F8], 2
0x18001e231  lea     rax, [rbp+140h+var_1C0]
0x18001e235  mov     dword ptr [rsp+240h+var_208], 1Ch
0x18001e23d  lea     rdx, [rsp+240h+var_1D0]
0x18001e242  mov     [rsp+240h+var_210], rax
0x18001e247  lea     rax, [rbp+140h+var_1A0]
0x18001e24b  mov     [rsp+240h+var_220], rax
0x18001e250  call    SetAllParameters
0x18001e255  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r13d
0x18001e25c  mov     ebx, eax
0x18001e25e  jnz     short loc_18001E282
0x18001e260  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e267  jz      short loc_18001E282
0x18001e269  mov     edx, 20h ; ' '
0x18001e26e  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001e275  mov     ecx, 404h
0x18001e27a  mov     r9d, eax
0x18001e27d  call    WPP_SF_D
0x18001e282  cmp     ebx, 1392h
0x18001e288  jnz     short loc_18001E2C6
0x18001e28a  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 8
0x18001e291  jz      short loc_18001E2A5
0x18001e293  mov     r9d, r15d
0x18001e296  lea     rdx, V6AddressAlreadyExists
0x18001e29d  mov     r8, rdi
0x18001e2a0  call    McTemplateU0b16q_EtwEventWriteTransfer
0x18001e2a5  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e2ac  jz      short loc_18001E2C6
0x18001e2ae  mov     rax, [r14]
0x18001e2b1  mov     r9, rdi
0x18001e2b4  mov     dword ptr [rsp+240h+var_218], 1392h
0x18001e2bc  mov     [rsp+240h+var_220], rax
0x18001e2c1  call    WPP_SF__IPV6_JD
0x18001e2c6  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r13d
0x18001e2cd  jz      loc_18001E37E
0x18001e2d3  test    ebx, ebx
0x18001e2d5  jz      loc_18001E386
0x18001e2db  mov     r15d, 404h
0x18001e2e1  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r13d
0x18001e2e8  jz      loc_18001E596
0x18001e2ee  test    ebx, ebx
0x18001e2f0  jz      short loc_18001E355
0x18001e2f2  test    byte ptr cs:xmmword_1800423E0, 2
0x18001e2f9  jz      short loc_18001E30C
0x18001e2fb  mov     edx, 25h ; '%'
0x18001e300  mov     dword ptr [rsp+240h+var_220], ebx
0x18001e304  mov     r9, rdi
0x18001e307  call    WPP_SF__IPV6_D
0x18001e30c  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001e313  jz      short loc_18001E327
0x18001e315  mov     r9d, ebx
0x18001e318  lea     rdx, ErrorAddingIpv6Address
0x18001e31f  mov     r8, rdi
0x18001e322  call    McTemplateU0b16q_EtwEventWriteTransfer
0x18001e327  mov     r9d, 13h
0x18001e32d  lea     rcx, [rbp+140h+var_180]
0x18001e331  mov     r8d, ebx
0x18001e334  xor     edx, edx
0x18001e336  call    InitializeTraceElementFromContext
0x18001e33b  movups  xmm0, xmmword ptr [rdi]
0x18001e33e  mov     eax, 17h
0x18001e343  lea     rcx, [rbp+140h+var_180]
0x18001e347  mov     [rbp+140h+var_16C], ax
0x18001e34b  movdqu  [rbp+140h+var_164], xmm0
0x18001e350  call    TraceLogEx
0x18001e355  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e35c  jz      loc_18001E569
0x18001e362  mov     edx, 26h ; '&'
0x18001e367  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001e36e  mov     ecx, r15d
0x18001e371  mov     r9d, ebx
0x18001e374  call    WPP_SF_D
0x18001e379  jmp     loc_18001E569
0x18001e37e  test    ebx, ebx
0x18001e380  jnz     loc_18001E506
0x18001e386  mov     r15d, 404h
0x18001e38c  mov     ecx, 1F4h; dwMilliseconds
0x18001e391  call    cs:__imp_Sleep
0x18001e398  nop     dword ptr [rax+rax+00h]
0x18001e39d  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r13d
0x18001e3a4  mov     rax, [r14]
0x18001e3a7  mov     qword ptr [rbp+140h+var_1A0], rax
0x18001e3ab  jz      short loc_18001E3FF
0x18001e3ad  mov     [rsp+240h+var_1E0], r13d
0x18001e3b2  lea     rax, [rsp+240h+var_1C8]
0x18001e3b7  mov     [rsp+240h+var_1F0], r13d
0x18001e3bc  lea     r9, [rbp+140h+var_1A0]
0x18001e3c0  mov     [rsp+240h+var_1F8], r13
0x18001e3c5  lea     rdx, NPI_MS_IPV6_MODULEID
0x18001e3cc  mov     [rsp+240h+var_200], 8
0x18001e3d4  mov     r8d, 0Ah
0x18001e3da  mov     [rsp+240h+var_208], rax
0x18001e3df  mov     dword ptr [rsp+240h+var_210], r13d
0x18001e3e4  mov     [rsp+240h+var_218], r13
0x18001e3e9  mov     dword ptr [rsp+240h+var_220], 18h
0x18001e3f1  call    GetAllParameters
0x18001e3f6  mov     ebx, eax
0x18001e3f8  test    eax, eax
0x18001e3fa  jmp     loc_18001E489
0x18001e3ff  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e406  jz      short loc_18001E41C
0x18001e408  mov     [rsp+240h+var_218], rax
0x18001e40d  mov     edx, 22h ; '"'
0x18001e412  mov     dword ptr [rsp+240h+var_220], r12d
0x18001e417  call    WPP_SF_dDJ
0x18001e41c  mov     [rsp+240h+var_1E0], r13d
0x18001e421  lea     rax, [rsp+240h+var_1C8]
0x18001e426  mov     [rsp+240h+var_1F0], r13d
0x18001e42b  lea     r9, [rbp+140h+var_1A0]
0x18001e42f  mov     [rsp+240h+var_1F8], r13
0x18001e434  lea     rdx, NPI_MS_IPV6_MODULEID
0x18001e43b  mov     [rsp+240h+var_200], 8
0x18001e443  mov     r8d, 0Ah
0x18001e449  mov     [rsp+240h+var_208], rax
0x18001e44e  mov     dword ptr [rsp+240h+var_210], r13d
0x18001e453  mov     [rsp+240h+var_218], r13
0x18001e458  mov     dword ptr [rsp+240h+var_220], 18h
0x18001e460  call    GetAllParameters
0x18001e465  mov     ebx, eax
0x18001e467  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e46e  jz      short loc_18001E487
0x18001e470  mov     edx, 23h ; '#'
0x18001e475  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001e47c  mov     ecx, r15d
0x18001e47f  mov     r9d, eax
0x18001e482  call    WPP_SF_D
0x18001e487  test    ebx, ebx
0x18001e489  jnz     loc_18001E2E1
0x18001e48f  mov     ecx, dword ptr [rsp+240h+var_1C8+4]
0x18001e493  cmp     ecx, 1
0x18001e496  jz      loc_18001E38C
0x18001e49c  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r13d
0x18001e4a3  jz      short loc_18001E4EA
0x18001e4a5  sub     ecx, 2
0x18001e4a8  jz      short loc_18001E4E0
0x18001e4aa  sub     ecx, 1
0x18001e4ad  jz      short loc_18001E4BE
0x18001e4af  cmp     ecx, 1
0x18001e4b2  jz      short loc_18001E4BE
0x18001e4b4  mov     ebx, 1Fh
0x18001e4b9  jmp     loc_18001E2E1
0x18001e4be  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e4c5  jz      loc_18001E2E1
0x18001e4cb  mov     edx, 24h ; '$'
0x18001e4d0  mov     ecx, r15d
0x18001e4d3  mov     r9, rdi
0x18001e4d6  call    WPP_SF__IPV6_
0x18001e4db  jmp     loc_18001E2E1
0x18001e4e0  mov     ebx, 1004h
0x18001e4e5  jmp     loc_18001E2E1
0x18001e4ea  sub     ecx, 2
0x18001e4ed  jz      short loc_18001E4E0
0x18001e4ef  sub     ecx, 1
0x18001e4f2  jz      loc_18001E596
0x18001e4f8  cmp     ecx, 1
0x18001e4fb  jz      loc_18001E596
0x18001e501  mov     ebx, 1Fh
0x18001e506  test    byte ptr cs:xmmword_1800423E0, 2
0x18001e50d  jz      short loc_18001E520
0x18001e50f  mov     edx, 27h ; '''
0x18001e514  mov     dword ptr [rsp+240h+var_220], ebx
0x18001e518  mov     r9, rdi
0x18001e51b  call    WPP_SF__IPV6_D
0x18001e520  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001e527  jz      short loc_18001E53B
0x18001e529  mov     r9d, ebx
0x18001e52c  lea     rdx, ErrorAddingIpv6Address
0x18001e533  mov     r8, rdi
0x18001e536  call    McTemplateU0b16q_EtwEventWriteTransfer
0x18001e53b  mov     r9d, 13h
0x18001e541  lea     rcx, [rbp+140h+var_180]
0x18001e545  mov     r8d, ebx
0x18001e548  xor     edx, edx
0x18001e54a  call    InitializeTraceElementFromContext
0x18001e54f  movups  xmm0, xmmword ptr [rdi]
0x18001e552  mov     eax, 17h
0x18001e557  lea     rcx, [rbp+140h+var_180]
0x18001e55b  mov     [rbp+140h+var_16C], ax
0x18001e55f  movdqu  [rbp+140h+var_164], xmm0
0x18001e564  call    TraceLogEx
0x18001e569  mov     eax, ebx
0x18001e56b  mov     rcx, [rbp+140h+var_40]
0x18001e572  xor     rcx, rsp; StackCookie
0x18001e575  call    __security_check_cookie
0x18001e57a  mov     rbx, [rsp+240h+arg_18]
0x18001e582  add     rsp, 210h
0x18001e589  pop     r15
0x18001e58b  pop     r14
0x18001e58d  pop     r13
0x18001e58f  pop     r12
0x18001e591  pop     rdi
0x18001e592  pop     rsi
0x18001e593  pop     rbp
0x18001e594  retn
0x18001e596  test    ebx, ebx
0x18001e598  jnz     loc_18001E506
0x18001e59e  test    byte ptr cs:xmmword_1800423E0, sil
0x18001e5a5  jz      short loc_18001E569
0x18001e5a7  lea     edx, [rbx+28h]
0x18001e5aa  mov     ecx, r15d
0x18001e5ad  mov     r9, rdi
0x18001e5b0  call    WPP_SF__IPV6_
0x18001e5b5  jmp     short loc_18001E569
```

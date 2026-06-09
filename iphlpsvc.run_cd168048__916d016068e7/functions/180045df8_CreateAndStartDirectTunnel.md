# CreateAndStartDirectTunnel

- ea: `0x180045df8`
- end: `0x18004646e`
- name: `CreateAndStartDirectTunnel`
- size: `1654`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069240`

## callees

- `0x180008200`
- `0x18000ce90`
- `0x180012dbc`
- `0x1800190e0`
- `0x18001e9bc`
- `0x180022b30`
- `0x180024240`
- `0x180043ed8`
- `0x180045df8`
- `0x18004ada8`
- `0x18004b630`
- `0x18004c1c8`
- `0x180053418`
- `0x180082078`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800461d9`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800461d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180046255`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180046255`
- `NSI!NsiSetAllParameters` at `0x18004623e`
- `NSI!NsiSetAllParameters` at `0x1800462ba`
- `NSI!NsiSetAllParameters` at `0x18004633d`
- `NSI!NsiSetAllParameters` at `0x18004623e`
- `NSI!NsiSetAllParameters` at `0x1800462ba`
- `NSI!NsiSetAllParameters` at `0x18004633d`
- `NSI!NsiFreeTable` at `0x1800460fb`
- `NSI!NsiFreeTable` at `0x180046127`
- `NSI!NsiFreeTable` at `0x18004614d`
- `NSI!NsiFreeTable` at `0x1800460fb`
- `NSI!NsiFreeTable` at `0x180046127`
- `NSI!NsiFreeTable` at `0x18004614d`
- `NSI!NsiGetAllParameters` at `0x18004604c`
- `NSI!NsiGetAllParameters` at `0x1800460b8`
- `NSI!NsiGetAllParameters` at `0x18004604c`
- `NSI!NsiGetAllParameters` at `0x1800460b8`
- `NSI!NsiAllocateAndGetTable` at `0x180045f81`
- `NSI!NsiAllocateAndGetTable` at `0x180045f81`

## string_xrefs

- `0x180045eeb`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x180046409`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18004634c`: `System\CurrentControlSet\Services\IPHLPSVC\Direct`
- `0x180045ee1`: `CreateAndStartDirectTunnel`
- `0x1800463fc`: `CreateAndStartDirectTunnel`
- `0x180046430`: `Leaving: CreateAndStartDirectTunnel`
- `0x180045e69`: `Entered: CreateAndStartDirectTunnel`
- `0x18004619b`: `Direct Tunnel failed to install new tunnel 0x%x`

## pseudocode

```c
__int64 __fastcall CreateAndStartDirectTunnel(int a1, int a2, const BYTE *a3)
{
  unsigned int AllParameters; // ebx
  int Table; // eax
  const wchar_t *v8; // rdx
  __int64 v9; // r9
  unsigned int i; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  int v14; // eax
  int started; // eax
  NTSTATUS v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 *v21; // rcx
  _OWORD *v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+28h] [rbp-D8h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  int v27; // [rsp+40h] [rbp-C0h]
  int v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  int v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+80h] [rbp-80h]
  unsigned int v36; // [rsp+88h] [rbp-78h] BYREF
  NET_LUID InterfaceLuid; // [rsp+90h] [rbp-70h] BYREF
  int InBuffer; // [rsp+A0h] [rbp-60h] BYREF
  GUID InterfaceGuid; // [rsp+A4h] [rbp-5Ch] BYREF
  int v40; // [rsp+B4h] [rbp-4Ch]
  _DWORD v41[8]; // [rsp+B8h] [rbp-48h] BYREF
  int Buf1; // [rsp+D8h] [rbp-28h] BYREF
  char v43; // [rsp+E0h] [rbp-20h]
  __int16 v44; // [rsp+E1h] [rbp-1Fh]
  char v45; // [rsp+E3h] [rbp-1Dh]
  _OWORD Buf2[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v47[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[20]; // [rsp+140h] [rbp+40h] BYREF
  int v49; // [rsp+154h] [rbp+54h]
  __int64 v50; // [rsp+160h] [rbp+60h]
  int v51; // [rsp+168h] [rbp+68h]
  int v52; // [rsp+1B8h] [rbp+B8h]
  int v53; // [rsp+218h] [rbp+118h]

  v35 = a2;
  memset_0(&InBuffer, 0, 0x58u);
  v36 = 0;
  InterfaceLuid.Value = 0;
  v33 = 0;
  v34 = 0;
  memset_0(v48, 0, 0xF0u);
  EventWriteEnterEx(0x20000, L"Entered: CreateAndStartDirectTunnel");
  if ( (a1 & 0xF0) == 0xE0
    || (unsigned int)(a1 - 1) > 0xFFFFFFFD
    || (_BYTE)a1 == 127
    || (a2 & 0xF0) == 0xE0
    || (_BYTE)a2 == 127
    || !a2
    || a2 == -1
    || a1 == a2 )
  {
    AllParameters = -2147024809;
    EventWriteError0(0x800000, L"Direct Tunnel invalid parameter 0x%x", 2147942487LL);
    goto LABEL_75;
  }
  v44 = *(_WORD *)((char *)&v35 + 1);
  v45 = HIBYTE(v35);
  v40 = 4;
  v41[2] = a1;
  v41[0] = 1;
  v43 = a2;
  Buf1 = 1;
  if ( !(unsigned int)GetAndTraceLock(
                        "onecoreuap\\net\\netio\\iphlpsvc\\service\\direct.c",
                        "CreateAndStartDirectTunnel",
                        310,
                        g_DirectTunnelLock) )
  {
    AllParameters = -2147024161;
    goto LABEL_73;
  }
  if ( (dword_1800CBAA0 & 1) == 0 )
  {
    AllParameters = -2147023641;
    goto LABEL_73;
  }
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v33, 8, 0, 0, 0, 0, &v34, 32, &v36, 0);
  AllParameters = Table;
  if ( Table )
  {
    if ( Table > 0 )
    {
      AllParameters = (unsigned __int16)Table;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  v9 = v34;
  for ( i = 0; ; ++i )
  {
    if ( i >= v36 )
    {
      NsiFreeTable(v33, 0, 0, v9);
      if ( !a3 )
        goto LABEL_37;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&a3[2 * v12] );
      v13 = (const wchar_t *)a3;
      if ( !v12 )
LABEL_37:
        v13 = L"Microsoft Direct Point-to-point Adapater";
      v14 = InstallTunnelInterface(
              2,
              (__int64)v13,
              (__int64)L"Microsoft Direct Point-to-point Adapater",
              1u,
              (__int64)&InterfaceGuid);
      AllParameters = v14;
      if ( v14 < 0 )
      {
        EventWriteError0(0x800000, L"Direct Tunnel failed to install new tunnel 0x%x", (unsigned int)v14);
        goto LABEL_73;
      }
      InBuffer = 2;
      started = StartTunnelInterfaceEx((char *)&InBuffer);
      AllParameters = started;
      if ( started )
      {
        if ( started > 0 )
          AllParameters = (unsigned __int16)started | 0x80070000;
        EventWriteError0(0x800000, L"Direct Tunnel failed to start tunnel 0x%x", AllParameters);
      }
      else
      {
        v16 = ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid);
        AllParameters = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            AllParameters = (unsigned __int16)v16 | 0x80070000;
          EventWriteError0(0x800000, L"Direct Tunnel failed to get tunnel LUID 0x%x", AllParameters);
        }
        else
        {
          v17 = 0;
          do
          {
            LODWORD(v25) = 32;
            LODWORD(v23) = 8;
            AllParameters = NsiSetAllParameters(
                              2,
                              0,
                              &NPI_MS_FL6T_MODULEID,
                              4,
                              &InterfaceLuid,
                              v23,
                              &Buf1,
                              v25,
                              v27,
                              v29,
                              v31);
            if ( AllParameters == 1168 )
              Sleep(0x32u);
            ++v17;
          }
          while ( v17 < 0xA && AllParameters == 1168 );
          if ( AllParameters )
          {
            if ( (int)AllParameters > 0 )
              AllParameters = (unsigned __int16)AllParameters | 0x80070000;
            EventWriteError0(0x800000, L"Direct Tunnel failed to set tunnel remote DL address 0x%x", AllParameters);
          }
          else
          {
            LODWORD(v25) = 32;
            LODWORD(v23) = 8;
            v18 = NsiSetAllParameters(2, 0, &NPI_MS_FL6T_MODULEID, 2, &InterfaceLuid, v23, v41, v25, v27, v29, v31);
            AllParameters = v18;
            if ( v18 )
            {
              if ( v18 > 0 )
                AllParameters = (unsigned __int16)v18 | 0x80070000;
              EventWriteError0(0x800000, L"Direct Tunnel failed to set tunnel local DL address 0x%x", AllParameters);
            }
            else
            {
              memset_0(v48, 255, 0xF0u);
              LODWORD(v26) = 240;
              LODWORD(v24) = 8;
              v50 = 0;
              v51 = 0;
              v52 = 0;
              v53 = 0;
              v49 = 0;
              NsiSetAllParameters(2, 0, &NPI_MS_IPV6_MODULEID, 7, &InterfaceLuid, v24, v48, v26, v28, v30, v32);
              v19 = StoreInterfaceGuidAndNameToRegistry(
                      (__int64)&InterfaceGuid,
                      (__int64)L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Direct",
                      a3,
                      0);
              AllParameters = v19;
              if ( !v19 )
              {
                v20 = MALLOC(0x20u);
                if ( v20 )
                {
                  *(GUID *)(v20 + 16) = InterfaceGuid;
                  v21 = (__int64 *)qword_1800CBAB0;
                  if ( *(__int64 **)qword_1800CBAB0 != &qword_1800CBAA8 )
                    __fastfail(3u);
                  *(_QWORD *)v20 = &qword_1800CBAA8;
                  *(_QWORD *)(v20 + 8) = v21;
                  *v21 = v20;
                  qword_1800CBAB0 = v20;
                  goto LABEL_73;
                }
                AllParameters = -2147024882;
                EventWriteError0(0x800000, L"Direct Tunnel failed to allocate tunnel state 0x%x", 2147942414LL);
LABEL_69:
                StopAndDeletePersistedTunnelState(&InterfaceGuid, &InterfaceLuid);
                goto LABEL_73;
              }
              if ( v19 > 0 )
                AllParameters = (unsigned __int16)v19 | 0x80070000;
              EventWriteError0(0x800000, L"Direct Tunnel failed to persist tunnel interface 0x%x", AllParameters);
            }
          }
        }
      }
      if ( !AllParameters )
        goto LABEL_73;
      goto LABEL_69;
    }
    v11 = 32LL * i;
    if ( *(_DWORD *)(v11 + v9 + 4) == 131 && *(_DWORD *)(v11 + v9 + 8) == 2 )
      break;
LABEL_29:
    ;
  }
  v31 = 0;
  v29 = 0;
  v27 = 0;
  HIDWORD(v25) = 0;
  v23 = Buf2;
  memset(v47, 0, sizeof(v47));
  memset(Buf2, 0, sizeof(Buf2));
  AllParameters = NsiGetAllParameters(1, &NPI_MS_FL6T_MODULEID, 4, v33 + 8LL * i);
  if ( AllParameters )
    goto LABEL_31;
  if ( memcmp_0(&Buf1, Buf2, 0x20u) )
    goto LABEL_28;
  v31 = 0;
  v29 = 0;
  v27 = 0;
  HIDWORD(v25) = 0;
  v23 = v47;
  AllParameters = NsiGetAllParameters(1, &NPI_MS_FL6T_MODULEID, 2, v33 + 8LL * i);
  if ( !AllParameters )
  {
    if ( !memcmp_0(v41, v47, 0x20u) )
    {
      NsiFreeTable(v33, 0, 0, v34);
      v8 = L"Direct Tunnel found duplicate existing tunnel 0x%x";
      AllParameters = -2147024844;
      goto LABEL_18;
    }
LABEL_28:
    v9 = v34;
    goto LABEL_29;
  }
LABEL_31:
  NsiFreeTable(v33, 0, 0, v34);
  if ( (int)AllParameters <= 0 )
    goto LABEL_17;
  AllParameters = (unsigned __int16)AllParameters;
LABEL_16:
  AllParameters |= 0x80070000;
LABEL_17:
  v8 = L"Direct Tunnel failed to get existing tunnels 0x%x";
LABEL_18:
  EventWriteError0(0x800000, v8, AllParameters);
LABEL_73:
  ReleaseAndTraceLock(
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\direct.c",
    "CreateAndStartDirectTunnel",
    567,
    g_DirectTunnelLock);
LABEL_75:
  EventWriteLeaveEx(0x20000, L"Leaving: CreateAndStartDirectTunnel");
  return AllParameters;
}

```

## disassembly

```asm
0x180045df8  mov     [rsp-8+arg_18], rbx
0x180045dfd  push    rbp
0x180045dfe  push    rsi
0x180045dff  push    rdi
0x180045e00  push    r12
0x180045e02  push    r13
0x180045e04  push    r14
0x180045e06  push    r15
0x180045e08  lea     rbp, [rsp-140h]
0x180045e10  sub     rsp, 240h
0x180045e17  mov     rax, cs:__security_cookie
0x180045e1e  xor     rax, rsp
0x180045e21  mov     [rbp+170h+var_40], rax
0x180045e28  mov     ebx, edx
0x180045e2a  mov     [rbp+170h+var_1F0], edx
0x180045e2d  xor     edx, edx; Val
0x180045e2f  mov     r14, r8
0x180045e32  mov     edi, ecx
0x180045e34  lea     rcx, [rbp+170h+InBuffer]; void *
0x180045e38  lea     r8d, [rdx+58h]; Size
0x180045e3c  call    memset_0
0x180045e41  xor     r15d, r15d
0x180045e44  lea     rcx, [rbp+170h+var_130]; void *
0x180045e48  mov     esi, 0F0h
0x180045e4d  mov     [rbp+170h+var_1E8], r15d
0x180045e51  mov     r8d, esi; Size
0x180045e54  mov     qword ptr [rbp+170h+InterfaceLuid], r15
0x180045e58  xor     edx, edx; Val
0x180045e5a  mov     [rsp+270h+var_200], r15
0x180045e5f  mov     [rsp+270h+var_1F8], r15
0x180045e64  call    memset_0
0x180045e69  lea     rdx, aEnteredCreatea; "Entered: CreateAndStartDirectTunnel"
0x180045e70  mov     ecx, 20000h
0x180045e75  call    EventWriteEnterEx
0x180045e7a  mov     eax, edi
0x180045e7c  and     eax, esi
0x180045e7e  cmp     al, 0E0h
0x180045e80  jz      loc_180046417
0x180045e86  lea     eax, [rdi-1]
0x180045e89  cmp     eax, 0FFFFFFFDh
0x180045e8c  ja      loc_180046417
0x180045e92  cmp     dil, 7Fh
0x180045e96  jz      loc_180046417
0x180045e9c  mov     eax, ebx
0x180045e9e  and     eax, esi
0x180045ea0  cmp     al, 0E0h
0x180045ea2  jz      loc_180046417
0x180045ea8  cmp     bl, 7Fh
0x180045eab  jz      loc_180046417
0x180045eb1  test    ebx, ebx
0x180045eb3  jz      loc_180046417
0x180045eb9  cmp     ebx, 0FFFFFFFFh
0x180045ebc  jz      loc_180046417
0x180045ec2  cmp     edi, ebx
0x180045ec4  jz      loc_180046417
0x180045eca  movzx   eax, word ptr [rbp+170h+var_1F0+1]
0x180045ece  lea     r12d, [r15+1]
0x180045ed2  mov     r9, cs:g_DirectTunnelLock
0x180045ed9  lea     r8d, [rsi+46h]
0x180045edd  mov     [rbp+170h+var_18F], ax
0x180045ee1  lea     rdx, aCreateandstart; "CreateAndStartDirectTunnel"
0x180045ee8  mov     al, byte ptr [rbp+170h+var_1F0+3]
0x180045eeb  lea     rcx, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180045ef2  mov     [rbp+170h+var_18D], al
0x180045ef5  mov     [rbp+170h+var_1BC], 4
0x180045efc  mov     [rbp+170h+var_1B0], edi
0x180045eff  mov     [rbp+170h+var_1B8], r12d
0x180045f03  mov     [rbp+170h+var_190], bl
0x180045f06  mov     [rbp+170h+Buf1], r12d
0x180045f0a  call    GetAndTraceLock
0x180045f0f  test    eax, eax
0x180045f11  jnz     short loc_180045F1D
0x180045f13  mov     ebx, 800702DFh
0x180045f18  jmp     loc_1800463F5
0x180045f1d  test    byte ptr cs:dword_1800CBAA0, r12b
0x180045f24  jnz     short loc_180045F30
0x180045f26  mov     ebx, 800704E7h
0x180045f2b  jmp     loc_1800463F5
0x180045f30  mov     [rsp+270h+var_210], r15b
0x180045f35  lea     rax, [rbp+170h+var_1E8]
0x180045f39  mov     [rsp+270h+var_218], rax
0x180045f3e  lea     r9, [rsp+270h+var_200]
0x180045f43  mov     [rsp+270h+var_220], 20h ; ' '
0x180045f4b  lea     rax, [rsp+270h+var_1F8]
0x180045f50  mov     [rsp+270h+var_228], rax
0x180045f55  lea     rdx, NPI_MS_IPV6_MODULEID
0x180045f5c  mov     [rsp+270h+var_230], r15d
0x180045f61  mov     r8d, 7
0x180045f67  mov     [rsp+270h+var_238], r15
0x180045f6c  mov     ecx, r12d
0x180045f6f  mov     dword ptr [rsp+270h+var_240], r15d
0x180045f74  mov     [rsp+270h+var_248], r15
0x180045f79  mov     dword ptr [rsp+270h+var_250], 8
0x180045f81  call    cs:__imp_NsiAllocateAndGetTable
0x180045f88  nop     dword ptr [rax+rax+00h]
0x180045f8d  mov     ebx, eax
0x180045f8f  test    eax, eax
0x180045f91  jz      short loc_180045FB7
0x180045f93  jle     short loc_180045F9E
0x180045f95  movzx   ebx, ax
0x180045f98  or      ebx, 80070000h
0x180045f9e  lea     rdx, aDirectTunnelFa; "Direct Tunnel failed to get existing tu"...
0x180045fa5  mov     r8d, ebx
0x180045fa8  mov     ecx, 800000h
0x180045fad  call    EventWriteError0
0x180045fb2  jmp     loc_1800463F5
0x180045fb7  mov     r9, [rsp+270h+var_1F8]
0x180045fbc  mov     edi, r15d
0x180045fbf  mov     r13d, 2
0x180045fc5  cmp     edi, [rbp+170h+var_1E8]
0x180045fc8  jnb     loc_180046143
0x180045fce  mov     eax, edi
0x180045fd0  shl     rax, 5
0x180045fd4  mov     esi, edi
0x180045fd6  cmp     dword ptr [rax+r9+4], 83h
0x180045fdf  jnz     loc_1800460E4
0x180045fe5  cmp     [rax+r9+8], r13d
0x180045fea  jnz     loc_1800460E4
0x180045ff0  mov     rax, [rsp+270h+var_200]
0x180045ff5  lea     rdx, NPI_MS_FL6T_MODULEID
0x180045ffc  mov     [rsp+270h+var_220], r15d
0x180046001  xorps   xmm0, xmm0
0x180046004  mov     [rsp+270h+var_228], r15
0x180046009  xorps   xmm1, xmm1
0x18004600c  mov     [rsp+270h+var_230], r15d
0x180046011  mov     r8d, 4
0x180046017  mov     [rsp+270h+var_238], r15
0x18004601c  lea     r9, [rax+rsi*8]
0x180046020  lea     rax, [rbp+170h+Buf2]
0x180046024  mov     dword ptr [rsp+270h+var_240], 20h ; ' '
0x18004602c  mov     [rsp+270h+var_248], rax
0x180046031  mov     ecx, r12d
0x180046034  mov     dword ptr [rsp+270h+var_250], 8
0x18004603c  movups  [rbp+170h+var_150], xmm0
0x180046040  movups  [rbp+170h+var_140], xmm0
0x180046044  movups  [rbp+170h+Buf2], xmm1
0x180046048  movups  [rbp+170h+var_160], xmm1
0x18004604c  call    cs:__imp_NsiGetAllParameters
0x180046053  nop     dword ptr [rax+rax+00h]
0x180046058  mov     ebx, eax
0x18004605a  test    eax, eax
0x18004605c  jnz     loc_180046118
0x180046062  lea     ebx, [rax+20h]
0x180046065  mov     r8d, ebx; Size
0x180046068  lea     rdx, [rbp+170h+Buf2]; Buf2
0x18004606c  lea     rcx, [rbp+170h+Buf1]; Buf1
0x180046070  call    memcmp_0
0x180046075  test    eax, eax
0x180046077  jnz     short loc_1800460DF
0x180046079  mov     rax, [rsp+270h+var_200]
0x18004607e  lea     rdx, NPI_MS_FL6T_MODULEID
0x180046085  mov     [rsp+270h+var_220], r15d
0x18004608a  mov     r8d, r13d
0x18004608d  mov     [rsp+270h+var_228], r15
0x180046092  mov     ecx, r12d
0x180046095  mov     [rsp+270h+var_230], r15d
0x18004609a  mov     [rsp+270h+var_238], r15
0x18004609f  lea     r9, [rax+rsi*8]
0x1800460a3  lea     rax, [rbp+170h+var_150]
0x1800460a7  mov     dword ptr [rsp+270h+var_240], ebx
0x1800460ab  mov     [rsp+270h+var_248], rax
0x1800460b0  mov     dword ptr [rsp+270h+var_250], 8
0x1800460b8  call    cs:__imp_NsiGetAllParameters
0x1800460bf  nop     dword ptr [rax+rax+00h]
0x1800460c4  mov     ebx, eax
0x1800460c6  test    eax, eax
0x1800460c8  jnz     short loc_180046118
0x1800460ca  lea     r8d, [rax+20h]; Size
0x1800460ce  lea     rdx, [rbp+170h+var_150]; Buf2
0x1800460d2  lea     rcx, [rbp+170h+var_1B8]; Buf1
0x1800460d6  call    memcmp_0
0x1800460db  test    eax, eax
0x1800460dd  jz      short loc_1800460EC
0x1800460df  mov     r9, [rsp+270h+var_1F8]
0x1800460e4  add     edi, r12d
0x1800460e7  jmp     loc_180045FC5
0x1800460ec  mov     r9, [rsp+270h+var_1F8]
0x1800460f1  xor     r8d, r8d
0x1800460f4  mov     rcx, [rsp+270h+var_200]
0x1800460f9  xor     edx, edx
0x1800460fb  call    cs:__imp_NsiFreeTable
0x180046102  nop     dword ptr [rax+rax+00h]
0x180046107  lea     rdx, aDirectTunnelFo; "Direct Tunnel found duplicate existing "...
0x18004610e  mov     ebx, 80070034h
0x180046113  jmp     loc_180045FA5
0x180046118  mov     r9, [rsp+270h+var_1F8]
0x18004611d  xor     r8d, r8d
0x180046120  mov     rcx, [rsp+270h+var_200]
0x180046125  xor     edx, edx
0x180046127  call    cs:__imp_NsiFreeTable
0x18004612e  nop     dword ptr [rax+rax+00h]
0x180046133  test    ebx, ebx
0x180046135  jle     loc_180045F9E
0x18004613b  movzx   ebx, bx
0x18004613e  jmp     loc_180045F98
0x180046143  mov     rcx, [rsp+270h+var_200]
0x180046148  xor     r8d, r8d
0x18004614b  xor     edx, edx
0x18004614d  call    cs:__imp_NsiFreeTable
0x180046154  nop     dword ptr [rax+rax+00h]
0x180046159  lea     r8, aMicrosoftDirec; "Microsoft Direct Point-to-point Adapate"...
0x180046160  test    r14, r14
0x180046163  jz      short loc_18004617B
0x180046165  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046169  inc     rax
0x18004616c  cmp     [r14+rax*2], r15w
0x180046171  jnz     short loc_180046169
0x180046173  mov     rdx, r14
0x180046176  test    rax, rax
0x180046179  jnz     short loc_18004617E
0x18004617b  mov     rdx, r8
0x18004617e  lea     rax, [rbp+170h+InterfaceGuid]
0x180046182  mov     r9d, r12d
0x180046185  mov     ecx, r13d
0x180046188  mov     [rsp+270h+var_250], rax
0x18004618d  call    InstallTunnelInterface
0x180046192  mov     ebx, eax
0x180046194  test    eax, eax
0x180046196  jns     short loc_1800461A7
0x180046198  mov     r8d, eax
0x18004619b  lea     rdx, aDirectTunnelFa_10; "Direct Tunnel failed to install new tun"...
0x1800461a2  jmp     loc_180045FA8
0x1800461a7  lea     rcx, [rbp+170h+InBuffer]; lpInBuffer
0x1800461ab  mov     [rbp+170h+InBuffer], r13d
0x1800461af  call    StartTunnelInterfaceEx
0x1800461b4  mov     ebx, eax
0x1800461b6  test    eax, eax
0x1800461b8  jz      short loc_1800461D1
0x1800461ba  jle     short loc_1800461C5
0x1800461bc  movzx   ebx, ax
0x1800461bf  or      ebx, 80070000h
0x1800461c5  lea     rdx, aDirectTunnelFa_11; "Direct Tunnel failed to start tunnel 0x"...
0x1800461cc  jmp     loc_180046377
0x1800461d1  lea     rdx, [rbp+170h+InterfaceLuid]; InterfaceLuid
0x1800461d5  lea     rcx, [rbp+170h+InterfaceGuid]; InterfaceGuid
0x1800461d9  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800461e0  nop     dword ptr [rax+rax+00h]
0x1800461e5  mov     ebx, eax
0x1800461e7  test    eax, eax
0x1800461e9  jz      short loc_180046202
0x1800461eb  jle     short loc_1800461F6
0x1800461ed  movzx   ebx, ax
0x1800461f0  or      ebx, 80070000h
0x1800461f6  lea     rdx, aDirectTunnelFa_7; "Direct Tunnel failed to get tunnel LUID"...
0x1800461fd  jmp     loc_180046377
0x180046202  mov     edi, r15d
0x180046205  mov     esi, 490h
0x18004620a  mov     dword ptr [rsp+270h+var_238], 20h ; ' '
0x180046212  lea     rax, [rbp+170h+Buf1]
0x180046216  mov     [rsp+270h+var_240], rax
0x18004621b  lea     r8, NPI_MS_FL6T_MODULEID
0x180046222  lea     rax, [rbp+170h+InterfaceLuid]
0x180046226  mov     dword ptr [rsp+270h+var_248], 8
0x18004622e  mov     r9d, 4
0x180046234  mov     [rsp+270h+var_250], rax
0x180046239  xor     edx, edx
0x18004623b  mov     ecx, r13d
0x18004623e  call    cs:__imp_NsiSetAllParameters
0x180046245  nop     dword ptr [rax+rax+00h]
0x18004624a  mov     ebx, eax
0x18004624c  cmp     eax, esi
0x18004624e  jnz     short loc_180046261
0x180046250  mov     ecx, 32h ; '2'; dwMilliseconds
0x180046255  call    cs:__imp_Sleep
0x18004625c  nop     dword ptr [rax+rax+00h]
0x180046261  add     edi, r12d
0x180046264  cmp     edi, 0Ah
0x180046267  jnb     short loc_18004626D
0x180046269  cmp     ebx, esi
0x18004626b  jz      short loc_18004620A
0x18004626d  test    ebx, ebx
0x18004626f  jz      short loc_180046288
0x180046271  jle     short loc_18004627C
0x180046273  movzx   ebx, bx
0x180046276  or      ebx, 80070000h
0x18004627c  lea     rdx, aDirectTunnelFa_2; "Direct Tunnel failed to set tunnel remo"...
0x180046283  jmp     loc_180046377
0x180046288  mov     dword ptr [rsp+270h+var_238], 20h ; ' '
0x180046290  lea     rax, [rbp+170h+var_1B8]
0x180046294  mov     [rsp+270h+var_240], rax
0x180046299  lea     r8, NPI_MS_FL6T_MODULEID
0x1800462a0  lea     rax, [rbp+170h+InterfaceLuid]
0x1800462a4  mov     edi, 8
0x1800462a9  mov     dword ptr [rsp+270h+var_248], edi
0x1800462ad  mov     r9d, r13d
0x1800462b0  xor     edx, edx
0x1800462b2  mov     [rsp+270h+var_250], rax
0x1800462b7  mov     ecx, r13d
0x1800462ba  call    cs:__imp_NsiSetAllParameters
0x1800462c1  nop     dword ptr [rax+rax+00h]
0x1800462c6  mov     ebx, eax
0x1800462c8  test    eax, eax
0x1800462ca  jz      short loc_1800462E3
0x1800462cc  jle     short loc_1800462D7
0x1800462ce  movzx   ebx, ax
0x1800462d1  or      ebx, 80070000h
0x1800462d7  lea     rdx, aDirectTunnelFa_1; "Direct Tunnel failed to set tunnel loca"...
0x1800462de  jmp     loc_180046377
0x1800462e3  mov     ebx, 0F0h
0x1800462e8  lea     rcx, [rbp+170h+var_130]; void *
  ... truncated ...
```

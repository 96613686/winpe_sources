# CreateAndStartDirectTunnel

- ea: `0x180045db8`
- end: `0x18004642e`
- name: `CreateAndStartDirectTunnel`
- size: `1654`
- prototype: `__int64 __fastcall(int, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069260`

## callees

- `0x180008210`
- `0x18000cea0`
- `0x180012dcc`
- `0x1800190f0`
- `0x18001e9cc`
- `0x180022b40`
- `0x180024250`
- `0x180043e98`
- `0x180045db8`
- `0x18004ad68`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800533d8`
- `0x180082268`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180046199`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180046199`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180046215`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180046215`
- `NSI!NsiSetAllParameters` at `0x1800461fe`
- `NSI!NsiSetAllParameters` at `0x18004627a`
- `NSI!NsiSetAllParameters` at `0x1800462fd`
- `NSI!NsiSetAllParameters` at `0x1800461fe`
- `NSI!NsiSetAllParameters` at `0x18004627a`
- `NSI!NsiSetAllParameters` at `0x1800462fd`
- `NSI!NsiFreeTable` at `0x1800460bb`
- `NSI!NsiFreeTable` at `0x1800460e7`
- `NSI!NsiFreeTable` at `0x18004610d`
- `NSI!NsiFreeTable` at `0x1800460bb`
- `NSI!NsiFreeTable` at `0x1800460e7`
- `NSI!NsiFreeTable` at `0x18004610d`
- `NSI!NsiGetAllParameters` at `0x18004600c`
- `NSI!NsiGetAllParameters` at `0x180046078`
- `NSI!NsiGetAllParameters` at `0x18004600c`
- `NSI!NsiGetAllParameters` at `0x180046078`
- `NSI!NsiAllocateAndGetTable` at `0x180045f41`
- `NSI!NsiAllocateAndGetTable` at `0x180045f41`

## string_xrefs

- `0x180045eab`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x1800463c9`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18004630c`: `System\CurrentControlSet\Services\IPHLPSVC\Direct`
- `0x180045ea1`: `CreateAndStartDirectTunnel`
- `0x1800463bc`: `CreateAndStartDirectTunnel`
- `0x1800463f0`: `Leaving: CreateAndStartDirectTunnel`
- `0x180045e29`: `Entered: CreateAndStartDirectTunnel`
- `0x18004615b`: `Direct Tunnel failed to install new tunnel 0x%x`

## pseudocode

```c
__int64 __fastcall CreateAndStartDirectTunnel(int a1, int a2, const wchar_t *a3)
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
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+80h] [rbp-80h]
  unsigned int v26; // [rsp+88h] [rbp-78h] BYREF
  NET_LUID InterfaceLuid; // [rsp+90h] [rbp-70h] BYREF
  int InBuffer; // [rsp+A0h] [rbp-60h] BYREF
  GUID InterfaceGuid; // [rsp+A4h] [rbp-5Ch] BYREF
  int v30; // [rsp+B4h] [rbp-4Ch]
  _DWORD v31[8]; // [rsp+B8h] [rbp-48h] BYREF
  int Buf1; // [rsp+D8h] [rbp-28h] BYREF
  char v33; // [rsp+E0h] [rbp-20h]
  __int16 v34; // [rsp+E1h] [rbp-1Fh]
  char v35; // [rsp+E3h] [rbp-1Dh]
  _OWORD Buf2[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v37[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v38[20]; // [rsp+140h] [rbp+40h] BYREF
  int v39; // [rsp+154h] [rbp+54h]
  __int64 v40; // [rsp+160h] [rbp+60h]
  int v41; // [rsp+168h] [rbp+68h]
  int v42; // [rsp+1B8h] [rbp+B8h]
  int v43; // [rsp+218h] [rbp+118h]

  v25 = a2;
  memset_0(&InBuffer, 0, 0x58u);
  v26 = 0;
  InterfaceLuid.Value = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v38, 0, 0xF0u);
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
  v34 = *(_WORD *)((char *)&v25 + 1);
  v35 = HIBYTE(v25);
  v30 = 4;
  v31[2] = a1;
  v31[0] = 1;
  v33 = a2;
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
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v23, 8, 0, 0, 0, 0, &v24, 32, &v26, 0);
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
  v9 = v24;
  for ( i = 0; ; ++i )
  {
    if ( i >= v26 )
    {
      NsiFreeTable(v23, 0, 0, v9);
      if ( !a3 )
        goto LABEL_37;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = a3;
      if ( !v12 )
LABEL_37:
        v13 = L"Microsoft Direct Point-to-point Adapater";
      v14 = InstallTunnelInterface(2, v13, L"Microsoft Direct Point-to-point Adapater", 1, &InterfaceGuid);
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
            AllParameters = NsiSetAllParameters(2, 0, &NPI_MS_FL6T_MODULEID, 4, &InterfaceLuid, 8, &Buf1, 32);
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
            v18 = NsiSetAllParameters(2, 0, &NPI_MS_FL6T_MODULEID, 2, &InterfaceLuid, 8, v31, 32);
            AllParameters = v18;
            if ( v18 )
            {
              if ( v18 > 0 )
                AllParameters = (unsigned __int16)v18 | 0x80070000;
              EventWriteError0(0x800000, L"Direct Tunnel failed to set tunnel local DL address 0x%x", AllParameters);
            }
            else
            {
              memset_0(v38, 255, 0xF0u);
              v40 = 0;
              v41 = 0;
              v42 = 0;
              v43 = 0;
              v39 = 0;
              NsiSetAllParameters(2, 0, &NPI_MS_IPV6_MODULEID, 7, &InterfaceLuid, 8, v38, 240);
              v19 = StoreInterfaceGuidAndNameToRegistry(
                      &InterfaceGuid,
                      L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Direct",
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
  memset(v37, 0, sizeof(v37));
  memset(Buf2, 0, sizeof(Buf2));
  AllParameters = NsiGetAllParameters(1, &NPI_MS_FL6T_MODULEID, 4, v23 + 8LL * i, 8, Buf2, 32, 0, 0, 0, 0);
  if ( AllParameters )
    goto LABEL_31;
  if ( memcmp_0(&Buf1, Buf2, 0x20u) )
    goto LABEL_28;
  AllParameters = NsiGetAllParameters(1, &NPI_MS_FL6T_MODULEID, 2, v23 + 8LL * i, 8, v37, 32, 0, 0, 0, 0);
  if ( !AllParameters )
  {
    if ( !memcmp_0(v31, v37, 0x20u) )
    {
      NsiFreeTable(v23, 0, 0, v24);
      v8 = L"Direct Tunnel found duplicate existing tunnel 0x%x";
      AllParameters = -2147024844;
      goto LABEL_18;
    }
LABEL_28:
    v9 = v24;
    goto LABEL_29;
  }
LABEL_31:
  NsiFreeTable(v23, 0, 0, v24);
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
0x180045db8  mov     [rsp-8+arg_18], rbx
0x180045dbd  push    rbp
0x180045dbe  push    rsi
0x180045dbf  push    rdi
0x180045dc0  push    r12
0x180045dc2  push    r13
0x180045dc4  push    r14
0x180045dc6  push    r15
0x180045dc8  lea     rbp, [rsp-140h]
0x180045dd0  sub     rsp, 240h
0x180045dd7  mov     rax, cs:__security_cookie
0x180045dde  xor     rax, rsp
0x180045de1  mov     [rbp+170h+var_40], rax
0x180045de8  mov     ebx, edx
0x180045dea  mov     [rbp+170h+var_1F0], edx
0x180045ded  xor     edx, edx; Val
0x180045def  mov     r14, r8
0x180045df2  mov     edi, ecx
0x180045df4  lea     rcx, [rbp+170h+InBuffer]; void *
0x180045df8  lea     r8d, [rdx+58h]; Size
0x180045dfc  call    memset_0
0x180045e01  xor     r15d, r15d
0x180045e04  lea     rcx, [rbp+170h+var_130]; void *
0x180045e08  mov     esi, 0F0h
0x180045e0d  mov     [rbp+170h+var_1E8], r15d
0x180045e11  mov     r8d, esi; Size
0x180045e14  mov     qword ptr [rbp+170h+InterfaceLuid], r15
0x180045e18  xor     edx, edx; Val
0x180045e1a  mov     [rsp+270h+var_200], r15
0x180045e1f  mov     [rsp+270h+var_1F8], r15
0x180045e24  call    memset_0
0x180045e29  lea     rdx, aEnteredCreatea; "Entered: CreateAndStartDirectTunnel"
0x180045e30  mov     ecx, 20000h
0x180045e35  call    EventWriteEnterEx
0x180045e3a  mov     eax, edi
0x180045e3c  and     eax, esi
0x180045e3e  cmp     al, 0E0h
0x180045e40  jz      loc_1800463D7
0x180045e46  lea     eax, [rdi-1]
0x180045e49  cmp     eax, 0FFFFFFFDh
0x180045e4c  ja      loc_1800463D7
0x180045e52  cmp     dil, 7Fh
0x180045e56  jz      loc_1800463D7
0x180045e5c  mov     eax, ebx
0x180045e5e  and     eax, esi
0x180045e60  cmp     al, 0E0h
0x180045e62  jz      loc_1800463D7
0x180045e68  cmp     bl, 7Fh
0x180045e6b  jz      loc_1800463D7
0x180045e71  test    ebx, ebx
0x180045e73  jz      loc_1800463D7
0x180045e79  cmp     ebx, 0FFFFFFFFh
0x180045e7c  jz      loc_1800463D7
0x180045e82  cmp     edi, ebx
0x180045e84  jz      loc_1800463D7
0x180045e8a  movzx   eax, word ptr [rbp+170h+var_1F0+1]
0x180045e8e  lea     r12d, [r15+1]
0x180045e92  mov     r9, cs:g_DirectTunnelLock
0x180045e99  lea     r8d, [rsi+46h]
0x180045e9d  mov     [rbp+170h+var_18F], ax
0x180045ea1  lea     rdx, aCreateandstart; "CreateAndStartDirectTunnel"
0x180045ea8  mov     al, byte ptr [rbp+170h+var_1F0+3]
0x180045eab  lea     rcx, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180045eb2  mov     [rbp+170h+var_18D], al
0x180045eb5  mov     [rbp+170h+var_1BC], 4
0x180045ebc  mov     [rbp+170h+var_1B0], edi
0x180045ebf  mov     [rbp+170h+var_1B8], r12d
0x180045ec3  mov     [rbp+170h+var_190], bl
0x180045ec6  mov     [rbp+170h+Buf1], r12d
0x180045eca  call    GetAndTraceLock
0x180045ecf  test    eax, eax
0x180045ed1  jnz     short loc_180045EDD
0x180045ed3  mov     ebx, 800702DFh
0x180045ed8  jmp     loc_1800463B5
0x180045edd  test    byte ptr cs:dword_1800CBAA0, r12b
0x180045ee4  jnz     short loc_180045EF0
0x180045ee6  mov     ebx, 800704E7h
0x180045eeb  jmp     loc_1800463B5
0x180045ef0  mov     [rsp+270h+var_210], r15b
0x180045ef5  lea     rax, [rbp+170h+var_1E8]
0x180045ef9  mov     [rsp+270h+var_218], rax
0x180045efe  lea     r9, [rsp+270h+var_200]
0x180045f03  mov     [rsp+270h+var_220], 20h ; ' '
0x180045f0b  lea     rax, [rsp+270h+var_1F8]
0x180045f10  mov     [rsp+270h+var_228], rax
0x180045f15  lea     rdx, NPI_MS_IPV6_MODULEID
0x180045f1c  mov     [rsp+270h+var_230], r15d
0x180045f21  mov     r8d, 7
0x180045f27  mov     [rsp+270h+var_238], r15
0x180045f2c  mov     ecx, r12d
0x180045f2f  mov     dword ptr [rsp+270h+var_240], r15d
0x180045f34  mov     [rsp+270h+var_248], r15
0x180045f39  mov     dword ptr [rsp+270h+var_250], 8
0x180045f41  call    cs:__imp_NsiAllocateAndGetTable
0x180045f48  nop     dword ptr [rax+rax+00h]
0x180045f4d  mov     ebx, eax
0x180045f4f  test    eax, eax
0x180045f51  jz      short loc_180045F77
0x180045f53  jle     short loc_180045F5E
0x180045f55  movzx   ebx, ax
0x180045f58  or      ebx, 80070000h
0x180045f5e  lea     rdx, aDirectTunnelFa; "Direct Tunnel failed to get existing tu"...
0x180045f65  mov     r8d, ebx
0x180045f68  mov     ecx, 800000h
0x180045f6d  call    EventWriteError0
0x180045f72  jmp     loc_1800463B5
0x180045f77  mov     r9, [rsp+270h+var_1F8]
0x180045f7c  mov     edi, r15d
0x180045f7f  mov     r13d, 2
0x180045f85  cmp     edi, [rbp+170h+var_1E8]
0x180045f88  jnb     loc_180046103
0x180045f8e  mov     eax, edi
0x180045f90  shl     rax, 5
0x180045f94  mov     esi, edi
0x180045f96  cmp     dword ptr [rax+r9+4], 83h
0x180045f9f  jnz     loc_1800460A4
0x180045fa5  cmp     [rax+r9+8], r13d
0x180045faa  jnz     loc_1800460A4
0x180045fb0  mov     rax, [rsp+270h+var_200]
0x180045fb5  lea     rdx, NPI_MS_FL6T_MODULEID
0x180045fbc  mov     [rsp+270h+var_220], r15d
0x180045fc1  xorps   xmm0, xmm0
0x180045fc4  mov     [rsp+270h+var_228], r15
0x180045fc9  xorps   xmm1, xmm1
0x180045fcc  mov     [rsp+270h+var_230], r15d
0x180045fd1  mov     r8d, 4
0x180045fd7  mov     [rsp+270h+var_238], r15
0x180045fdc  lea     r9, [rax+rsi*8]
0x180045fe0  lea     rax, [rbp+170h+Buf2]
0x180045fe4  mov     dword ptr [rsp+270h+var_240], 20h ; ' '
0x180045fec  mov     [rsp+270h+var_248], rax
0x180045ff1  mov     ecx, r12d
0x180045ff4  mov     dword ptr [rsp+270h+var_250], 8
0x180045ffc  movups  [rbp+170h+var_150], xmm0
0x180046000  movups  [rbp+170h+var_140], xmm0
0x180046004  movups  [rbp+170h+Buf2], xmm1
0x180046008  movups  [rbp+170h+var_160], xmm1
0x18004600c  call    cs:__imp_NsiGetAllParameters
0x180046013  nop     dword ptr [rax+rax+00h]
0x180046018  mov     ebx, eax
0x18004601a  test    eax, eax
0x18004601c  jnz     loc_1800460D8
0x180046022  lea     ebx, [rax+20h]
0x180046025  mov     r8d, ebx; Size
0x180046028  lea     rdx, [rbp+170h+Buf2]; Buf2
0x18004602c  lea     rcx, [rbp+170h+Buf1]; Buf1
0x180046030  call    memcmp_0
0x180046035  test    eax, eax
0x180046037  jnz     short loc_18004609F
0x180046039  mov     rax, [rsp+270h+var_200]
0x18004603e  lea     rdx, NPI_MS_FL6T_MODULEID
0x180046045  mov     [rsp+270h+var_220], r15d
0x18004604a  mov     r8d, r13d
0x18004604d  mov     [rsp+270h+var_228], r15
0x180046052  mov     ecx, r12d
0x180046055  mov     [rsp+270h+var_230], r15d
0x18004605a  mov     [rsp+270h+var_238], r15
0x18004605f  lea     r9, [rax+rsi*8]
0x180046063  lea     rax, [rbp+170h+var_150]
0x180046067  mov     dword ptr [rsp+270h+var_240], ebx
0x18004606b  mov     [rsp+270h+var_248], rax
0x180046070  mov     dword ptr [rsp+270h+var_250], 8
0x180046078  call    cs:__imp_NsiGetAllParameters
0x18004607f  nop     dword ptr [rax+rax+00h]
0x180046084  mov     ebx, eax
0x180046086  test    eax, eax
0x180046088  jnz     short loc_1800460D8
0x18004608a  lea     r8d, [rax+20h]; Size
0x18004608e  lea     rdx, [rbp+170h+var_150]; Buf2
0x180046092  lea     rcx, [rbp+170h+var_1B8]; Buf1
0x180046096  call    memcmp_0
0x18004609b  test    eax, eax
0x18004609d  jz      short loc_1800460AC
0x18004609f  mov     r9, [rsp+270h+var_1F8]
0x1800460a4  add     edi, r12d
0x1800460a7  jmp     loc_180045F85
0x1800460ac  mov     r9, [rsp+270h+var_1F8]
0x1800460b1  xor     r8d, r8d
0x1800460b4  mov     rcx, [rsp+270h+var_200]
0x1800460b9  xor     edx, edx
0x1800460bb  call    cs:__imp_NsiFreeTable
0x1800460c2  nop     dword ptr [rax+rax+00h]
0x1800460c7  lea     rdx, aDirectTunnelFo; "Direct Tunnel found duplicate existing "...
0x1800460ce  mov     ebx, 80070034h
0x1800460d3  jmp     loc_180045F65
0x1800460d8  mov     r9, [rsp+270h+var_1F8]
0x1800460dd  xor     r8d, r8d
0x1800460e0  mov     rcx, [rsp+270h+var_200]
0x1800460e5  xor     edx, edx
0x1800460e7  call    cs:__imp_NsiFreeTable
0x1800460ee  nop     dword ptr [rax+rax+00h]
0x1800460f3  test    ebx, ebx
0x1800460f5  jle     loc_180045F5E
0x1800460fb  movzx   ebx, bx
0x1800460fe  jmp     loc_180045F58
0x180046103  mov     rcx, [rsp+270h+var_200]
0x180046108  xor     r8d, r8d
0x18004610b  xor     edx, edx
0x18004610d  call    cs:__imp_NsiFreeTable
0x180046114  nop     dword ptr [rax+rax+00h]
0x180046119  lea     r8, aMicrosoftDirec; "Microsoft Direct Point-to-point Adapate"...
0x180046120  test    r14, r14
0x180046123  jz      short loc_18004613B
0x180046125  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046129  inc     rax
0x18004612c  cmp     [r14+rax*2], r15w
0x180046131  jnz     short loc_180046129
0x180046133  mov     rdx, r14
0x180046136  test    rax, rax
0x180046139  jnz     short loc_18004613E
0x18004613b  mov     rdx, r8
0x18004613e  lea     rax, [rbp+170h+InterfaceGuid]
0x180046142  mov     r9d, r12d
0x180046145  mov     ecx, r13d
0x180046148  mov     [rsp+270h+var_250], rax
0x18004614d  call    InstallTunnelInterface
0x180046152  mov     ebx, eax
0x180046154  test    eax, eax
0x180046156  jns     short loc_180046167
0x180046158  mov     r8d, eax
0x18004615b  lea     rdx, aDirectTunnelFa_10; "Direct Tunnel failed to install new tun"...
0x180046162  jmp     loc_180045F68
0x180046167  lea     rcx, [rbp+170h+InBuffer]; lpInBuffer
0x18004616b  mov     [rbp+170h+InBuffer], r13d
0x18004616f  call    StartTunnelInterfaceEx
0x180046174  mov     ebx, eax
0x180046176  test    eax, eax
0x180046178  jz      short loc_180046191
0x18004617a  jle     short loc_180046185
0x18004617c  movzx   ebx, ax
0x18004617f  or      ebx, 80070000h
0x180046185  lea     rdx, aDirectTunnelFa_11; "Direct Tunnel failed to start tunnel 0x"...
0x18004618c  jmp     loc_180046337
0x180046191  lea     rdx, [rbp+170h+InterfaceLuid]; InterfaceLuid
0x180046195  lea     rcx, [rbp+170h+InterfaceGuid]; InterfaceGuid
0x180046199  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800461a0  nop     dword ptr [rax+rax+00h]
0x1800461a5  mov     ebx, eax
0x1800461a7  test    eax, eax
0x1800461a9  jz      short loc_1800461C2
0x1800461ab  jle     short loc_1800461B6
0x1800461ad  movzx   ebx, ax
0x1800461b0  or      ebx, 80070000h
0x1800461b6  lea     rdx, aDirectTunnelFa_7; "Direct Tunnel failed to get tunnel LUID"...
0x1800461bd  jmp     loc_180046337
0x1800461c2  mov     edi, r15d
0x1800461c5  mov     esi, 490h
0x1800461ca  mov     dword ptr [rsp+270h+var_238], 20h ; ' '
0x1800461d2  lea     rax, [rbp+170h+Buf1]
0x1800461d6  mov     [rsp+270h+var_240], rax
0x1800461db  lea     r8, NPI_MS_FL6T_MODULEID
0x1800461e2  lea     rax, [rbp+170h+InterfaceLuid]
0x1800461e6  mov     dword ptr [rsp+270h+var_248], 8
0x1800461ee  mov     r9d, 4
0x1800461f4  mov     [rsp+270h+var_250], rax
0x1800461f9  xor     edx, edx
0x1800461fb  mov     ecx, r13d
0x1800461fe  call    cs:__imp_NsiSetAllParameters
0x180046205  nop     dword ptr [rax+rax+00h]
0x18004620a  mov     ebx, eax
0x18004620c  cmp     eax, esi
0x18004620e  jnz     short loc_180046221
0x180046210  mov     ecx, 32h ; '2'; dwMilliseconds
0x180046215  call    cs:__imp_Sleep
0x18004621c  nop     dword ptr [rax+rax+00h]
0x180046221  add     edi, r12d
0x180046224  cmp     edi, 0Ah
0x180046227  jnb     short loc_18004622D
0x180046229  cmp     ebx, esi
0x18004622b  jz      short loc_1800461CA
0x18004622d  test    ebx, ebx
0x18004622f  jz      short loc_180046248
0x180046231  jle     short loc_18004623C
0x180046233  movzx   ebx, bx
0x180046236  or      ebx, 80070000h
0x18004623c  lea     rdx, aDirectTunnelFa_2; "Direct Tunnel failed to set tunnel remo"...
0x180046243  jmp     loc_180046337
0x180046248  mov     dword ptr [rsp+270h+var_238], 20h ; ' '
0x180046250  lea     rax, [rbp+170h+var_1B8]
0x180046254  mov     [rsp+270h+var_240], rax
0x180046259  lea     r8, NPI_MS_FL6T_MODULEID
0x180046260  lea     rax, [rbp+170h+InterfaceLuid]
0x180046264  mov     edi, 8
0x180046269  mov     dword ptr [rsp+270h+var_248], edi
0x18004626d  mov     r9d, r13d
0x180046270  xor     edx, edx
0x180046272  mov     [rsp+270h+var_250], rax
0x180046277  mov     ecx, r13d
0x18004627a  call    cs:__imp_NsiSetAllParameters
0x180046281  nop     dword ptr [rax+rax+00h]
0x180046286  mov     ebx, eax
0x180046288  test    eax, eax
0x18004628a  jz      short loc_1800462A3
0x18004628c  jle     short loc_180046297
0x18004628e  movzx   ebx, ax
0x180046291  or      ebx, 80070000h
0x180046297  lea     rdx, aDirectTunnelFa_1; "Direct Tunnel failed to set tunnel loca"...
0x18004629e  jmp     loc_180046337
0x1800462a3  mov     ebx, 0F0h
0x1800462a8  lea     rcx, [rbp+170h+var_130]; void *
  ... truncated ...
```

# TeredoCreatePeerSocket

- ea: `0x18001bc30`
- end: `0x18001bf69`
- name: `TeredoCreatePeerSocket`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180009010`
- `0x18000d7c0`
- `0x180016ac0`
- `0x1800190f0`
- `0x18001bc30`
- `0x18001cab8`
- `0x18001cb20`
- `0x18001cb90`
- `0x180034390`
- `0x18004b5f0`
- `0x180051c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bee0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001be1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001be1d`
- `WS2_32!WSASocketW` at `0x18001bcb8`
- `WS2_32!WSASocketW` at `0x18001bcb8`
- `WS2_32!__imp_bind` at `0x18001bd38`
- `WS2_32!__imp_bind` at `0x18001bd38`
- `WS2_32!__imp_getsockname` at `0x18001bd86`
- `WS2_32!__imp_getsockname` at `0x18001bd86`
- `WS2_32!__imp_ntohs` at `0x18001bdb1`
- `WS2_32!__imp_ntohs` at `0x18001bdb1`
- `WS2_32!__imp_setsockopt` at `0x18001bcf9`
- `WS2_32!__imp_setsockopt` at `0x18001bcf9`

## string_xrefs

- `0x18001bc8e`: `Teredo create peer socket: Creating Socket Device 0x%p Peer 0x%p`
- `0x18001beb3`: `Create Socket failed: %u`
- `0x18001bf00`: `Failed to read socket name. Error (%d)`
- `0x18001bf4a`: `Created Peer Socket.`

## pseudocode

```c
__int64 __fastcall TeredoCreatePeerSocket(__int64 *a1)
{
  int v1; // edi
  __int64 v3; // rsi
  __int64 v4; // r14
  SOCKET v5; // rax
  SOCKET v6; // rcx
  __int64 v7; // rbp
  SOCKET v8; // rcx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // r8d
  PTP_IO ThreadpoolIo; // rax
  int i; // edi
  __int64 LastError; // rbx
  DWORD v17; // edi
  __int64 g; // [rsp+20h] [rbp-58h]
  DWORD dwFlags[2]; // [rsp+28h] [rbp-50h]
  int v20; // [rsp+30h] [rbp-48h]
  char optval[4]; // [rsp+40h] [rbp-38h] BYREF
  int namelen; // [rsp+44h] [rbp-34h] BYREF
  struct sockaddr name; // [rsp+48h] [rbp-30h] BYREF

  v1 = 1;
  *(_DWORD *)optval = 1;
  name = 0;
  namelen = 0;
  if ( dword_1800CA0E8 >= 200 )
    return 1158;
  v3 = a1[1];
  v4 = *a1;
  _InterlockedIncrement(&dword_1800CA0E8);
  EventWrite0(0x100000, L"Teredo create peer socket: Creating Socket Device 0x%p Peer 0x%p", a1, v3);
  v5 = WSASocketW(2, 2, 0, 0, 0, 1u);
  a1[3] = v5;
  if ( v5 == -1 )
  {
    LastError = GetLastError();
    EventWriteError0(0x100000, L"Create Socket failed: %u", LastError);
    _InterlockedDecrement(&dword_1800CA0E8);
    return (unsigned int)LastError;
  }
  *(_DWORD *)optval = 1;
  setsockopt(v5, 0xFFFF, 12293, optval, 4);
  if ( (unsigned int)TeredoEnableRealArrivalIf(a1[3]) )
    goto LABEL_20;
  while ( 1 )
  {
    v6 = a1[3];
    name = *(struct sockaddr *)(v4 + 2660);
    *(_WORD *)name.sa_data = 0;
    v7 = (unsigned int)bind(v6, &name, 16);
    EventWriteError0(0x100000, L"Socket bind failed. Error (%d)", v7);
    if ( (_DWORD)v7 != -1 )
      break;
    if ( !v1-- )
      goto LABEL_20;
  }
  if ( (_DWORD)v7 )
    goto LABEL_20;
  v8 = a1[3];
  namelen = 16;
  v9 = getsockname(v8, (struct sockaddr *)(v3 + 992), &namelen);
  if ( v9 )
  {
    EventWriteError0(0x100000, L"Failed to read socket name. Error (%d)", v9);
LABEL_20:
    v17 = GetLastError();
    TeredoDestroyPeerSocket(a1);
    return v17;
  }
  TeredoTraceAddress(L"Peer is", v3 + 20);
  v20 = ntohs(*(_WORD *)(v3 + 994));
  dwFlags[0] = *(unsigned __int8 *)(v3 + 999);
  LODWORD(g) = *(unsigned __int8 *)(v3 + 998);
  EventWrite0(
    0x100000,
    L"Peer's source mapping: %d.%d.%d.%d::%d",
    *(unsigned __int8 *)(v3 + 996),
    *(unsigned __int8 *)(v3 + 997),
    g,
    *(_QWORD *)dwFlags,
    v20);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0qqqbr0_EventWriteTransfer(v10, (unsigned int)EVENT_IPHLPSVC_ETW_TEREDO_MAPPING, v11, 2, 4, v3 + 992);
  ThreadpoolIo = CreateThreadpoolIo((HANDLE)a1[3], TeredoPeerIoComplete, 0, &CallbackEnvironment);
  a1[2] = (__int64)ThreadpoolIo;
  if ( !ThreadpoolIo )
    goto LABEL_20;
  for ( i = 0; i < 5; ++i )
  {
    if ( !(unsigned int)TeredoPeerPostReceive(a1, 0) )
      break;
  }
  if ( !i )
  {
    SetLastError(0x1Eu);
    goto LABEL_20;
  }
  TeredoRegisterPeerPortWithFirewall(*(unsigned __int16 *)(v3 + 994));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_IO,
      L"Created Peer Socket.");
  return 0;
}

```

## disassembly

```asm
0x18001bc30  mov     r11, rsp
0x18001bc33  push    rbx
0x18001bc34  push    rdi
0x18001bc35  push    r15
0x18001bc37  sub     rsp, 60h
0x18001bc3b  mov     rax, cs:__security_cookie
0x18001bc42  xor     rax, rsp
0x18001bc45  mov     [rsp+78h+var_20], rax
0x18001bc4a  xor     r15d, r15d
0x18001bc4d  xorps   xmm0, xmm0
0x18001bc50  cmp     cs:dword_1800CA0E8, 0C8h
0x18001bc5a  mov     edi, 1
0x18001bc5f  mov     rbx, rcx
0x18001bc62  mov     dword ptr [rsp+78h+optval], edi
0x18001bc66  movups  xmmword ptr [rsp+78h+name.sa_family], xmm0
0x18001bc6b  mov     [r11-34h], r15d
0x18001bc6f  jge     loc_18001BEA0
0x18001bc75  mov     [r11+18h], rsi
0x18001bc79  mov     rsi, [rcx+8]
0x18001bc7d  mov     [r11+20h], r14
0x18001bc81  mov     r14, [rcx]
0x18001bc84  lock inc cs:dword_1800CA0E8
0x18001bc8b  mov     r8, rcx
0x18001bc8e  lea     rdx, aTeredoCreatePe; "Teredo create peer socket: Creating Soc"...
0x18001bc95  mov     ecx, 100000h
0x18001bc9a  mov     r9, rsi
0x18001bc9d  call    EventWrite0
0x18001bca2  mov     edx, 2; type
0x18001bca7  mov     [rsp+78h+dwFlags], edi; dwFlags
0x18001bcab  mov     ecx, edx; af
0x18001bcad  mov     dword ptr [rsp+78h+g], r15d; g
0x18001bcb2  xor     r9d, r9d; lpProtocolInfo
0x18001bcb5  xor     r8d, r8d; protocol
0x18001bcb8  call    cs:__imp_WSASocketW
0x18001bcbf  nop     dword ptr [rax+rax+00h]
0x18001bcc4  mov     [rbx+18h], rax
0x18001bcc8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bccc  jz      loc_18001BEA7
0x18001bcd2  lea     r9, [rsp+78h+optval]; optval
0x18001bcd7  mov     [rsp+78h+arg_8], rbp
0x18001bcdf  mov     edx, 0FFFFh; level
0x18001bce4  mov     dword ptr [rsp+78h+optval], edi
0x18001bce8  mov     r8d, 3005h; optname
0x18001bcee  mov     dword ptr [rsp+78h+g], 4; optlen
0x18001bcf6  mov     rcx, rax; s
0x18001bcf9  call    cs:__imp_setsockopt
0x18001bd00  nop     dword ptr [rax+rax+00h]
0x18001bd05  mov     rcx, [rbx+18h]
0x18001bd09  call    TeredoEnableRealArrivalIf
0x18001bd0e  test    eax, eax
0x18001bd10  jnz     loc_18001BEE0
0x18001bd16  movups  xmm0, xmmword ptr [r14+0A64h]
0x18001bd1e  mov     rcx, [rbx+18h]; s
0x18001bd22  lea     rdx, [rsp+78h+name]; name
0x18001bd27  mov     r8d, 10h; namelen
0x18001bd2d  movups  xmmword ptr [rsp+78h+name.sa_family], xmm0
0x18001bd32  mov     word ptr [rsp+78h+name.sa_data], r15w
0x18001bd38  call    cs:__imp_bind
0x18001bd3f  nop     dword ptr [rax+rax+00h]
0x18001bd44  lea     rdx, aSocketBindFail; "Socket bind failed. Error (%d)"
0x18001bd4b  mov     ecx, 100000h
0x18001bd50  mov     r8d, eax
0x18001bd53  mov     ebp, eax
0x18001bd55  call    EventWriteError0
0x18001bd5a  cmp     ebp, 0FFFFFFFFh
0x18001bd5d  jz      loc_18001BED4
0x18001bd63  test    ebp, ebp
0x18001bd65  jnz     loc_18001BEE0
0x18001bd6b  mov     rcx, [rbx+18h]; s
0x18001bd6f  lea     rdi, [rsi+3E0h]
0x18001bd76  mov     rdx, rdi; name
0x18001bd79  mov     [rsp+78h+namelen], 10h
0x18001bd81  lea     r8, [rsp+78h+namelen]; namelen
0x18001bd86  call    cs:__imp_getsockname
0x18001bd8d  nop     dword ptr [rax+rax+00h]
0x18001bd92  test    eax, eax
0x18001bd94  jnz     loc_18001BEFD
0x18001bd9a  lea     rdx, [rsi+14h]
0x18001bd9e  lea     rcx, aPeerIs; "Peer is"
0x18001bda5  call    TeredoTraceAddress
0x18001bdaa  movzx   ecx, word ptr [rsi+3E2h]; netshort
0x18001bdb1  call    cs:__imp_ntohs
0x18001bdb8  nop     dword ptr [rax+rax+00h]
0x18001bdbd  movzx   ecx, byte ptr [rsi+3E7h]
0x18001bdc4  movzx   edx, byte ptr [rsi+3E6h]
0x18001bdcb  movzx   r9d, byte ptr [rsi+3E5h]
0x18001bdd3  movzx   r8d, byte ptr [rsi+3E4h]
0x18001bddb  movzx   eax, ax
0x18001bdde  mov     [rsp+78h+var_48], eax
0x18001bde2  mov     [rsp+78h+dwFlags], ecx
0x18001bde6  mov     ecx, 100000h
0x18001bdeb  mov     dword ptr [rsp+78h+g], edx
0x18001bdef  lea     rdx, aPeerSSourceMap; "Peer's source mapping: %d.%d.%d.%d::%d"
0x18001bdf6  call    EventWrite0
0x18001bdfb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001be02  jnz     loc_18001BF13
0x18001be08  mov     rcx, [rbx+18h]; fl
0x18001be0c  lea     r9, CallbackEnvironment; pcbe
0x18001be13  xor     r8d, r8d; pv
0x18001be16  lea     rdx, TeredoPeerIoComplete; pfnio
0x18001be1d  call    cs:__imp_CreateThreadpoolIo
0x18001be24  nop     dword ptr [rax+rax+00h]
0x18001be29  mov     [rbx+10h], rax
0x18001be2d  test    rax, rax
0x18001be30  jz      loc_18001BEE0
0x18001be36  mov     edi, r15d
0x18001be39  xor     edx, edx
0x18001be3b  mov     rcx, rbx
0x18001be3e  call    TeredoPeerPostReceive
0x18001be43  test    eax, eax
0x18001be45  jz      short loc_18001BE4E
0x18001be47  inc     edi
0x18001be49  cmp     edi, 5
0x18001be4c  jl      short loc_18001BE39
0x18001be4e  test    edi, edi
0x18001be50  jz      loc_18001BF37
0x18001be56  movzx   ecx, word ptr [rsi+3E2h]
0x18001be5d  call    TeredoRegisterPeerPortWithFirewall
0x18001be62  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001be69  jnz     loc_18001BF4A
0x18001be6f  xor     eax, eax
0x18001be71  mov     rbp, [rsp+78h+arg_8]
0x18001be79  mov     rsi, [rsp+78h+arg_10]
0x18001be81  mov     r14, [rsp+78h+arg_18]
0x18001be89  mov     rcx, [rsp+78h+var_20]
0x18001be8e  xor     rcx, rsp; StackCookie
0x18001be91  call    __security_check_cookie
0x18001be96  add     rsp, 60h
0x18001be9a  pop     r15
0x18001be9c  pop     rdi
0x18001be9d  pop     rbx
0x18001be9e  retn
0x18001bea0  mov     eax, 486h
0x18001bea5  jmp     short loc_18001BE89
0x18001bea7  call    cs:__imp_GetLastError
0x18001beae  nop     dword ptr [rax+rax+00h]
0x18001beb3  lea     rdx, aCreateSocketFa_0; "Create Socket failed: %u"
0x18001beba  mov     ecx, 100000h
0x18001bebf  mov     r8d, eax
0x18001bec2  mov     ebx, eax
0x18001bec4  call    EventWriteError0
0x18001bec9  lock dec cs:dword_1800CA0E8
0x18001bed0  mov     eax, ebx
0x18001bed2  jmp     short loc_18001BE79
0x18001bed4  mov     eax, edi
0x18001bed6  dec     edi
0x18001bed8  test    eax, eax
0x18001beda  jnz     loc_18001BD16
0x18001bee0  call    cs:__imp_GetLastError
0x18001bee7  nop     dword ptr [rax+rax+00h]
0x18001beec  mov     rcx, rbx
0x18001beef  mov     edi, eax
0x18001bef1  call    TeredoDestroyPeerSocket
0x18001bef6  mov     eax, edi
0x18001bef8  jmp     loc_18001BE71
0x18001befd  mov     r8d, eax
0x18001bf00  lea     rdx, aFailedToReadSo; "Failed to read socket name. Error (%d)"
0x18001bf07  mov     ecx, 100000h
0x18001bf0c  call    EventWriteError0
0x18001bf11  jmp     short loc_18001BEE0
0x18001bf13  mov     qword ptr [rsp+78h+dwFlags], rdi
0x18001bf18  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_MAPPING
0x18001bf1f  mov     r9d, 2
0x18001bf25  mov     dword ptr [rsp+78h+g], 4
0x18001bf2d  call    McTemplateU0qqqbr0_EventWriteTransfer
0x18001bf32  jmp     loc_18001BE08
0x18001bf37  mov     ecx, 1Eh; dwErrCode
0x18001bf3c  call    cs:__imp_SetLastError
0x18001bf43  nop     dword ptr [rax+rax+00h]
0x18001bf48  jmp     short loc_18001BEE0
0x18001bf4a  lea     r8, aCreatedPeerSoc; "Created Peer Socket."
0x18001bf51  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001bf58  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001bf5f  call    McTemplateU0z_EventWriteTransfer
0x18001bf64  jmp     loc_18001BE6F
```

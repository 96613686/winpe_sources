# TeredoCreatePeerSocket

- ea: `0x18001bc20`
- end: `0x18001bf59`
- name: `TeredoCreatePeerSocket`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180009000`
- `0x18000d7b0`
- `0x180016ab0`
- `0x1800190e0`
- `0x18001bc20`
- `0x18001caa8`
- `0x18001cb10`
- `0x18001cb80`
- `0x180034380`
- `0x18004b630`
- `0x180051c54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bed0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001be0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001be0d`
- `WS2_32!WSASocketW` at `0x18001bca8`
- `WS2_32!WSASocketW` at `0x18001bca8`
- `WS2_32!__imp_bind` at `0x18001bd28`
- `WS2_32!__imp_bind` at `0x18001bd28`
- `WS2_32!__imp_getsockname` at `0x18001bd76`
- `WS2_32!__imp_getsockname` at `0x18001bd76`
- `WS2_32!__imp_ntohs` at `0x18001bda1`
- `WS2_32!__imp_ntohs` at `0x18001bda1`
- `WS2_32!__imp_setsockopt` at `0x18001bce9`
- `WS2_32!__imp_setsockopt` at `0x18001bce9`

## string_xrefs

- `0x18001bc7e`: `Teredo create peer socket: Creating Socket Device 0x%p Peer 0x%p`
- `0x18001bea3`: `Create Socket failed: %u`
- `0x18001bef0`: `Failed to read socket name. Error (%d)`
- `0x18001bf3a`: `Created Peer Socket.`

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
0x18001bc20  mov     r11, rsp
0x18001bc23  push    rbx
0x18001bc24  push    rdi
0x18001bc25  push    r15
0x18001bc27  sub     rsp, 60h
0x18001bc2b  mov     rax, cs:__security_cookie
0x18001bc32  xor     rax, rsp
0x18001bc35  mov     [rsp+78h+var_20], rax
0x18001bc3a  xor     r15d, r15d
0x18001bc3d  xorps   xmm0, xmm0
0x18001bc40  cmp     cs:dword_1800CA0E8, 0C8h
0x18001bc4a  mov     edi, 1
0x18001bc4f  mov     rbx, rcx
0x18001bc52  mov     dword ptr [rsp+78h+optval], edi
0x18001bc56  movups  xmmword ptr [rsp+78h+name.sa_family], xmm0
0x18001bc5b  mov     [r11-34h], r15d
0x18001bc5f  jge     loc_18001BE90
0x18001bc65  mov     [r11+18h], rsi
0x18001bc69  mov     rsi, [rcx+8]
0x18001bc6d  mov     [r11+20h], r14
0x18001bc71  mov     r14, [rcx]
0x18001bc74  lock inc cs:dword_1800CA0E8
0x18001bc7b  mov     r8, rcx
0x18001bc7e  lea     rdx, aTeredoCreatePe; "Teredo create peer socket: Creating Soc"...
0x18001bc85  mov     ecx, 100000h
0x18001bc8a  mov     r9, rsi
0x18001bc8d  call    EventWrite0
0x18001bc92  mov     edx, 2; type
0x18001bc97  mov     [rsp+78h+dwFlags], edi; dwFlags
0x18001bc9b  mov     ecx, edx; af
0x18001bc9d  mov     dword ptr [rsp+78h+g], r15d; g
0x18001bca2  xor     r9d, r9d; lpProtocolInfo
0x18001bca5  xor     r8d, r8d; protocol
0x18001bca8  call    cs:__imp_WSASocketW
0x18001bcaf  nop     dword ptr [rax+rax+00h]
0x18001bcb4  mov     [rbx+18h], rax
0x18001bcb8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bcbc  jz      loc_18001BE97
0x18001bcc2  lea     r9, [rsp+78h+optval]; optval
0x18001bcc7  mov     [rsp+78h+arg_8], rbp
0x18001bccf  mov     edx, 0FFFFh; level
0x18001bcd4  mov     dword ptr [rsp+78h+optval], edi
0x18001bcd8  mov     r8d, 3005h; optname
0x18001bcde  mov     dword ptr [rsp+78h+g], 4; optlen
0x18001bce6  mov     rcx, rax; s
0x18001bce9  call    cs:__imp_setsockopt
0x18001bcf0  nop     dword ptr [rax+rax+00h]
0x18001bcf5  mov     rcx, [rbx+18h]
0x18001bcf9  call    TeredoEnableRealArrivalIf
0x18001bcfe  test    eax, eax
0x18001bd00  jnz     loc_18001BED0
0x18001bd06  movups  xmm0, xmmword ptr [r14+0A64h]
0x18001bd0e  mov     rcx, [rbx+18h]; s
0x18001bd12  lea     rdx, [rsp+78h+name]; name
0x18001bd17  mov     r8d, 10h; namelen
0x18001bd1d  movups  xmmword ptr [rsp+78h+name.sa_family], xmm0
0x18001bd22  mov     word ptr [rsp+78h+name.sa_data], r15w
0x18001bd28  call    cs:__imp_bind
0x18001bd2f  nop     dword ptr [rax+rax+00h]
0x18001bd34  lea     rdx, aSocketBindFail; "Socket bind failed. Error (%d)"
0x18001bd3b  mov     ecx, 100000h
0x18001bd40  mov     r8d, eax
0x18001bd43  mov     ebp, eax
0x18001bd45  call    EventWriteError0
0x18001bd4a  cmp     ebp, 0FFFFFFFFh
0x18001bd4d  jz      loc_18001BEC4
0x18001bd53  test    ebp, ebp
0x18001bd55  jnz     loc_18001BED0
0x18001bd5b  mov     rcx, [rbx+18h]; s
0x18001bd5f  lea     rdi, [rsi+3E0h]
0x18001bd66  mov     rdx, rdi; name
0x18001bd69  mov     [rsp+78h+namelen], 10h
0x18001bd71  lea     r8, [rsp+78h+namelen]; namelen
0x18001bd76  call    cs:__imp_getsockname
0x18001bd7d  nop     dword ptr [rax+rax+00h]
0x18001bd82  test    eax, eax
0x18001bd84  jnz     loc_18001BEED
0x18001bd8a  lea     rdx, [rsi+14h]
0x18001bd8e  lea     rcx, aPeerIs; "Peer is"
0x18001bd95  call    TeredoTraceAddress
0x18001bd9a  movzx   ecx, word ptr [rsi+3E2h]; netshort
0x18001bda1  call    cs:__imp_ntohs
0x18001bda8  nop     dword ptr [rax+rax+00h]
0x18001bdad  movzx   ecx, byte ptr [rsi+3E7h]
0x18001bdb4  movzx   edx, byte ptr [rsi+3E6h]
0x18001bdbb  movzx   r9d, byte ptr [rsi+3E5h]
0x18001bdc3  movzx   r8d, byte ptr [rsi+3E4h]
0x18001bdcb  movzx   eax, ax
0x18001bdce  mov     [rsp+78h+var_48], eax
0x18001bdd2  mov     [rsp+78h+dwFlags], ecx
0x18001bdd6  mov     ecx, 100000h
0x18001bddb  mov     dword ptr [rsp+78h+g], edx
0x18001bddf  lea     rdx, aPeerSSourceMap; "Peer's source mapping: %d.%d.%d.%d::%d"
0x18001bde6  call    EventWrite0
0x18001bdeb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001bdf2  jnz     loc_18001BF03
0x18001bdf8  mov     rcx, [rbx+18h]; fl
0x18001bdfc  lea     r9, CallbackEnvironment; pcbe
0x18001be03  xor     r8d, r8d; pv
0x18001be06  lea     rdx, TeredoPeerIoComplete; pfnio
0x18001be0d  call    cs:__imp_CreateThreadpoolIo
0x18001be14  nop     dword ptr [rax+rax+00h]
0x18001be19  mov     [rbx+10h], rax
0x18001be1d  test    rax, rax
0x18001be20  jz      loc_18001BED0
0x18001be26  mov     edi, r15d
0x18001be29  xor     edx, edx
0x18001be2b  mov     rcx, rbx
0x18001be2e  call    TeredoPeerPostReceive
0x18001be33  test    eax, eax
0x18001be35  jz      short loc_18001BE3E
0x18001be37  inc     edi
0x18001be39  cmp     edi, 5
0x18001be3c  jl      short loc_18001BE29
0x18001be3e  test    edi, edi
0x18001be40  jz      loc_18001BF27
0x18001be46  movzx   ecx, word ptr [rsi+3E2h]
0x18001be4d  call    TeredoRegisterPeerPortWithFirewall
0x18001be52  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001be59  jnz     loc_18001BF3A
0x18001be5f  xor     eax, eax
0x18001be61  mov     rbp, [rsp+78h+arg_8]
0x18001be69  mov     rsi, [rsp+78h+arg_10]
0x18001be71  mov     r14, [rsp+78h+arg_18]
0x18001be79  mov     rcx, [rsp+78h+var_20]
0x18001be7e  xor     rcx, rsp; StackCookie
0x18001be81  call    __security_check_cookie
0x18001be86  add     rsp, 60h
0x18001be8a  pop     r15
0x18001be8c  pop     rdi
0x18001be8d  pop     rbx
0x18001be8e  retn
0x18001be90  mov     eax, 486h
0x18001be95  jmp     short loc_18001BE79
0x18001be97  call    cs:__imp_GetLastError
0x18001be9e  nop     dword ptr [rax+rax+00h]
0x18001bea3  lea     rdx, aCreateSocketFa_0; "Create Socket failed: %u"
0x18001beaa  mov     ecx, 100000h
0x18001beaf  mov     r8d, eax
0x18001beb2  mov     ebx, eax
0x18001beb4  call    EventWriteError0
0x18001beb9  lock dec cs:dword_1800CA0E8
0x18001bec0  mov     eax, ebx
0x18001bec2  jmp     short loc_18001BE69
0x18001bec4  mov     eax, edi
0x18001bec6  dec     edi
0x18001bec8  test    eax, eax
0x18001beca  jnz     loc_18001BD06
0x18001bed0  call    cs:__imp_GetLastError
0x18001bed7  nop     dword ptr [rax+rax+00h]
0x18001bedc  mov     rcx, rbx
0x18001bedf  mov     edi, eax
0x18001bee1  call    TeredoDestroyPeerSocket
0x18001bee6  mov     eax, edi
0x18001bee8  jmp     loc_18001BE61
0x18001beed  mov     r8d, eax
0x18001bef0  lea     rdx, aFailedToReadSo; "Failed to read socket name. Error (%d)"
0x18001bef7  mov     ecx, 100000h
0x18001befc  call    EventWriteError0
0x18001bf01  jmp     short loc_18001BED0
0x18001bf03  mov     qword ptr [rsp+78h+dwFlags], rdi
0x18001bf08  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_MAPPING
0x18001bf0f  mov     r9d, 2
0x18001bf15  mov     dword ptr [rsp+78h+g], 4
0x18001bf1d  call    McTemplateU0qqqbr0_EventWriteTransfer
0x18001bf22  jmp     loc_18001BDF8
0x18001bf27  mov     ecx, 1Eh; dwErrCode
0x18001bf2c  call    cs:__imp_SetLastError
0x18001bf33  nop     dword ptr [rax+rax+00h]
0x18001bf38  jmp     short loc_18001BED0
0x18001bf3a  lea     r8, aCreatedPeerSoc; "Created Peer Socket."
0x18001bf41  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001bf48  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001bf4f  call    McTemplateU0z_EventWriteTransfer
0x18001bf54  jmp     loc_18001BE5F
```

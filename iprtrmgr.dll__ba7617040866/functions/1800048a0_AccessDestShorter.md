# AccessDestShorter

- ea: `0x1800048a0`
- end: `0x180004cf4`
- name: `AccessDestShorter`
- size: `1108`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x1800048a0`
- `0x18000a308`
- `0x18000ac60`
- `0x180051ec8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004ad2`
- `KERNEL32!HeapFree` at `0x180004c63`
- `KERNEL32!HeapFree` at `0x180004c75`
- `KERNEL32!HeapFree` at `0x180004ad2`
- `KERNEL32!HeapFree` at `0x180004c63`
- `KERNEL32!HeapFree` at `0x180004c75`
- `KERNEL32!HeapAlloc` at `0x180004a07`
- `KERNEL32!HeapAlloc` at `0x180004a90`
- `KERNEL32!HeapAlloc` at `0x180004a07`
- `KERNEL32!HeapAlloc` at `0x180004a90`
- `WS2_32!__imp_ntohl` at `0x180004af1`
- `WS2_32!__imp_ntohl` at `0x180004af1`
- `rtm!RtmGetLessSpecificDestination` at `0x180004bc9`
- `rtm!RtmGetLessSpecificDestination` at `0x180004c11`
- `rtm!RtmGetLessSpecificDestination` at `0x180004bc9`
- `rtm!RtmGetLessSpecificDestination` at `0x180004c11`
- `rtm!RtmReleaseDestInfo` at `0x180004bdb`
- `rtm!RtmReleaseDestInfo` at `0x180004c23`
- `rtm!RtmReleaseDestInfo` at `0x180004bdb`
- `rtm!RtmReleaseDestInfo` at `0x180004c23`
- `rtm!RtmGetMostSpecificDestination` at `0x180004b90`
- `rtm!RtmGetMostSpecificDestination` at `0x180004b90`

## string_xrefs

- `0x180004917`: `AccessDestShorter`
- `0x1800049d8`: `Leaving: AccessDestShorter`
- `0x180004a1e`: `Leaving: AccessDestShorter`
- `0x180004a66`: `Leaving: AccessDestShorter`
- `0x180004aa7`: `Leaving: AccessDestShorter`
- `0x180004c84`: `Leaving: AccessDestShorter`
- `0x180004ca8`: `Leaving: AccessDestShorter`

## pseudocode

```c
__int64 __fastcall AccessDestShorter(int a1, unsigned int a2, _DWORD *a3, unsigned int *a4, __int64 a5, int a6, int a7)
{
  char v11; // r9
  unsigned int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // r12
  unsigned int v16; // ebx
  char v17; // r9
  struct _RTM_DEST_INFO *DestInfo; // rdi
  struct _RTM_DEST_INFO *v19; // r15
  u_long v20; // ecx
  u_long v21; // edx
  USHORT v22; // ax
  u_long v23; // r8d
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  DWORD MostSpecificDestination; // ebx
  int v28; // edx
  unsigned int v29; // esi
  HANDLE v30; // rcx
  bool v31; // cf
  unsigned int v32; // [rsp+30h] [rbp-858h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-854h] BYREF
  struct _RTM_NET_ADDRESS dwBytes_4; // [rsp+38h] [rbp-850h] BYREF
  int v35; // [rsp+50h] [rbp-838h] BYREF
  _BYTE v36[2044]; // [rsp+54h] [rbp-834h] BYREF

  dwBytes = 0;
  v35 = 0;
  memset(&dwBytes_4, 0, sizeof(dwBytes_4));
  memset_0(v36, 0, sizeof(v36));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"Entered: %ws", L"AccessDestShorter");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v35);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  v13 = *a4;
  v32 = 0;
  if ( v13 <= 0xC )
  {
    v15 = 0;
    v14 = 0;
  }
  else
  {
    v14 = (v13 - 12) >> 6;
    v15 = a5 + 8;
    *(_DWORD *)(a5 + 8) = 0;
    v11 = Microsoft_Windows_RRASEnableBits;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v16 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v16 )
    {
      if ( v17 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestShorter");
      return v16;
    }
    DestInfo = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
    if ( !DestInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestShorter");
      return 8;
    }
    dwBytes = 0;
    v16 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v16 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestShorter");
LABEL_26:
      HeapFree(IPRouterHeap, 0, DestInfo);
      return v16;
    }
    v19 = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
    if ( !v19 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessDestShorter");
      v16 = 8;
      goto LABEL_26;
    }
    v20 = a3[2];
    dwBytes_4.AddressFamily = 2;
    *(_DWORD *)dwBytes_4.AddrBits = a3[1];
    v21 = ntohl(v20);
    v22 = 0;
    dwBytes_4.NumBits = 0;
    if ( (v21 & 0x10000) != 0 )
    {
      v22 = 16;
      dwBytes_4.NumBits = 16;
    }
    v23 = v21 << 16;
    if ( (v21 & 0x10000) == 0 )
      v23 = v21;
    if ( (v23 & 0x100) != 0 )
    {
      v22 += 8;
      dwBytes_4.NumBits = v22;
    }
    v24 = v23 << 8;
    if ( (v23 & 0x100) == 0 )
      v24 = v23;
    if ( (v24 & 0x10) != 0 )
    {
      v22 += 4;
      dwBytes_4.NumBits = v22;
    }
    v25 = 16 * v24;
    if ( (v24 & 0x10) == 0 )
      v25 = v24;
    for ( ; v25; v25 *= 2 )
      dwBytes_4.NumBits = ++v22;
    MostSpecificDestination = RtmGetMostSpecificDestination(g_hLocalRoute, &dwBytes_4, a3[4], a3[3], DestInfo);
    while ( !MostSpecificDestination )
    {
      AddDestinationRows((_DWORD)DestInfo, v26, (unsigned int)&v32, v14, v15);
      MostSpecificDestination = RtmGetLessSpecificDestination(g_hLocalRoute, DestInfo->DestHandle, a3[4], a3[3], v19);
      RtmReleaseDestInfo(g_hLocalRoute, DestInfo);
      if ( MostSpecificDestination )
        break;
      AddDestinationRows((_DWORD)v19, v28, (unsigned int)&v32, v14, v15);
      MostSpecificDestination = RtmGetLessSpecificDestination(g_hLocalRoute, v19->DestHandle, a3[4], a3[3], DestInfo);
      RtmReleaseDestInfo(g_hLocalRoute, v19);
    }
    v29 = 0;
    v30 = IPRouterHeap;
    if ( MostSpecificDestination != 1168 )
      v29 = MostSpecificDestination;
    v31 = v14 < v32;
    *a4 = (v32 << 6) + 12;
    if ( v31 )
      v29 = 122;
    HeapFree(v30, 0, DestInfo);
    HeapFree(IPRouterHeap, 0, v19);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessDestShorter");
    return v29;
  }
  else
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessDestShorter");
    return 87;
  }
}

```

## disassembly

```asm
0x1800048a0  mov     [rsp+arg_0], rbx
0x1800048a5  mov     [rsp+arg_8], rsi
0x1800048aa  push    rdi
0x1800048ab  push    r12
0x1800048ad  push    r13
0x1800048af  push    r14
0x1800048b1  push    r15
0x1800048b3  sub     rsp, 860h
0x1800048ba  mov     rax, cs:__security_cookie
0x1800048c1  xor     rax, rsp
0x1800048c4  mov     [rsp+888h+var_38], rax
0x1800048cc  mov     r12, [rsp+888h+arg_20]
0x1800048d4  mov     rsi, r8
0x1800048d7  mov     ebx, edx
0x1800048d9  mov     edi, ecx
0x1800048db  xor     r15d, r15d
0x1800048de  lea     rcx, [rsp+888h+var_834]; void *
0x1800048e3  xorps   xmm0, xmm0
0x1800048e6  mov     dword ptr [rsp+888h+dwBytes.AddressFamily], r15d
0x1800048eb  xor     eax, eax
0x1800048ed  mov     [rsp+888h+var_838], r15d
0x1800048f2  xor     edx, edx; Val
0x1800048f4  mov     [rsp+888h+var_840], eax
0x1800048f8  mov     r8d, 7FCh; Size
0x1800048fe  mov     r13, r9
0x180004901  movups  xmmword ptr [rsp+888h+dwBytes.AddrBits], xmm0
0x180004906  call    memset_0
0x18000490b  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180004912  test    r9b, r9b
0x180004915  jns     short loc_180004960
0x180004917  lea     r8, aAccessdestshor; "AccessDestShorter"
0x18000491e  mov     word ptr [rsp+888h+var_838], r15w
0x180004924  lea     rdx, aEnteredWs; "Entered: %ws"
0x18000492b  lea     rcx, [rsp+888h+var_838]
0x180004930  call    FormatRRASErrorString
0x180004935  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18000493c  test    r9b, r9b
0x18000493f  jns     short loc_180004960
0x180004941  lea     r8, [rsp+888h+var_838]
0x180004946  lea     rdx, RasRtrmgrTraceInfo
0x18000494d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004954  call    McTemplateU0z_EventWriteTransfer
0x180004959  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180004960  cmp     [rsp+888h+arg_30], 57h ; 'W'
0x180004968  jnz     short loc_180004974
0x18000496a  mov     eax, 32h ; '2'
0x18000496f  jmp     loc_180004CC7
0x180004974  mov     eax, [r13+0]
0x180004978  mov     [rsp+888h+var_858], r15d
0x18000497d  cmp     eax, 0Ch
0x180004980  jbe     short loc_18000499B
0x180004982  lea     r14d, [rax-0Ch]
0x180004986  shr     r14d, 6
0x18000498a  add     r12, 8
0x18000498e  mov     [r12], r15d
0x180004992  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180004999  jmp     short loc_1800049A1
0x18000499b  mov     r12, r15
0x18000499e  mov     r14d, r15d
0x1800049a1  shr     ebx, 2
0x1800049a4  mov     eax, 1
0x1800049a9  sub     ebx, eax
0x1800049ab  cmp     ebx, 4
0x1800049ae  jb      loc_180004CA2
0x1800049b4  cmp     edi, eax
0x1800049b6  jnz     loc_180004CA2
0x1800049bc  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x1800049c2  lea     rdx, [rsp+888h+dwBytes]
0x1800049c7  call    RTMSIZEOFDESTINFO
0x1800049cc  mov     ebx, eax
0x1800049ce  test    eax, eax
0x1800049d0  jz      short loc_1800049F9
0x1800049d2  test    r9b, 80h
0x1800049d6  jz      short loc_1800049F2
0x1800049d8  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x1800049df  lea     rdx, RasRtrmgrTraceInfo
0x1800049e6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800049ed  call    McTemplateU0z_EventWriteTransfer
0x1800049f2  mov     eax, ebx
0x1800049f4  jmp     loc_180004CC7
0x1800049f9  mov     r8d, dword ptr [rsp+888h+dwBytes.AddressFamily]; dwBytes
0x1800049fe  xor     edx, edx; dwFlags
0x180004a00  mov     rcx, cs:IPRouterHeap; hHeap
0x180004a07  call    cs:__imp_HeapAlloc
0x180004a0d  mov     rdi, rax
0x180004a10  test    rax, rax
0x180004a13  jnz     short loc_180004A42
0x180004a15  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004a1c  jz      short loc_180004A38
0x180004a1e  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x180004a25  lea     rdx, RasRtrmgrTraceInfo
0x180004a2c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004a33  call    McTemplateU0z_EventWriteTransfer
0x180004a38  mov     eax, 8
0x180004a3d  jmp     loc_180004CC7
0x180004a42  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x180004a48  lea     rdx, [rsp+888h+dwBytes]
0x180004a4d  mov     dword ptr [rsp+888h+dwBytes.AddressFamily], r15d
0x180004a52  call    RTMSIZEOFDESTINFO
0x180004a57  mov     ebx, eax
0x180004a59  test    eax, eax
0x180004a5b  jz      short loc_180004A82
0x180004a5d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004a64  jz      short loc_180004AC6
0x180004a66  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x180004a6d  lea     rdx, RasRtrmgrTraceInfo
0x180004a74  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004a7b  call    McTemplateU0z_EventWriteTransfer
0x180004a80  jmp     short loc_180004AC6
0x180004a82  mov     r8d, dword ptr [rsp+888h+dwBytes.AddressFamily]; dwBytes
0x180004a87  xor     edx, edx; dwFlags
0x180004a89  mov     rcx, cs:IPRouterHeap; hHeap
0x180004a90  call    cs:__imp_HeapAlloc
0x180004a96  mov     r15, rax
0x180004a99  test    rax, rax
0x180004a9c  jnz     short loc_180004ADD
0x180004a9e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004aa5  jz      short loc_180004AC1
0x180004aa7  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x180004aae  lea     rdx, RasRtrmgrTraceInfo
0x180004ab5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004abc  call    McTemplateU0z_EventWriteTransfer
0x180004ac1  mov     ebx, 8
0x180004ac6  mov     rcx, cs:IPRouterHeap; hHeap
0x180004acd  mov     r8, rdi; lpMem
0x180004ad0  xor     edx, edx; dwFlags
0x180004ad2  call    cs:__imp_HeapFree
0x180004ad8  jmp     loc_1800049F2
0x180004add  mov     ecx, [rsi+8]; netlong
0x180004ae0  mov     eax, 2
0x180004ae5  mov     word ptr [rsp+888h+dwBytes.AddrBits], ax
0x180004aea  mov     eax, [rsi+4]
0x180004aed  mov     dword ptr [rsp+888h+dwBytes.AddrBits+4], eax
0x180004af1  call    cs:__imp_ntohl
0x180004af7  mov     edx, eax
0x180004af9  xor     eax, eax
0x180004afb  mov     ecx, edx
0x180004afd  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180004b02  lea     r10d, [rax+10h]
0x180004b06  and     ecx, 10000h
0x180004b0c  jz      short loc_180004B17
0x180004b0e  movzx   eax, r10w
0x180004b12  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180004b17  mov     r8d, edx
0x180004b1a  shl     r8d, 10h
0x180004b1e  test    ecx, ecx
0x180004b20  cmovz   r8d, edx
0x180004b24  mov     r9d, r8d
0x180004b27  and     r9d, 100h
0x180004b2e  jz      short loc_180004B39
0x180004b30  add     ax, 8
0x180004b34  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180004b39  mov     edx, r8d
0x180004b3c  shl     edx, 8
0x180004b3f  test    r9d, r9d
0x180004b42  cmovz   edx, r8d
0x180004b46  mov     r8d, edx
0x180004b49  and     r8d, r10d
0x180004b4c  jz      short loc_180004B57
0x180004b4e  add     ax, 4
0x180004b52  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180004b57  mov     ecx, edx
0x180004b59  shl     ecx, 4
0x180004b5c  test    r8d, r8d
0x180004b5f  cmovz   ecx, edx
0x180004b62  test    ecx, ecx
0x180004b64  jz      short loc_180004B77
0x180004b66  mov     edx, 1
0x180004b6b  add     ax, dx
0x180004b6e  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180004b73  add     ecx, ecx
0x180004b75  jnz     short loc_180004B6B
0x180004b77  mov     r9d, [rsi+0Ch]; TargetViews
0x180004b7b  lea     rdx, [rsp+888h+dwBytes.AddrBits]; DestAddress
0x180004b80  mov     r8d, [rsi+10h]; ProtocolId
0x180004b84  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004b8b  mov     [rsp+888h+DestInfo], rdi; DestInfo
0x180004b90  call    cs:__imp_RtmGetMostSpecificDestination
0x180004b96  mov     ebx, eax
0x180004b98  jmp     loc_180004C29
0x180004b9d  mov     r9d, r14d
0x180004ba0  mov     [rsp+888h+DestInfo], r12
0x180004ba5  lea     r8, [rsp+888h+var_858]
0x180004baa  mov     rcx, rdi
0x180004bad  call    AddDestinationRows
0x180004bb2  mov     r9d, [rsi+0Ch]; TargetViews
0x180004bb6  mov     r8d, [rsi+10h]; ProtocolId
0x180004bba  mov     rdx, [rdi]; DestHandle
0x180004bbd  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004bc4  mov     [rsp+888h+DestInfo], r15; DestInfo
0x180004bc9  call    cs:__imp_RtmGetLessSpecificDestination
0x180004bcf  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004bd6  mov     rdx, rdi; DestInfo
0x180004bd9  mov     ebx, eax
0x180004bdb  call    cs:__imp_RtmReleaseDestInfo
0x180004be1  test    ebx, ebx
0x180004be3  jnz     short loc_180004C31
0x180004be5  mov     r9d, r14d
0x180004be8  mov     [rsp+888h+DestInfo], r12
0x180004bed  lea     r8, [rsp+888h+var_858]
0x180004bf2  mov     rcx, r15
0x180004bf5  call    AddDestinationRows
0x180004bfa  mov     r9d, [rsi+0Ch]; TargetViews
0x180004bfe  mov     r8d, [rsi+10h]; ProtocolId
0x180004c02  mov     rdx, [r15]; DestHandle
0x180004c05  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004c0c  mov     [rsp+888h+DestInfo], rdi; DestInfo
0x180004c11  call    cs:__imp_RtmGetLessSpecificDestination
0x180004c17  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004c1e  mov     rdx, r15; DestInfo
0x180004c21  mov     ebx, eax
0x180004c23  call    cs:__imp_RtmReleaseDestInfo
0x180004c29  test    ebx, ebx
0x180004c2b  jz      loc_180004B9D
0x180004c31  mov     eax, [rsp+888h+var_858]
0x180004c35  xor     esi, esi
0x180004c37  mov     rcx, cs:IPRouterHeap; hHeap
0x180004c3e  cmp     ebx, 490h
0x180004c44  mov     r8, rdi; lpMem
0x180004c47  cmovnz  esi, ebx
0x180004c4a  shl     eax, 6
0x180004c4d  add     eax, 0Ch
0x180004c50  cmp     r14d, [rsp+888h+var_858]
0x180004c55  mov     [r13+0], eax
0x180004c59  mov     eax, 7Ah ; 'z'
0x180004c5e  cmovb   esi, eax
0x180004c61  xor     edx, edx; dwFlags
0x180004c63  call    cs:__imp_HeapFree
0x180004c69  mov     rcx, cs:IPRouterHeap; hHeap
0x180004c70  mov     r8, r15; lpMem
0x180004c73  xor     edx, edx; dwFlags
0x180004c75  call    cs:__imp_HeapFree
0x180004c7b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004c82  jz      short loc_180004C9E
0x180004c84  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x180004c8b  lea     rdx, RasRtrmgrTraceInfo
0x180004c92  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004c99  call    McTemplateU0z_EventWriteTransfer
0x180004c9e  mov     eax, esi
0x180004ca0  jmp     short loc_180004CC7
0x180004ca2  test    r9b, 80h
0x180004ca6  jz      short loc_180004CC2
0x180004ca8  lea     r8, aLeavingAccessd_2; "Leaving: AccessDestShorter"
0x180004caf  lea     rdx, RasRtrmgrTraceInfo
0x180004cb6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004cbd  call    McTemplateU0z_EventWriteTransfer
0x180004cc2  mov     eax, 57h ; 'W'
0x180004cc7  mov     rcx, [rsp+888h+var_38]
0x180004ccf  xor     rcx, rsp; StackCookie
0x180004cd2  call    __security_check_cookie
0x180004cd7  lea     r11, [rsp+888h+var_28]
0x180004cdf  mov     rbx, [r11+30h]
0x180004ce3  mov     rsi, [r11+38h]
0x180004ce7  mov     rsp, r11
0x180004cea  pop     r15
0x180004cec  pop     r14
0x180004cee  pop     r13
0x180004cf0  pop     r12
0x180004cf2  pop     rdi
0x180004cf3  retn
```

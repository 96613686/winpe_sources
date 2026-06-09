# AccessRouteLonger

- ea: `0x180008a70`
- end: `0x180008e29`
- name: `AccessRouteLonger`
- size: `953`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180008a70`
- `0x18000a654`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008d87`
- `KERNEL32!HeapFree` at `0x180008d87`
- `KERNEL32!HeapAlloc` at `0x180008bc5`
- `KERNEL32!HeapAlloc` at `0x180008bc5`
- `WS2_32!__imp_ntohl` at `0x180008c16`
- `WS2_32!__imp_ntohl` at `0x180008c16`
- `rtm!RtmReleaseRoutes` at `0x180008d34`
- `rtm!RtmReleaseRoutes` at `0x180008d34`
- `rtm!RtmGetEnumRoutes` at `0x180008cf4`
- `rtm!RtmGetEnumRoutes` at `0x180008cf4`
- `rtm!RtmCreateRouteEnum` at `0x180008cca`
- `rtm!RtmCreateRouteEnum` at `0x180008cca`
- `rtm!RtmDeleteEnumHandle` at `0x180008d4a`
- `rtm!RtmDeleteEnumHandle` at `0x180008d4a`

## string_xrefs

- `0x180008af3`: `AccessRouteLonger`
- `0x180008bdc`: `Leaving: AccessRouteLonger`
- `0x180008d96`: `Leaving: AccessRouteLonger`
- `0x180008ddd`: `Leaving: AccessRouteLonger`
- `0x180008db8`: `Leaving: AccessRouteLonger: Integer Overflow`

## pseudocode

```c
__int64 __fastcall AccessRouteLonger(int a1, unsigned int a2, _DWORD *a3, _DWORD *a4, __int64 a5, int a6, int a7)
{
  char v11; // al
  __int64 v13; // r12
  unsigned __int64 v14; // rcx
  HANDLE *v15; // rsi
  int v16; // eax
  u_long v17; // ecx
  u_long v18; // edx
  USHORT v19; // ax
  u_long v20; // r8d
  int v21; // edx
  int v22; // ecx
  DWORD i; // edi
  DWORD EnumRoutes; // eax
  UINT v25; // edx
  __int64 v26; // rbx
  DWORD v27; // ebx
  unsigned int NumRoutes; // [rsp+54h] [rbp-864h] BYREF
  HANDLE EnumHandle; // [rsp+58h] [rbp-860h] BYREF
  _DWORD *v30; // [rsp+60h] [rbp-858h]
  struct _RTM_NET_ADDRESS StartDest; // [rsp+68h] [rbp-850h] BYREF
  int v32; // [rsp+80h] [rbp-838h] BYREF
  _BYTE v33[2044]; // [rsp+84h] [rbp-834h] BYREF

  NumRoutes = 0;
  EnumHandle = 0;
  v32 = 0;
  v30 = a4;
  memset(&StartDest, 0, sizeof(StartDest));
  memset_0(v33, 0, sizeof(v33));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"Entered: %ws", L"AccessRouteLonger");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v32);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( *a4 <= 0xCu )
  {
    v13 = 0;
  }
  else
  {
    v13 = a5 + 8;
    *(_DWORD *)(a5 + 8) = 0;
    v11 = Microsoft_Windows_RRASEnableBits;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v14 = 8LL * g_rtmProfile.MaxHandlesInEnum;
    if ( v14 > 0xFFFFFFFF )
    {
      if ( v11 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteLonger: Integer Overflow");
      return 534;
    }
    else
    {
      v15 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v14);
      if ( v15 )
      {
        v16 = a3[1];
        v17 = a3[2];
        StartDest.AddressFamily = 2;
        *(_DWORD *)StartDest.AddrBits = v16;
        v18 = ntohl(v17);
        v19 = 0;
        StartDest.NumBits = 0;
        if ( (v18 & 0x10000) != 0 )
        {
          v19 = 16;
          StartDest.NumBits = 16;
        }
        v20 = v18 << 16;
        if ( (v18 & 0x10000) == 0 )
          v20 = v18;
        if ( (v20 & 0x100) != 0 )
        {
          v19 += 8;
          StartDest.NumBits = v19;
        }
        v21 = v20 << 8;
        if ( (v20 & 0x100) == 0 )
          v21 = v20;
        if ( (v21 & 0x10) != 0 )
        {
          v19 += 4;
          StartDest.NumBits = v19;
        }
        v22 = 16 * v21;
        if ( (v21 & 0x10) == 0 )
          v22 = v21;
        for ( ; v22; v22 *= 2 )
          StartDest.NumBits = ++v19;
        i = RtmCreateRouteEnum(g_hLocalRoute, 0, a3[3], 2u, &StartDest, 0, 0, 0, &EnumHandle);
        if ( !i )
        {
          do
          {
            NumRoutes = g_rtmProfile.MaxHandlesInEnum;
            EnumRoutes = RtmGetEnumRoutes(g_hLocalRoute, EnumHandle, &NumRoutes, v15);
            v25 = NumRoutes;
            v26 = 0;
            for ( i = EnumRoutes; (unsigned int)v26 < NumRoutes; v26 = (unsigned int)(v26 + 1) )
            {
              AddRouteRows(v15[v26], v13);
              v25 = NumRoutes;
            }
            RtmReleaseRoutes(g_hLocalRoute, v25, v15);
          }
          while ( !i );
          RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
        }
        v27 = 0;
        if ( i != 259 )
          v27 = i;
        *v30 = 12;
        HeapFree(IPRouterHeap, 0, v15);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessRouteLonger");
        return v27;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessRouteLonger");
        return 8;
      }
    }
  }
  else
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessRouteLonger");
    return 87;
  }
}

```

## disassembly

```asm
0x180008a70  mov     [rsp+arg_0], rbx
0x180008a75  mov     [rsp+arg_8], rsi
0x180008a7a  push    rdi
0x180008a7b  push    r12
0x180008a7d  push    r13
0x180008a7f  push    r14
0x180008a81  push    r15
0x180008a83  sub     rsp, 890h
0x180008a8a  mov     rax, cs:__security_cookie
0x180008a91  xor     rax, rsp
0x180008a94  mov     [rsp+8B8h+var_38], rax
0x180008a9c  mov     rdi, [rsp+8B8h+arg_20]
0x180008aa4  xor     eax, eax
0x180008aa6  mov     r13, r8
0x180008aa9  mov     dword ptr [rsp+8B8h+var_850.AddrBits+0Ch], eax
0x180008aad  mov     ebx, edx
0x180008aaf  mov     [rsp+8B8h+NumRoutes], eax
0x180008ab3  mov     esi, ecx
0x180008ab5  mov     [rsp+8B8h+EnumHandle], rax
0x180008aba  xorps   xmm0, xmm0
0x180008abd  mov     [rsp+8B8h+var_838], eax
0x180008ac4  xor     edx, edx; Val
0x180008ac6  mov     [rsp+8B8h+var_858], r9
0x180008acb  mov     r8d, 7FCh; Size
0x180008ad1  lea     rcx, [rsp+8B8h+var_834]; void *
0x180008ad9  movups  xmmword ptr [rsp+8B8h+var_850.AddressFamily], xmm0
0x180008ade  mov     r15, r9
0x180008ae1  call    memset_0
0x180008ae6  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180008aed  test    al, al
0x180008aef  jns     short loc_180008B43
0x180008af1  xor     eax, eax
0x180008af3  lea     r8, aAccessroutelon; "AccessRouteLonger"
0x180008afa  lea     rdx, aEnteredWs; "Entered: %ws"
0x180008b01  mov     word ptr [rsp+8B8h+var_838], ax
0x180008b09  lea     rcx, [rsp+8B8h+var_838]
0x180008b11  call    FormatRRASErrorString
0x180008b16  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180008b1d  test    al, al
0x180008b1f  jns     short loc_180008B43
0x180008b21  lea     r8, [rsp+8B8h+var_838]
0x180008b29  lea     rdx, RasRtrmgrTraceInfo
0x180008b30  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008b37  call    McTemplateU0z_EventWriteTransfer
0x180008b3c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180008b43  cmp     [rsp+8B8h+arg_30], 57h ; 'W'
0x180008b4b  jnz     short loc_180008B57
0x180008b4d  mov     eax, 32h ; '2'
0x180008b52  jmp     loc_180008DFC
0x180008b57  mov     ecx, [r15]
0x180008b5a  xor     r14d, r14d
0x180008b5d  mov     [rsp+8B8h+var_868], r14d
0x180008b62  cmp     ecx, 0Ch
0x180008b65  jbe     short loc_180008B80
0x180008b67  lea     r12, [rdi+8]
0x180008b6b  lea     r15d, [rcx-0Ch]
0x180008b6f  mov     [r12], r14d
0x180008b73  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180008b7a  shr     r15d, 6
0x180008b7e  jmp     short loc_180008B86
0x180008b80  xor     r12d, r12d
0x180008b83  xor     r15d, r15d
0x180008b86  shr     ebx, 2
0x180008b89  mov     edi, 1
0x180008b8e  sub     ebx, edi
0x180008b90  cmp     ebx, 4
0x180008b93  jb      loc_180008DD9
0x180008b99  cmp     esi, edi
0x180008b9b  jnz     loc_180008DD9
0x180008ba1  mov     ecx, cs:g_rtmProfile.MaxHandlesInEnum
0x180008ba7  mov     edx, 0FFFFFFFFh
0x180008bac  shl     rcx, 3
0x180008bb0  cmp     rcx, rdx
0x180008bb3  ja      loc_180008DB4
0x180008bb9  mov     r8d, ecx; dwBytes
0x180008bbc  xor     edx, edx; dwFlags
0x180008bbe  mov     rcx, cs:IPRouterHeap; hHeap
0x180008bc5  call    cs:__imp_HeapAlloc
0x180008bcb  mov     rsi, rax
0x180008bce  test    rax, rax
0x180008bd1  jnz     short loc_180008C00
0x180008bd3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008bda  jz      short loc_180008BF6
0x180008bdc  lea     r8, aLeavingAccessr_0; "Leaving: AccessRouteLonger"
0x180008be3  lea     rdx, RasRtrmgrTraceInfo
0x180008bea  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008bf1  call    McTemplateU0z_EventWriteTransfer
0x180008bf6  mov     eax, 8
0x180008bfb  jmp     loc_180008DFC
0x180008c00  mov     eax, [r13+4]
0x180008c04  mov     ebx, 2
0x180008c09  mov     ecx, [r13+8]; netlong
0x180008c0d  mov     [rsp+8B8h+var_850.AddressFamily], bx
0x180008c12  mov     dword ptr [rsp+8B8h+var_850.AddrBits], eax
0x180008c16  call    cs:__imp_ntohl
0x180008c1c  mov     edx, eax
0x180008c1e  lea     r10d, [rbx+0Eh]
0x180008c22  xor     eax, eax
0x180008c24  mov     ecx, edx
0x180008c26  mov     [rsp+8B8h+var_850.NumBits], ax
0x180008c2b  and     ecx, 10000h
0x180008c31  jz      short loc_180008C3C
0x180008c33  movzx   eax, r10w
0x180008c37  mov     [rsp+8B8h+var_850.NumBits], ax
0x180008c3c  mov     r8d, edx
0x180008c3f  shl     r8d, 10h
0x180008c43  test    ecx, ecx
0x180008c45  cmovz   r8d, edx
0x180008c49  mov     r9d, r8d
0x180008c4c  and     r9d, 100h
0x180008c53  jz      short loc_180008C5E
0x180008c55  add     ax, 8
0x180008c59  mov     [rsp+8B8h+var_850.NumBits], ax
0x180008c5e  mov     edx, r8d
0x180008c61  shl     edx, 8
0x180008c64  test    r9d, r9d
0x180008c67  cmovz   edx, r8d
0x180008c6b  mov     r8d, edx
0x180008c6e  and     r8d, r10d
0x180008c71  jz      short loc_180008C7C
0x180008c73  add     ax, 4
0x180008c77  mov     [rsp+8B8h+var_850.NumBits], ax
0x180008c7c  mov     ecx, edx
0x180008c7e  shl     ecx, 4
0x180008c81  test    r8d, r8d
0x180008c84  cmovz   ecx, edx
0x180008c87  test    ecx, ecx
0x180008c89  jz      short loc_180008C97
0x180008c8b  add     ax, di
0x180008c8e  mov     [rsp+8B8h+var_850.NumBits], ax
0x180008c93  add     ecx, ecx
0x180008c95  jnz     short loc_180008C8B
0x180008c97  mov     r8d, [r13+0Ch]; TargetViews
0x180008c9b  lea     rax, [rsp+8B8h+EnumHandle]
0x180008ca0  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180008ca7  mov     r9d, ebx; EnumFlags
0x180008caa  mov     [rsp+8B8h+RtmEnumHandle], rax; RtmEnumHandle
0x180008caf  xor     edx, edx; DestHandle
0x180008cb1  mov     [rsp+8B8h+CriteriaInterface], r14d; CriteriaInterface
0x180008cb6  lea     rax, [rsp+8B8h+var_850]
0x180008cbb  mov     [rsp+8B8h+CriteriaRoute], r14; CriteriaRoute
0x180008cc0  mov     [rsp+8B8h+MatchingFlags], r14d; MatchingFlags
0x180008cc5  mov     [rsp+8B8h+StartDest], rax; StartDest
0x180008cca  call    cs:__imp_RtmCreateRouteEnum
0x180008cd0  mov     edi, eax
0x180008cd2  test    eax, eax
0x180008cd4  jnz     short loc_180008D55
0x180008cd6  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180008cdc  lea     r8, [rsp+8B8h+NumRoutes]; NumRoutes
0x180008ce1  mov     rdx, [rsp+8B8h+EnumHandle]; EnumHandle
0x180008ce6  mov     r9, rsi; RouteHandles
0x180008ce9  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180008cf0  mov     [rsp+8B8h+NumRoutes], eax
0x180008cf4  call    cs:__imp_RtmGetEnumRoutes
0x180008cfa  mov     edx, [rsp+8B8h+NumRoutes]
0x180008cfe  xor     ebx, ebx
0x180008d00  mov     edi, eax
0x180008d02  test    edx, edx
0x180008d04  jz      short loc_180008D2A
0x180008d06  mov     edx, [r13+10h]
0x180008d0a  lea     r8, [rsp+8B8h+var_868]
0x180008d0f  mov     rcx, [rsi+rbx*8]; RouteHandle
0x180008d13  mov     r9d, r15d
0x180008d16  mov     [rsp+8B8h+StartDest], r12; __int64
0x180008d1b  call    AddRouteRows
0x180008d20  mov     edx, [rsp+8B8h+NumRoutes]; NumRoutes
0x180008d24  inc     ebx
0x180008d26  cmp     ebx, edx
0x180008d28  jb      short loc_180008D06
0x180008d2a  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180008d31  mov     r8, rsi; RouteHandles
0x180008d34  call    cs:__imp_RtmReleaseRoutes
0x180008d3a  test    edi, edi
0x180008d3c  jz      short loc_180008CD6
0x180008d3e  mov     rdx, [rsp+8B8h+EnumHandle]; EnumHandle
0x180008d43  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180008d4a  call    cs:__imp_RtmDeleteEnumHandle
0x180008d50  mov     r14d, [rsp+8B8h+var_868]
0x180008d55  mov     rcx, [rsp+8B8h+var_858]
0x180008d5a  xor     ebx, ebx
0x180008d5c  cmp     edi, 103h
0x180008d62  mov     eax, r14d
0x180008d65  mov     r8, rsi; lpMem
0x180008d68  cmovnz  ebx, edi
0x180008d6b  shl     eax, 6
0x180008d6e  add     eax, 0Ch
0x180008d71  mov     [rcx], eax
0x180008d73  cmp     r15d, r14d
0x180008d76  mov     rcx, cs:IPRouterHeap; hHeap
0x180008d7d  mov     eax, 7Ah ; 'z'
0x180008d82  cmovb   ebx, eax
0x180008d85  xor     edx, edx; dwFlags
0x180008d87  call    cs:__imp_HeapFree
0x180008d8d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008d94  jz      short loc_180008DB0
0x180008d96  lea     r8, aLeavingAccessr_0; "Leaving: AccessRouteLonger"
0x180008d9d  lea     rdx, RasRtrmgrTraceInfo
0x180008da4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008dab  call    McTemplateU0z_EventWriteTransfer
0x180008db0  mov     eax, ebx
0x180008db2  jmp     short loc_180008DFC
0x180008db4  test    al, 80h
0x180008db6  jz      short loc_180008DD2
0x180008db8  lea     r8, aLeavingAccessr_2; "Leaving: AccessRouteLonger: Integer Ove"...
0x180008dbf  lea     rdx, RasRtrmgrTraceInfo
0x180008dc6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008dcd  call    McTemplateU0z_EventWriteTransfer
0x180008dd2  mov     eax, 216h
0x180008dd7  jmp     short loc_180008DFC
0x180008dd9  test    al, 80h
0x180008ddb  jz      short loc_180008DF7
0x180008ddd  lea     r8, aLeavingAccessr_0; "Leaving: AccessRouteLonger"
0x180008de4  lea     rdx, RasRtrmgrTraceInfo
0x180008deb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008df2  call    McTemplateU0z_EventWriteTransfer
0x180008df7  mov     eax, 57h ; 'W'
0x180008dfc  mov     rcx, [rsp+8B8h+var_38]
0x180008e04  xor     rcx, rsp; StackCookie
0x180008e07  call    __security_check_cookie
0x180008e0c  lea     r11, [rsp+8B8h+var_28]
0x180008e14  mov     rbx, [r11+30h]
0x180008e18  mov     rsi, [r11+38h]
0x180008e1c  mov     rsp, r11
0x180008e1f  pop     r15
0x180008e21  pop     r14
0x180008e23  pop     r13
0x180008e25  pop     r12
0x180008e27  pop     rdi
0x180008e28  retn
```

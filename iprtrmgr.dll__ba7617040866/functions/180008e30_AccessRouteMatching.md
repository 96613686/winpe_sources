# AccessRouteMatching

- ea: `0x180008e30`
- end: `0x180009144`
- name: `AccessRouteMatching`
- size: `788`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180008e30`
- `0x18000a908`
- `0x18000ac60`
- `0x180051ec8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800090e0`
- `KERNEL32!HeapFree` at `0x1800090e0`
- `KERNEL32!HeapAlloc` at `0x180008f96`
- `KERNEL32!HeapAlloc` at `0x180008f96`
- `WS2_32!__imp_ntohl` at `0x180008fe7`
- `WS2_32!__imp_ntohl` at `0x180008fe7`
- `rtm!RtmGetExactMatchDestination` at `0x180009086`
- `rtm!RtmGetExactMatchDestination` at `0x180009086`

## string_xrefs

- `0x180008ea8`: `AccessRouteMatching`
- `0x180008f67`: `Leaving: AccessRouteMatching`
- `0x180008fad`: `Leaving: AccessRouteMatching`
- `0x1800090f8`: `Leaving: AccessRouteMatching`

## pseudocode

```c
__int64 __fastcall AccessRouteMatching(
        int a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4,
        __int64 a5,
        int a6,
        int a7)
{
  char v11; // r9
  unsigned int v13; // eax
  unsigned int v14; // r14d
  unsigned int v15; // edi
  __int64 v16; // r15
  unsigned int v17; // ebx
  char v18; // r9
  bool v19; // zf
  struct _RTM_DEST_INFO *DestInfo; // rsi
  u_long v21; // ecx
  u_long v22; // edx
  USHORT v23; // ax
  u_long v24; // r8d
  int v25; // edx
  int v26; // ecx
  DWORD ExactMatchDestination; // eax
  unsigned int v28; // eax
  HANDLE v29; // rcx
  unsigned int v30; // [rsp+30h] [rbp-858h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-854h] BYREF
  struct _RTM_NET_ADDRESS dwBytes_4; // [rsp+38h] [rbp-850h] BYREF
  int v33; // [rsp+50h] [rbp-838h] BYREF
  char v34[2044]; // [rsp+54h] [rbp-834h] BYREF

  v33 = 0;
  dwBytes = 0;
  memset(&dwBytes_4, 0, sizeof(dwBytes_4));
  memset_0(v34, 0, sizeof(v34));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"Entered: %ws", L"AccessRouteMatching");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  v13 = *a4;
  v14 = 0;
  v30 = 0;
  if ( v13 <= 0xC )
  {
    v16 = 0;
    v15 = 0;
  }
  else
  {
    v15 = (v13 - 12) >> 6;
    v16 = a5 + 8;
    *(_DWORD *)(a5 + 8) = 0;
    v11 = Microsoft_Windows_RRASEnableBits;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v17 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v17 )
    {
      v19 = v18 >= 0;
LABEL_13:
      if ( !v19 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteMatching");
      return v17;
    }
    DestInfo = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
    if ( DestInfo )
    {
      v21 = a3[2];
      dwBytes_4.AddressFamily = 2;
      *(_DWORD *)dwBytes_4.AddrBits = a3[1];
      v22 = ntohl(v21);
      v23 = 0;
      dwBytes_4.NumBits = 0;
      if ( (v22 & 0x10000) != 0 )
      {
        v23 = 16;
        dwBytes_4.NumBits = 16;
      }
      v24 = v22 << 16;
      if ( (v22 & 0x10000) == 0 )
        v24 = v22;
      if ( (v24 & 0x100) != 0 )
      {
        v23 += 8;
        dwBytes_4.NumBits = v23;
      }
      v25 = v24 << 8;
      if ( (v24 & 0x100) == 0 )
        v25 = v24;
      if ( (v25 & 0x10) != 0 )
      {
        v23 += 4;
        dwBytes_4.NumBits = v23;
      }
      v26 = 16 * v25;
      if ( (v25 & 0x10) == 0 )
        v26 = v25;
      for ( ; v26; v26 *= 2 )
        dwBytes_4.NumBits = ++v23;
      ExactMatchDestination = RtmGetExactMatchDestination(g_hLocalRoute, &dwBytes_4, a3[4], a3[3], DestInfo);
      v17 = ExactMatchDestination;
      if ( ExactMatchDestination == 1168 )
      {
        v17 = 0;
      }
      else if ( !ExactMatchDestination )
      {
        v28 = AddRouteRowsOnDest(&DestInfo->DestHandle, (__int64)a3, (__int64)&v30, v15, v16);
        v14 = v30;
        v17 = v28;
      }
      v29 = IPRouterHeap;
      *a4 = (v14 << 6) + 12;
      if ( v15 < v14 )
        v17 = 122;
      HeapFree(v29, 0, DestInfo);
      v19 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
      goto LABEL_13;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessRouteMatching");
    return 8;
  }
  else
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessRouteMatching");
    return 87;
  }
}

```

## disassembly

```asm
0x180008e30  mov     [rsp+arg_0], rbx
0x180008e35  mov     [rsp+arg_8], rsi
0x180008e3a  push    rdi
0x180008e3b  push    r12
0x180008e3d  push    r13
0x180008e3f  push    r14
0x180008e41  push    r15
0x180008e43  sub     rsp, 860h
0x180008e4a  mov     rax, cs:__security_cookie
0x180008e51  xor     rax, rsp
0x180008e54  mov     [rsp+888h+var_38], rax
0x180008e5c  mov     r15, [rsp+888h+arg_20]
0x180008e64  xor     eax, eax
0x180008e66  mov     r13, r8
0x180008e69  mov     [rsp+888h+var_840], eax
0x180008e6d  mov     ebx, edx
0x180008e6f  mov     [rsp+888h+var_838], eax
0x180008e73  mov     esi, ecx
0x180008e75  mov     dword ptr [rsp+888h+dwBytes.AddressFamily], 0
0x180008e7d  xorps   xmm0, xmm0
0x180008e80  lea     rcx, [rsp+888h+var_834]; void *
0x180008e85  xor     edx, edx; Val
0x180008e87  mov     r8d, 7FCh; Size
0x180008e8d  movups  xmmword ptr [rsp+888h+dwBytes.AddrBits], xmm0
0x180008e92  mov     r12, r9
0x180008e95  call    memset_0
0x180008e9a  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180008ea1  test    r9b, r9b
0x180008ea4  jns     short loc_180008EF0
0x180008ea6  xor     eax, eax
0x180008ea8  lea     r8, aAccessroutemat; "AccessRouteMatching"
0x180008eaf  lea     rdx, aEnteredWs; "Entered: %ws"
0x180008eb6  mov     word ptr [rsp+888h+var_838], ax
0x180008ebb  lea     rcx, [rsp+888h+var_838]
0x180008ec0  call    FormatRRASErrorString
0x180008ec5  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180008ecc  test    r9b, r9b
0x180008ecf  jns     short loc_180008EF0
0x180008ed1  lea     r8, [rsp+888h+var_838]
0x180008ed6  lea     rdx, RasRtrmgrTraceInfo
0x180008edd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008ee4  call    McTemplateU0z_EventWriteTransfer
0x180008ee9  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180008ef0  cmp     [rsp+888h+arg_30], 57h ; 'W'
0x180008ef8  jnz     short loc_180008F04
0x180008efa  mov     eax, 32h ; '2'
0x180008eff  jmp     loc_180009117
0x180008f04  mov     eax, [r12]
0x180008f08  xor     r14d, r14d
0x180008f0b  mov     [rsp+888h+var_858], r14d
0x180008f10  cmp     eax, 0Ch
0x180008f13  jbe     short loc_180008F2B
0x180008f15  lea     edi, [rax-0Ch]
0x180008f18  shr     edi, 6
0x180008f1b  add     r15, 8
0x180008f1f  mov     [r15], r14d
0x180008f22  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180008f29  jmp     short loc_180008F30
0x180008f2b  xor     r15d, r15d
0x180008f2e  xor     edi, edi
0x180008f30  shr     ebx, 2
0x180008f33  mov     eax, 1
0x180008f38  sub     ebx, eax
0x180008f3a  cmp     ebx, 4
0x180008f3d  jb      loc_1800090F2
0x180008f43  cmp     esi, eax
0x180008f45  jnz     loc_1800090F2
0x180008f4b  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x180008f51  lea     rdx, [rsp+888h+dwBytes]
0x180008f56  call    RTMSIZEOFDESTINFO
0x180008f5b  mov     ebx, eax
0x180008f5d  test    eax, eax
0x180008f5f  jz      short loc_180008F88
0x180008f61  test    r9b, 80h
0x180008f65  jz      short loc_180008F81
0x180008f67  lea     r8, aLeavingAccessr; "Leaving: AccessRouteMatching"
0x180008f6e  lea     rdx, RasRtrmgrTraceInfo
0x180008f75  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008f7c  call    McTemplateU0z_EventWriteTransfer
0x180008f81  mov     eax, ebx
0x180008f83  jmp     loc_180009117
0x180008f88  mov     r8d, dword ptr [rsp+888h+dwBytes.AddressFamily]; dwBytes
0x180008f8d  xor     edx, edx; dwFlags
0x180008f8f  mov     rcx, cs:IPRouterHeap; hHeap
0x180008f96  call    cs:__imp_HeapAlloc
0x180008f9c  mov     rsi, rax
0x180008f9f  test    rax, rax
0x180008fa2  jnz     short loc_180008FD1
0x180008fa4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180008fab  jz      short loc_180008FC7
0x180008fad  lea     r8, aLeavingAccessr; "Leaving: AccessRouteMatching"
0x180008fb4  lea     rdx, RasRtrmgrTraceInfo
0x180008fbb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008fc2  call    McTemplateU0z_EventWriteTransfer
0x180008fc7  mov     eax, 8
0x180008fcc  jmp     loc_180009117
0x180008fd1  mov     ecx, [r13+8]; netlong
0x180008fd5  mov     eax, 2
0x180008fda  mov     word ptr [rsp+888h+dwBytes.AddrBits], ax
0x180008fdf  mov     eax, [r13+4]
0x180008fe3  mov     dword ptr [rsp+888h+dwBytes.AddrBits+4], eax
0x180008fe7  call    cs:__imp_ntohl
0x180008fed  mov     edx, eax
0x180008fef  xor     eax, eax
0x180008ff1  mov     ecx, edx
0x180008ff3  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180008ff8  lea     r10d, [rax+10h]
0x180008ffc  and     ecx, 10000h
0x180009002  jz      short loc_18000900D
0x180009004  movzx   eax, r10w
0x180009008  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x18000900d  mov     r8d, edx
0x180009010  shl     r8d, 10h
0x180009014  test    ecx, ecx
0x180009016  cmovz   r8d, edx
0x18000901a  mov     r9d, r8d
0x18000901d  and     r9d, 100h
0x180009024  jz      short loc_18000902F
0x180009026  add     ax, 8
0x18000902a  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x18000902f  mov     edx, r8d
0x180009032  shl     edx, 8
0x180009035  test    r9d, r9d
0x180009038  cmovz   edx, r8d
0x18000903c  mov     r8d, edx
0x18000903f  and     r8d, r10d
0x180009042  jz      short loc_18000904D
0x180009044  add     ax, 4
0x180009048  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x18000904d  mov     ecx, edx
0x18000904f  shl     ecx, 4
0x180009052  test    r8d, r8d
0x180009055  cmovz   ecx, edx
0x180009058  test    ecx, ecx
0x18000905a  jz      short loc_18000906D
0x18000905c  mov     edx, 1
0x180009061  add     ax, dx
0x180009064  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180009069  add     ecx, ecx
0x18000906b  jnz     short loc_180009061
0x18000906d  mov     r9d, [r13+0Ch]; TargetViews
0x180009071  lea     rdx, [rsp+888h+dwBytes.AddrBits]; DestAddress
0x180009076  mov     r8d, [r13+10h]; ProtocolId
0x18000907a  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180009081  mov     [rsp+888h+DestInfo], rsi; DestInfo
0x180009086  call    cs:__imp_RtmGetExactMatchDestination
0x18000908c  mov     ebx, eax
0x18000908e  cmp     eax, 490h
0x180009093  jnz     short loc_180009099
0x180009095  xor     ebx, ebx
0x180009097  jmp     short loc_1800090BC
0x180009099  test    eax, eax
0x18000909b  jnz     short loc_1800090BC
0x18000909d  mov     r9d, edi
0x1800090a0  mov     [rsp+888h+DestInfo], r15
0x1800090a5  lea     r8, [rsp+888h+var_858]
0x1800090aa  mov     rdx, r13
0x1800090ad  mov     rcx, rsi
0x1800090b0  call    AddRouteRowsOnDest
0x1800090b5  mov     r14d, [rsp+888h+var_858]
0x1800090ba  mov     ebx, eax
0x1800090bc  mov     rcx, cs:IPRouterHeap; hHeap
0x1800090c3  mov     eax, r14d
0x1800090c6  shl     eax, 6
0x1800090c9  mov     r8, rsi; lpMem
0x1800090cc  add     eax, 0Ch
0x1800090cf  mov     [r12], eax
0x1800090d3  cmp     edi, r14d
0x1800090d6  mov     eax, 7Ah ; 'z'
0x1800090db  cmovb   ebx, eax
0x1800090de  xor     edx, edx; dwFlags
0x1800090e0  call    cs:__imp_HeapFree
0x1800090e6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800090ed  jmp     loc_180008F65
0x1800090f2  test    r9b, 80h
0x1800090f6  jz      short loc_180009112
0x1800090f8  lea     r8, aLeavingAccessr; "Leaving: AccessRouteMatching"
0x1800090ff  lea     rdx, RasRtrmgrTraceInfo
0x180009106  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000910d  call    McTemplateU0z_EventWriteTransfer
0x180009112  mov     eax, 57h ; 'W'
0x180009117  mov     rcx, [rsp+888h+var_38]
0x18000911f  xor     rcx, rsp; StackCookie
0x180009122  call    __security_check_cookie
0x180009127  lea     r11, [rsp+888h+var_28]
0x18000912f  mov     rbx, [r11+30h]
0x180009133  mov     rsi, [r11+38h]
0x180009137  mov     rsp, r11
0x18000913a  pop     r15
0x18000913c  pop     r14
0x18000913e  pop     r13
0x180009140  pop     r12
0x180009142  pop     rdi
0x180009143  retn
```

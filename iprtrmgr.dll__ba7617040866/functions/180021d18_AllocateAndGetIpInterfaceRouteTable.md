# AllocateAndGetIpInterfaceRouteTable

- ea: `0x180021d18`
- end: `0x1800221b2`
- name: `AllocateAndGetIpInterfaceRouteTable`
- size: `1178`
- prototype: `__int64 __fastcall(int, int, int, int, int, NET_IF_COMPARTMENT_ID CompartmentId)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003e07c`

## callees

- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x180021d18`
- `0x180022f24`
- `0x18004a69c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180022127`
- `KERNEL32!HeapFree` at `0x180022127`
- `KERNEL32!HeapAlloc` at `0x180021fe0`
- `KERNEL32!HeapAlloc` at `0x180021fe0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180021e86`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180021e86`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021e93`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022151`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180021e93`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022151`
- `NSI!NsiAllocateAndGetTable` at `0x180021ee9`
- `NSI!NsiAllocateAndGetTable` at `0x180021ee9`
- `NSI!NsiFreeTable` at `0x180022143`
- `NSI!NsiFreeTable` at `0x180022143`

## string_xrefs

- `0x180021e08`: `AllocateAndGetIpInterfaceRouteTable: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x1800220d3`: `AllocateAndGetIpInterfaceRouteTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180021f7b`: `AllocateAndGetIpInterfaceRouteTable : error 0x%x computing size required for table bytes`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpInterfaceRouteTable(
        LPVOID *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        NET_IF_COMPARTMENT_ID CompartmentId)
{
  int v6; // r12d
  const NPI_MODULEID *v8; // rax
  int v9; // esi
  unsigned int RoutingDomainIdForCompartment; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int Table; // eax
  unsigned int v14; // r14d
  unsigned int v15; // eax
  unsigned __int16 v16; // r14
  HANDLE v17; // r14
  LPVOID v18; // rax
  unsigned int dwBytes; // [rsp+74h] [rbp-8Ch] BYREF
  NET_IF_COMPARTMENT_ID dwBytes_4; // [rsp+78h] [rbp-88h]
  HANDLE hHeap; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  const NPI_MODULEID *v25; // [rsp+98h] [rbp-68h]
  _OWORD v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v27; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v28; // [rsp+C4h] [rbp-3Ch]
  __int128 v29; // [rsp+D4h] [rbp-2Ch]
  int v30; // [rsp+E4h] [rbp-1Ch]
  int v31; // [rsp+F0h] [rbp-10h] BYREF
  char v32[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v6 = 0;
  hHeap = IPRouterHeap;
  dwBytes = 0;
  v23 = 0;
  v24 = 0;
  v8 = &NPI_MS_IPV4_MODULEID;
  v31 = 0;
  v26[0] = 0;
  if ( !a5 )
    v8 = &NPI_MS_IPV6_MODULEID;
  v25 = v8;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v9 = 1;
  v29 = 0;
  v26[1] = 0;
  if ( CompartmentId != 1 )
  {
    if ( gIsRtrMgrEtwEnabled )
    {
      RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(CompartmentId, v26);
      v11 = RoutingDomainIdForCompartment;
      if ( RoutingDomainIdForCompartment )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v31) = 0;
          FormatRRASErrorString(
            &v31,
            L"AllocateAndGetIpInterfaceRouteTable: NsiGetRoutingDomainIdForCompartment failed with error %d",
            RoutingDomainIdForCompartment);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v31);
        }
        return v11;
      }
    }
  }
  LOBYTE(dwBytes_4) = Microsoft_Windows_RRASEnableBits & 0x80;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: AllocateAndGetIpInterfaceRouteTable",
      (unsigned int)v26,
      0,
      (__int64)&v27);
  }
  *a1 = 0;
  dwBytes_4 = GetCurrentThreadCompartmentId();
  v12 = SetCurrentThreadCompartmentId(CompartmentId);
  v11 = v12;
  if ( v12 )
  {
    v9 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v31,
        L"AllocateAndGetIpInterfaceRouteTable: SetCurrentThreadCompartmentId failed and returned %d",
        v12);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v31,
          (unsigned int)v26,
          0,
          (__int64)&v27);
    }
    goto LABEL_31;
  }
  Table = NsiAllocateAndGetTable(1, v25, 16, &v23, a5 != 0 ? 48 : 72, &v24);
  v14 = Table;
  if ( Table )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v31,
        L"AllocateAndGetIpInterfaceRouteTable : error %d returned by NsiAllocateAndGetTable",
        Table);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v31,
          (unsigned int)v26,
          0,
          (__int64)&v27);
    }
    v11 = v14;
LABEL_31:
    v17 = hHeap;
    goto LABEL_32;
  }
  v15 = SizeofInterfaceRouteTable(0, &dwBytes);
  v16 = v15;
  if ( v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v31,
        L"AllocateAndGetIpInterfaceRouteTable : error 0x%x computing size required for table bytes",
        v15);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v31,
          (unsigned int)v26,
          0,
          (__int64)&v27);
    }
    v11 = v16;
    v6 = 1;
    if ( v16 )
      goto LABEL_31;
  }
  else
  {
    v17 = hHeap;
    v18 = HeapAlloc(hHeap, 0, dwBytes);
    *a1 = v18;
    if ( !v18 )
    {
      v11 = 14;
      v6 = 1;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v31, L"AllocateAndGetIpInterfaceRouteTable : error %d allocating %d bytes", 14, dwBytes);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v31,
            (unsigned int)v26,
            0,
            (__int64)&v27);
      }
LABEL_32:
      if ( *a1 )
      {
        HeapFree(v17, 0, *a1);
        *a1 = 0;
      }
      if ( !v6 )
        goto LABEL_36;
      goto LABEL_35;
    }
    *(_DWORD *)*a1 = 0;
  }
LABEL_35:
  NsiFreeTable(v23, v24, 0, 0);
LABEL_36:
  if ( v9 )
    SetCurrentThreadCompartmentId(dwBytes_4);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: AllocateAndGetIpInterfaceRouteTable",
      (unsigned int)v26,
      0,
      (__int64)&v27);
  }
  return v11;
}

```

## disassembly

```asm
0x180021d18  push    rbp
0x180021d1a  push    rbx
0x180021d1b  push    rsi
0x180021d1c  push    rdi
0x180021d1d  push    r12
0x180021d1f  push    r13
0x180021d21  push    r14
0x180021d23  push    r15
0x180021d25  lea     rbp, [rsp-808h]
0x180021d2d  sub     rsp, 908h
0x180021d34  mov     rax, cs:__security_cookie
0x180021d3b  xor     rax, rsp
0x180021d3e  mov     [rbp+840h+var_50], rax
0x180021d45  mov     rax, cs:IPRouterHeap
0x180021d4c  lea     rdx, NPI_MS_IPV6_MODULEID
0x180021d53  xor     r12d, r12d
0x180021d56  mov     [rbp+840h+hHeap], rax
0x180021d5a  mov     r15, rcx
0x180021d5d  mov     dword ptr [rsp+940h+dwBytes], r12d
0x180021d62  mov     ecx, [rbp+840h+arg_20]
0x180021d68  xorps   xmm0, xmm0
0x180021d6b  mov     eax, ecx
0x180021d6d  mov     [rbp+840h+var_8B8], r12
0x180021d71  neg     eax
0x180021d73  mov     [rbp+840h+var_8B0], r12
0x180021d77  lea     rax, NPI_MS_IPV4_MODULEID
0x180021d7e  mov     [rsp+940h+var_8D0], r12d
0x180021d83  sbb     r13d, r13d
0x180021d86  mov     [rbp+840h+var_850], r12d
0x180021d8a  and     r13d, 0FFFFFFE8h
0x180021d8e  mov     r8d, 7FCh; Size
0x180021d94  add     r13d, 48h ; 'H'
0x180021d98  test    ecx, ecx
0x180021d9a  lea     rcx, [rbp+840h+var_84C]; void *
0x180021d9e  movups  [rbp+840h+var_8A0], xmm0
0x180021da2  cmovz   rax, rdx
0x180021da6  xor     edx, edx; Val
0x180021da8  mov     [rbp+840h+var_8A8], rax
0x180021dac  call    memset_0
0x180021db1  mov     r14d, [rbp+840h+CompartmentId]
0x180021db8  xor     eax, eax
0x180021dba  xorps   xmm0, xmm0
0x180021dbd  mov     [rbp+840h+var_880], r12d
0x180021dc1  movups  [rbp+840h+var_87C], xmm0
0x180021dc5  mov     [rbp+840h+var_85C], eax
0x180021dc8  lea     esi, [rax+1]
0x180021dcb  movups  [rbp+840h+var_86C], xmm0
0x180021dcf  movups  [rbp+840h+var_890], xmm0
0x180021dd3  cmp     r14d, esi
0x180021dd6  jz      short loc_180021E41
0x180021dd8  cmp     cs:gIsRtrMgrEtwEnabled, r12d
0x180021ddf  jz      short loc_180021E41
0x180021de1  lea     rdx, [rbp+840h+var_8A0]
0x180021de5  mov     ecx, r14d
0x180021de8  call    NsiGetRoutingDomainIdForCompartment
0x180021ded  mov     ebx, eax
0x180021def  test    eax, eax
0x180021df1  jz      short loc_180021E41
0x180021df3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021dfa  jz      loc_18002218D
0x180021e00  mov     r8d, eax
0x180021e03  mov     word ptr [rbp+840h+var_850], r12w
0x180021e08  lea     rdx, aAllocateandget_0; "AllocateAndGetIpInterfaceRouteTable: Ns"...
0x180021e0f  lea     rcx, [rbp+840h+var_850]
0x180021e13  call    FormatRRASErrorString
0x180021e18  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180021e1f  jz      loc_18002218D
0x180021e25  lea     r8, [rbp+840h+var_850]
0x180021e29  lea     rdx, RasRtrMgrTraceError
0x180021e30  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021e37  call    McTemplateU0z_EventWriteTransfer
0x180021e3c  jmp     loc_18002218D
0x180021e41  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x180021e47  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021e4e  and     al, 80h
0x180021e50  mov     byte ptr [rsp+940h+dwBytes+4], al
0x180021e54  jz      short loc_180021E83
0x180021e56  lea     rax, [rbp+840h+var_880]
0x180021e5a  mov     word ptr [rbp+840h+var_880], r12w
0x180021e5f  mov     [rsp+940h+var_918], rax
0x180021e64  lea     r9, [rbp+840h+var_8A0]
0x180021e68  lea     r8, aEnteredAllocat_0; "Entered: AllocateAndGetIpInterfaceRoute"...
0x180021e6f  mov     [rsp+940h+var_920], r12
0x180021e74  lea     rdx, RasRtrmgrParamTraceInfo
0x180021e7b  mov     rcx, rdi
0x180021e7e  call    McTemplateU0zjzz_EventWriteTransfer
0x180021e83  mov     [r15], r12
0x180021e86  call    cs:__imp_GetCurrentThreadCompartmentId
0x180021e8c  mov     ecx, r14d; CompartmentId
0x180021e8f  mov     dword ptr [rsp+940h+dwBytes+4], eax
0x180021e93  call    cs:__imp_SetCurrentThreadCompartmentId
0x180021e99  xor     ecx, ecx
0x180021e9b  mov     ebx, eax
0x180021e9d  test    eax, eax
0x180021e9f  jnz     loc_1800220BC
0x180021ea5  mov     rdx, [rbp+840h+var_8A8]
0x180021ea9  lea     rax, [rsp+940h+var_8D0]
0x180021eae  mov     [rsp+940h+var_8E0], cl
0x180021eb2  lea     r9, [rbp+840h+var_8B8]
0x180021eb6  mov     [rsp+940h+var_8E8], rax
0x180021ebb  lea     r8d, [rbx+10h]
0x180021ebf  mov     [rsp+940h+var_8F0], ecx
0x180021ec3  lea     rax, [rbp+840h+var_8B0]
0x180021ec7  mov     [rsp+940h+var_8F8], rcx
0x180021ecc  mov     [rsp+940h+var_900], ecx
0x180021ed0  mov     [rsp+940h+var_908], rcx
0x180021ed5  mov     ecx, esi
0x180021ed7  mov     [rsp+940h+var_910], 20h ; ' '
0x180021edf  mov     [rsp+940h+var_918], rax
0x180021ee4  mov     dword ptr [rsp+940h+var_920], r13d
0x180021ee9  call    cs:__imp_NsiAllocateAndGetTable
0x180021eef  xor     r13d, r13d
0x180021ef2  mov     r14d, eax
0x180021ef5  test    eax, eax
0x180021ef7  jz      short loc_180021F55
0x180021ef9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180021f00  jge     short loc_180021F4D
0x180021f02  mov     r8d, eax
0x180021f05  mov     word ptr [rbp+840h+var_850], r13w
0x180021f0a  lea     rdx, aAllocateandget_4; "AllocateAndGetIpInterfaceRouteTable : e"...
0x180021f11  mov     word ptr [rbp+840h+var_880], r13w
0x180021f16  lea     rcx, [rbp+840h+var_850]
0x180021f1a  call    FormatRRASErrorString
0x180021f1f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180021f26  jge     short loc_180021F4D
0x180021f28  lea     rax, [rbp+840h+var_880]
0x180021f2c  mov     rcx, rdi
0x180021f2f  mov     [rsp+940h+var_918], rax
0x180021f34  lea     r9, [rbp+840h+var_8A0]
0x180021f38  lea     r8, [rbp+840h+var_850]
0x180021f3c  mov     [rsp+940h+var_920], r13
0x180021f41  lea     rdx, RasRtrmgrParamTraceInfo
0x180021f48  call    McTemplateU0zjzz_EventWriteTransfer
0x180021f4d  mov     ebx, r14d
0x180021f50  jmp     loc_180022116
0x180021f55  mov     ecx, [rsp+940h+var_8D0]
0x180021f59  lea     rdx, [rsp+940h+dwBytes]
0x180021f5e  call    SizeofInterfaceRouteTable
0x180021f63  mov     r14d, eax
0x180021f66  test    eax, eax
0x180021f68  jz      short loc_180021FD2
0x180021f6a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180021f71  jge     short loc_180021FBE
0x180021f73  mov     r8d, eax
0x180021f76  mov     word ptr [rbp+840h+var_850], r13w
0x180021f7b  lea     rdx, aAllocateandget_12; "AllocateAndGetIpInterfaceRouteTable : e"...
0x180021f82  mov     word ptr [rbp+840h+var_880], r13w
0x180021f87  lea     rcx, [rbp+840h+var_850]
0x180021f8b  call    FormatRRASErrorString
0x180021f90  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180021f97  jge     short loc_180021FBE
0x180021f99  lea     rax, [rbp+840h+var_880]
0x180021f9d  mov     rcx, rdi
0x180021fa0  mov     [rsp+940h+var_918], rax
0x180021fa5  lea     r9, [rbp+840h+var_8A0]
0x180021fa9  lea     r8, [rbp+840h+var_850]
0x180021fad  mov     [rsp+940h+var_920], r13
0x180021fb2  lea     rdx, RasRtrmgrParamTraceInfo
0x180021fb9  call    McTemplateU0zjzz_EventWriteTransfer
0x180021fbe  movzx   ebx, r14w
0x180021fc2  mov     r12d, esi
0x180021fc5  test    ebx, ebx
0x180021fc7  jz      loc_180022135
0x180021fcd  jmp     loc_180022116
0x180021fd2  mov     r14, [rbp+840h+hHeap]
0x180021fd6  xor     edx, edx; dwFlags
0x180021fd8  mov     r8d, dword ptr [rsp+940h+dwBytes]; dwBytes
0x180021fdd  mov     rcx, r14; hHeap
0x180021fe0  call    cs:__imp_HeapAlloc
0x180021fe6  mov     [r15], rax
0x180021fe9  test    rax, rax
0x180021fec  jnz     short loc_18002205A
0x180021fee  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180021ff5  lea     ebx, [rax+0Eh]
0x180021ff8  mov     r12d, esi
0x180021ffb  jge     loc_18002211A
0x180022001  mov     r9d, dword ptr [rsp+940h+dwBytes]
0x180022006  lea     rdx, aAllocateandget_8; "AllocateAndGetIpInterfaceRouteTable : e"...
0x18002200d  mov     r8d, ebx
0x180022010  mov     word ptr [rbp+840h+var_850], r13w
0x180022015  lea     rcx, [rbp+840h+var_850]
0x180022019  mov     word ptr [rbp+840h+var_880], r13w
0x18002201e  call    FormatRRASErrorString
0x180022023  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18002202a  jge     loc_18002211A
0x180022030  lea     rax, [rbp+840h+var_880]
0x180022034  mov     rcx, rdi
0x180022037  mov     [rsp+940h+var_918], rax
0x18002203c  lea     r9, [rbp+840h+var_8A0]
0x180022040  lea     r8, [rbp+840h+var_850]
0x180022044  mov     [rsp+940h+var_920], r13
0x180022049  lea     rdx, RasRtrmgrParamTraceInfo
0x180022050  call    McTemplateU0zjzz_EventWriteTransfer
0x180022055  jmp     loc_18002211A
0x18002205a  mov     ecx, [rsp+940h+var_8D0]
0x18002205e  mov     r14d, r13d
0x180022061  test    ecx, ecx
0x180022063  jz      short loc_1800220B5
0x180022065  mov     r12d, [rbp+840h+arg_20]
0x18002206c  mov     edx, r14d
0x18002206f  lea     r8, [rdx+rdx*8]
0x180022073  test    r12d, r12d
0x180022076  jz      short loc_180022086
0x180022078  lea     rcx, [rdx+rdx*2]
0x18002207c  shl     rcx, 4
0x180022080  add     rcx, [rbp+840h+var_8B8]
0x180022084  jmp     short loc_18002208E
0x180022086  mov     rax, [rbp+840h+var_8B8]
0x18002208a  lea     rcx, [rax+r8*8]
0x18002208e  mov     r9, [r15]
0x180022091  add     r9, 4
0x180022095  shl     rdx, 5
0x180022099  add     rdx, [rbp+840h+var_8B0]
0x18002209d  lea     r9, [r9+r8*8]
0x1800220a1  mov     r8d, r12d
0x1800220a4  call    ConvertRouteKeyToRouteInfo
0x1800220a9  mov     ecx, [rsp+940h+var_8D0]
0x1800220ad  add     r14d, esi
0x1800220b0  cmp     r14d, ecx
0x1800220b3  jb      short loc_18002206C
0x1800220b5  mov     rax, [r15]
0x1800220b8  mov     [rax], ecx
0x1800220ba  jmp     short loc_180022135
0x1800220bc  xor     r13d, r13d
0x1800220bf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800220c6  mov     esi, r13d
0x1800220c9  jge     short loc_180022116
0x1800220cb  mov     r8d, eax
0x1800220ce  mov     word ptr [rbp+840h+var_850], r13w
0x1800220d3  lea     rdx, aAllocateandget_5; "AllocateAndGetIpInterfaceRouteTable: Se"...
0x1800220da  mov     word ptr [rbp+840h+var_880], r13w
0x1800220df  lea     rcx, [rbp+840h+var_850]
0x1800220e3  call    FormatRRASErrorString
0x1800220e8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800220ef  jge     short loc_180022116
0x1800220f1  lea     rax, [rbp+840h+var_880]
0x1800220f5  mov     rcx, rdi
0x1800220f8  mov     [rsp+940h+var_918], rax
0x1800220fd  lea     r9, [rbp+840h+var_8A0]
0x180022101  lea     r8, [rbp+840h+var_850]
0x180022105  mov     [rsp+940h+var_920], r13
0x18002210a  lea     rdx, RasRtrmgrParamTraceInfo
0x180022111  call    McTemplateU0zjzz_EventWriteTransfer
0x180022116  mov     r14, [rbp+840h+hHeap]
0x18002211a  mov     r8, [r15]; lpMem
0x18002211d  test    r8, r8
0x180022120  jz      short loc_180022130
0x180022122  xor     edx, edx; dwFlags
0x180022124  mov     rcx, r14; hHeap
0x180022127  call    cs:__imp_HeapFree
0x18002212d  mov     [r15], r13
0x180022130  test    r12d, r12d
0x180022133  jz      short loc_180022149
0x180022135  mov     rdx, [rbp+840h+var_8B0]
0x180022139  xor     r9d, r9d
0x18002213c  mov     rcx, [rbp+840h+var_8B8]
0x180022140  xor     r8d, r8d
0x180022143  call    cs:__imp_NsiFreeTable
0x180022149  test    esi, esi
0x18002214b  jz      short loc_180022157
0x18002214d  mov     ecx, dword ptr [rsp+940h+dwBytes+4]; CompartmentId
0x180022151  call    cs:__imp_SetCurrentThreadCompartmentId
0x180022157  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002215e  jz      short loc_18002218D
0x180022160  lea     rax, [rbp+840h+var_880]
0x180022164  mov     word ptr [rbp+840h+var_880], r13w
0x180022169  mov     [rsp+940h+var_918], rax
0x18002216e  lea     r9, [rbp+840h+var_8A0]
0x180022172  lea     r8, aLeavingAllocat; "Leaving: AllocateAndGetIpInterfaceRoute"...
0x180022179  mov     [rsp+940h+var_920], r13
0x18002217e  lea     rdx, RasRtrmgrParamTraceInfo
0x180022185  mov     rcx, rdi
0x180022188  call    McTemplateU0zjzz_EventWriteTransfer
0x18002218d  mov     eax, ebx
0x18002218f  mov     rcx, [rbp+840h+var_50]
0x180022196  xor     rcx, rsp; StackCookie
0x180022199  call    __security_check_cookie
0x18002219e  add     rsp, 908h
0x1800221a5  pop     r15
0x1800221a7  pop     r14
0x1800221a9  pop     r13
0x1800221ab  pop     r12
0x1800221ad  pop     rdi
0x1800221ae  pop     rsi
0x1800221af  pop     rbx
0x1800221b0  pop     rbp
0x1800221b1  retn
```

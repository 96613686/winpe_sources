# AccessIpMatchingRoute

- ea: `0x1800061e8`
- end: `0x18000671d`
- name: `AccessIpMatchingRoute`
- size: `1333`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180026794`
- `0x180026c1c`
- `0x1800276bc`

## callees

- `0x1800061e8`
- `0x18000ac60`
- `0x180017aa8`
- `0x180022894`
- `0x1800488c0`
- `0x18004a340`
- `0x18004aeb4`
- `0x180052c3c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800065e8`
- `ntdll!RtlReleaseResource` at `0x1800065e8`
- `ntdll!RtlAcquireResourceShared` at `0x1800065ce`
- `ntdll!RtlAcquireResourceShared` at `0x1800065ce`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180006433`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180006433`

## string_xrefs

- `0x18000626d`: `AccessIpMatchingRoute`
- `0x1800062d5`: `Leaving: AccessIpMatchingRoute`
- `0x1800063e0`: `Leaving: AccessIpMatchingRoute`
- `0x180006685`: `Leaving: AccessIpMatchingRoute`
- `0x1800066bd`: `AccessIpMatchingRoute: Called with invalid buffer size %d for MIB_IPDESTROW`
- `0x1800063a2`: `AccessIpMatchingRoute: Dest %d.%d.%d.%d and Mask %d.%d.%d.%d wrong`
- `0x1800066a8`: `AccessIpMatchingRoute: Protocol %d not valid`
- `0x180006648`: `AccessIpMatchingRoute: Could not set route to RTM: Dest %x\n`
- `0x1800064ec`: `AccessIpMatchingRoute: Could not add or set route to Stack: Dest %x\n`
- `0x180006539`: `AccessIpMatchingRoute: Added Dest %d.%d.%d.%d and Mask %d.%d.%d.%d `
- `0x18000644c`: `AccessIpMatchingRoute: Could not delete route to Stack: Dest %x\n`
- `0x180006499`: `AccessIpMatchingRoute: Deleted Dest %d.%d.%d.%d and Mask %d.%d.%d.%d `

## pseudocode

```c
__int64 __fastcall AccessIpMatchingRoute(
        int a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4,
        _DWORD *a5,
        int a6,
        int a7)
{
  unsigned int v12; // eax
  struct _MIB_IPFORWARDROW *v13; // rdi
  int v14; // r8d
  __int64 v15; // r9
  const wchar_t *v16; // r8
  __int64 dwForwardProto; // r8
  unsigned int v18; // esi
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rdx
  __int64 dwForwardDest_low; // r8
  __int64 v22; // r9
  unsigned int v23; // eax
  void *v24; // r14
  unsigned int BestNextHopMaskGivenIndex; // ebx
  __int64 v26; // r8
  const wchar_t *v27; // rdx
  ULONG v28; // [rsp+20h] [rbp-E0h]
  ULONG v29; // [rsp+20h] [rbp-E0h]
  int dwForwardDest_high; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+28h] [rbp-D8h]
  int dwForwardMask_low; // [rsp+30h] [rbp-D0h]
  int v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+38h] [rbp-C8h]
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+40h] [rbp-C0h]
  int dwForwardMask_high; // [rsp+48h] [rbp-B8h]
  int v39; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v40[60]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int dwForwardDest; // [rsp+9Ch] [rbp-64h]
  unsigned int dwForwardMask; // [rsp+A0h] [rbp-60h]
  int v43; // [rsp+A4h] [rbp-5Ch]
  struct _GUID v44; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v45[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v46; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v47[2044]; // [rsp+104h] [rbp+4h] BYREF

  v44 = GUID_NULL;
  memset_0(v40, 0, 0x48u);
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"Entered: %ws", L"AccessIpMatchingRoute");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v46);
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 9 )
  {
    memset_0(v45, 0, sizeof(v45));
    if ( a2 < 4 || a2 - 4 < 0x14 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return 87;
      dwForwardProto = a2;
      v27 = L"AccessIpMatchingRoute: Called with invalid buffer size %d for MIB_IPDESTROW";
LABEL_63:
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, v27, dwForwardProto);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v16 = (const wchar_t *)&v46;
LABEL_65:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v16);
      }
      return 87;
    }
    v13 = (struct _MIB_IPFORWARDROW *)v45;
    v14 = a3[1];
    v45[1] = a3[2];
    v45[4] = a3[3];
    v45[3] = a3[4];
    v45[6] = a3[5];
    v45[0] = v14;
  }
  else
  {
    v12 = *a4;
    *a4 = 72;
    if ( v12 < 0x48 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIpMatchingRoute");
      return 122;
    }
    v13 = (struct _MIB_IPFORWARDROW *)(a5 + 2);
    *a5 = 31;
    v14 = a5[2];
  }
  if ( (v14 & v13->dwForwardMask) != v14 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v15 = BYTE1(v13->dwForwardDest);
      dwForwardMask_high = HIBYTE(v13->dwForwardMask);
      v36 = BYTE2(v13->dwForwardMask);
      v34 = BYTE1(v13->dwForwardMask);
      dwForwardMask_low = LOBYTE(v13->dwForwardMask);
      dwForwardDest_high = HIBYTE(v13->dwForwardDest);
      v28 = BYTE2(v13->dwForwardDest);
      LOWORD(v46) = 0;
      FormatRRASErrorString(
        &v46,
        L"AccessIpMatchingRoute: Dest %d.%d.%d.%d and Mask %d.%d.%d.%d wrong",
        (unsigned __int8)v14,
        v15,
        v28,
        dwForwardDest_high,
        dwForwardMask_low,
        v34,
        v36,
        dwForwardMask_high);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v46);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 87;
    v16 = L"Leaving: AccessIpMatchingRoute";
    goto LABEL_65;
  }
  dwForwardProto = v13->dwForwardProto;
  if ( (unsigned int)dwForwardProto > 4 )
  {
    v23 = 0;
    v18 = 1;
    while ( v23 < 5 )
    {
      if ( (_DWORD)dwForwardProto == LODWORD(g_rgRtmHandlesV4[2 * v23]) )
      {
        v24 = (void *)g_rgRtmHandlesV4[2 * v23 + 1];
        if ( v24 )
        {
          if ( a1 == 5 || a1 == 7 )
          {
            RtlAcquireResourceShared(&Resource, 1u);
            BestNextHopMaskGivenIndex = GetBestNextHopMaskGivenIndex(v13->dwForwardIfIndex, v13->dwForwardNextHop);
            RtlReleaseResource(&Resource);
            v43 = 1;
            ConvertMibRouteToRouteInfo(v13, v40);
            dwForwardDest = v13[1].dwForwardDest;
            dwForwardMask = v13[1].dwForwardMask;
            v18 = AddRtmRoute(v24, v40, 48, BestNextHopMaskGivenIndex, v13->dwForwardAge, 1u, &v44, 0);
            if ( v18 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v19 = L"AccessIpMatchingRoute: Could not set route to RTM: Dest %x\n";
              goto LABEL_53;
            }
          }
          else if ( a1 == 9 )
          {
            v43 = 1;
            ConvertMibRouteToRouteInfo(v13, v40);
            dwForwardDest = v13[1].dwForwardDest;
            dwForwardMask = v13[1].dwForwardMask;
            v18 = DeleteRtmRoute((int)v24, (int)v40, 1, &v44);
          }
          goto LABEL_56;
        }
        break;
      }
      ++v23;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 87;
    v27 = L"AccessIpMatchingRoute: Protocol %d not valid";
    goto LABEL_63;
  }
  if ( a1 == 5 || a1 == 7 )
  {
    if ( (unsigned int)IsOnLinkRoute(v13, 1) )
      v13->dwForwardNextHop = 0;
    v18 = CreateOrSetIpForwardEntry(v13);
    if ( v18 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_56;
      v19 = L"AccessIpMatchingRoute: Could not add or set route to Stack: Dest %x\n";
LABEL_53:
      v26 = v13->dwForwardDest;
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, v19, v26);
LABEL_54:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v46);
      goto LABEL_56;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_56;
    v39 = HIBYTE(v13->dwForwardMask);
    v37 = BYTE2(v13->dwForwardMask);
    v35 = BYTE1(v13->dwForwardMask);
    v33 = LOBYTE(v13->dwForwardMask);
    v31 = HIBYTE(v13->dwForwardDest);
    v29 = BYTE2(v13->dwForwardDest);
    v20 = L"AccessIpMatchingRoute: Added Dest %d.%d.%d.%d and Mask %d.%d.%d.%d ";
LABEL_33:
    dwForwardDest_low = LOBYTE(v13->dwForwardDest);
    v22 = BYTE1(v13->dwForwardDest);
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, v20, dwForwardDest_low, v22, v29, v31, v33, v35, v37, v39);
    goto LABEL_54;
  }
  if ( a1 == 9 )
  {
    if ( (unsigned int)IsOnLinkRoute(v13, 1) )
      v13->dwForwardNextHop = 0;
    v18 = DeleteIpForwardEntry(v13);
    if ( v18 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_56;
      v19 = L"AccessIpMatchingRoute: Could not delete route to Stack: Dest %x\n";
      goto LABEL_53;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_56;
    v39 = HIBYTE(v13->dwForwardMask);
    v37 = BYTE2(v13->dwForwardMask);
    v35 = BYTE1(v13->dwForwardMask);
    v33 = LOBYTE(v13->dwForwardMask);
    v31 = HIBYTE(v13->dwForwardDest);
    v29 = BYTE2(v13->dwForwardDest);
    v20 = L"AccessIpMatchingRoute: Deleted Dest %d.%d.%d.%d and Mask %d.%d.%d.%d ";
    goto LABEL_33;
  }
  v18 = 1;
LABEL_56:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIpMatchingRoute");
  return v18;
}

```

## disassembly

```asm
0x1800061e8  mov     [rsp-8+arg_0], rbx
0x1800061ed  push    rbp
0x1800061ee  push    rsi
0x1800061ef  push    rdi
0x1800061f0  push    r12
0x1800061f2  push    r13
0x1800061f4  push    r14
0x1800061f6  push    r15
0x1800061f8  lea     rbp, [rsp-810h]
0x180006200  sub     rsp, 910h
0x180006207  mov     rax, cs:__security_cookie
0x18000620e  xor     rax, rsp
0x180006211  mov     [rbp+840h+var_40], rax
0x180006218  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000621f  mov     r15, [rbp+840h+arg_20]
0x180006226  mov     edi, edx
0x180006228  xor     edx, edx; Val
0x18000622a  mov     rsi, r8
0x18000622d  mov     ebx, ecx
0x18000622f  mov     r14, r9
0x180006232  lea     rcx, [rsp+940h+var_8E0]; void *
0x180006237  movdqu  xmmword ptr [rbp+840h+var_890.Data1], xmm0
0x18000623c  lea     r8d, [rdx+48h]; Size
0x180006240  call    memset_0
0x180006245  xor     r12d, r12d
0x180006248  lea     rcx, [rbp+840h+var_83C]; void *
0x18000624c  xor     edx, edx; Val
0x18000624e  mov     [rbp+840h+var_840], r12d
0x180006252  mov     r8d, 7FCh; Size
0x180006258  call    memset_0
0x18000625d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006264  lea     r13, RasRtrmgrTraceInfo
0x18000626b  jge     short loc_1800062A5
0x18000626d  lea     r8, aAccessipmatchi_0; "AccessIpMatchingRoute"
0x180006274  mov     word ptr [rbp+840h+var_840], r12w
0x180006279  lea     rdx, aEnteredWs; "Entered: %ws"
0x180006280  lea     rcx, [rbp+840h+var_840]
0x180006284  call    FormatRRASErrorString
0x180006289  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006290  jge     short loc_1800062A5
0x180006292  lea     r8, [rbp+840h+var_840]
0x180006296  mov     rdx, r13
0x180006299  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800062a0  call    McTemplateU0z_EventWriteTransfer
0x1800062a5  cmp     [rbp+840h+arg_30], 57h ; 'W'
0x1800062ac  jnz     short loc_1800062B8
0x1800062ae  mov     eax, 32h ; '2'
0x1800062b3  jmp     loc_1800066F3
0x1800062b8  cmp     ebx, 9
0x1800062bb  jz      short loc_180006305
0x1800062bd  mov     eax, [r14]
0x1800062c0  mov     dword ptr [r14], 48h ; 'H'
0x1800062c7  cmp     eax, 48h ; 'H'
0x1800062ca  jnb     short loc_1800062F5
0x1800062cc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800062d3  jz      short loc_1800062EB
0x1800062d5  lea     r8, aLeavingAccessi_11; "Leaving: AccessIpMatchingRoute"
0x1800062dc  mov     rdx, r13
0x1800062df  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800062e6  call    McTemplateU0z_EventWriteTransfer
0x1800062eb  mov     eax, 7Ah ; 'z'
0x1800062f0  jmp     loc_1800066F3
0x1800062f5  lea     rdi, [r15+8]
0x1800062f9  mov     dword ptr [r15], 1Fh
0x180006300  mov     r8d, [rdi]
0x180006303  jmp     short loc_18000634D
0x180006305  xor     edx, edx; Val
0x180006307  lea     rcx, [rbp+840h+var_880]; void *
0x18000630b  lea     r8d, [rdx+40h]; Size
0x18000630f  call    memset_0
0x180006314  cmp     edi, 4
0x180006317  jb      loc_1800066B1
0x18000631d  lea     eax, [rdi-4]
0x180006320  cmp     eax, 14h
0x180006323  jb      loc_1800066B1
0x180006329  mov     eax, [rsi+8]
0x18000632c  lea     rdi, [rbp+840h+var_880]
0x180006330  mov     r8d, [rsi+4]
0x180006334  mov     [rbp+840h+var_87C], eax
0x180006337  mov     eax, [rsi+0Ch]
0x18000633a  mov     [rbp+840h+var_870], eax
0x18000633d  mov     eax, [rsi+10h]
0x180006340  mov     [rbp+840h+var_874], eax
0x180006343  mov     eax, [rsi+14h]
0x180006346  mov     [rbp+840h+var_868], eax
0x180006349  mov     [rbp+840h+var_880], r8d
0x18000634d  mov     eax, [rdi+4]
0x180006350  and     eax, r8d
0x180006353  cmp     eax, r8d
0x180006356  jz      loc_1800063EC
0x18000635c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006363  jge     short loc_1800063D3
0x180006365  movzx   ecx, byte ptr [rdi+3]
0x180006369  movzx   edx, byte ptr [rdi+2]
0x18000636d  movzx   r10d, byte ptr [rdi+7]
0x180006372  movzx   r11d, byte ptr [rdi+6]
0x180006377  movzx   ebx, byte ptr [rdi+5]
0x18000637b  movzx   eax, byte ptr [rdi+4]
0x18000637f  movzx   r9d, byte ptr [rdi+1]
0x180006384  mov     [rsp+940h+var_8F8], r10d
0x180006389  mov     [rsp+940h+var_900], r11d
0x18000638e  mov     dword ptr [rsp+940h+var_908], ebx
0x180006392  mov     dword ptr [rsp+940h+var_910], eax
0x180006396  mov     [rsp+940h+var_918], ecx
0x18000639a  lea     rcx, [rbp+840h+var_840]
0x18000639e  mov     [rsp+940h+var_920], edx
0x1800063a2  lea     rdx, aAccessipmatchi_3; "AccessIpMatchingRoute: Dest %d.%d.%d.%d"...
0x1800063a9  movzx   r8d, r8b
0x1800063ad  mov     word ptr [rbp+840h+var_840], r12w
0x1800063b2  call    FormatRRASErrorString
0x1800063b7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800063be  jge     short loc_1800063D3
0x1800063c0  lea     r8, [rbp+840h+var_840]
0x1800063c4  mov     rdx, r13
0x1800063c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800063ce  call    McTemplateU0z_EventWriteTransfer
0x1800063d3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800063da  jz      loc_1800066EE
0x1800063e0  lea     r8, aLeavingAccessi_11; "Leaving: AccessIpMatchingRoute"
0x1800063e7  jmp     loc_1800066DF
0x1800063ec  mov     r8d, [rdi+18h]
0x1800063f0  cmp     r8d, 4
0x1800063f4  ja      loc_180006545
0x1800063fa  cmp     ebx, 5
0x1800063fd  jz      loc_1800064BC
0x180006403  cmp     ebx, 7
0x180006406  jz      loc_1800064BC
0x18000640c  cmp     ebx, 9
0x18000640f  jz      short loc_18000641B
0x180006411  mov     esi, 1
0x180006416  jmp     loc_18000667C
0x18000641b  mov     edx, 1
0x180006420  mov     rcx, rdi
0x180006423  call    IsOnLinkRoute
0x180006428  test    eax, eax
0x18000642a  jz      short loc_180006430
0x18000642c  mov     [rdi+0Ch], r12d
0x180006430  mov     rcx, rdi; pRoute
0x180006433  call    cs:__imp_DeleteIpForwardEntry
0x180006439  mov     esi, eax
0x18000643b  test    eax, eax
0x18000643d  jz      short loc_180006458
0x18000643f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006446  jge     loc_18000667C
0x18000644c  lea     rdx, aAccessipmatchi_1; "AccessIpMatchingRoute: Could not delete"...
0x180006453  jmp     loc_18000664F
0x180006458  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18000645f  jge     loc_18000667C
0x180006465  movzx   edx, byte ptr [rdi+2]
0x180006469  movzx   r10d, byte ptr [rdi+7]
0x18000646e  movzx   r11d, byte ptr [rdi+6]
0x180006473  movzx   ebx, byte ptr [rdi+5]
0x180006477  movzx   eax, byte ptr [rdi+4]
0x18000647b  movzx   ecx, byte ptr [rdi+3]
0x18000647f  mov     [rsp+940h+var_8F8], r10d
0x180006484  mov     [rsp+940h+var_900], r11d
0x180006489  mov     dword ptr [rsp+940h+var_908], ebx
0x18000648d  mov     dword ptr [rsp+940h+var_910], eax
0x180006491  mov     [rsp+940h+var_918], ecx
0x180006495  mov     [rsp+940h+var_920], edx
0x180006499  lea     rdx, aAccessipmatchi_7; "AccessIpMatchingRoute: Deleted Dest %d."...
0x1800064a0  movzx   r8d, byte ptr [rdi]
0x1800064a4  lea     rcx, [rbp+840h+var_840]
0x1800064a8  movzx   r9d, byte ptr [rdi+1]
0x1800064ad  mov     word ptr [rbp+840h+var_840], r12w
0x1800064b2  call    FormatRRASErrorString
0x1800064b7  jmp     loc_180006660
0x1800064bc  mov     edx, 1
0x1800064c1  mov     rcx, rdi
0x1800064c4  call    IsOnLinkRoute
0x1800064c9  test    eax, eax
0x1800064cb  jz      short loc_1800064D1
0x1800064cd  mov     [rdi+0Ch], r12d
0x1800064d1  mov     rcx, rdi
0x1800064d4  call    CreateOrSetIpForwardEntry
0x1800064d9  mov     esi, eax
0x1800064db  test    eax, eax
0x1800064dd  jz      short loc_1800064F8
0x1800064df  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800064e6  jge     loc_18000667C
0x1800064ec  lea     rdx, aAccessipmatchi_5; "AccessIpMatchingRoute: Could not add or"...
0x1800064f3  jmp     loc_18000664F
0x1800064f8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800064ff  jge     loc_18000667C
0x180006505  movzx   edx, byte ptr [rdi+2]
0x180006509  movzx   r10d, byte ptr [rdi+7]
0x18000650e  movzx   r11d, byte ptr [rdi+6]
0x180006513  movzx   ebx, byte ptr [rdi+5]
0x180006517  movzx   eax, byte ptr [rdi+4]
0x18000651b  movzx   ecx, byte ptr [rdi+3]
0x18000651f  mov     [rsp+940h+var_8F8], r10d
0x180006524  mov     [rsp+940h+var_900], r11d
0x180006529  mov     dword ptr [rsp+940h+var_908], ebx
0x18000652d  mov     dword ptr [rsp+940h+var_910], eax
0x180006531  mov     [rsp+940h+var_918], ecx
0x180006535  mov     [rsp+940h+var_920], edx
0x180006539  lea     rdx, aAccessipmatchi_4; "AccessIpMatchingRoute: Added Dest %d.%d"...
0x180006540  jmp     loc_1800064A0
0x180006545  mov     eax, r12d
0x180006548  lea     r14, g_rgRtmHandlesV4
0x18000654f  mov     esi, 1
0x180006554  cmp     eax, 5
0x180006557  jnb     loc_18000669F
0x18000655d  mov     ecx, eax
0x18000655f  add     rcx, rcx
0x180006562  cmp     r8d, [r14+rcx*8]
0x180006566  jz      short loc_18000656C
0x180006568  add     eax, esi
0x18000656a  jmp     short loc_180006554
0x18000656c  mov     r14, [r14+rcx*8+8]
0x180006571  test    r14, r14
0x180006574  jz      loc_18000669F
0x18000657a  cmp     ebx, 5
0x18000657d  jz      short loc_1800065C4
0x18000657f  cmp     ebx, 7
0x180006582  jz      short loc_1800065C4
0x180006584  cmp     ebx, 9
0x180006587  jnz     loc_18000667C
0x18000658d  lea     rdx, [rsp+940h+var_8E0]
0x180006592  mov     [rbp+840h+var_89C], esi
0x180006595  mov     rcx, rdi
0x180006598  call    ConvertMibRouteToRouteInfo
0x18000659d  mov     eax, [rdi+38h]
0x1800065a0  lea     r9, [rbp+840h+var_890]; struct _GUID *
0x1800065a4  mov     [rbp+840h+var_8A4], eax
0x1800065a7  lea     rdx, [rsp+940h+var_8E0]; int
0x1800065ac  mov     eax, [rdi+3Ch]
0x1800065af  mov     r8d, esi; int
0x1800065b2  mov     rcx, r14; int
0x1800065b5  mov     [rbp+840h+var_8A0], eax
0x1800065b8  call    DeleteRtmRoute
0x1800065bd  mov     esi, eax
0x1800065bf  jmp     loc_18000667C
0x1800065c4  mov     dl, sil; Wait
0x1800065c7  lea     rcx, Resource; Resource
0x1800065ce  call    cs:__imp_RtlAcquireResourceShared
0x1800065d4  mov     edx, [rdi+0Ch]
0x1800065d7  mov     ecx, [rdi+10h]
0x1800065da  call    GetBestNextHopMaskGivenIndex
0x1800065df  lea     rcx, Resource; Resource
0x1800065e6  mov     ebx, eax
0x1800065e8  call    cs:__imp_RtlReleaseResource
0x1800065ee  lea     rdx, [rsp+940h+var_8E0]
0x1800065f3  mov     [rbp+840h+var_89C], esi
0x1800065f6  mov     rcx, rdi
0x1800065f9  call    ConvertMibRouteToRouteInfo
0x1800065fe  mov     eax, [rdi+38h]
0x180006601  lea     rdx, [rsp+940h+var_8E0]
0x180006606  mov     [rbp+840h+var_8A4], eax
0x180006609  mov     r9d, ebx
0x18000660c  mov     eax, [rdi+3Ch]
0x18000660f  mov     r8d, 30h ; '0'
0x180006615  mov     [rbp+840h+var_8A0], eax
0x180006618  mov     rcx, r14; RtmRegHandle
0x18000661b  lea     rax, [rbp+840h+var_890]
0x18000661f  mov     [rsp+940h+var_908], r12; __int64
0x180006624  mov     [rsp+940h+var_910], rax; struct _GUID *
0x180006629  mov     eax, [rdi+1Ch]
0x18000662c  mov     [rsp+940h+var_918], esi; int
0x180006630  mov     [rsp+940h+var_920], eax; ULONG
0x180006634  call    AddRtmRoute
0x180006639  mov     esi, eax
0x18000663b  test    eax, eax
0x18000663d  jz      short loc_18000667C
0x18000663f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006646  jge     short loc_18000667C
0x180006648  lea     rdx, aAccessipmatchi; "AccessIpMatchingRoute: Could not set ro"...
0x18000664f  mov     r8d, [rdi]
0x180006652  lea     rcx, [rbp+840h+var_840]
0x180006656  mov     word ptr [rbp+840h+var_840], r12w
0x18000665b  call    FormatRRASErrorString
0x180006660  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180006667  jge     short loc_18000667C
0x180006669  lea     r8, [rbp+840h+var_840]
0x18000666d  mov     rdx, r13
0x180006670  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006677  call    McTemplateU0z_EventWriteTransfer
0x18000667c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006683  jz      short loc_18000669B
0x180006685  lea     r8, aLeavingAccessi_11; "Leaving: AccessIpMatchingRoute"
0x18000668c  mov     rdx, r13
0x18000668f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006696  call    McTemplateU0z_EventWriteTransfer
0x18000669b  mov     eax, esi
0x18000669d  jmp     short loc_1800066F3
0x18000669f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800066a6  jge     short loc_1800066EE
0x1800066a8  lea     rdx, aAccessipmatchi_2; "AccessIpMatchingRoute: Protocol %d not "...
0x1800066af  jmp     short loc_1800066C4
0x1800066b1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800066b8  jge     short loc_1800066EE
0x1800066ba  mov     r8d, edi
0x1800066bd  lea     rdx, aAccessipmatchi_6; "AccessIpMatchingRoute: Called with inva"...
0x1800066c4  lea     rcx, [rbp+840h+var_840]
0x1800066c8  mov     word ptr [rbp+840h+var_840], r12w
0x1800066cd  call    FormatRRASErrorString
0x1800066d2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800066d9  jge     short loc_1800066EE
0x1800066db  lea     r8, [rbp+840h+var_840]
0x1800066df  mov     rdx, r13
  ... truncated ...
```
